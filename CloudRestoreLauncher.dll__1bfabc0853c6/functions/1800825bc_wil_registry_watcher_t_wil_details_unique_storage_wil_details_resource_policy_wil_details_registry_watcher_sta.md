# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800825bc`
- end: `0x180082741`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180081bf8`

## callees

- `0x18000cc64`
- `0x18001003c`
- `0x18001031c`
- `0x180011e84`
- `0x180011ea4`
- `0x180021a0c`
- `0x18006dc7c`
- `0x18006e4bc`
- `0x180080dbc`
- `0x180082560`
- `0x1800825bc`
- `0x180082770`

## import_xrefs

- `KERNEL32!CreateThreadpoolWait` at `0x1800826af`
- `KERNEL32!CreateThreadpoolWait` at `0x1800826af`
- `KERNEL32!SetThreadpoolWait` at `0x18008272f`
- `KERNEL32!SetThreadpoolWait` at `0x18008272f`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18008267d`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18008267d`

## string_xrefs

- `0x180082611`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18008264b`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18008268f`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800826f1`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
  __int64 v8; // r8
  __int64 v9; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v12; // edi
  unsigned int v13; // edx
  unsigned int v14; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v17; // r9
  struct _TP_WAIT *v18; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v21[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v21[0] = v7;
  if ( v7 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state(v7, a2, v8, a4);
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
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v9 + 128, 0, 0);
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
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v9, v13);
    return v12;
  }
  v14 = RegNotifyChangeKeyValue(
          *(HKEY *)(v9 + 120),
          *(unsigned __int8 *)(v9 + 144),
          0x10000005u,
          *(HANDLE *)(v9 + 128),
          1);
  if ( v14 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v14,
                  fAsynchronousa);
LABEL_14:
    v12 = LastError;
    goto LABEL_15;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v9,
                     0);
  v18 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v18 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v21);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v18);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v21);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v17);
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
0x1800825bc  push    rbx
0x1800825be  push    rsi
0x1800825bf  push    rdi
0x1800825c0  push    r14
0x1800825c2  sub     rsp, 48h
0x1800825c6  mov     rbx, r9
0x1800825c9  mov     rdi, rdx
0x1800825cc  mov     r14, rcx
0x1800825cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800825d6  mov     ecx, 0A0h; unsigned __int64
0x1800825db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800825e0  mov     [rsp+68h+var_38], rax
0x1800825e5  test    rax, rax
0x1800825e8  jz      short loc_1800825FD
0x1800825ea  mov     r9, rbx
0x1800825ed  mov     rdx, rdi
0x1800825f0  mov     rcx, rax
0x1800825f3  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800825f8  mov     rbx, rax
0x1800825fb  jmp     short loc_1800825FF
0x1800825fd  xor     ebx, ebx
0x1800825ff  test    rbx, rbx
0x180082602  jnz     short loc_180082629
0x180082604  mov     rcx, [rsp+68h]; this
0x180082609  mov     ebx, 8007000Eh
0x18008260e  mov     r9d, ebx; char *
0x180082611  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180082618  mov     edx, 0CBBh; void *
0x18008261d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082622  mov     eax, ebx
0x180082624  jmp     loc_180082737
0x180082629  lea     rsi, [rbx+80h]
0x180082630  xor     r8d, r8d
0x180082633  xor     edx, edx
0x180082635  mov     rcx, rsi
0x180082638  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18008263d  mov     edi, eax
0x18008263f  test    eax, eax
0x180082641  jns     short loc_180082661
0x180082643  mov     rcx, [rsp+68h]; this
0x180082648  mov     r9d, eax; char *
0x18008264b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180082652  mov     edx, 0CBCh; void *
0x180082657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008265c  jmp     loc_180082704
0x180082661  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180082668  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180082670  mov     r9, [rsi]; hEvent
0x180082673  mov     r8d, 10000005h; dwNotifyFilter
0x180082679  mov     rcx, [rbx+78h]; hKey
0x18008267d  call    cs:__imp_RegNotifyChangeKeyValue
0x180082683  test    eax, eax
0x180082685  jz      short loc_1800826A2
0x180082687  mov     rcx, [rsp+68h]; this
0x18008268c  mov     r9d, eax; char *
0x18008268f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180082696  mov     edx, 0CC2h; void *
0x18008269b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800826a0  jmp     short loc_180082702
0x1800826a2  xor     r8d, r8d; pcbe
0x1800826a5  mov     rdx, rbx; pv
0x1800826a8  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800826af  call    cs:__imp_CreateThreadpoolWait
0x1800826b5  mov     rdi, rax
0x1800826b8  mov     rsi, [rbx+88h]
0x1800826bf  test    rsi, rsi
0x1800826c2  jz      short loc_1800826E0
0x1800826c4  lea     rcx, [rsp+68h+var_38]; this
0x1800826c9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800826ce  mov     rcx, rsi; pwa
0x1800826d1  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800826d6  lea     rcx, [rsp+68h+var_38]; this
0x1800826db  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800826e0  mov     [rbx+88h], rdi
0x1800826e7  test    rdi, rdi
0x1800826ea  jnz     short loc_180082710
0x1800826ec  mov     rcx, [rsp+68h]; this
0x1800826f1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800826f8  mov     edx, 0CC5h; void *
0x1800826fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180082702  mov     edi, eax
0x180082704  mov     rcx, rbx; this
0x180082707  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18008270c  mov     eax, edi
0x18008270e  jmp     short loc_180082737
0x180082710  mov     rdx, rbx
0x180082713  mov     rcx, r14
0x180082716  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18008271b  mov     rcx, [r14]
0x18008271e  xor     r8d, r8d; pftTimeout
0x180082721  mov     rdx, [rcx+80h]; h
0x180082728  mov     rcx, [rcx+88h]; pwa
0x18008272f  call    cs:__imp_SetThreadpoolWait
0x180082735  xor     eax, eax
0x180082737  add     rsp, 48h
0x18008273b  pop     r14
0x18008273d  pop     rdi
0x18008273e  pop     rsi
0x18008273f  pop     rbx
0x180082740  retn
```
