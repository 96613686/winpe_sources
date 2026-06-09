# DloadReleaseSectionWriteAccess

- ea: `0x18000b2d0`
- end: `0x18000b322`
- name: `DloadReleaseSectionWriteAccess`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000af70`

## callees

- `0x18000b2d0`
- `0x18000b69c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b2ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b305`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b305`

## pseudocode

```c
void DloadReleaseSectionWriteAccess()
{
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  flOldProtect = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
  ReleaseSRWLockExclusive(&DloadSrwLock);
}

```

## disassembly

```asm
0x18000b2d0  sub     rsp, 28h
0x18000b2d4  test    cs:dword_1800263D0, 1000h
0x18000b2de  mov     [rsp+28h+flOldProtect], 0
0x18000b2e6  jz      short loc_18000B30B
0x18000b2e8  lea     rcx, DloadSrwLock; SRWLock
0x18000b2ef  call    cs:__imp_AcquireSRWLockExclusive
0x18000b2f5  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000b2fc  jz      short loc_18000B310
0x18000b2fe  lea     rcx, DloadSrwLock; SRWLock
0x18000b305  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b30b  add     rsp, 28h
0x18000b30f  retn
0x18000b310  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000b316  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x18000b31b  call    DloadProtectSection
0x18000b320  jmp     short loc_18000B2FE
```
