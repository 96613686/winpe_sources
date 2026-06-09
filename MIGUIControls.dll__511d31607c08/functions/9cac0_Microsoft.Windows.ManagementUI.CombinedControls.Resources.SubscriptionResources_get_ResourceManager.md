# Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::get_ResourceManager

- ea: `0x9cac0`
- end: `0x9caeb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `172`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9cb10`
- `0x9cb30`
- `0x9cb50`
- `0x9cb70`
- `0x9cb90`
- `0x9cbb0`
- `0x9cbd0`
- `0x9cbf0`
- `0x9cc10`
- `0x9cc30`
- `0x9cc50`
- `0x9cc70`
- `0x9cc90`
- `0x9ccb0`
- `0x9ccd0`
- `0x9ccf0`
- `0x9cd10`
- `0x9cd30`
- `0x9cd50`
- `0x9cd70`
- `0x9cd90`
- `0x9cdb0`
- `0x9cdd0`
- `0x9cdf0`
- `0x9ce10`
- `0x9ce30`
- `0x9ce50`
- `0x9ce70`
- `0x9ce90`
- `0x9ceb0`
- `0x9ced0`
- `0x9cef0`
- `0x9cf10`
- `0x9cf30`
- `0x9cf50`
- `0x9cf70`
- `0x9cf90`
- `0x9cfb0`
- `0x9cfd0`
- `0x9cff0`
- `0x9d010`
- `0x9d030`
- `0x9d050`
- `0x9d070`
- `0x9d090`
- `0x9d0b0`
- `0x9d0d0`
- `0x9d0f0`
- `0x9d110`
- `0x9d130`

## callees

- `0x9cac0`

## string_xrefs

- `0x9cac7`: `Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources`

## pseudocode

```c

```

## disassembly

```asm
0x9cac0  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::resourceMan
0x9cac5  brtrue.s loc_9CAE5
0x9cac7  ldstr    aMicrosoftWindo_5// "Microsoft.Windows.ManagementUI.Combined"...
0x9cacc  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources
0x9cad1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9cad6  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x9cadb  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x9cae0  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::resourceMan
0x9cae5  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.Resources.SubscriptionResources::resourceMan
0x9caea  ret
```
