# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180021a48`
- end: `0x180021c71`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(wil::details **, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002334c`

## callees

- `0x1800025b4`
- `0x180003a94`
- `0x18000aaf4`
- `0x18000ab14`
- `0x1800142c0`
- `0x18001e2b8`
- `0x1800219c0`
- `0x180021a48`
- `0x180021cb8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021be8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021c46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021be8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c34`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180021bd7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180021bd7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021be0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180021be0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180021ba4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180021ba4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021bc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021c5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021bc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180021c5c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180021b7e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180021b7e`

## string_xrefs

- `0x180021b15`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180021b4c`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180021bff`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        wil::details **a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  HANDLE *v11; // rsi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v13; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  int v16; // eax
  const char *v17; // r9
  PTP_WAIT ThreadpoolWait; // r14
  struct _TP_WAIT *v19; // rbp
  DWORD LastError; // ebx
  wil::details *v21; // rbp
  DWORD v22; // ebx
  struct wil::details::registry_watcher_state *v23; // rdx
  BOOL fAsynchronous; // [rsp+20h] [rbp-58h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
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
    *((_BYTE *)v8 + 144) = 0;
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
  v11 = (HANDLE *)(v8 + 16);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((void **)v8 + 16, 0);
  v9 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_19:
    wil::details::registry_watcher_state::~registry_watcher_state((wil::details::registry_watcher_state *)v8);
    operator delete(v8, (const struct std::nothrow_t *)0xA0);
    return v9;
  }
  v13 = RegNotifyChangeKeyValue((HKEY)v8[15], *((unsigned __int8 *)v8 + 144), 0x10000005u, *v11, 1);
  if ( v13 )
  {
    v16 = wil::details::in1diag3::Return_Win32(retaddr, v14, v15, (const char *)v13, fAsynchronousa);
LABEL_18:
    v9 = v16;
    goto LABEL_19;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     (PTP_WAIT_CALLBACK)wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     v8,
                     0);
  v19 = (struct _TP_WAIT *)v8[17];
  if ( v19 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v19, 0, 0);
    WaitForThreadpoolWaitCallbacks(v19, 1);
    CloseThreadpoolWait(v19);
    SetLastError(LastError);
  }
  v8[17] = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xCC5,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
            v17);
    goto LABEL_18;
  }
  v21 = *a1;
  if ( *a1 )
  {
    v22 = GetLastError();
    wil::details::delete_registry_watcher_state(v21, v23);
    SetLastError(v22);
  }
  *a1 = (wil::details *)v8;
  SetThreadpoolWait((PTP_WAIT)v8[17], *v11, 0);
  return 0;
}

```

## disassembly

```asm
0x180021a48  push    rbx
0x180021a4a  push    rbp
0x180021a4b  push    rsi
0x180021a4c  push    rdi
0x180021a4d  push    r14
0x180021a4f  push    r15
0x180021a51  sub     rsp, 48h
0x180021a55  mov     rbx, r9
0x180021a58  mov     rsi, rdx
0x180021a5b  mov     r15, rcx
0x180021a5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021a65  mov     ecx, 0A0h; unsigned __int64
0x180021a6a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021a6f  mov     rdi, rax
0x180021a72  mov     [rsp+78h+var_48], rax
0x180021a77  test    rax, rax
0x180021a7a  jz      loc_180021B01
0x180021a80  cmp     qword ptr [rbx+70h], 0
0x180021a85  jnz     short loc_180021A91
0x180021a87  mov     qword ptr [rax+70h], 0
0x180021a8f  jmp     short loc_180021AC1
0x180021a91  lea     rdx, [rax+8]
0x180021a95  mov     [rax+70h], rdx
0x180021a99  mov     rcx, [rbx+70h]
0x180021a9d  mov     rax, [rcx]
0x180021aa0  mov     rax, [rax+10h]
0x180021aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aa9  mov     rcx, [rbx+70h]
0x180021aad  mov     rax, [rcx]
0x180021ab0  mov     rax, [rax+18h]
0x180021ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ab9  mov     qword ptr [rbx+70h], 0
0x180021ac1  mov     rax, [rsi]
0x180021ac4  mov     [rdi+78h], rax
0x180021ac8  mov     qword ptr [rsi], 0
0x180021acf  mov     qword ptr [rdi+80h], 0
0x180021ada  mov     qword ptr [rdi+88h], 0
0x180021ae5  mov     byte ptr [rdi+90h], 0
0x180021aec  mov     dword ptr [rdi+94h], 1
0x180021af6  xor     eax, eax
0x180021af8  mov     [rdi+98h], rax
0x180021aff  jmp     short loc_180021B03
0x180021b01  xor     edi, edi
0x180021b03  test    rdi, rdi
0x180021b06  jnz     short loc_180021B2D
0x180021b08  mov     rcx, [rsp+78h]; this
0x180021b0d  mov     ebx, 8007000Eh
0x180021b12  mov     r9d, ebx; char *
0x180021b15  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021b1c  mov     edx, 0CBBh; void *
0x180021b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b26  mov     eax, ebx
0x180021b28  jmp     loc_180021C64
0x180021b2d  lea     rsi, [rdi+80h]
0x180021b34  xor     edx, edx
0x180021b36  mov     rcx, rsi
0x180021b39  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180021b3e  mov     ebx, eax
0x180021b40  test    eax, eax
0x180021b42  jns     short loc_180021B62
0x180021b44  mov     rcx, [rsp+78h]; this
0x180021b49  mov     r9d, eax; char *
0x180021b4c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021b53  mov     edx, 0CBCh; void *
0x180021b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b5d  jmp     loc_180021C12
0x180021b62  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x180021b69  mov     [rsp+78h+fAsynchronous], 1; unsigned int
0x180021b71  mov     r9, [rsi]; hEvent
0x180021b74  mov     r8d, 10000005h; dwNotifyFilter
0x180021b7a  mov     rcx, [rdi+78h]; hKey
0x180021b7e  call    cs:__imp_RegNotifyChangeKeyValue
0x180021b84  test    eax, eax
0x180021b86  jz      short loc_180021B97
0x180021b88  mov     rcx, [rsp+78h]; this
0x180021b8d  mov     r9d, eax; char *
0x180021b90  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021b95  jmp     short loc_180021C10
0x180021b97  xor     r8d, r8d; pcbe
0x180021b9a  mov     rdx, rdi; pv
0x180021b9d  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180021ba4  call    cs:__imp_CreateThreadpoolWait
0x180021baa  mov     r14, rax
0x180021bad  mov     rbp, [rdi+88h]
0x180021bb4  test    rbp, rbp
0x180021bb7  jz      short loc_180021BEE
0x180021bb9  call    cs:__imp_GetLastError
0x180021bbf  mov     ebx, eax
0x180021bc1  xor     r8d, r8d; pftTimeout
0x180021bc4  xor     edx, edx; h
0x180021bc6  mov     rcx, rbp; pwa
0x180021bc9  call    cs:__imp_SetThreadpoolWait
0x180021bcf  mov     edx, 1; fCancelPendingCallbacks
0x180021bd4  mov     rcx, rbp; pwa
0x180021bd7  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180021bdd  mov     rcx, rbp; pwa
0x180021be0  call    cs:__imp_CloseThreadpoolWait
0x180021be6  mov     ecx, ebx; dwErrCode
0x180021be8  call    cs:__imp_SetLastError
0x180021bee  mov     [rdi+88h], r14
0x180021bf5  test    r14, r14
0x180021bf8  jnz     short loc_180021C2C
0x180021bfa  mov     rcx, [rsp+78h]; this
0x180021bff  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021c06  mov     edx, 0CC5h; void *
0x180021c0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021c10  mov     ebx, eax
0x180021c12  mov     rcx, rdi; this
0x180021c15  call    ??1registry_watcher_state@details@wil@@QEAA@XZ; wil::details::registry_watcher_state::~registry_watcher_state(void)
0x180021c1a  mov     edx, 0A0h; struct std::nothrow_t *
0x180021c1f  mov     rcx, rdi; void *
0x180021c22  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021c27  jmp     loc_180021B26
0x180021c2c  mov     rbp, [r15]
0x180021c2f  test    rbp, rbp
0x180021c32  jz      short loc_180021C4C
0x180021c34  call    cs:__imp_GetLastError
0x180021c3a  mov     ebx, eax
0x180021c3c  mov     rcx, rbp; this
0x180021c3f  call    ?delete_registry_watcher_state@details@wil@@YAXPEAUregistry_watcher_state@12@@Z; wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *)
0x180021c44  mov     ecx, ebx; dwErrCode
0x180021c46  call    cs:__imp_SetLastError
0x180021c4c  mov     [r15], rdi
0x180021c4f  xor     r8d, r8d; pftTimeout
0x180021c52  mov     rdx, [rsi]; h
0x180021c55  mov     rcx, [rdi+88h]; pwa
0x180021c5c  call    cs:__imp_SetThreadpoolWait
0x180021c62  xor     eax, eax
0x180021c64  add     rsp, 48h
0x180021c68  pop     r15
0x180021c6a  pop     r14
0x180021c6c  pop     rdi
0x180021c6d  pop     rsi
0x180021c6e  pop     rbp
0x180021c6f  pop     rbx
0x180021c70  retn
```
