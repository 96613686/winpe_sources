# System.Windows.CoreCompatibilityPreferences::set_EnableMultiMonitorDisplayClipping

- ea: `0x18730`
- end: `0x18780`
- name: `System.Windows.CoreCompatibilityPreferences::set_EnableMultiMonitorDisplayClipping`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18790`

## callees

- `0x18730`
- `0x146e70`

## string_xrefs

- `0x18747`: `CompatibilityPreferencesSealed`
- `0x1875c`: `CoreCompatibilityPreferences`

## pseudocode

```c

```

## disassembly

```asm
0x18730  ldsfld   object System.Windows.CoreCompatibilityPreferences::_lockObject
0x18735  stloc.0
0x18736  ldc.i4.0
0x18737  stloc.1
0x18738  ldloc.0
0x18739  ldloca.s 1
0x1873b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x18740  ldsfld   bool System.Windows.CoreCompatibilityPreferences::_isSealed
0x18745  brfalse.s loc_1876D
0x18747  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x1874c  ldc.i4.2
0x1874d  newarr   [mscorlib]System.Object
0x18752  dup
0x18753  ldc.i4.0
0x18754  ldstr    aDisablemultimo// "DisableMultimonDisplayClipping"
0x18759  stelem.ref
0x1875a  dup
0x1875b  ldc.i4.1
0x1875c  ldstr    aCorecompatibil// "CoreCompatibilityPreferences"
0x18761  stelem.ref
0x18762  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x18767  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1876c  throw
0x1876d  ldarg.0
0x1876e  stsfld   valuetype [mscorlib]System.Nullable`1<bool> System.Windows.CoreCompatibilityPreferences::_enableMultiMonitorDisplayClipping
0x18773  leave.s  loc_1877F
0x18775  ldloc.1
0x18776  brfalse.s loc_1877E
0x18778  ldloc.0
0x18779  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1877e  endfinally
0x1877f  ret
```
