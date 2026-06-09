# TxfCreateTxfFo

- ea: `0x140245e30`
- end: `0x14024604b`
- name: `TxfCreateTxfFo`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14019dcc8`

## callees

- `0x140059740`
- `0x140245e30`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402b8006`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1402b8006`
- `ntoskrnl!ObfReferenceObject` at `0x140245ee0`
- `ntoskrnl!ObfReferenceObject` at `0x140245ee0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b801d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b801d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245e63`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245f53`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245e63`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140245f53`
- `ntoskrnl!KeInitializeEvent` at `0x140245ecd`
- `ntoskrnl!KeInitializeEvent` at `0x140245ecd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7fee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7fee`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140245e9b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140245e9b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245f14`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245fe6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245f14`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140245fe6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140245fcf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140246004`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7fc8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140245fcf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140246004`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7fc8`

## pseudocode

```c
_DWORD *__fastcall TxfCreateTxfFo(__int64 a1, __int16 a2, __int64 a3, int a4)
{
  __int64 v7; // rdi
  _DWORD *v8; // rbx
  struct _KEVENT *PoolWithTag; // rax
  PVOID v10; // rax

  v7 = *(_QWORD *)(a1 + 400);
  v8 = ExAllocateFromLookasideListEx(&TxfFoLookasideList);
  memset(v8, 0, 0x48u);
  *v8 = 4720407;
  PoolWithTag = (struct _KEVENT *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x38u, 0x6D667854u);
  *((_QWORD *)v8 + 5) = PoolWithTag;
  PoolWithTag->Header.LockNV = 1;
  PoolWithTag->Header.WaitListHead.Flink = 0;
  LODWORD(PoolWithTag->Header.WaitListHead.Blink) = 0;
  KeInitializeEvent(PoolWithTag + 1, SynchronizationEvent, 0);
  ObfReferenceObject(*(PVOID *)(v7 + 232));
  *((_QWORD *)v8 + 7) = *(_QWORD *)(v7 + 232);
  *((_QWORD *)v8 + 8) = *(_QWORD *)(v7 + 304);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 136LL), 1u);
  _InterlockedAdd((volatile signed __int32 *)(a3 + 4), 1u);
  *((_QWORD *)v8 + 1) = a3;
  if ( a2 == -1 )
  {
    if ( !a4 )
      v8[1] |= 4u;
  }
  else
  {
    ++v8[9];
    ++*(_DWORD *)(*(_QWORD *)(a3 + 16) + 32LL);
    if ( !*(_QWORD *)(a3 + 24) )
    {
      v10 = ExAllocateFromLookasideListEx(&NtfsScbNonpagedLookasideList);
      *(_QWORD *)(a3 + 24) = v10;
      memset(v10, 0, 0x48u);
      **(_WORD **)(a3 + 24) = 1799;
      *(_WORD *)(*(_QWORD *)(a3 + 24) + 2LL) = 72;
      *(_QWORD *)(*(_QWORD *)(a3 + 24) + 40LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 40LL)
                                                           + 16LL);
      *(_DWORD *)(*(_QWORD *)(a3 + 24) + 68LL) = 0;
      *(_QWORD *)(*(_QWORD *)(a3 + 24) + 56LL) = a3;
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a3 + 16) + 64LL) + 136LL));
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v7 + 24) + 80LL), 1u);
  if ( !*(_QWORD *)(v7 + 240) && (*(_DWORD *)(v7 + 12) & 1) == 0 )
  {
    v8[1] |= 0x20u;
    ++*(_DWORD *)(v7 + 4);
    *(_DWORD *)(v7 + 12) = *(_DWORD *)(v7 + 12) & 1 | ((*(_DWORD *)(v7 + 12) & 0xFFFFFFFE) + 2);
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v7 + 24) + 80LL));
  return v8;
}

```

## disassembly

```asm
0x140245e30  mov     [rsp+arg_8], rbx
0x140245e35  mov     [rsp+arg_10], r8
0x140245e3a  push    rsi
0x140245e3b  push    rdi
0x140245e3c  push    r12
0x140245e3e  push    r14
0x140245e40  push    r15
0x140245e42  sub     rsp, 30h
0x140245e46  mov     r14d, r9d
0x140245e49  mov     rsi, r8
0x140245e4c  movzx   r15d, dx
0x140245e50  mov     [rsp+58h+var_38], 0
0x140245e55  mov     rdi, [rcx+190h]
0x140245e5c  lea     rcx, TxfFoLookasideList; Lookaside
0x140245e63  call    cs:__imp_ExAllocateFromLookasideListEx
0x140245e6a  nop     dword ptr [rax+rax+00h]
0x140245e6f  mov     rbx, rax
0x140245e72  mov     [rsp+58h+arg_0], rax
0x140245e77  xor     edx, edx; Val
0x140245e79  lea     r8d, [rdx+48h]; Size
0x140245e7d  mov     rcx, rax; void *
0x140245e80  call    memset
0x140245e85  mov     dword ptr [rbx], 480717h
0x140245e8b  mov     edx, 38h ; '8'; NumberOfBytes
0x140245e90  mov     ecx, 210h; PoolType
0x140245e95  mov     r8d, 6D667854h; Tag
0x140245e9b  call    cs:__imp_ExAllocatePoolWithTag
0x140245ea2  nop     dword ptr [rax+rax+00h]
0x140245ea7  mov     [rbx+28h], rax
0x140245eab  mov     r12d, 1
0x140245eb1  mov     [rax], r12d
0x140245eb4  mov     qword ptr [rax+8], 0
0x140245ebc  mov     dword ptr [rax+10h], 0
0x140245ec3  lea     rcx, [rax+18h]; Event
0x140245ec7  xor     r8d, r8d; State
0x140245eca  mov     edx, r12d; Type
0x140245ecd  call    cs:__imp_KeInitializeEvent
0x140245ed4  nop     dword ptr [rax+rax+00h]
0x140245ed9  mov     rcx, [rdi+0E8h]; Object
0x140245ee0  call    cs:__imp_ObfReferenceObject
0x140245ee7  nop     dword ptr [rax+rax+00h]
0x140245eec  mov     rax, [rdi+0E8h]
0x140245ef3  mov     [rbx+38h], rax
0x140245ef7  mov     rax, [rdi+130h]
0x140245efe  mov     [rbx+40h], rax
0x140245f02  mov     rax, [rsi+10h]
0x140245f06  mov     rcx, [rax+40h]
0x140245f0a  mov     dl, r12b; Wait
0x140245f0d  mov     rcx, [rcx+88h]; Resource
0x140245f14  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140245f1b  nop     dword ptr [rax+rax+00h]
0x140245f20  mov     [rsp+58h+var_38], r12b
0x140245f25  lock add [rsi+4], r12d
0x140245f2a  mov     [rbx+8], rsi
0x140245f2e  mov     eax, 0FFFFh
0x140245f33  cmp     r15w, ax
0x140245f37  jz      short loc_140245FB7
0x140245f39  add     [rbx+24h], r12d
0x140245f3d  mov     rax, [rsi+10h]
0x140245f41  add     [rax+20h], r12d
0x140245f45  cmp     qword ptr [rsi+18h], 0
0x140245f4a  jnz     short loc_140245FC0
0x140245f4c  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x140245f53  call    cs:__imp_ExAllocateFromLookasideListEx
0x140245f5a  nop     dword ptr [rax+rax+00h]
0x140245f5f  mov     [rsi+18h], rax
0x140245f63  lea     r14d, [r12+47h]
0x140245f68  mov     r8d, r14d; Size
0x140245f6b  xor     edx, edx; Val
0x140245f6d  mov     rcx, rax; void *
0x140245f70  call    memset
0x140245f75  mov     rax, [rsi+18h]
0x140245f79  mov     ecx, 707h
0x140245f7e  mov     [rax], cx
0x140245f81  mov     rax, [rsi+18h]
0x140245f85  mov     [rax+2], r14w
0x140245f8a  mov     rax, [rsi+10h]
0x140245f8e  mov     rcx, [rax+40h]
0x140245f92  mov     rax, [rcx+28h]
0x140245f96  mov     rcx, [rsi+18h]
0x140245f9a  mov     rax, [rax+10h]
0x140245f9e  mov     [rcx+28h], rax
0x140245fa2  mov     rax, [rsi+18h]
0x140245fa6  mov     dword ptr [rax+44h], 0
0x140245fad  mov     rax, [rsi+18h]
0x140245fb1  mov     [rax+38h], rsi
0x140245fb5  jmp     short loc_140245FC0
0x140245fb7  test    r14d, r14d
0x140245fba  jnz     short loc_140245FC0
0x140245fbc  or      dword ptr [rbx+4], 4
0x140245fc0  mov     rax, [rsi+10h]
0x140245fc4  mov     rcx, [rax+40h]
0x140245fc8  mov     rcx, [rcx+88h]; Resource
0x140245fcf  call    cs:__imp_ExReleaseResourceLite
0x140245fd6  nop     dword ptr [rax+rax+00h]
0x140245fdb  mov     rcx, [rdi+18h]
0x140245fdf  add     rcx, 50h ; 'P'; Resource
0x140245fe3  mov     dl, r12b; Wait
0x140245fe6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140245fed  nop     dword ptr [rax+rax+00h]
0x140245ff2  cmp     qword ptr [rdi+0F0h], 0
0x140245ffa  jz      short loc_140246026
0x140245ffc  mov     rcx, [rdi+18h]
0x140246000  add     rcx, 50h ; 'P'; Resource
0x140246004  call    cs:__imp_ExReleaseResourceLite
0x14024600b  nop     dword ptr [rax+rax+00h]
0x140246010  mov     rax, rbx
0x140246013  mov     rbx, [rsp+58h+arg_8]
0x140246018  add     rsp, 30h
0x14024601c  pop     r15
0x14024601e  pop     r14
0x140246020  pop     r12
0x140246022  pop     rdi
0x140246023  pop     rsi
0x140246024  retn
0x140246026  mov     eax, [rdi+0Ch]
0x140246029  test    r12b, al
0x14024602c  jnz     short loc_140245FFC
0x14024602e  or      dword ptr [rbx+4], 20h
0x140246032  add     [rdi+4], r12d
0x140246036  mov     eax, [rdi+0Ch]
0x140246039  mov     ecx, eax
0x14024603b  and     ecx, 0FFFFFFFEh
0x14024603e  add     ecx, 2
0x140246041  and     eax, r12d
0x140246044  or      ecx, eax
0x140246046  mov     [rdi+0Ch], ecx
0x140246049  jmp     short loc_140245FFC
0x1402b7f6d  push    rbx
0x1402b7f6f  push    rbp
0x1402b7f70  push    rdi
0x1402b7f71  sub     rsp, 20h
0x1402b7f75  mov     rbp, rdx
0x1402b7f78  movzx   edi, cl
0x1402b7f7b  mov     rbx, [rbp+60h]
0x1402b7f7f  test    cl, cl
0x1402b7f81  jz      short loc_1402B7FAF
0x1402b7f83  mov     al, cs:NtfsStatusDebugFlags
0x1402b7f89  test    rbx, rbx
0x1402b7f8c  jz      short loc_1402B7FAF
0x1402b7f8e  cmp     qword ptr [rbx+8], 0
0x1402b7f93  jz      short loc_1402B7FAF
0x1402b7f95  mov     rdx, [rbp+70h]
0x1402b7f99  lock dec dword ptr [rdx+4]
0x1402b7f9d  cmp     dword ptr [rbx+24h], 0
0x1402b7fa1  jz      short loc_1402B7FAF
0x1402b7fa3  mov     rax, [rdx+10h]
0x1402b7fa7  mov     ecx, [rax+20h]
0x1402b7faa  dec     ecx
0x1402b7fac  mov     [rax+20h], ecx
0x1402b7faf  cmp     byte ptr [rbp+20h], 0
0x1402b7fb3  jz      short loc_1402B7FD5
0x1402b7fb5  mov     rax, [rbp+70h]
0x1402b7fb9  mov     rcx, [rax+10h]
0x1402b7fbd  mov     rcx, [rcx+40h]
0x1402b7fc1  mov     rcx, [rcx+88h]; Resource
0x1402b7fc8  call    cs:__imp_ExReleaseResourceLite
0x1402b7fcf  nop     dword ptr [rax+rax+00h]
0x1402b7fd4  nop
0x1402b7fd5  mov     eax, edi
0x1402b7fd7  test    dil, dil
0x1402b7fda  jz      short loc_1402B802A
0x1402b7fdc  test    rbx, rbx
0x1402b7fdf  jz      short loc_1402B802A
0x1402b7fe1  cmp     qword ptr [rbx+28h], 0
0x1402b7fe6  jz      short loc_1402B7FFB
0x1402b7fe8  xor     edx, edx; Tag
0x1402b7fea  mov     rcx, [rbx+28h]; P
0x1402b7fee  call    cs:__imp_ExFreePoolWithTag
0x1402b7ff5  nop     dword ptr [rax+rax+00h]
0x1402b7ffa  nop
0x1402b7ffb  cmp     qword ptr [rbx+38h], 0
0x1402b8000  jz      short loc_1402B8013
0x1402b8002  mov     rcx, [rbx+38h]; Object
0x1402b8006  call    cs:__imp_ObDereferenceObjectDeferDelete
0x1402b800d  nop     dword ptr [rax+rax+00h]
0x1402b8012  nop
0x1402b8013  mov     rdx, rbx; Entry
0x1402b8016  lea     rcx, TxfFoLookasideList; Lookaside
0x1402b801d  call    cs:__imp_ExFreeToLookasideListEx
0x1402b8024  nop     dword ptr [rax+rax+00h]
0x1402b8029  nop
0x1402b802a  add     rsp, 20h
0x1402b802e  pop     rdi
0x1402b802f  pop     rbp
0x1402b8030  pop     rbx
0x1402b8031  retn
```
