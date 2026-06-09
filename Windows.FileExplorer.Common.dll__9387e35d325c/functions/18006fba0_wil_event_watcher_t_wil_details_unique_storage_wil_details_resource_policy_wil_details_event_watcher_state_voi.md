# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x18006fba0`
- end: `0x18006fcfd`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18006d34c`

## callees

- `0x180003788`
- `0x180005214`
- `0x1800077c8`
- `0x18003169c`
- `0x180031f34`
- `0x180037ca0`
- `0x18006d530`
- `0x18006da14`
- `0x18006fba0`
- `0x18006fe28`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006fc51`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18006fc51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006fcc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18006fcc0`

## string_xrefs

- `0x18006fc31`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18006fc74`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18006fceb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        __int64 a1,
        __int64 a2,
        int a3,
        const char *a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  unsigned int LastError; // ebx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v12; // r9
  unsigned int v13; // edx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x116C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v17 = a2;
  v8 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v15 = (int)v8;
  if ( v8 )
  {
    wistd::function<void (void)>::function<void (void)>(v8, a4);
    v9[15] = a2;
    v17 = 0;
    v9[16] = 0;
    *((_DWORD *)v9 + 34) = a3;
    *((_DWORD *)v9 + 35) = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1173,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v15);
LABEL_9:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                     v9,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v9 + 16,
    ThreadpoolWait);
  if ( !v9[16] )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1176,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                  v12);
    wil::details::event_watcher_state::`scalar deleting destructor'((wil::details::event_watcher_state *)v9, v13);
    goto LABEL_9;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v9);
  if ( (a3 & 2) == 0 )
    SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 128LL), *(HANDLE *)(*(_QWORD *)a1 + 120LL), 0);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return 0;
}

```

## disassembly

```asm
0x18006fba0  mov     [rsp+arg_0], rbx
0x18006fba5  mov     [rsp+arg_10], rbp
0x18006fbaa  push    rsi
0x18006fbab  push    rdi
0x18006fbac  push    r14
0x18006fbae  sub     rsp, 30h
0x18006fbb2  mov     r14, r9
0x18006fbb5  mov     ebp, r8d
0x18006fbb8  mov     rbx, rdx
0x18006fbbb  mov     rsi, rcx
0x18006fbbe  test    rdx, rdx
0x18006fbc1  jz      loc_18006FCE6
0x18006fbc7  mov     [rsp+48h+arg_8], rdx
0x18006fbcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006fbd3  mov     ecx, 90h; unsigned __int64
0x18006fbd8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006fbdd  mov     rdi, rax
0x18006fbe0  mov     qword ptr [rsp+48h+var_28], rax; int
0x18006fbe5  test    rax, rax
0x18006fbe8  jz      short loc_18006FC1D
0x18006fbea  mov     rdx, r14
0x18006fbed  mov     rcx, rax
0x18006fbf0  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x18006fbf5  mov     [rdi+78h], rbx
0x18006fbf9  mov     [rsp+48h+arg_8], 0
0x18006fc02  mov     qword ptr [rdi+80h], 0
0x18006fc0d  mov     [rdi+88h], ebp
0x18006fc13  xor     eax, eax
0x18006fc15  mov     [rdi+8Ch], eax
0x18006fc1b  jmp     short loc_18006FC1F
0x18006fc1d  xor     edi, edi
0x18006fc1f  test    rdi, rdi
0x18006fc22  jnz     short loc_18006FC44
0x18006fc24  mov     rcx, [rsp+48h]; this
0x18006fc29  mov     ebx, 8007000Eh
0x18006fc2e  mov     r9d, ebx; char *
0x18006fc31  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006fc38  mov     edx, 1173h; void *
0x18006fc3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fc42  jmp     short loc_18006FC90
0x18006fc44  xor     r8d, r8d; pcbe
0x18006fc47  mov     rdx, rdi; pv
0x18006fc4a  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18006fc51  call    cs:__imp_CreateThreadpoolWait
0x18006fc57  lea     rbx, [rdi+80h]
0x18006fc5e  mov     rdx, rax
0x18006fc61  mov     rcx, rbx
0x18006fc64  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18006fc69  cmp     qword ptr [rbx], 0
0x18006fc6d  jnz     short loc_18006FC9E
0x18006fc6f  mov     rcx, [rsp+48h]; this
0x18006fc74  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006fc7b  mov     edx, 1176h; void *
0x18006fc80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006fc85  mov     ebx, eax
0x18006fc87  mov     rcx, rdi; this
0x18006fc8a  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x18006fc8f  nop
0x18006fc90  lea     rcx, [rsp+48h+arg_8]
0x18006fc95  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fc9a  mov     eax, ebx
0x18006fc9c  jmp     short loc_18006FCD3
0x18006fc9e  mov     rdx, rdi
0x18006fca1  mov     rcx, rsi
0x18006fca4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x18006fca9  test    bpl, 2
0x18006fcad  jnz     short loc_18006FCC7
0x18006fcaf  mov     rcx, [rsi]
0x18006fcb2  xor     r8d, r8d; pftTimeout
0x18006fcb5  mov     rdx, [rcx+78h]; h
0x18006fcb9  mov     rcx, [rcx+80h]; pwa
0x18006fcc0  call    cs:__imp_SetThreadpoolWait
0x18006fcc6  nop
0x18006fcc7  lea     rcx, [rsp+48h+arg_8]
0x18006fccc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fcd1  xor     eax, eax
0x18006fcd3  mov     rbx, [rsp+48h+arg_0]
0x18006fcd8  mov     rbp, [rsp+48h+arg_10]
0x18006fcdd  add     rsp, 30h
0x18006fce1  pop     r14
0x18006fce3  pop     rdi
0x18006fce4  pop     rsi
0x18006fce5  retn
0x18006fce6  mov     rcx, [rsp+48h]; this
0x18006fceb  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006fcf2  mov     edx, 116Ch; void *
0x18006fcf7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
