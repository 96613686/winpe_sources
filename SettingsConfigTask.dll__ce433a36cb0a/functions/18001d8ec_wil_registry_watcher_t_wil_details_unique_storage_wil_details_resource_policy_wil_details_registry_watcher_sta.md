# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18001d8ec`
- end: `0x18001dac3`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d840`

## callees

- `0x1800032ac`
- `0x180004264`
- `0x18000460c`
- `0x180004a88`
- `0x18000970c`
- `0x18000972c`
- `0x18001235c`
- `0x180013588`
- `0x180013684`
- `0x18001b968`
- `0x18001d7e8`
- `0x18001d8ec`
- `0x180020104`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001da5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001da5c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001d9de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001d9de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001daaf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001daaf`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001d9ac`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001d9ac`

## string_xrefs

- `0x18001d943`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18001d97a`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18001d9be`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18001da20`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  void *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdi
  unsigned int v10; // ebx
  HANDLE *v12; // r14
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v14; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rbx
  const char *v17; // r9
  struct _TP_WAIT *v18; // rsi
  __int64 v19; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  RTL_SRWLOCK *v22; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v23[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  v23[0] = v7;
  if ( v7 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state((__int64)v7, a2, v8, a4);
  else
    v9 = 0;
  if ( !v9 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v10;
  }
  v12 = (HANDLE *)(v9 + 128);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v9 + 128, 0);
  v10 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_16:
    wil::details::registry_watcher_state::`scalar deleting destructor'((struct _TP_WAIT **)v9);
    return v10;
  }
  v14 = RegNotifyChangeKeyValue(*(HKEY *)(v9 + 120), *(unsigned __int8 *)(v9 + 144), 0x10000005u, *v12, 1);
  if ( v14 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v14,
                  fAsynchronousa);
LABEL_15:
    v10 = LastError;
    goto LABEL_16;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     (PTP_WAIT_CALLBACK)wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v9,
                     0);
  v18 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v18 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v22);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v18);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v22);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v17);
    goto LABEL_15;
  }
  v19 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v23);
    AcquireSRWLockExclusive((PSRWLOCK)(v19 + 152));
    v22 = (RTL_SRWLOCK *)(v19 + 152);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 148), 0xFFFFFFFF) == 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        &v22,
        0);
      wil::details::registry_watcher_state::`scalar deleting destructor'((struct _TP_WAIT **)v19);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v23);
  }
  *a1 = v9;
  SetThreadpoolWait(*(PTP_WAIT *)(v9 + 136), *v12, 0);
  return 0;
}

```

## disassembly

```asm
0x18001d8ec  push    rbx
0x18001d8ee  push    rsi
0x18001d8ef  push    rdi
0x18001d8f0  push    r14
0x18001d8f2  push    r15
0x18001d8f4  sub     rsp, 40h
0x18001d8f8  mov     rbx, r9
0x18001d8fb  mov     rdi, rdx
0x18001d8fe  mov     r15, rcx
0x18001d901  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d908  mov     ecx, 0A0h; unsigned __int64
0x18001d90d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d912  mov     [rsp+68h+var_30], rax
0x18001d917  test    rax, rax
0x18001d91a  jz      short loc_18001D92F
0x18001d91c  mov     r9, rbx
0x18001d91f  mov     rdx, rdi
0x18001d922  mov     rcx, rax
0x18001d925  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18001d92a  mov     rdi, rax
0x18001d92d  jmp     short loc_18001D931
0x18001d92f  xor     edi, edi
0x18001d931  test    rdi, rdi
0x18001d934  jnz     short loc_18001D95B
0x18001d936  mov     rcx, [rsp+68h]; this
0x18001d93b  mov     ebx, 8007000Eh
0x18001d940  mov     r9d, ebx; char *
0x18001d943  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d94a  mov     edx, 0CBBh; void *
0x18001d94f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d954  mov     eax, ebx
0x18001d956  jmp     loc_18001DAB7
0x18001d95b  lea     r14, [rdi+80h]
0x18001d962  xor     edx, edx
0x18001d964  mov     rcx, r14
0x18001d967  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001d96c  mov     ebx, eax
0x18001d96e  test    eax, eax
0x18001d970  jns     short loc_18001D990
0x18001d972  mov     rcx, [rsp+68h]; this
0x18001d977  mov     r9d, eax; char *
0x18001d97a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d981  mov     edx, 0CBCh; void *
0x18001d986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d98b  jmp     loc_18001DA33
0x18001d990  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x18001d997  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x18001d99f  mov     r9, [r14]; hEvent
0x18001d9a2  mov     r8d, 10000005h; dwNotifyFilter
0x18001d9a8  mov     rcx, [rdi+78h]; hKey
0x18001d9ac  call    cs:__imp_RegNotifyChangeKeyValue
0x18001d9b2  test    eax, eax
0x18001d9b4  jz      short loc_18001D9D1
0x18001d9b6  mov     rcx, [rsp+68h]; this
0x18001d9bb  mov     r9d, eax; char *
0x18001d9be  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d9c5  mov     edx, 0CC2h; void *
0x18001d9ca  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d9cf  jmp     short loc_18001DA31
0x18001d9d1  xor     r8d, r8d; pcbe
0x18001d9d4  mov     rdx, rdi; pv
0x18001d9d7  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001d9de  call    cs:__imp_CreateThreadpoolWait
0x18001d9e4  mov     rbx, rax
0x18001d9e7  mov     rsi, [rdi+88h]
0x18001d9ee  test    rsi, rsi
0x18001d9f1  jz      short loc_18001DA0F
0x18001d9f3  lea     rcx, [rsp+68h+var_38]; this
0x18001d9f8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001d9fd  mov     rcx, rsi; pwa
0x18001da00  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x18001da05  lea     rcx, [rsp+68h+var_38]; this
0x18001da0a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001da0f  mov     [rdi+88h], rbx
0x18001da16  test    rbx, rbx
0x18001da19  jnz     short loc_18001DA40
0x18001da1b  mov     rcx, [rsp+68h]; this
0x18001da20  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001da27  mov     edx, 0CC5h; void *
0x18001da2c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001da31  mov     ebx, eax
0x18001da33  mov     rcx, rdi; this
0x18001da36  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18001da3b  jmp     loc_18001D954
0x18001da40  mov     rsi, [r15]
0x18001da43  test    rsi, rsi
0x18001da46  jz      short loc_18001DA9F
0x18001da48  lea     rcx, [rsp+68h+var_30]; this
0x18001da4d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001da52  lea     rbx, [rsi+98h]
0x18001da59  mov     rcx, rbx; SRWLock
0x18001da5c  call    cs:__imp_AcquireSRWLockExclusive
0x18001da62  mov     [rsp+68h+var_38], rbx
0x18001da67  or      eax, 0FFFFFFFFh
0x18001da6a  lock xadd [rsi+94h], eax
0x18001da72  cmp     eax, 1
0x18001da75  jnz     short loc_18001DA8B
0x18001da77  xor     edx, edx
0x18001da79  lea     rcx, [rsp+68h+var_38]
0x18001da7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18001da83  mov     rcx, rsi; this
0x18001da86  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18001da8b  lea     rcx, [rsp+68h+var_38]
0x18001da90  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001da95  lea     rcx, [rsp+68h+var_30]; this
0x18001da9a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001da9f  mov     [r15], rdi
0x18001daa2  xor     r8d, r8d; pftTimeout
0x18001daa5  mov     rdx, [r14]; h
0x18001daa8  mov     rcx, [rdi+88h]; pwa
0x18001daaf  call    cs:__imp_SetThreadpoolWait
0x18001dab5  xor     eax, eax
0x18001dab7  add     rsp, 40h
0x18001dabb  pop     r15
0x18001dabd  pop     r14
0x18001dabf  pop     rdi
0x18001dac0  pop     rsi
0x18001dac1  pop     rbx
0x18001dac2  retn
```
