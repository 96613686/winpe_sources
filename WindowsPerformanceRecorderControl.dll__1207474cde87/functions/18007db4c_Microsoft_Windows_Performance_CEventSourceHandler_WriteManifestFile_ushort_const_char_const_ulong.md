# Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(ushort const *,char const *,ulong)

- ea: `0x18007db4c`
- end: `0x18007dbf3`
- name: `?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBGPEBDK@Z`
- size: `167`
- prototype: `int(Microsoft::Windows::Performance::CEventSourceHandler *__hidden this, const unsigned __int16 *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007c33c`

## callees

- `0x18007db4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007db93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dbca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007db93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dbca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007dbe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007dbe2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007db85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007db85`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007dbc0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007dbc0`

## pseudocode

```c
int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(
        Microsoft::Windows::Performance::CEventSourceHandler *this,
        const unsigned __int16 *a2,
        const char *a3,
        DWORD a4)
{
  HANDLE FileW; // rax
  void *v7; // rdi
  int result; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  Microsoft::Windows::Performance::CEventSourceHandler *NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF

  NumberOfBytesWritten = this;
  FileW = CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v7 = FileW;
  if ( FileW )
  {
    v9 = 0;
    LODWORD(NumberOfBytesWritten) = 0;
    if ( !WriteFile(FileW, a3, a4, (LPDWORD)&NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v7);
    return v9;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18007db4c  mov     rax, rsp
0x18007db4f  mov     [rax+8], rcx
0x18007db53  push    rbx
0x18007db54  push    rbp
0x18007db55  push    rsi
0x18007db56  push    rdi
0x18007db57  sub     rsp, 48h
0x18007db5b  mov     qword ptr [rax-38h], 0
0x18007db63  mov     esi, r9d
0x18007db66  mov     rbp, r8
0x18007db69  mov     dword ptr [rax-40h], 80h
0x18007db70  mov     rcx, rdx; lpFileName
0x18007db73  mov     dword ptr [rax-48h], 2
0x18007db7a  xor     r9d, r9d; lpSecurityAttributes
0x18007db7d  xor     r8d, r8d; dwShareMode
0x18007db80  mov     edx, 40000000h; dwDesiredAccess
0x18007db85  call    cs:__imp_CreateFileW
0x18007db8b  mov     rdi, rax
0x18007db8e  test    rax, rax
0x18007db91  jnz     short loc_18007DBA7
0x18007db93  call    cs:__imp_GetLastError
0x18007db99  test    eax, eax
0x18007db9b  jle     short loc_18007DBEA
0x18007db9d  movzx   eax, ax
0x18007dba0  or      eax, 80070000h
0x18007dba5  jmp     short loc_18007DBEA
0x18007dba7  xor     ebx, ebx
0x18007dba9  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007dbae  mov     r8d, esi; nNumberOfBytesToWrite
0x18007dbb1  mov     dword ptr [rsp+68h+NumberOfBytesWritten], ebx
0x18007dbb5  mov     rdx, rbp; lpBuffer
0x18007dbb8  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x18007dbbd  mov     rcx, rdi; hFile
0x18007dbc0  call    cs:__imp_WriteFile
0x18007dbc6  test    eax, eax
0x18007dbc8  jnz     short loc_18007DBDF
0x18007dbca  call    cs:__imp_GetLastError
0x18007dbd0  mov     ebx, eax
0x18007dbd2  test    eax, eax
0x18007dbd4  jle     short loc_18007DBDF
0x18007dbd6  movzx   ebx, ax
0x18007dbd9  or      ebx, 80070000h
0x18007dbdf  mov     rcx, rdi; hObject
0x18007dbe2  call    cs:__imp_CloseHandle
0x18007dbe8  mov     eax, ebx
0x18007dbea  add     rsp, 48h
0x18007dbee  pop     rdi
0x18007dbef  pop     rsi
0x18007dbf0  pop     rbp
0x18007dbf1  pop     rbx
0x18007dbf2  retn
```
