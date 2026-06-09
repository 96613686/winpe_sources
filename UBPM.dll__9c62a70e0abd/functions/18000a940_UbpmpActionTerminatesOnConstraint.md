# UbpmpActionTerminatesOnConstraint

- ea: `0x18000a940`
- end: `0x18000a9a4`
- name: `UbpmpActionTerminatesOnConstraint`
- size: `100`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800293d0`
- `0x18002d890`

## callees

- `0x180009a30`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a95b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a95b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a967`

## pseudocode

```c
__int64 __fastcall UbpmpActionTerminatesOnConstraint(struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1, int a2, RPC_STATUS a3)
{
  char *v3; // rbp

  v3 = (char *)a1 + 208;
  RtlAcquireSRWLockExclusive((char *)a1 + 208);
  *((_DWORD *)v3 + 2) = GetCurrentThreadId();
  UbpmpActionTerminatesOnConstraintLocked(a1, a2, a3, 0);
  *((_DWORD *)v3 + 2) = 0;
  return RtlReleaseSRWLockExclusive(v3);
}

```

## disassembly

```asm
0x18000a940  push    rbx
0x18000a942  push    rbp
0x18000a943  push    rsi
0x18000a944  push    rdi
0x18000a945  sub     rsp, 28h
0x18000a949  lea     rbp, [rcx+0D0h]
0x18000a950  mov     rsi, rcx
0x18000a953  mov     rcx, rbp
0x18000a956  mov     ebx, r8d
0x18000a959  mov     edi, edx
0x18000a95b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a962  nop     dword ptr [rax+rax+00h]
0x18000a967  call    cs:__imp_GetCurrentThreadId
0x18000a96e  nop     dword ptr [rax+rax+00h]
0x18000a973  xor     r9d, r9d; struct _GUID *
0x18000a976  mov     r8d, ebx; unsigned int
0x18000a979  mov     edx, edi; unsigned int
0x18000a97b  mov     [rbp+8], eax
0x18000a97e  mov     rcx, rsi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000a981  call    ?UbpmpActionTerminatesOnConstraintLocked@@YAXPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@KKPEAU_GUID@@@Z; UbpmpActionTerminatesOnConstraintLocked(_UBPM_TRIGGER_CONSUMER_BLOCK *,ulong,ulong,_GUID *)
0x18000a986  mov     rcx, rbp
0x18000a989  mov     dword ptr [rbp+8], 0
0x18000a990  add     rsp, 28h
0x18000a994  pop     rdi
0x18000a995  pop     rsi
0x18000a996  pop     rbp
0x18000a997  pop     rbx
0x18000a998  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
