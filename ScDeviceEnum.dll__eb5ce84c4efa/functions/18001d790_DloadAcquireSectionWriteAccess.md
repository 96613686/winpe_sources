# DloadAcquireSectionWriteAccess

- ea: `0x18001d790`
- end: `0x18001d7e1`
- name: `DloadAcquireSectionWriteAccess`
- size: `81`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d9f0`

## callees

- `0x18001d790`
- `0x18001d8a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d7a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d7a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d7d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d7d6`

## pseudocode

```c
void DloadAcquireSectionWriteAccess()
{
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
}

```

## disassembly

```asm
0x18001d790  sub     rsp, 28h
0x18001d794  test    cs:dword_180021A70, 1000h
0x18001d79e  jz      short loc_18001D7DC
0x18001d7a0  lea     rcx, DloadSrwLock; SRWLock
0x18001d7a7  call    cs:__imp_AcquireSRWLockExclusive
0x18001d7ad  mov     eax, cs:DloadSectionLockCount
0x18001d7b3  inc     eax
0x18001d7b5  mov     cs:DloadSectionLockCount, eax
0x18001d7bb  cmp     eax, 1
0x18001d7be  jnz     short loc_18001D7CF
0x18001d7c0  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18001d7c7  lea     ecx, [rax+3]; flNewProtect
0x18001d7ca  call    DloadProtectSection
0x18001d7cf  lea     rcx, DloadSrwLock; SRWLock
0x18001d7d6  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d7dc  add     rsp, 28h
0x18001d7e0  retn
```
