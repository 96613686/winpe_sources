# AppV::Client::Host::UserManagerImpl::InternalLogoff(ulong)

- ea: `0x140049bcc`
- end: `0x140049e28`
- name: `?InternalLogoff@UserManagerImpl@Host@Client@AppV@@AEAA_KK@Z`
- size: `604`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::UserManagerImpl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14004a950`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x140049bcc`
- `0x14004b3f0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140049c1a`
- `KERNEL32!GetCurrentThreadId` at `0x140049c1a`
- `KERNEL32!LeaveCriticalSection` at `0x140049d63`
- `KERNEL32!LeaveCriticalSection` at `0x140049dad`
- `KERNEL32!LeaveCriticalSection` at `0x140049d63`
- `KERNEL32!LeaveCriticalSection` at `0x140049dad`
- `KERNEL32!EnterCriticalSection` at `0x140049c0b`
- `KERNEL32!EnterCriticalSection` at `0x140049c0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AppV::Client::Host::UserManagerImpl::InternalLogoff(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  LONG *p_LockCount; // r11
  __int64 *v5; // r8
  __int64 *v6; // rcx
  __int64 *v7; // rdx
  char v8; // r9
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  bool v14; // zf
  __int64 v16; // rax
  __int64 v17; // rsi
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rdi
  _DWORD v20[4]; // [rsp+20h] [rbp-89h] BYREF
  void **v21; // [rsp+30h] [rbp-79h]
  char v22; // [rsp+38h] [rbp-71h]
  struct _RTL_CRITICAL_SECTION *v23; // [rsp+40h] [rbp-69h]
  _OWORD v24[2]; // [rsp+48h] [rbp-61h] BYREF
  _OWORD v25[2]; // [rsp+68h] [rbp-41h] BYREF
  char *v26[4]; // [rsp+88h] [rbp-21h] BYREF
  int v27; // [rsp+A8h] [rbp-1h]
  void **v28; // [rsp+B0h] [rbp+7h] BYREF
  char *v29; // [rsp+C0h] [rbp+17h] BYREF

  v20[0] = a2;
  v21 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v3 = this + 3;
  v23 = this + 3;
  EnterCriticalSection(this + 3);
  if ( ++LODWORD(v3[1].DebugInfo) == 1 )
    HIDWORD(v3[1].DebugInfo) = GetCurrentThreadId();
  v22 = 1;
  p_LockCount = &this[4].LockCount;
  v5 = *(__int64 **)&this[4].LockCount;
  v6 = (__int64 *)v5[1];
  HIDWORD(v24[0]) = 0;
  v7 = v5;
  if ( !*((_BYTE *)v6 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v6 + 8) >= v20[0] )
      {
        v8 = 0;
        v7 = v6;
      }
      else
      {
        v8 = 1;
      }
      v9 = v6 + 2;
      if ( !v8 )
        v9 = v6;
      v6 = (__int64 *)*v9;
    }
    while ( !*(_BYTE *)(*v9 + 25) );
  }
  if ( *((_BYTE *)v7 + 25) || v20[0] < *((_DWORD *)v7 + 8) )
    v7 = v5;
  if ( v5 == v7 )
  {
    std::string::string(v26, "AppV::Client::Host::UserManagerImpl::InternalLogoff");
    v27 = 276;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v10);
    memset(v25, 0, sizeof(v25));
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)v25,
      L"User Manager ignoring logoff event for session %1% that it is not tracking",
      0x4Au);
    v12 = AppV::Log::fmt(v11, &v28, v25);
    v13 = AppV::LogFormatter::operator%<unsigned long>(v12, (__int64)v20);
    memset(v24, 0, sizeof(v24));
    std::wstring::_Construct<1,wchar_t const *>((char **)v24, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v26, 4, (int)v24, v13);
    std::wstring::~wstring((char **)v24);
    v28 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v29);
    std::wstring::~wstring((char **)v25);
    std::string::~string(v26);
    v14 = LODWORD(v3[1].DebugInfo)-- == 1;
    if ( v14 )
      HIDWORD(v3[1].DebugInfo) = 0;
    LeaveCriticalSection(v3);
    return 0x8000000000LL;
  }
  else
  {
    v16 = v7[6];
    if ( v16 )
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
    v17 = v7[5];
    *(_QWORD *)&v24[0] = v17;
    v18 = (volatile signed __int32 *)v7[6];
    *((_QWORD *)&v24[0] + 1) = v18;
    std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<AppV::Client::Host::Session>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<AppV::Client::Host::Session>>>,0>>::_Erase_unchecked(p_LockCount);
    v14 = LODWORD(v3[1].DebugInfo)-- == 1;
    if ( v14 )
      HIDWORD(v3[1].DebugInfo) = 0;
    LeaveCriticalSection(v3);
    v22 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    return v19;
  }
}

```

## disassembly

```asm
0x140049bcc  mov     [rsp-8+arg_10], rbx
0x140049bd1  push    rbp
0x140049bd2  push    rsi
0x140049bd3  push    rdi
0x140049bd4  lea     rbp, [rsp-47h]
0x140049bd9  sub     rsp, 0F0h
0x140049be0  mov     rax, cs:__security_cookie
0x140049be7  xor     rax, rsp
0x140049bea  mov     [rbp+57h+var_20], rax
0x140049bee  mov     rbx, rcx
0x140049bf1  mov     [rsp+100h+var_E0], edx
0x140049bf5  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140049bfc  mov     [rbp+57h+var_D0], rax
0x140049c00  lea     rdi, [rcx+78h]
0x140049c04  mov     [rbp+57h+var_C0], rdi
0x140049c08  mov     rcx, rdi; lpCriticalSection
0x140049c0b  call    cs:__imp_EnterCriticalSection
0x140049c11  inc     dword ptr [rdi+28h]
0x140049c14  cmp     dword ptr [rdi+28h], 1
0x140049c18  jnz     short loc_140049C23
0x140049c1a  call    cs:__imp_GetCurrentThreadId
0x140049c20  mov     [rdi+2Ch], eax
0x140049c23  mov     [rbp+57h+var_C8], 1
0x140049c27  lea     r11, [rbx+0A8h]
0x140049c2e  mov     r8, [r11]
0x140049c31  mov     rcx, [r8+8]
0x140049c35  xor     eax, eax
0x140049c37  mov     [rbp+57h+var_AC], eax
0x140049c3a  mov     rdx, r8
0x140049c3d  mov     r10d, [rsp+100h+var_E0]
0x140049c42  cmp     [rcx+19h], al
0x140049c45  jnz     short loc_140049C6C
0x140049c47  cmp     [rcx+20h], r10d
0x140049c4b  jnb     short loc_140049C52
0x140049c4d  mov     r9b, 1
0x140049c50  jmp     short loc_140049C58
0x140049c52  xor     r9b, r9b
0x140049c55  mov     rdx, rcx
0x140049c58  lea     rax, [rcx+10h]
0x140049c5c  test    r9b, r9b
0x140049c5f  cmovz   rax, rcx
0x140049c63  mov     rcx, [rax]
0x140049c66  cmp     byte ptr [rcx+19h], 0
0x140049c6a  jz      short loc_140049C47
0x140049c6c  cmp     byte ptr [rdx+19h], 0
0x140049c70  jnz     short loc_140049C78
0x140049c72  cmp     r10d, [rdx+20h]
0x140049c76  jnb     short loc_140049C7B
0x140049c78  mov     rdx, r8
0x140049c7b  cmp     r8, rdx
0x140049c7e  jnz     loc_140049D78
0x140049c84  lea     rdx, aAppvClientHost_0; "AppV::Client::Host::UserManagerImpl::In"...
0x140049c8b  lea     rcx, [rbp+57h+var_78]
0x140049c8f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140049c94  mov     [rbp+57h+var_58], 114h
0x140049c9b  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140049ca0  xorps   xmm0, xmm0
0x140049ca3  movups  [rbp+57h+var_98], xmm0
0x140049ca7  xorps   xmm1, xmm1
0x140049caa  movdqu  [rbp+57h+var_88], xmm1
0x140049caf  mov     r8d, 4Ah ; 'J'
0x140049cb5  lea     rdx, aUserManagerIgn_0; "User Manager ignoring logoff event for "...
0x140049cbc  lea     rcx, [rbp+57h+var_98]
0x140049cc0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049cc5  nop
0x140049cc6  lea     r8, [rbp+57h+var_98]
0x140049cca  lea     rdx, [rbp+57h+var_50]
0x140049cce  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140049cd3  nop
0x140049cd4  lea     rdx, [rsp+100h+var_E0]
0x140049cd9  mov     rcx, rax
0x140049cdc  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140049ce1  mov     rbx, rax
0x140049ce4  xorps   xmm0, xmm0
0x140049ce7  movups  xmmword ptr [rbp-61h], xmm0
0x140049ceb  xorps   xmm1, xmm1
0x140049cee  movdqu  [rbp+57h+var_A8], xmm1
0x140049cf3  mov     r8d, 6
0x140049cf9  lea     rdx, aClient; "Client"
0x140049d00  lea     rcx, [rbp+57h+var_B8]
0x140049d04  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049d09  nop
0x140049d0a  mov     r9, rbx
0x140049d0d  lea     r8, [rbp+57h+var_B8]
0x140049d11  mov     edx, 4
0x140049d16  lea     rcx, [rbp+57h+var_78]
0x140049d1a  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140049d1f  nop
0x140049d20  lea     rcx, [rbp+57h+var_B8]
0x140049d24  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140049d29  nop
0x140049d2a  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140049d31  mov     [rbp+57h+var_50], rax
0x140049d35  lea     rcx, [rbp+57h+var_40]
0x140049d39  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140049d3e  nop
0x140049d3f  lea     rcx, [rbp+57h+var_98]
0x140049d43  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140049d48  nop
0x140049d49  lea     rcx, [rbp+57h+var_78]
0x140049d4d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140049d52  nop
0x140049d53  sub     dword ptr [rdi+28h], 1
0x140049d57  jnz     short loc_140049D60
0x140049d59  mov     dword ptr [rdi+2Ch], 0
0x140049d60  mov     rcx, rdi; lpCriticalSection
0x140049d63  call    cs:__imp_LeaveCriticalSection
0x140049d69  mov     rax, 8000000000h
0x140049d73  jmp     loc_140049E09
0x140049d78  mov     rax, [rdx+30h]
0x140049d7c  test    rax, rax
0x140049d7f  jz      short loc_140049D85
0x140049d81  lock inc dword ptr [rax+8]
0x140049d85  mov     rsi, [rdx+28h]
0x140049d89  mov     [rbp+57h+var_B8], rsi
0x140049d8d  mov     rbx, [rdx+30h]
0x140049d91  mov     [rbp-59h], rbx
0x140049d95  mov     rcx, r11
0x140049d98  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VSession@Host@Client@AppV@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VSession@Host@Client@AppV@@@std@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VSession@Host@Client@AppV@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VSession@Host@Client@AppV@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<AppV::Client::Host::Session>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<AppV::Client::Host::Session>>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<AppV::Client::Host::Session>>>>,std::_Iterator_base0>)
0x140049d9d  sub     dword ptr [rdi+28h], 1
0x140049da1  jnz     short loc_140049DAA
0x140049da3  mov     dword ptr [rdi+2Ch], 0
0x140049daa  mov     rcx, rdi; lpCriticalSection
0x140049dad  call    cs:__imp_LeaveCriticalSection
0x140049db3  mov     [rbp+57h+var_C8], 0
0x140049db7  mov     rax, [rsi]
0x140049dba  mov     rcx, rsi
0x140049dbd  mov     rax, [rax+10h]
0x140049dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049dc6  mov     rdi, rax
0x140049dc9  test    rbx, rbx
0x140049dcc  jz      short loc_140049E06
0x140049dce  or      ecx, 0FFFFFFFFh
0x140049dd1  lock xadd [rbx+8], ecx
0x140049dd6  cmp     ecx, 1
0x140049dd9  jnz     short loc_140049E06
0x140049ddb  mov     rdx, [rbx]
0x140049dde  mov     rcx, rbx
0x140049de1  mov     rax, [rdx]
0x140049de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049de9  or      eax, 0FFFFFFFFh
0x140049dec  lock xadd [rbx+0Ch], eax
0x140049df1  cmp     eax, 1
0x140049df4  jnz     short loc_140049E06
0x140049df6  mov     rax, [rbx]
0x140049df9  mov     rcx, rbx
0x140049dfc  mov     rax, [rax+8]
0x140049e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049e05  nop
0x140049e06  mov     rax, rdi
0x140049e09  mov     rcx, [rbp+57h+var_20]
0x140049e0d  xor     rcx, rsp; StackCookie
0x140049e10  call    __security_check_cookie
0x140049e15  mov     rbx, [rsp+100h+arg_10]
0x140049e1d  add     rsp, 0F0h
0x140049e24  pop     rdi
0x140049e25  pop     rsi
0x140049e26  pop     rbp
0x140049e27  retn
```
