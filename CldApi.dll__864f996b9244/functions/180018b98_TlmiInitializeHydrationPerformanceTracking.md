# TlmiInitializeHydrationPerformanceTracking

- ea: `0x180018b98`
- end: `0x180018cda`
- name: `TlmiInitializeHydrationPerformanceTracking`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011e18`

## callees

- `0x180018b98`
- `0x18001a43c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018bb3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018bb3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018cce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018cce`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180018c62`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180018c8d`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180018c62`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180018c8d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180018cb2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180018cb2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180018be6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180018be6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018c06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018c28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018c06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018c28`

## pseudocode

```c
char TlmiInitializeHydrationPerformanceTracking()
{
  char result; // al

  result = byte_180028A58;
  if ( !byte_180028A58 )
  {
    RtlAcquireSRWLockExclusive(&qword_180028A60);
    if ( !byte_180028A58 )
    {
      qword_180028B58 = CreateThread(0, 0, TlmiHydrationPerformanceWorker, 0, 4u, 0);
      if ( qword_180028B58 )
      {
        hEvent = CreateEventW(0, 0, 0, 0);
        if ( hEvent )
        {
          qword_180028B50 = CreateEventW(0, 1, 0, 0);
          if ( qword_180028B50 )
          {
            RtlInitializeGenericTableAvl(
              &stru_180028A70,
              TlmiHPTableCompare,
              CfpOplockCompletionKeyTableAllocate,
              CfpSyncRootTableFree,
              0);
            RtlInitializeGenericTableAvl(
              &stru_180028AD8,
              TlmiHPTableCompare,
              CfpOplockCompletionKeyTableAllocate,
              CfpSyncRootTableFree,
              0);
            qword_180028A68 = &stru_180028A70;
            dword_180028B40 = 0;
            byte_180028A58 = 1;
            ResumeThread(qword_180028B58);
          }
        }
      }
    }
    if ( !byte_180028A58 )
      TlmiUninitializeHydrationPerformanceTracking();
    return RtlReleaseSRWLockExclusive(&qword_180028A60);
  }
  return result;
}

```

## disassembly

```asm
0x180018b98  push    rbx
0x180018b9a  sub     rsp, 30h
0x180018b9e  mov     al, cs:byte_180028A58
0x180018ba4  test    al, al
0x180018ba6  jnz     loc_180018CD4
0x180018bac  lea     rcx, qword_180028A60
0x180018bb3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180018bb9  mov     al, cs:byte_180028A58
0x180018bbf  test    al, al
0x180018bc1  jnz     loc_180018CB8
0x180018bc7  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180018bd0  lea     r8, TlmiHydrationPerformanceWorker; lpStartAddress
0x180018bd7  xor     r9d, r9d; lpParameter
0x180018bda  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x180018be2  xor     edx, edx; dwStackSize
0x180018be4  xor     ecx, ecx; lpThreadAttributes
0x180018be6  call    cs:__imp_CreateThread
0x180018bec  mov     cs:qword_180028B58, rax
0x180018bf3  test    rax, rax
0x180018bf6  jz      loc_180018CB8
0x180018bfc  xor     r9d, r9d; lpName
0x180018bff  xor     r8d, r8d; bInitialState
0x180018c02  xor     edx, edx; bManualReset
0x180018c04  xor     ecx, ecx; lpEventAttributes
0x180018c06  call    cs:__imp_CreateEventW
0x180018c0c  mov     cs:hEvent, rax
0x180018c13  test    rax, rax
0x180018c16  jz      loc_180018CB8
0x180018c1c  xor     r9d, r9d; lpName
0x180018c1f  xor     r8d, r8d; bInitialState
0x180018c22  xor     ecx, ecx; lpEventAttributes
0x180018c24  lea     edx, [r9+1]; bManualReset
0x180018c28  call    cs:__imp_CreateEventW
0x180018c2e  mov     cs:qword_180028B50, rax
0x180018c35  test    rax, rax
0x180018c38  jz      short loc_180018CB8
0x180018c3a  lea     rbx, stru_180028A70
0x180018c41  mov     qword ptr [rsp+38h+dwCreationFlags], 0; TableContext
0x180018c4a  mov     rcx, rbx; Table
0x180018c4d  lea     r9, CfpSyncRootTableFree; FreeRoutine
0x180018c54  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180018c5b  lea     rdx, TlmiHPTableCompare; CompareRoutine
0x180018c62  call    cs:__imp_RtlInitializeGenericTableAvl
0x180018c68  lea     r9, CfpSyncRootTableFree; FreeRoutine
0x180018c6f  mov     qword ptr [rsp+38h+dwCreationFlags], 0; TableContext
0x180018c78  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180018c7f  lea     rdx, TlmiHPTableCompare; CompareRoutine
0x180018c86  lea     rcx, stru_180028AD8; Table
0x180018c8d  call    cs:__imp_RtlInitializeGenericTableAvl
0x180018c93  mov     rcx, cs:qword_180028B58; hThread
0x180018c9a  mov     cs:qword_180028A68, rbx
0x180018ca1  mov     cs:dword_180028B40, 0
0x180018cab  mov     cs:byte_180028A58, 1
0x180018cb2  call    cs:__imp_ResumeThread
0x180018cb8  mov     al, cs:byte_180028A58
0x180018cbe  test    al, al
0x180018cc0  jnz     short loc_180018CC7
0x180018cc2  call    TlmiUninitializeHydrationPerformanceTracking
0x180018cc7  lea     rcx, qword_180028A60
0x180018cce  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018cd4  add     rsp, 30h
0x180018cd8  pop     rbx
0x180018cd9  retn
```
