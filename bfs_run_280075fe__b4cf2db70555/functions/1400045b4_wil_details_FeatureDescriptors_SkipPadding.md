# wil_details_FeatureDescriptors_SkipPadding

- ea: `0x1400045b4`
- end: `0x1400045d6`
- name: `wil_details_FeatureDescriptors_SkipPadding`
- size: `34`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14001e944`
- `0x14001ea7c`
- `0x14001eb10`
- `0x14001eb8c`
- `0x14001ec10`
- `0x14001f590`
- `0x14001f650`

## callees

- `0x1400045b4`

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
0x1400045b4  xchg    ax, ax
0x1400045b6  lea     rax, wil_details_featureDescriptors_z
0x1400045bd  cmp     rcx, rax
0x1400045c0  jnb     short loc_1400045D3
0x1400045c2  cmp     qword ptr [rcx], 0
0x1400045c6  jnz     short loc_1400045CE
0x1400045c8  add     rcx, 8
0x1400045cc  jmp     short loc_1400045B6
0x1400045ce  mov     rax, rcx
0x1400045d1  retn
0x1400045d3  xor     eax, eax
0x1400045d5  retn
```
