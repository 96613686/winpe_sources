# DloadAcquireSectionWriteAccess

- ea: `0x1800097d0`
- end: `0x18000982e`
- name: `DloadAcquireSectionWriteAccess`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009a60`

## callees

- `0x1800097d0`
- `0x180009900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000981c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000981c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800097e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800097e7`

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
0x1800097d0  sub     rsp, 28h
0x1800097d4  test    cs:dword_18000C0C0, 1000h
0x1800097de  jz      short loc_180009828
0x1800097e0  lea     rcx, DloadSrwLock; SRWLock
0x1800097e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800097ee  nop     dword ptr [rax+rax+00h]
0x1800097f3  mov     eax, cs:DloadSectionLockCount
0x1800097f9  inc     eax
0x1800097fb  mov     cs:DloadSectionLockCount, eax
0x180009801  cmp     eax, 1
0x180009804  jnz     short loc_180009815
0x180009806  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000980d  lea     ecx, [rax+3]; flNewProtect
0x180009810  call    DloadProtectSection
0x180009815  lea     rcx, DloadSrwLock; SRWLock
0x18000981c  call    cs:__imp_ReleaseSRWLockExclusive
0x180009823  nop     dword ptr [rax+rax+00h]
0x180009828  add     rsp, 28h
0x18000982c  retn
```
