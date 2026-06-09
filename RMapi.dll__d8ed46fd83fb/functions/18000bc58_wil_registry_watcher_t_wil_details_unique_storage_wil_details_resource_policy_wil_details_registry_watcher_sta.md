# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18000bc58`
- end: `0x18000bde4`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009184`

## callees

- `0x180005e00`
- `0x18000aac0`
- `0x18000adc0`
- `0x18000b798`
- `0x18000bc58`
- `0x18000bdec`
- `0x18000be18`
- `0x18000d7c8`
- `0x180010468`
- `0x18001fcd8`
- `0x180022c54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000bcd5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000bcd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcea`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000bd46`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18000bd46`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000bdce`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000bdce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000bd6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000bd6c`

## string_xrefs

- `0x18000bcb0`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18000bd10`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x18000bd8f`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
  __int64 v9; // rdi
  unsigned int v10; // ebx
  wil::details *v12; // rcx
  HANDLE Event; // rsi
  HANDLE *v14; // rbx
  int LastErrorFailHr; // eax
  unsigned int v16; // edx
  unsigned int v17; // eax
  void *v18; // rdx
  unsigned int v19; // r8d
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v22; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-38h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state(v7, a2, v8, a4);
  else
    v9 = 0;
  if ( !v9 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v10;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    v14 = (HANDLE *)(v9 + 128);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v9 + 128,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    v10 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_17:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v9,
        v16);
      return v10;
    }
    v14 = (HANDLE *)(v9 + 128);
  }
  v17 = RegNotifyChangeKeyValue(*(HKEY *)(v9 + 120), *(unsigned __int8 *)(v9 + 144), 0x10000005u, *v14, 1);
  if ( v17 )
  {
    LastError = wil::details::in1diag3::Return_Win32(retaddr, v18, v19, (const char *)v17, fAsynchronousa);
LABEL_16:
    v10 = LastError;
    goto LABEL_17;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v9,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v9 + 136,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v9 + 136) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v22);
    goto LABEL_16;
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
0x18000bc58  mov     [rsp+arg_10], rbx
0x18000bc5d  push    rsi
0x18000bc5e  push    rdi
0x18000bc5f  push    r14
0x18000bc61  sub     rsp, 40h
0x18000bc65  mov     rdi, r9
0x18000bc68  mov     rbx, rdx
0x18000bc6b  mov     r14, rcx
0x18000bc6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bc75  mov     ecx, 0A0h; unsigned __int64
0x18000bc7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bc7f  mov     [rsp+58h+var_28], rax
0x18000bc84  test    rax, rax
0x18000bc87  jz      short loc_18000BC9C
0x18000bc89  mov     r9, rdi
0x18000bc8c  mov     rdx, rbx
0x18000bc8f  mov     rcx, rax
0x18000bc92  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18000bc97  mov     rdi, rax
0x18000bc9a  jmp     short loc_18000BC9E
0x18000bc9c  xor     edi, edi
0x18000bc9e  test    rdi, rdi
0x18000bca1  jnz     short loc_18000BCC8
0x18000bca3  mov     rcx, [rsp+58h]; this
0x18000bca8  mov     ebx, 8007000Eh
0x18000bcad  mov     r9d, ebx; char *
0x18000bcb0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bcb7  mov     edx, 0CBBh; void *
0x18000bcbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bcc1  mov     eax, ebx
0x18000bcc3  jmp     loc_18000BDD6
0x18000bcc8  mov     r9d, 1F0003h; dwDesiredAccess
0x18000bcce  xor     r8d, r8d; dwFlags
0x18000bcd1  xor     edx, edx; lpName
0x18000bcd3  xor     ecx, ecx; lpEventAttributes
0x18000bcd5  call    cs:__imp_CreateEventExW
0x18000bcdb  mov     rsi, rax
0x18000bcde  test    rax, rax
0x18000bce1  jz      short loc_18000BCFD
0x18000bce3  lea     rbx, [rdi+80h]
0x18000bcea  call    cs:__imp_GetLastError
0x18000bcf0  mov     rdx, rsi
0x18000bcf3  mov     rcx, rbx
0x18000bcf6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000bcfb  jmp     short loc_18000BD2A
0x18000bcfd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bd02  mov     ebx, eax
0x18000bd04  test    eax, eax
0x18000bd06  jns     short loc_18000BD23
0x18000bd08  mov     rcx, [rsp+58h]; this
0x18000bd0d  mov     r9d, eax; char *
0x18000bd10  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bd17  mov     edx, 0CBCh; void *
0x18000bd1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd21  jmp     short loc_18000BDA2
0x18000bd23  lea     rbx, [rdi+80h]
0x18000bd2a  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x18000bd31  mov     [rsp+58h+fAsynchronous], 1; unsigned int
0x18000bd39  mov     r9, [rbx]; hEvent
0x18000bd3c  mov     r8d, 10000005h; dwNotifyFilter
0x18000bd42  mov     rcx, [rdi+78h]; hKey
0x18000bd46  call    cs:__imp_RegNotifyChangeKeyValue
0x18000bd4c  test    eax, eax
0x18000bd4e  jz      short loc_18000BD5F
0x18000bd50  mov     rcx, [rsp+58h]; this
0x18000bd55  mov     r9d, eax; char *
0x18000bd58  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000bd5d  jmp     short loc_18000BDA0
0x18000bd5f  xor     r8d, r8d; pcbe
0x18000bd62  mov     rdx, rdi; pv
0x18000bd65  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000bd6c  call    cs:__imp_CreateThreadpoolWait
0x18000bd72  lea     rbx, [rdi+88h]
0x18000bd79  mov     rdx, rax
0x18000bd7c  mov     rcx, rbx
0x18000bd7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18000bd84  cmp     qword ptr [rbx], 0
0x18000bd88  jnz     short loc_18000BDAF
0x18000bd8a  mov     rcx, [rsp+58h]; this
0x18000bd8f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bd96  mov     edx, 0CC5h; void *
0x18000bd9b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bda0  mov     ebx, eax
0x18000bda2  mov     rcx, rdi; this
0x18000bda5  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18000bdaa  jmp     loc_18000BCC1
0x18000bdaf  mov     rdx, rdi
0x18000bdb2  mov     rcx, r14
0x18000bdb5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18000bdba  mov     rcx, [r14]
0x18000bdbd  xor     r8d, r8d; pftTimeout
0x18000bdc0  mov     rdx, [rcx+80h]; h
0x18000bdc7  mov     rcx, [rcx+88h]; pwa
0x18000bdce  call    cs:__imp_SetThreadpoolWait
0x18000bdd4  xor     eax, eax
0x18000bdd6  mov     rbx, [rsp+58h+arg_10]
0x18000bddb  add     rsp, 40h
0x18000bddf  pop     r14
0x18000bde1  pop     rdi
0x18000bde2  pop     rsi
0x18000bde3  retn
```
