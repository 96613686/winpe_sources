# System.Windows.FrameworkPropertyMetadata::.ctor_9

- ea: `0x15aa0`
- end: `0x15af5`
- name: `System.Windows.FrameworkPropertyMetadata::.ctor_9`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x196b50`

## callees

- `0x15aa0`
- `0x15b30`
- `0x15e50`
- `0x38c40`
- `0x7eda0`

## string_xrefs

- `0x15ab5`: `defaultUpdateSourceTrigger`
- `0x15ada`: `defaultUpdateSourceTrigger`
- `0x15ad0`: `NoDefaultUpdateSourceTrigger`

## pseudocode

```c

```

## disassembly

```asm
0x15aa0  ldarg.0
0x15aa1  ldarg.1
0x15aa2  ldarg.3
0x15aa3  ldarg.s  4
0x15aa5  ldarg.s  5
0x15aa7  call     instance void [PresentationCore]System.Windows.UIPropertyMetadata::.ctor(object, class [WindowsBase]System.Windows.PropertyChangedCallback, class [WindowsBase]System.Windows.CoerceValueCallback, bool)
0x15aac  ldarg.s  6
0x15aae  call     bool System.Windows.Data.BindingOperations::IsValidUpdateSourceTrigger(valuetype System.Windows.Data.UpdateSourceTrigger value)
0x15ab3  brtrue.s loc_15ACC
0x15ab5  ldstr    aDefaultupdates// "defaultUpdateSourceTrigger"
0x15aba  ldarg.s  6
0x15abc  ldtoken  System.Windows.Data.UpdateSourceTrigger
0x15ac1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ac6  newobj   instance void [System]System.ComponentModel.InvalidEnumArgumentException::.ctor(string, int32, class [mscorlib]System.Type)
0x15acb  throw
0x15acc  ldarg.s  6
0x15ace  brtrue.s loc_15AE5
0x15ad0  ldstr    aNodefaultupdat// "NoDefaultUpdateSourceTrigger"
0x15ad5  call     string System.Windows.SR::Get(string id)
0x15ada  ldstr    aDefaultupdates// "defaultUpdateSourceTrigger"
0x15adf  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x15ae4  throw
0x15ae5  ldarg.0
0x15ae6  ldarg.2
0x15ae7  call     instance void System.Windows.FrameworkPropertyMetadata::TranslateFlags(valuetype System.Windows.FrameworkPropertyMetadataOptions flags)
0x15aec  ldarg.0
0x15aed  ldarg.s  6
0x15aef  call     instance void System.Windows.FrameworkPropertyMetadata::set_DefaultUpdateSourceTrigger(valuetype System.Windows.Data.UpdateSourceTrigger value)
0x15af4  ret
```
