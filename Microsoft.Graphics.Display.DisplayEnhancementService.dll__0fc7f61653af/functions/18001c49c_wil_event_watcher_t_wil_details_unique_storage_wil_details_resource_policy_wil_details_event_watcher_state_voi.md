# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x18001c49c`
- end: `0x18001c602`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001c404`
- `0x18007eb88`

## callees

- `0x18000740c`
- `0x180009534`
- `0x180009b3c`
- `0x180009eb0`
- `0x18000acf4`
- `0x18000deac`
- `0x18000decc`
- `0x180018e94`
- `0x18001984c`
- `0x1800198c8`
- `0x18001c49c`
- `0x18001c6e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001c542`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001c542`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001c5ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001c5ca`

## string_xrefs

- `0x18001c522`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001c584`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001c5f0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  unsigned int LastError; // edi
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v11; // r9
  struct _TP_WAIT *v12; // rsi
  unsigned int v13; // edx
  int v15[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0x116C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v17 = a2;
  v7 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  *(_QWORD *)v15 = v7;
  if ( v7 )
  {
    wistd::function<void (void)>::function<void (void)>(v7, a4);
    v8[15] = a2;
    v17 = 0;
    v8[16] = 0;
    v8[17] = 0;
  }
  else
  {
    v8 = 0;
  }
  if ( !v8 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1173,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)0x8007000ELL,
      v15[0]);
LABEL_11:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                     v8,
                     0);
  v12 = (struct _TP_WAIT *)v8[16];
  if ( v12 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v15);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v15);
  }
  v8[16] = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1176,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
                  v11);
    wil::details::event_watcher_state::`scalar deleting destructor'((wil::details::event_watcher_state *)v8, v13);
    goto LABEL_11;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v8);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 128LL), *(HANDLE *)(*(_QWORD *)a1 + 120LL), 0);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return 0;
}

```

## disassembly

```asm
0x18001c49c  mov     [rsp+arg_0], rbx
0x18001c4a1  push    rsi
0x18001c4a2  push    rdi
0x18001c4a3  push    r14
0x18001c4a5  sub     rsp, 30h
0x18001c4a9  mov     rsi, r9
0x18001c4ac  mov     rdi, rdx
0x18001c4af  mov     r14, rcx
0x18001c4b2  test    rdx, rdx
0x18001c4b5  jz      loc_18001C5EB
0x18001c4bb  mov     [rsp+48h+arg_8], rdx
0x18001c4c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c4c7  mov     ecx, 90h; unsigned __int64
0x18001c4cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c4d1  mov     rbx, rax
0x18001c4d4  mov     qword ptr [rsp+48h+var_28], rax; int
0x18001c4d9  test    rax, rax
0x18001c4dc  jz      short loc_18001C50E
0x18001c4de  mov     rdx, rsi
0x18001c4e1  mov     rcx, rax
0x18001c4e4  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x18001c4e9  mov     [rbx+78h], rdi
0x18001c4ed  mov     [rsp+48h+arg_8], 0
0x18001c4f6  mov     qword ptr [rbx+80h], 0
0x18001c501  mov     qword ptr [rbx+88h], 0
0x18001c50c  jmp     short loc_18001C510
0x18001c50e  xor     ebx, ebx
0x18001c510  test    rbx, rbx
0x18001c513  jnz     short loc_18001C535
0x18001c515  mov     rcx, [rsp+48h]; this
0x18001c51a  mov     edi, 8007000Eh
0x18001c51f  mov     r9d, edi; char *
0x18001c522  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c529  mov     edx, 1173h; void *
0x18001c52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c533  jmp     short loc_18001C5A0
0x18001c535  xor     r8d, r8d; pcbe
0x18001c538  mov     rdx, rbx; pv
0x18001c53b  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001c542  call    cs:__imp_CreateThreadpoolWait
0x18001c548  mov     rdi, rax
0x18001c54b  mov     rsi, [rbx+80h]
0x18001c552  test    rsi, rsi
0x18001c555  jz      short loc_18001C573
0x18001c557  lea     rcx, [rsp+48h+var_28]; this
0x18001c55c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c561  mov     rcx, rsi; pwa
0x18001c564  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x18001c569  lea     rcx, [rsp+48h+var_28]; this
0x18001c56e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c573  mov     [rbx+80h], rdi
0x18001c57a  test    rdi, rdi
0x18001c57d  jnz     short loc_18001C5AE
0x18001c57f  mov     rcx, [rsp+48h]; this
0x18001c584  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c58b  mov     edx, 1176h; void *
0x18001c590  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c595  mov     edi, eax
0x18001c597  mov     rcx, rbx; this
0x18001c59a  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x18001c59f  nop
0x18001c5a0  lea     rcx, [rsp+48h+arg_8]
0x18001c5a5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c5aa  mov     eax, edi
0x18001c5ac  jmp     short loc_18001C5DD
0x18001c5ae  mov     rdx, rbx
0x18001c5b1  mov     rcx, r14
0x18001c5b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x18001c5b9  mov     rcx, [r14]
0x18001c5bc  xor     r8d, r8d; pftTimeout
0x18001c5bf  mov     rdx, [rcx+78h]; h
0x18001c5c3  mov     rcx, [rcx+80h]; pwa
0x18001c5ca  call    cs:__imp_SetThreadpoolWait
0x18001c5d0  nop
0x18001c5d1  lea     rcx, [rsp+48h+arg_8]
0x18001c5d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001c5db  xor     eax, eax
0x18001c5dd  mov     rbx, [rsp+48h+arg_0]
0x18001c5e2  add     rsp, 30h
0x18001c5e6  pop     r14
0x18001c5e8  pop     rdi
0x18001c5e9  pop     rsi
0x18001c5ea  retn
0x18001c5eb  mov     rcx, [rsp+48h]; this
0x18001c5f0  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c5f7  mov     edx, 116Ch; void *
0x18001c5fc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
