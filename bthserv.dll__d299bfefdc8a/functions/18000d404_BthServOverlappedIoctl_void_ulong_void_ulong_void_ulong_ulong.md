# BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x18000d404`
- end: `0x18000d5a6`
- name: `?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z`
- size: `418`
- prototype: `DWORD __fastcall(HANDLE hFile, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void *lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b6f4`
- `0x180013ff4`
- `0x1800148c4`
- `0x180014c44`
- `0x180014f04`
- `0x18001517c`
- `0x1800155c0`
- `0x180015910`
- `0x180015b04`
- `0x180015df8`
- `0x1800160d8`
- `0x180016354`
- `0x180019768`
- `0x180019958`
- `0x18001b2b4`
- `0x18001bf4c`
- `0x18001d5a0`

## callees

- `0x180005788`
- `0x18000944c`
- `0x18000d404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d446`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000d446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d531`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d523`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d541`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d523`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d541`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000d511`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000d511`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d4a4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d4a4`

## pseudocode

```c
DWORD __fastcall BthServOverlappedIoctl(
        HANDLE hFile,
        DWORD dwIoControlCode,
        void *lpInBuffer,
        DWORD nInBufferSize,
        void *lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred)
{
  DWORD *lpBytesReturned; // rsi
  wil::details *v12; // rcx
  HANDLE Event; // rbx
  __int64 v14; // r8
  const char *v15; // r9
  DWORD LastError; // edi
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // r8
  const char *v23; // r9
  int v24; // [rsp+40h] [rbp-68h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  lpBytesReturned = (DWORD *)&v24;
  v24 = 0;
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
  }
  else
  {
    Event = 0;
    if ( (int)wil::details::GetLastErrorFailHr(v12) < 0 )
      return GetLastError();
  }
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = Event;
  if ( DeviceIoControl(
         hFile,
         dwIoControlCode,
         lpInBuffer,
         nInBufferSize,
         lpOutBuffer,
         nOutBufferSize,
         lpBytesReturned,
         &Overlapped) )
  {
    if ( Event )
    {
      if ( !CloseHandle(Event) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    }
    return 0;
  }
  LastError = GetLastError();
  if ( LastError == 997 )
  {
    if ( GetOverlappedResult(hFile, &Overlapped, lpBytesReturned, 1) )
    {
      if ( Event && !CloseHandle(Event) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
      return 0;
    }
    LastError = GetLastError();
    if ( Event && !CloseHandle(Event) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  }
  else if ( Event && !CloseHandle(Event) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000d404  push    rbx
0x18000d406  push    rbp
0x18000d407  push    rsi
0x18000d408  push    rdi
0x18000d409  push    r14
0x18000d40b  push    r15
0x18000d40d  sub     rsp, 78h
0x18000d411  mov     rax, [rsp+0A8h+lpNumberOfBytesTransferred]
0x18000d419  lea     rsi, [rsp+0A8h+var_68]
0x18000d41e  test    rax, rax
0x18000d421  mov     [rsp+0A8h+var_68], 0
0x18000d429  mov     edi, r9d
0x18000d42c  mov     r14, r8
0x18000d42f  cmovnz  rsi, rax
0x18000d433  mov     r15d, edx
0x18000d436  mov     rbp, rcx
0x18000d439  xor     r8d, r8d; dwFlags
0x18000d43c  xor     edx, edx; lpName
0x18000d43e  xor     ecx, ecx; lpEventAttributes
0x18000d440  mov     r9d, 1F0003h; dwDesiredAccess
0x18000d446  call    cs:__imp_CreateEventExW
0x18000d44c  mov     rbx, rax
0x18000d44f  test    rax, rax
0x18000d452  jz      short loc_18000D4C6
0x18000d454  call    cs:__imp_GetLastError
0x18000d45a  lea     rax, [rsp+0A8h+Overlapped]
0x18000d45f  mov     [rsp+0A8h+Overlapped.Internal], 0
0x18000d468  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x18000d46d  xorps   xmm0, xmm0
0x18000d470  mov     eax, [rsp+0A8h+arg_28]
0x18000d477  mov     r9d, edi; nInBufferSize
0x18000d47a  mov     [rsp+0A8h+lpBytesReturned], rsi; lpBytesReturned
0x18000d47f  mov     r8, r14; lpInBuffer
0x18000d482  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x18000d486  mov     edx, r15d; dwIoControlCode
0x18000d489  mov     rax, [rsp+0A8h+arg_20]
0x18000d491  mov     rcx, rbp; hDevice
0x18000d494  mov     [rsp+0A8h+lpOutBuffer], rax; lpOutBuffer
0x18000d499  movdqu  xmmword ptr [rsp+0A8h+Overlapped.InternalHigh], xmm0
0x18000d49f  mov     [rsp+0A8h+Overlapped.hEvent], rbx
0x18000d4a4  call    cs:__imp_DeviceIoControl
0x18000d4aa  test    eax, eax
0x18000d4ac  jz      short loc_18000D4D9
0x18000d4ae  test    rbx, rbx
0x18000d4b1  jz      short loc_18000D52D
0x18000d4b3  mov     rcx, rbx; hObject
0x18000d4b6  call    cs:__imp_CloseHandle
0x18000d4bc  test    eax, eax
0x18000d4be  jz      loc_18000D56D
0x18000d4c4  jmp     short loc_18000D52D
0x18000d4c6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000d4cb  xor     ebx, ebx
0x18000d4cd  test    eax, eax
0x18000d4cf  jns     short loc_18000D45A
0x18000d4d1  call    cs:__imp_GetLastError
0x18000d4d7  jmp     short loc_18000D54D
0x18000d4d9  call    cs:__imp_GetLastError
0x18000d4df  mov     edi, eax
0x18000d4e1  cmp     eax, 3E5h
0x18000d4e6  jz      short loc_18000D500
0x18000d4e8  test    rbx, rbx
0x18000d4eb  jz      short loc_18000D54B
0x18000d4ed  mov     rcx, rbx; hObject
0x18000d4f0  call    cs:__imp_CloseHandle
0x18000d4f6  test    eax, eax
0x18000d4f8  jz      loc_18000D580
0x18000d4fe  jmp     short loc_18000D54B
0x18000d500  mov     r9d, 1; bWait
0x18000d506  lea     rdx, [rsp+0A8h+Overlapped]; lpOverlapped
0x18000d50b  mov     r8, rsi; lpNumberOfBytesTransferred
0x18000d50e  mov     rcx, rbp; hFile
0x18000d511  call    cs:__imp_GetOverlappedResult
0x18000d517  test    eax, eax
0x18000d519  jz      short loc_18000D531
0x18000d51b  test    rbx, rbx
0x18000d51e  jz      short loc_18000D52D
0x18000d520  mov     rcx, rbx; hObject
0x18000d523  call    cs:__imp_CloseHandle
0x18000d529  test    eax, eax
0x18000d52b  jz      short loc_18000D593
0x18000d52d  xor     eax, eax
0x18000d52f  jmp     short loc_18000D54D
0x18000d531  call    cs:__imp_GetLastError
0x18000d537  mov     edi, eax
0x18000d539  test    rbx, rbx
0x18000d53c  jz      short loc_18000D54B
0x18000d53e  mov     rcx, rbx; hObject
0x18000d541  call    cs:__imp_CloseHandle
0x18000d547  test    eax, eax
0x18000d549  jz      short loc_18000D55A
0x18000d54b  mov     eax, edi
0x18000d54d  add     rsp, 78h
0x18000d551  pop     r15
0x18000d553  pop     r14
0x18000d555  pop     rdi
0x18000d556  pop     rsi
0x18000d557  pop     rbp
0x18000d558  pop     rbx
0x18000d559  retn
0x18000d55a  mov     rcx, [rsp+0A8h]; this
0x18000d562  mov     edx, 0A0Bh; void *
0x18000d567  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d56d  mov     rcx, [rsp+0A8h]; this
0x18000d575  mov     edx, 0A0Bh; void *
0x18000d57a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d580  mov     rcx, [rsp+0A8h]; this
0x18000d588  mov     edx, 0A0Bh; void *
0x18000d58d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d593  mov     rcx, [rsp+0A8h]; this
0x18000d59b  mov     edx, 0A0Bh; void *
0x18000d5a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
