# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x180007594`
- end: `0x1800077e9`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(wil::details::event_watcher_state **, void *, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800042fc`

## callees

- `0x180002d78`
- `0x180005144`
- `0x1800056e4`
- `0x180006e80`
- `0x180006ea0`
- `0x1800071e4`
- `0x180007594`
- `0x180010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000770f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000774b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000770f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000774b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007738`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007753`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007753`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007696`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007696`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800076bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007770`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800076bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007770`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800076c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800076c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800076d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800076d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007674`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000771e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000777f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007674`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000771e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000777f`

## string_xrefs

- `0x18000765a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800076f1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800077b7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        wil::details::event_watcher_state **a1,
        void *a2,
        int a3,
        __int64 a4)
{
  void *v6; // rbx
  _QWORD *v8; // rax
  void *v9; // rsi
  void *v10; // rdi
  __int64 v11; // r8
  const char *v12; // r9
  const char *v14; // r9
  PTP_WAIT ThreadpoolWait; // r14
  struct _TP_WAIT *v16; // rbp
  DWORD LastError; // edi
  unsigned int v18; // edi
  __int64 v19; // r8
  const char *v20; // r9
  wil::details::event_watcher_state *v21; // rbp
  DWORD v22; // edi
  __int64 v23; // r8
  const char *v24; // r9
  int v25; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = a2;
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x116C,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)a4);
  v8 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v25 = (int)v8;
  if ( v8 )
  {
    if ( *(_QWORD *)(a4 + 112) )
    {
      v8[14] = v8 + 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 16LL))(*(_QWORD *)(a4 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 24LL))(*(_QWORD *)(a4 + 112));
      *(_QWORD *)(a4 + 112) = 0;
    }
    else
    {
      v8[14] = 0;
    }
    *((_QWORD *)v9 + 15) = v6;
    v6 = 0;
    *((_QWORD *)v9 + 16) = 0;
    *((_DWORD *)v9 + 34) = a3;
    *((_DWORD *)v9 + 35) = 0;
    v10 = 0;
  }
  else
  {
    v9 = 0;
    v10 = v6;
  }
  if ( v9 )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                       v9,
                       0);
    v16 = (struct _TP_WAIT *)*((_QWORD *)v9 + 16);
    if ( v16 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v16, 0, 0);
      WaitForThreadpoolWaitCallbacks(v16, 1);
      CloseThreadpoolWait(v16);
      SetLastError(LastError);
    }
    *((_QWORD *)v9 + 16) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v21 = *a1;
      if ( *a1 )
      {
        v22 = GetLastError();
        wil::details::event_watcher_state::~event_watcher_state(v21);
        operator delete(v21);
        SetLastError(v22);
      }
      *a1 = (wil::details::event_watcher_state *)v9;
      if ( (a3 & 2) == 0 )
        SetThreadpoolWait(*((PTP_WAIT *)v9 + 16), *((HANDLE *)v9 + 15), 0);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
      return 0;
    }
    else
    {
      v18 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x1176,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v14);
      wil::details::event_watcher_state::~event_watcher_state((wil::details::event_watcher_state *)v9);
      operator delete(v9);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
      return v18;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1173,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v25);
    if ( v10 )
    {
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180007594  mov     [rsp+arg_0], rbx
0x180007599  mov     [rsp+arg_10], rbp
0x18000759e  push    rsi
0x18000759f  push    rdi
0x1800075a0  push    r12
0x1800075a2  push    r14
0x1800075a4  push    r15
0x1800075a6  sub     rsp, 30h
0x1800075aa  mov     rdi, r9
0x1800075ad  mov     r12d, r8d
0x1800075b0  mov     rbx, rdx
0x1800075b3  mov     r15, rcx
0x1800075b6  test    rdx, rdx
0x1800075b9  jz      loc_1800077B2
0x1800075bf  mov     [rsp+58h+arg_8], rdx
0x1800075c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800075cb  mov     ecx, 90h; unsigned __int64
0x1800075d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800075d5  mov     rsi, rax
0x1800075d8  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800075dd  test    rax, rax
0x1800075e0  jz      short loc_180007643
0x1800075e2  cmp     qword ptr [rdi+70h], 0
0x1800075e7  jnz     short loc_1800075F3
0x1800075e9  mov     qword ptr [rax+70h], 0
0x1800075f1  jmp     short loc_180007623
0x1800075f3  lea     rdx, [rax+8]
0x1800075f7  mov     [rax+70h], rdx
0x1800075fb  mov     rcx, [rdi+70h]
0x1800075ff  mov     rax, [rcx]
0x180007602  mov     rax, [rax+10h]
0x180007606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000760b  mov     rcx, [rdi+70h]
0x18000760f  mov     rax, [rcx]
0x180007612  mov     rax, [rax+18h]
0x180007616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000761b  mov     qword ptr [rdi+70h], 0
0x180007623  mov     [rsi+78h], rbx
0x180007627  xor     ebx, ebx
0x180007629  mov     [rsi+80h], rbx
0x180007630  mov     [rsi+88h], r12d
0x180007637  xor     eax, eax
0x180007639  mov     [rsi+8Ch], eax
0x18000763f  xor     edi, edi
0x180007641  jmp     short loc_180007648
0x180007643  xor     esi, esi
0x180007645  mov     rdi, rbx
0x180007648  test    rsi, rsi
0x18000764b  jnz     short loc_180007689
0x18000764d  mov     rcx, [rsp+58h]; this
0x180007652  mov     esi, 8007000Eh
0x180007657  mov     r9d, esi; char *
0x18000765a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007661  mov     edx, 1173h; void *
0x180007666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000766b  nop
0x18000766c  test    rdi, rdi
0x18000766f  jz      short loc_180007682
0x180007671  mov     rcx, rbx; hObject
0x180007674  call    cs:__imp_CloseHandle
0x18000767a  test    eax, eax
0x18000767c  jz      loc_1800077C9
0x180007682  mov     eax, esi
0x180007684  jmp     loc_18000778B
0x180007689  xor     r8d, r8d; pcbe
0x18000768c  mov     rdx, rsi; pv
0x18000768f  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180007696  call    cs:__imp_CreateThreadpoolWait
0x18000769c  mov     r14, rax
0x18000769f  mov     rbp, [rsi+80h]
0x1800076a6  test    rbp, rbp
0x1800076a9  jz      short loc_1800076E0
0x1800076ab  call    cs:__imp_GetLastError
0x1800076b1  mov     edi, eax
0x1800076b3  xor     r8d, r8d; pftTimeout
0x1800076b6  xor     edx, edx; h
0x1800076b8  mov     rcx, rbp; pwa
0x1800076bb  call    cs:__imp_SetThreadpoolWait
0x1800076c1  mov     edx, 1; fCancelPendingCallbacks
0x1800076c6  mov     rcx, rbp; pwa
0x1800076c9  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800076cf  mov     rcx, rbp; pwa
0x1800076d2  call    cs:__imp_CloseThreadpoolWait
0x1800076d8  mov     ecx, edi; dwErrCode
0x1800076da  call    cs:__imp_SetLastError
0x1800076e0  mov     [rsi+80h], r14
0x1800076e7  test    r14, r14
0x1800076ea  jnz     short loc_180007730
0x1800076ec  mov     rcx, [rsp+58h]; this
0x1800076f1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800076f8  mov     edx, 1176h; void *
0x1800076fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007702  mov     edi, eax
0x180007704  mov     rcx, rsi; this
0x180007707  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x18000770c  mov     rcx, rsi
0x18000770f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007715  nop
0x180007716  test    rbx, rbx
0x180007719  jz      short loc_18000772C
0x18000771b  mov     rcx, rbx; hObject
0x18000771e  call    cs:__imp_CloseHandle
0x180007724  test    eax, eax
0x180007726  jz      loc_1800077D9
0x18000772c  mov     eax, edi
0x18000772e  jmp     short loc_18000778B
0x180007730  mov     rbp, [r15]
0x180007733  test    rbp, rbp
0x180007736  jz      short loc_180007759
0x180007738  call    cs:__imp_GetLastError
0x18000773e  mov     edi, eax
0x180007740  mov     rcx, rbp; this
0x180007743  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x180007748  mov     rcx, rbp
0x18000774b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007751  mov     ecx, edi; dwErrCode
0x180007753  call    cs:__imp_SetLastError
0x180007759  mov     [r15], rsi
0x18000775c  test    r12b, 2
0x180007760  jnz     short loc_180007777
0x180007762  xor     r8d, r8d; pftTimeout
0x180007765  mov     rdx, [rsi+78h]; h
0x180007769  mov     rcx, [rsi+80h]; pwa
0x180007770  call    cs:__imp_SetThreadpoolWait
0x180007776  nop
0x180007777  test    rbx, rbx
0x18000777a  jz      short loc_180007789
0x18000777c  mov     rcx, rbx; hObject
0x18000777f  call    cs:__imp_CloseHandle
0x180007785  test    eax, eax
0x180007787  jz      short loc_1800077A2
0x180007789  xor     eax, eax
0x18000778b  mov     rbx, [rsp+58h+arg_0]
0x180007790  mov     rbp, [rsp+58h+arg_10]
0x180007795  add     rsp, 30h
0x180007799  pop     r15
0x18000779b  pop     r14
0x18000779d  pop     r12
0x18000779f  pop     rdi
0x1800077a0  pop     rsi
0x1800077a1  retn
0x1800077a2  mov     rcx, [rsp+58h]; this
0x1800077a7  mov     edx, 0A0Bh; void *
0x1800077ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800077b2  mov     rcx, [rsp+58h]; this
0x1800077b7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800077be  mov     edx, 116Ch; void *
0x1800077c3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800077c9  mov     rcx, [rsp+58h]; this
0x1800077ce  mov     edx, 0A0Bh; void *
0x1800077d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800077d9  mov     rcx, [rsp+58h]; this
0x1800077de  mov     edx, 0A0Bh; void *
0x1800077e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
