# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x18004de88`
- end: `0x18004dfde`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18004ddb8`

## callees

- `0x1800088bc`
- `0x180009cb8`
- `0x18000a108`
- `0x18000b694`
- `0x18000b6b4`
- `0x18000d3bc`
- `0x18004c934`
- `0x18004de88`
- `0x18004e0c8`
- `0x18004e11c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004dfa8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004dfa8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004df39`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004df39`

## string_xrefs

- `0x18004df19`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18004df5c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
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
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0x116C, a3, a4);
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
0x18004de88  mov     [rsp+arg_0], rbx
0x18004de8d  mov     [rsp+arg_10], rbp
0x18004de92  push    rsi
0x18004de93  push    rdi
0x18004de94  push    r14
0x18004de96  sub     rsp, 30h
0x18004de9a  mov     r14, r9
0x18004de9d  mov     ebp, r8d
0x18004dea0  mov     rbx, rdx
0x18004dea3  mov     rsi, rcx
0x18004dea6  test    rdx, rdx
0x18004dea9  jz      loc_18004DFCE
0x18004deaf  mov     [rsp+48h+arg_8], rdx
0x18004deb4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004debb  mov     ecx, 90h; unsigned __int64
0x18004dec0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004dec5  mov     rdi, rax
0x18004dec8  mov     qword ptr [rsp+48h+var_28], rax; int
0x18004decd  test    rax, rax
0x18004ded0  jz      short loc_18004DF05
0x18004ded2  mov     rdx, r14
0x18004ded5  mov     rcx, rax
0x18004ded8  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x18004dedd  mov     [rdi+78h], rbx
0x18004dee1  mov     [rsp+48h+arg_8], 0
0x18004deea  mov     qword ptr [rdi+80h], 0
0x18004def5  mov     [rdi+88h], ebp
0x18004defb  xor     eax, eax
0x18004defd  mov     [rdi+8Ch], eax
0x18004df03  jmp     short loc_18004DF07
0x18004df05  xor     edi, edi
0x18004df07  test    rdi, rdi
0x18004df0a  jnz     short loc_18004DF2C
0x18004df0c  mov     rcx, [rsp+48h]; this
0x18004df11  mov     ebx, 8007000Eh
0x18004df16  mov     r9d, ebx; char *
0x18004df19  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004df20  mov     edx, 1173h; void *
0x18004df25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004df2a  jmp     short loc_18004DF78
0x18004df2c  xor     r8d, r8d; pcbe
0x18004df2f  mov     rdx, rdi; pv
0x18004df32  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18004df39  call    cs:__imp_CreateThreadpoolWait
0x18004df3f  lea     rbx, [rdi+80h]
0x18004df46  mov     rdx, rax
0x18004df49  mov     rcx, rbx
0x18004df4c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18004df51  cmp     qword ptr [rbx], 0
0x18004df55  jnz     short loc_18004DF86
0x18004df57  mov     rcx, [rsp+48h]; this
0x18004df5c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004df63  mov     edx, 1176h; void *
0x18004df68  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004df6d  mov     ebx, eax
0x18004df6f  mov     rcx, rdi; this
0x18004df72  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x18004df77  nop
0x18004df78  lea     rcx, [rsp+48h+arg_8]
0x18004df7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004df82  mov     eax, ebx
0x18004df84  jmp     short loc_18004DFBB
0x18004df86  mov     rdx, rdi
0x18004df89  mov     rcx, rsi
0x18004df8c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x18004df91  test    bpl, 2
0x18004df95  jnz     short loc_18004DFAF
0x18004df97  mov     rcx, [rsi]
0x18004df9a  xor     r8d, r8d; pftTimeout
0x18004df9d  mov     rdx, [rcx+78h]; h
0x18004dfa1  mov     rcx, [rcx+80h]; pwa
0x18004dfa8  call    cs:__imp_SetThreadpoolWait
0x18004dfae  nop
0x18004dfaf  lea     rcx, [rsp+48h+arg_8]
0x18004dfb4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004dfb9  xor     eax, eax
0x18004dfbb  mov     rbx, [rsp+48h+arg_0]
0x18004dfc0  mov     rbp, [rsp+48h+arg_10]
0x18004dfc5  add     rsp, 30h
0x18004dfc9  pop     r14
0x18004dfcb  pop     rdi
0x18004dfcc  pop     rsi
0x18004dfcd  retn
0x18004dfce  mov     rcx, [rsp+48h]; this
0x18004dfd3  mov     edx, 116Ch; void *
0x18004dfd8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
