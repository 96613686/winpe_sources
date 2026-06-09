# CtnrSvcCreateAndProtectRecoveryKeyIfNecessaryInternal

- ea: `0x1800332d0`
- end: `0x18003396c`
- name: `CtnrSvcCreateAndProtectRecoveryKeyIfNecessaryInternal`
- size: `1692`
- prototype: `__int64(__int64 **, unsigned int, __int64, ...)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800067c0`
- `0x18000a8e0`
- `0x18000aa14`
- `0x18000c688`
- `0x180012190`
- `0x1800134a0`
- `0x1800143c0`
- `0x180018194`
- `0x18001a77c`
- `0x18001c02c`
- `0x1800204c4`
- `0x180022e68`
- `0x180023278`
- `0x180024c4c`
- `0x1800281a4`
- `0x180029980`
- `0x18002c640`
- `0x180032538`
- `0x18003261c`
- `0x180032ce8`
- `0x180032d4c`
- `0x180032f40`
- `0x1800332d0`
- `0x1800343f4`
- `0x180034870`
- `0x18005a42c`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180033657`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180033657`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800337e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800338da`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003392b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800337e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800338da`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003392b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180033421`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180033421`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033642`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033642`
- `ngcrecovery!NgcVerifyPinRecoverySecret` at `0x180033708`
- `ngcrecovery!NgcVerifyPinRecoverySecret` at `0x180033708`

## string_xrefs

- `0x180033327`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x1800333bf`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180033435`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x1800334ac`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x1800334e1`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180033570`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180033895`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 CtnrSvcCreateAndProtectRecoveryKeyIfNecessaryInternal(__int64 **a1, unsigned int a2, __int64 a3, ...)
{
  char v4; // si
  int v6; // eax
  int LastError; // ebx
  __int64 v8; // rax
  __int64 *v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // r8d
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  PSID *v15; // rax
  const WCHAR *v16; // rcx
  enum NgcUserAccountType *v17; // r8
  const char *v18; // r9
  enum _NGC_ENABLED_STATE *v19; // r8
  int v20; // eax
  int v21; // eax
  wil::details::in1diag3 *v22; // rcx
  __int64 *v23; // rcx
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rax
  LONG v31; // ebx
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // ebx
  unsigned int v35; // r8d
  int v36; // ecx
  _QWORD *v37; // rcx
  int v38; // ecx
  __int16 *v39; // rdx
  __int64 v40; // rcx
  LPCWSTR *v41; // rcx
  int IsPinRecoveryEnabled; // eax
  int v43; // edx
  int v44; // r8d
  __int64 v45; // rdx
  _DWORD *v47; // [rsp+20h] [rbp-E0h]
  char v48; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v49[3]; // [rsp+31h] [rbp-CFh] BYREF
  _DWORD v50[3]; // [rsp+34h] [rbp-CCh] BYREF
  NgcUtils *v51; // [rsp+40h] [rbp-C0h] BYREF
  NgcUtils *v52; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v53; // [rsp+50h] [rbp-B0h] BYREF
  int v54; // [rsp+58h] [rbp-A8h] BYREF
  int v55; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int8 *v56; // [rsp+60h] [rbp-A0h] BYREF
  FILETIME FileTime1; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v58[2]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v59; // [rsp+80h] [rbp-80h]
  NgcUtils **v60; // [rsp+88h] [rbp-78h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  char v62; // [rsp+98h] [rbp-68h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v64[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v65[8]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v66[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v67[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v68[8]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR StringSid[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v70; // [rsp+F0h] [rbp-10h]
  _QWORD v71[4]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  __int64 v73; // [rsp+168h] [rbp+68h] BYREF
  va_list va; // [rsp+168h] [rbp+68h]
  va_list va1; // [rsp+170h] [rbp+70h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v73 = va_arg(va1, _QWORD);
  v4 = a2;
  v64[1] = a1;
  v48 = 0;
  v6 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)&v48, a2);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x631,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
      (const char *)(unsigned int)v6,
      (int)v47);
    goto LABEL_59;
  }
  v58[0] = a1;
  va_copy((va_list)&v58[1], va);
  v59 = 256;
  FileTime1 = (FILETIME)2000LL;
  v8 = std::_To_absolute_time<__int64,std::ratio<1,1000>>(v64, &FileTime1);
  std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v8);
  *(_QWORD *)&v50[1] = 0;
  LODWORD(v56) = 0;
  v9 = *a1;
  v10 = **a1;
  v60 = (NgcUtils **)&v50[1];
  v61 = 0;
  v62 = 1;
  LastError = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, unsigned __int8 **))(v10 + 120))(
                v9,
                1,
                &v61,
                &v56);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v60);
  if ( LastError < 0 )
  {
    v12 = (unsigned int)LastError;
    v13 = 1605;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
      (const char *)v12,
      (int)v47);
LABEL_58:
    wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v50[1],
      0);
    wil::details::ScopeExitFnGuard__lambda_6f2256774413161a1669dd86c0c006a4___::operator()(v58);
LABEL_59:
    if ( v48 )
      CoUninitialize();
LABEL_61:
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(a1);
    return (unsigned int)LastError;
  }
  v14 = NgcUtils::ValidateStringPropertyData(*(NgcUtils **)&v50[1], (const unsigned __int8 *)(unsigned int)v56, v11);
  LastError = v14;
  if ( v14 < 0 )
  {
    v12 = (unsigned int)v14;
    v13 = 1609;
    goto LABEL_5;
  }
  std::wstring::wstring(StringSid, *(_QWORD *)&v50[1]);
  v51 = 0;
  v15 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v51);
  v16 = (const WCHAR *)StringSid;
  if ( v70 > 7 )
    v16 = StringSid[0];
  if ( !ConvertStringSidToSidW(v16, v15) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x650,
                  (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
                  v18);
LABEL_57:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v51);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
    goto LABEL_58;
  }
  v50[0] = 0;
  if ( (int)NgcUtils::GetUserAccountType(v51, v50, v17) >= 0 && v50[0] == 1 )
    goto LABEL_63;
  v55 = 0;
  v54 = 0;
  if ( v4 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(**a1 + 184))(*a1, 3, &v55);
    if ( v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x665,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
        (const char *)(unsigned int)v20,
        (int)v47);
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, int *))(**a1 + 112))(*a1, 9, &v54);
    v22 = retaddr;
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x669,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
        (const char *)(unsigned int)v21,
        (int)v47);
    if ( v55 && v54 )
    {
      if ( (Microsoft_Windows_HelloForBusinessEnableBits & 0x10) != 0 )
        McTemplateU0k_EventWriteTransfer(v22, EVENT_HFB_PINRECOVERY_FOUNDEXISTINGKEY, v51);
      v52 = 0;
      v50[0] = 0;
      v23 = *a1;
      v24 = **a1;
      v60 = &v52;
      v61 = 0;
      v62 = 1;
      v47 = v50;
      v25 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v24 + 152))(v23, 3, 9, &v61);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x684,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
          (const char *)(unsigned int)v25,
          (int)v50);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v60);
      if ( v52 && v50[0] == 8 )
      {
        std::vector<unsigned char>::vector<unsigned char>(v71, v52, (char *)v52 + 8);
        v26 = *(_QWORD *)v71[0];
        HIDWORD(v53) = HIDWORD(*(_QWORD *)v71[0]);
        LODWORD(v53) = v26;
        v64[0] = 2;
        v27 = SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(
                v64,
                v65,
                24);
        v28 = SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(
                v27,
                v66,
                60);
        v29 = SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(
                v28,
                v67,
                60);
        v30 = (_QWORD *)SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(
                          v29,
                          v68,
                          10000000);
        if ( v53 + *v30 < v53 )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
        FileTime1 = (FILETIME)(v53 + *v30);
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v31 = CompareFileTime(&FileTime1, &SystemTimeAsFileTime);
        std::vector<unsigned char>::_Tidy(v71);
        wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v52,
          0);
        if ( v31 > 0 )
          goto LABEL_43;
        v49[0] = 0;
        v52 = 0;
        v50[0] = 0;
        v32 = *a1;
        v33 = **a1;
        v60 = &v52;
        v61 = 0;
        v62 = 1;
        v34 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, _DWORD *))(v33 + 120))(v32, 9, &v61, v50);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v60);
        if ( v34 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 3 )
          {
            LODWORD(v53) = v34;
            v39 = (__int16 *)byte_1800A6B61;
            goto LABEL_41;
          }
        }
        else
        {
          v36 = NgcUtils::ValidateStringPropertyData(v52, (const unsigned __int8 *)v50[0], v35);
          if ( v36 >= 0 )
          {
            std::wstring::wstring(v71, v52);
            v37 = v71;
            if ( v71[3] > 7u )
              v37 = (_QWORD *)v71[0];
            v38 = NgcVerifyPinRecoverySecret(v37, v49);
            if ( v38 < 0 && (unsigned int)dword_1800BE0B8 > 3 )
            {
              LODWORD(v53) = v38;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1800BE0B8,
                (unsigned int)byte_1800A6AD1,
                0,
                0,
                (__int64)&v53);
            }
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v71);
            goto LABEL_42;
          }
          if ( (unsigned int)dword_1800BE0B8 > 3 )
          {
            LODWORD(v53) = v36;
            v39 = &word_1800A6B16;
LABEL_41:
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BE0B8,
              (_DWORD)v39,
              0,
              0,
              (__int64)&v53);
          }
        }
LABEL_42:
        wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v52,
          0);
        if ( v49[0] )
        {
LABEL_43:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v51);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
          wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &v50[1],
            0);
          wil::details::ScopeExitFnGuard__lambda_6f2256774413161a1669dd86c0c006a4___::operator()(v58);
          if ( v48 )
            CoUninitialize();
          LastError = 0;
          goto LABEL_61;
        }
        if ( (Microsoft_Windows_HelloForBusinessEnableBits & 0x10) != 0 )
          McTemplateU0k_EventWriteTransfer(v40, EVENT_HFB_PINRECOVERY_UPDATEKEY, v51);
        goto LABEL_49;
      }
      wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v52,
        0);
    }
  }
LABEL_49:
  v50[0] = 2;
  v41 = StringSid;
  if ( v70 > 7 )
    v41 = (LPCWSTR *)StringSid[0];
  IsPinRecoveryEnabled = PolicyManager::IsPinRecoveryEnabled((PolicyManager *)v41, (const unsigned __int16 *)v50, v19);
  LastError = IsPinRecoveryEnabled;
  if ( IsPinRecoveryEnabled < 0 )
  {
    v45 = 1782;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
      (const char *)(unsigned int)IsPinRecoveryEnabled,
      (int)v47);
    goto LABEL_57;
  }
  if ( v50[0] == 1 )
  {
    LOBYTE(v44) = v54 != 0;
    LOBYTE(v43) = v55 != 0;
    IsPinRecoveryEnabled = CreateAndProtectRecoveryKey((unsigned int)StringSid, v43, v44, (unsigned int)*a1, a3, v73);
    LastError = IsPinRecoveryEnabled;
    if ( IsPinRecoveryEnabled < 0 )
    {
      v45 = 1796;
      goto LABEL_56;
    }
    HIBYTE(v59) = 0;
  }
LABEL_63:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v51);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
  wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v50[1],
    0);
  wil::details::ScopeExitFnGuard__lambda_6f2256774413161a1669dd86c0c006a4___::operator()(v58);
  if ( v48 )
    CoUninitialize();
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(a1);
  return 0;
}

```

## disassembly

```asm
0x1800332d0  mov     [rsp-8+arg_8], rbx
0x1800332d5  mov     [rsp-8+arg_18], r9
0x1800332da  push    rbp
0x1800332db  push    rsi
0x1800332dc  push    rdi
0x1800332dd  push    r14
0x1800332df  push    r15
0x1800332e1  lea     rbp, [rsp-20h]
0x1800332e6  sub     rsp, 120h
0x1800332ed  mov     rax, cs:__security_cookie
0x1800332f4  xor     rax, rsp
0x1800332f7  mov     [rbp+40h+var_28], rax
0x1800332fb  mov     r14, r8
0x1800332fe  mov     sil, dl
0x180033301  mov     rdi, rcx
0x180033304  mov     [rbp+40h+var_90], rcx
0x180033308  xor     r15d, r15d
0x18003330b  mov     [rsp+140h+var_110], r15b
0x180033310  lea     rcx, [rsp+140h+var_110]; this
0x180033315  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18003331a  mov     ebx, eax
0x18003331c  test    eax, eax
0x18003331e  jns     short loc_18003333D
0x180033320  mov     rcx, [rbp+48h]; this
0x180033324  mov     r9d, eax; char *
0x180033327  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003332e  mov     edx, 631h; void *
0x180033333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033338  jmp     loc_1800338D3
0x18003333d  mov     [rsp+140h+var_D0], rdi
0x180033342  lea     rax, [rbp+40h+arg_18]
0x180033346  mov     [rsp+140h+var_C8], rax
0x18003334b  mov     [rbp+40h+var_C0], 100h
0x180033351  mov     qword ptr [rsp+140h+FileTime1.dwLowDateTime], 7D0h
0x18003335a  lea     rdx, [rsp+140h+FileTime1]
0x18003335f  lea     rcx, [rbp+40h+var_98]
0x180033363  call    ??$_To_absolute_time@_JU?$ratio@$00$0DOI@@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@0@@Z
0x180033368  mov     rcx, rax
0x18003336b  call    ??$sleep_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@this_thread@std@@YAXAEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x180033370  mov     qword ptr [rsp+140h+var_10C+4], r15
0x180033375  mov     dword ptr [rsp+140h+var_E0], r15d
0x18003337a  mov     rcx, [rdi]
0x18003337d  mov     rax, [rcx]
0x180033380  lea     rdx, [rsp+140h+var_10C+4]
0x180033385  mov     [rbp+40h+var_B8], rdx
0x180033389  mov     [rbp+40h+var_B0], r15
0x18003338d  mov     [rbp+40h+var_A8], 1
0x180033391  lea     r9, [rsp+140h+var_E0]
0x180033396  lea     r8, [rbp+40h+var_B0]
0x18003339a  mov     edx, 1
0x18003339f  mov     rax, [rax+78h]
0x1800333a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333a8  mov     ebx, eax
0x1800333aa  lea     rcx, [rbp+40h+var_B8]
0x1800333ae  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800333b3  test    ebx, ebx
0x1800333b5  jns     short loc_1800333D4
0x1800333b7  mov     r9d, ebx; char *
0x1800333ba  mov     edx, 645h; void *
0x1800333bf  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x1800333c6  mov     rcx, [rbp+48h]; this
0x1800333ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800333cf  jmp     loc_1800338BB
0x1800333d4  mov     edx, dword ptr [rsp+140h+var_E0]; unsigned __int8 *
0x1800333d8  mov     rcx, qword ptr [rsp+140h+var_10C+4]; this
0x1800333dd  call    ?ValidateStringPropertyData@NgcUtils@@YAJPEBEK@Z; NgcUtils::ValidateStringPropertyData(uchar const *,ulong)
0x1800333e2  mov     ebx, eax
0x1800333e4  test    eax, eax
0x1800333e6  jns     short loc_1800333F2
0x1800333e8  mov     r9d, eax
0x1800333eb  mov     edx, 649h
0x1800333f0  jmp     short loc_1800333BF
0x1800333f2  mov     rdx, qword ptr [rsp+140h+var_10C+4]
0x1800333f7  lea     rcx, [rbp+40h+StringSid]
0x1800333fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033400  nop
0x180033401  mov     [rsp+140h+var_100], r15
0x180033406  lea     rcx, [rsp+140h+var_100]
0x18003340b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x180033410  lea     rcx, [rbp+40h+StringSid]
0x180033414  cmp     [rbp+40h+var_50], 7
0x180033419  cmova   rcx, [rbp+40h+StringSid]; StringSid
0x18003341e  mov     rdx, rax; Sid
0x180033421  call    cs:__imp_ConvertStringSidToSidW
0x180033428  nop     dword ptr [rax+rax+00h]
0x18003342d  test    eax, eax
0x18003342f  jnz     short loc_18003344D
0x180033431  mov     rcx, [rbp+48h]; this
0x180033435  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x18003343c  mov     edx, 650h; void *
0x180033441  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033446  mov     ebx, eax
0x180033448  jmp     loc_1800338A6
0x18003344d  mov     dword ptr [rsp+140h+var_10C], r15d
0x180033452  lea     rdx, [rsp+140h+var_10C]; void *
0x180033457  mov     rcx, [rsp+140h+var_100]; this
0x18003345c  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x180033461  test    eax, eax
0x180033463  js      short loc_180033470
0x180033465  cmp     dword ptr [rsp+140h+var_10C], 1
0x18003346a  jz      loc_1800338F7
0x180033470  mov     [rsp+140h+var_E4], r15d
0x180033475  mov     [rsp+140h+var_E8], r15d
0x18003347a  test    sil, sil
0x18003347d  jz      loc_180033824
0x180033483  mov     rcx, [rdi]
0x180033486  mov     rax, [rcx]
0x180033489  lea     r8, [rsp+140h+var_E4]
0x18003348e  mov     esi, 3
0x180033493  mov     edx, esi
0x180033495  mov     rax, [rax+0B8h]
0x18003349c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334a1  mov     rcx, [rbp+48h]; this
0x1800334a5  test    eax, eax
0x1800334a7  jns     short loc_1800334BD
0x1800334a9  mov     r9d, eax; char *
0x1800334ac  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x1800334b3  mov     edx, 665h; void *
0x1800334b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800334bd  mov     rcx, [rdi]
0x1800334c0  mov     rax, [rcx]
0x1800334c3  lea     r8, [rsp+140h+var_E8]
0x1800334c8  mov     edx, 9
0x1800334cd  mov     rax, [rax+70h]
0x1800334d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334d6  mov     rcx, [rbp+48h]; this
0x1800334da  test    eax, eax
0x1800334dc  jns     short loc_1800334F2
0x1800334de  mov     r9d, eax; char *
0x1800334e1  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x1800334e8  mov     edx, 669h; void *
0x1800334ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800334f2  cmp     [rsp+140h+var_E4], r15d
0x1800334f7  jz      loc_180033824
0x1800334fd  cmp     [rsp+140h+var_E8], r15d
0x180033502  jz      loc_180033824
0x180033508  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 10h
0x18003350f  jz      short loc_180033522
0x180033511  mov     r8, [rsp+140h+var_100]
0x180033516  lea     rdx, EVENT_HFB_PINRECOVERY_FOUNDEXISTINGKEY
0x18003351d  call    McTemplateU0k_EventWriteTransfer
0x180033522  mov     [rsp+140h+var_F8], r15
0x180033527  mov     dword ptr [rsp+140h+var_10C], r15d
0x18003352c  mov     rcx, [rdi]
0x18003352f  mov     rax, [rcx]
0x180033532  lea     rdx, [rsp+140h+var_F8]
0x180033537  mov     [rbp+40h+var_B8], rdx
0x18003353b  mov     [rbp+40h+var_B0], r15
0x18003353f  mov     [rbp+40h+var_A8], 1
0x180033543  lea     rdx, [rsp+140h+var_10C]
0x180033548  mov     qword ptr [rsp+140h+var_120], rdx; int
0x18003354d  lea     r9, [rbp+40h+var_B0]
0x180033551  mov     r8d, 9
0x180033557  mov     edx, esi
0x180033559  mov     rax, [rax+98h]
0x180033560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033565  mov     rcx, [rbp+48h]; this
0x180033569  test    eax, eax
0x18003356b  jns     short loc_180033582
0x18003356d  mov     r9d, eax; char *
0x180033570  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180033577  mov     edx, 684h; void *
0x18003357c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033581  nop
0x180033582  lea     rcx, [rbp+40h+var_B8]
0x180033586  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003358b  mov     rdx, [rsp+140h+var_F8]
0x180033590  test    rdx, rdx
0x180033593  jz      loc_180033818
0x180033599  cmp     dword ptr [rsp+140h+var_10C], 8
0x18003359e  jnz     loc_180033818
0x1800335a4  lea     r8, [rdx+8]
0x1800335a8  lea     rcx, [rbp+40h+var_48]
0x1800335ac  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x1800335b1  nop
0x1800335b2  mov     rax, [rbp+40h+var_48]
0x1800335b6  mov     rax, [rax]
0x1800335b9  mov     rcx, rax
0x1800335bc  shr     rcx, 20h
0x1800335c0  mov     dword ptr [rsp+140h+var_F0+4], ecx
0x1800335c4  mov     dword ptr [rsp+140h+var_F0], eax
0x1800335c8  mov     [rbp+40h+var_98], 2
0x1800335d0  mov     r8d, 18h
0x1800335d6  lea     rdx, [rbp+40h+var_88]
0x1800335da  lea     rcx, [rbp+40h+var_98]
0x1800335de  call    ??$?DH@?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(int)
0x1800335e3  mov     ebx, 3Ch ; '<'
0x1800335e8  mov     r8d, ebx
0x1800335eb  lea     rdx, [rbp+40h+var_80]
0x1800335ef  mov     rcx, rax
0x1800335f2  call    ??$?DH@?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(int)
0x1800335f7  mov     r8d, ebx
0x1800335fa  lea     rdx, [rbp+40h+var_78]
0x1800335fe  mov     rcx, rax
0x180033601  call    ??$?DH@?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(int)
0x180033606  mov     r8d, 989680h
0x18003360c  lea     rdx, [rbp+40h+var_70]
0x180033610  mov     rcx, rax
0x180033613  call    ??$?DH@?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<int>(int)
0x180033618  mov     rdx, [rax]
0x18003361b  add     rdx, [rsp+140h+var_F0]
0x180033620  cmp     rdx, [rsp+140h+var_F0]
0x180033625  jb      loc_180033966
0x18003362b  mov     rax, rdx
0x18003362e  shr     rax, 20h
0x180033632  mov     [rsp+140h+FileTime1.dwHighDateTime], eax
0x180033636  mov     [rsp+140h+FileTime1.dwLowDateTime], edx
0x18003363a  mov     qword ptr [rbp+40h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18003363e  lea     rcx, [rbp+40h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180033642  call    cs:__imp_GetSystemTimeAsFileTime
0x180033649  nop     dword ptr [rax+rax+00h]
0x18003364e  lea     rdx, [rbp+40h+SystemTimeAsFileTime]; lpFileTime2
0x180033652  lea     rcx, [rsp+140h+FileTime1]; lpFileTime1
0x180033657  call    cs:__imp_CompareFileTime
0x18003365e  nop     dword ptr [rax+rax+00h]
0x180033663  mov     ebx, eax
0x180033665  lea     rcx, [rbp+40h+var_48]
0x180033669  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003366e  nop
0x18003366f  xor     edx, edx
0x180033671  lea     rcx, [rsp+140h+var_F8]
0x180033676  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x18003367b  test    ebx, ebx
0x18003367d  jg      loc_1800337B4
0x180033683  mov     [rsp+140h+var_10F], r15b
0x180033688  mov     [rsp+140h+var_F8], r15
0x18003368d  mov     dword ptr [rsp+140h+var_10C], r15d
0x180033692  mov     rcx, [rdi]
0x180033695  mov     rax, [rcx]
0x180033698  lea     r8, [rsp+140h+var_F8]
0x18003369d  mov     [rbp+40h+var_B8], r8
0x1800336a1  mov     [rbp+40h+var_B0], r15
0x1800336a5  mov     [rbp+40h+var_A8], 1
0x1800336a9  lea     r9, [rsp+140h+var_10C]
0x1800336ae  lea     r8, [rbp+40h+var_B0]
0x1800336b2  mov     edx, 9
0x1800336b7  mov     rax, [rax+78h]
0x1800336bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336c0  mov     ebx, eax
0x1800336c2  lea     rcx, [rbp+40h+var_B8]
0x1800336c6  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800336cb  test    ebx, ebx
0x1800336cd  js      loc_18003376F
0x1800336d3  mov     edx, dword ptr [rsp+140h+var_10C]; unsigned __int8 *
0x1800336d7  mov     rcx, [rsp+140h+var_F8]; this
0x1800336dc  call    ?ValidateStringPropertyData@NgcUtils@@YAJPEBEK@Z; NgcUtils::ValidateStringPropertyData(uchar const *,ulong)
0x1800336e1  mov     ecx, eax
0x1800336e3  test    eax, eax
0x1800336e5  js      short loc_180033758
0x1800336e7  mov     rdx, [rsp+140h+var_F8]
0x1800336ec  lea     rcx, [rbp+40h+var_48]
0x1800336f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800336f5  lea     rcx, [rbp+40h+var_48]
0x1800336f9  cmp     [rbp+40h+var_30], 7
0x1800336fe  cmova   rcx, [rbp+40h+var_48]
0x180033703  lea     rdx, [rsp+140h+var_10F]
0x180033708  call    cs:__imp_NgcVerifyPinRecoverySecret
0x18003370f  nop     dword ptr [rax+rax+00h]
0x180033714  mov     ecx, eax
0x180033716  test    eax, eax
0x180033718  js      short loc_180033725
0x18003371a  lea     rcx, [rbp+40h+var_48]
0x18003371e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180033723  jmp     short loc_1800337A1
0x180033725  mov     eax, cs:dword_1800BE0B8
0x18003372b  cmp     eax, esi
0x18003372d  jbe     short loc_18003371A
0x18003372f  mov     dword ptr [rsp+140h+var_F0], ecx
0x180033733  lea     rax, [rsp+140h+var_F0]
0x180033738  mov     qword ptr [rsp+140h+var_120], rax
0x18003373d  xor     r9d, r9d
0x180033740  xor     r8d, r8d
0x180033743  lea     rdx, byte_1800A6AD1
0x18003374a  lea     rcx, dword_1800BE0B8
0x180033751  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180033756  jmp     short loc_18003371A
0x180033758  mov     eax, cs:dword_1800BE0B8
0x18003375e  cmp     eax, esi
0x180033760  jbe     short loc_1800337A1
0x180033762  mov     dword ptr [rsp+140h+var_F0], ecx
0x180033766  lea     rdx, word_1800A6B16
0x18003376d  jmp     short loc_180033784
0x18003376f  mov     eax, cs:dword_1800BE0B8
0x180033775  cmp     eax, esi
0x180033777  jbe     short loc_1800337A1
0x180033779  mov     dword ptr [rsp+140h+var_F0], ebx
0x18003377d  lea     rdx, byte_1800A6B61
0x180033784  lea     rax, [rsp+140h+var_F0]
0x180033789  mov     qword ptr [rsp+140h+var_120], rax
0x18003378e  xor     r9d, r9d
0x180033791  xor     r8d, r8d
0x180033794  lea     rcx, dword_1800BE0B8
0x18003379b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800337a0  nop
0x1800337a1  xor     edx, edx
0x1800337a3  lea     rcx, [rsp+140h+var_F8]
0x1800337a8  call    ?reset@?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uchar *)
0x1800337ad  cmp     [rsp+140h+var_10F], r15b
0x1800337b2  jz      short loc_1800337FC
0x1800337b4  lea     rcx, [rsp+140h+var_100]
  ... truncated ...
```
