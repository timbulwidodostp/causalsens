# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Sensitivity analyses for (of) causal effects estimates to unmeasured confounding Use causalsens With (In) R Software
install.packages("causalsens")
library("causalsens")
causalsens = read.csv("https://raw.githubusercontent.com/timbulwidodostp/causalsens/main/causalsens/causalsens.csv",sep = ";")
# Estimation Sensitivity analyses for (of) causal effects estimates to unmeasured confounding Use causalsens With (In) R Software
lm <- lm(re78 ~ treat+age + education + black + hispanic + married + nodegree + re74 + re75 + u74 + u75, data = causalsens)
glm <- glm(treat ~ age + education + black + hispanic + married + nodegree + re74 + re75 + u74 + u75, data = causalsens, family = binomial())
alpha <- seq(-4500, 4500, by = 250)
causalsens <- causalsens(lm, glm, ~ age + education, data = causalsens, alpha = alpha, confound = one.sided.att)
par(mfrow=c(1,2))
plot(causalsens, type = "raw", bty = "n")
plot(causalsens, type = "r.squared", bty = "n")
# Sensitivity analyses for (of) causal effects estimates to unmeasured confounding Use causalsens With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished