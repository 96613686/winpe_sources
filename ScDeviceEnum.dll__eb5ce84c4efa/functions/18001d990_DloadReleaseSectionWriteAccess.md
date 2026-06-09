# DloadReleaseSectionWriteAccess

- ea: `0x18001d990`
- end: `0x18001d9e0`
- name: `DloadReleaseSectionWriteAccess`
- size: `80`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d9f0`

## callees

- `0x18001d8a8`
- `0x18001d990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d9af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d9af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d9d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d9d5`

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
0x18001d990  sub     rsp, 28h
0x18001d994  test    cs:dword_180021A70, 1000h
0x18001d99e  mov     [rsp+28h+flOldProtect], 0
0x18001d9a6  jz      short loc_18001D9DB
0x18001d9a8  lea     rcx, DloadSrwLock; SRWLock
0x18001d9af  call    cs:__imp_AcquireSRWLockExclusive
0x18001d9b5  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18001d9bc  jnz     short loc_18001D9CE
0x18001d9be  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18001d9c4  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x18001d9c9  call    DloadProtectSection
0x18001d9ce  lea     rcx, DloadSrwLock; SRWLock
0x18001d9d5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d9db  add     rsp, 28h
0x18001d9df  retn
```
