# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x18001fdd0`
- end: `0x18001ff28`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(__int64, wil::details *, __int64, const char *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001e2e8`

## callees

- `0x1800029b0`
- `0x1800050ac`
- `0x180005340`
- `0x180005468`
- `0x180005bac`
- `0x1800075c4`
- `0x1800075e4`
- `0x18001e440`
- `0x18001ea88`
- `0x18001ed9c`
- `0x18001fdd0`
- `0x180020028`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001fe4b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001fe4b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fec6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001fec6`

## string_xrefs

- `0x18001fe8d`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001fedf`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001ff16`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_take_hevent_ownership(
        __int64 a1,
        wil::details *a2,
        __int64 a3,
        const char *a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v10; // r9
  struct _TP_WAIT *v11; // rbp
  PTP_WAIT v12; // rdi
  unsigned int LastError; // edi
  unsigned int v14; // edx
  void *v15; // rdx
  void *v16; // rdx
  int v18[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  wil::details *v20; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0x116C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v20 = a2;
  v7 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    wistd::function<void (void)>::function<void (void)>(v7, a4);
    v8[15] = a2;
    v20 = 0;
    v8[16] = 0;
    v8[17] = 0;
    ThreadpoolWait = CreateThreadpoolWait(
                       wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::wait_callback,
                       v8,
                       0);
    v11 = (struct _TP_WAIT *)v8[16];
    v12 = ThreadpoolWait;
    if ( v11 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v18);
      wil::details::DestroyThreadPoolWait<0>::Destroy(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
    }
    v8[16] = v12;
    if ( v12 )
    {
      wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
        a1,
        v8);
      SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 128LL), *(HANDLE *)(*(_QWORD *)a1 + 120LL), 0);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v20,
        v16);
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1176,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
                  v10);
    wil::details::event_watcher_state::`scalar deleting destructor'((wil::details::event_watcher_state *)v8, v14);
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1173,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)0x8007000ELL,
      v18[0]);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v20,
    v15);
  return LastError;
}

```

## disassembly

```asm
0x18001fdd0  mov     [rsp+arg_0], rbx
0x18001fdd5  push    rbp
0x18001fdd6  push    rsi
0x18001fdd7  push    rdi
0x18001fdd8  sub     rsp, 30h
0x18001fddc  mov     rbp, r9
0x18001fddf  mov     rdi, rdx
0x18001fde2  mov     rsi, rcx
0x18001fde5  test    rdx, rdx
0x18001fde8  jz      loc_18001FF11
0x18001fdee  mov     [rsp+48h+arg_8], rdx
0x18001fdf3  mov     ecx, 90h; unsigned __int64
0x18001fdf8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fdff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fe04  mov     rbx, rax
0x18001fe07  test    rax, rax
0x18001fe0a  jz      loc_18001FEDA
0x18001fe10  mov     rdx, rbp
0x18001fe13  mov     rcx, rax
0x18001fe16  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x18001fe1b  xor     r8d, r8d; pcbe
0x18001fe1e  mov     [rbx+78h], rdi
0x18001fe22  mov     rdx, rbx; pv
0x18001fe25  mov     [rsp+48h+arg_8], 0
0x18001fe2e  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18001fe35  mov     qword ptr [rbx+80h], 0
0x18001fe40  mov     qword ptr [rbx+88h], 0
0x18001fe4b  call    cs:__imp_CreateThreadpoolWait
0x18001fe51  mov     rbp, [rbx+80h]
0x18001fe58  mov     rdi, rax
0x18001fe5b  test    rbp, rbp
0x18001fe5e  jz      short loc_18001FE7C
0x18001fe60  lea     rcx, [rsp+48h+var_28]; this
0x18001fe65  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001fe6a  mov     rcx, rbp; pwa
0x18001fe6d  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x18001fe72  lea     rcx, [rsp+48h+var_28]; this
0x18001fe77  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001fe7c  mov     [rbx+80h], rdi
0x18001fe83  test    rdi, rdi
0x18001fe86  jnz     short loc_18001FEAA
0x18001fe88  mov     rcx, [rsp+48h]; this
0x18001fe8d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fe94  mov     edx, 1176h; void *
0x18001fe99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fe9e  mov     rcx, rbx; this
0x18001fea1  mov     edi, eax
0x18001fea3  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x18001fea8  jmp     short loc_18001FEF8
0x18001feaa  mov     rdx, rbx
0x18001fead  mov     rcx, rsi
0x18001feb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x18001feb5  mov     rcx, [rsi]
0x18001feb8  xor     r8d, r8d; pftTimeout
0x18001febb  mov     rdx, [rcx+78h]; h
0x18001febf  mov     rcx, [rcx+80h]; pwa
0x18001fec6  call    cs:__imp_SetThreadpoolWait
0x18001fecc  lea     rcx, [rsp+48h+arg_8]
0x18001fed1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fed6  xor     eax, eax
0x18001fed8  jmp     short loc_18001FF04
0x18001feda  mov     rcx, [rsp+48h]; this
0x18001fedf  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fee6  mov     edi, 8007000Eh
0x18001feeb  mov     edx, 1173h; void *
0x18001fef0  mov     r9d, edi; char *
0x18001fef3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fef8  lea     rcx, [rsp+48h+arg_8]
0x18001fefd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ff02  mov     eax, edi
0x18001ff04  mov     rbx, [rsp+48h+arg_0]
0x18001ff09  add     rsp, 30h
0x18001ff0d  pop     rdi
0x18001ff0e  pop     rsi
0x18001ff0f  pop     rbp
0x18001ff10  retn
0x18001ff11  mov     rcx, [rsp+48h]; this
0x18001ff16  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ff1d  mov     edx, 116Ch; void *
0x18001ff22  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
