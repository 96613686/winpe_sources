# Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager

- ea: `0x9e20`
- end: `0x9e4b`
- name: `Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `89`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9e70`
- `0x9e90`
- `0x9eb0`
- `0x9ed0`
- `0x9ef0`
- `0x9f10`
- `0x9f30`
- `0x9f50`
- `0x9f70`
- `0x9f90`
- `0x9fb0`
- `0x9fd0`
- `0x9ff0`
- `0xa010`
- `0xa030`
- `0xa050`
- `0xa070`
- `0xa090`
- `0xa0b0`
- `0xa0d0`
- `0xa0f0`
- `0xa110`
- `0xa130`
- `0xa150`
- `0xa170`
- `0xa190`
- `0xa1b0`
- `0xa1d0`
- `0xa1f0`
- `0xa210`
- `0xa230`
- `0xa250`
- `0xa270`
- `0xa290`
- `0xa2b0`
- `0xa2d0`
- `0xa2f0`
- `0xa310`
- `0xa330`
- `0xa350`
- `0xa370`
- `0xa390`
- `0xa3b0`
- `0xa3d0`
- `0xa3f0`
- `0xa410`
- `0xa430`
- `0xa450`
- `0xa470`
- `0xa490`

## callees

- `0x9e20`

## pseudocode

```c

```

## disassembly

```asm
0x9e20  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceMan
0x9e25  brtrue.s loc_9E45
0x9e27  ldstr    aMicrosoftEvent// "Microsoft.EventViewer.SnapIn.Properties"...
0x9e2c  ldtoken  Microsoft.EventViewer.SnapIn.Properties.EventViewerResources
0x9e31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9e36  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x9e3b  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x9e40  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceMan
0x9e45  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::resourceMan
0x9e4a  ret
```
