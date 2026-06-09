# Appx::Packaging::Consumption::BundlePackageReader::CreateAppxFilesWithManifestData(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,bool)

- ea: `0x18001aa64`
- end: `0x18001af88`
- name: `?CreateAppxFilesWithManifestData@BundlePackageReader@Consumption@Packaging@Appx@@AEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@_N@Z`
- size: `1316`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180047244`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x1800197ac`
- `0x180019950`
- `0x18001aa64`
- `0x180025a0c`
- `0x1800269d0`
- `0x180071f50`
- `0x18007702c`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ade6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ac84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ad71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ade6`

## string_xrefs

- `0x18001acd8`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001acef`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001ad59`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001adce`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001ae2f`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001ae93`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001aeb0`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001af00`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001af2e`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001af46`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18001af6f`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::BundlePackageReader::CreateAppxFilesWithManifestData(
        __int64 a1,
        struct _RTL_AVL_TABLE *a2,
        char a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, struct IUri **); // rbx
  int v12; // eax
  int v13; // edi
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, struct IAppxBundleManifestPackageInfo **); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  char *v19; // rbx
  __int64 v20; // rcx
  int v21; // eax
  struct IOpcPartUriVtbl *v22; // rbx
  unsigned __int16 *QueryInterface; // rdx
  int v24; // eax
  struct IAppxBundleManifestPackageInfo *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rdx
  struct IOpcPartUriVtbl *lpVtbl; // rcx
  struct IAppxBundleManifestPackageInfo *v31; // rcx
  struct IUri *v32; // rcx
  __int64 v33; // rcx
  struct IUri *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rdx
  struct IOpcPartUriVtbl *v37; // rcx
  int v38; // [rsp+20h] [rbp-50h]
  __int64 v39; // [rsp+30h] [rbp-40h] BYREF
  struct IUri *v40; // [rsp+38h] [rbp-38h] BYREF
  struct IAppxFile *v41; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-28h] BYREF
  struct IOpcPartUri v43; // [rsp+50h] [rbp-20h] BYREF
  ULONG (__stdcall *v44)(IOpcPartUri *); // [rsp+58h] [rbp-18h] BYREF
  HRESULT (__stdcall *v45[2])(IOpcPartUri *, Uri_PROPERTY, DWORD *, DWORD); // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v47; // [rsp+B0h] [rbp+40h] BYREF
  struct IAppxBundleManifestPackageInfo *v48; // [rsp+C8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v39 = 0;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 32LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
  v8 = v7(v3, &v39);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
      (const char *)(unsigned int)v8,
      v38);
LABEL_39:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
    return v9;
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 56);
    v40 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, struct IUri **))(*(_QWORD *)v10 + 40LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
    v12 = v11(v10, &v40);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
        (const char *)(unsigned int)v12,
        v38);
LABEL_30:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
    }
    else
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 32LL))(v39, &v47);
      while ( v47 == 1 )
      {
        v14 = v39;
        v48 = 0;
        v15 = *(void (__fastcall **)(__int64, struct IAppxBundleManifestPackageInfo **))(*(_QWORD *)v39 + 24LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
        v15(v14, &v48);
        pv = 0;
        v16 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, LPVOID *))v48->lpVtbl->GetFileName)(
                v48,
                &pv);
        v9 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16E,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
            (const char *)(unsigned int)v16,
            v38);
          CoTaskMemFree(pv);
          v31 = v48;
          if ( v48 )
          {
            v48 = 0;
            ((void (__fastcall *)(struct IAppxBundleManifestPackageInfo *))v31->lpVtbl->Release)(v31);
          }
          v32 = v40;
          if ( v40 )
          {
            v40 = 0;
            ((void (__fastcall *)(struct IUri *))v32->lpVtbl->Release)(v32);
          }
          v33 = v39;
          if ( v39 )
          {
            v39 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          }
          return v9;
        }
        v44 = 0;
        v45[0] = 0;
        v17 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, ULONG (__stdcall **)(IOpcPartUri *)))v48->lpVtbl->GetOffset)(
                v48,
                &v44);
        v9 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x174,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
            (const char *)(unsigned int)v17,
            v38);
          CoTaskMemFree(pv);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
          goto LABEL_39;
        }
        v18 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, HRESULT (__stdcall **)(IOpcPartUri *, Uri_PROPERTY, DWORD *, DWORD)))v48->lpVtbl->GetSize)(
                v48,
                v45);
        v13 = v18;
        if ( v18 < 0 )
        {
          v27 = (unsigned int)v18;
          v26 = 373;
          goto LABEL_24;
        }
        if ( (unsigned __int64)v44 > -1LL - (unsigned __int64)v45[0] )
        {
          v13 = -2147024362;
          v26 = 374;
          v27 = 2147942934LL;
LABEL_24:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v26,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
            (const char *)v27,
            v38);
          goto LABEL_29;
        }
        if ( v44 )
        {
          v19 = (char *)v45[0] + (unsigned __int64)v44;
          v20 = *(_QWORD *)(a1 + 48);
          v43.lpVtbl = 0;
          v21 = Appx::Packaging::Consumption::PackageReaderHelper::ExtractFileInfo(
                  v20,
                  a2,
                  (const unsigned __int16 *)pv,
                  1,
                  0x80080204,
                  &v43);
          v13 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x185,
              (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
              (const char *)(unsigned int)v21,
              v38);
            lpVtbl = v43.lpVtbl;
            goto LABEL_28;
          }
          if ( (unsigned __int64)v19 > *(_QWORD *)(a1 + 40) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x187,
              (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
              (const char *)0x80080204LL,
              v38);
            v37 = v43.lpVtbl;
LABEL_59:
            Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(v37);
            v13 = -2146958844;
LABEL_29:
            CoTaskMemFree(pv);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
            goto LABEL_30;
          }
          v22 = v43.lpVtbl;
          if ( (char *)v43.lpVtbl->Release > (char *)v44 )
          {
            v36 = 392;
            goto LABEL_57;
          }
          if ( v43.lpVtbl->GetPropertyLength != v45[0] )
          {
            v36 = 393;
LABEL_57:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v36,
              (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
              (const char *)0x80080204LL,
              v38);
            v37 = v22;
            goto LABEL_59;
          }
          if ( LODWORD(v43.lpVtbl->AddRef) != -1 )
          {
            v13 = -2147024883;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x18D,
              (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
              (const char *)0x8007000DLL,
              v38);
            goto LABEL_27;
          }
          v41 = 0;
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
          QueryInterface = (unsigned __int16 *)v22->QueryInterface;
          if ( a3 )
          {
            v24 = Appx::Packaging::Consumption::BundlePayloadPackageFile::CreateStreaming(v48, QueryInterface, &v41);
            v13 = v24;
            if ( v24 < 0 )
            {
              v28 = 405;
              goto LABEL_26;
            }
          }
          else
          {
            v24 = Appx::Packaging::Consumption::BundlePayloadPackageFile::CreateNonstreaming(
                    v48,
                    QueryInterface,
                    *(struct IStream **)(a1 + 112),
                    v40,
                    *(struct Appx::Packaging::ManifestComparisonHelper **)(a1 + 96),
                    &v41);
            v13 = v24;
            if ( v24 < 0 )
            {
              v28 = 415;
LABEL_26:
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)v28,
                (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
                (const char *)(unsigned int)v24,
                v38);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
LABEL_27:
              lpVtbl = v22;
LABEL_28:
              Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(lpVtbl);
              goto LABEL_29;
            }
          }
          v22->QueryInterface = 0;
          v24 = Common::GenericMap<unsigned short *,unsigned short *>::Insert(*(_QWORD *)(a1 + 120), pv, v41);
          v13 = v24;
          if ( v24 < 0 )
          {
            v28 = 419;
            goto LABEL_26;
          }
          v41 = 0;
          pv = 0;
          Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(v22);
        }
        else
        {
          v13 = 0;
        }
        CoTaskMemFree(pv);
        v25 = v48;
        if ( v48 )
        {
          v48 = 0;
          ((void (__fastcall *)(struct IAppxBundleManifestPackageInfo *))v25->lpVtbl->Release)(v25);
        }
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 40LL))(v39, &v47);
      }
      if ( v13 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A7,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
          (const char *)(unsigned int)v13,
          v38);
      v34 = v40;
      if ( v40 )
      {
        v40 = 0;
        ((void (__fastcall *)(struct IUri *))v34->lpVtbl->Release)(v34);
      }
      v35 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
    }
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x18001aa64  mov     [rsp-38h+arg_8], rbx
0x18001aa69  push    rbp
0x18001aa6a  push    rsi
0x18001aa6b  push    rdi
0x18001aa6c  push    r12
0x18001aa6e  push    r13
0x18001aa70  push    r14
0x18001aa72  push    r15
0x18001aa74  mov     rbp, rsp
0x18001aa77  sub     rsp, 70h
0x18001aa7b  mov     rdi, [rcx+40h]
0x18001aa7f  mov     rsi, rcx
0x18001aa82  xor     r12d, r12d
0x18001aa85  lea     rcx, [rbp+var_40]
0x18001aa89  mov     [rbp+var_40], r12
0x18001aa8d  mov     r14b, r8b
0x18001aa90  mov     r15, rdx
0x18001aa93  mov     rax, [rdi]
0x18001aa96  mov     rbx, [rax+20h]
0x18001aa9a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001aa9f  lea     rdx, [rbp+var_40]
0x18001aaa3  mov     rcx, rdi
0x18001aaa6  mov     rax, rbx
0x18001aaa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaae  mov     ebx, eax
0x18001aab0  test    eax, eax
0x18001aab2  js      loc_18001AE8F
0x18001aab8  mov     rdi, [rsi+38h]
0x18001aabc  lea     rcx, [rbp+var_38]
0x18001aac0  mov     [rbp+var_38], r12
0x18001aac4  mov     rax, [rdi]
0x18001aac7  mov     rbx, [rax+28h]
0x18001aacb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001aad0  lea     rdx, [rbp+var_38]
0x18001aad4  mov     rcx, rdi
0x18001aad7  mov     rax, rbx
0x18001aada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aadf  mov     edi, eax
0x18001aae1  test    eax, eax
0x18001aae3  js      loc_18001AEAC
0x18001aae9  mov     rcx, [rbp+var_40]
0x18001aaed  lea     rdx, [rbp+arg_0]
0x18001aaf1  mov     [rbp+arg_0], r12d
0x18001aaf5  mov     rax, [rcx]
0x18001aaf8  mov     rax, [rax+20h]
0x18001aafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab01  mov     r13d, 80080204h
0x18001ab07  cmp     [rbp+arg_0], 1
0x18001ab0b  jnz     loc_18001AE4C
0x18001ab11  mov     rdi, [rbp+var_40]
0x18001ab15  lea     rcx, [rbp+arg_18]
0x18001ab19  mov     [rbp+arg_18], r12
0x18001ab1d  mov     rax, [rdi]
0x18001ab20  mov     rbx, [rax+18h]
0x18001ab24  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ab29  lea     rdx, [rbp+arg_18]
0x18001ab2d  mov     rcx, rdi
0x18001ab30  mov     rax, rbx
0x18001ab33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab38  mov     rcx, [rbp+arg_18]
0x18001ab3c  lea     rdx, [rbp+pv]
0x18001ab40  mov     [rbp+pv], r12
0x18001ab44  mov     rax, [rcx]
0x18001ab47  mov     rax, [rax+28h]
0x18001ab4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab50  mov     ebx, eax
0x18001ab52  test    eax, eax
0x18001ab54  js      loc_18001AD55
0x18001ab5a  mov     rcx, [rbp+arg_18]
0x18001ab5e  lea     rdx, [rbp+var_18]
0x18001ab62  mov     [rbp+var_18], r12
0x18001ab66  mov     [rbp+var_10], r12
0x18001ab6a  mov     rax, [rcx]
0x18001ab6d  mov     rax, [rax+30h]
0x18001ab71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab76  mov     ebx, eax
0x18001ab78  test    eax, eax
0x18001ab7a  js      loc_18001ADCA
0x18001ab80  mov     rcx, [rbp+arg_18]
0x18001ab84  lea     rdx, [rbp+var_10]
0x18001ab88  mov     rax, [rcx]
0x18001ab8b  mov     rax, [rax+38h]
0x18001ab8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab94  mov     edi, eax
0x18001ab96  test    eax, eax
0x18001ab98  js      loc_18001AE14
0x18001ab9e  mov     rdx, [rbp+var_10]
0x18001aba2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aba6  mov     rcx, [rbp+var_18]
0x18001abaa  sub     rax, rdx
0x18001abad  cmp     rcx, rax
0x18001abb0  ja      loc_18001ACC7
0x18001abb6  test    rcx, rcx
0x18001abb9  jz      loc_18001ACC2
0x18001abbf  mov     r8, [rbp+pv]
0x18001abc3  lea     rbx, [rdx+rcx]
0x18001abc7  mov     rcx, [rsi+30h]
0x18001abcb  lea     rax, [rbp+var_20]
0x18001abcf  mov     [rsp+70h+var_48], rax
0x18001abd4  mov     r9b, 1
0x18001abd7  mov     rdx, r15
0x18001abda  mov     dword ptr [rsp+70h+var_50], r13d; int
0x18001abdf  mov     [rbp+var_20], r12
0x18001abe3  call    ?ExtractFileInfo@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBG_NJPEAPEAUAppxFileInfo@234@@Z; Appx::Packaging::Consumption::PackageReaderHelper::ExtractFileInfo(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,bool,long,Appx::Packaging::Consumption::AppxFileInfo * *)
0x18001abe8  mov     edi, eax
0x18001abea  test    eax, eax
0x18001abec  js      loc_18001AE2B
0x18001abf2  cmp     rbx, [rsi+28h]
0x18001abf6  ja      loc_18001AF42
0x18001abfc  mov     rbx, [rbp+var_20]
0x18001ac00  mov     rax, [rbp+var_18]
0x18001ac04  cmp     [rbx+10h], rax
0x18001ac08  ja      loc_18001AF25
0x18001ac0e  mov     rax, [rbp+var_10]
0x18001ac12  cmp     [rbx+20h], rax
0x18001ac16  jnz     loc_18001AF1E
0x18001ac1c  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x18001ac20  jnz     loc_18001AEFC
0x18001ac26  lea     rcx, [rbp+var_30]
0x18001ac2a  mov     [rbp+var_30], r12
0x18001ac2e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ac33  mov     rdx, [rbx]; unsigned __int16 *
0x18001ac36  mov     rcx, [rbp+arg_18]; struct IAppxBundleManifestPackageInfo *
0x18001ac3a  test    r14b, r14b
0x18001ac3d  jz      loc_18001AEC9
0x18001ac43  lea     r8, [rbp+var_30]; struct IAppxFile **
0x18001ac47  call    ?CreateStreaming@BundlePayloadPackageFile@Consumption@Packaging@Appx@@SAJPEAUIAppxBundleManifestPackageInfo@@PEAGPEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::BundlePayloadPackageFile::CreateStreaming(IAppxBundleManifestPackageInfo *,ushort *,IAppxFile * *)
0x18001ac4c  mov     edi, eax
0x18001ac4e  test    eax, eax
0x18001ac50  js      loc_18001AE21
0x18001ac56  mov     [rbx], r12
0x18001ac59  mov     r8, [rbp+var_30]
0x18001ac5d  mov     rdx, [rbp+pv]
0x18001ac61  mov     rcx, [rsi+78h]
0x18001ac65  call    ?Insert@?$GenericMap@PEAGPEAG@Common@@QEAAJPEAG0@Z; Common::GenericMap<ushort *,ushort *>::Insert(ushort *,ushort *)
0x18001ac6a  mov     edi, eax
0x18001ac6c  test    eax, eax
0x18001ac6e  js      short loc_18001ACE6
0x18001ac70  mov     rcx, rbx
0x18001ac73  mov     [rbp+var_30], r12
0x18001ac77  mov     [rbp+pv], r12
0x18001ac7b  call    ??$AutoPtrDeallocate@UAppxFileInfo@Consumption@Packaging@Appx@@@Common@@YAXPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(Appx::Packaging::Consumption::AppxFileInfo *)
0x18001ac80  mov     rcx, [rbp+pv]; pv
0x18001ac84  call    cs:__imp_CoTaskMemFree
0x18001ac8b  nop     dword ptr [rax+rax+00h]
0x18001ac90  mov     rcx, [rbp+arg_18]
0x18001ac94  test    rcx, rcx
0x18001ac97  jz      short loc_18001ACA9
0x18001ac99  mov     [rbp+arg_18], r12
0x18001ac9d  mov     rax, [rcx]
0x18001aca0  mov     rax, [rax+10h]
0x18001aca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca9  mov     rcx, [rbp+var_40]
0x18001acad  lea     rdx, [rbp+arg_0]
0x18001acb1  mov     rax, [rcx]
0x18001acb4  mov     rax, [rax+28h]
0x18001acb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acbd  jmp     loc_18001AB07
0x18001acc2  mov     edi, r12d
0x18001acc5  jmp     short loc_18001AC80
0x18001acc7  mov     edi, 80070216h
0x18001accc  mov     edx, 176h; void *
0x18001acd1  mov     r9d, edi; char *
0x18001acd4  mov     rcx, [rbp+38h]; this
0x18001acd8  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001acdf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ace4  jmp     short loc_18001AD0F
0x18001ace6  mov     edx, 1A3h; void *
0x18001aceb  mov     rcx, [rbp+38h]; this
0x18001acef  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001acf6  mov     r9d, eax; char *
0x18001acf9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001acfe  lea     rcx, [rbp+var_30]
0x18001ad02  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ad07  mov     rcx, rbx
0x18001ad0a  call    ??$AutoPtrDeallocate@UAppxFileInfo@Consumption@Packaging@Appx@@@Common@@YAXPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(Appx::Packaging::Consumption::AppxFileInfo *)
0x18001ad0f  mov     rcx, [rbp+pv]; pv
0x18001ad13  call    cs:__imp_CoTaskMemFree
0x18001ad1a  nop     dword ptr [rax+rax+00h]
0x18001ad1f  lea     rcx, [rbp+arg_18]
0x18001ad23  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ad28  lea     rcx, [rbp+var_38]
0x18001ad2c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ad31  lea     rcx, [rbp+var_40]
0x18001ad35  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ad3a  mov     eax, edi
0x18001ad3c  mov     rbx, [rsp+70h+arg_8]
0x18001ad44  add     rsp, 70h
0x18001ad48  pop     r15
0x18001ad4a  pop     r14
0x18001ad4c  pop     r13
0x18001ad4e  pop     r12
0x18001ad50  pop     rdi
0x18001ad51  pop     rsi
0x18001ad52  pop     rbp
0x18001ad53  retn
0x18001ad55  mov     rcx, [rbp+38h]; this
0x18001ad59  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001ad60  mov     r9d, ebx; char *
0x18001ad63  mov     edx, 16Eh; void *
0x18001ad68  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ad6d  mov     rcx, [rbp+pv]; pv
0x18001ad71  call    cs:__imp_CoTaskMemFree
0x18001ad78  nop     dword ptr [rax+rax+00h]
0x18001ad7d  mov     rcx, [rbp+arg_18]
0x18001ad81  test    rcx, rcx
0x18001ad84  jz      short loc_18001AD96
0x18001ad86  mov     [rbp+arg_18], r12
0x18001ad8a  mov     rax, [rcx]
0x18001ad8d  mov     rax, [rax+10h]
0x18001ad91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad96  mov     rcx, [rbp+var_38]
0x18001ad9a  test    rcx, rcx
0x18001ad9d  jz      short loc_18001ADAF
0x18001ad9f  mov     [rbp+var_38], r12
0x18001ada3  mov     rax, [rcx]
0x18001ada6  mov     rax, [rax+10h]
0x18001adaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adaf  mov     rcx, [rbp+var_40]
0x18001adb3  test    rcx, rcx
0x18001adb6  jz      short loc_18001AE0D
0x18001adb8  mov     [rbp+var_40], r12
0x18001adbc  mov     rax, [rcx]
0x18001adbf  mov     rax, [rax+10h]
0x18001adc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adc8  jmp     short loc_18001AE0D
0x18001adca  mov     rcx, [rbp+38h]; this
0x18001adce  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001add5  mov     r9d, ebx; char *
0x18001add8  mov     edx, 174h; void *
0x18001addd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ade2  mov     rcx, [rbp+pv]; pv
0x18001ade6  call    cs:__imp_CoTaskMemFree
0x18001aded  nop     dword ptr [rax+rax+00h]
0x18001adf2  lea     rcx, [rbp+arg_18]
0x18001adf6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001adfb  lea     rcx, [rbp+var_38]
0x18001adff  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ae04  lea     rcx, [rbp+var_40]
0x18001ae08  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18001ae0d  mov     eax, ebx
0x18001ae0f  jmp     loc_18001AD3C
0x18001ae14  mov     r9d, eax
0x18001ae17  mov     edx, 175h
0x18001ae1c  jmp     loc_18001ACD4
0x18001ae21  mov     edx, 195h
0x18001ae26  jmp     loc_18001ACEB
0x18001ae2b  mov     rcx, [rbp+38h]; this
0x18001ae2f  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001ae36  mov     r9d, eax; char *
0x18001ae39  mov     edx, 185h; void *
0x18001ae3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ae43  mov     rcx, [rbp+var_20]
0x18001ae47  jmp     loc_18001AD0A
0x18001ae4c  test    edi, edi
0x18001ae4e  js      loc_18001AF6B
0x18001ae54  mov     rcx, [rbp+var_38]
0x18001ae58  test    rcx, rcx
0x18001ae5b  jz      short loc_18001AE6D
0x18001ae5d  mov     [rbp+var_38], r12
0x18001ae61  mov     rax, [rcx]
0x18001ae64  mov     rax, [rax+10h]
0x18001ae68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae6d  mov     rcx, [rbp+var_40]
0x18001ae71  test    rcx, rcx
0x18001ae74  jz      loc_18001AD3A
0x18001ae7a  mov     [rbp+var_40], r12
0x18001ae7e  mov     rax, [rcx]
0x18001ae81  mov     rax, [rax+10h]
0x18001ae85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae8a  jmp     loc_18001AD3A
0x18001ae8f  mov     rcx, [rbp+38h]; this
0x18001ae93  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001ae9a  mov     r9d, ebx; char *
0x18001ae9d  mov     edx, 160h; void *
0x18001aea2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001aea7  jmp     loc_18001AE04
0x18001aeac  mov     rcx, [rbp+38h]; this
0x18001aeb0  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001aeb7  mov     r9d, edi; char *
0x18001aeba  mov     edx, 162h; void *
0x18001aebf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001aec4  jmp     loc_18001AD28
0x18001aec9  mov     r9, [rbp+var_38]; struct IUri *
0x18001aecd  lea     rax, [rbp+var_30]
0x18001aed1  mov     r8, [rsi+70h]; struct IStream *
0x18001aed5  mov     [rsp+70h+var_48], rax; struct IAppxFile **
0x18001aeda  mov     rax, [rsi+60h]
0x18001aede  mov     [rsp+70h+var_50], rax; struct Appx::Packaging::ManifestComparisonHelper *
0x18001aee3  call    ?CreateNonstreaming@BundlePayloadPackageFile@Consumption@Packaging@Appx@@SAJPEAUIAppxBundleManifestPackageInfo@@PEAGPEAUIStream@@PEAUIUri@@PEAVManifestComparisonHelper@34@PEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::BundlePayloadPackageFile::CreateNonstreaming(IAppxBundleManifestPackageInfo *,ushort *,IStream *,IUri *,Appx::Packaging::ManifestComparisonHelper *,IAppxFile * *)
0x18001aee8  mov     edi, eax
0x18001aeea  test    eax, eax
0x18001aeec  jns     loc_18001AC56
0x18001aef2  mov     edx, 19Fh
0x18001aef7  jmp     loc_18001ACEB
0x18001aefc  mov     rcx, [rbp+38h]; this
0x18001af00  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18001af07  mov     edi, 8007000Dh
0x18001af0c  mov     edx, 18Dh; void *
0x18001af11  mov     r9d, edi; char *
  ... truncated ...
```
