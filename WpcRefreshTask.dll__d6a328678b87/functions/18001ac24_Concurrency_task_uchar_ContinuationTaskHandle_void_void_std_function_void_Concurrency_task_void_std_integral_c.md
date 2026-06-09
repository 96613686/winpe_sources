# Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18001ac24`
- end: `0x18001ae72`
- name: `?_Continue@?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d240`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x18001ac24`
- `0x18001c070`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001adb6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001adb6`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ae1d`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ae1d`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ad8d`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001ad8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
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
  *(_QWORD *)v7 = &std::_Func_impl_no_alloc<_lambda_dfadb08385c0ecb100cd522a7df6a8ea_,unsigned char,Concurrency::task<void>>::`vftable';
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
0x18001ac24  mov     [rsp-8+arg_8], rbx
0x18001ac29  mov     [rsp-8+arg_10], rsi
0x18001ac2e  push    rbp
0x18001ac2f  push    rdi
0x18001ac30  push    r12
0x18001ac32  push    r14
0x18001ac34  push    r15
0x18001ac36  lea     rbp, [rsp-20h]
0x18001ac3b  sub     rsp, 120h
0x18001ac42  mov     rax, cs:__security_cookie
0x18001ac49  xor     rax, rsp
0x18001ac4c  mov     [rbp+40h+var_30], rax
0x18001ac50  mov     rdi, rcx
0x18001ac53  mov     rax, [rcx+40h]
0x18001ac57  test    rax, rax
0x18001ac5a  jz      short loc_18001AC60
0x18001ac5c  lock inc dword ptr [rax+8]
0x18001ac60  mov     r14, [rcx+38h]
0x18001ac64  mov     r15, [rcx+40h]
0x18001ac68  mov     qword ptr [rsp+140h+var_100], r14
0x18001ac6d  mov     qword ptr [rsp+140h+var_100+8], r15
0x18001ac72  mov     r12, [rcx+28h]
0x18001ac76  lea     rax, [rsp+140h+var_F0]
0x18001ac7b  mov     [rsp+140h+var_120], rax
0x18001ac80  mov     [rbp+40h+var_B8], 0
0x18001ac88  mov     rcx, [rcx+80h]
0x18001ac8f  test    rcx, rcx
0x18001ac92  jz      short loc_18001ACAB
0x18001ac94  mov     rax, [rcx]
0x18001ac97  lea     rdx, [rsp+140h+var_F0]
0x18001ac9c  mov     rax, [rax]
0x18001ac9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca4  mov     rcx, rax
0x18001aca7  mov     [rbp+40h+var_B8], rax
0x18001acab  lea     rax, [rsp+140h+var_F0]
0x18001acb0  mov     [rsp+140h+var_120], rax
0x18001acb5  lea     rax, [rbp+40h+var_70]
0x18001acb9  mov     [rsp+140h+var_110], rax
0x18001acbe  mov     [rbp+40h+var_38], 0
0x18001acc6  test    rcx, rcx
0x18001acc9  jz      short loc_18001ACDE
0x18001accb  mov     rax, [rcx]
0x18001acce  lea     rdx, [rbp+40h+var_70]
0x18001acd2  mov     rax, [rax]
0x18001acd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acda  mov     [rbp+40h+var_38], rax
0x18001acde  mov     [rbp+40h+var_78], 0
0x18001ace6  mov     ecx, 48h ; 'H'; Size
0x18001aceb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001acf0  mov     rbx, rax
0x18001acf3  mov     [rsp+140h+var_110], rax
0x18001acf8  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_dfadb08385c0ecb100cd522a7df6a8ea_@@EV?$task@X@Concurrency@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_dfadb08385c0ecb100cd522a7df6a8ea_,uchar,Concurrency::task<void>>::`vftable'
0x18001acff  mov     [rbx], rax
0x18001ad02  lea     rsi, [rbx+8]
0x18001ad06  mov     [rsp+140h+var_108], rsi
0x18001ad0b  mov     qword ptr [rsi+38h], 0
0x18001ad13  mov     rcx, [rbp+40h+var_38]
0x18001ad17  test    rcx, rcx
0x18001ad1a  jz      short loc_18001AD32
0x18001ad1c  mov     rax, [rcx]
0x18001ad1f  mov     rdx, rsi
0x18001ad22  mov     rax, [rax]
0x18001ad25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad2a  mov     [rsi+38h], rax
0x18001ad2e  mov     rcx, [rbp+40h+var_38]
0x18001ad32  mov     [rbp+40h+var_78], rbx
0x18001ad36  test    rcx, rcx
0x18001ad39  jz      short loc_18001AD52
0x18001ad3b  mov     rax, [rcx]
0x18001ad3e  lea     rdx, [rbp+40h+var_70]
0x18001ad42  cmp     rcx, rdx
0x18001ad45  setnz   dl
0x18001ad48  mov     rax, [rax+20h]
0x18001ad4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad51  nop
0x18001ad52  mov     rcx, [rbp+40h+var_B8]
0x18001ad56  test    rcx, rcx
0x18001ad59  jz      short loc_18001AD7A
0x18001ad5b  mov     rax, [rcx]
0x18001ad5e  lea     rdx, [rsp+140h+var_F0]
0x18001ad63  cmp     rcx, rdx
0x18001ad66  setnz   dl
0x18001ad69  mov     rax, [rax+20h]
0x18001ad6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad72  mov     [rbp+40h+var_B8], 0
0x18001ad7a  mov     rsi, [rdi+28h]
0x18001ad7e  add     rsi, 160h
0x18001ad85  mov     [rsp+140h+var_108], rsi
0x18001ad8a  mov     rcx, rsi
0x18001ad8d  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18001ad93  nop
0x18001ad94  mov     [rsp+140h+var_120], r14
0x18001ad99  mov     [rsp+140h+var_118], r15
0x18001ad9e  xorps   xmm0, xmm0
0x18001ada1  movdqu  [rsp+140h+var_100], xmm0
0x18001ada7  lea     rax, [rsp+140h+var_120]
0x18001adac  mov     [rsp+140h+var_110], rax
0x18001adb1  test    rbx, rbx
0x18001adb4  jnz     short loc_18001ADBD
0x18001adb6  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001adbc  int     3; Trap to Debugger
0x18001adbd  mov     rax, [rbx]
0x18001adc0  lea     rdx, [rsp+140h+var_120]
0x18001adc5  mov     rcx, rbx
0x18001adc8  mov     rax, [rax+10h]
0x18001adcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001add1  mov     r14b, al
0x18001add4  mov     rdi, [rsp+140h+var_118]
0x18001add9  test    rdi, rdi
0x18001addc  jz      short loc_18001AE1A
0x18001adde  or      r15d, 0FFFFFFFFh
0x18001ade2  mov     ecx, r15d
0x18001ade5  lock xadd [rdi+8], ecx
0x18001adea  add     ecx, r15d
0x18001aded  jnz     short loc_18001AE1A
0x18001adef  mov     rdx, [rdi]
0x18001adf2  mov     rcx, rdi
0x18001adf5  mov     rax, [rdx]
0x18001adf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adfd  mov     eax, r15d
0x18001ae00  lock xadd [rdi+0Ch], eax
0x18001ae05  add     eax, r15d
0x18001ae08  jnz     short loc_18001AE1A
0x18001ae0a  mov     rax, [rdi]
0x18001ae0d  mov     rcx, rdi
0x18001ae10  mov     rax, [rax+8]
0x18001ae14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae19  nop
0x18001ae1a  mov     rcx, rsi
0x18001ae1d  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18001ae23  nop
0x18001ae24  mov     dl, r14b
0x18001ae27  mov     rcx, r12; this
0x18001ae2a  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18001ae2f  nop
0x18001ae30  mov     rax, [rbx]
0x18001ae33  lea     rcx, [rbp+40h+var_B0]
0x18001ae37  cmp     rbx, rcx
0x18001ae3a  setnz   dl
0x18001ae3d  mov     rcx, rbx
0x18001ae40  mov     rax, [rax+20h]
0x18001ae44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae49  nop
0x18001ae4a  mov     rcx, [rbp+40h+var_30]
0x18001ae4e  xor     rcx, rsp; StackCookie
0x18001ae51  call    __security_check_cookie
0x18001ae56  lea     r11, [rsp+140h+var_20]
0x18001ae5e  mov     rbx, [r11+38h]
0x18001ae62  mov     rsi, [r11+40h]
0x18001ae66  mov     rsp, r11
0x18001ae69  pop     r15
0x18001ae6b  pop     r14
0x18001ae6d  pop     r12
0x18001ae6f  pop     rdi
0x18001ae70  pop     rbp
0x18001ae71  retn
```
