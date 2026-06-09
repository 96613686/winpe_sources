# System.Web.HttpWorkerRequest::.cctor

- ea: `0x326a0`
- end: `0x32c51`
- name: `System.Web.HttpWorkerRequest::.cctor`
- size: `1457`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x32650`

## string_xrefs

- `0x32bab`: `User-Agent`
- `0x328ce`: `Cache-Control`
- `0x32bb0`: `HTTP_USER_AGENT`
- `0x326b8`: `Switching Protocols`
- `0x326d9`: `Created`
- `0x32722`: `Moved Permanently`
- `0x32752`: `Temporary Redirect`
- `0x327da`: `Request-Uri Too Long`
- `0x3285d`: `Service Unavailable`
- `0x328d3`: `HTTP_CACHE_CONTROL`

## pseudocode

```c

```

## disassembly

```asm
0x326a0  ldc.i4.6
0x326a1  newarr   string[]
0x326a6  dup
0x326a7  ldc.i4.1
0x326a8  ldc.i4.3
0x326a9  newarr   [mscorlib]System.String
0x326ae  dup
0x326af  ldc.i4.0
0x326b0  ldstr    aContinue// "Continue"
0x326b5  stelem.ref
0x326b6  dup
0x326b7  ldc.i4.1
0x326b8  ldstr    aSwitchingProto// "Switching Protocols"
0x326bd  stelem.ref
0x326be  dup
0x326bf  ldc.i4.2
0x326c0  ldstr    aProcessing// "Processing"
0x326c5  stelem.ref
0x326c6  stelem.ref
0x326c7  dup
0x326c8  ldc.i4.2
0x326c9  ldc.i4.8
0x326ca  newarr   [mscorlib]System.String
0x326cf  dup
0x326d0  ldc.i4.0
0x326d1  ldstr    aOk// "OK"
0x326d6  stelem.ref
0x326d7  dup
0x326d8  ldc.i4.1
0x326d9  ldstr    aCreated// "Created"
0x326de  stelem.ref
0x326df  dup
0x326e0  ldc.i4.2
0x326e1  ldstr    aAccepted// "Accepted"
0x326e6  stelem.ref
0x326e7  dup
0x326e8  ldc.i4.3
0x326e9  ldstr    aNonAuthoritati// "Non-Authoritative Information"
0x326ee  stelem.ref
0x326ef  dup
0x326f0  ldc.i4.4
0x326f1  ldstr    aNoContent// "No Content"
0x326f6  stelem.ref
0x326f7  dup
0x326f8  ldc.i4.5
0x326f9  ldstr    aResetContent// "Reset Content"
0x326fe  stelem.ref
0x326ff  dup
0x32700  ldc.i4.6
0x32701  ldstr    aPartialContent// "Partial Content"
0x32706  stelem.ref
0x32707  dup
0x32708  ldc.i4.7
0x32709  ldstr    aMultiStatus// "Multi-Status"
0x3270e  stelem.ref
0x3270f  stelem.ref
0x32710  dup
0x32711  ldc.i4.3
0x32712  ldc.i4.8
0x32713  newarr   [mscorlib]System.String
0x32718  dup
0x32719  ldc.i4.0
0x3271a  ldstr    aMultipleChoice// "Multiple Choices"
0x3271f  stelem.ref
0x32720  dup
0x32721  ldc.i4.1
0x32722  ldstr    aMovedPermanent// "Moved Permanently"
0x32727  stelem.ref
0x32728  dup
0x32729  ldc.i4.2
0x3272a  ldstr    aFound// "Found"
0x3272f  stelem.ref
0x32730  dup
0x32731  ldc.i4.3
0x32732  ldstr    aSeeOther// "See Other"
0x32737  stelem.ref
0x32738  dup
0x32739  ldc.i4.4
0x3273a  ldstr    aNotModified// "Not Modified"
0x3273f  stelem.ref
0x32740  dup
0x32741  ldc.i4.5
0x32742  ldstr    aUseProxy// "Use Proxy"
0x32747  stelem.ref
0x32748  dup
0x32749  ldc.i4.6
0x3274a  ldsfld   string [mscorlib]System.String::Empty
0x3274f  stelem.ref
0x32750  dup
0x32751  ldc.i4.7
0x32752  ldstr    aTemporaryRedir// "Temporary Redirect"
0x32757  stelem.ref
0x32758  stelem.ref
0x32759  dup
0x3275a  ldc.i4.4
0x3275b  ldc.i4.s 0x19
0x3275d  newarr   [mscorlib]System.String
0x32762  dup
0x32763  ldc.i4.0
0x32764  ldstr    aBadRequest// "Bad Request"
0x32769  stelem.ref
0x3276a  dup
0x3276b  ldc.i4.1
0x3276c  ldstr    aUnauthorized// "Unauthorized"
0x32771  stelem.ref
0x32772  dup
0x32773  ldc.i4.2
0x32774  ldstr    aPaymentRequire// "Payment Required"
0x32779  stelem.ref
0x3277a  dup
0x3277b  ldc.i4.3
0x3277c  ldstr    aForbidden// "Forbidden"
0x32781  stelem.ref
0x32782  dup
0x32783  ldc.i4.4
0x32784  ldstr    aNotFound// "Not Found"
0x32789  stelem.ref
0x3278a  dup
0x3278b  ldc.i4.5
0x3278c  ldstr    aMethodNotAllow_0// "Method Not Allowed"
0x32791  stelem.ref
0x32792  dup
0x32793  ldc.i4.6
0x32794  ldstr    aNotAcceptable// "Not Acceptable"
0x32799  stelem.ref
0x3279a  dup
0x3279b  ldc.i4.7
0x3279c  ldstr    aProxyAuthentic// "Proxy Authentication Required"
0x327a1  stelem.ref
0x327a2  dup
0x327a3  ldc.i4.8
0x327a4  ldstr    aRequestTimeout// "Request Timeout"
0x327a9  stelem.ref
0x327aa  dup
0x327ab  ldc.i4.s 9
0x327ad  ldstr    aConflict// "Conflict"
0x327b2  stelem.ref
0x327b3  dup
0x327b4  ldc.i4.s 0xA
0x327b6  ldstr    aGone// "Gone"
0x327bb  stelem.ref
0x327bc  dup
0x327bd  ldc.i4.s 0xB
0x327bf  ldstr    aLengthRequired// "Length Required"
0x327c4  stelem.ref
0x327c5  dup
0x327c6  ldc.i4.s 0xC
0x327c8  ldstr    aPreconditionFa// "Precondition Failed"
0x327cd  stelem.ref
0x327ce  dup
0x327cf  ldc.i4.s 0xD
0x327d1  ldstr    aRequestEntityT// "Request Entity Too Large"
0x327d6  stelem.ref
0x327d7  dup
0x327d8  ldc.i4.s 0xE
0x327da  ldstr    aRequestUriTooL// "Request-Uri Too Long"
0x327df  stelem.ref
0x327e0  dup
0x327e1  ldc.i4.s 0xF
0x327e3  ldstr    aUnsupportedMed// "Unsupported Media Type"
0x327e8  stelem.ref
0x327e9  dup
0x327ea  ldc.i4.s 0x10
0x327ec  ldstr    aRequestedRange// "Requested Range Not Satisfiable"
0x327f1  stelem.ref
0x327f2  dup
0x327f3  ldc.i4.s 0x11
0x327f5  ldstr    aExpectationFai// "Expectation Failed"
0x327fa  stelem.ref
0x327fb  dup
0x327fc  ldc.i4.s 0x12
0x327fe  ldsfld   string [mscorlib]System.String::Empty
0x32803  stelem.ref
0x32804  dup
0x32805  ldc.i4.s 0x13
0x32807  ldsfld   string [mscorlib]System.String::Empty
0x3280c  stelem.ref
0x3280d  dup
0x3280e  ldc.i4.s 0x14
0x32810  ldsfld   string [mscorlib]System.String::Empty
0x32815  stelem.ref
0x32816  dup
0x32817  ldc.i4.s 0x15
0x32819  ldsfld   string [mscorlib]System.String::Empty
0x3281e  stelem.ref
0x3281f  dup
0x32820  ldc.i4.s 0x16
0x32822  ldstr    aUnprocessableE// "Unprocessable Entity"
0x32827  stelem.ref
0x32828  dup
0x32829  ldc.i4.s 0x17
0x3282b  ldstr    aLocked// "Locked"
0x32830  stelem.ref
0x32831  dup
0x32832  ldc.i4.s 0x18
0x32834  ldstr    aFailedDependen// "Failed Dependency"
0x32839  stelem.ref
0x3283a  stelem.ref
0x3283b  dup
0x3283c  ldc.i4.5
0x3283d  ldc.i4.8
0x3283e  newarr   [mscorlib]System.String
0x32843  dup
0x32844  ldc.i4.0
0x32845  ldstr    aInternalServer// "Internal Server Error"
0x3284a  stelem.ref
0x3284b  dup
0x3284c  ldc.i4.1
0x3284d  ldstr    aNotImplemented// "Not Implemented"
0x32852  stelem.ref
0x32853  dup
0x32854  ldc.i4.2
0x32855  ldstr    aBadGateway// "Bad Gateway"
0x3285a  stelem.ref
0x3285b  dup
0x3285c  ldc.i4.3
0x3285d  ldstr    aServiceUnavail// "Service Unavailable"
0x32862  stelem.ref
0x32863  dup
0x32864  ldc.i4.4
0x32865  ldstr    aGatewayTimeout// "Gateway Timeout"
0x3286a  stelem.ref
0x3286b  dup
0x3286c  ldc.i4.5
0x3286d  ldstr    aHttpVersionNot// "Http Version Not Supported"
0x32872  stelem.ref
0x32873  dup
0x32874  ldc.i4.6
0x32875  ldsfld   string [mscorlib]System.String::Empty
0x3287a  stelem.ref
0x3287b  dup
0x3287c  ldc.i4.7
0x3287d  ldstr    aInsufficientSt// "Insufficient Storage"
0x32882  stelem.ref
0x32883  stelem.ref
0x32884  stsfld   string[][] System.Web.HttpWorkerRequest::s_HTTPStatusDescriptions
0x32889  ldc.i4.s 0x28
0x3288b  newarr   [mscorlib]System.String
0x32890  stsfld   string[] System.Web.HttpWorkerRequest::s_serverVarFromRequestHeaderNames
0x32895  ldc.i4.s 0x28
0x32897  newarr   [mscorlib]System.String
0x3289c  stsfld   string[] System.Web.HttpWorkerRequest::s_requestHeaderNames
0x328a1  ldc.i4.s 0x1E
0x328a3  newarr   [mscorlib]System.String
0x328a8  stsfld   string[] System.Web.HttpWorkerRequest::s_responseHeaderNames
0x328ad  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x328b2  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x328b7  stsfld   class [mscorlib]System.Collections.Hashtable System.Web.HttpWorkerRequest::s_requestHeadersLoookupTable
0x328bc  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x328c1  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x328c6  stsfld   class [mscorlib]System.Collections.Hashtable System.Web.HttpWorkerRequest::s_responseHeadersLoookupTable
0x328cb  ldc.i4.1
0x328cc  ldc.i4.1
0x328cd  ldc.i4.0
0x328ce  ldstr    aCacheControl// "Cache-Control"
0x328d3  ldstr    aHttpCacheContr// "HTTP_CACHE_CONTROL"
0x328d8  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x328dd  ldc.i4.1
0x328de  ldc.i4.1
0x328df  ldc.i4.1
0x328e0  ldstr    aConnection// "Connection"
0x328e5  ldstr    aHttpConnection// "HTTP_CONNECTION"
0x328ea  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x328ef  ldc.i4.1
0x328f0  ldc.i4.1
0x328f1  ldc.i4.2
0x328f2  ldstr    aDate// "Date"
0x328f7  ldstr    aHttpDate// "HTTP_DATE"
0x328fc  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x32901  ldc.i4.1
0x32902  ldc.i4.1
0x32903  ldc.i4.3
0x32904  ldstr    aKeepAlive// "Keep-Alive"
0x32909  ldstr    aHttpKeepAlive// "HTTP_KEEP_ALIVE"
0x3290e  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x32913  ldc.i4.1
0x32914  ldc.i4.1
0x32915  ldc.i4.4
0x32916  ldstr    aPragma// "Pragma"
0x3291b  ldstr    aHttpPragma// "HTTP_PRAGMA"
0x32920  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x32925  ldc.i4.1
0x32926  ldc.i4.1
0x32927  ldc.i4.5
0x32928  ldstr    aTrailer// "Trailer"
0x3292d  ldstr    aHttpTrailer// "HTTP_TRAILER"
0x32932  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x32937  ldc.i4.1
0x32938  ldc.i4.1
0x32939  ldc.i4.6
0x3293a  ldstr    aTransferEncodi// "Transfer-Encoding"
0x3293f  ldstr    aHttpTransferEn// "HTTP_TRANSFER_ENCODING"
0x32944  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x32949  ldc.i4.1
0x3294a  ldc.i4.1
0x3294b  ldc.i4.7
0x3294c  ldstr    aUpgrade// "Upgrade"
0x32951  ldstr    aHttpUpgrade// "HTTP_UPGRADE"
0x32956  call     void System.Web.HttpWorkerRequest::DefineHeader(bool isRequest, bool isResponse, int32 index, string headerName, string serverVarName)
0x3295b  ldc.i4.1
  ... truncated ...
```
