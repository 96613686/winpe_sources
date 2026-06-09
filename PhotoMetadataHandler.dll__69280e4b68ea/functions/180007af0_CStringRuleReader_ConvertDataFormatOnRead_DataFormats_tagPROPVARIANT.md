# CStringRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x180007af0`
- end: `0x180007daf`
- name: `?ConvertDataFormatOnRead@CStringRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `703`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007990`

## callees

- `0x180006fc0`
- `0x180007af0`
- `0x180007db8`
- `0x180008b54`
- `0x180008b7c`
- `0x1800132dc`
- `0x180014640`
- `0x18001d2a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007b53`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007c08`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007c4a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007c7f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007b53`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007c08`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007c4a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007c7f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007b7a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007b8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ccc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007cf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007d20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007d51`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007b7a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007b8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ccc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007cf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007d20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007d51`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStringRuleReader::ConvertDataFormatOnRead(__int64 a1, int a2, PROPVARIANT *a3)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  const struct _GUID *v7; // rdx
  unsigned int v8; // ebx
  int v10; // eax
  int InterfacePropVariant; // eax
  HRESULT v12; // eax
  PROPVARIANT pvarDest; // [rsp+20h] [rbp-20h] BYREF
  struct IWICMetadataQueryReader *v14; // [rsp+68h] [rbp+28h] BYREF

  v4 = a2 - 1;
  if ( !v4 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v12 = PropVariantCopy(&pvarDest, a3);
    v8 = v12;
    if ( v12 < 0
      || (PropVariantClear(a3), v12 = ConvertDelimitedString(&pvarDest, &qword_18008D468, a3), v8 = v12, v12 < 0) )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v12);
    }
    goto LABEL_11;
  }
  v5 = v4 - 9;
  if ( !v5 )
  {
    switch ( a3->vt )
    {
      case 0x1Eu:
      case 0x1Fu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v10 = PropVariantCopy(&pvarDest, a3);
        v8 = v10;
        if ( v10 >= 0 )
        {
          PropVariantClear(a3);
          v10 = ConvertDelimitedString(&pvarDest, &qword_18008D468, a3);
          v8 = v10;
          if ( v10 >= 0 )
            goto LABEL_11;
        }
        if ( !g_doStackCaptures )
          goto LABEL_11;
        break;
      case 0x101Eu:
        memset(&pvarDest, 0, sizeof(pvarDest));
        v10 = PropVariantCopy(&pvarDest, a3);
        v8 = v10;
        if ( v10 >= 0 && (PropVariantClear(a3), v10 = SniffAndConvertToWideString(&pvarDest, a3), v8 = v10, v10 >= 0)
          || !g_doStackCaptures )
        {
LABEL_11:
          PropVariantClear(&pvarDest);
          return v8;
        }
        break;
      case 0x101Fu:
        return 0;
      default:
        v8 = -2003292271;
        if ( g_doStackCaptures )
          DoStackCapture(-2003292271);
        return v8;
    }
LABEL_10:
    DoStackCapture(v10);
    goto LABEL_11;
  }
  v6 = v5 - 3;
  if ( !v6 || (v7 = (const struct _GUID *)(unsigned int)(v6 - 1), !(_DWORD)v7) )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v10 = PropVariantCopy(&pvarDest, a3);
    v8 = v10;
    if ( v10 >= 0 )
    {
      PropVariantClear(a3);
      v10 = ConvertXMPArrayToStringVectorOnRead(&pvarDest, a3);
      v8 = v10;
      if ( v10 >= 0 )
        goto LABEL_11;
    }
    if ( !g_doStackCaptures )
      goto LABEL_11;
    goto LABEL_10;
  }
  if ( (_DWORD)v7 != 4 )
    return 0;
  v14 = 0;
  InterfacePropVariant = QueryInterfacePropVariant(a3, v7, (void **)&v14);
  v8 = InterfacePropVariant;
  if ( InterfacePropVariant < 0
    || (PropVariantClear(a3),
        InterfacePropVariant = GetPeopleTagsFromReader(v14, a3),
        v8 = InterfacePropVariant,
        InterfacePropVariant < 0) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(InterfacePropVariant);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  return v8;
}

```

## disassembly

```asm
0x180007af0  mov     [rsp-8+arg_0], rbx
0x180007af5  mov     [rsp-8+arg_8], rdi
0x180007afa  push    rbp
0x180007afb  mov     rbp, rsp
0x180007afe  sub     rsp, 40h
0x180007b02  mov     rdi, r8
0x180007b05  sub     edx, 1
0x180007b08  jz      loc_180007C6B
0x180007b0e  sub     edx, 9
0x180007b11  jz      loc_180007D7F
0x180007b17  sub     edx, 3
0x180007b1a  jz      short loc_180007B3F
0x180007b1c  sub     edx, 1; struct _GUID *
0x180007b1f  jz      short loc_180007B3F
0x180007b21  cmp     edx, 4
0x180007b24  jz      loc_180007BC1
0x180007b2a  xor     ebx, ebx
0x180007b2c  mov     eax, ebx
0x180007b2e  mov     rbx, [rsp+40h+arg_0]
0x180007b33  mov     rdi, [rsp+40h+arg_8]
0x180007b38  add     rsp, 40h
0x180007b3c  pop     rbp
0x180007b3d  retn
0x180007b3f  xorps   xmm0, xmm0
0x180007b42  xor     eax, eax
0x180007b44  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180007b48  mov     qword ptr [rbp+pvarDest+10h], rax
0x180007b4c  mov     rdx, rdi; pvarSrc
0x180007b4f  lea     rcx, [rbp+pvarDest]; pvarDest
0x180007b53  call    cs:__imp_PropVariantCopy
0x180007b5a  nop     dword ptr [rax+rax+00h]
0x180007b5f  mov     ebx, eax
0x180007b61  test    eax, eax
0x180007b63  jns     short loc_180007B88
0x180007b65  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007b6c  jz      short loc_180007B76
0x180007b6e  mov     ecx, eax; int
0x180007b70  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007b75  nop
0x180007b76  lea     rcx, [rbp+pvarDest]; pvar
0x180007b7a  call    cs:__imp_PropVariantClear
0x180007b81  nop     dword ptr [rax+rax+00h]
0x180007b86  jmp     short loc_180007B2C
0x180007b88  mov     rcx, rdi; pvar
0x180007b8b  call    cs:__imp_PropVariantClear
0x180007b92  nop     dword ptr [rax+rax+00h]
0x180007b97  mov     rdx, rdi; struct tagPROPVARIANT *
0x180007b9a  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180007b9e  call    ?ConvertXMPArrayToStringVectorOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertXMPArrayToStringVectorOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180007ba3  mov     ebx, eax
0x180007ba5  test    eax, eax
0x180007ba7  js      short loc_180007B65
0x180007ba9  jmp     short loc_180007B76
0x180007bab  mov     ecx, eax; int
0x180007bad  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007bb2  nop
0x180007bb3  lea     rcx, [rbp+arg_18]
0x180007bb7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180007bbc  jmp     loc_180007B2C
0x180007bc1  mov     [rbp+arg_18], 0
0x180007bc9  lea     r8, [rbp+arg_18]; void **
0x180007bcd  mov     rcx, rdi; struct tagPROPVARIANT *
0x180007bd0  call    ?QueryInterfacePropVariant@@YAJAEBUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; QueryInterfacePropVariant(tagPROPVARIANT const &,_GUID const &,void * *)
0x180007bd5  mov     ebx, eax
0x180007bd7  test    eax, eax
0x180007bd9  jns     loc_180007CC9
0x180007bdf  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007be6  jnz     short loc_180007BAB
0x180007be8  jmp     short loc_180007BB3
0x180007bea  mov     ecx, eax; int
0x180007bec  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007bf1  nop
0x180007bf2  jmp     short loc_180007B76
0x180007bf4  xorps   xmm0, xmm0
0x180007bf7  xor     eax, eax
0x180007bf9  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180007bfd  mov     qword ptr [rbp+pvarDest+10h], rax
0x180007c01  mov     rdx, rdi; pvarSrc
0x180007c04  lea     rcx, [rbp+pvarDest]; pvarDest
0x180007c08  call    cs:__imp_PropVariantCopy
0x180007c0f  nop     dword ptr [rax+rax+00h]
0x180007c14  mov     ebx, eax
0x180007c16  test    eax, eax
0x180007c18  jns     loc_180007CF3
0x180007c1e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007c25  jnz     short loc_180007BEA
0x180007c27  jmp     short loc_180007BF2
0x180007c29  mov     ecx, eax; int
0x180007c2b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007c30  nop
0x180007c31  jmp     loc_180007B76
0x180007c36  xorps   xmm0, xmm0
0x180007c39  xor     eax, eax
0x180007c3b  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180007c3f  mov     qword ptr [rbp+pvarDest+10h], rax
0x180007c43  mov     rdx, rdi; pvarSrc
0x180007c46  lea     rcx, [rbp+pvarDest]; pvarDest
0x180007c4a  call    cs:__imp_PropVariantCopy
0x180007c51  nop     dword ptr [rax+rax+00h]
0x180007c56  mov     ebx, eax
0x180007c58  test    eax, eax
0x180007c5a  jns     loc_180007D1D
0x180007c60  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007c67  jnz     short loc_180007C29
0x180007c69  jmp     short loc_180007C31
0x180007c6b  xorps   xmm0, xmm0
0x180007c6e  xor     eax, eax
0x180007c70  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180007c74  mov     qword ptr [rbp+pvarDest+10h], rax
0x180007c78  mov     rdx, rdi; pvarSrc
0x180007c7b  lea     rcx, [rbp+pvarDest]; pvarDest
0x180007c7f  call    cs:__imp_PropVariantCopy
0x180007c86  nop     dword ptr [rax+rax+00h]
0x180007c8b  mov     ebx, eax
0x180007c8d  test    eax, eax
0x180007c8f  jns     loc_180007D4E
0x180007c95  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007c9c  jz      short loc_180007CA6
0x180007c9e  mov     ecx, eax; int
0x180007ca0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007ca5  nop
0x180007ca6  jmp     loc_180007B76
0x180007cab  mov     ebx, 88982F91h
0x180007cb0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007cb7  jz      loc_180007B2C
0x180007cbd  mov     ecx, ebx; int
0x180007cbf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007cc4  jmp     loc_180007B2C
0x180007cc9  mov     rcx, rdi; pvar
0x180007ccc  call    cs:__imp_PropVariantClear
0x180007cd3  nop     dword ptr [rax+rax+00h]
0x180007cd8  mov     rdx, rdi; ppropvar
0x180007cdb  mov     rcx, [rbp+arg_18]; struct IWICMetadataQueryReader *
0x180007cdf  call    ?GetPeopleTagsFromReader@@YAJPEAUIWICMetadataQueryReader@@PEAUtagPROPVARIANT@@@Z; GetPeopleTagsFromReader(IWICMetadataQueryReader *,tagPROPVARIANT *)
0x180007ce4  mov     ebx, eax
0x180007ce6  test    eax, eax
0x180007ce8  js      loc_180007BDF
0x180007cee  jmp     loc_180007BB3
0x180007cf3  mov     rcx, rdi; pvar
0x180007cf6  call    cs:__imp_PropVariantClear
0x180007cfd  nop     dword ptr [rax+rax+00h]
0x180007d02  mov     rdx, rdi; pvarDest
0x180007d05  lea     rcx, [rbp+pvarDest]; pvarSrc
0x180007d09  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180007d0e  mov     ebx, eax
0x180007d10  test    eax, eax
0x180007d12  js      loc_180007C1E
0x180007d18  jmp     loc_180007BF2
0x180007d1d  mov     rcx, rdi; pvar
0x180007d20  call    cs:__imp_PropVariantClear
0x180007d27  nop     dword ptr [rax+rax+00h]
0x180007d2c  mov     r8, rdi; struct tagPROPVARIANT *
0x180007d2f  lea     rdx, qword_18008D468; unsigned __int16 *
0x180007d36  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180007d3a  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x180007d3f  mov     ebx, eax
0x180007d41  test    eax, eax
0x180007d43  js      loc_180007C60
0x180007d49  jmp     loc_180007C31
0x180007d4e  mov     rcx, rdi; pvar
0x180007d51  call    cs:__imp_PropVariantClear
0x180007d58  nop     dword ptr [rax+rax+00h]
0x180007d5d  mov     r8, rdi; struct tagPROPVARIANT *
0x180007d60  lea     rdx, qword_18008D468; unsigned __int16 *
0x180007d67  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180007d6b  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x180007d70  mov     ebx, eax
0x180007d72  test    eax, eax
0x180007d74  js      loc_180007C95
0x180007d7a  jmp     loc_180007CA6
0x180007d7f  movzx   ecx, word ptr [r8]
0x180007d83  sub     ecx, 1Eh
0x180007d86  jz      loc_180007C36
0x180007d8c  sub     ecx, 1
0x180007d8f  jz      loc_180007C36
0x180007d95  sub     ecx, 0FFFh
0x180007d9b  jz      loc_180007BF4
0x180007da1  cmp     ecx, 1
0x180007da4  jz      loc_180007B2A
0x180007daa  jmp     loc_180007CAB
```
