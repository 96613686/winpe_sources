# BfspGetThreadPagePriority

- ea: `0x140002ec8`
- end: `0x140002f0e`
- name: `BfspGetThreadPagePriority`
- size: `70`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140003884`
- `0x14000b57c`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x140002ed4`
- `KERNEL32!GetCurrentThread` at `0x140002ed4`
- `ntdll!NtQueryInformationThread` at `0x140002ef5`
- `ntdll!NtQueryInformationThread` at `0x140002ef5`

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
0x140002ec8  sub     rsp, 38h
0x140002ecc  mov     [rsp+38h+ThreadInformation], 0
0x140002ed4  call    cs:__imp_GetCurrentThread
0x140002eda  mov     r9d, 4; ThreadInformationLength
0x140002ee0  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x140002ee9  mov     rcx, rax; ThreadHandle
0x140002eec  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x140002ef1  lea     edx, [r9+14h]; ThreadInformationClass
0x140002ef5  call    cs:__imp_NtQueryInformationThread
0x140002efb  test    eax, eax
0x140002efd  mov     ecx, 5
0x140002f02  cmovns  ecx, [rsp+38h+ThreadInformation]
0x140002f07  mov     eax, ecx
0x140002f09  add     rsp, 38h
0x140002f0d  retn
```
