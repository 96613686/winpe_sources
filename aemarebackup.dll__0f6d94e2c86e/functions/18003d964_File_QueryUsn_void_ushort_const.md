# File::QueryUsn(void *,ushort const *)

- ea: `0x18003d964`
- end: `0x18003dbe9`
- name: `?QueryUsn@File@@SA_JPEAXPEBG@Z`
- size: `645`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800415b0`

## callees

- `0x18003d964`
- `0x180042b68`
- `0x180042b84`
- `0x18004c020`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d9ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003daf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003db75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d9ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003daf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003db75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003db83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003db83`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18003db06`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18003db06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003da00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003da00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003daa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003daa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db97`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d9cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d9cc`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18003da9e`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18003da9e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003da44`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003db4a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003da44`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003db4a`

## pseudocode

```c
__int64 __fastcall File::QueryUsn(void *a1, const unsigned __int16 *a2, unsigned int a3, const char *a4)
{
  char *FileW; // rsi
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // r14
  wil *v10; // rcx
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // ebx
  unsigned int v14; // ebx
  HANDLE v15; // rax
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v18; // rax
  int v20; // eax
  int v21; // ebx
  const char *v22; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-58h]
  char *v25; // [rsp+40h] [rbp-38h]
  __int64 v27; // [rsp+48h] [rbp-30h]
  const std::exception *v28; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  void *MaximumComponentLength; // [rsp+80h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v32; // [rsp+98h] [rbp+20h]

  MaximumComponentLength = a1;
  try
  {
    v32 = 0;
    BytesReturned = 0;
    if ( !a2 )
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x949, a3, a4, dwCreationDisposition);
    FileW = (char *)CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    v25 = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x950, v5, v6);
    v7 = nOutBufferSize;
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 0xCu, v7);
    v32 = v9;
    if ( !DeviceIoControl(FileW, 0x900EBu, 0, 0, v9, nOutBufferSize, &BytesReturned, 0) )
    {
      if ( GetLastError() != 122 )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x95B, v11, v12);
      LODWORD(MaximumComponentLength) = 0;
      if ( GetVolumeInformationByHandleW(FileW, 0, 0, 0, (LPDWORD)&MaximumComponentLength, 0, 0, 0) )
      {
        v13 = (int)MaximumComponentLength;
      }
      else
      {
        dwCreationDispositiona = GetLastError();
        AslLogCallPrintf(1, "File::QueryUsn", 2403, "GetVolumeInformationByHandleW failed [%d]", dwCreationDispositiona);
        v13 = 260;
        LODWORD(MaximumComponentLength) = 260;
      }
      v14 = 2 * v13 + 64;
      LODWORD(nOutBufferSize) = v14;
      v15 = GetProcessHeap();
      v9 = HeapReAlloc(v15, 0xCu, v9, v14);
      v32 = v9;
      if ( !DeviceIoControl(FileW, 0x900EBu, 0, 0, v9, nOutBufferSize, &BytesReturned, 0) )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x96C, v16, v17);
    }
    v27 = v9[3];
  }
  catch ( const std::exception *v28 )
  {
    v21 = wil::ResultFromCaughtException(v10);
    v22 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v28 + 8LL))(v28);
    AslLogCallPrintf(1, "File::QueryUsn", 2421, "Exception: 0x%08x %s", v21, v22);
    FileW = v25;
    v9 = v32;
  }
  catch ( ... )
  {
    v20 = wil::ResultFromCaughtException(v10);
    AslLogCallPrintf(1, "File::QueryUsn", 2426, "Exception: [0x%08x]", v20);
    FileW = v25;
    v9 = v32;
  }
  if ( v9 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v9);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return v27;
}

```

## disassembly

```asm
0x18003d964  mov     r11, rsp
0x18003d967  mov     [r11+8], rcx
0x18003d96b  push    rbx
0x18003d96c  push    rsi
0x18003d96d  push    r14
0x18003d96f  sub     rsp, 60h
0x18003d973  mov     rax, rdx
0x18003d976  mov     [rsp+78h+var_30], 0
0x18003d97f  mov     [rsp+78h+arg_18], 0
0x18003d98b  mov     dword ptr [r11+18h], 0
0x18003d993  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFFh
0x18003d99b  test    rax, rax
0x18003d99e  jz      loc_18003DBAB
0x18003d9a4  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18003d9ad  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003d9b5  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18003d9bd  xor     r9d, r9d; lpSecurityAttributes
0x18003d9c0  mov     edx, 80000000h; dwDesiredAccess
0x18003d9c5  lea     r8d, [r9+7]; dwShareMode
0x18003d9c9  mov     rcx, rax; lpFileName
0x18003d9cc  call    cs:__imp_CreateFileW
0x18003d9d2  mov     rsi, rax
0x18003d9d5  mov     [rsp+78h+var_38], rax
0x18003d9da  inc     rax
0x18003d9dd  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003d9e3  jz      loc_18003DBBA
0x18003d9e9  mov     ebx, cs:nOutBufferSize
0x18003d9ef  call    cs:__imp_GetProcessHeap
0x18003d9f5  mov     r8d, ebx; dwBytes
0x18003d9f8  mov     edx, 0Ch; dwFlags
0x18003d9fd  mov     rcx, rax; hHeap
0x18003da00  call    cs:__imp_HeapAlloc
0x18003da06  mov     r14, rax
0x18003da09  mov     [rsp+78h+arg_18], rax
0x18003da11  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18003da1a  lea     rax, [rsp+78h+BytesReturned]
0x18003da22  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18003da27  mov     ecx, cs:nOutBufferSize
0x18003da2d  mov     [rsp+78h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x18003da31  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18003da36  xor     r9d, r9d; nInBufferSize
0x18003da39  xor     r8d, r8d; lpInBuffer
0x18003da3c  mov     edx, 900EBh; dwIoControlCode
0x18003da41  mov     rcx, rsi; hDevice
0x18003da44  call    cs:__imp_DeviceIoControl
0x18003da4a  test    eax, eax
0x18003da4c  jnz     loc_18003DB58
0x18003da52  call    cs:__imp_GetLastError
0x18003da58  cmp     eax, 7Ah ; 'z'
0x18003da5b  jnz     loc_18003DBC9
0x18003da61  mov     dword ptr [rsp+78h+MaximumComponentLength], 0
0x18003da6c  mov     dword ptr [rsp+78h+lpOverlapped], 0; nFileSystemNameSize
0x18003da74  mov     [rsp+78h+hTemplateFile], 0; lpFileSystemNameBuffer
0x18003da7d  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpFileSystemFlags
0x18003da86  lea     rax, [rsp+78h+MaximumComponentLength]
0x18003da8e  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMaximumComponentLength
0x18003da93  xor     r9d, r9d; lpVolumeSerialNumber
0x18003da96  xor     r8d, r8d; nVolumeNameSize
0x18003da99  xor     edx, edx; lpVolumeNameBuffer
0x18003da9b  mov     rcx, rsi; hFile
0x18003da9e  call    cs:__imp_GetVolumeInformationByHandleW
0x18003daa4  test    eax, eax
0x18003daa6  jnz     short loc_18003DADE
0x18003daa8  call    cs:__imp_GetLastError
0x18003daae  mov     [rsp+78h+dwCreationDisposition], eax
0x18003dab2  lea     r9, aGetvolumeinfor; "GetVolumeInformationByHandleW failed [%"...
0x18003dab9  mov     r8d, 963h
0x18003dabf  lea     rdx, aFileQueryusn; "File::QueryUsn"
0x18003dac6  mov     ecx, 1
0x18003dacb  call    AslLogCallPrintf
0x18003dad0  mov     ebx, 104h
0x18003dad5  mov     dword ptr [rsp+78h+MaximumComponentLength], ebx
0x18003dadc  jmp     short loc_18003DAE5
0x18003dade  mov     ebx, dword ptr [rsp+78h+MaximumComponentLength]
0x18003dae5  lea     ebx, ds:40h[rbx*2]
0x18003daec  mov     cs:nOutBufferSize, ebx
0x18003daf2  call    cs:__imp_GetProcessHeap
0x18003daf8  mov     r9d, ebx; dwBytes
0x18003dafb  mov     r8, r14; lpMem
0x18003dafe  mov     edx, 0Ch; dwFlags
0x18003db03  mov     rcx, rax; hHeap
0x18003db06  call    cs:__imp_HeapReAlloc
0x18003db0c  mov     r14, rax
0x18003db0f  mov     [rsp+78h+arg_18], rax
0x18003db17  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18003db20  lea     rax, [rsp+78h+BytesReturned]
0x18003db28  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18003db2d  mov     eax, cs:nOutBufferSize
0x18003db33  mov     [rsp+78h+dwFlagsAndAttributes], eax; nOutBufferSize
0x18003db37  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18003db3c  xor     r9d, r9d; nInBufferSize
0x18003db3f  xor     r8d, r8d; lpInBuffer
0x18003db42  mov     edx, 900EBh; dwIoControlCode
0x18003db47  mov     rcx, rsi; hDevice
0x18003db4a  call    cs:__imp_DeviceIoControl
0x18003db50  test    eax, eax
0x18003db52  jz      loc_18003DBD8
0x18003db58  mov     rax, [r14+18h]
0x18003db5c  mov     [rsp+78h+var_30], rax
0x18003db61  jmp     short loc_18003DB70
0x18003db63  mov     rsi, [rsp+78h+var_38]
0x18003db68  mov     r14, [rsp+78h+arg_18]
0x18003db70  test    r14, r14
0x18003db73  jz      short loc_18003DB8A
0x18003db75  call    cs:__imp_GetProcessHeap
0x18003db7b  mov     rcx, rax; hHeap
0x18003db7e  mov     r8, r14; lpMem
0x18003db81  xor     edx, edx; dwFlags
0x18003db83  call    cs:__imp_HeapFree
0x18003db89  nop
0x18003db8a  lea     rax, [rsi-1]
0x18003db8e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003db92  ja      short loc_18003DB9D
0x18003db94  mov     rcx, rsi; hObject
0x18003db97  call    cs:__imp_CloseHandle
0x18003db9d  mov     rax, [rsp+78h+var_30]
0x18003dba2  add     rsp, 60h
0x18003dba6  pop     r14
0x18003dba8  pop     rsi
0x18003dba9  pop     rbx
0x18003dbaa  retn
0x18003dbab  mov     rcx, [rsp+78h]; this
0x18003dbb0  mov     edx, 949h; void *
0x18003dbb5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003dbba  mov     rcx, [rsp+78h]; this
0x18003dbbf  mov     edx, 950h; void *
0x18003dbc4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003dbc9  mov     rcx, [rsp+78h]; this
0x18003dbce  mov     edx, 95Bh; void *
0x18003dbd3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003dbd8  mov     rcx, [rsp+78h]; this
0x18003dbdd  mov     edx, 96Ch; void *
0x18003dbe2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
