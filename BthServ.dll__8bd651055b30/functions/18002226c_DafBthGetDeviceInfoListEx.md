# DafBthGetDeviceInfoListEx

- ea: `0x18002226c`
- end: `0x180022472`
- name: `DafBthGetDeviceInfoListEx`
- size: `518`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002103c`

## callees

- `0x180001790`
- `0x180002470`
- `0x18000247c`
- `0x1800024ac`
- `0x18002226c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800222cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800222cb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800223b4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800223b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002241a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002241a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022447`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022447`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022355`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022410`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022355`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022410`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002232b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800223e6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002232b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800223e6`

## pseudocode

```c
__int64 __fastcall DafBthGetDeviceInfoListEx(HANDLE hFile, __int64 a2, _QWORD *a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  DWORD nOutBufferSize; // ebx
  _DWORD *v8; // rax
  _DWORD *lpOutBuffer; // rdi
  HANDLE hEvent; // rcx
  signed int v11; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-19h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-11h] BYREF
  _DWORD OutBuffer[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v16; // [rsp+70h] [rbp+17h]

  BytesReturned = 0;
  OutBuffer[1] = 3;
  OutBuffer[0] = 3;
  memset(&Overlapped, 0, 24);
  v16 = 0;
  Overlapped.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Overlapped.hEvent )
    goto LABEL_2;
  if ( !DeviceIoControl(hFile, 0x411058u, OutBuffer, 0x18u, OutBuffer, 0x18u, &BytesReturned, &Overlapped) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 997 )
    {
LABEL_3:
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_20;
    }
    if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
    {
LABEL_2:
      LastError = GetLastError();
      v6 = LastError;
      goto LABEL_3;
    }
  }
  if ( !DWORD2(v16) )
  {
    v6 = -2147023728;
    goto LABEL_20;
  }
  nOutBufferSize = 832 * DWORD2(v16) + 24;
  v8 = o_malloc_0(nOutBufferSize);
  lpOutBuffer = v8;
  if ( !v8 )
  {
    v6 = -2147024882;
    goto LABEL_20;
  }
  memset_0(v8, 0, nOutBufferSize);
  hEvent = Overlapped.hEvent;
  lpOutBuffer[1] = 3;
  *lpOutBuffer = 3;
  ResetEvent(hEvent);
  if ( DeviceIoControl(hFile, 0x411058u, lpOutBuffer, 0x18u, lpOutBuffer, nOutBufferSize, &BytesReturned, &Overlapped) )
    goto LABEL_19;
  v11 = GetLastError();
  v6 = v11;
  if ( v11 == 997 )
  {
    if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
    {
      v11 = GetLastError();
      v6 = v11;
      goto LABEL_16;
    }
LABEL_19:
    v6 = 0;
    *a3 = lpOutBuffer;
    goto LABEL_20;
  }
LABEL_16:
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80070000;
  free(lpOutBuffer);
LABEL_20:
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  return v6;
}

```

## disassembly

```asm
0x18002226c  mov     [rsp-8+arg_8], rbx
0x180022271  push    rbp
0x180022272  push    rsi
0x180022273  push    rdi
0x180022274  push    r14
0x180022276  push    r15
0x180022278  lea     rbp, [rsp-37h]
0x18002227d  sub     rsp, 90h
0x180022284  mov     rax, cs:__security_cookie
0x18002228b  xor     rax, rsp
0x18002228e  mov     [rbp+57h+var_30], rax
0x180022292  mov     eax, 3
0x180022297  mov     [rbp+57h+BytesReturned], 0
0x18002229e  xorps   xmm0, xmm0
0x1800222a1  mov     [rbp+57h+var_44], eax
0x1800222a4  mov     r15, r8
0x1800222a7  mov     [rbp+57h+OutBuffer], eax
0x1800222aa  mov     rsi, rcx
0x1800222ad  xorps   xmm1, xmm1
0x1800222b0  lea     r8d, [rax-2]; dwFlags
0x1800222b4  xor     edx, edx; lpName
0x1800222b6  xor     ecx, ecx; lpEventAttributes
0x1800222b8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800222be  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1800222c2  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1800222c6  movdqu  [rbp+57h+var_40], xmm1
0x1800222cb  call    cs:__imp_CreateEventExW
0x1800222d1  mov     [rbp+57h+Overlapped.hEvent], rax
0x1800222d5  test    rax, rax
0x1800222d8  jnz     short loc_1800222F8
0x1800222da  call    cs:__imp_GetLastError
0x1800222e0  mov     ebx, eax
0x1800222e2  test    eax, eax
0x1800222e4  jle     loc_18002243E
0x1800222ea  movzx   ebx, ax
0x1800222ed  or      ebx, 80070000h
0x1800222f3  jmp     loc_18002243E
0x1800222f8  mov     ecx, 18h
0x1800222fd  lea     rax, [rbp+57h+Overlapped]
0x180022301  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x180022306  lea     r8, [rbp+57h+OutBuffer]; lpInBuffer
0x18002230a  lea     rax, [rbp+57h+BytesReturned]
0x18002230e  mov     r9d, ecx; nInBufferSize
0x180022311  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x180022316  mov     edx, 411058h; dwIoControlCode
0x18002231b  mov     [rsp+0B0h+nOutBufferSize], ecx; nOutBufferSize
0x18002231f  lea     rax, [rbp+57h+OutBuffer]
0x180022323  mov     rcx, rsi; hDevice
0x180022326  mov     [rsp+0B0h+lpOutBuffer], rax; lpOutBuffer
0x18002232b  call    cs:__imp_DeviceIoControl
0x180022331  test    eax, eax
0x180022333  jnz     short loc_180022363
0x180022335  call    cs:__imp_GetLastError
0x18002233b  mov     ebx, eax
0x18002233d  cmp     eax, 3E5h
0x180022342  jnz     short loc_1800222E2
0x180022344  mov     r9d, 1; bWait
0x18002234a  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x18002234e  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180022352  mov     rcx, rsi; hFile
0x180022355  call    cs:__imp_GetOverlappedResult
0x18002235b  test    eax, eax
0x18002235d  jz      loc_1800222DA
0x180022363  mov     eax, dword ptr [rbp+57h+var_40+8]
0x180022366  test    eax, eax
0x180022368  jnz     short loc_180022374
0x18002236a  mov     ebx, 80070490h
0x18002236f  jmp     loc_18002243E
0x180022374  imul    ebx, eax, 340h
0x18002237a  add     ebx, 18h
0x18002237d  mov     ecx, ebx; Size
0x18002237f  mov     r14d, ebx
0x180022382  call    _o_malloc_0
0x180022387  mov     rdi, rax
0x18002238a  test    rax, rax
0x18002238d  jnz     short loc_180022399
0x18002238f  mov     ebx, 8007000Eh
0x180022394  jmp     loc_18002243E
0x180022399  mov     r8, r14; Size
0x18002239c  xor     edx, edx; Val
0x18002239e  mov     rcx, rdi; void *
0x1800223a1  call    memset_0
0x1800223a6  mov     rcx, [rbp+57h+Overlapped.hEvent]; hEvent
0x1800223aa  mov     eax, 3
0x1800223af  mov     [rdi+4], eax
0x1800223b2  mov     [rdi], eax
0x1800223b4  call    cs:__imp_ResetEvent
0x1800223ba  lea     rax, [rbp+57h+Overlapped]
0x1800223be  mov     r9d, 18h; nInBufferSize
0x1800223c4  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x1800223c9  mov     r8, rdi; lpInBuffer
0x1800223cc  lea     rax, [rbp+57h+BytesReturned]
0x1800223d0  mov     edx, 411058h; dwIoControlCode
0x1800223d5  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x1800223da  mov     rcx, rsi; hDevice
0x1800223dd  mov     [rsp+0B0h+nOutBufferSize], ebx; nOutBufferSize
0x1800223e1  mov     [rsp+0B0h+lpOutBuffer], rdi; lpOutBuffer
0x1800223e6  call    cs:__imp_DeviceIoControl
0x1800223ec  test    eax, eax
0x1800223ee  jnz     short loc_180022439
0x1800223f0  call    cs:__imp_GetLastError
0x1800223f6  mov     ebx, eax
0x1800223f8  cmp     eax, 3E5h
0x1800223fd  jnz     short loc_180022422
0x1800223ff  mov     r9d, 1; bWait
0x180022405  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x180022409  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002240d  mov     rcx, rsi; hFile
0x180022410  call    cs:__imp_GetOverlappedResult
0x180022416  test    eax, eax
0x180022418  jnz     short loc_180022439
0x18002241a  call    cs:__imp_GetLastError
0x180022420  mov     ebx, eax
0x180022422  test    eax, eax
0x180022424  jle     short loc_18002242F
0x180022426  movzx   ebx, ax
0x180022429  or      ebx, 80070000h
0x18002242f  mov     rcx, rdi; Block
0x180022432  call    free
0x180022437  jmp     short loc_18002243E
0x180022439  xor     ebx, ebx
0x18002243b  mov     [r15], rdi
0x18002243e  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x180022442  test    rcx, rcx
0x180022445  jz      short loc_18002244D
0x180022447  call    cs:__imp_CloseHandle
0x18002244d  mov     eax, ebx
0x18002244f  mov     rcx, [rbp+57h+var_30]
0x180022453  xor     rcx, rsp; StackCookie
0x180022456  call    __security_check_cookie
0x18002245b  mov     rbx, [rsp+0B0h+arg_8]
0x180022463  add     rsp, 90h
0x18002246a  pop     r15
0x18002246c  pop     r14
0x18002246e  pop     rdi
0x18002246f  pop     rsi
0x180022470  pop     rbp
0x180022471  retn
```
