# CLibTiffFrameEncode::FixStripOffsets(IWICMetadataWriter *,_ULARGE_INTEGER)

- ea: `0x1800dc608`
- end: `0x1800dc855`
- name: `?FixStripOffsets@CLibTiffFrameEncode@@AEAAJPEAUIWICMetadataWriter@@T_ULARGE_INTEGER@@@Z`
- size: `589`
- prototype: `int(CLibTiffFrameEncode *__hidden this, struct IWICMetadataWriter *, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bc28c`

## callees

- `0x180039480`
- `0x18004a800`
- `0x1800bd9d4`
- `0x1800dc608`
- `0x1800dc85c`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc6e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc6e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800dc762`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dc816`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800dc816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc82a`

## pseudocode

```c
__int64 __fastcall CLibTiffFrameEncode::FixStripOffsets(
        CLibTiffFrameEncode *this,
        struct IWICMetadataReader *a2,
        union _ULARGE_INTEGER a3)
{
  _DWORD *pElems; // rdi
  unsigned int v5; // ebx
  HRESULT StripOffsets; // eax
  int v7; // ecx
  unsigned int ulVal; // esi
  int v9; // eax
  unsigned int i; // r8d
  __int64 v11; // rdx
  ULONG v12; // r9d
  unsigned int j; // ecx
  unsigned int v14; // eax
  LONG uiVal; // eax
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-50h] BYREF
  __int128 v18; // [rsp+48h] [rbp-38h] BYREF
  _DWORD *v19; // [rsp+58h] [rbp-28h]
  __int128 v20; // [rsp+60h] [rbp-20h] BYREF
  __int64 v21; // [rsp+70h] [rbp-10h]
  CLibTiffFrameEncode *puResult; // [rsp+B0h] [rbp+30h] BYREF
  ULONG pulResult; // [rsp+B8h] [rbp+38h] BYREF

  puResult = this;
  pElems = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( !a2 )
  {
    v5 = -2147024809;
LABEL_33:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_36;
    v7 = v5;
    goto LABEL_35;
  }
  LODWORD(puResult) = 0;
  pulResult = 0;
  v21 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  StripOffsets = ULongLongToULong(a3.QuadPart, &pulResult);
  v5 = StripOffsets;
  if ( StripOffsets < 0
    || (StripOffsets = CLibTiffFrameUtil::GetStripOffsets(a2, &pvar), v5 = StripOffsets, StripOffsets < 0) )
  {
LABEL_4:
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_36;
    v7 = StripOffsets;
LABEL_35:
    DoStackCapture(v7);
    goto LABEL_36;
  }
  if ( (pvar.vt & 0x1000) == 0 )
  {
    pElems = CoTaskMemAlloc(4u);
    if ( !pElems )
      goto LABEL_11;
    ulVal = 1;
    if ( pvar.vt == 18 )
    {
      uiVal = pvar.uiVal;
    }
    else
    {
      if ( pvar.vt != 19 )
        goto LABEL_32;
      uiVal = pvar.lVal;
    }
    *pElems = uiVal;
    goto LABEL_14;
  }
  ulVal = pvar.ulVal;
  v9 = pvar.vt & 0xEFFF;
  if ( v9 != 18 )
  {
    if ( v9 == 19 )
    {
      pElems = pvar.cal.pElems;
      memset(&pvar, 0, sizeof(pvar));
      goto LABEL_14;
    }
LABEL_32:
    v5 = -2003292320;
    goto LABEL_33;
  }
  StripOffsets = ULongLongToUInt(4LL * pvar.ulVal, (UINT *)&puResult);
  v5 = StripOffsets;
  if ( StripOffsets < 0 )
    goto LABEL_4;
  pElems = CoTaskMemAlloc((unsigned int)puResult);
  if ( !pElems )
  {
LABEL_11:
    v5 = -2147024882;
    goto LABEL_33;
  }
  for ( i = 0; i < ulVal; pElems[v11] = *(unsigned __int16 *)&pvar.bstrblobVal.pData[2 * v11] )
    v11 = i++;
LABEL_14:
  v12 = pulResult;
  for ( j = 0; j < ulVal; ++j )
  {
    v14 = pElems[j];
    if ( v14 + v12 < v14 )
    {
      pElems[j] = -1;
      v5 = -2147024362;
      goto LABEL_33;
    }
    pElems[j] = v14 + v12;
  }
  if ( ulVal == 1 )
  {
    LOWORD(v18) = 19;
    DWORD2(v18) = *pElems;
  }
  else
  {
    DWORD2(v18) = ulVal;
    LOWORD(v18) = 4115;
    v19 = pElems;
  }
  LOWORD(v20) = 18;
  WORD4(v20) = 273;
  StripOffsets = ((__int64 (__fastcall *)(struct IWICMetadataReader *, _QWORD, __int128 *, __int128 *))a2->lpVtbl[1].QueryInterface)(
                   a2,
                   0,
                   &v20,
                   &v18);
  v5 = StripOffsets;
  if ( StripOffsets < 0 )
    goto LABEL_4;
LABEL_36:
  PropVariantClear((PROPVARIANT *)&pvar);
  if ( pElems )
    CoTaskMemFree(pElems);
  return v5;
}

```

## disassembly

```asm
0x1800dc608  mov     [rsp-28h+arg_10], rbx
0x1800dc60d  mov     [rsp-28h+arg_18], rsi
0x1800dc612  mov     [rsp-28h+puResult], rcx
0x1800dc617  push    rbp
0x1800dc618  push    rdi
0x1800dc619  push    r12
0x1800dc61b  push    r14
0x1800dc61d  push    r15
0x1800dc61f  mov     rbp, rsp
0x1800dc622  sub     rsp, 80h
0x1800dc629  xor     r12d, r12d
0x1800dc62c  xor     eax, eax
0x1800dc62e  mov     [rbp+var_40], rax
0x1800dc632  xorps   xmm0, xmm0
0x1800dc635  mov     r15, rdx
0x1800dc638  mov     edi, r12d
0x1800dc63b  movups  xmmword ptr [rbp+pvar], xmm0
0x1800dc63f  test    rdx, rdx
0x1800dc642  jnz     short loc_1800DC64E
0x1800dc644  mov     ebx, 80070057h
0x1800dc649  jmp     loc_1800DC802
0x1800dc64e  xorps   xmm1, xmm1
0x1800dc651  mov     dword ptr [rbp+puResult], r12d
0x1800dc655  lea     rdx, [rbp+pulResult]; pulResult
0x1800dc659  mov     [rbp+pulResult], r12d
0x1800dc65d  mov     rcx, r8; ullOperand
0x1800dc660  mov     [rbp+var_10], rax
0x1800dc664  movups  [rbp+var_38], xmm1
0x1800dc668  mov     [rbp+var_28], rax
0x1800dc66c  movups  [rbp+var_20], xmm0
0x1800dc670  call    ULongLongToULong
0x1800dc675  mov     ebx, eax
0x1800dc677  test    eax, eax
0x1800dc679  jns     short loc_1800DC68F
0x1800dc67b  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800dc682  jz      loc_1800DC812
0x1800dc688  mov     ecx, eax
0x1800dc68a  jmp     loc_1800DC80D
0x1800dc68f  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x1800dc693  mov     rcx, r15; struct IWICMetadataReader *
0x1800dc696  call    ?GetStripOffsets@CLibTiffFrameUtil@@SAJPEAUIWICMetadataReader@@PEAUtagPROPVARIANT@@@Z; CLibTiffFrameUtil::GetStripOffsets(IWICMetadataReader *,tagPROPVARIANT *)
0x1800dc69b  mov     ebx, eax
0x1800dc69d  test    eax, eax
0x1800dc69f  js      short loc_1800DC67B
0x1800dc6a1  mov     eax, 1000h
0x1800dc6a6  mov     ebx, 13h
0x1800dc6ab  test    word ptr [rbp+pvar], ax
0x1800dc6af  jz      loc_1800DC75D
0x1800dc6b5  movzx   eax, word ptr [rbp+pvar]
0x1800dc6b9  lea     r14d, [rbx-1]
0x1800dc6bd  mov     esi, dword ptr [rbp+pvar+8]
0x1800dc6c0  btr     eax, 0Ch
0x1800dc6c4  cmp     eax, r14d
0x1800dc6c7  jnz     short loc_1800DC742
0x1800dc6c9  mov     ecx, esi
0x1800dc6cb  lea     rdx, [rbp+puResult]; puResult
0x1800dc6cf  shl     rcx, 2; ullOperand
0x1800dc6d3  call    ULongLongToUInt
0x1800dc6d8  mov     ebx, eax
0x1800dc6da  test    eax, eax
0x1800dc6dc  js      short loc_1800DC67B
0x1800dc6de  mov     ecx, dword ptr [rbp+puResult]; cb
0x1800dc6e1  call    cs:__imp_CoTaskMemAlloc
0x1800dc6e8  nop     dword ptr [rax+rax+00h]
0x1800dc6ed  mov     rdi, rax
0x1800dc6f0  test    rax, rax
0x1800dc6f3  jnz     short loc_1800DC6FF
0x1800dc6f5  mov     ebx, 8007000Eh
0x1800dc6fa  jmp     loc_1800DC802
0x1800dc6ff  mov     r8d, r12d
0x1800dc702  test    esi, esi
0x1800dc704  jz      short loc_1800DC71C
0x1800dc706  mov     rax, [rbp+var_40]
0x1800dc70a  mov     edx, r8d
0x1800dc70d  inc     r8d
0x1800dc710  movzx   ecx, word ptr [rax+rdx*2]
0x1800dc714  mov     [rdi+rdx*4], ecx
0x1800dc717  cmp     r8d, esi
0x1800dc71a  jb      short loc_1800DC706
0x1800dc71c  mov     ebx, 13h
0x1800dc721  mov     r9d, [rbp+pulResult]
0x1800dc725  mov     ecx, r12d
0x1800dc728  cmp     ecx, esi
0x1800dc72a  jnb     short loc_1800DC7AB
0x1800dc72c  mov     edx, ecx
0x1800dc72e  mov     eax, [rdi+rdx*4]
0x1800dc731  lea     r8d, [rax+r9]
0x1800dc735  cmp     r8d, eax
0x1800dc738  jb      short loc_1800DC79D
0x1800dc73a  mov     [rdi+rdx*4], r8d
0x1800dc73e  inc     ecx
0x1800dc740  jmp     short loc_1800DC728
0x1800dc742  cmp     eax, ebx
0x1800dc744  jnz     loc_1800DC7FD
0x1800dc74a  mov     rdi, [rbp+var_40]
0x1800dc74e  xorps   xmm0, xmm0
0x1800dc751  xor     eax, eax
0x1800dc753  movups  xmmword ptr [rbp+pvar], xmm0
0x1800dc757  mov     [rbp+var_40], rax
0x1800dc75b  jmp     short loc_1800DC721
0x1800dc75d  mov     ecx, 4; cb
0x1800dc762  call    cs:__imp_CoTaskMemAlloc
0x1800dc769  nop     dword ptr [rax+rax+00h]
0x1800dc76e  mov     rdi, rax
0x1800dc771  test    rax, rax
0x1800dc774  jz      loc_1800DC6F5
0x1800dc77a  mov     esi, 1
0x1800dc77f  lea     r14d, [rsi+11h]
0x1800dc783  cmp     word ptr [rbp+pvar], r14w
0x1800dc788  jnz     short loc_1800DC792
0x1800dc78a  movzx   eax, word ptr [rbp+pvar+8]
0x1800dc78e  mov     [rdi], eax
0x1800dc790  jmp     short loc_1800DC721
0x1800dc792  cmp     word ptr [rbp+pvar], bx
0x1800dc796  jnz     short loc_1800DC7FD
0x1800dc798  mov     eax, dword ptr [rbp+pvar+8]
0x1800dc79b  jmp     short loc_1800DC78E
0x1800dc79d  mov     dword ptr [rdi+rdx*4], 0FFFFFFFFh
0x1800dc7a4  mov     ebx, 80070216h
0x1800dc7a9  jmp     short loc_1800DC802
0x1800dc7ab  cmp     esi, 1
0x1800dc7ae  jnz     short loc_1800DC7BB
0x1800dc7b0  mov     word ptr [rbp+var_38], bx
0x1800dc7b4  mov     eax, [rdi]
0x1800dc7b6  mov     dword ptr [rbp+var_38+8], eax
0x1800dc7b9  jmp     short loc_1800DC7CB
0x1800dc7bb  mov     eax, 1013h
0x1800dc7c0  mov     dword ptr [rbp+var_38+8], esi
0x1800dc7c3  mov     word ptr [rbp+var_38], ax
0x1800dc7c7  mov     [rbp+var_28], rdi
0x1800dc7cb  mov     eax, 111h
0x1800dc7d0  mov     word ptr [rbp+var_20], r14w
0x1800dc7d5  mov     word ptr [rbp+var_20+8], ax
0x1800dc7d9  lea     r9, [rbp+var_38]
0x1800dc7dd  mov     rax, [r15]
0x1800dc7e0  lea     r8, [rbp+var_20]
0x1800dc7e4  xor     edx, edx
0x1800dc7e6  mov     rcx, r15
0x1800dc7e9  mov     rax, [rax+48h]
0x1800dc7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc7f2  mov     ebx, eax
0x1800dc7f4  test    eax, eax
0x1800dc7f6  jns     short loc_1800DC812
0x1800dc7f8  jmp     loc_1800DC67B
0x1800dc7fd  mov     ebx, 88982F60h
0x1800dc802  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800dc809  jz      short loc_1800DC812
0x1800dc80b  mov     ecx, ebx; int
0x1800dc80d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800dc812  lea     rcx, [rbp+pvar]; pvar
0x1800dc816  call    cs:__imp_PropVariantClear
0x1800dc81d  nop     dword ptr [rax+rax+00h]
0x1800dc822  test    rdi, rdi
0x1800dc825  jz      short loc_1800DC836
0x1800dc827  mov     rcx, rdi; pv
0x1800dc82a  call    cs:__imp_CoTaskMemFree
0x1800dc831  nop     dword ptr [rax+rax+00h]
0x1800dc836  lea     r11, [rsp+80h+var_s0]
0x1800dc83e  mov     eax, ebx
0x1800dc840  mov     rbx, [r11+40h]
0x1800dc844  mov     rsi, [r11+48h]
0x1800dc848  mov     rsp, r11
0x1800dc84b  pop     r15
0x1800dc84d  pop     r14
0x1800dc84f  pop     r12
0x1800dc851  pop     rdi
0x1800dc852  pop     rbp
0x1800dc853  retn
```
