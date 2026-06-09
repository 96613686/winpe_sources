# DloadReleaseSectionWriteAccess

- ea: `0x1800099f0`
- end: `0x180009a4d`
- name: `DloadReleaseSectionWriteAccess`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009a60`

## callees

- `0x180009900`
- `0x1800099f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009a3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a0f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a0f`

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
0x1800099f0  sub     rsp, 28h
0x1800099f4  test    cs:dword_18000C0C0, 1000h
0x1800099fe  mov     [rsp+28h+flOldProtect], 0
0x180009a06  jz      short loc_180009A47
0x180009a08  lea     rcx, DloadSrwLock; SRWLock
0x180009a0f  call    cs:__imp_AcquireSRWLockExclusive
0x180009a16  nop     dword ptr [rax+rax+00h]
0x180009a1b  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180009a22  jnz     short loc_180009A34
0x180009a24  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180009a2a  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x180009a2f  call    DloadProtectSection
0x180009a34  lea     rcx, DloadSrwLock; SRWLock
0x180009a3b  call    cs:__imp_ReleaseSRWLockExclusive
0x180009a42  nop     dword ptr [rax+rax+00h]
0x180009a47  add     rsp, 28h
0x180009a4b  retn
```
