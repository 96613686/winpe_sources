# RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(ushort const *,_DSREG_JOIN_INFO *,int,void *,int,ushort const *)

- ea: `0x180097f90`
- end: `0x180098647`
- name: `?RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal@@YAJPEBGPEAU_DSREG_JOIN_INFO@@HPEAXH0@Z`
- size: `1719`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, struct _DSREG_JOIN_INFO *@<rdx>, int@<r8d>, void *@<r9>, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180097d10`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x180009be4`
- `0x1800179f8`
- `0x180017a88`
- `0x1800188f4`
- `0x180019640`
- `0x18002ecd8`
- `0x180045a8c`
- `0x180090d60`
- `0x180095efc`
- `0x180095ff4`
- `0x1800961e8`
- `0x18009627c`
- `0x180096310`
- `0x1800963f0`
- `0x1800964d4`
- `0x180096568`
- `0x1800965fc`
- `0x1800977e0`
- `0x180097acc`
- `0x180097f90`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180098086`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180098086`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x1800981e5`
- `DMCmnUtils!DmRaiseToastNotificationAndWait` at `0x1800981e5`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180098053`
- `DMCmnUtils!DmIsRunningInSystemContext` at `0x180098053`
- `DMCmnUtils!DmRequestAadUserToken` at `0x180098249`
- `DMCmnUtils!DmRequestAadUserToken` at `0x180098249`
- `DMCmnUtils!DmGetAadUserToken` at `0x18009810e`
- `DMCmnUtils!DmGetAadUserToken` at `0x18009810e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098178`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800985e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009834e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180098370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180098392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800983b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800983e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009834e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180098370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180098392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800983b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800983e1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800980e4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180098280`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800980e4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180098280`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180098033`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180098033`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180098168`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180098168`

## string_xrefs

- `0x180098161`: `%windir%\system32\deviceenroller.exe`
- `0x1800981de`: `DMAppsRes.dll`

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
  signed int ActiveUserSid; // ebx
  CEnrollmentLogger *Logger; // rax
  BOOL v13; // ecx
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
  CEnrollmentLogger *v32; // rax
  CEnrollmentLogger *v33; // rax
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v35)(_QWORD, GUID *, unsigned __int16 **); // rbx
  CEnrollmentLogger *v36; // rax
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v38)(_QWORD, GUID *, unsigned __int16 **); // rdi
  int v39; // eax
  __int64 (__fastcall ***v41)(_QWORD, GUID *, unsigned __int16 **); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+58h] [rbp-A8h] BYREF
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v44; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h] BYREF
  PCNZWCH sourceString; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v47[16]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v48; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v49; // [rsp+98h] [rbp-68h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string[2]; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v52[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v53; // [rsp+D0h] [rbp-30h]
  HSTRING v54[2]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v55[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v56; // [rsp+100h] [rbp+0h]
  _OWORD v57[5]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v58; // [rsp+160h] [rbp+60h]
  HSTRING v59; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 *v60; // [rsp+178h] [rbp+78h] BYREF
  char v61; // [rsp+180h] [rbp+80h]
  WCHAR Dst[264]; // [rsp+190h] [rbp+90h] BYREF

  sourceString = 0;
  v49 = 0;
  v50 = 0;
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
    LODWORD(v42) = 0;
    AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&v42, (unsigned int)a2);
    v10 = CoInitializeSecurity(0, -1, 0, 0, 1u, 3u, 0, 0x40u, 0);
    v47[0] = 0;
    v47[2] = 0;
    v43 = 0;
    DmIsRunningInSystemContext(&v43);
    if ( v43 )
    {
      v44 = 0;
      v59 = (HSTRING)&v44;
      v60 = 0;
      v61 = 1;
      ActiveUserSid = DmGetActiveUserSid(&v60);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v59);
      if ( ActiveUserSid >= 0 )
        ActiveUserSid = AutoImpersonate::ImpersonateSID((AutoImpersonate *)v47, v44);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
      if ( ActiveUserSid < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAutoEnrollImpersonateFailure(Logger, ActiveUserSid);
LABEL_10:
        AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v47);
        if ( (_DWORD)v42 )
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
    LODWORD(v41) = v13;
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
                        (const struct _GUID *)qword_1800E3D18,
                        0x7530u,
                        (int *)&v41);
      if ( ActiveUserSid == -2147024891 && v10 < 0 )
        ActiveUserSid = v10;
      v13 = (int)v41;
      if ( !(_DWORD)v41 )
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
        v13 = (int)v41;
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
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v47);
    if ( (_DWORD)v42 )
      CoUninitialize();
    goto LABEL_31;
  }
  ActiveUserSid = -2145910735;
LABEL_31:
  v17 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogAutoEnrollGetAadToken(v17, ActiveUserSid, v18, a1, v49);
  if ( ActiveUserSid >= 0 )
  {
    if ( v8 && a1 )
    {
      if ( sourceString )
      {
        Windows::Internal::StringReference::StringReference(&v59, (const unsigned __int16 (*)[48])v19);
        v42 = 0;
        ActiveUserSid = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
                          v59,
                          &v42);
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
            v23 = &word_1800D5B40;
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
          WindowsCreateString(a1, v25 + 1, v54);
          v26 = -1;
          do
            ++v26;
          while ( sourceString[v26] );
          WindowsCreateString(sourceString, v26 + 1, v52);
          if ( a2 )
          {
            v27 = (const WCHAR *)*((_QWORD *)a2 + 4);
            if ( v27 )
            {
              do
                ++v9;
              while ( v27[v9] );
              WindowsCreateString(v27, v9 + 1, v55);
            }
          }
          LODWORD(v53) = 0;
          LODWORD(v56) = 1;
          v28 = CEnrollmentLogger::GetLogger();
          StringRawBuffer = WindowsGetStringRawBuffer(v55[0], 0);
          CEnrollmentLogger::LogAutoEnrollEnrollmentInformation(v28, v8, a1, StringRawBuffer, v7);
          v41 = 0;
          v30 = v42;
          v31 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)v42 + 72LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
          v57[0] = *(_OWORD *)string;
          v57[1] = *(_OWORD *)v52;
          v57[2] = v53;
          v57[3] = *(_OWORD *)v54;
          v57[4] = *(_OWORD *)v55;
          v58 = v56;
          ActiveUserSid = v31(v30, v57, &v41);
          if ( ActiveUserSid >= 0 )
          {
            ActiveUserSid = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(v41);
            if ( ActiveUserSid >= 0 )
            {
              v45 = 0;
              v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
              v35 = (*v41)[8];
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              ActiveUserSid = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v35)(
                                v34,
                                &v45);
              if ( ActiveUserSid >= 0 )
              {
                v44 = 0;
                v48 = 0;
                v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v41;
                v38 = **v41;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                ActiveUserSid = v38(v37, &GUID_00000036_0000_0000_c000_000000000046, &v44);
                if ( ActiveUserSid >= 0 )
                {
                  ActiveUserSid = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 56LL))(v45, &v48);
                  if ( ActiveUserSid >= 0 )
                  {
                    v43 = 0;
                    ActiveUserSid = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 64LL))(v45, &v43);
                    if ( ActiveUserSid >= 0 )
                    {
                      ActiveUserSid = v43;
                      if ( v43 >= 0 )
                      {
                        v39 = 0;
                        if ( v43 != 1 )
                          v39 = v43;
                        ActiveUserSid = v39;
                        WindowsDeleteString(string[0]);
                        WindowsDeleteString(string[1]);
                        WindowsDeleteString(v52[0]);
                        WindowsDeleteString(v48);
                      }
                    }
                  }
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              }
              else
              {
                v36 = CEnrollmentLogger::GetLogger();
                CEnrollmentLogger::LogAutoEnrollGetAsyncResultsFailure(v36, ActiveUserSid);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
            }
            else
            {
              v33 = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogAutoEnrollWaitForCompletiongNoThrowFailure(v33, ActiveUserSid);
            }
          }
          else
          {
            v32 = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogAutoEnrollAADEnrollAsyncFailure(v32, ActiveUserSid);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      }
    }
    else
    {
      ActiveUserSid = -2145910735;
    }
  }
LABEL_72:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v49);
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&sourceString);
  return (unsigned int)ActiveUserSid;
}

```

## disassembly

```asm
0x180097f90  mov     [rsp-8+arg_10], rbx
0x180097f95  push    rbp
0x180097f96  push    rsi
0x180097f97  push    rdi
0x180097f98  push    r12
0x180097f9a  push    r13
0x180097f9c  push    r14
0x180097f9e  push    r15
0x180097fa0  lea     rbp, [rsp-2B0h]
0x180097fa8  sub     rsp, 3B0h
0x180097faf  mov     rax, cs:__security_cookie
0x180097fb6  xor     rax, rsp
0x180097fb9  mov     [rbp+2E0h+var_40], rax
0x180097fc0  mov     r14, rdx
0x180097fc3  mov     rsi, rcx
0x180097fc6  xor     r13d, r13d
0x180097fc9  mov     [rsp+3E0h+sourceString], r13
0x180097fce  mov     [rbp+2E0h+var_348], r13
0x180097fd2  mov     [rbp+2E0h+var_340], r13
0x180097fd6  test    rdx, rdx
0x180097fd9  jz      short loc_180097FE5
0x180097fdb  mov     r15, [rdx+28h]
0x180097fdf  mov     r12, [rdx+38h]
0x180097fe3  jmp     short loc_180097FEB
0x180097fe5  mov     r15, r13
0x180097fe8  mov     r12, r13
0x180097feb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180097fef  test    rsi, rsi
0x180097ff2  jz      loc_18009828E
0x180097ff8  mov     dword ptr [rsp+3E0h+var_388], r13d
0x180097ffd  lea     rcx, [rsp+3E0h+var_388]; this
0x180098002  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x180098007  mov     [rsp+3E0h+pReserved3], r13; pReserved3
0x18009800c  mov     [rsp+3E0h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180098014  mov     [rsp+3E0h+pAuthList], r13; pAuthList
0x180098019  mov     [rsp+3E0h+dwImpLevel], 3; dwImpLevel
0x180098021  mov     [rsp+3E0h+dwAuthnLevel], 1; dwAuthnLevel
0x180098029  xor     r9d, r9d; pReserved1
0x18009802c  xor     r8d, r8d; asAuthSvc
0x18009802f  mov     edx, edi; cAuthSvc
0x180098031  xor     ecx, ecx; pSecDesc
0x180098033  call    cs:__imp_CoInitializeSecurity
0x18009803a  nop     dword ptr [rax+rax+00h]
0x18009803f  mov     r13d, eax
0x180098042  xor     ebx, ebx
0x180098044  mov     [rbp+2E0h+var_360], bl
0x180098047  mov     [rbp+2E0h+var_35E], bl
0x18009804a  mov     [rsp+3E0h+var_380], ebx
0x18009804e  lea     rcx, [rsp+3E0h+var_380]
0x180098053  call    cs:__imp_?DmIsRunningInSystemContext@@YAJPEAH@Z; DmIsRunningInSystemContext(int *)
0x18009805a  nop     dword ptr [rax+rax+00h]
0x18009805f  cmp     [rsp+3E0h+var_380], ebx
0x180098063  jz      loc_1800980F7
0x180098069  mov     [rsp+3E0h+var_378], rbx
0x18009806e  lea     rax, [rsp+3E0h+var_378]
0x180098073  mov     [rbp+2E0h+var_270], rax
0x180098077  mov     [rbp+2E0h+var_268], rbx
0x18009807b  mov     [rbp+2E0h+var_260], 1
0x180098082  lea     rcx, [rbp+2E0h+var_268]
0x180098086  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18009808d  nop     dword ptr [rax+rax+00h]
0x180098092  mov     ebx, eax
0x180098094  lea     rcx, [rbp+2E0h+var_270]
0x180098098  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009809d  test    ebx, ebx
0x18009809f  js      short loc_1800980B1
0x1800980a1  mov     rdx, [rsp+3E0h+var_378]; unsigned __int16 *
0x1800980a6  lea     rcx, [rbp+2E0h+var_360]; this
0x1800980aa  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x1800980af  mov     ebx, eax
0x1800980b1  lea     rcx, [rsp+3E0h+var_378]
0x1800980b6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800980bb  test    ebx, ebx
0x1800980bd  jns     short loc_1800980F5
0x1800980bf  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800980c4  mov     edx, ebx; int
0x1800980c6  mov     rcx, rax; this
0x1800980c9  call    ?LogAutoEnrollImpersonateFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollImpersonateFailure(long)
0x1800980ce  nop
0x1800980cf  lea     rcx, [rbp+2E0h+var_360]; this
0x1800980d3  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800980d8  nop
0x1800980d9  cmp     dword ptr [rsp+3E0h+var_388], 0
0x1800980de  jz      loc_1800985FC
0x1800980e4  call    cs:__imp_CoUninitialize
0x1800980eb  nop     dword ptr [rax+rax+00h]
0x1800980f0  jmp     loc_1800985FC
0x1800980f5  xor     ebx, ebx
0x1800980f7  mov     qword ptr [rsp+3E0h+dwAuthnLevel], rbx
0x1800980fc  lea     r9, [rsp+3E0h+sourceString]
0x180098101  xor     r8d, r8d
0x180098104  mov     rdx, rsi
0x180098107  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x18009810e  call    cs:__imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x180098115  nop     dword ptr [rax+rax+00h]
0x18009811a  mov     ebx, eax
0x18009811c  cmp     eax, 0CAA2000Ch
0x180098121  jnz     loc_18009826C
0x180098127  xor     ecx, ecx
0x180098129  mov     eax, [rbp+2E0h+arg_20]
0x18009812f  test    eax, eax
0x180098131  setz    cl
0x180098134  mov     dword ptr [rsp+3E0h+var_390], ecx
0x180098138  test    eax, eax
0x18009813a  jz      loc_180098230
0x180098140  xor     edx, edx; Val
0x180098142  mov     r8d, 208h; Size
0x180098148  lea     rcx, [rbp+2E0h+Dst]; void *
0x18009814f  call    memset_0
0x180098154  mov     r8d, 104h; nSize
0x18009815a  lea     rdx, [rbp+2E0h+Dst]; lpDst
0x180098161  lea     rcx, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x180098168  call    cs:__imp_ExpandEnvironmentStringsW
0x18009816f  nop     dword ptr [rax+rax+00h]
0x180098174  test    eax, eax
0x180098176  jnz     short loc_18009819C
0x180098178  call    cs:__imp_GetLastError
0x18009817f  nop     dword ptr [rax+rax+00h]
0x180098184  mov     ebx, eax
0x180098186  test    eax, eax
0x180098188  jle     loc_1800980CF
0x18009818e  movzx   ebx, ax
0x180098191  or      ebx, 80070000h
0x180098197  jmp     loc_1800980CF
0x18009819c  lea     rax, [rsp+3E0h+var_390]
0x1800981a1  mov     [rsp+3E0h+pReserved3], rax
0x1800981a6  mov     [rsp+3E0h+dwCapabilities], 7530h
0x1800981ae  lea     rax, qword_1800E3D18
0x1800981b5  mov     [rsp+3E0h+pAuthList], rax
0x1800981ba  lea     rax, aAadjfromdj; "AADJFROMDJ"
0x1800981c1  mov     qword ptr [rsp+3E0h+dwImpLevel], rax
0x1800981c6  lea     rax, [rbp+2E0h+Dst]
0x1800981cd  mov     qword ptr [rsp+3E0h+dwAuthnLevel], rax
0x1800981d2  xor     r9d, r9d
0x1800981d5  mov     edx, 65F4h
0x1800981da  lea     r8d, [rdx+1]
0x1800981de  lea     rcx, LibFileName; "DMAppsRes.dll"
0x1800981e5  call    cs:__imp_?DmRaiseToastNotificationAndWait@@YAJPEBGII000AEBU_GUID@@KPEAH@Z; DmRaiseToastNotificationAndWait(ushort const *,uint,uint,ushort const *,ushort const *,ushort const *,_GUID const &,ulong,int *)
0x1800981ec  nop     dword ptr [rax+rax+00h]
0x1800981f1  mov     ebx, eax
0x1800981f3  cmp     eax, 80070005h
0x1800981f8  jnz     short loc_180098201
0x1800981fa  test    r13d, r13d
0x1800981fd  cmovs   ebx, r13d
0x180098201  mov     ecx, dword ptr [rsp+3E0h+var_390]
0x180098205  xor     r13d, r13d
0x180098208  test    ecx, ecx
0x18009820a  jnz     short loc_180098217
0x18009820c  test    ebx, ebx
0x18009820e  js      short loc_18009821B
0x180098210  mov     ebx, 8018002Ah
0x180098215  jmp     short loc_18009821B
0x180098217  test    ebx, ebx
0x180098219  jns     short loc_180098233
0x18009821b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180098220  mov     edx, ebx; int
0x180098222  mov     rcx, rax; this
0x180098225  call    ?LogAutoEnrollDmRaiseToastNotificationAndWaitFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollDmRaiseToastNotificationAndWaitFailure(long)
0x18009822a  mov     ecx, dword ptr [rsp+3E0h+var_390]
0x18009822e  jmp     short loc_180098233
0x180098230  xor     r13d, r13d
0x180098233  test    ecx, ecx
0x180098235  jz      short loc_18009826F
0x180098237  lea     r9, [rsp+3E0h+sourceString]
0x18009823c  xor     r8d, r8d
0x18009823f  mov     rdx, rsi
0x180098242  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180098249  call    cs:__imp_?DmRequestAadUserToken@@YAJPEBG00PEAPEAG@Z; DmRequestAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *)
0x180098250  nop     dword ptr [rax+rax+00h]
0x180098255  mov     ebx, eax
0x180098257  test    eax, eax
0x180098259  jns     short loc_18009826F
0x18009825b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180098260  mov     edx, ebx; int
0x180098262  mov     rcx, rax; this
0x180098265  call    ?LogAutoEnrollDmRequestAadUserTokenFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollDmRequestAadUserTokenFailure(long)
0x18009826a  jmp     short loc_18009826F
0x18009826c  xor     r13d, r13d
0x18009826f  lea     rcx, [rbp+2E0h+var_360]; this
0x180098273  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180098278  nop
0x180098279  cmp     dword ptr [rsp+3E0h+var_388], r13d
0x18009827e  jz      short loc_180098293
0x180098280  call    cs:__imp_CoUninitialize
0x180098287  nop     dword ptr [rax+rax+00h]
0x18009828c  jmp     short loc_180098293
0x18009828e  mov     ebx, 80180031h
0x180098293  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180098298  mov     rcx, [rbp+2E0h+var_348]
0x18009829c  mov     qword ptr [rsp+3E0h+dwAuthnLevel], rcx; unsigned __int16 *
0x1800982a1  mov     r9, rsi; unsigned __int16 *
0x1800982a4  mov     edx, ebx; int
0x1800982a6  mov     rcx, rax; this
0x1800982a9  call    ?LogAutoEnrollGetAadToken@CEnrollmentLogger@@QEAAXJHPEBG0@Z; CEnrollmentLogger::LogAutoEnrollGetAadToken(long,int,ushort const *,ushort const *)
0x1800982ae  test    ebx, ebx
0x1800982b0  js      loc_1800985FC
0x1800982b6  test    r12, r12
0x1800982b9  jz      loc_1800985F7
0x1800982bf  test    rsi, rsi
0x1800982c2  jz      loc_1800985F7
0x1800982c8  cmp     [rsp+3E0h+sourceString], r13
0x1800982cd  jz      loc_1800985FC
0x1800982d3  lea     rcx, [rbp+2E0h+var_270]; string
0x1800982d7  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x1800982dc  mov     [rsp+3E0h+var_388], r13
0x1800982e1  lea     rdx, [rsp+3E0h+var_388]
0x1800982e6  mov     rcx, [rbp+2E0h+var_270]
0x1800982ea  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x1800982ef  mov     ebx, eax
0x1800982f1  test    eax, eax
0x1800982f3  jns     short loc_180098304
0x1800982f5  lea     rcx, [rsp+3E0h+var_388]
0x1800982fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800982ff  jmp     loc_1800985FC
0x180098304  xor     edx, edx; Val
0x180098306  lea     r8d, [rdx+58h]; Size
0x18009830a  lea     rcx, [rbp+2E0h+string]; void *
0x18009830e  call    memset_0
0x180098313  test    r15, r15
0x180098316  jz      short loc_18009833E
0x180098318  mov     rdx, rdi
0x18009831b  inc     rdx
0x18009831e  cmp     [r15+rdx*2], r13w
0x180098323  jnz     short loc_18009831B
0x180098325  test    rdx, rdx
0x180098328  jz      short loc_18009833E
0x18009832a  mov     rax, rdi
0x18009832d  inc     rax
0x180098330  cmp     [r15+rax*2], r13w
0x180098335  jnz     short loc_18009832D
0x180098337  inc     edx
0x180098339  mov     rcx, r15
0x18009833c  jmp     short loc_18009834A
0x18009833e  mov     edx, 1; length
0x180098343  lea     rcx, word_1800D5B40; sourceString
0x18009834a  lea     r8, [rbp+2E0h+string]; string
0x18009834e  call    cs:__imp_WindowsCreateString
0x180098355  nop     dword ptr [rax+rax+00h]
0x18009835a  mov     rdx, rdi
0x18009835d  inc     rdx
0x180098360  cmp     [r12+rdx*2], r13w
0x180098365  jnz     short loc_18009835D
0x180098367  inc     edx; length
0x180098369  lea     r8, [rbp+2E0h+string+8]; string
0x18009836d  mov     rcx, r12; sourceString
0x180098370  call    cs:__imp_WindowsCreateString
0x180098377  nop     dword ptr [rax+rax+00h]
0x18009837c  mov     rdx, rdi
0x18009837f  inc     rdx
0x180098382  cmp     [rsi+rdx*2], r13w
0x180098387  jnz     short loc_18009837F
0x180098389  inc     edx; length
0x18009838b  lea     r8, [rbp+2E0h+var_300]; string
0x18009838f  mov     rcx, rsi; sourceString
0x180098392  call    cs:__imp_WindowsCreateString
0x180098399  nop     dword ptr [rax+rax+00h]
0x18009839e  mov     rcx, [rsp+3E0h+sourceString]; sourceString
0x1800983a3  mov     rdx, rdi
0x1800983a6  inc     rdx
0x1800983a9  cmp     [rcx+rdx*2], r13w
0x1800983ae  jnz     short loc_1800983A6
0x1800983b0  inc     edx; length
0x1800983b2  lea     r8, [rbp+2E0h+var_320]; string
0x1800983b6  call    cs:__imp_WindowsCreateString
0x1800983bd  nop     dword ptr [rax+rax+00h]
0x1800983c2  test    r14, r14
0x1800983c5  jz      short loc_1800983ED
0x1800983c7  mov     rcx, [r14+20h]; sourceString
0x1800983cb  test    rcx, rcx
0x1800983ce  jz      short loc_1800983ED
0x1800983d0  inc     rdi
0x1800983d3  cmp     [rcx+rdi*2], r13w
0x1800983d8  jnz     short loc_1800983D0
0x1800983da  lea     edx, [rdi+1]; length
0x1800983dd  lea     r8, [rbp+2E0h+var_2F0]; string
0x1800983e1  call    cs:__imp_WindowsCreateString
0x1800983e8  nop     dword ptr [rax+rax+00h]
0x1800983ed  mov     dword ptr [rbp+2E0h+var_310], r13d
0x1800983f1  mov     dword ptr [rbp+2E0h+var_2E0], 1
0x1800983f8  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800983fd  mov     rbx, rax
0x180098400  xor     edx, edx; length
0x180098402  mov     rcx, [rbp+2E0h+var_2F0]; string
0x180098406  call    cs:__imp_WindowsGetStringRawBuffer
0x18009840d  nop     dword ptr [rax+rax+00h]
0x180098412  mov     qword ptr [rsp+3E0h+dwAuthnLevel], r15; unsigned __int16 *
0x180098417  mov     r9, rax; unsigned __int16 *
0x18009841a  mov     r8, rsi; unsigned __int16 *
0x18009841d  mov     rdx, r12; unsigned __int16 *
0x180098420  mov     rcx, rbx; this
0x180098423  call    ?LogAutoEnrollEnrollmentInformation@CEnrollmentLogger@@QEAAXPEBG000@Z; CEnrollmentLogger::LogAutoEnrollEnrollmentInformation(ushort const *,ushort const *,ushort const *,ushort const *)
0x180098428  mov     [rsp+3E0h+var_390], r13
0x18009842d  mov     rdi, [rsp+3E0h+var_388]
0x180098432  mov     rax, [rdi]
0x180098435  mov     rbx, [rax+48h]
0x180098439  lea     rcx, [rsp+3E0h+var_390]
0x18009843e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180098443  movaps  xmm0, xmmword ptr [rbp+2E0h+string]
0x180098447  movaps  [rbp+2E0h+var_2D0], xmm0
0x18009844b  movaps  xmm1, xmmword ptr [rbp+2E0h+var_320]
  ... truncated ...
```
