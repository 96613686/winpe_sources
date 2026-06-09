# DloadAcquireSectionWriteAccess

- ea: `0x18001c798`
- end: `0x18001c7f6`
- name: `DloadAcquireSectionWriteAccess`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca20`

## callees

- `0x18001c798`
- `0x18001c8c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c7af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c7e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c7e4`

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
0x18001c798  sub     rsp, 28h
0x18001c79c  test    cs:dword_18001F140, 1000h
0x18001c7a6  jz      short loc_18001C7F0
0x18001c7a8  lea     rcx, DloadSrwLock; SRWLock
0x18001c7af  call    cs:__imp_AcquireSRWLockExclusive
0x18001c7b6  nop     dword ptr [rax+rax+00h]
0x18001c7bb  mov     eax, cs:DloadSectionLockCount
0x18001c7c1  inc     eax
0x18001c7c3  mov     cs:DloadSectionLockCount, eax
0x18001c7c9  cmp     eax, 1
0x18001c7cc  jnz     short loc_18001C7DD
0x18001c7ce  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18001c7d5  lea     ecx, [rax+3]; flNewProtect
0x18001c7d8  call    DloadProtectSection
0x18001c7dd  lea     rcx, DloadSrwLock; SRWLock
0x18001c7e4  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c7eb  nop     dword ptr [rax+rax+00h]
0x18001c7f0  add     rsp, 28h
0x18001c7f4  retn
```
