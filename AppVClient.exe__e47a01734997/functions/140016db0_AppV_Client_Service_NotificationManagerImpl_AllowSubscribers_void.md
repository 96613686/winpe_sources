# AppV::Client::Service::NotificationManagerImpl::AllowSubscribers(void)

- ea: `0x140016db0`
- end: `0x140016f3d`
- name: `?AllowSubscribers@NotificationManagerImpl@Service@Client@AppV@@UEAA_KXZ`
- size: `397`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::NotificationManagerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140016db0`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140016df7`
- `KERNEL32!GetCurrentThreadId` at `0x140016df7`
- `KERNEL32!LeaveCriticalSection` at `0x140016f1c`
- `KERNEL32!LeaveCriticalSection` at `0x140016f1c`
- `KERNEL32!EnterCriticalSection` at `0x140016de8`
- `KERNEL32!EnterCriticalSection` at `0x140016de8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140016e16`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140016e16`

## string_xrefs

- `0x140016e6a`: `AppV::Client::Service::NotificationManagerImpl::AllowSubscribers`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int64 __fastcall AppV::Client::Service::NotificationManagerImpl::AllowSubscribers(
        AppV::Client::Service::NotificationManagerImpl *this)
{
  char *v2; // rbx
  char *v3; // rax
  DWORD *SubAuthority; // rax
  unsigned __int64 v5; // rdi
  bool v6; // zf
  _OWORD v8[2]; // [rsp+40h] [rbp-39h] BYREF
  _OWORD v9[2]; // [rsp+60h] [rbp-19h] BYREF
  char *v10[4]; // [rsp+80h] [rbp+7h] BYREF
  int v11; // [rsp+A0h] [rbp+27h]

  v2 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ++*((_DWORD *)v2 + 10) == 1 )
    *((_DWORD *)v2 + 11) = GetCurrentThreadId();
  if ( *((_BYTE *)this + 64) )
  {
    v3 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v3 )
      SubAuthority = (DWORD *)(v3 + 1);
    else
      SubAuthority = ATL::Sids::SecurityNTAuthority.SubAuthority;
    v5 = (AppV::FileLookUp::getFileId(
            (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
            (const char *)SubAuthority) << 52)
       | 0x70300000201LL;
    v6 = (*((_DWORD *)v2 + 10))-- == 1;
    if ( v6 )
      *((_DWORD *)v2 + 11) = 0;
  }
  else
  {
    *((_BYTE *)this + 64) = 1;
    std::string::string(v10, "AppV::Client::Service::NotificationManagerImpl::AllowSubscribers");
    v11 = 64;
    memset(v9, 0, sizeof(v9));
    std::wstring::_Construct<1,wchar_t const *>((char **)v9, L"NotificationManager accepting subscribers", 0x29u);
    memset(v8, 0, sizeof(v8));
    std::wstring::_Construct<1,wchar_t const *>((char **)v8, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v10, 8, (int)v8, (__int64)v9);
    std::wstring::~wstring((char **)v8);
    std::wstring::~wstring((char **)v9);
    std::string::~string(v10);
    v6 = (*((_DWORD *)v2 + 10))-- == 1;
    if ( v6 )
      *((_DWORD *)v2 + 11) = 0;
    v5 = 0x8000000000LL;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
  return v5;
}

```

## disassembly

```asm
0x140016db0  push    rbp
0x140016db2  push    rbx
0x140016db3  push    rsi
0x140016db4  push    rdi
0x140016db5  lea     rbp, [rsp-3Fh]
0x140016dba  sub     rsp, 0B8h
0x140016dc1  mov     rax, cs:__security_cookie
0x140016dc8  xor     rax, rsp
0x140016dcb  mov     [rbp+57h+var_28], rax
0x140016dcf  mov     rdi, rcx
0x140016dd2  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140016dd9  mov     [rbp+57h+var_A8], rax
0x140016ddd  lea     rbx, [rcx+10h]
0x140016de1  mov     [rbp+57h+var_98], rbx
0x140016de5  mov     rcx, rbx; lpCriticalSection
0x140016de8  call    cs:__imp_EnterCriticalSection
0x140016dee  inc     dword ptr [rbx+28h]
0x140016df1  cmp     dword ptr [rbx+28h], 1
0x140016df5  jnz     short loc_140016E00
0x140016df7  call    cs:__imp_GetCurrentThreadId
0x140016dfd  mov     [rbx+2Ch], eax
0x140016e00  mov     [rbp+57h+var_A0], 1
0x140016e04  cmp     byte ptr [rdi+40h], 0
0x140016e08  jz      short loc_140016E66
0x140016e0a  mov     edx, 5Ch ; '\'; Ch
0x140016e0f  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x140016e16  call    cs:__imp_strrchr
0x140016e1c  test    rax, rax
0x140016e1f  jz      short loc_140016E26
0x140016e21  inc     rax
0x140016e24  jmp     short loc_140016E2D
0x140016e26  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x140016e2d  mov     rdx, rax; char *
0x140016e30  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140016e37  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140016e3c  mov     rdi, rax
0x140016e3f  shl     rdi, 34h
0x140016e43  mov     rax, 70300000201h
0x140016e4d  or      rdi, rax
0x140016e50  sub     dword ptr [rbx+28h], 1
0x140016e54  jnz     loc_140016F19
0x140016e5a  mov     dword ptr [rbx+2Ch], 0
0x140016e61  jmp     loc_140016F19
0x140016e66  mov     byte ptr [rdi+40h], 1
0x140016e6a  lea     rdx, aAppvClientServ_10; "AppV::Client::Service::NotificationMana"...
0x140016e71  lea     rcx, [rbp+57h+var_50]
0x140016e75  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140016e7a  mov     [rbp+57h+var_30], 40h ; '@'
0x140016e81  xorps   xmm0, xmm0
0x140016e84  movups  [rbp+57h+var_70], xmm0
0x140016e88  xorps   xmm1, xmm1
0x140016e8b  movdqu  [rbp+57h+var_60], xmm1
0x140016e90  mov     r8d, 29h ; ')'
0x140016e96  lea     rdx, aNotificationma_5; "NotificationManager accepting subscribe"...
0x140016e9d  lea     rcx, [rbp+57h+var_70]
0x140016ea1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140016ea6  nop
0x140016ea7  xorps   xmm0, xmm0
0x140016eaa  movups  [rbp+57h+var_90], xmm0
0x140016eae  xorps   xmm1, xmm1
0x140016eb1  movdqu  [rbp+57h+var_80], xmm1
0x140016eb6  mov     r8d, 6
0x140016ebc  lea     rdx, aClient; "Client"
0x140016ec3  lea     rcx, [rbp+57h+var_90]
0x140016ec7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140016ecc  nop
0x140016ecd  lea     r9, [rbp+57h+var_70]
0x140016ed1  lea     r8, [rbp+57h+var_90]
0x140016ed5  mov     edx, 8
0x140016eda  lea     rcx, [rbp+57h+var_50]
0x140016ede  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140016ee3  nop
0x140016ee4  lea     rcx, [rbp+57h+var_90]
0x140016ee8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016eed  nop
0x140016eee  lea     rcx, [rbp+57h+var_70]
0x140016ef2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016ef7  nop
0x140016ef8  lea     rcx, [rbp+57h+var_50]
0x140016efc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140016f01  nop
0x140016f02  sub     dword ptr [rbx+28h], 1
0x140016f06  jnz     short loc_140016F0F
0x140016f08  mov     dword ptr [rbx+2Ch], 0
0x140016f0f  mov     rdi, 8000000000h
0x140016f19  mov     rcx, rbx; lpCriticalSection
0x140016f1c  call    cs:__imp_LeaveCriticalSection
0x140016f22  mov     rax, rdi
0x140016f25  mov     rcx, [rbp+57h+var_28]
0x140016f29  xor     rcx, rsp; StackCookie
0x140016f2c  call    __security_check_cookie
0x140016f31  add     rsp, 0B8h
0x140016f38  pop     rdi
0x140016f39  pop     rsi
0x140016f3a  pop     rbx
0x140016f3b  pop     rbp
0x140016f3c  retn
```
