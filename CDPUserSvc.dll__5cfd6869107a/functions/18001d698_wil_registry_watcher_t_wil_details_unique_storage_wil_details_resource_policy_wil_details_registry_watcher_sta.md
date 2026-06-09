# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18001d698`
- end: `0x18001d7fd`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029fa4`

## callees

- `0x18000c810`
- `0x18000dae4`
- `0x18001d698`
- `0x18001d804`
- `0x18001d9b0`
- `0x18001e798`
- `0x18001f7cc`
- `0x180025f28`
- `0x18002c5e4`
- `0x180053cdc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001d7eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001d7eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001d789`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001d789`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001d757`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001d757`

## string_xrefs

- `0x18001d6f0`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18001d725`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18001d769`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18001d7ac`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void *v7; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v12; // edx
  unsigned int v13; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v16; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  if ( v7 )
    v8 = wil::details::registry_watcher_state::registry_watcher_state(v7, a2, 0, a4);
  else
    v8 = 0;
  if ( !v8 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v9;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v8 + 128);
  v9 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_14:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v8, v12);
    return v9;
  }
  v13 = RegNotifyChangeKeyValue(
          *(HKEY *)(v8 + 120),
          *(unsigned __int8 *)(v8 + 144),
          0x10000005u,
          *(HANDLE *)(v8 + 128),
          1);
  if ( v13 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v13,
                  fAsynchronousa);
LABEL_13:
    v9 = LastError;
    goto LABEL_14;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v8,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v8 + 136,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v8 + 136) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v16);
    goto LABEL_13;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v8);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 136LL), *(HANDLE *)(*(_QWORD *)a1 + 128LL), 0);
  return 0;
}

```

## disassembly

```asm
0x18001d698  push    rbx
0x18001d69a  push    rsi
0x18001d69b  push    rdi
0x18001d69c  push    r14
0x18001d69e  sub     rsp, 48h
0x18001d6a2  mov     rbx, r9
0x18001d6a5  mov     rdi, rdx
0x18001d6a8  mov     r14, rcx
0x18001d6ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d6b2  mov     ecx, 0A0h; unsigned __int64
0x18001d6b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d6bc  mov     [rsp+68h+var_38], rax
0x18001d6c1  test    rax, rax
0x18001d6c4  jz      short loc_18001D6DC
0x18001d6c6  mov     r9, rbx
0x18001d6c9  xor     r8d, r8d
0x18001d6cc  mov     rdx, rdi
0x18001d6cf  mov     rcx, rax
0x18001d6d2  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18001d6d7  mov     rdi, rax
0x18001d6da  jmp     short loc_18001D6DE
0x18001d6dc  xor     edi, edi
0x18001d6de  test    rdi, rdi
0x18001d6e1  jnz     short loc_18001D708
0x18001d6e3  mov     rcx, [rsp+68h]; this
0x18001d6e8  mov     ebx, 8007000Eh
0x18001d6ed  mov     r9d, ebx; char *
0x18001d6f0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d6f7  mov     edx, 0CBBh; void *
0x18001d6fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d701  mov     eax, ebx
0x18001d703  jmp     loc_18001D7F3
0x18001d708  lea     rsi, [rdi+80h]
0x18001d70f  mov     rcx, rsi
0x18001d712  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001d717  mov     ebx, eax
0x18001d719  test    eax, eax
0x18001d71b  jns     short loc_18001D73B
0x18001d71d  mov     rcx, [rsp+68h]; this
0x18001d722  mov     r9d, eax; char *
0x18001d725  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d72c  mov     edx, 0CBCh; void *
0x18001d731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d736  jmp     loc_18001D7BF
0x18001d73b  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x18001d742  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x18001d74a  mov     r9, [rsi]; hEvent
0x18001d74d  mov     r8d, 10000005h; dwNotifyFilter
0x18001d753  mov     rcx, [rdi+78h]; hKey
0x18001d757  call    cs:__imp_RegNotifyChangeKeyValue
0x18001d75d  test    eax, eax
0x18001d75f  jz      short loc_18001D77C
0x18001d761  mov     rcx, [rsp+68h]; this
0x18001d766  mov     r9d, eax; char *
0x18001d769  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d770  mov     edx, 0CC2h; void *
0x18001d775  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d77a  jmp     short loc_18001D7BD
0x18001d77c  xor     r8d, r8d; pcbe
0x18001d77f  mov     rdx, rdi; pv
0x18001d782  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001d789  call    cs:__imp_CreateThreadpoolWait
0x18001d78f  lea     rbx, [rdi+88h]
0x18001d796  mov     rdx, rax
0x18001d799  mov     rcx, rbx
0x18001d79c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18001d7a1  cmp     qword ptr [rbx], 0
0x18001d7a5  jnz     short loc_18001D7CC
0x18001d7a7  mov     rcx, [rsp+68h]; this
0x18001d7ac  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d7b3  mov     edx, 0CC5h; void *
0x18001d7b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d7bd  mov     ebx, eax
0x18001d7bf  mov     rcx, rdi; this
0x18001d7c2  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18001d7c7  jmp     loc_18001D701
0x18001d7cc  mov     rdx, rdi
0x18001d7cf  mov     rcx, r14
0x18001d7d2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18001d7d7  mov     rcx, [r14]
0x18001d7da  xor     r8d, r8d; pftTimeout
0x18001d7dd  mov     rdx, [rcx+80h]; h
0x18001d7e4  mov     rcx, [rcx+88h]; pwa
0x18001d7eb  call    cs:__imp_SetThreadpoolWait
0x18001d7f1  xor     eax, eax
0x18001d7f3  add     rsp, 48h
0x18001d7f7  pop     r14
0x18001d7f9  pop     rdi
0x18001d7fa  pop     rsi
0x18001d7fb  pop     rbx
0x18001d7fc  retn
```
