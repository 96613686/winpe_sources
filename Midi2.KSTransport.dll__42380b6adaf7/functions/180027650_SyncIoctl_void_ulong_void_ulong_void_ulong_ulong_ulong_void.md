# SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *,ulong,void *)

- ea: `0x180027650`
- end: `0x18002782d`
- name: `?SyncIoctl@@YAJPEAXK0K0KPEAKK0@Z`
- size: `477`
- prototype: `__int64 __fastcall(HANDLE hFile, DWORD dwIoControlCode, void *lpInBuffer, DWORD nInBufferSize, void *, DWORD, LPDWORD lpNumberOfBytesTransferred, unsigned int, void *)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002741c`
- `0x1800275a0`
- `0x180027ba4`
- `0x180027cb8`
- `0x180027ddc`
- `0x180027f00`
- `0x18002982c`
- `0x180029bf4`
- `0x18002a0d0`

## callees

- `0x18000a7f4`
- `0x18000a814`
- `0x180027650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002769e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002769e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002772b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002776f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002772b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002776f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027816`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027816`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002771d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002771d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180027765`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180027765`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18002779d`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18002779d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002774a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002774a`

## string_xrefs

- `0x1800276b4`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`
- `0x1800277e0`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

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
0x180027650  mov     rax, rsp
0x180027653  push    rbx
0x180027654  push    rbp
0x180027655  push    rsi
0x180027656  push    rdi
0x180027657  push    r12
0x180027659  push    r14
0x18002765b  push    r15
0x18002765d  sub     rsp, 70h
0x180027661  xorps   xmm0, xmm0
0x180027664  mov     dword ptr [rax+40h], 0
0x18002766b  lea     rsi, [rax+40h]
0x18002766f  mov     ebx, r9d
0x180027672  movups  xmmword ptr [rax-58h], xmm0
0x180027676  mov     r15, r8
0x180027679  mov     r12d, edx
0x18002767c  movups  xmmword ptr [rax-48h], xmm0
0x180027680  mov     rax, [rsp+0A8h+lpNumberOfBytesTransferred]
0x180027688  mov     rbp, rcx
0x18002768b  test    rax, rax
0x18002768e  cmovnz  rsi, rax
0x180027692  xor     r9d, r9d; lpName
0x180027695  xor     r8d, r8d; bInitialState
0x180027698  xor     ecx, ecx; lpEventAttributes
0x18002769a  lea     edx, [r9+1]; bManualReset
0x18002769e  call    cs:__imp_CreateEventW
0x1800276a4  mov     rdi, rax
0x1800276a7  test    rax, rax
0x1800276aa  jnz     short loc_1800276CA
0x1800276ac  mov     rcx, [rsp+0A8h]; this
0x1800276b4  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x1800276bb  lea     edx, [rax+37h]; void *
0x1800276be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800276c3  mov     [rsi], edi
0x1800276c5  jmp     loc_18002781E
0x1800276ca  mov     rax, [rsp+0A8h+arg_40]
0x1800276d2  mov     r9d, ebx; nInBufferSize
0x1800276d5  mov     [rsp+0A8h+var_60], rax
0x1800276da  mov     r8, r15; lpInBuffer
0x1800276dd  neg     rax
0x1800276e0  mov     [rsp+0A8h+Overlapped.hEvent], rdi
0x1800276e5  lea     rax, [rsp+0A8h+Overlapped]
0x1800276ea  mov     [rsp+0A8h+Handles], rdi
0x1800276ef  mov     [rsp+0A8h+lpOverlapped], rax; lpOverlapped
0x1800276f4  sbb     r14d, r14d
0x1800276f7  mov     eax, [rsp+0A8h+arg_28]
0x1800276fe  mov     edx, r12d; dwIoControlCode
0x180027701  mov     [rsp+0A8h+lpBytesReturned], rsi; lpBytesReturned
0x180027706  mov     rcx, rbp; hDevice
0x180027709  mov     [rsp+0A8h+nOutBufferSize], eax; nOutBufferSize
0x18002770d  neg     r14d
0x180027710  mov     rax, [rsp+0A8h+arg_20]
0x180027718  mov     [rsp+0A8h+lpOutBuffer], rax; int
0x18002771d  call    cs:__imp_DeviceIoControl
0x180027723  test    eax, eax
0x180027725  jnz     loc_18002780D
0x18002772b  call    cs:__imp_GetLastError
0x180027731  mov     ebx, eax
0x180027733  cmp     eax, 3E5h
0x180027738  jnz     short loc_180027777
0x18002773a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002773e  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x180027743  xor     r8d, r8d; bWaitAll
0x180027746  lea     ecx, [r14+1]; nCount
0x18002774a  call    cs:__imp_WaitForMultipleObjects
0x180027750  mov     rcx, rbp; hFile
0x180027753  test    eax, eax
0x180027755  jnz     short loc_180027798
0x180027757  lea     r9d, [rax+1]; bWait
0x18002775b  mov     r8, rsi; lpNumberOfBytesTransferred
0x18002775e  lea     rdx, [rsp+0A8h+Overlapped]; lpOverlapped
0x180027763  xor     ebx, ebx
0x180027765  call    cs:__imp_GetOverlappedResult
0x18002776b  test    eax, eax
0x18002776d  jnz     short loc_1800277B2
0x18002776f  call    cs:__imp_GetLastError
0x180027775  mov     ebx, eax
0x180027777  cmp     ebx, 0EAh
0x18002777d  jnz     short loc_1800277A5
0x18002777f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180027783  jz      short loc_18002778E
0x180027785  mov     rcx, rdi; hObject
0x180027788  call    cs:__imp_CloseHandle
0x18002778e  mov     eax, 800700EAh
0x180027793  jmp     loc_18002781E
0x180027798  mov     ebx, 3E3h
0x18002779d  call    cs:__imp_CancelIo
0x1800277a3  jmp     short loc_1800277A9
0x1800277a5  test    ebx, ebx
0x1800277a7  jle     short loc_1800277B4
0x1800277a9  movzx   ebx, bx
0x1800277ac  or      ebx, 80070000h
0x1800277b2  test    ebx, ebx
0x1800277b4  jns     short loc_18002780D
0x1800277b6  mov     ebp, 80070492h
0x1800277bb  cmp     ebx, ebp
0x1800277bd  jnz     short loc_1800277D8
0x1800277bf  mov     dword ptr [rsi], 0
0x1800277c5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800277c9  jz      short loc_1800277D4
0x1800277cb  mov     rcx, rdi; hObject
0x1800277ce  call    cs:__imp_CloseHandle
0x1800277d4  mov     eax, ebp
0x1800277d6  jmp     short loc_18002781E
0x1800277d8  mov     rcx, [rsp+0A8h]; this
0x1800277e0  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x1800277e7  mov     r9d, ebx; char *
0x1800277ea  mov     edx, 69h ; 'i'; void *
0x1800277ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277f4  mov     dword ptr [rsi], 0
0x1800277fa  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800277fe  jz      short loc_180027809
0x180027800  mov     rcx, rdi; hObject
0x180027803  call    cs:__imp_CloseHandle
0x180027809  mov     eax, ebx
0x18002780b  jmp     short loc_18002781E
0x18002780d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180027811  jz      short loc_18002781C
0x180027813  mov     rcx, rdi; hObject
0x180027816  call    cs:__imp_CloseHandle
0x18002781c  xor     eax, eax
0x18002781e  add     rsp, 70h
0x180027822  pop     r15
0x180027824  pop     r14
0x180027826  pop     r12
0x180027828  pop     rdi
0x180027829  pop     rsi
0x18002782a  pop     rbp
0x18002782b  pop     rbx
0x18002782c  retn
```
