# CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)

- ea: `0x18004943c`
- end: `0x18004977d`
- name: `?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z`
- size: `833`
- prototype: `__int64 __fastcall(__int64, int, void **, unsigned int, int, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800474e4`
- `0x180047ef8`
- `0x180048f40`

## callees

- `0x18004943c`
- `0x18004a800`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800495b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004964e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800496db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800495b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004964e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800496db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049738`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::SwapByteOrder(
        __int64 a1,
        int a2,
        void **a3,
        unsigned int a4,
        int a5,
        int *a6)
{
  _DWORD *v6; // rdi
  unsigned int v9; // ebx
  int v10; // r10d
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  _DWORD *v17; // rax
  unsigned int j; // r9d
  __int64 v19; // r8
  int v21; // edx
  int v22; // edx
  int v23; // ecx
  HRESULT v24; // eax
  unsigned int m; // r11d
  __int64 v26; // r9
  unsigned int v27; // r8d
  unsigned int i; // r9d
  __int64 v29; // r8
  unsigned int k; // r9d
  __int64 v31; // r8
  ULONG pulResult; // [rsp+48h] [rbp+10h] BYREF

  v6 = *a3;
  pulResult = 0;
  v9 = 0;
  v10 = 0;
  v11 = a2 - 3;
  if ( !v11 )
    goto LABEL_55;
  v12 = v11 - 1;
  if ( !v12 )
  {
LABEL_19:
    if ( a5 )
    {
      v17 = v6;
      goto LABEL_40;
    }
    v24 = ULongLongToULong(4LL * a4, &pulResult);
    v9 = v24;
    if ( v24 >= 0 )
    {
      v17 = CoTaskMemAlloc(pulResult);
      if ( !v17 )
        goto LABEL_57;
      v10 = 1;
LABEL_40:
      for ( i = 0; i < a4; v17[v29] = HIBYTE(v6[v29])
                                    | ((BYTE2(v6[v29]) | (((v6[v29] << 8) | BYTE1(v6[v29])) << 8)) << 8) )
        v29 = i++;
      goto LABEL_11;
    }
    if ( !(_DWORD)g_doStackCaptures )
      return v9;
LABEL_26:
    v23 = v24;
    goto LABEL_25;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
LABEL_7:
    if ( a5 )
    {
      v17 = v6;
      goto LABEL_9;
    }
    if ( 8 * (unsigned __int64)a4 > 0xFFFFFFFF )
    {
      v9 = -2147024362;
LABEL_23:
      if ( !(_DWORD)g_doStackCaptures )
        return v9;
      v23 = v9;
LABEL_25:
      DoStackCapture(v23);
      return v9;
    }
    v17 = CoTaskMemAlloc(8 * a4);
    if ( v17 )
    {
      v10 = 1;
LABEL_9:
      for ( j = 0;
            j < a4;
            v17[2 * v19 + 1] = HIBYTE(v6[2 * v19 + 1])
                             | ((BYTE2(v6[2 * v19 + 1]) | ((BYTE1(v6[2 * v19 + 1]) | (v6[2 * v19 + 1] << 8)) << 8)) << 8) )
      {
        v19 = j++;
        v17[2 * v19] = HIBYTE(v6[2 * v19])
                     | ((BYTE2(v6[2 * v19]) | (((v6[2 * v19] << 8) | BYTE1(v6[2 * v19])) << 8)) << 8);
      }
LABEL_11:
      if ( v10 )
        *a3 = v17;
      goto LABEL_13;
    }
LABEL_57:
    v9 = -2147024882;
    goto LABEL_23;
  }
  v14 = v13 - 3;
  if ( !v14 )
  {
LABEL_55:
    if ( a5 )
    {
      v17 = v6;
    }
    else
    {
      v24 = ULongLongToULong(2LL * a4, &pulResult);
      v9 = v24;
      if ( v24 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          return v9;
        goto LABEL_26;
      }
      v17 = CoTaskMemAlloc(pulResult);
      if ( !v17 )
        goto LABEL_57;
      v10 = 1;
    }
    for ( k = 0; k < a4; *((_WORD *)v17 + v31) = (*((_WORD *)v6 + v31) << 8) | *((unsigned __int8 *)v6 + 2 * v31 + 1) )
      v31 = k++;
    goto LABEL_11;
  }
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_19;
  v16 = v15 - 1;
  if ( !v16 )
    goto LABEL_7;
  v21 = v16 - 1;
  if ( !v21 )
    goto LABEL_19;
  v22 = v21 - 1;
  if ( !v22 )
  {
    if ( a5 )
    {
      v17 = v6;
    }
    else
    {
      v24 = ULongLongToULong(8LL * a4, &pulResult);
      v9 = v24;
      if ( v24 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          return v9;
        goto LABEL_26;
      }
      v17 = CoTaskMemAlloc(pulResult);
      if ( !v17 )
        goto LABEL_57;
      v10 = 1;
    }
    for ( m = 0; m < a4; v17[2 * v26] = _byteswap_ulong(v27) )
    {
      v26 = m++;
      v27 = v6[2 * v26 + 1];
      v17[2 * v26 + 1] = HIBYTE(v6[2 * v26])
                       | ((BYTE2(v6[2 * v26]) | (((v6[2 * v26] << 8) | BYTE1(v6[2 * v26])) << 8)) << 8);
    }
    goto LABEL_11;
  }
  if ( v22 == 1 )
    goto LABEL_19;
LABEL_13:
  if ( a6 )
    *a6 = v10;
  return v9;
}

```

## disassembly

```asm
0x18004943c  mov     [rsp+arg_0], rbx
0x180049441  mov     [rsp+arg_10], rbp
0x180049446  push    rsi
0x180049447  push    rdi
0x180049448  push    r14
0x18004944a  sub     rsp, 20h
0x18004944e  mov     rdi, [r8]
0x180049451  xor     ebp, ebp
0x180049453  mov     esi, r9d
0x180049456  mov     r14, r8
0x180049459  mov     [rsp+38h+pulResult], ebp
0x18004945d  mov     ebx, ebp
0x18004945f  mov     r10d, ebp
0x180049462  sub     edx, 3
0x180049465  jz      loc_180049754
0x18004946b  sub     edx, 1
0x18004946e  jz      loc_180049547
0x180049474  sub     edx, 1
0x180049477  jz      short loc_180049494
0x180049479  sub     edx, 3
0x18004947c  jz      loc_180049754
0x180049482  sub     edx, 1
0x180049485  jz      loc_180049547
0x18004948b  sub     edx, 1
0x18004948e  jnz     loc_180049534
0x180049494  cmp     [rsp+38h+arg_20], ebp
0x180049498  jz      loc_180049559
0x18004949e  mov     rax, rdi
0x1800494a1  mov     r9d, ebp
0x1800494a4  test    esi, esi
0x1800494a6  jz      short loc_180049507
0x1800494a8  mov     r8d, r9d
0x1800494ab  inc     r9d
0x1800494ae  mov     ecx, [rdi+r8*8]
0x1800494b2  movzx   edx, byte ptr [rdi+r8*8+1]
0x1800494b8  shl     ecx, 8
0x1800494bb  or      edx, ecx
0x1800494bd  movzx   ecx, byte ptr [rdi+r8*8+2]
0x1800494c3  shl     edx, 8
0x1800494c6  or      edx, ecx
0x1800494c8  movzx   ecx, byte ptr [rdi+r8*8+3]
0x1800494ce  shl     edx, 8
0x1800494d1  or      edx, ecx
0x1800494d3  mov     [rax+r8*8], edx
0x1800494d7  movzx   ecx, byte ptr [rdi+r8*8+5]
0x1800494dd  mov     edx, [rdi+r8*8+4]
0x1800494e2  shl     edx, 8
0x1800494e5  or      edx, ecx
0x1800494e7  movzx   ecx, byte ptr [rdi+r8*8+6]
0x1800494ed  shl     edx, 8
0x1800494f0  or      edx, ecx
0x1800494f2  movzx   ecx, byte ptr [rdi+r8*8+7]
0x1800494f8  shl     edx, 8
0x1800494fb  or      edx, ecx
0x1800494fd  mov     [rax+r8*8+4], edx
0x180049502  cmp     r9d, esi
0x180049505  jb      short loc_1800494A8
0x180049507  test    r10d, r10d
0x18004950a  jnz     loc_18004976D
0x180049510  mov     rax, [rsp+38h+arg_28]
0x180049515  test    rax, rax
0x180049518  jnz     loc_180049775
0x18004951e  mov     rbp, [rsp+38h+arg_10]
0x180049523  mov     eax, ebx
0x180049525  mov     rbx, [rsp+38h+arg_0]
0x18004952a  add     rsp, 20h
0x18004952e  pop     r14
0x180049530  pop     rdi
0x180049531  pop     rsi
0x180049532  retn
0x180049534  sub     edx, 1
0x180049537  jz      short loc_180049547
0x180049539  sub     edx, 1
0x18004953c  jz      loc_180049724
0x180049542  cmp     edx, 1
0x180049545  jnz     short loc_180049510
0x180049547  cmp     [rsp+38h+arg_20], ebp
0x18004954b  jz      loc_18004961F
0x180049551  mov     rax, rdi
0x180049554  jmp     loc_180049669
0x180049559  mov     rax, rsi
0x18004955c  mov     ecx, 0FFFFFFFFh
0x180049561  shl     rax, 3
0x180049565  cmp     rax, rcx
0x180049568  jbe     loc_180049736
0x18004956e  mov     ebx, 80070216h
0x180049573  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180049579  jz      short loc_18004951E
0x18004957b  mov     ecx, ebx; int
0x18004957d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180049582  jmp     short loc_18004951E
0x180049584  mov     ecx, eax
0x180049586  jmp     short loc_18004957D
0x180049588  mov     rcx, rsi
0x18004958b  lea     rdx, [rsp+38h+pulResult]; pulResult
0x180049590  shl     rcx, 3; ullOperand
0x180049594  call    ULongLongToULong
0x180049599  mov     ebx, eax
0x18004959b  test    eax, eax
0x18004959d  jns     short loc_1800495AF
0x18004959f  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800495a5  jnz     short loc_180049584
0x1800495a7  test    eax, eax
0x1800495a9  js      loc_18004951E
0x1800495af  mov     ecx, [rsp+38h+pulResult]; cb
0x1800495b3  call    cs:__imp_CoTaskMemAlloc
0x1800495ba  nop     dword ptr [rax+rax+00h]
0x1800495bf  test    rax, rax
0x1800495c2  jz      loc_180049763
0x1800495c8  mov     r10d, 1
0x1800495ce  mov     r11d, ebp
0x1800495d1  test    esi, esi
0x1800495d3  jz      loc_180049507
0x1800495d9  mov     r9d, r11d
0x1800495dc  inc     r11d
0x1800495df  mov     ecx, [rdi+r9*8]
0x1800495e3  movzx   edx, byte ptr [rdi+r9*8+1]
0x1800495e9  mov     r8d, [rdi+r9*8+4]
0x1800495ee  shl     ecx, 8
0x1800495f1  or      edx, ecx
0x1800495f3  movzx   ecx, byte ptr [rdi+r9*8+2]
0x1800495f9  shl     edx, 8
0x1800495fc  or      edx, ecx
0x1800495fe  movzx   ecx, byte ptr [rdi+r9*8+3]
0x180049604  shl     edx, 8
0x180049607  or      edx, ecx
0x180049609  mov     [rax+r9*8+4], edx
0x18004960e  bswap   r8d
0x180049611  mov     [rax+r9*8], r8d
0x180049615  cmp     r11d, esi
0x180049618  jb      short loc_1800495D9
0x18004961a  jmp     loc_180049507
0x18004961f  mov     rcx, rsi
0x180049622  lea     rdx, [rsp+38h+pulResult]; pulResult
0x180049627  shl     rcx, 2; ullOperand
0x18004962b  call    ULongLongToULong
0x180049630  mov     ebx, eax
0x180049632  test    eax, eax
0x180049634  jns     short loc_18004964A
0x180049636  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x18004963c  jnz     loc_180049584
0x180049642  test    eax, eax
0x180049644  js      loc_18004951E
0x18004964a  mov     ecx, [rsp+38h+pulResult]; cb
0x18004964e  call    cs:__imp_CoTaskMemAlloc
0x180049655  nop     dword ptr [rax+rax+00h]
0x18004965a  test    rax, rax
0x18004965d  jz      loc_180049763
0x180049663  mov     r10d, 1
0x180049669  mov     r9d, ebp
0x18004966c  test    esi, esi
0x18004966e  jz      loc_180049507
0x180049674  mov     r8d, r9d
0x180049677  inc     r9d
0x18004967a  mov     ecx, [rdi+r8*4]
0x18004967e  movzx   edx, byte ptr [rdi+r8*4+1]
0x180049684  shl     ecx, 8
0x180049687  or      edx, ecx
0x180049689  movzx   ecx, byte ptr [rdi+r8*4+2]
0x18004968f  shl     edx, 8
0x180049692  or      edx, ecx
0x180049694  movzx   ecx, byte ptr [rdi+r8*4+3]
0x18004969a  shl     edx, 8
0x18004969d  or      edx, ecx
0x18004969f  mov     [rax+r8*4], edx
0x1800496a3  cmp     r9d, esi
0x1800496a6  jb      short loc_180049674
0x1800496a8  jmp     loc_180049507
0x1800496ad  mov     rcx, rsi
0x1800496b0  lea     rdx, [rsp+38h+pulResult]; pulResult
0x1800496b5  add     rcx, rcx; ullOperand
0x1800496b8  call    ULongLongToULong
0x1800496bd  mov     ebx, eax
0x1800496bf  test    eax, eax
0x1800496c1  jns     short loc_1800496D7
0x1800496c3  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800496c9  jnz     loc_180049584
0x1800496cf  test    eax, eax
0x1800496d1  js      loc_18004951E
0x1800496d7  mov     ecx, [rsp+38h+pulResult]; cb
0x1800496db  call    cs:__imp_CoTaskMemAlloc
0x1800496e2  nop     dword ptr [rax+rax+00h]
0x1800496e7  test    rax, rax
0x1800496ea  jz      short loc_180049763
0x1800496ec  mov     r10d, 1
0x1800496f2  mov     r9d, ebp
0x1800496f5  test    esi, esi
0x1800496f7  jz      loc_180049507
0x1800496fd  mov     r8d, r9d
0x180049700  inc     r9d
0x180049703  movzx   ecx, word ptr [rdi+r8*2]
0x180049708  movzx   edx, byte ptr [rdi+r8*2+1]
0x18004970e  shl     cx, 8
0x180049712  or      dx, cx
0x180049715  mov     [rax+r8*2], dx
0x18004971a  cmp     r9d, esi
0x18004971d  jb      short loc_1800496FD
0x18004971f  jmp     loc_180049507
0x180049724  cmp     [rsp+38h+arg_20], ebp
0x180049728  jz      loc_180049588
0x18004972e  mov     rax, rdi
0x180049731  jmp     loc_1800495CE
0x180049736  mov     ecx, eax; cb
0x180049738  call    cs:__imp_CoTaskMemAlloc
0x18004973f  nop     dword ptr [rax+rax+00h]
0x180049744  test    rax, rax
0x180049747  jz      short loc_180049763
0x180049749  mov     r10d, 1
0x18004974f  jmp     loc_1800494A1
0x180049754  cmp     [rsp+38h+arg_20], ebp
0x180049758  jz      loc_1800496AD
0x18004975e  mov     rax, rdi
0x180049761  jmp     short loc_1800496F2
0x180049763  mov     ebx, 8007000Eh
0x180049768  jmp     loc_180049573
0x18004976d  mov     [r14], rax
0x180049770  jmp     loc_180049510
0x180049775  mov     [rax], r10d
0x180049778  jmp     loc_18004951E
```
