# AppV::Client::Host::ClientManagerImpl::Initialize(HINSTANCE__ *,AppV::Client::ClientHost &,AppV::Client::ClientEventSink &)

- ea: `0x14004d140`
- end: `0x14004d3ae`
- name: `?Initialize@ClientManagerImpl@Host@Client@AppV@@UEAA_KPEAUHINSTANCE__@@AEAVClientHost@34@AEAVClientEventSink@34@@Z`
- size: `622`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::ClientManagerImpl *__hidden this, HINSTANCE, struct AppV::Client::ClientHost *, struct AppV::Client::ClientEventSink *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x14004d140`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14004d194`
- `KERNEL32!GetCurrentThreadId` at `0x14004d194`
- `KERNEL32!LeaveCriticalSection` at `0x14004d389`
- `KERNEL32!LeaveCriticalSection` at `0x14004d389`
- `KERNEL32!EnterCriticalSection` at `0x14004d185`
- `KERNEL32!EnterCriticalSection` at `0x14004d185`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004d24e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004d24e`

## string_xrefs

- `0x14004d1d7`: `ClientManager recevied an Initialize request when already initialized`
- `0x14004d247`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004d25e`: `admin\appman\appv\client\host\common\clientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
unsigned __int64 __fastcall AppV::Client::Host::ClientManagerImpl::Initialize(
        AppV::Client::Host::ClientManagerImpl *this,
        HINSTANCE a2,
        struct AppV::Client::ClientHost *a3,
        struct AppV::Client::ClientEventSink *a4)
{
  char *v8; // rbx
  char *v9; // rax
  const char *v10; // rax
  unsigned __int64 v11; // rdi
  bool v12; // zf
  __int64 v13; // rax
  __int128 v15; // [rsp+50h] [rbp-49h] BYREF
  __int128 v16; // [rsp+60h] [rbp-39h]
  __int128 v17; // [rsp+70h] [rbp-29h] BYREF
  __int128 v18; // [rsp+80h] [rbp-19h]
  char *v19[4]; // [rsp+90h] [rbp-9h] BYREF
  int v20; // [rsp+B0h] [rbp+17h]

  v8 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ++*((_DWORD *)v8 + 10) == 1 )
    *((_DWORD *)v8 + 11) = GetCurrentThreadId();
  if ( *((_BYTE *)this + 64) )
  {
    std::string::string(v19, "AppV::Client::Host::ClientManagerImpl::Initialize");
    v20 = 62;
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v17,
      L"ClientManager recevied an Initialize request when already initialized",
      0x45u);
    v15 = 0;
    v16 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v15, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v19, 1, (int)&v15, (__int64)&v17);
    std::wstring::~wstring((char **)&v15);
    std::wstring::~wstring((char **)&v17);
    std::string::~string(v19);
    v9 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v9 )
      v10 = v9 + 1;
    else
      v10 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    v11 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v10) << 52)
        | 0x70E00000101LL;
    v12 = (*((_DWORD *)v8 + 10))-- == 1;
    if ( v12 )
      *((_DWORD *)v8 + 11) = 0;
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(AppV::Client::Host::ClientManagerImpl *, HINSTANCE, struct AppV::Client::ClientHost *, struct AppV::Client::ClientEventSink *))(*(_QWORD *)this + 40LL))(
            this,
            a2,
            a3,
            a4);
    if ( (v13 & 0x8000000000LL) != 0 )
    {
      *((_BYTE *)this + 64) = 1;
      std::string::string(v19, "AppV::Client::Host::ClientManagerImpl::Initialize");
      v20 = 71;
      v15 = 0;
      v16 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v15, L"ClientManager initialized", 0x19u);
      v17 = 0;
      v18 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v17, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v19, 4, (int)&v17, (__int64)&v15);
      std::wstring::~wstring((char **)&v17);
      std::wstring::~wstring((char **)&v15);
      std::string::~string(v19);
      v12 = (*((_DWORD *)v8 + 10))-- == 1;
      if ( v12 )
        *((_DWORD *)v8 + 11) = 0;
      v11 = 0x8000000000LL;
    }
    else
    {
      v12 = (*((_DWORD *)v8 + 10))-- == 1;
      if ( v12 )
        *((_DWORD *)v8 + 11) = 0;
      v11 = v13;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v8);
  return v11;
}

```

## disassembly

```asm
0x14004d140  push    rbp
0x14004d142  push    rbx
0x14004d143  push    rsi
0x14004d144  push    rdi
0x14004d145  push    r14
0x14004d147  push    r15
0x14004d149  lea     rbp, [rsp-2Fh]
0x14004d14e  sub     rsp, 0C8h
0x14004d155  mov     rax, cs:__security_cookie
0x14004d15c  xor     rax, rsp
0x14004d15f  mov     [rbp+57h+var_38], rax
0x14004d163  mov     r15, r9
0x14004d166  mov     r14, r8
0x14004d169  mov     rsi, rdx
0x14004d16c  mov     rdi, rcx
0x14004d16f  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004d176  mov     [rbp+57h+var_B8], rax
0x14004d17a  lea     rbx, [rcx+10h]
0x14004d17e  mov     [rbp+57h+var_A8], rbx
0x14004d182  mov     rcx, rbx; lpCriticalSection
0x14004d185  call    cs:__imp_EnterCriticalSection
0x14004d18b  inc     dword ptr [rbx+28h]
0x14004d18e  cmp     dword ptr [rbx+28h], 1
0x14004d192  jnz     short loc_14004D19D
0x14004d194  call    cs:__imp_GetCurrentThreadId
0x14004d19a  mov     [rbx+2Ch], eax
0x14004d19d  mov     [rbp+57h+var_B0], 1
0x14004d1a1  cmp     byte ptr [rdi+40h], 0
0x14004d1a5  jz      loc_14004D29E
0x14004d1ab  lea     rdx, aAppvClientHost_3; "AppV::Client::Host::ClientManagerImpl::"...
0x14004d1b2  lea     rcx, [rbp+57h+var_60]
0x14004d1b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004d1bb  mov     [rbp+57h+var_40], 3Eh ; '>'
0x14004d1c2  xorps   xmm0, xmm0
0x14004d1c5  movups  [rbp+57h+var_80], xmm0
0x14004d1c9  xorps   xmm1, xmm1
0x14004d1cc  movdqu  [rbp+57h+var_70], xmm1
0x14004d1d1  mov     r8d, 45h ; 'E'
0x14004d1d7  lea     rdx, aClientmanagerR_0; "ClientManager recevied an Initialize re"...
0x14004d1de  lea     rcx, [rbp+57h+var_80]
0x14004d1e2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d1e7  nop
0x14004d1e8  xorps   xmm0, xmm0
0x14004d1eb  movups  [rbp+57h+var_A0], xmm0
0x14004d1ef  xorps   xmm1, xmm1
0x14004d1f2  movdqu  [rbp+57h+var_90], xmm1
0x14004d1f7  mov     r8d, 6
0x14004d1fd  lea     rdx, aClient; "Client"
0x14004d204  lea     rcx, [rbp+57h+var_A0]
0x14004d208  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d20d  nop
0x14004d20e  lea     r9, [rbp+57h+var_80]
0x14004d212  lea     r8, [rbp+57h+var_A0]
0x14004d216  mov     edx, 1
0x14004d21b  lea     rcx, [rbp+57h+var_60]
0x14004d21f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004d224  nop
0x14004d225  lea     rcx, [rbp+57h+var_A0]
0x14004d229  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d22e  nop
0x14004d22f  lea     rcx, [rbp+57h+var_80]
0x14004d233  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d238  nop
0x14004d239  lea     rcx, [rbp+57h+var_60]
0x14004d23d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004d242  mov     edx, 5Ch ; '\'; Ch
0x14004d247  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004d24e  call    cs:__imp_strrchr
0x14004d254  test    rax, rax
0x14004d257  jz      short loc_14004D25E
0x14004d259  inc     rax
0x14004d25c  jmp     short loc_14004D265
0x14004d25e  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004d265  mov     rdx, rax; char *
0x14004d268  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004d26f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004d274  mov     rdi, rax
0x14004d277  shl     rdi, 34h
0x14004d27b  mov     rax, 70E00000101h
0x14004d285  or      rdi, rax
0x14004d288  sub     dword ptr [rbx+28h], 1
0x14004d28c  jnz     loc_14004D386
0x14004d292  mov     dword ptr [rbx+2Ch], 0
0x14004d299  jmp     loc_14004D386
0x14004d29e  mov     rax, [rdi]
0x14004d2a1  mov     r9, r15
0x14004d2a4  mov     r8, r14
0x14004d2a7  mov     rdx, rsi
0x14004d2aa  mov     rcx, rdi
0x14004d2ad  mov     rax, [rax+28h]
0x14004d2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004d2b6  mov     rsi, 8000000000h
0x14004d2c0  test    rsi, rax
0x14004d2c3  jnz     short loc_14004D2DA
0x14004d2c5  sub     dword ptr [rbx+28h], 1
0x14004d2c9  jnz     short loc_14004D2D2
0x14004d2cb  mov     dword ptr [rbx+2Ch], 0
0x14004d2d2  mov     rdi, rax
0x14004d2d5  jmp     loc_14004D386
0x14004d2da  mov     byte ptr [rdi+40h], 1
0x14004d2de  lea     rdx, aAppvClientHost_3; "AppV::Client::Host::ClientManagerImpl::"...
0x14004d2e5  lea     rcx, [rbp+57h+var_60]
0x14004d2e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004d2ee  mov     [rbp+57h+var_40], 47h ; 'G'
0x14004d2f5  xorps   xmm0, xmm0
0x14004d2f8  movups  [rbp+57h+var_A0], xmm0
0x14004d2fc  xorps   xmm1, xmm1
0x14004d2ff  movdqu  [rbp+57h+var_90], xmm1
0x14004d304  mov     r8d, 19h
0x14004d30a  lea     rdx, aClientmanagerI; "ClientManager initialized"
0x14004d311  lea     rcx, [rbp+57h+var_A0]
0x14004d315  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d31a  nop
0x14004d31b  xorps   xmm0, xmm0
0x14004d31e  movups  [rbp+57h+var_80], xmm0
0x14004d322  xorps   xmm1, xmm1
0x14004d325  movdqu  [rbp+57h+var_70], xmm1
0x14004d32a  mov     r8d, 6
0x14004d330  lea     rdx, aClient; "Client"
0x14004d337  lea     rcx, [rbp+57h+var_80]
0x14004d33b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004d340  nop
0x14004d341  lea     r9, [rbp+57h+var_A0]
0x14004d345  lea     r8, [rbp+57h+var_80]
0x14004d349  mov     edx, 4
0x14004d34e  lea     rcx, [rbp+57h+var_60]
0x14004d352  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004d357  nop
0x14004d358  lea     rcx, [rbp+57h+var_80]
0x14004d35c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d361  nop
0x14004d362  lea     rcx, [rbp+57h+var_A0]
0x14004d366  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004d36b  nop
0x14004d36c  lea     rcx, [rbp+57h+var_60]
0x14004d370  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004d375  nop
0x14004d376  sub     dword ptr [rbx+28h], 1
0x14004d37a  jnz     short loc_14004D383
0x14004d37c  mov     dword ptr [rbx+2Ch], 0
0x14004d383  mov     rdi, rsi
0x14004d386  mov     rcx, rbx; lpCriticalSection
0x14004d389  call    cs:__imp_LeaveCriticalSection
0x14004d38f  mov     rax, rdi
0x14004d392  mov     rcx, [rbp+57h+var_38]
0x14004d396  xor     rcx, rsp; StackCookie
0x14004d399  call    __security_check_cookie
0x14004d39e  add     rsp, 0C8h
0x14004d3a5  pop     r15
0x14004d3a7  pop     r14
0x14004d3a9  pop     rdi
0x14004d3aa  pop     rsi
0x14004d3ab  pop     rbx
0x14004d3ac  pop     rbp
0x14004d3ad  retn
```
