# System.Windows.Media.GlyphRun::CheckInitialized

- ea: `0x9a760`
- end: `0x9a779`
- name: `System.Windows.Media.GlyphRun::CheckInitialized`
- size: `25`
- prototype: ``
- caller_count: `25`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x99100`
- `0x99270`
- `0x99450`
- `0x99500`
- `0x995a0`
- `0x99670`
- `0x99690`
- `0x996b0`
- `0x996e0`
- `0x99710`
- `0x99760`
- `0x99780`
- `0x997e0`
- `0x99800`
- `0x99820`
- `0x99870`
- `0x998c0`
- `0x998e0`
- `0x99900`
- `0x999c0`
- `0x99f80`
- `0x9a0e0`
- `0x9a1d0`
- `0x9a220`
- `0x9a270`

## callees

- `0x9a760`
- `0x9a7e0`
- `0x146e40`

## string_xrefs

- `0x9a768`: `InitializationIncomplete`

## pseudocode

```c

```

## disassembly

```asm
0x9a760  ldarg.0
0x9a761  call     instance bool System.Windows.Media.GlyphRun::get_IsInitialized()
0x9a766  brtrue.s loc_9A778
0x9a768  ldstr    aInitialization// "InitializationIncomplete"
0x9a76d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x9a772  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9a777  throw
0x9a778  ret
```
