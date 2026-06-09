# TlmiInitializeRunawayHydrationDetection

- ea: `0x180018e24`
- end: `0x180018f40`
- name: `TlmiInitializeRunawayHydrationDetection`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011e18`

## callees

- `0x180018e24`
- `0x18001a4c4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018e3d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180018e3d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018f35`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180018f35`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180018e76`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180018e76`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180018f19`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180018f19`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180018eea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180018eea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018f03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018f03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018e9b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018eb9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018e9b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018eb9`

## pseudocode

```c
char TlmiInitializeRunawayHydrationDetection()
{
  char result; // al

  result = byte_1800289B0;
  if ( !byte_1800289B0 )
  {
    RtlAcquireSRWLockExclusive(&qword_1800289B8);
    if ( !byte_1800289B0 )
    {
      RtlInitializeGenericTableAvl(
        &stru_1800289C8,
        TlmiRHAppTableCompare,
        CfpOplockCompletionKeyTableAllocate,
        TlmiRHAppTableFree,
        0);
      *((_QWORD *)&xmmword_180028A30 + 1) = &xmmword_180028A30;
      *(_QWORD *)&xmmword_180028A30 = &xmmword_180028A30;
      qword_180028A40 = CreateEventW(0, 0, 0, 0);
      if ( qword_180028A40 )
      {
        qword_180028A48 = CreateEventW(0, 1, 0, 0);
        if ( qword_180028A48 )
        {
          qword_180028A50 = CreateThread(0, 0, TlmiRunawayHydrationWorker, 0, 4u, 0);
          if ( qword_180028A50 )
          {
            byte_1800289B0 = 1;
            qword_1800289C0 = GetTickCount();
            ResumeThread(qword_180028A50);
          }
        }
      }
    }
    if ( !byte_1800289B0 )
      TlmiUninitializeRunawayHydrationDetection();
    return RtlReleaseSRWLockExclusive(&qword_1800289B8);
  }
  return result;
}

```

## disassembly

```asm
0x180018e24  sub     rsp, 38h
0x180018e28  mov     al, cs:byte_1800289B0
0x180018e2e  test    al, al
0x180018e30  jnz     loc_180018F3B
0x180018e36  lea     rcx, qword_1800289B8
0x180018e3d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180018e43  mov     al, cs:byte_1800289B0
0x180018e49  test    al, al
0x180018e4b  jnz     loc_180018F1F
0x180018e51  lea     r9, TlmiRHAppTableFree; FreeRoutine
0x180018e58  mov     [rsp+38h+TableContext], 0; TableContext
0x180018e61  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180018e68  lea     rdx, TlmiRHAppTableCompare; CompareRoutine
0x180018e6f  lea     rcx, stru_1800289C8; Table
0x180018e76  call    cs:__imp_RtlInitializeGenericTableAvl
0x180018e7c  lea     rax, xmmword_180028A30
0x180018e83  xor     r9d, r9d; lpName
0x180018e86  xor     r8d, r8d; bInitialState
0x180018e89  mov     qword ptr cs:xmmword_180028A30+8, rax
0x180018e90  xor     edx, edx; bManualReset
0x180018e92  mov     qword ptr cs:xmmword_180028A30, rax
0x180018e99  xor     ecx, ecx; lpEventAttributes
0x180018e9b  call    cs:__imp_CreateEventW
0x180018ea1  mov     cs:qword_180028A40, rax
0x180018ea8  test    rax, rax
0x180018eab  jz      short loc_180018F1F
0x180018ead  xor     r9d, r9d; lpName
0x180018eb0  xor     r8d, r8d; bInitialState
0x180018eb3  xor     ecx, ecx; lpEventAttributes
0x180018eb5  lea     edx, [r9+1]; bManualReset
0x180018eb9  call    cs:__imp_CreateEventW
0x180018ebf  mov     cs:qword_180028A48, rax
0x180018ec6  test    rax, rax
0x180018ec9  jz      short loc_180018F1F
0x180018ecb  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180018ed4  lea     r8, TlmiRunawayHydrationWorker; lpStartAddress
0x180018edb  xor     r9d, r9d; lpParameter
0x180018ede  mov     dword ptr [rsp+38h+TableContext], 4; dwCreationFlags
0x180018ee6  xor     edx, edx; dwStackSize
0x180018ee8  xor     ecx, ecx; lpThreadAttributes
0x180018eea  call    cs:__imp_CreateThread
0x180018ef0  mov     cs:qword_180028A50, rax
0x180018ef7  test    rax, rax
0x180018efa  jz      short loc_180018F1F
0x180018efc  mov     cs:byte_1800289B0, 1
0x180018f03  call    cs:__imp_GetTickCount
0x180018f09  mov     rcx, cs:qword_180028A50; hThread
0x180018f10  mov     eax, eax
0x180018f12  mov     cs:qword_1800289C0, rax
0x180018f19  call    cs:__imp_ResumeThread
0x180018f1f  mov     al, cs:byte_1800289B0
0x180018f25  test    al, al
0x180018f27  jnz     short loc_180018F2E
0x180018f29  call    TlmiUninitializeRunawayHydrationDetection
0x180018f2e  lea     rcx, qword_1800289B8
0x180018f35  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180018f3b  add     rsp, 38h
0x180018f3f  retn
```
