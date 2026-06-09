# av_pix_fmt_desc_get

- ea: `0x18004c700`
- end: `0x18004c720`
- name: `av_pix_fmt_desc_get`
- size: `32`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18003a720`
- `0x18003afe0`
- `0x18003c57c`
- `0x180040350`
- `0x180040800`
- `0x180040b50`
- `0x180040da0`
- `0x180041120`
- `0x1800412a0`
- `0x1800414c0`
- `0x1800415d0`
- `0x1800417ac`

## callees

- `0x18004c700`

## pseudocode

```c
char **__fastcall av_pix_fmt_desc_get(unsigned int a1)
{
  if ( a1 > 0x10A )
    return 0;
  _mm_lfence();
  return &(&off_18008A690)[14 * (int)a1];
}

```

## disassembly

```asm
0x18004c700  cmp     ecx, 10Ah
0x18004c706  ja      short loc_18004C71D
0x18004c708  lfence
0x18004c70b  movsxd  rax, ecx
0x18004c70e  lea     rcx, off_18008A690; "yuv420p"
0x18004c715  imul    rax, 70h ; 'p'
0x18004c719  add     rax, rcx
0x18004c71c  retn
0x18004c71d  xor     eax, eax
0x18004c71f  retn
```
