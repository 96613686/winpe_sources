# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800511b0`
- end: `0x180051362`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800510fc`

## callees

- `0x180004e10`
- `0x18000797c`
- `0x180008000`
- `0x180008f18`
- `0x18000b10c`
- `0x18000b12c`
- `0x18000d070`
- `0x18000ef44`
- `0x18004cf44`
- `0x18004d8d8`
- `0x18004d9fc`
- `0x1800511b0`
- `0x180051954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005122a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18005122a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005123f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005123f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180051350`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180051350`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800512d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800512d0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005129e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005129e`

## string_xrefs

- `0x180051205`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180051265`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800512b0`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180051312`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  void *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  wil::details *v11; // rcx
  HANDLE Event; // rsi
  HANDLE *v13; // rdi
  int LastErrorFailHr; // eax
  unsigned int v15; // edi
  unsigned int v16; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v19; // r9
  struct _TP_WAIT *v20; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v23[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v23[0] = v7;
  if ( v7 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state((__int64)v7, a2, v8, a4);
  else
    v9 = 0;
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    v13 = (HANDLE *)(v9 + 128);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v9 + 128,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v11);
    v15 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_18:
      wil::details::registry_watcher_state::`scalar deleting destructor'((struct _TP_WAIT **)v9);
      return v15;
    }
    v13 = (HANDLE *)(v9 + 128);
  }
  v16 = RegNotifyChangeKeyValue(*(HKEY *)(v9 + 120), *(unsigned __int8 *)(v9 + 144), 0x10000005u, *v13, 1);
  if ( v16 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  (const char *)v16,
                  fAsynchronousa);
LABEL_17:
    v15 = LastError;
    goto LABEL_18;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     (PTP_WAIT_CALLBACK)wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v9,
                     0);
  v20 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v20 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v23);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v20);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v23);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  v19);
    goto LABEL_17;
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
0x1800511b0  push    rbx
0x1800511b2  push    rsi
0x1800511b3  push    rdi
0x1800511b4  push    r14
0x1800511b6  sub     rsp, 48h
0x1800511ba  mov     rbx, r9
0x1800511bd  mov     rdi, rdx
0x1800511c0  mov     r14, rcx
0x1800511c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800511ca  mov     ecx, 0A0h; unsigned __int64
0x1800511cf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800511d4  mov     [rsp+68h+var_38], rax
0x1800511d9  test    rax, rax
0x1800511dc  jz      short loc_1800511F1
0x1800511de  mov     r9, rbx
0x1800511e1  mov     rdx, rdi
0x1800511e4  mov     rcx, rax
0x1800511e7  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800511ec  mov     rbx, rax
0x1800511ef  jmp     short loc_1800511F3
0x1800511f1  xor     ebx, ebx
0x1800511f3  test    rbx, rbx
0x1800511f6  jnz     short loc_18005121D
0x1800511f8  mov     rcx, [rsp+68h]; this
0x1800511fd  mov     ebx, 8007000Eh
0x180051202  mov     r9d, ebx; char *
0x180051205  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005120c  mov     edx, 0CBBh; void *
0x180051211  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051216  mov     eax, ebx
0x180051218  jmp     loc_180051358
0x18005121d  mov     r9d, 1F0003h; dwDesiredAccess
0x180051223  xor     r8d, r8d; dwFlags
0x180051226  xor     edx, edx; lpName
0x180051228  xor     ecx, ecx; lpEventAttributes
0x18005122a  call    cs:__imp_CreateEventExW
0x180051230  mov     rsi, rax
0x180051233  test    rax, rax
0x180051236  jz      short loc_180051252
0x180051238  lea     rdi, [rbx+80h]
0x18005123f  call    cs:__imp_GetLastError
0x180051245  mov     rdx, rsi
0x180051248  mov     rcx, rdi
0x18005124b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180051250  jmp     short loc_180051282
0x180051252  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180051257  mov     edi, eax
0x180051259  test    eax, eax
0x18005125b  jns     short loc_18005127B
0x18005125d  mov     rcx, [rsp+68h]; this
0x180051262  mov     r9d, eax; char *
0x180051265  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005126c  mov     edx, 0CBCh; void *
0x180051271  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051276  jmp     loc_180051325
0x18005127b  lea     rdi, [rbx+80h]
0x180051282  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180051289  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180051291  mov     r9, [rdi]; hEvent
0x180051294  mov     r8d, 10000005h; dwNotifyFilter
0x18005129a  mov     rcx, [rbx+78h]; hKey
0x18005129e  call    cs:__imp_RegNotifyChangeKeyValue
0x1800512a4  test    eax, eax
0x1800512a6  jz      short loc_1800512C3
0x1800512a8  mov     rcx, [rsp+68h]; this
0x1800512ad  mov     r9d, eax; char *
0x1800512b0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800512b7  mov     edx, 0CC2h; void *
0x1800512bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800512c1  jmp     short loc_180051323
0x1800512c3  xor     r8d, r8d; pcbe
0x1800512c6  mov     rdx, rbx; pv
0x1800512c9  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800512d0  call    cs:__imp_CreateThreadpoolWait
0x1800512d6  mov     rdi, rax
0x1800512d9  mov     rsi, [rbx+88h]
0x1800512e0  test    rsi, rsi
0x1800512e3  jz      short loc_180051301
0x1800512e5  lea     rcx, [rsp+68h+var_38]; this
0x1800512ea  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800512ef  mov     rcx, rsi; pwa
0x1800512f2  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800512f7  lea     rcx, [rsp+68h+var_38]; this
0x1800512fc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180051301  mov     [rbx+88h], rdi
0x180051308  test    rdi, rdi
0x18005130b  jnz     short loc_180051331
0x18005130d  mov     rcx, [rsp+68h]; this
0x180051312  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180051319  mov     edx, 0CC5h; void *
0x18005131e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051323  mov     edi, eax
0x180051325  mov     rcx, rbx; this
0x180051328  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18005132d  mov     eax, edi
0x18005132f  jmp     short loc_180051358
0x180051331  mov     rdx, rbx
0x180051334  mov     rcx, r14
0x180051337  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18005133c  mov     rcx, [r14]
0x18005133f  xor     r8d, r8d; pftTimeout
0x180051342  mov     rdx, [rcx+80h]; h
0x180051349  mov     rcx, [rcx+88h]; pwa
0x180051350  call    cs:__imp_SetThreadpoolWait
0x180051356  xor     eax, eax
0x180051358  add     rsp, 48h
0x18005135c  pop     r14
0x18005135e  pop     rdi
0x18005135f  pop     rsi
0x180051360  pop     rbx
0x180051361  retn
```
