# AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::~SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>(void)

- ea: `0x14005607c`
- end: `0x140056273`
- name: `??1?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@UEAA@XZ`
- size: `503`
- prototype: `void **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140057160`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x14003c034`
- `0x14003c258`
- `0x14005607c`
- `0x14005a230`
- `0x14006a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14005623f`
- `KERNEL32!DeleteCriticalSection` at `0x14005623f`
- `KERNEL32!CloseHandle` at `0x140056197`
- `KERNEL32!CloseHandle` at `0x1400561ae`
- `KERNEL32!CloseHandle` at `0x140056197`
- `KERNEL32!CloseHandle` at `0x1400561ae`
- `KERNEL32!GetCurrentThreadId` at `0x1400560c7`
- `KERNEL32!GetCurrentThreadId` at `0x1400560c7`
- `KERNEL32!LeaveCriticalSection` at `0x140056188`
- `KERNEL32!LeaveCriticalSection` at `0x140056188`
- `KERNEL32!EnterCriticalSection` at `0x1400560b8`
- `KERNEL32!EnterCriticalSection` at `0x1400560b8`

## string_xrefs

- `0x14005612b`: `RegistryNotify`
- `0x140056106`: `reg. notify cleanup thread was cleaned up during 'dtor the SettingManager`
- `0x1400560da`: `AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::Client::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::~SettingManagerT`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void **__fastcall AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::~SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>(
        __int64 a1)
{
  __int64 v2; // rsi
  void *v4; // rcx
  void *v5; // rcx
  volatile signed __int32 *v6; // rdi
  volatile signed __int32 *v7; // rdi
  void **result; // rax
  _OWORD v9[2]; // [rsp+28h] [rbp-31h] BYREF
  _OWORD v10[2]; // [rsp+48h] [rbp-11h] BYREF
  char *v11[4]; // [rsp+68h] [rbp+Fh] BYREF
  int v12; // [rsp+88h] [rbp+2Fh]

  *(_QWORD *)a1 = &AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::`vftable';
  v2 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ++*(_DWORD *)(v2 + 40) == 1 )
    *(_DWORD *)(v2 + 44) = GetCurrentThreadId();
  if ( *(_BYTE *)(a1 + 112) )
  {
    std::string::string(
      v11,
      "AppV::Client::Service::Impl::SettingManagerT<struct AppV::Client::Service::Impl::SettingManagerEmpty,class AppV::C"
      "lient::Service::Impl::SettingWatcherT<struct AppV::Client::Service::Impl::SettingWatcherEmpty> >::~SettingManagerT");
    v12 = 103;
    memset(v10, 0, sizeof(v10));
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)v10,
      L"reg. notify cleanup thread was cleaned up during 'dtor the SettingManager",
      0x49u);
    memset(v9, 0, sizeof(v9));
    std::wstring::_Construct<1,wchar_t const *>((char **)v9, L"RegistryNotify", 0xEu);
    AppV::DecoratedLog::operator()(v11, 1, v9, v10);
    std::wstring::~wstring((char **)v9);
    std::wstring::~wstring((char **)v10);
    std::string::~string(v11);
    AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::ShutdownWatcherThread(a1);
  }
  if ( (*(_DWORD *)(v2 + 40))-- == 1 )
    *(_DWORD *)(v2 + 44) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
  v4 = *(void **)(a1 + 104);
  if ( v4 )
  {
    CloseHandle(v4);
    *(_QWORD *)(a1 + 104) = 0;
  }
  v5 = *(void **)(a1 + 96);
  if ( v5 )
  {
    CloseHandle(v5);
    *(_QWORD *)(a1 + 96) = 0;
  }
  v6 = *(volatile signed __int32 **)(a1 + 88);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = *(volatile signed __int32 **)(a1 + 72);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)v2);
  result = &AppV::Client::Service::Impl::SettingManager::`vftable';
  *(_QWORD *)a1 = &AppV::Client::Service::Impl::SettingManager::`vftable';
  return result;
}

```

## disassembly

```asm
0x14005607c  mov     [rsp-8+arg_8], rbx
0x140056081  mov     [rsp-8+arg_10], rsi
0x140056086  push    rbp
0x140056087  push    rdi
0x140056088  push    r14
0x14005608a  lea     rbp, [rsp-47h]
0x14005608f  sub     rsp, 0A0h
0x140056096  mov     rax, cs:__security_cookie
0x14005609d  xor     rax, rsp
0x1400560a0  mov     [rbp+57h+var_20], rax
0x1400560a4  mov     rbx, rcx
0x1400560a7  lea     rax, ??_7?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@6B@; const AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::`vftable'
0x1400560ae  mov     [rcx], rax
0x1400560b1  lea     rsi, [rcx+10h]
0x1400560b5  mov     rcx, rsi; lpCriticalSection
0x1400560b8  call    cs:__imp_EnterCriticalSection
0x1400560be  inc     dword ptr [rsi+28h]
0x1400560c1  cmp     dword ptr [rsi+28h], 1
0x1400560c5  jnz     short loc_1400560D0
0x1400560c7  call    cs:__imp_GetCurrentThreadId
0x1400560cd  mov     [rsi+2Ch], eax
0x1400560d0  cmp     byte ptr [rbx+70h], 0
0x1400560d4  jz      loc_140056174
0x1400560da  lea     rdx, aAppvClientServ_22; "AppV::Client::Service::Impl::SettingMan"...
0x1400560e1  lea     rcx, [rbp+57h+var_48]
0x1400560e5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400560ea  mov     [rbp+57h+var_28], 67h ; 'g'
0x1400560f1  xorps   xmm0, xmm0
0x1400560f4  movups  [rbp+57h+var_68], xmm0
0x1400560f8  xorps   xmm1, xmm1
0x1400560fb  movdqu  [rbp+57h+var_58], xmm1
0x140056100  mov     r8d, 49h ; 'I'
0x140056106  lea     rdx, aRegNotifyClean; "reg. notify cleanup thread was cleaned "...
0x14005610d  lea     rcx, [rbp+57h+var_68]
0x140056111  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140056116  xorps   xmm0, xmm0
0x140056119  movups  [rbp+57h+var_88], xmm0
0x14005611d  xorps   xmm1, xmm1
0x140056120  movdqu  [rbp+57h+var_78], xmm1
0x140056125  mov     r8d, 0Eh
0x14005612b  lea     rdx, aRegistrynotify; "RegistryNotify"
0x140056132  lea     rcx, [rbp+57h+var_88]
0x140056136  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005613b  lea     r9, [rbp+57h+var_68]
0x14005613f  lea     r8, [rbp+57h+var_88]
0x140056143  mov     edx, 1
0x140056148  lea     rcx, [rbp+57h+var_48]
0x14005614c  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140056151  lea     rcx, [rbp+57h+var_88]
0x140056155  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005615a  lea     rcx, [rbp+57h+var_68]
0x14005615e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140056163  lea     rcx, [rbp+57h+var_48]
0x140056167  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005616c  mov     rcx, rbx
0x14005616f  call    ?ShutdownWatcherThread@?$SettingManagerT@USettingManagerEmpty@Impl@Service@Client@AppV@@V?$SettingWatcherT@USettingWatcherEmpty@Impl@Service@Client@AppV@@@2345@@Impl@Service@Client@AppV@@AEAA_KXZ; AppV::Client::Service::Impl::SettingManagerT<AppV::Client::Service::Impl::SettingManagerEmpty,AppV::Client::Service::Impl::SettingWatcherT<AppV::Client::Service::Impl::SettingWatcherEmpty>>::ShutdownWatcherThread(void)
0x140056174  or      r14d, 0FFFFFFFFh
0x140056178  add     [rsi+28h], r14d
0x14005617c  jnz     short loc_140056185
0x14005617e  mov     dword ptr [rsi+2Ch], 0
0x140056185  mov     rcx, rsi; lpCriticalSection
0x140056188  call    cs:__imp_LeaveCriticalSection
0x14005618e  mov     rcx, [rbx+68h]; hObject
0x140056192  test    rcx, rcx
0x140056195  jz      short loc_1400561A5
0x140056197  call    cs:__imp_CloseHandle
0x14005619d  mov     qword ptr [rbx+68h], 0
0x1400561a5  mov     rcx, [rbx+60h]; hObject
0x1400561a9  test    rcx, rcx
0x1400561ac  jz      short loc_1400561BC
0x1400561ae  call    cs:__imp_CloseHandle
0x1400561b4  mov     qword ptr [rbx+60h], 0
0x1400561bc  mov     rdi, [rbx+58h]
0x1400561c0  test    rdi, rdi
0x1400561c3  jz      short loc_1400561FC
0x1400561c5  mov     eax, r14d
0x1400561c8  lock xadd [rdi+8], eax
0x1400561cd  add     eax, r14d
0x1400561d0  jnz     short loc_1400561FC
0x1400561d2  mov     rax, [rdi]
0x1400561d5  mov     rcx, rdi
0x1400561d8  mov     rax, [rax]
0x1400561db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400561e0  mov     eax, r14d
0x1400561e3  lock xadd [rdi+0Ch], eax
0x1400561e8  add     eax, r14d
0x1400561eb  jnz     short loc_1400561FC
0x1400561ed  mov     rax, [rdi]
0x1400561f0  mov     rcx, rdi
0x1400561f3  mov     rax, [rax+8]
0x1400561f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400561fc  mov     rdi, [rbx+48h]
0x140056200  test    rdi, rdi
0x140056203  jz      short loc_14005623C
0x140056205  mov     eax, r14d
0x140056208  lock xadd [rdi+8], eax
0x14005620d  add     eax, r14d
0x140056210  jnz     short loc_14005623C
0x140056212  mov     rax, [rdi]
0x140056215  mov     rcx, rdi
0x140056218  mov     rax, [rax]
0x14005621b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056220  mov     eax, r14d
0x140056223  lock xadd [rdi+0Ch], eax
0x140056228  add     eax, r14d
0x14005622b  jnz     short loc_14005623C
0x14005622d  mov     rax, [rdi]
0x140056230  mov     rcx, rdi
0x140056233  mov     rax, [rax+8]
0x140056237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005623c  mov     rcx, rsi; lpCriticalSection
0x14005623f  call    cs:__imp_DeleteCriticalSection
0x140056245  lea     rax, ??_7SettingManager@Impl@Service@Client@AppV@@6B@; const AppV::Client::Service::Impl::SettingManager::`vftable'
0x14005624c  mov     [rbx], rax
0x14005624f  mov     rcx, [rbp+57h+var_20]
0x140056253  xor     rcx, rsp; StackCookie
0x140056256  call    __security_check_cookie
0x14005625b  lea     r11, [rsp+0B0h+var_10]
0x140056263  mov     rbx, [r11+28h]
0x140056267  mov     rsi, [r11+30h]
0x14005626b  mov     rsp, r11
0x14005626e  pop     r14
0x140056270  pop     rdi
0x140056271  pop     rbp
0x140056272  retn
```
