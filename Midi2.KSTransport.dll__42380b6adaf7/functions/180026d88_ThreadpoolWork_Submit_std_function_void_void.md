# ThreadpoolWork::Submit(std::function<void (void)>)

- ea: `0x180026d88`
- end: `0x180026e7e`
- name: `?Submit@ThreadpoolWork@@QEAAXV?$function@$$A6AXXZ@std@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026b64`

## callees

- `0x1800256d4`
- `0x180026d88`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026dac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026dac`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180026e32`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180026e32`

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
0x180026d88  mov     [rsp+arg_10], rbx
0x180026d8d  mov     [rsp+arg_18], rbp
0x180026d92  mov     [rsp+arg_8], rdx
0x180026d97  push    rsi
0x180026d98  push    rdi
0x180026d99  push    r14
0x180026d9b  sub     rsp, 20h
0x180026d9f  mov     rbx, rdx
0x180026da2  mov     r14, rcx
0x180026da5  lea     rbp, [rcx+8]
0x180026da9  mov     rcx, rbp; lpCriticalSection
0x180026dac  call    cs:__imp_EnterCriticalSection
0x180026db2  mov     [rsp+38h+arg_0], rbp
0x180026db7  cmp     qword ptr [r14], 0
0x180026dbb  jz      short loc_180026E39
0x180026dbd  mov     rsi, [r14+38h]
0x180026dc1  cmp     rsi, [r14+40h]
0x180026dc5  jz      short loc_180026E20
0x180026dc7  mov     qword ptr [rsi+38h], 0
0x180026dcf  mov     rcx, [rbx+38h]
0x180026dd3  test    rcx, rcx
0x180026dd6  jz      short loc_180026E19
0x180026dd8  cmp     rcx, rbx
0x180026ddb  jnz     short loc_180026E0D
0x180026ddd  mov     rax, [rcx]
0x180026de0  mov     rdx, rsi
0x180026de3  mov     rax, [rax+8]
0x180026de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dec  mov     [rsi+38h], rax
0x180026df0  mov     rcx, [rbx+38h]
0x180026df4  test    rcx, rcx
0x180026df7  jz      short loc_180026E19
0x180026df9  mov     rax, [rcx]
0x180026dfc  cmp     rcx, rbx
0x180026dff  setnz   dl
0x180026e02  mov     rax, [rax+20h]
0x180026e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e0b  jmp     short loc_180026E11
0x180026e0d  mov     [rsi+38h], rcx
0x180026e11  mov     qword ptr [rbx+38h], 0
0x180026e19  add     qword ptr [r14+38h], 40h ; '@'
0x180026e1e  jmp     short loc_180026E2F
0x180026e20  mov     r8, rbx
0x180026e23  mov     rdx, rsi
0x180026e26  lea     rcx, [r14+30h]
0x180026e2a  call    ??$_Emplace_reallocate@V?$function@$$A6AXXZ@std@@@?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAPEAV?$function@$$A6AXXZ@1@QEAV21@$$QEAV21@@Z; std::vector<std::function<void (void)>>::_Emplace_reallocate<std::function<void (void)>>(std::function<void (void)> * const,std::function<void (void)> &&)
0x180026e2f  mov     rcx, [r14]; pwk
0x180026e32  call    cs:__imp_SubmitThreadpoolWork
0x180026e38  nop
0x180026e39  test    rbp, rbp
0x180026e3c  jz      short loc_180026E48
0x180026e3e  mov     rcx, rbp; lpCriticalSection
0x180026e41  call    cs:__imp_LeaveCriticalSection
0x180026e47  nop
0x180026e48  mov     rcx, [rbx+38h]
0x180026e4c  test    rcx, rcx
0x180026e4f  jz      short loc_180026E6B
0x180026e51  mov     rax, [rcx]
0x180026e54  cmp     rcx, rbx
0x180026e57  setnz   dl
0x180026e5a  mov     rax, [rax+20h]
0x180026e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e63  mov     qword ptr [rbx+38h], 0
0x180026e6b  mov     rbx, [rsp+38h+arg_10]
0x180026e70  mov     rbp, [rsp+38h+arg_18]
0x180026e75  add     rsp, 20h
0x180026e79  pop     r14
0x180026e7b  pop     rdi
0x180026e7c  pop     rsi
0x180026e7d  retn
```
