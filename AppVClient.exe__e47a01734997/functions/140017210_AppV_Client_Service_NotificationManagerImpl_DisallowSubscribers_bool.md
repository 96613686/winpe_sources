# AppV::Client::Service::NotificationManagerImpl::DisallowSubscribers(bool)

- ea: `0x140017210`
- end: `0x1400173bc`
- name: `?DisallowSubscribers@NotificationManagerImpl@Service@Client@AppV@@UEAA_K_N@Z`
- size: `428`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::NotificationManagerImpl *__hidden this, bool)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140017140`
- `0x140017210`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140017263`
- `KERNEL32!GetCurrentThreadId` at `0x140017263`
- `KERNEL32!LeaveCriticalSection` at `0x14001738f`
- `KERNEL32!LeaveCriticalSection` at `0x14001738f`
- `KERNEL32!EnterCriticalSection` at `0x140017254`
- `KERNEL32!EnterCriticalSection` at `0x140017254`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017282`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140017282`

## string_xrefs

- `0x1400172e4`: `AppV::Client::Service::NotificationManagerImpl::DisallowSubscribers`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int64 __fastcall AppV::Client::Service::NotificationManagerImpl::DisallowSubscribers(
        AppV::Client::Service::NotificationManagerImpl *this,
        bool a2)
{
  char *v4; // rbx
  char *v5; // rax
  DWORD *SubAuthority; // rax
  unsigned __int64 v7; // rdi
  bool v8; // zf
  unsigned __int64 v9; // rsi
  _OWORD v11[2]; // [rsp+40h] [rbp-29h] BYREF
  _OWORD v12[2]; // [rsp+60h] [rbp-9h] BYREF
  char *v13[4]; // [rsp+80h] [rbp+17h] BYREF
  int v14; // [rsp+A0h] [rbp+37h]

  v4 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ++*((_DWORD *)v4 + 10) == 1 )
    *((_DWORD *)v4 + 11) = GetCurrentThreadId();
  if ( *((_BYTE *)this + 64) )
  {
    v9 = AppV::Client::Service::NotificationManagerImpl::ClearSubscribers(this, a2);
    *((_BYTE *)this + 64) = 0;
    std::string::string(v13, "AppV::Client::Service::NotificationManagerImpl::DisallowSubscribers");
    v14 = 80;
    memset(v12, 0, sizeof(v12));
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)v12,
      L"NotificationManager no longer accepting subscribers",
      0x33u);
    memset(v11, 0, sizeof(v11));
    std::wstring::_Construct<1,wchar_t const *>((char **)v11, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v13, 8, (int)v11, (__int64)v12);
    std::wstring::~wstring((char **)v11);
    std::wstring::~wstring((char **)v12);
    std::string::~string(v13);
    v8 = (*((_DWORD *)v4 + 10))-- == 1;
    if ( v8 )
      *((_DWORD *)v4 + 11) = 0;
    v7 = v9;
  }
  else
  {
    v5 = strrchr((const char *)ATL::Sids::SecurityNTAuthority.SubAuthority, 92);
    if ( v5 )
      SubAuthority = (DWORD *)(v5 + 1);
    else
      SubAuthority = ATL::Sids::SecurityNTAuthority.SubAuthority;
    v7 = (AppV::FileLookUp::getFileId(
            (AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_,
            (const char *)SubAuthority) << 52)
       | 0x90300000202LL;
    v8 = (*((_DWORD *)v4 + 10))-- == 1;
    if ( v8 )
      *((_DWORD *)v4 + 11) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  return v7;
}

```

## disassembly

```asm
0x140017210  mov     [rsp-8+arg_10], rbx
0x140017215  mov     [rsp-8+arg_18], rsi
0x14001721a  push    rbp
0x14001721b  push    rdi
0x14001721c  push    r14
0x14001721e  lea     rbp, [rsp-47h]
0x140017223  sub     rsp, 0B0h
0x14001722a  mov     rax, cs:__security_cookie
0x140017231  xor     rax, rsp
0x140017234  mov     [rbp+57h+var_18], rax
0x140017238  mov     r14b, dl
0x14001723b  mov     rdi, rcx
0x14001723e  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140017245  mov     [rbp+57h+var_98], rax
0x140017249  lea     rbx, [rcx+10h]
0x14001724d  mov     [rbp+57h+var_88], rbx
0x140017251  mov     rcx, rbx; lpCriticalSection
0x140017254  call    cs:__imp_EnterCriticalSection
0x14001725a  inc     dword ptr [rbx+28h]
0x14001725d  cmp     dword ptr [rbx+28h], 1
0x140017261  jnz     short loc_14001726C
0x140017263  call    cs:__imp_GetCurrentThreadId
0x140017269  mov     [rbx+2Ch], eax
0x14001726c  mov     [rbp+57h+var_90], 1
0x140017270  cmp     byte ptr [rdi+40h], 0
0x140017274  jnz     short loc_1400172D2
0x140017276  mov     edx, 5Ch ; '\'; Ch
0x14001727b  lea     rcx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; Str
0x140017282  call    cs:__imp_strrchr
0x140017288  test    rax, rax
0x14001728b  jz      short loc_140017292
0x14001728d  inc     rax
0x140017290  jmp     short loc_140017299
0x140017292  lea     rax, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const ATL::Sids::SecurityNTAuthority ...
0x140017299  mov     rdx, rax; char *
0x14001729c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400172a3  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400172a8  mov     rdi, rax
0x1400172ab  shl     rdi, 34h
0x1400172af  mov     rax, 90300000202h
0x1400172b9  or      rdi, rax
0x1400172bc  sub     dword ptr [rbx+28h], 1
0x1400172c0  jnz     loc_14001738C
0x1400172c6  mov     dword ptr [rbx+2Ch], 0
0x1400172cd  jmp     loc_14001738C
0x1400172d2  mov     dl, r14b; bool
0x1400172d5  mov     rcx, rdi; this
0x1400172d8  call    ?ClearSubscribers@NotificationManagerImpl@Service@Client@AppV@@AEAA_K_N@Z; AppV::Client::Service::NotificationManagerImpl::ClearSubscribers(bool)
0x1400172dd  mov     rsi, rax
0x1400172e0  mov     byte ptr [rdi+40h], 0
0x1400172e4  lea     rdx, aAppvClientServ_28; "AppV::Client::Service::NotificationMana"...
0x1400172eb  lea     rcx, [rbp+57h+var_40]
0x1400172ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400172f4  mov     [rbp+57h+var_20], 50h ; 'P'
0x1400172fb  xorps   xmm0, xmm0
0x1400172fe  movups  [rbp+57h+var_60], xmm0
0x140017302  xorps   xmm1, xmm1
0x140017305  movdqu  [rbp+57h+var_50], xmm1
0x14001730a  mov     r8d, 33h ; '3'
0x140017310  lea     rdx, aNotificationma_4; "NotificationManager no longer accepting"...
0x140017317  lea     rcx, [rbp+57h+var_60]
0x14001731b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140017320  nop
0x140017321  xorps   xmm0, xmm0
0x140017324  movups  [rbp+57h+var_80], xmm0
0x140017328  xorps   xmm1, xmm1
0x14001732b  movdqu  [rbp+57h+var_70], xmm1
0x140017330  mov     r8d, 6
0x140017336  lea     rdx, aClient; "Client"
0x14001733d  lea     rcx, [rbp+57h+var_80]
0x140017341  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140017346  nop
0x140017347  lea     r9, [rbp+57h+var_60]
0x14001734b  lea     r8, [rbp+57h+var_80]
0x14001734f  mov     edx, 8
0x140017354  lea     rcx, [rbp+57h+var_40]
0x140017358  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14001735d  nop
0x14001735e  lea     rcx, [rbp+57h+var_80]
0x140017362  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017367  nop
0x140017368  lea     rcx, [rbp+57h+var_60]
0x14001736c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140017371  nop
0x140017372  lea     rcx, [rbp+57h+var_40]
0x140017376  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14001737b  nop
0x14001737c  sub     dword ptr [rbx+28h], 1
0x140017380  jnz     short loc_140017389
0x140017382  mov     dword ptr [rbx+2Ch], 0
0x140017389  mov     rdi, rsi
0x14001738c  mov     rcx, rbx; lpCriticalSection
0x14001738f  call    cs:__imp_LeaveCriticalSection
0x140017395  mov     rax, rdi
0x140017398  mov     rcx, [rbp+57h+var_18]
0x14001739c  xor     rcx, rsp; StackCookie
0x14001739f  call    __security_check_cookie
0x1400173a4  lea     r11, [rsp+0C0h+var_10]
0x1400173ac  mov     rbx, [r11+30h]
0x1400173b0  mov     rsi, [r11+38h]
0x1400173b4  mov     rsp, r11
0x1400173b7  pop     r14
0x1400173b9  pop     rdi
0x1400173ba  pop     rbp
0x1400173bb  retn
```
