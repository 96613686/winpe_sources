# BfspUncompressFile

- ea: `0x1800472f4`
- end: `0x18004741c`
- name: `BfspUncompressFile`
- size: `296`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180049234`

## callees

- `0x1800472f4`
- `0x180053234`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180047359`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180047359`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180047334`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180047334`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047387`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047387`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800473fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800473fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800473ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800473ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800473df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800473df`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800473ca`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800473ca`

## pseudocode

```c
DWORD __fastcall BfspUncompressFile(unsigned __int16 *a1)
{
  const WCHAR *v1; // rax
  WCHAR *v2; // rdi
  DWORD FileAttributesW; // eax
  DWORD LastError; // ebx
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  __int16 InBuffer; // [rsp+50h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF

  if ( a1 && *a1 )
  {
    v1 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v2 = (WCHAR *)v1;
    if ( !v1 )
      return GetLastError();
    FileAttributesW = GetFileAttributesW(v1);
    if ( FileAttributesW != -1 )
    {
      LastError = 0;
      if ( (FileAttributesW & 0x800) == 0 )
      {
LABEL_13:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
        return LastError;
      }
      if ( SetFileAttributesW(v2, 0x80u) )
      {
        FileW = CreateFileW(v2, 0xC0010000, 7u, 0, 3u, 0x80u, 0);
        if ( FileW != (HANDLE)-1LL )
        {
          BytesReturned = 0;
          InBuffer = 0;
          if ( !DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
            LastError = GetLastError();
          CloseHandle(FileW);
          goto LABEL_13;
        }
      }
    }
    LastError = GetLastError();
    goto LABEL_13;
  }
  return 87;
}

```

## disassembly

```asm
0x1800472f4  mov     [rsp+arg_10], rbx
0x1800472f9  mov     [rsp+arg_18], rsi
0x1800472fe  push    rdi
0x1800472ff  sub     rsp, 40h
0x180047303  test    rcx, rcx
0x180047306  jz      loc_180047407
0x18004730c  xor     eax, eax
0x18004730e  cmp     ax, [rcx]
0x180047311  jz      loc_180047407
0x180047317  xor     edx, edx
0x180047319  call    PrepareUnicodePathEx
0x18004731e  mov     rdi, rax
0x180047321  test    rax, rax
0x180047324  jnz     short loc_180047331
0x180047326  call    cs:__imp_GetLastError
0x18004732c  jmp     loc_18004740C
0x180047331  mov     rcx, rdi; lpFileName
0x180047334  call    cs:__imp_GetFileAttributesW
0x18004733a  cmp     eax, 0FFFFFFFFh
0x18004733d  jz      loc_1800473E7
0x180047343  xor     ebx, ebx
0x180047345  bt      eax, 0Bh
0x180047349  jnb     loc_1800473EF
0x18004734f  mov     esi, 80h
0x180047354  mov     rcx, rdi; lpFileName
0x180047357  mov     edx, esi; dwFileAttributes
0x180047359  call    cs:__imp_SetFileAttributesW
0x18004735f  test    eax, eax
0x180047361  jz      loc_1800473E7
0x180047367  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18004736c  lea     r8d, [rbx+7]; dwShareMode
0x180047370  mov     [rsp+48h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180047374  xor     r9d, r9d; lpSecurityAttributes
0x180047377  mov     edx, 0C0010000h; dwDesiredAccess
0x18004737c  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180047384  mov     rcx, rdi; lpFileName
0x180047387  call    cs:__imp_CreateFileW
0x18004738d  mov     rsi, rax
0x180047390  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047394  jz      short loc_1800473E7
0x180047396  xor     ecx, ecx
0x180047398  mov     [rsp+48h+BytesReturned], ebx
0x18004739c  mov     [rsp+48h+lpOverlapped], rcx; lpOverlapped
0x1800473a1  lea     rax, [rsp+48h+BytesReturned]
0x1800473a6  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x1800473ab  lea     r9d, [rbx+2]; nInBufferSize
0x1800473af  mov     [rsp+48h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x1800473b3  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x1800473b8  mov     qword ptr [rsp+48h+dwCreationDisposition], rcx; lpOutBuffer
0x1800473bd  mov     edx, 9C040h; dwIoControlCode
0x1800473c2  mov     [rsp+48h+InBuffer], cx
0x1800473c7  mov     rcx, rsi; hDevice
0x1800473ca  call    cs:__imp_DeviceIoControl
0x1800473d0  test    eax, eax
0x1800473d2  jnz     short loc_1800473DC
0x1800473d4  call    cs:__imp_GetLastError
0x1800473da  mov     ebx, eax
0x1800473dc  mov     rcx, rsi; hObject
0x1800473df  call    cs:__imp_CloseHandle
0x1800473e5  jmp     short loc_1800473EF
0x1800473e7  call    cs:__imp_GetLastError
0x1800473ed  mov     ebx, eax
0x1800473ef  call    cs:__imp_GetProcessHeap
0x1800473f5  mov     r8, rdi; lpMem
0x1800473f8  xor     edx, edx; dwFlags
0x1800473fa  mov     rcx, rax; hHeap
0x1800473fd  call    cs:__imp_HeapFree
0x180047403  mov     eax, ebx
0x180047405  jmp     short loc_18004740C
0x180047407  mov     eax, 57h ; 'W'
0x18004740c  mov     rbx, [rsp+48h+arg_10]
0x180047411  mov     rsi, [rsp+48h+arg_18]
0x180047416  add     rsp, 40h
0x18004741a  pop     rdi
0x18004741b  retn
```
