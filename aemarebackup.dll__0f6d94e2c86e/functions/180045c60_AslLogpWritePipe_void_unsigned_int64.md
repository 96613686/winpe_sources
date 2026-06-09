# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x180045c60`
- end: `0x180045d63`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `259`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800471a0`

## callees

- `0x180005b90`
- `0x180005bc0`
- `0x180045c60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045c9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045cf7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045c9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045cf7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045d45`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045d45`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180045cc6`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180045cc6`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180045d1c`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180045d1c`

## pseudocode

```c
void __fastcall AslLogpWritePipe(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW; // rbx
  DWORD Mode; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL
    || GetLastError_0() == 231
    && (WaitNamedPipeW(L"\\\\.\\pipe\\GmdAslLogger", 0),
        FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0),
        FileW != (HANDLE)-1LL) )
  {
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
    {
      NumberOfBytesWritten = 0;
      WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      CloseHandle_0(FileW);
    }
  }
}

```

## disassembly

```asm
0x180045c60  mov     rax, rsp
0x180045c63  mov     [rax+8], rbx
0x180045c67  mov     [rax+10h], rsi
0x180045c6b  push    rdi
0x180045c6c  sub     rsp, 40h
0x180045c70  mov     qword ptr [rax-18h], 0
0x180045c78  mov     rdi, rdx
0x180045c7b  mov     rsi, rcx
0x180045c7e  mov     dword ptr [rax-20h], 0
0x180045c85  mov     edx, 40000000h; dwDesiredAccess
0x180045c8a  mov     dword ptr [rax-28h], 3
0x180045c91  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180045c98  xor     r9d, r9d; lpSecurityAttributes
0x180045c9b  xor     r8d, r8d; dwShareMode
0x180045c9e  call    cs:__imp_CreateFileW
0x180045ca4  mov     rbx, rax
0x180045ca7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045cab  jnz     short loc_180045D06
0x180045cad  call    GetLastError_0
0x180045cb2  cmp     eax, 0E7h
0x180045cb7  jnz     loc_180045D53
0x180045cbd  xor     edx, edx; nTimeOut
0x180045cbf  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180045cc6  call    cs:__imp_WaitNamedPipeW
0x180045ccc  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180045cd5  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180045cdc  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180045ce4  xor     r9d, r9d; lpSecurityAttributes
0x180045ce7  xor     r8d, r8d; dwShareMode
0x180045cea  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180045cf2  mov     edx, 40000000h; dwDesiredAccess
0x180045cf7  call    cs:__imp_CreateFileW
0x180045cfd  mov     rbx, rax
0x180045d00  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045d04  jz      short loc_180045D53
0x180045d06  xor     r9d, r9d; lpCollectDataTimeout
0x180045d09  mov     [rsp+48h+Mode], 2
0x180045d11  xor     r8d, r8d; lpMaxCollectionCount
0x180045d14  lea     rdx, [rsp+48h+Mode]; lpMode
0x180045d19  mov     rcx, rbx; hNamedPipe
0x180045d1c  call    cs:__imp_SetNamedPipeHandleState
0x180045d22  test    eax, eax
0x180045d24  jz      short loc_180045D53
0x180045d26  mov     r8d, edi; nNumberOfBytesToWrite
0x180045d29  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180045d31  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180045d36  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x180045d3f  mov     rdx, rsi; lpBuffer
0x180045d42  mov     rcx, rbx; hFile
0x180045d45  call    cs:__imp_WriteFile
0x180045d4b  mov     rcx, rbx; hObject
0x180045d4e  call    CloseHandle_0
0x180045d53  mov     rbx, [rsp+48h+arg_0]
0x180045d58  mov     rsi, [rsp+48h+arg_8]
0x180045d5d  add     rsp, 40h
0x180045d61  pop     rdi
0x180045d62  retn
```
