# console_output_reopen_and_retry__lambda_61c1b8a38cedca4df5fdc542e6ccae6d_

- ea: `0x180020f64`
- end: `0x18002100e`
- name: `console_output_reopen_and_retry__lambda_61c1b8a38cedca4df5fdc542e6ccae6d___`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180020f64`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x180020f89`
- `KERNEL32!WriteConsoleW` at `0x180020ff9`
- `KERNEL32!WriteConsoleW` at `0x180020f89`
- `KERNEL32!WriteConsoleW` at `0x180020ff9`
- `KERNEL32!CloseHandle` at `0x180020fad`
- `KERNEL32!CloseHandle` at `0x180020fad`
- `KERNEL32!CreateFileW` at `0x180020fd8`
- `KERNEL32!CreateFileW` at `0x180020fd8`
- `KERNEL32!GetLastError` at `0x180020f95`
- `KERNEL32!GetLastError` at `0x180020f95`

## pseudocode

```c
__int64 __fastcall console_output_reopen_and_retry__lambda_61c1b8a38cedca4df5fdc542e6ccae6d_(__int64 a1)
{
  unsigned int v2; // edi
  HANDLE FileW; // rax
  DWORD *v4; // r9
  DWORD v5; // r8d
  const void *v6; // rdx

  v2 = WriteConsoleW(hObject, *(const void **)a1, *(_DWORD *)(a1 + 8), *(LPDWORD *)(a1 + 16), 0);
  if ( !v2 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hObject <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    FileW = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    v4 = *(DWORD **)(a1 + 16);
    v5 = *(_DWORD *)(a1 + 8);
    v6 = *(const void **)a1;
    hObject = FileW;
    return WriteConsoleW(FileW, v6, v5, v4, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x180020f64  mov     [rsp+arg_0], rbx
0x180020f69  push    rdi
0x180020f6a  sub     rsp, 40h
0x180020f6e  mov     r9, [rcx+10h]; lpNumberOfCharsWritten
0x180020f72  mov     rbx, rcx
0x180020f75  mov     r8d, [rcx+8]; nNumberOfCharsToWrite
0x180020f79  mov     rdx, [rcx]; lpBuffer
0x180020f7c  mov     rcx, cs:hObject; hConsoleOutput
0x180020f83  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x180020f89  call    cs:__imp_WriteConsoleW
0x180020f8f  mov     edi, eax
0x180020f91  test    eax, eax
0x180020f93  jnz     short loc_180021001
0x180020f95  call    cs:__imp_GetLastError
0x180020f9b  cmp     eax, 6
0x180020f9e  jnz     short loc_180021001
0x180020fa0  mov     rcx, cs:hObject; hObject
0x180020fa7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180020fab  ja      short loc_180020FB3
0x180020fad  call    cs:__imp_CloseHandle
0x180020fb3  and     [rsp+48h+var_18], 0
0x180020fb9  lea     rcx, FileName; "CONOUT$"
0x180020fc0  and     [rsp+48h+var_20], 0
0x180020fc5  mov     r8d, 3; dwShareMode
0x180020fcb  xor     r9d, r9d; lpSecurityAttributes
0x180020fce  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x180020fd3  mov     edx, 40000000h; dwDesiredAccess
0x180020fd8  call    cs:__imp_CreateFileW
0x180020fde  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x180020fe4  mov     rcx, rax; hConsoleOutput
0x180020fe7  mov     r9, [rbx+10h]; lpNumberOfCharsWritten
0x180020feb  mov     r8d, [rbx+8]; nNumberOfCharsToWrite
0x180020fef  mov     rdx, [rbx]; lpBuffer
0x180020ff2  mov     cs:hObject, rax
0x180020ff9  call    cs:__imp_WriteConsoleW
0x180020fff  mov     edi, eax
0x180021001  mov     rbx, [rsp+48h+arg_0]
0x180021006  mov     eax, edi
0x180021008  add     rsp, 40h
0x18002100c  pop     rdi
0x18002100d  retn
```
