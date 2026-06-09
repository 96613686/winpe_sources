# CempLockAcquireExclusive

- ea: `0x180001d14`
- end: `0x180001d32`
- name: `CempLockAcquireExclusive`
- size: `30`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800010a4`
- `0x180001c30`
- `0x180001c90`
- `0x180001f68`
- `0x180011f30`
- `0x180019620`
- `0x18001a82c`
- `0x18001a964`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d23`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001d1d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001d1d`

## pseudocode

```c
DWORD __fastcall CempLockAcquireExclusive(__int64 a1)
{
  DWORD result; // eax

  RtlAcquireSRWLockExclusive(a1);
  result = GetCurrentThreadId();
  *(_DWORD *)(a1 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x180001d14  push    rbx
0x180001d16  sub     rsp, 20h
0x180001d1a  mov     rbx, rcx
0x180001d1d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001d23  call    cs:__imp_GetCurrentThreadId
0x180001d29  mov     [rbx+8], eax
0x180001d2c  add     rsp, 20h
0x180001d30  pop     rbx
0x180001d31  retn
```
