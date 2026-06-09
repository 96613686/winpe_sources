# CStringRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x180006860`
- end: `0x180006adf`
- name: `?ConvertDataFormatOnRead@CStringRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `639`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006720`

## callees

- `0x180006860`
- `0x180006ae8`
- `0x180007804`
- `0x180007828`
- `0x1800084a0`
- `0x1800129d8`
- `0x180013c88`
- `0x18001c564`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800068c2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006962`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000699e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800069cd`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800068c2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006962`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000699e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800069cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800068e3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800068ee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a14`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a38`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a5c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a87`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800068e3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800068ee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a14`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a38`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a5c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006a87`

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
  HRESULT v10; // eax
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
    if ( v12 < 0 || (PropVariantClear(a3), v12 = ConvertDelimitedString(&pvarDest, L";", a3), v8 = v12, v12 < 0) )
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
          v10 = ConvertDelimitedString(&pvarDest, L";", a3);
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
0x180006860  mov     [rsp-8+arg_0], rbx
0x180006865  mov     [rsp-8+arg_8], rdi
0x18000686a  push    rbp
0x18000686b  mov     rbp, rsp
0x18000686e  sub     rsp, 40h
0x180006872  mov     rdi, r8
0x180006875  sub     edx, 1
0x180006878  jz      loc_1800069B9
0x18000687e  sub     edx, 9
0x180006881  jz      loc_180006AAF
0x180006887  sub     edx, 3
0x18000688a  jz      short loc_1800068AE
0x18000688c  sub     edx, 1; struct _GUID *
0x18000688f  jz      short loc_1800068AE
0x180006891  cmp     edx, 4
0x180006894  jz      loc_18000691B
0x18000689a  xor     ebx, ebx
0x18000689c  mov     eax, ebx
0x18000689e  mov     rbx, [rsp+40h+arg_0]
0x1800068a3  mov     rdi, [rsp+40h+arg_8]
0x1800068a8  add     rsp, 40h
0x1800068ac  pop     rbp
0x1800068ad  retn
0x1800068ae  xorps   xmm0, xmm0
0x1800068b1  xor     eax, eax
0x1800068b3  movups  xmmword ptr [rbp+pvarDest], xmm0
0x1800068b7  mov     qword ptr [rbp+pvarDest+10h], rax
0x1800068bb  mov     rdx, rdi; pvarSrc
0x1800068be  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800068c2  call    cs:__imp_PropVariantCopy
0x1800068c8  mov     ebx, eax
0x1800068ca  test    eax, eax
0x1800068cc  jns     short loc_1800068EB
0x1800068ce  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800068d5  jz      short loc_1800068DF
0x1800068d7  mov     ecx, eax; int
0x1800068d9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800068de  nop
0x1800068df  lea     rcx, [rbp+pvarDest]; pvar
0x1800068e3  call    cs:__imp_PropVariantClear
0x1800068e9  jmp     short loc_18000689C
0x1800068eb  mov     rcx, rdi; pvar
0x1800068ee  call    cs:__imp_PropVariantClear
0x1800068f4  mov     rdx, rdi; struct tagPROPVARIANT *
0x1800068f7  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x1800068fb  call    ?ConvertXMPArrayToStringVectorOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertXMPArrayToStringVectorOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006900  mov     ebx, eax
0x180006902  test    eax, eax
0x180006904  js      short loc_1800068CE
0x180006906  jmp     short loc_1800068DF
0x180006908  mov     ecx, eax; int
0x18000690a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000690f  nop
0x180006910  lea     rcx, [rbp+arg_18]
0x180006914  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006919  jmp     short loc_18000689C
0x18000691b  mov     [rbp+arg_18], 0
0x180006923  lea     r8, [rbp+arg_18]; void **
0x180006927  mov     rcx, rdi; struct tagPROPVARIANT *
0x18000692a  call    ?QueryInterfacePropVariant@@YAJAEBUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; QueryInterfacePropVariant(tagPROPVARIANT const &,_GUID const &,void * *)
0x18000692f  mov     ebx, eax
0x180006931  test    eax, eax
0x180006933  jns     loc_180006A11
0x180006939  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006940  jnz     short loc_180006908
0x180006942  jmp     short loc_180006910
0x180006944  mov     ecx, eax; int
0x180006946  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000694b  nop
0x18000694c  jmp     short loc_1800068DF
0x18000694e  xorps   xmm0, xmm0
0x180006951  xor     eax, eax
0x180006953  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006957  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000695b  mov     rdx, rdi; pvarSrc
0x18000695e  lea     rcx, [rbp+pvarDest]; pvarDest
0x180006962  call    cs:__imp_PropVariantCopy
0x180006968  mov     ebx, eax
0x18000696a  test    eax, eax
0x18000696c  jns     loc_180006A35
0x180006972  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180006979  jnz     short loc_180006944
0x18000697b  jmp     short loc_18000694C
0x18000697d  mov     ecx, eax; int
0x18000697f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006984  nop
0x180006985  jmp     loc_1800068DF
0x18000698a  xorps   xmm0, xmm0
0x18000698d  xor     eax, eax
0x18000698f  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180006993  mov     qword ptr [rbp+pvarDest+10h], rax
0x180006997  mov     rdx, rdi; pvarSrc
0x18000699a  lea     rcx, [rbp+pvarDest]; pvarDest
0x18000699e  call    cs:__imp_PropVariantCopy
0x1800069a4  mov     ebx, eax
0x1800069a6  test    eax, eax
0x1800069a8  jns     loc_180006A59
0x1800069ae  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800069b5  jnz     short loc_18000697D
0x1800069b7  jmp     short loc_180006985
0x1800069b9  xorps   xmm0, xmm0
0x1800069bc  xor     eax, eax
0x1800069be  movups  xmmword ptr [rbp+pvarDest], xmm0
0x1800069c2  mov     qword ptr [rbp+pvarDest+10h], rax
0x1800069c6  mov     rdx, rdi; pvarSrc
0x1800069c9  lea     rcx, [rbp+pvarDest]; pvarDest
0x1800069cd  call    cs:__imp_PropVariantCopy
0x1800069d3  mov     ebx, eax
0x1800069d5  test    eax, eax
0x1800069d7  jns     loc_180006A84
0x1800069dd  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800069e4  jz      short loc_1800069EE
0x1800069e6  mov     ecx, eax; int
0x1800069e8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800069ed  nop
0x1800069ee  jmp     loc_1800068DF
0x1800069f3  mov     ebx, 88982F91h
0x1800069f8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800069ff  jz      loc_18000689C
0x180006a05  mov     ecx, ebx; int
0x180006a07  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006a0c  jmp     loc_18000689C
0x180006a11  mov     rcx, rdi; pvar
0x180006a14  call    cs:__imp_PropVariantClear
0x180006a1a  mov     rdx, rdi; ppropvar
0x180006a1d  mov     rcx, [rbp+arg_18]; struct IWICMetadataQueryReader *
0x180006a21  call    ?GetPeopleTagsFromReader@@YAJPEAUIWICMetadataQueryReader@@PEAUtagPROPVARIANT@@@Z; GetPeopleTagsFromReader(IWICMetadataQueryReader *,tagPROPVARIANT *)
0x180006a26  mov     ebx, eax
0x180006a28  test    eax, eax
0x180006a2a  js      loc_180006939
0x180006a30  jmp     loc_180006910
0x180006a35  mov     rcx, rdi; pvar
0x180006a38  call    cs:__imp_PropVariantClear
0x180006a3e  mov     rdx, rdi; pvarDest
0x180006a41  lea     rcx, [rbp+pvarDest]; pvarSrc
0x180006a45  call    ?SniffAndConvertToWideString@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; SniffAndConvertToWideString(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180006a4a  mov     ebx, eax
0x180006a4c  test    eax, eax
0x180006a4e  js      loc_180006972
0x180006a54  jmp     loc_18000694C
0x180006a59  mov     rcx, rdi; pvar
0x180006a5c  call    cs:__imp_PropVariantClear
0x180006a62  mov     r8, rdi; struct tagPROPVARIANT *
0x180006a65  lea     rdx, asc_18008C47C; ";"
0x180006a6c  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180006a70  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x180006a75  mov     ebx, eax
0x180006a77  test    eax, eax
0x180006a79  js      loc_1800069AE
0x180006a7f  jmp     loc_180006985
0x180006a84  mov     rcx, rdi; pvar
0x180006a87  call    cs:__imp_PropVariantClear
0x180006a8d  mov     r8, rdi; struct tagPROPVARIANT *
0x180006a90  lea     rdx, asc_18008C47C; ";"
0x180006a97  lea     rcx, [rbp+pvarDest]; struct tagPROPVARIANT *
0x180006a9b  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x180006aa0  mov     ebx, eax
0x180006aa2  test    eax, eax
0x180006aa4  js      loc_1800069DD
0x180006aaa  jmp     loc_1800069EE
0x180006aaf  movzx   ecx, word ptr [r8]
0x180006ab3  sub     ecx, 1Eh
0x180006ab6  jz      loc_18000698A
0x180006abc  sub     ecx, 1
0x180006abf  jz      loc_18000698A
0x180006ac5  sub     ecx, 0FFFh
0x180006acb  jz      loc_18000694E
0x180006ad1  cmp     ecx, 1
0x180006ad4  jz      loc_18000689A
0x180006ada  jmp     loc_1800069F3
```
