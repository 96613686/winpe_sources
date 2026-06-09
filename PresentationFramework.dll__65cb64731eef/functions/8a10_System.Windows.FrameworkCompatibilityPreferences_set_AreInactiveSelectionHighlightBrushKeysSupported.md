# System.Windows.FrameworkCompatibilityPreferences::set_AreInactiveSelectionHighlightBrushKeysSupported

- ea: `0x8a10`
- end: `0x8a60`
- name: `System.Windows.FrameworkCompatibilityPreferences::set_AreInactiveSelectionHighlightBrushKeysSupported`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8a10`
- `0x38c70`

## string_xrefs

- `0x8a27`: `CompatibilityPreferencesSealed`
- `0x8a3c`: `FrameworkCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x8a10  ldsfld   object System.Windows.FrameworkCompatibilityPreferences::_lockObject
0x8a15  stloc.0
0x8a16  ldc.i4.0
0x8a17  stloc.1
0x8a18  ldloc.0
0x8a19  ldloca.s 1
0x8a1b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x8a20  ldsfld   bool System.Windows.FrameworkCompatibilityPreferences::_isSealed
0x8a25  brfalse.s loc_8A4D
0x8a27  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x8a2c  ldc.i4.2
0x8a2d  newarr   [mscorlib]System.Object
0x8a32  dup
0x8a33  ldc.i4.0
0x8a34  ldstr    aAreinactivesel// "AreInactiveSelectionHighlightBrushKeysS"...
0x8a39  stelem.ref
0x8a3a  dup
0x8a3b  ldc.i4.1
0x8a3c  ldstr    aFrameworkcompa// "FrameworkCompatibilityPreferences"
0x8a41  stelem.ref
0x8a42  call     string System.Windows.SR::Get(string id, object[] args)
0x8a47  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8a4c  throw
0x8a4d  ldarg.0
0x8a4e  stsfld   bool System.Windows.FrameworkCompatibilityPreferences::_areInactiveSelectionHighlightBrushKeysSupported
0x8a53  leave.s  loc_8A5F
0x8a55  ldloc.1
0x8a56  brfalse.s loc_8A5E
0x8a58  ldloc.0
0x8a59  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x8a5e  endfinally
0x8a5f  ret
```
