# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800367f8`
- end: `0x1800369b0`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034b10`

## callees

- `0x1800042d8`
- `0x180005d28`
- `0x1800063a4`
- `0x1800079a8`
- `0x18000a11c`
- `0x18000a13c`
- `0x18000bab8`
- `0x180034d00`
- `0x180035118`
- `0x180035144`
- `0x180036338`
- `0x1800367f8`
- `0x180036adc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003688d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003688d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180036878`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180036878`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003699e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18003699e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003691e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003691e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800368ec`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800368ec`

## string_xrefs

- `0x180036853`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800368b3`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800368fe`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180036960`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
  unsigned int v16; // edx
  unsigned int v17; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v20; // r9
  struct _TP_WAIT *v21; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v24[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  v24[0] = v8;
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_18:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v9,
        v16);
      return v15;
    }
    v13 = (HANDLE *)(v9 + 128);
  }
  v17 = RegNotifyChangeKeyValue(*(HKEY *)(v9 + 120), *(unsigned __int8 *)(v9 + 144), 0x10000005u, *v13, 1);
  if ( v17 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v17,
                  fAsynchronousa);
LABEL_17:
    v15 = LastError;
    goto LABEL_18;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v9,
                     0);
  v21 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v21 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v24);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v21);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v24);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v20);
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
0x1800367f8  push    rbx
0x1800367fa  push    rsi
0x1800367fb  push    rdi
0x1800367fc  push    r14
0x1800367fe  sub     rsp, 48h
0x180036802  mov     rbx, r9
0x180036805  mov     dil, r8b
0x180036808  mov     rsi, rdx
0x18003680b  mov     r14, rcx
0x18003680e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036815  mov     ecx, 0A0h; unsigned __int64
0x18003681a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003681f  mov     [rsp+68h+var_38], rax
0x180036824  test    rax, rax
0x180036827  jz      short loc_18003683F
0x180036829  mov     r9, rbx
0x18003682c  mov     r8b, dil
0x18003682f  mov     rdx, rsi
0x180036832  mov     rcx, rax
0x180036835  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18003683a  mov     rbx, rax
0x18003683d  jmp     short loc_180036841
0x18003683f  xor     ebx, ebx
0x180036841  test    rbx, rbx
0x180036844  jnz     short loc_18003686B
0x180036846  mov     rcx, [rsp+68h]; this
0x18003684b  mov     ebx, 8007000Eh
0x180036850  mov     r9d, ebx; char *
0x180036853  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003685a  mov     edx, 0CBBh; void *
0x18003685f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036864  mov     eax, ebx
0x180036866  jmp     loc_1800369A6
0x18003686b  mov     r9d, 1F0003h; dwDesiredAccess
0x180036871  xor     r8d, r8d; dwFlags
0x180036874  xor     edx, edx; lpName
0x180036876  xor     ecx, ecx; lpEventAttributes
0x180036878  call    cs:__imp_CreateEventExW
0x18003687e  mov     rsi, rax
0x180036881  test    rax, rax
0x180036884  jz      short loc_1800368A0
0x180036886  lea     rdi, [rbx+80h]
0x18003688d  call    cs:__imp_GetLastError
0x180036893  mov     rdx, rsi
0x180036896  mov     rcx, rdi
0x180036899  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003689e  jmp     short loc_1800368D0
0x1800368a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800368a5  mov     edi, eax
0x1800368a7  test    eax, eax
0x1800368a9  jns     short loc_1800368C9
0x1800368ab  mov     rcx, [rsp+68h]; this
0x1800368b0  mov     r9d, eax; char *
0x1800368b3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800368ba  mov     edx, 0CBCh; void *
0x1800368bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800368c4  jmp     loc_180036973
0x1800368c9  lea     rdi, [rbx+80h]
0x1800368d0  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x1800368d7  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x1800368df  mov     r9, [rdi]; hEvent
0x1800368e2  mov     r8d, 10000005h; dwNotifyFilter
0x1800368e8  mov     rcx, [rbx+78h]; hKey
0x1800368ec  call    cs:__imp_RegNotifyChangeKeyValue
0x1800368f2  test    eax, eax
0x1800368f4  jz      short loc_180036911
0x1800368f6  mov     rcx, [rsp+68h]; this
0x1800368fb  mov     r9d, eax; char *
0x1800368fe  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036905  mov     edx, 0CC2h; void *
0x18003690a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003690f  jmp     short loc_180036971
0x180036911  xor     r8d, r8d; pcbe
0x180036914  mov     rdx, rbx; pv
0x180036917  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18003691e  call    cs:__imp_CreateThreadpoolWait
0x180036924  mov     rdi, rax
0x180036927  mov     rsi, [rbx+88h]
0x18003692e  test    rsi, rsi
0x180036931  jz      short loc_18003694F
0x180036933  lea     rcx, [rsp+68h+var_38]; this
0x180036938  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003693d  mov     rcx, rsi; pwa
0x180036940  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x180036945  lea     rcx, [rsp+68h+var_38]; this
0x18003694a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003694f  mov     [rbx+88h], rdi
0x180036956  test    rdi, rdi
0x180036959  jnz     short loc_18003697F
0x18003695b  mov     rcx, [rsp+68h]; this
0x180036960  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036967  mov     edx, 0CC5h; void *
0x18003696c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036971  mov     edi, eax
0x180036973  mov     rcx, rbx; this
0x180036976  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18003697b  mov     eax, edi
0x18003697d  jmp     short loc_1800369A6
0x18003697f  mov     rdx, rbx
0x180036982  mov     rcx, r14
0x180036985  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18003698a  mov     rcx, [r14]
0x18003698d  xor     r8d, r8d; pftTimeout
0x180036990  mov     rdx, [rcx+80h]; h
0x180036997  mov     rcx, [rcx+88h]; pwa
0x18003699e  call    cs:__imp_SetThreadpoolWait
0x1800369a4  xor     eax, eax
0x1800369a6  add     rsp, 48h
0x1800369aa  pop     r14
0x1800369ac  pop     rdi
0x1800369ad  pop     rsi
0x1800369ae  pop     rbx
0x1800369af  retn
```
