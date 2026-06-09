# CreateTlgAggregateSession

- ea: `0x14000ec90`
- end: `0x14000edc0`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ef90`

## callees

- `0x140002ac0`
- `0x14000ec90`
- `0x14000edc8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000ed44`
- `ntoskrnl!KeInitializeEvent` at `0x14000ed44`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ecbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ed0e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ecbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ed0e`
- `ntoskrnl!ExAllocateTimer` at `0x14000ed91`
- `ntoskrnl!ExAllocateTimer` at `0x14000ed91`

## pseudocode

```c
_QWORD *__fastcall CreateTlgAggregateSession(char a1, char a2)
{
  _QWORD *PoolWithTag; // rax
  _QWORD *v5; // rbx
  char *v6; // rax
  char *v7; // rdi
  _QWORD *v8; // rax
  __int64 Timer; // rax

  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : 512), 0x178u, 0x47417254u);
  v5 = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_9;
  memset(PoolWithTag, 0, 0x178u);
  v5[34] = 0;
  if ( a2 || !a1 )
  {
    v6 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x40u, 0x47417254u);
    v7 = v6;
    if ( v6 )
      memset(v6, 0, 0x40u);
    v5[33] = v7;
    if ( !v7 )
      goto LABEL_9;
    KeInitializeEvent((PRKEVENT)(v7 + 32), NotificationEvent, 0);
    v8 = (_QWORD *)v5[33];
    v8[2] = TlgAggregateInternalFlushWorkItemRoutineKernelMode;
    v8[3] = v5;
    *v8 = 0;
    *(_WORD *)(v5[33] + 56LL) = 0;
    if ( a2 )
    {
      Timer = ExAllocateTimer(TlgAggregateInternalFlushTimerCallbackKernelMode, v5[33], 8);
      v5[45] = Timer;
      if ( !Timer )
      {
LABEL_9:
        DestroyAggregateSession(v5);
        return 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000ec90  push    rbx
0x14000ec92  push    rbp
0x14000ec93  push    rsi
0x14000ec94  push    rdi
0x14000ec95  sub     rsp, 28h
0x14000ec99  mov     al, cl
0x14000ec9b  mov     dil, cl
0x14000ec9e  neg     al
0x14000eca0  mov     sil, dl
0x14000eca3  mov     ebp, 178h
0x14000eca8  mov     r8d, 47417254h; Tag
0x14000ecae  sbb     ecx, ecx
0x14000ecb0  mov     edx, ebp; NumberOfBytes
0x14000ecb2  and     ecx, 0FFFFFE01h
0x14000ecb8  add     ecx, 200h; PoolType
0x14000ecbe  call    cs:__imp_ExAllocatePoolWithTag
0x14000ecc5  nop     dword ptr [rax+rax+00h]
0x14000ecca  mov     rbx, rax
0x14000eccd  test    rax, rax
0x14000ecd0  jz      loc_14000EDA9
0x14000ecd6  mov     r8d, ebp; Size
0x14000ecd9  xor     edx, edx; Val
0x14000ecdb  mov     rcx, rax; void *
0x14000ecde  call    memset
0x14000ece3  mov     qword ptr [rbx+110h], 0
0x14000ecee  test    sil, sil
0x14000ecf1  jnz     short loc_14000ECFC
0x14000ecf3  test    dil, dil
0x14000ecf6  jnz     loc_14000EDB3
0x14000ecfc  mov     ebp, 40h ; '@'
0x14000ed01  mov     r8d, 47417254h; Tag
0x14000ed07  mov     edx, ebp; NumberOfBytes
0x14000ed09  mov     ecx, 200h; PoolType
0x14000ed0e  call    cs:__imp_ExAllocatePoolWithTag
0x14000ed15  nop     dword ptr [rax+rax+00h]
0x14000ed1a  mov     rdi, rax
0x14000ed1d  test    rax, rax
0x14000ed20  jz      short loc_14000ED2F
0x14000ed22  mov     r8d, ebp; Size
0x14000ed25  xor     edx, edx; Val
0x14000ed27  mov     rcx, rax; void *
0x14000ed2a  call    memset
0x14000ed2f  mov     [rbx+108h], rdi
0x14000ed36  test    rdi, rdi
0x14000ed39  jz      short loc_14000EDA9
0x14000ed3b  lea     rcx, [rdi+20h]; Event
0x14000ed3f  xor     r8d, r8d; State
0x14000ed42  xor     edx, edx; Type
0x14000ed44  call    cs:__imp_KeInitializeEvent
0x14000ed4b  nop     dword ptr [rax+rax+00h]
0x14000ed50  mov     rax, [rbx+108h]
0x14000ed57  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x14000ed5e  mov     [rax+10h], rcx
0x14000ed62  mov     [rax+18h], rbx
0x14000ed66  mov     qword ptr [rax], 0
0x14000ed6d  xor     eax, eax
0x14000ed6f  mov     rcx, [rbx+108h]
0x14000ed76  mov     [rcx+38h], ax
0x14000ed7a  test    sil, sil
0x14000ed7d  jz      short loc_14000EDB3
0x14000ed7f  mov     rdx, [rbx+108h]
0x14000ed86  lea     r8d, [rax+8]
0x14000ed8a  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x14000ed91  call    cs:__imp_ExAllocateTimer
0x14000ed98  nop     dword ptr [rax+rax+00h]
0x14000ed9d  mov     [rbx+168h], rax
0x14000eda4  test    rax, rax
0x14000eda7  jnz     short loc_14000EDB3
0x14000eda9  mov     rcx, rbx; P
0x14000edac  call    DestroyAggregateSession
0x14000edb1  xor     ebx, ebx
0x14000edb3  mov     rax, rbx
0x14000edb6  add     rsp, 28h
0x14000edba  pop     rdi
0x14000edbb  pop     rsi
0x14000edbc  pop     rbp
0x14000edbd  pop     rbx
0x14000edbe  retn
```
