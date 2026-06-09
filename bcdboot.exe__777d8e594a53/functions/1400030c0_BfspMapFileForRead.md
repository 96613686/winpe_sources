# BfspMapFileForRead

- ea: `0x1400030c0`
- end: `0x1400032ca`
- name: `BfspMapFileForRead`
- size: `522`
- prototype: `LPVOID __fastcall(LPCWSTR lpFileName, DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000c024`
- `0x14000ff2c`
- `0x140010438`

## callees

- `0x1400030c0`
- `0x140003368`
- `0x14000e628`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000329d`
- `KERNEL32!SetLastError` at `0x14000329d`
- `KERNEL32!GetLastError` at `0x14000310d`
- `KERNEL32!GetLastError` at `0x14000317c`
- `KERNEL32!GetLastError` at `0x140003205`
- `KERNEL32!GetLastError` at `0x140003255`
- `KERNEL32!GetLastError` at `0x14000310d`
- `KERNEL32!GetLastError` at `0x14000317c`
- `KERNEL32!GetLastError` at `0x140003205`
- `KERNEL32!GetLastError` at `0x140003255`
- `KERNEL32!GetFileSizeEx` at `0x140003172`
- `KERNEL32!GetFileSizeEx` at `0x140003172`
- `KERNEL32!CreateFileW` at `0x1400030fe`
- `KERNEL32!CreateFileW` at `0x1400030fe`
- `KERNEL32!CloseHandle` at `0x14000328c`
- `KERNEL32!CloseHandle` at `0x140003295`
- `KERNEL32!CloseHandle` at `0x14000328c`
- `KERNEL32!CloseHandle` at `0x140003295`
- `KERNEL32!CreateFileMappingW` at `0x1400031f7`
- `KERNEL32!CreateFileMappingW` at `0x1400031f7`
- `KERNEL32!MapViewOfFile` at `0x140003247`
- `KERNEL32!MapViewOfFile` at `0x140003247`

## string_xrefs

- `0x140003135`: `Failed to open file %s for read! Error code = %#x`
- `0x140003151`: `Unable to open file %s for read because the file or path does not exist`
- `0x140003222`: `CreateFileMapping(%s) failed! Error code = %#x`

## pseudocode

```c
LPVOID __fastcall BfspMapFileForRead(LPCWSTR lpFileName, DWORD *a2, _QWORD *a3)
{
  LPVOID v3; // r14
  HANDLE FileW; // rax
  void *v8; // rsi
  DWORD LastError; // ebx
  DWORD v10; // eax
  HANDLE FileMappingW; // rbp
  DWORD v12; // eax
  DWORD v13; // eax
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  FileSize.QuadPart = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError - 2 <= 1 )
    {
      BfspLogMessage(2, L"Unable to open file %s for read because the file or path does not exist", lpFileName);
    }
    else
    {
      if ( LastError == 5 || LastError - 32 <= 1 )
        BfspPrintFileOwnerProcess(lpFileName);
      BfspLogMessage(4, L"Failed to open file %s for read! Error code = %#x", lpFileName, LastError);
    }
  }
  else
  {
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      if ( FileSize.HighPart )
      {
        LastError = 87;
        BfspLogMessage(4, L"File %s is too large!", lpFileName);
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
          v13 = GetLastError();
          LastError = v13;
          if ( v13 == 5 || v13 - 32 <= 1 )
            BfspPrintFileOwnerProcess(lpFileName);
          BfspLogMessage(4, L"MapViewOfFile(%s) failed! Error code = %#x", lpFileName, LastError);
          CloseHandle(FileMappingW);
        }
        else
        {
          v12 = GetLastError();
          LastError = v12;
          if ( v12 == 5 || v12 - 32 <= 1 )
            BfspPrintFileOwnerProcess(lpFileName);
          BfspLogMessage(4, L"CreateFileMapping(%s) failed! Error code = %#x", lpFileName, LastError);
        }
      }
    }
    else
    {
      v10 = GetLastError();
      LastError = v10;
      if ( v10 == 5 || v10 - 32 <= 1 )
        BfspPrintFileOwnerProcess(lpFileName);
      BfspLogMessage(4, L"Failed to get file size for %s! Error code = %#x", lpFileName, LastError);
    }
    CloseHandle(v8);
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x1400030c0  mov     rax, rsp
0x1400030c3  push    rbx
0x1400030c4  push    rbp
0x1400030c5  push    rsi
0x1400030c6  push    rdi
0x1400030c7  push    r14
0x1400030c9  push    r15
0x1400030cb  sub     rsp, 48h
0x1400030cf  xor     r14d, r14d
0x1400030d2  mov     qword ptr [rax+20h], 0
0x1400030da  mov     [rax-48h], r14
0x1400030de  mov     rbx, r8
0x1400030e1  mov     r15, rdx
0x1400030e4  mov     [rax-50h], r14d
0x1400030e8  xor     r9d, r9d; lpSecurityAttributes
0x1400030eb  mov     dword ptr [rax-58h], 3
0x1400030f2  lea     r8d, [r14+1]; dwShareMode
0x1400030f6  mov     edx, 80000000h; dwDesiredAccess
0x1400030fb  mov     rdi, rcx
0x1400030fe  call    cs:__imp_CreateFileW
0x140003104  mov     rsi, rax
0x140003107  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000310b  jnz     short loc_140003167
0x14000310d  call    cs:__imp_GetLastError
0x140003113  mov     ebx, eax
0x140003115  add     eax, 0FFFFFFFEh
0x140003118  cmp     eax, 1
0x14000311b  jbe     short loc_14000314E
0x14000311d  cmp     ebx, 5
0x140003120  jz      short loc_14000312A
0x140003122  lea     eax, [rbx-20h]
0x140003125  cmp     eax, 1
0x140003128  ja      short loc_140003132
0x14000312a  mov     rcx, rdi; lpFileName
0x14000312d  call    BfspPrintFileOwnerProcess
0x140003132  mov     r9d, ebx
0x140003135  lea     rdx, aFailedToOpenFi; "Failed to open file %s for read! Error "...
0x14000313c  mov     r8, rdi
0x14000313f  mov     ecx, 4
0x140003144  call    BfspLogMessage
0x140003149  jmp     loc_14000329B
0x14000314e  mov     r8, rdi
0x140003151  lea     rdx, aUnableToOpenFi; "Unable to open file %s for read because"...
0x140003158  mov     ecx, 2
0x14000315d  call    BfspLogMessage
0x140003162  jmp     loc_14000329B
0x140003167  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x14000316f  mov     rcx, rsi; hFile
0x140003172  call    cs:__imp_GetFileSizeEx
0x140003178  test    eax, eax
0x14000317a  jnz     short loc_1400031B5
0x14000317c  call    cs:__imp_GetLastError
0x140003182  mov     ebx, eax
0x140003184  cmp     eax, 5
0x140003187  jz      short loc_140003191
0x140003189  add     eax, 0FFFFFFE0h
0x14000318c  cmp     eax, 1
0x14000318f  ja      short loc_140003199
0x140003191  mov     rcx, rdi; lpFileName
0x140003194  call    BfspPrintFileOwnerProcess
0x140003199  lea     rdx, aFailedToGetFil; "Failed to get file size for %s! Error c"...
0x1400031a0  mov     r8, rdi
0x1400031a3  mov     r9d, ebx
0x1400031a6  mov     ecx, 4
0x1400031ab  call    BfspLogMessage
0x1400031b0  jmp     loc_140003292
0x1400031b5  cmp     dword ptr [rsp+78h+FileSize+4], r14d
0x1400031bd  jz      short loc_1400031DB
0x1400031bf  mov     ebx, 57h ; 'W'
0x1400031c4  lea     rdx, aFileSIsTooLarg; "File %s is too large!"
0x1400031cb  mov     r8, rdi
0x1400031ce  lea     ecx, [rbx-53h]
0x1400031d1  call    BfspLogMessage
0x1400031d6  jmp     loc_140003292
0x1400031db  mov     eax, dword ptr [rsp+78h+FileSize]
0x1400031e2  xor     r9d, r9d; dwMaximumSizeHigh
0x1400031e5  mov     [rsp+78h+lpName], r14; lpName
0x1400031ea  xor     edx, edx; lpFileMappingAttributes
0x1400031ec  mov     rcx, rsi; hFile
0x1400031ef  mov     [rsp+78h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x1400031f3  lea     r8d, [r9+2]; flProtect
0x1400031f7  call    cs:__imp_CreateFileMappingW
0x1400031fd  mov     rbp, rax
0x140003200  test    rax, rax
0x140003203  jnz     short loc_14000322E
0x140003205  call    cs:__imp_GetLastError
0x14000320b  mov     ebx, eax
0x14000320d  cmp     eax, 5
0x140003210  jz      short loc_14000321A
0x140003212  add     eax, 0FFFFFFE0h
0x140003215  cmp     eax, 1
0x140003218  ja      short loc_140003222
0x14000321a  mov     rcx, rdi; lpFileName
0x14000321d  call    BfspPrintFileOwnerProcess
0x140003222  lea     rdx, aCreatefilemapp; "CreateFileMapping(%s) failed! Error cod"...
0x140003229  jmp     loc_1400031A0
0x14000322e  mov     eax, dword ptr [rsp+78h+FileSize]
0x140003235  xor     r9d, r9d; dwFileOffsetLow
0x140003238  xor     r8d, r8d; dwFileOffsetHigh
0x14000323b  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x140003240  mov     rcx, rbp; hFileMappingObject
0x140003243  lea     edx, [r9+4]; dwDesiredAccess
0x140003247  call    cs:__imp_MapViewOfFile
0x14000324d  mov     r14, rax
0x140003250  test    rax, rax
0x140003253  jnz     short loc_1400032A5
0x140003255  call    cs:__imp_GetLastError
0x14000325b  mov     ebx, eax
0x14000325d  cmp     eax, 5
0x140003260  jz      short loc_14000326A
0x140003262  lea     ecx, [rax-20h]
0x140003265  cmp     ecx, 1
0x140003268  ja      short loc_140003272
0x14000326a  mov     rcx, rdi; lpFileName
0x14000326d  call    BfspPrintFileOwnerProcess
0x140003272  mov     r9d, ebx
0x140003275  lea     rdx, aMapviewoffileS; "MapViewOfFile(%s) failed! Error code = "...
0x14000327c  mov     r8, rdi
0x14000327f  mov     ecx, 4
0x140003284  call    BfspLogMessage
0x140003289  mov     rcx, rbp; hObject
0x14000328c  call    cs:__imp_CloseHandle
0x140003292  mov     rcx, rsi; hObject
0x140003295  call    cs:__imp_CloseHandle
0x14000329b  mov     ecx, ebx; dwErrCode
0x14000329d  call    cs:__imp_SetLastError
0x1400032a3  jmp     short loc_1400032BA
0x1400032a5  mov     eax, dword ptr [rsp+78h+FileSize]
0x1400032ac  mov     [r15], eax
0x1400032af  mov     [rbx], rsi
0x1400032b2  mov     [rbx+8], rbp
0x1400032b6  mov     [rbx+10h], r14
0x1400032ba  mov     rax, r14
0x1400032bd  add     rsp, 48h
0x1400032c1  pop     r15
0x1400032c3  pop     r14
0x1400032c5  pop     rdi
0x1400032c6  pop     rsi
0x1400032c7  pop     rbp
0x1400032c8  pop     rbx
0x1400032c9  retn
```
