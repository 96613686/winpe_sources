# BfspUncompressFile

- ea: `0x1400038d4`
- end: `0x1400039fc`
- name: `BfspUncompressFile`
- size: `296`
- prototype: `DWORD __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140009fd4`

## callees

- `0x1400038d4`
- `0x140011b18`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003906`
- `KERNEL32!GetLastError` at `0x1400039b4`
- `KERNEL32!GetLastError` at `0x1400039c7`
- `KERNEL32!GetLastError` at `0x140003906`
- `KERNEL32!GetLastError` at `0x1400039b4`
- `KERNEL32!GetLastError` at `0x1400039c7`
- `KERNEL32!HeapFree` at `0x1400039dd`
- `KERNEL32!HeapFree` at `0x1400039dd`
- `KERNEL32!GetProcessHeap` at `0x1400039cf`
- `KERNEL32!GetProcessHeap` at `0x1400039cf`
- `KERNEL32!DeviceIoControl` at `0x1400039aa`
- `KERNEL32!DeviceIoControl` at `0x1400039aa`
- `KERNEL32!CreateFileW` at `0x140003967`
- `KERNEL32!CreateFileW` at `0x140003967`
- `KERNEL32!GetFileAttributesW` at `0x140003914`
- `KERNEL32!GetFileAttributesW` at `0x140003914`
- `KERNEL32!SetFileAttributesW` at `0x140003939`
- `KERNEL32!SetFileAttributesW` at `0x140003939`
- `KERNEL32!CloseHandle` at `0x1400039bf`
- `KERNEL32!CloseHandle` at `0x1400039bf`

## pseudocode

```c
DWORD __fastcall BfspUncompressFile(const wchar_t *a1)
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
0x1400038d4  mov     [rsp+arg_10], rbx
0x1400038d9  mov     [rsp+arg_18], rsi
0x1400038de  push    rdi
0x1400038df  sub     rsp, 40h
0x1400038e3  test    rcx, rcx
0x1400038e6  jz      loc_1400039E7
0x1400038ec  xor     eax, eax
0x1400038ee  cmp     ax, [rcx]
0x1400038f1  jz      loc_1400039E7
0x1400038f7  xor     edx, edx
0x1400038f9  call    PrepareUnicodePathEx
0x1400038fe  mov     rdi, rax
0x140003901  test    rax, rax
0x140003904  jnz     short loc_140003911
0x140003906  call    cs:__imp_GetLastError
0x14000390c  jmp     loc_1400039EC
0x140003911  mov     rcx, rdi; lpFileName
0x140003914  call    cs:__imp_GetFileAttributesW
0x14000391a  cmp     eax, 0FFFFFFFFh
0x14000391d  jz      loc_1400039C7
0x140003923  xor     ebx, ebx
0x140003925  bt      eax, 0Bh
0x140003929  jnb     loc_1400039CF
0x14000392f  mov     esi, 80h
0x140003934  mov     rcx, rdi; lpFileName
0x140003937  mov     edx, esi; dwFileAttributes
0x140003939  call    cs:__imp_SetFileAttributesW
0x14000393f  test    eax, eax
0x140003941  jz      loc_1400039C7
0x140003947  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x14000394c  lea     r8d, [rbx+7]; dwShareMode
0x140003950  mov     [rsp+48h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x140003954  xor     r9d, r9d; lpSecurityAttributes
0x140003957  mov     edx, 0C0010000h; dwDesiredAccess
0x14000395c  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140003964  mov     rcx, rdi; lpFileName
0x140003967  call    cs:__imp_CreateFileW
0x14000396d  mov     rsi, rax
0x140003970  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003974  jz      short loc_1400039C7
0x140003976  xor     ecx, ecx
0x140003978  mov     [rsp+48h+BytesReturned], ebx
0x14000397c  mov     [rsp+48h+lpOverlapped], rcx; lpOverlapped
0x140003981  lea     rax, [rsp+48h+BytesReturned]
0x140003986  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x14000398b  lea     r9d, [rbx+2]; nInBufferSize
0x14000398f  mov     [rsp+48h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x140003993  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x140003998  mov     qword ptr [rsp+48h+dwCreationDisposition], rcx; lpOutBuffer
0x14000399d  mov     edx, 9C040h; dwIoControlCode
0x1400039a2  mov     [rsp+48h+InBuffer], cx
0x1400039a7  mov     rcx, rsi; hDevice
0x1400039aa  call    cs:__imp_DeviceIoControl
0x1400039b0  test    eax, eax
0x1400039b2  jnz     short loc_1400039BC
0x1400039b4  call    cs:__imp_GetLastError
0x1400039ba  mov     ebx, eax
0x1400039bc  mov     rcx, rsi; hObject
0x1400039bf  call    cs:__imp_CloseHandle
0x1400039c5  jmp     short loc_1400039CF
0x1400039c7  call    cs:__imp_GetLastError
0x1400039cd  mov     ebx, eax
0x1400039cf  call    cs:__imp_GetProcessHeap
0x1400039d5  mov     r8, rdi; lpMem
0x1400039d8  xor     edx, edx; dwFlags
0x1400039da  mov     rcx, rax; hHeap
0x1400039dd  call    cs:__imp_HeapFree
0x1400039e3  mov     eax, ebx
0x1400039e5  jmp     short loc_1400039EC
0x1400039e7  mov     eax, 57h ; 'W'
0x1400039ec  mov     rbx, [rsp+48h+arg_10]
0x1400039f1  mov     rsi, [rsp+48h+arg_18]
0x1400039f6  add     rsp, 40h
0x1400039fa  pop     rdi
0x1400039fb  retn
```
