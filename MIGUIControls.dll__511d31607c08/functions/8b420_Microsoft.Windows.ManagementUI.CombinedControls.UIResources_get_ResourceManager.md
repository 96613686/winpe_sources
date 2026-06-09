# Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_ResourceManager

- ea: `0x8b420`
- end: `0x8b44b`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `59`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8b470`
- `0x8b490`
- `0x8b4b0`
- `0x8b4d0`
- `0x8b4f0`
- `0x8b510`
- `0x8b530`
- `0x8b550`
- `0x8b570`
- `0x8b590`
- `0x8b5b0`
- `0x8b5d0`
- `0x8b5f0`
- `0x8b610`
- `0x8b630`
- `0x8b650`
- `0x8b670`
- `0x8b690`
- `0x8b6b0`
- `0x8b6d0`
- `0x8b6f0`
- `0x8b710`
- `0x8b730`
- `0x8b750`
- `0x8b770`
- `0x8b790`
- `0x8b7b0`
- `0x8b7d0`
- `0x8b7f0`
- `0x8b810`
- `0x8b830`
- `0x8b850`
- `0x8b870`
- `0x8b890`
- `0x8b8b0`
- `0x8b8d0`
- `0x8b8f0`
- `0x8b910`
- `0x8b930`
- `0x8b950`
- `0x8b970`
- `0x8b990`
- `0x8b9b0`
- `0x8b9d0`
- `0x8b9f0`
- `0x8ba10`
- `0x8ba30`
- `0x8ba50`
- `0x8ba70`
- `0x8ba90`

## callees

- `0x8b420`

## string_xrefs

- `0x8b427`: `Microsoft.Windows.ManagementUI.CombinedControls.UIResources`

## pseudocode

```c

```

## disassembly

```asm
0x8b420  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.UIResources::_resMgr
0x8b425  brtrue.s loc_8B445
0x8b427  ldstr    aMicrosoftWindo_2// "Microsoft.Windows.ManagementUI.Combined"...
0x8b42c  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.UIResources
0x8b431  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8b436  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x8b43b  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x8b440  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.UIResources::_resMgr
0x8b445  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.UIResources::_resMgr
0x8b44a  ret
```
