# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x18004821c`
- end: `0x180048384`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048e00`

## callees

- `0x18004821c`
- `0x18004838c`
- `0x180048804`
- `0x180048ea0`
- `0x18005c010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18004831e`
- `msvcp_win!_Mtx_unlock` at `0x18004832d`
- `msvcp_win!_Mtx_unlock` at `0x180048363`
- `msvcp_win!_Mtx_unlock` at `0x18004831e`
- `msvcp_win!_Mtx_unlock` at `0x18004832d`
- `msvcp_win!_Mtx_unlock` at `0x180048363`
- `msvcp_win!_Cnd_broadcast` at `0x180048359`
- `msvcp_win!_Cnd_broadcast` at `0x180048359`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800482a9`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800482a9`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800482d2`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800482d2`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800482b9`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800482b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_24118411a5dbe3bad2a5675dbe245306__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rdx
  Concurrency::details::_TaskEventLogger *v4; // rdi
  char v5; // si
  _BYTE *v6; // rdx
  struct _Mtx_internal_imp_t *v7; // rcx
  _QWORD v8[7]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD *v9; // [rsp+58h] [rbp-1h]
  _BYTE v10[56]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE *v11; // [rsp+98h] [rbp+3Fh]

  v2 = *(_QWORD *)(a1 + 8);
  v8[0] = off_18005EA70;
  v8[1] = *(_QWORD *)(a1 + 24);
  v9 = v8;
  Concurrency::details::_MakeVoidToUnitFunc(v10, v8);
  if ( v9 )
  {
    v3 = v8;
    LOBYTE(v3) = v9 != v8;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v9 + 32LL))(v9, v3);
    v9 = 0;
  }
  v4 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v4);
  if ( !v11 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v5 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v11 + 16LL))(v11);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v4);
  if ( v11 )
  {
    v6 = v10;
    LOBYTE(v6) = v11 != v10;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v11 + 32LL))(v11, v6);
    v11 = 0;
  }
  *(_BYTE *)(v2 + 368) = v5;
  std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 32));
  v7 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v7);
  }
  else
  {
    *(_DWORD *)(v2 + 8) = 3;
    _Mtx_unlock(v7);
    std::_Mutex_base::lock((std::_Mutex_base *)(v2 + 208));
    if ( *(int *)(v2 + 312) < 2 )
      *(_DWORD *)(v2 + 312) = 2;
    _Cnd_broadcast((_Cnd_t)(v2 + 136));
    _Mtx_unlock((_Mtx_t)(v2 + 208));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x18004821c  mov     [rsp-8+arg_18], rbx
0x180048221  push    rbp
0x180048222  push    rsi
0x180048223  push    rdi
0x180048224  lea     rbp, [rsp-47h]
0x180048229  sub     rsp, 0A0h
0x180048230  mov     rdi, rcx
0x180048233  mov     rbx, [rcx+8]
0x180048237  lea     rax, off_18005EA70
0x18004823e  mov     [rbp+57h+var_90], rax
0x180048242  mov     rax, [rcx+18h]
0x180048246  mov     [rbp+57h+var_88], rax
0x18004824a  lea     rax, [rbp+57h+var_90]
0x18004824e  mov     [rbp+57h+var_58], rax
0x180048252  lea     rax, [rbp+57h+var_90]
0x180048256  mov     [rbp+57h+arg_0], rax
0x18004825a  lea     rdx, [rbp+57h+var_90]
0x18004825e  lea     rcx, [rbp+57h+var_50]
0x180048262  call    ?_MakeVoidToUnitFunc@details@Concurrency@@YA?AV?$function@$$A6AEXZ@std@@AEBV?$function@$$A6AXXZ@4@@Z; Concurrency::details::_MakeVoidToUnitFunc(std::function<void (void)> const &)
0x180048267  nop
0x180048268  mov     rcx, [rbp+57h+var_58]
0x18004826c  test    rcx, rcx
0x18004826f  jz      short loc_18004828F
0x180048271  mov     rax, [rcx]
0x180048274  lea     rdx, [rbp+57h+var_90]
0x180048278  cmp     rcx, rdx
0x18004827b  setnz   dl
0x18004827e  mov     rax, [rax+20h]
0x180048282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048287  mov     [rbp+57h+var_58], 0
0x18004828f  lea     rax, [rbp+57h+var_50]
0x180048293  mov     [rbp+57h+arg_0], rax
0x180048297  mov     rdi, [rdi+8]
0x18004829b  add     rdi, 160h
0x1800482a2  mov     [rbp+57h+arg_10], rdi
0x1800482a6  mov     rcx, rdi
0x1800482a9  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1800482af  nop
0x1800482b0  mov     rcx, [rbp+57h+var_18]
0x1800482b4  test    rcx, rcx
0x1800482b7  jnz     short loc_1800482C0
0x1800482b9  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800482bf  int     3; Trap to Debugger
0x1800482c0  mov     rax, [rcx]
0x1800482c3  mov     rax, [rax+10h]
0x1800482c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482cc  mov     sil, al
0x1800482cf  mov     rcx, rdi
0x1800482d2  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x1800482d8  nop
0x1800482d9  mov     rcx, [rbp+57h+var_18]
0x1800482dd  test    rcx, rcx
0x1800482e0  jz      short loc_180048300
0x1800482e2  mov     rax, [rcx]
0x1800482e5  lea     rdx, [rbp+57h+var_50]
0x1800482e9  cmp     rcx, rdx
0x1800482ec  setnz   dl
0x1800482ef  mov     rax, [rax+20h]
0x1800482f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f8  mov     [rbp+57h+var_18], 0
0x180048300  mov     [rbx+170h], sil
0x180048307  lea     rdi, [rbx+20h]
0x18004830b  mov     rcx, rdi; this
0x18004830e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180048313  mov     eax, [rbx+8]
0x180048316  mov     rcx, rdi; _Mtx_t
0x180048319  cmp     eax, 4
0x18004831c  jnz     short loc_180048326
0x18004831e  call    cs:__imp__Mtx_unlock
0x180048324  jmp     short loc_180048371
0x180048326  mov     dword ptr [rbx+8], 3
0x18004832d  call    cs:__imp__Mtx_unlock
0x180048333  lea     rdi, [rbx+88h]
0x18004833a  lea     rcx, [rdi+48h]; this
0x18004833e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180048343  cmp     dword ptr [rdi+0B0h], 2
0x18004834a  jge     short loc_180048356
0x18004834c  mov     dword ptr [rdi+0B0h], 2
0x180048356  mov     rcx, rdi; _Cnd_t
0x180048359  call    cs:__imp__Cnd_broadcast
0x18004835f  lea     rcx, [rdi+48h]; _Mtx_t
0x180048363  call    cs:__imp__Mtx_unlock
0x180048369  mov     rcx, rbx; this
0x18004836c  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x180048371  mov     rbx, [rsp+0B0h+arg_18]
0x180048379  add     rsp, 0A0h
0x180048380  pop     rdi
0x180048381  pop     rsi
0x180048382  pop     rbp
0x180048383  retn
```
