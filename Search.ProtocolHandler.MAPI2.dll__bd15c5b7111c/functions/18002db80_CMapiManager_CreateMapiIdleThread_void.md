# CMapiManager::CreateMapiIdleThread(void)

- ea: `0x18002db80`
- end: `0x18002dc2b`
- name: `?CreateMapiIdleThread@CMapiManager@@AEAAJXZ`
- size: `171`
- prototype: `DWORD __fastcall(CMapiManager *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ec78`

## callees

- `0x18000b9f0`
- `0x18002db80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dbab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002dbab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dc10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002dc10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbfe`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002dbec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002dbec`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
DWORD __fastcall CMapiManager::CreateMapiIdleThread(CMapiManager *this)
{
  DWORD result; // eax
  HANDLE EventW; // rax
  HANDLE v4; // rax
  bool v5; // zf
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 32) == 1 )
    return 0;
  *((_DWORD *)this + 32) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 23) = EventW;
  if ( !EventW )
    return ResultFromLastError();
  ThreadId = 0;
  v4 = CreateThread(0, 0, MapiIdleThreadMain, this, 0, &ThreadId);
  *((_QWORD *)this + 22) = v4;
  if ( !v4 )
    return GetLastError();
  v5 = WaitForSingleObject(*((HANDLE *)this + 23), 0xFFFFFFFF) == 0;
  result = -2147467259;
  if ( v5 )
    return *((_DWORD *)this + 48);
  return result;
}

```

## disassembly

```asm
0x18002db80  push    rbx
0x18002db82  sub     rsp, 30h
0x18002db86  mov     edx, 1; bManualReset
0x18002db8b  mov     rbx, rcx
0x18002db8e  cmp     [rcx+80h], edx
0x18002db94  jnz     short loc_18002DB9D
0x18002db96  xor     eax, eax
0x18002db98  jmp     loc_18002DC25
0x18002db9d  mov     [rcx+80h], edx
0x18002dba3  xor     r9d, r9d; lpName
0x18002dba6  xor     ecx, ecx; lpEventAttributes
0x18002dba8  xor     r8d, r8d; bInitialState
0x18002dbab  call    cs:__imp_CreateEventW
0x18002dbb1  mov     [rbx+0B8h], rax
0x18002dbb8  test    rax, rax
0x18002dbbb  jnz     short loc_18002DBC4
0x18002dbbd  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002dbc2  jmp     short loc_18002DC25
0x18002dbc4  lea     rax, [rsp+38h+ThreadId]
0x18002dbc9  mov     [rsp+38h+ThreadId], 0
0x18002dbd1  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18002dbd6  lea     r8, ?MapiIdleThreadMain@@YAKPEAX@Z; lpStartAddress
0x18002dbdd  mov     r9, rbx; lpParameter
0x18002dbe0  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18002dbe8  xor     edx, edx; dwStackSize
0x18002dbea  xor     ecx, ecx; lpThreadAttributes
0x18002dbec  call    cs:__imp_CreateThread
0x18002dbf2  mov     [rbx+0B0h], rax
0x18002dbf9  test    rax, rax
0x18002dbfc  jnz     short loc_18002DC06
0x18002dbfe  call    cs:__imp_GetLastError
0x18002dc04  jmp     short loc_18002DC25
0x18002dc06  mov     rcx, [rbx+0B8h]; hHandle
0x18002dc0d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002dc10  call    cs:__imp_WaitForSingleObject
0x18002dc16  test    eax, eax
0x18002dc18  mov     eax, 80004005h
0x18002dc1d  jnz     short loc_18002DC25
0x18002dc1f  mov     eax, [rbx+0C0h]
0x18002dc25  add     rsp, 30h
0x18002dc29  pop     rbx
0x18002dc2a  retn
```
