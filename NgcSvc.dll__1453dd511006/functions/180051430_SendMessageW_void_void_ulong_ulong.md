# SendMessageW(void *,void *,ulong,ulong *)

- ea: `0x180051430`
- end: `0x180051637`
- name: `?SendMessageW@@YAJPEAX0KPEAK@Z`
- size: `519`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesTransferred)`
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
- `0x180048304`
- `0x180051430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051493`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180051493`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180051538`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180051538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800514fd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800514f3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800514f3`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18005158e`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18005158e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180051550`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800515cc`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180051550`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800515cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SendMessageW(
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
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
    v8 = 776;
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
    v8 = 777;
    goto LABEL_3;
  }
  if ( !hFile )
  {
    v8 = 778;
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  if ( !EventW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x30E,
             (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
             v11);
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = EventW;
  if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, lpNumberOfBytesTransferred, &Overlapped)
    || GetLastError() == 997 )
  {
    v16 = WaitForSingleObject(v12, 0x2710u);
    if ( v16 )
    {
      if ( v16 != 258 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x330,
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
                      (void *)0x329,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      v20);
        wil::details::CloseHandle((wil::details *)v12, v21);
        return LastError;
      }
      if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 1) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x32C,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      v22);
        wil::details::CloseHandle((wil::details *)v12, v23);
        return LastError;
      }
    }
    else if ( !GetOverlappedResult(hFile, &Overlapped, lpNumberOfBytesTransferred, 0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x324,
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
                (void *)0x31D,
                (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                v13);
  wil::details::CloseHandle((wil::details *)v12, v15);
  return LastError;
}

```

## disassembly

```asm
0x180051430  push    rbx
0x180051432  push    rbp
0x180051433  push    rsi
0x180051434  push    rdi
0x180051435  push    r14
0x180051437  sub     rsp, 50h
0x18005143b  mov     rsi, r9
0x18005143e  mov     r14d, r8d
0x180051441  mov     rbp, rdx
0x180051444  mov     rdi, rcx
0x180051447  test    rdx, rdx
0x18005144a  jnz     short loc_180051471
0x18005144c  mov     edx, 308h; void *
0x180051451  mov     ebx, 80070057h
0x180051456  mov     rcx, [rsp+78h]; this
0x18005145b  mov     r9d, ebx; char *
0x18005145e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180051465  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005146a  mov     eax, ebx
0x18005146c  jmp     loc_18005162C
0x180051471  test    rsi, rsi
0x180051474  jnz     short loc_18005147D
0x180051476  mov     edx, 309h
0x18005147b  jmp     short loc_180051451
0x18005147d  test    rdi, rdi
0x180051480  jnz     short loc_180051489
0x180051482  mov     edx, 30Ah
0x180051487  jmp     short loc_180051451
0x180051489  xor     r9d, r9d; lpName
0x18005148c  xor     r8d, r8d; bInitialState
0x18005148f  xor     edx, edx; bManualReset
0x180051491  xor     ecx, ecx; lpEventAttributes
0x180051493  call    cs:__imp_CreateEventW
0x180051499  mov     rbx, rax
0x18005149c  test    rax, rax
0x18005149f  jnz     short loc_1800514BD
0x1800514a1  mov     rcx, [rsp+78h]; this
0x1800514a6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1800514ad  mov     edx, 30Eh; void *
0x1800514b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800514b7  nop
0x1800514b8  jmp     loc_18005162C
0x1800514bd  mov     [rsp+78h+Overlapped.Internal], 0
0x1800514c6  mov     [rsp+78h+Overlapped.InternalHigh], 0
0x1800514cf  mov     [rsp+78h+Overlapped.hEvent], rbx
0x1800514d4  mov     qword ptr [rsp+78h+Overlapped.10h], 0
0x1800514dd  lea     rax, [rsp+78h+Overlapped]
0x1800514e2  mov     qword ptr [rsp+78h+lpOverlapped], rax; unsigned int
0x1800514e7  mov     r9, rsi; lpNumberOfBytesWritten
0x1800514ea  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800514ed  mov     rdx, rbp; lpBuffer
0x1800514f0  mov     rcx, rdi; hFile
0x1800514f3  call    cs:__imp_WriteFile
0x1800514f9  test    eax, eax
0x1800514fb  jnz     short loc_180051530
0x1800514fd  call    cs:__imp_GetLastError
0x180051503  cmp     eax, 3E5h
0x180051508  jz      short loc_180051530
0x18005150a  mov     rcx, [rsp+78h]; this
0x18005150f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180051516  mov     edx, 31Dh; void *
0x18005151b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051520  mov     edi, eax
0x180051522  mov     rcx, rbx; this
0x180051525  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005152a  nop
0x18005152b  jmp     loc_18005162A
0x180051530  mov     edx, 2710h; dwMilliseconds
0x180051535  mov     rcx, rbx; hHandle
0x180051538  call    cs:__imp_WaitForSingleObject
0x18005153e  test    eax, eax
0x180051540  jnz     short loc_180051584
0x180051542  xor     r9d, r9d; bWait
0x180051545  mov     r8, rsi; lpNumberOfBytesTransferred
0x180051548  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x18005154d  mov     rcx, rdi; hFile
0x180051550  call    cs:__imp_GetOverlappedResult
0x180051556  test    eax, eax
0x180051558  jnz     loc_1800515F9
0x18005155e  mov     rcx, [rsp+78h]; this
0x180051563  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18005156a  mov     edx, 324h; void *
0x18005156f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051574  mov     edi, eax
0x180051576  mov     rcx, rbx; this
0x180051579  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005157e  nop
0x18005157f  jmp     loc_18005162A
0x180051584  cmp     eax, 102h
0x180051589  jnz     short loc_180051606
0x18005158b  mov     rcx, rdi; hFile
0x18005158e  call    cs:__imp_CancelIo
0x180051594  test    eax, eax
0x180051596  jnz     short loc_1800515BB
0x180051598  mov     rcx, [rsp+78h]; this
0x18005159d  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1800515a4  mov     edx, 329h; void *
0x1800515a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800515ae  mov     edi, eax
0x1800515b0  mov     rcx, rbx; this
0x1800515b3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800515b8  nop
0x1800515b9  jmp     short loc_18005162A
0x1800515bb  mov     r9d, 1; bWait
0x1800515c1  mov     r8, rsi; lpNumberOfBytesTransferred
0x1800515c4  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x1800515c9  mov     rcx, rdi; hFile
0x1800515cc  call    cs:__imp_GetOverlappedResult
0x1800515d2  test    eax, eax
0x1800515d4  jnz     short loc_1800515F9
0x1800515d6  mov     rcx, [rsp+78h]; this
0x1800515db  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1800515e2  mov     edx, 32Ch; void *
0x1800515e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800515ec  mov     edi, eax
0x1800515ee  mov     rcx, rbx; this
0x1800515f1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800515f6  nop
0x1800515f7  jmp     short loc_18005162A
0x1800515f9  mov     rcx, rbx; this
0x1800515fc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180051601  nop
0x180051602  xor     eax, eax
0x180051604  jmp     short loc_18005162C
0x180051606  mov     rcx, [rsp+78h]; this
0x18005160b  mov     r9d, eax; char *
0x18005160e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180051615  mov     edx, 330h; void *
0x18005161a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005161f  mov     edi, eax
0x180051621  mov     rcx, rbx; this
0x180051624  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180051629  nop
0x18005162a  mov     eax, edi
0x18005162c  add     rsp, 50h
0x180051630  pop     r14
0x180051632  pop     rdi
0x180051633  pop     rsi
0x180051634  pop     rbp
0x180051635  pop     rbx
0x180051636  retn
```
