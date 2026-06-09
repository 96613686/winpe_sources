# CLibTiffFrameEncode::FixStripOffsets(IWICMetadataWriter *,_ULARGE_INTEGER)

- ea: `0x1800d9a18`
- end: `0x1800d9c48`
- name: `?FixStripOffsets@CLibTiffFrameEncode@@AEAAJPEAUIWICMetadataWriter@@T_ULARGE_INTEGER@@@Z`
- size: `560`
- prototype: `int(CLibTiffFrameEncode *__hidden this, struct IWICMetadataWriter *, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ba070`

## callees

- `0x1800554f0`
- `0x18006ac40`
- `0x1800bb784`
- `0x1800d9a18`
- `0x1800d9c50`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9af1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9b6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9af1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9b6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d9c16`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800d9c16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9c24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9c24`

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
0x1800d9a18  mov     [rsp-28h+arg_10], rbx
0x1800d9a1d  mov     [rsp-28h+arg_18], rsi
0x1800d9a22  mov     [rsp-28h+puResult], rcx
0x1800d9a27  push    rbp
0x1800d9a28  push    rdi
0x1800d9a29  push    r12
0x1800d9a2b  push    r14
0x1800d9a2d  push    r15
0x1800d9a2f  mov     rbp, rsp
0x1800d9a32  sub     rsp, 80h
0x1800d9a39  xor     r12d, r12d
0x1800d9a3c  xor     eax, eax
0x1800d9a3e  mov     [rbp+var_40], rax
0x1800d9a42  xorps   xmm0, xmm0
0x1800d9a45  mov     r15, rdx
0x1800d9a48  mov     edi, r12d
0x1800d9a4b  movups  xmmword ptr [rbp+pvar], xmm0
0x1800d9a4f  test    rdx, rdx
0x1800d9a52  jnz     short loc_1800D9A5E
0x1800d9a54  mov     ebx, 80070057h
0x1800d9a59  jmp     loc_1800D9C02
0x1800d9a5e  xorps   xmm1, xmm1
0x1800d9a61  mov     dword ptr [rbp+puResult], r12d
0x1800d9a65  lea     rdx, [rbp+pulResult]; pulResult
0x1800d9a69  mov     [rbp+pulResult], r12d
0x1800d9a6d  mov     rcx, r8; ullOperand
0x1800d9a70  mov     [rbp+var_10], rax
0x1800d9a74  movups  [rbp+var_38], xmm1
0x1800d9a78  mov     [rbp+var_28], rax
0x1800d9a7c  movups  [rbp+var_20], xmm0
0x1800d9a80  call    ULongLongToULong
0x1800d9a85  mov     ebx, eax
0x1800d9a87  test    eax, eax
0x1800d9a89  jns     short loc_1800D9A9F
0x1800d9a8b  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d9a92  jz      loc_1800D9C12
0x1800d9a98  mov     ecx, eax
0x1800d9a9a  jmp     loc_1800D9C0D
0x1800d9a9f  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x1800d9aa3  mov     rcx, r15; struct IWICMetadataReader *
0x1800d9aa6  call    ?GetStripOffsets@CLibTiffFrameUtil@@SAJPEAUIWICMetadataReader@@PEAUtagPROPVARIANT@@@Z; CLibTiffFrameUtil::GetStripOffsets(IWICMetadataReader *,tagPROPVARIANT *)
0x1800d9aab  mov     ebx, eax
0x1800d9aad  test    eax, eax
0x1800d9aaf  js      short loc_1800D9A8B
0x1800d9ab1  mov     eax, 1000h
0x1800d9ab6  mov     ebx, 13h
0x1800d9abb  test    word ptr [rbp+pvar], ax
0x1800d9abf  jz      loc_1800D9B67
0x1800d9ac5  movzx   eax, word ptr [rbp+pvar]
0x1800d9ac9  lea     r14d, [rbx-1]
0x1800d9acd  mov     esi, dword ptr [rbp+pvar+8]
0x1800d9ad0  btr     eax, 0Ch
0x1800d9ad4  cmp     eax, r14d
0x1800d9ad7  jnz     short loc_1800D9B4C
0x1800d9ad9  mov     ecx, esi
0x1800d9adb  lea     rdx, [rbp+puResult]; puResult
0x1800d9adf  shl     rcx, 2; ullOperand
0x1800d9ae3  call    ULongLongToUInt
0x1800d9ae8  mov     ebx, eax
0x1800d9aea  test    eax, eax
0x1800d9aec  js      short loc_1800D9A8B
0x1800d9aee  mov     ecx, dword ptr [rbp+puResult]; cb
0x1800d9af1  call    cs:__imp_CoTaskMemAlloc
0x1800d9af7  mov     rdi, rax
0x1800d9afa  test    rax, rax
0x1800d9afd  jnz     short loc_1800D9B09
0x1800d9aff  mov     ebx, 8007000Eh
0x1800d9b04  jmp     loc_1800D9C02
0x1800d9b09  mov     r8d, r12d
0x1800d9b0c  test    esi, esi
0x1800d9b0e  jz      short loc_1800D9B26
0x1800d9b10  mov     rax, [rbp+var_40]
0x1800d9b14  mov     edx, r8d
0x1800d9b17  inc     r8d
0x1800d9b1a  movzx   ecx, word ptr [rax+rdx*2]
0x1800d9b1e  mov     [rdi+rdx*4], ecx
0x1800d9b21  cmp     r8d, esi
0x1800d9b24  jb      short loc_1800D9B10
0x1800d9b26  mov     ebx, 13h
0x1800d9b2b  mov     r9d, [rbp+pulResult]
0x1800d9b2f  mov     ecx, r12d
0x1800d9b32  cmp     ecx, esi
0x1800d9b34  jnb     short loc_1800D9BAB
0x1800d9b36  mov     edx, ecx
0x1800d9b38  mov     eax, [rdi+rdx*4]
0x1800d9b3b  lea     r8d, [rax+r9]
0x1800d9b3f  cmp     r8d, eax
0x1800d9b42  jb      short loc_1800D9B9D
0x1800d9b44  mov     [rdi+rdx*4], r8d
0x1800d9b48  inc     ecx
0x1800d9b4a  jmp     short loc_1800D9B32
0x1800d9b4c  cmp     eax, ebx
0x1800d9b4e  jnz     loc_1800D9BFD
0x1800d9b54  mov     rdi, [rbp+var_40]
0x1800d9b58  xorps   xmm0, xmm0
0x1800d9b5b  xor     eax, eax
0x1800d9b5d  movups  xmmword ptr [rbp+pvar], xmm0
0x1800d9b61  mov     [rbp+var_40], rax
0x1800d9b65  jmp     short loc_1800D9B2B
0x1800d9b67  mov     ecx, 4; cb
0x1800d9b6c  call    cs:__imp_CoTaskMemAlloc
0x1800d9b72  mov     rdi, rax
0x1800d9b75  test    rax, rax
0x1800d9b78  jz      short loc_1800D9AFF
0x1800d9b7a  mov     esi, 1
0x1800d9b7f  lea     r14d, [rsi+11h]
0x1800d9b83  cmp     word ptr [rbp+pvar], r14w
0x1800d9b88  jnz     short loc_1800D9B92
0x1800d9b8a  movzx   eax, word ptr [rbp+pvar+8]
0x1800d9b8e  mov     [rdi], eax
0x1800d9b90  jmp     short loc_1800D9B2B
0x1800d9b92  cmp     word ptr [rbp+pvar], bx
0x1800d9b96  jnz     short loc_1800D9BFD
0x1800d9b98  mov     eax, dword ptr [rbp+pvar+8]
0x1800d9b9b  jmp     short loc_1800D9B8E
0x1800d9b9d  mov     dword ptr [rdi+rdx*4], 0FFFFFFFFh
0x1800d9ba4  mov     ebx, 80070216h
0x1800d9ba9  jmp     short loc_1800D9C02
0x1800d9bab  cmp     esi, 1
0x1800d9bae  jnz     short loc_1800D9BBB
0x1800d9bb0  mov     word ptr [rbp+var_38], bx
0x1800d9bb4  mov     eax, [rdi]
0x1800d9bb6  mov     dword ptr [rbp+var_38+8], eax
0x1800d9bb9  jmp     short loc_1800D9BCB
0x1800d9bbb  mov     eax, 1013h
0x1800d9bc0  mov     dword ptr [rbp+var_38+8], esi
0x1800d9bc3  mov     word ptr [rbp+var_38], ax
0x1800d9bc7  mov     [rbp+var_28], rdi
0x1800d9bcb  mov     eax, 111h
0x1800d9bd0  mov     word ptr [rbp+var_20], r14w
0x1800d9bd5  mov     word ptr [rbp+var_20+8], ax
0x1800d9bd9  lea     r9, [rbp+var_38]
0x1800d9bdd  mov     rax, [r15]
0x1800d9be0  lea     r8, [rbp+var_20]
0x1800d9be4  xor     edx, edx
0x1800d9be6  mov     rcx, r15
0x1800d9be9  mov     rax, [rax+48h]
0x1800d9bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bf2  mov     ebx, eax
0x1800d9bf4  test    eax, eax
0x1800d9bf6  jns     short loc_1800D9C12
0x1800d9bf8  jmp     loc_1800D9A8B
0x1800d9bfd  mov     ebx, 88982F60h
0x1800d9c02  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800d9c09  jz      short loc_1800D9C12
0x1800d9c0b  mov     ecx, ebx; int
0x1800d9c0d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d9c12  lea     rcx, [rbp+pvar]; pvar
0x1800d9c16  call    cs:__imp_PropVariantClear
0x1800d9c1c  test    rdi, rdi
0x1800d9c1f  jz      short loc_1800D9C2A
0x1800d9c21  mov     rcx, rdi; pv
0x1800d9c24  call    cs:__imp_CoTaskMemFree
0x1800d9c2a  lea     r11, [rsp+80h+var_s0]
0x1800d9c32  mov     eax, ebx
0x1800d9c34  mov     rbx, [r11+40h]
0x1800d9c38  mov     rsi, [r11+48h]
0x1800d9c3c  mov     rsp, r11
0x1800d9c3f  pop     r15
0x1800d9c41  pop     r14
0x1800d9c43  pop     r12
0x1800d9c45  pop     rdi
0x1800d9c46  pop     rbp
0x1800d9c47  retn
```
