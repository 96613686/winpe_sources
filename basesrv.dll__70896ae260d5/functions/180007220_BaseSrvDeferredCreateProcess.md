# BaseSrvDeferredCreateProcess

- ea: `0x180007220`
- end: `0x180007273`
- name: `BaseSrvDeferredCreateProcess`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180007220`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall BaseSrvDeferredCreateProcess(__int64 a1)
{
  unsigned int v1; // r8d

  v1 = 0;
  if ( *(_QWORD *)(a1 + 8) != (unsigned int)NtCurrentTeb()->ClientId.UniqueProcess )
    return 3221225506LL;
  if ( UserNotifyProcessCreate )
    return (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))UserNotifyProcessCreate)(
                           **(unsigned int **)(a1 + 64),
                           0,
                           0,
                           *(_DWORD *)(a1 + 72) | 0x20u);
  return v1;
}

```

## disassembly

```asm
0x180007220  sub     rsp, 38h
0x180007224  mov     rax, gs:40h
0x18000722d  xor     r8d, r8d
0x180007230  mov     edx, eax
0x180007232  cmp     [rcx+8], rdx
0x180007236  jz      short loc_180007243
0x180007238  mov     eax, 0C0000022h
0x18000723d  add     rsp, 38h
0x180007241  retn
0x180007243  mov     r10, cs:UserNotifyProcessCreate
0x18000724a  test    r10, r10
0x18000724d  jz      short loc_18000726A
0x18000724f  mov     rax, [rcx+40h]
0x180007253  xor     edx, edx
0x180007255  mov     r9d, [rcx+48h]
0x180007259  or      r9d, 20h
0x18000725d  mov     ecx, [rax]
0x18000725f  mov     rax, r10
0x180007262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007267  mov     r8d, eax
0x18000726a  mov     eax, r8d
0x18000726d  add     rsp, 38h
0x180007271  retn
```
