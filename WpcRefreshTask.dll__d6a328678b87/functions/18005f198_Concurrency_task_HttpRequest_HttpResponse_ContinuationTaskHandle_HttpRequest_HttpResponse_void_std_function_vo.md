# Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18005f198`
- end: `0x18005f3e6`
- name: `?_Continue@?$_ContinuationTaskHandle@VHttpResponse@HttpRequest@@XV?$function@$$A6AXV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@4@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@VHttpResponse@HttpRequest@@@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800600d0`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x18001c070`
- `0x18005f198`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005f32a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005f32a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005f391`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005f391`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005f301`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005f301`

## pseudocode

```c
__int64 __fastcall Concurrency::task<HttpRequest::HttpResponse>::_ContinuationTaskHandle<HttpRequest::HttpResponse,void,std::function<void (Concurrency::task<HttpRequest::HttpResponse>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        _QWORD *a1)
{
  __int64 v2; // rax
  _BYTE *v3; // r14
  volatile signed __int32 *v4; // r15
  Concurrency::details::_Task_impl_base *v5; // r12
  _BYTE *v6; // rcx
  char *v7; // rbx
  _BYTE *v8; // rcx
  _BYTE *v9; // rdx
  _BYTE *v10; // rdx
  Concurrency::details::_TaskEventLogger *v11; // rsi
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rdx
  _BYTE *v15; // [rsp+20h] [rbp-E0h] BYREF
  volatile signed __int32 *v16; // [rsp+28h] [rbp-D8h]
  char *v17; // [rsp+30h] [rbp-D0h]
  Concurrency::details::_TaskEventLogger *v18; // [rsp+38h] [rbp-C8h]
  __int128 v19; // [rsp+40h] [rbp-C0h]
  _BYTE v20[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v21; // [rsp+88h] [rbp-78h]
  char v22; // [rsp+90h] [rbp-70h] BYREF
  char *v23; // [rsp+C8h] [rbp-38h]
  _BYTE v24[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE *v25; // [rsp+108h] [rbp+8h]

  v2 = a1[8];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v3 = (_BYTE *)a1[7];
  v4 = (volatile signed __int32 *)a1[8];
  *(_QWORD *)&v19 = v3;
  *((_QWORD *)&v19 + 1) = v4;
  v5 = (Concurrency::details::_Task_impl_base *)a1[5];
  v15 = v20;
  v21 = 0;
  v6 = (_BYTE *)a1[16];
  if ( v6 )
  {
    v6 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v6)(v6, v20);
    v21 = v6;
  }
  v15 = v20;
  v17 = v24;
  v25 = 0;
  if ( v6 )
    v25 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v6)(v6, v24);
  v23 = 0;
  v7 = (char *)operator new(0x48u);
  v17 = v7;
  *(_QWORD *)v7 = &std::_Func_impl_no_alloc<_lambda_e58b3ea666e15b4ce2a73104f06f1120_,unsigned char,Concurrency::task<HttpRequest::HttpResponse>>::`vftable';
  v18 = (Concurrency::details::_TaskEventLogger *)(v7 + 8);
  *((_QWORD *)v7 + 8) = 0;
  v8 = v25;
  if ( v25 )
  {
    *((_QWORD *)v7 + 8) = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v25)(v25, (_QWORD *)v7 + 1);
    v8 = v25;
  }
  v23 = v7;
  if ( v8 )
  {
    v9 = v24;
    LOBYTE(v9) = v8 != v24;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v8 + 32LL))(v8, v9);
  }
  if ( v21 )
  {
    v10 = v20;
    LOBYTE(v10) = v21 != v20;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v21 + 32LL))(v21, v10);
    v21 = 0;
  }
  v11 = (Concurrency::details::_TaskEventLogger *)(a1[5] + 352LL);
  v18 = v11;
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v11);
  v15 = v3;
  v16 = v4;
  v19 = 0;
  v17 = (char *)&v15;
  if ( !v7 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(char *, _BYTE **))(*(_QWORD *)v7 + 16LL))(v7, &v15);
  v12 = v16;
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v11);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v5);
  LOBYTE(v13) = v7 != &v22;
  return (*(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 32LL))(v7, v13);
}

```

## disassembly

```asm
0x18005f198  mov     [rsp-8+arg_8], rbx
0x18005f19d  mov     [rsp-8+arg_10], rsi
0x18005f1a2  push    rbp
0x18005f1a3  push    rdi
0x18005f1a4  push    r12
0x18005f1a6  push    r14
0x18005f1a8  push    r15
0x18005f1aa  lea     rbp, [rsp-20h]
0x18005f1af  sub     rsp, 120h
0x18005f1b6  mov     rax, cs:__security_cookie
0x18005f1bd  xor     rax, rsp
0x18005f1c0  mov     [rbp+40h+var_30], rax
0x18005f1c4  mov     rdi, rcx
0x18005f1c7  mov     rax, [rcx+40h]
0x18005f1cb  test    rax, rax
0x18005f1ce  jz      short loc_18005F1D4
0x18005f1d0  lock inc dword ptr [rax+8]
0x18005f1d4  mov     r14, [rcx+38h]
0x18005f1d8  mov     r15, [rcx+40h]
0x18005f1dc  mov     qword ptr [rsp+140h+var_100], r14
0x18005f1e1  mov     qword ptr [rsp+140h+var_100+8], r15
0x18005f1e6  mov     r12, [rcx+28h]
0x18005f1ea  lea     rax, [rsp+140h+var_F0]
0x18005f1ef  mov     [rsp+140h+var_120], rax
0x18005f1f4  mov     [rbp+40h+var_B8], 0
0x18005f1fc  mov     rcx, [rcx+80h]
0x18005f203  test    rcx, rcx
0x18005f206  jz      short loc_18005F21F
0x18005f208  mov     rax, [rcx]
0x18005f20b  lea     rdx, [rsp+140h+var_F0]
0x18005f210  mov     rax, [rax]
0x18005f213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f218  mov     rcx, rax
0x18005f21b  mov     [rbp+40h+var_B8], rax
0x18005f21f  lea     rax, [rsp+140h+var_F0]
0x18005f224  mov     [rsp+140h+var_120], rax
0x18005f229  lea     rax, [rbp+40h+var_70]
0x18005f22d  mov     [rsp+140h+var_110], rax
0x18005f232  mov     [rbp+40h+var_38], 0
0x18005f23a  test    rcx, rcx
0x18005f23d  jz      short loc_18005F252
0x18005f23f  mov     rax, [rcx]
0x18005f242  lea     rdx, [rbp+40h+var_70]
0x18005f246  mov     rax, [rax]
0x18005f249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f24e  mov     [rbp+40h+var_38], rax
0x18005f252  mov     [rbp+40h+var_78], 0
0x18005f25a  mov     ecx, 48h ; 'H'; Size
0x18005f25f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005f264  mov     rbx, rax
0x18005f267  mov     [rsp+140h+var_110], rax
0x18005f26c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e58b3ea666e15b4ce2a73104f06f1120_@@EV?$task@VHttpResponse@HttpRequest@@@Concurrency@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e58b3ea666e15b4ce2a73104f06f1120_,uchar,Concurrency::task<HttpRequest::HttpResponse>>::`vftable'
0x18005f273  mov     [rbx], rax
0x18005f276  lea     rsi, [rbx+8]
0x18005f27a  mov     [rsp+140h+var_108], rsi
0x18005f27f  mov     qword ptr [rsi+38h], 0
0x18005f287  mov     rcx, [rbp+40h+var_38]
0x18005f28b  test    rcx, rcx
0x18005f28e  jz      short loc_18005F2A6
0x18005f290  mov     rax, [rcx]
0x18005f293  mov     rdx, rsi
0x18005f296  mov     rax, [rax]
0x18005f299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f29e  mov     [rsi+38h], rax
0x18005f2a2  mov     rcx, [rbp+40h+var_38]
0x18005f2a6  mov     [rbp+40h+var_78], rbx
0x18005f2aa  test    rcx, rcx
0x18005f2ad  jz      short loc_18005F2C6
0x18005f2af  mov     rax, [rcx]
0x18005f2b2  lea     rdx, [rbp+40h+var_70]
0x18005f2b6  cmp     rcx, rdx
0x18005f2b9  setnz   dl
0x18005f2bc  mov     rax, [rax+20h]
0x18005f2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2c5  nop
0x18005f2c6  mov     rcx, [rbp+40h+var_B8]
0x18005f2ca  test    rcx, rcx
0x18005f2cd  jz      short loc_18005F2EE
0x18005f2cf  mov     rax, [rcx]
0x18005f2d2  lea     rdx, [rsp+140h+var_F0]
0x18005f2d7  cmp     rcx, rdx
0x18005f2da  setnz   dl
0x18005f2dd  mov     rax, [rax+20h]
0x18005f2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2e6  mov     [rbp+40h+var_B8], 0
0x18005f2ee  mov     rsi, [rdi+28h]
0x18005f2f2  add     rsi, 160h
0x18005f2f9  mov     [rsp+140h+var_108], rsi
0x18005f2fe  mov     rcx, rsi
0x18005f301  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18005f307  nop
0x18005f308  mov     [rsp+140h+var_120], r14
0x18005f30d  mov     [rsp+140h+var_118], r15
0x18005f312  xorps   xmm0, xmm0
0x18005f315  movdqu  [rsp+140h+var_100], xmm0
0x18005f31b  lea     rax, [rsp+140h+var_120]
0x18005f320  mov     [rsp+140h+var_110], rax
0x18005f325  test    rbx, rbx
0x18005f328  jnz     short loc_18005F331
0x18005f32a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18005f330  int     3; Trap to Debugger
0x18005f331  mov     rax, [rbx]
0x18005f334  lea     rdx, [rsp+140h+var_120]
0x18005f339  mov     rcx, rbx
0x18005f33c  mov     rax, [rax+10h]
0x18005f340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f345  mov     r14b, al
0x18005f348  mov     rdi, [rsp+140h+var_118]
0x18005f34d  test    rdi, rdi
0x18005f350  jz      short loc_18005F38E
0x18005f352  or      r15d, 0FFFFFFFFh
0x18005f356  mov     ecx, r15d
0x18005f359  lock xadd [rdi+8], ecx
0x18005f35e  add     ecx, r15d
0x18005f361  jnz     short loc_18005F38E
0x18005f363  mov     rdx, [rdi]
0x18005f366  mov     rcx, rdi
0x18005f369  mov     rax, [rdx]
0x18005f36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f371  mov     eax, r15d
0x18005f374  lock xadd [rdi+0Ch], eax
0x18005f379  add     eax, r15d
0x18005f37c  jnz     short loc_18005F38E
0x18005f37e  mov     rax, [rdi]
0x18005f381  mov     rcx, rdi
0x18005f384  mov     rax, [rax+8]
0x18005f388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f38d  nop
0x18005f38e  mov     rcx, rsi
0x18005f391  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18005f397  nop
0x18005f398  mov     dl, r14b
0x18005f39b  mov     rcx, r12; this
0x18005f39e  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18005f3a3  nop
0x18005f3a4  mov     rax, [rbx]
0x18005f3a7  lea     rcx, [rbp+40h+var_B0]
0x18005f3ab  cmp     rbx, rcx
0x18005f3ae  setnz   dl
0x18005f3b1  mov     rcx, rbx
0x18005f3b4  mov     rax, [rax+20h]
0x18005f3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3bd  nop
0x18005f3be  mov     rcx, [rbp+40h+var_30]
0x18005f3c2  xor     rcx, rsp; StackCookie
0x18005f3c5  call    __security_check_cookie
0x18005f3ca  lea     r11, [rsp+140h+var_20]
0x18005f3d2  mov     rbx, [r11+38h]
0x18005f3d6  mov     rsi, [r11+40h]
0x18005f3da  mov     rsp, r11
0x18005f3dd  pop     r15
0x18005f3df  pop     r14
0x18005f3e1  pop     r12
0x18005f3e3  pop     rdi
0x18005f3e4  pop     rbp
0x18005f3e5  retn
```
