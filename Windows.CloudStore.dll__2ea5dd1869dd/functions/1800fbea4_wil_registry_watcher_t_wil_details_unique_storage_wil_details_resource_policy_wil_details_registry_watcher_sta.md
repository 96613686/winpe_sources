# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800fbea4`
- end: `0x1800fc009`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f12fc`

## callees

- `0x18003f768`
- `0x180042558`
- `0x1800425ac`
- `0x180042654`
- `0x1800426a8`
- `0x1800c8458`
- `0x1800fbea4`
- `0x1800fc644`
- `0x1800ff298`
- `0x1801236bc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolWait` at `0x1800fbff7`
- `api-ms-win-core-threadpool-l1-1-0!SetThreadpoolWait` at `0x1800fbff7`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolWait` at `0x1800fbf95`
- `api-ms-win-core-threadpool-l1-1-0!CreateThreadpoolWait` at `0x1800fbf95`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800fbf63`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800fbf63`

## string_xrefs

- `0x1800fbefc`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800fbf31`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800fbf75`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800fbfb8`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
0x1800fbea4  push    rbx
0x1800fbea6  push    rsi
0x1800fbea7  push    rdi
0x1800fbea8  push    r14
0x1800fbeaa  sub     rsp, 48h
0x1800fbeae  mov     rbx, r9
0x1800fbeb1  mov     rdi, rdx
0x1800fbeb4  mov     r14, rcx
0x1800fbeb7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800fbebe  mov     ecx, 0A0h; unsigned __int64
0x1800fbec3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800fbec8  mov     [rsp+68h+var_38], rax
0x1800fbecd  test    rax, rax
0x1800fbed0  jz      short loc_1800FBEE8
0x1800fbed2  mov     r9, rbx
0x1800fbed5  xor     r8d, r8d
0x1800fbed8  mov     rdx, rdi
0x1800fbedb  mov     rcx, rax
0x1800fbede  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800fbee3  mov     rdi, rax
0x1800fbee6  jmp     short loc_1800FBEEA
0x1800fbee8  xor     edi, edi
0x1800fbeea  test    rdi, rdi
0x1800fbeed  jnz     short loc_1800FBF14
0x1800fbeef  mov     rcx, [rsp+68h]; this
0x1800fbef4  mov     ebx, 8007000Eh
0x1800fbef9  mov     r9d, ebx; char *
0x1800fbefc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800fbf03  mov     edx, 0CBBh; void *
0x1800fbf08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fbf0d  mov     eax, ebx
0x1800fbf0f  jmp     loc_1800FBFFF
0x1800fbf14  lea     rsi, [rdi+80h]
0x1800fbf1b  mov     rcx, rsi
0x1800fbf1e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800fbf23  mov     ebx, eax
0x1800fbf25  test    eax, eax
0x1800fbf27  jns     short loc_1800FBF47
0x1800fbf29  mov     rcx, [rsp+68h]; this
0x1800fbf2e  mov     r9d, eax; char *
0x1800fbf31  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800fbf38  mov     edx, 0CBCh; void *
0x1800fbf3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fbf42  jmp     loc_1800FBFCB
0x1800fbf47  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x1800fbf4e  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x1800fbf56  mov     r9, [rsi]; hEvent
0x1800fbf59  mov     r8d, 10000005h; dwNotifyFilter
0x1800fbf5f  mov     rcx, [rdi+78h]; hKey
0x1800fbf63  call    cs:__imp_RegNotifyChangeKeyValue
0x1800fbf69  test    eax, eax
0x1800fbf6b  jz      short loc_1800FBF88
0x1800fbf6d  mov     rcx, [rsp+68h]; this
0x1800fbf72  mov     r9d, eax; char *
0x1800fbf75  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800fbf7c  mov     edx, 0CC2h; void *
0x1800fbf81  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fbf86  jmp     short loc_1800FBFC9
0x1800fbf88  xor     r8d, r8d; pcbe
0x1800fbf8b  mov     rdx, rdi; pv
0x1800fbf8e  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800fbf95  call    cs:__imp_CreateThreadpoolWait
0x1800fbf9b  lea     rbx, [rdi+88h]
0x1800fbfa2  mov     rdx, rax
0x1800fbfa5  mov     rcx, rbx
0x1800fbfa8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800fbfad  cmp     qword ptr [rbx], 0
0x1800fbfb1  jnz     short loc_1800FBFD8
0x1800fbfb3  mov     rcx, [rsp+68h]; this
0x1800fbfb8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800fbfbf  mov     edx, 0CC5h; void *
0x1800fbfc4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fbfc9  mov     ebx, eax
0x1800fbfcb  mov     rcx, rdi; this
0x1800fbfce  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800fbfd3  jmp     loc_1800FBF0D
0x1800fbfd8  mov     rdx, rdi
0x1800fbfdb  mov     rcx, r14
0x1800fbfde  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x1800fbfe3  mov     rcx, [r14]
0x1800fbfe6  xor     r8d, r8d; pftTimeout
0x1800fbfe9  mov     rdx, [rcx+80h]; h
0x1800fbff0  mov     rcx, [rcx+88h]; pwa
0x1800fbff7  call    cs:__imp_SetThreadpoolWait
0x1800fbffd  xor     eax, eax
0x1800fbfff  add     rsp, 48h
0x1800fc003  pop     r14
0x1800fc005  pop     rdi
0x1800fc006  pop     rsi
0x1800fc007  pop     rbx
0x1800fc008  retn
```
