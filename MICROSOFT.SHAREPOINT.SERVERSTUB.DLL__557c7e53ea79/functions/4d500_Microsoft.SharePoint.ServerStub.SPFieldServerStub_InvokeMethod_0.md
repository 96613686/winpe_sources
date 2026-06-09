# Microsoft.SharePoint.ServerStub.SPFieldServerStub::InvokeMethod_0

- ea: `0x4d500`
- end: `0x4d6ae`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::InvokeMethod_0`
- size: `430`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4d430`
- `0x4d460`
- `0x4d480`
- `0x4d490`
- `0x4d4a0`
- `0x4d4c0`
- `0x4d4e0`
- `0x4d500`

## string_xrefs

- `0x4d55f`: `Update`
- `0x4d619`: `Update`
- `0x4d56b`: `DeleteObject`
- `0x4d635`: `DeleteObject`
- `0x4d553`: `UpdateAndPushChanges`
- `0x4d5fd`: `UpdateAndPushChanges`

## pseudocode

```c

```

## disassembly

```asm
0x4d500  ldarg.s  4
0x4d502  brtrue.s loc_4D50F
0x4d504  ldstr    aProxycontext// "proxyContext"
0x4d509  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d50e  throw
0x4d50f  ldarg.1
0x4d510  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4d515  stloc.0
0x4d516  ldloc.0
0x4d517  brtrue.s loc_4D524
0x4d519  ldstr    aTarget// "target"
0x4d51e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d523  throw
0x4d524  ldarg.0
0x4d525  ldarg.2
0x4d526  ldarg.s  4
0x4d528  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d52d  starg.s  2
0x4d52f  ldarg.2
0x4d530  dup
0x4d531  stloc.1
0x4d532  brfalse  loc_4D6A0
0x4d537  volatile.
0x4d539  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000df0-1
0x4d53e  brtrue.s loc_4D5A1
0x4d540  ldc.i4.7
0x4d541  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4d546  dup
0x4d547  ldstr    aValidatesetval// "ValidateSetValue"
0x4d54c  ldc.i4.0
0x4d54d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d552  dup
0x4d553  ldstr    aUpdateandpushc// "UpdateAndPushChanges"
0x4d558  ldc.i4.1
0x4d559  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d55e  dup
0x4d55f  ldstr    aUpdate// "Update"
0x4d564  ldc.i4.2
0x4d565  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d56a  dup
0x4d56b  ldstr    aDeleteobject// "DeleteObject"
0x4d570  ldc.i4.3
0x4d571  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d576  dup
0x4d577  ldstr    aSetshowindispl// "SetShowInDisplayForm"
0x4d57c  ldc.i4.4
0x4d57d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d582  dup
0x4d583  ldstr    aSetshowineditf// "SetShowInEditForm"
0x4d588  ldc.i4.5
0x4d589  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d58e  dup
0x4d58f  ldstr    aSetshowinnewfo// "SetShowInNewForm"
0x4d594  ldc.i4.6
0x4d595  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d59a  volatile.
0x4d59c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000df0-1
0x4d5a1  volatile.
0x4d5a3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000df0-1
0x4d5a8  ldloc.1
0x4d5a9  ldloca.s 2
0x4d5ab  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4d5b0  brfalse  loc_4D6A0
0x4d5b5  ldloc.2
0x4d5b6  switch   loc_4D5DC, loc_4D5F8, loc_4D614, loc_4D630, loc_4D64C, loc_4D668, loc_4D684
0x4d5d7  br       loc_4D6A0
0x4d5dc  ldarg.s  5
0x4d5de  ldc.i4.1
0x4d5df  stind.i1
0x4d5e0  ldarg.0
0x4d5e1  ldstr    aValidatesetval// "ValidateSetValue"
0x4d5e6  ldarg.s  4
0x4d5e8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d5ed  ldloc.0
0x4d5ee  ldarg.3
0x4d5ef  ldarg.s  4
0x4d5f1  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::ValidateSetValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4d5f6  ldnull
0x4d5f7  ret
0x4d5f8  ldarg.s  5
0x4d5fa  ldc.i4.1
0x4d5fb  stind.i1
0x4d5fc  ldarg.0
0x4d5fd  ldstr    aUpdateandpushc// "UpdateAndPushChanges"
0x4d602  ldarg.s  4
0x4d604  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d609  ldloc.0
0x4d60a  ldarg.3
0x4d60b  ldarg.s  4
0x4d60d  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::UpdateAndPushChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4d612  ldnull
0x4d613  ret
0x4d614  ldarg.s  5
0x4d616  ldc.i4.1
0x4d617  stind.i1
0x4d618  ldarg.0
0x4d619  ldstr    aUpdate// "Update"
0x4d61e  ldarg.s  4
0x4d620  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d625  ldloc.0
0x4d626  ldarg.3
0x4d627  ldarg.s  4
0x4d629  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4d62e  ldnull
0x4d62f  ret
0x4d630  ldarg.s  5
0x4d632  ldc.i4.1
0x4d633  stind.i1
0x4d634  ldarg.0
0x4d635  ldstr    aDeleteobject// "DeleteObject"
0x4d63a  ldarg.s  4
0x4d63c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d641  ldloc.0
0x4d642  ldarg.3
0x4d643  ldarg.s  4
0x4d645  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4d64a  ldnull
0x4d64b  ret
0x4d64c  ldarg.s  5
0x4d64e  ldc.i4.1
0x4d64f  stind.i1
0x4d650  ldarg.0
0x4d651  ldstr    aSetshowindispl// "SetShowInDisplayForm"
0x4d656  ldarg.s  4
0x4d658  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d65d  ldloc.0
0x4d65e  ldarg.3
0x4d65f  ldarg.s  4
0x4d661  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetShowInDisplayForm_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4d666  ldnull
0x4d667  ret
0x4d668  ldarg.s  5
0x4d66a  ldc.i4.1
0x4d66b  stind.i1
0x4d66c  ldarg.0
0x4d66d  ldstr    aSetshowineditf// "SetShowInEditForm"
0x4d672  ldarg.s  4
0x4d674  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d679  ldloc.0
0x4d67a  ldarg.3
0x4d67b  ldarg.s  4
0x4d67d  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetShowInEditForm_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4d682  ldnull
0x4d683  ret
0x4d684  ldarg.s  5
0x4d686  ldc.i4.1
0x4d687  stind.i1
0x4d688  ldarg.0
0x4d689  ldstr    aSetshowinnewfo// "SetShowInNewForm"
0x4d68e  ldarg.s  4
0x4d690  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d695  ldloc.0
0x4d696  ldarg.3
0x4d697  ldarg.s  4
0x4d699  call     void Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetShowInNewForm_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPField target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4d69e  ldnull
0x4d69f  ret
0x4d6a0  ldarg.0
0x4d6a1  ldarg.1
0x4d6a2  ldarg.2
0x4d6a3  ldarg.3
0x4d6a4  ldarg.s  4
0x4d6a6  ldarg.s  5
0x4d6a8  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x4d6ad  ret
```
