# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x180024430`
- end: `0x18002467b`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180022fa8`

## callees

- `0x180003310`
- `0x180003b44`
- `0x180007d5c`
- `0x18000b274`
- `0x18000b29c`
- `0x18000ccf0`
- `0x180021c54`
- `0x180024430`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002450d`
- `KERNEL32!CloseHandle` at `0x1800245b9`
- `KERNEL32!CloseHandle` at `0x18002461e`
- `KERNEL32!CloseHandle` at `0x18002450d`
- `KERNEL32!CloseHandle` at `0x1800245b9`
- `KERNEL32!CloseHandle` at `0x18002461e`
- `KERNEL32!SetLastError` at `0x180024573`
- `KERNEL32!SetLastError` at `0x1800245f4`
- `KERNEL32!SetLastError` at `0x180024573`
- `KERNEL32!SetLastError` at `0x1800245f4`
- `KERNEL32!GetLastError` at `0x180024544`
- `KERNEL32!GetLastError` at `0x1800245d7`
- `KERNEL32!GetLastError` at `0x180024544`
- `KERNEL32!GetLastError` at `0x1800245d7`
- `KERNEL32!CloseThreadpoolWait` at `0x18002456b`
- `KERNEL32!CloseThreadpoolWait` at `0x18002456b`
- `KERNEL32!CreateThreadpoolWait` at `0x18002452f`
- `KERNEL32!CreateThreadpoolWait` at `0x18002452f`
- `KERNEL32!SetThreadpoolWait` at `0x180024554`
- `KERNEL32!SetThreadpoolWait` at `0x18002460f`
- `KERNEL32!SetThreadpoolWait` at `0x180024554`
- `KERNEL32!SetThreadpoolWait` at `0x18002460f`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180024562`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x180024562`

## string_xrefs

- `0x1800244f3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002458a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        __int64 a1,
        void *a2,
        unsigned int a3,
        __int64 a4)
{
  void *v5; // rbx
  _QWORD *v6; // rax
  void *v7; // rsi
  void *v8; // rdi
  unsigned int v9; // r8d
  const char *v10; // r9
  const char *v12; // r9
  PTP_WAIT ThreadpoolWait; // r14
  struct _TP_WAIT *v14; // rbp
  DWORD LastError; // edi
  unsigned int v16; // edi
  unsigned int v17; // r8d
  const char *v18; // r9
  wil::details::event_watcher_state *v19; // rbp
  DWORD v20; // edi
  unsigned int v21; // r8d
  const char *v22; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = a2;
  if ( !a2 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0x116C, a3, (const char *)a4);
  v6 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    if ( *(_QWORD *)(a4 + 112) )
    {
      v6[14] = v6 + 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 16LL))(*(_QWORD *)(a4 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 24LL))(*(_QWORD *)(a4 + 112));
      *(_QWORD *)(a4 + 112) = 0;
    }
    else
    {
      v6[14] = 0;
    }
    *((_QWORD *)v7 + 15) = v5;
    v5 = 0;
    *((_QWORD *)v7 + 16) = 0;
    *((_QWORD *)v7 + 17) = 0;
    v8 = 0;
  }
  else
  {
    v7 = 0;
    v8 = v5;
  }
  if ( v7 )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                       v7,
                       0);
    v14 = (struct _TP_WAIT *)*((_QWORD *)v7 + 16);
    if ( v14 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v14, 0, 0);
      WaitForThreadpoolWaitCallbacks(v14, 1);
      CloseThreadpoolWait(v14);
      SetLastError(LastError);
    }
    *((_QWORD *)v7 + 16) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v19 = g_FormChangedEventWatcher;
      if ( g_FormChangedEventWatcher )
      {
        v20 = GetLastError();
        wil::details::event_watcher_state::~event_watcher_state(v19);
        operator delete(v19);
        SetLastError(v20);
      }
      g_FormChangedEventWatcher = (wil::details::event_watcher_state *)v7;
      SetThreadpoolWait(*((PTP_WAIT *)v7 + 16), *((HANDLE *)v7 + 15), 0);
      if ( v5 && !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
      return 0;
    }
    else
    {
      v16 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x1176,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v12);
      wil::details::event_watcher_state::~event_watcher_state((wil::details::event_watcher_state *)v7);
      operator delete(v7);
      if ( v5 && !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1173,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      -2);
    if ( v8 )
    {
      if ( !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v9, v10);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180024430  mov     rax, rsp
0x180024433  mov     [rax+8], rcx
0x180024437  push    rbp
0x180024438  push    rsi
0x180024439  push    rdi
0x18002443a  push    r12
0x18002443c  push    r14
0x18002443e  sub     rsp, 30h
0x180024442  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18002444a  mov     [rax+20h], rbx
0x18002444e  mov     rdi, r9
0x180024451  mov     rbx, rdx
0x180024454  test    rdx, rdx
0x180024457  jz      loc_18002464B
0x18002445d  mov     [rax+8], rdx
0x180024461  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024468  mov     r12d, 90h
0x18002446e  mov     ecx, r12d; unsigned __int64
0x180024471  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024476  mov     rsi, rax
0x180024479  mov     [rsp+58h+arg_8], rax
0x18002447e  test    rax, rax
0x180024481  jz      short loc_1800244DC
0x180024483  cmp     qword ptr [rdi+70h], 0
0x180024488  jnz     short loc_180024494
0x18002448a  mov     qword ptr [rax+70h], 0
0x180024492  jmp     short loc_1800244C4
0x180024494  lea     rdx, [rax+8]
0x180024498  mov     [rax+70h], rdx
0x18002449c  mov     rcx, [rdi+70h]
0x1800244a0  mov     rax, [rcx]
0x1800244a3  mov     rax, [rax+10h]
0x1800244a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244ac  mov     rcx, [rdi+70h]
0x1800244b0  mov     rax, [rcx]
0x1800244b3  mov     rax, [rax+18h]
0x1800244b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244bc  mov     qword ptr [rdi+70h], 0
0x1800244c4  mov     [rsi+78h], rbx
0x1800244c8  xor     ebx, ebx
0x1800244ca  mov     [rsi+80h], rbx
0x1800244d1  mov     [rsi+88h], rbx
0x1800244d8  xor     edi, edi
0x1800244da  jmp     short loc_1800244E1
0x1800244dc  xor     esi, esi
0x1800244de  mov     rdi, rbx
0x1800244e1  test    rsi, rsi
0x1800244e4  jnz     short loc_180024522
0x1800244e6  mov     rcx, [rsp+58h]; this
0x1800244eb  mov     esi, 8007000Eh
0x1800244f0  mov     r9d, esi; char *
0x1800244f3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800244fa  mov     edx, 1173h; void *
0x1800244ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024504  nop
0x180024505  test    rdi, rdi
0x180024508  jz      short loc_18002451B
0x18002450a  mov     rcx, rbx; hObject
0x18002450d  call    cs:__imp_CloseHandle
0x180024513  test    eax, eax
0x180024515  jz      loc_18002465B
0x18002451b  mov     eax, esi
0x18002451d  jmp     loc_18002462A
0x180024522  xor     r8d, r8d; pcbe
0x180024525  mov     rdx, rsi; pv
0x180024528  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18002452f  call    cs:__imp_CreateThreadpoolWait
0x180024535  mov     r14, rax
0x180024538  mov     rbp, [rsi+80h]
0x18002453f  test    rbp, rbp
0x180024542  jz      short loc_180024579
0x180024544  call    cs:__imp_GetLastError
0x18002454a  mov     edi, eax
0x18002454c  xor     r8d, r8d; pftTimeout
0x18002454f  xor     edx, edx; h
0x180024551  mov     rcx, rbp; pwa
0x180024554  call    cs:__imp_SetThreadpoolWait
0x18002455a  mov     edx, 1; fCancelPendingCallbacks
0x18002455f  mov     rcx, rbp; pwa
0x180024562  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180024568  mov     rcx, rbp; pwa
0x18002456b  call    cs:__imp_CloseThreadpoolWait
0x180024571  mov     ecx, edi; dwErrCode
0x180024573  call    cs:__imp_SetLastError
0x180024579  mov     [rsi+80h], r14
0x180024580  test    r14, r14
0x180024583  jnz     short loc_1800245CB
0x180024585  mov     rcx, [rsp+58h]; this
0x18002458a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024591  mov     edx, 1176h; void *
0x180024596  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002459b  mov     edi, eax
0x18002459d  mov     rcx, rsi; this
0x1800245a0  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x1800245a5  mov     rdx, r12
0x1800245a8  mov     rcx, rsi; Block
0x1800245ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800245b0  nop
0x1800245b1  test    rbx, rbx
0x1800245b4  jz      short loc_1800245C7
0x1800245b6  mov     rcx, rbx; hObject
0x1800245b9  call    cs:__imp_CloseHandle
0x1800245bf  test    eax, eax
0x1800245c1  jz      loc_18002466B
0x1800245c7  mov     eax, edi
0x1800245c9  jmp     short loc_18002462A
0x1800245cb  mov     rbp, cs:?g_FormChangedEventWatcher@@3V?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> g_FormChangedEventWatcher
0x1800245d2  test    rbp, rbp
0x1800245d5  jz      short loc_1800245FA
0x1800245d7  call    cs:__imp_GetLastError
0x1800245dd  mov     edi, eax
0x1800245df  mov     rcx, rbp; this
0x1800245e2  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x1800245e7  mov     rdx, r12
0x1800245ea  mov     rcx, rbp; Block
0x1800245ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800245f2  mov     ecx, edi; dwErrCode
0x1800245f4  call    cs:__imp_SetLastError
0x1800245fa  mov     cs:?g_FormChangedEventWatcher@@3V?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rsi; wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> g_FormChangedEventWatcher
0x180024601  xor     r8d, r8d; pftTimeout
0x180024604  mov     rdx, [rsi+78h]; h
0x180024608  mov     rcx, [rsi+80h]; pwa
0x18002460f  call    cs:__imp_SetThreadpoolWait
0x180024615  nop
0x180024616  test    rbx, rbx
0x180024619  jz      short loc_180024628
0x18002461b  mov     rcx, rbx; hObject
0x18002461e  call    cs:__imp_CloseHandle
0x180024624  test    eax, eax
0x180024626  jz      short loc_18002463B
0x180024628  xor     eax, eax
0x18002462a  mov     rbx, [rsp+58h+arg_18]
0x18002462f  add     rsp, 30h
0x180024633  pop     r14
0x180024635  pop     r12
0x180024637  pop     rdi
0x180024638  pop     rsi
0x180024639  pop     rbp
0x18002463a  retn
0x18002463b  mov     rcx, [rsp+58h]; this
0x180024640  mov     edx, 0A0Bh; void *
0x180024645  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002464b  mov     rcx, [rsp+58h]; this
0x180024650  mov     edx, 116Ch; void *
0x180024655  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002465b  mov     rcx, [rsp+58h]; this
0x180024660  mov     edx, 0A0Bh; void *
0x180024665  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002466b  mov     rcx, [rsp+58h]; this
0x180024670  mov     edx, 0A0Bh; void *
0x180024675  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
