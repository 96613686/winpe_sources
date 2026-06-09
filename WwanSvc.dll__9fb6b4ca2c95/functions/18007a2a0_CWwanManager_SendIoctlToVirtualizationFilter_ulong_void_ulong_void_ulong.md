# CWwanManager::SendIoctlToVirtualizationFilter(ulong,void *,ulong,void *,ulong)

- ea: `0x18007a2a0`
- end: `0x18007a42a`
- name: `?SendIoctlToVirtualizationFilter@CWwanManager@@AEAAKKPEAXK0K@Z`
- size: `394`
- prototype: `unsigned int(CWwanManager *__hidden this, unsigned int, void *, unsigned int, void *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180073dd0`
- `0x180073ff4`

## callees

- `0x180012300`
- `0x18007a2a0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007a405`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007a405`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a34a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007a34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a31b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a417`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a417`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a301`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007a301`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007a3a2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007a3a2`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18007a3e5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18007a3e5`

## string_xrefs

- `0x18007a321`: `Failed to open handle to vwifi [%u]`
- `0x18007a360`: `Failed to create overlapped.hEvent for vwifi [%u]`

## pseudocode

```c
__int64 __fastcall CWwanManager::SendIoctlToVirtualizationFilter(CWwanManager *this, __int64 a2, void *a3)
{
  DWORD LastError; // eax
  const unsigned __int16 *v6; // r8
  ULONG v7; // ebx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesTransferred = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( *((_QWORD *)this + 30) == -1 )
    *((_QWORD *)this + 30) = CreateFileW(*((LPCWSTR *)this + 31), 0x80000000, 1u, 0, 3u, 0x40000080u, 0);
  if ( *((_QWORD *)this + 30) == -1 )
  {
    LastError = GetLastError();
    v6 = L"Failed to open handle to vwifi [%u]";
LABEL_5:
    v7 = LastError;
    WwanLog::Error("CWwanManager::SendIoctlToVirtualizationFilter", 0, v6, LastError);
    goto LABEL_14;
  }
  Overlapped.hEvent = CreateEventW(0, 0, 0, 0);
  if ( !Overlapped.hEvent )
  {
    LastError = GetLastError();
    v6 = L"Failed to create overlapped.hEvent for vwifi [%u]";
    goto LABEL_5;
  }
  if ( !DeviceIoControl(*((HANDLE *)this + 30), 0x120020u, a3, 0x24u, 0, 0, 0, &Overlapped) && GetLastError() != 997 )
  {
    LastError = GetLastError();
    v6 = L"Failed to send IOCTL to vwifi [%u]";
    goto LABEL_5;
  }
  if ( !GetOverlappedResult(*((HANDLE *)this + 30), &Overlapped, &NumberOfBytesTransferred, 1) )
  {
    LastError = GetLastError();
    v6 = L"IOCTL request to vwifi failed asynchronously [%u]";
    goto LABEL_5;
  }
  v7 = RtlNtStatusToDosErrorNoTeb(Overlapped.Internal);
LABEL_14:
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  return v7;
}

```

## disassembly

```asm
0x18007a2a0  mov     rax, rsp
0x18007a2a3  mov     [rax+8], rbx
0x18007a2a7  mov     [rax+20h], r9d
0x18007a2ab  push    rdi
0x18007a2ac  sub     rsp, 60h
0x18007a2b0  xorps   xmm0, xmm0
0x18007a2b3  mov     dword ptr [rax+20h], 0
0x18007a2ba  movups  xmmword ptr [rax-28h], xmm0
0x18007a2be  mov     rdi, r8
0x18007a2c1  mov     rbx, rcx
0x18007a2c4  movups  xmmword ptr [rax-18h], xmm0
0x18007a2c8  mov     rax, [rcx+0F0h]
0x18007a2cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007a2d3  jnz     short loc_18007A30E
0x18007a2d5  mov     rcx, [rcx+0F8h]; lpFileName
0x18007a2dc  lea     r8d, [rax+2]; dwShareMode
0x18007a2e0  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18007a2e9  xor     r9d, r9d; lpSecurityAttributes
0x18007a2ec  mov     [rsp+68h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18007a2f4  mov     edx, 80000000h; dwDesiredAccess
0x18007a2f9  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18007a301  call    cs:__imp_CreateFileW
0x18007a307  mov     [rbx+0F0h], rax
0x18007a30e  mov     rax, [rbx+0F0h]
0x18007a315  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007a319  jnz     short loc_18007A340
0x18007a31b  call    cs:__imp_GetLastError
0x18007a321  lea     r8, aFailedToOpenHa; "Failed to open handle to vwifi [%u]"
0x18007a328  mov     r9d, eax
0x18007a32b  lea     rcx, aCwwanmanagerSe_2; "CWwanManager::SendIoctlToVirtualization"...
0x18007a332  xor     edx, edx; struct _GUID *
0x18007a334  mov     ebx, eax
0x18007a336  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007a33b  jmp     loc_18007A40D
0x18007a340  xor     r9d, r9d; lpName
0x18007a343  xor     r8d, r8d; bInitialState
0x18007a346  xor     edx, edx; bManualReset
0x18007a348  xor     ecx, ecx; lpEventAttributes
0x18007a34a  call    cs:__imp_CreateEventW
0x18007a350  mov     [rsp+68h+Overlapped.hEvent], rax
0x18007a355  test    rax, rax
0x18007a358  jnz     short loc_18007A369
0x18007a35a  call    cs:__imp_GetLastError
0x18007a360  lea     r8, aFailedToCreate_12; "Failed to create overlapped.hEvent for "...
0x18007a367  jmp     short loc_18007A328
0x18007a369  mov     rcx, [rbx+0F0h]; hDevice
0x18007a370  lea     rax, [rsp+68h+Overlapped]
0x18007a375  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18007a37a  mov     r9d, 24h ; '$'; nInBufferSize
0x18007a380  mov     [rsp+68h+hTemplateFile], 0; lpBytesReturned
0x18007a389  mov     r8, rdi; lpInBuffer
0x18007a38c  mov     [rsp+68h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18007a394  mov     edx, 120020h; dwIoControlCode
0x18007a399  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOutBuffer
0x18007a3a2  call    cs:__imp_DeviceIoControl
0x18007a3a8  test    eax, eax
0x18007a3aa  jnz     short loc_18007A3CB
0x18007a3ac  call    cs:__imp_GetLastError
0x18007a3b2  cmp     eax, 3E5h
0x18007a3b7  jz      short loc_18007A3CB
0x18007a3b9  call    cs:__imp_GetLastError
0x18007a3bf  lea     r8, aFailedToSendIo; "Failed to send IOCTL to vwifi [%u]"
0x18007a3c6  jmp     loc_18007A328
0x18007a3cb  mov     rcx, [rbx+0F0h]; hFile
0x18007a3d2  lea     r8, [rsp+68h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18007a3da  mov     r9d, 1; bWait
0x18007a3e0  lea     rdx, [rsp+68h+Overlapped]; lpOverlapped
0x18007a3e5  call    cs:__imp_GetOverlappedResult
0x18007a3eb  test    eax, eax
0x18007a3ed  jnz     short loc_18007A401
0x18007a3ef  call    cs:__imp_GetLastError
0x18007a3f5  lea     r8, aIoctlRequestTo; "IOCTL request to vwifi failed asynchron"...
0x18007a3fc  jmp     loc_18007A328
0x18007a401  mov     ecx, dword ptr [rsp+68h+Overlapped.Internal]; Status
0x18007a405  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18007a40b  mov     ebx, eax
0x18007a40d  mov     rcx, [rsp+68h+Overlapped.hEvent]; hObject
0x18007a412  test    rcx, rcx
0x18007a415  jz      short loc_18007A41D
0x18007a417  call    cs:__imp_CloseHandle
0x18007a41d  mov     eax, ebx
0x18007a41f  mov     rbx, [rsp+68h+arg_0]
0x18007a424  add     rsp, 60h
0x18007a428  pop     rdi
0x18007a429  retn
```
