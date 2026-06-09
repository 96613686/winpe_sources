# System.Windows.FrameworkCompatibilityPreferences::set_ShouldThrowOnDataGridCopyOrCutFailure

- ea: `0x8e70`
- end: `0x8ea4`
- name: `System.Windows.FrameworkCompatibilityPreferences::set_ShouldThrowOnDataGridCopyOrCutFailure`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8ec0`

## callees

- `0x8e70`
- `0x38c70`

## string_xrefs

- `0x8e77`: `CompatibilityPreferencesSealed`
- `0x8e8c`: `FrameworkCompatibilityPreferences`
- `0x8e84`: `ShouldThrowOnDataGridCopyOrCutFailure`

## pseudocode

```c

```

## disassembly

```asm
0x8e70  ldsfld   bool System.Windows.FrameworkCompatibilityPreferences::_isSealed
0x8e75  brfalse.s loc_8E9D
0x8e77  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x8e7c  ldc.i4.2
0x8e7d  newarr   [mscorlib]System.Object
0x8e82  dup
0x8e83  ldc.i4.0
0x8e84  ldstr    aShouldthrowond// "ShouldThrowOnDataGridCopyOrCutFailure"
0x8e89  stelem.ref
0x8e8a  dup
0x8e8b  ldc.i4.1
0x8e8c  ldstr    aFrameworkcompa// "FrameworkCompatibilityPreferences"
0x8e91  stelem.ref
0x8e92  call     string System.Windows.SR::Get(string id, object[] args)
0x8e97  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8e9c  throw
0x8e9d  ldarg.0
0x8e9e  stsfld   bool System.Windows.FrameworkCompatibilityPreferences::_shouldThrowOnDataGridCopyOrCutFailure
0x8ea3  ret
```
