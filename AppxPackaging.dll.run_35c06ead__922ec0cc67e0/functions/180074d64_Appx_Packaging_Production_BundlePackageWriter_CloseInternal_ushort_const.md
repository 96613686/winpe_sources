# Appx::Packaging::Production::BundlePackageWriter::CloseInternal(ushort const *)

- ea: `0x180074d64`
- end: `0x180074f2d`
- name: `?CloseInternal@BundlePackageWriter@Production@Packaging@Appx@@AEAAJPEBG@Z`
- size: `457`
- prototype: `int(Appx::Packaging::Production::BundlePackageWriter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f08f0`

## callees

- `0x180005eb8`
- `0x180071f50`
- `0x180074d64`
- `0x180074f34`
- `0x180076b84`
- `0x180076bd4`
- `0x18007fdf4`
- `0x1800801a4`
- `0x180106010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180074e5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180074e8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180074e5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180074e8d`
- `urlmon!CreateUri` at `0x180074dd3`
- `urlmon!CreateUri` at `0x180074dd3`

## string_xrefs

- `0x180074eb1`: `AppxMetadata\AppxBundleManifest.xml`
- `0x180074ea6`: `application/vnd.ms-appx.bundlemanifest+xml`
- `0x180074de9`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x180074e4a`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`
- `0x180074f05`: `onecore\printscan\appxpackaging\production\src\bundlepackagewriter.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::BundlePackageWriter::CloseInternal(
        Appx::Packaging::Production::BundlePackageWriter *this,
        const unsigned __int16 *a2)
{
  Appx::Packaging::Production::BundleManifestWriterHelper *v2; // rbx
  int v5; // ebx
  __int64 v6; // rdx
  HRESULT v7; // eax
  __int64 v8; // rdx
  OLECHAR *v9; // rcx
  int v11; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  struct IStream *v13; // [rsp+70h] [rbp+20h] BYREF
  IUri *ppURI; // [rsp+80h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+38h] BYREF

  v2 = (Appx::Packaging::Production::BundleManifestWriterHelper *)*((_QWORD *)this + 7);
  v13 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v13);
  v5 = Appx::Packaging::Production::BundleManifestWriterHelper::EndBundleManifest(v2, &v13);
  if ( v5 < 0 )
  {
    v6 = 445;
LABEL_17:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
      (const char *)(unsigned int)v5,
      v11);
    goto LABEL_18;
  }
  if ( !*((_BYTE *)this + 73) )
  {
    ppURI = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
    v7 = CreateUri(a2, 1u, 0, &ppURI);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v7,
        v11);
LABEL_6:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
      goto LABEL_18;
    }
    Microsoft::WRL::ComPtr<IUri>::operator=(*((_QWORD *)this + 7) + 944LL);
    bstrString = 0;
    v5 = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, &bstrString);
    if ( v5 < 0 )
    {
      v8 = 454;
LABEL_9:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\bundlepackagewriter.cpp",
        (const char *)(unsigned int)v5,
        v11);
      SysFreeString(bstrString);
      goto LABEL_6;
    }
    v5 = Appx::Packaging::Production::PackageWriterHelper::InitializeBlockMapWriter(
           *((Appx::Packaging::Production::PackageWriterHelper **)this + 6),
           bstrString);
    if ( v5 < 0 )
    {
      v8 = 455;
      goto LABEL_9;
    }
    v9 = bstrString;
    *((_BYTE *)this + 73) = 1;
    SysFreeString(v9);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&ppURI);
  }
  v11 = 1;
  v5 = Appx::Packaging::Production::PackageWriterHelper::AddPart(
         *((_QWORD *)this + 6),
         L"AppxMetadata\\AppxBundleManifest.xml",
         0,
         L"application/vnd.ms-appx.bundlemanifest+xml");
  if ( v5 < 0 )
  {
    v6 = 468;
    goto LABEL_17;
  }
  v5 = Appx::Packaging::Production::PackageWriterHelper::Close(*((Appx::Packaging::Production::PackageWriterHelper **)this
                                                               + 6));
  if ( v5 < 0 )
  {
    v6 = 470;
    goto LABEL_17;
  }
LABEL_18:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180074d64  mov     [rsp-18h+arg_8], rbx
0x180074d69  push    rbp
0x180074d6a  push    rsi
0x180074d6b  push    rdi
0x180074d6c  mov     rbp, rsp
0x180074d6f  sub     rsp, 50h
0x180074d73  mov     rbx, [rcx+38h]
0x180074d77  mov     rdi, rcx
0x180074d7a  lea     rcx, [rbp+arg_0]
0x180074d7e  mov     [rbp+arg_0], 0
0x180074d86  mov     rsi, rdx
0x180074d89  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180074d8e  lea     rdx, [rbp+arg_0]; struct IStream **
0x180074d92  mov     rcx, rbx; this
0x180074d95  call    ?EndBundleManifest@BundleManifestWriterHelper@Production@Packaging@Appx@@QEAAJPEAPEAUIStream@@@Z; Appx::Packaging::Production::BundleManifestWriterHelper::EndBundleManifest(IStream * *)
0x180074d9a  mov     ebx, eax
0x180074d9c  test    eax, eax
0x180074d9e  jns     short loc_180074DAA
0x180074da0  mov     edx, 1BDh
0x180074da5  jmp     loc_180074F01
0x180074daa  cmp     byte ptr [rdi+49h], 0
0x180074dae  jnz     loc_180074EA2
0x180074db4  lea     rcx, [rbp+ppURI]
0x180074db8  mov     [rbp+ppURI], 0
0x180074dc0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180074dc5  xor     r8d, r8d; dwReserved
0x180074dc8  lea     r9, [rbp+ppURI]; ppURI
0x180074dcc  mov     rcx, rsi; pwzURI
0x180074dcf  lea     edx, [r8+1]; dwFlags
0x180074dd3  call    cs:__imp_CreateUri
0x180074dda  nop     dword ptr [rax+rax+00h]
0x180074ddf  mov     ebx, eax
0x180074de1  test    eax, eax
0x180074de3  jns     short loc_180074E0B
0x180074de5  mov     rcx, [rbp+18h]; this
0x180074de9  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x180074df0  mov     r9d, eax; char *
0x180074df3  mov     edx, 1C2h; void *
0x180074df8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074dfd  lea     rcx, [rbp+ppURI]
0x180074e01  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180074e06  jmp     loc_180074F14
0x180074e0b  mov     rcx, [rdi+38h]
0x180074e0f  mov     rdx, [rbp+ppURI]
0x180074e13  add     rcx, 3B0h
0x180074e1a  call    ??4?$ComPtr@UIUri@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUri@@@Z; Microsoft::WRL::ComPtr<IUri>::operator=(IUri *)
0x180074e1f  mov     rcx, [rbp+ppURI]
0x180074e23  lea     rdx, [rbp+bstrString]
0x180074e27  mov     [rbp+bstrString], 0
0x180074e2f  mov     rax, [rcx]
0x180074e32  mov     rax, [rax+38h]
0x180074e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e3b  mov     ebx, eax
0x180074e3d  test    eax, eax
0x180074e3f  jns     short loc_180074E6B
0x180074e41  mov     edx, 1C6h; void *
0x180074e46  mov     rcx, [rbp+18h]; this
0x180074e4a  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x180074e51  mov     r9d, ebx; char *
0x180074e54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074e59  mov     rcx, [rbp+bstrString]; bstrString
0x180074e5d  call    cs:__imp_SysFreeString
0x180074e64  nop     dword ptr [rax+rax+00h]
0x180074e69  jmp     short loc_180074DFD
0x180074e6b  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x180074e6f  mov     rcx, [rdi+30h]; this
0x180074e73  call    ?InitializeBlockMapWriter@PackageWriterHelper@Production@Packaging@Appx@@QEAAJQEBG@Z; Appx::Packaging::Production::PackageWriterHelper::InitializeBlockMapWriter(ushort const * const)
0x180074e78  mov     ebx, eax
0x180074e7a  test    eax, eax
0x180074e7c  jns     short loc_180074E85
0x180074e7e  mov     edx, 1C7h
0x180074e83  jmp     short loc_180074E46
0x180074e85  mov     rcx, [rbp+bstrString]; bstrString
0x180074e89  mov     byte ptr [rdi+49h], 1
0x180074e8d  call    cs:__imp_SysFreeString
0x180074e94  nop     dword ptr [rax+rax+00h]
0x180074e99  lea     rcx, [rbp+ppURI]
0x180074e9d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180074ea2  mov     rax, [rbp+arg_0]
0x180074ea6  lea     r9, ?ContentType@BundleManifest@Packaging@Appx@@3QBGB; "application/vnd.ms-appx.bundlemanifest+"...
0x180074ead  mov     rcx, [rdi+30h]
0x180074eb1  lea     rdx, ?FileName@BundleManifest@Packaging@Appx@@3QBGB; "AppxMetadata\\AppxBundleManifest.xml"
0x180074eb8  mov     [rsp+50h+var_10], 0
0x180074ec1  xor     r8d, r8d
0x180074ec4  mov     [rsp+50h+var_18], 0
0x180074ec9  mov     [rsp+50h+var_20], 1
0x180074ece  mov     [rsp+50h+var_28], rax
0x180074ed3  mov     [rsp+50h+var_30], 1; int
0x180074edb  call    ?AddPart@PackageWriterHelper@Production@Packaging@Appx@@QEAAJQEBGW4FileType@FileNameHelper@34@0W4APPX_COMPRESSION_OPTION@@PEAUIStream@@_N4_K@Z; Appx::Packaging::Production::PackageWriterHelper::AddPart(ushort const * const,Appx::Packaging::FileNameHelper::FileType,ushort const * const,APPX_COMPRESSION_OPTION,IStream *,bool,bool,unsigned __int64)
0x180074ee0  mov     ebx, eax
0x180074ee2  test    eax, eax
0x180074ee4  jns     short loc_180074EED
0x180074ee6  mov     edx, 1D4h
0x180074eeb  jmp     short loc_180074F01
0x180074eed  mov     rcx, [rdi+30h]; this
0x180074ef1  call    ?Close@PackageWriterHelper@Production@Packaging@Appx@@QEAAJXZ; Appx::Packaging::Production::PackageWriterHelper::Close(void)
0x180074ef6  mov     ebx, eax
0x180074ef8  test    eax, eax
0x180074efa  jns     short loc_180074F14
0x180074efc  mov     edx, 1D6h; void *
0x180074f01  mov     rcx, [rbp+18h]; this
0x180074f05  lea     r8, aOnecorePrintsc_144; "onecore\\printscan\\appxpackaging\\prod"...
0x180074f0c  mov     r9d, ebx; char *
0x180074f0f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074f14  lea     rcx, [rbp+arg_0]
0x180074f18  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180074f1d  mov     eax, ebx
0x180074f1f  mov     rbx, [rsp+50h+arg_8]
0x180074f24  add     rsp, 50h
0x180074f28  pop     rdi
0x180074f29  pop     rsi
0x180074f2a  pop     rbp
0x180074f2b  retn
```
