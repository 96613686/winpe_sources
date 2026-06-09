# File::QueryUsn(void *,ushort const *)

- ea: `0x1800c5fb0`
- end: `0x1800c6236`
- name: `?QueryUsn@File@@SA_JPEAXPEBG@Z`
- size: `646`
- prototype: `__int64 __fastcall(HANDLE hDevice, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800c76d0`
- `0x1800c9400`

## callees

- `0x18001036c`
- `0x1800295dc`
- `0x1800c5fb0`
- `0x1800c93ac`
- `0x1800c93d0`
- `0x1800c99cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c6081`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c6081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c617e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c617e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6217`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800c6192`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800c6192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c60d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c60d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6134`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c6022`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c6022`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x1800c612a`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x1800c612a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c60c5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c61d6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c60c5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800c61d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall File::QueryUsn(HANDLE hDevice, LPCWSTR lpFileName, unsigned int a3, const char *a4)
{
  HANDLE v4; // r14
  HANDLE FileW; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rsi
  wil *v11; // rcx
  unsigned int v12; // r8d
  const char *v13; // r9
  DWORD LastError; // eax
  int v15; // ebx
  unsigned int v16; // ebx
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  HANDLE v20; // rax
  int v22; // eax
  int v23; // ebx
  const char *v24; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  __int64 v26; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+48h] [rbp-30h]
  const std::exception *v28; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 MaximumComponentLength; // [rsp+80h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v32; // [rsp+98h] [rbp+20h]

  try
  {
    v4 = hDevice;
    v27 = 0;
    v32 = 0;
    BytesReturned = 0;
    v26 = -1;
    if ( hDevice == (HANDLE)-1LL )
    {
      if ( !lpFileName )
        wil::details::in1diag3::Throw_Win32(retaddr, 0, a3, a4, dwCreationDisposition);
      FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v26,
        FileW);
      MaximumComponentLength = -1;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&MaximumComponentLength);
      v4 = (HANDLE)v26;
      if ( ((v26 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x950, v6, v7);
    }
    v8 = nOutBufferSize;
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 0xCu, v8);
    v32 = v10;
    if ( !DeviceIoControl(v4, 0x900EBu, 0, 0, v10, nOutBufferSize, &BytesReturned, 0) )
    {
      if ( GetLastError() != 122 )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x95B, v12, v13);
      LODWORD(MaximumComponentLength) = 0;
      if ( GetVolumeInformationByHandleW(v4, 0, 0, 0, (LPDWORD)&MaximumComponentLength, 0, 0, 0) )
      {
        v15 = MaximumComponentLength;
      }
      else
      {
        LastError = GetLastError();
        AslLogCallPrintf(1, "File::QueryUsn", 2403, "GetVolumeInformationByHandleW failed [%d]", LastError);
        v15 = 260;
        LODWORD(MaximumComponentLength) = 260;
      }
      v16 = 2 * v15 + 64;
      LODWORD(nOutBufferSize) = v16;
      v17 = GetProcessHeap();
      v10 = HeapReAlloc(v17, 0xCu, v10, v16);
      v32 = v10;
      if ( !DeviceIoControl(v4, 0x900EBu, 0, 0, v10, nOutBufferSize, &BytesReturned, 0) )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x96C, v18, v19);
    }
    v27 = v10[3];
  }
  catch ( const std::exception *v28 )
  {
    v23 = wil::ResultFromCaughtException(v11);
    v24 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v28 + 8LL))(v28);
    AslLogCallPrintf(1, "File::QueryUsn", 2421, "Exception: 0x%08x %s", v23, v24);
    v10 = v32;
  }
  catch ( ... )
  {
    v22 = wil::ResultFromCaughtException(v11);
    AslLogCallPrintf(1, "File::QueryUsn", 2426, "Exception: [0x%08x]", v22);
    v10 = v32;
  }
  if ( v10 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v10);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
  return v27;
}

```

## disassembly

```asm
0x1800c5fb0  mov     r11, rsp
0x1800c5fb3  push    rbx
0x1800c5fb4  push    rsi
0x1800c5fb5  push    r14
0x1800c5fb7  sub     rsp, 60h
0x1800c5fbb  mov     rax, rdx
0x1800c5fbe  mov     r14, rcx
0x1800c5fc1  mov     [rsp+78h+var_30], 0
0x1800c5fca  mov     [rsp+78h+arg_18], 0
0x1800c5fd6  mov     dword ptr [r11+18h], 0
0x1800c5fde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800c5fe2  mov     [r11-38h], rbx
0x1800c5fe6  cmp     rcx, rbx
0x1800c5fe9  jnz     short loc_1800C606A
0x1800c5feb  test    rax, rax
0x1800c5fee  jnz     short loc_1800C5FFA
0x1800c5ff0  mov     rcx, [rsp+78h]; this
0x1800c5ff5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800c5ffa  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800c6003  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c600b  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c6013  xor     r9d, r9d; lpSecurityAttributes
0x1800c6016  mov     edx, 80000000h; dwDesiredAccess
0x1800c601b  lea     r8d, [r9+7]; dwShareMode
0x1800c601f  mov     rcx, rax; lpFileName
0x1800c6022  call    cs:__imp_CreateFileW
0x1800c6028  mov     rdx, rax
0x1800c602b  lea     rcx, [rsp+78h+var_38]
0x1800c6030  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c6035  mov     [rsp+78h+MaximumComponentLength], rbx
0x1800c603d  lea     rcx, [rsp+78h+MaximumComponentLength]
0x1800c6045  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c604a  mov     r14, [rsp+78h+var_38]
0x1800c604f  lea     rax, [r14+1]
0x1800c6053  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800c6059  jnz     short loc_1800C606A
0x1800c605b  mov     rcx, [rsp+78h]; this
0x1800c6060  mov     edx, 950h; void *
0x1800c6065  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800c606a  mov     ebx, cs:nOutBufferSize
0x1800c6070  call    cs:__imp_GetProcessHeap
0x1800c6076  mov     r8d, ebx; dwBytes
0x1800c6079  mov     edx, 0Ch; dwFlags
0x1800c607e  mov     rcx, rax; hHeap
0x1800c6081  call    cs:__imp_HeapAlloc
0x1800c6087  mov     rsi, rax
0x1800c608a  mov     [rsp+78h+arg_18], rax
0x1800c6092  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800c609b  lea     rax, [rsp+78h+BytesReturned]
0x1800c60a3  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x1800c60a8  mov     ecx, cs:nOutBufferSize
0x1800c60ae  mov     [rsp+78h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x1800c60b2  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi; lpOutBuffer
0x1800c60b7  xor     r9d, r9d; nInBufferSize
0x1800c60ba  xor     r8d, r8d; lpInBuffer
0x1800c60bd  mov     edx, 900EBh; dwIoControlCode
0x1800c60c2  mov     rcx, r14; hDevice
0x1800c60c5  call    cs:__imp_DeviceIoControl
0x1800c60cb  test    eax, eax
0x1800c60cd  jnz     loc_1800C61EF
0x1800c60d3  call    cs:__imp_GetLastError
0x1800c60d9  cmp     eax, 7Ah ; 'z'
0x1800c60dc  jz      short loc_1800C60ED
0x1800c60de  mov     rcx, [rsp+78h]; this
0x1800c60e3  mov     edx, 95Bh; void *
0x1800c60e8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800c60ed  mov     dword ptr [rsp+78h+MaximumComponentLength], 0
0x1800c60f8  mov     dword ptr [rsp+78h+lpOverlapped], 0; nFileSystemNameSize
0x1800c6100  mov     [rsp+78h+hTemplateFile], 0; lpFileSystemNameBuffer
0x1800c6109  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpFileSystemFlags
0x1800c6112  lea     rax, [rsp+78h+MaximumComponentLength]
0x1800c611a  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMaximumComponentLength
0x1800c611f  xor     r9d, r9d; lpVolumeSerialNumber
0x1800c6122  xor     r8d, r8d; nVolumeNameSize
0x1800c6125  xor     edx, edx; lpVolumeNameBuffer
0x1800c6127  mov     rcx, r14; hFile
0x1800c612a  call    cs:__imp_GetVolumeInformationByHandleW
0x1800c6130  test    eax, eax
0x1800c6132  jnz     short loc_1800C616A
0x1800c6134  call    cs:__imp_GetLastError
0x1800c613a  mov     [rsp+78h+dwCreationDisposition], eax
0x1800c613e  lea     r9, aGetvolumeinfor; "GetVolumeInformationByHandleW failed [%"...
0x1800c6145  mov     r8d, 963h
0x1800c614b  lea     rdx, aFileQueryusn; "File::QueryUsn"
0x1800c6152  mov     ecx, 1
0x1800c6157  call    AslLogCallPrintf
0x1800c615c  mov     ebx, 104h
0x1800c6161  mov     dword ptr [rsp+78h+MaximumComponentLength], ebx
0x1800c6168  jmp     short loc_1800C6171
0x1800c616a  mov     ebx, dword ptr [rsp+78h+MaximumComponentLength]
0x1800c6171  lea     ebx, ds:40h[rbx*2]
0x1800c6178  mov     cs:nOutBufferSize, ebx
0x1800c617e  call    cs:__imp_GetProcessHeap
0x1800c6184  mov     r9d, ebx; dwBytes
0x1800c6187  mov     r8, rsi; lpMem
0x1800c618a  mov     edx, 0Ch; dwFlags
0x1800c618f  mov     rcx, rax; hHeap
0x1800c6192  call    cs:__imp_HeapReAlloc
0x1800c6198  mov     rsi, rax
0x1800c619b  mov     [rsp+78h+arg_18], rax
0x1800c61a3  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800c61ac  lea     rax, [rsp+78h+BytesReturned]
0x1800c61b4  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x1800c61b9  mov     eax, cs:nOutBufferSize
0x1800c61bf  mov     [rsp+78h+dwFlagsAndAttributes], eax; nOutBufferSize
0x1800c61c3  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi; lpOutBuffer
0x1800c61c8  xor     r9d, r9d; nInBufferSize
0x1800c61cb  xor     r8d, r8d; lpInBuffer
0x1800c61ce  mov     edx, 900EBh; dwIoControlCode
0x1800c61d3  mov     rcx, r14; hDevice
0x1800c61d6  call    cs:__imp_DeviceIoControl
0x1800c61dc  test    eax, eax
0x1800c61de  jnz     short loc_1800C61EF
0x1800c61e0  mov     rcx, [rsp+78h]; this
0x1800c61e5  mov     edx, 96Ch; void *
0x1800c61ea  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800c61ef  mov     rax, [rsi+18h]
0x1800c61f3  mov     [rsp+78h+var_30], rax
0x1800c61f8  jmp     short loc_1800C6204
0x1800c61fa  jmp     short $+2
0x1800c61fc  mov     rsi, [rsp+78h+arg_18]
0x1800c6204  test    rsi, rsi
0x1800c6207  jz      short loc_1800C621E
0x1800c6209  call    cs:__imp_GetProcessHeap
0x1800c620f  mov     rcx, rax; hHeap
0x1800c6212  mov     r8, rsi; lpMem
0x1800c6215  xor     edx, edx; dwFlags
0x1800c6217  call    cs:__imp_HeapFree
0x1800c621d  nop
0x1800c621e  lea     rcx, [rsp+78h+var_38]
0x1800c6223  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c6228  mov     rax, [rsp+78h+var_30]
0x1800c622d  add     rsp, 60h
0x1800c6231  pop     r14
0x1800c6233  pop     rsi
0x1800c6234  pop     rbx
0x1800c6235  retn
```
