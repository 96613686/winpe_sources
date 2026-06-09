# CommonUtil::CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>::~CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>(void)

- ea: `0x14000409c`
- end: `0x1400040b4`
- name: `??1?$CGenericAutoScopeLock@V?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fc42`

## callees

- `0x14000409c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1400040a9`
- `KERNEL32!LeaveCriticalSection` at `0x1400040a9`

## pseudocode

```c
void __fastcall CommonUtil::CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>::~CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a1);
}

```

## disassembly

```asm
0x14000409c  sub     rsp, 28h
0x1400040a0  cmp     byte ptr [rcx+8], 0
0x1400040a4  jz      short loc_1400040AF
0x1400040a6  mov     rcx, [rcx]; lpCriticalSection
0x1400040a9  call    cs:__imp_LeaveCriticalSection
0x1400040af  add     rsp, 28h
0x1400040b3  retn
```
