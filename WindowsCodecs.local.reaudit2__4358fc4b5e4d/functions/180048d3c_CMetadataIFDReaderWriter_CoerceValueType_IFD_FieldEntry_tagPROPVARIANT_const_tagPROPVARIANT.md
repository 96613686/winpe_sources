# CMetadataIFDReaderWriter::CoerceValueType(IFD::FieldEntry *,tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180048d3c`
- end: `0x180048f39`
- name: `?CoerceValueType@CMetadataIFDReaderWriter@@IEAAJPEAVFieldEntry@IFD@@PEBUtagPROPVARIANT@@PEAU4@@Z`
- size: `509`
- prototype: `int(CMetadataIFDReaderWriter *__hidden this, struct IFD::FieldEntry *, const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002cde0`
- `0x18004889c`

## callees

- `0x180039480`
- `0x180048d3c`
- `0x180049eb8`
- `0x18004ecd4`
- `0x1800bd9d4`
- `0x1800c597c`
- `0x1800cd3a0`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048d8e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180048d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180048e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048f13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048f28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048f13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180048f28`

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
0x180048d3c  mov     [rsp+puResult], rcx
0x180048d41  push    rbx
0x180048d42  push    rbp
0x180048d43  push    rsi
0x180048d44  push    rdi
0x180048d45  push    r14
0x180048d47  push    r15
0x180048d49  sub     rsp, 28h
0x180048d4d  xor     eax, eax
0x180048d4f  xorps   xmm0, xmm0
0x180048d52  movups  xmmword ptr [r9], xmm0
0x180048d56  mov     rcx, rdx; this
0x180048d59  mov     [r9+10h], rax
0x180048d5d  mov     rsi, r9
0x180048d60  mov     r14, r8
0x180048d63  xor     ebp, ebp
0x180048d65  call    ?IsCommentTag@FieldEntry@IFD@@QEAAHXZ; IFD::FieldEntry::IsCommentTag(void)
0x180048d6a  test    eax, eax
0x180048d6c  jnz     short loc_180048DB8
0x180048d6e  cmp     word ptr [r8], 1Fh
0x180048d73  jz      loc_180048E07
0x180048d79  mov     eax, 101Fh
0x180048d7e  cmp     [r8], ax
0x180048d82  jz      loc_180048E37
0x180048d88  mov     rdx, r8; pvarSrc
0x180048d8b  mov     rcx, r9; pvarDest
0x180048d8e  call    cs:__imp_PropVariantCopy
0x180048d95  nop     dword ptr [rax+rax+00h]
0x180048d9a  mov     ebx, eax
0x180048d9c  test    eax, eax
0x180048d9e  js      short loc_180048DE5
0x180048da0  test    ebx, ebx
0x180048da2  js      loc_180048EF6
0x180048da8  mov     eax, ebx
0x180048daa  add     rsp, 28h
0x180048dae  pop     r15
0x180048db0  pop     r14
0x180048db2  pop     rdi
0x180048db3  pop     rsi
0x180048db4  pop     rbp
0x180048db5  pop     rbx
0x180048db6  retn
0x180048db8  mov     rdx, rsi; struct tagPROPVARIANT *
0x180048dbb  mov     rcx, r14; struct tagPROPVARIANT *
0x180048dbe  call    ?CoerceStringVectors@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z; CoerceStringVectors(tagPROPVARIANT const &,tagPROPVARIANT *)
0x180048dc3  mov     ebx, eax
0x180048dc5  test    eax, eax
0x180048dc7  js      short loc_180048DF6
0x180048dc9  mov     rcx, rsi; pvar
0x180048dcc  call    ?ConvertCommentToBlob@@YAJPEAUtagPROPVARIANT@@@Z; ConvertCommentToBlob(tagPROPVARIANT *)
0x180048dd1  mov     ebx, eax
0x180048dd3  test    eax, eax
0x180048dd5  jns     short loc_180048DA0
0x180048dd7  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180048ddd  jnz     short loc_180048DFE
0x180048ddf  test    eax, eax
0x180048de1  js      short loc_180048DA8
0x180048de3  jmp     short loc_180048DA0
0x180048de5  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180048deb  jz      short loc_180048DA0
0x180048ded  mov     ecx, eax; int
0x180048def  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180048df4  jmp     short loc_180048DA0
0x180048df6  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180048dfc  jz      short loc_180048DA8
0x180048dfe  mov     ecx, eax; int
0x180048e00  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180048e05  jmp     short loc_180048DA8
0x180048e07  mov     rcx, [r14+8]; lpWideCharStr
0x180048e0b  lea     rdx, [r9+8]; char **
0x180048e0f  xor     r8d, r8d; unsigned int
0x180048e12  call    ?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z; CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)
0x180048e17  mov     ebx, eax
0x180048e19  test    eax, eax
0x180048e1b  jns     short loc_180048E2D
0x180048e1d  cmp     cs:?g_doStackCaptures@@3HA, ebp; int g_doStackCaptures
0x180048e23  jnz     short loc_180048DFE
0x180048e25  test    eax, eax
0x180048e27  js      loc_180048DA8
0x180048e2d  mov     word ptr [rsi], 1Eh
0x180048e32  jmp     loc_180048DA0
0x180048e37  mov     dword ptr [rsp+58h+puResult], ebp
0x180048e3b  lea     rdx, [rsp+58h+puResult]; puResult
0x180048e40  mov     ebp, [r8+8]
0x180048e44  mov     ecx, ebp
0x180048e46  shl     rcx, 3; ullOperand
0x180048e4a  call    ULongLongToUInt
0x180048e4f  mov     ebx, eax
0x180048e51  test    eax, eax
0x180048e53  jns     short loc_180048E66
0x180048e55  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180048e5c  jnz     short loc_180048DFE
0x180048e5e  test    eax, eax
0x180048e60  js      loc_180048DA8
0x180048e66  mov     r15d, dword ptr [rsp+58h+puResult]
0x180048e6b  mov     ecx, r15d; cb
0x180048e6e  call    cs:__imp_CoTaskMemAlloc
0x180048e75  nop     dword ptr [rax+rax+00h]
0x180048e7a  mov     rdi, rax
0x180048e7d  test    rax, rax
0x180048e80  jz      short loc_180048EA8
0x180048e82  mov     r8d, r15d; Size
0x180048e85  xor     edx, edx; Val
0x180048e87  mov     rcx, rax; void *
0x180048e8a  call    memset_0
0x180048e8f  xor     r15d, r15d
0x180048e92  cmp     r15d, ebp
0x180048e95  jb      short loc_180048EC1
0x180048e97  mov     [rsi+10h], rdi
0x180048e9b  mov     [rsi+8], ebp
0x180048e9e  mov     word ptr [rsi], 101Eh
0x180048ea3  jmp     loc_180048DA0
0x180048ea8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180048eaf  mov     ebx, 8007000Eh
0x180048eb4  jz      loc_180048DA8
0x180048eba  mov     ecx, ebx
0x180048ebc  jmp     loc_180048E00
0x180048ec1  mov     rcx, [r14+10h]
0x180048ec5  lea     rdx, [rdi+r15*8]; char **
0x180048ec9  xor     r8d, r8d; unsigned int
0x180048ecc  mov     rcx, [rcx+r15*8]; lpWideCharStr
0x180048ed0  call    ?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z; CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)
0x180048ed5  mov     ebx, eax
0x180048ed7  test    eax, eax
0x180048ed9  jns     short loc_180048EF1
0x180048edb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180048ee2  jz      short loc_180048EED
0x180048ee4  mov     ecx, eax; int
0x180048ee6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180048eeb  jmp     short loc_180048F01
0x180048eed  test    eax, eax
0x180048eef  js      short loc_180048EF8
0x180048ef1  inc     r15d
0x180048ef4  jmp     short loc_180048E92
0x180048ef6  xor     edi, edi
0x180048ef8  test    rdi, rdi
0x180048efb  jz      loc_180048DA8
0x180048f01  xor     esi, esi
0x180048f03  mov     r14, rdi
0x180048f06  test    ebp, ebp
0x180048f08  jz      short loc_180048F25
0x180048f0a  mov     rcx, [r14+rsi*8]; pv
0x180048f0e  test    rcx, rcx
0x180048f11  jz      short loc_180048F1F
0x180048f13  call    cs:__imp_CoTaskMemFree
0x180048f1a  nop     dword ptr [rax+rax+00h]
0x180048f1f  inc     esi
0x180048f21  cmp     esi, ebp
0x180048f23  jb      short loc_180048F0A
0x180048f25  mov     rcx, rdi; pv
0x180048f28  call    cs:__imp_CoTaskMemFree
0x180048f2f  nop     dword ptr [rax+rax+00h]
0x180048f34  jmp     loc_180048DA8
```
