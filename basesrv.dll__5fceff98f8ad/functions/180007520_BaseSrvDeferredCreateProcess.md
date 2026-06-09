# BaseSrvDeferredCreateProcess

- ea: `0x180007520`
- end: `0x18000756f`
- name: `BaseSrvDeferredCreateProcess`
- size: `79`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007520`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall BaseSrvDeferredCreateProcess(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 8) != (unsigned int)NtCurrentTeb()->ClientId.UniqueProcess )
    return 3221225506LL;
  result = 0;
  if ( UserNotifyProcessCreate )
    return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))UserNotifyProcessCreate)(
             **(unsigned int **)(a1 + 64),
             0,
             0,
             *(_DWORD *)(a1 + 72) | 0x20u);
  return result;
}

```

## disassembly

```asm
0x180007520  sub     rsp, 38h
0x180007524  mov     rax, gs:40h
0x18000752d  mov     edx, eax
0x18000752f  cmp     [rcx+8], rdx
0x180007533  jz      short loc_180007540
0x180007535  mov     eax, 0C0000022h
0x18000753a  add     rsp, 38h
0x18000753e  retn
0x180007540  mov     r10, cs:UserNotifyProcessCreate
0x180007547  xor     eax, eax
0x180007549  test    r10, r10
0x18000754c  jz      short loc_180007569
0x18000754e  mov     r9d, [rcx+48h]
0x180007552  xor     r8d, r8d
0x180007555  mov     rcx, [rcx+40h]
0x180007559  or      r9d, 20h
0x18000755d  xor     edx, edx
0x18000755f  mov     rax, r10
0x180007562  mov     ecx, [rcx]
0x180007564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007569  add     rsp, 38h
0x18000756d  retn
```
