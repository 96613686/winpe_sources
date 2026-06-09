# wil::make_registry_watcher_nothrow(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180007b64`
- end: `0x180007df3`
- name: `?make_registry_watcher_nothrow@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800072a0`

## callees

- `0x180007b64`
- `0x180008000`
- `0x180008570`
- `0x180026f10`
- `0x180034768`
- `0x180034c6c`
- `0x180034db4`
- `0x18003c650`
- `0x18003c670`
- `0x18003f1f0`
- `0x18005659c`
- `0x18006b6bc`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007c6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c7b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007da7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007da7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007d31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007d31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007dd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007dd5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007bb3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007bb3`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180007cd0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180007cd0`

## string_xrefs

- `0x180007cdf`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180007d03`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180007d73`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180007db4`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
wil::details::registry_watcher_state **__fastcall wil::make_registry_watcher_nothrow(
        wil::details::registry_watcher_state **a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5)
{
  LSTATUS v6; // eax
  bool v7; // sf
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rsi
  wil::details *v11; // rcx
  HANDLE Event; // rbp
  wil::details *v13; // rsi
  void *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // edx
  int LastErrorFailHr; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v19; // r9
  struct _TP_WAIT *v20; // rbp
  PTP_WAIT v21; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char v26; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  *a1 = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_CURRENT_USER, a3, 0, 0, 0, 0x10u, 0, &hKey, 0);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( !v7 )
  {
    v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( v8 )
    {
      v10 = a5;
      if ( *(_QWORD *)(a5 + 112) )
      {
        v8[14] = v8 + 1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 112) + 16LL))(*(_QWORD *)(v10 + 112));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 112) + 24LL))(*(_QWORD *)(v10 + 112));
        *(_QWORD *)(v10 + 112) = 0;
      }
      else
      {
        v8[14] = 0;
      }
      v9[15] = hKey;
      hKey = 0;
      v9[16] = 0;
      v9[17] = 0;
      *((_BYTE *)v9 + 144) = 0;
      *((_DWORD *)v9 + 37) = 1;
      v9[19] = 0;
      Event = CreateEventExW(0, 0, 0, 0x1F0003u);
      if ( Event )
      {
        GetLastError();
        v13 = (wil::details *)v9[16];
        if ( v13 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
          wil::details::CloseHandle(v13, v14);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
        }
        v9[16] = Event;
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v11);
        if ( LastErrorFailHr < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCBC,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
            (const char *)(unsigned int)LastErrorFailHr,
            fAsynchronous);
          goto LABEL_16;
        }
      }
      v15 = RegNotifyChangeKeyValue((HKEY)v9[15], *((unsigned __int8 *)v9 + 144), 0x10000005u, (HANDLE)v9[16], 1);
      if ( v15 )
      {
        wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xCC2,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
          (const char *)v15,
          fAsynchronousa);
LABEL_16:
        wil::details::registry_watcher_state::`scalar deleting destructor'(
          (wil::details::registry_watcher_state *)v9,
          v16);
        goto LABEL_25;
      }
      ThreadpoolWait = CreateThreadpoolWait(
                         wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                         v9,
                         0);
      v20 = (struct _TP_WAIT *)v9[17];
      v21 = ThreadpoolWait;
      if ( v20 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
        wil::details::DestroyThreadPoolWait<0>::Destroy(v20);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
      }
      v9[17] = v21;
      if ( !v21 )
      {
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xCC5,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
          v19);
        goto LABEL_16;
      }
      if ( *a1 )
        wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*a1);
      *a1 = (wil::details::registry_watcher_state *)v9;
      SetThreadpoolWait((PTP_WAIT)v9[17], (HANDLE)v9[16], 0);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBB,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
        (const char *)0x8007000ELL,
        fAsynchronous);
    }
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x180007b64  mov     rax, rsp
0x180007b67  mov     [rax+18h], rbx
0x180007b6b  mov     [rax+20h], rbp
0x180007b6f  mov     [rax+10h], rdx
0x180007b73  push    rsi
0x180007b74  push    rdi
0x180007b75  push    r14
0x180007b77  sub     rsp, 50h
0x180007b7b  xor     r14d, r14d
0x180007b7e  mov     rdi, rcx
0x180007b81  mov     [rax-28h], r14
0x180007b85  mov     rdx, r8; lpSubKey
0x180007b88  mov     [rcx], r14
0x180007b8b  xor     r9d, r9d; lpClass
0x180007b8e  lea     rcx, [rax+10h]
0x180007b92  mov     [rax+10h], r14
0x180007b96  mov     [rax-30h], rcx
0x180007b9a  xor     r8d, r8d; Reserved
0x180007b9d  mov     [rax-38h], r14
0x180007ba1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180007ba8  mov     dword ptr [rax-40h], 10h
0x180007baf  mov     [rax-48h], r14d
0x180007bb3  call    cs:__imp_RegCreateKeyExW
0x180007bb9  test    eax, eax
0x180007bbb  jle     short loc_180007BC7
0x180007bbd  movzx   eax, ax
0x180007bc0  or      eax, 80070000h
0x180007bc5  test    eax, eax
0x180007bc7  js      loc_180007DCB
0x180007bcd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007bd4  mov     ecx, 0A0h; unsigned __int64
0x180007bd9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007bde  mov     rbx, rax
0x180007be1  test    rax, rax
0x180007be4  jz      loc_180007DAF
0x180007bea  mov     rsi, [rsp+68h+arg_20]
0x180007bf2  cmp     [rsi+70h], r14
0x180007bf6  jnz     short loc_180007BFE
0x180007bf8  mov     [rax+70h], r14
0x180007bfc  jmp     short loc_180007C2A
0x180007bfe  lea     rdx, [rax+8]
0x180007c02  mov     [rax+70h], rdx
0x180007c06  mov     rcx, [rsi+70h]
0x180007c0a  mov     rax, [rcx]
0x180007c0d  mov     rax, [rax+10h]
0x180007c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c16  mov     rcx, [rsi+70h]
0x180007c1a  mov     rax, [rcx]
0x180007c1d  mov     rax, [rax+18h]
0x180007c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c26  mov     [rsi+70h], r14
0x180007c2a  mov     rax, [rsp+68h+hKey]
0x180007c2f  mov     r9d, 1F0003h; dwDesiredAccess
0x180007c35  mov     [rbx+78h], rax
0x180007c39  xor     r8d, r8d; dwFlags
0x180007c3c  mov     [rsp+68h+hKey], r14
0x180007c41  xor     eax, eax
0x180007c43  mov     [rbx+80h], r14
0x180007c4a  xor     edx, edx; lpName
0x180007c4c  mov     [rbx+88h], r14
0x180007c53  xor     ecx, ecx; lpEventAttributes
0x180007c55  mov     [rbx+90h], r14b
0x180007c5c  mov     dword ptr [rbx+94h], 1
0x180007c66  mov     [rbx+98h], rax
0x180007c6d  call    cs:__imp_CreateEventExW
0x180007c73  mov     rbp, rax
0x180007c76  test    rax, rax
0x180007c79  jz      short loc_180007CF5
0x180007c7b  call    cs:__imp_GetLastError
0x180007c81  mov     rsi, [rbx+80h]
0x180007c88  test    rsi, rsi
0x180007c8b  jz      short loc_180007CA9
0x180007c8d  lea     rcx, [rsp+68h+arg_0]; this
0x180007c92  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007c97  mov     rcx, rsi; this
0x180007c9a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180007c9f  lea     rcx, [rsp+68h+arg_0]; this
0x180007ca4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007ca9  mov     [rbx+80h], rbp
0x180007cb0  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180007cb7  mov     r8d, 10000005h; dwNotifyFilter
0x180007cbd  mov     r9, [rbx+80h]; hEvent
0x180007cc4  mov     rcx, [rbx+78h]; hKey
0x180007cc8  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180007cd0  call    cs:__imp_RegNotifyChangeKeyValue
0x180007cd6  test    eax, eax
0x180007cd8  jz      short loc_180007D24
0x180007cda  mov     rcx, [rsp+68h]; this
0x180007cdf  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007ce6  mov     r9d, eax; char *
0x180007ce9  mov     edx, 0CC2h; void *
0x180007cee  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180007cf3  jmp     short loc_180007D17
0x180007cf5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007cfa  test    eax, eax
0x180007cfc  jns     short loc_180007CB0
0x180007cfe  mov     rcx, [rsp+68h]; this
0x180007d03  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007d0a  mov     r9d, eax; char *
0x180007d0d  mov     edx, 0CBCh; void *
0x180007d12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d17  mov     rcx, rbx; this
0x180007d1a  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180007d1f  jmp     loc_180007DCB
0x180007d24  xor     r8d, r8d; pcbe
0x180007d27  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180007d2e  mov     rdx, rbx; pv
0x180007d31  call    cs:__imp_CreateThreadpoolWait
0x180007d37  mov     rbp, [rbx+88h]
0x180007d3e  mov     rsi, rax
0x180007d41  test    rbp, rbp
0x180007d44  jz      short loc_180007D62
0x180007d46  lea     rcx, [rsp+68h+arg_0]; this
0x180007d4b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007d50  mov     rcx, rbp; pwa
0x180007d53  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x180007d58  lea     rcx, [rsp+68h+arg_0]; this
0x180007d5d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007d62  mov     [rbx+88h], rsi
0x180007d69  test    rsi, rsi
0x180007d6c  jnz     short loc_180007D86
0x180007d6e  mov     rcx, [rsp+68h]; this
0x180007d73  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007d7a  mov     edx, 0CC5h; void *
0x180007d7f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007d84  jmp     short loc_180007D17
0x180007d86  mov     rcx, [rdi]; this
0x180007d89  test    rcx, rcx
0x180007d8c  jz      short loc_180007D93
0x180007d8e  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z; wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)
0x180007d93  mov     [rdi], rbx
0x180007d96  xor     r8d, r8d; pftTimeout
0x180007d99  mov     rdx, [rbx+80h]; h
0x180007da0  mov     rcx, [rbx+88h]; pwa
0x180007da7  call    cs:__imp_SetThreadpoolWait
0x180007dad  jmp     short loc_180007DCB
0x180007daf  mov     rcx, [rsp+68h]; this
0x180007db4  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007dbb  mov     r9d, 8007000Eh; char *
0x180007dc1  mov     edx, 0CBBh; void *
0x180007dc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007dcb  mov     rcx, [rsp+68h+hKey]; hKey
0x180007dd0  test    rcx, rcx
0x180007dd3  jz      short loc_180007DDB
0x180007dd5  call    cs:__imp_RegCloseKey
0x180007ddb  lea     r11, [rsp+68h+var_18]
0x180007de0  mov     rax, rdi
0x180007de3  mov     rbx, [r11+30h]
0x180007de7  mov     rbp, [r11+38h]
0x180007deb  mov     rsp, r11
0x180007dee  pop     r14
0x180007df0  pop     rdi
0x180007df1  pop     rsi
0x180007df2  retn
```
