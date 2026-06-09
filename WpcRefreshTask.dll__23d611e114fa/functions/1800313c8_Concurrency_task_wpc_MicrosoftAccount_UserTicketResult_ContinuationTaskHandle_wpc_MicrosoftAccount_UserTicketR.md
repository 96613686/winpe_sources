# Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1800313c8`
- end: `0x180031616`
- name: `?_Continue@?$_ContinuationTaskHandle@UUserTicketResult@MicrosoftAccount@wpc@@XV?$function@$$A6AXV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@Z@std@@U?$integral_constant@_N$00@5@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031d10`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x18001c070`
- `0x1800313c8`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003155a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003155a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800315c1`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800315c1`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031531`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180031531`

## pseudocode

```c
__int64 __fastcall Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>::_ContinuationTaskHandle<wpc::MicrosoftAccount::UserTicketResult,void,std::function<void (Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
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
  *(_QWORD *)v7 = &std::_Func_impl_no_alloc<_lambda_83293b9750ae69dabe7cbdda09564b34_,unsigned char,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>>::`vftable';
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
0x1800313c8  mov     [rsp-8+arg_8], rbx
0x1800313cd  mov     [rsp-8+arg_10], rsi
0x1800313d2  push    rbp
0x1800313d3  push    rdi
0x1800313d4  push    r12
0x1800313d6  push    r14
0x1800313d8  push    r15
0x1800313da  lea     rbp, [rsp-20h]
0x1800313df  sub     rsp, 120h
0x1800313e6  mov     rax, cs:__security_cookie
0x1800313ed  xor     rax, rsp
0x1800313f0  mov     [rbp+40h+var_30], rax
0x1800313f4  mov     rdi, rcx
0x1800313f7  mov     rax, [rcx+40h]
0x1800313fb  test    rax, rax
0x1800313fe  jz      short loc_180031404
0x180031400  lock inc dword ptr [rax+8]
0x180031404  mov     r14, [rcx+38h]
0x180031408  mov     r15, [rcx+40h]
0x18003140c  mov     qword ptr [rsp+140h+var_100], r14
0x180031411  mov     qword ptr [rsp+140h+var_100+8], r15
0x180031416  mov     r12, [rcx+28h]
0x18003141a  lea     rax, [rsp+140h+var_F0]
0x18003141f  mov     [rsp+140h+var_120], rax
0x180031424  mov     [rbp+40h+var_B8], 0
0x18003142c  mov     rcx, [rcx+80h]
0x180031433  test    rcx, rcx
0x180031436  jz      short loc_18003144F
0x180031438  mov     rax, [rcx]
0x18003143b  lea     rdx, [rsp+140h+var_F0]
0x180031440  mov     rax, [rax]
0x180031443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031448  mov     rcx, rax
0x18003144b  mov     [rbp+40h+var_B8], rax
0x18003144f  lea     rax, [rsp+140h+var_F0]
0x180031454  mov     [rsp+140h+var_120], rax
0x180031459  lea     rax, [rbp+40h+var_70]
0x18003145d  mov     [rsp+140h+var_110], rax
0x180031462  mov     [rbp+40h+var_38], 0
0x18003146a  test    rcx, rcx
0x18003146d  jz      short loc_180031482
0x18003146f  mov     rax, [rcx]
0x180031472  lea     rdx, [rbp+40h+var_70]
0x180031476  mov     rax, [rax]
0x180031479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003147e  mov     [rbp+40h+var_38], rax
0x180031482  mov     [rbp+40h+var_78], 0
0x18003148a  mov     ecx, 48h ; 'H'; Size
0x18003148f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031494  mov     rbx, rax
0x180031497  mov     [rsp+140h+var_110], rax
0x18003149c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_83293b9750ae69dabe7cbdda09564b34_@@EV?$task@UUserTicketResult@MicrosoftAccount@wpc@@@Concurrency@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_83293b9750ae69dabe7cbdda09564b34_,uchar,Concurrency::task<wpc::MicrosoftAccount::UserTicketResult>>::`vftable'
0x1800314a3  mov     [rbx], rax
0x1800314a6  lea     rsi, [rbx+8]
0x1800314aa  mov     [rsp+140h+var_108], rsi
0x1800314af  mov     qword ptr [rsi+38h], 0
0x1800314b7  mov     rcx, [rbp+40h+var_38]
0x1800314bb  test    rcx, rcx
0x1800314be  jz      short loc_1800314D6
0x1800314c0  mov     rax, [rcx]
0x1800314c3  mov     rdx, rsi
0x1800314c6  mov     rax, [rax]
0x1800314c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314ce  mov     [rsi+38h], rax
0x1800314d2  mov     rcx, [rbp+40h+var_38]
0x1800314d6  mov     [rbp+40h+var_78], rbx
0x1800314da  test    rcx, rcx
0x1800314dd  jz      short loc_1800314F6
0x1800314df  mov     rax, [rcx]
0x1800314e2  lea     rdx, [rbp+40h+var_70]
0x1800314e6  cmp     rcx, rdx
0x1800314e9  setnz   dl
0x1800314ec  mov     rax, [rax+20h]
0x1800314f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314f5  nop
0x1800314f6  mov     rcx, [rbp+40h+var_B8]
0x1800314fa  test    rcx, rcx
0x1800314fd  jz      short loc_18003151E
0x1800314ff  mov     rax, [rcx]
0x180031502  lea     rdx, [rsp+140h+var_F0]
0x180031507  cmp     rcx, rdx
0x18003150a  setnz   dl
0x18003150d  mov     rax, [rax+20h]
0x180031511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031516  mov     [rbp+40h+var_B8], 0
0x18003151e  mov     rsi, [rdi+28h]
0x180031522  add     rsi, 160h
0x180031529  mov     [rsp+140h+var_108], rsi
0x18003152e  mov     rcx, rsi
0x180031531  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180031537  nop
0x180031538  mov     [rsp+140h+var_120], r14
0x18003153d  mov     [rsp+140h+var_118], r15
0x180031542  xorps   xmm0, xmm0
0x180031545  movdqu  [rsp+140h+var_100], xmm0
0x18003154b  lea     rax, [rsp+140h+var_120]
0x180031550  mov     [rsp+140h+var_110], rax
0x180031555  test    rbx, rbx
0x180031558  jnz     short loc_180031561
0x18003155a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180031560  int     3; Trap to Debugger
0x180031561  mov     rax, [rbx]
0x180031564  lea     rdx, [rsp+140h+var_120]
0x180031569  mov     rcx, rbx
0x18003156c  mov     rax, [rax+10h]
0x180031570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031575  mov     r14b, al
0x180031578  mov     rdi, [rsp+140h+var_118]
0x18003157d  test    rdi, rdi
0x180031580  jz      short loc_1800315BE
0x180031582  or      r15d, 0FFFFFFFFh
0x180031586  mov     ecx, r15d
0x180031589  lock xadd [rdi+8], ecx
0x18003158e  add     ecx, r15d
0x180031591  jnz     short loc_1800315BE
0x180031593  mov     rdx, [rdi]
0x180031596  mov     rcx, rdi
0x180031599  mov     rax, [rdx]
0x18003159c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315a1  mov     eax, r15d
0x1800315a4  lock xadd [rdi+0Ch], eax
0x1800315a9  add     eax, r15d
0x1800315ac  jnz     short loc_1800315BE
0x1800315ae  mov     rax, [rdi]
0x1800315b1  mov     rcx, rdi
0x1800315b4  mov     rax, [rax+8]
0x1800315b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315bd  nop
0x1800315be  mov     rcx, rsi
0x1800315c1  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800315c7  nop
0x1800315c8  mov     dl, r14b
0x1800315cb  mov     rcx, r12; this
0x1800315ce  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x1800315d3  nop
0x1800315d4  mov     rax, [rbx]
0x1800315d7  lea     rcx, [rbp+40h+var_B0]
0x1800315db  cmp     rbx, rcx
0x1800315de  setnz   dl
0x1800315e1  mov     rcx, rbx
0x1800315e4  mov     rax, [rax+20h]
0x1800315e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315ed  nop
0x1800315ee  mov     rcx, [rbp+40h+var_30]
0x1800315f2  xor     rcx, rsp; StackCookie
0x1800315f5  call    __security_check_cookie
0x1800315fa  lea     r11, [rsp+140h+var_20]
0x180031602  mov     rbx, [r11+38h]
0x180031606  mov     rsi, [r11+40h]
0x18003160a  mov     rsp, r11
0x18003160d  pop     r15
0x18003160f  pop     r14
0x180031611  pop     r12
0x180031613  pop     rdi
0x180031614  pop     rbp
0x180031615  retn
```
