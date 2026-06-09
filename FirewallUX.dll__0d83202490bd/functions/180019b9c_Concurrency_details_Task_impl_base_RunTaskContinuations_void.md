# Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)

- ea: `0x180019b9c`
- end: `0x180019d3d`
- name: `?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180019210`
- `0x18001956c`

## callees

- `0x1800021c0`
- `0x180019b9c`
- `0x180019d44`
- `0x180019e40`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180019c61`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180019c61`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_RunTaskContinuations(
        Concurrency::details::_Task_impl_base *this)
{
  __int64 v2; // rbx
  __int64 v3; // r14
  __int64 v4; // r8
  char *v5; // rdx
  char *v6; // rsi
  __int64 v7; // r8
  _QWORD *v8; // rdx
  volatile signed __int32 *v9; // rbx
  char *v10; // [rsp+30h] [rbp-39h] BYREF
  volatile signed __int32 *v11; // [rsp+38h] [rbp-31h]
  _QWORD v12[7]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v13; // [rsp+78h] [rbp+Fh]

  v2 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v2 )
  {
    do
    {
      v3 = *(_QWORD *)(v2 + 8);
      (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v2 + 16LL))(v2, &v10);
      if ( *((_DWORD *)this + 2) != 4 || *(_BYTE *)(v2 + 32) )
      {
        v6 = v10;
        Concurrency::details::_TaskEventLogger::_LogScheduleTask(
          (Concurrency::details::_TaskEventLogger *)(v10 + 352),
          1);
        v7 = *(unsigned int *)(v2 + 36);
        if ( *(_QWORD *)(v2 + 16) )
        {
          if ( (_DWORD)v7 != -1 )
          {
            *(_DWORD *)(v2 + 36) = 16;
            LODWORD(v7) = 16;
          }
          v12[0] = std::X$$V::Z::_Func_impl_no_alloc<`Concurrency::details::_Task_impl_base::_ScheduleContinuationTask'::`5'::_lambda_1_,Concurrency::details::AXPEAU_ContinuationTaskHandleBase * const>::`vftable';
          v12[1] = v2;
          v13 = v12;
          Concurrency::details::_ScheduleFuncWithAutoInline(v12, (unsigned int)v7);
          if ( v13 )
          {
            v8 = v12;
            LOBYTE(v8) = v13 != v12;
            (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 32LL))(v13, v8);
          }
        }
        else
        {
          Concurrency::details::_Task_impl_base::_ScheduleTask(v6, v2, v7);
        }
      }
      else
      {
        v5 = (char *)this + 16;
        if ( *((_QWORD *)this + 2) )
        {
          LOBYTE(v4) = 1;
        }
        else
        {
          v5 = v10 + 16;
          v4 = 0;
        }
        LOBYTE(v5) = 1;
        (*(void (__fastcall **)(char *, char *, __int64))(*(_QWORD *)v10 + 8LL))(v10, v5, v4);
        (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
      }
      v9 = v11;
      if ( v11 && !_InterlockedDecrement(v11 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( !_InterlockedDecrement(v9 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
      v2 = v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x180019b9c  push    rbp
0x180019b9e  push    rbx
0x180019b9f  push    rsi
0x180019ba0  push    rdi
0x180019ba1  push    r12
0x180019ba3  push    r14
0x180019ba5  lea     rbp, [rsp-2Fh]
0x180019baa  sub     rsp, 98h
0x180019bb1  mov     rax, cs:__security_cookie
0x180019bb8  xor     rax, rsp
0x180019bbb  mov     [rbp+57h+var_40], rax
0x180019bbf  mov     rdi, rcx
0x180019bc2  mov     rbx, [rcx+70h]
0x180019bc6  mov     qword ptr [rcx+70h], 0
0x180019bce  test    rbx, rbx
0x180019bd1  jz      loc_180019D21
0x180019bd7  or      r12d, 0FFFFFFFFh
0x180019bdb  mov     r14, [rbx+8]
0x180019bdf  mov     rax, [rbx]
0x180019be2  lea     rdx, [rbp+57h+var_90]
0x180019be6  mov     rcx, rbx
0x180019be9  mov     rax, [rax+10h]
0x180019bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bf2  nop
0x180019bf3  mov     eax, [rdi+8]
0x180019bf6  cmp     eax, 4
0x180019bf9  jnz     short loc_180019C54
0x180019bfb  cmp     byte ptr [rbx+20h], 0
0x180019bff  jnz     short loc_180019C54
0x180019c01  lea     rdx, [rdi+10h]
0x180019c05  mov     rcx, [rbp+57h+var_90]
0x180019c09  mov     rax, [rcx]
0x180019c0c  mov     rax, [rax+8]
0x180019c10  cmp     qword ptr [rdx], 0
0x180019c14  jz      short loc_180019C26
0x180019c16  mov     [rsp+0C0h+var_A0], rdx
0x180019c1b  mov     r9b, 1
0x180019c1e  mov     r8b, r9b
0x180019c21  mov     dl, r9b
0x180019c24  jmp     short loc_180019C37
0x180019c26  lea     rdx, [rcx+10h]
0x180019c2a  mov     [rsp+0C0h+var_A0], rdx
0x180019c2f  xor     r9d, r9d
0x180019c32  xor     r8d, r8d
0x180019c35  mov     dl, 1
0x180019c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c3c  mov     rax, [rbx]
0x180019c3f  mov     edx, 1
0x180019c44  mov     rcx, rbx
0x180019c47  mov     rax, [rax]
0x180019c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c4f  jmp     loc_180019CD5
0x180019c54  mov     rsi, [rbp+57h+var_90]
0x180019c58  lea     rcx, [rsi+160h]
0x180019c5f  mov     dl, 1
0x180019c61  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x180019c67  mov     r8d, [rbx+24h]
0x180019c6b  cmp     qword ptr [rbx+10h], 0
0x180019c70  jz      short loc_180019CC9
0x180019c72  cmp     r8d, r12d
0x180019c75  jz      short loc_180019C84
0x180019c77  mov     dword ptr [rbx+24h], 10h
0x180019c7e  mov     r8d, 10h
0x180019c84  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?4??_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@45@@Z@X$$V@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)'::`5'::_lambda_1_,void,>::`vftable'
0x180019c8b  mov     [rbp+57h+var_80], rax
0x180019c8f  mov     [rbp+57h+var_78], rbx
0x180019c93  lea     rax, [rbp+57h+var_80]
0x180019c97  mov     [rbp+57h+var_48], rax
0x180019c9b  mov     edx, r8d
0x180019c9e  lea     rcx, [rbp+57h+var_80]
0x180019ca2  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180019ca7  nop
0x180019ca8  mov     rcx, [rbp+57h+var_48]
0x180019cac  test    rcx, rcx
0x180019caf  jz      short loc_180019CD5
0x180019cb1  mov     rax, [rcx]
0x180019cb4  lea     rdx, [rbp+57h+var_80]
0x180019cb8  cmp     rcx, rdx
0x180019cbb  setnz   dl
0x180019cbe  mov     rax, [rax+20h]
0x180019cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc7  jmp     short loc_180019CD5
0x180019cc9  mov     rdx, rbx
0x180019ccc  mov     rcx, rsi
0x180019ccf  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x180019cd4  nop
0x180019cd5  mov     rbx, [rbp+57h+var_88]
0x180019cd9  test    rbx, rbx
0x180019cdc  jz      short loc_180019D15
0x180019cde  mov     eax, r12d
0x180019ce1  lock xadd [rbx+8], eax
0x180019ce6  add     eax, r12d
0x180019ce9  jnz     short loc_180019D15
0x180019ceb  mov     rax, [rbx]
0x180019cee  mov     rcx, rbx
0x180019cf1  mov     rax, [rax]
0x180019cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cf9  mov     eax, r12d
0x180019cfc  lock xadd [rbx+0Ch], eax
0x180019d01  add     eax, r12d
0x180019d04  jnz     short loc_180019D15
0x180019d06  mov     rax, [rbx]
0x180019d09  mov     rcx, rbx
0x180019d0c  mov     rax, [rax+8]
0x180019d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d15  mov     rbx, r14
0x180019d18  test    r14, r14
0x180019d1b  jnz     loc_180019BDB
0x180019d21  mov     rcx, [rbp+57h+var_40]
0x180019d25  xor     rcx, rsp; StackCookie
0x180019d28  call    __security_check_cookie
0x180019d2d  add     rsp, 98h
0x180019d34  pop     r14
0x180019d36  pop     r12
0x180019d38  pop     rdi
0x180019d39  pop     rsi
0x180019d3a  pop     rbx
0x180019d3b  pop     rbp
0x180019d3c  retn
```
