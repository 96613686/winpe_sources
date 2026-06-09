# Microsoft.ManagementConsole.ViewDescriptionCollection::CreateView

- ea: `0x8be0`
- end: `0x8c1b`
- name: `Microsoft.ManagementConsole.ViewDescriptionCollection::CreateView`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd60`

## callees

- `0x8be0`
- `0x8ed0`
- `0x98f0`

## string_xrefs

- `0x8bf3`: `ViewDescription id:{0} not found. Cannot create view.`

## pseudocode

```c

```

## disassembly

```asm
0x8be0  ldarg.0
0x8be1  ldarg.1
0x8be2  call     instance class Microsoft.ManagementConsole.ViewDescription Microsoft.ManagementConsole.ViewDescriptionCollection::GetViewDescriptionById(int32 id)
0x8be7  stloc.0
0x8be8  ldloc.0
0x8be9  brtrue.s loc_8C10
0x8beb  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x8bf0  ldc.i4.8
0x8bf1  ldc.i4.s 0xC
0x8bf3  ldstr    aViewdescriptio_2// "ViewDescription id:{0} not found. Canno"...
0x8bf8  ldc.i4.1
0x8bf9  newarr   [mscorlib]System.Object
0x8bfe  stloc.1
0x8bff  ldloc.1
0x8c00  ldc.i4.0
0x8c01  ldarg.1
0x8c02  box      [mscorlib]System.Int32
0x8c07  stelem.ref
0x8c08  ldloc.1
0x8c09  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x8c0e  ldnull
0x8c0f  ret
0x8c10  ldloc.0
0x8c11  ldarg.2
0x8c12  ldarg.3
0x8c13  ldarg.s  4
0x8c15  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IMessageClient Microsoft.ManagementConsole.ViewDescription::CreateView(class Microsoft.ManagementConsole.ScopeNode scopeNode, int32 componentId, int32 viewInstanceId)
0x8c1a  ret
```
