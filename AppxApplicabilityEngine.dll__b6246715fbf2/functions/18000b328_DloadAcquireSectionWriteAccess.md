# DloadAcquireSectionWriteAccess

- ea: `0x18000b328`
- end: `0x18000b382`
- name: `DloadAcquireSectionWriteAccess`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000af70`

## callees

- `0x18000b328`
- `0x18000b69c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b344`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b344`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b368`

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
0x18000b328  sub     rsp, 28h
0x18000b32c  test    cs:dword_1800263D0, 1000h
0x18000b336  jnz     short loc_18000B33D
0x18000b338  add     rsp, 28h
0x18000b33c  retn
0x18000b33d  lea     rcx, DloadSrwLock; SRWLock
0x18000b344  call    cs:__imp_AcquireSRWLockExclusive
0x18000b34a  mov     eax, cs:DloadSectionLockCount
0x18000b350  inc     eax
0x18000b352  mov     cs:DloadSectionLockCount, eax
0x18000b358  cmp     eax, 1
0x18000b35b  jz      short loc_18000B36F
0x18000b35d  lea     rcx, DloadSrwLock
0x18000b364  add     rsp, 28h
0x18000b368  jmp     cs:__imp_ReleaseSRWLockExclusive
0x18000b36f  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000b376  mov     ecx, 4; flNewProtect
0x18000b37b  call    DloadProtectSection
0x18000b380  jmp     short loc_18000B35D
```
