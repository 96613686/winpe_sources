# VmMigrationTcpTransport::SendSynchronously(VmMigrationTcpTransport::_TRANSPORT_BUFFER *)

- ea: `0x1401e0b30`
- end: `0x1401e0d3f`
- name: `?SendSynchronously@VmMigrationTcpTransport@@IEAAJPEAU_TRANSPORT_BUFFER@1@@Z`
- size: `527`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, struct VmMigrationTcpTransport::_TRANSPORT_BUFFER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401e08b0`

## callees

- `0x140027a4c`
- `0x14005b628`
- `0x14006af38`
- `0x14009d7ac`
- `0x140132940`
- `0x1401e0b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401e0b6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401e0b6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401e0b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401e0b84`
- `WS2_32!WSASend` at `0x1401e0bed`
- `WS2_32!WSASend` at `0x1401e0bed`
- `WS2_32!WSAGetOverlappedResult` at `0x1401e0cb6`
- `WS2_32!WSAGetOverlappedResult` at `0x1401e0cb6`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0c02`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0cc6`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0c02`
- `WS2_32!__imp_WSAGetLastError` at `0x1401e0cc6`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1401e0c89`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1401e0c89`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401e0c4f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1401e0c4f`

## string_xrefs

- `0x1401e0baf`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401e0c6c`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401e0cdd`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1401e0cf9`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VmMigrationTcpTransport::SendSynchronously(HANDLE *this, struct _WSABUF *a2)
{
  signed int LastError; // eax
  unsigned int Error; // eax
  DWORD v6; // eax
  const char *v7; // r9
  unsigned int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  int dwFlags; // [rsp+20h] [rbp-78h]
  unsigned int dwFlagsa; // [rsp+20h] [rbp-78h]
  unsigned int dwFlagsb; // [rsp+20h] [rbp-78h]
  HANDLE EventW; // [rsp+40h] [rbp-58h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-50h] BYREF
  DWORD cbTransfer; // [rsp+68h] [rbp-30h] BYREF
  DWORD v17; // [rsp+6Ch] [rbp-2Ch] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  memset(&Overlapped, 0, 24);
  EventW = CreateEventW(0, 1, 0, 0);
  Overlapped.hEvent = EventW;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  try
  {
    if ( !Overlapped.hEvent )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
        (const char *)(unsigned int)LastError,
        dwFlags);
    if ( WSASend((SOCKET)this[65], a2 + 6, 1u, 0, 0, &Overlapped, 0) == -1 )
    {
      Error = WSAGetLastError();
      if ( Error != 997 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x23D,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)Error,
          dwFlagsa);
      cbTransfer = 0;
      v17 = 0;
      Handles[0] = this[91];
      Handles[1] = Overlapped.hEvent;
      v6 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v6 )
      {
        if ( v6 != 1 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x22A,
            (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
            v7);
      }
      else
      {
        CancelIoEx(this[65], &Overlapped);
      }
      if ( !WSAGetOverlappedResult((SOCKET)this[65], &Overlapped, &cbTransfer, 1, &v17) )
      {
        v8 = WSAGetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x236,
          (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
          (const char *)v8,
          dwFlagsb);
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&EventW);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x244,
                           (unsigned int)"onecore\\vm\\common\\migration\\vmmigrationtcptransport.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1401e0b30  mov     [rsp+arg_10], rbx
0x1401e0b35  push    rdi
0x1401e0b36  sub     rsp, 90h
0x1401e0b3d  mov     rax, cs:__security_cookie
0x1401e0b44  xor     rax, rsp
0x1401e0b47  mov     [rsp+98h+var_18], rax
0x1401e0b4f  mov     rdi, rdx
0x1401e0b52  mov     rbx, rcx
0x1401e0b55  xorps   xmm0, xmm0
0x1401e0b58  movups  xmmword ptr [rsp+98h+Overlapped.Internal], xmm0
0x1401e0b5d  movups  xmmword ptr [rsp+98h+Overlapped.10h], xmm0
0x1401e0b62  xor     r9d, r9d; lpName
0x1401e0b65  xor     r8d, r8d; bInitialState
0x1401e0b68  lea     edx, [r9+1]; bManualReset
0x1401e0b6c  xor     ecx, ecx; lpEventAttributes
0x1401e0b6e  call    cs:__imp_CreateEventW
0x1401e0b75  nop     dword ptr [rax+rax+00h]
0x1401e0b7a  mov     [rsp+98h+var_58], rax
0x1401e0b7f  mov     [rsp+98h+Overlapped.hEvent], rax
0x1401e0b84  call    cs:__imp_GetLastError
0x1401e0b8b  nop     dword ptr [rax+rax+00h]
0x1401e0b90  test    eax, eax
0x1401e0b92  jle     short loc_1401E0B9C
0x1401e0b94  movzx   eax, ax
0x1401e0b97  or      eax, 80070000h
0x1401e0b9c  mov     rcx, [rsp+98h]; this
0x1401e0ba4  cmp     [rsp+98h+Overlapped.hEvent], 0
0x1401e0baa  jnz     short loc_1401E0BC0
0x1401e0bac  mov     r9d, eax; char *
0x1401e0baf  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0bb6  mov     edx, 204h; void *
0x1401e0bbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401e0bc0  lea     rdx, [rdi+60h]; lpBuffers
0x1401e0bc4  mov     [rsp+98h+lpCompletionRoutine], 0; lpCompletionRoutine
0x1401e0bcd  lea     rax, [rsp+98h+Overlapped]
0x1401e0bd2  mov     [rsp+98h+lpOverlapped], rax; lpOverlapped
0x1401e0bd7  mov     [rsp+98h+dwFlags], 0; unsigned int
0x1401e0bdf  xor     r9d, r9d; lpNumberOfBytesSent
0x1401e0be2  lea     r8d, [r9+1]; dwBufferCount
0x1401e0be6  mov     rcx, [rbx+208h]; s
0x1401e0bed  call    cs:__imp_WSASend
0x1401e0bf4  nop     dword ptr [rax+rax+00h]
0x1401e0bf9  cmp     eax, 0FFFFFFFFh
0x1401e0bfc  jnz     loc_1401E0D0B
0x1401e0c02  call    cs:__imp_WSAGetLastError
0x1401e0c09  nop     dword ptr [rax+rax+00h]
0x1401e0c0e  cmp     eax, 3E5h
0x1401e0c13  jnz     loc_1401E0CEE
0x1401e0c19  mov     [rsp+98h+cbTransfer], 0
0x1401e0c21  mov     [rsp+98h+var_2C], 0
0x1401e0c29  mov     rax, [rbx+2D8h]
0x1401e0c30  mov     [rsp+98h+Handles], rax
0x1401e0c35  mov     rax, [rsp+98h+Overlapped.hEvent]
0x1401e0c3a  mov     [rsp+98h+var_20], rax
0x1401e0c3f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1401e0c43  xor     r8d, r8d; bWaitAll
0x1401e0c46  lea     rdx, [rsp+98h+Handles]; lpHandles
0x1401e0c4b  lea     ecx, [r8+2]; nCount
0x1401e0c4f  call    cs:__imp_WaitForMultipleObjects
0x1401e0c56  nop     dword ptr [rax+rax+00h]
0x1401e0c5b  test    eax, eax
0x1401e0c5d  jz      short loc_1401E0C7D
0x1401e0c5f  cmp     eax, 1
0x1401e0c62  jz      short loc_1401E0C95
0x1401e0c64  mov     rcx, [rsp+98h]; this
0x1401e0c6c  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0c73  mov     edx, 22Ah; void *
0x1401e0c78  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401e0c7d  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x1401e0c82  mov     rcx, [rbx+208h]; hFile
0x1401e0c89  call    cs:__imp_CancelIoEx
0x1401e0c90  nop     dword ptr [rax+rax+00h]
0x1401e0c95  lea     rax, [rsp+98h+var_2C]
0x1401e0c9a  mov     qword ptr [rsp+98h+dwFlags], rax; unsigned int
0x1401e0c9f  mov     r9d, 1; fWait
0x1401e0ca5  lea     r8, [rsp+98h+cbTransfer]; lpcbTransfer
0x1401e0caa  lea     rdx, [rsp+98h+Overlapped]; lpOverlapped
0x1401e0caf  mov     rcx, [rbx+208h]; s
0x1401e0cb6  call    cs:__imp_WSAGetOverlappedResult
0x1401e0cbd  nop     dword ptr [rax+rax+00h]
0x1401e0cc2  test    eax, eax
0x1401e0cc4  jnz     short loc_1401E0D0B
0x1401e0cc6  call    cs:__imp_WSAGetLastError
0x1401e0ccd  nop     dword ptr [rax+rax+00h]
0x1401e0cd2  mov     r9d, eax; char *
0x1401e0cd5  mov     rcx, [rsp+98h]; this
0x1401e0cdd  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0ce4  mov     edx, 236h; void *
0x1401e0ce9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1401e0cee  mov     rcx, [rsp+98h]; this
0x1401e0cf6  mov     r9d, eax; char *
0x1401e0cf9  lea     r8, aOnecoreVmCommo_44; "onecore\\vm\\common\\migration\\vmmigra"...
0x1401e0d00  mov     edx, 23Dh; void *
0x1401e0d05  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1401e0d0b  lea     rcx, [rsp+98h+var_58]
0x1401e0d10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1401e0d15  xor     eax, eax
0x1401e0d17  jmp     short loc_1401E0D1D
0x1401e0d19  mov     eax, [rsp+98h+cbTransfer]
0x1401e0d1d  mov     rcx, [rsp+98h+var_18]
0x1401e0d25  xor     rcx, rsp; StackCookie
0x1401e0d28  call    __security_check_cookie
0x1401e0d2d  mov     rbx, [rsp+98h+arg_10]
0x1401e0d35  add     rsp, 90h
0x1401e0d3c  pop     rdi
0x1401e0d3d  retn
```
