# DloadReleaseSectionWriteAccess

- ea: `0x18001c9b8`
- end: `0x18001ca15`
- name: `DloadReleaseSectionWriteAccess`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca20`

## callees

- `0x18001c8c8`
- `0x18001c9b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c9d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c9d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ca03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ca03`

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
0x18001c9b8  sub     rsp, 28h
0x18001c9bc  test    cs:dword_18001F140, 1000h
0x18001c9c6  mov     [rsp+28h+flOldProtect], 0
0x18001c9ce  jz      short loc_18001CA0F
0x18001c9d0  lea     rcx, DloadSrwLock; SRWLock
0x18001c9d7  call    cs:__imp_AcquireSRWLockExclusive
0x18001c9de  nop     dword ptr [rax+rax+00h]
0x18001c9e3  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18001c9ea  jnz     short loc_18001C9FC
0x18001c9ec  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18001c9f2  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x18001c9f7  call    DloadProtectSection
0x18001c9fc  lea     rcx, DloadSrwLock; SRWLock
0x18001ca03  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ca0a  nop     dword ptr [rax+rax+00h]
0x18001ca0f  add     rsp, 28h
0x18001ca13  retn
```
