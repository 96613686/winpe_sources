# Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext

- ea: `0x3250`
- end: `0x3260`
- name: `Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext`
- size: `16`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x13d0`
- `0x14f0`
- `0x3260`
- `0x32a0`

## pseudocode

```c

```

## disassembly

```asm
0x3250  ldstr    aRequestcontext// "RequestContext"
0x3255  call     object [mscorlib]System.Runtime.Remoting.Messaging.CallContext::LogicalGetData(string)
0x325a  isinst   Microsoft.BIServer.HostingEnvironment.Request.RequestContext
0x325f  ret
```
