# Appx::Packaging::Production::BundleManifestWriterHelper::EndBundleManifest(IStream * *)

- ea: `0x180074f34`
- end: `0x1800752ec`
- name: `?EndBundleManifest@BundleManifestWriterHelper@Production@Packaging@Appx@@QEAAJPEAPEAUIStream@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(Appx::Packaging::Production::BundleManifestWriterHelper *__hidden this, struct IStream **)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180074a4c`
- `0x180074d64`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x1800133fc`
- `0x18004f914`
- `0x18005a0b0`
- `0x180074f34`
- `0x180096a00`
- `0x1800c9aac`
- `0x1800f2670`
- `0x1800f4208`
- `0x1800f430c`
- `0x1800f43c0`
- `0x1800f44e4`
- `0x1800f459c`
- `0x1800f48c4`
- `0x180106010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18007502a`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18007502a`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800751d8`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1800751d8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180074f9a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180074f9a`

## string_xrefs

- `0x18007503a`: `http://schemas.microsoft.com/appx/2013/bundle`
- `0x180075002`: `http://schemas.microsoft.com/appx/2018/bundle`
- `0x18007501a`: `http://schemas.microsoft.com/appx/2017/bundle`
- `0x180075049`: `http://schemas.microsoft.com/appx/2016/bundle`
- `0x180074f65`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180074fe0`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x1800750b4`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075108`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x18007514d`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x18007519e`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x180075204`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`
- `0x18007525c`: `onecore\printscan\appxpackaging\production\src\bundlemanifestwriterhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::BundleManifestWriterHelper::EndBundleManifest(
        Appx::Packaging::Production::BundleManifestWriterHelper *this,
        struct IStream **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HRESULT v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // rcx
  bool v11; // cc
  const unsigned __int16 *v12; // rbx
  char v13; // si
  Appx::Packaging::BundleManifest::BundleManifestXmlWriter *v14; // rcx
  Appx::Packaging::BundleManifest::BundleManifestXmlWriter *v15; // rbx
  int started; // eax
  unsigned int v17; // esi
  unsigned __int64 i; // rsi
  int v19; // eax
  unsigned int v20; // r14d
  struct _RTL_AVL_TABLE *v21; // rsi
  struct Appx::Packaging::BundleManifest::OptionalBundleInfo **v22; // rax
  int v23; // edi
  __int64 v24; // rdx
  int v25; // eax
  __int64 (__fastcall *v27)(__int64, LPSTREAM *); // rbx
  int v28; // eax
  PVOID RestartKey; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  LPSTREAM ppstm; // [rsp+68h] [rbp+38h] BYREF
  struct Appx::Packaging::BundleManifest::BundleManifestReaderImpl *v32; // [rsp+70h] [rbp+40h] BYREF
  Appx::Packaging::BundleManifest::BundleManifestXmlWriter *v33; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  v4 = Appx::Packaging::Production::BundleManifestWriterHelper::ValidatePayloadPackageExtension(this, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
      (const char *)(unsigned int)v4,
      (int)RestartKey);
    return v5;
  }
  ppstm = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
  v6 = CreateStreamOnHGlobal(0, 1, &ppstm);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 677;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
      (const char *)v7,
      (int)RestartKey);
    goto LABEL_44;
  }
  v9 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    v27 = *(__int64 (__fastcall **)(__int64, LPSTREAM *))(*(_QWORD *)v9 + 32LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
    v28 = v27(v9, &ppstm);
    v5 = v28;
    if ( v28 < 0 )
    {
      v7 = (unsigned int)v28;
      v8 = 727;
      goto LABEL_8;
    }
  }
  else
  {
    if ( !Appx::Packaging::BundleValidationHelper::ContainsApplicationPackage((Appx::Packaging::Production::BundleManifestWriterHelper *)((char *)this + 8)) )
    {
      v5 = -2147019873;
      v8 = 683;
      v7 = 2147947423LL;
      goto LABEL_8;
    }
    v11 = *((_DWORD *)this + 228) <= 1u;
    v33 = 0;
    if ( v11 )
    {
      v13 = 1;
      if ( *((_BYTE *)this + 1113) )
      {
        v12 = L"http://schemas.microsoft.com/appx/2017/bundle";
      }
      else if ( RtlNumberGenericTableElementsAvl((PRTL_AVL_TABLE)((char *)this + 992))
             || (v12 = L"http://schemas.microsoft.com/appx/2013/bundle", *((_BYTE *)this + 1112)) )
      {
        v12 = L"http://schemas.microsoft.com/appx/2016/bundle";
      }
    }
    else
    {
      v12 = L"http://schemas.microsoft.com/appx/2018/bundle";
      v13 = 0;
    }
    if ( *((_DWORD *)this + 228) > 1u && (*((_BYTE *)this + 916) || v13) )
    {
      v5 = -2146958844;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v10, &EVENT_BUNDLE_VALIDATION_INVALID_PACKAGES_VERSIONS, 2148008452LL);
      AppxPackagingLog(&EVENT_BUNDLE_VALIDATION_INVALID_PACKAGES_VERSIONS, 0xB0000105, -2146958844);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\bundle\\src\\bundlevalidationpackageset.cpp",
        (const char *)0x80080204LL,
        (int)RestartKey);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BF,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)0x80080204LL,
        (int)RestartKey);
      v14 = 0;
      goto LABEL_22;
    }
    v32 = ppstm;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v32);
    v5 = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::Create(&v32, v12, &v33);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v32);
    if ( (v5 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)v5,
        (int)RestartKey);
      v14 = v33;
LABEL_22:
      Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>((__int64 (__fastcall ***)(_QWORD, __int64))v14);
      goto LABEL_44;
    }
    v15 = v33;
    started = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::StartBundleManifest(
                v33,
                *((const unsigned __int16 **)this + 116),
                *((const unsigned __int16 **)this + 117),
                *((_QWORD *)this + 119));
    v17 = started;
    if ( started < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C1,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)(unsigned int)started,
        (int)RestartKey);
      Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>((__int64 (__fastcall ***)(_QWORD, __int64))v15);
      v5 = v17;
      goto LABEL_44;
    }
    for ( i = 0; i < *((_QWORD *)this + 122); ++i )
    {
      v19 = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::AddPackage(
              v15,
              *(struct Appx::Packaging::BundleManifest::PackageInfo **)(*((_QWORD *)this + 120) + 8 * i));
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C5,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
          (const char *)(unsigned int)v19,
          (int)RestartKey);
        Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>((__int64 (__fastcall ***)(_QWORD, __int64))v15);
        v5 = v20;
        goto LABEL_44;
      }
    }
    RestartKey = 0;
    v21 = (struct _RTL_AVL_TABLE *)((char *)this + 992);
    while ( 1 )
    {
      v22 = (struct Appx::Packaging::BundleManifest::OptionalBundleInfo **)RtlEnumerateGenericTableWithoutSplayingAvl(
                                                                             v21,
                                                                             &RestartKey);
      if ( !v22 )
        break;
      v23 = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::AddOptionalBundle(v15, v22[1]);
      if ( v23 < 0 )
      {
        v24 = 716;
        goto LABEL_36;
      }
    }
    v23 = Appx::Packaging::BundleManifest::BundleManifestXmlWriter::EndBundleManifest(v15);
    if ( v23 < 0 )
    {
      v24 = 719;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)(unsigned int)v23,
        (int)RestartKey);
LABEL_37:
      Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>((__int64 (__fastcall ***)(_QWORD, __int64))v15);
      v5 = v23;
      goto LABEL_44;
    }
    v32 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v32);
    v25 = Appx::Packaging::BundleManifest::BundleManifestReaderImpl::Create(ppstm, &v32, 0);
    v23 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D3,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlemanifestwriterhelper.cpp",
        (const char *)(unsigned int)v25,
        (int)RestartKey);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v32);
      goto LABEL_37;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v32);
    Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>((__int64 (__fastcall ***)(_QWORD, __int64))v15);
  }
  v5 = 0;
  *a2 = ppstm;
  ppstm = 0;
LABEL_44:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppstm);
  return v5;
}

```

## disassembly

```asm
0x180074f34  mov     [rsp-28h+arg_0], rbx
0x180074f39  push    rbp
0x180074f3a  push    rsi
0x180074f3b  push    rdi
0x180074f3c  push    r14
0x180074f3e  push    r15
0x180074f40  mov     rbp, rsp
0x180074f43  sub     rsp, 30h
0x180074f47  mov     r15, rdx
0x180074f4a  mov     qword ptr [rdx], 0
0x180074f51  xor     edx, edx; unsigned __int16 *
0x180074f53  mov     rdi, rcx
0x180074f56  call    ?ValidatePayloadPackageExtension@BundleManifestWriterHelper@Production@Packaging@Appx@@AEAAJPEBG@Z; Appx::Packaging::Production::BundleManifestWriterHelper::ValidatePayloadPackageExtension(ushort const *)
0x180074f5b  mov     ebx, eax
0x180074f5d  test    eax, eax
0x180074f5f  jns     short loc_180074F7E
0x180074f61  mov     rcx, [rbp+28h]; this
0x180074f65  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180074f6c  mov     r9d, eax; char *
0x180074f6f  mov     edx, 29Fh; void *
0x180074f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074f79  jmp     loc_1800752A6
0x180074f7e  lea     rcx, [rbp+ppstm]
0x180074f82  mov     [rbp+ppstm], 0
0x180074f8a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180074f8f  lea     r8, [rbp+ppstm]; ppstm
0x180074f93  mov     edx, 1; fDeleteOnRelease
0x180074f98  xor     ecx, ecx; hGlobal
0x180074f9a  call    cs:__imp_CreateStreamOnHGlobal
0x180074fa1  nop     dword ptr [rax+rax+00h]
0x180074fa6  mov     ebx, eax
0x180074fa8  test    eax, eax
0x180074faa  jns     short loc_180074FB6
0x180074fac  mov     r9d, eax
0x180074faf  mov     edx, 2A5h
0x180074fb4  jmp     short loc_180074FDC
0x180074fb6  mov     rsi, [rdi]
0x180074fb9  test    rsi, rsi
0x180074fbc  jnz     loc_1800752BA
0x180074fc2  lea     rcx, [rdi+8]; this
0x180074fc6  call    ?ContainsApplicationPackage@BundleValidationHelper@Packaging@Appx@@QEAA_NXZ; Appx::Packaging::BundleValidationHelper::ContainsApplicationPackage(void)
0x180074fcb  test    al, al
0x180074fcd  jnz     short loc_180074FF1
0x180074fcf  mov     ebx, 8007139Fh
0x180074fd4  mov     edx, 2ABh; void *
0x180074fd9  mov     r9d, ebx; char *
0x180074fdc  mov     rcx, [rbp+28h]; this
0x180074fe0  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180074fe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074fec  jmp     loc_18007529D
0x180074ff1  cmp     dword ptr [rdi+390h], 1
0x180074ff8  mov     [rbp+arg_18], 0
0x180075000  jbe     short loc_18007500E
0x180075002  lea     rbx, ?Namespace2018@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2018/"...
0x180075009  xor     sil, sil
0x18007500c  jmp     short loc_180075050
0x18007500e  cmp     byte ptr [rdi+459h], 0
0x180075015  mov     sil, 1
0x180075018  jz      short loc_180075023
0x18007501a  lea     rbx, ?Namespace2017@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2017/"...
0x180075021  jmp     short loc_180075050
0x180075023  lea     rcx, [rdi+3E0h]; Table
0x18007502a  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180075031  nop     dword ptr [rax+rax+00h]
0x180075036  test    eax, eax
0x180075038  jnz     short loc_180075049
0x18007503a  lea     rbx, ?Namespace@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2013/"...
0x180075041  cmp     [rdi+458h], al
0x180075047  jz      short loc_180075050
0x180075049  lea     rbx, ?Namespace2016@BundleManifest@Packaging@Appx@@3QBGB; "http://schemas.microsoft.com/appx/2016/"...
0x180075050  cmp     dword ptr [rdi+390h], 1
0x180075057  jbe     short loc_1800750D4
0x180075059  cmp     byte ptr [rdi+394h], 0
0x180075060  jnz     short loc_180075067
0x180075062  test    sil, sil
0x180075065  jz      short loc_1800750D4
0x180075067  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x18007506e  mov     ebx, 80080204h
0x180075073  jz      short loc_180075084
0x180075075  mov     r8d, ebx
0x180075078  lea     rdx, EVENT_BUNDLE_VALIDATION_INVALID_PACKAGES_VERSIONS
0x18007507f  call    McTemplateU0q_EventWriteTransfer
0x180075084  mov     r8d, ebx; int
0x180075087  lea     rcx, EVENT_BUNDLE_VALIDATION_INVALID_PACKAGES_VERSIONS; struct _EVENT_DESCRIPTOR *
0x18007508e  mov     edx, 0B0000105h; unsigned int
0x180075093  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJ@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long)
0x180075098  mov     rcx, [rbp+28h]; this
0x18007509c  lea     r8, aOnecorePrintsc_78; "onecore\\printscan\\appxpackaging\\lib"...
0x1800750a3  mov     r9d, ebx; char *
0x1800750a6  mov     edx, 0F3h; void *
0x1800750ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800750b0  mov     rcx, [rbp+28h]; this
0x1800750b4  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x1800750bb  mov     r9d, ebx; char *
0x1800750be  mov     edx, 2BFh; void *
0x1800750c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800750c8  xor     ecx, ecx
0x1800750ca  call    ??$AutoPtrDeallocate@VBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Common@@YAXPEAVBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)
0x1800750cf  jmp     loc_18007529D
0x1800750d4  mov     rax, [rbp+ppstm]
0x1800750d8  lea     rcx, [rbp+arg_10]
0x1800750dc  mov     [rbp+arg_10], rax
0x1800750e0  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x1800750e5  lea     r8, [rbp+arg_18]
0x1800750e9  mov     rdx, rbx
0x1800750ec  lea     rcx, [rbp+arg_10]
0x1800750f0  call    ?Create@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@SAJAEBV?$ComPtr@UIStream@@@WRL@Microsoft@@PEBGPEAPEAV1234@@Z; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::Create(Microsoft::WRL::ComPtr<IStream> const &,ushort const *,Appx::Packaging::BundleManifest::BundleManifestXmlWriter * *)
0x1800750f5  lea     rcx, [rbp+arg_10]
0x1800750f9  mov     ebx, eax
0x1800750fb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075100  test    ebx, ebx
0x180075102  jns     short loc_180075122
0x180075104  mov     rcx, [rbp+28h]; this
0x180075108  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x18007510f  mov     r9d, ebx; char *
0x180075112  mov     edx, 2C0h; void *
0x180075117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007511c  mov     rcx, [rbp+arg_18]
0x180075120  jmp     short loc_1800750CA
0x180075122  mov     rbx, [rbp+arg_18]
0x180075126  mov     r9, [rdi+3B8h]; unsigned __int64
0x18007512d  mov     rcx, rbx; this
0x180075130  mov     r8, [rdi+3A8h]; unsigned __int16 *
0x180075137  mov     rdx, [rdi+3A0h]; unsigned __int16 *
0x18007513e  call    ?StartBundleManifest@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@QEAAJPEBG0_K@Z; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::StartBundleManifest(ushort const *,ushort const *,unsigned __int64)
0x180075143  mov     esi, eax
0x180075145  test    eax, eax
0x180075147  jns     short loc_180075170
0x180075149  mov     rcx, [rbp+28h]; this
0x18007514d  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075154  mov     r9d, eax; char *
0x180075157  mov     edx, 2C1h; void *
0x18007515c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075161  mov     rcx, rbx
0x180075164  call    ??$AutoPtrDeallocate@VBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Common@@YAXPEAVBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)
0x180075169  mov     ebx, esi
0x18007516b  jmp     loc_18007529D
0x180075170  xor     esi, esi
0x180075172  cmp     rsi, [rdi+3D0h]
0x180075179  jnb     short loc_1800751C2
0x18007517b  mov     rdx, [rdi+3C0h]
0x180075182  mov     rcx, rbx; this
0x180075185  mov     rdx, [rdx+rsi*8]; struct Appx::Packaging::BundleManifest::PackageInfo *
0x180075189  call    ?AddPackage@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@QEAAJPEAUPackageInfo@234@@Z; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::AddPackage(Appx::Packaging::BundleManifest::PackageInfo *)
0x18007518e  mov     r14d, eax
0x180075191  test    eax, eax
0x180075193  js      short loc_18007519A
0x180075195  inc     rsi
0x180075198  jmp     short loc_180075172
0x18007519a  mov     rcx, [rbp+28h]; this
0x18007519e  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x1800751a5  mov     r9d, r14d; char *
0x1800751a8  mov     edx, 2C5h; void *
0x1800751ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800751b2  mov     rcx, rbx
0x1800751b5  call    ??$AutoPtrDeallocate@VBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Common@@YAXPEAVBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)
0x1800751ba  mov     ebx, r14d
0x1800751bd  jmp     loc_18007529D
0x1800751c2  mov     [rbp+RestartKey], 0
0x1800751ca  lea     rsi, [rdi+3E0h]
0x1800751d1  lea     rdx, [rbp+RestartKey]; RestartKey
0x1800751d5  mov     rcx, rsi; Table
0x1800751d8  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1800751df  nop     dword ptr [rax+rax+00h]
0x1800751e4  mov     rcx, rbx; this
0x1800751e7  test    rax, rax
0x1800751ea  jz      short loc_18007521F
0x1800751ec  mov     rdx, [rax+8]; struct Appx::Packaging::BundleManifest::OptionalBundleInfo *
0x1800751f0  call    ?AddOptionalBundle@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@QEAAJPEAUOptionalBundleInfo@234@@Z; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::AddOptionalBundle(Appx::Packaging::BundleManifest::OptionalBundleInfo *)
0x1800751f5  mov     edi, eax
0x1800751f7  test    eax, eax
0x1800751f9  jns     short loc_1800751D1
0x1800751fb  mov     edx, 2CCh; void *
0x180075200  mov     rcx, [rbp+28h]; this
0x180075204  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x18007520b  mov     r9d, edi; char *
0x18007520e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075213  mov     rcx, rbx
0x180075216  call    ??$AutoPtrDeallocate@VBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Common@@YAXPEAVBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)
0x18007521b  mov     ebx, edi
0x18007521d  jmp     short loc_18007529D
0x18007521f  call    ?EndBundleManifest@BundleManifestXmlWriter@BundleManifest@Packaging@Appx@@QEAAJXZ; Appx::Packaging::BundleManifest::BundleManifestXmlWriter::EndBundleManifest(void)
0x180075224  mov     edi, eax
0x180075226  test    eax, eax
0x180075228  jns     short loc_180075231
0x18007522a  mov     edx, 2CFh
0x18007522f  jmp     short loc_180075200
0x180075231  lea     rcx, [rbp+arg_10]
0x180075235  mov     [rbp+arg_10], 0
0x18007523d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075242  mov     rcx, [rbp+ppstm]; struct IStream *
0x180075246  lea     rdx, [rbp+arg_10]; struct Appx::Packaging::BundleManifest::BundleManifestReaderImpl **
0x18007524a  xor     r8d, r8d; unsigned __int16 **
0x18007524d  call    ?Create@BundleManifestReaderImpl@BundleManifest@Packaging@Appx@@SAJPEAUIStream@@PEAPEAV1234@PEAPEAG@Z; Appx::Packaging::BundleManifest::BundleManifestReaderImpl::Create(IStream *,Appx::Packaging::BundleManifest::BundleManifestReaderImpl * *,ushort * *)
0x180075252  mov     edi, eax
0x180075254  test    eax, eax
0x180075256  jns     short loc_18007527B
0x180075258  mov     rcx, [rbp+28h]; this
0x18007525c  lea     r8, aOnecorePrintsc_13; "onecore\\printscan\\appxpackaging\\prod"...
0x180075263  mov     r9d, eax; char *
0x180075266  mov     edx, 2D3h; void *
0x18007526b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180075270  lea     rcx, [rbp+arg_10]
0x180075274  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075279  jmp     short loc_180075213
0x18007527b  lea     rcx, [rbp+arg_10]
0x18007527f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180075284  mov     rcx, rbx
0x180075287  call    ??$AutoPtrDeallocate@VBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Common@@YAXPEAVBundleManifestXmlWriter@BundleManifest@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::BundleManifest::BundleManifestXmlWriter>(Appx::Packaging::BundleManifest::BundleManifestXmlWriter *)
0x18007528c  mov     rax, [rbp+ppstm]
0x180075290  xor     ebx, ebx
0x180075292  mov     [r15], rax
0x180075295  mov     [rbp+ppstm], 0
0x18007529d  lea     rcx, [rbp+ppstm]
0x1800752a1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800752a6  mov     eax, ebx
0x1800752a8  mov     rbx, [rsp+30h+arg_0]
0x1800752ad  add     rsp, 30h
0x1800752b1  pop     r15
0x1800752b3  pop     r14
0x1800752b5  pop     rdi
0x1800752b6  pop     rsi
0x1800752b7  pop     rbp
0x1800752b8  retn
0x1800752ba  mov     rax, [rsi]
0x1800752bd  lea     rcx, [rbp+ppstm]
0x1800752c1  mov     rbx, [rax+20h]
0x1800752c5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800752ca  lea     rdx, [rbp+ppstm]
0x1800752ce  mov     rcx, rsi
0x1800752d1  mov     rax, rbx
0x1800752d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800752d9  mov     ebx, eax
0x1800752db  test    eax, eax
0x1800752dd  jns     short loc_18007528C
0x1800752df  mov     r9d, eax
0x1800752e2  mov     edx, 2D7h
0x1800752e7  jmp     loc_180074FDC
```
