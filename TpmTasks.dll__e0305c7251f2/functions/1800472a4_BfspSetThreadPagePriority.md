# BfspSetThreadPagePriority

- ea: `0x1800472a4`
- end: `0x1800472ed`
- name: `BfspSetThreadPagePriority`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004a678`

## callees

- `0x180046adc`
- `0x1800472a4`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1800472d8`
- `ntdll!NtSetInformationThread` at `0x1800472d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800472c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800472c3`

## pseudocode

```c
__int64 __fastcall BfspSetThreadPagePriority(int a1)
{
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  int ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  ThreadInformation = 0;
  if ( (unsigned int)BfspGetThreadPagePriority() != a1 )
  {
    ThreadInformation = a1;
    CurrentThread = GetCurrentThread();
    return (unsigned int)NtSetInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u);
  }
  return v1;
}

```

## disassembly

```asm
0x1800472a4  mov     [rsp+arg_8], rbx
0x1800472a9  push    rdi
0x1800472aa  sub     rsp, 20h
0x1800472ae  xor     ebx, ebx
0x1800472b0  mov     edi, ecx
0x1800472b2  mov     [rsp+28h+ThreadInformation], ebx
0x1800472b6  call    BfspGetThreadPagePriority
0x1800472bb  cmp     eax, edi
0x1800472bd  jz      short loc_1800472E0
0x1800472bf  mov     [rsp+28h+ThreadInformation], edi
0x1800472c3  call    cs:__imp_GetCurrentThread
0x1800472c9  mov     rcx, rax; ThreadHandle
0x1800472cc  lea     r9d, [rbx+4]; ThreadInformationLength
0x1800472d0  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1800472d5  lea     edx, [rbx+18h]; ThreadInformationClass
0x1800472d8  call    cs:__imp_NtSetInformationThread
0x1800472de  mov     ebx, eax
0x1800472e0  mov     eax, ebx
0x1800472e2  mov     rbx, [rsp+28h+arg_8]
0x1800472e7  add     rsp, 20h
0x1800472eb  pop     rdi
0x1800472ec  retn
```
