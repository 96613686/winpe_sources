# AsyncPipe::StartRead(void)

- ea: `0x14000da74`
- end: `0x14000dbb3`
- name: `?StartRead@AsyncPipe@@AEAAXXZ`
- size: `319`
- prototype: `void __fastcall(char *pv)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d5b4`
- `0x14000d6c0`
- `0x14000d744`

## callees

- `0x14000da74`
- `0x14000e1b4`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000daec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14000daec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000db23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000db23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000da9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000da9c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000db76`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000db76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000daae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000daae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000dbac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000db80`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000db46`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000db46`

## string_xrefs

- `0x14000dac7`: `CreateEvent`
- `0x14000db01`: `CreateThreadpoolWait`

## pseudocode

```c
void __fastcall AsyncPipe::StartRead(char *pv)
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
    __FatalError(v4, 0x16Au, "CreateEvent", LastError);
  }
  ThreadpoolWait = CreateThreadpoolWait(AsyncPipe::ReadCompletedStatic, pv, (PTP_CALLBACK_ENVIRON)(pv + 1472));
  *((_QWORD *)pv + 11) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v6 = GetLastError();
    __FatalError(v7, 0x16Du, "CreateThreadpoolWait", v6);
  }
  SetThreadpoolWait(*((PTP_WAIT *)pv + 11), *((HANDLE *)pv + 16), 0);
  if ( ReadFile(*((HANDLE *)pv + 3), pv + 260, 0x4B0u, (LPDWORD)pv + 64, (LPOVERLAPPED)(pv + 104)) )
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
    __FatalError(v10, 0x177u, "SetEvent", v9);
  }
LABEL_10:
  LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 168));
}

```

## disassembly

```asm
0x14000da74  mov     [rsp+arg_0], rbx
0x14000da79  mov     [rsp+arg_8], rsi
0x14000da7e  push    rdi
0x14000da7f  sub     rsp, 30h
0x14000da83  mov     rax, [rcx]
0x14000da86  mov     rbx, rcx
0x14000da89  mov     rax, [rax+10h]
0x14000da8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da92  lea     rdi, [rbx+0A8h]
0x14000da99  mov     rcx, rdi; lpCriticalSection
0x14000da9c  call    cs:__imp_EnterCriticalSection
0x14000daa2  xor     r9d, r9d; lpName
0x14000daa5  xor     r8d, r8d; bInitialState
0x14000daa8  xor     ecx, ecx; lpEventAttributes
0x14000daaa  lea     edx, [r9+1]; bManualReset
0x14000daae  call    cs:__imp_CreateEventW
0x14000dab4  lea     rsi, [rbx+68h]
0x14000dab8  mov     [rsi+18h], rax
0x14000dabc  test    rax, rax
0x14000dabf  jnz     short loc_14000DADB
0x14000dac1  call    cs:__imp_GetLastError
0x14000dac7  lea     r8, aCreateevent; "CreateEvent"
0x14000dace  mov     edx, 16Ah; unsigned int
0x14000dad3  mov     r9d, eax; unsigned int
0x14000dad6  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000dadb  lea     r8, [rbx+5C0h]; pcbe
0x14000dae2  mov     rdx, rbx; pv
0x14000dae5  lea     rcx, ?ReadCompletedStatic@AsyncPipe@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x14000daec  call    cs:__imp_CreateThreadpoolWait
0x14000daf2  mov     [rbx+58h], rax
0x14000daf6  test    rax, rax
0x14000daf9  jnz     short loc_14000DB15
0x14000dafb  call    cs:__imp_GetLastError
0x14000db01  lea     r8, aCreatethreadpo; "CreateThreadpoolWait"
0x14000db08  mov     edx, 16Dh; unsigned int
0x14000db0d  mov     r9d, eax; unsigned int
0x14000db10  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000db15  mov     rdx, [rbx+80h]; h
0x14000db1c  xor     r8d, r8d; pftTimeout
0x14000db1f  mov     rcx, [rbx+58h]; pwa
0x14000db23  call    cs:__imp_SetThreadpoolWait
0x14000db29  mov     rcx, [rbx+18h]; hFile
0x14000db2d  lea     r9, [rbx+100h]; lpNumberOfBytesRead
0x14000db34  lea     rdx, [rbx+104h]; lpBuffer
0x14000db3b  mov     [rsp+38h+lpOverlapped], rsi; lpOverlapped
0x14000db40  mov     r8d, 4B0h; nNumberOfBytesToRead
0x14000db46  call    cs:__imp_ReadFile
0x14000db4c  test    eax, eax
0x14000db4e  jz      short loc_14000DB5C
0x14000db50  mov     dword ptr [rbx+0F8h], 0
0x14000db5a  jmp     short loc_14000DB6F
0x14000db5c  call    cs:__imp_GetLastError
0x14000db62  mov     [rbx+0F8h], eax
0x14000db68  cmp     eax, 3E5h
0x14000db6d  jz      short loc_14000DB9A
0x14000db6f  mov     rcx, [rbx+80h]; hEvent
0x14000db76  call    cs:__imp_SetEvent
0x14000db7c  test    eax, eax
0x14000db7e  jnz     short loc_14000DB9A
0x14000db80  call    cs:__imp_GetLastError
0x14000db86  lea     r8, aSetevent; "SetEvent"
0x14000db8d  mov     edx, 177h; unsigned int
0x14000db92  mov     r9d, eax; unsigned int
0x14000db95  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000db9a  mov     rcx, rdi
0x14000db9d  mov     rbx, [rsp+38h+arg_0]
0x14000dba2  mov     rsi, [rsp+38h+arg_8]
0x14000dba7  add     rsp, 30h
0x14000dbab  pop     rdi
0x14000dbac  jmp     cs:__imp_LeaveCriticalSection
```
