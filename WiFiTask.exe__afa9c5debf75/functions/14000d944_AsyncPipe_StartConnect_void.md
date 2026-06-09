# AsyncPipe::StartConnect(void)

- ea: `0x14000d944`
- end: `0x14000da6d`
- name: `?StartConnect@AsyncPipe@@AEAAXXZ`
- size: `297`
- prototype: `void __fastcall(char *pv)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d5b4`
- `0x14000d6c0`

## callees

- `0x14000d944`
- `0x14000e1b4`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000d9bb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000d9bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000d9f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000d9f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d96c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d96c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000da30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000da30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000d97e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000d97e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000da66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000da3a`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14000da00`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x14000da00`

## string_xrefs

- `0x14000d996`: `CreateEvent`
- `0x14000d9d0`: `CreateThreadpoolWait`

## pseudocode

```c
void __fastcall AsyncPipe::StartConnect(char *pv)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  const char *v4; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  DWORD v6; // eax
  const char *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // eax
  const char *v10; // rcx

  (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 16LL))(pv);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 168));
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)pv + 16) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    __FatalError(v4, 0xE8u, "CreateEvent", LastError);
  }
  ThreadpoolWait = CreateThreadpoolWait(AsyncPipe::ReadCompletedStatic, pv, (PTP_CALLBACK_ENVIRON)(pv + 1472));
  *((_QWORD *)pv + 11) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v6 = GetLastError();
    __FatalError(v7, 0xEBu, "CreateThreadpoolWait", v6);
  }
  SetThreadpoolWait(*((PTP_WAIT *)pv + 11), *((HANDLE *)pv + 16), 0);
  if ( ConnectNamedPipe(*((HANDLE *)pv + 3), (LPOVERLAPPED)(pv + 104)) )
  {
    *((_DWORD *)pv + 62) = 0;
  }
  else
  {
    v8 = GetLastError();
    *((_DWORD *)pv + 62) = v8;
    if ( v8 == 997 )
      goto LABEL_10;
  }
  if ( !SetEvent(*((HANDLE *)pv + 16)) )
  {
    v9 = GetLastError();
    __FatalError(v10, 0xF5u, "SetEvent", v9);
  }
LABEL_10:
  LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 168));
}

```

## disassembly

```asm
0x14000d944  mov     [rsp+arg_0], rbx
0x14000d949  mov     [rsp+arg_8], rsi
0x14000d94e  push    rdi
0x14000d94f  sub     rsp, 20h
0x14000d953  mov     rax, [rcx]
0x14000d956  mov     rbx, rcx
0x14000d959  mov     rax, [rax+10h]
0x14000d95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d962  lea     rdi, [rbx+0A8h]
0x14000d969  mov     rcx, rdi; lpCriticalSection
0x14000d96c  call    cs:__imp_EnterCriticalSection
0x14000d972  xor     r9d, r9d; lpName
0x14000d975  xor     r8d, r8d; bInitialState
0x14000d978  xor     ecx, ecx; lpEventAttributes
0x14000d97a  lea     edx, [r9+1]; bManualReset
0x14000d97e  call    cs:__imp_CreateEventW
0x14000d984  mov     [rbx+80h], rax
0x14000d98b  test    rax, rax
0x14000d98e  jnz     short loc_14000D9AA
0x14000d990  call    cs:__imp_GetLastError
0x14000d996  lea     r8, aCreateevent; "CreateEvent"
0x14000d99d  mov     edx, 0E8h; unsigned int
0x14000d9a2  mov     r9d, eax; unsigned int
0x14000d9a5  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d9aa  lea     r8, [rbx+5C0h]; pcbe
0x14000d9b1  mov     rdx, rbx; pv
0x14000d9b4  lea     rcx, ?ReadCompletedStatic@AsyncPipe@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14000d9bb  call    cs:__imp_CreateThreadpoolWait
0x14000d9c1  mov     [rbx+58h], rax
0x14000d9c5  test    rax, rax
0x14000d9c8  jnz     short loc_14000D9E4
0x14000d9ca  call    cs:__imp_GetLastError
0x14000d9d0  lea     r8, aCreatethreadpo; "CreateThreadpoolWait"
0x14000d9d7  mov     edx, 0EBh; unsigned int
0x14000d9dc  mov     r9d, eax; unsigned int
0x14000d9df  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d9e4  mov     rdx, [rbx+80h]; h
0x14000d9eb  xor     r8d, r8d; pftTimeout
0x14000d9ee  mov     rcx, [rbx+58h]; pwa
0x14000d9f2  call    cs:__imp_SetThreadpoolWait
0x14000d9f8  mov     rcx, [rbx+18h]; hNamedPipe
0x14000d9fc  lea     rdx, [rbx+68h]; lpOverlapped
0x14000da00  call    cs:__imp_ConnectNamedPipe
0x14000da06  test    eax, eax
0x14000da08  jz      short loc_14000DA16
0x14000da0a  mov     dword ptr [rbx+0F8h], 0
0x14000da14  jmp     short loc_14000DA29
0x14000da16  call    cs:__imp_GetLastError
0x14000da1c  mov     [rbx+0F8h], eax
0x14000da22  cmp     eax, 3E5h
0x14000da27  jz      short loc_14000DA54
0x14000da29  mov     rcx, [rbx+80h]; hEvent
0x14000da30  call    cs:__imp_SetEvent
0x14000da36  test    eax, eax
0x14000da38  jnz     short loc_14000DA54
0x14000da3a  call    cs:__imp_GetLastError
0x14000da40  lea     r8, aSetevent; "SetEvent"
0x14000da47  mov     edx, 0F5h; unsigned int
0x14000da4c  mov     r9d, eax; unsigned int
0x14000da4f  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000da54  mov     rcx, rdi
0x14000da57  mov     rbx, [rsp+28h+arg_0]
0x14000da5c  mov     rsi, [rsp+28h+arg_8]
0x14000da61  add     rsp, 20h
0x14000da65  pop     rdi
0x14000da66  jmp     cs:__imp_LeaveCriticalSection
```
