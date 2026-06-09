# Appx::Packaging::AppxEncryptionFactoryImpl::DecryptPackage(IStream *,IStream *,APPX_KEY_INFO const *)

- ea: `0x18008e6e0`
- end: `0x18008ebd2`
- name: `?DecryptPackage@AppxEncryptionFactoryImpl@Packaging@Appx@@UEAAJPEAUIStream@@0PEBUAPPX_KEY_INFO@@@Z`
- size: `1266`
- prototype: `__int64 __fastcall(Appx::Packaging::AppxEncryptionFactoryImpl *__hidden this, struct IStream *, struct IStream *, const struct APPX_KEY_INFO *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180071f50`
- `0x18008e6e0`
- `0x18008ebd8`
- `0x18008ed60`
- `0x18008edcc`
- `0x18008fdb4`
- `0x18008fde0`
- `0x18008fe34`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ea95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ead4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ea95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ead4`

## string_xrefs

- `0x18008e714`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008e762`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008e7ae`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008e7f8`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008e842`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008e88c`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008e8d6`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008e922`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008eac1`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008eb0d`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008eb27`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008eb60`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppxEncryptionFactoryImpl::DecryptPackage(
        Appx::Packaging::AppxEncryptionFactoryImpl *this,
        struct IStream *a2,
        struct IStream *a3,
        const struct APPX_KEY_INFO *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // eax
  struct IAppxPackageReader *v10; // rdi
  HRESULT (__stdcall *GetFootprintFile)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  struct IAppxPackageReader *v16; // rdi
  HRESULT (__stdcall *GetPayloadFiles)(IAppxPackageReader *, IAppxFilesEnumerator **); // rbx
  int v18; // eax
  struct IAppxPackageReader *v19; // rdi
  HRESULT (__stdcall *GetBlockMap)(IAppxPackageReader *, IAppxBlockMapReader **); // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, IUri **); // rbx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64 *); // rbx
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, int *); // rbx
  int v32; // eax
  const unsigned __int16 *FileExtension; // rax
  struct Appx::Packaging::AddFileSettings *v34; // rax
  __int64 v35; // rdx
  int v37; // [rsp+20h] [rbp-49h]
  struct IAppxPackageReader *v38; // [rsp+30h] [rbp-39h] BYREF
  __int64 v39; // [rsp+38h] [rbp-31h] BYREF
  __int64 v40; // [rsp+40h] [rbp-29h] BYREF
  __int64 v41; // [rsp+48h] [rbp-21h] BYREF
  __int64 v42; // [rsp+50h] [rbp-19h] BYREF
  struct IAppxPackageWriter *v43; // [rsp+58h] [rbp-11h] BYREF
  IUri *v44; // [rsp+60h] [rbp-9h] BYREF
  __int64 v45; // [rsp+68h] [rbp-1h] BYREF
  int v46[2]; // [rsp+70h] [rbp+7h] BYREF
  struct APPX_PACKAGE_SETTINGS pv; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v48; // [rsp+88h] [rbp+1Fh] BYREF
  __int128 v49; // [rsp+90h] [rbp+27h] BYREF
  int v50; // [rsp+A0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v52; // [rsp+D8h] [rbp+6Fh] BYREF

  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = 145;
      goto LABEL_3;
    }
    v38 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v38);
    v9 = Appx::Packaging::Consumption::AppxEncryptedPackageReader::Create(a2, a4, 0, &v38);
    v8 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v9,
        v37);
LABEL_51:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v38);
      return (unsigned int)v8;
    }
    v10 = v38;
    v40 = 0;
    GetFootprintFile = v38->lpVtbl->GetFootprintFile;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
    v12 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, _QWORD, __int64 *))GetFootprintFile)(v10, 0, &v40);
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v12,
        v37);
LABEL_50:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
      goto LABEL_51;
    }
    v13 = v40;
    v41 = 0;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 56LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
    v15 = v14(v13, &v41);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v15,
        v37);
LABEL_49:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
      goto LABEL_50;
    }
    v16 = v38;
    v39 = 0;
    GetPayloadFiles = v38->lpVtbl->GetPayloadFiles;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
    v18 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetPayloadFiles)(v16, &v39);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v18,
        v37);
LABEL_48:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
      goto LABEL_49;
    }
    v19 = v38;
    v42 = 0;
    GetBlockMap = v38->lpVtbl->GetBlockMap;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
    v21 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetBlockMap)(v19, &v42);
    v8 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v21,
        v37);
LABEL_47:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
      goto LABEL_48;
    }
    v22 = v42;
    v44 = 0;
    v23 = *(__int64 (__fastcall **)(__int64, IUri **))(*(_QWORD *)v42 + 40LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
    v24 = v23(v22, &v44);
    v8 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v24,
        v37);
LABEL_46:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
      goto LABEL_47;
    }
    pv.hashMethod = v44;
    *(_QWORD *)&pv.forceZip32 = 0;
    v43 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
    v25 = Appx::Packaging::Production::AppxPackageWriter::Create(a3, &pv, &v43);
    v8 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v25,
        v37);
LABEL_45:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v43);
      goto LABEL_46;
    }
    v50 = 0;
    v49 = 0;
    v8 = Appx::Packaging::AddFileSettingsListContainer::Initialize((Appx::Packaging::AddFileSettingsListContainer *)&v49);
    if ( v8 >= 0 )
    {
      v52 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 32LL))(v39, &v52);
      if ( v8 >= 0 )
      {
        while ( v52 )
        {
          v27 = v39;
          v45 = 0;
          v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 24LL);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
          v29 = v28(v27, &v45);
          v8 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
              (const char *)(unsigned int)v29,
              v37);
            goto LABEL_35;
          }
          v30 = v45;
          *(_QWORD *)v46 = 0;
          v31 = *(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 56LL);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v46);
          v32 = v31(v30, v46);
          v8 = v32;
          if ( v32 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xBC,
              (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
              (const char *)(unsigned int)v32,
              v37);
            goto LABEL_34;
          }
          *(_QWORD *)&pv.forceZip32 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, struct APPX_PACKAGE_SETTINGS *))(*(_QWORD *)v45 + 40LL))(v45, &pv);
          if ( v8 < 0 )
          {
            v35 = 190;
LABEL_33:
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)v35,
              (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
              (const char *)(unsigned int)v8,
              v37);
            CoTaskMemFree(*(LPVOID *)&pv.forceZip32);
LABEL_34:
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v46);
LABEL_35:
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
            goto LABEL_44;
          }
          v48 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v45 + 24LL))(v45, &v48);
          if ( v8 < 0 )
          {
            v35 = 192;
            goto LABEL_33;
          }
          FileExtension = Appx::Packaging::FileExtensionHelper::GetFileExtension(*(wchar_t **)&pv.forceZip32);
          v34 = Appx::Packaging::AddFileSettingsListContainer::Find(
                  (Appx::Packaging::AddFileSettingsListContainer *)&v49,
                  FileExtension);
          v37 = v46[0];
          v8 = ((__int64 (__fastcall *)(struct IAppxPackageWriter *, _QWORD, _QWORD, _QWORD))v43->lpVtbl->AddPayloadFile)(
                 v43,
                 *(_QWORD *)&pv.forceZip32,
                 *(_QWORD *)v34,
                 v48);
          if ( v8 < 0 )
          {
            v35 = 197;
            goto LABEL_33;
          }
          v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 40LL))(v39, &v52);
          if ( v8 < 0 )
          {
            v35 = 198;
            goto LABEL_33;
          }
          CoTaskMemFree(*(LPVOID *)&pv.forceZip32);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v46);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
        }
        v8 = ((__int64 (__fastcall *)(struct IAppxPackageWriter *, __int64))v43->lpVtbl->Close)(v43, v41);
        if ( v8 >= 0 )
          goto LABEL_44;
        v26 = 202;
      }
      else
      {
        v26 = 182;
      }
    }
    else
    {
      v26 = 177;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
      (const char *)(unsigned int)v8,
      v37);
LABEL_44:
    Appx::Packaging::AddFileSettingsListContainer::~AddFileSettingsListContainer((Appx::Packaging::AddFileSettingsListContainer *)&v49);
    goto LABEL_45;
  }
  v7 = 144;
LABEL_3:
  v8 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
    (const char *)0x80004003LL,
    v37);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008e6e0  mov     [rsp-8+arg_0], rbx
0x18008e6e5  mov     [rsp-8+arg_10], rsi
0x18008e6ea  push    rbp
0x18008e6eb  push    rdi
0x18008e6ec  push    r14
0x18008e6ee  lea     rbp, [rsp-47h]
0x18008e6f3  sub     rsp, 0B0h
0x18008e6fa  xor     r14d, r14d
0x18008e6fd  mov     rdi, r9
0x18008e700  mov     rsi, r8
0x18008e703  mov     rbx, rdx
0x18008e706  test    rdx, rdx
0x18008e709  jnz     short loc_18008E72D
0x18008e70b  mov     edx, 90h; void *
0x18008e710  mov     rcx, [rbp+5Fh]; this
0x18008e714  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e71b  mov     ebx, 80004003h
0x18008e720  mov     r9d, ebx; char *
0x18008e723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e728  jmp     loc_18008EBB7
0x18008e72d  test    rsi, rsi
0x18008e730  jnz     short loc_18008E739
0x18008e732  mov     edx, 91h
0x18008e737  jmp     short loc_18008E710
0x18008e739  lea     rcx, [rbp+57h+var_90]
0x18008e73d  mov     [rbp+57h+var_90], r14
0x18008e741  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e746  lea     r9, [rbp+57h+var_90]; struct IAppxPackageReader **
0x18008e74a  xor     r8d, r8d; unsigned __int16 *
0x18008e74d  mov     rdx, rdi; struct APPX_KEY_INFO *
0x18008e750  mov     rcx, rbx; struct IStream *
0x18008e753  call    ?Create@AppxEncryptedPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEBUAPPX_KEY_INFO@@PEBGPEAPEAUIAppxPackageReader@@@Z; Appx::Packaging::Consumption::AppxEncryptedPackageReader::Create(IStream *,APPX_KEY_INFO const *,ushort const *,IAppxPackageReader * *)
0x18008e758  mov     ebx, eax
0x18008e75a  test    eax, eax
0x18008e75c  jns     short loc_18008E77B
0x18008e75e  mov     rcx, [rbp+5Fh]; this
0x18008e762  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e769  mov     r9d, eax; char *
0x18008e76c  mov     edx, 97h; void *
0x18008e771  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e776  jmp     loc_18008EBAE
0x18008e77b  mov     rdi, [rbp+57h+var_90]
0x18008e77f  lea     rcx, [rbp+57h+var_80]
0x18008e783  mov     [rbp+57h+var_80], r14
0x18008e787  mov     rax, [rdi]
0x18008e78a  mov     rbx, [rax+20h]
0x18008e78e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e793  lea     r8, [rbp+57h+var_80]
0x18008e797  xor     edx, edx
0x18008e799  mov     rcx, rdi
0x18008e79c  mov     rax, rbx
0x18008e79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e7a4  mov     ebx, eax
0x18008e7a6  test    eax, eax
0x18008e7a8  jns     short loc_18008E7C7
0x18008e7aa  mov     rcx, [rbp+5Fh]; this
0x18008e7ae  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e7b5  mov     r9d, eax; char *
0x18008e7b8  mov     edx, 99h; void *
0x18008e7bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e7c2  jmp     loc_18008EBA5
0x18008e7c7  mov     rdi, [rbp+57h+var_80]
0x18008e7cb  lea     rcx, [rbp+57h+var_78]
0x18008e7cf  mov     [rbp+57h+var_78], r14
0x18008e7d3  mov     rax, [rdi]
0x18008e7d6  mov     rbx, [rax+38h]
0x18008e7da  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e7df  lea     rdx, [rbp+57h+var_78]
0x18008e7e3  mov     rcx, rdi
0x18008e7e6  mov     rax, rbx
0x18008e7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e7ee  mov     ebx, eax
0x18008e7f0  test    eax, eax
0x18008e7f2  jns     short loc_18008E811
0x18008e7f4  mov     rcx, [rbp+5Fh]; this
0x18008e7f8  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e7ff  mov     r9d, eax; char *
0x18008e802  mov     edx, 9Bh; void *
0x18008e807  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e80c  jmp     loc_18008EB9C
0x18008e811  mov     rdi, [rbp+57h+var_90]
0x18008e815  lea     rcx, [rbp+57h+var_88]
0x18008e819  mov     [rbp+57h+var_88], r14
0x18008e81d  mov     rax, [rdi]
0x18008e820  mov     rbx, [rax+30h]
0x18008e824  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e829  lea     rdx, [rbp+57h+var_88]
0x18008e82d  mov     rcx, rdi
0x18008e830  mov     rax, rbx
0x18008e833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e838  mov     ebx, eax
0x18008e83a  test    eax, eax
0x18008e83c  jns     short loc_18008E85B
0x18008e83e  mov     rcx, [rbp+5Fh]; this
0x18008e842  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e849  mov     r9d, eax; char *
0x18008e84c  mov     edx, 9Dh; void *
0x18008e851  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e856  jmp     loc_18008EB93
0x18008e85b  mov     rdi, [rbp+57h+var_90]
0x18008e85f  lea     rcx, [rbp+57h+var_70]
0x18008e863  mov     [rbp+57h+var_70], r14
0x18008e867  mov     rax, [rdi]
0x18008e86a  mov     rbx, [rax+18h]
0x18008e86e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e873  lea     rdx, [rbp+57h+var_70]
0x18008e877  mov     rcx, rdi
0x18008e87a  mov     rax, rbx
0x18008e87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e882  mov     ebx, eax
0x18008e884  test    eax, eax
0x18008e886  jns     short loc_18008E8A5
0x18008e888  mov     rcx, [rbp+5Fh]; this
0x18008e88c  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e893  mov     r9d, eax; char *
0x18008e896  mov     edx, 0A0h; void *
0x18008e89b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e8a0  jmp     loc_18008EB8A
0x18008e8a5  mov     rdi, [rbp+57h+var_70]
0x18008e8a9  lea     rcx, [rbp+57h+var_60]
0x18008e8ad  mov     [rbp+57h+var_60], r14
0x18008e8b1  mov     rax, [rdi]
0x18008e8b4  mov     rbx, [rax+28h]
0x18008e8b8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e8bd  lea     rdx, [rbp+57h+var_60]
0x18008e8c1  mov     rcx, rdi
0x18008e8c4  mov     rax, rbx
0x18008e8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8cc  mov     ebx, eax
0x18008e8ce  test    eax, eax
0x18008e8d0  jns     short loc_18008E8EF
0x18008e8d2  mov     rcx, [rbp+5Fh]; this
0x18008e8d6  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e8dd  mov     r9d, eax; char *
0x18008e8e0  mov     edx, 0A3h; void *
0x18008e8e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e8ea  jmp     loc_18008EB81
0x18008e8ef  mov     rax, [rbp+57h+var_60]
0x18008e8f3  lea     rcx, [rbp+57h+var_68]
0x18008e8f7  mov     [rbp+57h+var_40], rax
0x18008e8fb  mov     [rbp+57h+pv], r14
0x18008e8ff  mov     [rbp+57h+var_68], r14
0x18008e903  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e908  lea     r8, [rbp+57h+var_68]; struct IAppxPackageWriter **
0x18008e90c  mov     rcx, rsi; struct IStream *
0x18008e90f  lea     rdx, [rbp+57h+pv]; struct APPX_PACKAGE_SETTINGS *
0x18008e913  call    ?Create@AppxPackageWriter@Production@Packaging@Appx@@SAJPEAUIStream@@PEAUAPPX_PACKAGE_SETTINGS@@PEAPEAUIAppxPackageWriter@@@Z; Appx::Packaging::Production::AppxPackageWriter::Create(IStream *,APPX_PACKAGE_SETTINGS *,IAppxPackageWriter * *)
0x18008e918  mov     ebx, eax
0x18008e91a  test    eax, eax
0x18008e91c  jns     short loc_18008E93B
0x18008e91e  mov     rcx, [rbp+5Fh]; this
0x18008e922  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008e929  mov     r9d, eax; char *
0x18008e92c  mov     edx, 0AEh; void *
0x18008e931  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e936  jmp     loc_18008EB78
0x18008e93b  xorps   xmm0, xmm0
0x18008e93e  mov     [rbp+57h+var_20], r14d
0x18008e942  lea     rcx, [rbp+57h+var_30]; this
0x18008e946  movdqu  [rbp+57h+var_30], xmm0
0x18008e94b  call    ?Initialize@AddFileSettingsListContainer@Packaging@Appx@@QEAAJXZ; Appx::Packaging::AddFileSettingsListContainer::Initialize(void)
0x18008e950  mov     ebx, eax
0x18008e952  test    eax, eax
0x18008e954  jns     short loc_18008E960
0x18008e956  mov     edx, 0B1h
0x18008e95b  jmp     loc_18008EB5C
0x18008e960  mov     rcx, [rbp+57h+var_88]
0x18008e964  lea     rdx, [rbp+57h+arg_8]
0x18008e968  mov     [rbp+57h+arg_8], r14d
0x18008e96c  mov     rax, [rcx]
0x18008e96f  mov     rax, [rax+20h]
0x18008e973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e978  mov     ebx, eax
0x18008e97a  test    eax, eax
0x18008e97c  jns     short loc_18008E988
0x18008e97e  mov     edx, 0B6h
0x18008e983  jmp     loc_18008EB5C
0x18008e988  cmp     [rbp+57h+arg_8], r14d
0x18008e98c  jz      loc_18008EB3D
0x18008e992  mov     rdi, [rbp+57h+var_88]
0x18008e996  lea     rcx, [rbp+57h+var_58]
0x18008e99a  mov     [rbp+57h+var_58], r14
0x18008e99e  mov     rax, [rdi]
0x18008e9a1  mov     rbx, [rax+18h]
0x18008e9a5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e9aa  lea     rdx, [rbp+57h+var_58]
0x18008e9ae  mov     rcx, rdi
0x18008e9b1  mov     rax, rbx
0x18008e9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9b9  mov     ebx, eax
0x18008e9bb  test    eax, eax
0x18008e9bd  js      loc_18008EB23
0x18008e9c3  mov     rdi, [rbp+57h+var_58]
0x18008e9c7  lea     rcx, [rbp+57h+var_50]
0x18008e9cb  mov     qword ptr [rbp+57h+var_50], r14
0x18008e9cf  mov     rax, [rdi]
0x18008e9d2  mov     rbx, [rax+38h]
0x18008e9d6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008e9db  lea     rdx, [rbp+57h+var_50]
0x18008e9df  mov     rcx, rdi
0x18008e9e2  mov     rax, rbx
0x18008e9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9ea  mov     ebx, eax
0x18008e9ec  test    eax, eax
0x18008e9ee  js      loc_18008EB09
0x18008e9f4  mov     rcx, [rbp+57h+var_58]
0x18008e9f8  lea     rdx, [rbp+57h+pv]
0x18008e9fc  mov     [rbp+57h+pv], r14
0x18008ea00  mov     rax, [rcx]
0x18008ea03  mov     rax, [rax+28h]
0x18008ea07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea0c  mov     ebx, eax
0x18008ea0e  test    eax, eax
0x18008ea10  js      loc_18008EB02
0x18008ea16  mov     rcx, [rbp+57h+var_58]
0x18008ea1a  lea     rdx, [rbp+57h+var_38]
0x18008ea1e  mov     [rbp+57h+var_38], r14d
0x18008ea22  mov     rax, [rcx]
0x18008ea25  mov     rax, [rax+18h]
0x18008ea29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea2e  mov     ebx, eax
0x18008ea30  test    eax, eax
0x18008ea32  js      loc_18008EAFB
0x18008ea38  mov     rcx, [rbp+57h+pv]; Str
0x18008ea3c  call    ?GetFileExtension@FileExtensionHelper@Packaging@Appx@@SAPEBGPEBG@Z; Appx::Packaging::FileExtensionHelper::GetFileExtension(ushort const *)
0x18008ea41  mov     rdx, rax; unsigned __int16 *
0x18008ea44  lea     rcx, [rbp+57h+var_30]; this
0x18008ea48  call    ?Find@AddFileSettingsListContainer@Packaging@Appx@@QEAAAEAVAddFileSettings@23@PEBG@Z; Appx::Packaging::AddFileSettingsListContainer::Find(ushort const *)
0x18008ea4d  mov     rcx, [rbp+57h+var_68]
0x18008ea51  mov     r10, qword ptr [rbp+57h+var_50]
0x18008ea55  mov     r9d, [rbp+57h+var_38]
0x18008ea59  mov     r8, [rax]
0x18008ea5c  mov     rax, [rcx]
0x18008ea5f  mov     rdx, [rbp+57h+pv]
0x18008ea63  mov     qword ptr [rsp+0C0h+var_A0], r10; int
0x18008ea68  mov     rax, [rax+18h]
0x18008ea6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea71  mov     ebx, eax
0x18008ea73  test    eax, eax
0x18008ea75  js      short loc_18008EAF4
0x18008ea77  mov     rcx, [rbp+57h+var_88]
0x18008ea7b  lea     rdx, [rbp+57h+arg_8]
0x18008ea7f  mov     rax, [rcx]
0x18008ea82  mov     rax, [rax+28h]
0x18008ea86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea8b  mov     ebx, eax
0x18008ea8d  test    eax, eax
0x18008ea8f  js      short loc_18008EAB8
0x18008ea91  mov     rcx, [rbp+57h+pv]; pv
0x18008ea95  call    cs:__imp_CoTaskMemFree
0x18008ea9c  nop     dword ptr [rax+rax+00h]
0x18008eaa1  lea     rcx, [rbp+57h+var_50]
0x18008eaa5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008eaaa  lea     rcx, [rbp+57h+var_58]
0x18008eaae  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008eab3  jmp     loc_18008E988
0x18008eab8  mov     edx, 0C6h; void *
0x18008eabd  mov     rcx, [rbp+5Fh]; this
0x18008eac1  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008eac8  mov     r9d, ebx; char *
0x18008eacb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ead0  mov     rcx, [rbp+57h+pv]; pv
0x18008ead4  call    cs:__imp_CoTaskMemFree
0x18008eadb  nop     dword ptr [rax+rax+00h]
0x18008eae0  lea     rcx, [rbp+57h+var_50]
0x18008eae4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008eae9  lea     rcx, [rbp+57h+var_58]
0x18008eaed  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008eaf2  jmp     short loc_18008EB6F
0x18008eaf4  mov     edx, 0C5h
0x18008eaf9  jmp     short loc_18008EABD
0x18008eafb  mov     edx, 0C0h
0x18008eb00  jmp     short loc_18008EABD
0x18008eb02  mov     edx, 0BEh
0x18008eb07  jmp     short loc_18008EABD
0x18008eb09  mov     rcx, [rbp+5Fh]; this
0x18008eb0d  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008eb14  mov     r9d, ebx; char *
0x18008eb17  mov     edx, 0BCh; void *
0x18008eb1c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008eb21  jmp     short loc_18008EAE0
0x18008eb23  mov     rcx, [rbp+5Fh]; this
0x18008eb27  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008eb2e  mov     r9d, ebx; char *
0x18008eb31  mov     edx, 0BAh; void *
0x18008eb36  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008eb3b  jmp     short loc_18008EAE9
0x18008eb3d  mov     rcx, [rbp+57h+var_68]
0x18008eb41  mov     rdx, [rbp+57h+var_78]
0x18008eb45  mov     rax, [rcx]
0x18008eb48  mov     rax, [rax+20h]
0x18008eb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb51  mov     ebx, eax
0x18008eb53  test    eax, eax
0x18008eb55  jns     short loc_18008EB6F
0x18008eb57  mov     edx, 0CAh; void *
0x18008eb5c  mov     rcx, [rbp+5Fh]; this
0x18008eb60  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008eb67  mov     r9d, ebx; char *
0x18008eb6a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
  ... truncated ...
```
