# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x18002acac`
- end: `0x18002ae22`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000fa98`

## callees

- `0x180010b08`
- `0x1800112a4`
- `0x1800112c8`
- `0x180015404`
- `0x180015494`
- `0x18001be40`
- `0x18001de4c`
- `0x180022eac`
- `0x180022ed8`
- `0x18002909c`
- `0x18002acac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002adf2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002adf2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002ad51`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002ad51`

## string_xrefs

- `0x18002ad31`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002ad93`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        wil::details::event_watcher_state **a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  void *v7; // rax
  void *v8; // rbx
  unsigned int LastError; // edi
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v11; // r9
  struct _TP_WAIT *v12; // rbp
  unsigned int v13; // edx
  wil::details::event_watcher_state *v15; // rdi
  unsigned int v16; // edx
  int v17[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v19; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0x116C, a3, a4);
  v19 = a2;
  v7 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  *(_QWORD *)v17 = v7;
  if ( v7 )
  {
    wistd::function<void (void)>::function<void (void)>(v7, a4);
    *((_QWORD *)v8 + 15) = a2;
    v19 = 0;
    *((_QWORD *)v8 + 16) = 0;
    *((_QWORD *)v8 + 17) = 0;
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
      v17[0]);
LABEL_11:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                     v8,
                     0);
  v12 = (struct _TP_WAIT *)*((_QWORD *)v8 + 16);
  if ( v12 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v17);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v17);
  }
  *((_QWORD *)v8 + 16) = ThreadpoolWait;
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
  v15 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v17);
    wil::details::event_watcher_state::`scalar deleting destructor'(v15, v16);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v17);
  }
  *a1 = (wil::details::event_watcher_state *)v8;
  SetThreadpoolWait(*((PTP_WAIT *)v8 + 16), *((HANDLE *)v8 + 15), 0);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
  return 0;
}

```

## disassembly

```asm
0x18002acac  mov     [rsp+arg_0], rbx
0x18002acb1  push    rbp
0x18002acb2  push    rsi
0x18002acb3  push    rdi
0x18002acb4  sub     rsp, 30h
0x18002acb8  mov     rbp, r9
0x18002acbb  mov     rdi, rdx
0x18002acbe  mov     rsi, rcx
0x18002acc1  test    rdx, rdx
0x18002acc4  jz      loc_18002AE12
0x18002acca  mov     [rsp+48h+arg_8], rdx
0x18002accf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002acd6  mov     ecx, 90h; unsigned __int64
0x18002acdb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ace0  mov     rbx, rax
0x18002ace3  mov     qword ptr [rsp+48h+var_28], rax; int
0x18002ace8  test    rax, rax
0x18002aceb  jz      short loc_18002AD1D
0x18002aced  mov     rdx, rbp
0x18002acf0  mov     rcx, rax
0x18002acf3  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x18002acf8  mov     [rbx+78h], rdi
0x18002acfc  mov     [rsp+48h+arg_8], 0
0x18002ad05  mov     qword ptr [rbx+80h], 0
0x18002ad10  mov     qword ptr [rbx+88h], 0
0x18002ad1b  jmp     short loc_18002AD1F
0x18002ad1d  xor     ebx, ebx
0x18002ad1f  test    rbx, rbx
0x18002ad22  jnz     short loc_18002AD44
0x18002ad24  mov     rcx, [rsp+48h]; this
0x18002ad29  mov     edi, 8007000Eh
0x18002ad2e  mov     r9d, edi; char *
0x18002ad31  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ad38  mov     edx, 1173h; void *
0x18002ad3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ad42  jmp     short loc_18002ADAF
0x18002ad44  xor     r8d, r8d; pcbe
0x18002ad47  mov     rdx, rbx; pv
0x18002ad4a  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18002ad51  call    cs:__imp_CreateThreadpoolWait
0x18002ad57  mov     rdi, rax
0x18002ad5a  mov     rbp, [rbx+80h]
0x18002ad61  test    rbp, rbp
0x18002ad64  jz      short loc_18002AD82
0x18002ad66  lea     rcx, [rsp+48h+var_28]; this
0x18002ad6b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ad70  mov     rcx, rbp; pwa
0x18002ad73  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x18002ad78  lea     rcx, [rsp+48h+var_28]; this
0x18002ad7d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ad82  mov     [rbx+80h], rdi
0x18002ad89  test    rdi, rdi
0x18002ad8c  jnz     short loc_18002ADBD
0x18002ad8e  mov     rcx, [rsp+48h]; this
0x18002ad93  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ad9a  mov     edx, 1176h; void *
0x18002ad9f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ada4  mov     edi, eax
0x18002ada6  mov     rcx, rbx; this
0x18002ada9  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x18002adae  nop
0x18002adaf  lea     rcx, [rsp+48h+arg_8]
0x18002adb4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002adb9  mov     eax, edi
0x18002adbb  jmp     short loc_18002AE05
0x18002adbd  mov     rdi, [rsi]
0x18002adc0  test    rdi, rdi
0x18002adc3  jz      short loc_18002ADE1
0x18002adc5  lea     rcx, [rsp+48h+var_28]; this
0x18002adca  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002adcf  mov     rcx, rdi; this
0x18002add2  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x18002add7  lea     rcx, [rsp+48h+var_28]; this
0x18002addc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ade1  mov     [rsi], rbx
0x18002ade4  xor     r8d, r8d; pftTimeout
0x18002ade7  mov     rdx, [rbx+78h]; h
0x18002adeb  mov     rcx, [rbx+80h]; pwa
0x18002adf2  call    cs:__imp_SetThreadpoolWait
0x18002adf8  nop
0x18002adf9  lea     rcx, [rsp+48h+arg_8]
0x18002adfe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002ae03  xor     eax, eax
0x18002ae05  mov     rbx, [rsp+48h+arg_0]
0x18002ae0a  add     rsp, 30h
0x18002ae0e  pop     rdi
0x18002ae0f  pop     rsi
0x18002ae10  pop     rbp
0x18002ae11  retn
0x18002ae12  mov     rcx, [rsp+48h]; this
0x18002ae17  mov     edx, 116Ch; void *
0x18002ae1c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
