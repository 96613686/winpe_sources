# Appx::Packaging::AppxEncryptionFactoryImpl::EncryptBundle(IStream *,IStream *,APPX_ENCRYPTED_PACKAGE_SETTINGS2 const *,APPX_KEY_INFO const *,APPX_ENCRYPTED_EXEMPTIONS const *)

- ea: `0x180082cb0`
- end: `0x180083286`
- name: `?EncryptBundle@AppxEncryptionFactoryImpl@Packaging@Appx@@UEAAJPEAUIStream@@0PEBUAPPX_ENCRYPTED_PACKAGE_SETTINGS2@@PEBUAPPX_KEY_INFO@@PEBUAPPX_ENCRYPTED_EXEMPTIONS@@@Z`
- size: `1494`
- prototype: `__int64 __fastcall(Appx::Packaging::AppxEncryptionFactoryImpl *__hidden this, struct IStream *, struct IStream *, const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *, const struct APPX_KEY_INFO *, const struct APPX_ENCRYPTED_EXEMPTIONS *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180071f50`
- `0x180082690`
- `0x180082cb0`
- `0x18008328c`
- `0x180083588`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083098`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180082e85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180082e85`

## string_xrefs

- `0x1800831cc`: `*CopyOptionalBundles`
- `0x180082ce6`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180082d32`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180082d73`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180082dc3`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180082e19`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180082ea0`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180082f56`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180083085`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x1800830cd`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x1800830e7`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x180083137`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x1800831b7`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`
- `0x18008320a`: `onecore\printscan\appxpackaging\dll\lib\appxencryptionfactory.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppxEncryptionFactoryImpl::EncryptBundle(
        Appx::Packaging::AppxEncryptionFactoryImpl *this,
        struct IStream *a2,
        struct IStream *a3,
        const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *a4,
        const struct APPX_KEY_INFO *a5)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  int v11; // esi
  int valid; // eax
  int v13; // eax
  struct IAppxBundleReader *v14; // rbx
  HRESULT (__stdcall *QueryInterface)(IAppxBundleReader *, const IID *const, void **); // rdi
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  HRESULT VersionFromBundle; // eax
  unsigned __int64 *v23; // r8
  __int64 v24; // rdx
  __int64 (__fastcall *v25)(Appx::Packaging::AppxEncryptionFactoryImpl *, struct IStream *, struct IAppxBundleReaderVtbl *, const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *); // rbx
  struct IAppxBundleReader *v26; // rdi
  HRESULT (__stdcall *GetPayloadPackages)(IAppxBundleReader *, IAppxFilesEnumerator **); // rbx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64 *); // rbx
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64 **); // rbx
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  struct IAppxBundleReader *v38; // rdi
  HRESULT (__stdcall *GetManifest)(IAppxBundleReader *, IAppxBundleManifestReader **); // rbx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, __int64 *); // rbx
  __int64 (__fastcall ***v44)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v45)(_QWORD, GUID *, __int64 *); // rdi
  int v46; // eax
  __int64 v47; // rdx
  int v48; // eax
  int ppv; // [rsp+20h] [rbp-89h]
  int ppva; // [rsp+20h] [rbp-89h]
  __int64 v52; // [rsp+40h] [rbp-69h] BYREF
  __int64 v53; // [rsp+48h] [rbp-61h] BYREF
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-59h] BYREF
  __int64 v55; // [rsp+58h] [rbp-51h] BYREF
  LPVOID v56; // [rsp+60h] [rbp-49h] BYREF
  __int64 v57; // [rsp+68h] [rbp-41h] BYREF
  __int64 v58; // [rsp+70h] [rbp-39h] BYREF
  __int64 v59; // [rsp+78h] [rbp-31h] BYREF
  __int64 *v60; // [rsp+80h] [rbp-29h] BYREF
  __int64 v61; // [rsp+88h] [rbp-21h] BYREF
  struct IAppxBundleReader *v62; // [rsp+90h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-11h] BYREF
  int v64; // [rsp+A0h] [rbp-9h] BYREF
  struct IAppxBundleReader v65; // [rsp+A8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]
  int v67; // [rsp+108h] [rbp+5Fh] BYREF

  if ( a2 )
  {
    if ( !a3 )
    {
      v9 = 254;
      goto LABEL_3;
    }
    if ( !a4 )
    {
      v9 = 255;
      goto LABEL_3;
    }
    v11 = (int)a5;
    if ( a5 )
    {
      valid = Appx::Packaging::EncryptionHelper::ValidAppxKeyInfo(a5);
      v10 = valid;
      if ( valid < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
          (const char *)(unsigned int)valid,
          ppv);
        return v10;
      }
    }
    v62 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
    v13 = Appx::Packaging::Consumption::BundlePackageReader::Create(a2, 1, 0, &v62);
    v10 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v13,
        ppv);
LABEL_68:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      return v10;
    }
    v14 = v62;
    v52 = 0;
    QueryInterface = v62->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
    v16 = ((__int64 (__fastcall *)(struct IAppxBundleReader *, GUID *, __int64 *))QueryInterface)(
            v14,
            &GUID_7b15dcbd_0419_4b53_8c9a_09d3edc73cf5,
            &v52);
    v10 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v16,
        ppv);
LABEL_67:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
      goto LABEL_68;
    }
    v17 = v52;
    v53 = 0;
    v64 = 0;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 32LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
    v19 = v18(v17, &v53);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 268;
LABEL_17:
      v21 = (unsigned int)v19;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)v21,
        ppv);
LABEL_66:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v53);
      goto LABEL_67;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v53 + 32LL))(v53, &v64);
    v10 = v19;
    if ( v19 < 0 )
    {
      v20 = 269;
      goto LABEL_17;
    }
    if ( v64 )
    {
      v10 = -2147024846;
      v20 = 270;
      v21 = 2147942450LL;
      goto LABEL_18;
    }
    v54 = 0;
    v56 = 0;
    VersionFromBundle = CoCreateInstance(
                          &GUID_dc664fdd_d868_46ee_8780_8d196cb739f7,
                          0,
                          1u,
                          &GUID_80e8e04d_8c88_44ae_a011_7cadf6fb2e72,
                          &v56);
    v10 = VersionFromBundle;
    if ( VersionFromBundle < 0 )
    {
      v24 = 280;
LABEL_25:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)VersionFromBundle,
        ppva);
LABEL_65:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
      goto LABEL_66;
    }
    v65.lpVtbl = 0;
    VersionFromBundle = Appx::Packaging::GetVersionFromBundle((Appx::Packaging *)v62, &v65, v23);
    v10 = VersionFromBundle;
    if ( VersionFromBundle < 0 )
    {
      v24 = 284;
      goto LABEL_25;
    }
    v25 = *(__int64 (__fastcall **)(Appx::Packaging::AppxEncryptionFactoryImpl *, struct IStream *, struct IAppxBundleReaderVtbl *, const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *))(*(_QWORD *)this + 48LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
    ppva = v11;
    VersionFromBundle = v25(this, a3, v65.lpVtbl, a4);
    v10 = VersionFromBundle;
    if ( VersionFromBundle < 0 )
    {
      v24 = 291;
      goto LABEL_25;
    }
    v26 = v62;
    v55 = 0;
    v67 = 0;
    GetPayloadPackages = v62->lpVtbl->GetPayloadPackages;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
    v28 = ((__int64 (__fastcall *)(struct IAppxBundleReader *, __int64 *))GetPayloadPackages)(v26, &v55);
    v10 = v28;
    if ( v28 < 0 )
    {
      v29 = 296;
LABEL_32:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v28,
        v11);
LABEL_64:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v55);
      goto LABEL_65;
    }
    v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 32LL))(v55, &v67);
    v10 = v28;
    if ( v28 < 0 )
    {
      v29 = 297;
      goto LABEL_32;
    }
    while ( v67 )
    {
      v30 = v55;
      v57 = 0;
      v31 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 24LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
      v32 = v31(v30, &v57);
      v10 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x12E,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
          (const char *)(unsigned int)v32,
          v11);
        goto LABEL_45;
      }
      v33 = v57;
      v60 = 0;
      v34 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v57 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
      v35 = v34(v33, &v60);
      v10 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x130,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
          (const char *)(unsigned int)v35,
          v11);
        goto LABEL_44;
      }
      pv = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v57 + 40LL))(v57, &pv);
      v10 = v36;
      if ( v36 < 0 )
      {
        v37 = 306;
LABEL_43:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
          (const char *)(unsigned int)v36,
          v11);
        CoTaskMemFree(pv);
LABEL_44:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
LABEL_45:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
        goto LABEL_64;
      }
      v36 = (*v54)[3](v54, (GUID *)pv, v60);
      v10 = v36;
      if ( v36 < 0 )
      {
        v37 = 308;
        goto LABEL_43;
      }
      v36 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 40LL))(v55, &v67);
      v10 = v36;
      if ( v36 < 0 )
      {
        v37 = 310;
        goto LABEL_43;
      }
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
    }
    v38 = v62;
    v59 = 0;
    v58 = 0;
    GetManifest = v62->lpVtbl->GetManifest;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v59);
    v40 = ((__int64 (__fastcall *)(struct IAppxBundleReader *, __int64 *))GetManifest)(v38, &v59);
    v10 = v40;
    if ( v40 < 0 )
    {
      v41 = 316;
LABEL_52:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
        (const char *)(unsigned int)v40,
        v11);
LABEL_63:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v59);
      goto LABEL_64;
    }
    v42 = v59;
    v43 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 40LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
    v40 = v43(v42, &v58);
    v10 = v40;
    if ( v40 < 0 )
    {
      v41 = 317;
      goto LABEL_52;
    }
    v44 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v54;
    v61 = 0;
    v45 = **v54;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
    v46 = v45(v44, &GUID_e644be82_f0fa_42b8_a956_8d1cb48ee379, &v61);
    v10 = v46;
    if ( v46 >= 0 )
    {
      v46 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v61 + 24LL))(
              v61,
              L"*CopyOptionalBundles",
              v58);
      v10 = v46;
      if ( v46 >= 0 )
      {
        v48 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v54)[4])(v54);
        v10 = v48;
        if ( v48 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x143,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
            (const char *)(unsigned int)v48,
            v11);
        goto LABEL_62;
      }
      v47 = 320;
    }
    else
    {
      v47 = 319;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
      (const char *)(unsigned int)v46,
      v11);
LABEL_62:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
    goto LABEL_63;
  }
  v9 = 253;
LABEL_3:
  v10 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxencryptionfactory.cpp",
    (const char *)0x80004003LL,
    ppv);
  return v10;
}

```

## disassembly

```asm
0x180082cb0  push    rbp
0x180082cb2  push    rbx
0x180082cb3  push    rsi
0x180082cb4  push    rdi
0x180082cb5  push    r12
0x180082cb7  push    r13
0x180082cb9  push    r14
0x180082cbb  push    r15
0x180082cbd  lea     rbp, [rsp-0Fh]
0x180082cc2  sub     rsp, 0B8h
0x180082cc9  xor     r13d, r13d
0x180082ccc  mov     r14, r9
0x180082ccf  mov     r15, r8
0x180082cd2  mov     rdi, rdx
0x180082cd5  mov     r12, rcx
0x180082cd8  test    rdx, rdx
0x180082cdb  jnz     short loc_180082CFF
0x180082cdd  mov     edx, 0FDh; void *
0x180082ce2  mov     rcx, [rbp+4Fh]; this
0x180082ce6  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x180082ced  mov     ebx, 80004003h
0x180082cf2  mov     r9d, ebx; char *
0x180082cf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082cfa  jmp     loc_18008326F
0x180082cff  test    r15, r15
0x180082d02  jnz     short loc_180082D0B
0x180082d04  mov     edx, 0FEh
0x180082d09  jmp     short loc_180082CE2
0x180082d0b  test    r14, r14
0x180082d0e  jnz     short loc_180082D17
0x180082d10  mov     edx, 0FFh
0x180082d15  jmp     short loc_180082CE2
0x180082d17  mov     rsi, [rbp+47h+arg_20]
0x180082d1b  test    rsi, rsi
0x180082d1e  jz      short loc_180082D4B
0x180082d20  mov     rcx, rsi; struct APPX_KEY_INFO *
0x180082d23  call    ?ValidAppxKeyInfo@EncryptionHelper@Packaging@Appx@@SAJAEBUAPPX_KEY_INFO@@@Z; Appx::Packaging::EncryptionHelper::ValidAppxKeyInfo(APPX_KEY_INFO const &)
0x180082d28  mov     ebx, eax
0x180082d2a  test    eax, eax
0x180082d2c  jns     short loc_180082D4B
0x180082d2e  mov     rcx, [rbp+4Fh]; this
0x180082d32  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x180082d39  mov     r9d, eax; char *
0x180082d3c  mov     edx, 101h; void *
0x180082d41  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082d46  jmp     loc_18008326F
0x180082d4b  lea     rcx, [rbp+47h+var_60]
0x180082d4f  mov     [rbp+47h+var_60], r13
0x180082d53  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180082d58  lea     r9, [rbp+47h+var_60]; struct IAppxBundleReader **
0x180082d5c  xor     r8d, r8d; unsigned __int16 *
0x180082d5f  mov     dl, 1; bool
0x180082d61  mov     rcx, rdi; struct IStream *
0x180082d64  call    ?Create@BundlePackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAUIAppxBundleReader@@@Z; Appx::Packaging::Consumption::BundlePackageReader::Create(IStream *,bool,ushort const *,IAppxBundleReader * *)
0x180082d69  mov     ebx, eax
0x180082d6b  test    eax, eax
0x180082d6d  jns     short loc_180082D8C
0x180082d6f  mov     rcx, [rbp+4Fh]; this
0x180082d73  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x180082d7a  mov     r9d, eax; char *
0x180082d7d  mov     edx, 105h; void *
0x180082d82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082d87  jmp     loc_180083266
0x180082d8c  mov     rbx, [rbp+47h+var_60]
0x180082d90  lea     rcx, [rbp+47h+var_B0]
0x180082d94  mov     [rbp+47h+var_B0], r13
0x180082d98  mov     rax, [rbx]
0x180082d9b  mov     rdi, [rax]
0x180082d9e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180082da3  lea     r8, [rbp+47h+var_B0]
0x180082da7  mov     rcx, rbx
0x180082daa  lea     rdx, _GUID_7b15dcbd_0419_4b53_8c9a_09d3edc73cf5
0x180082db1  mov     rax, rdi
0x180082db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082db9  mov     ebx, eax
0x180082dbb  test    eax, eax
0x180082dbd  jns     short loc_180082DDC
0x180082dbf  mov     rcx, [rbp+4Fh]; this
0x180082dc3  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x180082dca  mov     r9d, eax; char *
0x180082dcd  mov     edx, 109h; void *
0x180082dd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082dd7  jmp     loc_18008325D
0x180082ddc  mov     rdi, [rbp+47h+var_B0]
0x180082de0  lea     rcx, [rbp+47h+var_A8]
0x180082de4  mov     [rbp+47h+var_A8], r13
0x180082de8  mov     [rbp+47h+var_50], r13d
0x180082dec  mov     rax, [rdi]
0x180082def  mov     rbx, [rax+20h]
0x180082df3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180082df8  lea     rdx, [rbp+47h+var_A8]
0x180082dfc  mov     rcx, rdi
0x180082dff  mov     rax, rbx
0x180082e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e07  mov     ebx, eax
0x180082e09  test    eax, eax
0x180082e0b  jns     short loc_180082E2A
0x180082e0d  mov     edx, 10Ch; void *
0x180082e12  mov     r9d, eax; char *
0x180082e15  mov     rcx, [rbp+4Fh]; this
0x180082e19  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x180082e20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082e25  jmp     loc_180083254
0x180082e2a  mov     rcx, [rbp+47h+var_A8]
0x180082e2e  lea     rdx, [rbp+47h+var_50]
0x180082e32  mov     rax, [rcx]
0x180082e35  mov     rax, [rax+20h]
0x180082e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e3e  mov     ebx, eax
0x180082e40  test    eax, eax
0x180082e42  jns     short loc_180082E4B
0x180082e44  mov     edx, 10Dh
0x180082e49  jmp     short loc_180082E12
0x180082e4b  cmp     [rbp+47h+var_50], r13d
0x180082e4f  jz      short loc_180082E60
0x180082e51  mov     ebx, 80070032h
0x180082e56  mov     edx, 10Eh
0x180082e5b  mov     r9d, ebx
0x180082e5e  jmp     short loc_180082E15
0x180082e60  xor     edx, edx; pUnkOuter
0x180082e62  mov     [rbp+47h+var_A0], r13
0x180082e66  lea     rax, [rbp+47h+var_90]
0x180082e6a  mov     [rbp+47h+var_90], r13
0x180082e6e  lea     r9, _GUID_80e8e04d_8c88_44ae_a011_7cadf6fb2e72; riid
0x180082e75  mov     [rsp+0F0h+ppv], rax; int
0x180082e7a  lea     rcx, _GUID_dc664fdd_d868_46ee_8780_8d196cb739f7; rclsid
0x180082e81  lea     r8d, [rdx+1]; dwClsContext
0x180082e85  call    cs:__imp_CoCreateInstance
0x180082e8c  nop     dword ptr [rax+rax+00h]
0x180082e91  mov     ebx, eax
0x180082e93  test    eax, eax
0x180082e95  jns     short loc_180082EB4
0x180082e97  mov     edx, 118h; void *
0x180082e9c  mov     rcx, [rbp+4Fh]; this
0x180082ea0  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x180082ea7  mov     r9d, eax; char *
0x180082eaa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082eaf  jmp     loc_180083242
0x180082eb4  mov     rcx, [rbp+47h+var_60]; this
0x180082eb8  lea     rdx, [rbp+47h+var_48]; struct IAppxBundleReader *
0x180082ebc  mov     [rbp+47h+var_48.lpVtbl], r13
0x180082ec0  call    ?GetVersionFromBundle@Packaging@Appx@@YAJPEAUIAppxBundleReader@@PEA_K@Z; Appx::Packaging::GetVersionFromBundle(IAppxBundleReader *,unsigned __int64 *)
0x180082ec5  mov     ebx, eax
0x180082ec7  test    eax, eax
0x180082ec9  jns     short loc_180082ED2
0x180082ecb  mov     edx, 11Ch
0x180082ed0  jmp     short loc_180082E9C
0x180082ed2  mov     rax, [r12]
0x180082ed6  lea     rcx, [rbp+47h+var_A0]
0x180082eda  mov     rbx, [rax+30h]
0x180082ede  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180082ee3  mov     rcx, [rbp+47h+arg_28]
0x180082ee7  lea     rax, [rbp+47h+var_A0]
0x180082eeb  mov     r8, [rbp+47h+var_48.lpVtbl]
0x180082eef  mov     r9, r14
0x180082ef2  mov     [rsp+0F0h+var_C0], rax
0x180082ef7  mov     rdx, r15
0x180082efa  mov     [rsp+0F0h+var_C8], rcx
0x180082eff  mov     rax, rbx
0x180082f02  mov     rcx, r12
0x180082f05  mov     [rsp+0F0h+ppv], rsi; int
0x180082f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f0f  mov     ebx, eax
0x180082f11  test    eax, eax
0x180082f13  jns     short loc_180082F1C
0x180082f15  mov     edx, 123h
0x180082f1a  jmp     short loc_180082E9C
0x180082f1c  mov     rdi, [rbp+47h+var_60]
0x180082f20  lea     rcx, [rbp+47h+var_98]
0x180082f24  mov     [rbp+47h+var_98], r13
0x180082f28  mov     [rbp+47h+arg_8], r13d
0x180082f2c  mov     rax, [rdi]
0x180082f2f  mov     rbx, [rax+30h]
0x180082f33  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180082f38  lea     rdx, [rbp+47h+var_98]
0x180082f3c  mov     rcx, rdi
0x180082f3f  mov     rax, rbx
0x180082f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f47  mov     ebx, eax
0x180082f49  test    eax, eax
0x180082f4b  jns     short loc_180082F6A
0x180082f4d  mov     edx, 128h; void *
0x180082f52  mov     rcx, [rbp+4Fh]; this
0x180082f56  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x180082f5d  mov     r9d, eax; char *
0x180082f60  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082f65  jmp     loc_180083239
0x180082f6a  mov     rcx, [rbp+47h+var_98]
0x180082f6e  lea     rdx, [rbp+47h+arg_8]
0x180082f72  mov     rax, [rcx]
0x180082f75  mov     rax, [rax+20h]
0x180082f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f7e  mov     ebx, eax
0x180082f80  test    eax, eax
0x180082f82  jns     short loc_180082F8B
0x180082f84  mov     edx, 129h
0x180082f89  jmp     short loc_180082F52
0x180082f8b  cmp     [rbp+47h+arg_8], r13d
0x180082f8f  jz      loc_1800830FD
0x180082f95  mov     rdi, [rbp+47h+var_98]
0x180082f99  lea     rcx, [rbp+47h+var_88]
0x180082f9d  mov     [rbp+47h+var_88], r13
0x180082fa1  mov     rax, [rdi]
0x180082fa4  mov     rbx, [rax+18h]
0x180082fa8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180082fad  lea     rdx, [rbp+47h+var_88]
0x180082fb1  mov     rcx, rdi
0x180082fb4  mov     rax, rbx
0x180082fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082fbc  mov     ebx, eax
0x180082fbe  test    eax, eax
0x180082fc0  js      loc_1800830E3
0x180082fc6  mov     rdi, [rbp+47h+var_88]
0x180082fca  lea     rcx, [rbp+47h+var_70]
0x180082fce  mov     [rbp+47h+var_70], r13
0x180082fd2  mov     rax, [rdi]
0x180082fd5  mov     rbx, [rax+38h]
0x180082fd9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180082fde  lea     rdx, [rbp+47h+var_70]
0x180082fe2  mov     rcx, rdi
0x180082fe5  mov     rax, rbx
0x180082fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082fed  mov     ebx, eax
0x180082fef  test    eax, eax
0x180082ff1  js      loc_1800830C9
0x180082ff7  mov     rcx, [rbp+47h+var_88]
0x180082ffb  lea     rdx, [rbp+47h+pv]
0x180082fff  mov     [rbp+47h+pv], r13
0x180083003  mov     rax, [rcx]
0x180083006  mov     rax, [rax+28h]
0x18008300a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008300f  mov     ebx, eax
0x180083011  test    eax, eax
0x180083013  js      loc_1800830C2
0x180083019  mov     rcx, [rbp+47h+var_A0]
0x18008301d  mov     r8, [rbp+47h+var_70]
0x180083021  mov     rdx, [rbp+47h+pv]
0x180083025  mov     rax, [rcx]
0x180083028  mov     rax, [rax+18h]
0x18008302c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083031  mov     ebx, eax
0x180083033  test    eax, eax
0x180083035  js      loc_1800830BB
0x18008303b  mov     rcx, [rbp+47h+var_98]
0x18008303f  lea     rdx, [rbp+47h+arg_8]
0x180083043  mov     rax, [rcx]
0x180083046  mov     rax, [rax+28h]
0x18008304a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008304f  mov     ebx, eax
0x180083051  test    eax, eax
0x180083053  js      short loc_18008307C
0x180083055  mov     rcx, [rbp+47h+pv]; pv
0x180083059  call    cs:__imp_CoTaskMemFree
0x180083060  nop     dword ptr [rax+rax+00h]
0x180083065  lea     rcx, [rbp+47h+var_70]
0x180083069  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008306e  lea     rcx, [rbp+47h+var_88]
0x180083072  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180083077  jmp     loc_180082F8B
0x18008307c  mov     edx, 136h; void *
0x180083081  mov     rcx, [rbp+4Fh]; this
0x180083085  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x18008308c  mov     r9d, eax; char *
0x18008308f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083094  mov     rcx, [rbp+47h+pv]; pv
0x180083098  call    cs:__imp_CoTaskMemFree
0x18008309f  nop     dword ptr [rax+rax+00h]
0x1800830a4  lea     rcx, [rbp+47h+var_70]
0x1800830a8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800830ad  lea     rcx, [rbp+47h+var_88]
0x1800830b1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800830b6  jmp     loc_180083239
0x1800830bb  mov     edx, 134h
0x1800830c0  jmp     short loc_180083081
0x1800830c2  mov     edx, 132h
0x1800830c7  jmp     short loc_180083081
0x1800830c9  mov     rcx, [rbp+4Fh]; this
0x1800830cd  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x1800830d4  mov     r9d, eax; char *
0x1800830d7  mov     edx, 130h; void *
0x1800830dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800830e1  jmp     short loc_1800830A4
0x1800830e3  mov     rcx, [rbp+4Fh]; this
0x1800830e7  lea     r8, aOnecorePrintsc_189; "onecore\\printscan\\appxpackaging\\dll"...
0x1800830ee  mov     r9d, eax; char *
0x1800830f1  mov     edx, 12Eh; void *
0x1800830f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800830fb  jmp     short loc_1800830AD
0x1800830fd  mov     rdi, [rbp+47h+var_60]
0x180083101  lea     rcx, [rbp+47h+var_78]
0x180083105  mov     [rbp+47h+var_78], r13
0x180083109  mov     [rbp+47h+var_80], r13
0x18008310d  mov     rax, [rdi]
0x180083110  mov     rbx, [rax+28h]
0x180083114  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180083119  lea     rdx, [rbp+47h+var_78]
0x18008311d  mov     rcx, rdi
0x180083120  mov     rax, rbx
0x180083123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083128  mov     ebx, eax
  ... truncated ...
```
