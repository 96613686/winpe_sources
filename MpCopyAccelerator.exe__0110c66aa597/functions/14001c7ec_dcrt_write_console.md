# __dcrt_write_console

- ea: `0x14001c7ec`
- end: `0x14001c8aa`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001bf40`

## callees

- `0x14001c7ec`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14001c86c`
- `KERNEL32!CreateFileW` at `0x14001c86c`
- `KERNEL32!CloseHandle` at `0x14001c841`
- `KERNEL32!CloseHandle` at `0x14001c841`
- `KERNEL32!GetLastError` at `0x14001c829`
- `KERNEL32!GetLastError` at `0x14001c829`
- `KERNEL32!WriteConsoleW` at `0x14001c81d`
- `KERNEL32!WriteConsoleW` at `0x14001c88b`
- `KERNEL32!WriteConsoleW` at `0x14001c81d`
- `KERNEL32!WriteConsoleW` at `0x14001c88b`

## pseudocode

```c
__int64 __fastcall _dcrt_write_console(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x14001c7ec  mov     rax, rsp
0x14001c7ef  mov     [rax+8], rbx
0x14001c7f3  mov     [rax+10h], rbp
0x14001c7f7  mov     [rax+18h], rsi
0x14001c7fb  push    rdi
0x14001c7fc  sub     rsp, 40h
0x14001c800  and     qword ptr [rax-28h], 0
0x14001c805  mov     rdi, r8
0x14001c808  mov     r9, r8; lpNumberOfCharsWritten
0x14001c80b  mov     esi, edx
0x14001c80d  mov     r8d, edx; nNumberOfCharsToWrite
0x14001c810  mov     rbp, rcx
0x14001c813  mov     rdx, rcx; lpBuffer
0x14001c816  mov     rcx, cs:hObject; hConsoleOutput
0x14001c81d  call    cs:__imp_WriteConsoleW
0x14001c823  mov     ebx, eax
0x14001c825  test    eax, eax
0x14001c827  jnz     short loc_14001C893
0x14001c829  call    cs:__imp_GetLastError
0x14001c82f  cmp     eax, 6
0x14001c832  jnz     short loc_14001C893
0x14001c834  mov     rcx, cs:hObject; hObject
0x14001c83b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14001c83f  ja      short loc_14001C847
0x14001c841  call    cs:__imp_CloseHandle
0x14001c847  and     [rsp+48h+var_18], 0
0x14001c84d  lea     rcx, FileName
0x14001c854  and     [rsp+48h+var_20], 0
0x14001c859  mov     r8d, 3; dwShareMode
0x14001c85f  xor     r9d, r9d; lpSecurityAttributes
0x14001c862  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x14001c867  mov     edx, 40000000h; dwDesiredAccess
0x14001c86c  call    cs:__imp_CreateFileW
0x14001c872  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x14001c878  mov     r9, rdi; lpNumberOfCharsWritten
0x14001c87b  mov     rcx, rax; hConsoleOutput
0x14001c87e  mov     cs:hObject, rax
0x14001c885  mov     r8d, esi; nNumberOfCharsToWrite
0x14001c888  mov     rdx, rbp; lpBuffer
0x14001c88b  call    cs:__imp_WriteConsoleW
0x14001c891  mov     ebx, eax
0x14001c893  mov     rbp, [rsp+48h+arg_8]
0x14001c898  mov     eax, ebx
0x14001c89a  mov     rbx, [rsp+48h+arg_0]
0x14001c89f  mov     rsi, [rsp+48h+arg_10]
0x14001c8a4  add     rsp, 40h
0x14001c8a8  pop     rdi
0x14001c8a9  retn
```
