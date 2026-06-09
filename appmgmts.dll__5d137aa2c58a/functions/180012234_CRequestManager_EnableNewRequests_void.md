# CRequestManager::EnableNewRequests(void)

- ea: `0x180012234`
- end: `0x1800122a1`
- name: `?EnableNewRequests@CRequestManager@@QEAAKXZ`
- size: `109`
- prototype: `__int64 __fastcall(CRequestManager *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800124bc`

## callees

- `0x180012234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001228c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001228c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012274`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012274`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001224c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001224c`

## pseudocode

```c
__int64 __fastcall CRequestManager::EnableNewRequests(CRequestManager *this)
{
  unsigned int v2; // edi
  HANDLE EventW; // rax

  v2 = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 14) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 1) = EventW;
  if ( EventW )
    *((_DWORD *)this + 15) = 1;
  else
    return GetLastError();
  return v2;
}

```

## disassembly

```asm
0x180012234  mov     [rsp+arg_8], rbx
0x180012239  mov     [rsp+arg_0], rcx
0x18001223e  push    rdi
0x18001223f  sub     rsp, 20h
0x180012243  mov     rbx, rcx
0x180012246  xor     edi, edi
0x180012248  add     rcx, 10h; lpCriticalSection
0x18001224c  call    cs:__imp_InitializeCriticalSection
0x180012252  jmp     short loc_18001225E
0x180012254  mov     edi, 0Eh
0x180012259  mov     rbx, [rsp+28h+arg_0]
0x18001225e  test    edi, edi
0x180012260  jnz     short loc_180012294
0x180012262  mov     dword ptr [rbx+38h], 1
0x180012269  xor     r9d, r9d; lpName
0x18001226c  xor     r8d, r8d; bInitialState
0x18001226f  lea     edx, [rdi+1]; bManualReset
0x180012272  xor     ecx, ecx; lpEventAttributes
0x180012274  call    cs:__imp_CreateEventW
0x18001227a  mov     [rbx+8], rax
0x18001227e  test    rax, rax
0x180012281  jz      short loc_18001228C
0x180012283  mov     dword ptr [rbx+3Ch], 1
0x18001228a  jmp     short loc_180012294
0x18001228c  call    cs:__imp_GetLastError
0x180012292  mov     edi, eax
0x180012294  mov     eax, edi
0x180012296  mov     rbx, [rsp+28h+arg_8]
0x18001229b  add     rsp, 20h
0x18001229f  pop     rdi
0x1800122a0  retn
```
