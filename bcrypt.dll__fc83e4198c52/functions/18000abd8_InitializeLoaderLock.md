# _InitializeLoaderLock

- ea: `0x18000abd8`
- end: `0x18000ac1c`
- name: `_InitializeLoaderLock`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab58`

## callees

- `0x180005060`
- `0x18000abd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000abe7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000abe7`

## string_xrefs

- `0x18000abfd`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

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
0x18000abd8  push    rbx
0x18000abda  sub     rsp, 20h
0x18000abde  xor     ebx, ebx
0x18000abe0  lea     rcx, g_csLoaderLock; lpCriticalSection
0x18000abe7  call    cs:__imp_InitializeCriticalSection
0x18000abee  nop     dword ptr [rax+rax+00h]
0x18000abf3  jmp     short loc_18000AC13
0x18000abf5  mov     ebx, eax
0x18000abf7  mov     r9d, 0D0h
0x18000abfd  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ac04  lea     rdx, aSresult; "sResult"
0x18000ac0b  mov     ecx, eax
0x18000ac0d  call    DebugTraceError
0x18000ac12  nop
0x18000ac13  mov     eax, ebx
0x18000ac15  add     rsp, 20h
0x18000ac19  pop     rbx
0x18000ac1a  retn
```
