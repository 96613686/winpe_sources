# biCompressionFromSubtype

- ea: `0x180029884`
- end: `0x180029adc`
- name: `biCompressionFromSubtype`
- size: `600`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180029020`

## callees

- `0x180029884`

## pseudocode

```c
__int64 __fastcall biCompressionFromSubtype(_QWORD *a1)
{
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax

  v1 = *a1 - *(_QWORD *)&MEDIASUBTYPE_IYUV.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_IYUV.Data1 )
    v1 = a1[1] - *(_QWORD *)MEDIASUBTYPE_IYUV.Data4;
  if ( !v1 )
    return *(unsigned int *)a1;
  v2 = *a1 - MEDIASUBTYPE_I420;
  if ( *a1 == MEDIASUBTYPE_I420 )
    v2 = a1[1] - 0x719B3800AA000080LL;
  if ( !v2 )
    return *(unsigned int *)a1;
  v3 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YV12.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YV12.Data1 )
    v3 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YV12.Data4;
  if ( !v3 )
    return *(unsigned int *)a1;
  v4 = *a1 - *(_QWORD *)&MEDIASUBTYPE_NV12.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_NV12.Data1 )
    v4 = a1[1] - *(_QWORD *)MEDIASUBTYPE_NV12.Data4;
  if ( !v4 )
    return *(unsigned int *)a1;
  v5 = *a1 - *(_QWORD *)&MEDIASUBTYPE_NV11.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_NV11.Data1 )
    v5 = a1[1] - *(_QWORD *)MEDIASUBTYPE_NV11.Data4;
  if ( !v5 )
    return *(unsigned int *)a1;
  v6 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YUY2.Data1 )
    v6 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YUY2.Data4;
  if ( !v6 )
    return *(unsigned int *)a1;
  v7 = *a1 - *(_QWORD *)&MEDIASUBTYPE_UYVY.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_UYVY.Data1 )
    v7 = a1[1] - *(_QWORD *)MEDIASUBTYPE_UYVY.Data4;
  if ( !v7 )
    return *(unsigned int *)a1;
  v8 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YVYU.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YVYU.Data1 )
    v8 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YVYU.Data4;
  if ( !v8 )
    return *(unsigned int *)a1;
  v9 = *a1 - MEDIASUBTYPE_V216;
  if ( *a1 == MEDIASUBTYPE_V216 )
    v9 = a1[1] - 0x719B3800AA000080LL;
  if ( !v9 )
    return *(unsigned int *)a1;
  v10 = *a1 - MEDIASUBTYPE_V410;
  if ( *a1 == MEDIASUBTYPE_V410 )
    v10 = a1[1] - 0x719B3800AA000080LL;
  if ( !v10 )
    return *(unsigned int *)a1;
  v11 = *a1 - *(_QWORD *)&MEDIASUBTYPE_AYUV.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_AYUV.Data1 )
    v11 = a1[1] - *(_QWORD *)MEDIASUBTYPE_AYUV.Data4;
  if ( !v11 )
    return *(unsigned int *)a1;
  v12 = *a1 - *(_QWORD *)&MEDIASUBTYPE_YVU9.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_YVU9.Data1 )
    v12 = a1[1] - *(_QWORD *)MEDIASUBTYPE_YVU9.Data4;
  if ( !v12 )
    return *(unsigned int *)a1;
  v13 = *a1 - MEDIASUBTYPE_v210;
  if ( *a1 == MEDIASUBTYPE_v210 )
    v13 = a1[1] - 0x719B3800AA000080LL;
  if ( !v13 )
    return *(unsigned int *)a1;
  v14 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB32.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB32.Data1 )
    v14 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB32.Data4;
  if ( !v14 )
    return 0;
  v15 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB24.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB24.Data1 )
    v15 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB24.Data4;
  if ( !v15 )
    return 0;
  v16 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 )
    v16 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB565.Data4;
  if ( !v16 )
    return 3;
  v18 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB555.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB555.Data1 )
    v18 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB555.Data4;
  if ( !v18 )
    return 0;
  v19 = *a1 - *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 )
    v19 = a1[1] - *(_QWORD *)MEDIASUBTYPE_RGB8.Data4;
  if ( !v19 )
    return 0;
  v20 = *a1 - *(_QWORD *)&MEDIASUBTYPE_ARGB32.Data1;
  if ( *a1 == *(_QWORD *)&MEDIASUBTYPE_ARGB32.Data1 )
    v20 = a1[1] - *(_QWORD *)MEDIASUBTYPE_ARGB32.Data4;
  if ( !v20 )
    return 0;
  else
    return *(unsigned int *)a1;
}

```

## disassembly

```asm
0x180029884  mov     rax, [rcx]
0x180029887  sub     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data1
0x18002988e  jnz     short loc_18002989B
0x180029890  mov     rax, [rcx+8]
0x180029894  sub     rax, qword ptr cs:MEDIASUBTYPE_IYUV.Data4
0x18002989b  test    rax, rax
0x18002989e  jz      loc_180029AD9
0x1800298a4  mov     rax, [rcx]
0x1800298a7  sub     rax, cs:MEDIASUBTYPE_I420
0x1800298ae  jnz     short loc_1800298BB
0x1800298b0  mov     rax, [rcx+8]
0x1800298b4  sub     rax, cs:qword_180054E78
0x1800298bb  test    rax, rax
0x1800298be  jz      loc_180029AD9
0x1800298c4  mov     rax, [rcx]
0x1800298c7  sub     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data1
0x1800298ce  jnz     short loc_1800298DB
0x1800298d0  mov     rax, [rcx+8]
0x1800298d4  sub     rax, qword ptr cs:MEDIASUBTYPE_YV12.Data4
0x1800298db  test    rax, rax
0x1800298de  jz      loc_180029AD9
0x1800298e4  mov     rax, [rcx]
0x1800298e7  sub     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data1
0x1800298ee  jnz     short loc_1800298FB
0x1800298f0  mov     rax, [rcx+8]
0x1800298f4  sub     rax, qword ptr cs:MEDIASUBTYPE_NV12.Data4
0x1800298fb  test    rax, rax
0x1800298fe  jz      loc_180029AD9
0x180029904  mov     rax, [rcx]
0x180029907  sub     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data1
0x18002990e  jnz     short loc_18002991B
0x180029910  mov     rax, [rcx+8]
0x180029914  sub     rax, qword ptr cs:MEDIASUBTYPE_NV11.Data4
0x18002991b  test    rax, rax
0x18002991e  jz      loc_180029AD9
0x180029924  mov     rax, [rcx]
0x180029927  sub     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data1
0x18002992e  jnz     short loc_18002993B
0x180029930  mov     rax, [rcx+8]
0x180029934  sub     rax, qword ptr cs:MEDIASUBTYPE_YUY2.Data4
0x18002993b  test    rax, rax
0x18002993e  jz      loc_180029AD9
0x180029944  mov     rax, [rcx]
0x180029947  sub     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data1
0x18002994e  jnz     short loc_18002995B
0x180029950  mov     rax, [rcx+8]
0x180029954  sub     rax, qword ptr cs:MEDIASUBTYPE_UYVY.Data4
0x18002995b  test    rax, rax
0x18002995e  jz      loc_180029AD9
0x180029964  mov     rax, [rcx]
0x180029967  sub     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data1
0x18002996e  jnz     short loc_18002997B
0x180029970  mov     rax, [rcx+8]
0x180029974  sub     rax, qword ptr cs:MEDIASUBTYPE_YVYU.Data4
0x18002997b  test    rax, rax
0x18002997e  jz      loc_180029AD9
0x180029984  mov     rax, [rcx]
0x180029987  sub     rax, cs:MEDIASUBTYPE_V216
0x18002998e  jnz     short loc_18002999B
0x180029990  mov     rax, [rcx+8]
0x180029994  sub     rax, cs:qword_180054E48
0x18002999b  test    rax, rax
0x18002999e  jz      loc_180029AD9
0x1800299a4  mov     rax, [rcx]
0x1800299a7  sub     rax, cs:MEDIASUBTYPE_V410
0x1800299ae  jnz     short loc_1800299BB
0x1800299b0  mov     rax, [rcx+8]
0x1800299b4  sub     rax, cs:qword_180054E58
0x1800299bb  test    rax, rax
0x1800299be  jz      loc_180029AD9
0x1800299c4  mov     rax, [rcx]
0x1800299c7  sub     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data1
0x1800299ce  jnz     short loc_1800299DB
0x1800299d0  mov     rax, [rcx+8]
0x1800299d4  sub     rax, qword ptr cs:MEDIASUBTYPE_AYUV.Data4
0x1800299db  test    rax, rax
0x1800299de  jz      loc_180029AD9
0x1800299e4  mov     rax, [rcx]
0x1800299e7  sub     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data1
0x1800299ee  jnz     short loc_1800299FB
0x1800299f0  mov     rax, [rcx+8]
0x1800299f4  sub     rax, qword ptr cs:MEDIASUBTYPE_YVU9.Data4
0x1800299fb  test    rax, rax
0x1800299fe  jz      loc_180029AD9
0x180029a04  mov     rax, [rcx]
0x180029a07  sub     rax, cs:MEDIASUBTYPE_v210
0x180029a0e  jnz     short loc_180029A1B
0x180029a10  mov     rax, [rcx+8]
0x180029a14  sub     rax, cs:qword_180054E68
0x180029a1b  test    rax, rax
0x180029a1e  jz      loc_180029AD9
0x180029a24  mov     rax, [rcx]
0x180029a27  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data1
0x180029a2e  jnz     short loc_180029A3B
0x180029a30  mov     rax, [rcx+8]
0x180029a34  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB32.Data4
0x180029a3b  test    rax, rax
0x180029a3e  jz      loc_180029AD6
0x180029a44  mov     rax, [rcx]
0x180029a47  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data1
0x180029a4e  jnz     short loc_180029A5B
0x180029a50  mov     rax, [rcx+8]
0x180029a54  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB24.Data4
0x180029a5b  test    rax, rax
0x180029a5e  jz      short loc_180029AD6
0x180029a60  mov     rax, [rcx]
0x180029a63  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x180029a6a  jnz     short loc_180029A77
0x180029a6c  mov     rax, [rcx+8]
0x180029a70  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x180029a77  test    rax, rax
0x180029a7a  jnz     short loc_180029A82
0x180029a7c  mov     eax, 3
0x180029a81  retn
0x180029a82  mov     rax, [rcx]
0x180029a85  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data1
0x180029a8c  jnz     short loc_180029A99
0x180029a8e  mov     rax, [rcx+8]
0x180029a92  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB555.Data4
0x180029a99  test    rax, rax
0x180029a9c  jz      short loc_180029AD6
0x180029a9e  mov     rax, [rcx]
0x180029aa1  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x180029aa8  jnz     short loc_180029AB5
0x180029aaa  mov     rax, [rcx+8]
0x180029aae  sub     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x180029ab5  test    rax, rax
0x180029ab8  jz      short loc_180029AD6
0x180029aba  mov     rax, [rcx]
0x180029abd  sub     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data1
0x180029ac4  jnz     short loc_180029AD1
0x180029ac6  mov     rax, [rcx+8]
0x180029aca  sub     rax, qword ptr cs:MEDIASUBTYPE_ARGB32.Data4
0x180029ad1  test    rax, rax
0x180029ad4  jnz     short loc_180029AD9
0x180029ad6  xor     eax, eax
0x180029ad8  retn
0x180029ad9  mov     eax, [rcx]
0x180029adb  retn
```
