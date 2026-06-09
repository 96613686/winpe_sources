# System.Web.HttpRequest::SetDynamicCompression

- ea: `0x1c930`
- end: `0x1c97b`
- name: `System.Web.HttpRequest::SetDynamicCompression`
- size: `75`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x28460`
- `0x28c00`
- `0x28cc0`

## callees

- `0x1c930`
- `0x26a60`
- `0x164560`

## string_xrefs

- `0x1c949`: `IIS_EnableDynamicCompression`
- `0x1c965`: `IIS_EnableDynamicCompression`

## pseudocode

```c

```

## disassembly

```asm
0x1c930  ldarg.0
0x1c931  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1c936  isinst   System.Web.Hosting.IIS7WorkerRequest
0x1c93b  stloc.0
0x1c93c  ldloc.0
0x1c93d  brtrue.s loc_1C940
0x1c93f  ret
0x1c940  ldarg.0
0x1c941  ldfld    class System.Web.HttpServerVarsCollection System.Web.HttpRequest::_serverVariables
0x1c946  brtrue.s loc_1C95F
0x1c948  ldloc.0
0x1c949  ldstr    aIisEnabledynam// "IIS_EnableDynamicCompression"
0x1c94e  ldarg.1
0x1c94f  brtrue.s loc_1C958
0x1c951  ldstr    a0// "0"
0x1c956  br.s     loc_1C959
0x1c958  ldnull
0x1c959  callvirt instance void System.Web.Hosting.IIS7WorkerRequest::SetServerVariable(string name, string value)
0x1c95e  ret
0x1c95f  ldarg.0
0x1c960  ldfld    class System.Web.HttpServerVarsCollection System.Web.HttpRequest::_serverVariables
0x1c965  ldstr    aIisEnabledynam// "IIS_EnableDynamicCompression"
0x1c96a  ldarg.1
0x1c96b  brtrue.s loc_1C974
0x1c96d  ldstr    a0// "0"
0x1c972  br.s     loc_1C975
0x1c974  ldnull
0x1c975  callvirt instance void System.Web.HttpServerVarsCollection::SetNoDemand(string name, string value)
0x1c97a  ret
```
