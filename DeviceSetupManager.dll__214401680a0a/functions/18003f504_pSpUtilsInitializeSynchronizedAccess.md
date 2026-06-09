# _pSpUtilsInitializeSynchronizedAccess

- ea: `0x18003f504`
- end: `0x18003f586`
- name: `_pSpUtilsInitializeSynchronizedAccess`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180040390`
- `0x1800403e0`

## callees

- `0x18003f504`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f524`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f524`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18003f539`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18003f539`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f566`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f54c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f557`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f557`

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
0x18003f504  mov     [rsp+arg_0], rbx
0x18003f509  mov     [rsp+arg_8], rsi
0x18003f50e  push    rdi
0x18003f50f  sub     rsp, 20h
0x18003f513  xor     r9d, r9d; lpName
0x18003f516  mov     rsi, rcx
0x18003f519  xor     r8d, r8d; bInitialState
0x18003f51c  xor     ecx, ecx; lpEventAttributes
0x18003f51e  lea     ebx, [r9+1]
0x18003f522  mov     edx, ebx; bManualReset
0x18003f524  call    cs:__imp_CreateEventW
0x18003f52a  mov     [rsi], rax
0x18003f52d  test    rax, rax
0x18003f530  jz      short loc_18003F56C
0x18003f532  xor     r8d, r8d; lpName
0x18003f535  xor     edx, edx; bInitialOwner
0x18003f537  xor     ecx, ecx; lpMutexAttributes
0x18003f539  call    cs:__imp_CreateMutexW
0x18003f53f  mov     [rsi+8], rax
0x18003f543  test    rax, rax
0x18003f546  jz      short loc_18003F54C
0x18003f548  mov     eax, ebx
0x18003f54a  jmp     short loc_18003F576
0x18003f54c  call    cs:__imp_GetLastError
0x18003f552  mov     rcx, [rsi]; hObject
0x18003f555  mov     ebx, eax
0x18003f557  call    cs:__imp_CloseHandle
0x18003f55d  mov     ecx, ebx; dwErrCode
0x18003f55f  mov     qword ptr [rsi], 0
0x18003f566  call    cs:__imp_SetLastError
0x18003f56c  mov     qword ptr [rsi+8], 0
0x18003f574  xor     eax, eax
0x18003f576  mov     rbx, [rsp+28h+arg_0]
0x18003f57b  mov     rsi, [rsp+28h+arg_8]
0x18003f580  add     rsp, 20h
0x18003f584  pop     rdi
0x18003f585  retn
```
