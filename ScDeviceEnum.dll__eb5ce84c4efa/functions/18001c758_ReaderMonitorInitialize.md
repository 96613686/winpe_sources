# ReaderMonitorInitialize

- ea: `0x18001c758`
- end: `0x18001c8c5`
- name: `ReaderMonitorInitialize`
- size: `365`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ecd4`

## callees

- `0x18001c758`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c7ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c7d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c7ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c805`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c7ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c7d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c7ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c840`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c81d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c81d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c836`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c836`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001c896`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001c896`
- `ntdll!RtlInitializeCriticalSection` at `0x18001c773`
- `ntdll!RtlInitializeCriticalSection` at `0x18001c773`

## pseudocode

```c
__int64 __fastcall ReaderMonitorInitialize(__int64 a1)
{
  HANDLE EventW; // rax
  DWORD LastError; // esi
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  HANDLE CurrentThread; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax

  hHeap = *(HANDLE *)(a1 + 32);
  if ( RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 48)) )
    return 8;
  *(_DWORD *)(a1 + 216) = 1;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 88) = EventW;
  if ( !EventW )
    return GetLastError();
  v5 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 96) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 104) = v6;
  if ( !v6 )
    return GetLastError();
  v7 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 240) = v7;
  if ( !v7 )
    return GetLastError();
  LastError = 0;
  if ( *(_DWORD *)a1 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)(a1 + 248)) )
      LastError = GetLastError();
  }
  *(_DWORD *)(a1 + 136) = 3;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 192) = 0;
  *(_DWORD *)(a1 + 196) = 1;
  *(_DWORD *)(a1 + 200) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *(_QWORD *)(a1 + 208) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    *(_QWORD *)(a1 + 152) = ThreadpoolCleanupGroup;
    *(_QWORD *)(a1 + 160) = 0;
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18001c758  push    rbx
0x18001c75a  push    rbp
0x18001c75b  push    rsi
0x18001c75c  push    rdi
0x18001c75d  sub     rsp, 28h
0x18001c761  mov     rax, [rcx+20h]
0x18001c765  mov     rdi, rcx
0x18001c768  add     rcx, 30h ; '0'; CriticalSection
0x18001c76c  mov     cs:hHeap, rax
0x18001c773  call    cs:__imp_RtlInitializeCriticalSection
0x18001c779  xor     ebp, ebp
0x18001c77b  test    eax, eax
0x18001c77d  jz      short loc_18001C787
0x18001c77f  lea     eax, [rbp+8]
0x18001c782  jmp     loc_18001C8BC
0x18001c787  xor     r9d, r9d; lpName
0x18001c78a  mov     dword ptr [rdi+0D8h], 1
0x18001c794  xor     r8d, r8d; bInitialState
0x18001c797  mov     [rdi+108h], rbp
0x18001c79e  xor     edx, edx; bManualReset
0x18001c7a0  mov     [rdi+78h], rbp
0x18001c7a4  xor     ecx, ecx; lpEventAttributes
0x18001c7a6  mov     [rdi+80h], rbp
0x18001c7ad  call    cs:__imp_CreateEventW
0x18001c7b3  mov     [rdi+58h], rax
0x18001c7b7  test    rax, rax
0x18001c7ba  jnz     short loc_18001C7C9
0x18001c7bc  call    cs:__imp_GetLastError
0x18001c7c2  mov     esi, eax
0x18001c7c4  jmp     loc_18001C8BA
0x18001c7c9  xor     r9d, r9d; lpName
0x18001c7cc  xor     r8d, r8d; bInitialState
0x18001c7cf  xor     edx, edx; bManualReset
0x18001c7d1  xor     ecx, ecx; lpEventAttributes
0x18001c7d3  call    cs:__imp_CreateEventW
0x18001c7d9  mov     [rdi+60h], rax
0x18001c7dd  test    rax, rax
0x18001c7e0  jz      short loc_18001C7BC
0x18001c7e2  xor     r9d, r9d; lpName
0x18001c7e5  xor     r8d, r8d; bInitialState
0x18001c7e8  xor     edx, edx; bManualReset
0x18001c7ea  xor     ecx, ecx; lpEventAttributes
0x18001c7ec  call    cs:__imp_CreateEventW
0x18001c7f2  mov     [rdi+68h], rax
0x18001c7f6  test    rax, rax
0x18001c7f9  jz      short loc_18001C7BC
0x18001c7fb  xor     r9d, r9d; lpName
0x18001c7fe  xor     r8d, r8d; bInitialState
0x18001c801  xor     edx, edx; bManualReset
0x18001c803  xor     ecx, ecx; lpEventAttributes
0x18001c805  call    cs:__imp_CreateEventW
0x18001c80b  mov     [rdi+0F0h], rax
0x18001c812  test    rax, rax
0x18001c815  jz      short loc_18001C7BC
0x18001c817  mov     esi, ebp
0x18001c819  cmp     [rdi], ebp
0x18001c81b  jz      short loc_18001C848
0x18001c81d  call    cs:__imp_GetCurrentThread
0x18001c823  mov     edx, 4; DesiredAccess
0x18001c828  lea     r9, [rdi+0F8h]; TokenHandle
0x18001c82f  mov     rcx, rax; ThreadHandle
0x18001c832  lea     r8d, [rdx-3]; OpenAsSelf
0x18001c836  call    cs:__imp_OpenThreadToken
0x18001c83c  test    eax, eax
0x18001c83e  jnz     short loc_18001C848
0x18001c840  call    cs:__imp_GetLastError
0x18001c846  mov     esi, eax
0x18001c848  mov     dword ptr [rdi+88h], 3
0x18001c852  mov     [rdi+90h], rbp
0x18001c859  mov     [rdi+98h], rbp
0x18001c860  mov     [rdi+0A0h], rbp
0x18001c867  mov     [rdi+0A8h], rbp
0x18001c86e  mov     [rdi+0B0h], rbp
0x18001c875  mov     [rdi+0B8h], rbp
0x18001c87c  mov     [rdi+0C0h], ebp
0x18001c882  mov     dword ptr [rdi+0C4h], 1
0x18001c88c  mov     dword ptr [rdi+0C8h], 48h ; 'H'
0x18001c896  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001c89c  mov     [rdi+0D0h], rax
0x18001c8a3  test    rax, rax
0x18001c8a6  jz      loc_18001C7BC
0x18001c8ac  mov     [rdi+98h], rax
0x18001c8b3  mov     [rdi+0A0h], rbp
0x18001c8ba  mov     eax, esi
0x18001c8bc  add     rsp, 28h
0x18001c8c0  pop     rdi
0x18001c8c1  pop     rsi
0x18001c8c2  pop     rbp
0x18001c8c3  pop     rbx
0x18001c8c4  retn
```
