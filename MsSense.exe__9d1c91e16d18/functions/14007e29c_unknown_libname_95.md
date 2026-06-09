# unknown_libname_95

- ea: `0x14007e29c`
- end: `0x14007e35a`
- name: `unknown_libname_95`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14007d8b4`

## callees

- `0x14007e29c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14007e31c`
- `KERNEL32!CreateFileW` at `0x14007e31c`
- `KERNEL32!WriteConsoleW` at `0x14007e2cd`
- `KERNEL32!WriteConsoleW` at `0x14007e33b`
- `KERNEL32!WriteConsoleW` at `0x14007e2cd`
- `KERNEL32!WriteConsoleW` at `0x14007e33b`
- `KERNEL32!GetLastError` at `0x14007e2d9`
- `KERNEL32!GetLastError` at `0x14007e2d9`
- `KERNEL32!CloseHandle` at `0x14007e2f1`
- `KERNEL32!CloseHandle` at `0x14007e2f1`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_95(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x14007e29c  mov     rax, rsp
0x14007e29f  mov     [rax+8], rbx
0x14007e2a3  mov     [rax+10h], rbp
0x14007e2a7  mov     [rax+18h], rsi
0x14007e2ab  push    rdi
0x14007e2ac  sub     rsp, 40h
0x14007e2b0  and     qword ptr [rax-28h], 0
0x14007e2b5  mov     rdi, r8
0x14007e2b8  mov     r9, r8; lpNumberOfCharsWritten
0x14007e2bb  mov     esi, edx
0x14007e2bd  mov     r8d, edx; nNumberOfCharsToWrite
0x14007e2c0  mov     rbp, rcx
0x14007e2c3  mov     rdx, rcx; lpBuffer
0x14007e2c6  mov     rcx, cs:hObject; hConsoleOutput
0x14007e2cd  call    cs:WriteConsoleW
0x14007e2d3  mov     ebx, eax
0x14007e2d5  test    eax, eax
0x14007e2d7  jnz     short loc_14007E343
0x14007e2d9  call    cs:GetLastError
0x14007e2df  cmp     eax, 6
0x14007e2e2  jnz     short loc_14007E343
0x14007e2e4  mov     rcx, cs:hObject; hObject
0x14007e2eb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14007e2ef  ja      short loc_14007E2F7
0x14007e2f1  call    cs:CloseHandle
0x14007e2f7  and     [rsp+48h+var_18], 0
0x14007e2fd  lea     rcx, FileName
0x14007e304  and     [rsp+48h+var_20], 0
0x14007e309  mov     r8d, 3; dwShareMode
0x14007e30f  xor     r9d, r9d; lpSecurityAttributes
0x14007e312  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x14007e317  mov     edx, 40000000h; dwDesiredAccess
0x14007e31c  call    cs:CreateFileW
0x14007e322  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x14007e328  mov     r9, rdi; lpNumberOfCharsWritten
0x14007e32b  mov     rcx, rax; hConsoleOutput
0x14007e32e  mov     cs:hObject, rax
0x14007e335  mov     r8d, esi; nNumberOfCharsToWrite
0x14007e338  mov     rdx, rbp; lpBuffer
0x14007e33b  call    cs:WriteConsoleW
0x14007e341  mov     ebx, eax
0x14007e343  mov     rbp, [rsp+48h+arg_8]
0x14007e348  mov     eax, ebx
0x14007e34a  mov     rbx, [rsp+48h+arg_0]
0x14007e34f  mov     rsi, [rsp+48h+arg_10]
0x14007e354  add     rsp, 40h
0x14007e358  pop     rdi
0x14007e359  retn
```
