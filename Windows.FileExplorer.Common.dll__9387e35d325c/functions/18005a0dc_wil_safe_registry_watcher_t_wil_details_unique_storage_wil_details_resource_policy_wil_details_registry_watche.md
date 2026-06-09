# wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18005a0dc`
- end: `0x18005a242`
- name: `?create_common@?$safe_registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059ff4`

## callees

- `0x18000329c`
- `0x180003788`
- `0x180003ba8`
- `0x180003bd0`
- `0x1800077c8`
- `0x180020cac`
- `0x18002edcc`
- `0x18003169c`
- `0x180037ca0`
- `0x18005a0dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a1ce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a1ce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a230`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a230`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005a19c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005a19c`

## string_xrefs

- `0x18005a137`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`
- `0x18005a16a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`
- `0x18005a1ae`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`
- `0x18005a1f1`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`

## pseudocode

```c
__int64 __fastcall wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
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
      (void *)0x7F,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
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
      (void *)0x80,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
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
                  (void *)0x86,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
                  (const char *)v15,
                  fAsynchronousa);
LABEL_13:
    v11 = LastError;
    goto LABEL_14;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v10,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v10 + 136,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v10 + 136) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x89,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
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
0x18005a0dc  push    rbx
0x18005a0de  push    rsi
0x18005a0df  push    rdi
0x18005a0e0  push    r14
0x18005a0e2  sub     rsp, 48h
0x18005a0e6  mov     rbx, r9
0x18005a0e9  mov     dil, r8b
0x18005a0ec  mov     rsi, rdx
0x18005a0ef  mov     r14, rcx
0x18005a0f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005a0f9  mov     ecx, 0A0h; unsigned __int64
0x18005a0fe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005a103  mov     [rsp+68h+var_38], rax
0x18005a108  test    rax, rax
0x18005a10b  jz      short loc_18005A123
0x18005a10d  mov     r9, rbx
0x18005a110  mov     r8b, dil
0x18005a113  mov     rdx, rsi
0x18005a116  mov     rcx, rax
0x18005a119  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18005a11e  mov     rdi, rax
0x18005a121  jmp     short loc_18005A125
0x18005a123  xor     edi, edi
0x18005a125  test    rdi, rdi
0x18005a128  jnz     short loc_18005A14D
0x18005a12a  mov     rcx, [rsp+68h]; this
0x18005a12f  mov     ebx, 8007000Eh
0x18005a134  mov     r9d, ebx; char *
0x18005a137  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18005a13e  lea     edx, [rdi+7Fh]; void *
0x18005a141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a146  mov     eax, ebx
0x18005a148  jmp     loc_18005A238
0x18005a14d  lea     rsi, [rdi+80h]
0x18005a154  mov     rcx, rsi
0x18005a157  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005a15c  mov     ebx, eax
0x18005a15e  test    eax, eax
0x18005a160  jns     short loc_18005A180
0x18005a162  mov     rcx, [rsp+68h]; this
0x18005a167  mov     r9d, eax; char *
0x18005a16a  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18005a171  mov     edx, 80h; void *
0x18005a176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a17b  jmp     loc_18005A204
0x18005a180  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x18005a187  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x18005a18f  mov     r9, [rsi]; hEvent
0x18005a192  mov     r8d, 10000005h; dwNotifyFilter
0x18005a198  mov     rcx, [rdi+78h]; hKey
0x18005a19c  call    cs:__imp_RegNotifyChangeKeyValue
0x18005a1a2  test    eax, eax
0x18005a1a4  jz      short loc_18005A1C1
0x18005a1a6  mov     rcx, [rsp+68h]; this
0x18005a1ab  mov     r9d, eax; char *
0x18005a1ae  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18005a1b5  mov     edx, 86h; void *
0x18005a1ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005a1bf  jmp     short loc_18005A202
0x18005a1c1  xor     r8d, r8d; pcbe
0x18005a1c4  mov     rdx, rdi; pv
0x18005a1c7  lea     rcx, ?callback@?$safe_registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005a1ce  call    cs:__imp_CreateThreadpoolWait
0x18005a1d4  lea     rbx, [rdi+88h]
0x18005a1db  mov     rdx, rax
0x18005a1de  mov     rcx, rbx
0x18005a1e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18005a1e6  cmp     qword ptr [rbx], 0
0x18005a1ea  jnz     short loc_18005A211
0x18005a1ec  mov     rcx, [rsp+68h]; this
0x18005a1f1  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18005a1f8  mov     edx, 89h; void *
0x18005a1fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005a202  mov     ebx, eax
0x18005a204  mov     rcx, rdi; this
0x18005a207  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18005a20c  jmp     loc_18005A146
0x18005a211  mov     rdx, rdi
0x18005a214  mov     rcx, r14
0x18005a217  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18005a21c  mov     rcx, [r14]
0x18005a21f  xor     r8d, r8d; pftTimeout
0x18005a222  mov     rdx, [rcx+80h]; h
0x18005a229  mov     rcx, [rcx+88h]; pwa
0x18005a230  call    cs:__imp_SetThreadpoolWait
0x18005a236  xor     eax, eax
0x18005a238  add     rsp, 48h
0x18005a23c  pop     r14
0x18005a23e  pop     rdi
0x18005a23f  pop     rsi
0x18005a240  pop     rbx
0x18005a241  retn
```
