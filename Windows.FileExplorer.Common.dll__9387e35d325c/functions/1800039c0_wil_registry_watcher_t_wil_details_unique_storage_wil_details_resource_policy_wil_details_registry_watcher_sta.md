# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800039c0`
- end: `0x180003b9f`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003914`

## callees

- `0x18000329c`
- `0x180003788`
- `0x1800039c0`
- `0x180003ba8`
- `0x180003bd0`
- `0x1800077c8`
- `0x18002edcc`
- `0x18003169c`
- `0x180037ca0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180003b0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180003b0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003b6a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003b6a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180003ac8`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180003ac8`

## string_xrefs

- `0x180003a80`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180003ada`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180003b31`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180003b89`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v11; // eax
  int LastError; // eax
  unsigned int v13; // edx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v16; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    if ( *(_QWORD *)(a4 + 112) )
    {
      v7[14] = v7 + 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 16LL))(*(_QWORD *)(a4 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 24LL))(*(_QWORD *)(a4 + 112));
      *(_QWORD *)(a4 + 112) = 0;
    }
    else
    {
      v7[14] = 0;
    }
    v8[15] = *a2;
    *a2 = 0;
    v8[16] = 0;
    v8[17] = 0;
    *((_BYTE *)v8 + 144) = 1;
    *((_DWORD *)v8 + 37) = 1;
    v8[19] = 0;
  }
  else
  {
    v8 = 0;
  }
  if ( !v8 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v9;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v8 + 16);
  v9 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
    goto LABEL_11;
  }
  v11 = RegNotifyChangeKeyValue((HKEY)v8[15], *((unsigned __int8 *)v8 + 144), 0x10000005u, (HANDLE)v8[16], 1);
  if ( v11 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v11,
                  fAsynchronousa);
LABEL_10:
    v9 = LastError;
LABEL_11:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v8, v13);
    return v9;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     v8,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v8 + 17,
    ThreadpoolWait);
  if ( !v8[17] )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v16);
    goto LABEL_10;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v8);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 136LL), *(HANDLE *)(*(_QWORD *)a1 + 128LL), 0);
  return 0;
}

```

## disassembly

```asm
0x1800039c0  push    rbx
0x1800039c2  push    rsi
0x1800039c3  push    rdi
0x1800039c4  push    r14
0x1800039c6  sub     rsp, 48h
0x1800039ca  mov     rbx, r9
0x1800039cd  mov     rsi, rdx
0x1800039d0  mov     r14, rcx
0x1800039d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800039da  mov     ecx, 0A0h; unsigned __int64
0x1800039df  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800039e4  mov     rdi, rax
0x1800039e7  mov     [rsp+68h+var_38], rax
0x1800039ec  test    rax, rax
0x1800039ef  jz      loc_180003B44
0x1800039f5  cmp     qword ptr [rbx+70h], 0
0x1800039fa  jz      loc_180003B74
0x180003a00  lea     rdx, [rax+8]
0x180003a04  mov     [rax+70h], rdx
0x180003a08  mov     rcx, [rbx+70h]
0x180003a0c  mov     rax, [rcx]
0x180003a0f  mov     rax, [rax+10h]
0x180003a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a18  mov     rcx, [rbx+70h]
0x180003a1c  mov     rax, [rcx]
0x180003a1f  mov     rax, [rax+18h]
0x180003a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a28  mov     qword ptr [rbx+70h], 0
0x180003a30  mov     rax, [rsi]
0x180003a33  mov     [rdi+78h], rax
0x180003a37  mov     qword ptr [rsi], 0
0x180003a3e  mov     qword ptr [rdi+80h], 0
0x180003a49  mov     qword ptr [rdi+88h], 0
0x180003a54  mov     byte ptr [rdi+90h], 1
0x180003a5b  mov     dword ptr [rdi+94h], 1
0x180003a65  xor     eax, eax
0x180003a67  mov     [rdi+98h], rax
0x180003a6e  test    rdi, rdi
0x180003a71  jnz     short loc_180003A93
0x180003a73  mov     rcx, [rsp+68h]; this
0x180003a78  mov     ebx, 8007000Eh
0x180003a7d  mov     r9d, ebx; char *
0x180003a80  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003a87  mov     edx, 0CBBh; void *
0x180003a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a91  jmp     short loc_180003AF5
0x180003a93  lea     rsi, [rdi+80h]
0x180003a9a  mov     rcx, rsi
0x180003a9d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180003aa2  mov     ebx, eax
0x180003aa4  test    eax, eax
0x180003aa6  js      loc_180003B81
0x180003aac  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x180003ab3  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180003abb  mov     r9, [rsi]; hEvent
0x180003abe  mov     r8d, 10000005h; dwNotifyFilter
0x180003ac4  mov     rcx, [rdi+78h]; hKey
0x180003ac8  call    cs:__imp_RegNotifyChangeKeyValue
0x180003ace  test    eax, eax
0x180003ad0  jz      short loc_180003B01
0x180003ad2  mov     rcx, [rsp+68h]; this
0x180003ad7  mov     r9d, eax; char *
0x180003ada  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003ae1  mov     edx, 0CC2h; void *
0x180003ae6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180003aeb  mov     ebx, eax
0x180003aed  mov     rcx, rdi; this
0x180003af0  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180003af5  mov     eax, ebx
0x180003af7  add     rsp, 48h
0x180003afb  pop     r14
0x180003afd  pop     rdi
0x180003afe  pop     rsi
0x180003aff  pop     rbx
0x180003b00  retn
0x180003b01  xor     r8d, r8d; pcbe
0x180003b04  mov     rdx, rdi; pv
0x180003b07  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180003b0e  call    cs:__imp_CreateThreadpoolWait
0x180003b14  lea     rbx, [rdi+88h]
0x180003b1b  mov     rdx, rax
0x180003b1e  mov     rcx, rbx
0x180003b21  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180003b26  cmp     qword ptr [rbx], 0
0x180003b2a  jnz     short loc_180003B4B
0x180003b2c  mov     rcx, [rsp+68h]; this
0x180003b31  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003b38  mov     edx, 0CC5h; void *
0x180003b3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180003b42  jmp     short loc_180003AEB
0x180003b44  xor     edi, edi
0x180003b46  jmp     loc_180003A6E
0x180003b4b  mov     rdx, rdi
0x180003b4e  mov     rcx, r14
0x180003b51  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180003b56  mov     rcx, [r14]
0x180003b59  xor     r8d, r8d; pftTimeout
0x180003b5c  mov     rdx, [rcx+80h]; h
0x180003b63  mov     rcx, [rcx+88h]; pwa
0x180003b6a  call    cs:__imp_SetThreadpoolWait
0x180003b70  xor     eax, eax
0x180003b72  jmp     short loc_180003AF7
0x180003b74  mov     qword ptr [rax+70h], 0
0x180003b7c  jmp     loc_180003A30
0x180003b81  mov     rcx, [rsp+68h]; this
0x180003b86  mov     r9d, eax; char *
0x180003b89  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003b90  mov     edx, 0CBCh; void *
0x180003b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b9a  jmp     loc_180003AED
```
