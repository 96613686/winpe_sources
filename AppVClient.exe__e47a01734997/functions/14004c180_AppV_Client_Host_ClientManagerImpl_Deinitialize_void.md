# AppV::Client::Host::ClientManagerImpl::Deinitialize(void)

- ea: `0x14004c180`
- end: `0x14004c3b3`
- name: `?Deinitialize@ClientManagerImpl@Host@Client@AppV@@UEAA_KXZ`
- size: `563`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::ClientManagerImpl *__hidden this)`
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
- `0x14004c180`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14004c1c7`
- `KERNEL32!GetCurrentThreadId` at `0x14004c1c7`
- `KERNEL32!LeaveCriticalSection` at `0x14004c392`
- `KERNEL32!LeaveCriticalSection` at `0x14004c392`
- `KERNEL32!EnterCriticalSection` at `0x14004c1b8`
- `KERNEL32!EnterCriticalSection` at `0x14004c1b8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004c281`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004c281`

## string_xrefs

- `0x14004c27a`: `admin\appman\appv\client\host\common\clientmanager.cpp`
- `0x14004c291`: `admin\appman\appv\client\host\common\clientmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
unsigned __int64 __fastcall AppV::Client::Host::ClientManagerImpl::Deinitialize(
        AppV::Client::Host::ClientManagerImpl *this)
{
  char *v2; // rbx
  char *v3; // rax
  const char *v4; // rax
  unsigned __int64 v5; // rdi
  bool v6; // zf
  __int64 v7; // rsi
  __int128 v9; // [rsp+40h] [rbp-39h] BYREF
  __int128 v10; // [rsp+50h] [rbp-29h]
  __int128 v11; // [rsp+60h] [rbp-19h] BYREF
  __int128 v12; // [rsp+70h] [rbp-9h]
  char *v13[4]; // [rsp+80h] [rbp+7h] BYREF
  int v14; // [rsp+A0h] [rbp+27h]

  v2 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ++*((_DWORD *)v2 + 10) == 1 )
    *((_DWORD *)v2 + 11) = GetCurrentThreadId();
  if ( *((_BYTE *)this + 64) )
  {
    v7 = (*(__int64 (__fastcall **)(AppV::Client::Host::ClientManagerImpl *))(*(_QWORD *)this + 48LL))(this);
    *((_BYTE *)this + 64) = 0;
    std::string::string(v13, "AppV::Client::Host::ClientManagerImpl::Deinitialize");
    v14 = 88;
    v9 = 0;
    v10 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v9, L"ClientManager deinitialized", 0x1Bu);
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v11, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v13, 4, (int)&v11, (__int64)&v9);
    std::wstring::~wstring((char **)&v11);
    std::wstring::~wstring((char **)&v9);
    std::string::~string(v13);
    v6 = (*((_DWORD *)v2 + 10))-- == 1;
    if ( v6 )
      *((_DWORD *)v2 + 11) = 0;
    v5 = v7;
  }
  else
  {
    std::string::string(v13, "AppV::Client::Host::ClientManagerImpl::Deinitialize");
    v14 = 81;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v11,
      L"ClientManager recevied an operational request when not initialized",
      0x42u);
    v9 = 0;
    v10 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v9, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v13, 1, (int)&v9, (__int64)&v11);
    std::wstring::~wstring((char **)&v9);
    std::wstring::~wstring((char **)&v11);
    std::string::~string(v13);
    v3 = strrchr("admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp", 92);
    if ( v3 )
      v4 = v3 + 1;
    else
      v4 = "admin\\appman\\appv\\client\\host\\common\\clientmanager.cpp";
    v5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v4) << 52)
       | 0xA0E00000102LL;
    v6 = (*((_DWORD *)v2 + 10))-- == 1;
    if ( v6 )
      *((_DWORD *)v2 + 11) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
  return v5;
}

```

## disassembly

```asm
0x14004c180  push    rbp
0x14004c182  push    rbx
0x14004c183  push    rsi
0x14004c184  push    rdi
0x14004c185  lea     rbp, [rsp-3Fh]
0x14004c18a  sub     rsp, 0B8h
0x14004c191  mov     rax, cs:__security_cookie
0x14004c198  xor     rax, rsp
0x14004c19b  mov     [rbp+57h+var_28], rax
0x14004c19f  mov     rdi, rcx
0x14004c1a2  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004c1a9  mov     [rbp+57h+var_A8], rax
0x14004c1ad  lea     rbx, [rcx+10h]
0x14004c1b1  mov     [rbp+57h+var_98], rbx
0x14004c1b5  mov     rcx, rbx; lpCriticalSection
0x14004c1b8  call    cs:__imp_EnterCriticalSection
0x14004c1be  inc     dword ptr [rbx+28h]
0x14004c1c1  cmp     dword ptr [rbx+28h], 1
0x14004c1c5  jnz     short loc_14004C1D0
0x14004c1c7  call    cs:__imp_GetCurrentThreadId
0x14004c1cd  mov     [rbx+2Ch], eax
0x14004c1d0  mov     [rbp+57h+var_A0], 1
0x14004c1d4  cmp     byte ptr [rdi+40h], 0
0x14004c1d8  jnz     loc_14004C2D1
0x14004c1de  lea     rdx, aAppvClientHost_21; "AppV::Client::Host::ClientManagerImpl::"...
0x14004c1e5  lea     rcx, [rbp+57h+var_50]
0x14004c1e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004c1ee  mov     [rbp+57h+var_30], 51h ; 'Q'
0x14004c1f5  xorps   xmm0, xmm0
0x14004c1f8  movups  [rbp+57h+var_70], xmm0
0x14004c1fc  xorps   xmm1, xmm1
0x14004c1ff  movdqu  [rbp+57h+var_60], xmm1
0x14004c204  mov     r8d, 42h ; 'B'
0x14004c20a  lea     rdx, aClientmanagerR; "ClientManager recevied an operational r"...
0x14004c211  lea     rcx, [rbp+57h+var_70]
0x14004c215  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c21a  nop
0x14004c21b  xorps   xmm0, xmm0
0x14004c21e  movups  [rbp+57h+var_90], xmm0
0x14004c222  xorps   xmm1, xmm1
0x14004c225  movdqu  [rbp+57h+var_80], xmm1
0x14004c22a  mov     r8d, 6
0x14004c230  lea     rdx, aClient; "Client"
0x14004c237  lea     rcx, [rbp+57h+var_90]
0x14004c23b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c240  nop
0x14004c241  lea     r9, [rbp+57h+var_70]
0x14004c245  lea     r8, [rbp+57h+var_90]
0x14004c249  mov     edx, 1
0x14004c24e  lea     rcx, [rbp+57h+var_50]
0x14004c252  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004c257  nop
0x14004c258  lea     rcx, [rbp+57h+var_90]
0x14004c25c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c261  nop
0x14004c262  lea     rcx, [rbp+57h+var_70]
0x14004c266  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c26b  nop
0x14004c26c  lea     rcx, [rbp+57h+var_50]
0x14004c270  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004c275  mov     edx, 5Ch ; '\'; Ch
0x14004c27a  lea     rcx, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004c281  call    cs:__imp_strrchr
0x14004c287  test    rax, rax
0x14004c28a  jz      short loc_14004C291
0x14004c28c  inc     rax
0x14004c28f  jmp     short loc_14004C298
0x14004c291  lea     rax, aAdminAppmanApp_18; "admin\\appman\\appv\\client\\host\\comm"...
0x14004c298  mov     rdx, rax; char *
0x14004c29b  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004c2a2  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004c2a7  mov     rdi, rax
0x14004c2aa  shl     rdi, 34h
0x14004c2ae  mov     rax, 0A0E00000102h
0x14004c2b8  or      rdi, rax
0x14004c2bb  sub     dword ptr [rbx+28h], 1
0x14004c2bf  jnz     loc_14004C38F
0x14004c2c5  mov     dword ptr [rbx+2Ch], 0
0x14004c2cc  jmp     loc_14004C38F
0x14004c2d1  mov     rax, [rdi]
0x14004c2d4  mov     rcx, rdi
0x14004c2d7  mov     rax, [rax+30h]
0x14004c2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c2e0  mov     rsi, rax
0x14004c2e3  mov     byte ptr [rdi+40h], 0
0x14004c2e7  lea     rdx, aAppvClientHost_21; "AppV::Client::Host::ClientManagerImpl::"...
0x14004c2ee  lea     rcx, [rbp+57h+var_50]
0x14004c2f2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004c2f7  mov     [rbp+57h+var_30], 58h ; 'X'
0x14004c2fe  xorps   xmm0, xmm0
0x14004c301  movups  [rbp+57h+var_90], xmm0
0x14004c305  xorps   xmm1, xmm1
0x14004c308  movdqu  [rbp+57h+var_80], xmm1
0x14004c30d  mov     r8d, 1Bh
0x14004c313  lea     rdx, aClientmanagerD; "ClientManager deinitialized"
0x14004c31a  lea     rcx, [rbp+57h+var_90]
0x14004c31e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c323  nop
0x14004c324  xorps   xmm0, xmm0
0x14004c327  movups  [rbp+57h+var_70], xmm0
0x14004c32b  xorps   xmm1, xmm1
0x14004c32e  movdqu  [rbp+57h+var_60], xmm1
0x14004c333  mov     r8d, 6
0x14004c339  lea     rdx, aClient; "Client"
0x14004c340  lea     rcx, [rbp+57h+var_70]
0x14004c344  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004c349  nop
0x14004c34a  lea     r9, [rbp+57h+var_90]
0x14004c34e  lea     r8, [rbp+57h+var_70]
0x14004c352  mov     edx, 4
0x14004c357  lea     rcx, [rbp+57h+var_50]
0x14004c35b  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004c360  nop
0x14004c361  lea     rcx, [rbp+57h+var_70]
0x14004c365  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c36a  nop
0x14004c36b  lea     rcx, [rbp+57h+var_90]
0x14004c36f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004c374  nop
0x14004c375  lea     rcx, [rbp+57h+var_50]
0x14004c379  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004c37e  nop
0x14004c37f  sub     dword ptr [rbx+28h], 1
0x14004c383  jnz     short loc_14004C38C
0x14004c385  mov     dword ptr [rbx+2Ch], 0
0x14004c38c  mov     rdi, rsi
0x14004c38f  mov     rcx, rbx; lpCriticalSection
0x14004c392  call    cs:__imp_LeaveCriticalSection
0x14004c398  mov     rax, rdi
0x14004c39b  mov     rcx, [rbp+57h+var_28]
0x14004c39f  xor     rcx, rsp; StackCookie
0x14004c3a2  call    __security_check_cookie
0x14004c3a7  add     rsp, 0B8h
0x14004c3ae  pop     rdi
0x14004c3af  pop     rsi
0x14004c3b0  pop     rbx
0x14004c3b1  pop     rbp
0x14004c3b2  retn
```
