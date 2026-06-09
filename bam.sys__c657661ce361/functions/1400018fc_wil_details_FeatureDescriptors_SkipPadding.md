# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400018fc`
- end: `0x14000191e`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b594`
- `0x14000b724`
- `0x14000b7c0`
- `0x14000b83c`
- `0x14000b8c0`
- `0x1400161ec`
- `0x1400162ac`

## callees

- `0x1400018fc`

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
0x1400018fc  xchg    ax, ax
0x1400018fe  lea     rax, wil_details_featureDescriptors_z
0x140001905  cmp     rcx, rax
0x140001908  jnb     short loc_14000191B
0x14000190a  cmp     qword ptr [rcx], 0
0x14000190e  jnz     short loc_140001916
0x140001910  add     rcx, 8
0x140001914  jmp     short loc_1400018FE
0x140001916  mov     rax, rcx
0x140001919  retn
0x14000191b  xor     eax, eax
0x14000191d  retn
```
