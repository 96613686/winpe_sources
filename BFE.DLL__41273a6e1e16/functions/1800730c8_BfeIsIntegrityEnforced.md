# BfeIsIntegrityEnforced

- ea: `0x1800730c8`
- end: `0x180073251`
- name: `BfeIsIntegrityEnforced`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800654d0`

## callees

- `0x180012d8c`
- `0x1800730c8`
- `0x180073ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800731de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073236`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800730fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800730fb`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180073150`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180073150`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007320d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007320d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18007319d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18007319d`

## string_xrefs

- `0x18007311f`: `CreateFileW`
- `0x180073173`: `CreateFileMappingW`
- `0x1800731ed`: `RtlpImageNtHeader`

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
0x1800730c8  push    rbx
0x1800730ca  push    rbp
0x1800730cb  push    rsi
0x1800730cc  push    rdi
0x1800730cd  push    r14
0x1800730cf  sub     rsp, 40h
0x1800730d3  xor     r9d, r9d; lpSecurityAttributes
0x1800730d6  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800730df  mov     r14, rdx
0x1800730e2  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800730ea  mov     edx, 80000000h; dwDesiredAccess
0x1800730ef  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800730f7  lea     r8d, [r9+1]; dwShareMode
0x1800730fb  call    cs:__imp_CreateFileW
0x180073102  nop     dword ptr [rax+rax+00h]
0x180073107  mov     rsi, rax
0x18007310a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007310e  jnz     short loc_180073133
0x180073110  call    cs:__imp_GetLastError
0x180073117  nop     dword ptr [rax+rax+00h]
0x18007311c  mov     r8d, eax
0x18007311f  lea     rdx, aCreatefilew; "CreateFileW"
0x180073126  call    WfpReportSysErrorAsWinError
0x18007312b  mov     rbx, rax
0x18007312e  jmp     loc_180073242
0x180073133  xor     r9d, r9d; dwMaximumSizeHigh
0x180073136  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18007313f  xor     edx, edx; lpFileMappingAttributes
0x180073141  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180073149  mov     rcx, rsi; hFile
0x18007314c  lea     r8d, [r9+2]; flProtect
0x180073150  call    cs:__imp_CreateFileMappingW
0x180073157  nop     dword ptr [rax+rax+00h]
0x18007315c  mov     rdi, rax
0x18007315f  test    rax, rax
0x180073162  jnz     short loc_180073187
0x180073164  call    cs:__imp_GetLastError
0x18007316b  nop     dword ptr [rax+rax+00h]
0x180073170  mov     r8d, eax
0x180073173  lea     rdx, aCreatefilemapp; "CreateFileMappingW"
0x18007317a  call    WfpReportSysErrorAsWinError
0x18007317f  mov     rbx, rax
0x180073182  jmp     loc_18007322E
0x180073187  xor     r9d, r9d; dwFileOffsetLow
0x18007318a  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180073193  xor     r8d, r8d; dwFileOffsetHigh
0x180073196  mov     rcx, rdi; hFileMappingObject
0x180073199  lea     edx, [r9+4]; dwDesiredAccess
0x18007319d  call    cs:__imp_MapViewOfFile
0x1800731a4  nop     dword ptr [rax+rax+00h]
0x1800731a9  mov     rbp, rax
0x1800731ac  test    rax, rax
0x1800731af  jnz     short loc_1800731D1
0x1800731b1  call    cs:__imp_GetLastError
0x1800731b8  nop     dword ptr [rax+rax+00h]
0x1800731bd  mov     r8d, eax
0x1800731c0  lea     rdx, aMapviewoffile; "MapViewOfFile"
0x1800731c7  call    WfpReportSysErrorAsWinError
0x1800731cc  mov     rbx, rax
0x1800731cf  jmp     short loc_180073219
0x1800731d1  mov     rcx, rbp
0x1800731d4  call    RtlpImageNtHeader
0x1800731d9  test    rax, rax
0x1800731dc  jnz     short loc_1800731FE
0x1800731de  call    cs:__imp_GetLastError
0x1800731e5  nop     dword ptr [rax+rax+00h]
0x1800731ea  mov     r8d, eax
0x1800731ed  lea     rdx, aRtlpimagenthea; "RtlpImageNtHeader"
0x1800731f4  call    WfpReportSysErrorAsWinError
0x1800731f9  mov     rbx, rax
0x1800731fc  jmp     short loc_18007320A
0x1800731fe  movzx   eax, byte ptr [rax+5Eh]
0x180073202  xor     ebx, ebx
0x180073204  shr     eax, 7
0x180073207  mov     [r14], eax
0x18007320a  mov     rcx, rbp; lpBaseAddress
0x18007320d  call    cs:__imp_UnmapViewOfFile
0x180073214  nop     dword ptr [rax+rax+00h]
0x180073219  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18007321d  jz      short loc_18007322E
0x18007321f  mov     rcx, rdi; hObject
0x180073222  call    cs:__imp_CloseHandle
0x180073229  nop     dword ptr [rax+rax+00h]
0x18007322e  test    rsi, rsi
0x180073231  jz      short loc_180073242
0x180073233  mov     rcx, rsi; hObject
0x180073236  call    cs:__imp_CloseHandle
0x18007323d  nop     dword ptr [rax+rax+00h]
0x180073242  mov     rax, rbx
0x180073245  add     rsp, 40h
0x180073249  pop     r14
0x18007324b  pop     rdi
0x18007324c  pop     rsi
0x18007324d  pop     rbp
0x18007324e  pop     rbx
0x18007324f  retn
```
