# AppV::Client::Host::UserManagerImpl::SessionAsync(_TP_CALLBACK_INSTANCE *,void *,bool)

- ea: `0x14004a950`
- end: `0x14004adfb`
- name: `?SessionAsync@UserManagerImpl@Host@Client@AppV@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX_N@Z`
- size: `1195`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004a590`
- `0x14004a5b0`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x1400094bc`
- `0x140010158`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x140049250`
- `0x140049bcc`
- `0x140049e30`
- `0x14004a950`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004abd3`
- `KERNEL32!GetLastError` at `0x14004abd3`
- `KERNEL32!CallbackMayRunLong` at `0x14004a982`
- `KERNEL32!CallbackMayRunLong` at `0x14004a982`

## string_xrefs

- `0x14004ab1b`: `User Manager background thread waiting for concurrent operations on session %1% to complete`
- `0x14004ac08`: `User Manager background thread failed to wait for concurrent operations on session %1% to complete, error = %2%`
- `0x14004acd7`: `User Manager background thread finished waiting for concurrent operations on session %1% and can proceed`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall AppV::Client::Host::UserManagerImpl::SessionAsync(struct _TP_CALLBACK_INSTANCE *a1, void *a2, char a3)
{
  unsigned int v4; // esi
  AppV::Client::Host::UserManagerImpl *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // r14
  volatile signed __int32 *v8; // rdi
  _QWORD *v9; // rax
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rbx
  unsigned int v25; // [rsp+20h] [rbp-A9h] BYREF
  AppV::Client::Host::UserManagerImpl *v26; // [rsp+28h] [rbp-A1h] BYREF
  volatile signed __int32 *v27; // [rsp+30h] [rbp-99h]
  _QWORD *v28; // [rsp+38h] [rbp-91h] BYREF
  _QWORD *v29; // [rsp+40h] [rbp-89h] BYREF
  __int128 v30; // [rsp+48h] [rbp-81h] BYREF
  __int128 v31; // [rsp+58h] [rbp-71h] BYREF
  __int64 v32; // [rsp+68h] [rbp-61h]
  volatile signed __int32 *v33; // [rsp+70h] [rbp-59h]
  __int128 v34; // [rsp+78h] [rbp-51h] BYREF
  __int64 v35; // [rsp+88h] [rbp-41h]
  __int64 v36; // [rsp+90h] [rbp-39h]
  char *v37[4]; // [rsp+98h] [rbp-31h] BYREF
  int v38; // [rsp+B8h] [rbp-11h]
  _QWORD v39[2]; // [rsp+C0h] [rbp-9h] BYREF
  char *v40[4]; // [rsp+D0h] [rbp+7h] BYREF

  v4 = (unsigned int)a2;
  CallbackMayRunLong(a1);
  AppV::Client::Host::UserManagerImpl::GetInstance(&v26);
  v5 = v26;
  if ( !v26 )
  {
    v11 = v27;
    if ( !v27 )
      return;
    goto LABEL_24;
  }
  *(_QWORD *)&v31 =  AppV::Client::Service::NotificationManager::`vcall'{16,{flat}};
  DWORD2(v31) = v4;
  v6 = *((_QWORD *)v26 + 4);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = *((_QWORD *)v5 + 3);
  v32 = v7;
  v8 = (volatile signed __int32 *)*((_QWORD *)v5 + 4);
  v33 = v8;
  v9 = operator new(0x28u);
  v28 = v9;
  *v9 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,unsigned __int64 (AppV::Client::Host::SessionQueue::*)(unsigned long),std::shared_ptr<AppV::Client::Host::SessionQueue> &,unsigned long &>>::`vftable';
  v9[1] =  AppV::Client::Service::NotificationManager::`vcall'{16,{flat}};
  *((_DWORD *)v9 + 4) = v4;
  v9[3] = 0;
  v9[4] = 0;
  if ( v8 )
    _InterlockedIncrement(v8 + 2);
  v9[3] = v7;
  v9[4] = v8;
  v29 = v9;
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v30 = 0;
  if ( ((*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**((_QWORD **)v26 + 3) + 24LL))(
          *((_QWORD *)v26 + 3),
          v4,
          &v30)
      & 0x8000000000LL) != 0 )
  {
    v25 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 8LL))(v30);
    std::string::string(v37, "AppV::Client::Host::UserManagerImpl::SessionAsync");
    v38 = 417;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v12);
    v31 = 0;
    v32 = 0;
    v33 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v31,
      L"User Manager background thread waiting for concurrent operations on session %1% to complete",
      0x5Bu);
    v14 = AppV::Log::fmt(v13, v39, &v31);
    v15 = AppV::LogFormatter::operator%<unsigned long>(v14, (__int64)&v25);
    v34 = 0;
    v35 = 0;
    v36 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v34, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v37, 4, (int)&v34, v15);
    std::wstring::~wstring((char **)&v34);
    v39[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v40);
    std::wstring::~wstring((char **)&v31);
    std::string::~string(v37);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 16LL))(v30) )
    {
      std::string::string(v37, "AppV::Client::Host::UserManagerImpl::SessionAsync");
      v38 = 429;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v21);
      v34 = 0;
      v35 = 0;
      v36 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v34,
        L"User Manager background thread finished waiting for concurrent operations on session %1% and can proceed",
        0x68u);
      v23 = AppV::Log::fmt(v22, v39, &v34);
      v24 = AppV::LogFormatter::operator%<unsigned long>(v23, (__int64)&v25);
      v31 = 0;
      v32 = 0;
      v33 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v37, 4, (int)&v31, v24);
    }
    else
    {
      LODWORD(v28) = GetLastError();
      std::string::string(v37, "AppV::Client::Host::UserManagerImpl::SessionAsync");
      v38 = 425;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v16);
      v34 = 0;
      v35 = 0;
      v36 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v34,
        L"User Manager background thread failed to wait for concurrent operations on session %1% to complete, error = %2%",
        0x6Fu);
      v18 = AppV::Log::fmt(v17, v39, &v34);
      v19 = AppV::LogFormatter::operator%<unsigned long>(v18, (__int64)&v25);
      v20 = AppV::LogFormatter::operator%<unsigned long>(v19, (__int64)&v28);
      v31 = 0;
      v32 = 0;
      v33 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v37, 2, (int)&v31, v20);
    }
    std::wstring::~wstring((char **)&v31);
    v39[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v40);
    std::wstring::~wstring((char **)&v34);
    std::string::~string(v37);
    if ( a3 )
      AppV::Client::Host::UserManagerImpl::InternalLogon((struct _RTL_CRITICAL_SECTION *)v26, v25);
    else
      AppV::Client::Host::UserManagerImpl::InternalLogoff((struct _RTL_CRITICAL_SECTION *)v26, v25);
  }
  v10 = (volatile signed __int32 *)*((_QWORD *)&v30 + 1);
  if ( *((_QWORD *)&v30 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v29);
  v11 = v27;
  if ( v27 )
  {
LABEL_24:
    if ( !_InterlockedDecrement(v11 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( !_InterlockedDecrement(v11 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
}

```

## disassembly

```asm
0x14004a950  mov     [rsp-8+arg_10], rbx
0x14004a955  mov     [rsp-8+arg_18], rsi
0x14004a95a  push    rbp
0x14004a95b  push    rdi
0x14004a95c  push    r12
0x14004a95e  push    r14
0x14004a960  push    r15
0x14004a962  lea     rbp, [rsp-37h]
0x14004a967  sub     rsp, 100h
0x14004a96e  mov     rax, cs:__security_cookie
0x14004a975  xor     rax, rsp
0x14004a978  mov     [rbp+57h+var_30], rax
0x14004a97c  mov     r15b, r8b
0x14004a97f  mov     rsi, rdx
0x14004a982  call    cs:__imp_CallbackMayRunLong
0x14004a988  lea     rcx, [rsp+120h+var_F8]
0x14004a98d  call    ?GetInstance@UserManagerImpl@Host@Client@AppV@@CA?AV?$shared_ptr@VUserManagerImpl@Host@Client@AppV@@@std@@XZ; AppV::Client::Host::UserManagerImpl::GetInstance(void)
0x14004a992  nop
0x14004a993  mov     rdi, [rsp+120h+var_F8]
0x14004a998  xor     r12d, r12d
0x14004a99b  test    rdi, rdi
0x14004a99e  jz      loc_14004AD93
0x14004a9a4  lea     rbx, ??_9NotificationManager@Service@Client@AppV@@$BBA@AA; [thunk]: AppV::Client::Service::NotificationManager::`vcall'{16,{flat}}
0x14004a9ab  mov     qword ptr [rbp+57h+var_C8], rbx
0x14004a9af  mov     dword ptr [rbp+57h+var_C8+8], esi
0x14004a9b2  mov     rax, [rdi+20h]
0x14004a9b6  test    rax, rax
0x14004a9b9  jz      short loc_14004A9BF
0x14004a9bb  lock inc dword ptr [rax+8]
0x14004a9bf  mov     r14, [rdi+18h]
0x14004a9c3  mov     [rbp+57h+var_B8], r14
0x14004a9c7  mov     rdi, [rdi+20h]
0x14004a9cb  mov     [rbp+57h+var_B0], rdi
0x14004a9cf  mov     ecx, 28h ; '('; Size
0x14004a9d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004a9d9  mov     [rsp+120h+var_E8], rax
0x14004a9de  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P8SessionQueue@Host@Client@AppV@@EAA_KK@ZAEAV?$shared_ptr@VSessionQueue@Host@Client@AppV@@@2@AEAK@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,unsigned __int64 (AppV::Client::Host::SessionQueue::*)(ulong),std::shared_ptr<AppV::Client::Host::SessionQueue> &,ulong &>>::`vftable'
0x14004a9e5  mov     [rax], rcx
0x14004a9e8  mov     [rax+8], rbx
0x14004a9ec  mov     [rax+10h], esi
0x14004a9ef  mov     [rax+18h], r12
0x14004a9f3  mov     [rax+20h], r12
0x14004a9f7  mov     rbx, rdi
0x14004a9fa  test    rdi, rdi
0x14004a9fd  jz      short loc_14004AA03
0x14004a9ff  lock inc dword ptr [rdi+8]
0x14004aa03  mov     [rax+18h], r14
0x14004aa07  mov     [rax+20h], rdi
0x14004aa0b  mov     [rsp+120h+var_E0], rax
0x14004aa10  or      edi, 0FFFFFFFFh
0x14004aa13  test    rbx, rbx
0x14004aa16  jz      short loc_14004AA4B
0x14004aa18  mov     eax, edi
0x14004aa1a  lock xadd [rbx+8], eax
0x14004aa1f  add     eax, edi
0x14004aa21  jnz     short loc_14004AA4B
0x14004aa23  mov     rax, [rbx]
0x14004aa26  mov     rcx, rbx
0x14004aa29  mov     rax, [rax]
0x14004aa2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aa31  mov     eax, edi
0x14004aa33  lock xadd [rbx+0Ch], eax
0x14004aa38  add     eax, edi
0x14004aa3a  jnz     short loc_14004AA4B
0x14004aa3c  mov     rax, [rbx]
0x14004aa3f  mov     rcx, rbx
0x14004aa42  mov     rax, [rax+8]
0x14004aa46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aa4b  xorps   xmm0, xmm0
0x14004aa4e  movdqu  [rsp+120h+var_D8], xmm0
0x14004aa54  mov     rax, [rsp+120h+var_F8]
0x14004aa59  mov     rcx, [rax+18h]
0x14004aa5d  mov     rax, [rcx]
0x14004aa60  lea     r8, [rsp+120h+var_D8]
0x14004aa65  mov     edx, esi
0x14004aa67  mov     rax, [rax+18h]
0x14004aa6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aa70  bt      rax, 27h ; '''
0x14004aa75  jb      short loc_14004AAD2
0x14004aa77  mov     rbx, qword ptr [rbp+57h+var_D8+8]
0x14004aa7b  test    rbx, rbx
0x14004aa7e  jz      short loc_14004AAB4
0x14004aa80  mov     eax, edi
0x14004aa82  lock xadd [rbx+8], eax
0x14004aa87  add     eax, edi
0x14004aa89  jnz     short loc_14004AAB4
0x14004aa8b  mov     rax, [rbx]
0x14004aa8e  mov     rcx, rbx
0x14004aa91  mov     rax, [rax]
0x14004aa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aa99  mov     eax, edi
0x14004aa9b  lock xadd [rbx+0Ch], eax
0x14004aaa0  add     eax, edi
0x14004aaa2  jnz     short loc_14004AAB4
0x14004aaa4  mov     rax, [rbx]
0x14004aaa7  mov     rcx, rbx
0x14004aaaa  mov     rax, [rax+8]
0x14004aaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aab3  nop
0x14004aab4  lea     rcx, [rsp+120h+var_E0]; this
0x14004aab9  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14004aabe  nop
0x14004aabf  mov     rbx, [rsp+120h+var_F0]
0x14004aac4  test    rbx, rbx
0x14004aac7  jz      loc_14004ADD3
0x14004aacd  jmp     loc_14004ADA0
0x14004aad2  mov     rcx, qword ptr [rsp+120h+var_D8]
0x14004aad7  mov     rax, [rcx]
0x14004aada  mov     rax, [rax+8]
0x14004aade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aae3  mov     [rsp+120h+var_100], eax
0x14004aae7  lea     rsi, aAppvClientHost_26; "AppV::Client::Host::UserManagerImpl::Se"...
0x14004aaee  mov     rdx, rsi
0x14004aaf1  lea     rcx, [rbp+57h+var_88]
0x14004aaf5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004aafa  mov     [rbp+57h+var_68], 1A1h
0x14004ab01  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004ab06  xorps   xmm0, xmm0
0x14004ab09  movups  [rbp+57h+var_C8], xmm0
0x14004ab0d  mov     [rbp+57h+var_B8], r12
0x14004ab11  mov     [rbp+57h+var_B0], r12
0x14004ab15  mov     r8d, 5Bh ; '['
0x14004ab1b  lea     rdx, aUserManagerBac_0; "User Manager background thread waiting "...
0x14004ab22  lea     rcx, [rbp+57h+var_C8]
0x14004ab26  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004ab2b  nop
0x14004ab2c  lea     r8, [rbp+57h+var_C8]
0x14004ab30  lea     rdx, [rbp+57h+var_60]
0x14004ab34  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004ab39  nop
0x14004ab3a  lea     rdx, [rsp+120h+var_100]
0x14004ab3f  mov     rcx, rax
0x14004ab42  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004ab47  mov     rbx, rax
0x14004ab4a  xorps   xmm0, xmm0
0x14004ab4d  movups  [rbp+57h+var_A8], xmm0
0x14004ab51  mov     [rbp+57h+var_98], r12
0x14004ab55  mov     [rbp+57h+var_90], r12
0x14004ab59  mov     r14d, 6
0x14004ab5f  mov     r8d, r14d
0x14004ab62  lea     rdx, aClient; "Client"
0x14004ab69  lea     rcx, [rbp+57h+var_A8]
0x14004ab6d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004ab72  nop
0x14004ab73  mov     r9, rbx
0x14004ab76  lea     r8, [rbp+57h+var_A8]
0x14004ab7a  lea     edx, [r14-2]
0x14004ab7e  lea     rcx, [rbp+57h+var_88]
0x14004ab82  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004ab87  nop
0x14004ab88  lea     rcx, [rbp+57h+var_A8]
0x14004ab8c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ab91  nop
0x14004ab92  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004ab99  mov     [rbp+57h+var_60], rax
0x14004ab9d  lea     rcx, [rbp+57h+var_50]
0x14004aba1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004aba6  nop
0x14004aba7  lea     rcx, [rbp+57h+var_C8]
0x14004abab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004abb0  nop
0x14004abb1  lea     rcx, [rbp+57h+var_88]
0x14004abb5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004abba  mov     rcx, qword ptr [rsp+120h+var_D8]
0x14004abbf  mov     rax, [rcx]
0x14004abc2  mov     rax, [rax+10h]
0x14004abc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004abcb  test    al, al
0x14004abcd  jnz     loc_14004ACAA
0x14004abd3  call    cs:__imp_GetLastError
0x14004abd9  mov     dword ptr [rsp+120h+var_E8], eax
0x14004abdd  mov     rdx, rsi
0x14004abe0  lea     rcx, [rbp+57h+var_88]
0x14004abe4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004abe9  mov     [rbp+57h+var_68], 1A9h
0x14004abf0  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004abf5  xorps   xmm0, xmm0
0x14004abf8  movups  [rbp+57h+var_A8], xmm0
0x14004abfc  mov     [rbp+57h+var_98], r12
0x14004ac00  mov     [rbp+57h+var_90], r12
0x14004ac04  lea     r8d, [r14+69h]
0x14004ac08  lea     rdx, aUserManagerBac_1; "User Manager background thread failed t"...
0x14004ac0f  lea     rcx, [rbp+57h+var_A8]
0x14004ac13  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004ac18  nop
0x14004ac19  lea     r8, [rbp+57h+var_A8]
0x14004ac1d  lea     rdx, [rbp+57h+var_60]
0x14004ac21  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004ac26  nop
0x14004ac27  lea     rdx, [rsp+120h+var_100]
0x14004ac2c  mov     rcx, rax
0x14004ac2f  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004ac34  lea     rdx, [rsp+120h+var_E8]
0x14004ac39  mov     rcx, rax
0x14004ac3c  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004ac41  mov     rbx, rax
0x14004ac44  xorps   xmm0, xmm0
0x14004ac47  movups  [rbp+57h+var_C8], xmm0
0x14004ac4b  mov     [rbp+57h+var_B8], r12
0x14004ac4f  mov     [rbp+57h+var_B0], r12
0x14004ac53  mov     r8d, r14d
0x14004ac56  lea     rdx, aClient; "Client"
0x14004ac5d  lea     rcx, [rbp+57h+var_C8]
0x14004ac61  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004ac66  nop
0x14004ac67  mov     r9, rbx
0x14004ac6a  lea     r8, [rbp+57h+var_C8]
0x14004ac6e  lea     edx, [r14-4]
0x14004ac72  lea     rcx, [rbp+57h+var_88]
0x14004ac76  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004ac7b  nop
0x14004ac7c  lea     rcx, [rbp+57h+var_C8]
0x14004ac80  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ac85  nop
0x14004ac86  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004ac8d  mov     [rbp+57h+var_60], rax
0x14004ac91  lea     rcx, [rbp+57h+var_50]
0x14004ac95  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ac9a  nop
0x14004ac9b  lea     rcx, [rbp+57h+var_A8]
0x14004ac9f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004aca4  nop
0x14004aca5  jmp     loc_14004AD68
0x14004acaa  mov     rdx, rsi
0x14004acad  lea     rcx, [rbp+57h+var_88]
0x14004acb1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004acb6  mov     [rbp+57h+var_68], 1ADh
0x14004acbd  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004acc2  xorps   xmm0, xmm0
0x14004acc5  movups  [rbp+57h+var_A8], xmm0
0x14004acc9  mov     [rbp+57h+var_98], r12
0x14004accd  mov     [rbp+57h+var_90], r12
0x14004acd1  mov     r8d, 68h ; 'h'
0x14004acd7  lea     rdx, aUserManagerBac; "User Manager background thread finished"...
0x14004acde  lea     rcx, [rbp+57h+var_A8]
0x14004ace2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004ace7  nop
0x14004ace8  lea     r8, [rbp+57h+var_A8]
0x14004acec  lea     rdx, [rbp+57h+var_60]
0x14004acf0  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004acf5  nop
0x14004acf6  lea     rdx, [rsp+120h+var_100]
0x14004acfb  mov     rcx, rax
0x14004acfe  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004ad03  mov     rbx, rax
0x14004ad06  xorps   xmm0, xmm0
0x14004ad09  movups  [rbp+57h+var_C8], xmm0
0x14004ad0d  mov     [rbp+57h+var_B8], r12
0x14004ad11  mov     [rbp+57h+var_B0], r12
0x14004ad15  mov     r8, r14
0x14004ad18  lea     rdx, aClient; "Client"
0x14004ad1f  lea     rcx, [rbp+57h+var_C8]
0x14004ad23  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004ad28  nop
0x14004ad29  mov     r9, rbx
0x14004ad2c  lea     r8, [rbp+57h+var_C8]
0x14004ad30  mov     edx, 4
0x14004ad35  lea     rcx, [rbp+57h+var_88]
0x14004ad39  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004ad3e  nop
0x14004ad3f  lea     rcx, [rbp+57h+var_C8]
0x14004ad43  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ad48  nop
0x14004ad49  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004ad50  mov     [rbp+57h+var_60], rax
0x14004ad54  lea     rcx, [rbp+57h+var_50]
0x14004ad58  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ad5d  nop
0x14004ad5e  lea     rcx, [rbp+57h+var_A8]
0x14004ad62  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004ad67  nop
0x14004ad68  lea     rcx, [rbp+57h+var_88]
0x14004ad6c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004ad71  mov     edx, [rsp+120h+var_100]; unsigned int
0x14004ad75  mov     rcx, [rsp+120h+var_F8]; this
0x14004ad7a  test    r15b, r15b
0x14004ad7d  jz      short loc_14004AD89
0x14004ad7f  call    ?InternalLogon@UserManagerImpl@Host@Client@AppV@@AEAA_KK@Z; AppV::Client::Host::UserManagerImpl::InternalLogon(ulong)
0x14004ad84  jmp     loc_14004AA77
0x14004ad89  call    ?InternalLogoff@UserManagerImpl@Host@Client@AppV@@AEAA_KK@Z; AppV::Client::Host::UserManagerImpl::InternalLogoff(ulong)
0x14004ad8e  jmp     loc_14004AA77
0x14004ad93  mov     rbx, [rsp+120h+var_F0]
0x14004ad98  test    rbx, rbx
0x14004ad9b  jz      short loc_14004ADD3
0x14004ad9d  or      edi, 0FFFFFFFFh
0x14004ada0  mov     eax, edi
0x14004ada2  lock xadd [rbx+8], eax
0x14004ada7  add     eax, edi
0x14004ada9  jnz     short loc_14004ADD3
0x14004adab  mov     rax, [rbx]
0x14004adae  mov     rcx, rbx
0x14004adb1  mov     rax, [rax]
0x14004adb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004adb9  mov     eax, edi
0x14004adbb  lock xadd [rbx+0Ch], eax
0x14004adc0  add     eax, edi
0x14004adc2  jnz     short loc_14004ADD3
0x14004adc4  mov     rax, [rbx]
0x14004adc7  mov     rcx, rbx
0x14004adca  mov     rax, [rax+8]
  ... truncated ...
```
