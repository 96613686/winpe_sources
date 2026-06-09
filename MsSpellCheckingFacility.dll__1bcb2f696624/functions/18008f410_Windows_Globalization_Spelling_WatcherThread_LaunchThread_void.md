# Windows::Globalization::Spelling::WatcherThread::LaunchThread(void)

- ea: `0x18008f410`
- end: `0x18008f492`
- name: `?LaunchThread@WatcherThread@Spelling@Globalization@Windows@@AEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::WatcherThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180072284`

## callees

- `0x180058514`
- `0x180075b80`
- `0x18008f410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008f463`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18008f463`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f42a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008f42a`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::WatcherThread::LaunchThread(
        Windows::Globalization::Spelling::WatcherThread *this)
{
  int Error; // ebx
  HANDLE EventW; // rax
  HANDLE Thread; // rax

  Error = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( !EventW )
    Error = ResultFromKnownLastError();
  if ( Error < 0
    || (Thread = CreateThread(0, 0, Windows::Globalization::Spelling::WatcherThread::WatcherThreadProc, this, 0, 0),
        (*((_QWORD *)this + 4) = Thread) == 0)
    && (Error = ResultFromKnownLastError(), Error < 0) )
  {
    Windows::Globalization::Spelling::WatcherThread::ReleaseThreadTerminateSignal(this);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18008f410  mov     [rsp+arg_0], rbx
0x18008f415  push    rdi
0x18008f416  sub     rsp, 30h
0x18008f41a  mov     rdi, rcx
0x18008f41d  xor     ebx, ebx
0x18008f41f  xor     r9d, r9d; lpName
0x18008f422  xor     r8d, r8d; bInitialState
0x18008f425  xor     ecx, ecx; lpEventAttributes
0x18008f427  lea     edx, [rbx+1]; bManualReset
0x18008f42a  call    cs:__imp_CreateEventW
0x18008f430  mov     [rdi+28h], rax
0x18008f434  test    rax, rax
0x18008f437  jnz     short loc_18008F440
0x18008f439  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008f43e  mov     ebx, eax
0x18008f440  test    ebx, ebx
0x18008f442  js      short loc_18008F47D
0x18008f444  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18008f44d  lea     r8, ?WatcherThreadProc@WatcherThread@Spelling@Globalization@Windows@@CAKPEAX@Z; lpStartAddress
0x18008f454  mov     r9, rdi; lpParameter
0x18008f457  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18008f45f  xor     edx, edx; dwStackSize
0x18008f461  xor     ecx, ecx; lpThreadAttributes
0x18008f463  call    cs:__imp_CreateThread
0x18008f469  mov     [rdi+20h], rax
0x18008f46d  test    rax, rax
0x18008f470  jnz     short loc_18008F485
0x18008f472  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008f477  mov     ebx, eax
0x18008f479  test    eax, eax
0x18008f47b  jns     short loc_18008F485
0x18008f47d  mov     rcx, rdi; this
0x18008f480  call    ?ReleaseThreadTerminateSignal@WatcherThread@Spelling@Globalization@Windows@@AEAAXXZ; Windows::Globalization::Spelling::WatcherThread::ReleaseThreadTerminateSignal(void)
0x18008f485  mov     eax, ebx
0x18008f487  mov     rbx, [rsp+38h+arg_0]
0x18008f48c  add     rsp, 30h
0x18008f490  pop     rdi
0x18008f491  retn
```
