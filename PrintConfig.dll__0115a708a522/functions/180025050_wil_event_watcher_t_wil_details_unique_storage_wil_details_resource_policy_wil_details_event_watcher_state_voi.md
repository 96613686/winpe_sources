# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x180025050`
- end: `0x1800252e4`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(__int64, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180023af4`

## callees

- `0x180003430`
- `0x180003c64`
- `0x180007dcc`
- `0x18000b444`
- `0x18000b470`
- `0x18000ce74`
- `0x1800226d8`
- `0x180025050`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002512d`
- `KERNEL32!CloseHandle` at `0x180025203`
- `KERNEL32!CloseHandle` at `0x180025280`
- `KERNEL32!CloseHandle` at `0x18002512d`
- `KERNEL32!CloseHandle` at `0x180025203`
- `KERNEL32!CloseHandle` at `0x180025280`
- `KERNEL32!SetLastError` at `0x1800251b7`
- `KERNEL32!SetLastError` at `0x18002524a`
- `KERNEL32!SetLastError` at `0x1800251b7`
- `KERNEL32!SetLastError` at `0x18002524a`
- `KERNEL32!GetLastError` at `0x180025170`
- `KERNEL32!GetLastError` at `0x180025227`
- `KERNEL32!GetLastError` at `0x180025170`
- `KERNEL32!GetLastError` at `0x180025227`
- `KERNEL32!CloseThreadpoolWait` at `0x1800251a9`
- `KERNEL32!CloseThreadpoolWait` at `0x1800251a9`
- `KERNEL32!CreateThreadpoolWait` at `0x180025155`
- `KERNEL32!CreateThreadpoolWait` at `0x180025155`
- `KERNEL32!SetThreadpoolWait` at `0x180025186`
- `KERNEL32!SetThreadpoolWait` at `0x18002526b`
- `KERNEL32!SetThreadpoolWait` at `0x180025186`
- `KERNEL32!SetThreadpoolWait` at `0x18002526b`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x18002519a`
- `KERNEL32!WaitForThreadpoolWaitCallbacks` at `0x18002519a`

## string_xrefs

- `0x180025113`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800251d4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4)
{
  void *v5; // rbx
  _QWORD *v6; // rax
  void *v7; // rsi
  void *v8; // rdi
  __int64 v9; // r8
  const char *v10; // r9
  const char *v12; // r9
  PTP_WAIT ThreadpoolWait; // r14
  struct _TP_WAIT *v14; // rbp
  DWORD LastError; // edi
  unsigned int v16; // edi
  __int64 v17; // r8
  const char *v18; // r9
  wil::details::event_watcher_state *v19; // rbp
  DWORD v20; // edi
  __int64 v21; // r8
  const char *v22; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = a2;
  if ( !a2 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, 4460, a3, (const char *)a4);
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
                       (PTP_WAIT_CALLBACK)wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
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
              (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
      (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL);
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
0x180025050  mov     rax, rsp
0x180025053  mov     [rax+8], rcx
0x180025057  push    rbp
0x180025058  push    rsi
0x180025059  push    rdi
0x18002505a  push    r12
0x18002505c  push    r14
0x18002505e  sub     rsp, 30h
0x180025062  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18002506a  mov     [rax+20h], rbx
0x18002506e  mov     rdi, r9
0x180025071  mov     rbx, rdx
0x180025074  test    rdx, rdx
0x180025077  jz      loc_1800252B4
0x18002507d  mov     [rax+8], rdx
0x180025081  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025088  mov     r12d, 90h
0x18002508e  mov     ecx, r12d; unsigned __int64
0x180025091  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025096  mov     rsi, rax
0x180025099  mov     [rsp+58h+arg_8], rax
0x18002509e  test    rax, rax
0x1800250a1  jz      short loc_1800250FC
0x1800250a3  cmp     qword ptr [rdi+70h], 0
0x1800250a8  jnz     short loc_1800250B4
0x1800250aa  mov     qword ptr [rax+70h], 0
0x1800250b2  jmp     short loc_1800250E4
0x1800250b4  lea     rdx, [rax+8]
0x1800250b8  mov     [rax+70h], rdx
0x1800250bc  mov     rcx, [rdi+70h]
0x1800250c0  mov     rax, [rcx]
0x1800250c3  mov     rax, [rax+10h]
0x1800250c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250cc  mov     rcx, [rdi+70h]
0x1800250d0  mov     rax, [rcx]
0x1800250d3  mov     rax, [rax+18h]
0x1800250d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250dc  mov     qword ptr [rdi+70h], 0
0x1800250e4  mov     [rsi+78h], rbx
0x1800250e8  xor     ebx, ebx
0x1800250ea  mov     [rsi+80h], rbx
0x1800250f1  mov     [rsi+88h], rbx
0x1800250f8  xor     edi, edi
0x1800250fa  jmp     short loc_180025101
0x1800250fc  xor     esi, esi
0x1800250fe  mov     rdi, rbx
0x180025101  test    rsi, rsi
0x180025104  jnz     short loc_180025148
0x180025106  mov     rcx, [rsp+58h]; this
0x18002510b  mov     esi, 8007000Eh
0x180025110  mov     r9d, esi; char *
0x180025113  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002511a  mov     edx, 1173h; void *
0x18002511f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025124  nop
0x180025125  test    rdi, rdi
0x180025128  jz      short loc_180025141
0x18002512a  mov     rcx, rbx; hObject
0x18002512d  call    cs:__imp_CloseHandle
0x180025134  nop     dword ptr [rax+rax+00h]
0x180025139  test    eax, eax
0x18002513b  jz      loc_1800252C4
0x180025141  mov     eax, esi
0x180025143  jmp     loc_180025292
0x180025148  xor     r8d, r8d; pcbe
0x18002514b  mov     rdx, rsi; pv
0x18002514e  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180025155  call    cs:__imp_CreateThreadpoolWait
0x18002515c  nop     dword ptr [rax+rax+00h]
0x180025161  mov     r14, rax
0x180025164  mov     rbp, [rsi+80h]
0x18002516b  test    rbp, rbp
0x18002516e  jz      short loc_1800251C3
0x180025170  call    cs:__imp_GetLastError
0x180025177  nop     dword ptr [rax+rax+00h]
0x18002517c  mov     edi, eax
0x18002517e  xor     r8d, r8d; pftTimeout
0x180025181  xor     edx, edx; h
0x180025183  mov     rcx, rbp; pwa
0x180025186  call    cs:__imp_SetThreadpoolWait
0x18002518d  nop     dword ptr [rax+rax+00h]
0x180025192  mov     edx, 1; fCancelPendingCallbacks
0x180025197  mov     rcx, rbp; pwa
0x18002519a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800251a1  nop     dword ptr [rax+rax+00h]
0x1800251a6  mov     rcx, rbp; pwa
0x1800251a9  call    cs:__imp_CloseThreadpoolWait
0x1800251b0  nop     dword ptr [rax+rax+00h]
0x1800251b5  mov     ecx, edi; dwErrCode
0x1800251b7  call    cs:__imp_SetLastError
0x1800251be  nop     dword ptr [rax+rax+00h]
0x1800251c3  mov     [rsi+80h], r14
0x1800251ca  test    r14, r14
0x1800251cd  jnz     short loc_18002521B
0x1800251cf  mov     rcx, [rsp+58h]; this
0x1800251d4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800251db  mov     edx, 1176h; void *
0x1800251e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800251e5  mov     edi, eax
0x1800251e7  mov     rcx, rsi; this
0x1800251ea  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x1800251ef  mov     rdx, r12
0x1800251f2  mov     rcx, rsi; Block
0x1800251f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800251fa  nop
0x1800251fb  test    rbx, rbx
0x1800251fe  jz      short loc_180025217
0x180025200  mov     rcx, rbx; hObject
0x180025203  call    cs:__imp_CloseHandle
0x18002520a  nop     dword ptr [rax+rax+00h]
0x18002520f  test    eax, eax
0x180025211  jz      loc_1800252D4
0x180025217  mov     eax, edi
0x180025219  jmp     short loc_180025292
0x18002521b  mov     rbp, cs:?g_FormChangedEventWatcher@@3V?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> g_FormChangedEventWatcher
0x180025222  test    rbp, rbp
0x180025225  jz      short loc_180025256
0x180025227  call    cs:__imp_GetLastError
0x18002522e  nop     dword ptr [rax+rax+00h]
0x180025233  mov     edi, eax
0x180025235  mov     rcx, rbp; this
0x180025238  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x18002523d  mov     rdx, r12
0x180025240  mov     rcx, rbp; Block
0x180025243  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025248  mov     ecx, edi; dwErrCode
0x18002524a  call    cs:__imp_SetLastError
0x180025251  nop     dword ptr [rax+rax+00h]
0x180025256  mov     cs:?g_FormChangedEventWatcher@@3V?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rsi; wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>> g_FormChangedEventWatcher
0x18002525d  xor     r8d, r8d; pftTimeout
0x180025260  mov     rdx, [rsi+78h]; h
0x180025264  mov     rcx, [rsi+80h]; pwa
0x18002526b  call    cs:__imp_SetThreadpoolWait
0x180025272  nop     dword ptr [rax+rax+00h]
0x180025277  nop
0x180025278  test    rbx, rbx
0x18002527b  jz      short loc_180025290
0x18002527d  mov     rcx, rbx; hObject
0x180025280  call    cs:__imp_CloseHandle
0x180025287  nop     dword ptr [rax+rax+00h]
0x18002528c  test    eax, eax
0x18002528e  jz      short loc_1800252A4
0x180025290  xor     eax, eax
0x180025292  mov     rbx, [rsp+58h+arg_18]
0x180025297  add     rsp, 30h
0x18002529b  pop     r14
0x18002529d  pop     r12
0x18002529f  pop     rdi
0x1800252a0  pop     rsi
0x1800252a1  pop     rbp
0x1800252a2  retn
0x1800252a4  mov     rcx, [rsp+58h]; this
0x1800252a9  mov     edx, 0A0Bh; void *
0x1800252ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800252b4  mov     rcx, [rsp+58h]; this
0x1800252b9  mov     edx, 116Ch; void *
0x1800252be  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800252c4  mov     rcx, [rsp+58h]; this
0x1800252c9  mov     edx, 0A0Bh; void *
0x1800252ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800252d4  mov     rcx, [rsp+58h]; this
0x1800252d9  mov     edx, 0A0Bh; void *
0x1800252de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
