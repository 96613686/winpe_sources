# unknown_libname_47

- ea: `0x140024dcc`
- end: `0x140024e8a`
- name: `unknown_libname_47`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002457c`

## callees

- `0x140024dcc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140024e4c`
- `KERNEL32!CreateFileW` at `0x140024e4c`
- `KERNEL32!CloseHandle` at `0x140024e21`
- `KERNEL32!CloseHandle` at `0x140024e21`
- `KERNEL32!GetLastError` at `0x140024e09`
- `KERNEL32!GetLastError` at `0x140024e09`
- `KERNEL32!WriteConsoleW` at `0x140024dfd`
- `KERNEL32!WriteConsoleW` at `0x140024e6b`
- `KERNEL32!WriteConsoleW` at `0x140024dfd`
- `KERNEL32!WriteConsoleW` at `0x140024e6b`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_47(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x140024dcc  mov     rax, rsp
0x140024dcf  mov     [rax+8], rbx
0x140024dd3  mov     [rax+10h], rbp
0x140024dd7  mov     [rax+18h], rsi
0x140024ddb  push    rdi
0x140024ddc  sub     rsp, 40h
0x140024de0  and     qword ptr [rax-28h], 0
0x140024de5  mov     rdi, r8
0x140024de8  mov     r9, r8; lpNumberOfCharsWritten
0x140024deb  mov     esi, edx
0x140024ded  mov     r8d, edx; nNumberOfCharsToWrite
0x140024df0  mov     rbp, rcx
0x140024df3  mov     rdx, rcx; lpBuffer
0x140024df6  mov     rcx, cs:hObject; hConsoleOutput
0x140024dfd  call    cs:WriteConsoleW
0x140024e03  mov     ebx, eax
0x140024e05  test    eax, eax
0x140024e07  jnz     short loc_140024E73
0x140024e09  call    cs:GetLastError
0x140024e0f  cmp     eax, 6
0x140024e12  jnz     short loc_140024E73
0x140024e14  mov     rcx, cs:hObject; hObject
0x140024e1b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140024e1f  ja      short loc_140024E27
0x140024e21  call    cs:CloseHandle
0x140024e27  and     [rsp+48h+var_18], 0
0x140024e2d  lea     rcx, FileName
0x140024e34  and     [rsp+48h+var_20], 0
0x140024e39  mov     r8d, 3; dwShareMode
0x140024e3f  xor     r9d, r9d; lpSecurityAttributes
0x140024e42  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x140024e47  mov     edx, 40000000h; dwDesiredAccess
0x140024e4c  call    cs:CreateFileW
0x140024e52  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x140024e58  mov     r9, rdi; lpNumberOfCharsWritten
0x140024e5b  mov     rcx, rax; hConsoleOutput
0x140024e5e  mov     cs:hObject, rax
0x140024e65  mov     r8d, esi; nNumberOfCharsToWrite
0x140024e68  mov     rdx, rbp; lpBuffer
0x140024e6b  call    cs:WriteConsoleW
0x140024e71  mov     ebx, eax
0x140024e73  mov     rbp, [rsp+48h+arg_8]
0x140024e78  mov     eax, ebx
0x140024e7a  mov     rbx, [rsp+48h+arg_0]
0x140024e7f  mov     rsi, [rsp+48h+arg_10]
0x140024e84  add     rsp, 40h
0x140024e88  pop     rdi
0x140024e89  retn
```
