# System.Windows.CoreCompatibilityPreferences::set_IncludeAllInkInBoundingBox

- ea: `0x186a0`
- end: `0x186f0`
- name: `System.Windows.CoreCompatibilityPreferences::set_IncludeAllInkInBoundingBox`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18700`

## callees

- `0x186a0`
- `0x146e70`

## string_xrefs

- `0x186b7`: `CompatibilityPreferencesSealed`
- `0x186cc`: `CoreCompatibilityPreferences`
- `0x186c4`: `IncludeAllInkInBoundingBox`

## pseudocode

```c

```

## disassembly

```asm
0x186a0  ldsfld   object System.Windows.CoreCompatibilityPreferences::_lockObject
0x186a5  stloc.0
0x186a6  ldc.i4.0
0x186a7  stloc.1
0x186a8  ldloc.0
0x186a9  ldloca.s 1
0x186ab  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x186b0  ldsfld   bool System.Windows.CoreCompatibilityPreferences::_isSealed
0x186b5  brfalse.s loc_186DD
0x186b7  ldstr    aCompatibilityp// "CompatibilityPreferencesSealed"
0x186bc  ldc.i4.2
0x186bd  newarr   [mscorlib]System.Object
0x186c2  dup
0x186c3  ldc.i4.0
0x186c4  ldstr    aIncludeallinki// "IncludeAllInkInBoundingBox"
0x186c9  stelem.ref
0x186ca  dup
0x186cb  ldc.i4.1
0x186cc  ldstr    aCorecompatibil// "CoreCompatibilityPreferences"
0x186d1  stelem.ref
0x186d2  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x186d7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x186dc  throw
0x186dd  ldarg.0
0x186de  stsfld   bool System.Windows.CoreCompatibilityPreferences::_includeAllInkInBoundingBox
0x186e3  leave.s  loc_186EF
0x186e5  ldloc.1
0x186e6  brfalse.s loc_186EE
0x186e8  ldloc.0
0x186e9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x186ee  endfinally
0x186ef  ret
```
