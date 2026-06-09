# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x18002d240`
- end: `0x18002d345`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `261`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002db68`

## callees

- `0x18002d240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d28d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d32f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d32f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d326`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002d326`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d27e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d2d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d27e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d2d8`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18002d2a7`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18002d2a7`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18002d2fd`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18002d2fd`

## pseudocode

```c
void __fastcall AslLogpWritePipe(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW; // rbx
  DWORD Mode; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL
    || GetLastError() == 231
    && (WaitNamedPipeW(L"\\\\.\\pipe\\GmdAslLogger", 0),
        FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0),
        FileW != (HANDLE)-1LL) )
  {
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
    {
      NumberOfBytesWritten = 0;
      WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      CloseHandle(FileW);
    }
  }
}

```

## disassembly

```asm
0x18002d240  mov     rax, rsp
0x18002d243  mov     [rax+8], rbx
0x18002d247  mov     [rax+10h], rsi
0x18002d24b  push    rdi
0x18002d24c  sub     rsp, 40h
0x18002d250  mov     qword ptr [rax-18h], 0
0x18002d258  mov     rdi, rdx
0x18002d25b  mov     rsi, rcx
0x18002d25e  mov     dword ptr [rax-20h], 0
0x18002d265  mov     edx, 40000000h; dwDesiredAccess
0x18002d26a  mov     dword ptr [rax-28h], 3
0x18002d271  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18002d278  xor     r9d, r9d; lpSecurityAttributes
0x18002d27b  xor     r8d, r8d; dwShareMode
0x18002d27e  call    cs:__imp_CreateFileW
0x18002d284  mov     rbx, rax
0x18002d287  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d28b  jnz     short loc_18002D2E7
0x18002d28d  call    cs:__imp_GetLastError
0x18002d293  cmp     eax, 0E7h
0x18002d298  jnz     loc_18002D335
0x18002d29e  xor     edx, edx; nTimeOut
0x18002d2a0  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18002d2a7  call    cs:__imp_WaitNamedPipeW
0x18002d2ad  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002d2b6  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18002d2bd  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002d2c5  xor     r9d, r9d; lpSecurityAttributes
0x18002d2c8  xor     r8d, r8d; dwShareMode
0x18002d2cb  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d2d3  mov     edx, 40000000h; dwDesiredAccess
0x18002d2d8  call    cs:__imp_CreateFileW
0x18002d2de  mov     rbx, rax
0x18002d2e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d2e5  jz      short loc_18002D335
0x18002d2e7  xor     r9d, r9d; lpCollectDataTimeout
0x18002d2ea  mov     [rsp+48h+Mode], 2
0x18002d2f2  xor     r8d, r8d; lpMaxCollectionCount
0x18002d2f5  lea     rdx, [rsp+48h+Mode]; lpMode
0x18002d2fa  mov     rcx, rbx; hNamedPipe
0x18002d2fd  call    cs:__imp_SetNamedPipeHandleState
0x18002d303  test    eax, eax
0x18002d305  jz      short loc_18002D335
0x18002d307  mov     r8d, edi; nNumberOfBytesToWrite
0x18002d30a  mov     [rsp+48h+NumberOfBytesWritten], 0
0x18002d312  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002d317  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x18002d320  mov     rdx, rsi; lpBuffer
0x18002d323  mov     rcx, rbx; hFile
0x18002d326  call    cs:__imp_WriteFile
0x18002d32c  mov     rcx, rbx; hObject
0x18002d32f  call    cs:__imp_CloseHandle
0x18002d335  mov     rbx, [rsp+48h+arg_0]
0x18002d33a  mov     rsi, [rsp+48h+arg_8]
0x18002d33f  add     rsp, 40h
0x18002d343  pop     rdi
0x18002d344  retn
```
