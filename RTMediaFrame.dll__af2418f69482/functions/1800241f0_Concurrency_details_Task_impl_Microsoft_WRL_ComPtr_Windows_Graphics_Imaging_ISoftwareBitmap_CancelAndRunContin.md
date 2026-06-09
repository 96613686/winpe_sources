# Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_CancelAndRunContinuations(bool,bool,bool,std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)

- ea: `0x1800241f0`
- end: `0x1800243ab`
- name: `?_CancelAndRunContinuations@?$_Task_impl@V?$ComPtr@UISoftwareBitmap@Imaging@Graphics@Windows@@@WRL@Microsoft@@@details@Concurrency@@UEAA_N_N00AEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@@Z`
- size: `443`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001df10`
- `0x1800241f0`
- `0x1800243b4`
- `0x1800243e0`
- `0x18002448c`
- `0x180026920`
- `0x180032350`
- `0x180052010`

## import_xrefs

- `msvcp_win!_Cnd_broadcast` at `0x180024303`
- `msvcp_win!_Cnd_broadcast` at `0x180024303`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800242a6`
- `msvcp_win!?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800242a6`
- `msvcp_win!_Mtx_unlock` at `0x1800242b0`
- `msvcp_win!_Mtx_unlock` at `0x18002430d`
- `msvcp_win!_Mtx_unlock` at `0x180024386`
- `msvcp_win!_Mtx_unlock` at `0x1800242b0`
- `msvcp_win!_Mtx_unlock` at `0x18002430d`
- `msvcp_win!_Mtx_unlock` at `0x180024386`

## pseudocode

```c
char __fastcall Concurrency::details::_Task_impl<Microsoft::WRL::ComPtr<Windows::Graphics::Imaging::ISoftwareBitmap>>::_CancelAndRunContinuations(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  struct _Mtx_internal_imp_t *v8; // rsi
  int v9; // eax
  int v10; // ebx
  int v11; // ebx
  _QWORD *v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v15[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v16; // [rsp+68h] [rbp-50h]

  v8 = (struct _Mtx_internal_imp_t *)(a1 + 32);
  v14 = a1 + 32;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 32));
  v9 = *(_DWORD *)(a1 + 8);
  if ( !a3 )
  {
    if ( v9 != 3 && *(_DWORD *)(a1 + 8) != 4 && (*(_DWORD *)(a1 + 8) != 2 || a2) )
      goto LABEL_8;
LABEL_23:
    _Mtx_unlock(v8);
    return 0;
  }
  if ( v9 == 4 )
    goto LABEL_23;
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(a1 + 16, a5);
LABEL_8:
  if ( a2 )
  {
    *(_DWORD *)(a1 + 8) = 4;
    v10 = 1;
  }
  else
  {
    v10 = 0;
    if ( *(_DWORD *)(a1 + 8) == 1 )
      v10 = 2;
    *(_DWORD *)(a1 + 8) = 2;
    Concurrency::details::_TaskEventLogger::_LogCancelTask((Concurrency::details::_TaskEventLogger *)(a1 + 352));
  }
  _Mtx_unlock(v8);
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      if ( *(_QWORD *)(a1 + 432) )
        std::_Func_class<void,>::operator()(a1 + 376);
    }
  }
  else
  {
    std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 208));
    if ( *(int *)(a1 + 312) < 2 )
      *(_DWORD *)(a1 + 312) = 2;
    _Cnd_broadcast((_Cnd_t)(a1 + 136));
    _Mtx_unlock((_Mtx_t)(a1 + 208));
    if ( *(_QWORD *)(a1 + 112) )
    {
      v16 = 0;
      v15[0] = &std::_Func_impl_no_alloc<_lambda_64759b1c64d06d85b31a2d526b42d9d4_,void,>::`vftable';
      v15[1] = *(_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                            &v14,
                            a1);
      v16 = v15;
      Concurrency::details::_ScheduleFuncWithAutoInline(v15, 16);
      if ( v16 )
      {
        v12 = v15;
        LOBYTE(v12) = v16 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v12);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800241f0  push    rbx
0x1800241f2  push    rbp
0x1800241f3  push    rsi
0x1800241f4  push    rdi
0x1800241f5  push    r12
0x1800241f7  push    r14
0x1800241f9  sub     rsp, 88h
0x180024200  mov     rax, cs:__security_cookie
0x180024207  xor     rax, rsp
0x18002420a  mov     [rsp+0B8h+var_48], rax
0x18002420f  mov     bl, r8b
0x180024212  mov     bpl, dl
0x180024215  mov     rdi, rcx
0x180024218  mov     r14, [rsp+0B8h+arg_20]
0x180024220  lea     rsi, [rcx+20h]
0x180024224  mov     [rsp+0B8h+var_98], rsi
0x180024229  mov     rcx, rsi; this
0x18002422c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180024231  nop
0x180024232  mov     r12d, 2
0x180024238  mov     eax, [rdi+8]
0x18002423b  test    bl, bl
0x18002423d  jz      short loc_180024256
0x18002423f  cmp     eax, 4
0x180024242  jz      loc_180024383
0x180024248  lea     rcx, [rdi+10h]
0x18002424c  mov     rdx, r14
0x18002424f  call    ??4?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Concurrency::details::_ExceptionHolder>::operator=(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &)
0x180024254  jmp     short loc_18002427C
0x180024256  cmp     eax, 3
0x180024259  jz      loc_180024383
0x18002425f  mov     eax, [rdi+8]
0x180024262  cmp     eax, 4
0x180024265  jz      loc_180024383
0x18002426b  mov     eax, [rdi+8]
0x18002426e  cmp     eax, r12d
0x180024271  jnz     short loc_18002427C
0x180024273  test    bpl, bpl
0x180024276  jz      loc_180024383
0x18002427c  test    bpl, bpl
0x18002427f  jz      short loc_18002428F
0x180024281  mov     dword ptr [rdi+8], 4
0x180024288  mov     ebx, 1
0x18002428d  jmp     short loc_1800242AD
0x18002428f  mov     eax, [rdi+8]
0x180024292  xor     ebx, ebx
0x180024294  cmp     eax, 1
0x180024297  cmovz   ebx, r12d
0x18002429b  mov     [rdi+8], r12d
0x18002429f  lea     rcx, [rdi+160h]
0x1800242a6  call    cs:__imp_?_LogCancelTask@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogCancelTask(void)
0x1800242ac  nop
0x1800242ad  mov     rcx, rsi; _Mtx_t
0x1800242b0  call    cs:__imp__Mtx_unlock
0x1800242b6  sub     ebx, 1
0x1800242b9  jz      short loc_1800242E0
0x1800242bb  cmp     ebx, 1
0x1800242be  jnz     loc_18002437F
0x1800242c4  lea     rcx, [rdi+178h]
0x1800242cb  cmp     qword ptr [rcx+38h], 0
0x1800242d0  jz      loc_18002437F
0x1800242d6  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1800242db  jmp     loc_18002437F
0x1800242e0  lea     rbx, [rdi+88h]
0x1800242e7  lea     rcx, [rbx+48h]; this
0x1800242eb  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800242f0  cmp     [rbx+0B0h], r12d
0x1800242f7  jge     short loc_180024300
0x1800242f9  mov     [rbx+0B0h], r12d
0x180024300  mov     rcx, rbx; _Cnd_t
0x180024303  call    cs:__imp__Cnd_broadcast
0x180024309  lea     rcx, [rbx+48h]; _Mtx_t
0x18002430d  call    cs:__imp__Mtx_unlock
0x180024313  cmp     qword ptr [rdi+70h], 0
0x180024318  jz      short loc_18002437F
0x18002431a  mov     [rsp+0B8h+var_50], 0
0x180024323  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_64759b1c64d06d85b31a2d526b42d9d4_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_64759b1c64d06d85b31a2d526b42d9d4_,void,>::`vftable'
0x18002432a  mov     [rsp+0B8h+var_88], rax
0x18002432f  mov     rdx, rdi
0x180024332  lea     rcx, [rsp+0B8h+var_98]
0x180024337  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18002433c  mov     rcx, [rax]
0x18002433f  mov     [rsp+0B8h+var_80], rcx
0x180024344  lea     rax, [rsp+0B8h+var_88]
0x180024349  mov     [rsp+0B8h+var_50], rax
0x18002434e  mov     edx, 10h
0x180024353  lea     rcx, [rsp+0B8h+var_88]
0x180024358  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x18002435d  nop
0x18002435e  mov     rcx, [rsp+0B8h+var_50]
0x180024363  test    rcx, rcx
0x180024366  jz      short loc_18002437F
0x180024368  mov     rax, [rcx]
0x18002436b  lea     rdx, [rsp+0B8h+var_88]
0x180024370  cmp     rcx, rdx
0x180024373  setnz   dl
0x180024376  mov     rax, [rax+20h]
0x18002437a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002437f  mov     al, 1
0x180024381  jmp     short loc_18002438E
0x180024383  mov     rcx, rsi; _Mtx_t
0x180024386  call    cs:__imp__Mtx_unlock
0x18002438c  xor     al, al
0x18002438e  mov     rcx, [rsp+0B8h+var_48]
0x180024393  xor     rcx, rsp; StackCookie
0x180024396  call    __security_check_cookie
0x18002439b  add     rsp, 88h
0x1800243a2  pop     r14
0x1800243a4  pop     r12
0x1800243a6  pop     rdi
0x1800243a7  pop     rsi
0x1800243a8  pop     rbp
0x1800243a9  pop     rbx
0x1800243aa  retn
```
