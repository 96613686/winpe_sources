# RefsAcquireRangeLock(_IRP_CONTEXT *,_SCB_NONPAGED *,__int64,__int64,uchar,_RANGE_LOCK_STATE *)

- ea: `0x140076060`
- end: `0x1400764ce`
- name: `?RefsAcquireRangeLock@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB_NONPAGED@@_J2EPEAU_RANGE_LOCK_STATE@@@Z`
- size: `1134`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _SCB_NONPAGED *, __int64, __int64, char, struct _RANGE_LOCK_STATE *)`
- caller_count: `14`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x1400867d0`
- `0x1400ba4d0`
- `0x1400ea220`
- `0x1400eaac8`
- `0x1400ebf08`
- `0x1400ec8a4`
- `0x1400ee708`
- `0x1400f0948`
- `0x1400f192c`
- `0x140291a00`
- `0x140295fb0`
- `0x14029ddd4`
- `0x1402a2e00`
- `0x1402b2c70`

## callees

- `0x140076060`
- `0x140076ad0`
- `0x1400845e0`
- `0x1400862c0`
- `0x140089b40`
- `0x14009c7a0`
- `0x1400d0fd8`
- `0x1400d13a8`
- `0x1401f3c1c`
- `0x1401f3cec`
- `0x1401f3fc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400761cc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400762f3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401fed3a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400761cc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400762f3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401fed3a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007614b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400762d9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007633e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400763e1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fed21`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fedbd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007614b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400762d9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14007633e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400763e1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fed21`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401fedbd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140076219`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007631e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400764b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fed53`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fed79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fedef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140076219`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14007631e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400764b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fed53`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fed79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401fedef`

## pseudocode

```c
void __fastcall RefsAcquireRangeLock(
        struct _IRP_CONTEXT *a1,
        struct _SCB_NONPAGED *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        struct _RANGE_LOCK_STATE *a6)
{
  struct _IRP_CONTEXT *v7; // rbx
  __int64 v8; // rax
  char v9; // cl
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int128 v14; // rdi
  KSPIN_LOCK *v15; // r14
  KSPIN_LOCK **v16; // rbx
  NTSTATUS inserted; // r15d
  _QWORD *i; // r10
  unsigned __int64 j; // rax
  __int64 v21; // rcx
  char v22; // dl
  __int64 v23; // rcx
  __int64 v24; // r8
  char v25; // al
  _QWORD *v26; // rdx
  __int64 v27; // rax
  _QWORD *v28; // rbx
  _QWORD *v29; // rax
  unsigned __int64 v30; // rax
  char v31; // cl
  unsigned __int64 v32; // rdi
  __int64 v33; // rdx
  __int64 v34; // r14
  KSPIN_LOCK *v35; // rbx
  KSPIN_LOCK **v36; // rsi
  _QWORD *v37; // rax
  NTSTATUS v38; // r15d
  int v39; // eax
  _QWORD *v40; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-29h] BYREF
  __int128 v43; // [rsp+60h] [rbp-11h] BYREF

  v7 = a1;
  if ( (*((_DWORD *)a1 + 1) & 0x40) != 0 )
    return;
  v8 = *((_QWORD *)a2 + 7);
  LockHandle.LockQueue = 0;
  v43 = 0;
  if ( !a5 )
  {
    v9 = 14;
    if ( *(_DWORD *)(v8 + 552) == 12 )
      v9 = 12;
    v10 = 1 << v9;
    *(_QWORD *)&LockHandle.OldIrql = 0;
    v11 = v10 - 1;
    v12 = -v10;
    *(_QWORD *)&v14 = a3 & v12;
    v13 = v12 & (a3 + a4 + v11);
    *((_QWORD *)&v14 + 1) = v13 - 1;
    if ( v13 - 1 < (a3 & (unsigned __int64)v12) && v13 != (_QWORD)v14 )
    {
      inserted = -1073741407;
      goto LABEL_44;
    }
    v15 = (KSPIN_LOCK *)*((_QWORD *)a2 + 8);
    v16 = (KSPIN_LOCK **)((char *)a2 + 64);
    if ( !v15 )
    {
      inserted = FsLibPrivateInitializeRangeLock((char *)a2 + 64);
      if ( inserted < 0 )
        goto LABEL_43;
      v15 = *v16;
    }
    inserted = 0;
    v43 = v14;
    if ( !v15[1] )
    {
      KeAcquireInStackQueuedSpinLock(v15, &LockHandle);
      if ( !v15[1] )
      {
        v40 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
        v15[1] = (KSPIN_LOCK)v40;
        if ( !v40 )
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          inserted = -1073741670;
          goto LABEL_43;
        }
        v40[1] = 0;
        *(_QWORD *)v15[1] = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( v15[3] )
    {
      KeAcquireInStackQueuedSpinLock(v15, &LockHandle);
      if ( v15[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v15, &v43, 0) )
        goto LABEL_56;
      v25 = FsLibPrivateSearchArrayForRange(v15[2], &v43);
    }
    else
    {
      KeAcquireInStackQueuedSpinLock(v15, &LockHandle);
      for ( i = (_QWORD *)v15[2]; i; i = (_QWORD *)*i )
      {
        for ( j = i[1]; _BitScanForward64((unsigned __int64 *)&v21, j); j &= ~(1LL << v22) )
        {
          v22 = v21;
          v23 = 2 * v21;
          v24 = i[v23 + 2];
          if ( (__int64)v43 > v24 )
            goto LABEL_16;
          if ( v24 <= *((__int64 *)&v43 + 1) )
            goto LABEL_18;
          if ( (__int64)v43 >= v24 )
          {
LABEL_16:
            if ( (__int64)v43 <= i[v23 + 3] )
            {
LABEL_18:
              v25 = 0;
              goto LABEL_19;
            }
          }
        }
      }
      v25 = 1;
    }
LABEL_19:
    if ( v25 )
    {
      v26 = (_QWORD *)v15[1];
      do
      {
        v27 = v26[1];
        if ( v27 != -1 )
        {
          v30 = ~v27;
          goto LABEL_26;
        }
        v28 = v26;
        v26 = (_QWORD *)*v26;
      }
      while ( v26 );
      v29 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
      *v28 = v29;
      v26 = v29;
      if ( !v29 )
      {
        inserted = -1073741670;
        goto LABEL_27;
      }
      v29[1] = 0;
      *v29 = 0;
      v30 = -1;
LABEL_26:
      _BitScanForward64(&v30, v30);
      *(_QWORD *)a6 = v26;
      *((_QWORD *)a6 + 1) = 1LL << v30;
      v26[1] |= 1LL << v30;
      *(_OWORD *)&v26[2 * v30 + 2] = v43;
LABEL_27:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_28:
      if ( inserted >= 0 )
        return;
LABEL_43:
      v7 = a1;
LABEL_44:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          &WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
          (unsigned int)inserted);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(inserted, v7, "ResrcSup.c", 0xE54u);
      RefsRaiseStatusInternal(v7, inserted, a3);
      __debugbreak();
    }
LABEL_56:
    inserted = FsLibInsertWaitingLock(v15, &v43, 0x80000000LL, &LockHandle, a6);
    goto LABEL_28;
  }
  v31 = *(_BYTE *)(v8 + 552);
  v32 = a3 >> v31 << v31;
  v33 = (a3 + a4 + *(unsigned int *)(v8 + 544)) >> v31 << v31;
  *(_QWORD *)&LockHandle.OldIrql = 0;
  v34 = v33 - 1;
  if ( v33 - 1 < v32 && v33 != v32 )
  {
    v38 = -1073741407;
    goto LABEL_77;
  }
  v35 = (KSPIN_LOCK *)*((_QWORD *)a2 + 8);
  v36 = (KSPIN_LOCK **)((char *)a2 + 64);
  if ( !v35 )
  {
    v39 = FsLibPrivateInitializeRangeLock((char *)a2 + 64);
    if ( v39 < 0 )
    {
      v38 = v39;
      goto LABEL_49;
    }
    v35 = *v36;
  }
  *(_QWORD *)&v43 = v32;
  *((_QWORD *)&v43 + 1) = v34;
  if ( !v35[2] )
  {
    KeAcquireInStackQueuedSpinLock(v35, &LockHandle);
    if ( !v35[2] )
    {
      v37 = ExAllocateFromNPagedLookasideList(&FsLibRangeLockIntLookasideList);
      v35[2] = (KSPIN_LOCK)v37;
      if ( !v37 )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v38 = -1073741670;
        goto LABEL_49;
      }
      v37[1] = 0;
      *(_QWORD *)v35[2] = 0;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( v35[3] )
  {
    KeAcquireInStackQueuedSpinLock(v35, &LockHandle);
    if ( v35[3] && !(unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v35, &v43, 0) )
      goto LABEL_76;
  }
  else
  {
    KeAcquireInStackQueuedSpinLock(v35, &LockHandle);
  }
  if ( (unsigned __int8)FsLibPrivateCheckForExclusiveRangeLockAccess(v35, &v43) )
  {
    v38 = FsLibPrivateInsertRangeLockExclusive(v35, &v43, a6);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_48;
  }
LABEL_76:
  v38 = FsLibInsertWaitingLock(v35, &v43, 2147483649LL, &LockHandle, a6);
LABEL_48:
  if ( v38 < 0 )
  {
LABEL_49:
    v7 = a1;
LABEL_77:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        &WPP_31376ab3b8073048edfb14e725e449b5_Traceguids,
        (unsigned int)v38);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v38, v7, "ResrcSup.c", 0xE63u);
    RefsRaiseStatusInternal(v7, v38, a3);
    JUMPOUT(0x1401FEE8CLL);
  }
}

```

## disassembly

```asm
0x140076060  mov     r11, rsp
0x140076063  push    rbp
0x140076064  push    rbx
0x140076065  push    r13
0x140076067  lea     rbp, [r11-4Fh]
0x14007606b  sub     rsp, 0A0h
0x140076072  mov     rax, cs:__security_cookie
0x140076079  xor     rax, rsp
0x14007607c  mov     [rbp+47h+var_48], rax
0x140076080  mov     eax, [rcx+4]
0x140076083  mov     r10, rdx
0x140076086  mov     r13, [rbp+47h+arg_28]
0x14007608a  mov     rbx, rcx
0x14007608d  mov     [rbp+47h+var_80], rcx
0x140076091  test    al, 40h
0x140076093  jnz     loc_140076253
0x140076099  cmp     [rbp+47h+arg_20], 0
0x14007609d  xorps   xmm0, xmm0
0x1400760a0  mov     rax, [rdx+38h]
0x1400760a4  mov     [r11-20h], rsi
0x1400760a8  mov     [r11-28h], rdi
0x1400760ac  mov     [r11-38h], r14
0x1400760b0  mov     [r11-40h], r15
0x1400760b4  movups  xmmword ptr [rbp+47h+LockHandle.LockQueue.Next], xmm0
0x1400760b8  movups  [rbp+47h+var_58], xmm0
0x1400760bc  jnz     loc_14007627D
0x1400760c2  mov     eax, [rax+228h]
0x1400760c8  mov     ecx, 0Eh
0x1400760cd  cmp     eax, 0Ch
0x1400760d0  mov     [r11-30h], r12
0x1400760d4  mov     r12d, 1
0x1400760da  cmovz   cx, ax
0x1400760de  mov     eax, r12d
0x1400760e1  shl     eax, cl
0x1400760e3  movsxd  rcx, eax
0x1400760e6  xor     eax, eax
0x1400760e8  mov     rdx, rcx
0x1400760eb  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x1400760ef  dec     rcx
0x1400760f2  neg     rdx
0x1400760f5  add     rcx, r9
0x1400760f8  mov     rdi, rdx
0x1400760fb  add     rcx, r8
0x1400760fe  and     rdi, r8
0x140076101  and     rcx, rdx
0x140076104  lea     rsi, [rcx-1]
0x140076108  cmp     rsi, rdi
0x14007610b  jb      loc_1400763B9
0x140076111  mov     r14, [r10+40h]
0x140076115  lea     rbx, [r10+40h]
0x140076119  test    r14, r14
0x14007611c  jz      loc_1400763CA
0x140076122  xor     r15d, r15d
0x140076125  mov     qword ptr [rbp+47h+var_58], rdi
0x140076129  mov     qword ptr [rbp+47h+var_58+8], rsi
0x14007612d  cmp     [r14+8], r15
0x140076131  jz      loc_1401FED1A
0x140076137  mov     rax, [r14+18h]
0x14007613b  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x14007613f  mov     rcx, r14; SpinLock
0x140076142  test    rax, rax
0x140076145  jnz     loc_1400763E1
0x14007614b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140076152  nop     dword ptr [rax+rax+00h]
0x140076157  mov     r10, [r14+10h]
0x14007615b  mov     r11, qword ptr [rbp+47h+var_58+8]
0x14007615f  mov     r9, qword ptr [rbp+47h+var_58]
0x140076163  test    r10, r10
0x140076166  jz      loc_140076274
0x14007616c  mov     rax, [r10+8]
0x140076170  bsf     rcx, rax
0x140076174  jz      loc_14007626C
0x14007617a  mov     edx, ecx
0x14007617c  add     rcx, rcx
0x14007617f  mov     r8, [r10+rcx*8+10h]
0x140076184  cmp     r9, r8
0x140076187  jg      short loc_140076193
0x140076189  cmp     r8, r11
0x14007618c  jle     short loc_1400761A0
0x14007618e  cmp     r9, r8
0x140076191  jl      short loc_14007619A
0x140076193  cmp     r9, [r10+rcx*8+18h]
0x140076198  jle     short loc_1400761A0
0x14007619a  btr     rax, rdx
0x14007619e  jmp     short loc_140076170
0x1400761a0  xor     al, al
0x1400761a2  test    al, al
0x1400761a4  jz      loc_140076413
0x1400761aa  mov     rdx, [r14+8]
0x1400761ae  xchg    ax, ax
0x1400761b0  mov     rax, [rdx+8]
0x1400761b4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400761b8  jnz     short loc_1400761EF
0x1400761ba  mov     rbx, rdx
0x1400761bd  mov     rdx, [rdx]
0x1400761c0  test    rdx, rdx
0x1400761c3  jnz     short loc_1400761B0
0x1400761c5  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1400761cc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400761d3  nop     dword ptr [rax+rax+00h]
0x1400761d8  mov     [rbx], rax
0x1400761db  mov     rdx, rax
0x1400761de  test    rax, rax
0x1400761e1  jnz     loc_1401FEDA2
0x1400761e7  mov     r15d, 0C000009Ah
0x1400761ed  jmp     short loc_140076215
0x1400761ef  not     rax
0x1400761f2  bsf     rax, rax
0x1400761f6  mov     [r13+0], rdx
0x1400761fa  mov     ecx, eax
0x1400761fc  inc     rax
0x1400761ff  shl     r12, cl
0x140076202  mov     [r13+8], r12
0x140076206  or      [rdx+8], r12
0x14007620a  movups  xmm0, [rbp+47h+var_58]
0x14007620e  add     rax, rax
0x140076211  movups  xmmword ptr [rdx+rax*8], xmm0
0x140076215  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x140076219  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140076220  nop     dword ptr [rax+rax+00h]
0x140076225  test    r15d, r15d
0x140076228  js      loc_140076371
0x14007622e  mov     r12, [rsp+0B0h+var_28]
0x140076236  mov     r14, [rsp+0B0h+var_30]
0x14007623e  mov     rdi, [rsp+0B0h+var_20]
0x140076246  mov     rsi, [rsp+98h]
0x14007624e  mov     r15, [rsp+0B0h+var_38]
0x140076253  mov     rcx, [rbp+47h+var_48]
0x140076257  xor     rcx, rsp; StackCookie
0x14007625a  call    __security_check_cookie
0x14007625f  add     rsp, 0A0h
0x140076266  pop     r13
0x140076268  pop     rbx
0x140076269  pop     rbp
0x14007626a  retn
0x14007626c  mov     r10, [r10]
0x14007626f  jmp     loc_140076163
0x140076274  movzx   eax, r12b
0x140076278  jmp     loc_1400761A2
0x14007627d  movsx   ecx, byte ptr [rax+228h]
0x140076284  mov     rdi, r8
0x140076287  mov     edx, [rax+220h]
0x14007628d  xor     eax, eax
0x14007628f  add     rdx, r9
0x140076292  sar     rdi, cl
0x140076295  add     rdx, r8
0x140076298  shl     rdi, cl
0x14007629b  sar     rdx, cl
0x14007629e  shl     rdx, cl
0x1400762a1  mov     qword ptr [rbp+47h+LockHandle.OldIrql], rax
0x1400762a5  lea     r14, [rdx-1]
0x1400762a9  cmp     r14, rdi
0x1400762ac  jb      loc_140076487
0x1400762b2  mov     rbx, [r10+40h]
0x1400762b6  lea     rsi, [r10+40h]
0x1400762ba  test    rbx, rbx
0x1400762bd  jz      loc_14007649B
0x1400762c3  mov     qword ptr [rbp+47h+var_58], rdi
0x1400762c7  mov     qword ptr [rbp+47h+var_58+8], r14
0x1400762cb  cmp     qword ptr [rbx+10h], 0
0x1400762d0  jnz     short loc_14007632A
0x1400762d2  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1400762d6  mov     rcx, rbx; SpinLock
0x1400762d9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400762e0  nop     dword ptr [rax+rax+00h]
0x1400762e5  cmp     qword ptr [rbx+10h], 0
0x1400762ea  jnz     short loc_14007631A
0x1400762ec  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1400762f3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400762fa  nop     dword ptr [rax+rax+00h]
0x1400762ff  mov     [rbx+10h], rax
0x140076303  test    rax, rax
0x140076306  jz      loc_1400764B3
0x14007630c  xor     r15d, r15d
0x14007630f  mov     [rax+8], r15
0x140076313  mov     rax, [rbx+10h]
0x140076317  mov     [rax], r15
0x14007631a  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x14007631e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140076325  nop     dword ptr [rax+rax+00h]
0x14007632a  mov     rax, [rbx+18h]
0x14007632e  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x140076332  mov     rcx, rbx; SpinLock
0x140076335  test    rax, rax
0x140076338  jz      loc_1401FEDBD
0x14007633e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140076345  nop     dword ptr [rax+rax+00h]
0x14007634a  cmp     qword ptr [rbx+18h], 0
0x14007634f  lea     rdx, [rbp+47h+var_58]
0x140076353  jz      loc_1401FEDCD
0x140076359  xor     r8d, r8d
0x14007635c  mov     rcx, rbx
0x14007635f  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140076364  test    al, al
0x140076366  jnz     loc_1401FEDC9
0x14007636c  jmp     loc_1401FEE01
0x140076371  mov     rbx, [rbp+47h+var_80]
0x140076375  mov     rcx, cs:WPP_GLOBAL_Control
0x14007637c  lea     rax, WPP_GLOBAL_Control
0x140076383  cmp     rcx, rax
0x140076386  jnz     loc_140076436
0x14007638c  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140076393  test    al, al
0x140076395  jnz     loc_14007646A
0x14007639b  mov     edx, r15d; int
0x14007639e  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400763a1  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1400763a6  int     3; Trap to Debugger
0x1400763a7  test    r15d, r15d
0x1400763aa  jns     loc_140076236
0x1400763b0  mov     rbx, [rbp+47h+var_80]
0x1400763b4  jmp     loc_1401FEE24
0x1400763b9  cmp     rcx, rdi
0x1400763bc  jz      loc_140076111
0x1400763c2  mov     r15d, 0C00001A1h
0x1400763c8  jmp     short loc_140076375
0x1400763ca  mov     rcx, rbx
0x1400763cd  call    FsLibPrivateInitializeRangeLock
0x1400763d2  mov     r15d, eax
0x1400763d5  test    eax, eax
0x1400763d7  js      short loc_140076371
0x1400763d9  mov     r14, [rbx]
0x1400763dc  jmp     loc_140076122
0x1400763e1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400763e8  nop     dword ptr [rax+rax+00h]
0x1400763ed  lea     rdx, [rbp+47h+var_58]
0x1400763f1  cmp     [r14+18h], r15
0x1400763f5  jz      loc_1401FED8B
0x1400763fb  xor     r8d, r8d
0x1400763fe  mov     rcx, r14
0x140076401  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140076406  test    al, al
0x140076408  jz      short loc_140076413
0x14007640a  lea     rdx, [rbp+47h+var_58]
0x14007640e  jmp     loc_1401FED8B
0x140076413  lea     r9, [rbp+47h+LockHandle]
0x140076417  mov     [rsp+20h], r13
0x14007641c  mov     r8d, 80000000h
0x140076422  lea     rdx, [rbp+47h+var_58]
0x140076426  mov     rcx, r14
0x140076429  call    FsLibInsertWaitingLock
0x14007642e  mov     r15d, eax
0x140076431  jmp     loc_140076225
0x140076436  test    dword ptr [rcx+2Ch], 100h
0x14007643d  jz      loc_14007638C
0x140076443  cmp     byte ptr [rcx+29h], 4
0x140076447  jb      loc_14007638C
0x14007644d  mov     rcx, [rcx+18h]
0x140076451  lea     r8, WPP_31376ab3b8073048edfb14e725e449b5_Traceguids
0x140076458  mov     edx, 12h
0x14007645d  mov     r9d, r15d
0x140076460  call    WPP_SF_d
0x140076465  jmp     loc_14007638C
0x14007646a  mov     r9d, 0E54h; unsigned int
0x140076470  lea     r8, aResrcsupC; "ResrcSup.c"
0x140076477  mov     rdx, rbx; struct _IRP_CONTEXT *
0x14007647a  mov     ecx, r15d; Status
0x14007647d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140076482  jmp     loc_14007639B
0x140076487  cmp     rdx, rdi
0x14007648a  jz      loc_1400762B2
0x140076490  mov     r15d, 0C00001A1h
0x140076496  jmp     loc_1401FEE24
0x14007649b  mov     rcx, rsi
0x14007649e  call    FsLibPrivateInitializeRangeLock
0x1400764a3  test    eax, eax
0x1400764a5  jns     loc_1401FEDB5
0x1400764ab  mov     r15d, eax
0x1400764ae  jmp     loc_1400763B0
0x1400764b3  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1400764b7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400764be  nop     dword ptr [rax+rax+00h]
0x1400764c3  mov     r15d, 0C000009Ah
0x1400764c9  jmp     loc_1400763B0
0x1401fed1a  lea     rdx, [rbp+47h+LockHandle]; LockHandle
0x1401fed1e  mov     rcx, r14; SpinLock
0x1401fed21  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1401fed28  nop     dword ptr [rax+rax+00h]
0x1401fed2d  cmp     [r14+8], r15
0x1401fed31  jnz     short loc_1401FED75
0x1401fed33  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x1401fed3a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401fed41  nop     dword ptr [rax+rax+00h]
0x1401fed46  mov     [r14+8], rax
0x1401fed4a  test    rax, rax
0x1401fed4d  jnz     short loc_1401FED6A
0x1401fed4f  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1401fed53  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401fed5a  nop     dword ptr [rax+rax+00h]
0x1401fed5f  mov     r15d, 0C000009Ah
0x1401fed65  jmp     loc_140076371
0x1401fed6a  mov     [rax+8], r15
0x1401fed6e  mov     rax, [r14+8]
0x1401fed72  mov     [rax], r15
0x1401fed75  lea     rcx, [rbp+47h+LockHandle]; LockHandle
0x1401fed79  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401fed80  nop     dword ptr [rax+rax+00h]
0x1401fed85  nop
0x1401fed86  jmp     loc_140076137
0x1401fed8b  mov     rax, r14
  ... truncated ...
```
