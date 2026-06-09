# ReceiveMessage(void *,void *,ulong,ulong *)

- ea: `0x18000b310`
- end: `0x18000b523`
- name: `?ReceiveMessage@@YAJPEAX0KPEAK@Z`
- size: `531`
- prototype: `__int64 __fastcall(HANDLE hFile, void *lpBuffer, DWORD nNumberOfBytesToRead, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000aaf8`
- `0x18000adcc`
- `0x1800379cc`
- `0x18003826c`
- `0x180050f6c`

## callees

- `0x18000782c`
- `0x180007964`
- `0x18000948c`
- `0x18000b310`
- `0x180048304`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b37e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b37e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b423`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3e8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000b3de`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000b3de`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18000b47a`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18000b47a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b43c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b4b8`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b43c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b4b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ReceiveMessage(
        HANDLE hFile,
        void *lpBuffer,
        DWORD nNumberOfBytesToRead,
        LPDWORD lpNumberOfBytesTransferred)
{
  __int64 v8; // rdx
  HANDLE EventW; // rax
  const char *v11; // r9
  void *v12; // rbx
  const char *v13; // r9
  unsigned int LastError; // edi
  void *v15; // rdx
  DWORD v16; // eax
  void *v17; // rdx
  const char *v18; // r9
  void *v19; // rdx
  const char *v20; // r9
  void *v21; // rdx
  const char *v22; // r9
  void *v23; // rdx
  void *v24; // rdx
  int lpOverlapped; // [rsp+20h] [rbp-58h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-58h]
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !lpBuffer )
  {
    v8 = 828;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
      (const char *)0x80070057LL,
      lpOverlapped);
    return 2147942487LL;
  }
  if ( !lpNumberOfBytesTransferred )
  {
    v8 = 829;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v8 = 830;
    goto LABEL_3;
  }
  if ( !nNumberOfBytesToRead )
  {
    v8 = 831;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  if ( !EventW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x342,
             (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
             v11);
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = EventW;
  if ( ReadFile(hFile, lpBuffer, nNumberOfBytesToRead, lpNumberOfBytesTransferred, &Overlapped) || GetLastError() == 997 )
  {
    v16 = WaitForSingleObject(v12, 0x2710u);
    if ( v16 )
    {
      if ( v16 != 258 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x364,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      (const char *)v16,
                      lpOverlappeda);
        wil::details::CloseHandle((wil::details *)v12, v24);
        return LastError;
      }
      if ( !CancelIo(hFile) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x35D,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      v20);
        wil::details::CloseHandle((wil::details *)v12, v21);
        return LastError;
      }
      if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x360,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      v22);
        wil::details::CloseHandle((wil::details *)v12, v23);
        return LastError;
      }
    }
    else if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x358,
                    (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                    v18);
      wil::details::CloseHandle((wil::details *)v12, v19);
      return LastError;
    }
    wil::details::CloseHandle((wil::details *)v12, v17);
    return 0;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x351,
                (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                v13);
  wil::details::CloseHandle((wil::details *)v12, v15);
  return LastError;
}

```

## disassembly

```asm
0x18000b310  push    rbx
0x18000b312  push    rbp
0x18000b313  push    rsi
0x18000b314  push    rdi
0x18000b315  push    r14
0x18000b317  sub     rsp, 50h
0x18000b31b  mov     rsi, r9
0x18000b31e  mov     ebp, r8d
0x18000b321  mov     r14, rdx
0x18000b324  mov     rdi, rcx
0x18000b327  test    rdx, rdx
0x18000b32a  jnz     short loc_18000B351
0x18000b32c  mov     edx, 33Ch; void *
0x18000b331  mov     ebx, 80070057h
0x18000b336  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18000b33d  mov     r9d, ebx; char *
0x18000b340  mov     rcx, [rsp+78h]; this
0x18000b345  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b34a  mov     eax, ebx
0x18000b34c  jmp     loc_18000B518
0x18000b351  test    rsi, rsi
0x18000b354  jnz     short loc_18000B35D
0x18000b356  mov     edx, 33Dh
0x18000b35b  jmp     short loc_18000B331
0x18000b35d  test    rdi, rdi
0x18000b360  jnz     short loc_18000B369
0x18000b362  mov     edx, 33Eh
0x18000b367  jmp     short loc_18000B331
0x18000b369  test    ebp, ebp
0x18000b36b  jnz     short loc_18000B374
0x18000b36d  mov     edx, 33Fh
0x18000b372  jmp     short loc_18000B331
0x18000b374  xor     r9d, r9d; lpName
0x18000b377  xor     r8d, r8d; bInitialState
0x18000b37a  xor     edx, edx; bManualReset
0x18000b37c  xor     ecx, ecx; lpEventAttributes
0x18000b37e  call    cs:__imp_CreateEventW
0x18000b384  mov     rbx, rax
0x18000b387  test    rax, rax
0x18000b38a  jnz     short loc_18000B3A8
0x18000b38c  mov     rcx, [rsp+78h]; this
0x18000b391  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18000b398  mov     edx, 342h; void *
0x18000b39d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b3a2  nop
0x18000b3a3  jmp     loc_18000B518
0x18000b3a8  mov     [rsp+78h+Overlapped.Internal], 0
0x18000b3b1  mov     [rsp+78h+Overlapped.InternalHigh], 0
0x18000b3ba  mov     [rsp+78h+Overlapped.hEvent], rbx
0x18000b3bf  mov     qword ptr [rsp+78h+Overlapped.10h], 0
0x18000b3c8  lea     rax, [rsp+78h+Overlapped]
0x18000b3cd  mov     qword ptr [rsp+78h+lpOverlapped], rax; unsigned int
0x18000b3d2  mov     r9, rsi; lpNumberOfBytesRead
0x18000b3d5  mov     r8d, ebp; nNumberOfBytesToRead
0x18000b3d8  mov     rdx, r14; lpBuffer
0x18000b3db  mov     rcx, rdi; hFile
0x18000b3de  call    cs:__imp_ReadFile
0x18000b3e4  test    eax, eax
0x18000b3e6  jnz     short loc_18000B41B
0x18000b3e8  call    cs:__imp_GetLastError
0x18000b3ee  cmp     eax, 3E5h
0x18000b3f3  jz      short loc_18000B41B
0x18000b3f5  mov     rcx, [rsp+78h]; this
0x18000b3fa  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18000b401  mov     edx, 351h; void *
0x18000b406  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b40b  mov     edi, eax
0x18000b40d  mov     rcx, rbx; this
0x18000b410  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b415  nop
0x18000b416  jmp     loc_18000B516
0x18000b41b  mov     edx, 2710h; dwMilliseconds
0x18000b420  mov     rcx, rbx; hHandle
0x18000b423  call    cs:__imp_WaitForSingleObject
0x18000b429  test    eax, eax
0x18000b42b  jnz     short loc_18000B470
0x18000b42d  lea     r9d, [rax+1]; bWait
0x18000b431  mov     r8, rsi; lpNumberOfBytesTransferred
0x18000b434  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x18000b439  mov     rcx, rdi; hFile
0x18000b43c  call    cs:__imp_GetOverlappedResult
0x18000b442  test    eax, eax
0x18000b444  jnz     loc_18000B4E5
0x18000b44a  mov     rcx, [rsp+78h]; this
0x18000b44f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18000b456  mov     edx, 358h; void *
0x18000b45b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b460  mov     edi, eax
0x18000b462  mov     rcx, rbx; this
0x18000b465  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b46a  nop
0x18000b46b  jmp     loc_18000B516
0x18000b470  cmp     eax, 102h
0x18000b475  jnz     short loc_18000B4F2
0x18000b477  mov     rcx, rdi; hFile
0x18000b47a  call    cs:__imp_CancelIo
0x18000b480  test    eax, eax
0x18000b482  jnz     short loc_18000B4A7
0x18000b484  mov     rcx, [rsp+78h]; this
0x18000b489  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18000b490  mov     edx, 35Dh; void *
0x18000b495  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b49a  mov     edi, eax
0x18000b49c  mov     rcx, rbx; this
0x18000b49f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b4a4  nop
0x18000b4a5  jmp     short loc_18000B516
0x18000b4a7  mov     r9d, 1; bWait
0x18000b4ad  mov     r8, rsi; lpNumberOfBytesTransferred
0x18000b4b0  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x18000b4b5  mov     rcx, rdi; hFile
0x18000b4b8  call    cs:__imp_GetOverlappedResult
0x18000b4be  test    eax, eax
0x18000b4c0  jnz     short loc_18000B4E5
0x18000b4c2  mov     rcx, [rsp+78h]; this
0x18000b4c7  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18000b4ce  mov     edx, 360h; void *
0x18000b4d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b4d8  mov     edi, eax
0x18000b4da  mov     rcx, rbx; this
0x18000b4dd  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b4e2  nop
0x18000b4e3  jmp     short loc_18000B516
0x18000b4e5  mov     rcx, rbx; this
0x18000b4e8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b4ed  nop
0x18000b4ee  xor     eax, eax
0x18000b4f0  jmp     short loc_18000B518
0x18000b4f2  mov     rcx, [rsp+78h]; this
0x18000b4f7  mov     r9d, eax; char *
0x18000b4fa  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18000b501  mov     edx, 364h; void *
0x18000b506  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b50b  mov     edi, eax
0x18000b50d  mov     rcx, rbx; this
0x18000b510  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000b515  nop
0x18000b516  mov     eax, edi
0x18000b518  add     rsp, 50h
0x18000b51c  pop     r14
0x18000b51e  pop     rdi
0x18000b51f  pop     rsi
0x18000b520  pop     rbp
0x18000b521  pop     rbx
0x18000b522  retn
```
