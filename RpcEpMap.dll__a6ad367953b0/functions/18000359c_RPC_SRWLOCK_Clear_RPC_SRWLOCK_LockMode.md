# RPC_SRWLOCK::Clear(RPC_SRWLOCK::LockMode)

- ea: `0x18000359c`
- end: `0x1800035cd`
- name: `?Clear@RPC_SRWLOCK@@QEAAXW4LockMode@1@@Z`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800014b0`
- `0x1800018a0`
- `0x180003a1c`
- `0x180006e70`
- `0x180007300`

## callees

- `0x18000359c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800035c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800035b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800035b0`

## pseudocode

```c
__int64 __fastcall RPC_SRWLOCK::Clear(__int64 a1, int a2)
{
  __int64 result; // rax

  if ( !a2 )
    return RtlReleaseSRWLockShared(&EpMapRWLock);
  if ( a2 == 1 )
    return RtlReleaseSRWLockExclusive(&EpMapRWLock);
  return result;
}

```

## disassembly

```asm
0x18000359c  sub     rsp, 28h
0x1800035a0  test    edx, edx
0x1800035a2  jz      short loc_1800035BB
0x1800035a4  cmp     edx, 1
0x1800035a7  jnz     short loc_1800035B6
0x1800035a9  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x1800035b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800035b6  add     rsp, 28h
0x1800035ba  retn
0x1800035bb  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x1800035c2  add     rsp, 28h
0x1800035c6  jmp     cs:__imp_RtlReleaseSRWLockShared
```
