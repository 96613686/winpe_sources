# Microsoft.ManagementConsole.Node::Initialize

- ea: `0x710`
- end: `0x793`
- name: `Microsoft.ManagementConsole.Node::Initialize`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18a0`
- `0x2090`

## callees

- `0x120`
- `0x160`
- `0x6c0`
- `0x6d0`
- `0x710`
- `0x4210`
- `0x8440`
- `0x8470`

## string_xrefs

- `0x763`: `The max value for Node identifiers has been reached; no new nodes can be created.`

## pseudocode

```c

```

## disassembly

```asm
0x710  ldarg.0
0x711  ldarg.1
0x712  call     instance void Microsoft.ManagementConsole.Node::set_Data(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeData value)
0x717  ldarg.0
0x718  call     class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.SnapInBase::get_SnapInInstance()
0x71d  isinst   Microsoft.ManagementConsole.NamespaceSnapInBase
0x722  stfld    class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::_snapIn
0x727  ldarg.0
0x728  ldfld    class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::_snapIn
0x72d  brtrue.s loc_74F
0x72f  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionCommonWrongThread()
0x734  ldc.i4.1
0x735  newarr   [mscorlib]System.Object
0x73a  stloc.0
0x73b  ldloc.0
0x73c  ldc.i4.0
0x73d  ldstr    aNode// "Node"
0x742  stelem.ref
0x743  ldloc.0
0x744  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x749  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x74e  throw
0x74f  ldsfld   int32 Microsoft.ManagementConsole.Node::_idCounter
0x754  ldc.i4   0x7FFFFFFF
0x759  bne.un.s loc_77D
0x75b  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x760  ldc.i4.2
0x761  ldc.i4.s 0xC
0x763  ldstr    aTheMaxValueFor// "The max value for Node identifiers has "...
0x768  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0x76d  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionMMCOutOfResources()
0x772  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x777  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x77c  throw
0x77d  ldarg.0
0x77e  call     instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeData Microsoft.ManagementConsole.Node::get_Data()
0x783  ldsflda  int32 Microsoft.ManagementConsole.Node::_idCounter
0x788  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x78d  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeData::set_Id(int32)
0x792  ret
```
