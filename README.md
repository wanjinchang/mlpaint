# MLPaint: the Real-Time Handwritten Digit Recognizer

MLPaint is an MLDB.ai plugin that does real-time handwritten digit recognition. The plugin was trained on the [MNIST dataset](http://yann.lecun.com/exdb/mnist/). The WebUI allows a user to draw digits and receive real-time predictions as to what digit it most likely is. On top of that, the plugin displays the *explain matrix*, showing the user why the model made the prediction it made. MLPaint is a great example of white-box machine learning.

Some links:

- [Youtube demo](https://www.youtube.com/watch?v=WGdLCXDiDSo)
- The [Recognizing Handwritten Digits demo](https://docs.mldb.ai/ipy/notebooks/_demos/_latest/Real-Time%20Digits%20Recognizer.html) explains the machine learning behind MLPaint

Try *MLPaint* for free! Just create a [free MLDB.ai account](https://mldb.ai/#signup) to launch an instance and run the [Recognizing Handwritten Digits demo](https://docs.mldb.ai/ipy/notebooks/_demos/_latest/Real-Time%20Digits%20Recognizer.html) from within your MLDB instance.

### Installing MLPaint

One way is to the [Recognizing Handwritten Digits demo](https://docs.mldb.ai/ipy/notebooks/_demos/_latest/Real-Time%20Digits%20Recognizer.html) notebook from a running instance of MLDB.

Alternatively, from a notebook running on MLDB, run the following:

```python
from pymldb import Connection
mldb = Connection()

mldb.put("/v1/plugins/mlpaint", {
    "type": "python",
    "params": {
        "address": "git://github.com/mldbai/mlpaint"
    }
})
```

You can then browse to `https://<host:port>/v1/plugins/mlpaint/routes/static/index.html` to access the UI.
