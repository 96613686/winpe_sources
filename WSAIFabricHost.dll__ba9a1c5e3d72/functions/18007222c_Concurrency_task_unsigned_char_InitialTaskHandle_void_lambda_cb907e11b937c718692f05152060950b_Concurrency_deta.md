# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x18007222c`
- end: `0x1800724ae`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180073610`

## callees

- `0x180004ca0`
- `0x180007ad0`
- `0x180071ad0`
- `0x18007222c`
- `0x180072abc`
- `0x180089010`

## import_xrefs

- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180072371`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180072371`
- `msvcp_win!_Cnd_broadcast` at `0x180072485`
- `msvcp_win!_Cnd_broadcast` at `0x180072485`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180072381`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180072381`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18007239a`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18007239a`
- `msvcp_win!_Mtx_unlock` at `0x180072404`
- `msvcp_win!_Mtx_unlock` at `0x180072435`
- `msvcp_win!_Mtx_unlock` at `0x18007248f`
- `msvcp_win!_Mtx_unlock` at `0x180072404`
- `msvcp_win!_Mtx_unlock` at `0x180072435`
- `msvcp_win!_Mtx_unlock` at `0x18007248f`
- `msvcp_win!_Mtx_lock` at `0x1800723d6`
- `msvcp_win!_Mtx_lock` at `0x180072446`
- `msvcp_win!_Mtx_lock` at `0x1800723d6`
- `msvcp_win!_Mtx_lock` at `0x180072446`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180072468`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800724a7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180072468`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800724a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_cb907e11b937c718692f05152060950b__Concurrency::details::_TypeSelectorNoAsync_::_Init(
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
  v11[0] = off_18008BA00;
  v11[1] = *(_QWORD *)(a1 + 24);
  v12 = v11;
  v16 = 0;
  v16 = (_BYTE *)std::_Func_impl_no_alloc__lambda_cb907e11b937c718692f05152060950b__void_::_Move(v11, v15);
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
    JUMPOUT(0x1800724ADLL);
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
0x18007222c  mov     [rsp-8+arg_8], rbx
0x180072231  mov     [rsp-8+arg_10], rsi
0x180072236  push    rbp
0x180072237  push    rdi
0x180072238  push    r14
0x18007223a  lea     rbp, [rsp-10h]
0x18007223f  sub     rsp, 110h
0x180072246  mov     rax, cs:__security_cookie
0x18007224d  xor     rax, rsp
0x180072250  mov     [rbp+20h+var_20], rax
0x180072254  mov     r14, rcx
0x180072257  mov     rdi, [rcx+8]
0x18007225b  lea     rax, [rbp+20h+var_A0]
0x18007225f  mov     [rsp+120h+var_F8], rax
0x180072264  lea     rax, off_18008BA00
0x18007226b  mov     [rsp+120h+var_E0], rax
0x180072270  mov     rax, [rcx+18h]
0x180072274  mov     [rsp+120h+var_D8], rax
0x180072279  lea     rax, [rsp+120h+var_E0]
0x18007227e  mov     [rsp+120h+var_A8], rax
0x180072283  lea     rax, [rsp+120h+var_E0]
0x180072288  mov     [rsp+120h+var_F0], rax
0x18007228d  lea     rax, [rbp+20h+var_60]
0x180072291  mov     [rsp+120h+var_100], rax
0x180072296  mov     [rbp+20h+var_28], 0
0x18007229e  lea     rdx, [rbp+20h+var_60]
0x1800722a2  lea     rcx, [rsp+120h+var_E0]
0x1800722a7  call    std___Func_impl_no_alloc__lambda_cb907e11b937c718692f05152060950b__void____Move
0x1800722ac  mov     [rbp+20h+var_28], rax
0x1800722b0  mov     [rbp+20h+var_68], 0
0x1800722b8  mov     ecx, 48h ; 'H'; Size
0x1800722bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800722c2  mov     rbx, rax
0x1800722c5  mov     [rsp+120h+var_100], rax
0x1800722ca  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x1800722d1  mov     [rbx], rax
0x1800722d4  lea     rsi, [rbx+8]
0x1800722d8  mov     [rsp+120h+var_E8], rsi
0x1800722dd  mov     qword ptr [rsi+38h], 0
0x1800722e5  mov     rcx, [rbp+20h+var_28]
0x1800722e9  test    rcx, rcx
0x1800722ec  jz      short loc_180072304
0x1800722ee  mov     rax, [rcx]
0x1800722f1  mov     rdx, rsi
0x1800722f4  mov     rax, [rax]
0x1800722f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800722fc  mov     [rsi+38h], rax
0x180072300  mov     rcx, [rbp+20h+var_28]
0x180072304  mov     [rbp+20h+var_68], rbx
0x180072308  test    rcx, rcx
0x18007230b  jz      short loc_18007232B
0x18007230d  mov     rax, [rcx]
0x180072310  lea     rdx, [rbp+20h+var_60]
0x180072314  cmp     rcx, rdx
0x180072317  setnz   dl
0x18007231a  mov     rax, [rax+20h]
0x18007231e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072323  mov     [rbp+20h+var_28], 0
0x18007232b  mov     rcx, [rsp+120h+var_A8]
0x180072330  test    rcx, rcx
0x180072333  jz      short loc_180072355
0x180072335  mov     rax, [rcx]
0x180072338  lea     rdx, [rsp+120h+var_E0]
0x18007233d  cmp     rcx, rdx
0x180072340  setnz   dl
0x180072343  mov     rax, [rax+20h]
0x180072347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007234c  mov     [rsp+120h+var_A8], 0
0x180072355  lea     rax, [rbp+20h+var_A0]
0x180072359  mov     [rsp+120h+var_E8], rax
0x18007235e  mov     rbx, [r14+8]
0x180072362  add     rbx, 160h
0x180072369  mov     [rsp+120h+var_100], rbx
0x18007236e  mov     rcx, rbx
0x180072371  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180072377  nop
0x180072378  mov     rcx, [rbp+20h+var_68]
0x18007237c  test    rcx, rcx
0x18007237f  jnz     short loc_180072388
0x180072381  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180072387  int     3; Trap to Debugger
0x180072388  mov     rax, [rcx]
0x18007238b  mov     rax, [rax+10h]
0x18007238f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072394  mov     sil, al
0x180072397  mov     rcx, rbx
0x18007239a  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800723a0  nop
0x1800723a1  mov     rcx, [rbp+20h+var_68]
0x1800723a5  test    rcx, rcx
0x1800723a8  jz      short loc_1800723C8
0x1800723aa  mov     rdx, [rcx]
0x1800723ad  mov     rax, [rdx+20h]
0x1800723b1  lea     rdx, [rbp+20h+var_A0]
0x1800723b5  cmp     rcx, rdx
0x1800723b8  setnz   dl
0x1800723bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723c0  mov     [rbp+20h+var_68], 0
0x1800723c8  mov     [rdi+170h], sil
0x1800723cf  lea     rbx, [rdi+20h]
0x1800723d3  mov     rcx, rbx; _Mtx_t
0x1800723d6  call    cs:__imp__Mtx_lock
0x1800723dc  test    eax, eax
0x1800723de  jnz     loc_1800724A2
0x1800723e4  mov     eax, [rbx+4Ch]
0x1800723e7  mov     r14d, 7FFFFFFFh
0x1800723ed  cmp     eax, r14d
0x1800723f0  jnz     short loc_1800723F9
0x1800723f2  dec     eax
0x1800723f4  mov     [rbx+4Ch], eax
0x1800723f7  jmp     short loc_180072463
0x1800723f9  mov     eax, [rdi+8]
0x1800723fc  mov     rcx, rbx; _Mtx_t
0x1800723ff  cmp     eax, 4
0x180072402  jnz     short loc_18007242E
0x180072404  call    cs:__imp__Mtx_unlock
0x18007240a  mov     rcx, [rbp+20h+var_20]
0x18007240e  xor     rcx, rsp; StackCookie
0x180072411  call    __security_check_cookie
0x180072416  lea     r11, [rsp+120h+var_10]
0x18007241e  mov     rbx, [r11+28h]
0x180072422  mov     rsi, [r11+30h]
0x180072426  mov     rsp, r11
0x180072429  pop     r14
0x18007242b  pop     rdi
0x18007242c  pop     rbp
0x18007242d  retn
0x18007242e  mov     dword ptr [rdi+8], 3
0x180072435  call    cs:__imp__Mtx_unlock
0x18007243b  lea     rsi, [rdi+88h]
0x180072442  lea     rcx, [rsi+48h]; _Mtx_t
0x180072446  call    cs:__imp__Mtx_lock
0x18007244c  test    eax, eax
0x18007244e  jnz     short loc_1800724A2
0x180072450  mov     eax, [rsi+94h]
0x180072456  cmp     eax, r14d
0x180072459  jnz     short loc_18007246F
0x18007245b  dec     eax
0x18007245d  mov     [rsi+94h], eax
0x180072463  mov     ecx, 6
0x180072468  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18007246e  int     3; Trap to Debugger
0x18007246f  cmp     dword ptr [rsi+0B0h], 2
0x180072476  jge     short loc_180072482
0x180072478  mov     dword ptr [rsi+0B0h], 2
0x180072482  mov     rcx, rsi; _Cnd_t
0x180072485  call    cs:__imp__Cnd_broadcast
0x18007248b  lea     rcx, [rsi+48h]; _Mtx_t
0x18007248f  call    cs:__imp__Mtx_unlock
0x180072495  mov     rcx, rdi; this
0x180072498  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x18007249d  jmp     loc_18007240A
0x1800724a2  mov     ecx, 5
0x1800724a7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
