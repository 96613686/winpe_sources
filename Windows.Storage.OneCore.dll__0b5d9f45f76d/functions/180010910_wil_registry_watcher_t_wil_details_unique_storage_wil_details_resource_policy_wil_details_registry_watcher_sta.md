# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180010910`
- end: `0x180010ac8`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010828`

## callees

- `0x180003100`
- `0x1800047c4`
- `0x180004e40`
- `0x180005db8`
- `0x180007f8c`
- `0x180007fac`
- `0x1800098a8`
- `0x18000d000`
- `0x18000dcfc`
- `0x18000df94`
- `0x18000f040`
- `0x180010910`
- `0x180011494`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010990`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180010990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180010ab6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180010ab6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180010a36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180010a36`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180010a04`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180010a04`

## string_xrefs

- `0x18001096b`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800109cb`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180010a16`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180010a78`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        __int64 a1,
        _QWORD *a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
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

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v23[0] = v8;
  if ( v8 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state((__int64)v8, a2, a3, a4);
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
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
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
0x180010910  push    rbx
0x180010912  push    rsi
0x180010913  push    rdi
0x180010914  push    r14
0x180010916  sub     rsp, 48h
0x18001091a  mov     rbx, r9
0x18001091d  mov     dil, r8b
0x180010920  mov     rsi, rdx
0x180010923  mov     r14, rcx
0x180010926  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001092d  mov     ecx, 0A0h; unsigned __int64
0x180010932  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010937  mov     [rsp+68h+var_38], rax
0x18001093c  test    rax, rax
0x18001093f  jz      short loc_180010957
0x180010941  mov     r9, rbx
0x180010944  mov     r8b, dil
0x180010947  mov     rdx, rsi
0x18001094a  mov     rcx, rax
0x18001094d  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180010952  mov     rbx, rax
0x180010955  jmp     short loc_180010959
0x180010957  xor     ebx, ebx
0x180010959  test    rbx, rbx
0x18001095c  jnz     short loc_180010983
0x18001095e  mov     rcx, [rsp+68h]; this
0x180010963  mov     ebx, 8007000Eh
0x180010968  mov     r9d, ebx; char *
0x18001096b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010972  mov     edx, 0CBBh; void *
0x180010977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001097c  mov     eax, ebx
0x18001097e  jmp     loc_180010ABE
0x180010983  mov     r9d, 1F0003h; dwDesiredAccess
0x180010989  xor     r8d, r8d; dwFlags
0x18001098c  xor     edx, edx; lpName
0x18001098e  xor     ecx, ecx; lpEventAttributes
0x180010990  call    cs:__imp_CreateEventExW
0x180010996  mov     rsi, rax
0x180010999  test    rax, rax
0x18001099c  jz      short loc_1800109B8
0x18001099e  lea     rdi, [rbx+80h]
0x1800109a5  call    cs:__imp_GetLastError
0x1800109ab  mov     rdx, rsi
0x1800109ae  mov     rcx, rdi
0x1800109b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800109b6  jmp     short loc_1800109E8
0x1800109b8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800109bd  mov     edi, eax
0x1800109bf  test    eax, eax
0x1800109c1  jns     short loc_1800109E1
0x1800109c3  mov     rcx, [rsp+68h]; this
0x1800109c8  mov     r9d, eax; char *
0x1800109cb  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800109d2  mov     edx, 0CBCh; void *
0x1800109d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109dc  jmp     loc_180010A8B
0x1800109e1  lea     rdi, [rbx+80h]
0x1800109e8  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x1800109ef  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x1800109f7  mov     r9, [rdi]; hEvent
0x1800109fa  mov     r8d, 10000005h; dwNotifyFilter
0x180010a00  mov     rcx, [rbx+78h]; hKey
0x180010a04  call    cs:__imp_RegNotifyChangeKeyValue
0x180010a0a  test    eax, eax
0x180010a0c  jz      short loc_180010A29
0x180010a0e  mov     rcx, [rsp+68h]; this
0x180010a13  mov     r9d, eax; char *
0x180010a16  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010a1d  mov     edx, 0CC2h; void *
0x180010a22  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010a27  jmp     short loc_180010A89
0x180010a29  xor     r8d, r8d; pcbe
0x180010a2c  mov     rdx, rbx; pv
0x180010a2f  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180010a36  call    cs:__imp_CreateThreadpoolWait
0x180010a3c  mov     rdi, rax
0x180010a3f  mov     rsi, [rbx+88h]
0x180010a46  test    rsi, rsi
0x180010a49  jz      short loc_180010A67
0x180010a4b  lea     rcx, [rsp+68h+var_38]; this
0x180010a50  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180010a55  mov     rcx, rsi; pwa
0x180010a58  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x180010a5d  lea     rcx, [rsp+68h+var_38]; this
0x180010a62  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180010a67  mov     [rbx+88h], rdi
0x180010a6e  test    rdi, rdi
0x180010a71  jnz     short loc_180010A97
0x180010a73  mov     rcx, [rsp+68h]; this
0x180010a78  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010a7f  mov     edx, 0CC5h; void *
0x180010a84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010a89  mov     edi, eax
0x180010a8b  mov     rcx, rbx; this
0x180010a8e  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180010a93  mov     eax, edi
0x180010a95  jmp     short loc_180010ABE
0x180010a97  mov     rdx, rbx
0x180010a9a  mov     rcx, r14
0x180010a9d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180010aa2  mov     rcx, [r14]
0x180010aa5  xor     r8d, r8d; pftTimeout
0x180010aa8  mov     rdx, [rcx+80h]; h
0x180010aaf  mov     rcx, [rcx+88h]; pwa
0x180010ab6  call    cs:__imp_SetThreadpoolWait
0x180010abc  xor     eax, eax
0x180010abe  add     rsp, 48h
0x180010ac2  pop     r14
0x180010ac4  pop     rdi
0x180010ac5  pop     rsi
0x180010ac6  pop     rbx
0x180010ac7  retn
```
