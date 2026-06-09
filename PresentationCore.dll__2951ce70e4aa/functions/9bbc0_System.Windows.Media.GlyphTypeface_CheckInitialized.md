# System.Windows.Media.GlyphTypeface::CheckInitialized

- ea: `0x9bbc0`
- end: `0x9bbda`
- name: `System.Windows.Media.GlyphTypeface::CheckInitialized`
- size: `26`
- prototype: ``
- caller_count: `61`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9aa70`
- `0x9aa90`
- `0x9aad0`
- `0x9aae0`
- `0x9abb0`
- `0x9abd0`
- `0x9abf0`
- `0x9ac10`
- `0x9ac90`
- `0x9acc0`
- `0x9acf0`
- `0x9ad00`
- `0x9ad70`
- `0x9ad80`
- `0x9ada0`
- `0x9adc0`
- `0x9ade0`
- `0x9ae00`
- `0x9ae20`
- `0x9ae40`
- `0x9ae60`
- `0x9ae80`
- `0x9aea0`
- `0x9aec0`
- `0x9aee0`
- `0x9af00`
- `0x9af20`
- `0x9af40`
- `0x9af80`
- `0x9afb0`
- `0x9afe0`
- `0x9b010`
- `0x9b030`
- `0x9b060`
- `0x9b090`
- `0x9b0c0`
- `0x9b0f0`
- `0x9b180`
- `0x9b1a0`
- `0x9b1c0`
- `0x9b1e0`
- `0x9b200`
- `0x9b220`
- `0x9b240`
- `0x9b260`
- `0x9b280`
- `0x9b2a0`
- `0x9b2e0`
- `0x9b2f0`
- `0x9b550`

## callees

- `0x9bbc0`
- `0x146e40`

## string_xrefs

- `0x9bbc9`: `InitializationIncomplete`

## pseudocode

```c

```

## disassembly

```asm
0x9bbc0  ldarg.0
0x9bbc1  ldfld    valuetype InitializationState System.Windows.Media.GlyphTypeface::_initializationState
0x9bbc6  ldc.i4.2
0x9bbc7  beq.s    loc_9BBD9
0x9bbc9  ldstr    aInitialization// "InitializationIncomplete"
0x9bbce  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x9bbd3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9bbd8  throw
0x9bbd9  ret
```
