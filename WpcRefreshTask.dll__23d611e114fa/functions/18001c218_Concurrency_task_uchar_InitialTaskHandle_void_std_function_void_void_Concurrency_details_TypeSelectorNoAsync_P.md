# Concurrency::task<uchar>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Perform(void)

- ea: `0x18001c218`
- end: `0x18001c3f7`
- name: `?_Perform@?$_InitialTaskHandle@XV?$function@$$A6AXXZ@std@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXXZ`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d2e0`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x18001c070`
- `0x18001c218`
- `0x1800ae010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c381`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c381`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c39a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c39a`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c371`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18001c371`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,std::function<void (void)>,Concurrency::details::_TypeSelectorNoAsync>::_Perform(
        __int64 a1)
{
  Concurrency::details::_Task_impl_base *v2; // r14
  _BYTE *v3; // rcx
  _QWORD *v4; // rbx
  _BYTE *v5; // rcx
  _BYTE *v6; // rdx
  _BYTE *v7; // rdx
  Concurrency::details::_TaskEventLogger *v8; // rbx
  _BYTE *v9; // rdx
  _BYTE v11[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v12; // [rsp+78h] [rbp-88h]
  _BYTE v13[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v14; // [rsp+B8h] [rbp-48h]
  _BYTE v15[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *v16; // [rsp+F8h] [rbp-8h]

  v2 = *(Concurrency::details::_Task_impl_base **)(a1 + 8);
  v12 = 0;
  v3 = *(_BYTE **)(a1 + 80);
  if ( v3 )
  {
    v3 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v3)(v3, v11);
    v12 = v3;
  }
  v16 = 0;
  if ( v3 )
    v16 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v3)(v3, v15);
  v14 = 0;
  v4 = operator new(0x48u);
  *v4 = &std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::`vftable';
  v4[8] = 0;
  v5 = v16;
  if ( v16 )
  {
    v4[8] = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v16)(v16, v4 + 1);
    v5 = v16;
  }
  v14 = v4;
  if ( v5 )
  {
    v6 = v15;
    LOBYTE(v6) = v5 != v15;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v5 + 32LL))(v5, v6);
  }
  if ( v12 )
  {
    v7 = v11;
    LOBYTE(v7) = v12 != v11;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v12 + 32LL))(v12, v7);
    v12 = 0;
  }
  v8 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v8);
  if ( !v14 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v14 + 16LL))(v14);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v8);
  if ( v14 )
  {
    v9 = v13;
    LOBYTE(v9) = v14 != v13;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v14 + 32LL))(v14, v9);
    v14 = 0;
  }
  return Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v2);
}

```

## disassembly

```asm
0x18001c218  mov     [rsp-8+arg_8], rbx
0x18001c21d  mov     [rsp-8+arg_10], rsi
0x18001c222  push    rbp
0x18001c223  push    rdi
0x18001c224  push    r14
0x18001c226  lea     rbp, [rsp-10h]
0x18001c22b  sub     rsp, 110h
0x18001c232  mov     rax, cs:__security_cookie
0x18001c239  xor     rax, rsp
0x18001c23c  mov     [rbp+20h+var_20], rax
0x18001c240  mov     rsi, rcx
0x18001c243  mov     r14, [rcx+8]
0x18001c247  lea     rax, [rbp+20h+var_A0]
0x18001c24b  mov     [rsp+120h+var_F8], rax
0x18001c250  lea     rax, [rsp+120h+var_E0]
0x18001c255  mov     [rsp+120h+var_F0], rax
0x18001c25a  mov     [rsp+120h+var_A8], 0
0x18001c263  mov     rcx, [rcx+50h]
0x18001c267  test    rcx, rcx
0x18001c26a  jz      short loc_18001C284
0x18001c26c  mov     rax, [rcx]
0x18001c26f  lea     rdx, [rsp+120h+var_E0]
0x18001c274  mov     rax, [rax]
0x18001c277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c27c  mov     rcx, rax
0x18001c27f  mov     [rsp+120h+var_A8], rax
0x18001c284  lea     rax, [rsp+120h+var_E0]
0x18001c289  mov     [rsp+120h+var_F0], rax
0x18001c28e  lea     rax, [rbp+20h+var_60]
0x18001c292  mov     [rsp+120h+var_100], rax
0x18001c297  mov     [rbp+20h+var_28], 0
0x18001c29f  test    rcx, rcx
0x18001c2a2  jz      short loc_18001C2B7
0x18001c2a4  mov     rax, [rcx]
0x18001c2a7  lea     rdx, [rbp+20h+var_60]
0x18001c2ab  mov     rax, [rax]
0x18001c2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2b3  mov     [rbp+20h+var_28], rax
0x18001c2b7  mov     [rbp+20h+var_68], 0
0x18001c2bf  mov     ecx, 48h ; 'H'; Size
0x18001c2c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c2c9  mov     rbx, rax
0x18001c2cc  mov     [rsp+120h+var_100], rax
0x18001c2d1  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x18001c2d8  mov     [rbx], rax
0x18001c2db  lea     rdi, [rbx+8]
0x18001c2df  mov     [rsp+120h+var_E8], rdi
0x18001c2e4  mov     qword ptr [rdi+38h], 0
0x18001c2ec  mov     rcx, [rbp+20h+var_28]
0x18001c2f0  test    rcx, rcx
0x18001c2f3  jz      short loc_18001C30B
0x18001c2f5  mov     rax, [rcx]
0x18001c2f8  mov     rdx, rdi
0x18001c2fb  mov     rax, [rax]
0x18001c2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c303  mov     [rdi+38h], rax
0x18001c307  mov     rcx, [rbp+20h+var_28]
0x18001c30b  mov     [rbp+20h+var_68], rbx
0x18001c30f  test    rcx, rcx
0x18001c312  jz      short loc_18001C32B
0x18001c314  mov     rax, [rcx]
0x18001c317  lea     rdx, [rbp+20h+var_60]
0x18001c31b  cmp     rcx, rdx
0x18001c31e  setnz   dl
0x18001c321  mov     rax, [rax+20h]
0x18001c325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c32a  nop
0x18001c32b  mov     rcx, [rsp+120h+var_A8]
0x18001c330  test    rcx, rcx
0x18001c333  jz      short loc_18001C355
0x18001c335  mov     rax, [rcx]
0x18001c338  lea     rdx, [rsp+120h+var_E0]
0x18001c33d  cmp     rcx, rdx
0x18001c340  setnz   dl
0x18001c343  mov     rax, [rax+20h]
0x18001c347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c34c  mov     [rsp+120h+var_A8], 0
0x18001c355  lea     rax, [rbp+20h+var_A0]
0x18001c359  mov     [rsp+120h+var_E8], rax
0x18001c35e  mov     rbx, [rsi+8]
0x18001c362  add     rbx, 160h
0x18001c369  mov     [rsp+120h+var_100], rbx
0x18001c36e  mov     rcx, rbx
0x18001c371  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18001c377  nop
0x18001c378  mov     rcx, [rbp+20h+var_68]
0x18001c37c  test    rcx, rcx
0x18001c37f  jnz     short loc_18001C388
0x18001c381  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001c387  int     3; Trap to Debugger
0x18001c388  mov     rax, [rcx]
0x18001c38b  mov     rax, [rax+10h]
0x18001c38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c394  mov     dil, al
0x18001c397  mov     rcx, rbx
0x18001c39a  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18001c3a0  nop
0x18001c3a1  mov     rcx, [rbp+20h+var_68]
0x18001c3a5  test    rcx, rcx
0x18001c3a8  jz      short loc_18001C3C8
0x18001c3aa  mov     rdx, [rcx]
0x18001c3ad  mov     rax, [rdx+20h]
0x18001c3b1  lea     rdx, [rbp+20h+var_A0]
0x18001c3b5  cmp     rcx, rdx
0x18001c3b8  setnz   dl
0x18001c3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3c0  mov     [rbp+20h+var_68], 0
0x18001c3c8  mov     dl, dil
0x18001c3cb  mov     rcx, r14; this
0x18001c3ce  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18001c3d3  mov     rcx, [rbp+20h+var_20]
0x18001c3d7  xor     rcx, rsp; StackCookie
0x18001c3da  call    __security_check_cookie
0x18001c3df  lea     r11, [rsp+120h+var_10]
0x18001c3e7  mov     rbx, [r11+28h]
0x18001c3eb  mov     rsi, [r11+30h]
0x18001c3ef  mov     rsp, r11
0x18001c3f2  pop     r14
0x18001c3f4  pop     rdi
0x18001c3f5  pop     rbp
0x18001c3f6  retn
```
