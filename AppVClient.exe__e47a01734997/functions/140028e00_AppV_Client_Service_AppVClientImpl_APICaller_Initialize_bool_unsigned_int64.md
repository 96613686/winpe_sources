# AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)

- ea: `0x140028e00`
- end: `0x1400293b9`
- name: `?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z`
- size: `1465`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl::APICaller *this, char, unsigned __int64 *)`
- caller_count: `52`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140021630`
- `0x140021840`
- `0x140022090`
- `0x140022890`
- `0x1400235f0`
- `0x1400237d0`
- `0x140023c60`
- `0x140024460`
- `0x1400249a0`
- `0x140024b60`
- `0x140025240`
- `0x140025370`
- `0x140025820`
- `0x140025be0`
- `0x1400260e0`
- `0x140026330`
- `0x140026540`
- `0x140026760`
- `0x140026980`
- `0x140026c00`
- `0x140026f30`
- `0x1400271d0`
- `0x140027500`
- `0x140027750`
- `0x140027930`
- `0x140028330`
- `0x140028520`
- `0x140028710`
- `0x140029570`
- `0x1400297d0`
- `0x140029a10`
- `0x140029d60`
- `0x140029fe0`
- `0x14002a300`
- `0x14002a974`
- `0x14002ac74`
- `0x14002b080`
- `0x14002b460`
- `0x14002be30`
- `0x1400353a0`
- `0x140035710`
- `0x140035c00`
- `0x140035ea0`
- `0x140036290`
- `0x140036df0`
- `0x140036f10`
- `0x140037710`
- `0x140037880`
- `0x140037b00`
- `0x140037eb0`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x1400094bc`
- `0x14000a410`
- `0x140010158`
- `0x1400147fc`
- `0x140018bec`
- `0x1400214c8`
- `0x140028e00`
- `0x1400386f0`
- `0x1400393c4`
- `0x140039e78`
- `0x140039f30`
- `0x140039fac`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x14006a010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x14002925c`
- `KERNEL32!ResetEvent` at `0x14002925c`
- `KERNEL32!GetLastError` at `0x14002926b`
- `KERNEL32!GetLastError` at `0x14002926b`
- `KERNEL32!GetCurrentThreadId` at `0x140029227`
- `KERNEL32!GetCurrentThreadId` at `0x140029227`
- `KERNEL32!LeaveCriticalSection` at `0x14002935e`
- `KERNEL32!LeaveCriticalSection` at `0x14002935e`
- `KERNEL32!EnterCriticalSection` at `0x14002920e`
- `KERNEL32!EnterCriticalSection` at `0x14002920e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028efe`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028f9e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140029082`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400290d9`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028efe`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140028f9e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140029082`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400290d9`
- `ole32!CoImpersonateClient` at `0x140028f42`
- `ole32!CoImpersonateClient` at `0x140028f42`
- `ole32!CoRevertToSelf` at `0x140028fe0`

## string_xrefs

- `0x140028e7e`: `A public API call was rejected because the Client service is in the process of shutting down.`
- `0x140028ef7`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140028f0e`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140028f97`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140028fae`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x14002907b`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400290d2`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400290e9`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140029149`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140028e4f`: `AppV::Client::Service::AppVClientImpl::APICaller::Initialize`
- `0x140029275`: `AppV::Client::Service::AppVClientImpl::APICaller::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
        AppV::Client::Service::AppVClientImpl::APICaller *this,
        char a2,
        unsigned __int64 *a3)
{
  char *v7; // rax
  const char *v8; // rax
  HRESULT v9; // eax
  __int64 v10; // r8
  unsigned __int64 v11; // rbx
  char *v12; // rax
  const char *v13; // rax
  _QWORD *v14; // rax
  struct ATL::CAccessToken *v15; // rdx
  unsigned int v16; // r8d
  AppV::Client::Service::AppVClientImpl::APICaller *v17; // rcx
  struct ATL::CAccessToken *v18; // rdx
  const struct ATL::CAccessToken *v19; // rdx
  int v20; // eax
  char *v21; // rax
  const char *v22; // rax
  struct ATL::CAccessToken *v23; // rdx
  char v24; // bl
  char *v25; // rax
  const char *v26; // rax
  __int64 v27; // r8
  unsigned __int64 v28; // rax
  __int64 v29; // r8
  int v30; // ecx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rbx
  void (__fastcall ***v34)(_QWORD, __int64); // rcx
  HRESULT v35; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v36; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v37[24]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h]
  __int128 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int128 v42; // [rsp+80h] [rbp-80h] BYREF
  HRESULT *v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+98h] [rbp-68h]
  int v45; // [rsp+A0h] [rbp-60h]
  __int128 v46; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  void **v49; // [rsp+C8h] [rbp-38h] BYREF
  char v50[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v51[16]; // [rsp+F8h] [rbp-8h] BYREF
  HRESULT *v52; // [rsp+108h] [rbp+8h]
  __int64 v53; // [rsp+110h] [rbp+10h]
  __int128 *v54; // [rsp+118h] [rbp+18h]
  __int64 v55; // [rsp+120h] [rbp+20h]

  *a3 = 0;
  if ( *(_BYTE *)this )
    return 0;
  if ( AppV::Client::Service::AppVClientImpl::st_allowCalls )
  {
    v9 = CoImpersonateClient();
    v11 = (unsigned int)v9;
    if ( v9 < 0 )
    {
      if ( (Microsoft_AppV_ClientEnableBits & 0x40) != 0 )
      {
        v35 = v9;
        v43 = &v35;
        v44 = 4;
        McGenEventWrite_EventWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_Context,
          APPV_CLIENT_Evt_CoImpersonateFailed,
          v10,
          2,
          &v42);
      }
      v12 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v12 )
        v13 = v12 + 1;
      else
        v13 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      *a3 = v11
          | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v13) << 52)
          | 0x332300000000LL;
      return (unsigned int)v11;
    }
    v14 = operator new(0x18u);
    *(_QWORD *)&v39 = v14;
    v17 = (AppV::Client::Service::AppVClientImpl::APICaller *)&appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,long (*)(void),>>::`vftable';
    *v14 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,long (*)(void),>>::`vftable';
    v14[1] = CoRevertToSelf;
    v36 = v14;
    if ( a2 )
    {
      *(_QWORD *)v37 = &ATL::CAccessToken::`vftable';
      *(_OWORD *)&v37[8] = 0;
      v38 = 0;
      if ( !softgrid::shared::get_effective_impersonation_token((softgrid::shared *)v37, v15, v16) )
      {
        *(_QWORD *)v37 = &ATL::CAccessToken::`vftable';
        ATL::CAccessToken::Clear((ATL::CAccessToken *)v37);
LABEL_27:
        v25 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
        if ( v25 )
          v26 = v25 + 1;
        else
          v26 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
        *a3 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v26) << 52)
            | 0x340300000102LL;
        if ( (Microsoft_AppV_ClientEnableBits & 0x40) != 0 )
          McGenEventWrite_EventWriteTransfer(
            PROVIDER_MICROSOFT_APPV_CLIENT_Context,
            APPV_CLIENT_Evt_APIAccessDenied,
            v27,
            1,
            &v39);
        LODWORD(v11) = -2147024891;
LABEL_50:
        appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v36);
        return (unsigned int)v11;
      }
      if ( softgrid::shared::token_is_admin((softgrid::shared *)v37, v18) )
      {
        *(_QWORD *)v37 = &ATL::CAccessToken::`vftable';
        ATL::CAccessToken::Clear((ATL::CAccessToken *)v37);
      }
      else
      {
        if ( softgrid::shared::token_is_system((softgrid::shared *)v37, v19)
          || (v24 = 0, softgrid::shared::token_is_networkservice((softgrid::shared *)v37, v23)) )
        {
          v24 = 1;
        }
        *(_QWORD *)v37 = &ATL::CAccessToken::`vftable';
        ATL::CAccessToken::Clear((ATL::CAccessToken *)v37);
        if ( !v24 )
          goto LABEL_27;
      }
    }
    v20 = AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel(v17);
    v11 = (unsigned int)v20;
    if ( v20 >= 0 )
    {
      v28 = AppV::Client::Service::AppVClientImpl::AcquireUserSession();
      v11 = v28;
      if ( (v28 & 0x8000000000LL) != 0 )
      {
        *(_QWORD *)v37 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
        *(_QWORD *)&v37[16] = &AppV::Client::Service::AppVClientImpl::APICaller::st_lock;
        EnterCriticalSection(&AppV::Client::Service::AppVClientImpl::APICaller::st_lock);
        v30 = qword_1400B0D68 + 1;
        LODWORD(qword_1400B0D68) = v30;
        if ( v30 == 1 )
        {
          HIDWORD(qword_1400B0D68) = GetCurrentThreadId();
          v30 = qword_1400B0D68;
        }
        v37[8] = 1;
        if ( ++AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers == 1 )
        {
          if ( !ResetEvent(AppV::Client::Service::AppVClientImpl::APICaller::st_callersIdle) )
          {
            LODWORD(v39) = GetLastError();
            std::string::string(v51, "AppV::Client::Service::AppVClientImpl::APICaller::Initialize");
            LODWORD(v54) = 448;
            AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance();
            v42 = 0;
            v43 = 0;
            v44 = 0;
            std::wstring::_Construct<1,wchar_t const *>(
              &v42,
              L"Failed to reset idle API callers event, error = %1%",
              51);
            v32 = AppV::Log::fmt(v31, &v49, &v42);
            v33 = AppV::LogFormatter::operator%<unsigned long>(v32, &v39);
            v46 = 0;
            v47 = 0;
            v48 = 0;
            std::wstring::_Construct<1,wchar_t const *>(&v46, L"Client", 6);
            AppV::DecoratedLog::operator()(v51, 8, &v46, v33);
            std::wstring::~wstring(&v46);
            v49 = &AppV::LogFormatter::`vftable';
            std::wstring::~wstring(v50);
            std::wstring::~wstring(&v42);
            std::string::~string(v51);
          }
          v30 = qword_1400B0D68;
        }
        LODWORD(qword_1400B0D68) = v30 - 1;
        if ( v30 == 1 )
          qword_1400B0D68 = 0;
        LeaveCriticalSection(&AppV::Client::Service::AppVClientImpl::APICaller::st_lock);
        *(_BYTE *)this = 1;
        v34 = (void (__fastcall ***)(_QWORD, __int64))v36;
        v36 = 0;
        if ( v34 )
          (**v34)(v34, 1);
        LODWORD(v11) = 0;
      }
      else
      {
        if ( (Microsoft_AppV_ClientEnableBits & 0x10) != 0 )
        {
          v35 = HIDWORD(v28);
          LODWORD(v39) = v28;
          v52 = &v35;
          v53 = 4;
          v54 = &v39;
          v55 = 4;
          McGenEventWrite_EventWriteTransfer(
            PROVIDER_MICROSOFT_APPV_CLIENT_Context,
            APPV_CLIENT_Evt_APILogonFailed,
            v29,
            3,
            v51);
        }
        *a3 = v11;
        LODWORD(v11) = -2147467259;
      }
    }
    else
    {
      v21 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v21 )
        v22 = v21 + 1;
      else
        v22 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      *a3 = v11
          | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v22) << 52)
          | 0x352300000000LL;
    }
    goto LABEL_50;
  }
  std::string::string(&v42, "AppV::Client::Service::AppVClientImpl::APICaller::Initialize");
  v45 = 402;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    &v39,
    L"A public API call was rejected because the Client service is in the process of shutting down.",
    93);
  memset(v37, 0, sizeof(v37));
  v38 = 0;
  std::wstring::_Construct<1,wchar_t const *>(v37, L"Client", 6);
  AppV::DecoratedLog::operator()(&v42, 8, v37, &v39);
  std::wstring::~wstring(v37);
  std::wstring::~wstring(&v39);
  std::string::~string(&v42);
  v7 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
  if ( v7 )
    v8 = v7 + 1;
  else
    v8 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
  *a3 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v8) << 52)
      | 0x320300000101LL;
  return 2147500037LL;
}

```

## disassembly

```asm
0x140028e00  mov     [rsp-8+arg_8], rbx
0x140028e05  push    rbp
0x140028e06  push    rsi
0x140028e07  push    rdi
0x140028e08  push    r14
0x140028e0a  push    r15
0x140028e0c  lea     rbp, [rsp-30h]
0x140028e11  sub     rsp, 130h
0x140028e18  mov     rax, cs:__security_cookie
0x140028e1f  xor     rax, rsp
0x140028e22  mov     [rbp+50h+var_28], rax
0x140028e26  mov     rdi, r8
0x140028e29  mov     r14b, dl
0x140028e2c  mov     rsi, rcx
0x140028e2f  xor     r15d, r15d
0x140028e32  mov     [r8], r15
0x140028e35  cmp     [rcx], r15b
0x140028e38  jz      short loc_140028E41
0x140028e3a  xor     eax, eax
0x140028e3c  jmp     loc_140029396
0x140028e41  mov     al, cs:?st_allowCalls@AppVClientImpl@Service@Client@AppV@@0_NC; bool volatile AppV::Client::Service::AppVClientImpl::st_allowCalls
0x140028e47  test    al, al
0x140028e49  jnz     loc_140028F42
0x140028e4f  lea     rdx, aAppvClientServ_25; "AppV::Client::Service::AppVClientImpl::"...
0x140028e56  lea     rcx, [rbp+50h+var_D0]
0x140028e5a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140028e5f  mov     [rbp+50h+var_B0], 192h
0x140028e66  xorps   xmm0, xmm0
0x140028e69  movups  [rsp+150h+var_F0], xmm0
0x140028e6e  mov     [rsp+150h+var_E0], r15
0x140028e73  mov     [rsp+150h+var_D8], r15
0x140028e78  mov     r8d, 5Dh ; ']'
0x140028e7e  lea     rdx, aAPublicApiCall; "A public API call was rejected because "...
0x140028e85  lea     rcx, [rsp+150h+var_F0]
0x140028e8a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140028e8f  nop
0x140028e90  xorps   xmm0, xmm0
0x140028e93  movups  [rsp+150h+var_110], xmm0
0x140028e98  mov     [rsp+150h+var_100], r15
0x140028e9d  mov     [rsp+150h+var_F8], r15
0x140028ea2  mov     r8d, 6
0x140028ea8  lea     rdx, aClient; "Client"
0x140028eaf  lea     rcx, [rsp+150h+var_110]
0x140028eb4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140028eb9  nop
0x140028eba  lea     r9, [rsp+150h+var_F0]
0x140028ebf  lea     r8, [rsp+150h+var_110]
0x140028ec4  mov     edx, 8
0x140028ec9  lea     rcx, [rbp+50h+var_D0]
0x140028ecd  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140028ed2  nop
0x140028ed3  lea     rcx, [rsp+150h+var_110]
0x140028ed8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028edd  nop
0x140028ede  lea     rcx, [rsp+150h+var_F0]
0x140028ee3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140028ee8  nop
0x140028ee9  lea     rcx, [rbp+50h+var_D0]
0x140028eed  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140028ef2  mov     edx, 5Ch ; '\'; Ch
0x140028ef7  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140028efe  call    cs:__imp_strrchr
0x140028f04  test    rax, rax
0x140028f07  jz      short loc_140028F0E
0x140028f09  inc     rax
0x140028f0c  jmp     short loc_140028F15
0x140028f0e  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140028f15  mov     rdx, rax; char *
0x140028f18  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140028f1f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140028f24  shl     rax, 34h
0x140028f28  mov     rcx, 320300000101h
0x140028f32  or      rax, rcx
0x140028f35  mov     [rdi], rax
0x140028f38  mov     eax, 80004005h
0x140028f3d  jmp     loc_140029396
0x140028f42  call    cs:__imp_CoImpersonateClient
0x140028f48  mov     ebx, eax
0x140028f4a  test    eax, eax
0x140028f4c  jns     loc_140028FE0
0x140028f52  test    cs:Microsoft_AppV_ClientEnableBits, 40h
0x140028f59  jz      short loc_140028F92
0x140028f5b  mov     [rsp+150h+var_120], ebx
0x140028f5f  lea     rax, [rsp+150h+var_120]
0x140028f64  mov     [rbp+50h+var_C0], rax
0x140028f68  mov     [rbp+50h+var_B8], 4
0x140028f70  lea     rax, [rbp+50h+var_D0]
0x140028f74  mov     [rsp+150h+var_130], rax
0x140028f79  mov     r9d, 2
0x140028f7f  lea     rdx, APPV_CLIENT_Evt_CoImpersonateFailed
0x140028f86  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x140028f8d  call    McGenEventWrite_EventWriteTransfer
0x140028f92  mov     edx, 5Ch ; '\'; Ch
0x140028f97  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140028f9e  call    cs:__imp_strrchr
0x140028fa4  test    rax, rax
0x140028fa7  jz      short loc_140028FAE
0x140028fa9  inc     rax
0x140028fac  jmp     short loc_140028FB5
0x140028fae  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140028fb5  mov     rdx, rax; char *
0x140028fb8  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140028fbf  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140028fc4  shl     rax, 34h
0x140028fc8  or      rax, rbx
0x140028fcb  mov     rcx, 332300000000h
0x140028fd5  or      rax, rcx
0x140028fd8  mov     [rdi], rax
0x140028fdb  jmp     loc_140029394
0x140028fe0  mov     rbx, cs:__imp_CoRevertToSelf
0x140028fe7  mov     ecx, 18h; Size
0x140028fec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140028ff1  mov     qword ptr [rsp+150h+var_F0], rax
0x140028ff6  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P6AJXZ$$V@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,long (*)(void),>>::`vftable'
0x140028ffd  mov     [rax], rcx
0x140029000  mov     [rax+8], rbx
0x140029004  mov     [rsp+150h+var_118], rax
0x140029009  test    r14b, r14b
0x14002900c  jz      short loc_140029067
0x14002900e  lea     r14, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x140029015  mov     qword ptr [rsp+150h+var_110], r14
0x14002901a  xorps   xmm0, xmm0
0x14002901d  movdqu  [rsp+150h+var_110+8], xmm0
0x140029023  mov     [rsp+150h+var_F8], r15
0x140029028  lea     rcx, [rsp+150h+var_110]; this
0x14002902d  call    ?get_effective_impersonation_token@shared@softgrid@@YA_NAEAVCAccessToken@ATL@@K@Z; softgrid::shared::get_effective_impersonation_token(ATL::CAccessToken &,ulong)
0x140029032  test    al, al
0x140029034  jnz     short loc_14002904A
0x140029036  mov     qword ptr [rsp+150h+var_110], r14
0x14002903b  lea     rcx, [rsp+150h+var_110]; this
0x140029040  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x140029045  jmp     loc_1400290CD
0x14002904a  lea     rcx, [rsp+150h+var_110]; this
0x14002904f  call    ?token_is_admin@shared@softgrid@@YA_NAEAVCAccessToken@ATL@@@Z; softgrid::shared::token_is_admin(ATL::CAccessToken &)
0x140029054  test    al, al
0x140029056  jz      short loc_140029099
0x140029058  mov     qword ptr [rsp+150h+var_110], r14
0x14002905d  lea     rcx, [rsp+150h+var_110]; this
0x140029062  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x140029067  call    ?VerifyImpersonationLevel@APICaller@AppVClientImpl@Service@Client@AppV@@AEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::VerifyImpersonationLevel(void)
0x14002906c  mov     ebx, eax
0x14002906e  test    eax, eax
0x140029070  jns     loc_14002917B
0x140029076  mov     edx, 5Ch ; '\'; Ch
0x14002907b  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140029082  call    cs:__imp_strrchr
0x140029088  test    rax, rax
0x14002908b  jz      loc_140029149
0x140029091  inc     rax
0x140029094  jmp     loc_140029150
0x140029099  lea     rcx, [rsp+150h+var_110]; this
0x14002909e  call    ?token_is_system@shared@softgrid@@YA_NAEBVCAccessToken@ATL@@@Z; softgrid::shared::token_is_system(ATL::CAccessToken const &)
0x1400290a3  test    al, al
0x1400290a5  jnz     short loc_1400290B8
0x1400290a7  lea     rcx, [rsp+150h+var_110]; this
0x1400290ac  call    ?token_is_networkservice@shared@softgrid@@YA_NAEAVCAccessToken@ATL@@@Z; softgrid::shared::token_is_networkservice(ATL::CAccessToken &)
0x1400290b1  test    al, al
0x1400290b3  mov     bl, r15b
0x1400290b6  jz      short loc_1400290BA
0x1400290b8  mov     bl, 1
0x1400290ba  mov     qword ptr [rsp+150h+var_110], r14
0x1400290bf  lea     rcx, [rsp+150h+var_110]; this
0x1400290c4  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x1400290c9  test    bl, bl
0x1400290cb  jnz     short loc_140029067
0x1400290cd  mov     edx, 5Ch ; '\'; Ch
0x1400290d2  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400290d9  call    cs:__imp_strrchr
0x1400290df  test    rax, rax
0x1400290e2  jz      short loc_1400290E9
0x1400290e4  inc     rax
0x1400290e7  jmp     short loc_1400290F0
0x1400290e9  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400290f0  mov     rdx, rax; char *
0x1400290f3  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400290fa  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400290ff  shl     rax, 34h
0x140029103  mov     rcx, 340300000102h
0x14002910d  or      rax, rcx
0x140029110  mov     [rdi], rax
0x140029113  test    cs:Microsoft_AppV_ClientEnableBits, 40h
0x14002911a  jz      short loc_14002913F
0x14002911c  lea     rax, [rsp+150h+var_F0]
0x140029121  mov     [rsp+150h+var_130], rax
0x140029126  mov     r9d, 1
0x14002912c  lea     rdx, APPV_CLIENT_Evt_APIAccessDenied
0x140029133  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x14002913a  call    McGenEventWrite_EventWriteTransfer
0x14002913f  mov     ebx, 80070005h
0x140029144  jmp     loc_14002938A
0x140029149  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140029150  mov     rdx, rax; char *
0x140029153  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14002915a  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14002915f  shl     rax, 34h
0x140029163  or      rax, rbx
0x140029166  mov     rcx, 352300000000h
0x140029170  or      rax, rcx
0x140029173  mov     [rdi], rax
0x140029176  jmp     loc_14002938A
0x14002917b  call    ?AcquireUserSession@AppVClientImpl@Service@Client@AppV@@CA_KXZ; AppV::Client::Service::AppVClientImpl::AcquireUserSession(void)
0x140029180  mov     rbx, rax
0x140029183  bt      rax, 27h ; '''
0x140029188  jb      short loc_1400291F3
0x14002918a  test    cs:Microsoft_AppV_ClientEnableBits, 10h
0x140029191  jz      short loc_1400291E6
0x140029193  mov     dword ptr [rsp+150h+var_F0], ebx
0x140029197  mov     rcx, rax
0x14002919a  shr     rcx, 20h
0x14002919e  mov     [rsp+150h+var_120], ecx
0x1400291a2  lea     rax, [rsp+150h+var_120]
0x1400291a7  mov     [rbp+50h+var_48], rax
0x1400291ab  mov     [rbp+50h+var_40], 4
0x1400291b3  lea     rax, [rsp+150h+var_F0]
0x1400291b8  mov     [rbp+50h+var_38], rax
0x1400291bc  mov     [rbp+50h+var_30], 4
0x1400291c4  lea     rax, [rbp+50h+var_58]
0x1400291c8  mov     [rsp+150h+var_130], rax
0x1400291cd  mov     r9d, 3
0x1400291d3  lea     rdx, APPV_CLIENT_Evt_APILogonFailed
0x1400291da  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x1400291e1  call    McGenEventWrite_EventWriteTransfer
0x1400291e6  mov     [rdi], rbx
0x1400291e9  mov     ebx, 80004005h
0x1400291ee  jmp     loc_14002938A
0x1400291f3  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400291fa  mov     qword ptr [rsp+150h+var_110], rax
0x1400291ff  lea     rdi, ?st_lock@APICaller@AppVClientImpl@Service@Client@AppV@@0Vcritical_section@shared@softricity@@A; softricity::shared::critical_section AppV::Client::Service::AppVClientImpl::APICaller::st_lock
0x140029206  mov     [rsp+150h+var_100], rdi
0x14002920b  mov     rcx, rdi; lpCriticalSection
0x14002920e  call    cs:__imp_EnterCriticalSection
0x140029214  mov     ecx, dword ptr cs:qword_1400B0D68
0x14002921a  inc     ecx
0x14002921c  mov     dword ptr cs:qword_1400B0D68, ecx
0x140029222  cmp     ecx, 1
0x140029225  jnz     short loc_140029239
0x140029227  call    cs:__imp_GetCurrentThreadId
0x14002922d  mov     dword ptr cs:qword_1400B0D68+4, eax
0x140029233  mov     ecx, dword ptr cs:qword_1400B0D68
0x140029239  mov     byte ptr [rsp+150h+var_110+8], 1
0x14002923e  mov     eax, cs:?st_activeCallers@APICaller@AppVClientImpl@Service@Client@AppV@@0KA; ulong AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers
0x140029244  inc     eax
0x140029246  mov     cs:?st_activeCallers@APICaller@AppVClientImpl@Service@Client@AppV@@0KA, eax; ulong AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers
0x14002924c  cmp     eax, 1
0x14002924f  jnz     loc_140029349
0x140029255  mov     rcx, cs:?st_callersIdle@APICaller@AppVClientImpl@Service@Client@AppV@@0Vevent@shared@softricity@@A; hEvent
0x14002925c  call    cs:__imp_ResetEvent
0x140029262  cmp     eax, 1
0x140029265  jz      loc_140029343
0x14002926b  call    cs:__imp_GetLastError
0x140029271  mov     dword ptr [rsp+150h+var_F0], eax
0x140029275  lea     rdx, aAppvClientServ_25; "AppV::Client::Service::AppVClientImpl::"...
0x14002927c  lea     rcx, [rbp+50h+var_58]
0x140029280  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029285  mov     dword ptr [rbp+50h+var_38], 1C0h
0x14002928c  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140029291  xorps   xmm0, xmm0
0x140029294  movups  [rbp+50h+var_D0], xmm0
0x140029298  mov     [rbp+50h+var_C0], r15
0x14002929c  mov     [rbp+50h+var_B8], r15
0x1400292a0  mov     r8d, 33h ; '3'
0x1400292a6  lea     rdx, aFailedToResetI; "Failed to reset idle API callers event,"...
0x1400292ad  lea     rcx, [rbp+50h+var_D0]
0x1400292b1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400292b6  nop
0x1400292b7  lea     r8, [rbp+50h+var_D0]
0x1400292bb  lea     rdx, [rbp+50h+var_88]
0x1400292bf  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400292c4  nop
0x1400292c5  lea     rdx, [rsp+150h+var_F0]
0x1400292ca  mov     rcx, rax
0x1400292cd  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400292d2  mov     rbx, rax
0x1400292d5  xorps   xmm0, xmm0
0x1400292d8  movups  [rbp+50h+var_A8], xmm0
0x1400292dc  mov     [rbp+50h+var_98], r15
0x1400292e0  mov     [rbp+50h+var_90], r15
0x1400292e4  mov     r8d, 6
0x1400292ea  lea     rdx, aClient; "Client"
0x1400292f1  lea     rcx, [rbp+50h+var_A8]
0x1400292f5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400292fa  nop
0x1400292fb  mov     r9, rbx
0x1400292fe  lea     r8, [rbp+50h+var_A8]
0x140029302  mov     edx, 8
0x140029307  lea     rcx, [rbp+50h+var_58]
0x14002930b  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140029310  nop
0x140029311  lea     rcx, [rbp+50h+var_A8]
0x140029315  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002931a  nop
0x14002931b  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140029322  mov     [rbp+50h+var_88], rax
0x140029326  lea     rcx, [rbp+50h+var_78]
0x14002932a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002932f  nop
0x140029330  lea     rcx, [rbp+50h+var_D0]
0x140029334  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029339  nop
0x14002933a  lea     rcx, [rbp+50h+var_58]
  ... truncated ...
```
