# SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *,ulong,void *)

- ea: `0x1800481b4`
- end: `0x180048391`
- name: `?SyncIoctl@@YAJPEAXK0K0KPEAKK0@Z`
- size: `477`
- prototype: `__int64 __fastcall(HANDLE hFile, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void *, DWORD, LPDWORD lpNumberOfBytesTransferred, unsigned int, void *)`
- caller_count: `11`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025070`
- `0x18003b10c`
- `0x180047e9c`
- `0x180048014`
- `0x180048708`
- `0x18004881c`
- `0x180048940`
- `0x180048a64`
- `0x18004a36c`
- `0x18004a59c`
- `0x18004aa70`

## callees

- `0x18000b374`
- `0x18000b394`
- `0x1800481b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048202`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004828f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004828f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800482d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800482ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004837a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800482ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048367`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004837a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180048281`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180048281`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800482c9`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800482c9`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180048301`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180048301`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800482ae`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800482ae`

## string_xrefs

- `0x180048218`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`
- `0x180048344`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

## pseudocode

```c
__int64 __fastcall SyncIoctl(
        HANDLE hFile,
        DWORD dwIoControlCode,
        void *lpInBuffer,
        DWORD nInBufferSize,
        void *a5,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred,
        unsigned int a8,
        void *a9)
{
  unsigned int *lpBytesReturned; // rsi
  HANDLE EventW; // rax
  const char *v15; // r9
  void *v16; // rdi
  __int64 result; // rax
  BOOL v18; // r14d
  signed int LastError; // ebx
  bool v20; // sf
  int lpOutBuffer; // [rsp+20h] [rbp-88h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-68h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  a8 = 0;
  lpBytesReturned = &a8;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  EventW = CreateEventW(0, 1, 0, 0);
  v16 = EventW;
  if ( !EventW )
  {
    result = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x37,
               (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
               v15);
    *lpBytesReturned = 0;
    return result;
  }
  Handles[1] = a9;
  Overlapped.hEvent = EventW;
  Handles[0] = EventW;
  v18 = a9 != 0;
  if ( DeviceIoControl(
         hFile,
         dwIoControlCode,
         lpInBuffer,
         nInBufferSize,
         a5,
         nOutBufferSize,
         lpBytesReturned,
         &Overlapped) )
  {
    goto LABEL_26;
  }
  LastError = GetLastError();
  if ( LastError == 997 )
  {
    if ( WaitForMultipleObjects(v18 + 1, Handles, 0, 0xFFFFFFFF) )
    {
      LOWORD(LastError) = 995;
      CancelIo(hFile);
LABEL_16:
      LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    LastError = 0;
    if ( GetOverlappedResult(hFile, &Overlapped, lpBytesReturned, 1) )
    {
LABEL_17:
      v20 = LastError < 0;
      goto LABEL_18;
    }
    LastError = GetLastError();
  }
  if ( LastError == 234 )
  {
    if ( v16 != (void *)-1LL )
      CloseHandle(v16);
    return 2147942634LL;
  }
  v20 = LastError < 0;
  if ( LastError > 0 )
    goto LABEL_16;
LABEL_18:
  if ( v20 )
  {
    if ( LastError == -2147023726 )
    {
      *lpBytesReturned = 0;
      if ( v16 != (void *)-1LL )
        CloseHandle(v16);
      return 2147943570LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
        (const char *)(unsigned int)LastError,
        lpOutBuffer);
      *lpBytesReturned = 0;
      if ( v16 != (void *)-1LL )
        CloseHandle(v16);
      return (unsigned int)LastError;
    }
  }
LABEL_26:
  if ( v16 != (void *)-1LL )
    CloseHandle(v16);
  return 0;
}

```

## disassembly

```asm
0x1800481b4  mov     rax, rsp
0x1800481b7  push    rbx
0x1800481b8  push    rbp
0x1800481b9  push    rsi
0x1800481ba  push    rdi
0x1800481bb  push    r12
0x1800481bd  push    r14
0x1800481bf  push    r15
0x1800481c1  sub     rsp, 70h
0x1800481c5  xorps   xmm0, xmm0
0x1800481c8  mov     dword ptr [rax+40h], 0
0x1800481cf  lea     rsi, [rax+40h]
0x1800481d3  mov     ebx, r9d
0x1800481d6  movups  xmmword ptr [rax-58h], xmm0
0x1800481da  mov     r15, r8
0x1800481dd  mov     r12d, edx
0x1800481e0  movups  xmmword ptr [rax-48h], xmm0
0x1800481e4  mov     rax, [rsp+0A8h+lpNumberOfBytesTransferred]
0x1800481ec  mov     rbp, rcx
0x1800481ef  test    rax, rax
0x1800481f2  cmovnz  rsi, rax
0x1800481f6  xor     r9d, r9d; lpName
0x1800481f9  xor     r8d, r8d; bInitialState
0x1800481fc  xor     ecx, ecx; lpEventAttributes
0x1800481fe  lea     edx, [r9+1]; bManualReset
0x180048202  call    cs:__imp_CreateEventW
0x180048208  mov     rdi, rax
0x18004820b  test    rax, rax
0x18004820e  jnz     short loc_18004822E
0x180048210  mov     rcx, [rsp+0A8h]; this
0x180048218  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x18004821f  lea     edx, [rax+37h]; void *
0x180048222  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180048227  mov     [rsi], edi
0x180048229  jmp     loc_180048382
0x18004822e  mov     rax, [rsp+0A8h+arg_40]
0x180048236  mov     r9d, ebx; nInBufferSize
0x180048239  mov     [rsp+0A8h+var_60], rax
0x18004823e  mov     r8, r15; lpInBuffer
0x180048241  neg     rax
0x180048244  mov     [rsp+0A8h+Overlapped.hEvent], rdi
0x180048249  lea     rax, [rsp+0A8h+Overlapped]
0x18004824e  mov     [rsp+0A8h+Handles], rdi
0x180048253  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x180048258  sbb     r14d, r14d
0x18004825b  mov     eax, [rsp+0A8h+arg_28]
0x180048262  mov     edx, r12d; dwIoControlCode
0x180048265  mov     [rsp+0A8h+lpBytesReturned], rsi; lpBytesReturned
0x18004826a  mov     rcx, rbp; hDevice
0x18004826d  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x180048271  neg     r14d
0x180048274  mov     rax, [rsp+0A8h+arg_20]
0x18004827c  mov     [rsp+0A8h+lpOutBuffer], rax; int
0x180048281  call    cs:__imp_DeviceIoControl
0x180048287  test    eax, eax
0x180048289  jnz     loc_180048371
0x18004828f  call    cs:__imp_GetLastError
0x180048295  mov     ebx, eax
0x180048297  cmp     eax, 3E5h
0x18004829c  jnz     short loc_1800482DB
0x18004829e  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800482a2  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x1800482a7  xor     r8d, r8d; bWaitAll
0x1800482aa  lea     ecx, [r14+1]; nCount
0x1800482ae  call    cs:__imp_WaitForMultipleObjects
0x1800482b4  mov     rcx, rbp; hFile
0x1800482b7  test    eax, eax
0x1800482b9  jnz     short loc_1800482FC
0x1800482bb  lea     r9d, [rax+1]; bWait
0x1800482bf  mov     r8, rsi; lpNumberOfBytesTransferred
0x1800482c2  lea     rdx, [rsp+0A8h+Overlapped]; lpOverlapped
0x1800482c7  xor     ebx, ebx
0x1800482c9  call    cs:__imp_GetOverlappedResult
0x1800482cf  test    eax, eax
0x1800482d1  jnz     short loc_180048316
0x1800482d3  call    cs:__imp_GetLastError
0x1800482d9  mov     ebx, eax
0x1800482db  cmp     ebx, 0EAh
0x1800482e1  jnz     short loc_180048309
0x1800482e3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800482e7  jz      short loc_1800482F2
0x1800482e9  mov     rcx, rdi; hObject
0x1800482ec  call    cs:__imp_CloseHandle
0x1800482f2  mov     eax, 800700EAh
0x1800482f7  jmp     loc_180048382
0x1800482fc  mov     ebx, 3E3h
0x180048301  call    cs:__imp_CancelIo
0x180048307  jmp     short loc_18004830D
0x180048309  test    ebx, ebx
0x18004830b  jle     short loc_180048318
0x18004830d  movzx   ebx, bx
0x180048310  or      ebx, 80070000h
0x180048316  test    ebx, ebx
0x180048318  jns     short loc_180048371
0x18004831a  mov     ebp, 80070492h
0x18004831f  cmp     ebx, ebp
0x180048321  jnz     short loc_18004833C
0x180048323  mov     dword ptr [rsi], 0
0x180048329  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18004832d  jz      short loc_180048338
0x18004832f  mov     rcx, rdi; hObject
0x180048332  call    cs:__imp_CloseHandle
0x180048338  mov     eax, ebp
0x18004833a  jmp     short loc_180048382
0x18004833c  mov     rcx, [rsp+0A8h]; this
0x180048344  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x18004834b  mov     r9d, ebx; char *
0x18004834e  mov     edx, 69h ; 'i'; void *
0x180048353  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048358  mov     dword ptr [rsi], 0
0x18004835e  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180048362  jz      short loc_18004836D
0x180048364  mov     rcx, rdi; hObject
0x180048367  call    cs:__imp_CloseHandle
0x18004836d  mov     eax, ebx
0x18004836f  jmp     short loc_180048382
0x180048371  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180048375  jz      short loc_180048380
0x180048377  mov     rcx, rdi; hObject
0x18004837a  call    cs:__imp_CloseHandle
0x180048380  xor     eax, eax
0x180048382  add     rsp, 70h
0x180048386  pop     r15
0x180048388  pop     r14
0x18004838a  pop     r12
0x18004838c  pop     rdi
0x18004838d  pop     rsi
0x18004838e  pop     rbp
0x18004838f  pop     rbx
0x180048390  retn
```
