# NtfsDeallocateCompressionBuffer

- ea: `0x140005f40`
- end: `0x140006663`
- name: `NtfsDeallocateCompressionBuffer`
- size: `1827`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b2d0`
- `0x140175ad0`
- `0x140177c30`

## callees

- `0x140005f40`
- `0x140007ea0`
- `0x1400105d4`
- `0x140010670`
- `0x14001072c`
- `0x140010788`
- `0x14002c240`
- `0x14002f558`
- `0x1400346b4`
- `0x140038e9c`
- `0x140040f4c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005cd49`
- `ntoskrnl!KeSetEvent` at `0x14005cdc5`
- `ntoskrnl!KeSetEvent` at `0x14005cd49`
- `ntoskrnl!KeSetEvent` at `0x14005cdc5`
- `ntoskrnl!MmUnmapLockedPages` at `0x140006556`
- `ntoskrnl!MmUnmapLockedPages` at `0x140006556`
- `ntoskrnl!IoFreeMdl` at `0x140006565`
- `ntoskrnl!IoFreeMdl` at `0x140006565`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ffc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006309`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000647e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ffc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006309`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400063c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000647e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006107`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006239`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006107`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006239`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000609c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400061ce`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000609c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400061ce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000633a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400065e0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000633a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400065e0`

## pseudocode

```c
void __fastcall NtfsDeallocateCompressionBuffer(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v7; // rbp
  void *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  KSPIN_LOCK **v14; // rax
  KSPIN_LOCK *v15; // rbp
  __int64 v16; // rdi
  KSPIN_LOCK *v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // rsi
  _QWORD *v20; // rdx
  _QWORD *v21; // r8
  unsigned __int64 i; // r10
  bool v23; // zf
  __int64 v24; // rax
  char v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  KSPIN_LOCK v28; // r14
  int v29; // edi
  KSPIN_LOCK *v30; // r15
  __int64 v31; // r12
  __int64 v32; // rdx
  unsigned __int8 v33; // r9
  KSPIN_LOCK **v34; // rax
  KSPIN_LOCK *v35; // rbp
  __int64 v36; // rdi
  KSPIN_LOCK *v37; // rcx
  __int64 v38; // rsi
  __int64 v39; // rsi
  _QWORD *v40; // rdx
  _QWORD *v41; // r8
  unsigned __int64 j; // r10
  __int64 v43; // rax
  char v44; // r9
  __int64 v45; // rax
  __int64 v46; // rcx
  KSPIN_LOCK v47; // r14
  KSPIN_LOCK *v48; // r15
  __int64 v49; // r12
  __int64 v50; // rdx
  unsigned __int8 v51; // r9
  __int64 v52; // r14
  void *v53; // r15
  __int64 v54; // rcx
  bool v55; // sf
  __int64 v56; // r8
  __int64 v57; // rdx
  _QWORD *v58; // rdi
  __int64 v59; // rax
  unsigned __int64 v60; // rbp
  __int64 v61; // rsi
  char v62; // al
  __int64 v63; // r8
  int inserted; // eax
  char v65; // al
  __int64 v66; // r8
  int v67; // eax
  __int128 v68; // [rsp+20h] [rbp-68h] BYREF
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF
  struct _KLOCK_QUEUE_HANDLE v70; // [rsp+48h] [rbp-40h] BYREF

  if ( a1 )
    v7 = *(_QWORD *)(a1 + 104);
  else
    v7 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 40LL) + 384LL;
  if ( !*(_QWORD *)(a3 + 48) )
  {
    v8 = *(void **)(a3 + 32);
    if ( !v8 )
      goto LABEL_5;
    if ( v8 != (void *)qword_140095978 && v8 != (void *)qword_140095990 && v8 != (void *)qword_1400959C0 )
    {
      v57 = *(_QWORD *)(v7 + 5512);
      if ( v8 == *(void **)(v57 + 128) )
        _InterlockedExchange64((volatile __int64 *)(v57 + 8), 0);
      else
        ExFreePoolWithTag(v8, 0);
      goto LABEL_5;
    }
    if ( --dword_140095938 )
      goto LABEL_5;
LABEL_98:
    _InterlockedExchange64(&qword_1400958C0, 0);
    goto LABEL_5;
  }
  *(_DWORD *)(*(_QWORD *)(a2 + 8) + 40LL) = *(_DWORD *)(a3 + 40);
  v52 = *(_QWORD *)(a2 + 8);
  v53 = *(void **)(a3 + 32);
  if ( v52 )
  {
    if ( v52 != qword_140095980 && v52 != qword_140095998 && v52 != qword_1400959B0 && v52 != qword_1400959C8 )
    {
      v59 = *(_QWORD *)(v7 + 5512);
      if ( v52 != *(_QWORD *)(v59 + 136) || v59 == -128 )
      {
        if ( (*(_BYTE *)(v52 + 10) & 1) != 0 )
          MmUnmapLockedPages(*(PVOID *)(v52 + 24), *(PMDL *)(a2 + 8));
        IoFreeMdl((PMDL)v52);
      }
    }
  }
  if ( v53 )
  {
    if ( v53 == (void *)qword_140095978 || v53 == (void *)qword_140095990 || v53 == (void *)qword_1400959C0 )
    {
      if ( --dword_140095938 )
        goto LABEL_5;
      goto LABEL_98;
    }
    v54 = *(_QWORD *)(v7 + 5512);
    if ( v53 == *(void **)(v54 + 128) )
      _InterlockedExchange64((volatile __int64 *)(v54 + 8), 0);
    else
      ExFreePoolWithTag(v53, 0);
  }
LABEL_5:
  v9 = *(_QWORD *)(a3 + 48);
  if ( v9 )
  {
    *(_QWORD *)(a2 + 8) = v9;
    *(_QWORD *)(a2 + 112) = *(_QWORD *)(a3 + 56);
  }
  v10 = *(_QWORD *)(a3 + 96);
  v11 = (_QWORD *)(a3 + 96);
  if ( v10 )
  {
    if ( v10 == qword_140095978 || v10 == qword_140095990 || v10 == qword_1400959C0 )
    {
      if ( --dword_140095938 )
        goto LABEL_14;
      _InterlockedExchange64(&qword_1400958C0, 0);
    }
    else
    {
      v12 = *(_QWORD *)(v7 + 5512);
      if ( v10 == *(_QWORD *)(v12 + 128) )
      {
        _InterlockedExchange64((volatile __int64 *)(v12 + 8), 0);
        goto LABEL_14;
      }
      ExFreePoolWithTag(*(PVOID *)(a3 + 96), 0);
    }
    v11 = (_QWORD *)(a3 + 96);
  }
LABEL_14:
  *(_QWORD *)(a3 + 48) = 0;
  *(_QWORD *)(a3 + 56) = 0;
  *(_QWORD *)(a3 + 32) = 0;
  *v11 = 0;
  *(_DWORD *)(a3 + 40) = 0;
  if ( !a4 )
  {
    if ( *(_DWORD *)(a3 + 88) != 8 )
      ExFreePoolWithTag(*(PVOID *)(a3 + 80), 0);
    v13 = *(_DWORD *)(a3 + 112);
    if ( (v13 & 3) != 0 )
    {
      if ( (*(_DWORD *)(a3 + 112) & 3) == 3 )
      {
        v58 = *(_QWORD **)(a3 + 120);
        if ( *v58 )
        {
          v60 = *(_QWORD *)(a3 + 128);
          v61 = *(_QWORD *)(a3 + 136);
          if ( v61 + v60 - 1 < v60 && v61 )
          {
            v29 = -1073741407;
          }
          else if ( (unsigned int)FsLibUnlockRangeShared(
                                    *(_QWORD *)(a3 + 120),
                                    *(_QWORD *)(a3 + 128),
                                    *(_QWORD *)(a3 + 136)) )
          {
            v29 = FsLibUnlockRangeExclusive(v58, v60, v61);
          }
          else
          {
            v29 = 0;
          }
        }
        else
        {
          v29 = -1073741698;
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_67;
        v55 = v29 < 0;
        if ( v29 )
        {
          if ( v29 != 294
            && (unsigned int)(v29 - 298) > 1
            && (unsigned int)v29 < 0xFFFFFFED
            && v29 != -1073741608
            && v29 != -1073741802
            && v29 != -1073741807
            && (unsigned int)(v29 + 2147483643) > 1
            && v29 != 259 )
          {
            NtfsStatusTraceAndDebugInternal(0, (unsigned int)v29, 1903345);
          }
          goto LABEL_67;
        }
        goto LABEL_68;
      }
      if ( (v13 & 1) != 0 )
      {
        v14 = *(KSPIN_LOCK ***)(a3 + 120);
        memset(&LockHandle, 0, sizeof(LockHandle));
        v68 = 0;
        v15 = *v14;
        if ( (*v14)[1] )
        {
          v16 = *(_QWORD *)(a3 + 128);
          v17 = *v14;
          v18 = *(_QWORD *)(a3 + 136) - 1LL;
          *(_QWORD *)&v68 = v16;
          v19 = v16 + v18;
          *((_QWORD *)&v68 + 1) = v19;
          KeAcquireInStackQueuedSpinLock(v17, &LockHandle);
          v20 = (_QWORD *)v15[1];
          v21 = 0;
LABEL_22:
          if ( v20 )
          {
            for ( i = v20[1]; ; i &= ~(1LL << v25) )
            {
              v23 = !_BitScanForward64((unsigned __int64 *)&v24, i);
              if ( v23 )
              {
                v21 = v20;
                v20 = (_QWORD *)*v20;
                goto LABEL_22;
              }
              v25 = v24;
              v26 = 2 * v24;
              if ( v20[v26 + 2] == v16 && v20[v26 + 3] == v19 )
                break;
            }
            v27 = v20[1] & ~(1LL << v25);
            v20[1] = v27;
            if ( !v27 && v21 )
            {
              *v21 = *v20;
              *v20 = 0;
              ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v20);
            }
            v28 = v15[3];
            v29 = 0;
            if ( v28 )
            {
              v30 = v15 + 3;
              do
              {
                v31 = *(_QWORD *)(v28 + 40);
                if ( (unsigned __int8)AreRangeLocksOverlapping(&v68)
                  && ((v33 = *(_BYTE *)(v28 + 36), (v33 & 2) != 0)
                   || v15[3] == v28
                   || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v15, v32, v33))
                  && ((v33 & 1) == 0
                    ? (v62 = FsLibPrivateSearchArrayForRange(v15[2]))
                    : (v62 = FsLibPrivateCheckForExclusiveRangeLockAccess(v15)),
                      v62) )
                {
                  v63 = *(_QWORD *)(v28 + 48);
                  if ( (*(_BYTE *)(v28 + 36) & 1) != 0 )
                    inserted = FsLibPrivateInsertRangeLockExclusive(v15, v31, v63);
                  else
                    inserted = FsLibPrivateInsertRangeLockShared(v15, v31, v63);
                  *(_DWORD *)(v28 + 32) = inserted;
                  *v30 = *(_QWORD *)v28;
                  if ( v28 == v15[4] )
                    v15[4] = (KSPIN_LOCK)v30;
                  KeSetEvent((PRKEVENT)(v28 + 8), 0, 0);
                }
                else
                {
                  v30 = (KSPIN_LOCK *)v28;
                }
                v28 = *v30;
              }
              while ( *v30 );
            }
          }
          else
          {
            v29 = -1073741698;
            if ( v15[3] )
              FsLibPrivateCheckWaitingRangeLocks(v15, v15, &v68);
          }
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        else
        {
          v29 = -1073741698;
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_67;
        v55 = v29 < 0;
        if ( v29 )
        {
          v56 = 1903353;
LABEL_73:
          NtfsStatusTraceAndDebugInternal(0, (unsigned int)v29, v56);
LABEL_67:
          v55 = v29 < 0;
          goto LABEL_68;
        }
        goto LABEL_68;
      }
      if ( (v13 & 2) != 0 )
      {
        v34 = *(KSPIN_LOCK ***)(a3 + 120);
        memset(&v70, 0, sizeof(v70));
        v68 = 0;
        v35 = *v34;
        if ( (*v34)[2] )
        {
          v36 = *(_QWORD *)(a3 + 128);
          v37 = *v34;
          v38 = *(_QWORD *)(a3 + 136) - 1LL;
          *(_QWORD *)&v68 = v36;
          v39 = v36 + v38;
          *((_QWORD *)&v68 + 1) = v39;
          KeAcquireInStackQueuedSpinLock(v37, &v70);
          v40 = (_QWORD *)v35[2];
          v41 = 0;
LABEL_41:
          if ( v40 )
          {
            for ( j = v40[1]; ; j &= ~(1LL << v44) )
            {
              v23 = !_BitScanForward64((unsigned __int64 *)&v43, j);
              if ( v23 )
              {
                v41 = v40;
                v40 = (_QWORD *)*v40;
                goto LABEL_41;
              }
              v44 = v43;
              v45 = 2 * v43;
              if ( v40[v45 + 2] == v36 && v40[v45 + 3] == v39 )
                break;
            }
            v46 = v40[1] & ~(1LL << v44);
            v40[1] = v46;
            if ( !v46 && v41 )
            {
              *v41 = *v40;
              *v40 = 0;
              ExFreeToNPagedLookasideList(&FsLibRangeLockIntLookasideList, v40);
            }
            v47 = v35[3];
            v29 = 0;
            if ( v47 )
            {
              v48 = v35 + 3;
              do
              {
                v49 = *(_QWORD *)(v47 + 40);
                if ( (unsigned __int8)AreRangeLocksOverlapping(&v68)
                  && ((v51 = *(_BYTE *)(v47 + 36), (v51 & 2) != 0)
                   || v35[3] == v47
                   || (unsigned __int8)FsLibPrivateCheckFirstWaitingRangeLockForAccess(v35, v50, v51))
                  && ((v51 & 1) == 0
                    ? (v65 = FsLibPrivateSearchArrayForRange(v35[2]))
                    : (v65 = FsLibPrivateCheckForExclusiveRangeLockAccess(v35)),
                      v65) )
                {
                  v66 = *(_QWORD *)(v47 + 48);
                  if ( (*(_BYTE *)(v47 + 36) & 1) != 0 )
                    v67 = FsLibPrivateInsertRangeLockExclusive(v35, v49, v66);
                  else
                    v67 = FsLibPrivateInsertRangeLockShared(v35, v49, v66);
                  *(_DWORD *)(v47 + 32) = v67;
                  *v48 = *(_QWORD *)v47;
                  if ( v47 == v35[4] )
                    v35[4] = (KSPIN_LOCK)v48;
                  KeSetEvent((PRKEVENT)(v47 + 8), 0, 0);
                }
                else
                {
                  v48 = (KSPIN_LOCK *)v47;
                }
                v47 = *v48;
              }
              while ( *v48 );
            }
          }
          else
          {
            v29 = -1073741698;
            if ( v35[3] )
              FsLibPrivateCheckWaitingRangeLocks(v35, v35, &v68);
          }
          KeReleaseInStackQueuedSpinLock(&v70);
        }
        else
        {
          v29 = -1073741698;
        }
        if ( !NtfsStatusDebugFlags )
          goto LABEL_67;
        v55 = v29 < 0;
        if ( v29 )
        {
          v56 = 1903361;
          goto LABEL_73;
        }
LABEL_68:
        if ( !v55 )
          *(_DWORD *)(a3 + 112) &= 0xFFFFFFFC;
        return;
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225598LL, 1903365);
    }
  }
}

```

## disassembly

```asm
0x140005f40  push    rbx
0x140005f42  push    rbp
0x140005f43  push    rsi
0x140005f44  push    rdi
0x140005f45  push    r12
0x140005f47  sub     rsp, 60h
0x140005f4b  movzx   esi, r9b
0x140005f4f  mov     rbx, r8
0x140005f52  mov     rdi, rdx
0x140005f55  test    rcx, rcx
0x140005f58  jnz     loc_140006172
0x140005f5e  mov     rax, [rdx+0B8h]
0x140005f65  mov     rbp, [rax+28h]
0x140005f69  add     rbp, 180h
0x140005f70  xor     r12d, r12d
0x140005f73  mov     [rsp+88h+arg_0], r14
0x140005f7b  mov     [rsp+88h+arg_8], r15
0x140005f83  cmp     [r8+30h], r12
0x140005f87  jnz     loc_1400062A4
0x140005f8d  mov     rcx, [r8+20h]; P
0x140005f91  test    rcx, rcx
0x140005f94  jnz     loc_14000638A
0x140005f9a  mov     rax, [rbx+30h]
0x140005f9e  test    rax, rax
0x140005fa1  jz      short loc_140005FAF
0x140005fa3  mov     [rdi+8], rax
0x140005fa7  mov     rax, [rbx+38h]
0x140005fab  mov     [rdi+70h], rax
0x140005faf  mov     rax, [rbx+60h]
0x140005fb3  lea     rcx, [rbx+60h]
0x140005fb7  test    rax, rax
0x140005fba  jz      short loc_14000600C
0x140005fbc  cmp     rax, cs:qword_140095978
0x140005fc3  jz      loc_1400064C0
0x140005fc9  cmp     rax, cs:qword_140095990
0x140005fd0  jz      loc_1400064C0
0x140005fd6  cmp     rax, cs:qword_1400959C0
0x140005fdd  jz      loc_1400064C0
0x140005fe3  mov     rdx, [rbp+1588h]
0x140005fea  cmp     rax, [rdx+80h]
0x140005ff1  jz      loc_14000660E
0x140005ff7  xor     edx, edx; Tag
0x140005ff9  mov     rcx, rax; P
0x140005ffc  call    cs:__imp_ExFreePoolWithTag
0x140006003  nop     dword ptr [rax+rax+00h]
0x140006008  lea     rcx, [rbx+60h]
0x14000600c  mov     [rbx+30h], r12
0x140006010  mov     [rbx+38h], r12
0x140006014  mov     [rbx+20h], r12
0x140006018  mov     [rcx], r12
0x14000601b  mov     [rbx+28h], r12d
0x14000601f  test    sil, sil
0x140006022  jnz     loc_140006359
0x140006028  cmp     dword ptr [rbx+58h], 8
0x14000602c  jnz     loc_140006478
0x140006032  mov     eax, [rbx+70h]
0x140006035  mov     ecx, eax
0x140006037  and     ecx, 3
0x14000603a  jz      loc_140006359
0x140006040  cmp     ecx, 3
0x140006043  jz      loc_1400063D8
0x140006049  test    al, 1
0x14000604b  jz      loc_14000617B
0x140006051  xor     eax, eax
0x140006053  xorps   xmm0, xmm0
0x140006056  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000605b  mov     rax, [rbx+78h]
0x14000605f  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140006064  movups  [rsp+88h+var_68], xmm0
0x140006069  mov     rbp, [rax]
0x14000606c  cmp     [rbp+8], r12
0x140006070  jz      loc_1400065AF
0x140006076  mov     rdi, [rbx+80h]
0x14000607d  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x140006082  mov     rsi, [rbx+88h]
0x140006089  mov     rcx, rbp; SpinLock
0x14000608c  dec     rsi
0x14000608f  mov     qword ptr [rsp+88h+var_68], rdi
0x140006094  add     rsi, rdi
0x140006097  mov     qword ptr [rsp+88h+var_68+8], rsi
0x14000609c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400060a3  nop     dword ptr [rax+rax+00h]
0x1400060a8  mov     rdx, [rbp+8]; Entry
0x1400060ac  mov     r8, r12
0x1400060af  test    rdx, rdx
0x1400060b2  jz      loc_14000631A
0x1400060b8  mov     rcx, [rdx+8]
0x1400060bc  mov     r10, rcx
0x1400060bf  bsf     rax, r10
0x1400060c3  jz      loc_14000648F
0x1400060c9  mov     r9d, eax
0x1400060cc  add     rax, rax
0x1400060cf  cmp     [rdx+rax*8+10h], rdi
0x1400060d4  jnz     loc_140006576
0x1400060da  cmp     [rdx+rax*8+18h], rsi
0x1400060df  jnz     loc_140006576
0x1400060e5  btr     rcx, r9
0x1400060e9  mov     [rdx+8], rcx
0x1400060ed  test    rcx, rcx
0x1400060f0  jnz     short loc_140006113
0x1400060f2  test    r8, r8
0x1400060f5  jz      short loc_140006113
0x1400060f7  mov     rax, [rdx]
0x1400060fa  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140006101  mov     [r8], rax
0x140006104  mov     [rdx], r12
0x140006107  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000610e  nop     dword ptr [rax+rax+00h]
0x140006113  mov     r14, [rbp+18h]
0x140006117  mov     edi, r12d
0x14000611a  test    r14, r14
0x14000611d  jz      loc_140006335
0x140006123  lea     r15, [rbp+18h]
0x140006127  mov     r12, [r14+28h]
0x14000612b  lea     rcx, [rsp+88h+var_68]
0x140006130  mov     rdx, r12
0x140006133  call    AreRangeLocksOverlapping
0x140006138  test    al, al
0x14000613a  jz      loc_14005CD57
0x140006140  movzx   r9d, byte ptr [r14+24h]
0x140006145  test    r9b, 2
0x140006149  jnz     loc_14005CCEF
0x14000614f  cmp     [rbp+18h], r14
0x140006153  jz      loc_14005CCEF
0x140006159  movzx   r8d, r9b
0x14000615d  mov     rcx, rbp
0x140006160  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140006165  test    al, al
0x140006167  jnz     loc_14005CCEF
0x14000616d  jmp     loc_14005CD57
0x140006172  mov     rbp, [rcx+68h]
0x140006176  jmp     loc_140005F70
0x14000617b  test    al, 2
0x14000617d  jz      loc_14000649A
0x140006183  xor     eax, eax
0x140006185  xorps   xmm0, xmm0
0x140006188  mov     qword ptr [rsp+88h+var_40.OldIrql], rax
0x14000618d  mov     rax, [rbx+78h]
0x140006191  movups  xmmword ptr [rsp+88h+var_40.LockQueue.Next], xmm0
0x140006196  movups  [rsp+88h+var_68], xmm0
0x14000619b  mov     rbp, [rax]
0x14000619e  cmp     [rbp+10h], r12
0x1400061a2  jz      loc_1400065B9
0x1400061a8  mov     rdi, [rbx+80h]
0x1400061af  lea     rdx, [rsp+88h+var_40]; LockHandle
0x1400061b4  mov     rsi, [rbx+88h]
0x1400061bb  mov     rcx, rbp; SpinLock
0x1400061be  dec     rsi
0x1400061c1  mov     qword ptr [rsp+88h+var_68], rdi
0x1400061c6  add     rsi, rdi
0x1400061c9  mov     qword ptr [rsp+88h+var_68+8], rsi
0x1400061ce  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400061d5  nop     dword ptr [rax+rax+00h]
0x1400061da  mov     rdx, [rbp+10h]; Entry
0x1400061de  mov     r8, r12
0x1400061e1  test    rdx, rdx
0x1400061e4  jz      loc_1400065C0
0x1400061ea  mov     rcx, [rdx+8]
0x1400061ee  mov     r10, rcx
0x1400061f1  bsf     rax, r10
0x1400061f5  jz      loc_14000657F
0x1400061fb  mov     r9d, eax
0x1400061fe  add     rax, rax
0x140006201  cmp     [rdx+rax*8+10h], rdi
0x140006206  jnz     loc_1400065A6
0x14000620c  cmp     [rdx+rax*8+18h], rsi
0x140006211  jnz     loc_1400065A6
0x140006217  btr     rcx, r9
0x14000621b  mov     [rdx+8], rcx
0x14000621f  test    rcx, rcx
0x140006222  jnz     short loc_140006245
0x140006224  test    r8, r8
0x140006227  jz      short loc_140006245
0x140006229  mov     rax, [rdx]
0x14000622c  lea     rcx, FsLibRangeLockIntLookasideList; Lookaside
0x140006233  mov     [r8], rax
0x140006236  mov     [rdx], r12
0x140006239  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006240  nop     dword ptr [rax+rax+00h]
0x140006245  mov     r14, [rbp+18h]
0x140006249  mov     edi, r12d
0x14000624c  test    r14, r14
0x14000624f  jz      loc_1400065DB
0x140006255  lea     r15, [rbp+18h]
0x140006259  mov     r12, [r14+28h]
0x14000625d  lea     rcx, [rsp+88h+var_68]
0x140006262  mov     rdx, r12
0x140006265  call    AreRangeLocksOverlapping
0x14000626a  test    al, al
0x14000626c  jz      loc_14005CDD3
0x140006272  movzx   r9d, byte ptr [r14+24h]
0x140006277  test    r9b, 2
0x14000627b  jnz     loc_14005CD6B
0x140006281  cmp     [rbp+18h], r14
0x140006285  jz      loc_14005CD6B
0x14000628b  movzx   r8d, r9b
0x14000628f  mov     rcx, rbp
0x140006292  call    FsLibPrivateCheckFirstWaitingRangeLockForAccess
0x140006297  test    al, al
0x140006299  jnz     loc_14005CD6B
0x14000629f  jmp     loc_14005CDD3
0x1400062a4  mov     rcx, [rdx+8]
0x1400062a8  mov     eax, [r8+28h]
0x1400062ac  mov     [rcx+28h], eax
0x1400062af  mov     r14, [rdx+8]
0x1400062b3  mov     r15, [r8+20h]
0x1400062b7  test    r14, r14
0x1400062ba  jnz     loc_1400064F8
0x1400062c0  test    r15, r15
0x1400062c3  jz      loc_140005F9A
0x1400062c9  cmp     r15, cs:qword_140095978
0x1400062d0  jz      loc_14000658A
0x1400062d6  cmp     r15, cs:qword_140095990
0x1400062dd  jz      loc_14000658A
0x1400062e3  cmp     r15, cs:qword_1400959C0
0x1400062ea  jz      loc_14000658A
0x1400062f0  mov     rcx, [rbp+1588h]
0x1400062f7  cmp     r15, [rcx+80h]
0x1400062fe  jz      loc_140006626
0x140006304  xor     edx, edx; Tag
0x140006306  mov     rcx, r15; P
0x140006309  call    cs:__imp_ExFreePoolWithTag
0x140006310  nop     dword ptr [rax+rax+00h]
0x140006315  jmp     loc_140005F9A
0x14000631a  mov     edi, 0C000007Eh
0x14000631f  cmp     [rbp+18h], r12
0x140006323  jz      short loc_140006335
0x140006325  lea     r8, [rsp+88h+var_68]
0x14000632a  mov     rdx, rbp
0x14000632d  mov     rcx, rbp
0x140006330  call    FsLibPrivateCheckWaitingRangeLocks
0x140006335  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000633a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140006341  nop     dword ptr [rax+rax+00h]
0x140006346  movzx   eax, cs:NtfsStatusDebugFlags
0x14000634d  test    al, al
0x14000634f  jnz     short loc_140006375
0x140006351  test    edi, edi
0x140006353  js      short loc_140006359
0x140006355  and     dword ptr [rbx+70h], 0FFFFFFFCh
0x140006359  mov     r15, [rsp+88h+arg_8]
0x140006361  mov     r14, [rsp+88h+arg_0]
0x140006369  add     rsp, 60h
0x14000636d  pop     r12
0x14000636f  pop     rdi
0x140006370  pop     rsi
0x140006371  pop     rbp
0x140006372  pop     rbx
0x140006373  retn
0x140006375  test    edi, edi
0x140006377  jz      short loc_140006353
0x140006379  mov     r8d, 1D0AF9h
0x14000637f  mov     edx, edi
0x140006381  xor     ecx, ecx
0x140006383  call    NtfsStatusTraceAndDebugInternal
0x140006388  jmp     short loc_140006351
0x14000638a  cmp     rcx, cs:qword_140095978
0x140006391  jz      loc_1400064DC
0x140006397  cmp     rcx, cs:qword_140095990
0x14000639e  jz      loc_1400064DC
0x1400063a4  cmp     rcx, cs:qword_1400959C0
0x1400063ab  jz      loc_1400064DC
0x1400063b1  mov     rdx, [rbp+1588h]
0x1400063b8  cmp     rcx, [rdx+80h]
0x1400063bf  jz      loc_14000661A
0x1400063c5  xor     edx, edx; Tag
0x1400063c7  call    cs:__imp_ExFreePoolWithTag
0x1400063ce  nop     dword ptr [rax+rax+00h]
0x1400063d3  jmp     loc_140005F9A
0x1400063d8  mov     rdi, [rbx+78h]
0x1400063dc  cmp     [rdi], r12
0x1400063df  jnz     loc_140006632
0x1400063e5  mov     edi, 0C000007Eh
0x1400063ea  movzx   ecx, cs:NtfsStatusDebugFlags
0x1400063f1  test    cl, cl
0x1400063f3  jz      loc_140006351
0x1400063f9  test    edi, edi
0x1400063fb  jz      loc_140006353
0x140006401  cmp     edi, 126h
0x140006407  jz      loc_140006351
0x14000640d  lea     ecx, [rdi-12Ah]
0x140006413  cmp     ecx, 1
0x140006416  jbe     loc_140006351
0x14000641c  cmp     edi, 0FFFFFFEDh
0x14000641f  jnb     loc_140006351
0x140006425  cmp     edi, 0C00000D8h
0x14000642b  jz      loc_140006351
0x140006431  cmp     edi, 0C0000016h
0x140006437  jz      loc_140006351
0x14000643d  cmp     edi, 0C0000011h
0x140006443  jz      loc_140006351
0x140006449  lea     eax, [rdi+7FFFFFFBh]
0x14000644f  cmp     eax, 1
0x140006452  jbe     loc_140006351
0x140006458  cmp     edi, 103h
0x14000645e  jz      loc_140006351
0x140006464  mov     r8d, 1D0AF1h
0x14000646a  mov     edx, edi
0x14000646c  xor     ecx, ecx
0x14000646e  call    NtfsStatusTraceAndDebugInternal
  ... truncated ...
```
