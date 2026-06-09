# HampIpcChannelAcquireLock

- ea: `0x180004a70`
- end: `0x180004a92`
- name: `HampIpcChannelAcquireLock`
- size: `34`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800049fc`
- `0x18000bed0`
- `0x180019620`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a83`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004a7d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004a7d`

## pseudocode

```c
DWORD __fastcall HampIpcChannelAcquireLock(__int64 a1)
{
  DWORD result; // eax

  RtlAcquireSRWLockExclusive(a1 + 8);
  result = GetCurrentThreadId();
  *(_DWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x180004a70  push    rbx
0x180004a72  sub     rsp, 20h
0x180004a76  mov     rbx, rcx
0x180004a79  add     rcx, 8
0x180004a7d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004a83  call    cs:__imp_GetCurrentThreadId
0x180004a89  mov     [rbx+10h], eax
0x180004a8c  add     rsp, 20h
0x180004a90  pop     rbx
0x180004a91  retn
```
