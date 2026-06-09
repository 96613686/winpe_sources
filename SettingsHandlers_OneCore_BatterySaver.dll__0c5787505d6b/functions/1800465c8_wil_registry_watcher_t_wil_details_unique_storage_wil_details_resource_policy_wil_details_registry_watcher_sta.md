# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800465c8`
- end: `0x180046742`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(__int64, _QWORD *, char, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046240`

## callees

- `0x18000a000`
- `0x18000b198`
- `0x18000b85c`
- `0x18000eaac`
- `0x18000eacc`
- `0x18002b70c`
- `0x180045e28`
- `0x1800460ac`
- `0x1800460d8`
- `0x180046454`
- `0x1800465c8`
- `0x18004679c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800466b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800466b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180046730`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180046730`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004668a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004668a`

## string_xrefs

- `0x180046623`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180046658`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800466f2`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        __int64 a1,
        _QWORD *a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v12; // edi
  unsigned int v13; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v18; // r9
  struct _TP_WAIT *v19; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v22[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  v22[0] = v8;
  if ( v8 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state((__int64)v8, a2, a3, a4);
  else
    v9 = 0;
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v9 + 128);
  v12 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_15:
    wil::details::registry_watcher_state::`scalar deleting destructor'((struct _TP_WAIT **)v9);
    return v12;
  }
  v13 = RegNotifyChangeKeyValue(
          *(HKEY *)(v9 + 120),
          *(unsigned __int8 *)(v9 + 144),
          0x10000005u,
          *(HANDLE *)(v9 + 128),
          1);
  if ( v13 )
  {
    LastError = wil::details::in1diag3::Return_Win32(retaddr, v14, v15, (const char *)v13, fAsynchronousa);
LABEL_14:
    v12 = LastError;
    goto LABEL_15;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     (PTP_WAIT_CALLBACK)wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v9,
                     0);
  v19 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v19 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v22);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v19);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v18);
    goto LABEL_14;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v9);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 136LL), *(HANDLE *)(*(_QWORD *)a1 + 128LL), 0);
  return 0;
}

```

## disassembly

```asm
0x1800465c8  push    rbx
0x1800465ca  push    rsi
0x1800465cb  push    rdi
0x1800465cc  push    r14
0x1800465ce  sub     rsp, 48h
0x1800465d2  mov     rbx, r9
0x1800465d5  mov     dil, r8b
0x1800465d8  mov     rsi, rdx
0x1800465db  mov     r14, rcx
0x1800465de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800465e5  mov     ecx, 0A0h; unsigned __int64
0x1800465ea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800465ef  mov     [rsp+68h+var_38], rax
0x1800465f4  test    rax, rax
0x1800465f7  jz      short loc_18004660F
0x1800465f9  mov     r9, rbx
0x1800465fc  mov     r8b, dil
0x1800465ff  mov     rdx, rsi
0x180046602  mov     rcx, rax
0x180046605  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18004660a  mov     rbx, rax
0x18004660d  jmp     short loc_180046611
0x18004660f  xor     ebx, ebx
0x180046611  test    rbx, rbx
0x180046614  jnz     short loc_18004663B
0x180046616  mov     rcx, [rsp+68h]; this
0x18004661b  mov     ebx, 8007000Eh
0x180046620  mov     r9d, ebx; char *
0x180046623  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004662a  mov     edx, 0CBBh; void *
0x18004662f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046634  mov     eax, ebx
0x180046636  jmp     loc_180046738
0x18004663b  lea     rsi, [rbx+80h]
0x180046642  mov     rcx, rsi
0x180046645  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18004664a  mov     edi, eax
0x18004664c  test    eax, eax
0x18004664e  jns     short loc_18004666E
0x180046650  mov     rcx, [rsp+68h]; this
0x180046655  mov     r9d, eax; char *
0x180046658  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004665f  mov     edx, 0CBCh; void *
0x180046664  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046669  jmp     loc_180046705
0x18004666e  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180046675  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x18004667d  mov     r9, [rsi]; hEvent
0x180046680  mov     r8d, 10000005h; dwNotifyFilter
0x180046686  mov     rcx, [rbx+78h]; hKey
0x18004668a  call    cs:__imp_RegNotifyChangeKeyValue
0x180046690  test    eax, eax
0x180046692  jz      short loc_1800466A3
0x180046694  mov     rcx, [rsp+68h]; this
0x180046699  mov     r9d, eax; char *
0x18004669c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800466a1  jmp     short loc_180046703
0x1800466a3  xor     r8d, r8d; pcbe
0x1800466a6  mov     rdx, rbx; pv
0x1800466a9  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800466b0  call    cs:__imp_CreateThreadpoolWait
0x1800466b6  mov     rdi, rax
0x1800466b9  mov     rsi, [rbx+88h]
0x1800466c0  test    rsi, rsi
0x1800466c3  jz      short loc_1800466E1
0x1800466c5  lea     rcx, [rsp+68h+var_38]; this
0x1800466ca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800466cf  mov     rcx, rsi; pwa
0x1800466d2  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800466d7  lea     rcx, [rsp+68h+var_38]; this
0x1800466dc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800466e1  mov     [rbx+88h], rdi
0x1800466e8  test    rdi, rdi
0x1800466eb  jnz     short loc_180046711
0x1800466ed  mov     rcx, [rsp+68h]; this
0x1800466f2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800466f9  mov     edx, 0CC5h; void *
0x1800466fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180046703  mov     edi, eax
0x180046705  mov     rcx, rbx; this
0x180046708  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18004670d  mov     eax, edi
0x18004670f  jmp     short loc_180046738
0x180046711  mov     rdx, rbx
0x180046714  mov     rcx, r14
0x180046717  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18004671c  mov     rcx, [r14]
0x18004671f  xor     r8d, r8d; pftTimeout
0x180046722  mov     rdx, [rcx+80h]; h
0x180046729  mov     rcx, [rcx+88h]; pwa
0x180046730  call    cs:__imp_SetThreadpoolWait
0x180046736  xor     eax, eax
0x180046738  add     rsp, 48h
0x18004673c  pop     r14
0x18004673e  pop     rdi
0x18004673f  pop     rsi
0x180046740  pop     rbx
0x180046741  retn
```
