# BfspGetThreadPagePriority

- ea: `0x180046adc`
- end: `0x180046b22`
- name: `BfspGetThreadPagePriority`
- size: `70`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800472a4`
- `0x18004a678`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180046b09`
- `ntdll!NtQueryInformationThread` at `0x180046b09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046ae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180046ae8`

## pseudocode

```c
__int64 BfspGetThreadPagePriority()
{
  HANDLE CurrentThread; // rax
  NTSTATUS v1; // eax
  unsigned int v2; // ecx
  unsigned int ThreadInformation; // [rsp+40h] [rbp+8h] BYREF

  ThreadInformation = 0;
  CurrentThread = GetCurrentThread();
  v1 = NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0);
  v2 = 5;
  if ( v1 >= 0 )
    return ThreadInformation;
  return v2;
}

```

## disassembly

```asm
0x180046adc  sub     rsp, 38h
0x180046ae0  mov     [rsp+38h+ThreadInformation], 0
0x180046ae8  call    cs:__imp_GetCurrentThread
0x180046aee  mov     r9d, 4; ThreadInformationLength
0x180046af4  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180046afd  mov     rcx, rax; ThreadHandle
0x180046b00  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x180046b05  lea     edx, [r9+14h]; ThreadInformationClass
0x180046b09  call    cs:__imp_NtQueryInformationThread
0x180046b0f  test    eax, eax
0x180046b11  mov     ecx, 5
0x180046b16  cmovns  ecx, [rsp+38h+ThreadInformation]
0x180046b1b  mov     eax, ecx
0x180046b1d  add     rsp, 38h
0x180046b21  retn
```
