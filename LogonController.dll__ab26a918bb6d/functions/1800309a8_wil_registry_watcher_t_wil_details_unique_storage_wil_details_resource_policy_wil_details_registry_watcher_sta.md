# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800309a8`
- end: `0x180030b5a`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800140c8`

## callees

- `0x18000ba40`
- `0x18000baa4`
- `0x1800309a8`
- `0x180030b60`
- `0x18004ecd0`
- `0x18005d488`
- `0x18005d4e8`
- `0x18005d5a0`
- `0x18005d718`
- `0x18005f250`
- `0x180060d00`
- `0x180063024`
- `0x18006f0d8`

## import_xrefs

- `KERNEL32!CreateThreadpoolWait` at `0x180030ac8`
- `KERNEL32!CreateThreadpoolWait` at `0x180030ac8`
- `KERNEL32!SetThreadpoolWait` at `0x180030b48`
- `KERNEL32!SetThreadpoolWait` at `0x180030b48`
- `KERNEL32!CreateEventExW` at `0x180030a22`
- `KERNEL32!CreateEventExW` at `0x180030a22`
- `KERNEL32!GetLastError` at `0x180030a37`
- `KERNEL32!GetLastError` at `0x180030a37`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180030a96`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180030a96`

## string_xrefs

- `0x1800309fd`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180030a5d`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180030aa8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180030b0a`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

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
  wil::details *v11; // rcx
  HANDLE Event; // rsi
  HANDLE *v13; // rdi
  int LastErrorFailHr; // eax
  unsigned int v15; // edi
  unsigned int v16; // edx
  unsigned int v17; // eax
  unsigned int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v20; // r9
  struct _TP_WAIT *v21; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v24[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  v24[0] = v7;
  if ( v7 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state(v7, a2, v8, a4);
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  (const char *)v17,
                  fAsynchronousa);
LABEL_17:
    v15 = LastError;
    goto LABEL_18;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
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
0x1800309a8  push    rbx
0x1800309aa  push    rsi
0x1800309ab  push    rdi
0x1800309ac  push    r14
0x1800309ae  sub     rsp, 48h
0x1800309b2  mov     rbx, r9
0x1800309b5  mov     rdi, rdx
0x1800309b8  mov     r14, rcx
0x1800309bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800309c2  mov     ecx, 0A0h; unsigned __int64
0x1800309c7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800309cc  mov     [rsp+68h+var_38], rax
0x1800309d1  test    rax, rax
0x1800309d4  jz      short loc_1800309E9
0x1800309d6  mov     r9, rbx
0x1800309d9  mov     rdx, rdi
0x1800309dc  mov     rcx, rax
0x1800309df  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800309e4  mov     rbx, rax
0x1800309e7  jmp     short loc_1800309EB
0x1800309e9  xor     ebx, ebx
0x1800309eb  test    rbx, rbx
0x1800309ee  jnz     short loc_180030A15
0x1800309f0  mov     rcx, [rsp+68h]; this
0x1800309f5  mov     ebx, 8007000Eh
0x1800309fa  mov     r9d, ebx; char *
0x1800309fd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030a04  mov     edx, 0CBBh; void *
0x180030a09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a0e  mov     eax, ebx
0x180030a10  jmp     loc_180030B50
0x180030a15  mov     r9d, 1F0003h; dwDesiredAccess
0x180030a1b  xor     r8d, r8d; dwFlags
0x180030a1e  xor     edx, edx; lpName
0x180030a20  xor     ecx, ecx; lpEventAttributes
0x180030a22  call    cs:__imp_CreateEventExW
0x180030a28  mov     rsi, rax
0x180030a2b  test    rax, rax
0x180030a2e  jz      short loc_180030A4A
0x180030a30  lea     rdi, [rbx+80h]
0x180030a37  call    cs:__imp_GetLastError
0x180030a3d  mov     rdx, rsi
0x180030a40  mov     rcx, rdi
0x180030a43  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180030a48  jmp     short loc_180030A7A
0x180030a4a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180030a4f  mov     edi, eax
0x180030a51  test    eax, eax
0x180030a53  jns     short loc_180030A73
0x180030a55  mov     rcx, [rsp+68h]; this
0x180030a5a  mov     r9d, eax; char *
0x180030a5d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030a64  mov     edx, 0CBCh; void *
0x180030a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030a6e  jmp     loc_180030B1D
0x180030a73  lea     rdi, [rbx+80h]
0x180030a7a  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180030a81  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180030a89  mov     r9, [rdi]; hEvent
0x180030a8c  mov     r8d, 10000005h; dwNotifyFilter
0x180030a92  mov     rcx, [rbx+78h]; hKey
0x180030a96  call    cs:__imp_RegNotifyChangeKeyValue
0x180030a9c  test    eax, eax
0x180030a9e  jz      short loc_180030ABB
0x180030aa0  mov     rcx, [rsp+68h]; this
0x180030aa5  mov     r9d, eax; char *
0x180030aa8  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030aaf  mov     edx, 0CC2h; void *
0x180030ab4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180030ab9  jmp     short loc_180030B1B
0x180030abb  xor     r8d, r8d; pcbe
0x180030abe  mov     rdx, rbx; pv
0x180030ac1  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180030ac8  call    cs:__imp_CreateThreadpoolWait
0x180030ace  mov     rdi, rax
0x180030ad1  mov     rsi, [rbx+88h]
0x180030ad8  test    rsi, rsi
0x180030adb  jz      short loc_180030AF9
0x180030add  lea     rcx, [rsp+68h+var_38]; this
0x180030ae2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030ae7  mov     rcx, rsi; pwa
0x180030aea  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x180030aef  lea     rcx, [rsp+68h+var_38]; this
0x180030af4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030af9  mov     [rbx+88h], rdi
0x180030b00  test    rdi, rdi
0x180030b03  jnz     short loc_180030B29
0x180030b05  mov     rcx, [rsp+68h]; this
0x180030b0a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180030b11  mov     edx, 0CC5h; void *
0x180030b16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030b1b  mov     edi, eax
0x180030b1d  mov     rcx, rbx; this
0x180030b20  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180030b25  mov     eax, edi
0x180030b27  jmp     short loc_180030B50
0x180030b29  mov     rdx, rbx
0x180030b2c  mov     rcx, r14
0x180030b2f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180030b34  mov     rcx, [r14]
0x180030b37  xor     r8d, r8d; pftTimeout
0x180030b3a  mov     rdx, [rcx+80h]; h
0x180030b41  mov     rcx, [rcx+88h]; pwa
0x180030b48  call    cs:__imp_SetThreadpoolWait
0x180030b4e  xor     eax, eax
0x180030b50  add     rsp, 48h
0x180030b54  pop     r14
0x180030b56  pop     rdi
0x180030b57  pop     rsi
0x180030b58  pop     rbx
0x180030b59  retn
```
