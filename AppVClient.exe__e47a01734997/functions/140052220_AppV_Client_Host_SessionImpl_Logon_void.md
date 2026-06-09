# AppV::Client::Host::SessionImpl::Logon(void)

- ea: `0x140052220`
- end: `0x140052c7f`
- name: `?Logon@SessionImpl@Host@Client@AppV@@UEAA_KXZ`
- size: `2655`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::SessionImpl *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008224`
- `0x140008e64`
- `0x1400094bc`
- `0x140010158`
- `0x1400147fc`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x140046c58`
- `0x140046eb0`
- `0x140051534`
- `0x140052220`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140052748`
- `ADVAPI32!EventActivityIdControl` at `0x140052748`
- `KERNEL32!GetCurrentThreadId` at `0x1400522c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400522c9`
- `KERNEL32!LeaveCriticalSection` at `0x140052c3e`
- `KERNEL32!LeaveCriticalSection` at `0x140052c3e`
- `KERNEL32!EnterCriticalSection` at `0x1400522b3`
- `KERNEL32!EnterCriticalSection` at `0x1400522b3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400523b4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005276c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400527ac`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400527e5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005281c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400523b4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005276c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400527ac`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400527e5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005281c`

## string_xrefs

- `0x14005252b`: `A Session failed to impersonate the user in session %1% in order to process the Logon, error = %2%`
- `0x1400523aa`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x140052762`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x14005231c`: `A Session received a Logon request when it was already logged on`
- `0x14005288c`: `ignoring a logon event for session %1%, because the user is already being tracked`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
unsigned __int64 __fastcall AppV::Client::Host::SessionImpl::Logon(AppV::Client::Host::SessionImpl *this)
{
  _DWORD *v2; // r12
  int v3; // ebx
  _QWORD *v4; // rax
  char *v5; // rax
  const char *v6; // rax
  unsigned __int64 v7; // rbx
  _QWORD *v8; // rax
  void (__fastcall ***v9)(_QWORD, __int64, _QWORD); // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  char *v21; // rax
  const char *v22; // rax
  char *v23; // rax
  const char *v24; // rax
  char *v25; // rax
  const char *v26; // rax
  char *v27; // rax
  const char *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rbx
  void (__fastcall ***v42)(_QWORD, __int64); // rcx
  bool v43; // zf
  void (__fastcall ***v44)(_QWORD, __int64); // rcx
  __int64 v46; // [rsp+30h] [rbp-128h] BYREF
  _QWORD *v47; // [rsp+38h] [rbp-120h] BYREF
  void (__fastcall ***v48)(_QWORD, __int64, _QWORD); // [rsp+40h] [rbp-118h] BYREF
  _QWORD v49[2]; // [rsp+48h] [rbp-110h] BYREF
  char v50; // [rsp+58h] [rbp-100h]
  char *v51; // [rsp+60h] [rbp-F8h]
  __int128 v52; // [rsp+68h] [rbp-F0h] BYREF
  __int64 v53; // [rsp+78h] [rbp-E0h]
  __int64 v54; // [rsp+80h] [rbp-D8h]
  char v55[4]; // [rsp+88h] [rbp-D0h] BYREF
  GUID ActivityId; // [rsp+8Ch] [rbp-CCh] BYREF
  int v57; // [rsp+A8h] [rbp-B0h]
  __int128 v58; // [rsp+B0h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-98h]
  __int64 v60; // [rsp+C8h] [rbp-90h]
  _QWORD v61[2]; // [rsp+D0h] [rbp-88h] BYREF
  char *v62[4]; // [rsp+E0h] [rbp-78h] BYREF
  __int128 v63; // [rsp+100h] [rbp-58h] BYREF
  __int64 *v64; // [rsp+110h] [rbp-48h]
  __int64 v65; // [rsp+118h] [rbp-40h]

  v46 = 0x8000000000LL;
  v2 = (_DWORD *)((char *)this + 16);
  v3 = *((_DWORD *)this + 4);
  v4 = operator new(0x20u);
  v47 = v4;
  *v4 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (&)(unsigned long,unsigned __int64),unsigned long const &,std::reference_wrapper<unsigned __int64 const>>>::`vftable';
  v4[1] = AppV::Client::Host::Session::ReportPublicLogonError;
  v4[2] = &v46;
  *((_DWORD *)v4 + 6) = v3;
  v49[0] = v4;
  v49[1] = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v51 = (char *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( ++*((_DWORD *)this + 22) == 1 )
    *((_DWORD *)this + 23) = GetCurrentThreadId();
  v50 = 1;
  if ( *((_BYTE *)this + 96) )
  {
    std::string::string(v55, "AppV::Client::Host::SessionImpl::Logon");
    v57 = 65;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v52,
      L"A Session received a Logon request when it was already logged on",
      0x40u);
    v58 = 0;
    v59 = 0;
    v60 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v58, L"Client", 6u);
    AppV::DecoratedLog::operator()(v55, 1, (int)&v58, (__int64)&v52);
    std::wstring::~wstring((char **)&v58);
    std::wstring::~wstring((char **)&v52);
    std::string::~string((char **)v55);
    v5 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
    v7 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6) << 52)
       | 0x80E00000303LL;
    goto LABEL_57;
  }
  v48 = 0;
  if ( (AppV::Client::Host::SessionImpl::IncrementUserProfileRefCount(this) & 0x8000000000LL) != 0 )
  {
    v8 = operator new(0x18u);
    *(_QWORD *)&v52 = v8;
    *v8 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,unsigned __int64 (AppV::Client::Host::SessionImpl::*)(void),AppV::Client::Host::SessionImpl *>>::`vftable';
    v8[1] = AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount;
    v8[2] = this;
    v47 = v8;
    v9 = v48;
    if ( v48 )
    {
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64, _QWORD)))(*v48)[1])(v48);
      v9 = v48;
    }
    v10 = 0;
    v48 = 0;
    if ( v9 )
    {
      (**v9)(v9, 1, 0);
      v10 = (void (__fastcall ***)(_QWORD, __int64))v48;
    }
    v11 = (__int64)v47;
    v47 = 0;
    v48 = (void (__fastcall ***)(_QWORD, __int64, _QWORD))v11;
    if ( v10 )
      (**v10)(v10, 1);
    appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v47);
  }
  *(_QWORD *)&v58 = &AppV::Client::Impersonator::`vftable';
  DWORD2(v58) = 0;
  BYTE12(v58) = 0;
  v59 = 0;
  v46 = AppV::Client::Impersonator::Impersonate((AppV::Client::Impersonator *)&v58, **((void ***)this + 3));
  if ( (v46 & 0x8000000000LL) != 0 )
  {
    AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v55);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    {
      LODWORD(v47) = *v2;
      v64 = (__int64 *)&v47;
      v65 = 4;
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        Service_ControllerUserLogonBegin,
        v17,
        2,
        &v63);
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          ISVAPI_ControllerUserLogonBegin,
          v18,
          1,
          &v52);
    }
    v46 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 40LL))(*((_QWORD *)this + 1));
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    {
      LODWORD(v47) = *v2;
      v64 = (__int64 *)&v47;
      v65 = 4;
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        Service_ControllerUserLogonEnd,
        v19,
        2,
        &v63);
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          ISVAPI_ControllerUserLogonEnd,
          v20,
          1,
          &v52);
    }
    if ( v55[0] )
      EventActivityIdControl(2u, &ActivityId);
    if ( (v46 & 0x8000000000LL) != 0 )
    {
      std::string::string(v55, "AppV::Client::Host::SessionImpl::Logon");
      v57 = 108;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v38);
      v52 = 0;
      v53 = 0;
      v54 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v52,
        L"UserManager successfully logged on the user in session %1%",
        0x3Au);
      v40 = AppV::Log::fmt(v39, v61, &v52);
      v41 = AppV::LogFormatter::operator%<unsigned long>(v40, (__int64)v2);
      v63 = 0;
      v64 = 0;
      v65 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v63, L"Client", 6u);
      AppV::DecoratedLog::operator()(v55, 4, (int)&v63, v41);
      std::wstring::~wstring((char **)&v63);
      v61[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v62);
      std::wstring::~wstring((char **)&v52);
      std::string::~string((char **)v55);
    }
    else
    {
      v21 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
      if ( v21 )
        v22 = v21 + 1;
      else
        v22 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
      AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v22);
      if ( (v46 & 0x8000000000LL) != 0 )
        goto LABEL_44;
      v23 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
      v24 = v23 ? v23 + 1 : "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
      AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v24);
      if ( (v46 & 0x2000000000LL) != 0
        || ((v25 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92)) == 0
          ? (v26 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp")
          : (v26 = v25 + 1),
            (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v26),
             (BYTE4(v46) & 0x1F) != 2)
         || ((v27 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92)) == 0
           ? (v28 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp")
           : (v28 = v27 + 1),
             AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v28),
             (_DWORD)v46 != 769)) )
      {
LABEL_44:
        std::string::string(v55, "AppV::Client::Host::SessionImpl::Logon");
        v57 = 120;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v33);
        v52 = 0;
        v53 = 0;
        v54 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v52,
          L"Orchestration failed to process a user logon for session %1%, error = %2%",
          0x49u);
        v35 = AppV::Log::fmt(v34, v61, &v52);
        v36 = AppV::LogFormatter::operator%<unsigned long>(v35, (__int64)v2);
        v47 = (_QWORD *)v46;
        v37 = AppV::LogFormatter::operator%(v36, (__int64 *)&v47);
        v63 = 0;
        v64 = 0;
        v65 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v63, L"Client", 6u);
        AppV::DecoratedLog::operator()(v55, 1, (int)&v63, v37);
        std::wstring::~wstring((char **)&v63);
        v61[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v62);
        std::wstring::~wstring((char **)&v52);
        std::string::~string((char **)v55);
      }
      else
      {
        std::string::string(v55, "AppV::Client::Host::SessionImpl::Logon");
        v57 = 113;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v29);
        v52 = 0;
        v53 = 0;
        v54 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v52,
          L"ignoring a logon event for session %1%, because the user is already being tracked",
          0x51u);
        v31 = AppV::Log::fmt(v30, v61, &v52);
        v32 = AppV::LogFormatter::operator%<unsigned long>(v31, (__int64)v2);
        v63 = 0;
        v64 = 0;
        v65 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v63, L"Client", 6u);
        AppV::DecoratedLog::operator()(v55, 4, (int)&v63, v32);
        std::wstring::~wstring((char **)&v63);
        v61[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v62);
        std::wstring::~wstring((char **)&v52);
        std::string::~string((char **)v55);
        v46 = 0x8000000000LL;
      }
    }
    v42 = (void (__fastcall ***)(_QWORD, __int64))v49[0];
    if ( (v46 & 0x8000000000LL) != 0 )
    {
      *((_BYTE *)this + 96) = 1;
    }
    else
    {
      v43 = v49[0] == 0;
      if ( !v49[0] )
      {
LABEL_51:
        v49[0] = 0;
        if ( !v43 )
          (**v42)(v42, 1);
        AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v58);
        v7 = v46;
        if ( (v46 & 0x8000000000LL) != 0 )
        {
          v44 = (void (__fastcall ***)(_QWORD, __int64))v48;
          v48 = 0;
          if ( v44 )
          {
            (**v44)(v44, 1);
            v7 = v46;
          }
        }
        goto LABEL_56;
      }
      (*(void (**)(void))(*(_QWORD *)v49[0] + 8LL))();
      v42 = (void (__fastcall ***)(_QWORD, __int64))v49[0];
    }
    v43 = v42 == 0;
    goto LABEL_51;
  }
  std::string::string(v55, "AppV::Client::Host::SessionImpl::Logon");
  v57 = 89;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v12);
  v63 = 0;
  v64 = 0;
  v65 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)&v63,
    L"A Session failed to impersonate the user in session %1% in order to process the Logon, error = %2%",
    0x62u);
  v14 = AppV::Log::fmt(v13, v61, &v63);
  v15 = AppV::LogFormatter::operator%<unsigned long>(v14, (__int64)this + 16);
  v47 = (_QWORD *)v46;
  v16 = AppV::LogFormatter::operator%(v15, (__int64 *)&v47);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v52, L"Client", 6u);
  AppV::DecoratedLog::operator()(v55, 1, (int)&v52, v16);
  std::wstring::~wstring((char **)&v52);
  v61[0] = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(v62);
  std::wstring::~wstring((char **)&v63);
  std::string::~string((char **)v55);
  v7 = v46;
  AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v58);
LABEL_56:
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v48);
LABEL_57:
  v43 = (*((_DWORD *)this + 22))-- == 1;
  if ( v43 )
    *((_DWORD *)this + 23) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)v49);
  return v7;
}

```

## disassembly

```asm
0x140052220  mov     [rsp+arg_8], rbx
0x140052225  mov     [rsp+arg_10], rsi
0x14005222a  push    rdi
0x14005222b  push    r12
0x14005222d  push    r13
0x14005222f  push    r14
0x140052231  push    r15
0x140052233  sub     rsp, 130h
0x14005223a  mov     rax, cs:__security_cookie
0x140052241  xor     rax, rsp
0x140052244  mov     [rsp+158h+var_38], rax
0x14005224c  mov     rsi, rcx
0x14005224f  mov     r15, 8000000000h
0x140052259  mov     [rsp+158h+var_128], r15
0x14005225e  lea     r12, [rcx+10h]
0x140052262  mov     ebx, [r12]
0x140052266  mov     ecx, 20h ; ' '; Size
0x14005226b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140052270  mov     [rsp+158h+var_120], rax
0x140052275  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@A6AXK_K@ZAEBKV?$reference_wrapper@$$CB_K@2@@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (&)(ulong,unsigned __int64),ulong const &,std::reference_wrapper<unsigned __int64 const>>>::`vftable'
0x14005227c  mov     [rax], rcx
0x14005227f  lea     rcx, ?ReportPublicLogonError@Session@Host@Client@AppV@@SAXK_K@Z; AppV::Client::Host::Session::ReportPublicLogonError(ulong,unsigned __int64)
0x140052286  mov     [rax+8], rcx
0x14005228a  lea     rcx, [rsp+158h+var_128]
0x14005228f  mov     [rax+10h], rcx
0x140052293  mov     [rax+18h], ebx
0x140052296  mov     [rsp+158h+var_110], rax
0x14005229b  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400522a2  mov     [rsp+158h+var_108], rax
0x1400522a7  lea     rdi, [rsi+30h]
0x1400522ab  mov     [rsp+158h+var_F8], rdi
0x1400522b0  mov     rcx, rdi; lpCriticalSection
0x1400522b3  call    cs:__imp_EnterCriticalSection
0x1400522b9  mov     r14d, 1
0x1400522bf  add     [rdi+28h], r14d
0x1400522c3  cmp     [rdi+28h], r14d
0x1400522c7  jnz     short loc_1400522D2
0x1400522c9  call    cs:__imp_GetCurrentThreadId
0x1400522cf  mov     [rdi+2Ch], eax
0x1400522d2  mov     [rsp+158h+var_100], r14b
0x1400522d7  xor     r13d, r13d
0x1400522da  cmp     [rsi+60h], r13b
0x1400522de  jz      loc_1400523EF
0x1400522e4  lea     rdx, aAppvClientHost_6; "AppV::Client::Host::SessionImpl::Logon"
0x1400522eb  lea     rcx, [rsp+158h+var_D0]
0x1400522f3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400522f8  mov     [rsp+158h+var_B0], 41h ; 'A'
0x140052303  xorps   xmm0, xmm0
0x140052306  movups  [rsp+158h+var_F0], xmm0
0x14005230b  mov     [rsp+158h+var_E0], r13
0x140052310  mov     [rsp+158h+var_D8], r13
0x140052318  lea     r8d, [r13+40h]
0x14005231c  lea     rdx, aASessionReceiv_0; "A Session received a Logon request when"...
0x140052323  lea     rcx, [rsp+158h+var_F0]
0x140052328  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005232d  nop
0x14005232e  xorps   xmm0, xmm0
0x140052331  movups  [rsp+158h+var_A8], xmm0
0x140052339  mov     [rsp+158h+var_98], r13
0x140052341  mov     [rsp+158h+var_90], r13
0x140052349  lea     r8d, [r13+6]
0x14005234d  lea     rdx, aClient; "Client"
0x140052354  lea     rcx, [rsp+158h+var_A8]
0x14005235c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140052361  nop
0x140052362  lea     r9, [rsp+158h+var_F0]
0x140052367  lea     r8, [rsp+158h+var_A8]
0x14005236f  mov     edx, r14d
0x140052372  lea     rcx, [rsp+158h+var_D0]
0x14005237a  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14005237f  nop
0x140052380  lea     rcx, [rsp+158h+var_A8]
0x140052388  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005238d  nop
0x14005238e  lea     rcx, [rsp+158h+var_F0]
0x140052393  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140052398  nop
0x140052399  lea     rcx, [rsp+158h+var_D0]
0x1400523a1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400523a6  lea     edx, [r13+5Ch]; Ch
0x1400523aa  lea     rbx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x1400523b1  mov     rcx, rbx; Str
0x1400523b4  call    cs:__imp_strrchr
0x1400523ba  test    rax, rax
0x1400523bd  jz      short loc_1400523C4
0x1400523bf  add     rax, r14
0x1400523c2  jmp     short loc_1400523C7
0x1400523c4  mov     rax, rbx
0x1400523c7  mov     rdx, rax; char *
0x1400523ca  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400523d1  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400523d6  mov     rbx, rax
0x1400523d9  shl     rbx, 34h
0x1400523dd  mov     rax, 80E00000303h
0x1400523e7  or      rbx, rax
0x1400523ea  jmp     loc_140052C31
0x1400523ef  mov     [rsp+158h+var_118], r13
0x1400523f4  mov     rcx, rsi; this
0x1400523f7  call    ?IncrementUserProfileRefCount@SessionImpl@Host@Client@AppV@@AEAA_KXZ; AppV::Client::Host::SessionImpl::IncrementUserProfileRefCount(void)
0x1400523fc  test    r15, rax
0x1400523ff  jz      loc_14005249D
0x140052405  mov     ecx, 18h; Size
0x14005240a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005240f  mov     qword ptr [rsp+158h+var_F0], rax
0x140052414  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P8SessionImpl@Host@Client@AppV@@EAA_KXZPEAV3456@@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,unsigned __int64 (AppV::Client::Host::SessionImpl::*)(void),AppV::Client::Host::SessionImpl *>>::`vftable'
0x14005241b  mov     [rax], rcx
0x14005241e  lea     rcx, ?DecrementUserProfileRefCount@SessionImpl@Host@Client@AppV@@AEAA_KXZ; AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount(void)
0x140052425  mov     [rax+8], rcx
0x140052429  mov     [rax+10h], rsi
0x14005242d  mov     [rsp+158h+var_120], rax
0x140052432  mov     rcx, [rsp+158h+var_118]
0x140052437  test    rcx, rcx
0x14005243a  jz      short loc_14005244D
0x14005243c  mov     rax, [rcx]
0x14005243f  mov     rax, [rax+8]
0x140052443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052448  mov     rcx, [rsp+158h+var_118]
0x14005244d  mov     r8, r13
0x140052450  mov     [rsp+158h+var_118], r13
0x140052455  test    rcx, rcx
0x140052458  jz      short loc_14005246D
0x14005245a  mov     rax, [rcx]
0x14005245d  mov     edx, r14d
0x140052460  mov     rax, [rax]
0x140052463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052468  mov     r8, [rsp+158h+var_118]
0x14005246d  mov     rax, [rsp+158h+var_120]
0x140052472  mov     [rsp+158h+var_120], r13
0x140052477  mov     [rsp+158h+var_118], rax
0x14005247c  test    r8, r8
0x14005247f  jz      short loc_140052493
0x140052481  mov     rax, [r8]
0x140052484  mov     edx, r14d
0x140052487  mov     rcx, r8
0x14005248a  mov     rax, [rax]
0x14005248d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052492  nop
0x140052493  lea     rcx, [rsp+158h+var_120]; this
0x140052498  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14005249d  lea     rax, ??_7Impersonator@Client@AppV@@6B@; const AppV::Client::Impersonator::`vftable'
0x1400524a4  mov     qword ptr [rsp+158h+var_A8], rax
0x1400524ac  mov     dword ptr [rsp+158h+var_A8+8], r13d
0x1400524b4  mov     byte ptr [rsp+158h+var_A8+0Ch], r13b
0x1400524bc  mov     [rsp+158h+var_98], r13
0x1400524c4  mov     rdx, [rsi+18h]
0x1400524c8  mov     rdx, [rdx]; void *
0x1400524cb  lea     rcx, [rsp+158h+var_A8]; this
0x1400524d3  call    ?Impersonate@Impersonator@Client@AppV@@UEAA_KPEAX@Z; AppV::Client::Impersonator::Impersonate(void *)
0x1400524d8  mov     [rsp+158h+var_128], rax
0x1400524dd  test    r15, rax
0x1400524e0  jnz     loc_14005261C
0x1400524e6  lea     rdx, aAppvClientHost_6; "AppV::Client::Host::SessionImpl::Logon"
0x1400524ed  lea     rcx, [rsp+158h+var_D0]
0x1400524f5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400524fa  mov     [rsp+158h+var_B0], 59h ; 'Y'
0x140052505  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005250a  xorps   xmm0, xmm0
0x14005250d  movups  [rsp+158h+var_58], xmm0
0x140052515  mov     [rsp+158h+var_48], r13
0x14005251d  mov     [rsp+158h+var_40], r13
0x140052525  mov     r8d, 62h ; 'b'
0x14005252b  lea     rdx, aASessionFailed_0; "A Session failed to impersonate the use"...
0x140052532  lea     rcx, [rsp+158h+var_58]
0x14005253a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005253f  nop
0x140052540  lea     r8, [rsp+158h+var_58]
0x140052548  lea     rdx, [rsp+158h+var_88]
0x140052550  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140052555  nop
0x140052556  lea     rdx, [rsi+10h]
0x14005255a  mov     rcx, rax
0x14005255d  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140052562  mov     rcx, [rsp+158h+var_128]
0x140052567  mov     [rsp+158h+var_120], rcx
0x14005256c  lea     rdx, [rsp+158h+var_120]
0x140052571  mov     rcx, rax
0x140052574  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x140052579  mov     rbx, rax
0x14005257c  xorps   xmm0, xmm0
0x14005257f  movups  [rsp+158h+var_F0], xmm0
0x140052584  mov     [rsp+158h+var_E0], r13
0x140052589  mov     [rsp+158h+var_D8], r13
0x140052591  mov     r8d, 6
0x140052597  lea     rdx, aClient; "Client"
0x14005259e  lea     rcx, [rsp+158h+var_F0]
0x1400525a3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400525a8  nop
0x1400525a9  mov     r9, rbx
0x1400525ac  lea     r8, [rsp+158h+var_F0]
0x1400525b1  mov     edx, r14d
0x1400525b4  lea     rcx, [rsp+158h+var_D0]
0x1400525bc  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400525c1  nop
0x1400525c2  lea     rcx, [rsp+158h+var_F0]
0x1400525c7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400525cc  nop
0x1400525cd  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400525d4  mov     [rsp+158h+var_88], rax
0x1400525dc  lea     rcx, [rsp+158h+var_78]
0x1400525e4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400525e9  nop
0x1400525ea  lea     rcx, [rsp+158h+var_58]
0x1400525f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400525f7  nop
0x1400525f8  lea     rcx, [rsp+158h+var_D0]
0x140052600  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140052605  mov     rbx, [rsp+158h+var_128]
0x14005260a  lea     rcx, [rsp+158h+var_A8]; this
0x140052612  call    ??1Impersonator@Client@AppV@@UEAA@XZ; AppV::Client::Impersonator::~Impersonator(void)
0x140052617  jmp     loc_140052C26
0x14005261c  lea     rcx, [rsp+158h+var_D0]
0x140052624  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x140052629  nop
0x14005262a  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x140052630  lea     rbx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140052637  test    r14b, al
0x14005263a  jz      short loc_1400526A6
0x14005263c  mov     eax, [r12]
0x140052640  mov     dword ptr [rsp+158h+var_120], eax
0x140052644  lea     rax, [rsp+158h+var_120]
0x140052649  mov     [rsp+158h+var_48], rax
0x140052651  mov     [rsp+158h+var_40], 4
0x14005265d  lea     rax, [rsp+158h+var_58]
0x140052665  mov     [rsp+158h+var_138], rax
0x14005266a  mov     r9d, 2
0x140052670  lea     rdx, Service_ControllerUserLogonBegin
0x140052677  mov     rcx, rbx
0x14005267a  call    McGenEventWrite_EventWriteTransfer
0x14005267f  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x140052685  test    r14b, al
0x140052688  jz      short loc_1400526A6
0x14005268a  lea     rax, [rsp+158h+var_F0]
0x14005268f  mov     [rsp+158h+var_138], rax
0x140052694  mov     r9d, r14d
0x140052697  lea     rdx, ISVAPI_ControllerUserLogonBegin
0x14005269e  mov     rcx, rbx
0x1400526a1  call    McGenEventWrite_EventWriteTransfer
0x1400526a6  mov     rcx, [rsi+8]
0x1400526aa  mov     rax, [rcx]
0x1400526ad  mov     rax, [rax+28h]
0x1400526b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400526b6  mov     [rsp+158h+var_128], rax
0x1400526bb  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x1400526c1  test    r14b, al
0x1400526c4  jz      short loc_140052731
0x1400526c6  mov     eax, [r12]
0x1400526ca  mov     dword ptr [rsp+158h+var_120], eax
0x1400526ce  lea     rax, [rsp+158h+var_120]
0x1400526d3  mov     [rsp+158h+var_48], rax
0x1400526db  mov     [rsp+158h+var_40], 4
0x1400526e7  lea     rax, [rsp+158h+var_58]
0x1400526ef  mov     [rsp+158h+var_138], rax
0x1400526f4  mov     r9d, 2
0x1400526fa  lea     rdx, Service_ControllerUserLogonEnd
0x140052701  mov     rcx, rbx
0x140052704  call    McGenEventWrite_EventWriteTransfer
0x140052709  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x14005270f  test    r14b, al
0x140052712  jz      short loc_140052731
0x140052714  lea     rax, [rsp+158h+var_F0]
0x140052719  mov     [rsp+158h+var_138], rax
0x14005271e  mov     r9d, r14d
0x140052721  lea     rdx, ISVAPI_ControllerUserLogonEnd
0x140052728  mov     rcx, rbx
0x14005272b  call    McGenEventWrite_EventWriteTransfer
0x140052730  nop
0x140052731  cmp     [rsp+158h+var_D0], r13b
0x140052739  jz      short loc_14005274E
0x14005273b  lea     rdx, [rsp+158h+ActivityId]; ActivityId
0x140052743  mov     ecx, 2; ControlCode
0x140052748  call    cs:__imp_EventActivityIdControl
0x14005274e  test    [rsp+158h+var_128], r15
0x140052753  jnz     loc_140052AA3
0x140052759  mov     r15d, 5Ch ; '\'
0x14005275f  mov     edx, r15d; Ch
0x140052762  lea     rbx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x140052769  mov     rcx, rbx; Str
0x14005276c  call    cs:__imp_strrchr
0x140052772  test    rax, rax
0x140052775  jz      short loc_14005277C
0x140052777  add     rax, r14
0x14005277a  jmp     short loc_14005277F
0x14005277c  mov     rax, rbx
0x14005277f  mov     rdx, rax; char *
0x140052782  lea     r14, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; AppV::FileLookUp MeyersSingleton<AppV::FileLookUp>::instance_
0x140052789  mov     rcx, r14; this
0x14005278c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140052791  mov     rax, 8000000000h
0x14005279b  test    [rsp+158h+var_128], rax
0x1400527a0  jnz     loc_140052970
0x1400527a6  mov     edx, r15d; Ch
0x1400527a9  mov     rcx, rbx; Str
0x1400527ac  call    cs:__imp_strrchr
0x1400527b2  test    rax, rax
0x1400527b5  jz      short loc_1400527BC
0x1400527b7  inc     rax
0x1400527ba  jmp     short loc_1400527BF
0x1400527bc  mov     rax, rbx
0x1400527bf  mov     rdx, rax; char *
0x1400527c2  mov     rcx, r14; this
  ... truncated ...
```
