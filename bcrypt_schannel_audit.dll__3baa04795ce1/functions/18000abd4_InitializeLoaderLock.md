# _InitializeLoaderLock

- ea: `0x18000abd4`
- end: `0x18000ac18`
- name: `_InitializeLoaderLock`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab54`

## callees

- `0x180005060`
- `0x18000abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000abe3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000abe3`

## string_xrefs

- `0x18000abf9`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 InitializeLoaderLock()
{
  InitializeCriticalSection(&g_csLoaderLock);
  return 0;
}

```

## disassembly

```asm
0x18000abd4  push    rbx
0x18000abd6  sub     rsp, 20h
0x18000abda  xor     ebx, ebx
0x18000abdc  lea     rcx, g_csLoaderLock; lpCriticalSection
0x18000abe3  call    cs:__imp_InitializeCriticalSection
0x18000abea  nop     dword ptr [rax+rax+00h]
0x18000abef  jmp     short loc_18000AC0F
0x18000abf1  mov     ebx, eax
0x18000abf3  mov     r9d, 0D0h
0x18000abf9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ac00  lea     rdx, aSresult; "sResult"
0x18000ac07  mov     ecx, eax
0x18000ac09  call    DebugTraceError
0x18000ac0e  nop
0x18000ac0f  mov     eax, ebx
0x18000ac11  add     rsp, 20h
0x18000ac15  pop     rbx
0x18000ac16  retn
```
