# BfspOpenSystemPartition

- ea: `0x180046ec0`
- end: `0x180046f52`
- name: `BfspOpenSystemPartition`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800466ec`
- `0x18004695c`

## callees

- `0x1800467b0`
- `0x180046ec0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046f11`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046f11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046f3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046f3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046f2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046f1d`

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
0x180046ec0  mov     [rsp+arg_0], rbx
0x180046ec5  mov     [rsp+arg_8], rsi
0x180046eca  push    rdi
0x180046ecb  sub     rsp, 40h
0x180046ecf  mov     rbx, rcx
0x180046ed2  mov     esi, edx
0x180046ed4  mov     cl, 1
0x180046ed6  call    BfspGetSystemPartition
0x180046edb  mov     rdi, rax
0x180046ede  test    rax, rax
0x180046ee1  jnz     short loc_180046EED
0x180046ee3  call    cs:__imp_GetLastError
0x180046ee9  mov     ebx, eax
0x180046eeb  jmp     short loc_180046F40
0x180046eed  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180046ef6  mov     r8d, 3; dwShareMode
0x180046efc  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180046f04  xor     r9d, r9d; lpSecurityAttributes
0x180046f07  mov     edx, esi; dwDesiredAccess
0x180046f09  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180046f0e  mov     rcx, rdi; lpFileName
0x180046f11  call    cs:__imp_CreateFileW
0x180046f17  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046f1b  jnz     short loc_180046F27
0x180046f1d  call    cs:__imp_GetLastError
0x180046f23  mov     ebx, eax
0x180046f25  jmp     short loc_180046F2C
0x180046f27  mov     [rbx], rax
0x180046f2a  xor     ebx, ebx
0x180046f2c  call    cs:__imp_GetProcessHeap
0x180046f32  mov     r8, rdi; lpMem
0x180046f35  xor     edx, edx; dwFlags
0x180046f37  mov     rcx, rax; hHeap
0x180046f3a  call    cs:__imp_HeapFree
0x180046f40  mov     rsi, [rsp+48h+arg_8]
0x180046f45  mov     eax, ebx
0x180046f47  mov     rbx, [rsp+48h+arg_0]
0x180046f4c  add     rsp, 40h
0x180046f50  pop     rdi
0x180046f51  retn
```
