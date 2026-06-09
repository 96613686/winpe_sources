# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180085dc0`
- end: `0x180085f7c`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180085cd8`

## callees

- `0x1800088bc`
- `0x180009a74`
- `0x180009d58`
- `0x18000b694`
- `0x18000b6b4`
- `0x18000dc5c`
- `0x1800153a0`
- `0x18004e0c8`
- `0x18004fd20`
- `0x1800843c8`
- `0x1800847ac`
- `0x180085dc0`
- `0x180085f84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180085f17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180085f17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085f67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180085f67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085eb7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180085eb7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180085e85`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180085e85`

## string_xrefs

- `0x180085e1e`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180085e53`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180085e97`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180085eda`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        __int64 *a1,
        __int64 a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdi
  unsigned int v11; // ebx
  HANDLE *v13; // r14
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v15; // edx
  unsigned int v16; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v19; // r9
  __int64 v20; // rsi
  unsigned int v21; // edx
  BOOL fAsynchronous; // [rsp+20h] [rbp-58h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-58h]
  __int64 v24; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v25[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v25[0] = v8;
  if ( v8 )
  {
    LOBYTE(v9) = a3;
    v10 = wil::details::registry_watcher_state::registry_watcher_state(v8, a2, v9, a4);
  }
  else
  {
    v10 = 0;
  }
  if ( !v10 )
  {
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v11;
  }
  v13 = (HANDLE *)(v10 + 128);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v10 + 128);
  v11 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_14:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v10, v15);
    return v11;
  }
  v16 = RegNotifyChangeKeyValue(*(HKEY *)(v10 + 120), *(unsigned __int8 *)(v10 + 144), 0x10000005u, *v13, 1);
  if ( v16 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  (const char *)v16,
                  fAsynchronousa);
LABEL_13:
    v11 = LastError;
    goto LABEL_14;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v10,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v10 + 136,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v10 + 136) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  v19);
    goto LABEL_13;
  }
  v20 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v25);
    AcquireSRWLockExclusive((PSRWLOCK)(v20 + 152));
    v24 = v20 + 152;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 + 148), 0xFFFFFFFF) == 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        &v24,
        0);
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v20,
        v21);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v25);
  }
  *a1 = v10;
  SetThreadpoolWait(*(PTP_WAIT *)(v10 + 136), *v13, 0);
  return 0;
}

```

## disassembly

```asm
0x180085dc0  push    rbx
0x180085dc2  push    rbp
0x180085dc3  push    rsi
0x180085dc4  push    rdi
0x180085dc5  push    r14
0x180085dc7  push    r15
0x180085dc9  sub     rsp, 48h
0x180085dcd  mov     rbx, r9
0x180085dd0  mov     dil, r8b
0x180085dd3  mov     rsi, rdx
0x180085dd6  mov     rbp, rcx
0x180085dd9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180085de0  mov     ecx, 0A0h; unsigned __int64
0x180085de5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180085dea  mov     [rsp+78h+var_40], rax
0x180085def  test    rax, rax
0x180085df2  jz      short loc_180085E0A
0x180085df4  mov     r9, rbx
0x180085df7  mov     r8b, dil
0x180085dfa  mov     rdx, rsi
0x180085dfd  mov     rcx, rax
0x180085e00  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180085e05  mov     rdi, rax
0x180085e08  jmp     short loc_180085E0C
0x180085e0a  xor     edi, edi
0x180085e0c  test    rdi, rdi
0x180085e0f  jnz     short loc_180085E36
0x180085e11  mov     rcx, [rsp+78h]; this
0x180085e16  mov     ebx, 8007000Eh
0x180085e1b  mov     r9d, ebx; char *
0x180085e1e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180085e25  mov     edx, 0CBBh; void *
0x180085e2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085e2f  mov     eax, ebx
0x180085e31  jmp     loc_180085F6F
0x180085e36  lea     r14, [rdi+80h]
0x180085e3d  mov     rcx, r14
0x180085e40  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180085e45  mov     ebx, eax
0x180085e47  test    eax, eax
0x180085e49  jns     short loc_180085E69
0x180085e4b  mov     rcx, [rsp+78h]; this
0x180085e50  mov     r9d, eax; char *
0x180085e53  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180085e5a  mov     edx, 0CBCh; void *
0x180085e5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085e64  jmp     loc_180085EED
0x180085e69  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x180085e70  mov     [rsp+78h+fAsynchronous], 1; unsigned int
0x180085e78  mov     r9, [r14]; hEvent
0x180085e7b  mov     r8d, 10000005h; dwNotifyFilter
0x180085e81  mov     rcx, [rdi+78h]; hKey
0x180085e85  call    cs:__imp_RegNotifyChangeKeyValue
0x180085e8b  test    eax, eax
0x180085e8d  jz      short loc_180085EAA
0x180085e8f  mov     rcx, [rsp+78h]; this
0x180085e94  mov     r9d, eax; char *
0x180085e97  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180085e9e  mov     edx, 0CC2h; void *
0x180085ea3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180085ea8  jmp     short loc_180085EEB
0x180085eaa  xor     r8d, r8d; pcbe
0x180085ead  mov     rdx, rdi; pv
0x180085eb0  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180085eb7  call    cs:__imp_CreateThreadpoolWait
0x180085ebd  lea     r15, [rdi+88h]
0x180085ec4  mov     rdx, rax
0x180085ec7  mov     rcx, r15
0x180085eca  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180085ecf  cmp     qword ptr [r15], 0
0x180085ed3  jnz     short loc_180085EFA
0x180085ed5  mov     rcx, [rsp+78h]; this
0x180085eda  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180085ee1  mov     edx, 0CC5h; void *
0x180085ee6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180085eeb  mov     ebx, eax
0x180085eed  mov     rcx, rdi; this
0x180085ef0  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180085ef5  jmp     loc_180085E2F
0x180085efa  mov     rsi, [rbp+0]
0x180085efe  test    rsi, rsi
0x180085f01  jz      short loc_180085F5A
0x180085f03  lea     rcx, [rsp+78h+var_40]; this
0x180085f08  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180085f0d  lea     rbx, [rsi+98h]
0x180085f14  mov     rcx, rbx; SRWLock
0x180085f17  call    cs:__imp_AcquireSRWLockExclusive
0x180085f1d  mov     [rsp+78h+var_48], rbx
0x180085f22  or      eax, 0FFFFFFFFh
0x180085f25  lock xadd [rsi+94h], eax
0x180085f2d  cmp     eax, 1
0x180085f30  jnz     short loc_180085F46
0x180085f32  xor     edx, edx
0x180085f34  lea     rcx, [rsp+78h+var_48]
0x180085f39  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180085f3e  mov     rcx, rsi; this
0x180085f41  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180085f46  lea     rcx, [rsp+78h+var_48]
0x180085f4b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180085f50  lea     rcx, [rsp+78h+var_40]; this
0x180085f55  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180085f5a  mov     [rbp+0], rdi
0x180085f5e  xor     r8d, r8d; pftTimeout
0x180085f61  mov     rdx, [r14]; h
0x180085f64  mov     rcx, [r15]; pwa
0x180085f67  call    cs:__imp_SetThreadpoolWait
0x180085f6d  xor     eax, eax
0x180085f6f  add     rsp, 48h
0x180085f73  pop     r15
0x180085f75  pop     r14
0x180085f77  pop     rdi
0x180085f78  pop     rsi
0x180085f79  pop     rbp
0x180085f7a  pop     rbx
0x180085f7b  retn
```
