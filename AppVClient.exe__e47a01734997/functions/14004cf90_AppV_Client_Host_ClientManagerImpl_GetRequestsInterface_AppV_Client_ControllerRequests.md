# AppV::Client::Host::ClientManagerImpl::GetRequestsInterface(AppV::Client::ControllerRequests * &)

- ea: `0x14004cf90`
- end: `0x14004d134`
- name: `?GetRequestsInterface@ClientManagerImpl@Host@Client@AppV@@UEBA_KAEAPEAVControllerRequests@34@@Z`
- size: `420`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::ClientManagerImpl *__hidden this, struct AppV::Client::ControllerRequests **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14004cf90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14004cfe3`
- `KERNEL32!GetCurrentThreadId` at `0x14004cfe3`
- `KERNEL32!LeaveCriticalSection` at `0x14004d107`
- `KERNEL32!LeaveCriticalSection` at `0x14004d107`
- `KERNEL32!EnterCriticalSection` at `0x14004cfd4`
- `KERNEL32!EnterCriticalSection` at `0x14004cfd4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004d09d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004d09d`

## string_xrefs

- `0x14004d096`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004d0ad`: `admin\appman\appv\client\host\common\clientmanager.cpp`

## pseudocode

```c
unsigned __int64 __fastcall AppV::Client::Host::ClientManagerImpl::GetRequestsInterface(
        AppV::Client::Host::ClientManagerImpl *this,
        struct AppV::Client::ControllerRequests **a2)
{
  char *v4; // rbx
  char *v5; // rax
  const char *v6; // rax
  unsigned __int64 v7; // rdi
  bool v8; // zf
  _OWORD v10[2]; // [rsp+40h] [rbp-29h] BYREF
  _OWORD v11[2]; // [rsp+60h] [rbp-9h] BYREF
  char *v12[4]; // [rsp+80h] [rbp+17h] BYREF
  int v13; // [rsp+A0h] [rbp+37h]

  v4 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ++*((_DWORD *)v4 + 10) == 1 )
    *((_DWORD *)v4 + 11) = GetCurrentThreadId();
  if ( *((_BYTE *)this + 64) )
  {
    *a2 = (struct AppV::Client::ControllerRequests *)*((_QWORD *)this + 12);
    v8 = (*((_DWORD *)v4 + 10))-- == 1;
    if ( v8 )
      *((_DWORD *)v4 + 11) = 0;
    v7 = 0x8000000000LL;
  }
  else
  {
    std::string::string(v12, "AppV::Client::Host::ClientManagerImpl::GetRequestsInterface");
    v13 = 112;
    memset(v11, 0, sizeof(v11));
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)v11,
      L"ClientManager recevied an operational request when not initialized",
      0x42u);
    memset(v10, 0, sizeof(v10));
    std::wstring::_Construct<1,wchar_t const *>((char **)v10, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v12, 1, (int)v10, (__int64)v11);
    std::wstring::~wstring((char **)v10);
    std::wstring::~wstring((char **)v11);
    std::string::~string(v12);
    v5 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    v7 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6) << 52)
       | 0xE0E00000102LL;
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
0x14004cf90  mov     [rsp-8+arg_0], rbx
0x14004cf95  mov     [rsp-8+arg_10], rsi
0x14004cf9a  push    rbp
0x14004cf9b  push    rdi
0x14004cf9c  push    r14
0x14004cf9e  lea     rbp, [rsp-47h]
0x14004cfa3  sub     rsp, 0B0h
0x14004cfaa  mov     rax, cs:__security_cookie
0x14004cfb1  xor     rax, rsp
0x14004cfb4  mov     [rbp+57h+var_18], rax
0x14004cfb8  mov     r14, rdx
0x14004cfbb  mov     rsi, rcx
0x14004cfbe  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004cfc5  mov     [rbp+57h+var_98], rax
0x14004cfc9  lea     rbx, [rcx+10h]
0x14004cfcd  mov     [rbp+57h+var_88], rbx
0x14004cfd1  mov     rcx, rbx; lpCriticalSection
0x14004cfd4  call    cs:__imp_EnterCriticalSection
0x14004cfda  inc     dword ptr [rbx+28h]
0x14004cfdd  cmp     dword ptr [rbx+28h], 1
0x14004cfe1  jnz     short loc_14004CFEC
0x14004cfe3  call    cs:__imp_GetCurrentThreadId
0x14004cfe9  mov     [rbx+2Ch], eax
0x14004cfec  mov     [rbp+57h+var_90], 1
0x14004cff0  cmp     byte ptr [rsi+40h], 0
0x14004cff4  jnz     loc_14004D0E6
0x14004cffa  lea     rdx, aAppvClientHost_18; "AppV::Client::Host::ClientManagerImpl::"...
0x14004d001  lea     rcx, [rbp+57h+var_40]
0x14004d005  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004d00a  mov     [rbp+57h+var_20], 70h ; 'p'
0x14004d011  xorps   xmm0, xmm0
0x14004d014  movups  [rbp+57h+var_60], xmm0
0x14004d018  xorps   xmm1, xmm1
0x14004d01b  movdqu  [rbp+57h+var_50], xmm1
0x14004d020  mov     r8d, 42h ; 'B'
0x14004d026  lea     rdx, aClientmanagerR; "ClientManager recevied an operational r"...
0x14004d02d  lea     rcx, [rbp+57h+var_60]
0x14004d031  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d036  nop
0x14004d037  xorps   xmm0, xmm0
0x14004d03a  movups  [rbp+57h+var_80], xmm0
0x14004d03e  xorps   xmm1, xmm1
0x14004d041  movdqu  [rbp+57h+var_70], xmm1
0x14004d046  mov     r8d, 6
0x14004d04c  lea     rdx, aClient; "Client"
0x14004d053  lea     rcx, [rbp+57h+var_80]
0x14004d057  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d05c  nop
0x14004d05d  lea     r9, [rbp+57h+var_60]
0x14004d061  lea     r8, [rbp+57h+var_80]
0x14004d065  mov     edx, 1
0x14004d06a  lea     rcx, [rbp+57h+var_40]
0x14004d06e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004d073  nop
0x14004d074  lea     rcx, [rbp+57h+var_80]
0x14004d078  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d07d  nop
0x14004d07e  lea     rcx, [rbp+57h+var_60]
0x14004d082  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d087  nop
0x14004d088  lea     rcx, [rbp+57h+var_40]
0x14004d08c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004d091  mov     edx, 5Ch ; '\'; Ch
0x14004d096  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004d09d  call    cs:__imp_strrchr
0x14004d0a3  test    rax, rax
0x14004d0a6  jz      short loc_14004D0AD
0x14004d0a8  inc     rax
0x14004d0ab  jmp     short loc_14004D0B4
0x14004d0ad  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004d0b4  mov     rdx, rax; char *
0x14004d0b7  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004d0be  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004d0c3  mov     rdi, rax
0x14004d0c6  shl     rdi, 34h
0x14004d0ca  mov     rax, 0E0E00000102h
0x14004d0d4  or      rdi, rax
0x14004d0d7  sub     dword ptr [rbx+28h], 1
0x14004d0db  jnz     short loc_14004D104
0x14004d0dd  mov     dword ptr [rbx+2Ch], 0
0x14004d0e4  jmp     short loc_14004D104
0x14004d0e6  mov     rax, [rsi+60h]
0x14004d0ea  mov     [r14], rax
0x14004d0ed  sub     dword ptr [rbx+28h], 1
0x14004d0f1  jnz     short loc_14004D0FA
0x14004d0f3  mov     dword ptr [rbx+2Ch], 0
0x14004d0fa  mov     rdi, 8000000000h
0x14004d104  mov     rcx, rbx; lpCriticalSection
0x14004d107  call    cs:__imp_LeaveCriticalSection
0x14004d10d  mov     rax, rdi
0x14004d110  mov     rcx, [rbp+57h+var_18]
0x14004d114  xor     rcx, rsp; StackCookie
0x14004d117  call    __security_check_cookie
0x14004d11c  lea     r11, [rsp+0C0h+var_10]
0x14004d124  mov     rbx, [r11+20h]
0x14004d128  mov     rsi, [r11+30h]
0x14004d12c  mov     rsp, r11
0x14004d12f  pop     r14
0x14004d131  pop     rdi
0x14004d132  pop     rbp
0x14004d133  retn
```
