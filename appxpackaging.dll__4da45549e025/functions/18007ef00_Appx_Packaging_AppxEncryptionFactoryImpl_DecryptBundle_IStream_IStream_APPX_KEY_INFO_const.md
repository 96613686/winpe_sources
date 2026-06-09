# Appx::Packaging::AppxEncryptionFactoryImpl::DecryptBundle(IStream *,IStream *,APPX_KEY_INFO const *)

- ea: `0x18007ef00`
- end: `0x18007f5aa`
- name: `?DecryptBundle@AppxEncryptionFactoryImpl@Packaging@Appx@@UEAAJPEAUIStream@@0PEBUAPPX_KEY_INFO@@@Z`
- size: `1706`
- prototype: `__int64 __fastcall(Appx::Packaging::AppxEncryptionFactoryImpl *__hidden this, struct IStream *, struct IStream *, const struct APPX_KEY_INFO *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180071f50`
- `0x18007e5d4`
- `0x18007e684`
- `0x18007e738`
- `0x18007ef00`
- `0x1800809fc`
- `0x180083588`
- `0x1800844ac`
- `0x180087cb4`
- `0x1800992c4`
- `0x18009d3d0`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f27d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f3d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f27d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f3d0`

## string_xrefs

- `0x18007f506`: `*CopyOptionalBundles`
- `0x18007ef3d`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007ef99`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f009`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f04f`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f096`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f2a3`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f2c6`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f2f2`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f31e`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f34a`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f373`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f39c`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f3bb`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f3f6`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f415`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f46a`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f4e6`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18007f53f`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::AppxEncryptionFactoryImpl::DecryptBundle(
        Appx::Packaging::AppxEncryptionFactoryImpl *this,
        struct IStream *a2,
        struct IStream *a3,
        struct APPX_KEY_INFO *a4)
{
  __int64 v7; // rdx
  int VersionFromBundle; // ebx
  unsigned __int64 *v10; // r8
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  Appx::Packaging *v13; // rdi
  __int64 (__fastcall *v14)(Appx::Packaging *, __int64 *); // rbx
  int v15; // eax
  int v16; // eax
  struct IOpcFactory **v17; // r8
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  struct IAppxBundleWriter *v20; // rdi
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, Appx::Packaging **)); // rbx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v25)(_QWORD, GUID *, Appx::Packaging **); // rsi
  int v26; // eax
  int v27; // eax
  unsigned int v28; // esi
  WCHAR *v29; // rax
  unsigned __int16 *v30; // r8
  WCHAR *v31; // rbx
  int TempPath2W; // eax
  struct IStream **v33; // r9
  int TempFileStream; // eax
  struct IAppxMessageHandler *v35; // r9
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rdx
  Appx::Packaging *v48; // rsi
  __int64 (__fastcall *v49)(Appx::Packaging *, __int64 *); // rbx
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rsi
  __int64 (__fastcall *v53)(__int64, __int64 *); // rbx
  HRESULT (__stdcall *QueryInterface)(IAppxBundleWriter *, const IID *const, void **); // rbx
  int v55; // eax
  __int64 v56; // rdx
  int v57; // eax
  int v58; // [rsp+28h] [rbp-39h]
  int v59; // [rsp+28h] [rbp-39h]
  Appx::Packaging *v60; // [rsp+38h] [rbp-29h] BYREF
  __int64 v61; // [rsp+40h] [rbp-21h] BYREF
  struct IAppxEncryptedPackageFile *v62; // [rsp+48h] [rbp-19h] BYREF
  __int64 v63; // [rsp+50h] [rbp-11h] BYREF
  __int64 v64; // [rsp+58h] [rbp-9h] BYREF
  struct IAppxBundleWriter *v65; // [rsp+60h] [rbp-1h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, Appx::Packaging **); // [rsp+68h] [rbp+7h] BYREF
  __int64 v67; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v68; // [rsp+78h] [rbp+17h] BYREF
  Appx::Packaging *v69; // [rsp+80h] [rbp+1Fh] BYREF
  LPVOID pv; // [rsp+88h] [rbp+27h] BYREF
  IAppxBundleReader v71; // [rsp+90h] [rbp+2Fh] BYREF
  __int64 v72; // [rsp+98h] [rbp+37h]
  __int64 v73; // [rsp+A0h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  int v75; // [rsp+D0h] [rbp+6Fh] BYREF

  v73 = -2;
  if ( !a2 )
  {
    v7 = 340;
LABEL_3:
    VersionFromBundle = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
      (const char *)0x80004003LL,
      v58);
    return (unsigned int)VersionFromBundle;
  }
  if ( !a3 )
  {
    v7 = 341;
    goto LABEL_3;
  }
  v60 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
  VersionFromBundle = Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create((__int64)a2, a4, 0, &v60, 1);
  v11 = retaddr;
  if ( VersionFromBundle < 0 )
  {
    v12 = 347;
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      v11,
      (void *)v12,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
      (const char *)(unsigned int)VersionFromBundle,
      v59);
LABEL_10:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
    return (unsigned int)VersionFromBundle;
  }
  v71.lpVtbl = 0;
  VersionFromBundle = Appx::Packaging::GetVersionFromBundle(v60, &v71, v10);
  v11 = retaddr;
  if ( VersionFromBundle < 0 )
  {
    v12 = 351;
    goto LABEL_9;
  }
  v61 = 0;
  v13 = v60;
  v14 = *(__int64 (__fastcall **)(Appx::Packaging *, __int64 *))(*(_QWORD *)v60 + 48LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
  v15 = v14(v13, &v61);
  VersionFromBundle = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
      (const char *)(unsigned int)v15,
      v59);
LABEL_15:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
    goto LABEL_10;
  }
  v65 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  v16 = Appx::Packaging::Production::BundlePackageWriter::Create(a3, (unsigned __int64)v71.lpVtbl, &v65);
  VersionFromBundle = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
      (const char *)(unsigned int)v16,
      v59);
LABEL_18:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    goto LABEL_15;
  }
  v75 = 0;
  v68 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
  VersionFromBundle = Appx::Packaging::CreateOpcFactory(0, (struct IAppxMessageHandler *)&v68, v17);
  v18 = retaddr;
  if ( VersionFromBundle < 0 )
  {
    v19 = 367;
    goto LABEL_21;
  }
  VersionFromBundle = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 32LL))(v61, &v75);
  v18 = retaddr;
  if ( VersionFromBundle < 0 )
  {
    v19 = 369;
LABEL_21:
    wil::details::in1diag3::_Log_Hr(
      v18,
      (void *)v19,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
      (const char *)(unsigned int)VersionFromBundle,
      v59);
LABEL_22:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    goto LABEL_18;
  }
  v20 = v65;
  while ( 1 )
  {
    if ( !v75 )
    {
      v64 = 0;
      v63 = 0;
      v48 = v60;
      v49 = *(__int64 (__fastcall **)(Appx::Packaging *, __int64 *))(*(_QWORD *)v60 + 40LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
      v50 = v49(v48, &v64);
      v28 = v50;
      if ( v50 < 0 )
      {
        v51 = 406;
LABEL_52:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v51,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
          (const char *)(unsigned int)v50,
          v59);
LABEL_63:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
        goto LABEL_64;
      }
      v52 = v64;
      v53 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v64 + 40LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
      v50 = v53(v52, &v63);
      v28 = v50;
      if ( v50 < 0 )
      {
        v51 = 407;
        goto LABEL_52;
      }
      v67 = 0;
      QueryInterface = v20->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      v55 = ((__int64 (__fastcall *)(struct IAppxBundleWriter *, GUID *, __int64 *))QueryInterface)(
              v20,
              &GUID_6d8fe971_01cc_49a0_b685_233851279962,
              &v67);
      v28 = v55;
      if ( v55 >= 0 )
      {
        v55 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v67 + 24LL))(
                v67,
                L"*CopyOptionalBundles",
                v63);
        v28 = v55;
        if ( v55 >= 0 )
        {
          v57 = ((__int64 (__fastcall *)(struct IAppxBundleWriter *))v20->lpVtbl->Close)(v20);
          v28 = v57;
          if ( v57 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x19D,
              (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
              (const char *)(unsigned int)v57,
              v59);
          goto LABEL_62;
        }
        v56 = 410;
      }
      else
      {
        v56 = 409;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v56,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v55,
        v59);
LABEL_62:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      goto LABEL_63;
    }
    v66 = 0;
    v21 = v61;
    v22 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, Appx::Packaging **)))(*(_QWORD *)v61 + 24LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
    v23 = v22(v21, &v66);
    VersionFromBundle = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v23,
        v59);
      goto LABEL_49;
    }
    v69 = 0;
    v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
    v25 = **v66;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
    v26 = v25(v24, &GUID_c2cb2364_4fa9_4878_8c9c_7e2afb98b6d2, &v69);
    VersionFromBundle = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v26,
        v59);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
LABEL_49:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
      goto LABEL_22;
    }
    pv = 0;
    v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, Appx::Packaging **), LPVOID *))(*v66)[5])(
            v66,
            &pv);
    v28 = v27;
    if ( v27 < 0 )
      break;
    v29 = (WCHAR *)operator new[](0xFFFEu, (const struct std::nothrow_t *)&std::nothrow);
    v31 = v29;
    if ( !v29 )
    {
      v28 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)0x8007000ELL,
        v59);
      operator delete(0, v47);
      goto LABEL_46;
    }
    TempPath2W = Appx::Packaging::DownlevelPortability::GetTempPath2W(0x7FFFu, v29, v30);
    v28 = TempPath2W;
    if ( TempPath2W < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x181,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)TempPath2W,
        v59);
      operator delete(v31, v46);
      goto LABEL_46;
    }
    v62 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
    TempFileStream = Appx::Packaging::CreateTempFileStream(
                       (Appx::Packaging *)v31,
                       L"AXB",
                       (const unsigned __int16 *)&v62,
                       v33);
    v28 = TempFileStream;
    if ( TempFileStream < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)TempFileStream,
        v59);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      operator delete(v31, v45);
      goto LABEL_46;
    }
    v36 = Appx::Packaging::DecryptPayloadPackage(v69, v62, 0, v35);
    v28 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v36,
        v59);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      operator delete(v31, v44);
      goto LABEL_46;
    }
    v72 = 0;
    v37 = (*(__int64 (__fastcall **)(struct IAppxEncryptedPackageFile *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v62 + 40LL))(
            v62,
            0,
            0,
            0);
    v28 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v37,
        v59);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      operator delete(v31, v43);
      goto LABEL_46;
    }
    v38 = ((__int64 (__fastcall *)(struct IAppxBundleWriter *, LPVOID, struct IAppxEncryptedPackageFile *))v20->lpVtbl->AddPayloadPackage)(
            v20,
            pv,
            v62);
    v28 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v38,
        v59);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      operator delete(v31, v42);
      goto LABEL_46;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
    v39 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 40LL))(v61, &v75);
    v28 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x190,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v39,
        v59);
      operator delete(v31, v41);
      goto LABEL_46;
    }
    operator delete(v31, v40);
    CoTaskMemFree(pv);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x17B,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
    (const char *)(unsigned int)v27,
    v59);
LABEL_46:
  CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
LABEL_64:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
  return v28;
}

```

## disassembly

```asm
0x18007ef00  mov     rax, rsp
0x18007ef03  push    rbp
0x18007ef04  push    rdi
0x18007ef05  push    r14
0x18007ef07  lea     rbp, [rax-5Fh]
0x18007ef0b  sub     rsp, 0A0h
0x18007ef12  mov     [rbp+57h+var_18], 0FFFFFFFFFFFFFFFEh
0x18007ef1a  mov     [rax+8], rbx
0x18007ef1e  mov     [rax+18h], rsi
0x18007ef22  mov     rdi, r9
0x18007ef25  mov     rsi, r8
0x18007ef28  mov     rbx, rdx
0x18007ef2b  xor     r14d, r14d
0x18007ef2e  test    rdx, rdx
0x18007ef31  jnz     short loc_18007EF57
0x18007ef33  mov     edx, 154h; void *
0x18007ef38  mov     ebx, 80004003h
0x18007ef3d  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007ef44  mov     r9d, ebx; char *
0x18007ef47  mov     rcx, [rbp+5Fh]; this
0x18007ef4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ef50  mov     eax, ebx
0x18007ef52  jmp     loc_18007F591
0x18007ef57  test    rsi, rsi
0x18007ef5a  jnz     short loc_18007EF63
0x18007ef5c  mov     edx, 155h
0x18007ef61  jmp     short loc_18007EF38
0x18007ef63  mov     [rbp+57h+var_80], r14
0x18007ef67  lea     rcx, [rbp+57h+var_80]
0x18007ef6b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ef70  mov     [rsp+0B0h+var_90], 1; int
0x18007ef78  lea     r9, [rbp+57h+var_80]
0x18007ef7c  xor     r8d, r8d
0x18007ef7f  mov     rdx, rdi
0x18007ef82  mov     rcx, rbx
0x18007ef85  call    ?Create@AppxEncryptedBundleReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEBUAPPX_KEY_INFO@@PEBGPEAPEAUIAppxBundleReader@@W4EncryptionKeyType@Encryption@34@@Z; Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create(IStream *,APPX_KEY_INFO const *,ushort const *,IAppxBundleReader * *,Appx::Packaging::Encryption::EncryptionKeyType)
0x18007ef8a  mov     ebx, eax
0x18007ef8c  mov     rcx, [rbp+5Fh]; this
0x18007ef90  test    eax, eax
0x18007ef92  jns     short loc_18007EFB3
0x18007ef94  mov     edx, 15Bh; void *
0x18007ef99  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007efa0  mov     r9d, ebx; char *
0x18007efa3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007efa8  lea     rcx, [rbp+57h+var_80]
0x18007efac  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007efb1  jmp     short loc_18007EF50
0x18007efb3  mov     [rbp+57h+var_28.lpVtbl], r14
0x18007efb7  lea     rdx, [rbp+57h+var_28]; struct IAppxBundleReader *
0x18007efbb  mov     rcx, [rbp+57h+var_80]; this
0x18007efbf  call    ?GetVersionFromBundle@Packaging@Appx@@YAJPEAUIAppxBundleReader@@PEA_K@Z; Appx::Packaging::GetVersionFromBundle(IAppxBundleReader *,unsigned __int64 *)
0x18007efc4  mov     ebx, eax
0x18007efc6  mov     rcx, [rbp+5Fh]
0x18007efca  test    eax, eax
0x18007efcc  jns     short loc_18007EFD5
0x18007efce  mov     edx, 15Fh
0x18007efd3  jmp     short loc_18007EF99
0x18007efd5  mov     [rbp+57h+var_78], r14
0x18007efd9  mov     rdi, [rbp+57h+var_80]
0x18007efdd  mov     rax, [rdi]
0x18007efe0  mov     rbx, [rax+30h]
0x18007efe4  lea     rcx, [rbp+57h+var_78]
0x18007efe8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007efed  lea     rdx, [rbp+57h+var_78]
0x18007eff1  mov     rcx, rdi
0x18007eff4  mov     rax, rbx
0x18007eff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007effc  mov     ebx, eax
0x18007effe  mov     rcx, [rbp+5Fh]; this
0x18007f002  test    eax, eax
0x18007f004  jns     short loc_18007F025
0x18007f006  mov     r9d, eax; char *
0x18007f009  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f010  mov     edx, 162h; void *
0x18007f015  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f01a  lea     rcx, [rbp+57h+var_78]
0x18007f01e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f023  jmp     short loc_18007EFA8
0x18007f025  mov     [rbp+57h+var_58], r14
0x18007f029  lea     rcx, [rbp+57h+var_58]
0x18007f02d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f032  lea     r8, [rbp+57h+var_58]; struct IAppxBundleWriter **
0x18007f036  mov     rdx, [rbp+57h+var_28.lpVtbl]; unsigned __int64
0x18007f03a  mov     rcx, rsi; struct IStream *
0x18007f03d  call    ?Create@BundlePackageWriter@Production@Packaging@Appx@@SAJPEAUIStream@@_KPEAPEAUIAppxBundleWriter@@@Z; Appx::Packaging::Production::BundlePackageWriter::Create(IStream *,unsigned __int64,IAppxBundleWriter * *)
0x18007f042  mov     ebx, eax
0x18007f044  mov     rcx, [rbp+5Fh]; this
0x18007f048  test    eax, eax
0x18007f04a  jns     short loc_18007F06B
0x18007f04c  mov     r9d, eax; char *
0x18007f04f  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f056  mov     edx, 169h; void *
0x18007f05b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f060  lea     rcx, [rbp+57h+var_58]
0x18007f064  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f069  jmp     short loc_18007F01A
0x18007f06b  mov     [rbp+57h+arg_8], r14d
0x18007f06f  mov     [rbp+57h+var_40], r14
0x18007f073  lea     rcx, [rbp+57h+var_40]
0x18007f077  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f07c  lea     rdx, [rbp+57h+var_40]; struct IAppxMessageHandler *
0x18007f080  xor     ecx, ecx; this
0x18007f082  call    ?CreateOpcFactory@Packaging@Appx@@YAJPEAUIAppxMessageHandler@@PEAPEAUIOpcFactory@@@Z; Appx::Packaging::CreateOpcFactory(IAppxMessageHandler *,IOpcFactory * *)
0x18007f087  mov     ebx, eax
0x18007f089  mov     rcx, [rbp+5Fh]; this
0x18007f08d  test    eax, eax
0x18007f08f  jns     short loc_18007F0B0
0x18007f091  mov     edx, 16Fh; void *
0x18007f096  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f09d  mov     r9d, ebx; char *
0x18007f0a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f0a5  lea     rcx, [rbp+57h+var_40]
0x18007f0a9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f0ae  jmp     short loc_18007F060
0x18007f0b0  mov     rcx, [rbp+57h+var_78]
0x18007f0b4  mov     rax, [rcx]
0x18007f0b7  lea     rdx, [rbp+57h+arg_8]
0x18007f0bb  mov     rax, [rax+20h]
0x18007f0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0c4  mov     ebx, eax
0x18007f0c6  mov     rcx, [rbp+5Fh]
0x18007f0ca  test    eax, eax
0x18007f0cc  jns     short loc_18007F0D5
0x18007f0ce  mov     edx, 171h
0x18007f0d3  jmp     short loc_18007F096
0x18007f0d5  mov     rdi, [rbp+57h+var_58]
0x18007f0d9  cmp     [rbp+57h+arg_8], r14d
0x18007f0dd  jz      loc_18007F434
0x18007f0e3  mov     [rbp+57h+var_50], r14
0x18007f0e7  mov     rsi, [rbp+57h+var_78]
0x18007f0eb  mov     rax, [rsi]
0x18007f0ee  mov     rbx, [rax+18h]
0x18007f0f2  lea     rcx, [rbp+57h+var_50]
0x18007f0f6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f0fb  lea     rdx, [rbp+57h+var_50]
0x18007f0ff  mov     rcx, rsi
0x18007f102  mov     rax, rbx
0x18007f105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f10a  mov     ebx, eax
0x18007f10c  mov     rcx, [rbp+5Fh]; this
0x18007f110  test    eax, eax
0x18007f112  js      loc_18007F412
0x18007f118  mov     [rbp+57h+var_38], r14
0x18007f11c  mov     rbx, [rbp+57h+var_50]
0x18007f120  mov     rax, [rbx]
0x18007f123  mov     rsi, [rax]
0x18007f126  lea     rcx, [rbp+57h+var_38]
0x18007f12a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f12f  lea     r8, [rbp+57h+var_38]
0x18007f133  lea     rdx, _GUID_c2cb2364_4fa9_4878_8c9c_7e2afb98b6d2
0x18007f13a  mov     rcx, rbx
0x18007f13d  mov     rax, rsi
0x18007f140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f145  mov     ebx, eax
0x18007f147  mov     rcx, [rbp+5Fh]; this
0x18007f14b  test    eax, eax
0x18007f14d  js      loc_18007F3F3
0x18007f153  mov     [rbp+57h+pv], r14
0x18007f157  mov     rcx, [rbp+57h+var_50]
0x18007f15b  mov     rax, [rcx]
0x18007f15e  lea     rdx, [rbp+57h+pv]
0x18007f162  mov     rax, [rax+28h]
0x18007f166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f16b  mov     esi, eax
0x18007f16d  mov     rcx, [rbp+5Fh]; this
0x18007f171  test    eax, eax
0x18007f173  js      loc_18007F3B8
0x18007f179  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007f180  mov     ecx, 0FFFEh; unsigned __int64
0x18007f185  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007f18a  mov     rbx, rax
0x18007f18d  test    rax, rax
0x18007f190  jz      loc_18007F390
0x18007f196  mov     rdx, rax; lpBuffer
0x18007f199  mov     ecx, 7FFFh; nBufferLength
0x18007f19e  call    ?GetTempPath2W@DownlevelPortability@Packaging@Appx@@YAJKPEAG@Z; Appx::Packaging::DownlevelPortability::GetTempPath2W(ulong,ushort *)
0x18007f1a3  mov     esi, eax
0x18007f1a5  mov     rcx, [rbp+5Fh]; this
0x18007f1a9  test    eax, eax
0x18007f1ab  js      loc_18007F370
0x18007f1b1  mov     [rbp+57h+var_70], r14
0x18007f1b5  lea     rcx, [rbp+57h+var_70]
0x18007f1b9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f1be  lea     r8, [rbp+57h+var_70]; unsigned __int16 *
0x18007f1c2  lea     rdx, ?TempFilePrefix@Bundle@Packaging@Appx@@3QBGB; "AXB"
0x18007f1c9  mov     rcx, rbx; this
0x18007f1cc  call    ?CreateTempFileStream@Packaging@Appx@@YAJPEBG0PEAPEAUIStream@@@Z; Appx::Packaging::CreateTempFileStream(ushort const *,ushort const *,IStream * *)
0x18007f1d1  mov     esi, eax
0x18007f1d3  mov     rcx, [rbp+5Fh]; this
0x18007f1d7  test    eax, eax
0x18007f1d9  js      loc_18007F347
0x18007f1df  xor     r8d, r8d; struct IStream *
0x18007f1e2  mov     rdx, [rbp+57h+var_70]; struct IAppxEncryptedPackageFile *
0x18007f1e6  mov     rcx, [rbp+57h+var_38]; this
0x18007f1ea  call    ?DecryptPayloadPackage@Packaging@Appx@@YAJPEAUIAppxEncryptedPackageFile@@PEAUIStream@@PEAUIAppxMessageHandler@@@Z; Appx::Packaging::DecryptPayloadPackage(IAppxEncryptedPackageFile *,IStream *,IAppxMessageHandler *)
0x18007f1ef  mov     esi, eax
0x18007f1f1  mov     rcx, [rbp+5Fh]; this
0x18007f1f5  test    eax, eax
0x18007f1f7  js      loc_18007F31B
0x18007f1fd  mov     [rbp+57h+var_20], r14
0x18007f201  mov     rcx, [rbp+57h+var_70]
0x18007f205  mov     rax, [rcx]
0x18007f208  xor     r9d, r9d
0x18007f20b  xor     r8d, r8d
0x18007f20e  mov     rdx, r14
0x18007f211  mov     rax, [rax+28h]
0x18007f215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f21a  mov     esi, eax
0x18007f21c  mov     rcx, [rbp+5Fh]; this
0x18007f220  test    eax, eax
0x18007f222  js      loc_18007F2EF
0x18007f228  mov     rax, [rdi]
0x18007f22b  mov     r8, [rbp+57h+var_70]
0x18007f22f  mov     rdx, [rbp+57h+pv]
0x18007f233  mov     rcx, rdi
0x18007f236  mov     rax, [rax+18h]
0x18007f23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f23f  mov     esi, eax
0x18007f241  mov     rcx, [rbp+5Fh]; this
0x18007f245  test    eax, eax
0x18007f247  js      short loc_18007F2C3
0x18007f249  lea     rcx, [rbp+57h+var_70]
0x18007f24d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f252  mov     rcx, [rbp+57h+var_78]
0x18007f256  mov     rax, [rcx]
0x18007f259  lea     rdx, [rbp+57h+arg_8]
0x18007f25d  mov     rax, [rax+28h]
0x18007f261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f266  mov     esi, eax
0x18007f268  mov     rcx, [rbp+5Fh]; this
0x18007f26c  test    eax, eax
0x18007f26e  js      short loc_18007F2A0
0x18007f270  mov     rcx, rbx; void *
0x18007f273  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f278  nop
0x18007f279  mov     rcx, [rbp+57h+pv]; pv
0x18007f27d  call    cs:__imp_CoTaskMemFree
0x18007f284  nop     dword ptr [rax+rax+00h]
0x18007f289  lea     rcx, [rbp+57h+var_38]
0x18007f28d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f292  lea     rcx, [rbp+57h+var_50]
0x18007f296  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f29b  jmp     loc_18007F0D9
0x18007f2a0  mov     r9d, eax; char *
0x18007f2a3  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f2aa  mov     edx, 190h; void *
0x18007f2af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f2b4  nop
0x18007f2b5  mov     rcx, rbx; void *
0x18007f2b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f2bd  nop
0x18007f2be  jmp     loc_18007F3CC
0x18007f2c3  mov     r9d, eax; char *
0x18007f2c6  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f2cd  mov     edx, 18Dh; void *
0x18007f2d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f2d7  lea     rcx, [rbp+57h+var_70]
0x18007f2db  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f2e0  nop
0x18007f2e1  mov     rcx, rbx; void *
0x18007f2e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f2e9  nop
0x18007f2ea  jmp     loc_18007F3CC
0x18007f2ef  mov     r9d, eax; char *
0x18007f2f2  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f2f9  mov     edx, 18Bh; void *
0x18007f2fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f303  lea     rcx, [rbp+57h+var_70]
0x18007f307  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f30c  nop
0x18007f30d  mov     rcx, rbx; void *
0x18007f310  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f315  nop
0x18007f316  jmp     loc_18007F3CC
0x18007f31b  mov     r9d, eax; char *
0x18007f31e  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f325  mov     edx, 187h; void *
0x18007f32a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f32f  lea     rcx, [rbp+57h+var_70]
0x18007f333  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f338  nop
0x18007f339  mov     rcx, rbx; void *
0x18007f33c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f341  nop
0x18007f342  jmp     loc_18007F3CC
0x18007f347  mov     r9d, eax; char *
0x18007f34a  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f351  mov     edx, 185h; void *
0x18007f356  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f35b  lea     rcx, [rbp+57h+var_70]
0x18007f35f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007f364  nop
0x18007f365  mov     rcx, rbx; void *
0x18007f368  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007f36d  nop
0x18007f36e  jmp     short loc_18007F3CC
0x18007f370  mov     r9d, eax; char *
0x18007f373  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18007f37a  mov     edx, 181h; void *
0x18007f37f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
  ... truncated ...
```
