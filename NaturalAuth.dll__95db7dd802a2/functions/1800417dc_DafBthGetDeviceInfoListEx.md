# DafBthGetDeviceInfoListEx

- ea: `0x1800417dc`
- end: `0x1800419e2`
- name: `DafBthGetDeviceInfoListEx`
- size: `518`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180035760`

## callees

- `0x180004170`
- `0x1800050c8`
- `0x1800050d4`
- `0x180005140`
- `0x1800417dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180041924`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180041924`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004183b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004183b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004184a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004198a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004184a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004198a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800419b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800419b7`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800418c5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180041980`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800418c5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180041980`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004189b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180041956`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004189b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180041956`

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
0x1800417dc  mov     [rsp-8+arg_8], rbx
0x1800417e1  push    rbp
0x1800417e2  push    rsi
0x1800417e3  push    rdi
0x1800417e4  push    r14
0x1800417e6  push    r15
0x1800417e8  lea     rbp, [rsp-37h]
0x1800417ed  sub     rsp, 90h
0x1800417f4  mov     rax, cs:__security_cookie
0x1800417fb  xor     rax, rsp
0x1800417fe  mov     [rbp+57h+var_30], rax
0x180041802  mov     eax, 3
0x180041807  mov     [rbp+57h+BytesReturned], 0
0x18004180e  xorps   xmm0, xmm0
0x180041811  mov     [rbp+57h+var_44], eax
0x180041814  mov     r15, r8
0x180041817  mov     [rbp+57h+OutBuffer], eax
0x18004181a  mov     rsi, rcx
0x18004181d  xorps   xmm1, xmm1
0x180041820  lea     r8d, [rax-2]; dwFlags
0x180041824  xor     edx, edx; lpName
0x180041826  xor     ecx, ecx; lpEventAttributes
0x180041828  mov     r9d, 1F0003h; dwDesiredAccess
0x18004182e  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180041832  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180041836  movdqu  [rbp+57h+var_40], xmm1
0x18004183b  call    cs:__imp_CreateEventExW
0x180041841  mov     [rbp+57h+Overlapped.hEvent], rax
0x180041845  test    rax, rax
0x180041848  jnz     short loc_180041868
0x18004184a  call    cs:__imp_GetLastError
0x180041850  mov     ebx, eax
0x180041852  test    eax, eax
0x180041854  jle     loc_1800419AE
0x18004185a  movzx   ebx, ax
0x18004185d  or      ebx, 80070000h
0x180041863  jmp     loc_1800419AE
0x180041868  mov     ecx, 18h
0x18004186d  lea     rax, [rbp+57h+Overlapped]
0x180041871  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x180041876  lea     r8, [rbp+57h+OutBuffer]; lpInBuffer
0x18004187a  lea     rax, [rbp+57h+BytesReturned]
0x18004187e  mov     r9d, ecx; nInBufferSize
0x180041881  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x180041886  mov     edx, 411058h; dwIoControlCode
0x18004188b  mov     [rsp+0B0h+nOutBufferSize], ecx; nOutBufferSize
0x18004188f  lea     rax, [rbp+57h+OutBuffer]
0x180041893  mov     rcx, rsi; hDevice
0x180041896  mov     [rsp+0B0h+lpOutBuffer], rax; lpOutBuffer
0x18004189b  call    cs:__imp_DeviceIoControl
0x1800418a1  test    eax, eax
0x1800418a3  jnz     short loc_1800418D3
0x1800418a5  call    cs:__imp_GetLastError
0x1800418ab  mov     ebx, eax
0x1800418ad  cmp     eax, 3E5h
0x1800418b2  jnz     short loc_180041852
0x1800418b4  mov     r9d, 1; bWait
0x1800418ba  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x1800418be  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x1800418c2  mov     rcx, rsi; hFile
0x1800418c5  call    cs:__imp_GetOverlappedResult
0x1800418cb  test    eax, eax
0x1800418cd  jz      loc_18004184A
0x1800418d3  mov     eax, dword ptr [rbp+57h+var_40+8]
0x1800418d6  test    eax, eax
0x1800418d8  jnz     short loc_1800418E4
0x1800418da  mov     ebx, 80070490h
0x1800418df  jmp     loc_1800419AE
0x1800418e4  imul    ebx, eax, 340h
0x1800418ea  add     ebx, 18h
0x1800418ed  mov     ecx, ebx; Size
0x1800418ef  mov     r14d, ebx
0x1800418f2  call    _o_malloc_0
0x1800418f7  mov     rdi, rax
0x1800418fa  test    rax, rax
0x1800418fd  jnz     short loc_180041909
0x1800418ff  mov     ebx, 8007000Eh
0x180041904  jmp     loc_1800419AE
0x180041909  mov     r8, r14; Size
0x18004190c  xor     edx, edx; Val
0x18004190e  mov     rcx, rdi; void *
0x180041911  call    memset_0
0x180041916  mov     rcx, [rbp+57h+Overlapped.hEvent]; hEvent
0x18004191a  mov     eax, 3
0x18004191f  mov     [rdi+4], eax
0x180041922  mov     [rdi], eax
0x180041924  call    cs:__imp_ResetEvent
0x18004192a  lea     rax, [rbp+57h+Overlapped]
0x18004192e  mov     r9d, 18h; nInBufferSize
0x180041934  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x180041939  mov     r8, rdi; lpInBuffer
0x18004193c  lea     rax, [rbp+57h+BytesReturned]
0x180041940  mov     edx, 411058h; dwIoControlCode
0x180041945  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x18004194a  mov     rcx, rsi; hDevice
0x18004194d  mov     [rsp+0B0h+nOutBufferSize], ebx; nOutBufferSize
0x180041951  mov     [rsp+0B0h+lpOutBuffer], rdi; lpOutBuffer
0x180041956  call    cs:__imp_DeviceIoControl
0x18004195c  test    eax, eax
0x18004195e  jnz     short loc_1800419A9
0x180041960  call    cs:__imp_GetLastError
0x180041966  mov     ebx, eax
0x180041968  cmp     eax, 3E5h
0x18004196d  jnz     short loc_180041992
0x18004196f  mov     r9d, 1; bWait
0x180041975  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x180041979  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18004197d  mov     rcx, rsi; hFile
0x180041980  call    cs:__imp_GetOverlappedResult
0x180041986  test    eax, eax
0x180041988  jnz     short loc_1800419A9
0x18004198a  call    cs:__imp_GetLastError
0x180041990  mov     ebx, eax
0x180041992  test    eax, eax
0x180041994  jle     short loc_18004199F
0x180041996  movzx   ebx, ax
0x180041999  or      ebx, 80070000h
0x18004199f  mov     rcx, rdi; Block
0x1800419a2  call    free
0x1800419a7  jmp     short loc_1800419AE
0x1800419a9  xor     ebx, ebx
0x1800419ab  mov     [r15], rdi
0x1800419ae  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x1800419b2  test    rcx, rcx
0x1800419b5  jz      short loc_1800419BD
0x1800419b7  call    cs:__imp_CloseHandle
0x1800419bd  mov     eax, ebx
0x1800419bf  mov     rcx, [rbp+57h+var_30]
0x1800419c3  xor     rcx, rsp; StackCookie
0x1800419c6  call    __security_check_cookie
0x1800419cb  mov     rbx, [rsp+0B0h+arg_8]
0x1800419d3  add     rsp, 90h
0x1800419da  pop     r15
0x1800419dc  pop     r14
0x1800419de  pop     rdi
0x1800419df  pop     rsi
0x1800419e0  pop     rbp
0x1800419e1  retn
```
