# Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::get_ResourceManager

- ea: `0x1fb90`
- end: `0x1fbbb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1fbe0`
- `0x1fc00`
- `0x1fc20`
- `0x1fc40`
- `0x1fc60`
- `0x1fc80`
- `0x1fca0`
- `0x1fcc0`
- `0x1fce0`
- `0x1fd00`
- `0x1fd20`
- `0x1fd40`
- `0x1fd60`
- `0x1fd80`
- `0x1fda0`
- `0x1fdc0`
- `0x1fde0`
- `0x1fe00`
- `0x1fe20`
- `0x1fe40`
- `0x1fe60`
- `0x1fe80`
- `0x1fea0`
- `0x1fec0`
- `0x1fee0`
- `0x1ff00`
- `0x1ff20`
- `0x1ff40`
- `0x1ff60`
- `0x1ff80`
- `0x1ffa0`

## callees

- `0x1fb90`

## string_xrefs

- `0x1fb97`: `Microsoft.Windows.ManagementUI.CombinedControls.EvtResources`

## pseudocode

```c

```

## disassembly

```asm
0x1fb90  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::resourceMan
0x1fb95  brtrue.s loc_1FBB5
0x1fb97  ldstr    aMicrosoftWindo_0// "Microsoft.Windows.ManagementUI.Combined"...
0x1fb9c  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EvtResources
0x1fba1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fba6  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x1fbab  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x1fbb0  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::resourceMan
0x1fbb5  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::resourceMan
0x1fbba  ret
```
