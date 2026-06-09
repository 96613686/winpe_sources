# RPC_SRWLOCK::Request(RPC_SRWLOCK::LockMode)

- ea: `0x180005080`
- end: `0x1800050b1`
- name: `?Request@RPC_SRWLOCK@@QEAAXW4LockMode@1@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800018a0`
- `0x180003a1c`
- `0x180006e70`
- `0x180007300`

## callees

- `0x180005080`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x1800050aa`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005094`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180005094`

## pseudocode

```c
__int64 __fastcall RPC_SRWLOCK::Request(__int64 a1, int a2)
{
  __int64 result; // rax

  if ( !a2 )
    return RtlAcquireSRWLockShared(&EpMapRWLock);
  if ( a2 == 1 )
    return RtlAcquireSRWLockExclusive(&EpMapRWLock);
  return result;
}

```

## disassembly

```asm
0x180005080  sub     rsp, 28h
0x180005084  test    edx, edx
0x180005086  jz      short loc_18000509F
0x180005088  cmp     edx, 1
0x18000508b  jnz     short loc_18000509A
0x18000508d  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x180005094  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000509a  add     rsp, 28h
0x18000509e  retn
0x18000509f  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x1800050a6  add     rsp, 28h
0x1800050aa  jmp     cs:__imp_RtlAcquireSRWLockShared
```
