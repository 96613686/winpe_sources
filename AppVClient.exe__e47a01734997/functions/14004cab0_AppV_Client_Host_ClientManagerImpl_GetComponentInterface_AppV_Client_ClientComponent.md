# AppV::Client::Host::ClientManagerImpl::GetComponentInterface(AppV::Client::ClientComponent * &)

- ea: `0x14004cab0`
- end: `0x14004cc54`
- name: `?GetComponentInterface@ClientManagerImpl@Host@Client@AppV@@UEBA_KAEAPEAVClientComponent@34@@Z`
- size: `420`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::ClientManagerImpl *__hidden this, struct AppV::Client::ClientComponent **)`
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
- `0x14004cab0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14004cb03`
- `KERNEL32!GetCurrentThreadId` at `0x14004cb03`
- `KERNEL32!LeaveCriticalSection` at `0x14004cc27`
- `KERNEL32!LeaveCriticalSection` at `0x14004cc27`
- `KERNEL32!EnterCriticalSection` at `0x14004caf4`
- `KERNEL32!EnterCriticalSection` at `0x14004caf4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004cbbd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004cbbd`

## string_xrefs

- `0x14004cbb6`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004cbcd`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004cb1a`: `AppV::Client::Host::ClientManagerImpl::GetComponentInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int64 __fastcall AppV::Client::Host::ClientManagerImpl::GetComponentInterface(
        AppV::Client::Host::ClientManagerImpl *this,
        struct AppV::Client::ClientComponent **a2)
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
    *a2 = (struct AppV::Client::ClientComponent *)*((_QWORD *)this + 11);
    v8 = (*((_DWORD *)v4 + 10))-- == 1;
    if ( v8 )
      *((_DWORD *)v4 + 11) = 0;
    v7 = 0x8000000000LL;
  }
  else
  {
    std::string::string(v12, "AppV::Client::Host::ClientManagerImpl::GetComponentInterface");
    v13 = 98;
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
       | 0xC0E00000102LL;
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
0x14004cab0  mov     [rsp-8+arg_0], rbx
0x14004cab5  mov     [rsp-8+arg_10], rsi
0x14004caba  push    rbp
0x14004cabb  push    rdi
0x14004cabc  push    r14
0x14004cabe  lea     rbp, [rsp-47h]
0x14004cac3  sub     rsp, 0B0h
0x14004caca  mov     rax, cs:__security_cookie
0x14004cad1  xor     rax, rsp
0x14004cad4  mov     [rbp+57h+var_18], rax
0x14004cad8  mov     r14, rdx
0x14004cadb  mov     rsi, rcx
0x14004cade  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004cae5  mov     [rbp+57h+var_98], rax
0x14004cae9  lea     rbx, [rcx+10h]
0x14004caed  mov     [rbp+57h+var_88], rbx
0x14004caf1  mov     rcx, rbx; lpCriticalSection
0x14004caf4  call    cs:__imp_EnterCriticalSection
0x14004cafa  inc     dword ptr [rbx+28h]
0x14004cafd  cmp     dword ptr [rbx+28h], 1
0x14004cb01  jnz     short loc_14004CB0C
0x14004cb03  call    cs:__imp_GetCurrentThreadId
0x14004cb09  mov     [rbx+2Ch], eax
0x14004cb0c  mov     [rbp+57h+var_90], 1
0x14004cb10  cmp     byte ptr [rsi+40h], 0
0x14004cb14  jnz     loc_14004CC06
0x14004cb1a  lea     rdx, aAppvClientHost_28; "AppV::Client::Host::ClientManagerImpl::"...
0x14004cb21  lea     rcx, [rbp+57h+var_40]
0x14004cb25  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004cb2a  mov     [rbp+57h+var_20], 62h ; 'b'
0x14004cb31  xorps   xmm0, xmm0
0x14004cb34  movups  [rbp+57h+var_60], xmm0
0x14004cb38  xorps   xmm1, xmm1
0x14004cb3b  movdqu  [rbp+57h+var_50], xmm1
0x14004cb40  mov     r8d, 42h ; 'B'
0x14004cb46  lea     rdx, aClientmanagerR; "ClientManager recevied an operational r"...
0x14004cb4d  lea     rcx, [rbp+57h+var_60]
0x14004cb51  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004cb56  nop
0x14004cb57  xorps   xmm0, xmm0
0x14004cb5a  movups  [rbp+57h+var_80], xmm0
0x14004cb5e  xorps   xmm1, xmm1
0x14004cb61  movdqu  [rbp+57h+var_70], xmm1
0x14004cb66  mov     r8d, 6
0x14004cb6c  lea     rdx, aClient; "Client"
0x14004cb73  lea     rcx, [rbp+57h+var_80]
0x14004cb77  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004cb7c  nop
0x14004cb7d  lea     r9, [rbp+57h+var_60]
0x14004cb81  lea     r8, [rbp+57h+var_80]
0x14004cb85  mov     edx, 1
0x14004cb8a  lea     rcx, [rbp+57h+var_40]
0x14004cb8e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004cb93  nop
0x14004cb94  lea     rcx, [rbp+57h+var_80]
0x14004cb98  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004cb9d  nop
0x14004cb9e  lea     rcx, [rbp+57h+var_60]
0x14004cba2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004cba7  nop
0x14004cba8  lea     rcx, [rbp+57h+var_40]
0x14004cbac  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004cbb1  mov     edx, 5Ch ; '\'; Ch
0x14004cbb6  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004cbbd  call    cs:__imp_strrchr
0x14004cbc3  test    rax, rax
0x14004cbc6  jz      short loc_14004CBCD
0x14004cbc8  inc     rax
0x14004cbcb  jmp     short loc_14004CBD4
0x14004cbcd  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004cbd4  mov     rdx, rax; char *
0x14004cbd7  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004cbde  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004cbe3  mov     rdi, rax
0x14004cbe6  shl     rdi, 34h
0x14004cbea  mov     rax, 0C0E00000102h
0x14004cbf4  or      rdi, rax
0x14004cbf7  sub     dword ptr [rbx+28h], 1
0x14004cbfb  jnz     short loc_14004CC24
0x14004cbfd  mov     dword ptr [rbx+2Ch], 0
0x14004cc04  jmp     short loc_14004CC24
0x14004cc06  mov     rax, [rsi+58h]
0x14004cc0a  mov     [r14], rax
0x14004cc0d  sub     dword ptr [rbx+28h], 1
0x14004cc11  jnz     short loc_14004CC1A
0x14004cc13  mov     dword ptr [rbx+2Ch], 0
0x14004cc1a  mov     rdi, 8000000000h
0x14004cc24  mov     rcx, rbx; lpCriticalSection
0x14004cc27  call    cs:__imp_LeaveCriticalSection
0x14004cc2d  mov     rax, rdi
0x14004cc30  mov     rcx, [rbp+57h+var_18]
0x14004cc34  xor     rcx, rsp; StackCookie
0x14004cc37  call    __security_check_cookie
0x14004cc3c  lea     r11, [rsp+0C0h+var_10]
0x14004cc44  mov     rbx, [r11+20h]
0x14004cc48  mov     rsi, [r11+30h]
0x14004cc4c  mov     rsp, r11
0x14004cc4f  pop     r14
0x14004cc51  pop     rdi
0x14004cc52  pop     rbp
0x14004cc53  retn
```
