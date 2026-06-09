# unknown_libname_16

- ea: `0x14000c89c`
- end: `0x14000c95a`
- name: `unknown_libname_16`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c620`

## callees

- `0x14000c89c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000c8d9`
- `KERNEL32!GetLastError` at `0x14000c8d9`
- `KERNEL32!WriteConsoleW` at `0x14000c8cd`
- `KERNEL32!WriteConsoleW` at `0x14000c93b`
- `KERNEL32!WriteConsoleW` at `0x14000c8cd`
- `KERNEL32!WriteConsoleW` at `0x14000c93b`
- `KERNEL32!CreateFileW` at `0x14000c91c`
- `KERNEL32!CreateFileW` at `0x14000c91c`
- `KERNEL32!CloseHandle` at `0x14000c8f1`
- `KERNEL32!CloseHandle` at `0x14000c8f1`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_16(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  unsigned int v6; // ebx

  v6 = WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v6 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hObject <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    hObject = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    return WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x14000c89c  mov     rax, rsp
0x14000c89f  mov     [rax+8], rbx
0x14000c8a3  mov     [rax+10h], rbp
0x14000c8a7  mov     [rax+18h], rsi
0x14000c8ab  push    rdi
0x14000c8ac  sub     rsp, 40h
0x14000c8b0  and     qword ptr [rax-28h], 0
0x14000c8b5  mov     rdi, r8
0x14000c8b8  mov     r9, r8; lpNumberOfCharsWritten
0x14000c8bb  mov     esi, edx
0x14000c8bd  mov     r8d, edx; nNumberOfCharsToWrite
0x14000c8c0  mov     rbp, rcx
0x14000c8c3  mov     rdx, rcx; lpBuffer
0x14000c8c6  mov     rcx, cs:hObject; hConsoleOutput
0x14000c8cd  call    cs:WriteConsoleW
0x14000c8d3  mov     ebx, eax
0x14000c8d5  test    eax, eax
0x14000c8d7  jnz     short loc_14000C943
0x14000c8d9  call    cs:GetLastError
0x14000c8df  cmp     eax, 6
0x14000c8e2  jnz     short loc_14000C943
0x14000c8e4  mov     rcx, cs:hObject; hObject
0x14000c8eb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000c8ef  ja      short loc_14000C8F7
0x14000c8f1  call    cs:CloseHandle
0x14000c8f7  and     [rsp+48h+var_18], 0
0x14000c8fd  lea     rcx, FileName
0x14000c904  and     [rsp+48h+var_20], 0
0x14000c909  mov     r8d, 3; dwShareMode
0x14000c90f  xor     r9d, r9d; lpSecurityAttributes
0x14000c912  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x14000c917  mov     edx, 40000000h; dwDesiredAccess
0x14000c91c  call    cs:CreateFileW
0x14000c922  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x14000c928  mov     r9, rdi; lpNumberOfCharsWritten
0x14000c92b  mov     rcx, rax; hConsoleOutput
0x14000c92e  mov     cs:hObject, rax
0x14000c935  mov     r8d, esi; nNumberOfCharsToWrite
0x14000c938  mov     rdx, rbp; lpBuffer
0x14000c93b  call    cs:WriteConsoleW
0x14000c941  mov     ebx, eax
0x14000c943  mov     rbp, [rsp+48h+arg_8]
0x14000c948  mov     eax, ebx
0x14000c94a  mov     rbx, [rsp+48h+arg_0]
0x14000c94f  mov     rsi, [rsp+48h+arg_10]
0x14000c954  add     rsp, 40h
0x14000c958  pop     rdi
0x14000c959  retn
```
