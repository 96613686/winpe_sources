# RefsReleaseRangeLockIoContext(REFS_IO_CONTEXT *)

- ea: `0x140085ef0`
- end: `0x1400862b1`
- name: `?RefsReleaseRangeLockIoContext@@YAXPEAUREFS_IO_CONTEXT@@@Z`
- size: `961`
- prototype: `void __fastcall(struct REFS_IO_CONTEXT *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1400b6650`
- `0x1400b6ba0`
- `0x1400e9e48`
- `0x14033e290`

## callees

- `0x1400845e0`
- `0x140085ef0`
- `0x140089b40`
- `0x140089bf0`
- `0x1400901a0`
- `0x14009c7a0`
- `0x1400cf214`
- `0x1401f3cec`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1402009a9`
- `ntoskrnl!KeSetEvent` at `0x140200a8e`
- `ntoskrnl!KeSetEvent` at `0x1402009a9`
- `ntoskrnl!KeSetEvent` at `0x140200a8e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086262`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086294`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14020092c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140200a10`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086262`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140086294`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14020092c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140200a10`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140085fc5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400860b3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140086143`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400861ca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140085fc5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400860b3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140086143`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400861ca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008617b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140086202`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14008617b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140086202`

## pseudocode

```c
void __fastcall RefsReleaseRangeLockIoContext(struct REFS_IO_CONTEXT *a1)
{
  bool v1; // zf
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // r9
  __int64 v6; // r8
  __int64 v7; // rax
  int v8; // eax
  char v9; // cl
  KSPIN_LOCK *v10; // r14
  __int64 v11; // rcx
  __int64 v12; // r15
  __int64 v13; // rbp
  _QWORD *v14; // rdx
  KSPIN_LOCK v15; // rbp
  KSPIN_LOCK *v16; // r12
  __int64 v17; // r13
  __int64 v18; // rdx
  unsigned __int8 v19; // r9
  KSPIN_LOCK *v20; // rbp
  __int64 v21; // r15
  __int64 v22; // r14
  _QWORD *v23; // rdx
  KSPIN_LOCK v24; // r15
  KSPIN_LOCK *v25; // r12
  __int64 v26; // r13
  __int64 v27; // rdx
  unsigned __int8 v28; // r9
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // r8
  _QWORD *k; // rcx
  _QWORD *v33; // rdx
  _QWORD *v34; // rcx
  _QWORD *v35; // r8
  _QWORD *j; // rcx
  unsigned __int64 m; // r9
  unsigned __int64 i; // r9
  __int64 v39; // rax
  char v40; // r10
  __int64 v41; // rax
  __int64 v42; // r8
  char v43; // al
  __int64 v44; // r8
  int v45; // eax
  __int64 v46; // rax
  char v47; // r10
  __int64 v48; // rax
  __int64 v49; // r8
  char v50; // al
  __int64 v51; // r8
  int inserted; // eax
  __int128 v53; // [rsp+20h] [rbp-88h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-78h] BYREF
  struct _KLOCK_QUEUE_HANDLE v55; // [rsp+48h] [rbp-60h] BYREF

  v1 = *((_BYTE *)a1 + 836) == 0;
  v2 = (_QWORD *)((char *)a1 + 32);
  v3 = *((_QWORD *)a1 + 102);
  v4 = *((unsigned int *)a1 + 208);
  v6 = *((_QWORD *)a1 + 103);
  v53 = 0;
  v7 = *(_QWORD *)(v3 + 56);
  if ( !v1 )
  {
    v20 = *(KSPIN_LOCK **)(v3 + 64);
    memset(&v55, 0, sizeof(v55));
    if ( !v20[2] )
      goto LABEL_5;
    v21 = v6 >> *(_BYTE *)(v7 + 552) << *(_BYTE *)(v7 + 552);
    v22 = ((v4 + v6 + *(unsigned int *)(v7 + 544)) >> *(_BYTE *)(v7 + 552) << *(_BYTE *)(v7 + 552)) - 1;
    *(_QWORD *)&v53 = v21;
    *((_QWORD *)&v53 + 1) = v22;
    if ( a1 == (struct REFS_IO_CONTEXT *)-32LL || !*((_QWORD *)a1 + 5) )
    {
      KeAcquireInStackQueuedSpinLock(v20, &v55);
      v29 = (_QWORD *)v20[2];
      v30 = 0;
LABEL_28:
      if ( !v29 )
      {
        if ( v20[3] )
          FsLibPrivateCheckWaitingRangeLocks(v20, v20, &v53);
LABEL_31:
        KeReleaseInStackQueuedSpinLock(&v55);
        if ( !v2 )
          goto LABEL_5;
        goto LABEL_43;
      }
      for ( i = v29[1]; ; i &= ~(1LL << v47) )
      {
        v1 = !_BitScanForward64((unsigned __int64 *)&v46, i);
        if ( v1 )
        {
          v30 = v29;
          v29 = (_QWORD *)*v29;
          goto LABEL_28;
        }
        v47 = v46;
        v48 = 2 * v46;
        if ( v29[v48 + 2] == v21 && v29[v48 + 3] == v22 )
          break;
      }
      v49 = v29[1] & ~(1LL << v47);
      v29[1] = v49;
      if ( !v49 && v30 )
      {
        *v30 = *v29;
        *v29 = 0;
        ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v29);
      }
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v20, &v55);
      v23 = (_QWORD *)v20[2];
      *(_QWORD *)(*v2 + 8LL) &= ~v2[1];
      if ( (_QWORD *)*v2 != v23 && !*(_QWORD *)(*v2 + 8LL) )
      {
        v35 = v23;
        for ( j = v23; j; j = (_QWORD *)*j )
        {
          if ( !j[1] && j != v23 )
          {
            *v35 = *j;
            ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, j);
            break;
          }
          v35 = j;
        }
      }
    }
    v24 = v20[3];
    if ( v24 )
    {
      v25 = v20 + 3;
      do
      {
        v26 = *(_QWORD *)(v24 + 40);
        if ( (unsigned __int8)AreRangeLocksOverlapping(&v53, v26)
          && ((v28 = *(_BYTE *)(v24 + 36), (v28 & 2) != 0)
           || v20[3] == v24
           || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v20, v27, v28))
          && ((v28 & 1) == 0
            ? (v50 = FsLibPrivateSearchArrayForRange(v20[2], v26))
            : (v50 = FsLibPrivateCheckForExclusiveRangeLockAccess(v20, v26)),
              v50) )
        {
          v51 = *(_QWORD *)(v24 + 48);
          if ( (*(_BYTE *)(v24 + 36) & 1) != 0 )
            inserted = FsLibPrivateInsertRangeLockExclusive(v20, v26, v51);
          else
            inserted = FsLibPrivateInsertRangeLockShared(v20, v26, v51);
          *(_DWORD *)(v24 + 32) = inserted;
          *v25 = *(_QWORD *)v24;
          if ( v24 == v20[4] )
            v20[4] = (KSPIN_LOCK)v25;
          KeSetEvent((PRKEVENT)(v24 + 8), 0, 0);
        }
        else
        {
          v25 = (KSPIN_LOCK *)v24;
        }
        v24 = *v25;
      }
      while ( *v25 );
    }
    goto LABEL_31;
  }
  v8 = *(_DWORD *)(v7 + 552);
  v9 = 14;
  v10 = *(KSPIN_LOCK **)(v3 + 64);
  LockHandle.LockQueue = 0;
  if ( v8 == 12 )
    v9 = 12;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  if ( v10[1] )
  {
    v11 = 1 << v9;
    v12 = v6 & -v11;
    v13 = (-v11 & (v4 + v11 + v6 - 1)) - 1;
    *(_QWORD *)&v53 = v12;
    *((_QWORD *)&v53 + 1) = v13;
    if ( v2 && v2[1] )
    {
      KeAcquireInStackQueuedSpinLock(v10, &LockHandle);
      v14 = (_QWORD *)v10[1];
      *(_QWORD *)(*v2 + 8LL) &= ~v2[1];
      if ( (_QWORD *)*v2 != v14 && !*(_QWORD *)(*v2 + 8LL) )
      {
        v31 = v14;
        for ( k = v14; k; k = (_QWORD *)*k )
        {
          if ( !k[1] && k != v14 )
          {
            *v31 = *k;
            ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, k);
            break;
          }
          v31 = k;
        }
      }
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v10, &LockHandle);
      v33 = (_QWORD *)v10[1];
      v34 = 0;
LABEL_39:
      if ( !v33 )
      {
        if ( v10[3] )
          FsLibPrivateCheckWaitingRangeLocks(v10, v10, &v53);
LABEL_42:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( !v2 )
          goto LABEL_5;
LABEL_43:
        v2[1] = 0;
        goto LABEL_5;
      }
      for ( m = v33[1]; ; m &= ~(1LL << v40) )
      {
        v1 = !_BitScanForward64((unsigned __int64 *)&v39, m);
        if ( v1 )
        {
          v34 = v33;
          v33 = (_QWORD *)*v33;
          goto LABEL_39;
        }
        v40 = v39;
        v41 = 2 * v39;
        if ( v33[v41 + 2] == v12 && v33[v41 + 3] == v13 )
          break;
      }
      v42 = v33[1] & ~(1LL << v40);
      v33[1] = v42;
      if ( !v42 && v34 )
      {
        *v34 = *v33;
        *v33 = 0;
        ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v33);
      }
    }
    v15 = v10[3];
    if ( v15 )
    {
      v16 = v10 + 3;
      do
      {
        v17 = *(_QWORD *)(v15 + 40);
        if ( (unsigned __int8)AreRangeLocksOverlapping(&v53, v17)
          && ((v19 = *(_BYTE *)(v15 + 36), (v19 & 2) != 0)
           || v10[3] == v15
           || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v10, v18, v19))
          && ((v19 & 1) == 0
            ? (v43 = FsLibPrivateSearchArrayForRange(v10[2], v17))
            : (v43 = FsLibPrivateCheckForExclusiveRangeLockAccess(v10, v17)),
              v43) )
        {
          v44 = *(_QWORD *)(v15 + 48);
          if ( (*(_BYTE *)(v15 + 36) & 1) != 0 )
            v45 = FsLibPrivateInsertRangeLockExclusive(v10, v17, v44);
          else
            v45 = FsLibPrivateInsertRangeLockShared(v10, v17, v44);
          *(_DWORD *)(v15 + 32) = v45;
          *v16 = *(_QWORD *)v15;
          if ( v15 == v10[4] )
            v10[4] = (KSPIN_LOCK)v16;
          KeSetEvent((PRKEVENT)(v15 + 8), 0, 0);
        }
        else
        {
          v16 = (KSPIN_LOCK *)v15;
        }
        v15 = *v16;
      }
      while ( *v16 );
    }
    goto LABEL_42;
  }
LABEL_5:
  *((_QWORD *)a1 + 102) = 0;
}

```

## disassembly

```asm
0x140085ef0  push    rbx
0x140085ef2  push    rbp
0x140085ef3  push    rsi
0x140085ef4  push    rdi
0x140085ef5  push    r12
0x140085ef7  push    r13
0x140085ef9  push    r14
0x140085efb  push    r15
0x140085efd  sub     rsp, 68h
0x140085f01  cmp     byte ptr [rcx+344h], 0
0x140085f08  lea     rdi, [rcx+20h]
0x140085f0c  mov     rdx, [rcx+330h]
0x140085f13  xorps   xmm0, xmm0
0x140085f16  mov     r9d, [rcx+340h]
0x140085f1d  mov     rbx, rcx
0x140085f20  mov     r8, [rcx+338h]
0x140085f27  movups  [rsp+0A8h+var_88], xmm0
0x140085f2c  mov     rax, [rdx+38h]
0x140085f30  jnz     loc_14008604D
0x140085f36  mov     eax, [rax+228h]
0x140085f3c  mov     ecx, 0Eh
0x140085f41  mov     r14, [rdx+40h]
0x140085f45  cmp     eax, 0Ch
0x140085f48  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140085f4d  cmovz   cx, ax
0x140085f51  xor     eax, eax
0x140085f53  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140085f58  cmp     [r14+8], rax
0x140085f5c  jnz     short loc_140085F79
0x140085f5e  xor     esi, esi
0x140085f60  mov     [rbx+330h], rsi
0x140085f67  add     rsp, 68h
0x140085f6b  pop     r15
0x140085f6d  pop     r14
0x140085f6f  pop     r13
0x140085f71  pop     r12
0x140085f73  pop     rdi
0x140085f74  pop     rsi
0x140085f75  pop     rbp
0x140085f76  pop     rbx
0x140085f77  retn
0x140085f79  mov     eax, 1
0x140085f7e  lea     rbp, [r8-1]
0x140085f82  shl     eax, cl
0x140085f84  movsxd  rcx, eax
0x140085f87  add     rbp, rcx
0x140085f8a  mov     rdx, rcx
0x140085f8d  neg     rdx
0x140085f90  add     rbp, r9
0x140085f93  and     rbp, rdx
0x140085f96  mov     r15, rdx
0x140085f99  and     r15, r8
0x140085f9c  dec     rbp
0x140085f9f  mov     qword ptr [rsp+0A8h+var_88], r15
0x140085fa4  mov     qword ptr [rsp+0A8h+var_88+8], rbp
0x140085fa9  test    rdi, rdi
0x140085fac  jz      loc_1400861C2
0x140085fb2  cmp     qword ptr [rdi+8], 0
0x140085fb7  jz      loc_1400861C2
0x140085fbd  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x140085fc2  mov     rcx, r14; SpinLock
0x140085fc5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140085fcc  nop     dword ptr [rax+rax+00h]
0x140085fd1  mov     rax, [rdi+8]
0x140085fd5  mov     rdx, [r14+8]
0x140085fd9  not     rax
0x140085fdc  mov     rcx, [rdi]
0x140085fdf  and     [rcx+8], rax
0x140085fe3  mov     rax, [rdi]
0x140085fe6  cmp     rax, rdx
0x140085fe9  jnz     loc_140086195
0x140085fef  xor     esi, esi
0x140085ff1  mov     rbp, [r14+18h]
0x140085ff5  test    rbp, rbp
0x140085ff8  jz      loc_1400861FD
0x140085ffe  lea     r12, [r14+18h]
0x140086002  mov     r13, [rbp+28h]
0x140086006  lea     rcx, [rsp+0A8h+var_88]
0x14008600b  mov     rdx, r13
0x14008600e  call    AreRangeLocksOverlapping
0x140086013  test    al, al
0x140086015  jz      loc_1402009B7
0x14008601b  movzx   r9d, byte ptr [rbp+24h]
0x140086020  test    r9b, 2
0x140086024  jnz     loc_14020094F
0x14008602a  cmp     [r14+18h], rbp
0x14008602e  jz      loc_14020094F
0x140086034  movzx   r8d, r9b
0x140086038  mov     rcx, r14
0x14008603b  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140086040  test    al, al
0x140086042  jnz     loc_14020094F
0x140086048  jmp     loc_1402009B7
0x14008604d  mov     rbp, [rdx+40h]
0x140086051  xor     ecx, ecx
0x140086053  movups  xmmword ptr [rsp+0A8h+var_60.LockQueue.Next], xmm0
0x140086058  mov     qword ptr [rsp+0A8h+var_60.OldIrql], rcx
0x14008605d  cmp     [rbp+10h], rcx
0x140086061  jz      loc_140085F5E
0x140086067  movsx   ecx, byte ptr [rax+228h]
0x14008606e  mov     r15, r8
0x140086071  mov     r14d, [rax+220h]
0x140086078  add     r14, r8
0x14008607b  sar     r15, cl
0x14008607e  add     r14, r9
0x140086081  shl     r15, cl
0x140086084  sar     r14, cl
0x140086087  shl     r14, cl
0x14008608a  dec     r14
0x14008608d  mov     qword ptr [rsp+0A8h+var_88], r15
0x140086092  mov     qword ptr [rsp+0A8h+var_88+8], r14
0x140086097  test    rdi, rdi
0x14008609a  jz      loc_14008613B
0x1400860a0  cmp     qword ptr [rdi+8], 0
0x1400860a5  jz      loc_14008613B
0x1400860ab  lea     rdx, [rsp+0A8h+var_60]; LockHandle
0x1400860b0  mov     rcx, rbp; SpinLock
0x1400860b3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400860ba  nop     dword ptr [rax+rax+00h]
0x1400860bf  mov     rax, [rdi+8]
0x1400860c3  mov     rdx, [rbp+10h]
0x1400860c7  not     rax
0x1400860ca  mov     rcx, [rdi]
0x1400860cd  and     [rcx+8], rax
0x1400860d1  mov     rax, [rdi]
0x1400860d4  cmp     rax, rdx
0x1400860d7  jnz     loc_140086220
0x1400860dd  xor     esi, esi
0x1400860df  mov     r15, [rbp+18h]
0x1400860e3  test    r15, r15
0x1400860e6  jz      loc_140086176
0x1400860ec  lea     r12, [rbp+18h]
0x1400860f0  mov     r13, [r15+28h]
0x1400860f4  lea     rcx, [rsp+0A8h+var_88]
0x1400860f9  mov     rdx, r13
0x1400860fc  call    AreRangeLocksOverlapping
0x140086101  test    al, al
0x140086103  jz      loc_140200A9C
0x140086109  movzx   r9d, byte ptr [r15+24h]
0x14008610e  test    r9b, 2
0x140086112  jnz     loc_140200A33
0x140086118  cmp     [rbp+18h], r15
0x14008611c  jz      loc_140200A33
0x140086122  movzx   r8d, r9b
0x140086126  mov     rcx, rbp
0x140086129  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x14008612e  test    al, al
0x140086130  jnz     loc_140200A33
0x140086136  jmp     loc_140200A9C
0x14008613b  lea     rdx, [rsp+0A8h+var_60]; LockHandle
0x140086140  mov     rcx, rbp; SpinLock
0x140086143  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14008614a  nop     dword ptr [rax+rax+00h]
0x14008614f  mov     rdx, [rbp+10h]; Entry
0x140086153  xor     esi, esi
0x140086155  mov     ecx, esi
0x140086157  test    rdx, rdx
0x14008615a  jnz     loc_1400862A5
0x140086160  cmp     [rbp+18h], rsi
0x140086164  jz      short loc_140086176
0x140086166  lea     r8, [rsp+0A8h+var_88]
0x14008616b  mov     rdx, rbp
0x14008616e  mov     rcx, rbp
0x140086171  call    FsLibPrivateCheckWaitingRangeLocks
0x140086176  lea     rcx, [rsp+0A8h+var_60]; LockHandle
0x14008617b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140086182  nop     dword ptr [rax+rax+00h]
0x140086187  test    rdi, rdi
0x14008618a  jnz     loc_140086217
0x140086190  jmp     loc_140085F60
0x140086195  cmp     qword ptr [rax+8], 0
0x14008619a  jnz     loc_140085FEF
0x1400861a0  mov     r8, rdx
0x1400861a3  mov     rcx, rdx
0x1400861a6  test    rcx, rcx
0x1400861a9  jz      loc_140085FEF
0x1400861af  cmp     qword ptr [rcx+8], 0
0x1400861b4  jz      loc_140086249
0x1400861ba  mov     r8, rcx
0x1400861bd  mov     rcx, [rcx]
0x1400861c0  jmp     short loc_1400861A6
0x1400861c2  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x1400861c7  mov     rcx, r14; SpinLock
0x1400861ca  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400861d1  nop     dword ptr [rax+rax+00h]
0x1400861d6  mov     rdx, [r14+8]; Entry
0x1400861da  xor     esi, esi
0x1400861dc  mov     ecx, esi
0x1400861de  test    rdx, rdx
0x1400861e1  jnz     loc_140086273
0x1400861e7  cmp     [r14+18h], rsi
0x1400861eb  jz      short loc_1400861FD
0x1400861ed  lea     r8, [rsp+0A8h+var_88]
0x1400861f2  mov     rdx, r14
0x1400861f5  mov     rcx, r14
0x1400861f8  call    FsLibPrivateCheckWaitingRangeLocks
0x1400861fd  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140086202  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140086209  nop     dword ptr [rax+rax+00h]
0x14008620e  test    rdi, rdi
0x140086211  jz      loc_140085F60
0x140086217  mov     [rdi+8], rsi
0x14008621b  jmp     loc_140085F60
0x140086220  cmp     qword ptr [rax+8], 0
0x140086225  jnz     loc_1400860DD
0x14008622b  mov     r8, rdx
0x14008622e  mov     rcx, rdx
0x140086231  test    rcx, rcx
0x140086234  jz      loc_1400860DD
0x14008623a  cmp     qword ptr [rcx+8], 0
0x14008623f  jz      short loc_14008627F
0x140086241  mov     r8, rcx
0x140086244  mov     rcx, [rcx]
0x140086247  jmp     short loc_140086231
0x140086249  cmp     rcx, rdx
0x14008624c  jz      loc_1400861BA
0x140086252  mov     rax, [rcx]
0x140086255  mov     rdx, rcx; Entry
0x140086258  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x14008625f  mov     [r8], rax
0x140086262  call    cs:__imp_ExFreeToNPagedLookasideList
0x140086269  nop     dword ptr [rax+rax+00h]
0x14008626e  jmp     loc_140085FEF
0x140086273  mov     r8, [rdx+8]
0x140086277  mov     r9, r8
0x14008627a  jmp     loc_1402008E8
0x14008627f  cmp     rcx, rdx
0x140086282  jz      short loc_140086241
0x140086284  mov     rax, [rcx]
0x140086287  mov     rdx, rcx; Entry
0x14008628a  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140086291  mov     [r8], rax
0x140086294  call    cs:__imp_ExFreeToNPagedLookasideList
0x14008629b  nop     dword ptr [rax+rax+00h]
0x1400862a0  jmp     loc_1400860DD
0x1400862a5  mov     r8, [rdx+8]
0x1400862a9  mov     r9, r8
0x1400862ac  jmp     loc_1402009CC
0x1402008e8  bsf     rax, r9
0x1402008ec  jz      short loc_140200944
0x1402008ee  mov     r10d, eax
0x1402008f1  add     rax, rax
0x1402008f4  cmp     [rdx+rax*8+10h], r15
0x1402008f9  jnz     short loc_14020093E
0x1402008fb  cmp     [rdx+rax*8+18h], rbp
0x140200900  jnz     short loc_14020093E
0x140200902  btr     r8, r10
0x140200906  mov     [rdx+8], r8
0x14020090a  test    r8, r8
0x14020090d  jnz     loc_140085FF1
0x140200913  test    rcx, rcx
0x140200916  jz      loc_140085FF1
0x14020091c  mov     rax, [rdx]
0x14020091f  mov     [rcx], rax
0x140200922  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140200929  mov     [rdx], rsi
0x14020092c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140200933  nop     dword ptr [rax+rax+00h]
0x140200938  nop
0x140200939  jmp     loc_140085FF1
0x14020093e  btr     r9, r10
0x140200942  jmp     short loc_1402008E8
0x140200944  mov     rcx, rdx
0x140200947  mov     rdx, [rdx]
0x14020094a  jmp     loc_1400861DE
0x14020094f  mov     rdx, r13
0x140200952  test    r9b, 1
0x140200956  jz      short loc_140200962
0x140200958  mov     rcx, r14
0x14020095b  call    FsLibPrivateCheckForExclusiveRangeLockAccess
0x140200960  jmp     short loc_14020096B
0x140200962  mov     rcx, [r14+10h]
0x140200966  call    FsLibPrivateSearchArrayForRange
0x14020096b  test    al, al
0x14020096d  jz      short loc_1402009B7
0x14020096f  test    byte ptr [rbp+24h], 1
0x140200973  mov     rdx, r13
0x140200976  mov     r8, [rbp+30h]
0x14020097a  mov     rcx, r14
0x14020097d  jz      short loc_140200986
0x14020097f  call    FsLibPrivateInsertRangeLockExclusive
0x140200984  jmp     short loc_14020098B
0x140200986  call    FsLibPrivateInsertRangeLockShared
0x14020098b  mov     [rbp+20h], eax
0x14020098e  mov     rax, [rbp+0]
0x140200992  mov     [r12], rax
0x140200996  cmp     rbp, [r14+20h]
0x14020099a  jnz     short loc_1402009A0
0x14020099c  mov     [r14+20h], r12
0x1402009a0  lea     rcx, [rbp+8]; Event
0x1402009a4  xor     r8d, r8d; Wait
0x1402009a7  xor     edx, edx; Increment
0x1402009a9  call    cs:__imp_KeSetEvent
0x1402009b0  nop     dword ptr [rax+rax+00h]
0x1402009b5  jmp     short loc_1402009BA
0x1402009b7  mov     r12, rbp
0x1402009ba  mov     rbp, [r12]
0x1402009be  test    rbp, rbp
0x1402009c1  jnz     loc_140086002
0x1402009c7  jmp     loc_1400861FD
  ... truncated ...
```
