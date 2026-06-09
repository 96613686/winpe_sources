# System.Windows.FrameworkCompatibilityPreferences::set_ShouldThrowOnCopyOrCutFailure

- ea: `0x8d30`
- end: `0x8d64`
- name: `System.Windows.FrameworkCompatibilityPreferences::set_ShouldThrowOnCopyOrCutFailure`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8d80`

## callees

- `0x8d30`
- `0x38c70`

## string_xrefs

- `0x8d37`: `CompatibilityPreferencesSealed`
- `0x8d4c`: `FrameworkCompatibilityPreferences`
- `0x8d44`: `ShouldThrowOnCopyOrCutFailure`

## pseudocode

```c

```

## disassembly

```asm
0x8d30  ldsfld   bool System.Windows.FrameworkCompatibilityPreferences::_isSealed
0x8d35  brfalse.s loc_8D5D
0x8d37  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x8d3c  ldc.i4.2
0x8d3d  newarr   [mscorlib]System.Object
0x8d42  dup
0x8d43  ldc.i4.0
0x8d44  ldstr    aShouldthrowonc// "ShouldThrowOnCopyOrCutFailure"
0x8d49  stelem.ref
0x8d4a  dup
0x8d4b  ldc.i4.1
0x8d4c  ldstr    aFrameworkcompa// "FrameworkCompatibilityPreferences"
0x8d51  stelem.ref
0x8d52  call     string System.Windows.SR::Get(string id, object[] args)
0x8d57  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8d5c  throw
0x8d5d  ldarg.0
0x8d5e  stsfld   bool System.Windows.FrameworkCompatibilityPreferences::_shouldThrowOnCopyOrCutFailure
0x8d63  ret
```
