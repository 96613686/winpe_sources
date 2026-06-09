# System.Windows.CoreCompatibilityPreferences::set_IsAltKeyRequiredInAccessKeyDefaultScope

- ea: `0x18630`
- end: `0x18680`
- name: `System.Windows.CoreCompatibilityPreferences::set_IsAltKeyRequiredInAccessKeyDefaultScope`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18630`
- `0x146e70`

## string_xrefs

- `0x18647`: `CompatibilityPreferencesSealed`
- `0x18654`: `IsAltKeyRequiredInAccessKeyDefaultScope`
- `0x1865c`: `CoreCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x18630  ldsfld   object System.Windows.CoreCompatibilityPreferences::_lockObject
0x18635  stloc.0
0x18636  ldc.i4.0
0x18637  stloc.1
0x18638  ldloc.0
0x18639  ldloca.s 1
0x1863b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x18640  ldsfld   bool System.Windows.CoreCompatibilityPreferences::_isSealed
0x18645  brfalse.s loc_1866D
0x18647  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x1864c  ldc.i4.2
0x1864d  newarr   [mscorlib]System.Object
0x18652  dup
0x18653  ldc.i4.0
0x18654  ldstr    aIsaltkeyrequir// "IsAltKeyRequiredInAccessKeyDefaultScope"
0x18659  stelem.ref
0x1865a  dup
0x1865b  ldc.i4.1
0x1865c  ldstr    aCorecompatibil// "CoreCompatibilityPreferences"
0x18661  stelem.ref
0x18662  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x18667  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1866c  throw
0x1866d  ldarg.0
0x1866e  stsfld   bool System.Windows.CoreCompatibilityPreferences::_isAltKeyRequiredInAccessKeyDefaultScope
0x18673  leave.s  loc_1867F
0x18675  ldloc.1
0x18676  brfalse.s loc_1867E
0x18678  ldloc.0
0x18679  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1867e  endfinally
0x1867f  ret
```
