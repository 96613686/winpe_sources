# UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)

- ea: `0x1800103c0`
- end: `0x1800103eb`
- name: `?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z`
- size: `43`
- prototype: `void __fastcall(struct _UBPM_SRWLOCK *)`
- caller_count: `33`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001a3c`
- `0x180002ec0`
- `0x180003100`
- `0x1800033b0`
- `0x180003438`
- `0x180003da0`
- `0x18000d9bc`
- `0x18000dda4`
- `0x180010220`
- `0x180011480`
- `0x18001be4c`
- `0x18001c160`
- `0x18001cb40`
- `0x180024d08`
- `0x180029060`
- `0x18002cdc0`
- `0x18002d260`
- `0x18002d654`
- `0x18002f7f0`
- `0x18002fde0`
- `0x180030234`
- `0x180030390`
- `0x180032acc`
- `0x180036910`
- `0x1800371e0`
- `0x1800381e0`
- `0x180038dd0`
- `0x180038e50`
- `0x180038f40`
- `0x1800390b0`
- `0x18003e53c`
- `0x18003e9bc`
- `0x18003ea60`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800103c9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800103c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103d5`

## pseudocode

```c
void __fastcall UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(struct _UBPM_SRWLOCK *a1)
{
  RtlAcquireSRWLockExclusive(a1);
  *((_DWORD *)a1 + 2) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x1800103c0  push    rbx
0x1800103c2  sub     rsp, 20h
0x1800103c6  mov     rbx, rcx
0x1800103c9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800103d0  nop     dword ptr [rax+rax+00h]
0x1800103d5  call    cs:__imp_GetCurrentThreadId
0x1800103dc  nop     dword ptr [rax+rax+00h]
0x1800103e1  mov     [rbx+8], eax
0x1800103e4  add     rsp, 20h
0x1800103e8  pop     rbx
0x1800103e9  retn
```
