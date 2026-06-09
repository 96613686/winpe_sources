# CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::~CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(void)

- ea: `0x14001e238`
- end: `0x14001e250`
- name: `??1?$CGenericAutoLock@U?$CMpReadLockFunctor@VCMpSRWLock@CommonUtil@@@CommonUtil@@@CommonUtil@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400262e7`

## callees

- `0x14001e238`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x14001e245`
- `KERNEL32!ReleaseSRWLockShared` at `0x14001e245`

## pseudocode

```c
void __fastcall CommonUtil::CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>::~CGenericAutoLock<CommonUtil::CMpReadLockFunctor<CommonUtil::CMpSRWLock>>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    ReleaseSRWLockShared(*(PSRWLOCK *)a1);
}

```

## disassembly

```asm
0x14001e238  sub     rsp, 28h
0x14001e23c  cmp     byte ptr [rcx+8], 0
0x14001e240  jz      short loc_14001E24B
0x14001e242  mov     rcx, [rcx]; SRWLock
0x14001e245  call    cs:__imp_ReleaseSRWLockShared
0x14001e24b  add     rsp, 28h
0x14001e24f  retn
```
