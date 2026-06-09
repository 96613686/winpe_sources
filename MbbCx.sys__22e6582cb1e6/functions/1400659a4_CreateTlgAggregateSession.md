# CreateTlgAggregateSession

- ea: `0x1400659a4`
- end: `0x140065ad4`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400661d4`

## callees

- `0x140048340`
- `0x1400659a4`
- `0x140065adc`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140065a58`
- `ntoskrnl!KeInitializeEvent` at `0x140065a58`
- `ntoskrnl!ExAllocateTimer` at `0x140065aa5`
- `ntoskrnl!ExAllocateTimer` at `0x140065aa5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400659d2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140065a22`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400659d2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140065a22`

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
0x1400659a4  push    rbx
0x1400659a6  push    rbp
0x1400659a7  push    rsi
0x1400659a8  push    rdi
0x1400659a9  sub     rsp, 28h
0x1400659ad  mov     al, cl
0x1400659af  mov     dil, cl
0x1400659b2  neg     al
0x1400659b4  mov     sil, dl
0x1400659b7  mov     ebp, 178h
0x1400659bc  mov     r8d, 47417254h; Tag
0x1400659c2  sbb     ecx, ecx
0x1400659c4  mov     edx, ebp; NumberOfBytes
0x1400659c6  and     ecx, 0FFFFFE01h
0x1400659cc  add     ecx, 200h; PoolType
0x1400659d2  call    cs:__imp_ExAllocatePoolWithTag
0x1400659d9  nop     dword ptr [rax+rax+00h]
0x1400659de  mov     rbx, rax
0x1400659e1  test    rax, rax
0x1400659e4  jz      loc_140065ABD
0x1400659ea  mov     r8d, ebp; Size
0x1400659ed  xor     edx, edx; Val
0x1400659ef  mov     rcx, rax; void *
0x1400659f2  call    memset
0x1400659f7  mov     qword ptr [rbx+110h], 0
0x140065a02  test    sil, sil
0x140065a05  jnz     short loc_140065A10
0x140065a07  test    dil, dil
0x140065a0a  jnz     loc_140065AC7
0x140065a10  mov     ebp, 40h ; '@'
0x140065a15  mov     r8d, 47417254h; Tag
0x140065a1b  mov     edx, ebp; NumberOfBytes
0x140065a1d  mov     ecx, 200h; PoolType
0x140065a22  call    cs:__imp_ExAllocatePoolWithTag
0x140065a29  nop     dword ptr [rax+rax+00h]
0x140065a2e  mov     rdi, rax
0x140065a31  test    rax, rax
0x140065a34  jz      short loc_140065A43
0x140065a36  mov     r8d, ebp; Size
0x140065a39  xor     edx, edx; Val
0x140065a3b  mov     rcx, rax; void *
0x140065a3e  call    memset
0x140065a43  mov     [rbx+108h], rdi
0x140065a4a  test    rdi, rdi
0x140065a4d  jz      short loc_140065ABD
0x140065a4f  lea     rcx, [rdi+20h]; Event
0x140065a53  xor     r8d, r8d; State
0x140065a56  xor     edx, edx; Type
0x140065a58  call    cs:__imp_KeInitializeEvent
0x140065a5f  nop     dword ptr [rax+rax+00h]
0x140065a64  mov     rax, [rbx+108h]
0x140065a6b  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x140065a72  mov     [rax+10h], rcx
0x140065a76  mov     [rax+18h], rbx
0x140065a7a  mov     qword ptr [rax], 0
0x140065a81  xor     eax, eax
0x140065a83  mov     rcx, [rbx+108h]
0x140065a8a  mov     [rcx+38h], ax
0x140065a8e  test    sil, sil
0x140065a91  jz      short loc_140065AC7
0x140065a93  mov     rdx, [rbx+108h]
0x140065a9a  lea     r8d, [rax+8]
0x140065a9e  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x140065aa5  call    cs:__imp_ExAllocateTimer
0x140065aac  nop     dword ptr [rax+rax+00h]
0x140065ab1  mov     [rbx+168h], rax
0x140065ab8  test    rax, rax
0x140065abb  jnz     short loc_140065AC7
0x140065abd  mov     rcx, rbx; P
0x140065ac0  call    DestroyAggregateSession
0x140065ac5  xor     ebx, ebx
0x140065ac7  mov     rax, rbx
0x140065aca  add     rsp, 28h
0x140065ace  pop     rdi
0x140065acf  pop     rsi
0x140065ad0  pop     rbp
0x140065ad1  pop     rbx
0x140065ad2  retn
```
