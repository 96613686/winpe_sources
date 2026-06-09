# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x140023e70`
- end: `0x140024028`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140023d98`

## callees

- `0x140002d60`
- `0x140007b48`
- `0x140008248`
- `0x14000bb58`
- `0x14000e010`
- `0x14000e030`
- `0x140011278`
- `0x140021408`
- `0x14002207c`
- `0x14002222c`
- `0x140022fa8`
- `0x140023e70`
- `0x140024258`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140023ef0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140023ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023f05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140024016`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140024016`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140023f96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140023f96`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x140023f64`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x140023f64`

## string_xrefs

- `0x140023ecb`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x140023f2b`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x140023f76`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x140023fd8`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
  __int64 v10; // rbx
  wil::details *v12; // rcx
  HANDLE Event; // rsi
  HANDLE *v14; // rdi
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  unsigned int v17; // edx
  unsigned int v18; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v21; // r9
  struct _TP_WAIT *v22; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v25[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v25[0] = v8;
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    v14 = (HANDLE *)(v10 + 128);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v10 + 128,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_18:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v10,
        v17);
      return v16;
    }
    v14 = (HANDLE *)(v10 + 128);
  }
  v18 = RegNotifyChangeKeyValue(*(HKEY *)(v10 + 120), *(unsigned __int8 *)(v10 + 144), 0x10000005u, *v14, 1);
  if ( v18 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v18,
                  fAsynchronousa);
LABEL_17:
    v16 = LastError;
    goto LABEL_18;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v10,
                     0);
  v22 = *(struct _TP_WAIT **)(v10 + 136);
  if ( v22 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v25);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v22);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v25);
  }
  *(_QWORD *)(v10 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v21);
    goto LABEL_17;
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
0x140023e70  push    rbx
0x140023e72  push    rsi
0x140023e73  push    rdi
0x140023e74  push    r14
0x140023e76  sub     rsp, 48h
0x140023e7a  mov     rbx, r9
0x140023e7d  mov     dil, r8b
0x140023e80  mov     rsi, rdx
0x140023e83  mov     r14, rcx
0x140023e86  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140023e8d  mov     ecx, 0A0h; unsigned __int64
0x140023e92  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140023e97  mov     [rsp+68h+var_38], rax
0x140023e9c  test    rax, rax
0x140023e9f  jz      short loc_140023EB7
0x140023ea1  mov     r9, rbx
0x140023ea4  mov     r8b, dil
0x140023ea7  mov     rdx, rsi
0x140023eaa  mov     rcx, rax
0x140023ead  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x140023eb2  mov     rbx, rax
0x140023eb5  jmp     short loc_140023EB9
0x140023eb7  xor     ebx, ebx
0x140023eb9  test    rbx, rbx
0x140023ebc  jnz     short loc_140023EE3
0x140023ebe  mov     rcx, [rsp+68h]; this
0x140023ec3  mov     ebx, 8007000Eh
0x140023ec8  mov     r9d, ebx; char *
0x140023ecb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140023ed2  mov     edx, 0CBBh; void *
0x140023ed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023edc  mov     eax, ebx
0x140023ede  jmp     loc_14002401E
0x140023ee3  mov     r9d, 1F0003h; dwDesiredAccess
0x140023ee9  xor     r8d, r8d; dwFlags
0x140023eec  xor     edx, edx; lpName
0x140023eee  xor     ecx, ecx; lpEventAttributes
0x140023ef0  call    cs:__imp_CreateEventExW
0x140023ef6  mov     rsi, rax
0x140023ef9  test    rax, rax
0x140023efc  jz      short loc_140023F18
0x140023efe  lea     rdi, [rbx+80h]
0x140023f05  call    cs:__imp_GetLastError
0x140023f0b  mov     rdx, rsi
0x140023f0e  mov     rcx, rdi
0x140023f11  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140023f16  jmp     short loc_140023F48
0x140023f18  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140023f1d  mov     edi, eax
0x140023f1f  test    eax, eax
0x140023f21  jns     short loc_140023F41
0x140023f23  mov     rcx, [rsp+68h]; this
0x140023f28  mov     r9d, eax; char *
0x140023f2b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140023f32  mov     edx, 0CBCh; void *
0x140023f37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023f3c  jmp     loc_140023FEB
0x140023f41  lea     rdi, [rbx+80h]
0x140023f48  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x140023f4f  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x140023f57  mov     r9, [rdi]; hEvent
0x140023f5a  mov     r8d, 10000005h; dwNotifyFilter
0x140023f60  mov     rcx, [rbx+78h]; hKey
0x140023f64  call    cs:__imp_RegNotifyChangeKeyValue
0x140023f6a  test    eax, eax
0x140023f6c  jz      short loc_140023F89
0x140023f6e  mov     rcx, [rsp+68h]; this
0x140023f73  mov     r9d, eax; char *
0x140023f76  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140023f7d  mov     edx, 0CC2h; void *
0x140023f82  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140023f87  jmp     short loc_140023FE9
0x140023f89  xor     r8d, r8d; pcbe
0x140023f8c  mov     rdx, rbx; pv
0x140023f8f  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140023f96  call    cs:__imp_CreateThreadpoolWait
0x140023f9c  mov     rdi, rax
0x140023f9f  mov     rsi, [rbx+88h]
0x140023fa6  test    rsi, rsi
0x140023fa9  jz      short loc_140023FC7
0x140023fab  lea     rcx, [rsp+68h+var_38]; this
0x140023fb0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023fb5  mov     rcx, rsi; pwa
0x140023fb8  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x140023fbd  lea     rcx, [rsp+68h+var_38]; this
0x140023fc2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023fc7  mov     [rbx+88h], rdi
0x140023fce  test    rdi, rdi
0x140023fd1  jnz     short loc_140023FF7
0x140023fd3  mov     rcx, [rsp+68h]; this
0x140023fd8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140023fdf  mov     edx, 0CC5h; void *
0x140023fe4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140023fe9  mov     edi, eax
0x140023feb  mov     rcx, rbx; this
0x140023fee  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x140023ff3  mov     eax, edi
0x140023ff5  jmp     short loc_14002401E
0x140023ff7  mov     rdx, rbx
0x140023ffa  mov     rcx, r14
0x140023ffd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x140024002  mov     rcx, [r14]
0x140024005  xor     r8d, r8d; pftTimeout
0x140024008  mov     rdx, [rcx+80h]; h
0x14002400f  mov     rcx, [rcx+88h]; pwa
0x140024016  call    cs:__imp_SetThreadpoolWait
0x14002401c  xor     eax, eax
0x14002401e  add     rsp, 48h
0x140024022  pop     r14
0x140024024  pop     rdi
0x140024025  pop     rsi
0x140024026  pop     rbx
0x140024027  retn
```
