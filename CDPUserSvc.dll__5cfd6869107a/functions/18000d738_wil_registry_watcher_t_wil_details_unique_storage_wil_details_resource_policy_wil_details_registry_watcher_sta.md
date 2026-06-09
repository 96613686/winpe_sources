# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18000d738`
- end: `0x18000d8a0`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ebe0`

## callees

- `0x18000c810`
- `0x18000d738`
- `0x18000dae4`
- `0x18001d804`
- `0x18001d9b0`
- `0x18001e798`
- `0x18001f7cc`
- `0x180025f28`
- `0x18002c5e4`
- `0x180053cdc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d88e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d88e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000d82c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000d82c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000d7fa`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000d7fa`

## string_xrefs

- `0x18000d793`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18000d7c8`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18000d80c`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18000d84f`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdi
  unsigned int v11; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v14; // edx
  unsigned int v15; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v18; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v11;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v10 + 128);
  v11 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_14:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v10, v14);
    return v11;
  }
  v15 = RegNotifyChangeKeyValue(
          *(HKEY *)(v10 + 120),
          *(unsigned __int8 *)(v10 + 144),
          0x10000005u,
          *(HANDLE *)(v10 + 128),
          1);
  if ( v15 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v15,
                  fAsynchronousa);
LABEL_13:
    v11 = LastError;
    goto LABEL_14;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v18);
    goto LABEL_13;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v10);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 136LL), *(HANDLE *)(*(_QWORD *)a1 + 128LL), 0);
  return 0;
}

```

## disassembly

```asm
0x18000d738  push    rbx
0x18000d73a  push    rsi
0x18000d73b  push    rdi
0x18000d73c  push    r14
0x18000d73e  sub     rsp, 48h
0x18000d742  mov     rbx, r9
0x18000d745  mov     dil, r8b
0x18000d748  mov     rsi, rdx
0x18000d74b  mov     r14, rcx
0x18000d74e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d755  mov     ecx, 0A0h; unsigned __int64
0x18000d75a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d75f  mov     [rsp+68h+var_38], rax
0x18000d764  test    rax, rax
0x18000d767  jz      short loc_18000D77F
0x18000d769  mov     r9, rbx
0x18000d76c  mov     r8b, dil
0x18000d76f  mov     rdx, rsi
0x18000d772  mov     rcx, rax
0x18000d775  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18000d77a  mov     rdi, rax
0x18000d77d  jmp     short loc_18000D781
0x18000d77f  xor     edi, edi
0x18000d781  test    rdi, rdi
0x18000d784  jnz     short loc_18000D7AB
0x18000d786  mov     rcx, [rsp+68h]; this
0x18000d78b  mov     ebx, 8007000Eh
0x18000d790  mov     r9d, ebx; char *
0x18000d793  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d79a  mov     edx, 0CBBh; void *
0x18000d79f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7a4  mov     eax, ebx
0x18000d7a6  jmp     loc_18000D896
0x18000d7ab  lea     rsi, [rdi+80h]
0x18000d7b2  mov     rcx, rsi
0x18000d7b5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000d7ba  mov     ebx, eax
0x18000d7bc  test    eax, eax
0x18000d7be  jns     short loc_18000D7DE
0x18000d7c0  mov     rcx, [rsp+68h]; this
0x18000d7c5  mov     r9d, eax; char *
0x18000d7c8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d7cf  mov     edx, 0CBCh; void *
0x18000d7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7d9  jmp     loc_18000D862
0x18000d7de  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x18000d7e5  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x18000d7ed  mov     r9, [rsi]; hEvent
0x18000d7f0  mov     r8d, 10000005h; dwNotifyFilter
0x18000d7f6  mov     rcx, [rdi+78h]; hKey
0x18000d7fa  call    cs:__imp_RegNotifyChangeKeyValue
0x18000d800  test    eax, eax
0x18000d802  jz      short loc_18000D81F
0x18000d804  mov     rcx, [rsp+68h]; this
0x18000d809  mov     r9d, eax; char *
0x18000d80c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d813  mov     edx, 0CC2h; void *
0x18000d818  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000d81d  jmp     short loc_18000D860
0x18000d81f  xor     r8d, r8d; pcbe
0x18000d822  mov     rdx, rdi; pv
0x18000d825  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000d82c  call    cs:__imp_CreateThreadpoolWait
0x18000d832  lea     rbx, [rdi+88h]
0x18000d839  mov     rdx, rax
0x18000d83c  mov     rcx, rbx
0x18000d83f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18000d844  cmp     qword ptr [rbx], 0
0x18000d848  jnz     short loc_18000D86F
0x18000d84a  mov     rcx, [rsp+68h]; this
0x18000d84f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d856  mov     edx, 0CC5h; void *
0x18000d85b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d860  mov     ebx, eax
0x18000d862  mov     rcx, rdi; this
0x18000d865  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18000d86a  jmp     loc_18000D7A4
0x18000d86f  mov     rdx, rdi
0x18000d872  mov     rcx, r14
0x18000d875  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18000d87a  mov     rcx, [r14]
0x18000d87d  xor     r8d, r8d; pftTimeout
0x18000d880  mov     rdx, [rcx+80h]; h
0x18000d887  mov     rcx, [rcx+88h]; pwa
0x18000d88e  call    cs:__imp_SetThreadpoolWait
0x18000d894  xor     eax, eax
0x18000d896  add     rsp, 48h
0x18000d89a  pop     r14
0x18000d89c  pop     rdi
0x18000d89d  pop     rsi
0x18000d89e  pop     rbx
0x18000d89f  retn
```
