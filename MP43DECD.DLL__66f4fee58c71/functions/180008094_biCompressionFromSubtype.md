# biCompressionFromSubtype

- ea: `0x180008094`
- end: `0x1800082b3`
- name: `biCompressionFromSubtype`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004750`

## callees

- `0x180008094`

## pseudocode

```c
__int64 __fastcall biCompressionFromSubtype(_QWORD *a1)
{
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_IYUV.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_IYUV.Data4
    || *a1 == MEDIASUBTYPE_I420 && a1[1] == 0x719B3800AA000080LL
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YV12.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YV12.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_NV12.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_NV12.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_NV11.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_NV11.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YUY2.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_UYVY.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_UYVY.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YVYU.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YVYU.Data4
    || *a1 == MEDIASUBTYPE_V216 && a1[1] == 0x719B3800AA000080LL
    || *a1 == MEDIASUBTYPE_V410 && a1[1] == 0x719B3800AA000080LL
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_AYUV.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_AYUV.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_YVU9.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_YVU9.Data4
    || *a1 == MEDIASUBTYPE_v210 && a1[1] == 0x719B3800AA000080LL )
  {
    return *(unsigned int *)a1;
  }
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB32.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_RGB32.Data4
    || *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB24.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_RGB24.Data4 )
  {
    return 0;
  }
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 && a1[1] == *(_QWORD *)MEDIASUBTYPE_RGB565.Data4 )
    return 3;
  if ( (*a1 != *(_QWORD *)&MEDIASUBTYPE_RGB555.Data1 || a1[1] != *(_QWORD *)MEDIASUBTYPE_RGB555.Data4)
    && (*a1 != *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 || a1[1] != *(_QWORD *)MEDIASUBTYPE_RGB8.Data4)
    && (*a1 != *(_QWORD *)&MEDIASUBTYPE_ARGB32.Data1 || a1[1] != *(_QWORD *)MEDIASUBTYPE_ARGB32.Data4) )
  {
    return *(unsigned int *)a1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180008094  mov     rax, [rcx]
0x180008097  cmp     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data1
0x18000809e  jnz     short loc_1800080B1
0x1800080a0  mov     rax, [rcx+8]
0x1800080a4  cmp     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data4
0x1800080ab  jz      loc_1800082B0
0x1800080b1  mov     rax, [rcx]
0x1800080b4  cmp     rax, cs:MEDIASUBTYPE_I420
0x1800080bb  jnz     short loc_1800080CE
0x1800080bd  mov     rax, [rcx+8]
0x1800080c1  cmp     rax, cs:qword_1800241B8
0x1800080c8  jz      loc_1800082B0
0x1800080ce  mov     rax, [rcx]
0x1800080d1  cmp     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data1
0x1800080d8  jnz     short loc_1800080EB
0x1800080da  mov     rax, [rcx+8]
0x1800080de  cmp     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data4
0x1800080e5  jz      loc_1800082B0
0x1800080eb  mov     rax, [rcx]
0x1800080ee  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data1
0x1800080f5  jnz     short loc_180008108
0x1800080f7  mov     rax, [rcx+8]
0x1800080fb  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data4
0x180008102  jz      loc_1800082B0
0x180008108  mov     rax, [rcx]
0x18000810b  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data1
0x180008112  jnz     short loc_180008125
0x180008114  mov     rax, [rcx+8]
0x180008118  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data4
0x18000811f  jz      loc_1800082B0
0x180008125  mov     rax, [rcx]
0x180008128  cmp     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data1
0x18000812f  jnz     short loc_180008142
0x180008131  mov     rax, [rcx+8]
0x180008135  cmp     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data4
0x18000813c  jz      loc_1800082B0
0x180008142  mov     rax, [rcx]
0x180008145  cmp     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data1
0x18000814c  jnz     short loc_18000815F
0x18000814e  mov     rax, [rcx+8]
0x180008152  cmp     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data4
0x180008159  jz      loc_1800082B0
0x18000815f  mov     rax, [rcx]
0x180008162  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data1
0x180008169  jnz     short loc_18000817C
0x18000816b  mov     rax, [rcx+8]
0x18000816f  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data4
0x180008176  jz      loc_1800082B0
0x18000817c  mov     rax, [rcx]
0x18000817f  cmp     rax, cs:MEDIASUBTYPE_V216
0x180008186  jnz     short loc_180008199
0x180008188  mov     rax, [rcx+8]
0x18000818c  cmp     rax, cs:qword_180024188
0x180008193  jz      loc_1800082B0
0x180008199  mov     rax, [rcx]
0x18000819c  cmp     rax, cs:MEDIASUBTYPE_V410
0x1800081a3  jnz     short loc_1800081B6
0x1800081a5  mov     rax, [rcx+8]
0x1800081a9  cmp     rax, cs:qword_180024198
0x1800081b0  jz      loc_1800082B0
0x1800081b6  mov     rax, [rcx]
0x1800081b9  cmp     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data1
0x1800081c0  jnz     short loc_1800081D3
0x1800081c2  mov     rax, [rcx+8]
0x1800081c6  cmp     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data4
0x1800081cd  jz      loc_1800082B0
0x1800081d3  mov     rax, [rcx]
0x1800081d6  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data1
0x1800081dd  jnz     short loc_1800081F0
0x1800081df  mov     rax, [rcx+8]
0x1800081e3  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data4
0x1800081ea  jz      loc_1800082B0
0x1800081f0  mov     rax, [rcx]
0x1800081f3  cmp     rax, cs:MEDIASUBTYPE_v210
0x1800081fa  jnz     short loc_18000820D
0x1800081fc  mov     rax, [rcx+8]
0x180008200  cmp     rax, cs:qword_1800241A8
0x180008207  jz      loc_1800082B0
0x18000820d  mov     rax, [rcx]
0x180008210  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data1
0x180008217  jnz     short loc_18000822A
0x180008219  mov     rax, [rcx+8]
0x18000821d  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data4
0x180008224  jz      loc_1800082AD
0x18000822a  mov     rax, [rcx]
0x18000822d  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data1
0x180008234  jnz     short loc_180008243
0x180008236  mov     rax, [rcx+8]
0x18000823a  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data4
0x180008241  jz      short loc_1800082AD
0x180008243  mov     rax, [rcx]
0x180008246  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x18000824d  jnz     short loc_180008262
0x18000824f  mov     rax, [rcx+8]
0x180008253  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x18000825a  jnz     short loc_180008262
0x18000825c  mov     eax, 3
0x180008261  retn
0x180008262  mov     rax, [rcx]
0x180008265  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data1
0x18000826c  jnz     short loc_18000827B
0x18000826e  mov     rax, [rcx+8]
0x180008272  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data4
0x180008279  jz      short loc_1800082AD
0x18000827b  mov     rax, [rcx]
0x18000827e  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x180008285  jnz     short loc_180008294
0x180008287  mov     rax, [rcx+8]
0x18000828b  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x180008292  jz      short loc_1800082AD
0x180008294  mov     rax, [rcx]
0x180008297  cmp     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data1
0x18000829e  jnz     short loc_1800082B0
0x1800082a0  mov     rax, [rcx+8]
0x1800082a4  cmp     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data4
0x1800082ab  jnz     short loc_1800082B0
0x1800082ad  xor     eax, eax
0x1800082af  retn
0x1800082b0  mov     eax, [rcx]
0x1800082b2  retn
```
