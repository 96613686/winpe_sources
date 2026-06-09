# Microsoft.SharePoint.Client.ClientRequestService::GetOData4RestServiceType

- ea: `0x6700`
- end: `0x681f`
- name: `Microsoft.SharePoint.Client.ClientRequestService::GetOData4RestServiceType`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x69f0`
- `0x13a90`

## callees

- `0x6700`
- `0xe010`
- `0x16f10`

## string_xrefs

- `0x6797`: `https://go.microsoft.com/fwlink/?LinkId=511784`
- `0x67f3`: `https://go.microsoft.com/fwlink/?LinkId=511784`
- `0x67ab`: `Microsoft.SharePoint.Client.OData.RestService`
- `0x67d6`: `Microsoft.SharePoint.Client.OData.RestService`

## pseudocode

```c

```

## disassembly

```asm
0x6700  ldsfld   class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientRequestService::s_OData4RestServiceType
0x6705  ldnull
0x6706  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x670b  brfalse  loc_6819
0x6710  ldc.i4.0
0x6711  stloc.3
0x6712  ldsfld   object Microsoft.SharePoint.Client.ClientRequestService::s_lock
0x6717  dup
0x6718  stloc.s  4
0x671a  ldloca.s 3
0x671c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6721  ldsfld   class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientRequestService::s_OData4RestServiceType
0x6726  ldnull
0x6727  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x672c  brfalse  loc_680C
0x6731  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x6736  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x673b  stloc.0
0x673c  ldloc.0
0x673d  ldloc.0
0x673e  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x6743  ldstr    aOdata// ".OData"
0x6748  call     string [mscorlib]System.String::Concat(string, string)
0x674d  callvirt instance void [mscorlib]System.Reflection.AssemblyName::set_Name(string)
0x6752  ldloc.0
0x6753  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(class [mscorlib]System.Reflection.AssemblyName)
0x6758  stloc.1
0x6759  ldloc.1
0x675a  ldnull
0x675b  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x6760  brfalse.s loc_67AA
0x6762  ldarg.0
0x6763  ldc.i4   0x6407D8
0x6768  ldc.i4.1
0x6769  ldstr    aCannotLoadAsse// "Cannot load assembly {0}"
0x676e  ldc.i4.1
0x676f  newarr   [mscorlib]System.Object
0x6774  stloc.s  5
0x6776  ldloc.s  5
0x6778  ldc.i4.0
0x6779  ldloc.0
0x677a  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x677f  stelem.ref
0x6780  ldloc.s  5
0x6782  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6787  ldstr    aOdatalibmissin// "ODataLibMissing"
0x678c  ldc.i4.1
0x678d  newarr   [mscorlib]System.Object
0x6792  stloc.s  6
0x6794  ldloc.s  6
0x6796  ldc.i4.0
0x6797  ldstr    aHttpsGoMicroso// "https://go.microsoft.com/fwlink/?LinkId"...
0x679c  stelem.ref
0x679d  ldloc.s  6
0x679f  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x67a4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x67a9  throw
0x67aa  ldloc.1
0x67ab  ldstr    aMicrosoftShare// "Microsoft.SharePoint.Client.OData.RestS"...
0x67b0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x67b5  stloc.2
0x67b6  ldloc.2
0x67b7  ldnull
0x67b8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67bd  brfalse.s loc_6806
0x67bf  ldarg.0
0x67c0  ldc.i4   0x6407D9
0x67c5  ldc.i4.1
0x67c6  ldstr    aCannotLoadType// "Cannot load type {0}"
0x67cb  ldc.i4.1
0x67cc  newarr   [mscorlib]System.Object
0x67d1  stloc.s  7
0x67d3  ldloc.s  7
0x67d5  ldc.i4.0
0x67d6  ldstr    aMicrosoftShare// "Microsoft.SharePoint.Client.OData.RestS"...
0x67db  stelem.ref
0x67dc  ldloc.s  7
0x67de  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x67e3  ldstr    aOdatalibmissin// "ODataLibMissing"
0x67e8  ldc.i4.1
0x67e9  newarr   [mscorlib]System.Object
0x67ee  stloc.s  8
0x67f0  ldloc.s  8
0x67f2  ldc.i4.0
0x67f3  ldstr    aHttpsGoMicroso// "https://go.microsoft.com/fwlink/?LinkId"...
0x67f8  stelem.ref
0x67f9  ldloc.s  8
0x67fb  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x6800  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6805  throw
0x6806  ldloc.2
0x6807  stsfld   class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientRequestService::s_OData4RestServiceType
0x680c  leave.s  loc_6819
0x680e  ldloc.3
0x680f  brfalse.s loc_6818
0x6811  ldloc.s  4
0x6813  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6818  endfinally
0x6819  ldsfld   class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientRequestService::s_OData4RestServiceType
0x681e  ret
```
