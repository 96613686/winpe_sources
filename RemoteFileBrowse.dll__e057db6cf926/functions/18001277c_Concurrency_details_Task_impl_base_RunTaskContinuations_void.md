# Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)

- ea: `0x18001277c`
- end: `0x18001291d`
- name: `?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ`
- size: `417`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180011e30`
- `0x18001213c`

## callees

- `0x180002030`
- `0x18001277c`
- `0x180012924`
- `0x180012a20`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180012841`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x180012841`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
          v12[0] = &std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable';
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
0x18001277c  push    rbp
0x18001277e  push    rbx
0x18001277f  push    rsi
0x180012780  push    rdi
0x180012781  push    r12
0x180012783  push    r14
0x180012785  lea     rbp, [rsp-2Fh]
0x18001278a  sub     rsp, 98h
0x180012791  mov     rax, cs:__security_cookie
0x180012798  xor     rax, rsp
0x18001279b  mov     [rbp+57h+var_40], rax
0x18001279f  mov     rdi, rcx
0x1800127a2  mov     rbx, [rcx+70h]
0x1800127a6  mov     qword ptr [rcx+70h], 0
0x1800127ae  test    rbx, rbx
0x1800127b1  jz      loc_180012901
0x1800127b7  or      r12d, 0FFFFFFFFh
0x1800127bb  mov     r14, [rbx+8]
0x1800127bf  mov     rax, [rbx]
0x1800127c2  lea     rdx, [rbp+57h+var_90]
0x1800127c6  mov     rcx, rbx
0x1800127c9  mov     rax, [rax+10h]
0x1800127cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127d2  nop
0x1800127d3  mov     eax, [rdi+8]
0x1800127d6  cmp     eax, 4
0x1800127d9  jnz     short loc_180012834
0x1800127db  cmp     byte ptr [rbx+20h], 0
0x1800127df  jnz     short loc_180012834
0x1800127e1  lea     rdx, [rdi+10h]
0x1800127e5  mov     rcx, [rbp+57h+var_90]
0x1800127e9  mov     rax, [rcx]
0x1800127ec  mov     rax, [rax+8]
0x1800127f0  cmp     qword ptr [rdx], 0
0x1800127f4  jz      short loc_180012806
0x1800127f6  mov     [rsp+0C0h+var_A0], rdx
0x1800127fb  mov     r9b, 1
0x1800127fe  mov     r8b, r9b
0x180012801  mov     dl, r9b
0x180012804  jmp     short loc_180012817
0x180012806  lea     rdx, [rcx+10h]
0x18001280a  mov     [rsp+0C0h+var_A0], rdx
0x18001280f  xor     r9d, r9d
0x180012812  xor     r8d, r8d
0x180012815  mov     dl, 1
0x180012817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001281c  mov     rax, [rbx]
0x18001281f  mov     edx, 1
0x180012824  mov     rcx, rbx
0x180012827  mov     rax, [rax]
0x18001282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001282f  jmp     loc_1800128B5
0x180012834  mov     rsi, [rbp+57h+var_90]
0x180012838  lea     rcx, [rsi+160h]
0x18001283f  mov     dl, 1
0x180012841  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x180012847  mov     r8d, [rbx+24h]
0x18001284b  cmp     qword ptr [rbx+10h], 0
0x180012850  jz      short loc_1800128A9
0x180012852  cmp     r8d, r12d
0x180012855  jz      short loc_180012864
0x180012857  mov     dword ptr [rbx+24h], 10h
0x18001285e  mov     r8d, 10h
0x180012864  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2fa3e3d11fb97352afa77a4a13bfb543_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2fa3e3d11fb97352afa77a4a13bfb543_,void,>::`vftable'
0x18001286b  mov     [rbp+57h+var_80], rax
0x18001286f  mov     [rbp+57h+var_78], rbx
0x180012873  lea     rax, [rbp+57h+var_80]
0x180012877  mov     [rbp+57h+var_48], rax
0x18001287b  mov     edx, r8d
0x18001287e  lea     rcx, [rbp+57h+var_80]
0x180012882  call    ?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z; Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)
0x180012887  nop
0x180012888  mov     rcx, [rbp+57h+var_48]
0x18001288c  test    rcx, rcx
0x18001288f  jz      short loc_1800128B5
0x180012891  mov     rax, [rcx]
0x180012894  lea     rdx, [rbp+57h+var_80]
0x180012898  cmp     rcx, rdx
0x18001289b  setnz   dl
0x18001289e  mov     rax, [rax+20h]
0x1800128a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a7  jmp     short loc_1800128B5
0x1800128a9  mov     rdx, rbx
0x1800128ac  mov     rcx, rsi
0x1800128af  call    ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
0x1800128b4  nop
0x1800128b5  mov     rbx, [rbp+57h+var_88]
0x1800128b9  test    rbx, rbx
0x1800128bc  jz      short loc_1800128F5
0x1800128be  mov     eax, r12d
0x1800128c1  lock xadd [rbx+8], eax
0x1800128c6  add     eax, r12d
0x1800128c9  jnz     short loc_1800128F5
0x1800128cb  mov     rax, [rbx]
0x1800128ce  mov     rcx, rbx
0x1800128d1  mov     rax, [rax]
0x1800128d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128d9  mov     eax, r12d
0x1800128dc  lock xadd [rbx+0Ch], eax
0x1800128e1  add     eax, r12d
0x1800128e4  jnz     short loc_1800128F5
0x1800128e6  mov     rax, [rbx]
0x1800128e9  mov     rcx, rbx
0x1800128ec  mov     rax, [rax+8]
0x1800128f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128f5  mov     rbx, r14
0x1800128f8  test    r14, r14
0x1800128fb  jnz     loc_1800127BB
0x180012901  mov     rcx, [rbp+57h+var_40]
0x180012905  xor     rcx, rsp; StackCookie
0x180012908  call    __security_check_cookie
0x18001290d  add     rsp, 98h
0x180012914  pop     r14
0x180012916  pop     r12
0x180012918  pop     rdi
0x180012919  pop     rsi
0x18001291a  pop     rbx
0x18001291b  pop     rbp
0x18001291c  retn
```
