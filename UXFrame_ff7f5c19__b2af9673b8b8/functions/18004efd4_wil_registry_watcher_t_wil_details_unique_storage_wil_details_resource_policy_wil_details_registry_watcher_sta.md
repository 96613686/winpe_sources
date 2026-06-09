# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18004efd4`
- end: `0x18004f143`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f898`

## callees

- `0x180002bcc`
- `0x18000f1d8`
- `0x180015f40`
- `0x18002d484`
- `0x1800324c4`
- `0x18003e3f4`
- `0x180049dd4`
- `0x18004ef80`
- `0x18004efd4`
- `0x18004fc94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004f099`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004f099`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004f0cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004f0cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004f12d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004f12d`

## string_xrefs

- `0x18004f032`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`
- `0x18004f067`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`
- `0x18004f0ab`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`
- `0x18004f0ee`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\registry.h`

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
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v14; // edx
  unsigned int v15; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v18; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-38h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
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
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v11;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v10 + 128);
  v11 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
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
                  (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
                  (const char *)v15,
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
                  (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\registry.h",
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
0x18004efd4  mov     [rsp+arg_10], rbx
0x18004efd9  push    rsi
0x18004efda  push    rdi
0x18004efdb  push    r14
0x18004efdd  sub     rsp, 40h
0x18004efe1  mov     rsi, r9
0x18004efe4  mov     bl, r8b
0x18004efe7  mov     rdi, rdx
0x18004efea  mov     r14, rcx
0x18004efed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004eff4  mov     ecx, 0A0h; unsigned __int64
0x18004eff9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004effe  mov     [rsp+58h+var_28], rax
0x18004f003  test    rax, rax
0x18004f006  jz      short loc_18004F01E
0x18004f008  mov     r9, rsi
0x18004f00b  mov     r8b, bl
0x18004f00e  mov     rdx, rdi
0x18004f011  mov     rcx, rax
0x18004f014  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18004f019  mov     rdi, rax
0x18004f01c  jmp     short loc_18004F020
0x18004f01e  xor     edi, edi
0x18004f020  test    rdi, rdi
0x18004f023  jnz     short loc_18004F04A
0x18004f025  mov     rcx, [rsp+58h]; this
0x18004f02a  mov     ebx, 8007000Eh
0x18004f02f  mov     r9d, ebx; char *
0x18004f032  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004f039  mov     edx, 0CBBh; void *
0x18004f03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f043  mov     eax, ebx
0x18004f045  jmp     loc_18004F135
0x18004f04a  lea     rsi, [rdi+80h]
0x18004f051  mov     rcx, rsi
0x18004f054  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004f059  mov     ebx, eax
0x18004f05b  test    eax, eax
0x18004f05d  jns     short loc_18004F07D
0x18004f05f  mov     rcx, [rsp+58h]; this
0x18004f064  mov     r9d, eax; char *
0x18004f067  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004f06e  mov     edx, 0CBCh; void *
0x18004f073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f078  jmp     loc_18004F101
0x18004f07d  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x18004f084  mov     [rsp+58h+fAsynchronous], 1; unsigned int
0x18004f08c  mov     r9, [rsi]; hEvent
0x18004f08f  mov     r8d, 10000005h; dwNotifyFilter
0x18004f095  mov     rcx, [rdi+78h]; hKey
0x18004f099  call    cs:__imp_RegNotifyChangeKeyValue
0x18004f09f  test    eax, eax
0x18004f0a1  jz      short loc_18004F0BE
0x18004f0a3  mov     rcx, [rsp+58h]; this
0x18004f0a8  mov     r9d, eax; char *
0x18004f0ab  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004f0b2  mov     edx, 0CC2h; void *
0x18004f0b7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004f0bc  jmp     short loc_18004F0FF
0x18004f0be  xor     r8d, r8d; pcbe
0x18004f0c1  mov     rdx, rdi; pv
0x18004f0c4  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18004f0cb  call    cs:__imp_CreateThreadpoolWait
0x18004f0d1  lea     rbx, [rdi+88h]
0x18004f0d8  mov     rdx, rax
0x18004f0db  mov     rcx, rbx
0x18004f0de  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18004f0e3  cmp     qword ptr [rbx], 0
0x18004f0e7  jnz     short loc_18004F10E
0x18004f0e9  mov     rcx, [rsp+58h]; this
0x18004f0ee  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004f0f5  mov     edx, 0CC5h; void *
0x18004f0fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f0ff  mov     ebx, eax
0x18004f101  mov     rcx, rdi; this
0x18004f104  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18004f109  jmp     loc_18004F043
0x18004f10e  mov     rdx, rdi
0x18004f111  mov     rcx, r14
0x18004f114  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18004f119  mov     rcx, [r14]
0x18004f11c  xor     r8d, r8d; pftTimeout
0x18004f11f  mov     rdx, [rcx+80h]; h
0x18004f126  mov     rcx, [rcx+88h]; pwa
0x18004f12d  call    cs:__imp_SetThreadpoolWait
0x18004f133  xor     eax, eax
0x18004f135  mov     rbx, [rsp+58h+arg_10]
0x18004f13a  add     rsp, 40h
0x18004f13e  pop     r14
0x18004f140  pop     rdi
0x18004f141  pop     rsi
0x18004f142  retn
```
