# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x180012b04`
- end: `0x180012c07`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `259`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180013314`

## callees

- `0x1800039f0`
- `0x180003a20`
- `0x180012b04`

## import_xrefs

- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180012bc0`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180012bc0`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180012b6a`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180012b6a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012b42`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012b9b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012b42`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012b9b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012be9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012be9`

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
0x180012b04  mov     rax, rsp
0x180012b07  mov     [rax+8], rbx
0x180012b0b  mov     [rax+10h], rsi
0x180012b0f  push    rdi
0x180012b10  sub     rsp, 40h
0x180012b14  mov     qword ptr [rax-18h], 0
0x180012b1c  mov     rdi, rdx
0x180012b1f  mov     rsi, rcx
0x180012b22  mov     dword ptr [rax-20h], 0
0x180012b29  mov     edx, 40000000h; dwDesiredAccess
0x180012b2e  mov     dword ptr [rax-28h], 3
0x180012b35  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180012b3c  xor     r9d, r9d; lpSecurityAttributes
0x180012b3f  xor     r8d, r8d; dwShareMode
0x180012b42  call    cs:__imp_CreateFileW
0x180012b48  mov     rbx, rax
0x180012b4b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012b4f  jnz     short loc_180012BAA
0x180012b51  call    GetLastError_0
0x180012b56  cmp     eax, 0E7h
0x180012b5b  jnz     loc_180012BF7
0x180012b61  xor     edx, edx; nTimeOut
0x180012b63  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180012b6a  call    cs:__imp_WaitNamedPipeW
0x180012b70  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180012b79  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180012b80  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180012b88  xor     r9d, r9d; lpSecurityAttributes
0x180012b8b  xor     r8d, r8d; dwShareMode
0x180012b8e  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180012b96  mov     edx, 40000000h; dwDesiredAccess
0x180012b9b  call    cs:__imp_CreateFileW
0x180012ba1  mov     rbx, rax
0x180012ba4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012ba8  jz      short loc_180012BF7
0x180012baa  xor     r9d, r9d; lpCollectDataTimeout
0x180012bad  mov     [rsp+48h+Mode], 2
0x180012bb5  xor     r8d, r8d; lpMaxCollectionCount
0x180012bb8  lea     rdx, [rsp+48h+Mode]; lpMode
0x180012bbd  mov     rcx, rbx; hNamedPipe
0x180012bc0  call    cs:__imp_SetNamedPipeHandleState
0x180012bc6  test    eax, eax
0x180012bc8  jz      short loc_180012BF7
0x180012bca  mov     r8d, edi; nNumberOfBytesToWrite
0x180012bcd  mov     [rsp+48h+NumberOfBytesWritten], 0
0x180012bd5  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180012bda  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x180012be3  mov     rdx, rsi; lpBuffer
0x180012be6  mov     rcx, rbx; hFile
0x180012be9  call    cs:__imp_WriteFile
0x180012bef  mov     rcx, rbx; hObject
0x180012bf2  call    CloseHandle_0
0x180012bf7  mov     rbx, [rsp+48h+arg_0]
0x180012bfc  mov     rsi, [rsp+48h+arg_8]
0x180012c01  add     rsp, 40h
0x180012c05  pop     rdi
0x180012c06  retn
```
