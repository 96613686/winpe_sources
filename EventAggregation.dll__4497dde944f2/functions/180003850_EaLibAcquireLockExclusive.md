# EaLibAcquireLockExclusive

- ea: `0x180003850`
- end: `0x18000386e`
- name: `EaLibAcquireLockExclusive`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180008ca8`
- `0x180008d98`
- `0x18000b120`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003859`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003859`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000385f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000385f`

## pseudocode

```c
DWORD __fastcall EaLibAcquireLockExclusive(__int64 a1)
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
0x180003850  push    rbx
0x180003852  sub     rsp, 20h
0x180003856  mov     rbx, rcx
0x180003859  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000385f  call    cs:__imp_GetCurrentThreadId
0x180003865  mov     [rbx+8], eax
0x180003868  add     rsp, 20h
0x18000386c  pop     rbx
0x18000386d  retn
```
