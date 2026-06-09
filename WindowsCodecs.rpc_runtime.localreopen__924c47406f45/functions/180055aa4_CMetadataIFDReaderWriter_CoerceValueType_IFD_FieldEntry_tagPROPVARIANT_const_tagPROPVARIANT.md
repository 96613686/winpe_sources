# CMetadataIFDReaderWriter::CoerceValueType(IFD::FieldEntry *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180055aa4`
- end: `0x180055c84`
- name: `?CoerceValueType@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEBUtagPROPVARIANT@@PEAU4@@Z`
- size: `480`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *this, struct IFD::FieldEntry *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800374f0`
- `0x180055e7c`

## callees

- `0x180022d44`
- `0x180054fec`
- `0x180055aa4`
- `0x18006ac40`
- `0x1800bb784`
- `0x1800c35d0`
- `0x1800caea4`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180055af6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180055af6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055bcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055c79`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::CoerceValueType(
        CMetadataIFDReaderWriter *this,
        struct IFD::FieldEntry *a2,
        const struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  unsigned int v6; // ebp
  __int64 v7; // r8
  __int64 v8; // r9
  HRESULT v9; // eax
  unsigned int v10; // ebx
  HRESULT v12; // eax
  int v13; // ecx
  unsigned int v14; // r15d
  BYTE *v15; // rax
  BYTE *v16; // rdi
  __int64 i; // r15
  int v18; // eax
  __int64 j; // rsi
  void *v20; // rcx
  CMetadataIFDReaderWriter *puResult; // [rsp+60h] [rbp+8h] BYREF

  puResult = this;
  *(_OWORD *)&a4->vt = 0;
  a4->bstrblobVal.pData = 0;
  v6 = 0;
  if ( (unsigned int)IFD::FieldEntry::IsCommentTag(a2) )
  {
    v12 = CoerceStringVectors(a3, a4);
    v10 = v12;
    if ( v12 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v10;
      goto LABEL_14;
    }
    v12 = ConvertCommentToBlob((PROPVARIANT *)a4);
    v10 = v12;
    if ( v12 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v10;
      goto LABEL_14;
    }
    goto LABEL_5;
  }
  if ( *(_WORD *)v7 == 31 )
  {
    v12 = CoerceWideStrToAnsiStrCodepage(a3->bstrVal, (char **)(v8 + 8), 0);
    v10 = v12;
    if ( v12 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v10;
      goto LABEL_14;
    }
    a4->vt = 30;
LABEL_5:
    if ( (v10 & 0x80000000) == 0 )
      return v10;
    v16 = 0;
    goto LABEL_35;
  }
  if ( *(_WORD *)v7 != 4127 )
  {
    v9 = PropVariantCopy((PROPVARIANT *)v8, (const PROPVARIANT *)v7);
    v10 = v9;
    if ( v9 < 0 && (_DWORD)g_doStackCaptures )
      DoStackCapture(v9);
    goto LABEL_5;
  }
  LODWORD(puResult) = 0;
  v6 = *(_DWORD *)(v7 + 8);
  v12 = ULongLongToUInt(8LL * v6, (UINT *)&puResult);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      return v10;
LABEL_14:
    v13 = v12;
LABEL_15:
    DoStackCapture(v13);
    return v10;
  }
  v14 = (unsigned int)puResult;
  v15 = (BYTE *)CoTaskMemAlloc((unsigned int)puResult);
  v16 = v15;
  if ( !v15 )
  {
    v10 = -2147024882;
    if ( !(_DWORD)g_doStackCaptures )
      return v10;
    v13 = -2147024882;
    goto LABEL_15;
  }
  memset_0(v15, 0, v14);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v6 )
    {
      a4->bstrblobVal.pData = v16;
      a4->lVal = v6;
      a4->vt = 4126;
      goto LABEL_5;
    }
    v18 = CoerceWideStrToAnsiStrCodepage(*(LPCWCH *)&a3->bstrblobVal.pData[8 * i], (char **)&v16[8 * i], 0);
    v10 = v18;
    if ( v18 < 0 )
      break;
  }
  if ( !(_DWORD)g_doStackCaptures )
  {
LABEL_35:
    if ( !v16 )
      return v10;
    goto LABEL_36;
  }
  DoStackCapture(v18);
LABEL_36:
  for ( j = 0; (unsigned int)j < v6; j = (unsigned int)(j + 1) )
  {
    v20 = *(void **)&v16[8 * j];
    if ( v20 )
      CoTaskMemFree(v20);
  }
  CoTaskMemFree(v16);
  return v10;
}

```

## disassembly

```asm
0x180055aa4  mov     [rsp+puResult], rcx
0x180055aa9  push    rbx
0x180055aaa  push    rbp
0x180055aab  push    rsi
0x180055aac  push    rdi
0x180055aad  push    r14
0x180055aaf  push    r15
0x180055ab1  sub     rsp, 28h
0x180055ab5  xor     eax, eax
0x180055ab7  xorps   xmm0, xmm0
0x180055aba  movups  xmmword ptr [r9], xmm0
0x180055abe  mov     rcx, rdx; this
0x180055ac1  mov     [r9+10h], rax
0x180055ac5  mov     rsi, r9
0x180055ac8  mov     r14, r8
0x180055acb  xor     ebp, ebp
0x180055acd  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x180055ad2  test    eax, eax
0x180055ad4  jnz     short loc_180055B19
0x180055ad6  cmp     word ptr [r8], 1Fh
0x180055adb  jz      loc_180055B68
0x180055ae1  mov     eax, 101Fh
0x180055ae6  cmp     [r8], ax
0x180055aea  jz      loc_180055B94
0x180055af0  mov     rdx, r8; pvarSrc
0x180055af3  mov     rcx, r9; pvarDest
0x180055af6  call    cs:__imp_PropVariantCopy
0x180055afc  mov     ebx, eax
0x180055afe  test    eax, eax
0x180055b00  js      short loc_180055B46
0x180055b02  test    ebx, ebx
0x180055b04  js      loc_180055C4D
0x180055b0a  mov     eax, ebx
0x180055b0c  add     rsp, 28h
0x180055b10  pop     r15
0x180055b12  pop     r14
0x180055b14  pop     rdi
0x180055b15  pop     rsi
0x180055b16  pop     rbp
0x180055b17  pop     rbx
0x180055b18  retn
0x180055b19  mov     rdx, rsi; struct tagPROPVARIANT *
0x180055b1c  mov     rcx, r14; struct tagPROPVARIANT *
0x180055b1f  call    ?CoerceStringVectors@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z; CoerceStringVectors(tagPROPVARIANT const &,tagPROPVARIANT *)
0x180055b24  mov     ebx, eax
0x180055b26  test    eax, eax
0x180055b28  js      short loc_180055B57
0x180055b2a  mov     rcx, rsi; pvar
0x180055b2d  call    ?ConvertCommentToBlob@@YAJPEAUtagPROPVARIANT@@@Z; ConvertCommentToBlob(tagPROPVARIANT *)
0x180055b32  mov     ebx, eax
0x180055b34  test    eax, eax
0x180055b36  jns     short loc_180055B02
0x180055b38  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180055b3e  jnz     short loc_180055B5F
0x180055b40  test    eax, eax
0x180055b42  js      short loc_180055B0A
0x180055b44  jmp     short loc_180055B02
0x180055b46  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180055b4c  jz      short loc_180055B02
0x180055b4e  mov     ecx, eax; int
0x180055b50  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180055b55  jmp     short loc_180055B02
0x180055b57  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180055b5d  jz      short loc_180055B0A
0x180055b5f  mov     ecx, eax; int
0x180055b61  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180055b66  jmp     short loc_180055B0A
0x180055b68  mov     rcx, [r14+8]; lpWideCharStr
0x180055b6c  lea     rdx, [r9+8]; char **
0x180055b70  xor     r8d, r8d; unsigned int
0x180055b73  call    ?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z; CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)
0x180055b78  mov     ebx, eax
0x180055b7a  test    eax, eax
0x180055b7c  jns     short loc_180055B8A
0x180055b7e  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180055b84  jnz     short loc_180055B5F
0x180055b86  test    eax, eax
0x180055b88  js      short loc_180055B0A
0x180055b8a  mov     word ptr [rsi], 1Eh
0x180055b8f  jmp     loc_180055B02
0x180055b94  mov     dword ptr [rsp+58h+puResult], ebp
0x180055b98  lea     rdx, [rsp+58h+puResult]; puResult
0x180055b9d  mov     ebp, [r8+8]
0x180055ba1  mov     ecx, ebp
0x180055ba3  shl     rcx, 3; ullOperand
0x180055ba7  call    ULongLongToUInt
0x180055bac  mov     ebx, eax
0x180055bae  test    eax, eax
0x180055bb0  jns     short loc_180055BC3
0x180055bb2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180055bb9  jnz     short loc_180055B5F
0x180055bbb  test    eax, eax
0x180055bbd  js      loc_180055B0A
0x180055bc3  mov     r15d, dword ptr [rsp+58h+puResult]
0x180055bc8  mov     ecx, r15d; cb
0x180055bcb  call    cs:__imp_CoTaskMemAlloc
0x180055bd1  mov     rdi, rax
0x180055bd4  test    rax, rax
0x180055bd7  jz      short loc_180055BFF
0x180055bd9  mov     r8d, r15d; Size
0x180055bdc  xor     edx, edx; Val
0x180055bde  mov     rcx, rax; void *
0x180055be1  call    memset_0
0x180055be6  xor     r15d, r15d
0x180055be9  cmp     r15d, ebp
0x180055bec  jb      short loc_180055C18
0x180055bee  mov     [rsi+10h], rdi
0x180055bf2  mov     [rsi+8], ebp
0x180055bf5  mov     word ptr [rsi], 101Eh
0x180055bfa  jmp     loc_180055B02
0x180055bff  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180055c06  mov     ebx, 8007000Eh
0x180055c0b  jz      loc_180055B0A
0x180055c11  mov     ecx, ebx
0x180055c13  jmp     loc_180055B61
0x180055c18  mov     rcx, [r14+10h]
0x180055c1c  lea     rdx, [rdi+r15*8]; char **
0x180055c20  xor     r8d, r8d; unsigned int
0x180055c23  mov     rcx, [rcx+r15*8]; lpWideCharStr
0x180055c27  call    ?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z; CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)
0x180055c2c  mov     ebx, eax
0x180055c2e  test    eax, eax
0x180055c30  jns     short loc_180055C48
0x180055c32  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180055c39  jz      short loc_180055C44
0x180055c3b  mov     ecx, eax; int
0x180055c3d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180055c42  jmp     short loc_180055C58
0x180055c44  test    eax, eax
0x180055c46  js      short loc_180055C4F
0x180055c48  inc     r15d
0x180055c4b  jmp     short loc_180055BE9
0x180055c4d  xor     edi, edi
0x180055c4f  test    rdi, rdi
0x180055c52  jz      loc_180055B0A
0x180055c58  xor     esi, esi
0x180055c5a  mov     r14, rdi
0x180055c5d  test    ebp, ebp
0x180055c5f  jz      short loc_180055C76
0x180055c61  mov     rcx, [r14+rsi*8]; pv
0x180055c65  test    rcx, rcx
0x180055c68  jz      short loc_180055C70
0x180055c6a  call    cs:__imp_CoTaskMemFree
0x180055c70  inc     esi
0x180055c72  cmp     esi, ebp
0x180055c74  jb      short loc_180055C61
0x180055c76  mov     rcx, rdi; pv
0x180055c79  call    cs:__imp_CoTaskMemFree
0x180055c7f  jmp     loc_180055B0A
```
