# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x18001213c`
- end: `0x1800123be`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012f40`

## callees

- `0x180002030`
- `0x18000208c`
- `0x180011a50`
- `0x18001213c`
- `0x18001277c`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180012291`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180012291`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800122aa`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800122aa`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180012281`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180012281`
- `msvcp_win!_Cnd_broadcast` at `0x180012395`
- `msvcp_win!_Cnd_broadcast` at `0x180012395`
- `msvcp_win!_Mtx_unlock` at `0x180012314`
- `msvcp_win!_Mtx_unlock` at `0x180012345`
- `msvcp_win!_Mtx_unlock` at `0x18001239f`
- `msvcp_win!_Mtx_unlock` at `0x180012314`
- `msvcp_win!_Mtx_unlock` at `0x180012345`
- `msvcp_win!_Mtx_unlock` at `0x18001239f`
- `msvcp_win!_Mtx_lock` at `0x1800122e6`
- `msvcp_win!_Mtx_lock` at `0x180012356`
- `msvcp_win!_Mtx_lock` at `0x1800122e6`
- `msvcp_win!_Mtx_lock` at `0x180012356`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012378`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800123b7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012378`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800123b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  _BYTE *v4; // rcx
  _BYTE *v5; // rdx
  _QWORD *v6; // rdx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  char v8; // si
  _BYTE *v9; // rdx
  struct _Mtx_internal_imp_t *v10; // rcx
  _QWORD v11[7]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v12; // [rsp+78h] [rbp-88h]
  _BYTE v13[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v14; // [rsp+B8h] [rbp-48h]
  _BYTE v15[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *v16; // [rsp+F8h] [rbp-8h]

  v2 = *(_QWORD *)(a1 + 8);
  v11[0] = off_18001A758;
  v11[1] = *(_QWORD *)(a1 + 24);
  v12 = v11;
  v16 = 0;
  v16 = (_BYTE *)std::_Func_impl_no_alloc__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__void_::_Move(v11, v15);
  v14 = 0;
  v3 = operator new(0x48u);
  *v3 = &std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::`vftable';
  v3[8] = 0;
  v4 = v16;
  if ( v16 )
  {
    v3[8] = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v16)(v16, v3 + 1);
    v4 = v16;
  }
  v14 = v3;
  if ( v4 )
  {
    v5 = v15;
    LOBYTE(v5) = v4 != v15;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v4 + 32LL))(v4, v5);
    v16 = 0;
  }
  if ( v12 )
  {
    v6 = v11;
    LOBYTE(v6) = v12 != v11;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v12 + 32LL))(v12, v6);
    v12 = 0;
  }
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  if ( !v14 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v8 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v14 + 16LL))(v14);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  if ( v14 )
  {
    v9 = v13;
    LOBYTE(v9) = v14 != v13;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v14 + 32LL))(v14, v9);
    v14 = 0;
  }
  *(_BYTE *)(v2 + 368) = v8;
  if ( _Mtx_lock((_Mtx_t)(v2 + 32)) )
    goto LABEL_23;
  if ( *(_DWORD *)(v2 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 108) = 2147483646;
    goto LABEL_19;
  }
  v10 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v10);
    return;
  }
  *(_DWORD *)(v2 + 8) = 3;
  _Mtx_unlock(v10);
  if ( _Mtx_lock((_Mtx_t)(v2 + 208)) )
  {
LABEL_23:
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x1800123BDLL);
  }
  if ( *(_DWORD *)(v2 + 284) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 284) = 2147483646;
LABEL_19:
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( *(int *)(v2 + 312) < 2 )
    *(_DWORD *)(v2 + 312) = 2;
  _Cnd_broadcast((_Cnd_t)(v2 + 136));
  _Mtx_unlock((_Mtx_t)(v2 + 208));
  Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
}

```

## disassembly

```asm
0x18001213c  mov     [rsp-8+arg_8], rbx
0x180012141  mov     [rsp-8+arg_10], rsi
0x180012146  push    rbp
0x180012147  push    rdi
0x180012148  push    r14
0x18001214a  lea     rbp, [rsp-10h]
0x18001214f  sub     rsp, 110h
0x180012156  mov     rax, cs:__security_cookie
0x18001215d  xor     rax, rsp
0x180012160  mov     [rbp+20h+var_20], rax
0x180012164  mov     r14, rcx
0x180012167  mov     rdi, [rcx+8]
0x18001216b  lea     rax, [rbp+20h+var_A0]
0x18001216f  mov     [rsp+120h+var_F8], rax
0x180012174  lea     rax, off_18001A758
0x18001217b  mov     [rsp+120h+var_E0], rax
0x180012180  mov     rax, [rcx+18h]
0x180012184  mov     [rsp+120h+var_D8], rax
0x180012189  lea     rax, [rsp+120h+var_E0]
0x18001218e  mov     [rsp+120h+var_A8], rax
0x180012193  lea     rax, [rsp+120h+var_E0]
0x180012198  mov     [rsp+120h+var_F0], rax
0x18001219d  lea     rax, [rbp+20h+var_60]
0x1800121a1  mov     [rsp+120h+var_100], rax
0x1800121a6  mov     [rbp+20h+var_28], 0
0x1800121ae  lea     rdx, [rbp+20h+var_60]
0x1800121b2  lea     rcx, [rsp+120h+var_E0]
0x1800121b7  call    std___Func_impl_no_alloc__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__void____Move
0x1800121bc  mov     [rbp+20h+var_28], rax
0x1800121c0  mov     [rbp+20h+var_68], 0
0x1800121c8  mov     ecx, 48h ; 'H'; Size
0x1800121cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800121d2  mov     rbx, rax
0x1800121d5  mov     [rsp+120h+var_100], rax
0x1800121da  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x1800121e1  mov     [rbx], rax
0x1800121e4  lea     rsi, [rbx+8]
0x1800121e8  mov     [rsp+120h+var_E8], rsi
0x1800121ed  mov     qword ptr [rsi+38h], 0
0x1800121f5  mov     rcx, [rbp+20h+var_28]
0x1800121f9  test    rcx, rcx
0x1800121fc  jz      short loc_180012214
0x1800121fe  mov     rax, [rcx]
0x180012201  mov     rdx, rsi
0x180012204  mov     rax, [rax]
0x180012207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001220c  mov     [rsi+38h], rax
0x180012210  mov     rcx, [rbp+20h+var_28]
0x180012214  mov     [rbp+20h+var_68], rbx
0x180012218  test    rcx, rcx
0x18001221b  jz      short loc_18001223B
0x18001221d  mov     rax, [rcx]
0x180012220  lea     rdx, [rbp+20h+var_60]
0x180012224  cmp     rcx, rdx
0x180012227  setnz   dl
0x18001222a  mov     rax, [rax+20h]
0x18001222e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012233  mov     [rbp+20h+var_28], 0
0x18001223b  mov     rcx, [rsp+120h+var_A8]
0x180012240  test    rcx, rcx
0x180012243  jz      short loc_180012265
0x180012245  mov     rax, [rcx]
0x180012248  lea     rdx, [rsp+120h+var_E0]
0x18001224d  cmp     rcx, rdx
0x180012250  setnz   dl
0x180012253  mov     rax, [rax+20h]
0x180012257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001225c  mov     [rsp+120h+var_A8], 0
0x180012265  lea     rax, [rbp+20h+var_A0]
0x180012269  mov     [rsp+120h+var_E8], rax
0x18001226e  mov     rbx, [r14+8]
0x180012272  add     rbx, 160h
0x180012279  mov     [rsp+120h+var_100], rbx
0x18001227e  mov     rcx, rbx
0x180012281  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180012287  nop
0x180012288  mov     rcx, [rbp+20h+var_68]
0x18001228c  test    rcx, rcx
0x18001228f  jnz     short loc_180012298
0x180012291  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180012297  int     3; Trap to Debugger
0x180012298  mov     rax, [rcx]
0x18001229b  mov     rax, [rax+10h]
0x18001229f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122a4  mov     sil, al
0x1800122a7  mov     rcx, rbx
0x1800122aa  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800122b0  nop
0x1800122b1  mov     rcx, [rbp+20h+var_68]
0x1800122b5  test    rcx, rcx
0x1800122b8  jz      short loc_1800122D8
0x1800122ba  mov     rdx, [rcx]
0x1800122bd  mov     rax, [rdx+20h]
0x1800122c1  lea     rdx, [rbp+20h+var_A0]
0x1800122c5  cmp     rcx, rdx
0x1800122c8  setnz   dl
0x1800122cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122d0  mov     [rbp+20h+var_68], 0
0x1800122d8  mov     [rdi+170h], sil
0x1800122df  lea     rbx, [rdi+20h]
0x1800122e3  mov     rcx, rbx; _Mtx_t
0x1800122e6  call    cs:__imp__Mtx_lock
0x1800122ec  test    eax, eax
0x1800122ee  jnz     loc_1800123B2
0x1800122f4  mov     eax, [rbx+4Ch]
0x1800122f7  mov     r14d, 7FFFFFFFh
0x1800122fd  cmp     eax, r14d
0x180012300  jnz     short loc_180012309
0x180012302  dec     eax
0x180012304  mov     [rbx+4Ch], eax
0x180012307  jmp     short loc_180012373
0x180012309  mov     eax, [rdi+8]
0x18001230c  mov     rcx, rbx; _Mtx_t
0x18001230f  cmp     eax, 4
0x180012312  jnz     short loc_18001233E
0x180012314  call    cs:__imp__Mtx_unlock
0x18001231a  mov     rcx, [rbp+20h+var_20]
0x18001231e  xor     rcx, rsp; StackCookie
0x180012321  call    __security_check_cookie
0x180012326  lea     r11, [rsp+120h+var_10]
0x18001232e  mov     rbx, [r11+28h]
0x180012332  mov     rsi, [r11+30h]
0x180012336  mov     rsp, r11
0x180012339  pop     r14
0x18001233b  pop     rdi
0x18001233c  pop     rbp
0x18001233d  retn
0x18001233e  mov     dword ptr [rdi+8], 3
0x180012345  call    cs:__imp__Mtx_unlock
0x18001234b  lea     rsi, [rdi+88h]
0x180012352  lea     rcx, [rsi+48h]; _Mtx_t
0x180012356  call    cs:__imp__Mtx_lock
0x18001235c  test    eax, eax
0x18001235e  jnz     short loc_1800123B2
0x180012360  mov     eax, [rsi+94h]
0x180012366  cmp     eax, r14d
0x180012369  jnz     short loc_18001237F
0x18001236b  dec     eax
0x18001236d  mov     [rsi+94h], eax
0x180012373  mov     ecx, 6
0x180012378  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001237e  int     3; Trap to Debugger
0x18001237f  cmp     dword ptr [rsi+0B0h], 2
0x180012386  jge     short loc_180012392
0x180012388  mov     dword ptr [rsi+0B0h], 2
0x180012392  mov     rcx, rsi; _Cnd_t
0x180012395  call    cs:__imp__Cnd_broadcast
0x18001239b  lea     rcx, [rsi+48h]; _Mtx_t
0x18001239f  call    cs:__imp__Mtx_unlock
0x1800123a5  mov     rcx, rdi; this
0x1800123a8  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x1800123ad  jmp     loc_18001231A
0x1800123b2  mov     ecx, 5
0x1800123b7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
