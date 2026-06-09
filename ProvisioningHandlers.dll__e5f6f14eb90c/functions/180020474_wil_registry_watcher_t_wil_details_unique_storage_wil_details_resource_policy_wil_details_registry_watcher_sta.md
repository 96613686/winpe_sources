# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180020474`
- end: `0x18002064b`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020398`

## callees

- `0x1800034b8`
- `0x180004394`
- `0x180004a90`
- `0x180006080`
- `0x1800087cc`
- `0x1800087ec`
- `0x18000a614`
- `0x180010284`
- `0x180011ff0`
- `0x180013810`
- `0x18001c7b8`
- `0x180020474`
- `0x180021e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800204f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800204f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002050f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002050f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800205ac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800205ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180020632`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180020632`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180020574`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180020574`

## string_xrefs

- `0x1800204cf`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x18002053b`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x18002058c`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800205f4`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

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

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
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
0x180020474  push    rbx
0x180020476  push    rsi
0x180020477  push    rdi
0x180020478  push    r14
0x18002047a  sub     rsp, 48h
0x18002047e  mov     rbx, r9
0x180020481  mov     dil, r8b
0x180020484  mov     rsi, rdx
0x180020487  mov     r14, rcx
0x18002048a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020491  mov     ecx, 0A0h; unsigned __int64
0x180020496  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002049b  mov     [rsp+68h+var_38], rax
0x1800204a0  test    rax, rax
0x1800204a3  jz      short loc_1800204BB
0x1800204a5  mov     r9, rbx
0x1800204a8  mov     r8b, dil
0x1800204ab  mov     rdx, rsi
0x1800204ae  mov     rcx, rax
0x1800204b1  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800204b6  mov     rbx, rax
0x1800204b9  jmp     short loc_1800204BD
0x1800204bb  xor     ebx, ebx
0x1800204bd  test    rbx, rbx
0x1800204c0  jnz     short loc_1800204E7
0x1800204c2  mov     rcx, [rsp+68h]; this
0x1800204c7  mov     ebx, 8007000Eh
0x1800204cc  mov     r9d, ebx; char *
0x1800204cf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800204d6  mov     edx, 0CBBh; void *
0x1800204db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204e0  mov     eax, ebx
0x1800204e2  jmp     loc_180020640
0x1800204e7  mov     r9d, 1F0003h; dwDesiredAccess
0x1800204ed  xor     r8d, r8d; dwFlags
0x1800204f0  xor     edx, edx; lpName
0x1800204f2  xor     ecx, ecx; lpEventAttributes
0x1800204f4  call    cs:__imp_CreateEventExW
0x1800204fb  nop     dword ptr [rax+rax+00h]
0x180020500  mov     rsi, rax
0x180020503  test    rax, rax
0x180020506  jz      short loc_180020528
0x180020508  lea     rdi, [rbx+80h]
0x18002050f  call    cs:__imp_GetLastError
0x180020516  nop     dword ptr [rax+rax+00h]
0x18002051b  mov     rdx, rsi
0x18002051e  mov     rcx, rdi
0x180020521  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180020526  jmp     short loc_180020558
0x180020528  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002052d  mov     edi, eax
0x18002052f  test    eax, eax
0x180020531  jns     short loc_180020551
0x180020533  mov     rcx, [rsp+68h]; this
0x180020538  mov     r9d, eax; char *
0x18002053b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020542  mov     edx, 0CBCh; void *
0x180020547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002054c  jmp     loc_180020607
0x180020551  lea     rdi, [rbx+80h]
0x180020558  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x18002055f  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180020567  mov     r9, [rdi]; hEvent
0x18002056a  mov     r8d, 10000005h; dwNotifyFilter
0x180020570  mov     rcx, [rbx+78h]; hKey
0x180020574  call    cs:__imp_RegNotifyChangeKeyValue
0x18002057b  nop     dword ptr [rax+rax+00h]
0x180020580  test    eax, eax
0x180020582  jz      short loc_18002059F
0x180020584  mov     rcx, [rsp+68h]; this
0x180020589  mov     r9d, eax; char *
0x18002058c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020593  mov     edx, 0CC2h; void *
0x180020598  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002059d  jmp     short loc_180020605
0x18002059f  xor     r8d, r8d; pcbe
0x1800205a2  mov     rdx, rbx; pv
0x1800205a5  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800205ac  call    cs:__imp_CreateThreadpoolWait
0x1800205b3  nop     dword ptr [rax+rax+00h]
0x1800205b8  mov     rdi, rax
0x1800205bb  mov     rsi, [rbx+88h]
0x1800205c2  test    rsi, rsi
0x1800205c5  jz      short loc_1800205E3
0x1800205c7  lea     rcx, [rsp+68h+var_38]; this
0x1800205cc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800205d1  mov     rcx, rsi; pwa
0x1800205d4  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800205d9  lea     rcx, [rsp+68h+var_38]; this
0x1800205de  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800205e3  mov     [rbx+88h], rdi
0x1800205ea  test    rdi, rdi
0x1800205ed  jnz     short loc_180020613
0x1800205ef  mov     rcx, [rsp+68h]; this
0x1800205f4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800205fb  mov     edx, 0CC5h; void *
0x180020600  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020605  mov     edi, eax
0x180020607  mov     rcx, rbx; this
0x18002060a  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18002060f  mov     eax, edi
0x180020611  jmp     short loc_180020640
0x180020613  mov     rdx, rbx
0x180020616  mov     rcx, r14
0x180020619  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18002061e  mov     rcx, [r14]
0x180020621  xor     r8d, r8d; pftTimeout
0x180020624  mov     rdx, [rcx+80h]; h
0x18002062b  mov     rcx, [rcx+88h]; pwa
0x180020632  call    cs:__imp_SetThreadpoolWait
0x180020639  nop     dword ptr [rax+rax+00h]
0x18002063e  xor     eax, eax
0x180020640  add     rsp, 48h
0x180020644  pop     r14
0x180020646  pop     rdi
0x180020647  pop     rsi
0x180020648  pop     rbx
0x180020649  retn
```
