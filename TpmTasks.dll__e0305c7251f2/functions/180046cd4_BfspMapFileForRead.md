# BfspMapFileForRead

- ea: `0x180046cd4`
- end: `0x180046eb9`
- name: `BfspMapFileForRead`
- size: `485`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003eda0`
- `0x180046758`
- `0x180051ee4`
- `0x180052400`

## callees

- `0x180046cd4`
- `0x180047280`
- `0x18004cdd4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180046d79`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180046d79`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046d12`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046d12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046e8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046d83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046e84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046e84`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046e42`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180046e42`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180046dfd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180046dfd`

## string_xrefs

- `0x180046d58`: `Unable to open file %s for read because the file or path does not exist`
- `0x180046d3e`: `Failed to open file %s for read! Error code = %#x`
- `0x180046e1d`: `CreateFileMapping(%s) failed! Error code = %#x`

## pseudocode

```c
LPVOID __fastcall BfspMapFileForRead(const WCHAR *a1, DWORD *a2, _QWORD *a3)
{
  LPVOID v3; // r14
  HANDLE FileW; // rax
  void *v8; // rsi
  __int64 LastError; // rbx
  HANDLE FileMappingW; // rbp
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  FileSize.QuadPart = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(LastError) = GetLastError();
    if ( (unsigned int)(LastError - 2) <= 1 )
    {
      BfspLogMessage(2, L"Unable to open file %s for read because the file or path does not exist", a1);
    }
    else
    {
      BfspPrintOwnerProcessOnSharingError(a1, (unsigned int)LastError);
      BfspLogMessage(4, L"Failed to open file %s for read! Error code = %#x", a1, (unsigned int)LastError);
    }
  }
  else
  {
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      if ( FileSize.HighPart )
      {
        LODWORD(LastError) = 87;
        BfspPrintOwnerProcessOnSharingError(a1, 87);
        BfspLogMessage(4, L"File %s is too large!", a1);
      }
      else
      {
        FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, FileSize.LowPart, 0);
        if ( FileMappingW )
        {
          v3 = MapViewOfFile(FileMappingW, 4u, 0, 0, FileSize.LowPart);
          if ( v3 )
          {
            *a2 = FileSize.LowPart;
            *a3 = v8;
            a3[1] = FileMappingW;
            a3[2] = v3;
            return v3;
          }
          LastError = GetLastError();
          BfspPrintOwnerProcessOnSharingError(a1, LastError);
          BfspLogMessage(4, L"MapViewOfFile(%s) failed! Error code = %#x", a1, (unsigned int)LastError);
          CloseHandle(FileMappingW);
        }
        else
        {
          LastError = GetLastError();
          BfspPrintOwnerProcessOnSharingError(a1, LastError);
          BfspLogMessage(4, L"CreateFileMapping(%s) failed! Error code = %#x", a1, (unsigned int)LastError);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      BfspPrintOwnerProcessOnSharingError(a1, LastError);
      BfspLogMessage(4, L"Failed to get file size for %s! Error code = %#x", a1, (unsigned int)LastError);
    }
    CloseHandle(v8);
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x180046cd4  mov     rax, rsp
0x180046cd7  push    rbx
0x180046cd8  push    rbp
0x180046cd9  push    rsi
0x180046cda  push    rdi
0x180046cdb  push    r14
0x180046cdd  push    r15
0x180046cdf  sub     rsp, 48h
0x180046ce3  xor     r14d, r14d
0x180046ce6  mov     qword ptr [rax+20h], 0
0x180046cee  mov     [rax-48h], r14
0x180046cf2  mov     rbx, r8
0x180046cf5  mov     r15, rdx
0x180046cf8  mov     [rax-50h], r14d
0x180046cfc  xor     r9d, r9d; lpSecurityAttributes
0x180046cff  mov     dword ptr [rax-58h], 3
0x180046d06  lea     r8d, [r14+1]; dwShareMode
0x180046d0a  mov     edx, 80000000h; dwDesiredAccess
0x180046d0f  mov     rdi, rcx
0x180046d12  call    cs:__imp_CreateFileW
0x180046d18  mov     rsi, rax
0x180046d1b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046d1f  jnz     short loc_180046D6E
0x180046d21  call    cs:__imp_GetLastError
0x180046d27  mov     ebx, eax
0x180046d29  add     eax, 0FFFFFFFEh
0x180046d2c  cmp     eax, 1
0x180046d2f  jbe     short loc_180046D55
0x180046d31  mov     edx, ebx
0x180046d33  mov     rcx, rdi
0x180046d36  call    BfspPrintOwnerProcessOnSharingError
0x180046d3b  mov     r9d, ebx
0x180046d3e  lea     rdx, aFailedToOpenFi; "Failed to open file %s for read! Error "...
0x180046d45  mov     r8, rdi
0x180046d48  lea     ecx, [rsi+5]
0x180046d4b  call    BfspLogMessage
0x180046d50  jmp     loc_180046E8A
0x180046d55  mov     r8, rdi
0x180046d58  lea     rdx, aUnableToOpenFi; "Unable to open file %s for read because"...
0x180046d5f  mov     ecx, 2
0x180046d64  call    BfspLogMessage
0x180046d69  jmp     loc_180046E8A
0x180046d6e  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x180046d76  mov     rcx, rsi; hFile
0x180046d79  call    cs:__imp_GetFileSizeEx
0x180046d7f  test    eax, eax
0x180046d81  jnz     short loc_180046DB1
0x180046d83  call    cs:__imp_GetLastError
0x180046d89  mov     edx, eax
0x180046d8b  mov     rcx, rdi
0x180046d8e  mov     ebx, eax
0x180046d90  call    BfspPrintOwnerProcessOnSharingError
0x180046d95  lea     rdx, aFailedToGetFil; "Failed to get file size for %s! Error c"...
0x180046d9c  mov     r8, rdi
0x180046d9f  mov     r9d, ebx
0x180046da2  mov     ecx, 4
0x180046da7  call    BfspLogMessage
0x180046dac  jmp     loc_180046E81
0x180046db1  cmp     dword ptr [rsp+78h+FileSize+4], r14d
0x180046db9  jz      short loc_180046DE1
0x180046dbb  mov     ebx, 57h ; 'W'
0x180046dc0  mov     rcx, rdi
0x180046dc3  mov     edx, ebx
0x180046dc5  call    BfspPrintOwnerProcessOnSharingError
0x180046dca  mov     r8, rdi
0x180046dcd  lea     rdx, aFileSIsTooLarg; "File %s is too large!"
0x180046dd4  lea     ecx, [rbx-53h]
0x180046dd7  call    BfspLogMessage
0x180046ddc  jmp     loc_180046E81
0x180046de1  mov     eax, dword ptr [rsp+78h+FileSize]
0x180046de8  xor     r9d, r9d; dwMaximumSizeHigh
0x180046deb  mov     [rsp+78h+lpName], r14; lpName
0x180046df0  xor     edx, edx; lpFileMappingAttributes
0x180046df2  mov     rcx, rsi; hFile
0x180046df5  mov     [rsp+78h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x180046df9  lea     r8d, [r9+2]; flProtect
0x180046dfd  call    cs:__imp_CreateFileMappingW
0x180046e03  mov     rbp, rax
0x180046e06  test    rax, rax
0x180046e09  jnz     short loc_180046E29
0x180046e0b  call    cs:__imp_GetLastError
0x180046e11  mov     edx, eax
0x180046e13  mov     rcx, rdi
0x180046e16  mov     ebx, eax
0x180046e18  call    BfspPrintOwnerProcessOnSharingError
0x180046e1d  lea     rdx, aCreatefilemapp; "CreateFileMapping(%s) failed! Error cod"...
0x180046e24  jmp     loc_180046D9C
0x180046e29  mov     eax, dword ptr [rsp+78h+FileSize]
0x180046e30  xor     r9d, r9d; dwFileOffsetLow
0x180046e33  xor     r8d, r8d; dwFileOffsetHigh
0x180046e36  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x180046e3b  mov     rcx, rbp; hFileMappingObject
0x180046e3e  lea     edx, [r9+4]; dwDesiredAccess
0x180046e42  call    cs:__imp_MapViewOfFile
0x180046e48  mov     r14, rax
0x180046e4b  test    rax, rax
0x180046e4e  jnz     short loc_180046E94
0x180046e50  call    cs:__imp_GetLastError
0x180046e56  mov     edx, eax
0x180046e58  mov     rcx, rdi
0x180046e5b  mov     ebx, eax
0x180046e5d  call    BfspPrintOwnerProcessOnSharingError
0x180046e62  mov     r9d, ebx
0x180046e65  lea     rdx, aMapviewoffileS; "MapViewOfFile(%s) failed! Error code = "...
0x180046e6c  mov     r8, rdi
0x180046e6f  lea     ecx, [r14+4]
0x180046e73  call    BfspLogMessage
0x180046e78  mov     rcx, rbp; hObject
0x180046e7b  call    cs:__imp_CloseHandle
0x180046e81  mov     rcx, rsi; hObject
0x180046e84  call    cs:__imp_CloseHandle
0x180046e8a  mov     ecx, ebx; dwErrCode
0x180046e8c  call    cs:__imp_SetLastError
0x180046e92  jmp     short loc_180046EA9
0x180046e94  mov     eax, dword ptr [rsp+78h+FileSize]
0x180046e9b  mov     [r15], eax
0x180046e9e  mov     [rbx], rsi
0x180046ea1  mov     [rbx+8], rbp
0x180046ea5  mov     [rbx+10h], r14
0x180046ea9  mov     rax, r14
0x180046eac  add     rsp, 48h
0x180046eb0  pop     r15
0x180046eb2  pop     r14
0x180046eb4  pop     rdi
0x180046eb5  pop     rsi
0x180046eb6  pop     rbp
0x180046eb7  pop     rbx
0x180046eb8  retn
```
