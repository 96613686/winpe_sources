# CreateTlgAggregateSession

- ea: `0x1400466bc`
- end: `0x1400467ec`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140046ef4`

## callees

- `0x14000be80`
- `0x1400466bc`
- `0x1400467f4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400466ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004673a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400466ea`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004673a`
- `ntoskrnl!KeInitializeEvent` at `0x140046770`
- `ntoskrnl!KeInitializeEvent` at `0x140046770`
- `ntoskrnl!ExAllocateTimer` at `0x1400467bd`
- `ntoskrnl!ExAllocateTimer` at `0x1400467bd`

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
0x1400466bc  push    rbx
0x1400466be  push    rbp
0x1400466bf  push    rsi
0x1400466c0  push    rdi
0x1400466c1  sub     rsp, 28h
0x1400466c5  mov     al, cl
0x1400466c7  mov     dil, cl
0x1400466ca  neg     al
0x1400466cc  mov     sil, dl
0x1400466cf  mov     ebp, 178h
0x1400466d4  mov     r8d, 47417254h; Tag
0x1400466da  sbb     ecx, ecx
0x1400466dc  mov     edx, ebp; NumberOfBytes
0x1400466de  and     ecx, 0FFFFFE01h
0x1400466e4  add     ecx, 200h; PoolType
0x1400466ea  call    cs:__imp_ExAllocatePoolWithTag
0x1400466f1  nop     dword ptr [rax+rax+00h]
0x1400466f6  mov     rbx, rax
0x1400466f9  test    rax, rax
0x1400466fc  jz      loc_1400467D5
0x140046702  mov     r8d, ebp; Size
0x140046705  xor     edx, edx; Val
0x140046707  mov     rcx, rax; void *
0x14004670a  call    memset
0x14004670f  mov     qword ptr [rbx+110h], 0
0x14004671a  test    sil, sil
0x14004671d  jnz     short loc_140046728
0x14004671f  test    dil, dil
0x140046722  jnz     loc_1400467DF
0x140046728  mov     ebp, 40h ; '@'
0x14004672d  mov     r8d, 47417254h; Tag
0x140046733  mov     edx, ebp; NumberOfBytes
0x140046735  mov     ecx, 200h; PoolType
0x14004673a  call    cs:__imp_ExAllocatePoolWithTag
0x140046741  nop     dword ptr [rax+rax+00h]
0x140046746  mov     rdi, rax
0x140046749  test    rax, rax
0x14004674c  jz      short loc_14004675B
0x14004674e  mov     r8d, ebp; Size
0x140046751  xor     edx, edx; Val
0x140046753  mov     rcx, rax; void *
0x140046756  call    memset
0x14004675b  mov     [rbx+108h], rdi
0x140046762  test    rdi, rdi
0x140046765  jz      short loc_1400467D5
0x140046767  lea     rcx, [rdi+20h]; Event
0x14004676b  xor     r8d, r8d; State
0x14004676e  xor     edx, edx; Type
0x140046770  call    cs:__imp_KeInitializeEvent
0x140046777  nop     dword ptr [rax+rax+00h]
0x14004677c  mov     rax, [rbx+108h]
0x140046783  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x14004678a  mov     [rax+10h], rcx
0x14004678e  mov     [rax+18h], rbx
0x140046792  mov     qword ptr [rax], 0
0x140046799  xor     eax, eax
0x14004679b  mov     rcx, [rbx+108h]
0x1400467a2  mov     [rcx+38h], ax
0x1400467a6  test    sil, sil
0x1400467a9  jz      short loc_1400467DF
0x1400467ab  mov     rdx, [rbx+108h]
0x1400467b2  lea     r8d, [rax+8]
0x1400467b6  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x1400467bd  call    cs:__imp_ExAllocateTimer
0x1400467c4  nop     dword ptr [rax+rax+00h]
0x1400467c9  mov     [rbx+168h], rax
0x1400467d0  test    rax, rax
0x1400467d3  jnz     short loc_1400467DF
0x1400467d5  mov     rcx, rbx; P
0x1400467d8  call    DestroyAggregateSession
0x1400467dd  xor     ebx, ebx
0x1400467df  mov     rax, rbx
0x1400467e2  add     rsp, 28h
0x1400467e6  pop     rdi
0x1400467e7  pop     rsi
0x1400467e8  pop     rbp
0x1400467e9  pop     rbx
0x1400467ea  retn
```
