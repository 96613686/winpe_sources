# BfspSetThreadPagePriority

- ea: `0x140003884`
- end: `0x1400038cd`
- name: `BfspSetThreadPagePriority`
- size: `73`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000b57c`

## callees

- `0x140002ec8`
- `0x140003884`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1400038a3`
- `KERNEL32!GetCurrentThread` at `0x1400038a3`
- `ntdll!NtSetInformationThread` at `0x1400038b8`
- `ntdll!NtSetInformationThread` at `0x1400038b8`

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
0x140003884  mov     [rsp+arg_8], rbx
0x140003889  push    rdi
0x14000388a  sub     rsp, 20h
0x14000388e  xor     ebx, ebx
0x140003890  mov     edi, ecx
0x140003892  mov     [rsp+28h+ThreadInformation], ebx
0x140003896  call    BfspGetThreadPagePriority
0x14000389b  cmp     eax, edi
0x14000389d  jz      short loc_1400038C0
0x14000389f  mov     [rsp+28h+ThreadInformation], edi
0x1400038a3  call    cs:__imp_GetCurrentThread
0x1400038a9  mov     rcx, rax; ThreadHandle
0x1400038ac  lea     r9d, [rbx+4]; ThreadInformationLength
0x1400038b0  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1400038b5  lea     edx, [rbx+18h]; ThreadInformationClass
0x1400038b8  call    cs:__imp_NtSetInformationThread
0x1400038be  mov     ebx, eax
0x1400038c0  mov     eax, ebx
0x1400038c2  mov     rbx, [rsp+28h+arg_8]
0x1400038c7  add     rsp, 20h
0x1400038cb  pop     rdi
0x1400038cc  retn
```
