# unknown_libname_73

- ea: `0x14001b71c`
- end: `0x14001b7da`
- name: `unknown_libname_73`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001ad74`

## callees

- `0x14001b71c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001b759`
- `KERNEL32!GetLastError` at `0x14001b759`
- `KERNEL32!CloseHandle` at `0x14001b771`
- `KERNEL32!CloseHandle` at `0x14001b771`
- `KERNEL32!CreateFileW` at `0x14001b79c`
- `KERNEL32!CreateFileW` at `0x14001b79c`
- `KERNEL32!WriteConsoleW` at `0x14001b74d`
- `KERNEL32!WriteConsoleW` at `0x14001b7bb`
- `KERNEL32!WriteConsoleW` at `0x14001b74d`
- `KERNEL32!WriteConsoleW` at `0x14001b7bb`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_73(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x14001b71c  mov     rax, rsp
0x14001b71f  mov     [rax+8], rbx
0x14001b723  mov     [rax+10h], rbp
0x14001b727  mov     [rax+18h], rsi
0x14001b72b  push    rdi
0x14001b72c  sub     rsp, 40h
0x14001b730  and     qword ptr [rax-28h], 0
0x14001b735  mov     rdi, r8
0x14001b738  mov     r9, r8; lpNumberOfCharsWritten
0x14001b73b  mov     esi, edx
0x14001b73d  mov     r8d, edx; nNumberOfCharsToWrite
0x14001b740  mov     rbp, rcx
0x14001b743  mov     rdx, rcx; lpBuffer
0x14001b746  mov     rcx, cs:hObject; hConsoleOutput
0x14001b74d  call    cs:WriteConsoleW
0x14001b753  mov     ebx, eax
0x14001b755  test    eax, eax
0x14001b757  jnz     short loc_14001B7C3
0x14001b759  call    cs:GetLastError
0x14001b75f  cmp     eax, 6
0x14001b762  jnz     short loc_14001B7C3
0x14001b764  mov     rcx, cs:hObject; hObject
0x14001b76b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14001b76f  ja      short loc_14001B777
0x14001b771  call    cs:CloseHandle
0x14001b777  and     [rsp+48h+var_18], 0
0x14001b77d  lea     rcx, FileName
0x14001b784  and     [rsp+48h+var_20], 0
0x14001b789  mov     r8d, 3; dwShareMode
0x14001b78f  xor     r9d, r9d; lpSecurityAttributes
0x14001b792  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x14001b797  mov     edx, 40000000h; dwDesiredAccess
0x14001b79c  call    cs:CreateFileW
0x14001b7a2  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x14001b7a8  mov     r9, rdi; lpNumberOfCharsWritten
0x14001b7ab  mov     rcx, rax; hConsoleOutput
0x14001b7ae  mov     cs:hObject, rax
0x14001b7b5  mov     r8d, esi; nNumberOfCharsToWrite
0x14001b7b8  mov     rdx, rbp; lpBuffer
0x14001b7bb  call    cs:WriteConsoleW
0x14001b7c1  mov     ebx, eax
0x14001b7c3  mov     rbp, [rsp+48h+arg_8]
0x14001b7c8  mov     eax, ebx
0x14001b7ca  mov     rbx, [rsp+48h+arg_0]
0x14001b7cf  mov     rsi, [rsp+48h+arg_10]
0x14001b7d4  add     rsp, 40h
0x14001b7d8  pop     rdi
0x14001b7d9  retn
```
