# biCompressionFromSubtype

- ea: `0x180008154`
- end: `0x180008373`
- name: `biCompressionFromSubtype`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004810`

## callees

- `0x180008154`

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
0x180008154  mov     rax, [rcx]
0x180008157  cmp     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data1
0x18000815e  jnz     short loc_180008171
0x180008160  mov     rax, [rcx+8]
0x180008164  cmp     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data4
0x18000816b  jz      loc_180008370
0x180008171  mov     rax, [rcx]
0x180008174  cmp     rax, cs:MEDIASUBTYPE_I420
0x18000817b  jnz     short loc_18000818E
0x18000817d  mov     rax, [rcx+8]
0x180008181  cmp     rax, cs:qword_1800241A8
0x180008188  jz      loc_180008370
0x18000818e  mov     rax, [rcx]
0x180008191  cmp     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data1
0x180008198  jnz     short loc_1800081AB
0x18000819a  mov     rax, [rcx+8]
0x18000819e  cmp     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data4
0x1800081a5  jz      loc_180008370
0x1800081ab  mov     rax, [rcx]
0x1800081ae  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data1
0x1800081b5  jnz     short loc_1800081C8
0x1800081b7  mov     rax, [rcx+8]
0x1800081bb  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data4
0x1800081c2  jz      loc_180008370
0x1800081c8  mov     rax, [rcx]
0x1800081cb  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data1
0x1800081d2  jnz     short loc_1800081E5
0x1800081d4  mov     rax, [rcx+8]
0x1800081d8  cmp     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data4
0x1800081df  jz      loc_180008370
0x1800081e5  mov     rax, [rcx]
0x1800081e8  cmp     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data1
0x1800081ef  jnz     short loc_180008202
0x1800081f1  mov     rax, [rcx+8]
0x1800081f5  cmp     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data4
0x1800081fc  jz      loc_180008370
0x180008202  mov     rax, [rcx]
0x180008205  cmp     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data1
0x18000820c  jnz     short loc_18000821F
0x18000820e  mov     rax, [rcx+8]
0x180008212  cmp     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data4
0x180008219  jz      loc_180008370
0x18000821f  mov     rax, [rcx]
0x180008222  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data1
0x180008229  jnz     short loc_18000823C
0x18000822b  mov     rax, [rcx+8]
0x18000822f  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data4
0x180008236  jz      loc_180008370
0x18000823c  mov     rax, [rcx]
0x18000823f  cmp     rax, cs:MEDIASUBTYPE_V216
0x180008246  jnz     short loc_180008259
0x180008248  mov     rax, [rcx+8]
0x18000824c  cmp     rax, cs:qword_180024178
0x180008253  jz      loc_180008370
0x180008259  mov     rax, [rcx]
0x18000825c  cmp     rax, cs:MEDIASUBTYPE_V410
0x180008263  jnz     short loc_180008276
0x180008265  mov     rax, [rcx+8]
0x180008269  cmp     rax, cs:qword_180024188
0x180008270  jz      loc_180008370
0x180008276  mov     rax, [rcx]
0x180008279  cmp     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data1
0x180008280  jnz     short loc_180008293
0x180008282  mov     rax, [rcx+8]
0x180008286  cmp     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data4
0x18000828d  jz      loc_180008370
0x180008293  mov     rax, [rcx]
0x180008296  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data1
0x18000829d  jnz     short loc_1800082B0
0x18000829f  mov     rax, [rcx+8]
0x1800082a3  cmp     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data4
0x1800082aa  jz      loc_180008370
0x1800082b0  mov     rax, [rcx]
0x1800082b3  cmp     rax, cs:MEDIASUBTYPE_v210
0x1800082ba  jnz     short loc_1800082CD
0x1800082bc  mov     rax, [rcx+8]
0x1800082c0  cmp     rax, cs:qword_180024198
0x1800082c7  jz      loc_180008370
0x1800082cd  mov     rax, [rcx]
0x1800082d0  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data1
0x1800082d7  jnz     short loc_1800082EA
0x1800082d9  mov     rax, [rcx+8]
0x1800082dd  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data4
0x1800082e4  jz      loc_18000836D
0x1800082ea  mov     rax, [rcx]
0x1800082ed  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data1
0x1800082f4  jnz     short loc_180008303
0x1800082f6  mov     rax, [rcx+8]
0x1800082fa  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data4
0x180008301  jz      short loc_18000836D
0x180008303  mov     rax, [rcx]
0x180008306  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x18000830d  jnz     short loc_180008322
0x18000830f  mov     rax, [rcx+8]
0x180008313  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x18000831a  jnz     short loc_180008322
0x18000831c  mov     eax, 3
0x180008321  retn
0x180008322  mov     rax, [rcx]
0x180008325  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data1
0x18000832c  jnz     short loc_18000833B
0x18000832e  mov     rax, [rcx+8]
0x180008332  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data4
0x180008339  jz      short loc_18000836D
0x18000833b  mov     rax, [rcx]
0x18000833e  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x180008345  jnz     short loc_180008354
0x180008347  mov     rax, [rcx+8]
0x18000834b  cmp     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x180008352  jz      short loc_18000836D
0x180008354  mov     rax, [rcx]
0x180008357  cmp     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data1
0x18000835e  jnz     short loc_180008370
0x180008360  mov     rax, [rcx+8]
0x180008364  cmp     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data4
0x18000836b  jnz     short loc_180008370
0x18000836d  xor     eax, eax
0x18000836f  retn
0x180008370  mov     eax, [rcx]
0x180008372  retn
```
