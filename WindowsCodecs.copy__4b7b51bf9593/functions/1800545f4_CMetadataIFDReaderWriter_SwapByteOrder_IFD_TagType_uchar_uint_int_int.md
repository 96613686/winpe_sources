# CMetadataIFDReaderWriter::SwapByteOrder(IFD::TagType,uchar * *,uint,int,int *)

- ea: `0x1800545f4`
- end: `0x18005491c`
- name: `?SwapByteOrder@CMetadataIFDReaderWriter@@IEAAJW4TagType@IFD@@PEAPEAEIHPEAH@Z`
- size: `808`
- prototype: `__int64 __fastcall(__int64, int, void **, unsigned int, int, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054104`
- `0x18005879c`
- `0x1800aeeb4`

## callees

- `0x1800545f4`
- `0x1800554f0`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005476a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800547ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800548dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005476a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800547ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800548dd`

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
0x1800545f4  mov     [rsp+arg_0], rbx
0x1800545f9  mov     [rsp+arg_10], rbp
0x1800545fe  push    rsi
0x1800545ff  push    rdi
0x180054600  push    r14
0x180054602  sub     rsp, 20h
0x180054606  mov     rdi, [r8]
0x180054609  xor     ebp, ebp
0x18005460b  mov     esi, r9d
0x18005460e  mov     r14, r8
0x180054611  mov     [rsp+38h+pulResult], ebp
0x180054615  mov     ebx, ebp
0x180054617  mov     r10d, ebp
0x18005461a  sub     edx, 3
0x18005461d  jz      loc_1800548F3
0x180054623  sub     edx, 1
0x180054626  jz      loc_1800546FE
0x18005462c  sub     edx, 1
0x18005462f  jz      short loc_18005464C
0x180054631  sub     edx, 3
0x180054634  jz      loc_1800548F3
0x18005463a  sub     edx, 1
0x18005463d  jz      loc_1800546FE
0x180054643  sub     edx, 1
0x180054646  jnz     loc_1800546EB
0x18005464c  cmp     [rsp+38h+arg_20], ebp
0x180054650  jz      loc_180054710
0x180054656  mov     rax, rdi
0x180054659  mov     r9d, ebp
0x18005465c  test    esi, esi
0x18005465e  jz      short loc_1800546BF
0x180054660  mov     r8d, r9d
0x180054663  inc     r9d
0x180054666  mov     ecx, [rdi+r8*8]
0x18005466a  movzx   edx, byte ptr [rdi+r8*8+1]
0x180054670  shl     ecx, 8
0x180054673  or      edx, ecx
0x180054675  movzx   ecx, byte ptr [rdi+r8*8+2]
0x18005467b  shl     edx, 8
0x18005467e  or      edx, ecx
0x180054680  movzx   ecx, byte ptr [rdi+r8*8+3]
0x180054686  shl     edx, 8
0x180054689  or      edx, ecx
0x18005468b  mov     [rax+r8*8], edx
0x18005468f  movzx   ecx, byte ptr [rdi+r8*8+5]
0x180054695  mov     edx, [rdi+r8*8+4]
0x18005469a  shl     edx, 8
0x18005469d  or      edx, ecx
0x18005469f  movzx   ecx, byte ptr [rdi+r8*8+6]
0x1800546a5  shl     edx, 8
0x1800546a8  or      edx, ecx
0x1800546aa  movzx   ecx, byte ptr [rdi+r8*8+7]
0x1800546b0  shl     edx, 8
0x1800546b3  or      edx, ecx
0x1800546b5  mov     [rax+r8*8+4], edx
0x1800546ba  cmp     r9d, esi
0x1800546bd  jb      short loc_180054660
0x1800546bf  test    r10d, r10d
0x1800546c2  jnz     loc_18005490C
0x1800546c8  mov     rax, [rsp+38h+arg_28]
0x1800546cd  test    rax, rax
0x1800546d0  jnz     loc_180054914
0x1800546d6  mov     rbp, [rsp+38h+arg_10]
0x1800546db  mov     eax, ebx
0x1800546dd  mov     rbx, [rsp+38h+arg_0]
0x1800546e2  add     rsp, 20h
0x1800546e6  pop     r14
0x1800546e8  pop     rdi
0x1800546e9  pop     rsi
0x1800546ea  retn
0x1800546eb  sub     edx, 1
0x1800546ee  jz      short loc_1800546FE
0x1800546f0  sub     edx, 1
0x1800546f3  jz      loc_1800548C9
0x1800546f9  cmp     edx, 1
0x1800546fc  jnz     short loc_1800546C8
0x1800546fe  cmp     [rsp+38h+arg_20], ebp
0x180054702  jz      loc_1800547D0
0x180054708  mov     rax, rdi
0x18005470b  jmp     loc_180054814
0x180054710  mov     rax, rsi
0x180054713  mov     ecx, 0FFFFFFFFh
0x180054718  shl     rax, 3
0x18005471c  cmp     rax, rcx
0x18005471f  jbe     loc_1800548DB
0x180054725  mov     ebx, 80070216h
0x18005472a  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180054730  jz      short loc_1800546D6
0x180054732  mov     ecx, ebx; int
0x180054734  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180054739  jmp     short loc_1800546D6
0x18005473b  mov     ecx, eax
0x18005473d  jmp     short loc_180054734
0x18005473f  mov     rcx, rsi
0x180054742  lea     rdx, [rsp+38h+pulResult]; pulResult
0x180054747  shl     rcx, 3; ullOperand
0x18005474b  call    ULongLongToULong
0x180054750  mov     ebx, eax
0x180054752  test    eax, eax
0x180054754  jns     short loc_180054766
0x180054756  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x18005475c  jnz     short loc_18005473B
0x18005475e  test    eax, eax
0x180054760  js      loc_1800546D6
0x180054766  mov     ecx, [rsp+38h+pulResult]; cb
0x18005476a  call    cs:__imp_CoTaskMemAlloc
0x180054770  test    rax, rax
0x180054773  jz      loc_180054902
0x180054779  mov     r10d, 1
0x18005477f  mov     r11d, ebp
0x180054782  test    esi, esi
0x180054784  jz      loc_1800546BF
0x18005478a  mov     r9d, r11d
0x18005478d  inc     r11d
0x180054790  mov     ecx, [rdi+r9*8]
0x180054794  movzx   edx, byte ptr [rdi+r9*8+1]
0x18005479a  mov     r8d, [rdi+r9*8+4]
0x18005479f  shl     ecx, 8
0x1800547a2  or      edx, ecx
0x1800547a4  movzx   ecx, byte ptr [rdi+r9*8+2]
0x1800547aa  shl     edx, 8
0x1800547ad  or      edx, ecx
0x1800547af  movzx   ecx, byte ptr [rdi+r9*8+3]
0x1800547b5  shl     edx, 8
0x1800547b8  or      edx, ecx
0x1800547ba  mov     [rax+r9*8+4], edx
0x1800547bf  bswap   r8d
0x1800547c2  mov     [rax+r9*8], r8d
0x1800547c6  cmp     r11d, esi
0x1800547c9  jb      short loc_18005478A
0x1800547cb  jmp     loc_1800546BF
0x1800547d0  mov     rcx, rsi
0x1800547d3  lea     rdx, [rsp+38h+pulResult]; pulResult
0x1800547d8  shl     rcx, 2; ullOperand
0x1800547dc  call    ULongLongToULong
0x1800547e1  mov     ebx, eax
0x1800547e3  test    eax, eax
0x1800547e5  jns     short loc_1800547FB
0x1800547e7  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x1800547ed  jnz     loc_18005473B
0x1800547f3  test    eax, eax
0x1800547f5  js      loc_1800546D6
0x1800547fb  mov     ecx, [rsp+38h+pulResult]; cb
0x1800547ff  call    cs:__imp_CoTaskMemAlloc
0x180054805  test    rax, rax
0x180054808  jz      loc_180054902
0x18005480e  mov     r10d, 1
0x180054814  mov     r9d, ebp
0x180054817  test    esi, esi
0x180054819  jz      loc_1800546BF
0x18005481f  mov     r8d, r9d
0x180054822  inc     r9d
0x180054825  mov     ecx, [rdi+r8*4]
0x180054829  movzx   edx, byte ptr [rdi+r8*4+1]
0x18005482f  shl     ecx, 8
0x180054832  or      edx, ecx
0x180054834  movzx   ecx, byte ptr [rdi+r8*4+2]
0x18005483a  shl     edx, 8
0x18005483d  or      edx, ecx
0x18005483f  movzx   ecx, byte ptr [rdi+r8*4+3]
0x180054845  shl     edx, 8
0x180054848  or      edx, ecx
0x18005484a  mov     [rax+r8*4], edx
0x18005484e  cmp     r9d, esi
0x180054851  jb      short loc_18005481F
0x180054853  jmp     loc_1800546BF
0x180054858  mov     rcx, rsi
0x18005485b  lea     rdx, [rsp+38h+pulResult]; pulResult
0x180054860  add     rcx, rcx; ullOperand
0x180054863  call    ULongLongToULong
0x180054868  mov     ebx, eax
0x18005486a  test    eax, eax
0x18005486c  jns     short loc_180054882
0x18005486e  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180054874  jnz     loc_18005473B
0x18005487a  test    eax, eax
0x18005487c  js      loc_1800546D6
0x180054882  mov     ecx, [rsp+38h+pulResult]; cb
0x180054886  call    cs:__imp_CoTaskMemAlloc
0x18005488c  test    rax, rax
0x18005488f  jz      short loc_180054902
0x180054891  mov     r10d, 1
0x180054897  mov     r9d, ebp
0x18005489a  test    esi, esi
0x18005489c  jz      loc_1800546BF
0x1800548a2  mov     r8d, r9d
0x1800548a5  inc     r9d
0x1800548a8  movzx   ecx, word ptr [rdi+r8*2]
0x1800548ad  movzx   edx, byte ptr [rdi+r8*2+1]
0x1800548b3  shl     cx, 8
0x1800548b7  or      dx, cx
0x1800548ba  mov     [rax+r8*2], dx
0x1800548bf  cmp     r9d, esi
0x1800548c2  jb      short loc_1800548A2
0x1800548c4  jmp     loc_1800546BF
0x1800548c9  cmp     [rsp+38h+arg_20], ebp
0x1800548cd  jz      loc_18005473F
0x1800548d3  mov     rax, rdi
0x1800548d6  jmp     loc_18005477F
0x1800548db  mov     ecx, eax; cb
0x1800548dd  call    cs:__imp_CoTaskMemAlloc
0x1800548e3  test    rax, rax
0x1800548e6  jz      short loc_180054902
0x1800548e8  mov     r10d, 1
0x1800548ee  jmp     loc_180054659
0x1800548f3  cmp     [rsp+38h+arg_20], ebp
0x1800548f7  jz      loc_180054858
0x1800548fd  mov     rax, rdi
0x180054900  jmp     short loc_180054897
0x180054902  mov     ebx, 8007000Eh
0x180054907  jmp     loc_18005472A
0x18005490c  mov     [r14], rax
0x18005490f  jmp     loc_1800546C8
0x180054914  mov     [rax], r10d
0x180054917  jmp     loc_1800546D6
```
