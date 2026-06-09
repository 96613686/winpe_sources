# CUserTileStore::_SetImagesOnUserManagerAndCache(IStream *,IStream *,IStream *,IStream *,ushort const *)

- ea: `0x1800392fc`
- end: `0x180039ba7`
- name: `?_SetImagesOnUserManagerAndCache@CUserTileStore@@AEAAJPEAUIStream@@000PEBG@Z`
- size: `2219`
- prototype: `int(CUserTileStore *__hidden this, struct IStream *, struct IStream *, struct IStream *, struct IStream *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180039164`

## callees

- `0x18000bd60`
- `0x1800140e0`
- `0x180021d80`
- `0x18002a974`
- `0x18002be34`
- `0x180034db4`
- `0x180039140`
- `0x1800392fc`
- `0x180039bb0`
- `0x18003a070`
- `0x18003a47c`
- `0x18003a51c`
- `0x1800485b8`
- `0x180049544`
- `0x18004f0c4`
- `0x180050ba0`
- `0x1800aa9f0`
- `0x1800c4cf8`
- `0x1800c5e3c`
- `0x1800d36a4`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800397b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800397b5`
- `ntdll!WinSqmSetDWORD` at `0x180039a88`
- `ntdll!WinSqmSetDWORD` at `0x180039a88`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800399cf`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x1800399cf`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1800396dc`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x1800396dc`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x1800399ea`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x1800399ea`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180039391`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180039391`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x180039aec`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x180039aec`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180039428`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180039428`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800393e6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800393e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800395bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800395bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CUserTileStore::_SetImagesOnUserManagerAndCache(
        CUserTileStore *this,
        struct IStream *a2,
        struct IStream *a3,
        struct IStream *a4,
        struct IStream *a5,
        unsigned __int16 *a6)
{
  char *v10; // r14
  LPOLESTR *v11; // rdi
  unsigned int v12; // ebx
  HRESULT v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  _QWORD **v18; // rax
  _QWORD *v19; // rbx
  LPVOID v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  struct IStream *v23; // rcx
  HRESULT v24; // eax
  __int64 v25; // rcx
  LPVOID v26; // rbx
  __int64 (__fastcall *v27)(LPVOID, _QWORD, _QWORD, struct IStream *); // r14
  struct IStream *v28; // rdx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  const WCHAR *v33; // rbx
  unsigned __int64 v34; // rcx
  signed int v35; // eax
  unsigned int v36; // eax
  __int64 v37; // r8
  __int64 *v38; // rax
  __int64 v39; // rbx
  LPVOID v40; // rcx
  int v41; // eax
  int v42; // eax
  int v43; // eax
  void *v44; // rdx
  unsigned int v45; // r8d
  __int64 (*v46)(void); // rbx
  const char *v47; // r9
  __int64 (*v48)(void); // rax
  int v49; // eax
  struct IStream *v50; // rcx
  unsigned int v51; // edx
  HRESULT TilePath; // eax
  int v53; // eax
  int *ppv; // [rsp+20h] [rbp-148h]
  int ppva; // [rsp+20h] [rbp-148h]
  int ppvb; // [rsp+20h] [rbp-148h]
  int ppvc; // [rsp+20h] [rbp-148h]
  char v58[8]; // [rsp+40h] [rbp-128h] BYREF
  unsigned int v59[2]; // [rsp+48h] [rbp-120h] BYREF
  LPVOID v60; // [rsp+50h] [rbp-118h] BYREF
  int v61[2]; // [rsp+58h] [rbp-110h] BYREF
  __int64 v62; // [rsp+60h] [rbp-108h] BYREF
  struct IStream *v63; // [rsp+68h] [rbp-100h] BYREF
  char *v64; // [rsp+70h] [rbp-F8h] BYREF
  LPWSTR v65; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v66; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v67; // [rsp+88h] [rbp-E0h] BYREF
  __int64 v68; // [rsp+90h] [rbp-D8h] BYREF
  LPWSTR v69; // [rsp+98h] [rbp-D0h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-C0h] BYREF
  __int64 v72; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 *v73; // [rsp+B8h] [rbp-B0h] BYREF
  __int64 *v74; // [rsp+C0h] [rbp-A8h] BYREF
  int v75[2]; // [rsp+C8h] [rbp-A0h] BYREF
  _QWORD *v76; // [rsp+D0h] [rbp-98h] BYREF
  unsigned __int16 *v77; // [rsp+D8h] [rbp-90h]
  __int64 *v78; // [rsp+E0h] [rbp-88h]
  char v79; // [rsp+E8h] [rbp-80h]
  GUID pguid; // [rsp+F0h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp-68h] BYREF
  __int64 v82; // [rsp+118h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v77 = a6;
  v10 = (char *)this + 48;
  *((_BYTE *)this + 48) = 0;
  v11 = (LPOLESTR *)((char *)this + 40);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (char *)this + 40,
    0);
  if ( !a2 && !a3 && !a4 )
  {
    v12 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x559,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
    return v12;
  }
  if ( (unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) )
    return 2147500037LL;
  v62 = 0;
  v14 = CoCreateInstanceAsSystem(&CLSID_UserTileBroker, &GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76, &v62);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1372;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v14,
      (int)ppv);
LABEL_68:
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v62);
    return v12;
  }
  pguid = 0;
  v14 = CoCreateGuid(&pguid);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1376;
    goto LABEL_12;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v11,
    0);
  v14 = StringFromCLSID(&pguid, v11);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1377;
    goto LABEL_12;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, LPOLESTR))(*(_QWORD *)v62 + 48LL))(v62, *v11);
  v12 = v14;
  if ( v14 < 0 )
  {
    v15 = 1378;
    goto LABEL_12;
  }
  v78 = &v62;
  v79 = 1;
  try
  {
    wil::GetActivationFactory<Windows::System::IUserStatics>((const WCHAR *)&v74);
    v68 = 0;
    v16 = *v74;
    v68 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 56))(v74, &v68);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x56E,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v17,
        (int)ppv);
    v18 = (_QWORD **)wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(
                       &v60,
                       v68);
    v19 = *v18;
    *v18 = 0;
    v76 = v19;
    v20 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v67 = 0;
    v21 = *v19;
    v67 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(v21 + 48))(v19, 0, &v67);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x572,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v22,
        (int)ppv);
    v23 = a3;
    if ( !a3 )
      v23 = a2;
    v63 = v23;
    if ( v23 )
    {
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v23 + 8LL))(v23);
      v23 = v63;
    }
    if ( !v23 )
    {
      v60 = 0;
      v24 = CoCreateInstance(&CLSID_UserTileValidator, 0, 1u, &GUID_0406e498_0916_49c2_a1c4_10db7bf76766, &v60);
      if ( v24 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x57D,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
          (const char *)(unsigned int)v24,
          ppva);
      v25 = 0;
      *(_QWORD *)v61 = 0;
      *(_QWORD *)v59 = 0;
      v26 = v60;
      v27 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, struct IStream *))(*(_QWORD *)v60 + 24LL);
      *(_QWORD *)v59 = 0;
      v28 = v63;
      v63 = 0;
      if ( v28 )
      {
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v28 + 16LL))(v28);
        v25 = *(_QWORD *)v61;
      }
      *(_QWORD *)v61 = 0;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      ppv = v61;
      v29 = v27(v26, 0, 0, a4);
      if ( v29 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x57F,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
          (const char *)(unsigned int)v29,
          (int)v61);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v59);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(v61);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v60);
      v23 = v63;
      v10 = (char *)this + 48;
    }
    v70 = 0;
    v30 = CreateRandomAccessStreamOverStream(v23, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v70);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x584,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v30,
        (int)ppv);
    wil::GetActivationFactory<Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>((const WCHAR *)&v73);
    v66 = 0;
    v31 = *v73;
    v66 = 0;
    v32 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v31 + 64))(v73, v70, &v66);
    if ( v32 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x587,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v32,
        (int)ppv);
    v61[0] = *((_DWORD *)this + 8);
    wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics6>((const WCHAR *)&v72);
    v33 = *v11;
    v82 = 0;
    v59[0] = 0;
    v34 = -1;
    do
      ++v34;
    while ( v33[v34] );
    v35 = ULongLongToUInt(v34, v59);
    if ( v35 < 0 )
    {
      RaiseException(v35, 1u, 0, 0);
      __debugbreak();
    }
    v36 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v59[0]);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v33, v36, v59[0]);
    *(_QWORD *)v59 = v82;
    *(_QWORD *)v75 = v66;
    v71 = v67;
    v38 = (__int64 *)___call_and_wait_for_completion_UIUserManagerStatics6_Internal_System_Windows__PEAUIUser_34_PEAUIRandomAccessStreamReference_Streams_Storage_4_IPEAUHSTRING____PEAPEAU__IAsyncOperation_PEAVSetPictureResult_Internal_System_Windows___Foundation_4___ZPEAU534_PEAU6784_AEAIPEAU9__wil__YA_A_PPEAUIUserManagerStatics6_Internal_System_Windows__P81234_EAAJPEAUIUser_34_PEAUIRandomAccessStreamReference_Streams_Storage_4_IPEAUHSTRING____PEAPEAU__IAsyncOperation_PEAVSetPictureResult_Internal_System_Windows___Foundation_4__Z__QEAPEAU534___QEAPEAU6784_AEAI__QEAPEAU9__Z(
                       (__int64)&v60,
                       v72,
                       v37,
                       &v71,
                       (__int64)v75,
                       (__int64)v61,
                       v59);
    v39 = *v38;
    *v38 = 0;
    v71 = v39;
    v40 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v82 = 0;
    LODWORD(v64) = 0;
    v58[0] = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v39 + 48LL))(v39, &v64);
    if ( v41 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x598,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v41,
        ppvb);
    v42 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 64LL))(v39, v10);
    if ( v42 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x599,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v42,
        ppvb);
    v43 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 72LL))(v39, v58);
    if ( v43 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x59A,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v43,
        ppvb);
    if ( (int)v64 < 0 && !v58[0] )
      wil::details::in1diag3::Throw_Hr(retaddr, v44, v45, (const char *)(unsigned int)v64, ppvb);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v71);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v72);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v66);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v73);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v70);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v63);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v67);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v76);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v68);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v74);
    v79 = 0;
    IStream_Reset(a3);
    v46 = *(__int64 (**)(void))(*(_QWORD *)v62 + 24LL);
    ppvc = GetScaleFactorForDevice(1);
    v47 = (const char *)a4;
    v48 = v46;
  }
  catch ( ... )
  {
    v61[0] = wil::details::in1diag3::Return_CaughtException(
               retaddr,
               (void *)0x5A1,
               (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
               v47);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 56LL))(v62);
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v62);
    return (unsigned int)v61[0];
  }
  v49 = v48();
  v12 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A7,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v49,
      ppvc);
    goto LABEL_68;
  }
  _AddUserTileToHistory(v50);
  v69 = 0;
  v51 = (_GetTilePath(2u, 0, 0, &v69) >> 31) + 3;
  if ( a2 && a3 && a4 )
    v51 = 4;
  SQMSetDWORDStreamDataPointWithAppID(0x2141u, v51, v77);
  WinSqmSetDWORD(0, 10451, 1);
  v65 = 0;
  TilePath = _GetTilePath(1u, 0, 0, &v65);
  v12 = TilePath;
  if ( TilePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B1,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)TilePath,
      ppvc);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v65);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v69);
    goto LABEL_68;
  }
  v53 = SHSetUserPicturePath(0, 0, v65);
  v12 = v53;
  if ( v53 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B2,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v53,
      ppvc);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v65);
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v69);
    goto LABEL_68;
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v65);
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v69);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v62);
  return 0;
}

```

## disassembly

```asm
0x1800392fc  push    rbx
0x1800392fe  push    rsi
0x1800392ff  push    rdi
0x180039300  push    r12
0x180039302  push    r13
0x180039304  push    r14
0x180039306  push    r15
0x180039308  sub     rsp, 130h
0x18003930f  mov     rax, cs:__security_cookie
0x180039316  xor     rax, rsp
0x180039319  mov     [rsp+168h+var_48], rax
0x180039321  mov     r12, r9
0x180039324  mov     rsi, r8
0x180039327  mov     r13, rdx
0x18003932a  mov     r15, rcx
0x18003932d  mov     rax, [rsp+168h+arg_28]
0x180039335  mov     [rsp+168h+var_90], rax
0x18003933d  lea     r14, [rcx+30h]
0x180039341  mov     byte ptr [r14], 0
0x180039345  lea     rdi, [rcx+28h]
0x180039349  xor     edx, edx
0x18003934b  mov     rcx, rdi
0x18003934e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039353  test    r13, r13
0x180039356  jnz     short loc_18003938A
0x180039358  test    rsi, rsi
0x18003935b  jnz     short loc_18003938A
0x18003935d  test    r12, r12
0x180039360  jnz     short loc_18003938A
0x180039362  mov     rcx, [rsp+168h]; this
0x18003936a  mov     ebx, 80070057h
0x18003936f  mov     r9d, ebx; char *
0x180039372  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180039379  mov     edx, 559h; void *
0x18003937e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039383  mov     eax, ebx
0x180039385  jmp     loc_180039B84
0x18003938a  lea     rcx, POLID_UseDefaultTile
0x180039391  call    cs:__imp_SHWindowsPolicy
0x180039397  test    eax, eax
0x180039399  jz      short loc_1800393A5
0x18003939b  mov     eax, 80004005h
0x1800393a0  jmp     loc_180039B84
0x1800393a5  mov     [rsp+168h+var_108], 0
0x1800393ae  lea     r8, [rsp+168h+var_108]
0x1800393b3  lea     rdx, _GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76
0x1800393ba  lea     rcx, CLSID_UserTileBroker
0x1800393c1  call    CoCreateInstanceAsSystem
0x1800393c6  mov     ebx, eax
0x1800393c8  test    eax, eax
0x1800393ca  jns     short loc_1800393D3
0x1800393cc  mov     edx, 55Ch
0x1800393d1  jmp     short loc_1800393F7
0x1800393d3  xorps   xmm0, xmm0
0x1800393d6  movups  xmmword ptr [rsp+168h+pguid.Data1], xmm0
0x1800393de  lea     rcx, [rsp+168h+pguid]; pguid
0x1800393e6  call    cs:__imp_CoCreateGuid
0x1800393ec  mov     ebx, eax
0x1800393ee  test    eax, eax
0x1800393f0  jns     short loc_180039413
0x1800393f2  mov     edx, 560h; void *
0x1800393f7  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800393fe  mov     r9d, eax; char *
0x180039401  mov     rcx, [rsp+168h]; this
0x180039409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003940e  jmp     loc_180039B2E
0x180039413  xor     edx, edx
0x180039415  mov     rcx, rdi
0x180039418  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003941d  mov     rdx, rdi; lplpsz
0x180039420  lea     rcx, [rsp+168h+pguid]; rclsid
0x180039428  call    cs:__imp_StringFromCLSID
0x18003942e  mov     ebx, eax
0x180039430  test    eax, eax
0x180039432  jns     short loc_18003943B
0x180039434  mov     edx, 561h
0x180039439  jmp     short loc_1800393F7
0x18003943b  mov     rcx, [rsp+168h+var_108]
0x180039440  mov     rax, [rcx]
0x180039443  mov     rdx, [rdi]
0x180039446  mov     rax, [rax+30h]
0x18003944a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003944f  mov     ebx, eax
0x180039451  test    eax, eax
0x180039453  jns     short loc_18003945C
0x180039455  mov     edx, 562h
0x18003945a  jmp     short loc_1800393F7
0x18003945c  lea     rax, [rsp+168h+var_108]
0x180039461  mov     [rsp+168h+var_88], rax
0x180039469  mov     [rsp+168h+var_80], 1
0x180039471  lea     rcx, [rsp+168h+var_A8]
0x180039479  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::IUserStatics>(ushort const *)
0x18003947e  nop
0x18003947f  mov     [rsp+168h+var_D8], 0
0x18003948b  mov     rcx, [rsp+168h+var_A8]
0x180039493  mov     rax, [rcx]
0x180039496  mov     [rsp+168h+var_D8], 0
0x1800394a2  lea     rdx, [rsp+168h+var_D8]
0x1800394aa  mov     rax, [rax+38h]
0x1800394ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394b3  mov     rcx, [rsp+168h]; this
0x1800394bb  test    eax, eax
0x1800394bd  jns     short loc_1800394D3
0x1800394bf  mov     r9d, eax; char *
0x1800394c2  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800394c9  mov     edx, 56Eh; void *
0x1800394ce  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800394d3  mov     rdx, [rsp+168h+var_D8]
0x1800394db  lea     rcx, [rsp+168h+var_118]
0x1800394e0  call    ??$wait_for_completion@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::System::User *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS)
0x1800394e5  mov     rbx, [rax]
0x1800394e8  mov     qword ptr [rax], 0
0x1800394ef  mov     [rsp+168h+var_98], rbx
0x1800394f7  mov     rcx, [rsp+168h+var_118]
0x1800394fc  test    rcx, rcx
0x1800394ff  jz      short loc_180039517
0x180039501  mov     [rsp+168h+var_118], 0
0x18003950a  mov     rax, [rcx]
0x18003950d  mov     rax, [rax+10h]
0x180039511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039516  nop
0x180039517  mov     [rsp+168h+var_E0], 0
0x180039523  mov     rax, [rbx]
0x180039526  mov     [rsp+168h+var_E0], 0
0x180039532  lea     r8, [rsp+168h+var_E0]
0x18003953a  xor     edx, edx
0x18003953c  mov     rcx, rbx
0x18003953f  mov     rax, [rax+30h]
0x180039543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039548  mov     rcx, [rsp+168h]; this
0x180039550  xor     ebx, ebx
0x180039552  test    eax, eax
0x180039554  jns     short loc_18003956B
0x180039556  mov     r9d, eax; char *
0x180039559  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x180039560  mov     edx, 572h; void *
0x180039565  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003956b  mov     rcx, rsi
0x18003956e  test    rsi, rsi
0x180039571  cmovz   rcx, r13
0x180039575  mov     [rsp+168h+var_100], rcx
0x18003957a  test    rcx, rcx
0x18003957d  jz      short loc_180039590
0x18003957f  mov     rax, [rcx]
0x180039582  mov     rax, [rax+8]
0x180039586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003958b  mov     rcx, [rsp+168h+var_100]
0x180039590  test    rcx, rcx
0x180039593  jnz     loc_1800396C3
0x180039599  mov     [rsp+168h+var_118], rbx
0x18003959e  lea     rax, [rsp+168h+var_118]
0x1800395a3  mov     [rsp+168h+ppv], rax; int
0x1800395a8  lea     r9, _GUID_0406e498_0916_49c2_a1c4_10db7bf76766; riid
0x1800395af  xor     edx, edx; pUnkOuter
0x1800395b1  lea     r8d, [rcx+1]; dwClsContext
0x1800395b5  lea     rcx, CLSID_UserTileValidator; rclsid
0x1800395bc  call    cs:__imp_CoCreateInstance
0x1800395c2  mov     rcx, [rsp+168h]; this
0x1800395ca  test    eax, eax
0x1800395cc  jns     short loc_1800395E2
0x1800395ce  mov     r9d, eax; char *
0x1800395d1  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800395d8  mov     edx, 57Dh; void *
0x1800395dd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800395e2  mov     rcx, rbx
0x1800395e5  mov     qword ptr [rsp+168h+var_110], rbx
0x1800395ea  mov     qword ptr [rsp+168h+var_120], rbx
0x1800395ef  mov     rbx, [rsp+168h+var_118]
0x1800395f4  mov     rax, [rbx]
0x1800395f7  mov     r14, [rax+18h]
0x1800395fb  mov     qword ptr [rsp+168h+var_120], 0
0x180039604  mov     rdx, [rsp+168h+var_100]
0x180039609  mov     [rsp+168h+var_100], 0
0x180039612  test    rdx, rdx
0x180039615  jz      short loc_18003962B
0x180039617  mov     rax, [rdx]
0x18003961a  mov     rcx, rdx
0x18003961d  mov     rax, [rax+10h]
0x180039621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039626  mov     rcx, qword ptr [rsp+168h+var_110]
0x18003962b  mov     qword ptr [rsp+168h+var_110], 0
0x180039634  test    rcx, rcx
0x180039637  jz      short loc_180039646
0x180039639  mov     rax, [rcx]
0x18003963c  mov     rax, [rax+10h]
0x180039640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039645  nop
0x180039646  lea     rax, [rsp+168h+var_120]
0x18003964b  mov     [rsp+168h+var_138], rax
0x180039650  lea     rax, [rsp+168h+var_100]
0x180039655  mov     [rsp+168h+var_140], rax
0x18003965a  lea     rax, [rsp+168h+var_110]
0x18003965f  mov     [rsp+168h+ppv], rax; int
0x180039664  mov     r9, r12
0x180039667  xor     r8d, r8d
0x18003966a  xor     edx, edx
0x18003966c  mov     rcx, rbx
0x18003966f  mov     rax, r14
0x180039672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039677  mov     rcx, [rsp+168h]; this
0x18003967f  xor     ebx, ebx
0x180039681  test    eax, eax
0x180039683  jns     short loc_18003969A
0x180039685  mov     r9d, eax; char *
0x180039688  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003968f  mov     edx, 57Fh; void *
0x180039694  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003969a  lea     rcx, [rsp+168h+var_120]
0x18003969f  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800396a4  nop
0x1800396a5  lea     rcx, [rsp+168h+var_110]
0x1800396aa  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800396af  nop
0x1800396b0  lea     rcx, [rsp+168h+var_118]
0x1800396b5  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800396ba  mov     rcx, [rsp+168h+var_100]
0x1800396bf  lea     r14, [r15+30h]
0x1800396c3  mov     [rsp+168h+var_C8], rbx
0x1800396cb  lea     r9, [rsp+168h+var_C8]
0x1800396d3  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800396da  xor     edx, edx
0x1800396dc  call    cs:__imp_CreateRandomAccessStreamOverStream
0x1800396e2  mov     rcx, [rsp+168h]; this
0x1800396ea  test    eax, eax
0x1800396ec  jns     short loc_180039702
0x1800396ee  mov     r9d, eax; char *
0x1800396f1  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800396f8  mov     edx, 584h; void *
0x1800396fd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180039702  lea     rcx, [rsp+168h+var_B0]
0x18003970a  call    ??$GetActivationFactory@UIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@@@wil@@YA?AV?$com_ptr_t@UIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>(ushort const *)
0x18003970f  nop
0x180039710  mov     [rsp+168h+var_E8], rbx
0x180039718  mov     rcx, [rsp+168h+var_B0]
0x180039720  mov     rax, [rcx]
0x180039723  mov     [rsp+168h+var_E8], rbx
0x18003972b  lea     r8, [rsp+168h+var_E8]
0x180039733  mov     rdx, [rsp+168h+var_C8]
0x18003973b  mov     rax, [rax+40h]
0x18003973f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039744  mov     rcx, [rsp+168h]; this
0x18003974c  test    eax, eax
0x18003974e  jns     short loc_180039764
0x180039750  mov     r9d, eax; char *
0x180039753  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18003975a  mov     edx, 587h; void *
0x18003975f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180039764  mov     eax, [r15+20h]
0x180039768  mov     [rsp+168h+var_110], eax
0x18003976c  lea     rcx, [rsp+168h+var_B8]
0x180039774  call    ??$GetActivationFactory@UIUserManagerStatics6@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserManagerStatics6@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics6>(ushort const *)
0x180039779  nop
0x18003977a  mov     rbx, [rdi]
0x18003977d  xor     r15d, r15d
0x180039780  mov     [rsp+168h+var_50], r15
0x180039788  mov     [rsp+168h+var_120], r15d
0x18003978d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180039791  inc     rcx; unsigned __int64
0x180039794  cmp     [rbx+rcx*2], r15w
0x180039799  jnz     short loc_180039791
0x18003979b  lea     rdx, [rsp+168h+var_120]; unsigned int *
0x1800397a0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800397a5  test    eax, eax
0x1800397a7  jns     short loc_1800397BC
0x1800397a9  xor     r9d, r9d; lpArguments
0x1800397ac  xor     r8d, r8d; nNumberOfArguments
0x1800397af  lea     edx, [r9+1]; dwExceptionFlags
0x1800397b3  mov     ecx, eax; dwExceptionCode
0x1800397b5  call    cs:__imp_RaiseException
0x1800397bb  int     3; Trap to Debugger
0x1800397bc  mov     ecx, [rsp+168h+var_120]; unsigned int
0x1800397c0  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800397c5  mov     r9d, [rsp+168h+var_120]; unsigned int
0x1800397ca  mov     r8d, eax; unsigned int
0x1800397cd  mov     rdx, rbx; sourceString
0x1800397d0  lea     rcx, [rsp+168h+hstringHeader]; hstringHeader
0x1800397d8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800397dd  nop
0x1800397de  mov     rax, [rsp+168h+var_50]
0x1800397e6  mov     qword ptr [rsp+168h+var_120], rax
0x1800397eb  mov     rax, [rsp+168h+var_E8]
0x1800397f3  mov     qword ptr [rsp+168h+var_A0], rax
0x1800397fb  mov     rax, [rsp+168h+var_E0]
0x180039803  mov     [rsp+168h+var_C0], rax
0x18003980b  lea     rax, [rsp+168h+var_120]
0x180039810  mov     [rsp+168h+var_138], rax
0x180039815  lea     rax, [rsp+168h+var_110]
0x18003981a  mov     [rsp+168h+var_140], rax
0x18003981f  lea     rax, [rsp+168h+var_A0]
0x180039827  mov     [rsp+168h+ppv], rax; int
0x18003982c  lea     r9, [rsp+168h+var_C0]
0x180039834  mov     rdx, [rsp+168h+var_B8]
0x18003983c  lea     rcx, [rsp+168h+var_118]
0x180039841  call    ??$call_and_wait_for_completion@UIUserManagerStatics6@Internal@System@Windows@@PEAUIUser@34@PEAUIRandomAccessStreamReference@Streams@Storage@4@IPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@4@$$ZPEAU534@PEAU6784@AEAIPEAU9@@wil@@YA?A_PPEAUIUserManagerStatics6@Internal@System@Windows@@P81234@EAAJPEAUIUser@34@PEAUIRandomAccessStreamReference@Streams@Storage@4@IPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@4@@Z$$QEAPEAU534@$$QEAPEAU6784@AEAI$$QEAPEAU9@@Z
0x180039846  mov     rbx, [rax]
0x180039849  mov     [rax], r15
0x18003984c  mov     [rsp+168h+var_C0], rbx
0x180039854  mov     rcx, [rsp+168h+var_118]
0x180039859  test    rcx, rcx
0x18003985c  jz      short loc_180039870
  ... truncated ...
```
