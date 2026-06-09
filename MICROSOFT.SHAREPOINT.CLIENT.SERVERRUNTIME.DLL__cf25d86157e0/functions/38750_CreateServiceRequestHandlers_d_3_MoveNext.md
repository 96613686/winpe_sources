# <CreateServiceRequestHandlers>d__3::MoveNext

- ea: `0x38750`
- end: `0x38855`
- name: `<CreateServiceRequestHandlers>d__3::MoveNext`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0xe000`
- `0xed10`
- `0x15680`
- `0x38750`
- `0x38880`
- `0x388e0`

## string_xrefs

- `0x387dc`: `Type '{0}' is not a ClientServiceRequestHandler type.`

## pseudocode

```c

```

## disassembly

```asm
0x38750  ldarg.0
0x38751  ldfld    int32 <CreateServiceRequestHandlers>d__3::<>1__state
0x38756  stloc.1
0x38757  ldloc.1
0x38758  switch   loc_3876E, loc_38848, loc_3882B
0x38769  br       loc_38848
0x3876e  ldarg.0
0x3876f  ldc.i4.m1
0x38770  stfld    int32 <CreateServiceRequestHandlers>d__3::<>1__state
0x38775  ldarg.0
0x38776  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <CreateServiceRequestHandlers>d__3::serviceHost
0x3877b  call     void Microsoft.SharePoint.Client.ProxyMap::EnsureInited(class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x38780  ldarg.0
0x38781  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.SharePoint.Client.ProxyMap::s_requestHandlerTypes
0x38786  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::GetEnumerator()
0x3878b  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Type> <CreateServiceRequestHandlers>d__3::<>7__wrap6
0x38790  ldarg.0
0x38791  ldc.i4.1
0x38792  stfld    int32 <CreateServiceRequestHandlers>d__3::<>1__state
0x38797  br       loc_38832
0x3879c  ldarg.0
0x3879d  ldarg.0
0x3879e  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Type> <CreateServiceRequestHandlers>d__3::<>7__wrap6
0x387a3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Type>::get_Current()
0x387a8  stfld    class [mscorlib]System.Type <CreateServiceRequestHandlers>d__3::<type>5__4
0x387ad  ldarg.0
0x387ae  ldarg.0
0x387af  ldfld    class [mscorlib]System.Type <CreateServiceRequestHandlers>d__3::<type>5__4
0x387b4  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x387b9  isinst   Microsoft.SharePoint.Client.ClientServiceProcessingHandler
0x387be  stfld    class Microsoft.SharePoint.Client.ClientServiceProcessingHandler <CreateServiceRequestHandlers>d__3::<handler>5__5
0x387c3  ldarg.0
0x387c4  ldfld    class Microsoft.SharePoint.Client.ClientServiceProcessingHandler <CreateServiceRequestHandlers>d__3::<handler>5__5
0x387c9  brtrue.s loc_38803
0x387cb  ldarg.0
0x387cc  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <CreateServiceRequestHandlers>d__3::serviceHost
0x387d1  ldc.i4   0x18C25E
0x387d6  ldc.i4.1
0x387d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x387dc  ldstr    aType0IsNotACli// "Type '{0}' is not a ClientServiceReques"...
0x387e1  ldc.i4.1
0x387e2  newarr   [mscorlib]System.Object
0x387e7  stloc.2
0x387e8  ldloc.2
0x387e9  ldc.i4.0
0x387ea  ldarg.0
0x387eb  ldfld    class [mscorlib]System.Type <CreateServiceRequestHandlers>d__3::<type>5__4
0x387f0  callvirt instance string [mscorlib]System.Type::get_FullName()
0x387f5  stelem.ref
0x387f6  ldloc.2
0x387f7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x387fc  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x38801  br.s     loc_38832
0x38803  ldarg.0
0x38804  ldfld    class Microsoft.SharePoint.Client.ClientServiceProcessingHandler <CreateServiceRequestHandlers>d__3::<handler>5__5
0x38809  ldarg.0
0x3880a  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <CreateServiceRequestHandlers>d__3::serviceHost
0x3880f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceProcessingHandler::Initialize(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x38814  ldarg.0
0x38815  ldarg.0
0x38816  ldfld    class Microsoft.SharePoint.Client.ClientServiceProcessingHandler <CreateServiceRequestHandlers>d__3::<handler>5__5
0x3881b  stfld    class Microsoft.SharePoint.Client.ClientServiceProcessingHandler <CreateServiceRequestHandlers>d__3::<>2__current
0x38820  ldarg.0
0x38821  ldc.i4.2
0x38822  stfld    int32 <CreateServiceRequestHandlers>d__3::<>1__state
0x38827  ldc.i4.1
0x38828  stloc.0
0x38829  leave.s  loc_38853
0x3882b  ldarg.0
0x3882c  ldc.i4.1
0x3882d  stfld    int32 <CreateServiceRequestHandlers>d__3::<>1__state
0x38832  ldarg.0
0x38833  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Type> <CreateServiceRequestHandlers>d__3::<>7__wrap6
0x38838  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Type>::MoveNext()
0x3883d  brtrue   loc_3879C
0x38842  ldarg.0
0x38843  call     instance void <CreateServiceRequestHandlers>d__3::<>m__Finally7()
0x38848  ldc.i4.0
0x38849  stloc.0
0x3884a  leave.s  loc_38853
0x3884c  ldarg.0
0x3884d  call     instance void <CreateServiceRequestHandlers>d__3::System.IDisposable.Dispose()
0x38852  endfinally
0x38853  ldloc.0
0x38854  ret
```
