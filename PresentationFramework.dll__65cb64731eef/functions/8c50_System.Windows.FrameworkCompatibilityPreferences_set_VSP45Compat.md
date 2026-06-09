# System.Windows.FrameworkCompatibilityPreferences::set_VSP45Compat

- ea: `0x8c50`
- end: `0x8ca0`
- name: `System.Windows.FrameworkCompatibilityPreferences::set_VSP45Compat`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8cb0`

## callees

- `0x8c50`
- `0x38c70`

## string_xrefs

- `0x8c67`: `CompatibilityPreferencesSealed`
- `0x8c7c`: `FrameworkCompatibilityPreferences`
- `0x8c74`: `IsVirtualizingStackPanel_45Compatible`

## pseudocode

```c

```

## disassembly

```asm
0x8c50  ldsfld   object System.Windows.FrameworkCompatibilityPreferences::_lockObject
0x8c55  stloc.0
0x8c56  ldc.i4.0
0x8c57  stloc.1
0x8c58  ldloc.0
0x8c59  ldloca.s 1
0x8c5b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x8c60  ldsfld   bool System.Windows.FrameworkCompatibilityPreferences::_isSealed
0x8c65  brfalse.s loc_8C8D
0x8c67  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x8c6c  ldc.i4.2
0x8c6d  newarr   [mscorlib]System.Object
0x8c72  dup
0x8c73  ldc.i4.0
0x8c74  ldstr    aIsvirtualizing// "IsVirtualizingStackPanel_45Compatible"
0x8c79  stelem.ref
0x8c7a  dup
0x8c7b  ldc.i4.1
0x8c7c  ldstr    aFrameworkcompa// "FrameworkCompatibilityPreferences"
0x8c81  stelem.ref
0x8c82  call     string System.Windows.SR::Get(string id, object[] args)
0x8c87  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8c8c  throw
0x8c8d  ldarg.0
0x8c8e  stsfld   bool System.Windows.FrameworkCompatibilityPreferences::_vsp45Compat
0x8c93  leave.s  loc_8C9F
0x8c95  ldloc.1
0x8c96  brfalse.s loc_8C9E
0x8c98  ldloc.0
0x8c99  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8c9e  endfinally
0x8c9f  ret
```
