* **v1**: Reproducing IronVenon's results with artificial neural network.
    * Train-test split: test_size=0.2, random_state=0.
    * Standard scaler.
    * fit(X_train, Y_train, batch_size=32, epochs=100).
---
* **v2**: Improving v1.
    * Train-test split: **test_size=0.3**, **random_state=42**, **stratify=Y**. 
    * **MinMax scaler**.
    * fit(X_train, Y_train, batch_size=32, epochs=100, **validation_data=(X_test, Y_test))**.
---
* **v3**: Changing back to Standard scaler.
    * Train-test split: test_size=0.3, random_state=42, stratify=Y. 
    * **Standard scaler**.
    * fit(X_train, Y_train, batch_size=32, epochs=100, validation_data=(X_test, Y_test)).
---
* **v4**: Cross-validation.
    * Train-test split: **test_size=0.2**, random_state=42, stratify=Y. 
    * Standard scaler.
    * fit(X_train, Y_train, batch_size=32, **epochs=150**, validation_data=(X_test, Y_test)).
    * **n_splits=4**.
---
* **v5**: Preparing model for deploy.
    * **Full dataset for training**.
    * Standard scaler.
    * fit(X, Y, batch_size=32, **epochs=1000**)