## Predic-tweet

What is it
---------------

Allow people to tweet a prediction with hash, hold them accountable for revealing its content.

What happens currently
----------------------------


People can commit a public hash to twitter. This allows them to claim in future that a prediction was known to them at point X in time, and allows anyone to verify that claim.

However, this doesn't force predictor to disclose all their predictions, allowing them to engage in p-hacking. 

The predictor can make multiple claims, reveal only the ones which come out true, and depend on the public memory being fickle.

What predic-tweet allows
---------------------------


A predictor can tweet or otherwise disclose a prediction, with guarantees that the prediction will be disclosed in future.

The parties
---------------

1. The predictotor
2. A notary
3. An oracle

The Oracle
---------------

The Oracle is very simple. It publishes a public key on a fixed schedule and the private keys corresponding to the public key after a set delay.

It holds no other knowledge except the private key to be published with the set delay.


How it works
---------------

The predictor publishes the hash of prediction and the encrypted prediction. The encrypted prediction is multi signed by keys of all the three parties.

Predic-tweet makes the following two important guarantees

1. The prediction can be publically verified after publication
2. The prediction can be revealed by any two of the three parties working in tandem.

It holds these other important features

1. Predictor can reveal the prediction at any time. The prediction can be verified by anyone from the original hash
2. The notary can reveal the secret after the Oracle's private keys are revealed, without needed any information from the predictor. The prediction can be verified by anyone from the original hash 
3. The Oracle play no part in the transaction except publishing the keys on shedule. It doesn't even know that its keys are being used in the prediction
4. The predictor and notary together can decide not to reveal the secret. Since two of three signatures are required to reveal the secret, the Oracle's keys can not be used by itself.


Implementation
-----------------

