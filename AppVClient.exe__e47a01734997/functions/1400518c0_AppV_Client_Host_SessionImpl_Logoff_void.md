# AppV::Client::Host::SessionImpl::Logoff(void)

- ea: `0x1400518c0`
- end: `0x140052216`
- name: `?Logoff@SessionImpl@Host@Client@AppV@@UEAA_KXZ`
- size: `2390`
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
- `0x140050ec0`
- `0x1400518c0`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140051d15`
- `ADVAPI32!EventActivityIdControl` at `0x140051d15`
- `KERNEL32!GetCurrentThreadId` at `0x14005195a`
- `KERNEL32!GetCurrentThreadId` at `0x14005195a`
- `KERNEL32!LeaveCriticalSection` at `0x1400521e0`
- `KERNEL32!LeaveCriticalSection` at `0x1400521e0`
- `KERNEL32!EnterCriticalSection` at `0x14005194b`
- `KERNEL32!EnterCriticalSection` at `0x14005194b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051a3a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051d39`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051d76`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051db3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051dee`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051a3a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051d39`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051d76`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051db3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140051dee`

## string_xrefs

- `0x140051a30`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x140051d2f`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x140051b00`: `A Session failed to impersonate the user in session %1% in order to process the Logoff, error = %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
unsigned __int64 __fastcall AppV::Client::Host::SessionImpl::Logoff(AppV::Client::Host::SessionImpl *this)
{
  _DWORD *v2; // r12
  int v3; // ebx
  _QWORD *v4; // rax
  char *v5; // rax
  const char *v6; // rax
  unsigned __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  char *v17; // rax
  const char *v18; // rax
  char *v19; // rax
  const char *v20; // rax
  char *v21; // rax
  const char *v22; // rax
  char *v23; // rax
  const char *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rbx
  void (__fastcall ***v38)(_QWORD, __int64); // rcx
  bool v39; // zf
  __int64 v41; // [rsp+30h] [rbp-158h] BYREF
  _QWORD v42[2]; // [rsp+38h] [rbp-150h] BYREF
  char v43; // [rsp+48h] [rbp-140h]
  char *v44; // [rsp+50h] [rbp-138h]
  __int128 v45; // [rsp+58h] [rbp-130h] BYREF
  __int64 v46; // [rsp+68h] [rbp-120h]
  __int64 v47; // [rsp+70h] [rbp-118h]
  __int128 v48; // [rsp+78h] [rbp-110h] BYREF
  __int128 *v49; // [rsp+88h] [rbp-100h]
  __int64 v50; // [rsp+90h] [rbp-F8h]
  int v51; // [rsp+98h] [rbp-F0h]
  GUID ActivityId; // [rsp+A0h] [rbp-E8h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-D8h]
  __int64 v54; // [rsp+B8h] [rbp-D0h]
  __int128 v55; // [rsp+C8h] [rbp-C0h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-B0h]
  __int64 v57; // [rsp+E0h] [rbp-A8h]
  char *v58[2]; // [rsp+E8h] [rbp-A0h] BYREF
  char *v59[2]; // [rsp+F8h] [rbp-90h] BYREF
  int v60; // [rsp+108h] [rbp-80h]
  _QWORD v61[2]; // [rsp+118h] [rbp-70h] BYREF
  char *v62[4]; // [rsp+128h] [rbp-60h] BYREF

  v41 = 0x8000000000LL;
  v2 = (_DWORD *)((char *)this + 16);
  v3 = *((_DWORD *)this + 4);
  v4 = operator new(0x20u);
  *(_QWORD *)&v45 = v4;
  *v4 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (&)(unsigned long,unsigned __int64),unsigned long const &,std::reference_wrapper<unsigned __int64 const>>>::`vftable';
  v4[1] = AppV::Client::Host::Session::ReportPublicLogoffError;
  v4[2] = &v41;
  *((_DWORD *)v4 + 6) = v3;
  v42[0] = v4;
  v42[1] = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v44 = (char *)this + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( ++*((_DWORD *)this + 22) == 1 )
    *((_DWORD *)this + 23) = GetCurrentThreadId();
  v43 = 1;
  if ( !*((_BYTE *)this + 96) )
  {
    std::string::string(&v48, "AppV::Client::Host::SessionImpl::Logoff");
    v51 = 153;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v45,
      L"A Session received a Logoff request when it was not logged on",
      0x3Du);
    v55 = 0;
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v55, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)&v48, 1, (int)&v55, (__int64)&v45);
    std::wstring::~wstring((char **)&v55);
    std::wstring::~wstring((char **)&v45);
    std::string::~string((char **)&v48);
    v5 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
    v7 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6) << 52)
       | 0x130E00000303LL;
    goto LABEL_46;
  }
  *(_QWORD *)&v55 = &AppV::Client::Impersonator::`vftable';
  DWORD2(v55) = 0;
  BYTE12(v55) = 0;
  v56 = 0;
  v41 = AppV::Client::Impersonator::Impersonate((AppV::Client::Impersonator *)&v55, **((void ***)this + 3));
  if ( (v41 & 0x8000000000LL) == 0 )
  {
    std::string::string(&v48, "AppV::Client::Host::SessionImpl::Logoff");
    v51 = 164;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v8);
    ActivityId = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&ActivityId,
      L"A Session failed to impersonate the user in session %1% in order to process the Logoff, error = %2%",
      0x63u);
    v10 = AppV::Log::fmt(v9, v58, &ActivityId);
    v11 = AppV::LogFormatter::operator%<unsigned long>(v10, (__int64)v2);
    *(_QWORD *)&v45 = v41;
    v12 = AppV::LogFormatter::operator%(v11, (__int64 *)&v45);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v45, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)&v48, 1, (int)&v45, v12);
    std::wstring::~wstring((char **)&v45);
    v58[0] = (char *)&AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v59);
    std::wstring::~wstring((char **)&ActivityId);
    std::string::~string((char **)&v48);
    v7 = v41;
    AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v55);
    goto LABEL_46;
  }
  *((_BYTE *)this + 96) = 0;
  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)&ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v45) = *v2;
    v49 = &v45;
    v50 = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_ControllerUserLogoffBegin,
      v13,
      2,
      &v48);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        ISVAPI_ControllerUserLogoffBegin,
        v14,
        1,
        &v45);
  }
  v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1));
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
  {
    LODWORD(v45) = *v2;
    v49 = &v45;
    v50 = 4;
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_ControllerUserLogoffEnd,
      v15,
      2,
      &v48);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        ISVAPI_ControllerUserLogoffEnd,
        v16,
        1,
        &v45);
  }
  if ( LOBYTE(ActivityId.Data1) )
    EventActivityIdControl(2u, (LPGUID)&ActivityId.Data2);
  if ( (v41 & 0x8000000000LL) != 0 )
  {
    std::string::string(v58, "AppV::Client::Host::SessionImpl::Logoff");
    v60 = 186;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v34);
    ActivityId = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&ActivityId,
      L"UserManager successfully logged off the user in session %1%",
      0x3Bu);
    v36 = AppV::Log::fmt(v35, v61, &ActivityId);
    v37 = AppV::LogFormatter::operator%<unsigned long>(v36, (__int64)v2);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v58, 4, (int)&v48, v37);
    std::wstring::~wstring((char **)&v48);
    v61[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v62);
    std::wstring::~wstring((char **)&ActivityId);
    std::string::~string(v58);
  }
  else
  {
    v17 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
    if ( v17 )
      v18 = v17 + 1;
    else
      v18 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
    AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v18);
    if ( (v41 & 0x8000000000LL) != 0 )
      goto LABEL_36;
    v19 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
    v20 = v19 ? v19 + 1 : "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
    AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v20);
    if ( (v41 & 0x2000000000LL) != 0
      || ((v21 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92)) == 0
        ? (v22 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp")
        : (v22 = v21 + 1),
          (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v22),
           (BYTE4(v41) & 0x1F) != 2)
       || ((v23 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92)) == 0
         ? (v24 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp")
         : (v24 = v23 + 1),
           AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v24),
           (_DWORD)v41 != 770)) )
    {
LABEL_36:
      std::string::string(v58, "AppV::Client::Host::SessionImpl::Logoff");
      v60 = 198;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v29);
      v48 = 0;
      v49 = 0;
      v50 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v48,
        L"Orchestration failed to process a user logoff for session %1%, error = %2%",
        0x4Au);
      v31 = AppV::Log::fmt(v30, v61, &v48);
      v32 = AppV::LogFormatter::operator%<unsigned long>(v31, (__int64)v2);
      *(_QWORD *)&v45 = v41;
      v33 = AppV::LogFormatter::operator%(v32, (__int64 *)&v45);
      ActivityId = 0;
      v53 = 0;
      v54 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&ActivityId, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v58, 1, (int)&ActivityId, v33);
      std::wstring::~wstring((char **)&ActivityId);
      v61[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v62);
      std::wstring::~wstring((char **)&v48);
      std::string::~string(v58);
    }
    else
    {
      std::string::string(&v48, "AppV::Client::Host::SessionImpl::Logoff");
      v51 = 191;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v25);
      v45 = 0;
      v46 = 0;
      v47 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v45,
        L"ignoring a logoff event for session %1%, because the user is not being tracked",
        0x4Eu);
      v27 = AppV::Log::fmt(v26, v58, &v45);
      v28 = AppV::LogFormatter::operator%<unsigned long>(v27, (__int64)v2);
      ActivityId = 0;
      v53 = 0;
      v54 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&ActivityId, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)&v48, 4, (int)&ActivityId, v28);
      std::wstring::~wstring((char **)&ActivityId);
      v58[0] = (char *)&AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v59);
      std::wstring::~wstring((char **)&v45);
      std::string::~string((char **)&v48);
      v41 = 0x8000000000LL;
    }
  }
  v38 = (void (__fastcall ***)(_QWORD, __int64))v42[0];
  if ( (v41 & 0x8000000000LL) != 0 )
    goto LABEL_41;
  v39 = v42[0] == 0;
  if ( v42[0] )
  {
    (*(void (**)(void))(*(_QWORD *)v42[0] + 8LL))();
    v38 = (void (__fastcall ***)(_QWORD, __int64))v42[0];
LABEL_41:
    v39 = v38 == 0;
  }
  v42[0] = 0;
  if ( !v39 )
    (**v38)(v38, 1);
  AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v55);
  v7 = v41;
  if ( (v41 & 0x8000000000LL) != 0 )
  {
    AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount(this);
    v7 = v41;
  }
LABEL_46:
  v39 = (*((_DWORD *)this + 22))-- == 1;
  if ( v39 )
    *((_DWORD *)this + 23) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)v42);
  return v7;
}

```

## disassembly

```asm
0x1400518c0  push    rbx
0x1400518c2  push    rdi
0x1400518c3  push    r12
0x1400518c5  push    r13
0x1400518c7  push    r14
0x1400518c9  push    r15
0x1400518cb  sub     rsp, 158h
0x1400518d2  mov     rax, cs:__security_cookie
0x1400518d9  xor     rax, rsp
0x1400518dc  mov     [rsp+188h+var_40], rax
0x1400518e4  mov     r14, rcx
0x1400518e7  mov     r15, 8000000000h
0x1400518f1  mov     [rsp+188h+var_158], r15
0x1400518f6  lea     r12, [rcx+10h]
0x1400518fa  mov     ebx, [r12]
0x1400518fe  mov     ecx, 20h ; ' '; Size
0x140051903  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140051908  mov     qword ptr [rsp+188h+var_130], rax
0x14005190d  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@A6AXK_K@ZAEBKV?$reference_wrapper@$$CB_K@2@@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (&)(ulong,unsigned __int64),ulong const &,std::reference_wrapper<unsigned __int64 const>>>::`vftable'
0x140051914  mov     [rax], rcx
0x140051917  lea     rcx, ?ReportPublicLogoffError@Session@Host@Client@AppV@@SAXK_K@Z; AppV::Client::Host::Session::ReportPublicLogoffError(ulong,unsigned __int64)
0x14005191e  mov     [rax+8], rcx
0x140051922  lea     rcx, [rsp+188h+var_158]
0x140051927  mov     [rax+10h], rcx
0x14005192b  mov     [rax+18h], ebx
0x14005192e  mov     [rsp+188h+var_150], rax
0x140051933  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14005193a  mov     [rsp+188h+var_148], rax
0x14005193f  lea     rdi, [r14+30h]
0x140051943  mov     [rsp+188h+var_138], rdi
0x140051948  mov     rcx, rdi; lpCriticalSection
0x14005194b  call    cs:__imp_EnterCriticalSection
0x140051951  inc     dword ptr [rdi+28h]
0x140051954  cmp     dword ptr [rdi+28h], 1
0x140051958  jnz     short loc_140051963
0x14005195a  call    cs:__imp_GetCurrentThreadId
0x140051960  mov     [rdi+2Ch], eax
0x140051963  mov     [rsp+188h+var_140], 1
0x140051968  xor     r13d, r13d
0x14005196b  cmp     [r14+60h], r13b
0x14005196f  jnz     loc_140051A75
0x140051975  lea     rdx, aAppvClientHost_1; "AppV::Client::Host::SessionImpl::Logoff"
0x14005197c  lea     rcx, [rsp+188h+var_110]
0x140051981  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140051986  mov     [rsp+188h+var_F0], 99h
0x140051991  xorps   xmm0, xmm0
0x140051994  movups  [rsp+188h+var_130], xmm0
0x140051999  mov     [rsp+188h+var_120], r13
0x14005199e  mov     [rsp+188h+var_118], r13
0x1400519a3  lea     r8d, [r13+3Dh]
0x1400519a7  lea     rdx, aASessionReceiv; "A Session received a Logoff request whe"...
0x1400519ae  lea     rcx, [rsp+188h+var_130]
0x1400519b3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400519b8  nop
0x1400519b9  xorps   xmm0, xmm0
0x1400519bc  movups  [rsp+188h+var_C0], xmm0
0x1400519c4  mov     [rsp+188h+var_B0], r13
0x1400519cc  mov     [rsp+188h+var_A8], r13
0x1400519d4  lea     r8d, [r13+6]
0x1400519d8  lea     rdx, aClient; "Client"
0x1400519df  lea     rcx, [rsp+188h+var_C0]
0x1400519e7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400519ec  nop
0x1400519ed  lea     r9, [rsp+188h+var_130]
0x1400519f2  lea     r8, [rsp+188h+var_C0]
0x1400519fa  lea     edx, [r13+1]
0x1400519fe  lea     rcx, [rsp+188h+var_110]
0x140051a03  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140051a08  nop
0x140051a09  lea     rcx, [rsp+188h+var_C0]
0x140051a11  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051a16  nop
0x140051a17  lea     rcx, [rsp+188h+var_130]
0x140051a1c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051a21  nop
0x140051a22  lea     rcx, [rsp+188h+var_110]
0x140051a27  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140051a2c  lea     edx, [r13+5Ch]; Ch
0x140051a30  lea     rbx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x140051a37  mov     rcx, rbx; Str
0x140051a3a  call    cs:__imp_strrchr
0x140051a40  test    rax, rax
0x140051a43  jz      short loc_140051A4A
0x140051a45  inc     rax
0x140051a48  jmp     short loc_140051A4D
0x140051a4a  mov     rax, rbx
0x140051a4d  mov     rdx, rax; char *
0x140051a50  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140051a57  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140051a5c  mov     rbx, rax
0x140051a5f  shl     rbx, 34h
0x140051a63  mov     rax, 130E00000303h
0x140051a6d  or      rbx, rax
0x140051a70  jmp     loc_1400521D3
0x140051a75  lea     rax, ??_7Impersonator@Client@AppV@@6B@; const AppV::Client::Impersonator::`vftable'
0x140051a7c  mov     qword ptr [rsp+188h+var_C0], rax
0x140051a84  mov     dword ptr [rsp+188h+var_C0+8], r13d
0x140051a8c  mov     byte ptr [rsp+188h+var_C0+0Ch], r13b
0x140051a94  mov     [rsp+188h+var_B0], r13
0x140051a9c  mov     rdx, [r14+18h]
0x140051aa0  mov     rdx, [rdx]; void *
0x140051aa3  lea     rcx, [rsp+188h+var_C0]; this
0x140051aab  call    ?Impersonate@Impersonator@Client@AppV@@UEAA_KPEAX@Z; AppV::Client::Impersonator::Impersonate(void *)
0x140051ab0  mov     [rsp+188h+var_158], rax
0x140051ab5  test    r15, rax
0x140051ab8  jnz     loc_140051BE9
0x140051abe  lea     rdx, aAppvClientHost_1; "AppV::Client::Host::SessionImpl::Logoff"
0x140051ac5  lea     rcx, [rsp+188h+var_110]
0x140051aca  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140051acf  mov     [rsp+188h+var_F0], 0A4h
0x140051ada  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140051adf  xorps   xmm0, xmm0
0x140051ae2  movups  xmmword ptr [rsp+188h+ActivityId.Data1], xmm0
0x140051aea  mov     [rsp+188h+var_D8], r13
0x140051af2  mov     [rsp+188h+var_D0], r13
0x140051afa  mov     r8d, 63h ; 'c'
0x140051b00  lea     rdx, aASessionFailed; "A Session failed to impersonate the use"...
0x140051b07  lea     rcx, [rsp+188h+ActivityId]
0x140051b0f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140051b14  nop
0x140051b15  lea     r8, [rsp+188h+ActivityId]
0x140051b1d  lea     rdx, [rsp+188h+var_A0]
0x140051b25  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140051b2a  nop
0x140051b2b  mov     rdx, r12
0x140051b2e  mov     rcx, rax
0x140051b31  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140051b36  mov     rcx, [rsp+188h+var_158]
0x140051b3b  mov     qword ptr [rsp+188h+var_130], rcx
0x140051b40  lea     rdx, [rsp+188h+var_130]
0x140051b45  mov     rcx, rax
0x140051b48  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x140051b4d  mov     rbx, rax
0x140051b50  xorps   xmm0, xmm0
0x140051b53  movups  [rsp+188h+var_130], xmm0
0x140051b58  mov     [rsp+188h+var_120], r13
0x140051b5d  mov     [rsp+188h+var_118], r13
0x140051b62  mov     r8d, 6
0x140051b68  lea     rdx, aClient; "Client"
0x140051b6f  lea     rcx, [rsp+188h+var_130]
0x140051b74  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140051b79  nop
0x140051b7a  mov     r9, rbx
0x140051b7d  lea     r8, [rsp+188h+var_130]
0x140051b82  mov     edx, 1
0x140051b87  lea     rcx, [rsp+188h+var_110]
0x140051b8c  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140051b91  nop
0x140051b92  lea     rcx, [rsp+188h+var_130]
0x140051b97  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051b9c  nop
0x140051b9d  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140051ba4  mov     [rsp+188h+var_A0], rax
0x140051bac  lea     rcx, [rsp+188h+var_90]
0x140051bb4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051bb9  nop
0x140051bba  lea     rcx, [rsp+188h+ActivityId]
0x140051bc2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051bc7  nop
0x140051bc8  lea     rcx, [rsp+188h+var_110]
0x140051bcd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140051bd2  mov     rbx, [rsp+188h+var_158]
0x140051bd7  lea     rcx, [rsp+188h+var_C0]; this
0x140051bdf  call    ??1Impersonator@Client@AppV@@UEAA@XZ; AppV::Client::Impersonator::~Impersonator(void)
0x140051be4  jmp     loc_1400521D3
0x140051be9  mov     [r14+60h], r13b
0x140051bed  lea     rcx, [rsp+188h+ActivityId]
0x140051bf5  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x140051bfa  nop
0x140051bfb  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x140051c01  lea     rbx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140051c08  test    al, 1
0x140051c0a  jz      short loc_140051C75
0x140051c0c  mov     eax, [r12]
0x140051c10  mov     dword ptr [rsp+188h+var_130], eax
0x140051c14  lea     rax, [rsp+188h+var_130]
0x140051c19  mov     [rsp+188h+var_100], rax
0x140051c21  mov     [rsp+188h+var_F8], 4
0x140051c2d  lea     rax, [rsp+188h+var_110]
0x140051c32  mov     [rsp+188h+var_168], rax
0x140051c37  mov     r9d, 2
0x140051c3d  lea     rdx, Service_ControllerUserLogoffBegin
0x140051c44  mov     rcx, rbx
0x140051c47  call    McGenEventWrite_EventWriteTransfer
0x140051c4c  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x140051c52  test    al, 1
0x140051c54  jz      short loc_140051C75
0x140051c56  lea     rax, [rsp+188h+var_130]
0x140051c5b  mov     [rsp+188h+var_168], rax
0x140051c60  mov     r9d, 1
0x140051c66  lea     rdx, ISVAPI_ControllerUserLogoffBegin
0x140051c6d  mov     rcx, rbx
0x140051c70  call    McGenEventWrite_EventWriteTransfer
0x140051c75  mov     rcx, [r14+8]
0x140051c79  mov     rax, [rcx]
0x140051c7c  mov     rax, [rax+30h]
0x140051c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051c85  mov     [rsp+188h+var_158], rax
0x140051c8a  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x140051c90  test    al, 1
0x140051c92  jz      short loc_140051CFE
0x140051c94  mov     eax, [r12]
0x140051c98  mov     dword ptr [rsp+188h+var_130], eax
0x140051c9c  lea     rax, [rsp+188h+var_130]
0x140051ca1  mov     [rsp+188h+var_100], rax
0x140051ca9  mov     [rsp+188h+var_F8], 4
0x140051cb5  lea     rax, [rsp+188h+var_110]
0x140051cba  mov     [rsp+188h+var_168], rax
0x140051cbf  mov     r9d, 2
0x140051cc5  lea     rdx, Service_ControllerUserLogoffEnd
0x140051ccc  mov     rcx, rbx
0x140051ccf  call    McGenEventWrite_EventWriteTransfer
0x140051cd4  mov     eax, cs:Microsoft_AppV_SharedPerformanceEnableBits
0x140051cda  test    al, 1
0x140051cdc  jz      short loc_140051CFE
0x140051cde  lea     rax, [rsp+188h+var_130]
0x140051ce3  mov     [rsp+188h+var_168], rax
0x140051ce8  mov     r9d, 1
0x140051cee  lea     rdx, ISVAPI_ControllerUserLogoffEnd
0x140051cf5  mov     rcx, rbx
0x140051cf8  call    McGenEventWrite_EventWriteTransfer
0x140051cfd  nop
0x140051cfe  cmp     byte ptr [rsp+188h+ActivityId.Data1], r13b
0x140051d06  jz      short loc_140051D1B
0x140051d08  lea     rdx, [rsp+188h+ActivityId.Data2]; ActivityId
0x140051d10  mov     ecx, 2; ControlCode
0x140051d15  call    cs:__imp_EventActivityIdControl
0x140051d1b  test    [rsp+188h+var_158], r15
0x140051d20  jnz     loc_140052066
0x140051d26  mov     r15d, 5Ch ; '\'
0x140051d2c  mov     edx, r15d; Ch
0x140051d2f  lea     rbx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x140051d36  mov     rcx, rbx; Str
0x140051d39  call    cs:__imp_strrchr
0x140051d3f  test    rax, rax
0x140051d42  jz      short loc_140051D49
0x140051d44  inc     rax
0x140051d47  jmp     short loc_140051D4C
0x140051d49  mov     rax, rbx
0x140051d4c  mov     rdx, rax; char *
0x140051d4f  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140051d56  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140051d5b  mov     rax, 8000000000h
0x140051d65  test    [rsp+188h+var_158], rax
0x140051d6a  jnz     loc_140051F34
0x140051d70  mov     edx, r15d; Ch
0x140051d73  mov     rcx, rbx; Str
0x140051d76  call    cs:__imp_strrchr
0x140051d7c  test    rax, rax
0x140051d7f  jz      short loc_140051D86
0x140051d81  inc     rax
0x140051d84  jmp     short loc_140051D89
0x140051d86  mov     rax, rbx
0x140051d89  mov     rdx, rax; char *
0x140051d8c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140051d93  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140051d98  mov     rax, 2000000000h
0x140051da2  test    [rsp+188h+var_158], rax
0x140051da7  jnz     loc_140051F34
0x140051dad  mov     edx, r15d; Ch
0x140051db0  mov     rcx, rbx; Str
0x140051db3  call    cs:__imp_strrchr
0x140051db9  test    rax, rax
0x140051dbc  jz      short loc_140051DC3
0x140051dbe  inc     rax
0x140051dc1  jmp     short loc_140051DC6
0x140051dc3  mov     rax, rbx
0x140051dc6  mov     rdx, rax; char *
0x140051dc9  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140051dd0  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140051dd5  mov     rax, [rsp+188h+var_158]
0x140051dda  shr     rax, 20h
0x140051dde  and     al, 1Fh
0x140051de0  cmp     al, 2
0x140051de2  jnz     loc_140051F34
0x140051de8  mov     edx, r15d; Ch
0x140051deb  mov     rcx, rbx; Str
0x140051dee  call    cs:__imp_strrchr
0x140051df4  test    rax, rax
0x140051df7  jz      short loc_140051DFE
0x140051df9  inc     rax
0x140051dfc  jmp     short loc_140051E01
0x140051dfe  mov     rax, rbx
0x140051e01  mov     rdx, rax; char *
0x140051e04  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140051e0b  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140051e10  shl     rax, 34h
0x140051e14  or      eax, 302h
0x140051e19  cmp     dword ptr [rsp+188h+var_158], eax
0x140051e1d  jnz     loc_140051F34
0x140051e23  lea     rdx, aAppvClientHost_1; "AppV::Client::Host::SessionImpl::Logoff"
0x140051e2a  lea     rcx, [rsp+188h+var_110]
0x140051e2f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140051e34  mov     [rsp+188h+var_F0], 0BFh
0x140051e3f  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140051e44  xorps   xmm0, xmm0
0x140051e47  movups  [rsp+188h+var_130], xmm0
0x140051e4c  mov     [rsp+188h+var_120], r13
0x140051e51  mov     [rsp+188h+var_118], r13
0x140051e56  mov     r8d, 4Eh ; 'N'
  ... truncated ...
```
