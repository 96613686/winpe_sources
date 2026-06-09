# BfspOpenSystemPartition

- ea: `0x1400032d0`
- end: `0x140003362`
- name: `BfspOpenSystemPartition`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD *, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140002ba8`
- `0x140009bdc`

## callees

- `0x140002c14`
- `0x1400032d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400032f3`
- `KERNEL32!GetLastError` at `0x14000332d`
- `KERNEL32!GetLastError` at `0x1400032f3`
- `KERNEL32!GetLastError` at `0x14000332d`
- `KERNEL32!HeapFree` at `0x14000334a`
- `KERNEL32!HeapFree` at `0x14000334a`
- `KERNEL32!GetProcessHeap` at `0x14000333c`
- `KERNEL32!GetProcessHeap` at `0x14000333c`
- `KERNEL32!CreateFileW` at `0x140003321`
- `KERNEL32!CreateFileW` at `0x140003321`

## pseudocode

```c
__int64 __fastcall BfspOpenSystemPartition(_QWORD *a1, DWORD a2)
{
  wchar_t *SystemPartition; // rax
  wchar_t *v5; // rdi
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  HANDLE ProcessHeap; // rax

  SystemPartition = BfspGetSystemPartition(1);
  v5 = SystemPartition;
  if ( SystemPartition )
  {
    FileW = CreateFileW(SystemPartition, a2, 3u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      *a1 = FileW;
      LastError = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1400032d0  mov     [rsp+arg_0], rbx
0x1400032d5  mov     [rsp+arg_8], rsi
0x1400032da  push    rdi
0x1400032db  sub     rsp, 40h
0x1400032df  mov     rbx, rcx
0x1400032e2  mov     esi, edx
0x1400032e4  mov     cl, 1
0x1400032e6  call    BfspGetSystemPartition
0x1400032eb  mov     rdi, rax
0x1400032ee  test    rax, rax
0x1400032f1  jnz     short loc_1400032FD
0x1400032f3  call    cs:__imp_GetLastError
0x1400032f9  mov     ebx, eax
0x1400032fb  jmp     short loc_140003350
0x1400032fd  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140003306  mov     r8d, 3; dwShareMode
0x14000330c  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140003314  xor     r9d, r9d; lpSecurityAttributes
0x140003317  mov     edx, esi; dwDesiredAccess
0x140003319  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x14000331e  mov     rcx, rdi; lpFileName
0x140003321  call    cs:__imp_CreateFileW
0x140003327  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000332b  jnz     short loc_140003337
0x14000332d  call    cs:__imp_GetLastError
0x140003333  mov     ebx, eax
0x140003335  jmp     short loc_14000333C
0x140003337  mov     [rbx], rax
0x14000333a  xor     ebx, ebx
0x14000333c  call    cs:__imp_GetProcessHeap
0x140003342  mov     r8, rdi; lpMem
0x140003345  xor     edx, edx; dwFlags
0x140003347  mov     rcx, rax; hHeap
0x14000334a  call    cs:__imp_HeapFree
0x140003350  mov     rsi, [rsp+48h+arg_8]
0x140003355  mov     eax, ebx
0x140003357  mov     rbx, [rsp+48h+arg_0]
0x14000335c  add     rsp, 40h
0x140003360  pop     rdi
0x140003361  retn
```
