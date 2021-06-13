# IACV-problem
This is the solution to a problem by IACV Lab IISc. 
A semi-supervised cross-domain adaptation for Image Classification. The Dataset contained images from 7 classes from 4 Domains.
The unlabelled dataset is the Sketch Domain and the training sample consisted of the Image domain.
The Loss functions to be incorporated were as follows:

  (a) standard cross-entropy loss computed on the Labeled Source dataset as LCE(x,y), for x ∈ S.
  (b) weighted cross-entropy loss function computed on the unlabeled Target data, satisfying the condition mentioned here. Let’s say the soft-max output for class-c of an input sample x ∈ T is σc(x). Then, compute:
  σmax(x) = max σc(x) c∈C
  ypred(x) = arg max σc(x) c∈C
  Lweighted−CE(x) = σmax(x).LCE(x,ypred(x)),if σmax(x) ≥ 0.95 = 0, otherwise
  (c) entropy loss computed on the unlabeled Target data as H(x), for x ∈ T .
  
The model should be optimized by jointly minimizing the total loss L = λ1LCE + λ2Lweighted−CE +λ3H,whereλj’s,j=1,2,3arethehyper-parameters,andcan
be obtained according to the classification accuracy on validation set.
