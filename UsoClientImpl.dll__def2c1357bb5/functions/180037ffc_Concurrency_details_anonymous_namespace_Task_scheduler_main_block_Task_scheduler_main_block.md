# Concurrency::details::_anonymous_namespace_::_Task_scheduler_main_block::__Task_scheduler_main_block

- ea: `0x180037ffc`
- end: `0x1800380c4`
- name: `Concurrency::details::_anonymous_namespace_::_Task_scheduler_main_block::__Task_scheduler_main_block`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180062d00`

## callees

- `0x180036d78`
- `0x180036ed8`
- `0x180037ffc`
- `0x1800563c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038092`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038092`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038058`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18003804e`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18003804e`

## pseudocode

```c
void Concurrency::details::_anonymous_namespace_::_Task_scheduler_main_block::__Task_scheduler_main_block()
{
  int v0; // eax

  if ( (unsigned int)mtx_do_lock(qword_18009D270) )
    std::_Throw_Cpp_error(5);
  v0 = dword_18009D2BC;
  if ( dword_18009D2BC == 0x7FFFFFFF )
  {
    dword_18009D2BC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  while ( qword_18009F9C0 )
  {
    dword_18009D2B8 = -1;
    dword_18009D2BC = v0 - 1;
    if ( !SleepConditionVariableSRW(&ConditionVariable, &stru_18009D280, 0xFFFFFFFF, 0) )
      abort();
    dword_18009D2B8 = GetCurrentThreadId();
    v0 = dword_18009D2BC + 1;
  }
  dword_18009D2BC = v0 - 1;
  if ( v0 == 1 )
  {
    dword_18009D2B8 = -1;
    ReleaseSRWLockExclusive(&stru_18009D280);
  }
}

```

## disassembly

```asm
0x180037ffc  sub     rsp, 28h
0x180038000  lea     rcx, qword_18009D270
0x180038007  call    mtx_do_lock
0x18003800c  test    eax, eax
0x18003800e  jnz     loc_18003809E
0x180038014  mov     eax, cs:dword_18009D2BC
0x18003801a  cmp     eax, 7FFFFFFFh
0x18003801f  jz      loc_1800380A9
0x180038025  jmp     short loc_18003806C
0x180038027  mov     cs:dword_18009D2B8, 0FFFFFFFFh
0x180038031  dec     eax
0x180038033  mov     cs:dword_18009D2BC, eax
0x180038039  xor     r9d, r9d; Flags
0x18003803c  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180038040  lea     rdx, stru_18009D280; SRWLock
0x180038047  lea     rcx, ConditionVariable; ConditionVariable
0x18003804e  call    cs:__imp_SleepConditionVariableSRW
0x180038054  test    eax, eax
0x180038056  jz      short loc_1800380BE
0x180038058  call    cs:__imp_GetCurrentThreadId
0x18003805e  mov     cs:dword_18009D2B8, eax
0x180038064  mov     eax, cs:dword_18009D2BC
0x18003806a  inc     eax
0x18003806c  cmp     cs:qword_18009F9C0, 0
0x180038074  jnz     short loc_180038027
0x180038076  sub     eax, 1
0x180038079  mov     cs:dword_18009D2BC, eax
0x18003807f  jnz     short loc_180038099
0x180038081  mov     cs:dword_18009D2B8, 0FFFFFFFFh
0x18003808b  lea     rcx, stru_18009D280; SRWLock
0x180038092  call    cs:__imp_ReleaseSRWLockExclusive
0x180038098  nop
0x180038099  add     rsp, 28h
0x18003809d  retn
0x18003809e  mov     ecx, 5; int
0x1800380a3  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800380a9  mov     cs:dword_18009D2BC, 7FFFFFFEh
0x1800380b3  mov     ecx, 6; int
0x1800380b8  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800380be  call    abort
```
