# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x1800697f8`
- end: `0x1800698f9`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `257`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180028b98`

## callees

- `0x18005ab10`
- `0x18005abc0`
- `0x18005aca0`
- `0x1800697f8`

## import_xrefs

- `KERNEL32!SetNamedPipeHandleState` at `0x1800698b2`
- `KERNEL32!SetNamedPipeHandleState` at `0x1800698b2`
- `KERNEL32!WriteFile` at `0x1800698db`
- `KERNEL32!WriteFile` at `0x1800698db`
- `KERNEL32!WaitNamedPipeW` at `0x18006985d`
- `KERNEL32!WaitNamedPipeW` at `0x18006985d`

## pseudocode

```c
void __fastcall AslLogpWritePipe(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW_0; // rbx
  DWORD Mode; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  FileW_0 = CreateFileW_0(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileW_0 != (HANDLE)-1LL
    || GetLastError_0() == 231
    && (WaitNamedPipeW(L"\\\\.\\pipe\\GmdAslLogger", 0),
        FileW_0 = CreateFileW_0(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0),
        FileW_0 != (HANDLE)-1LL) )
  {
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW_0, &Mode, 0, 0) )
    {
      NumberOfBytesWritten = 0;
      WriteFile(FileW_0, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      CloseHandle_0(FileW_0);
    }
  }
}

```

## disassembly

```asm
0x1800697f8  mov     rax, rsp
0x1800697fb  mov     [rax+8], rbx
0x1800697ff  mov     [rax+10h], rsi
0x180069803  push    rdi
0x180069804  sub     rsp, 40h
0x180069808  mov     qword ptr [rax-18h], 0
0x180069810  mov     rdi, rdx
0x180069813  mov     rsi, rcx
0x180069816  mov     dword ptr [rax-20h], 0
0x18006981d  mov     edx, 40000000h; dwDesiredAccess
0x180069822  mov     dword ptr [rax-28h], 3
0x180069829  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180069830  xor     r9d, r9d; lpSecurityAttributes
0x180069833  xor     r8d, r8d; dwShareMode
0x180069836  call    CreateFileW_0
0x18006983b  mov     rbx, rax
0x18006983e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180069842  jnz     short loc_18006989C
0x180069844  call    GetLastError_0
0x180069849  cmp     eax, 0E7h
0x18006984e  jnz     loc_1800698E9
0x180069854  xor     edx, edx; nTimeOut
0x180069856  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18006985d  call    cs:__imp_WaitNamedPipeW
0x180069863  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18006986c  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x180069873  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18006987b  xor     r9d, r9d; lpSecurityAttributes
0x18006987e  xor     r8d, r8d; dwShareMode
0x180069881  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180069889  mov     edx, 40000000h; dwDesiredAccess
0x18006988e  call    CreateFileW_0
0x180069893  mov     rbx, rax
0x180069896  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006989a  jz      short loc_1800698E9
0x18006989c  xor     r9d, r9d; lpCollectDataTimeout
0x18006989f  mov     [rsp+48h+Mode], 2
0x1800698a7  xor     r8d, r8d; lpMaxCollectionCount
0x1800698aa  lea     rdx, [rsp+48h+Mode]; lpMode
0x1800698af  mov     rcx, rbx; hNamedPipe
0x1800698b2  call    cs:__imp_SetNamedPipeHandleState
0x1800698b8  test    eax, eax
0x1800698ba  jz      short loc_1800698E9
0x1800698bc  mov     r8d, edi; nNumberOfBytesToWrite
0x1800698bf  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1800698c7  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800698cc  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x1800698d5  mov     rdx, rsi; lpBuffer
0x1800698d8  mov     rcx, rbx; hFile
0x1800698db  call    cs:__imp_WriteFile
0x1800698e1  mov     rcx, rbx; hObject
0x1800698e4  call    CloseHandle_0
0x1800698e9  mov     rbx, [rsp+48h+arg_0]
0x1800698ee  mov     rsi, [rsp+48h+arg_8]
0x1800698f3  add     rsp, 40h
0x1800698f7  pop     rdi
0x1800698f8  retn
```
