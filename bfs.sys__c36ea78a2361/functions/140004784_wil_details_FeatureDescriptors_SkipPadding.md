# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x140004784`
- end: `0x1400047a6`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001e944`
- `0x14001ead4`
- `0x14001eb70`
- `0x14001ebec`
- `0x14001ec70`
- `0x14001f590`
- `0x14001f650`

## callees

- `0x140004784`

## pseudocode

```c
__int64 *__fastcall wil_details_FeatureDescriptors_SkipPadding(__int64 *a1)
{
  while ( a1 < wil_details_featureDescriptors_z )
  {
    if ( *a1 )
      return a1;
    ++a1;
  }
  return 0;
}

```

## disassembly

```asm
0x140004784  xchg    ax, ax
0x140004786  lea     rax, wil_details_featureDescriptors_z
0x14000478d  cmp     rcx, rax
0x140004790  jnb     short loc_1400047A3
0x140004792  cmp     qword ptr [rcx], 0
0x140004796  jnz     short loc_14000479E
0x140004798  add     rcx, 8
0x14000479c  jmp     short loc_140004786
0x14000479e  mov     rax, rcx
0x1400047a1  retn
0x1400047a3  xor     eax, eax
0x1400047a5  retn
```
