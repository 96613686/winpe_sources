# Appx::Packaging::Consumption::BundlePackageStreamingReader::CreateUnknownStreamingReader2(IAppxStreamingDataSource *,APPX_PACKAGE_READER_OPTIONS,IAppxFootprintFileDownloadProgressHandler *,ushort const *,IUnknown * *)

- ea: `0x180005f60`
- end: `0x180006802`
- name: `?CreateUnknownStreamingReader2@BundlePackageStreamingReader@Consumption@Packaging@Appx@@SAJPEAUIAppxStreamingDataSource@@W4APPX_PACKAGE_READER_OPTIONS@@PEAUIAppxFootprintFileDownloadProgressHandler@@PEBGPEAPEAUIUnknown@@@Z`
- size: `2210`
- prototype: `static int __high(struct IAppxStreamingDataSource *, enum APPX_PACKAGE_READER_OPTIONS, struct IAppxFootprintFileDownloadProgressHandler *, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005f890`
- `0x1800932b0`

## callees

- `0x180005eb8`
- `0x180005ee4`
- `0x180005f60`
- `0x180006808`
- `0x1800068d0`
- `0x180008114`
- `0x180008488`
- `0x1800133fc`
- `0x180024894`
- `0x180024974`
- `0x180025f70`
- `0x1800462cc`
- `0x180046e28`
- `0x18005e5c0`
- `0x1800992a0`
- `0x1800c9aac`
- `0x180106010`

## import_xrefs

- `OpcServices!__imp_GetCloneableStream` at `0x180005ff1`
- `OpcServices!__imp_GetCloneableStream` at `0x180005ff1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180006351`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180006551`
- `OLEAUT32!__imp_SysFreeString` at `0x18000656a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006664`
- `OLEAUT32!__imp_SysFreeString` at `0x180006714`
- `OLEAUT32!__imp_SysFreeString` at `0x180006778`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067d7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180006351`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800063ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064eb`
- `OLEAUT32!__imp_SysFreeString` at `0x180006551`
- `OLEAUT32!__imp_SysFreeString` at `0x18000656a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006664`
- `OLEAUT32!__imp_SysFreeString` at `0x180006714`
- `OLEAUT32!__imp_SysFreeString` at `0x180006778`
- `OLEAUT32!__imp_SysFreeString` at `0x1800067d7`

## string_xrefs

- `0x18000623f`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800062a5`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800063a8`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x18000644f`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180006488`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180006533`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800065f7`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x18000660c`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x18000664c`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180006676`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800066cd`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800066f3`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x180006757`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800067b6`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagestreamingreader.cpp`
- `0x1800060cc`: `AppxMetadata\AppxBundleManifest.xml`
- `0x180006063`: `AppxManifest.xml`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::BundlePackageStreamingReader::CreateUnknownStreamingReader2(
        struct IAppxStreamingDataSource *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v7; // eax
  int CloneableStream; // ebx
  struct Appx::Packaging::StreamOverDataSource *v9; // rsi
  int PackagePartsMap; // eax
  int v11; // eax
  Appx::Packaging::FileNameHelper *v12; // rdi
  int v13; // eax
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD); // rbx
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned int v22; // esi
  __int64 (__fastcall ***v23)(_QWORD, GUID *, _QWORD); // rsi
  int v24; // eax
  struct IOpcPartUri *v25; // rcx
  struct IOpcPartUri *v26; // rcx
  __int64 v27; // rcx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 (__fastcall ***v33)(_QWORD, GUID *, _QWORD); // rsi
  int v34; // eax
  struct IOpcPartUri *v35; // rcx
  struct IOpcPartUri *v36; // rcx
  struct IOpcPartUri *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdx
  void (*v40)(void); // rax
  __int64 v41; // rdx
  int v42; // [rsp+20h] [rbp-71h]
  _QWORD *v43; // [rsp+20h] [rbp-71h]
  _QWORD *v44; // [rsp+20h] [rbp-71h]
  __int64 v45; // [rsp+40h] [rbp-51h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-49h] BYREF
  struct IOpcPartUri *v47; // [rsp+50h] [rbp-41h] BYREF
  BSTR v48; // [rsp+58h] [rbp-39h] BYREF
  struct Appx::Packaging::StreamOverDataSource *v49; // [rsp+60h] [rbp-31h] BYREF
  struct IOpcPartUri *v50; // [rsp+68h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-21h] BYREF
  struct Appx::Packaging::FileNameHelper *v52; // [rsp+78h] [rbp-19h] BYREF
  _QWORD v53[2]; // [rsp+80h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v53[0] = a4;
  if ( !a1 )
  {
    v39 = 292;
LABEL_59:
    CloneableStream = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)0x80004003LL,
      v42);
    return (unsigned int)CloneableStream;
  }
  if ( !a5 )
  {
    v39 = 293;
    goto LABEL_59;
  }
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(a1, EVENT_STREAMING_READER_CREATE_START, a2);
  v49 = 0;
  v7 = Appx::Packaging::StreamOverDataSource::Create(a1);
  CloneableStream = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v7,
      v42);
    return (unsigned int)CloneableStream;
  }
  v45 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
  v9 = v49;
  CloneableStream = GetCloneableStream(v49, &v45);
  if ( CloneableStream < 0 )
  {
    v41 = 300;
LABEL_71:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)CloneableStream,
      v42);
LABEL_74:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
LABEL_35:
    if ( v9 )
      (*(void (__fastcall **)(struct Appx::Packaging::StreamOverDataSource *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)CloneableStream;
  }
  CloneableStream = Appx::Packaging::Consumption::StreamingReaderHelper::PrefetchPackageMetadata(v9);
  if ( CloneableStream < 0 )
  {
    v41 = 304;
    goto LABEL_71;
  }
  v46 = 0;
  PackagePartsMap = Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(v45, &v46);
  CloneableStream = PackagePartsMap;
  if ( PackagePartsMap < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)PackagePartsMap,
      v42);
    goto LABEL_33;
  }
  v52 = 0;
  v11 = Appx::Packaging::FileNameHelper::Create(&v52);
  CloneableStream = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v11,
      v42);
    Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v52);
LABEL_33:
    Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v46);
    v29 = v45;
    if ( v45 )
    {
      v45 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    goto LABEL_35;
  }
  v47 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
  v12 = v52;
  v13 = Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(v52, L"AppxManifest.xml", &v47);
  CloneableStream = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v13,
      v42);
LABEL_73:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
    Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
    Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v46);
    goto LABEL_74;
  }
  v48 = 0;
  v14 = ((__int64 (__fastcall *)(struct IOpcPartUri *, BSTR *))v47->lpVtbl->GetAbsoluteUri)(v47, &v48);
  CloneableStream = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v14,
      v42);
    SysFreeString(v48);
    goto LABEL_73;
  }
  v15 = v46;
  if ( !Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>::Find(v46, v48) )
  {
    v50 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    v16 = Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(
            v12,
            L"AppxMetadata\\AppxBundleManifest.xml",
            &v50);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
        (const char *)(unsigned int)v16,
        v42);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
      SysFreeString(v48);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v15);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
    }
    else
    {
      bstrString = 0;
      v18 = ((__int64 (__fastcall *)(struct IOpcPartUri *, BSTR *))v50->lpVtbl->GetAbsoluteUri)(v50, &bstrString);
      v17 = v18;
      if ( v18 >= 0 )
      {
        if ( !Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>::Find(v15, bstrString) )
        {
          v17 = -2147024883;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16E,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
            (const char *)0x8007000DLL,
            v42);
          SysFreeString(bstrString);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
          SysFreeString(v48);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
          Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
          Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v15);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
          if ( v9 )
          {
            v40 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
            goto LABEL_67;
          }
          return v17;
        }
        v46 = 0;
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        LODWORD(v43) = a2;
        v19 = Appx::Packaging::Consumption::BundlePackageStreamingReader::Create(a1, &v49, v45, v15);
        v22 = v19;
        if ( v19 >= 0 )
        {
          if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
          {
            v43 = v53;
            McGenEventWrite_EventWriteTransfer(v20, EVENT_STREAMING_READER_CREATE_STOP, v21, 1);
          }
          v23 = v46;
          v24 = (**v46)(v46, &GUID_00000000_0000_0000_c000_000000000046, a5);
          v17 = v24;
          if ( v24 >= 0 )
          {
            if ( v23 )
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v23)[2])(v23);
            SysFreeString(bstrString);
            v25 = v50;
            if ( v50 )
            {
              v50 = 0;
              ((void (__fastcall *)(struct IOpcPartUri *))v25->lpVtbl->Release)(v25);
            }
            SysFreeString(v48);
            v26 = v47;
            if ( v47 )
            {
              v47 = 0;
              ((void (__fastcall *)(struct IOpcPartUri *))v26->lpVtbl->Release)(v26);
            }
            Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
            Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v15);
            v27 = v45;
            if ( !v45 )
              goto LABEL_29;
            v45 = 0;
LABEL_28:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
LABEL_29:
            if ( v49 )
              (*(void (__fastcall **)(struct Appx::Packaging::StreamOverDataSource *))(*(_QWORD *)v49 + 16LL))(v49);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x169,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
            (const char *)(unsigned int)v24,
            (int)v43);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
          SysFreeString(bstrString);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
          goto LABEL_63;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x167,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
          (const char *)(unsigned int)v19,
          a2);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        SysFreeString(bstrString);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
        goto LABEL_60;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
        (const char *)(unsigned int)v18,
        v42);
      SysFreeString(bstrString);
      v36 = v50;
      if ( v50 )
      {
        v50 = 0;
        ((void (__fastcall *)(struct IOpcPartUri *))v36->lpVtbl->Release)(v36);
      }
      SysFreeString(v48);
      v37 = v47;
      if ( v47 )
      {
        v47 = 0;
        ((void (__fastcall *)(struct IOpcPartUri *))v37->lpVtbl->Release)(v37);
      }
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v15);
      v38 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
    }
    if ( v9 )
    {
      v40 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
      goto LABEL_67;
    }
    return v17;
  }
  v46 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
  LODWORD(v44) = a2;
  v30 = Appx::Packaging::Consumption::AppxPackageStreamingReader::Create(a1, &v49, v45, v15);
  v22 = v30;
  if ( v30 >= 0 )
  {
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      v44 = v53;
      McGenEventWrite_EventWriteTransfer(v31, EVENT_STREAMING_READER_CREATE_STOP, v32, 1);
    }
    v33 = v46;
    v34 = (**v46)(v46, &GUID_00000000_0000_0000_c000_000000000046, a5);
    v17 = v34;
    if ( v34 >= 0 )
    {
      if ( v33 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v33)[2])(v33);
      SysFreeString(v48);
      v35 = v47;
      if ( v47 )
      {
        v47 = 0;
        ((void (__fastcall *)(struct IOpcPartUri *))v35->lpVtbl->Release)(v35);
      }
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v15);
      v27 = v45;
      if ( !v45 )
        goto LABEL_29;
      v45 = 0;
      goto LABEL_28;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
      (const char *)(unsigned int)v34,
      (int)v44);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
LABEL_63:
    SysFreeString(v48);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
    Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
    Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v15);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
    if ( v49 )
    {
      v40 = *(void (**)(void))(*(_QWORD *)v49 + 16LL);
LABEL_67:
      v40();
      return v17;
    }
    return v17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14D,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagestreamingreader.cpp",
    (const char *)(unsigned int)v30,
    a2);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
LABEL_60:
  SysFreeString(v48);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
  Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v12);
  Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v15);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
  if ( v49 )
    (*(void (__fastcall **)(struct Appx::Packaging::StreamOverDataSource *))(*(_QWORD *)v49 + 16LL))(v49);
  return v22;
}

```

## disassembly

```asm
0x180005f60  push    rbp
0x180005f62  push    rbx
0x180005f63  push    rsi
0x180005f64  push    rdi
0x180005f65  push    r12
0x180005f67  push    r13
0x180005f69  push    r14
0x180005f6b  push    r15
0x180005f6d  lea     rbp, [rsp-17h]
0x180005f72  sub     rsp, 0A8h
0x180005f79  mov     rax, cs:__security_cookie
0x180005f80  xor     rax, rsp
0x180005f83  mov     [rbp+4Fh+var_50], rax
0x180005f87  mov     r13, [rbp+4Fh+arg_20]
0x180005f8b  xor     edi, edi
0x180005f8d  mov     [rbp+4Fh+var_60], r9
0x180005f91  mov     r14, r9
0x180005f94  mov     rbx, r8
0x180005f97  mov     r12d, edx
0x180005f9a  mov     r15, rcx
0x180005f9d  test    rcx, rcx
0x180005fa0  jz      loc_18000647F
0x180005fa6  test    r13, r13
0x180005fa9  jz      loc_1800065B5
0x180005faf  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x180005fb6  jnz     loc_1800065BF
0x180005fbc  lea     r8, [rbp+4Fh+var_80]
0x180005fc0  mov     [rbp+4Fh+var_80], rdi
0x180005fc4  mov     rdx, rbx
0x180005fc7  mov     rcx, r15; struct IAppxStreamingDataSource *
0x180005fca  call    ?Create@StreamOverDataSource@Packaging@Appx@@SAJPEAUIAppxStreamingDataSource@@PEAUIAppxFootprintFileDownloadProgressHandler@@AEAV?$ComPtr@VStreamOverDataSource@Packaging@Appx@@@WRL@Microsoft@@@Z; Appx::Packaging::StreamOverDataSource::Create(IAppxStreamingDataSource *,IAppxFootprintFileDownloadProgressHandler *,Microsoft::WRL::ComPtr<Appx::Packaging::StreamOverDataSource> &)
0x180005fcf  mov     ebx, eax
0x180005fd1  test    eax, eax
0x180005fd3  js      loc_18000644B
0x180005fd9  lea     rcx, [rbp+4Fh+var_A0]
0x180005fdd  mov     [rbp+4Fh+var_A0], rdi
0x180005fe1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180005fe6  mov     rsi, [rbp+4Fh+var_80]
0x180005fea  lea     rdx, [rbp+4Fh+var_A0]
0x180005fee  mov     rcx, rsi
0x180005ff1  call    cs:__imp_GetCloneableStream
0x180005ff8  nop     dword ptr [rax+rax+00h]
0x180005ffd  mov     ebx, eax
0x180005fff  test    eax, eax
0x180006001  js      loc_1800065E7
0x180006007  mov     rcx, rsi; struct Appx::Packaging::StreamOverDataSource *
0x18000600a  call    ?PrefetchPackageMetadata@StreamingReaderHelper@Consumption@Packaging@Appx@@SAJPEAVStreamOverDataSource@34@@Z; Appx::Packaging::Consumption::StreamingReaderHelper::PrefetchPackageMetadata(Appx::Packaging::StreamOverDataSource *)
0x18000600f  mov     ebx, eax
0x180006011  test    eax, eax
0x180006013  js      loc_1800065EE
0x180006019  mov     rcx, [rbp+4Fh+var_A0]
0x18000601d  lea     rdx, [rbp+4Fh+var_98]
0x180006021  mov     [rbp+4Fh+var_98], rdi
0x180006025  call    ?GetPackagePartsMap@PackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEAPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(IStream *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> * *)
0x18000602a  mov     ebx, eax
0x18000602c  test    eax, eax
0x18000602e  js      loc_18000623B
0x180006034  lea     rcx, [rbp+4Fh+var_68]; struct Appx::Packaging::FileNameHelper **
0x180006038  mov     [rbp+4Fh+var_68], rdi
0x18000603c  call    ?Create@FileNameHelper@Packaging@Appx@@SAJPEAPEAV123@@Z; Appx::Packaging::FileNameHelper::Create(Appx::Packaging::FileNameHelper * *)
0x180006041  mov     ebx, eax
0x180006043  test    eax, eax
0x180006045  js      loc_1800062A1
0x18000604b  lea     rcx, [rbp+4Fh+var_90]
0x18000604f  mov     [rbp+4Fh+var_90], rdi
0x180006053  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180006058  mov     rdi, [rbp+4Fh+var_68]
0x18000605c  lea     r8, [rbp+4Fh+var_90]; struct IOpcPartUri **
0x180006060  mov     rcx, rdi; this
0x180006063  lea     rdx, ?FileName@Manifest@Packaging@Appx@@3QBGB; "AppxManifest.xml"
0x18000606a  call    ?CreatePartUriWithoutValidation@FileNameHelper@Packaging@Appx@@QEAAJPEBGPEAPEAUIOpcPartUri@@@Z; Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(ushort const *,IOpcPartUri * *)
0x18000606f  mov     ebx, eax
0x180006071  test    eax, eax
0x180006073  js      loc_180006608
0x180006079  mov     rcx, [rbp+4Fh+var_90]
0x18000607d  lea     rdx, [rbp+4Fh+var_88]
0x180006081  mov     [rbp+4Fh+var_88], 0
0x180006089  mov     rax, [rcx]
0x18000608c  mov     rax, [rax+38h]
0x180006090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006095  mov     ebx, eax
0x180006097  test    eax, eax
0x180006099  js      loc_180006648
0x18000609f  mov     rbx, [rbp+4Fh+var_98]
0x1800060a3  mov     rdx, [rbp+4Fh+var_88]
0x1800060a7  mov     rcx, rbx
0x1800060aa  call    ?Find@?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@QEAAPEAUAppxFileInfo@Consumption@Packaging@Appx@@PEBG@Z; Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>::Find(ushort const *)
0x1800060af  test    rax, rax
0x1800060b2  jnz     loc_1800062C4
0x1800060b8  lea     rcx, [rbp+4Fh+var_78]
0x1800060bc  mov     [rbp+4Fh+var_78], rax
0x1800060c0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800060c5  lea     r8, [rbp+4Fh+var_78]; struct IOpcPartUri **
0x1800060c9  mov     rcx, rdi; this
0x1800060cc  lea     rdx, ?FileName@BundleManifest@Packaging@Appx@@3QBGB; "AppxMetadata\\AppxBundleManifest.xml"
0x1800060d3  call    ?CreatePartUriWithoutValidation@FileNameHelper@Packaging@Appx@@QEAAJPEBGPEAPEAUIOpcPartUri@@@Z; Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(ushort const *,IOpcPartUri * *)
0x1800060d8  mov     r14d, eax
0x1800060db  test    eax, eax
0x1800060dd  js      loc_1800066EF
0x1800060e3  mov     rcx, [rbp+4Fh+var_78]
0x1800060e7  lea     rdx, [rbp+4Fh+bstrString]
0x1800060eb  mov     [rbp+4Fh+bstrString], 0
0x1800060f3  mov     rax, [rcx]
0x1800060f6  mov     rax, [rax+38h]
0x1800060fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ff  mov     r14d, eax
0x180006102  test    eax, eax
0x180006104  js      loc_1800063A4
0x18000610a  mov     rdx, [rbp+4Fh+bstrString]
0x18000610e  mov     rcx, rbx
0x180006111  call    ?Find@?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@QEAAPEAUAppxFileInfo@Consumption@Packaging@Appx@@PEBG@Z; Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>::Find(ushort const *)
0x180006116  test    rax, rax
0x180006119  jz      loc_18000652F
0x18000611f  lea     rcx, [rbp+4Fh+var_98]
0x180006123  mov     [rbp+4Fh+var_98], 0
0x18000612b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180006130  mov     r8, [rbp+4Fh+var_A0]
0x180006134  lea     rax, [rbp+4Fh+var_98]
0x180006138  mov     [rsp+0E0h+var_B0], rax
0x18000613d  lea     rdx, [rbp+4Fh+var_80]
0x180006141  mov     rax, [rbp+4Fh+var_60]
0x180006145  mov     r9, rbx
0x180006148  mov     [rsp+0E0h+var_B8], rax
0x18000614d  mov     rcx, r15
0x180006150  mov     [rsp+0E0h+var_C0], r12d; int
0x180006155  call    ?Create@BundlePackageStreamingReader@Consumption@Packaging@Appx@@CAJPEAUIAppxStreamingDataSource@@AEAV?$ComPtr@VStreamOverDataSource@Packaging@Appx@@@WRL@Microsoft@@PEAUIStream@@PEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@W4APPX_PACKAGE_READER_OPTIONS@@PEBGPEAPEAV?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VBundlePackageStreamingReader@Consumption@Packaging@Appx@@@78@@Z; Appx::Packaging::Consumption::BundlePackageStreamingReader::Create(IAppxStreamingDataSource *,Microsoft::WRL::ComPtr<Appx::Packaging::StreamOverDataSource> &,IStream *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,APPX_PACKAGE_READER_OPTIONS,ushort const *,Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::BundlePackageStreamingReader> * *)
0x18000615a  xor     r15d, r15d
0x18000615d  mov     esi, eax
0x18000615f  test    eax, eax
0x180006161  js      loc_180006753
0x180006167  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18000616e  jnz     loc_180006792
0x180006174  mov     rsi, [rbp+4Fh+var_98]
0x180006178  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000617f  mov     r8, r13
0x180006182  mov     rcx, rsi
0x180006185  mov     rax, [rsi]
0x180006188  mov     rax, [rax]
0x18000618b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006190  mov     r14d, eax
0x180006193  test    eax, eax
0x180006195  js      loc_1800067B2
0x18000619b  test    rsi, rsi
0x18000619e  jz      short loc_1800061AF
0x1800061a0  mov     rax, [rsi]
0x1800061a3  mov     rcx, rsi
0x1800061a6  mov     rax, [rax+10h]
0x1800061aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061af  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800061b3  call    cs:__imp_SysFreeString
0x1800061ba  nop     dword ptr [rax+rax+00h]
0x1800061bf  mov     rcx, [rbp+4Fh+var_78]
0x1800061c3  test    rcx, rcx
0x1800061c6  jz      short loc_1800061D8
0x1800061c8  mov     [rbp+4Fh+var_78], r15
0x1800061cc  mov     rax, [rcx]
0x1800061cf  mov     rax, [rax+10h]
0x1800061d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d8  mov     rcx, [rbp+4Fh+var_88]; bstrString
0x1800061dc  call    cs:__imp_SysFreeString
0x1800061e3  nop     dword ptr [rax+rax+00h]
0x1800061e8  mov     rcx, [rbp+4Fh+var_90]
0x1800061ec  test    rcx, rcx
0x1800061ef  jz      short loc_180006201
0x1800061f1  mov     [rbp+4Fh+var_90], r15
0x1800061f5  mov     rax, [rcx]
0x1800061f8  mov     rax, [rax+10h]
0x1800061fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006201  mov     rcx, rdi
0x180006204  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x180006209  mov     rcx, rbx
0x18000620c  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x180006211  mov     rcx, [rbp+4Fh+var_A0]
0x180006215  test    rcx, rcx
0x180006218  jz      short loc_18000622A
0x18000621a  mov     [rbp+4Fh+var_A0], r15
0x18000621e  mov     rax, [rcx]
0x180006221  mov     rax, [rax+10h]
0x180006225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622a  mov     rcx, [rbp+4Fh+var_80]
0x18000622e  test    rcx, rcx
0x180006231  jnz     loc_1800067F1
0x180006237  xor     eax, eax
0x180006239  jmp     short loc_180006280
0x18000623b  mov     rcx, [rbp+57h]; this
0x18000623f  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x180006246  mov     r9d, ebx; char *
0x180006249  mov     edx, 134h; void *
0x18000624e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006253  mov     rcx, [rbp+4Fh+var_98]
0x180006257  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x18000625c  mov     rcx, [rbp+4Fh+var_A0]
0x180006260  test    rcx, rcx
0x180006263  jz      short loc_180006275
0x180006265  mov     [rbp+4Fh+var_A0], rdi
0x180006269  mov     rax, [rcx]
0x18000626c  mov     rax, [rax+10h]
0x180006270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006275  test    rsi, rsi
0x180006278  jnz     loc_1800065D3
0x18000627e  mov     eax, ebx
0x180006280  mov     rcx, [rbp+4Fh+var_50]
0x180006284  xor     rcx, rsp; StackCookie
0x180006287  call    __security_check_cookie
0x18000628c  add     rsp, 0A8h
0x180006293  pop     r15
0x180006295  pop     r14
0x180006297  pop     r13
0x180006299  pop     r12
0x18000629b  pop     rdi
0x18000629c  pop     rsi
0x18000629d  pop     rbx
0x18000629e  pop     rbp
0x18000629f  retn
0x1800062a1  mov     rcx, [rbp+57h]; this
0x1800062a5  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x1800062ac  mov     r9d, ebx; char *
0x1800062af  mov     edx, 137h; void *
0x1800062b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062b9  mov     rcx, [rbp+4Fh+var_68]
0x1800062bd  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x1800062c2  jmp     short loc_180006253
0x1800062c4  lea     rcx, [rbp+4Fh+var_98]
0x1800062c8  mov     [rbp+4Fh+var_98], 0
0x1800062d0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800062d5  mov     r8, [rbp+4Fh+var_A0]
0x1800062d9  lea     rax, [rbp+4Fh+var_98]
0x1800062dd  mov     [rsp+0E0h+var_B0], rax
0x1800062e2  lea     rdx, [rbp+4Fh+var_80]
0x1800062e6  mov     [rsp+0E0h+var_B8], r14
0x1800062eb  mov     r9, rbx
0x1800062ee  mov     rcx, r15
0x1800062f1  mov     [rsp+0E0h+var_C0], r12d; int
0x1800062f6  call    ?Create@AppxPackageStreamingReader@Consumption@Packaging@Appx@@SAJPEAUIAppxStreamingDataSource@@AEAV?$ComPtr@VStreamOverDataSource@Packaging@Appx@@@WRL@Microsoft@@PEAUIStream@@PEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@W4APPX_PACKAGE_READER_OPTIONS@@PEBGPEAPEAV?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageStreamingReader@Consumption@Packaging@Appx@@@78@@Z; Appx::Packaging::Consumption::AppxPackageStreamingReader::Create(IAppxStreamingDataSource *,Microsoft::WRL::ComPtr<Appx::Packaging::StreamOverDataSource> &,IStream *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,APPX_PACKAGE_READER_OPTIONS,ushort const *,Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageStreamingReader> * *)
0x1800062fb  mov     esi, eax
0x1800062fd  test    eax, eax
0x1800062ff  js      loc_180006672
0x180006305  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18000630c  jnz     loc_1800066A9
0x180006312  mov     rsi, [rbp+4Fh+var_98]
0x180006316  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000631d  mov     r8, r13
0x180006320  mov     rcx, rsi
0x180006323  mov     rax, [rsi]
0x180006326  mov     rax, [rax]
0x180006329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632e  mov     r14d, eax
0x180006331  test    eax, eax
0x180006333  js      loc_1800066C9
0x180006339  test    rsi, rsi
0x18000633c  jz      short loc_18000634D
0x18000633e  mov     rax, [rsi]
0x180006341  mov     rcx, rsi
0x180006344  mov     rax, [rax+10h]
0x180006348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634d  mov     rcx, [rbp+4Fh+var_88]; bstrString
0x180006351  call    cs:__imp_SysFreeString
0x180006358  nop     dword ptr [rax+rax+00h]
0x18000635d  mov     rcx, [rbp+4Fh+var_90]
0x180006361  test    rcx, rcx
0x180006364  jz      short loc_18000637A
0x180006366  mov     [rbp+4Fh+var_90], 0
0x18000636e  mov     rax, [rcx]
0x180006371  mov     rax, [rax+10h]
0x180006375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637a  mov     rcx, rdi
0x18000637d  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x180006382  mov     rcx, rbx
0x180006385  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x18000638a  mov     rcx, [rbp+4Fh+var_A0]
0x18000638e  test    rcx, rcx
0x180006391  jz      loc_18000622A
0x180006397  mov     [rbp+4Fh+var_A0], 0
0x18000639f  jmp     loc_18000621E
0x1800063a4  mov     rcx, [rbp+57h]; this
0x1800063a8  lea     r8, aOnecorePrintsc_103; "onecore\\printscan\\appxpackaging\\cons"...
0x1800063af  mov     r9d, r14d; char *
0x1800063b2  mov     edx, 159h; void *
0x1800063b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063bc  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800063c0  call    cs:__imp_SysFreeString
0x1800063c7  nop     dword ptr [rax+rax+00h]
0x1800063cc  mov     rcx, [rbp+4Fh+var_78]
0x1800063d0  xor     r15d, r15d
0x1800063d3  test    rcx, rcx
0x1800063d6  jz      short loc_1800063E8
0x1800063d8  mov     [rbp+4Fh+var_78], r15
0x1800063dc  mov     rax, [rcx]
0x1800063df  mov     rax, [rax+10h]
0x1800063e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063e8  mov     rcx, [rbp+4Fh+var_88]; bstrString
0x1800063ec  call    cs:__imp_SysFreeString
0x1800063f3  nop     dword ptr [rax+rax+00h]
0x1800063f8  mov     rcx, [rbp+4Fh+var_90]
0x1800063fc  test    rcx, rcx
0x1800063ff  jz      short loc_180006411
0x180006401  mov     [rbp+4Fh+var_90], r15
0x180006405  mov     rax, [rcx]
0x180006408  mov     rax, [rax+10h]
0x18000640c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
