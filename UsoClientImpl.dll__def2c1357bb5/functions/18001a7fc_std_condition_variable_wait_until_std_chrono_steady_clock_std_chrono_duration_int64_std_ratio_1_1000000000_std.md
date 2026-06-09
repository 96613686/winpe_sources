# std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)

- ea: `0x18001a7fc`
- end: `0x18001a8c5`
- name: `??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800105d8`
- `0x1800120a0`
- `0x180019598`

## callees

- `0x18001a7fc`
- `0x18002eadc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a897`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001a88f`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18001a88f`

## pseudocode

```c
__int64 __fastcall std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
        RTL_CONDITION_VARIABLE *a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rdi
  BOOL v9; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  while ( 1 )
  {
    std::chrono::steady_clock::now(&v12);
    if ( *a3 == v12 || *a3 < v12 )
      break;
    v6 = *a3 - v12;
    if ( v6 <= 86400000000000LL )
    {
      v7 = v6 / 1000000;
      if ( 1000000 * (v6 / 1000000) < v6 )
        LODWORD(v7) = v7 + 1;
    }
    else
    {
      LODWORD(v7) = 86400000;
    }
    v8 = *a2;
    --*(_DWORD *)(v8 + 76);
    *(_DWORD *)(v8 + 72) = -1;
    v9 = SleepConditionVariableSRW(a1 + 1, (PSRWLOCK)(v8 + 16), v7, 0);
    CurrentThreadId = GetCurrentThreadId();
    ++*(_DWORD *)(v8 + 76);
    *(_DWORD *)(v8 + 72) = CurrentThreadId;
    if ( v9 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001a7fc  mov     [rsp+arg_0], rbx
0x18001a801  push    rbp
0x18001a802  push    rsi
0x18001a803  push    rdi
0x18001a804  push    r14
0x18001a806  push    r15
0x18001a808  sub     rsp, 20h
0x18001a80c  mov     rsi, r8
0x18001a80f  mov     r14, rdx
0x18001a812  mov     rbp, rcx
0x18001a815  mov     r15, 4E94914F0000h
0x18001a81f  lea     rcx, [rsp+48h+arg_10]
0x18001a824  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18001a829  mov     r9, [rsi]
0x18001a82c  mov     rax, [rsp+48h+arg_10]
0x18001a831  cmp     r9, rax
0x18001a834  jz      short loc_18001A8AF
0x18001a836  jl      short loc_18001A8AF
0x18001a838  sub     r9, rax
0x18001a83b  cmp     r9, r15
0x18001a83e  jz      short loc_18001A84A
0x18001a840  jl      short loc_18001A84A
0x18001a842  mov     r8d, 5265C00h
0x18001a848  jmp     short loc_18001A877
0x18001a84a  mov     rax, 431BDE82D7B634DBh
0x18001a854  imul    r9
0x18001a857  mov     r8, rdx
0x18001a85a  sar     r8, 12h
0x18001a85e  mov     rax, r8
0x18001a861  shr     rax, 3Fh
0x18001a865  add     r8, rax
0x18001a868  imul    rax, r8, 0F4240h
0x18001a86f  cmp     rax, r9
0x18001a872  jge     short loc_18001A877
0x18001a874  inc     r8; dwMilliseconds
0x18001a877  mov     rdi, [r14]
0x18001a87a  lea     rcx, [rbp+8]; ConditionVariable
0x18001a87e  xor     r9d, r9d; Flags
0x18001a881  dec     dword ptr [rdi+4Ch]
0x18001a884  lea     rdx, [rdi+10h]; SRWLock
0x18001a888  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x18001a88f  call    cs:__imp_SleepConditionVariableSRW
0x18001a895  mov     ebx, eax
0x18001a897  call    cs:__imp_GetCurrentThreadId
0x18001a89d  inc     dword ptr [rdi+4Ch]
0x18001a8a0  mov     [rdi+48h], eax
0x18001a8a3  test    ebx, ebx
0x18001a8a5  jz      loc_18001A81F
0x18001a8ab  xor     eax, eax
0x18001a8ad  jmp     short loc_18001A8B4
0x18001a8af  mov     eax, 1
0x18001a8b4  mov     rbx, [rsp+48h+arg_0]
0x18001a8b9  add     rsp, 20h
0x18001a8bd  pop     r15
0x18001a8bf  pop     r14
0x18001a8c1  pop     rdi
0x18001a8c2  pop     rsi
0x18001a8c3  pop     rbp
0x18001a8c4  retn
```
