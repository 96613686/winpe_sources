# CommonUtil::CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>::~CGenericAutoScopeLock<CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>>(void)

- ea: `0x140003680`
- end: `0x140003698`
- name: `??1?$CGenericAutoScopeLock@V?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001231f`

## callees

- `0x140003680`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14000368d`
- `KERNEL32!LeaveCriticalSection` at `0x14000368d`

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
0x140003680  sub     rsp, 28h
0x140003684  cmp     byte ptr [rcx+8], 0
0x140003688  jz      short loc_140003693
0x14000368a  mov     rcx, [rcx]; lpCriticalSection
0x14000368d  call    cs:__imp_LeaveCriticalSection
0x140003693  add     rsp, 28h
0x140003697  retn
```
