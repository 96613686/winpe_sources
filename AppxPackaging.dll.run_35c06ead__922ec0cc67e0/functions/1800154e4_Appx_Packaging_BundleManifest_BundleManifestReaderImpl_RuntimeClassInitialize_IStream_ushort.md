# Appx::Packaging::BundleManifest::BundleManifestReaderImpl::RuntimeClassInitialize(IStream *,ushort * *)

- ea: `0x1800154e4`
- end: `0x1800157c1`
- name: `?RuntimeClassInitialize@BundleManifestReaderImpl@BundleManifest@Packaging@Appx@@QEAAJPEAUIStream@@PEAPEAG@Z`
- size: `733`
- prototype: `__int64 __fastcall(Appx::Packaging::BundleManifest::BundleManifestReaderImpl *__hidden this, struct IStream *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18004fa0c`

## callees

- `0x180005eb8`
- `0x180009eb8`
- `0x18000d010`
- `0x180010f40`
- `0x1800133fc`
- `0x180014630`
- `0x1800154e4`
- `0x1800157c8`
- `0x1800158e4`
- `0x1800160e8`
- `0x1800199a4`
- `0x18001b1a8`
- `0x180035d8c`
- `0x180071f50`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001565b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001565b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156b8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156e4`

## string_xrefs

- `0x1800156a6`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreader.cpp`
- `0x1800156cc`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreader.cpp`
- `0x1800156fb`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreader.cpp`
- `0x180015723`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreader.cpp`
- `0x180015759`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreader.cpp`
- `0x18001578e`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreader.cpp`
- `0x1800157a8`: `onecore\printscan\appxpackaging\manifest\src\bundlemanifestreader.cpp`
- `0x18001555f`: `http://schemas.microsoft.com/appx/2013/bundle`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::BundleManifest::BundleManifestReaderImpl::RuntimeClassInitialize(
        Appx::Packaging::BundleManifest::BundleManifestReaderImpl *this,
        struct IStream *a2,
        unsigned __int16 **a3)
{
  int v5; // eax
  struct Common::AutoBStr *v6; // r9
  unsigned int v7; // ebx
  int v8; // eax
  OLECHAR *v9; // rbx
  int v10; // edi
  unsigned __int64 v11; // r8
  int PackageInfoNodesList; // eax
  struct IXMLDOMNodeList *v13; // rdi
  int v14; // eax
  unsigned int v15; // esi
  int v16; // eax
  int v17; // eax
  __int64 v19; // rdx
  int Src; // [rsp+20h] [rbp-48h]
  struct IXMLDOMNodeList *v21; // [rsp+30h] [rbp-38h] BYREF
  int v22; // [rsp+38h] [rbp-30h] BYREF
  const unsigned __int16 *v23; // [rsp+40h] [rbp-28h]
  int v24; // [rsp+48h] [rbp-20h]
  const wchar_t *v25; // [rsp+50h] [rbp-18h]
  int v26; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  BSTR bstrString; // [rsp+B8h] [rbp+50h] BYREF

  v5 = Appx::Packaging::BundleManifest::BundleManifestReaderImpl::ValidateSchema(this, a2, a3);
  v7 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreader.cpp",
      (const char *)(unsigned int)v5,
      Src);
  }
  else
  {
    bstrString = 0;
    v23 = L"b:Bundle | b2:Bundle | b3:Bundle | b4:Bundle";
    v24 = 44;
    v25 = L"']";
    v22 = 1;
    v26 = 0;
    v8 = Appx::Packaging::BuildXPath(
           (Appx::Packaging *)&v22,
           (const struct Appx::Packaging::XPathComponent *)1,
           &bstrString,
           v6);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v9 = bstrString;
      v10 = Appx::Packaging::Manifest::ManifestReaderBase::InitializeRoot(
              (Appx::Packaging::BundleManifest::BundleManifestReaderImpl *)((char *)this + 48),
              bstrString,
              L"http://schemas.microsoft.com/appx/2013/bundle");
      if ( v10 < 0 )
      {
        v19 = 86;
        goto LABEL_19;
      }
      if ( !a3 )
      {
        v10 = Appx::Packaging::Manifest::ManifestReaderBase::ValidateIdentifiers(
                (Appx::Packaging::BundleManifest::BundleManifestReaderImpl *)((char *)this + 48),
                (const struct Appx::Packaging::Manifest::IdentityXPaths *)&Appx::Packaging::BundleManifest::IdentityXPathsTable,
                2u);
        if ( v10 < 0 )
        {
          v19 = 91;
LABEL_19:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreader.cpp",
            (const char *)(unsigned int)v10,
            Src);
LABEL_20:
          SysFreeString(v9);
          return (unsigned int)v10;
        }
      }
      v10 = Appx::Packaging::Manifest::ManifestReaderBase::NormalizeFileNames(
              (Appx::Packaging::BundleManifest::BundleManifestReaderImpl *)((char *)this + 48),
              (const struct Appx::Packaging::Manifest::FileNameTable *)&Appx::Packaging::BundleManifest::FileNameXPaths,
              3u);
      if ( v10 < 0 )
      {
        v19 = 94;
        goto LABEL_19;
      }
      v10 = Appx::Packaging::BundleManifest::BundleManifestReaderImpl::InitializePackageId(this);
      if ( v10 < 0 )
      {
        v19 = 96;
        goto LABEL_19;
      }
      if ( a3 )
        goto LABEL_13;
      v21 = 0;
      LODWORD(bstrString) = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v21);
      PackageInfoNodesList = Appx::Packaging::BundleManifest::BundleManifestReaderImpl::GetPackageInfoNodesList(
                               this,
                               &v21,
                               (int *)&bstrString);
      v10 = PackageInfoNodesList;
      if ( PackageInfoNodesList < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x67,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreader.cpp",
          (const char *)(unsigned int)PackageInfoNodesList,
          Src);
        if ( v21 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v21->lpVtbl->Release)(v21);
        goto LABEL_20;
      }
      v13 = v21;
      v14 = Appx::Packaging::BundleManifest::BundleManifestReaderImpl::ValidatePackageNodes(
              (__int64)this,
              (__int64 *)v21,
              (int)bstrString,
              (__int64)this + 104,
              *((_WORD **)this + 28),
              *((_WORD **)this + 29));
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x68,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreader.cpp",
          (const char *)(unsigned int)v14,
          Src);
      }
      else
      {
        v16 = Appx::Packaging::BundleManifest::BundleManifestReaderImpl::ValidateOptionalBundles(this);
        v15 = v16;
        if ( v16 >= 0 )
        {
          if ( v13 )
            ((void (__fastcall *)(struct IXMLDOMNodeList *))v13->lpVtbl->Release)(v13);
LABEL_13:
          v17 = Appx::Packaging::SetStreamPosition(*((Appx::Packaging **)this + 6), 0, v11);
          v15 = v17;
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6E,
              (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreader.cpp",
              (const char *)(unsigned int)v17,
              Src);
LABEL_15:
          SysFreeString(v9);
          return v15;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreader.cpp",
          (const char *)(unsigned int)v16,
          Src);
      }
      if ( v13 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v13->lpVtbl->Release)(v13);
      goto LABEL_15;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\bundlemanifestreader.cpp",
      (const char *)(unsigned int)v8,
      Src);
    SysFreeString(bstrString);
  }
  return v7;
}

```

## disassembly

```asm
0x1800154e4  push    rbp
0x1800154e6  push    rbx
0x1800154e7  push    rsi
0x1800154e8  push    rdi
0x1800154e9  push    r14
0x1800154eb  push    r15
0x1800154ed  mov     rbp, rsp
0x1800154f0  sub     rsp, 68h
0x1800154f4  mov     rsi, r8
0x1800154f7  mov     r14, rcx
0x1800154fa  call    ?ValidateSchema@BundleManifestReaderImpl@BundleManifest@Packaging@Appx@@AEAAJPEAUIStream@@PEAPEAG@Z; Appx::Packaging::BundleManifest::BundleManifestReaderImpl::ValidateSchema(IStream *,ushort * *)
0x1800154ff  mov     ebx, eax
0x180015501  test    eax, eax
0x180015503  js      loc_1800156F7
0x180015509  lea     rax, ?BundleRootNodeXPath@BundleManifest@Packaging@Appx@@3QBGB; "b:Bundle | b2:Bundle | b3:Bundle | b4:B"...
0x180015510  mov     [rbp+bstrString], 0
0x180015518  mov     [rbp+var_28], rax
0x18001551c  lea     r8, [rbp+bstrString]; unsigned int
0x180015520  lea     rax, asc_1801177B4; "']"
0x180015527  mov     [rbp+var_20], 2Ch ; ','
0x18001552e  mov     edx, 1; struct Appx::Packaging::XPathComponent *
0x180015533  mov     [rbp+var_18], rax
0x180015537  lea     rcx, [rbp+var_30]; this
0x18001553b  mov     [rbp+var_30], edx
0x18001553e  mov     [rbp+var_10], 0
0x180015545  call    ?BuildXPath@Packaging@Appx@@YAJPEBUXPathComponent@12@IAEAVAutoBStr@Common@@@Z; Appx::Packaging::BuildXPath(Appx::Packaging::XPathComponent const *,uint,Common::AutoBStr &)
0x18001554a  mov     ebx, eax
0x18001554c  test    eax, eax
0x18001554e  js      loc_1800156C8
0x180015554  mov     rbx, [rbp+bstrString]
0x180015558  lea     r15, [r14+30h]
0x18001555c  mov     rdx, rbx; unsigned __int16 *
0x18001555f  lea     r8, ?Namespace@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2013/"...
0x180015566  mov     rcx, r15; this
0x180015569  call    ?InitializeRoot@ManifestReaderBase@Manifest@Packaging@Appx@@QEAAJPEAGPEBG@Z; Appx::Packaging::Manifest::ManifestReaderBase::InitializeRoot(ushort *,ushort const *)
0x18001556e  mov     edi, eax
0x180015570  test    eax, eax
0x180015572  js      loc_18001569D
0x180015578  test    rsi, rsi
0x18001557b  jz      loc_180015677
0x180015581  mov     r8d, 3; unsigned int
0x180015587  lea     rdx, ?FileNameXPaths@BundleManifest@Packaging@Appx@@3QBUFileNameTable@Manifest@23@B; struct Appx::Packaging::Manifest::FileNameTable *
0x18001558e  mov     rcx, r15; this
0x180015591  call    ?NormalizeFileNames@ManifestReaderBase@Manifest@Packaging@Appx@@QEAAJPEBUFileNameTable@234@K@Z; Appx::Packaging::Manifest::ManifestReaderBase::NormalizeFileNames(Appx::Packaging::Manifest::FileNameTable const *,ulong)
0x180015596  mov     edi, eax
0x180015598  test    eax, eax
0x18001559a  js      loc_180015711
0x1800155a0  mov     rcx, r14; this
0x1800155a3  call    ?InitializePackageId@BundleManifestReaderImpl@BundleManifest@Packaging@Appx@@AEAAJXZ; Appx::Packaging::BundleManifest::BundleManifestReaderImpl::InitializePackageId(void)
0x1800155a8  mov     edi, eax
0x1800155aa  test    eax, eax
0x1800155ac  js      loc_180015718
0x1800155b2  test    rsi, rsi
0x1800155b5  jnz     loc_180015644
0x1800155bb  lea     rcx, [rbp+var_38]
0x1800155bf  mov     [rbp+var_38], rsi
0x1800155c3  mov     dword ptr [rbp+bstrString], esi
0x1800155c6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800155cb  lea     r8, [rbp+bstrString]; int *
0x1800155cf  mov     rcx, r14; this
0x1800155d2  lea     rdx, [rbp+var_38]; struct IXMLDOMNodeList **
0x1800155d6  call    ?GetPackageInfoNodesList@BundleManifestReaderImpl@BundleManifest@Packaging@Appx@@AEAAJPEAPEAUIXMLDOMNodeList@@PEAJ@Z; Appx::Packaging::BundleManifest::BundleManifestReaderImpl::GetPackageInfoNodesList(IXMLDOMNodeList * *,long *)
0x1800155db  mov     edi, eax
0x1800155dd  test    eax, eax
0x1800155df  js      loc_18001571F
0x1800155e5  mov     rax, [r14+0E8h]
0x1800155ec  lea     r9, [r14+68h]; int
0x1800155f0  mov     rdi, [rbp+var_38]
0x1800155f4  mov     rcx, r14; int
0x1800155f7  mov     r8d, dword ptr [rbp+bstrString]; int
0x1800155fb  mov     rdx, rdi; int
0x1800155fe  mov     [rsp+68h+var_40], rax; void *
0x180015603  mov     rax, [r14+0E0h]
0x18001560a  mov     [rsp+68h+Src], rax; int
0x18001560f  call    ?ValidatePackageNodes@BundleManifestReaderImpl@BundleManifest@Packaging@Appx@@AEAAJPEAUIXMLDOMNodeList@@JPEAV?$GenericMap@PEAGPEAX@Common@@PEBG2@Z; Appx::Packaging::BundleManifest::BundleManifestReaderImpl::ValidatePackageNodes(IXMLDOMNodeList *,long,Common::GenericMap<ushort *,void *> *,ushort const *,ushort const *)
0x180015614  mov     esi, eax
0x180015616  test    eax, eax
0x180015618  js      loc_18001578A
0x18001561e  mov     rcx, r14; this
0x180015621  call    ?ValidateOptionalBundles@BundleManifestReaderImpl@BundleManifest@Packaging@Appx@@AEAAJXZ; Appx::Packaging::BundleManifest::BundleManifestReaderImpl::ValidateOptionalBundles(void)
0x180015626  mov     esi, eax
0x180015628  test    eax, eax
0x18001562a  js      loc_180015755
0x180015630  test    rdi, rdi
0x180015633  jz      short loc_180015644
0x180015635  mov     rax, [rdi]
0x180015638  mov     rcx, rdi
0x18001563b  mov     rax, [rax+10h]
0x18001563f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015644  mov     rcx, [r15]; this
0x180015647  xor     edx, edx; struct IStream *
0x180015649  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x18001564e  mov     esi, eax
0x180015650  test    eax, eax
0x180015652  js      loc_1800157A4
0x180015658  mov     rcx, rbx; bstrString
0x18001565b  call    cs:__imp_SysFreeString
0x180015662  nop     dword ptr [rax+rax+00h]
0x180015667  mov     eax, esi
0x180015669  add     rsp, 68h
0x18001566d  pop     r15
0x18001566f  pop     r14
0x180015671  pop     rdi
0x180015672  pop     rsi
0x180015673  pop     rbx
0x180015674  pop     rbp
0x180015675  retn
0x180015677  mov     r8d, 2; unsigned int
0x18001567d  lea     rdx, ?IdentityXPathsTable@BundleManifest@Packaging@Appx@@3QBUIdentityXPaths@Manifest@23@B; struct Appx::Packaging::Manifest::IdentityXPaths *
0x180015684  mov     rcx, r15; this
0x180015687  call    ?ValidateIdentifiers@ManifestReaderBase@Manifest@Packaging@Appx@@QEAAJPEBUIdentityXPaths@234@K@Z; Appx::Packaging::Manifest::ManifestReaderBase::ValidateIdentifiers(Appx::Packaging::Manifest::IdentityXPaths const *,ulong)
0x18001568c  mov     edi, eax
0x18001568e  test    eax, eax
0x180015690  jns     loc_180015581
0x180015696  mov     edx, 5Bh ; '['
0x18001569b  jmp     short loc_1800156A2
0x18001569d  mov     edx, 56h ; 'V'; void *
0x1800156a2  mov     rcx, [rbp+30h]; this
0x1800156a6  lea     r8, aOnecorePrintsc_132; "onecore\\printscan\\appxpackaging\\mani"...
0x1800156ad  mov     r9d, edi; char *
0x1800156b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800156b5  mov     rcx, rbx; bstrString
0x1800156b8  call    cs:__imp_SysFreeString
0x1800156bf  nop     dword ptr [rax+rax+00h]
0x1800156c4  mov     eax, edi
0x1800156c6  jmp     short loc_180015669
0x1800156c8  mov     rcx, [rbp+30h]; this
0x1800156cc  lea     r8, aOnecorePrintsc_132; "onecore\\printscan\\appxpackaging\\mani"...
0x1800156d3  mov     r9d, ebx; char *
0x1800156d6  mov     edx, 55h ; 'U'; void *
0x1800156db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800156e0  mov     rcx, [rbp+bstrString]; bstrString
0x1800156e4  call    cs:__imp_SysFreeString
0x1800156eb  nop     dword ptr [rax+rax+00h]
0x1800156f0  mov     eax, ebx
0x1800156f2  jmp     loc_180015669
0x1800156f7  mov     rcx, [rbp+30h]; this
0x1800156fb  lea     r8, aOnecorePrintsc_132; "onecore\\printscan\\appxpackaging\\mani"...
0x180015702  mov     r9d, ebx; char *
0x180015705  mov     edx, 52h ; 'R'; void *
0x18001570a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001570f  jmp     short loc_1800156F0
0x180015711  mov     edx, 5Eh ; '^'
0x180015716  jmp     short loc_1800156A2
0x180015718  mov     edx, 60h ; '`'
0x18001571d  jmp     short loc_1800156A2
0x18001571f  mov     rcx, [rbp+30h]; this
0x180015723  lea     r8, aOnecorePrintsc_132; "onecore\\printscan\\appxpackaging\\mani"...
0x18001572a  mov     r9d, edi; char *
0x18001572d  mov     edx, 67h ; 'g'; void *
0x180015732  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015737  mov     rcx, [rbp+var_38]
0x18001573b  test    rcx, rcx
0x18001573e  jz      loc_1800156B5
0x180015744  mov     rdx, [rcx]
0x180015747  mov     rax, [rdx+10h]
0x18001574b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015750  jmp     loc_1800156B5
0x180015755  mov     rcx, [rbp+30h]; this
0x180015759  lea     r8, aOnecorePrintsc_132; "onecore\\printscan\\appxpackaging\\mani"...
0x180015760  mov     r9d, eax; char *
0x180015763  mov     edx, 6Ah ; 'j'; void *
0x180015768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001576d  test    rdi, rdi
0x180015770  jz      loc_180015658
0x180015776  mov     rcx, [rdi]
0x180015779  mov     rax, [rcx+10h]
0x18001577d  mov     rcx, rdi
0x180015780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015785  jmp     loc_180015658
0x18001578a  mov     rcx, [rbp+30h]; this
0x18001578e  lea     r8, aOnecorePrintsc_132; "onecore\\printscan\\appxpackaging\\mani"...
0x180015795  mov     r9d, eax; char *
0x180015798  mov     edx, 68h ; 'h'; void *
0x18001579d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800157a2  jmp     short loc_18001576D
0x1800157a4  mov     rcx, [rbp+30h]; this
0x1800157a8  lea     r8, aOnecorePrintsc_132; "onecore\\printscan\\appxpackaging\\mani"...
0x1800157af  mov     r9d, eax; char *
0x1800157b2  mov     edx, 6Eh ; 'n'; void *
0x1800157b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800157bc  jmp     loc_180015658
```
