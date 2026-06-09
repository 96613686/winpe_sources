# wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18006c580`
- end: `0x18006c6e3`
- name: `?create_common@?$safe_registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006c4cc`

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
- `0x18006c580`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006c66f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006c66f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c6d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006c6d1`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006c63d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006c63d`

## string_xrefs

- `0x18006c5d8`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`
- `0x18006c60b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`
- `0x18006c64f`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`
- `0x18006c692`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SafeRegistryWatcher.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdi
  unsigned int v10; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v13; // edx
  unsigned int v14; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v17; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
  {
    LOBYTE(v8) = 1;
    v9 = wil::details::registry_watcher_state::registry_watcher_state(v7, a2, v8, a4);
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v10;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v9 + 128);
  v10 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_14:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v9, v13);
    return v10;
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
                  (void *)0x86,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
                  (const char *)v14,
                  fAsynchronousa);
LABEL_13:
    v10 = LastError;
    goto LABEL_14;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::safe_registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v9,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v9 + 136,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v9 + 136) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x89,
                  (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SafeRegistryWatcher.h",
                  v17);
    goto LABEL_13;
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
0x18006c580  push    rbx
0x18006c582  push    rsi
0x18006c583  push    rdi
0x18006c584  push    r14
0x18006c586  sub     rsp, 48h
0x18006c58a  mov     rbx, r9
0x18006c58d  mov     rdi, rdx
0x18006c590  mov     r14, rcx
0x18006c593  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006c59a  mov     ecx, 0A0h; unsigned __int64
0x18006c59f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006c5a4  mov     [rsp+68h+var_38], rax
0x18006c5a9  test    rax, rax
0x18006c5ac  jz      short loc_18006C5C4
0x18006c5ae  mov     r9, rbx
0x18006c5b1  mov     r8b, 1
0x18006c5b4  mov     rdx, rdi
0x18006c5b7  mov     rcx, rax
0x18006c5ba  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18006c5bf  mov     rdi, rax
0x18006c5c2  jmp     short loc_18006C5C6
0x18006c5c4  xor     edi, edi
0x18006c5c6  test    rdi, rdi
0x18006c5c9  jnz     short loc_18006C5EE
0x18006c5cb  mov     rcx, [rsp+68h]; this
0x18006c5d0  mov     ebx, 8007000Eh
0x18006c5d5  mov     r9d, ebx; char *
0x18006c5d8  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006c5df  lea     edx, [rdi+7Fh]; void *
0x18006c5e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c5e7  mov     eax, ebx
0x18006c5e9  jmp     loc_18006C6D9
0x18006c5ee  lea     rsi, [rdi+80h]
0x18006c5f5  mov     rcx, rsi
0x18006c5f8  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18006c5fd  mov     ebx, eax
0x18006c5ff  test    eax, eax
0x18006c601  jns     short loc_18006C621
0x18006c603  mov     rcx, [rsp+68h]; this
0x18006c608  mov     r9d, eax; char *
0x18006c60b  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006c612  mov     edx, 80h; void *
0x18006c617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c61c  jmp     loc_18006C6A5
0x18006c621  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x18006c628  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x18006c630  mov     r9, [rsi]; hEvent
0x18006c633  mov     r8d, 10000005h; dwNotifyFilter
0x18006c639  mov     rcx, [rdi+78h]; hKey
0x18006c63d  call    cs:__imp_RegNotifyChangeKeyValue
0x18006c643  test    eax, eax
0x18006c645  jz      short loc_18006C662
0x18006c647  mov     rcx, [rsp+68h]; this
0x18006c64c  mov     r9d, eax; char *
0x18006c64f  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006c656  mov     edx, 86h; void *
0x18006c65b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c660  jmp     short loc_18006C6A3
0x18006c662  xor     r8d, r8d; pcbe
0x18006c665  mov     rdx, rdi; pv
0x18006c668  lea     rcx, ?callback@?$safe_registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18006c66f  call    cs:__imp_CreateThreadpoolWait
0x18006c675  lea     rbx, [rdi+88h]
0x18006c67c  mov     rdx, rax
0x18006c67f  mov     rcx, rbx
0x18006c682  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18006c687  cmp     qword ptr [rbx], 0
0x18006c68b  jnz     short loc_18006C6B2
0x18006c68d  mov     rcx, [rsp+68h]; this
0x18006c692  lea     r8, aShellcommonShe; "shellcommon\\shell\\fileexplorer\\windo"...
0x18006c699  mov     edx, 89h; void *
0x18006c69e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006c6a3  mov     ebx, eax
0x18006c6a5  mov     rcx, rdi; this
0x18006c6a8  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18006c6ad  jmp     loc_18006C5E7
0x18006c6b2  mov     rdx, rdi
0x18006c6b5  mov     rcx, r14
0x18006c6b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18006c6bd  mov     rcx, [r14]
0x18006c6c0  xor     r8d, r8d; pftTimeout
0x18006c6c3  mov     rdx, [rcx+80h]; h
0x18006c6ca  mov     rcx, [rcx+88h]; pwa
0x18006c6d1  call    cs:__imp_SetThreadpoolWait
0x18006c6d7  xor     eax, eax
0x18006c6d9  add     rsp, 48h
0x18006c6dd  pop     r14
0x18006c6df  pop     rdi
0x18006c6e0  pop     rsi
0x18006c6e1  pop     rbx
0x18006c6e2  retn
```
