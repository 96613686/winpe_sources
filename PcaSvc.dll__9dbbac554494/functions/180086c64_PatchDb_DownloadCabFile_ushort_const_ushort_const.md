# PatchDb_DownloadCabFile(ushort const *,ushort const *)

- ea: `0x180086c64`
- end: `0x180086f80`
- name: `?PatchDb_DownloadCabFile@@YAKPEBG0@Z`
- size: `796`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18004248c`

## callees

- `0x180012920`
- `0x180086c64`
- `0x180087c20`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180086e98`
- `ntdll!RtlNtStatusToDosError` at `0x180086ed3`
- `ntdll!RtlNtStatusToDosError` at `0x180086e98`
- `ntdll!RtlNtStatusToDosError` at `0x180086ed3`
- `ntdll!RtlFreeHeap` at `0x180086f39`
- `ntdll!RtlFreeHeap` at `0x180086f39`
- `ntdll!RtlAllocateHeap` at `0x180086e26`
- `ntdll!RtlAllocateHeap` at `0x180086e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086f03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086f42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086f42`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180086dcb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180086dcb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180086e76`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180086e76`
- `WINHTTP!WinHttpReadData` at `0x180086e46`
- `WINHTTP!WinHttpReadData` at `0x180086e46`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180086d71`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180086d71`
- `WINHTTP!WinHttpCloseHandle` at `0x180086f51`
- `WINHTTP!WinHttpCloseHandle` at `0x180086f5f`
- `WINHTTP!WinHttpCloseHandle` at `0x180086f51`
- `WINHTTP!WinHttpCloseHandle` at `0x180086f5f`

## string_xrefs

- `0x180086cb7`: `Attempting to query [%ws]`
- `0x180086f09`: `Failed to read data [%d]\n`
- `0x180086de4`: `Failed to create file [%ws]: %d`
- `0x180086ebf`: `Failed to write to file [%d]`
- `0x180086e9e`: `WriteSize and DownloadSize don't match %d %d\n`

## pseudocode

```c
__int64 __fastcall PatchDb_DownloadCabFile(const unsigned __int16 *a1, LPCWSTR lpFileName)
{
  unsigned int v4; // eax
  DWORD v5; // ebx
  void *v6; // rdi
  HANDLE FileW; // r14
  PVOID Heap; // rsi
  ULONG v9; // eax
  const char *v10; // r9
  int v11; // r8d
  DWORD v12; // eax
  DWORD LastError; // eax
  const char *v14; // r9
  int v15; // r8d
  ULONG v16; // eax
  char dwCreationDisposition; // [rsp+20h] [rbp-50h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-50h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-48h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-30h] BYREF
  HINTERNET hRequest; // [rsp+48h] [rbp-28h] BYREF
  HINTERNET hInternet; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR ppwszAcceptTypes[3]; // [rsp+58h] [rbp-18h] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+B0h] [rbp+40h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+B8h] [rbp+48h] BYREF

  hRequest = 0;
  hInternet = 0;
  dwNumberOfBytesAvailable = 0;
  dwNumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  ppwszAcceptTypes[0] = L"*/*";
  ppwszAcceptTypes[1] = 0;
  AslLogCallPrintf(
    3,
    (unsigned int)"PatchDb_DownloadCabFile",
    1660,
    (unsigned int)"Attempting to query [%ws]",
    (char)a1);
  v4 = PatchDb_SendRequest(a1, 0, ppwszAcceptTypes, &hRequest, &hInternet);
  if ( v4
    && (AslLogCallPrintf(
          1,
          (unsigned int)"PatchDb_DownloadCabFile",
          1669,
          (unsigned int)"Failed to send request using default proxy %x",
          v4),
        (v5 = PatchDb_SendRequest(a1, 4u, ppwszAcceptTypes, &hRequest, &hInternet)) != 0) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"PatchDb_DownloadCabFile",
      1678,
      (unsigned int)"Failed to send request using auto proxy",
      dwCreationDisposition);
    v6 = hRequest;
  }
  else
  {
    v6 = hRequest;
    if ( WinHttpQueryDataAvailable(hRequest, &dwNumberOfBytesAvailable) )
    {
      FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LODWORD(dwFlagsAndAttributes) = GetLastError();
        v5 = dwFlagsAndAttributes;
        AslLogCallPrintf(
          1,
          (unsigned int)"PatchDb_DownloadCabFile",
          1705,
          (unsigned int)"Failed to create file [%ws]: %d",
          lpFileName,
          dwFlagsAndAttributes);
      }
      else
      {
        v5 = 8;
        dwNumberOfBytesAvailable = 0x2000;
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2000u);
        if ( Heap )
        {
          while ( WinHttpReadData(v6, Heap, dwNumberOfBytesAvailable, &dwNumberOfBytesRead) )
          {
            if ( !dwNumberOfBytesRead )
              goto LABEL_15;
            if ( dwNumberOfBytesRead > dwNumberOfBytesAvailable )
            {
              v16 = RtlNtStatusToDosError(-1073741306);
              v10 = "Downloaded size more than buffer size [%d] > [%d]";
              v11 = 1730;
              v5 = v16;
              LODWORD(dwFlagsAndAttributes) = dwNumberOfBytesAvailable;
              v12 = dwNumberOfBytesRead;
              goto LABEL_19;
            }
            if ( !WriteFile(FileW, Heap, dwNumberOfBytesRead, &NumberOfBytesWritten, 0) )
            {
              LastError = GetLastError();
              v14 = "Failed to write to file [%d]";
              v15 = 1736;
              goto LABEL_21;
            }
            if ( dwNumberOfBytesRead != NumberOfBytesWritten )
            {
              v9 = RtlNtStatusToDosError(-1073741306);
              v10 = "WriteSize and DownloadSize don't match %d %d\n";
              v11 = 1742;
              v5 = v9;
              LODWORD(dwFlagsAndAttributes) = dwNumberOfBytesRead;
              v12 = NumberOfBytesWritten;
LABEL_19:
              dwCreationDispositiona[0] = v12;
              AslLogCallPrintf(
                1,
                (unsigned int)"PatchDb_DownloadCabFile",
                v11,
                (_DWORD)v10,
                *(_QWORD *)dwCreationDispositiona,
                dwFlagsAndAttributes);
              goto LABEL_22;
            }
            if ( !dwNumberOfBytesRead )
            {
LABEL_15:
              v5 = 0;
              goto LABEL_22;
            }
          }
          LastError = GetLastError();
          v14 = "Failed to read data [%d]\n";
          v15 = 1720;
LABEL_21:
          dwCreationDispositiona[0] = LastError;
          v5 = LastError;
          AslLogCallPrintf(
            1,
            (unsigned int)"PatchDb_DownloadCabFile",
            v15,
            (_DWORD)v14,
            *(_QWORD *)dwCreationDispositiona);
LABEL_22:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        }
        CloseHandle(FileW);
      }
    }
    else
    {
      v5 = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"PatchDb_DownloadCabFile",
        1688,
        (unsigned int)"Failed to verify if data is available: [%d].",
        v5);
    }
  }
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( v6 )
    WinHttpCloseHandle(v6);
  return v5;
}

```

## disassembly

```asm
0x180086c64  mov     [rsp-28h+arg_0], rbx
0x180086c69  mov     [rsp-28h+arg_8], rsi
0x180086c6e  push    rbp
0x180086c6f  push    rdi
0x180086c70  push    r12
0x180086c72  push    r13
0x180086c74  push    r14
0x180086c76  mov     rbp, rsp
0x180086c79  sub     rsp, 70h
0x180086c7d  mov     rsi, rdx
0x180086c80  mov     qword ptr [rsp+70h+dwCreationDisposition], rcx
0x180086c85  mov     rbx, rcx
0x180086c88  mov     [rbp+hRequest], 0
0x180086c90  lea     rax, asc_1801104F8; "*/*"
0x180086c97  mov     [rbp+hInternet], 0
0x180086c9f  lea     r12, aPatchdbDownloa; "PatchDb_DownloadCabFile"
0x180086ca6  mov     [rbp+dwNumberOfBytesAvailable], 0
0x180086cad  mov     rdx, r12
0x180086cb0  mov     [rbp+dwNumberOfBytesRead], 0
0x180086cb7  lea     r9, aAttemptingToQu; "Attempting to query [%ws]"
0x180086cbe  mov     [rbp+NumberOfBytesWritten], 0
0x180086cc5  mov     r8d, 67Ch
0x180086ccb  mov     [rbp+ppwszAcceptTypes], rax
0x180086ccf  mov     ecx, 3
0x180086cd4  mov     [rbp+var_10], 0
0x180086cdc  call    AslLogCallPrintf
0x180086ce1  lea     rax, [rbp+hInternet]
0x180086ce5  xor     edx, edx; dwAccessType
0x180086ce7  lea     r9, [rbp+hRequest]; void **
0x180086ceb  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; void **
0x180086cf0  lea     r8, [rbp+ppwszAcceptTypes]; ppwszAcceptTypes
0x180086cf4  mov     rcx, rbx; unsigned __int16 *
0x180086cf7  call    ?PatchDb_SendRequest@@YAKPEBGKPEAPEBGAEAPEAX2@Z; PatchDb_SendRequest(ushort const *,ulong,ushort const * *,void * &,void * &)
0x180086cfc  mov     r13d, 1
0x180086d02  test    eax, eax
0x180086d04  jz      short loc_180086D66
0x180086d06  lea     r9, aFailedToSendRe; "Failed to send request using default pr"...
0x180086d0d  mov     [rsp+70h+dwCreationDisposition], eax
0x180086d11  mov     r8d, 685h
0x180086d17  mov     rdx, r12
0x180086d1a  mov     ecx, r13d
0x180086d1d  call    AslLogCallPrintf
0x180086d22  lea     rax, [rbp+hInternet]
0x180086d26  mov     rcx, rbx; unsigned __int16 *
0x180086d29  lea     r9, [rbp+hRequest]; void **
0x180086d2d  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; void **
0x180086d32  lea     r8, [rbp+ppwszAcceptTypes]; ppwszAcceptTypes
0x180086d36  lea     edx, [r13+3]; dwAccessType
0x180086d3a  call    ?PatchDb_SendRequest@@YAKPEBGKPEAPEBGAEAPEAX2@Z; PatchDb_SendRequest(ushort const *,ulong,ushort const * *,void * &,void * &)
0x180086d3f  mov     ebx, eax
0x180086d41  test    eax, eax
0x180086d43  jz      short loc_180086D66
0x180086d45  lea     r9, aFailedToSendRe_0; "Failed to send request using auto proxy"
0x180086d4c  mov     r8d, 68Eh
0x180086d52  mov     rdx, r12
0x180086d55  mov     ecx, r13d
0x180086d58  call    AslLogCallPrintf
0x180086d5d  mov     rdi, [rbp+hRequest]
0x180086d61  jmp     loc_180086F48
0x180086d66  mov     rdi, [rbp+hRequest]
0x180086d6a  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x180086d6e  mov     rcx, rdi; hRequest
0x180086d71  call    cs:__imp_WinHttpQueryDataAvailable
0x180086d77  test    eax, eax
0x180086d79  jnz     short loc_180086DA4
0x180086d7b  call    cs:__imp_GetLastError
0x180086d81  lea     r9, aFailedToVerify_4; "Failed to verify if data is available: "...
0x180086d88  mov     r8d, 698h
0x180086d8e  mov     rdx, r12
0x180086d91  mov     [rsp+70h+dwCreationDisposition], eax
0x180086d95  mov     ecx, r13d
0x180086d98  mov     ebx, eax
0x180086d9a  call    AslLogCallPrintf
0x180086d9f  jmp     loc_180086F48
0x180086da4  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180086dad  xor     r9d, r9d; lpSecurityAttributes
0x180086db0  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180086db8  xor     r8d, r8d; dwShareMode
0x180086dbb  mov     edx, 40000000h; dwDesiredAccess
0x180086dc0  mov     [rsp+70h+dwCreationDisposition], 2; dwCreationDisposition
0x180086dc8  mov     rcx, rsi; lpFileName
0x180086dcb  call    cs:__imp_CreateFileW
0x180086dd1  mov     r14, rax
0x180086dd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180086dd8  jnz     short loc_180086E08
0x180086dda  call    cs:__imp_GetLastError
0x180086de0  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], eax
0x180086de4  lea     r9, aFailedToCreate_61; "Failed to create file [%ws]: %d"
0x180086deb  mov     r8d, 6A9h
0x180086df1  mov     qword ptr [rsp+70h+dwCreationDisposition], rsi
0x180086df6  mov     rdx, r12
0x180086df9  mov     ecx, r13d
0x180086dfc  mov     ebx, eax
0x180086dfe  call    AslLogCallPrintf
0x180086e03  jmp     loc_180086F48
0x180086e08  mov     r8d, 2000h; Size
0x180086e0e  mov     ebx, 8
0x180086e13  mov     [rbp+dwNumberOfBytesAvailable], r8d
0x180086e17  mov     edx, ebx; Flags
0x180086e19  mov     rcx, gs:60h
0x180086e22  mov     rcx, [rcx+30h]; HeapHandle
0x180086e26  call    cs:__imp_RtlAllocateHeap
0x180086e2c  mov     rsi, rax
0x180086e2f  test    rax, rax
0x180086e32  jz      loc_180086F3F
0x180086e38  mov     r8d, [rbp+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x180086e3c  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180086e40  mov     rdx, rsi; lpBuffer
0x180086e43  mov     rcx, rdi; hRequest
0x180086e46  call    cs:__imp_WinHttpReadData
0x180086e4c  test    eax, eax
0x180086e4e  jz      loc_180086F03
0x180086e54  mov     r8d, [rbp+dwNumberOfBytesRead]; nNumberOfBytesToWrite
0x180086e58  test    r8d, r8d
0x180086e5b  jz      short loc_180086E8C
0x180086e5d  cmp     r8d, [rbp+dwNumberOfBytesAvailable]
0x180086e61  ja      short loc_180086ECE
0x180086e63  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180086e67  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180086e70  mov     rdx, rsi; lpBuffer
0x180086e73  mov     rcx, r14; hFile
0x180086e76  call    cs:__imp_WriteFile
0x180086e7c  test    eax, eax
0x180086e7e  jz      short loc_180086EB9
0x180086e80  mov     eax, [rbp+dwNumberOfBytesRead]
0x180086e83  cmp     eax, [rbp+NumberOfBytesWritten]
0x180086e86  jnz     short loc_180086E93
0x180086e88  test    eax, eax
0x180086e8a  jnz     short loc_180086E38
0x180086e8c  xor     ebx, ebx
0x180086e8e  jmp     loc_180086F27
0x180086e93  mov     ecx, 0C0000206h; Status
0x180086e98  call    cs:__imp_RtlNtStatusToDosError
0x180086e9e  lea     r9, aWritesizeAndDo; "WriteSize and DownloadSize don't match "...
0x180086ea5  mov     r8d, 6CEh
0x180086eab  mov     ebx, eax
0x180086ead  mov     eax, [rbp+dwNumberOfBytesRead]
0x180086eb0  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], eax
0x180086eb4  mov     eax, [rbp+NumberOfBytesWritten]
0x180086eb7  jmp     short loc_180086EF2
0x180086eb9  call    cs:__imp_GetLastError
0x180086ebf  lea     r9, aFailedToWriteT_2; "Failed to write to file [%d]"
0x180086ec6  mov     r8d, 6C8h
0x180086ecc  jmp     short loc_180086F16
0x180086ece  mov     ecx, 0C0000206h; Status
0x180086ed3  call    cs:__imp_RtlNtStatusToDosError
0x180086ed9  lea     r9, aDownloadedSize; "Downloaded size more than buffer size ["...
0x180086ee0  mov     r8d, 6C2h
0x180086ee6  mov     ebx, eax
0x180086ee8  mov     eax, [rbp+dwNumberOfBytesAvailable]
0x180086eeb  mov     dword ptr [rsp+70h+dwFlagsAndAttributes], eax
0x180086eef  mov     eax, [rbp+dwNumberOfBytesRead]
0x180086ef2  mov     rdx, r12
0x180086ef5  mov     [rsp+70h+dwCreationDisposition], eax
0x180086ef9  mov     ecx, r13d
0x180086efc  call    AslLogCallPrintf
0x180086f01  jmp     short loc_180086F27
0x180086f03  call    cs:__imp_GetLastError
0x180086f09  lea     r9, aFailedToReadDa; "Failed to read data [%d]\n"
0x180086f10  mov     r8d, 6B8h
0x180086f16  mov     rdx, r12
0x180086f19  mov     [rsp+70h+dwCreationDisposition], eax
0x180086f1d  mov     ecx, r13d
0x180086f20  mov     ebx, eax
0x180086f22  call    AslLogCallPrintf
0x180086f27  mov     rcx, gs:60h
0x180086f30  mov     r8, rsi; P
0x180086f33  xor     edx, edx; Flags
0x180086f35  mov     rcx, [rcx+30h]; HeapHandle
0x180086f39  call    cs:__imp_RtlFreeHeap
0x180086f3f  mov     rcx, r14; hObject
0x180086f42  call    cs:__imp_CloseHandle
0x180086f48  mov     rcx, [rbp+hInternet]; hInternet
0x180086f4c  test    rcx, rcx
0x180086f4f  jz      short loc_180086F57
0x180086f51  call    cs:__imp_WinHttpCloseHandle
0x180086f57  test    rdi, rdi
0x180086f5a  jz      short loc_180086F65
0x180086f5c  mov     rcx, rdi; hInternet
0x180086f5f  call    cs:__imp_WinHttpCloseHandle
0x180086f65  lea     r11, [rsp+70h+var_s0]
0x180086f6a  mov     eax, ebx
0x180086f6c  mov     rbx, [r11+30h]
0x180086f70  mov     rsi, [r11+38h]
0x180086f74  mov     rsp, r11
0x180086f77  pop     r14
0x180086f79  pop     r13
0x180086f7b  pop     r12
0x180086f7d  pop     rdi
0x180086f7e  pop     rbp
0x180086f7f  retn
```
