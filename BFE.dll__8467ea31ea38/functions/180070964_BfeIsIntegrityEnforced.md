# BfeIsIntegrityEnforced

- ea: `0x180070964`
- end: `0x180070ab0`
- name: `BfeIsIntegrityEnforced`
- size: `332`
- prototype: `__int64 __fastcall(const WCHAR *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180063180`

## callees

- `0x18001236c`
- `0x180070964`
- `0x1800714d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800709a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800709ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800709a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800709ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070a9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070a9c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070997`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180070997`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800709e0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800709e0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180070a7f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180070a7f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180070a21`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180070a21`

## string_xrefs

- `0x1800709af`: `CreateFileW`
- `0x1800709f7`: `CreateFileMappingW`
- `0x180070a5f`: `RtlpImageNtHeader`

## pseudocode

```c
__int64 __fastcall BfeIsIntegrityEnforced(const WCHAR *a1, int *a2)
{
  HANDLE FileW; // rax
  void *v4; // rsi
  DWORD LastError; // eax
  __int64 v6; // rcx
  __int64 v7; // rbx
  HANDLE FileMappingW; // rax
  void *v9; // rdi
  DWORD v10; // eax
  __int64 v11; // rcx
  const void *v12; // rax
  const void *v13; // rbp
  DWORD v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  DWORD v17; // eax
  __int64 v18; // rcx

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    return WfpReportSysErrorAsWinError(v6, "CreateFileW", LastError);
  }
  else
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    v9 = FileMappingW;
    if ( FileMappingW )
    {
      v12 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v13 = v12;
      if ( v12 )
      {
        v16 = RtlpImageNtHeader(v12);
        if ( v16 )
        {
          v7 = 0;
          *a2 = *(unsigned __int8 *)(v16 + 94) >> 7;
        }
        else
        {
          v17 = GetLastError();
          v7 = WfpReportSysErrorAsWinError(v18, "RtlpImageNtHeader", v17);
        }
        UnmapViewOfFile(v13);
      }
      else
      {
        v14 = GetLastError();
        v7 = WfpReportSysErrorAsWinError(v15, "MapViewOfFile", v14);
      }
      if ( v9 != (void *)-1LL )
        CloseHandle(v9);
    }
    else
    {
      v10 = GetLastError();
      v7 = WfpReportSysErrorAsWinError(v11, "CreateFileMappingW", v10);
    }
    if ( v4 )
      CloseHandle(v4);
  }
  return v7;
}

```

## disassembly

```asm
0x180070964  push    rbx
0x180070966  push    rbp
0x180070967  push    rsi
0x180070968  push    rdi
0x180070969  push    r14
0x18007096b  sub     rsp, 40h
0x18007096f  xor     r9d, r9d; lpSecurityAttributes
0x180070972  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18007097b  mov     r14, rdx
0x18007097e  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180070986  mov     edx, 80000000h; dwDesiredAccess
0x18007098b  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180070993  lea     r8d, [r9+1]; dwShareMode
0x180070997  call    cs:__imp_CreateFileW
0x18007099d  mov     rsi, rax
0x1800709a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800709a4  jnz     short loc_1800709C3
0x1800709a6  call    cs:__imp_GetLastError
0x1800709ac  mov     r8d, eax
0x1800709af  lea     rdx, aCreatefilew; "CreateFileW"
0x1800709b6  call    WfpReportSysErrorAsWinError
0x1800709bb  mov     rbx, rax
0x1800709be  jmp     loc_180070AA2
0x1800709c3  xor     r9d, r9d; dwMaximumSizeHigh
0x1800709c6  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x1800709cf  xor     edx, edx; lpFileMappingAttributes
0x1800709d1  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800709d9  mov     rcx, rsi; hFile
0x1800709dc  lea     r8d, [r9+2]; flProtect
0x1800709e0  call    cs:__imp_CreateFileMappingW
0x1800709e6  mov     rdi, rax
0x1800709e9  test    rax, rax
0x1800709ec  jnz     short loc_180070A0B
0x1800709ee  call    cs:__imp_GetLastError
0x1800709f4  mov     r8d, eax
0x1800709f7  lea     rdx, aCreatefilemapp; "CreateFileMappingW"
0x1800709fe  call    WfpReportSysErrorAsWinError
0x180070a03  mov     rbx, rax
0x180070a06  jmp     loc_180070A94
0x180070a0b  xor     r9d, r9d; dwFileOffsetLow
0x180070a0e  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180070a17  xor     r8d, r8d; dwFileOffsetHigh
0x180070a1a  mov     rcx, rdi; hFileMappingObject
0x180070a1d  lea     edx, [r9+4]; dwDesiredAccess
0x180070a21  call    cs:__imp_MapViewOfFile
0x180070a27  mov     rbp, rax
0x180070a2a  test    rax, rax
0x180070a2d  jnz     short loc_180070A49
0x180070a2f  call    cs:__imp_GetLastError
0x180070a35  mov     r8d, eax
0x180070a38  lea     rdx, aMapviewoffile; "MapViewOfFile"
0x180070a3f  call    WfpReportSysErrorAsWinError
0x180070a44  mov     rbx, rax
0x180070a47  jmp     short loc_180070A85
0x180070a49  mov     rcx, rbp
0x180070a4c  call    RtlpImageNtHeader
0x180070a51  test    rax, rax
0x180070a54  jnz     short loc_180070A70
0x180070a56  call    cs:__imp_GetLastError
0x180070a5c  mov     r8d, eax
0x180070a5f  lea     rdx, aRtlpimagenthea; "RtlpImageNtHeader"
0x180070a66  call    WfpReportSysErrorAsWinError
0x180070a6b  mov     rbx, rax
0x180070a6e  jmp     short loc_180070A7C
0x180070a70  movzx   eax, byte ptr [rax+5Eh]
0x180070a74  xor     ebx, ebx
0x180070a76  shr     eax, 7
0x180070a79  mov     [r14], eax
0x180070a7c  mov     rcx, rbp; lpBaseAddress
0x180070a7f  call    cs:__imp_UnmapViewOfFile
0x180070a85  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180070a89  jz      short loc_180070A94
0x180070a8b  mov     rcx, rdi; hObject
0x180070a8e  call    cs:__imp_CloseHandle
0x180070a94  test    rsi, rsi
0x180070a97  jz      short loc_180070AA2
0x180070a99  mov     rcx, rsi; hObject
0x180070a9c  call    cs:__imp_CloseHandle
0x180070aa2  mov     rax, rbx
0x180070aa5  add     rsp, 40h
0x180070aa9  pop     r14
0x180070aab  pop     rdi
0x180070aac  pop     rsi
0x180070aad  pop     rbp
0x180070aae  pop     rbx
0x180070aaf  retn
```
