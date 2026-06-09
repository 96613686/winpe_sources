# ThreadpoolWork::Submit(std::function<void (void)>)

- ea: `0x180047838`
- end: `0x18004792e`
- name: `?Submit@ThreadpoolWork@@QEAAXV?$function@$$A6AXXZ@std@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180047614`

## callees

- `0x1800461a8`
- `0x180047838`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004785c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004785c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800478f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800478f1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800478e2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800478e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ThreadpoolWork::Submit(__int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 v5; // rdx
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( *(_QWORD *)a1 )
  {
    v6 = *(_QWORD *)(a1 + 56);
    if ( v6 == *(_QWORD *)(a1 + 64) )
    {
      std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)>>(
        a1 + 48,
        *(_QWORD *)(a1 + 56),
        a2);
      goto LABEL_11;
    }
    *(_QWORD *)(v6 + 56) = 0;
    v7 = *(_QWORD *)(a2 + 56);
    if ( v7 )
    {
      if ( v7 != a2 )
      {
        *(_QWORD *)(v6 + 56) = v7;
        goto LABEL_8;
      }
      *(_QWORD *)(v6 + 56) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, v6);
      v9 = *(_QWORD *)(a2 + 56);
      if ( v9 )
      {
        LOBYTE(v8) = v9 != a2;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 32LL))(v9, v8);
LABEL_8:
        *(_QWORD *)(a2 + 56) = 0;
      }
    }
    *(_QWORD *)(a1 + 56) += 64LL;
LABEL_11:
    SubmitThreadpoolWork(*(PTP_WORK *)a1);
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  v10 = *(_QWORD *)(a2 + 56);
  if ( v10 )
  {
    LOBYTE(v5) = v10 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, v5);
    *(_QWORD *)(a2 + 56) = 0;
  }
}

```

## disassembly

```asm
0x180047838  mov     [rsp+arg_10], rbx
0x18004783d  mov     [rsp+arg_18], rbp
0x180047842  mov     [rsp+arg_8], rdx
0x180047847  push    rsi
0x180047848  push    rdi
0x180047849  push    r14
0x18004784b  sub     rsp, 20h
0x18004784f  mov     rbx, rdx
0x180047852  mov     r14, rcx
0x180047855  lea     rbp, [rcx+8]
0x180047859  mov     rcx, rbp; lpCriticalSection
0x18004785c  call    cs:__imp_EnterCriticalSection
0x180047862  mov     [rsp+38h+arg_0], rbp
0x180047867  cmp     qword ptr [r14], 0
0x18004786b  jz      short loc_1800478E9
0x18004786d  mov     rsi, [r14+38h]
0x180047871  cmp     rsi, [r14+40h]
0x180047875  jz      short loc_1800478D0
0x180047877  mov     qword ptr [rsi+38h], 0
0x18004787f  mov     rcx, [rbx+38h]
0x180047883  test    rcx, rcx
0x180047886  jz      short loc_1800478C9
0x180047888  cmp     rcx, rbx
0x18004788b  jnz     short loc_1800478BD
0x18004788d  mov     rax, [rcx]
0x180047890  mov     rdx, rsi
0x180047893  mov     rax, [rax+8]
0x180047897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004789c  mov     [rsi+38h], rax
0x1800478a0  mov     rcx, [rbx+38h]
0x1800478a4  test    rcx, rcx
0x1800478a7  jz      short loc_1800478C9
0x1800478a9  mov     rax, [rcx]
0x1800478ac  cmp     rcx, rbx
0x1800478af  setnz   dl
0x1800478b2  mov     rax, [rax+20h]
0x1800478b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478bb  jmp     short loc_1800478C1
0x1800478bd  mov     [rsi+38h], rcx
0x1800478c1  mov     qword ptr [rbx+38h], 0
0x1800478c9  add     qword ptr [r14+38h], 40h ; '@'
0x1800478ce  jmp     short loc_1800478DF
0x1800478d0  mov     r8, rbx
0x1800478d3  mov     rdx, rsi
0x1800478d6  lea     rcx, [r14+30h]
0x1800478da  call    ??$_Emplace_reallocate@V?$function@$$A6AXXZ@std@@@?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAPEAV?$function@$$A6AXXZ@1@QEAV21@$$QEAV21@@Z; std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)>>(std::function<void (void)> * const,std::function<void (void)> &&)
0x1800478df  mov     rcx, [r14]; pwk
0x1800478e2  call    cs:__imp_SubmitThreadpoolWork
0x1800478e8  nop
0x1800478e9  test    rbp, rbp
0x1800478ec  jz      short loc_1800478F8
0x1800478ee  mov     rcx, rbp; lpCriticalSection
0x1800478f1  call    cs:__imp_LeaveCriticalSection
0x1800478f7  nop
0x1800478f8  mov     rcx, [rbx+38h]
0x1800478fc  test    rcx, rcx
0x1800478ff  jz      short loc_18004791B
0x180047901  mov     rax, [rcx]
0x180047904  cmp     rcx, rbx
0x180047907  setnz   dl
0x18004790a  mov     rax, [rax+20h]
0x18004790e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047913  mov     qword ptr [rbx+38h], 0
0x18004791b  mov     rbx, [rsp+38h+arg_10]
0x180047920  mov     rbp, [rsp+38h+arg_18]
0x180047925  add     rsp, 20h
0x180047929  pop     r14
0x18004792b  pop     rdi
0x18004792c  pop     rsi
0x18004792d  retn
```
