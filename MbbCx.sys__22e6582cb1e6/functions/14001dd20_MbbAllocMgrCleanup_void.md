# MbbAllocMgrCleanup(void *)

- ea: `0x14001dd20`
- end: `0x14001ddee`
- name: `?MbbAllocMgrCleanup@@YAXPEAX@Z`
- size: `206`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400196ac`
- `0x14001a2a4`
- `0x14001deb0`
- `0x140023db0`

## callees

- `0x14001dd20`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001ddc0`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001ddc0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dd94`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dd94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ddd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ddd1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ddb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ddb1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001dd36`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001dd36`

## pseudocode

```c
void __fastcall MbbAllocMgrCleanup(char *P)
{
  KSPIN_LOCK *v1; // rbp
  _QWORD **v3; // rsi
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax

  v1 = (KSPIN_LOCK *)(P + 128);
  v3 = (_QWORD **)(P + 160);
  P[136] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 16);
  v4 = *v3;
  if ( *v3 != v3 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      if ( *(_QWORD **)(*v4 + 8LL) != v4
        || (v6 = (_QWORD *)v4[1], (_QWORD *)*v6 != v4)
        || (*v6 = v5, v7 = v4 - 2, v5[1] = v6, v8 = *(v4 - 2), *(_QWORD **)(v8 + 8) != v4 - 2)
        || (v9 = (_QWORD *)v7[1], (_QWORD *)*v9 != v7) )
      {
        __fastfail(3u);
      }
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)P, v7);
      v4 = v5;
    }
    while ( v5 != v3 );
  }
  KeReleaseSpinLock(v1, P[136]);
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)P);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14001dd20  push    rbx
0x14001dd22  push    rbp
0x14001dd23  push    rsi
0x14001dd24  push    rdi
0x14001dd25  sub     rsp, 28h
0x14001dd29  lea     rbp, [rcx+80h]
0x14001dd30  mov     rbx, rcx
0x14001dd33  mov     rcx, rbp; SpinLock
0x14001dd36  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001dd3d  nop     dword ptr [rax+rax+00h]
0x14001dd42  lea     rsi, [rbx+0A0h]
0x14001dd49  mov     [rbx+88h], al
0x14001dd4f  mov     rax, [rsi]
0x14001dd52  cmp     rax, rsi
0x14001dd55  jz      short loc_14001DDA8
0x14001dd57  mov     rdi, [rax]
0x14001dd5a  cmp     [rdi+8], rax
0x14001dd5e  jnz     loc_14001DDE7
0x14001dd64  mov     rcx, [rax+8]
0x14001dd68  cmp     [rcx], rax
0x14001dd6b  jnz     short loc_14001DDE7
0x14001dd6d  mov     [rcx], rdi
0x14001dd70  lea     rdx, [rax-10h]; Entry
0x14001dd74  mov     [rdi+8], rcx
0x14001dd78  mov     rcx, [rdx]
0x14001dd7b  cmp     [rcx+8], rdx
0x14001dd7f  jnz     short loc_14001DDE7
0x14001dd81  mov     rax, [rdx+8]
0x14001dd85  cmp     [rax], rdx
0x14001dd88  jnz     short loc_14001DDE7
0x14001dd8a  mov     [rax], rcx
0x14001dd8d  mov     [rcx+8], rax
0x14001dd91  mov     rcx, rbx; Lookaside
0x14001dd94  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001dd9b  nop     dword ptr [rax+rax+00h]
0x14001dda0  mov     rax, rdi
0x14001dda3  cmp     rdi, rsi
0x14001dda6  jnz     short loc_14001DD57
0x14001dda8  mov     dl, [rbx+88h]; NewIrql
0x14001ddae  mov     rcx, rbp; SpinLock
0x14001ddb1  call    cs:__imp_KeReleaseSpinLock
0x14001ddb8  nop     dword ptr [rax+rax+00h]
0x14001ddbd  mov     rcx, rbx; Lookaside
0x14001ddc0  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001ddc7  nop     dword ptr [rax+rax+00h]
0x14001ddcc  xor     edx, edx; Tag
0x14001ddce  mov     rcx, rbx; P
0x14001ddd1  call    cs:__imp_ExFreePoolWithTag
0x14001ddd8  nop     dword ptr [rax+rax+00h]
0x14001dddd  add     rsp, 28h
0x14001dde1  pop     rdi
0x14001dde2  pop     rsi
0x14001dde3  pop     rbp
0x14001dde4  pop     rbx
0x14001dde5  retn
0x14001dde7  mov     ecx, 3
0x14001ddec  int     29h; Win8: RtlFailFast(ecx)
```
