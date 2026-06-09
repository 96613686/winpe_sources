# AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount(void)

- ea: `0x140050ec0`
- end: `0x140051322`
- name: `?DecrementUserProfileRefCount@SessionImpl@Host@Client@AppV@@AEAA_KXZ`
- size: `1122`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::SessionImpl *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400518c0`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x140050bd4`
- `0x140050ec0`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x140050fd1`
- `ADVAPI32!DuplicateTokenEx` at `0x140050fd1`
- `KERNEL32!CloseHandle` at `0x1400512f8`
- `KERNEL32!CloseHandle` at `0x1400512f8`
- `KERNEL32!GetLastError` at `0x140050fdf`
- `KERNEL32!GetLastError` at `0x1400511bf`
- `KERNEL32!GetLastError` at `0x140050fdf`
- `KERNEL32!GetLastError` at `0x1400511bf`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140050ff3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400511d4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140050ff3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400511d4`
- `USERENV!UnloadUserProfile` at `0x1400511b1`
- `USERENV!UnloadUserProfile` at `0x1400511b1`

## string_xrefs

- `0x140050fec`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x140051003`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x1400511cd`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x1400511e4`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x140051246`: `Call to ::UnloadUserProfile() from PackageConfigManagerImpl::decrement_user_profile_ref_count() failed with error %1%`
- `0x140051062`: `Call to ::DuplicateTokenEx() from SessionImpl::DecrementUserProfileRefCount() failed with error %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
unsigned __int64 __fastcall AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount(
        AppV::Client::Host::SessionImpl *this)
{
  __int64 v3; // rbx
  char *v4; // rax
  const char *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rbx
  char *v11; // rax
  const char *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned __int64 v17; // rdi
  DWORD LastError; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-61h] BYREF
  HANDLE hObject[2]; // [rsp+40h] [rbp-59h] BYREF
  __int128 v21; // [rsp+50h] [rbp-49h] BYREF
  __int128 v22; // [rsp+60h] [rbp-39h]
  __int128 v23; // [rsp+70h] [rbp-29h] BYREF
  __int128 v24; // [rsp+80h] [rbp-19h]
  char *v25[4]; // [rsp+90h] [rbp-9h] BYREF
  int v26; // [rsp+B0h] [rbp+17h]
  _QWORD v27[2]; // [rsp+B8h] [rbp+1Fh] BYREF
  char *v28[4]; // [rsp+C8h] [rbp+2Fh] BYREF

  if ( *((_QWORD *)this + 5) == -1 )
  {
    std::string::string(v25, "AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount");
    v26 = 298;
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v23,
      L"Warning: SessionImpl::DecrementUserProfileRefCount() ignoring request to unload user profile because the user prof"
       "ile handle is invalid.",
      0x88u);
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v21, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v25, 4, (int)&v21, (__int64)&v23);
    std::wstring::~wstring((char **)&v21);
    std::wstring::~wstring((char **)&v23);
    std::string::~string(v25);
    return 0x8000000000LL;
  }
  else
  {
    v19 = 0x8000000000LL;
    hObject[0] = 0;
    if ( DuplicateTokenEx(**((HANDLE **)this + 3), 0xEu, 0, SecurityImpersonation, TokenImpersonation, hObject) )
    {
      v10 = hObject[0];
      hObject[1] = hObject[0];
      std::string::string(v25, "AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount");
      v26 = 313;
      v21 = 0;
      v22 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v21,
        L"Calling ::UnloadUserProfile() from SessionImpl::DecrementUserProfileRefCount().",
        0x4Fu);
      v23 = 0;
      v24 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v23, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v25, 4, (int)&v23, (__int64)&v21);
      std::wstring::~wstring((char **)&v23);
      std::wstring::~wstring((char **)&v21);
      std::string::~string(v25);
      if ( UnloadUserProfile(**((HANDLE **)this + 3), *((HANDLE *)this + 5)) )
      {
        *((_QWORD *)this + 5) = -1;
      }
      else
      {
        LastError = GetLastError();
        v11 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
        if ( v11 )
          v12 = v11 + 1;
        else
          v12 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
        v19 = LastError
            | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v12) << 52)
            | 0x272E00000000LL;
        std::string::string(v25, "AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount");
        v26 = 318;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v13);
        v21 = 0;
        v22 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v21,
          L"Call to ::UnloadUserProfile() from PackageConfigManagerImpl::decrement_user_profile_ref_count() failed with error %1%",
          0x75u);
        v15 = AppV::Log::fmt(v14, v27, &v21);
        v16 = AppV::LogFormatter::operator%<unsigned long>(v15, (__int64)&LastError);
        v23 = 0;
        v24 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v23, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v25, 1, (int)&v23, v16);
        std::wstring::~wstring((char **)&v23);
        v27[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v28);
        std::wstring::~wstring((char **)&v21);
        std::string::~string(v25);
      }
      v17 = v19;
      if ( v10 )
        CloseHandle(v10);
      return v17;
    }
    else
    {
      v3 = GetLastError();
      v4 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
      if ( v4 )
        v5 = v4 + 1;
      else
        v5 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
      v19 = v3
          | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v5) << 52)
          | 0x262E00000000LL;
      std::string::string(v25, "AppV::Client::Host::SessionImpl::DecrementUserProfileRefCount");
      v26 = 308;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v6);
      v21 = 0;
      v22 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v21,
        L"Call to ::DuplicateTokenEx() from SessionImpl::DecrementUserProfileRefCount() failed with error %1%",
        0x63u);
      v8 = AppV::Log::fmt(v7, v27, &v21);
      v9 = AppV::LogFormatter::operator%<unsigned __int64>(v8, &v19);
      v23 = 0;
      v24 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v23, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v25, 1, (int)&v23, v9);
      std::wstring::~wstring((char **)&v23);
      v27[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v28);
      std::wstring::~wstring((char **)&v21);
      std::string::~string(v25);
      return v19;
    }
  }
}

```

## disassembly

```asm
0x140050ec0  mov     [rsp-8+arg_8], rbx
0x140050ec5  mov     [rsp-8+arg_10], rdi
0x140050eca  push    rbp
0x140050ecb  lea     rbp, [rsp-57h]
0x140050ed0  sub     rsp, 0F0h
0x140050ed7  mov     rax, cs:__security_cookie
0x140050ede  xor     rax, rsp
0x140050ee1  mov     [rbp+57h+var_8], rax
0x140050ee5  mov     rdi, rcx
0x140050ee8  cmp     qword ptr [rcx+28h], 0FFFFFFFFFFFFFFFFh
0x140050eed  jnz     loc_140050F99
0x140050ef3  lea     rdx, aAppvClientHost_27; "AppV::Client::Host::SessionImpl::Decrem"...
0x140050efa  lea     rcx, [rbp+57h+var_60]
0x140050efe  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140050f03  mov     [rbp+57h+var_40], 12Ah
0x140050f0a  xorps   xmm0, xmm0
0x140050f0d  movups  [rbp+57h+var_80], xmm0
0x140050f11  xorps   xmm1, xmm1
0x140050f14  movdqu  [rbp+57h+var_70], xmm1
0x140050f19  mov     r8d, 88h
0x140050f1f  lea     rdx, aWarningSession_0; "Warning: SessionImpl::DecrementUserProf"...
0x140050f26  lea     rcx, [rbp+57h+var_80]
0x140050f2a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140050f2f  nop
0x140050f30  xorps   xmm0, xmm0
0x140050f33  movups  [rbp+57h+var_A0], xmm0
0x140050f37  xorps   xmm1, xmm1
0x140050f3a  movdqu  [rbp+57h+var_90], xmm1
0x140050f3f  mov     r8d, 6
0x140050f45  lea     rdx, aClient; "Client"
0x140050f4c  lea     rcx, [rbp+57h+var_A0]
0x140050f50  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140050f55  nop
0x140050f56  lea     r9, [rbp+57h+var_80]
0x140050f5a  lea     r8, [rbp+57h+var_A0]
0x140050f5e  mov     edx, 4
0x140050f63  lea     rcx, [rbp+57h+var_60]
0x140050f67  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140050f6c  nop
0x140050f6d  lea     rcx, [rbp+57h+var_A0]
0x140050f71  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050f76  nop
0x140050f77  lea     rcx, [rbp+57h+var_80]
0x140050f7b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050f80  nop
0x140050f81  lea     rcx, [rbp+57h+var_60]
0x140050f85  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140050f8a  mov     rax, 8000000000h
0x140050f94  jmp     loc_140051301
0x140050f99  mov     rax, 8000000000h
0x140050fa3  mov     [rbp+57h+var_B8], rax
0x140050fa7  mov     [rbp+57h+hObject], 0
0x140050faf  mov     rcx, [rcx+18h]
0x140050fb3  lea     rax, [rbp+57h+hObject]
0x140050fb7  mov     [rsp+0F0h+phNewToken], rax; phNewToken
0x140050fbc  mov     r9d, 2; ImpersonationLevel
0x140050fc2  mov     [rsp+0F0h+TokenType], r9d; TokenType
0x140050fc7  xor     r8d, r8d; lpTokenAttributes
0x140050fca  lea     edx, [r9+0Ch]; dwDesiredAccess
0x140050fce  mov     rcx, [rcx]; hExistingToken
0x140050fd1  call    cs:__imp_DuplicateTokenEx
0x140050fd7  test    eax, eax
0x140050fd9  jnz     loc_140051107
0x140050fdf  call    cs:__imp_GetLastError
0x140050fe5  mov     ebx, eax
0x140050fe7  mov     edx, 5Ch ; '\'; Ch
0x140050fec  lea     rcx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x140050ff3  call    cs:__imp_strrchr
0x140050ff9  test    rax, rax
0x140050ffc  jz      short loc_140051003
0x140050ffe  inc     rax
0x140051001  jmp     short loc_14005100A
0x140051003  lea     rax, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x14005100a  mov     rdx, rax; char *
0x14005100d  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140051014  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140051019  shl     rax, 34h
0x14005101d  or      rax, rbx
0x140051020  mov     rcx, 262E00000000h
0x14005102a  or      rax, rcx
0x14005102d  mov     [rbp+57h+var_B8], rax
0x140051031  lea     rdx, aAppvClientHost_27; "AppV::Client::Host::SessionImpl::Decrem"...
0x140051038  lea     rcx, [rbp+57h+var_60]
0x14005103c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140051041  mov     [rbp+57h+var_40], 134h
0x140051048  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005104d  xorps   xmm0, xmm0
0x140051050  movups  [rbp+57h+var_A0], xmm0
0x140051054  xorps   xmm1, xmm1
0x140051057  movdqu  [rbp+57h+var_90], xmm1
0x14005105c  mov     r8d, 63h ; 'c'
0x140051062  lea     rdx, aCallToDuplicat; "Call to ::DuplicateTokenEx() from Sessi"...
0x140051069  lea     rcx, [rbp+57h+var_A0]
0x14005106d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140051072  nop
0x140051073  lea     r8, [rbp+57h+var_A0]
0x140051077  lea     rdx, [rbp+57h+var_38]
0x14005107b  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140051080  nop
0x140051081  lea     rdx, [rbp+57h+var_B8]
0x140051085  mov     rcx, rax
0x140051088  call    ??$?L_K@LogFormatter@AppV@@QEAAAEAV01@AEA_K@Z; AppV::LogFormatter::operator%<unsigned __int64>(unsigned __int64 &)
0x14005108d  mov     rbx, rax
0x140051090  xorps   xmm0, xmm0
0x140051093  movups  [rbp+57h+var_80], xmm0
0x140051097  xorps   xmm1, xmm1
0x14005109a  movdqu  [rbp+57h+var_70], xmm1
0x14005109f  mov     r8d, 6
0x1400510a5  lea     rdx, aClient; "Client"
0x1400510ac  lea     rcx, [rbp+57h+var_80]
0x1400510b0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400510b5  nop
0x1400510b6  mov     r9, rbx
0x1400510b9  lea     r8, [rbp+57h+var_80]
0x1400510bd  mov     edx, 1
0x1400510c2  lea     rcx, [rbp+57h+var_60]
0x1400510c6  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400510cb  nop
0x1400510cc  lea     rcx, [rbp+57h+var_80]
0x1400510d0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400510d5  nop
0x1400510d6  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400510dd  mov     [rbp+57h+var_38], rax
0x1400510e1  lea     rcx, [rbp+57h+var_28]
0x1400510e5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400510ea  nop
0x1400510eb  lea     rcx, [rbp+57h+var_A0]
0x1400510ef  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400510f4  nop
0x1400510f5  lea     rcx, [rbp+57h+var_60]
0x1400510f9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400510fe  mov     rax, [rbp+57h+var_B8]
0x140051102  jmp     loc_140051301
0x140051107  mov     rbx, [rbp+57h+hObject]
0x14005110b  mov     [rbp+57h+var_A8], rbx
0x14005110f  lea     rdx, aAppvClientHost_27; "AppV::Client::Host::SessionImpl::Decrem"...
0x140051116  lea     rcx, [rbp+57h+var_60]
0x14005111a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005111f  mov     [rbp+57h+var_40], 139h
0x140051126  xorps   xmm0, xmm0
0x140051129  movups  [rbp+57h+var_A0], xmm0
0x14005112d  xorps   xmm1, xmm1
0x140051130  movdqu  [rbp+57h+var_90], xmm1
0x140051135  mov     r8d, 4Fh ; 'O'
0x14005113b  lea     rdx, aCallingUnloadu; "Calling ::UnloadUserProfile() from Sess"...
0x140051142  lea     rcx, [rbp+57h+var_A0]
0x140051146  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005114b  nop
0x14005114c  xorps   xmm0, xmm0
0x14005114f  movups  [rbp+57h+var_80], xmm0
0x140051153  xorps   xmm1, xmm1
0x140051156  movdqu  [rbp+57h+var_70], xmm1
0x14005115b  mov     r8d, 6
0x140051161  lea     rdx, aClient; "Client"
0x140051168  lea     rcx, [rbp+57h+var_80]
0x14005116c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140051171  nop
0x140051172  lea     r9, [rbp+57h+var_A0]
0x140051176  lea     r8, [rbp+57h+var_80]
0x14005117a  mov     edx, 4
0x14005117f  lea     rcx, [rbp+57h+var_60]
0x140051183  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140051188  nop
0x140051189  lea     rcx, [rbp+57h+var_80]
0x14005118d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051192  nop
0x140051193  lea     rcx, [rbp+57h+var_A0]
0x140051197  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005119c  nop
0x14005119d  lea     rcx, [rbp+57h+var_60]
0x1400511a1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400511a6  mov     rcx, [rdi+18h]
0x1400511aa  mov     rdx, [rdi+28h]; hProfile
0x1400511ae  mov     rcx, [rcx]; hToken
0x1400511b1  call    cs:__imp_UnloadUserProfile
0x1400511b7  test    eax, eax
0x1400511b9  jnz     loc_1400512E4
0x1400511bf  call    cs:__imp_GetLastError
0x1400511c5  mov     [rbp+57h+var_C0], eax
0x1400511c8  mov     edx, 5Ch ; '\'; Ch
0x1400511cd  lea     rcx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x1400511d4  call    cs:__imp_strrchr
0x1400511da  test    rax, rax
0x1400511dd  jz      short loc_1400511E4
0x1400511df  inc     rax
0x1400511e2  jmp     short loc_1400511EB
0x1400511e4  lea     rax, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x1400511eb  mov     rdx, rax; char *
0x1400511ee  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400511f5  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400511fa  shl     rax, 34h
0x1400511fe  mov     ecx, [rbp+57h+var_C0]
0x140051201  or      rax, rcx
0x140051204  mov     rcx, 272E00000000h
0x14005120e  or      rax, rcx
0x140051211  mov     [rbp+57h+var_B8], rax
0x140051215  lea     rdx, aAppvClientHost_27; "AppV::Client::Host::SessionImpl::Decrem"...
0x14005121c  lea     rcx, [rbp+57h+var_60]
0x140051220  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140051225  mov     [rbp+57h+var_40], 13Eh
0x14005122c  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140051231  xorps   xmm0, xmm0
0x140051234  movups  [rbp+57h+var_A0], xmm0
0x140051238  xorps   xmm1, xmm1
0x14005123b  movdqu  [rbp+57h+var_90], xmm1
0x140051240  mov     r8d, 75h ; 'u'
0x140051246  lea     rdx, aCallToUnloadus; "Call to ::UnloadUserProfile() from Pack"...
0x14005124d  lea     rcx, [rbp+57h+var_A0]
0x140051251  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140051256  nop
0x140051257  lea     r8, [rbp+57h+var_A0]
0x14005125b  lea     rdx, [rbp+57h+var_38]
0x14005125f  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140051264  nop
0x140051265  lea     rdx, [rbp+57h+var_C0]
0x140051269  mov     rcx, rax
0x14005126c  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140051271  mov     rdi, rax
0x140051274  xorps   xmm0, xmm0
0x140051277  movups  [rbp+57h+var_80], xmm0
0x14005127b  xorps   xmm1, xmm1
0x14005127e  movdqu  [rbp+57h+var_70], xmm1
0x140051283  mov     r8d, 6
0x140051289  lea     rdx, aClient; "Client"
0x140051290  lea     rcx, [rbp+57h+var_80]
0x140051294  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140051299  nop
0x14005129a  mov     r9, rdi
0x14005129d  lea     r8, [rbp+57h+var_80]
0x1400512a1  mov     edx, 1
0x1400512a6  lea     rcx, [rbp+57h+var_60]
0x1400512aa  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400512af  nop
0x1400512b0  lea     rcx, [rbp+57h+var_80]
0x1400512b4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400512b9  nop
0x1400512ba  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400512c1  mov     [rbp+57h+var_38], rax
0x1400512c5  lea     rcx, [rbp+57h+var_28]
0x1400512c9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400512ce  nop
0x1400512cf  lea     rcx, [rbp+57h+var_A0]
0x1400512d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400512d8  nop
0x1400512d9  lea     rcx, [rbp+57h+var_60]
0x1400512dd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400512e2  jmp     short loc_1400512EC
0x1400512e4  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x1400512ec  mov     rdi, [rbp+57h+var_B8]
0x1400512f0  test    rbx, rbx
0x1400512f3  jz      short loc_1400512FE
0x1400512f5  mov     rcx, rbx; hObject
0x1400512f8  call    cs:__imp_CloseHandle
0x1400512fe  mov     rax, rdi
0x140051301  mov     rcx, [rbp+57h+var_8]
0x140051305  xor     rcx, rsp; StackCookie
0x140051308  call    __security_check_cookie
0x14005130d  lea     r11, [rsp+0F0h+var_s0]
0x140051315  mov     rbx, [r11+18h]
0x140051319  mov     rdi, [r11+20h]
0x14005131d  mov     rsp, r11
0x140051320  pop     rbp
0x140051321  retn
```
