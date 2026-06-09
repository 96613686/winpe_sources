# _pSpUtilsInitializeSynchronizedAccess

- ea: `0x14000b8dc`
- end: `0x14000b95e`
- name: `_pSpUtilsInitializeSynchronizedAccess`
- size: `130`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140010a88`
- `0x140010ad8`

## callees

- `0x14000b8dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b8fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b8fc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000b911`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000b911`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b924`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b93e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b93e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b92f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b92f`

## pseudocode

```c
__int64 __fastcall pSpUtilsInitializeSynchronizedAccess(__int64 a1)
{
  HANDLE EventW; // rax
  HANDLE MutexW; // rax
  DWORD LastError; // ebx

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)a1 = EventW;
  if ( EventW )
  {
    MutexW = CreateMutexW(0, 0, 0);
    *(_QWORD *)(a1 + 8) = MutexW;
    if ( MutexW )
      return 1;
    LastError = GetLastError();
    CloseHandle(*(HANDLE *)a1);
    *(_QWORD *)a1 = 0;
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 8) = 0;
  return 0;
}

```

## disassembly

```asm
0x14000b8dc  mov     [rsp+arg_0], rbx
0x14000b8e1  mov     [rsp+arg_8], rsi
0x14000b8e6  push    rdi
0x14000b8e7  sub     rsp, 20h
0x14000b8eb  xor     r9d, r9d; lpName
0x14000b8ee  mov     rsi, rcx
0x14000b8f1  xor     r8d, r8d; bInitialState
0x14000b8f4  xor     ecx, ecx; lpEventAttributes
0x14000b8f6  lea     ebx, [r9+1]
0x14000b8fa  mov     edx, ebx; bManualReset
0x14000b8fc  call    cs:__imp_CreateEventW
0x14000b902  mov     [rsi], rax
0x14000b905  test    rax, rax
0x14000b908  jz      short loc_14000B944
0x14000b90a  xor     r8d, r8d; lpName
0x14000b90d  xor     edx, edx; bInitialOwner
0x14000b90f  xor     ecx, ecx; lpMutexAttributes
0x14000b911  call    cs:__imp_CreateMutexW
0x14000b917  mov     [rsi+8], rax
0x14000b91b  test    rax, rax
0x14000b91e  jz      short loc_14000B924
0x14000b920  mov     eax, ebx
0x14000b922  jmp     short loc_14000B94E
0x14000b924  call    cs:__imp_GetLastError
0x14000b92a  mov     rcx, [rsi]; hObject
0x14000b92d  mov     ebx, eax
0x14000b92f  call    cs:__imp_CloseHandle
0x14000b935  mov     ecx, ebx; dwErrCode
0x14000b937  mov     qword ptr [rsi], 0
0x14000b93e  call    cs:__imp_SetLastError
0x14000b944  mov     qword ptr [rsi+8], 0
0x14000b94c  xor     eax, eax
0x14000b94e  mov     rbx, [rsp+28h+arg_0]
0x14000b953  mov     rsi, [rsp+28h+arg_8]
0x14000b958  add     rsp, 20h
0x14000b95c  pop     rdi
0x14000b95d  retn
```
