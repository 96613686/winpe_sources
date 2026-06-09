# Microsoft.SharePoint.Client.ProxyMap::ProcessClientServiceRequestHandlerAttribute

- ea: `0x16280`
- end: `0x16305`
- name: `Microsoft.SharePoint.Client.ProxyMap::ProcessClientServiceRequestHandlerAttribute`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x15ab0`

## callees

- `0xe000`
- `0xeda0`
- `0x16280`

## string_xrefs

- `0x162c2`: `Found client service request handler type {0}`

## pseudocode

```c

```

## disassembly

```asm
0x16280  ldarg.0
0x16281  ldtoken  Microsoft.SharePoint.Client.ClientServiceProcessingHandlerTypeAttribute
0x16286  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1628b  ldc.i4.0
0x1628c  callvirt instance object[] [mscorlib]System.Reflection.Assembly::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x16291  stloc.0
0x16292  ldloc.0
0x16293  brfalse.s loc_16304
0x16295  ldloc.0
0x16296  stloc.2
0x16297  ldc.i4.0
0x16298  stloc.3
0x16299  br.s     loc_162FE
0x1629b  ldloc.2
0x1629c  ldloc.3
0x1629d  ldelem.ref
0x1629e  castclass Microsoft.SharePoint.Client.ClientServiceProcessingHandlerTypeAttribute
0x162a3  stloc.1
0x162a4  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.SharePoint.Client.ProxyMap::s_requestHandlerTypes
0x162a9  ldloc.1
0x162aa  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientServiceProcessingHandlerTypeAttribute::get_ProcessingHandlerType()
0x162af  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Contains(var<u1>)
0x162b4  brtrue.s loc_162FA
0x162b6  ldarg.1
0x162b7  ldc.i4   0x18C25C
0x162bc  ldc.i4.3
0x162bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x162c2  ldstr    aFoundClientSer// "Found client service request handler ty"...
0x162c7  ldc.i4.1
0x162c8  newarr   [mscorlib]System.Object
0x162cd  stloc.s  4
0x162cf  ldloc.s  4
0x162d1  ldc.i4.0
0x162d2  ldloc.1
0x162d3  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientServiceProcessingHandlerTypeAttribute::get_ProcessingHandlerType()
0x162d8  callvirt instance string [mscorlib]System.Type::get_FullName()
0x162dd  stelem.ref
0x162de  ldloc.s  4
0x162e0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x162e5  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x162ea  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type> Microsoft.SharePoint.Client.ProxyMap::s_requestHandlerTypes
0x162ef  ldloc.1
0x162f0  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientServiceProcessingHandlerTypeAttribute::get_ProcessingHandlerType()
0x162f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Type>::Add(var<u1>)
0x162fa  ldloc.3
0x162fb  ldc.i4.1
0x162fc  add
0x162fd  stloc.3
0x162fe  ldloc.3
0x162ff  ldloc.2
0x16300  ldlen
0x16301  conv.i4
0x16302  blt.s    loc_1629B
0x16304  ret
```
