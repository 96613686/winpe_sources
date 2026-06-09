# Microsoft.SharePoint.ServerStub.SPFieldServerStub::InvokeMethod

- ea: `0x4aff0`
- end: `0x4b19e`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::InvokeMethod`
- size: `430`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4af20`
- `0x4af50`
- `0x4af70`
- `0x4af80`
- `0x4af90`
- `0x4afb0`
- `0x4afd0`
- `0x4aff0`

## string_xrefs

- `0x4b04f`: `Update`
- `0x4b109`: `Update`
- `0x4b05b`: `DeleteObject`
- `0x4b125`: `DeleteObject`
- `0x4b043`: `UpdateAndPushChanges`
- `0x4b0ed`: `UpdateAndPushChanges`

## pseudocode

```c

```

## disassembly

```asm
0x4aff0  ldarg.s  4
0x4aff2  brtrue.s loc_4AFFF
0x4aff4  ldstr    aProxycontext// "proxyContext"
0x4aff9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4affe  throw
0x4afff  ldarg.1
0x4b000  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4b005  stloc.0
0x4b006  ldloc.0
0x4b007  brtrue.s loc_4B014
0x4b009  ldstr    aTarget// "target"
0x4b00e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b013  throw
0x4b014  ldarg.0
0x4b015  ldarg.2
0x4b016  ldarg.s  4
0x4b018  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b01d  starg.s  2
0x4b01f  ldarg.2
0x4b020  dup
0x4b021  stloc.1
0x4b022  brfalse  loc_4B190
0x4b027  volatile.
0x4b029  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ddd-1
0x4b02e  brtrue.s loc_4B091
0x4b030  ldc.i4.7
0x4b031  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4b036  dup
0x4b037  ldstr    aValidatesetval// "ValidateSetValue"
0x4b03c  ldc.i4.0
0x4b03d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b042  dup
0x4b043  ldstr    aUpdateandpushc// "UpdateAndPushChanges"
0x4b048  ldc.i4.1
0x4b049  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b04e  dup
0x4b04f  ldstr    aUpdate// "Update"
0x4b054  ldc.i4.2
0x4b055  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b05a  dup
0x4b05b  ldstr    aDeleteobject// "DeleteObject"
0x4b060  ldc.i4.3
0x4b061  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b066  dup
0x4b067  ldstr    aSetshowindispl// "SetShowInDisplayForm"
0x4b06c  ldc.i4.4
0x4b06d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b072  dup
0x4b073  ldstr    aSetshowineditf// "SetShowInEditForm"
0x4b078  ldc.i4.5
0x4b079  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b07e  dup
0x4b07f  ldstr    aSetshowinnewfo// "SetShowInNewForm"
0x4b084  ldc.i4.6
0x4b085  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b08a  volatile.
0x4b08c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ddd-1
0x4b091  volatile.
0x4b093  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ddd-1
0x4b098  ldloc.1
0x4b099  ldloca.s 2
0x4b09b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4b0a0  brfalse  loc_4B190
0x4b0a5  ldloc.2
0x4b0a6  switch   loc_4B0CC, loc_4B0E8, loc_4B104, loc_4B120, loc_4B13C, loc_4B158, loc_4B174
0x4b0c7  br       loc_4B190
0x4b0cc  ldarg.s  5
0x4b0ce  ldc.i4.1
0x4b0cf  stind.i1
0x4b0d0  ldarg.0
0x4b0d1  ldstr    aValidatesetval// "ValidateSetValue"
0x4b0d6  ldarg.s  4
0x4b0d8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b0dd  ldloc.0
0x4b0de  ldarg.3
0x4b0df  ldarg.s  4
0x4b0e1  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::ValidateSetValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b0e6  ldnull
0x4b0e7  ret
0x4b0e8  ldarg.s  5
0x4b0ea  ldc.i4.1
0x4b0eb  stind.i1
0x4b0ec  ldarg.0
0x4b0ed  ldstr    aUpdateandpushc// "UpdateAndPushChanges"
0x4b0f2  ldarg.s  4
0x4b0f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b0f9  ldloc.0
0x4b0fa  ldarg.3
0x4b0fb  ldarg.s  4
0x4b0fd  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::UpdateAndPushChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b102  ldnull
0x4b103  ret
0x4b104  ldarg.s  5
0x4b106  ldc.i4.1
0x4b107  stind.i1
0x4b108  ldarg.0
0x4b109  ldstr    aUpdate// "Update"
0x4b10e  ldarg.s  4
0x4b110  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b115  ldloc.0
0x4b116  ldarg.3
0x4b117  ldarg.s  4
0x4b119  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b11e  ldnull
0x4b11f  ret
0x4b120  ldarg.s  5
0x4b122  ldc.i4.1
0x4b123  stind.i1
0x4b124  ldarg.0
0x4b125  ldstr    aDeleteobject// "DeleteObject"
0x4b12a  ldarg.s  4
0x4b12c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b131  ldloc.0
0x4b132  ldarg.3
0x4b133  ldarg.s  4
0x4b135  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b13a  ldnull
0x4b13b  ret
0x4b13c  ldarg.s  5
0x4b13e  ldc.i4.1
0x4b13f  stind.i1
0x4b140  ldarg.0
0x4b141  ldstr    aSetshowindispl// "SetShowInDisplayForm"
0x4b146  ldarg.s  4
0x4b148  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b14d  ldloc.0
0x4b14e  ldarg.3
0x4b14f  ldarg.s  4
0x4b151  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetShowInDisplayForm_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b156  ldnull
0x4b157  ret
0x4b158  ldarg.s  5
0x4b15a  ldc.i4.1
0x4b15b  stind.i1
0x4b15c  ldarg.0
0x4b15d  ldstr    aSetshowineditf// "SetShowInEditForm"
0x4b162  ldarg.s  4
0x4b164  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b169  ldloc.0
0x4b16a  ldarg.3
0x4b16b  ldarg.s  4
0x4b16d  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetShowInEditForm_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b172  ldnull
0x4b173  ret
0x4b174  ldarg.s  5
0x4b176  ldc.i4.1
0x4b177  stind.i1
0x4b178  ldarg.0
0x4b179  ldstr    aSetshowinnewfo// "SetShowInNewForm"
0x4b17e  ldarg.s  4
0x4b180  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b185  ldloc.0
0x4b186  ldarg.3
0x4b187  ldarg.s  4
0x4b189  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetShowInNewForm_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b18e  ldnull
0x4b18f  ret
0x4b190  ldarg.0
0x4b191  ldarg.1
0x4b192  ldarg.2
0x4b193  ldarg.3
0x4b194  ldarg.s  4
0x4b196  ldarg.s  5
0x4b198  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x4b19d  ret
```
