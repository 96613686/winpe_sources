# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800423dc`
- end: `0x18004254f`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040cbc`

## callees

- `0x1800423dc`
- `0x180042558`
- `0x1800425ac`
- `0x180042654`
- `0x1800426a8`
- `0x18009f3cc`
- `0x1800c8458`
- `0x1800fc644`
- `0x1800ff298`
- `0x1801236bc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolWait` at `0x1800424d4`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolWait` at `0x1800424d4`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolWait` at `0x18004247e`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolWait` at `0x18004247e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180042463`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180042463`

## string_xrefs

- `0x1800424a1`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800424f3`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180042510`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180042539`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        wil::details::registry_watcher_state **a1,
        __int64 a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rbx
  HANDLE *v11; // rsi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v13; // edi
  unsigned int v14; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v16; // r9
  int LastError; // eax
  unsigned int v18; // edx
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
  if ( v10 )
  {
    v11 = (HANDLE *)(v10 + 128);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v10 + 128);
    v13 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        fAsynchronous);
      goto LABEL_9;
    }
    v14 = RegNotifyChangeKeyValue(*(HKEY *)(v10 + 120), *(unsigned __int8 *)(v10 + 144), 0x10000005u, *v11, 1);
    if ( v14 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xCC2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                    (const char *)v14,
                    fAsynchronousa);
      goto LABEL_8;
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
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                    v16);
LABEL_8:
      v13 = LastError;
LABEL_9:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v10,
        v18);
      return v13;
    }
    if ( *a1 )
      wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*a1);
    *a1 = (wil::details::registry_watcher_state *)v10;
    SetThreadpoolWait(*(PTP_WAIT *)(v10 + 136), *v11, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800423dc  push    rbx
0x1800423de  push    rsi
0x1800423df  push    rdi
0x1800423e0  push    r14
0x1800423e2  sub     rsp, 48h
0x1800423e6  mov     rbx, r9
0x1800423e9  mov     dil, r8b
0x1800423ec  mov     rsi, rdx
0x1800423ef  mov     r14, rcx
0x1800423f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800423f9  mov     ecx, 0A0h; unsigned __int64
0x1800423fe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180042403  mov     [rsp+68h+var_38], rax
0x180042408  test    rax, rax
0x18004240b  jz      loc_180042523
0x180042411  mov     r9, rbx
0x180042414  mov     r8b, dil
0x180042417  mov     rdx, rsi
0x18004241a  mov     rcx, rax
0x18004241d  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180042422  mov     rbx, rax
0x180042425  test    rbx, rbx
0x180042428  jz      loc_1800424E6
0x18004242e  lea     rsi, [rbx+80h]
0x180042435  mov     rcx, rsi
0x180042438  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004243d  mov     edi, eax
0x18004243f  test    eax, eax
0x180042441  js      loc_180042531
0x180042447  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x18004244e  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180042456  mov     r9, [rsi]; hEvent
0x180042459  mov     r8d, 10000005h; dwNotifyFilter
0x18004245f  mov     rcx, [rbx+78h]; hKey
0x180042463  call    cs:__imp_RegNotifyChangeKeyValue
0x180042469  test    eax, eax
0x18004246b  jnz     loc_180042508
0x180042471  xor     r8d, r8d; pcbe
0x180042474  mov     rdx, rbx; pv
0x180042477  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18004247e  call    cs:__imp_CreateThreadpoolWait
0x180042484  lea     rdi, [rbx+88h]
0x18004248b  mov     rdx, rax
0x18004248e  mov     rcx, rdi
0x180042491  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180042496  cmp     qword ptr [rdi], 0
0x18004249a  jnz     short loc_1800424C0
0x18004249c  mov     rcx, [rsp+68h]; this
0x1800424a1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800424a8  mov     edx, 0CC5h; void *
0x1800424ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800424b2  mov     edi, eax
0x1800424b4  mov     rcx, rbx; this
0x1800424b7  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800424bc  mov     eax, edi
0x1800424be  jmp     short loc_1800424DC
0x1800424c0  mov     rcx, [r14]; this
0x1800424c3  test    rcx, rcx
0x1800424c6  jnz     short loc_18004252A
0x1800424c8  mov     [r14], rbx
0x1800424cb  xor     r8d, r8d; pftTimeout
0x1800424ce  mov     rdx, [rsi]; h
0x1800424d1  mov     rcx, [rdi]; pwa
0x1800424d4  call    cs:__imp_SetThreadpoolWait
0x1800424da  xor     eax, eax
0x1800424dc  add     rsp, 48h
0x1800424e0  pop     r14
0x1800424e2  pop     rdi
0x1800424e3  pop     rsi
0x1800424e4  pop     rbx
0x1800424e5  retn
0x1800424e6  mov     rcx, [rsp+68h]; this
0x1800424eb  mov     ebx, 8007000Eh
0x1800424f0  mov     r9d, ebx; char *
0x1800424f3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800424fa  mov     edx, 0CBBh; void *
0x1800424ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042504  mov     eax, ebx
0x180042506  jmp     short loc_1800424DC
0x180042508  mov     rcx, [rsp+68h]; this
0x18004250d  mov     r9d, eax; char *
0x180042510  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180042517  mov     edx, 0CC2h; void *
0x18004251c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042521  jmp     short loc_1800424B2
0x180042523  xor     ebx, ebx
0x180042525  jmp     loc_180042425
0x18004252a  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z; wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)
0x18004252f  jmp     short loc_1800424C8
0x180042531  mov     rcx, [rsp+68h]; this
0x180042536  mov     r9d, eax; char *
0x180042539  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180042540  mov     edx, 0CBCh; void *
0x180042545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004254a  jmp     loc_1800424B4
```
