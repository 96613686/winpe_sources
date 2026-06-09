# RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(ushort const *,_DSREG_JOIN_INFO *,int,void *,int,ushort const *)

- ea: `0x18009563c`
- end: `0x180095c7a`
- name: `?RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal@@YAJPEBGPEAU_DSREG_JOIN_INFO@@HPEAXH0@Z`
- size: `1598`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, struct _DSREG_JOIN_INFO *@<rdx>, int@<r8d>, void *@<r9>, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800953d0`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000992c`
- `0x180017204`
- `0x180017284`
- `0x18001a46c`
- `0x18001b190`
- `0x180030068`
- `0x180045e04`
- `0x18008e7fc`
- `0x180093684`
- `0x18009377c`
- `0x180093968`
- `0x1800939f8`
- `0x180093a88`
- `0x180093b68`
- `0x180093c48`
- `0x180093cd8`
- `0x180093d68`
- `0x180094ec4`
- `0x18009519c`
- `0x18009563c`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmRequestAadUserToken` at `0x1800958c5`
- `DMCmnUtils!DmRequestAadUserToken` at `0x1800958c5`
- `DMCmnUtils!DmGetAadUserToken` at `0x1800957a2`
- `DMCmnUtils!DmGetAadUserToken` at `0x1800957a2`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x1800956f9`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x1800956f9`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180095726`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180095726`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x180095867`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x180095867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095c20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095a58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095a58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800959be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800959da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800959f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180095a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180095a39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800959be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800959da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800959f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180095a14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180095a39`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009577e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800958f6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009577e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800958f6`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1800956df`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1800956df`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800957f6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800957f6`

## string_xrefs

- `0x1800957ef`: `%windir%\system32\deviceenroller.exe`
- `0x180095860`: `DMAppsRes.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(
        const unsigned __int16 *a1,
        struct _DSREG_JOIN_INFO *a2,
        __int64 a3,
        void *a4,
        int a5)
{
  const unsigned __int16 *v7; // r15
  const WCHAR *v8; // r12
  __int64 v9; // rdi
  HRESULT v10; // r13d
  int ActiveUserSid; // ebx
  CEnrollmentLogger *Logger; // rax
  int v13; // ecx
  signed int LastError; // eax
  CEnrollmentLogger *v15; // rax
  CEnrollmentLogger *v16; // rax
  CEnrollmentLogger *v17; // rax
  int v18; // r8d
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  UINT32 v22; // edx
  const WCHAR *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  const WCHAR *v27; // rcx
  CEnrollmentLogger *v28; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _OWORD *, _QWORD); // rbx
  DWORD v32; // edx
  int v33; // r8d
  CEnrollmentLogger *v34; // rax
  CEnrollmentLogger *v35; // rax
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v37)(_QWORD, GUID *, __int64 *); // rbx
  CEnrollmentLogger *v38; // rax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v40)(_QWORD, GUID *, unsigned __int16 **); // rdi
  int v41; // eax
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  PCNZWCH sourceString; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v49[16]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v50; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v51; // [rsp+98h] [rbp-68h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string[2]; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v54[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v55; // [rsp+D0h] [rbp-30h]
  HSTRING v56[2]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v57[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v58; // [rsp+100h] [rbp+0h]
  _OWORD v59[5]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v60; // [rsp+160h] [rbp+60h]
  HSTRING v61; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 *v62; // [rsp+178h] [rbp+78h] BYREF
  char v63; // [rsp+180h] [rbp+80h]
  WCHAR Dst[264]; // [rsp+190h] [rbp+90h] BYREF

  sourceString = 0;
  v51 = 0;
  v52 = 0;
  if ( a2 )
  {
    v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
    v8 = (const WCHAR *)*((_QWORD *)a2 + 7);
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  v9 = -1;
  if ( a1 )
  {
    LODWORD(v44) = 0;
    AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v44, (unsigned int)a2);
    v10 = CoInitializeSecurity(0, -1, 0, 0, 1u, 3u, 0, 0x40u, 0);
    v49[0] = 0;
    v49[2] = 0;
    v45 = 0;
    DmIsRunningInSystemContext(&v45);
    if ( v45 )
    {
      v46 = 0;
      v61 = (HSTRING)&v46;
      v62 = 0;
      v63 = 1;
      ActiveUserSid = DmGetActiveUserSid(&v62);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v61);
      if ( ActiveUserSid >= 0 )
        ActiveUserSid = AutoImpersonate::ImpersonateSID((AutoImpersonate *)v49, v46);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
      if ( ActiveUserSid < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollImpersonateFailure(Logger, ActiveUserSid);
LABEL_10:
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v49);
        if ( (_DWORD)v44 )
          CoUninitialize();
        goto LABEL_72;
      }
    }
    ActiveUserSid = DmGetAadUserToken(
                      L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                      a1,
                      0,
                      (unsigned __int16 **)&sourceString,
                      0);
    if ( ActiveUserSid != -895352820 )
      goto LABEL_28;
    v13 = a5 == 0;
    LODWORD(v43) = v13;
    if ( a5 )
    {
      memset_0(Dst, 0, 0x208u);
      if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\deviceenroller.exe", Dst, 0x104u) )
      {
        LastError = GetLastError();
        ActiveUserSid = LastError;
        if ( LastError > 0 )
          ActiveUserSid = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_10;
      }
      ActiveUserSid = DmRaiseToastNotificationAndWait(
                        L"DMAppsRes.dll",
                        0x65F4u,
                        0x65F5u,
                        0,
                        Dst,
                        L"AADJFROMDJ",
                        (const struct _GUID *)qword_1800DFDA8,
                        0x7530u,
                        (int *)&v43);
      if ( ActiveUserSid == -2147024891 && v10 < 0 )
        ActiveUserSid = v10;
      v13 = (int)v43;
      if ( !(_DWORD)v43 )
      {
        if ( ActiveUserSid >= 0 )
          ActiveUserSid = -2145910742;
        goto LABEL_24;
      }
      if ( ActiveUserSid < 0 )
      {
LABEL_24:
        v15 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollDmRaiseToastNotificationAndWaitFailure(v15, ActiveUserSid);
        v13 = (int)v43;
      }
    }
    if ( v13 )
    {
      ActiveUserSid = DmRequestAadUserToken(
                        L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                        a1,
                        0,
                        (unsigned __int16 **)&sourceString);
      if ( ActiveUserSid < 0 )
      {
        v16 = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollDmRequestAadUserTokenFailure(v16, ActiveUserSid);
      }
    }
LABEL_28:
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v49);
    if ( (_DWORD)v44 )
      CoUninitialize();
    goto LABEL_31;
  }
  ActiveUserSid = -2145910735;
LABEL_31:
  v17 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogAutoEnrollGetAadToken(v17, ActiveUserSid, v18, a1, v51);
  if ( ActiveUserSid >= 0 )
  {
    if ( v8 && a1 )
    {
      if ( sourceString )
      {
        Windows::Internal::StringReference::StringReference(&v61, (const unsigned __int16 (*)[48])v19);
        v44 = 0;
        ActiveUserSid = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
                          (__int64)v61,
                          (__int64)&v44);
        if ( ActiveUserSid >= 0 )
        {
          memset_0(string, 0, 0x58u);
          if ( !v7 )
            goto LABEL_44;
          v20 = -1;
          do
            ++v20;
          while ( v7[v20] );
          if ( v20 )
          {
            v21 = -1;
            do
              ++v21;
            while ( v7[v21] );
            v22 = v20 + 1;
            v23 = v7;
          }
          else
          {
LABEL_44:
            v22 = 1;
            v23 = &word_1800D1BC0;
          }
          WindowsCreateString(v23, v22, string);
          v24 = -1;
          do
            ++v24;
          while ( v8[v24] );
          WindowsCreateString(v8, v24 + 1, &string[1]);
          v25 = -1;
          do
            ++v25;
          while ( a1[v25] );
          WindowsCreateString(a1, v25 + 1, v56);
          v26 = -1;
          do
            ++v26;
          while ( sourceString[v26] );
          WindowsCreateString(sourceString, v26 + 1, v54);
          if ( a2 )
          {
            v27 = (const WCHAR *)*((_QWORD *)a2 + 4);
            if ( v27 )
            {
              do
                ++v9;
              while ( v27[v9] );
              WindowsCreateString(v27, v9 + 1, v57);
            }
          }
          LODWORD(v55) = 0;
          LODWORD(v58) = 1;
          v28 = CEnrollmentLogger::GetLogger();
          StringRawBuffer = WindowsGetStringRawBuffer(v57[0], 0);
          CEnrollmentLogger::LogAutoEnrollEnrollmentInformation(v28, v8, a1, StringRawBuffer, v7);
          v43 = 0;
          v30 = v44;
          v31 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)v44 + 72LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
          v59[0] = *(_OWORD *)string;
          v59[1] = *(_OWORD *)v54;
          v59[2] = v55;
          v59[3] = *(_OWORD *)v56;
          v59[4] = *(_OWORD *)v57;
          v60 = v58;
          ActiveUserSid = v31(v30, v59, &v43);
          if ( ActiveUserSid >= 0 )
          {
            ActiveUserSid = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(
                              v43,
                              v32,
                              v33);
            if ( ActiveUserSid >= 0 )
            {
              v47 = 0;
              v36 = v43;
              v37 = (*v43)[8];
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
              ActiveUserSid = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v37)(
                                v36,
                                &v47);
              if ( ActiveUserSid >= 0 )
              {
                v46 = 0;
                v50 = 0;
                v39 = v43;
                v40 = (__int64 (__fastcall *)(_QWORD, GUID *, unsigned __int16 **))**v43;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                ActiveUserSid = v40(v39, &GUID_00000036_0000_0000_c000_000000000046, &v46);
                if ( ActiveUserSid >= 0 )
                {
                  ActiveUserSid = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v47 + 56LL))(v47, &v50);
                  if ( ActiveUserSid >= 0 )
                  {
                    v45 = 0;
                    ActiveUserSid = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 64LL))(v47, &v45);
                    if ( ActiveUserSid >= 0 )
                    {
                      ActiveUserSid = v45;
                      if ( v45 >= 0 )
                      {
                        v41 = 0;
                        if ( v45 != 1 )
                          v41 = v45;
                        ActiveUserSid = v41;
                        WindowsDeleteString(string[0]);
                        WindowsDeleteString(string[1]);
                        WindowsDeleteString(v54[0]);
                        WindowsDeleteString(v50);
                      }
                    }
                  }
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
              }
              else
              {
                v38 = CEnrollmentLogger::GetLogger();
                CEnrollmentLogger::LogAutoEnrollGetAsyncResultsFailure(v38, ActiveUserSid);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
            }
            else
            {
              v35 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogAutoEnrollWaitForCompletiongNoThrowFailure(v35, ActiveUserSid);
            }
          }
          else
          {
            v34 = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogAutoEnrollAADEnrollAsyncFailure(v34, ActiveUserSid);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      }
    }
    else
    {
      ActiveUserSid = -2145910735;
    }
  }
LABEL_72:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v51);
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&sourceString);
  return (unsigned int)ActiveUserSid;
}

```

## disassembly

```asm
0x18009563c  mov     [rsp-8+arg_10], rbx
0x180095641  push    rbp
0x180095642  push    rsi
0x180095643  push    rdi
0x180095644  push    r12
0x180095646  push    r13
0x180095648  push    r14
0x18009564a  push    r15
0x18009564c  lea     rbp, [rsp-2B0h]
0x180095654  sub     rsp, 3B0h
0x18009565b  mov     rax, cs:__security_cookie
0x180095662  xor     rax, rsp
0x180095665  mov     [rbp+2E0h+var_40], rax
0x18009566c  mov     r14, rdx
0x18009566f  mov     rsi, rcx
0x180095672  xor     r13d, r13d
0x180095675  mov     [rsp+3E0h+sourceString], r13
0x18009567a  mov     [rbp+2E0h+var_348], r13
0x18009567e  mov     [rbp+2E0h+var_340], r13
0x180095682  test    rdx, rdx
0x180095685  jz      short loc_180095691
0x180095687  mov     r15, [rdx+28h]
0x18009568b  mov     r12, [rdx+38h]
0x18009568f  jmp     short loc_180095697
0x180095691  mov     r15, r13
0x180095694  mov     r12, r13
0x180095697  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009569b  test    rsi, rsi
0x18009569e  jz      loc_1800958FE
0x1800956a4  mov     dword ptr [rsp+3E0h+var_388], r13d
0x1800956a9  lea     rcx, [rsp+3E0h+var_388]; this
0x1800956ae  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x1800956b3  mov     [rsp+3E0h+pReserved3], r13; pReserved3
0x1800956b8  mov     [rsp+3E0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800956c0  mov     [rsp+3E0h+pAuthList], r13; pAuthList
0x1800956c5  mov     [rsp+3E0h+dwImpLevel], 3; dwImpLevel
0x1800956cd  mov     [rsp+3E0h+dwAuthnLevel], 1; dwAuthnLevel
0x1800956d5  xor     r9d, r9d; pReserved1
0x1800956d8  xor     r8d, r8d; asAuthSvc
0x1800956db  mov     edx, edi; cAuthSvc
0x1800956dd  xor     ecx, ecx; pSecDesc
0x1800956df  call    cs:__imp_CoInitializeSecurity
0x1800956e5  mov     r13d, eax
0x1800956e8  xor     ebx, ebx
0x1800956ea  mov     [rbp+2E0h+var_360], bl
0x1800956ed  mov     [rbp+2E0h+var_35E], bl
0x1800956f0  mov     [rsp+3E0h+var_380], ebx
0x1800956f4  lea     rcx, [rsp+3E0h+var_380]
0x1800956f9  call    cs:__imp_?DmIsRunningInSystemContext@@YAJPEAH@Z; DmIsRunningInSystemContext(int *)
0x1800956ff  cmp     [rsp+3E0h+var_380], ebx
0x180095703  jz      loc_18009578B
0x180095709  mov     [rsp+3E0h+var_378], rbx
0x18009570e  lea     rax, [rsp+3E0h+var_378]
0x180095713  mov     [rbp+2E0h+var_270], rax
0x180095717  mov     [rbp+2E0h+var_268], rbx
0x18009571b  mov     [rbp+2E0h+var_260], 1
0x180095722  lea     rcx, [rbp+2E0h+var_268]
0x180095726  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18009572c  mov     ebx, eax
0x18009572e  lea     rcx, [rbp+2E0h+var_270]
0x180095732  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180095737  test    ebx, ebx
0x180095739  js      short loc_18009574B
0x18009573b  mov     rdx, [rsp+3E0h+var_378]; unsigned __int16 *
0x180095740  lea     rcx, [rbp+2E0h+var_360]; this
0x180095744  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x180095749  mov     ebx, eax
0x18009574b  lea     rcx, [rsp+3E0h+var_378]
0x180095750  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180095755  test    ebx, ebx
0x180095757  jns     short loc_180095789
0x180095759  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18009575e  mov     edx, ebx; int
0x180095760  mov     rcx, rax; this
0x180095763  call    ?LogAutoEnrollImpersonateFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollImpersonateFailure(long)
0x180095768  nop
0x180095769  lea     rcx, [rbp+2E0h+var_360]; this
0x18009576d  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180095772  nop
0x180095773  cmp     dword ptr [rsp+3E0h+var_388], 0
0x180095778  jz      loc_180095C30
0x18009577e  call    cs:__imp_CoUninitialize
0x180095784  jmp     loc_180095C30
0x180095789  xor     ebx, ebx
0x18009578b  mov     qword ptr [rsp+3E0h+dwAuthnLevel], rbx
0x180095790  lea     r9, [rsp+3E0h+sourceString]
0x180095795  xor     r8d, r8d
0x180095798  mov     rdx, rsi
0x18009579b  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x1800957a2  call    cs:__imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x1800957a8  mov     ebx, eax
0x1800957aa  cmp     eax, 0CAA2000Ch
0x1800957af  jnz     loc_1800958E2
0x1800957b5  xor     ecx, ecx
0x1800957b7  mov     eax, [rbp+2E0h+arg_20]
0x1800957bd  test    eax, eax
0x1800957bf  setz    cl
0x1800957c2  mov     dword ptr [rsp+3E0h+var_390], ecx
0x1800957c6  test    eax, eax
0x1800957c8  jz      loc_1800958AC
0x1800957ce  xor     edx, edx; Val
0x1800957d0  mov     r8d, 208h; Size
0x1800957d6  lea     rcx, [rbp+2E0h+Dst]; void *
0x1800957dd  call    memset_0
0x1800957e2  mov     r8d, 104h; nSize
0x1800957e8  lea     rdx, [rbp+2E0h+Dst]; lpDst
0x1800957ef  lea     rcx, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x1800957f6  call    cs:__imp_ExpandEnvironmentStringsW
0x1800957fc  test    eax, eax
0x1800957fe  jnz     short loc_18009581E
0x180095800  call    cs:__imp_GetLastError
0x180095806  mov     ebx, eax
0x180095808  test    eax, eax
0x18009580a  jle     loc_180095769
0x180095810  movzx   ebx, ax
0x180095813  or      ebx, 80070000h
0x180095819  jmp     loc_180095769
0x18009581e  lea     rax, [rsp+3E0h+var_390]
0x180095823  mov     [rsp+3E0h+pReserved3], rax
0x180095828  mov     [rsp+3E0h+dwCapabilities], 7530h
0x180095830  lea     rax, qword_1800DFDA8
0x180095837  mov     [rsp+3E0h+pAuthList], rax
0x18009583c  lea     rax, aAadjfromdj; "AADJFROMDJ"
0x180095843  mov     qword ptr [rsp+3E0h+dwImpLevel], rax
0x180095848  lea     rax, [rbp+2E0h+Dst]
0x18009584f  mov     qword ptr [rsp+3E0h+dwAuthnLevel], rax
0x180095854  xor     r9d, r9d
0x180095857  mov     edx, 65F4h
0x18009585c  lea     r8d, [rdx+1]
0x180095860  lea     rcx, LibFileName; "DMAppsRes.dll"
0x180095867  call    cs:__imp_?DmRaiseToastNotificationAndWait@@YAJPEBGII000AEBU_GUID@@KPEAH@Z; DmRaiseToastNotificationAndWait(ushort const *,uint,uint,ushort const *,ushort const *,ushort const *,_GUID const &,ulong,int *)
0x18009586d  mov     ebx, eax
0x18009586f  cmp     eax, 80070005h
0x180095874  jnz     short loc_18009587D
0x180095876  test    r13d, r13d
0x180095879  cmovs   ebx, r13d
0x18009587d  mov     ecx, dword ptr [rsp+3E0h+var_390]
0x180095881  xor     r13d, r13d
0x180095884  test    ecx, ecx
0x180095886  jnz     short loc_180095893
0x180095888  test    ebx, ebx
0x18009588a  js      short loc_180095897
0x18009588c  mov     ebx, 8018002Ah
0x180095891  jmp     short loc_180095897
0x180095893  test    ebx, ebx
0x180095895  jns     short loc_1800958AF
0x180095897  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18009589c  mov     edx, ebx; int
0x18009589e  mov     rcx, rax; this
0x1800958a1  call    ?LogAutoEnrollDmRaiseToastNotificationAndWaitFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollDmRaiseToastNotificationAndWaitFailure(long)
0x1800958a6  mov     ecx, dword ptr [rsp+3E0h+var_390]
0x1800958aa  jmp     short loc_1800958AF
0x1800958ac  xor     r13d, r13d
0x1800958af  test    ecx, ecx
0x1800958b1  jz      short loc_1800958E5
0x1800958b3  lea     r9, [rsp+3E0h+sourceString]
0x1800958b8  xor     r8d, r8d
0x1800958bb  mov     rdx, rsi
0x1800958be  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x1800958c5  call    cs:__imp_?DmRequestAadUserToken@@YAJPEBG00PEAPEAG@Z; DmRequestAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800958cb  mov     ebx, eax
0x1800958cd  test    eax, eax
0x1800958cf  jns     short loc_1800958E5
0x1800958d1  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800958d6  mov     edx, ebx; int
0x1800958d8  mov     rcx, rax; this
0x1800958db  call    ?LogAutoEnrollDmRequestAadUserTokenFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollDmRequestAadUserTokenFailure(long)
0x1800958e0  jmp     short loc_1800958E5
0x1800958e2  xor     r13d, r13d
0x1800958e5  lea     rcx, [rbp+2E0h+var_360]; this
0x1800958e9  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800958ee  nop
0x1800958ef  cmp     dword ptr [rsp+3E0h+var_388], r13d
0x1800958f4  jz      short loc_180095903
0x1800958f6  call    cs:__imp_CoUninitialize
0x1800958fc  jmp     short loc_180095903
0x1800958fe  mov     ebx, 80180031h
0x180095903  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180095908  mov     rcx, [rbp+2E0h+var_348]
0x18009590c  mov     qword ptr [rsp+3E0h+dwAuthnLevel], rcx; unsigned __int16 *
0x180095911  mov     r9, rsi; unsigned __int16 *
0x180095914  mov     edx, ebx; int
0x180095916  mov     rcx, rax; this
0x180095919  call    ?LogAutoEnrollGetAadToken@CEnrollmentLogger@@QEAAXJHPEBG0@Z; CEnrollmentLogger::LogAutoEnrollGetAadToken(long,int,ushort const *,ushort const *)
0x18009591e  test    ebx, ebx
0x180095920  js      loc_180095C30
0x180095926  test    r12, r12
0x180095929  jz      loc_180095C2B
0x18009592f  test    rsi, rsi
0x180095932  jz      loc_180095C2B
0x180095938  cmp     [rsp+3E0h+sourceString], r13
0x18009593d  jz      loc_180095C30
0x180095943  lea     rcx, [rbp+2E0h+var_270]; string
0x180095947  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x18009594c  mov     [rsp+3E0h+var_388], r13
0x180095951  lea     rdx, [rsp+3E0h+var_388]
0x180095956  mov     rcx, [rbp+2E0h+var_270]
0x18009595a  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x18009595f  mov     ebx, eax
0x180095961  test    eax, eax
0x180095963  jns     short loc_180095974
0x180095965  lea     rcx, [rsp+3E0h+var_388]
0x18009596a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009596f  jmp     loc_180095C30
0x180095974  xor     edx, edx; Val
0x180095976  lea     r8d, [rdx+58h]; Size
0x18009597a  lea     rcx, [rbp+2E0h+string]; void *
0x18009597e  call    memset_0
0x180095983  test    r15, r15
0x180095986  jz      short loc_1800959AE
0x180095988  mov     rdx, rdi
0x18009598b  inc     rdx
0x18009598e  cmp     [r15+rdx*2], r13w
0x180095993  jnz     short loc_18009598B
0x180095995  test    rdx, rdx
0x180095998  jz      short loc_1800959AE
0x18009599a  mov     rax, rdi
0x18009599d  inc     rax
0x1800959a0  cmp     [r15+rax*2], r13w
0x1800959a5  jnz     short loc_18009599D
0x1800959a7  inc     edx
0x1800959a9  mov     rcx, r15
0x1800959ac  jmp     short loc_1800959BA
0x1800959ae  mov     edx, 1; length
0x1800959b3  lea     rcx, word_1800D1BC0; sourceString
0x1800959ba  lea     r8, [rbp+2E0h+string]; string
0x1800959be  call    cs:__imp_WindowsCreateString
0x1800959c4  mov     rdx, rdi
0x1800959c7  inc     rdx
0x1800959ca  cmp     [r12+rdx*2], r13w
0x1800959cf  jnz     short loc_1800959C7
0x1800959d1  inc     edx; length
0x1800959d3  lea     r8, [rbp+2E0h+string+8]; string
0x1800959d7  mov     rcx, r12; sourceString
0x1800959da  call    cs:__imp_WindowsCreateString
0x1800959e0  mov     rdx, rdi
0x1800959e3  inc     rdx
0x1800959e6  cmp     [rsi+rdx*2], r13w
0x1800959eb  jnz     short loc_1800959E3
0x1800959ed  inc     edx; length
0x1800959ef  lea     r8, [rbp+2E0h+var_300]; string
0x1800959f3  mov     rcx, rsi; sourceString
0x1800959f6  call    cs:__imp_WindowsCreateString
0x1800959fc  mov     rcx, [rsp+3E0h+sourceString]; sourceString
0x180095a01  mov     rdx, rdi
0x180095a04  inc     rdx
0x180095a07  cmp     [rcx+rdx*2], r13w
0x180095a0c  jnz     short loc_180095A04
0x180095a0e  inc     edx; length
0x180095a10  lea     r8, [rbp+2E0h+var_320]; string
0x180095a14  call    cs:__imp_WindowsCreateString
0x180095a1a  test    r14, r14
0x180095a1d  jz      short loc_180095A3F
0x180095a1f  mov     rcx, [r14+20h]; sourceString
0x180095a23  test    rcx, rcx
0x180095a26  jz      short loc_180095A3F
0x180095a28  inc     rdi
0x180095a2b  cmp     [rcx+rdi*2], r13w
0x180095a30  jnz     short loc_180095A28
0x180095a32  lea     edx, [rdi+1]; length
0x180095a35  lea     r8, [rbp+2E0h+var_2F0]; string
0x180095a39  call    cs:__imp_WindowsCreateString
0x180095a3f  mov     dword ptr [rbp+2E0h+var_310], r13d
0x180095a43  mov     dword ptr [rbp+2E0h+var_2E0], 1
0x180095a4a  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180095a4f  mov     rbx, rax
0x180095a52  xor     edx, edx; length
0x180095a54  mov     rcx, [rbp+2E0h+var_2F0]; string
0x180095a58  call    cs:__imp_WindowsGetStringRawBuffer
0x180095a5e  mov     qword ptr [rsp+3E0h+dwAuthnLevel], r15; unsigned __int16 *
0x180095a63  mov     r9, rax; unsigned __int16 *
0x180095a66  mov     r8, rsi; unsigned __int16 *
0x180095a69  mov     rdx, r12; unsigned __int16 *
0x180095a6c  mov     rcx, rbx; this
0x180095a6f  call    ?LogAutoEnrollEnrollmentInformation@CEnrollmentLogger@@QEAAXPEBG000@Z; CEnrollmentLogger::LogAutoEnrollEnrollmentInformation(ushort const *,ushort const *,ushort const *,ushort const *)
0x180095a74  mov     [rsp+3E0h+var_390], r13
0x180095a79  mov     rdi, [rsp+3E0h+var_388]
0x180095a7e  mov     rax, [rdi]
0x180095a81  mov     rbx, [rax+48h]
0x180095a85  lea     rcx, [rsp+3E0h+var_390]
0x180095a8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180095a8f  movaps  xmm0, xmmword ptr [rbp+2E0h+string]
0x180095a93  movaps  [rbp+2E0h+var_2D0], xmm0
0x180095a97  movaps  xmm1, xmmword ptr [rbp+2E0h+var_320]
0x180095a9b  movaps  [rbp+2E0h+var_2C0], xmm1
0x180095a9f  movaps  xmm0, [rbp+2E0h+var_310]
0x180095aa3  movaps  [rbp+2E0h+var_2B0], xmm0
0x180095aa7  movaps  xmm1, xmmword ptr [rbp+2E0h+var_300]
0x180095aab  movaps  [rbp+2E0h+var_2A0], xmm1
0x180095aaf  movaps  xmm0, xmmword ptr [rbp+2E0h+var_2F0]
0x180095ab3  movaps  [rbp+2E0h+var_290], xmm0
0x180095ab7  movsd   xmm1, [rbp+2E0h+var_2E0]
0x180095abc  movsd   [rbp+2E0h+var_280], xmm1
0x180095ac1  lea     r8, [rsp+3E0h+var_390]
0x180095ac6  lea     rdx, [rbp+2E0h+var_2D0]
0x180095aca  mov     rcx, rdi
0x180095acd  mov     rax, rbx
0x180095ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ad5  mov     ebx, eax
0x180095ad7  test    eax, eax
  ... truncated ...
```
