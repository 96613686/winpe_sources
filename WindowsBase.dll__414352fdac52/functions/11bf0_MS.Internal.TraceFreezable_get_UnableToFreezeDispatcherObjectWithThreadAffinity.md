# MS.Internal.TraceFreezable::get_UnableToFreezeDispatcherObjectWithThreadAffinity

- ea: `0x11bf0`
- end: `0x11c36`
- name: `MS.Internal.TraceFreezable::get_UnableToFreezeDispatcherObjectWithThreadAffinity`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x38750`

## callees

- `0xf360`
- `0x11bf0`

## string_xrefs

- `0x11c00`: `CanFreeze is returning false because a DependencyProperty on the Freezable has a value that is a DispatcherObject with thread affinity`

## pseudocode

```c

```

## disassembly

```asm
0x11bf0  ldsfld   class MS.Internal.AvTraceDetails MS.Internal.TraceFreezable::_UnableToFreezeDispatcherObjectWithThreadAffinity
0x11bf5  brtrue.s loc_11C30
0x11bf7  ldc.i4.2
0x11bf8  ldc.i4.5
0x11bf9  newarr   [mscorlib]System.String
0x11bfe  dup
0x11bff  ldc.i4.0
0x11c00  ldstr    aCanfreezeIsRet_0// "CanFreeze is returning false because a "...
0x11c05  stelem.ref
0x11c06  dup
0x11c07  ldc.i4.1
0x11c08  ldstr    aFreezable// "Freezable"
0x11c0d  stelem.ref
0x11c0e  dup
0x11c0f  ldc.i4.2
0x11c10  ldstr    aDp// "DP"
0x11c15  stelem.ref
0x11c16  dup
0x11c17  ldc.i4.3
0x11c18  ldstr    aDpownertype// "DpOwnerType"
0x11c1d  stelem.ref
0x11c1e  dup
0x11c1f  ldc.i4.4
0x11c20  ldstr    aValue_0// "Value"
0x11c25  stelem.ref
0x11c26  newobj   instance void MS.Internal.AvTraceDetails::.ctor(int32 id, string[] labels)
0x11c2b  stsfld   class MS.Internal.AvTraceDetails MS.Internal.TraceFreezable::_UnableToFreezeDispatcherObjectWithThreadAffinity
0x11c30  ldsfld   class MS.Internal.AvTraceDetails MS.Internal.TraceFreezable::_UnableToFreezeDispatcherObjectWithThreadAffinity
0x11c35  ret
```
