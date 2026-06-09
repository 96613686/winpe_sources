# CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::~CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(void)

- ea: `0x14001e250`
- end: `0x14001e268`
- name: `??1?$CGenericAutoLock@U?$CMpWriteLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400262f3`

## callees

- `0x14001e250`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001e25d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001e25d`

## pseudocode

```c
void __fastcall CommonUtil::CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>::~CGenericAutoLock<CommonUtil::CMpWriteLockFunctor<CommonUtil::CMpSRWLock>>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    ReleaseSRWLockExclusive(*(PSRWLOCK *)a1);
}

```

## disassembly

```asm
0x14001e250  sub     rsp, 28h
0x14001e254  cmp     byte ptr [rcx+8], 0
0x14001e258  jz      short loc_14001E263
0x14001e25a  mov     rcx, [rcx]; SRWLock
0x14001e25d  call    cs:__imp_ReleaseSRWLockExclusive
0x14001e263  add     rsp, 28h
0x14001e267  retn
```
