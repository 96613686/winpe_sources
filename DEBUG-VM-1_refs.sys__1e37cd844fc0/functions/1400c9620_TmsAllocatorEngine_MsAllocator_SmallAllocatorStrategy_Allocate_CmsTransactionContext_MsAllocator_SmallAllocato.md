# TmsAllocatorEngine<MsAllocator::SmallAllocatorStrategy>::Allocate(CmsTransactionContext *,MsAllocator::SmallAllocatorStrategy::State *,SmsAllocationContext *,_RANGE const *,_RANGE *,_RANGE *)

- ea: `0x1400c9620`
- end: `0x1400ca022`
- name: `?Allocate@?$TmsAllocatorEngine@VSmallAllocatorStrategy@MsAllocator@@@@SAJPEAVCmsTransactionContext@@PEAUState@SmallAllocatorStrategy@MsAllocator@@PEAUSmsAllocationContext@@PEBU_RANGE@@PEAU7@4@Z`
- size: `2562`
- prototype: `__int64 __usercall@<rax>(struct CmsTransactionContext *@<rcx>, struct _RANGE *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14006e060`

## callees

- `0x1400347f8`
- `0x140035a7c`
- `0x1400a7828`
- `0x1400c9620`
- `0x1400ca030`
- `0x1400ca6a0`
- `0x1400cae60`
- `0x14012c7f8`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x1400c986d`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400c9f20`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400c9fec`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c9cd5`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c9e3a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c9faf`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c9cd5`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c9e3a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400c9faf`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9cea`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9e67`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9fc4`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9cea`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9e67`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400c9fc4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c983a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c9f6f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c983a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400c9f6f`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9880`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9f33`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9fff`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9880`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9f33`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c9fff`

## pseudocode

```c
__int64 __fastcall TmsAllocatorEngine<MsAllocator::SmallAllocatorStrategy>::Allocate(
        struct CmsTransactionContext *a1,
        _QWORD *a2,
        signed __int64 a3,
        __int64 a4,
        struct _RANGE *a5,
        struct _RANGE *a6)
{
  __int64 v6; // r14
  unsigned __int64 v7; // r12
  signed __int64 v8; // rsi
  __int64 v10; // r13
  int v11; // eax
  int v12; // ecx
  unsigned int v13; // ecx
  __int64 v14; // r9
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rax
  struct _IO_REMOVE_LOCK *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdi
  struct SmsAllocationContext *v21; // r10
  char v22; // al
  int Region; // ebx
  unsigned __int64 v24; // rcx
  __int64 v25; // rcx
  __int16 v26; // dx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  __int16 v30; // r8
  unsigned __int64 v31; // rax
  int v32; // ecx
  int v33; // eax
  bool v34; // zf
  bool v35; // r8
  __int16 v36; // bx
  bool v37; // dl
  bool v38; // di
  __int16 v39; // dx
  unsigned __int64 v40; // rcx
  int v41; // eax
  int v42; // eax
  __int64 v43; // rcx
  __int16 v44; // dx
  unsigned __int64 v45; // rcx
  int v46; // eax
  char v47; // cl
  __int64 v48; // rcx
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  int v53; // ecx
  unsigned int v54; // eax
  int v55; // eax
  __int64 v56; // rcx
  char v57; // al
  __int64 v58; // rcx
  struct _IO_REMOVE_LOCK *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  signed __int32 v63[8]; // [rsp+0h] [rbp-100h] BYREF
  struct _RANGE *v64; // [rsp+20h] [rbp-E0h]
  _QWORD *v65; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v66; // [rsp+48h] [rbp-B8h]
  __int64 v67; // [rsp+50h] [rbp-B0h]
  unsigned int v68; // [rsp+58h] [rbp-A8h]
  bool v69; // [rsp+5Ch] [rbp-A4h]
  char v70; // [rsp+5Dh] [rbp-A3h]
  __int16 v71; // [rsp+5Eh] [rbp-A2h]
  signed __int64 v72; // [rsp+60h] [rbp-A0h]
  _QWORD **v73; // [rsp+68h] [rbp-98h]
  unsigned __int128 v74; // [rsp+70h] [rbp-90h] BYREF
  __int128 *v75; // [rsp+80h] [rbp-80h]
  __int64 v76; // [rsp+88h] [rbp-78h]
  int v77; // [rsp+90h] [rbp-70h]
  struct SmsContainer *v78; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v79; // [rsp+A8h] [rbp-58h]
  _QWORD v80[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v81; // [rsp+C0h] [rbp-40h]
  __int128 v82; // [rsp+D0h] [rbp-30h]
  __int128 v83; // [rsp+E0h] [rbp-20h]
  __int128 v84; // [rsp+F0h] [rbp-10h]
  __int128 v85; // [rsp+100h] [rbp+0h]
  __int64 v86; // [rsp+110h] [rbp+10h]
  char v87; // [rsp+170h] [rbp+70h]
  int v88; // [rsp+178h] [rbp+78h]
  int v89; // [rsp+180h] [rbp+80h]
  __int64 v90; // [rsp+188h] [rbp+88h]

  v6 = *(_QWORD *)(a3 + 16);
  v7 = *(_QWORD *)(a4 + 8);
  v8 = a3;
  v80[0] = 0;
  v80[1] = 0;
  v10 = *(_QWORD *)(v6 + 456);
  v73 = &v65;
  v65 = a2;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v71 = 0;
  v72 = a3;
  v74 = 0;
  v75 = 0;
  v77 = 0;
  v76 = 0;
  v78 = 0;
  v88 = *(_DWORD *)(v6 + 468);
  v87 = 0;
  v89 = *(_DWORD *)(a3 + 68) & 8;
  v11 = *(_DWORD *)(a3 + 84);
  if ( v7 <= 0x20 && (v11 & 2) != 0 )
    v12 = 4;
  else
    v12 = 0;
  *(_DWORD *)(a3 + 84) = v12 | v11 & 0xFFFFFFFB;
  do
  {
    while ( 1 )
    {
      v13 = 0;
      v66 = 0;
      v68 = 0;
      v69 = 0;
      v71 = 0;
      v67 = 0;
LABEL_7:
      v74 = 0;
      v75 = 0;
      v77 = 0;
      v76 = 0;
      v14 = *(_QWORD *)(*v65 + 56LL);
      LOBYTE(a3) = !v66 && !v67;
      v15 = *(_QWORD *)a1 & 0x100000000LL;
      v66 = 0;
      v67 = v14;
      v69 = v15 != 0;
      if ( (_BYTE)a3 )
      {
        if ( v65[2] && !v15 )
        {
          v67 = v65[2];
          v69 = 1;
        }
        v70 = 1;
        goto LABEL_26;
      }
      v16 = v13 + 1;
      v68 = v16;
      if ( v16 <= 1 )
        break;
      if ( v16 <= 3 )
      {
        v69 = 0;
        goto LABEL_26;
      }
      if ( v16 <= 4 )
      {
        LOBYTE(v71) = 1;
        goto LABEL_26;
      }
      if ( v16 <= 5 )
      {
        HIBYTE(v71) = 1;
        goto LABEL_26;
      }
      if ( (*(_DWORD *)(v8 + 84) & 0x200) == 0 || v87 )
      {
        Region = -1073741697;
        goto LABEL_168;
      }
      v87 = 1;
    }
    v70 = 0;
    v17 = v65[2];
    v69 = v17 != 0;
    if ( v17 )
      v67 = v65[2];
    do
    {
      while ( 1 )
      {
LABEL_26:
        if ( v78 )
        {
          v18 = (struct _IO_REMOVE_LOCK *)(*(_QWORD *)(v10 + 3272) + 480LL);
          _InterlockedDecrement((volatile signed __int32 *)v78 + 23);
          IoReleaseRemoveLockEx(v18, 0, 0x20u);
          --*((_DWORD *)a1 + 88);
          v78 = 0;
        }
        if ( (v77 & 4) != 0 )
        {
          v19 = (__int64)v75;
          if ( _InterlockedDecrement((volatile signed __int32 *)v75 + 12) < 0 && (_BYTE)KdDebuggerEnabled )
            __debugbreak();
          ExReleasePushLockEx(v19 + 40, 0);
          LOBYTE(v77) = v77 & 0xFB;
        }
        v20 = (__int64)*v73;
        v21 = (struct SmsAllocationContext *)v73[4];
        v90 = (*v73)[1];
        LOBYTE(v77) = v77 ^ (*((_BYTE *)v73 + 31) ^ v77) & 1;
        v22 = *((_BYTE *)v73 + 30);
        v79 = 0;
        LOBYTE(v77) = v77 ^ (v77 ^ (2 * v22)) & 2;
        if ( *((_BYTE *)v73 + 29) && v90 && *(_QWORD *)v90 > (unsigned __int64)v74 )
        {
          Region = 0;
          v75 = (__int128 *)v90;
          v74 = *(_OWORD *)v90;
        }
        else
        {
          Region = MsAllocator::StrategySupport::LinearAcquireNextRegion(
                     a1,
                     v21,
                     *((_BYTE *)v73 + 28) == 0,
                     (const struct _RANGE *)(v73 + 1),
                     (struct MsAllocator::AllocationCandidate *)&v74);
          if ( Region < 0 )
            goto LABEL_54;
        }
        do
        {
          a3 = 0;
          v79 = *(_QWORD *)(v20 + 16);
          v24 = *(_QWORD *)v75 + *((_QWORD *)v75 + 1);
          if ( v24 > v79 )
            a3 = _InterlockedCompareExchange64((volatile signed __int64 *)(v20 + 16), v24, v79);
        }
        while ( v24 > v79 && a3 != v79 );
        if ( v90 )
        {
          v25 = *(int *)(v90 + 16);
          if ( (*(_BYTE *)(v90 + 36) & 2) == 0 )
            goto LABEL_46;
          if ( *(_DWORD *)(v90 + 16) )
          {
            v25 = *(_QWORD *)(v90 + 8);
LABEL_46:
            if ( v25 && (*(_BYTE *)(v90 + 36) & 0x20) == 0 )
              goto LABEL_54;
          }
        }
        v26 = *((_WORD *)v75 + 18);
        v27 = *((int *)v75 + 4);
        if ( (v26 & 2) != 0 )
        {
          if ( !*((_DWORD *)v75 + 4) )
            goto LABEL_54;
          v27 = *((_QWORD *)v75 + 1);
        }
        if ( v27 && (v26 & 0x20) == 0 )
          _InterlockedExchange64((volatile __int64 *)(v20 + 8), (__int64)v75);
LABEL_54:
        if ( Region < 0 )
          break;
        ++*(_DWORD *)(v8 + 80);
        if ( v89 )
        {
          v28 = 0;
          v29 = -(__int64)v88 & (v88 + v74 - 1);
          if ( (_QWORD)v74 + *((_QWORD *)&v74 + 1) > v29 )
            v28 = *((_QWORD *)&v74 + 1) + v74 - v29;
          if ( v28 >= v88 )
          {
            v74 = __PAIR128__(v28, v29);
            goto LABEL_61;
          }
        }
        else
        {
          v28 = *((_QWORD *)&v74 + 1);
LABEL_61:
          v30 = *((_WORD *)v75 + 18);
          v31 = *((int *)v75 + 4);
          if ( (v30 & 2) != 0 && *((_DWORD *)v75 + 4) )
            v31 = *((_QWORD *)v75 + 1);
          if ( v31 >= v28 )
            v31 = v28;
          if ( v31 )
          {
            v32 = *(_DWORD *)(v8 + 68);
            if ( (v31 >= v7 || (v32 & 8) == 0) && (v30 & 0x64) == 0 && ((v32 & 0x40) != 0 || (v30 & 8) == 0) )
            {
              if ( *(_BYTE *)(v6 + 492) == 2
                || (v33 = CmsAllocator::PopulateContainersForCandidate(
                            (CmsAllocator *)v6,
                            a1,
                            (struct SmsAllocationContext *)v8,
                            (const struct MsAllocator::AllocationCandidate *)&v74,
                            (struct _RANGE *)v80,
                            &v78),
                    Region = v33,
                    v33 >= 0) )
              {
                v35 = (v77 & 2) != 0 || v87;
                v36 = *((_WORD *)v75 + 18) & 2;
                _InterlockedOr(v63, 0);
                v37 = (v77 & 1) != 0 || (*(_DWORD *)(v8 + 84) & 4) == 0 && !v36;
                v38 = !v36
                   && *((_QWORD *)v75 + 1) == *(_DWORD *)(v6 + 468)
                   && !v35
                   && !v37
                   && (*(_DWORD *)(v8 + 84) & 0x200) == 0;
                if ( !CmsAllocator::TryLockCandidateForAllocation(
                        (CmsAllocator *)v6,
                        a1,
                        (struct SmsAllocationContext *)v8,
                        (const struct MsAllocator::AllocationCandidate *)&v74,
                        v35,
                        v37,
                        v38) )
                  goto LABEL_106;
                LOBYTE(v77) = v77 | 4;
                v39 = *((_WORD *)v75 + 18);
                v40 = *((int *)v75 + 4);
                if ( (v39 & 2) != 0 && *((_DWORD *)v75 + 4) )
                  v40 = *((_QWORD *)v75 + 1);
                if ( v40 >= *((_QWORD *)&v74 + 1) )
                  v40 = *((_QWORD *)&v74 + 1);
                if ( v40 )
                {
                  v41 = *(_DWORD *)(v8 + 68);
                  if ( (v40 >= v7 || (v41 & 8) == 0) && (v39 & 0x64) == 0 && ((v41 & 0x40) != 0 || (v39 & 8) == 0) )
                  {
                    if ( !v36 )
                      goto LABEL_120;
                    v42 = CmsAllocator::PrepareRangeOnlyCandidateForAllocation(
                            (CmsAllocator *)v6,
                            a1,
                            (struct SmsAllocationContext *)v8,
                            (struct MsAllocator::AllocationCandidate *)&v74);
                    Region = v42;
                    if ( v42 >= 0 )
                    {
                      v44 = *((_WORD *)v75 + 18);
                      v45 = *((int *)v75 + 4);
                      if ( (v44 & 2) != 0 && *((_DWORD *)v75 + 4) )
                        v45 = *((_QWORD *)v75 + 1);
                      if ( v45 >= *((_QWORD *)&v74 + 1) )
                        v45 = *((_QWORD *)&v74 + 1);
                      if ( v45 )
                      {
                        v46 = *(_DWORD *)(v8 + 68);
                        if ( (v45 >= v7 || (v46 & 8) == 0) && (v44 & 0x64) == 0 && ((v46 & 0x40) != 0 || (v44 & 8) == 0) )
                        {
LABEL_120:
                          v47 = *(_BYTE *)(v6 + 492);
                          if ( v47 != 3
                            || (*(_DWORD *)(v8 + 68) & 0x10) != 0
                            || *(_QWORD *)v75 == *(_QWORD *)((char *)v78
                                                           + (unsigned int)(16
                                                                          * *(_DWORD *)(*(_QWORD *)(v10 + 3272) + 388LL))
                                                           + 672) )
                          {
                            if ( (*(_DWORD *)(v8 + 84) & 1) != 0 )
                            {
                              if ( ((unsigned __int8)(1 << v47) & *((_BYTE *)a1 + 220)) == 0 )
                              {
                                v48 = *(_QWORD *)(v8 + 40);
                                if ( v48 )
                                  ExReleaseAutoExpandPushLockShared(v48, 2, a3);
                                else
                                  ExReleaseAutoExpandPushLockExclusive(v6 + 440, 2);
                              }
                              *(_DWORD *)(v8 + 84) &= ~1u;
                            }
                            v34 = *(_BYTE *)(v6 + 492) == 3;
                            v49 = v75[1];
                            v81 = *v75;
                            v50 = v75[2];
                            v82 = v49;
                            v51 = v75[3];
                            v83 = v50;
                            v52 = v75[4];
                            v84 = v51;
                            *(_QWORD *)&v51 = *((_QWORD *)v75 + 10);
                            v85 = v52;
                            v86 = v51;
                            if ( (v34 || !byte_140269025)
                              && (*(_DWORD *)(v8 + 84) & 4) != 0
                              && v38
                              && *((_QWORD *)&v74 + 1) == *((_QWORD *)v75 + 1)
                              && ((*(_DWORD *)(v8 + 68) & 0x400) != 0
                               || *((_BYTE *)&unk_140209844 + 12 * *(int *)(v10 + 3900))) )
                            {
                              v53 = 128;
                            }
                            else
                            {
                              v53 = 0;
                            }
                            v54 = v53 | *(_DWORD *)(v8 + 84) & 0xFFFFFF7F;
                            v64 = a5;
                            *(_DWORD *)(v8 + 84) = v54;
                            v55 = CmsAllocator::AllocateFromCandidate(
                                    (CmsAllocator *)v6,
                                    a1,
                                    (struct SmsAllocationContext *)v8,
                                    (struct MsAllocator::AllocationCandidate *)&v74,
                                    v64);
                            Region = v55;
                            if ( v55 >= 0 )
                            {
                              *(_OWORD *)a6 = *(_OWORD *)a5;
                              v57 = *(_BYTE *)(v6 + 492);
                              if ( v57 != 2 )
                              {
                                if ( v57 == 3 )
                                  CmsAllocator::UpdateVolumeContainerForCompletedAllocation(
                                    (CmsAllocator *)v6,
                                    a1,
                                    (struct MsAllocator::AllocationCandidate *)&v74,
                                    (struct SmsAllocationContext *)v8,
                                    v78,
                                    a6);
                                *(_QWORD *)a5 = v80[0] + (*(int *)a5 & (unsigned __int64)(v88 - 1));
                              }
                              v58 = (__int64)v75;
                              if ( _InterlockedDecrement((volatile signed __int32 *)v75 + 12) < 0
                                && (_BYTE)KdDebuggerEnabled )
                              {
                                __debugbreak();
                              }
                              ExReleasePushLockEx(v58 + 40, 0);
                              LOBYTE(v77) = v77 & 0xFB;
                              goto LABEL_168;
                            }
                            if ( v55 != -1073741267 && v55 != -1073741197 )
                            {
                              v34 = v55 == -1073741431;
                              goto LABEL_25;
                            }
                          }
                        }
                      }
                    }
                    else
                    {
                      if ( v42 != -1073741267 )
                        goto LABEL_168;
LABEL_106:
                      v43 = *((_QWORD *)&v74 + 1);
                      if ( *((_QWORD *)&v74 + 1) >= (unsigned __int64)v88 )
                        v43 = v88;
                      *((_QWORD *)&v74 + 1) = v43;
                    }
                  }
                }
              }
              else
              {
                v34 = v33 == -1073741267;
LABEL_25:
                if ( !v34 )
                  goto LABEL_168;
              }
            }
          }
        }
      }
      if ( Region == -1073741197 || Region == -1073741172 )
      {
        v13 = v68;
        goto LABEL_7;
      }
    }
    while ( Region == -1073741198 );
    if ( Region != -1073741400 || (*(_DWORD *)(v8 + 68) & 0x800) != 0 )
      break;
    if ( (*(_DWORD *)(v8 + 84) & 1) != 0 )
    {
      if ( ((unsigned __int8)(1 << *(_BYTE *)(v6 + 492)) & *((_BYTE *)a1 + 220)) == 0 )
      {
        v56 = *(_QWORD *)(v8 + 40);
        if ( v56 )
          ExReleaseAutoExpandPushLockShared(v56, 2, a3);
        else
          ExReleaseAutoExpandPushLockExclusive(v6 + 440, 2);
      }
      *(_DWORD *)(v8 + 84) &= ~1u;
    }
    Region = CmsVolume::TriageAllocator((CmsVolume *)v10, a1);
  }
  while ( Region >= 0 );
LABEL_168:
  if ( v78 )
  {
    v59 = (struct _IO_REMOVE_LOCK *)(*(_QWORD *)(v10 + 3272) + 480LL);
    _InterlockedDecrement((volatile signed __int32 *)v78 + 23);
    IoReleaseRemoveLockEx(v59, 0, 0x20u);
    --*((_DWORD *)a1 + 88);
  }
  if ( (*(_DWORD *)(v8 + 84) & 1) != 0 )
  {
    if ( ((unsigned __int8)(1 << *(_BYTE *)(v6 + 492)) & *((_BYTE *)a1 + 220)) == 0 )
    {
      v60 = *(_QWORD *)(v8 + 40);
      if ( v60 )
        ExReleaseAutoExpandPushLockShared(v60, 2, a3);
      else
        ExReleaseAutoExpandPushLockExclusive(v6 + 440, 2);
    }
    *(_DWORD *)(v8 + 84) &= ~1u;
  }
  if ( (v77 & 4) != 0 )
  {
    v61 = (__int64)v75;
    if ( _InterlockedDecrement((volatile signed __int32 *)v75 + 12) < 0 && (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    ExReleasePushLockEx(v61 + 40, 0);
  }
  return (unsigned int)Region;
}

```

## disassembly

```asm
0x1400c9620  push    rbp
0x1400c9622  push    rbx
0x1400c9623  push    rsi
0x1400c9624  push    rdi
0x1400c9625  push    r12
0x1400c9627  push    r13
0x1400c9629  push    r14
0x1400c962b  push    r15
0x1400c962d  lea     rbp, [rsp-28h]
0x1400c9632  sub     rsp, 128h
0x1400c9639  mov     r14, [r8+10h]
0x1400c963d  lea     rax, [rsp+160h+var_120]
0x1400c9642  mov     r12, [r9+8]
0x1400c9646  xorps   xmm0, xmm0
0x1400c9649  mov     rsi, r8
0x1400c964c  mov     [rbp+60h+var_B0], 0
0x1400c9654  mov     r15, rcx
0x1400c9657  mov     [rbp+60h+var_A8], 0
0x1400c965f  mov     r13, [r14+1C8h]
0x1400c9666  mov     [rsp+160h+var_F8], rax
0x1400c966b  mov     [rsp+160h+var_120], rdx
0x1400c9670  mov     [rsp+160h+var_118], 0
0x1400c9679  mov     [rsp+160h+var_110], 0
0x1400c9682  mov     [rsp+160h+var_108], 0
0x1400c968a  mov     [rsp+160h+var_104], 0
0x1400c968f  mov     [rsp+160h+var_102], 0
0x1400c9696  mov     [rsp+160h+var_100], r8
0x1400c969b  movdqa  [rsp+160h+var_F0], xmm0
0x1400c96a1  mov     [rbp+60h+var_E0], 0
0x1400c96a9  mov     [rbp+60h+var_D0], 0
0x1400c96b0  mov     [rbp+60h+var_D8], 0
0x1400c96b8  mov     [rbp+60h+var_C0], 0
0x1400c96c0  mov     eax, [r14+1D4h]
0x1400c96c7  mov     [rbp+60h+arg_8], eax
0x1400c96ca  mov     eax, [r8+44h]
0x1400c96ce  and     eax, 8
0x1400c96d1  mov     [rbp+60h+arg_0], 0
0x1400c96d5  mov     [rbp+60h+arg_10], eax
0x1400c96db  mov     eax, [r8+54h]
0x1400c96df  cmp     r12, 20h ; ' '
0x1400c96e3  ja      short loc_1400C96F0
0x1400c96e5  test    al, 2
0x1400c96e7  jz      short loc_1400C96F0
0x1400c96e9  mov     ecx, 4
0x1400c96ee  jmp     short loc_1400C96F2
0x1400c96f0  xor     ecx, ecx
0x1400c96f2  and     eax, 0FFFFFFFBh
0x1400c96f5  or      eax, ecx
0x1400c96f7  mov     [r8+54h], eax
0x1400c96fb  mov     r10, 100000000h
0x1400c9705  mov     edi, 0FFFFFFFFh
0x1400c970a  nop     word ptr [rax+rax+00h]
0x1400c9710  xor     ecx, ecx
0x1400c9712  mov     [rsp+160h+var_118], 0
0x1400c971b  mov     [rsp+160h+var_108], ecx
0x1400c971f  mov     [rsp+160h+var_104], cl
0x1400c9723  mov     [rsp+160h+var_102], cx
0x1400c9728  mov     [rsp+160h+var_110], 0
0x1400c9731  cmp     [rsp+160h+var_118], 0
0x1400c9737  xorps   xmm0, xmm0
0x1400c973a  mov     rdx, [rsp+160h+var_120]
0x1400c973f  movdqa  [rsp+160h+var_F0], xmm0
0x1400c9745  mov     [rbp+60h+var_E0], 0
0x1400c974d  mov     [rbp+60h+var_D0], 0
0x1400c9754  mov     [rbp+60h+var_D8], 0
0x1400c975c  mov     rax, [rdx]
0x1400c975f  mov     r9, [rax+38h]
0x1400c9763  jnz     short loc_1400C9772
0x1400c9765  cmp     [rsp+160h+var_110], 0
0x1400c976b  jnz     short loc_1400C9772
0x1400c976d  mov     r8b, 1
0x1400c9770  jmp     short loc_1400C9775
0x1400c9772  xor     r8b, r8b
0x1400c9775  mov     rax, [r15]
0x1400c9778  and     rax, r10
0x1400c977b  mov     [rsp+160h+var_118], 0
0x1400c9784  mov     [rsp+160h+var_110], r9
0x1400c9789  setnz   [rsp+160h+var_104]
0x1400c978e  test    r8b, r8b
0x1400c9791  jz      short loc_1400C97B2
0x1400c9793  mov     rcx, [rdx+10h]
0x1400c9797  test    rcx, rcx
0x1400c979a  jz      short loc_1400C97AB
0x1400c979c  test    rax, rax
0x1400c979f  jnz     short loc_1400C97AB
0x1400c97a1  mov     [rsp+160h+var_110], rcx
0x1400c97a6  mov     [rsp+160h+var_104], 1
0x1400c97ab  mov     [rsp+160h+var_103], 1
0x1400c97b0  jmp     short loc_1400C9815
0x1400c97b2  inc     ecx
0x1400c97b4  mov     [rsp+160h+var_108], ecx
0x1400c97b8  cmp     ecx, 1
0x1400c97bb  ja      short loc_1400C97DE
0x1400c97bd  mov     [rsp+160h+var_103], 0
0x1400c97c2  mov     rax, [rdx+10h]
0x1400c97c6  test    rax, rax
0x1400c97c9  setnz   [rsp+160h+var_104]
0x1400c97ce  test    rax, rax
0x1400c97d1  jz      short loc_1400C9815
0x1400c97d3  mov     rax, [rdx+10h]
0x1400c97d7  mov     [rsp+160h+var_110], rax
0x1400c97dc  jmp     short loc_1400C9815
0x1400c97de  cmp     ecx, 3
0x1400c97e1  ja      short loc_1400C97EA
0x1400c97e3  mov     [rsp+160h+var_104], 0
0x1400c97e8  jmp     short loc_1400C9815
0x1400c97ea  cmp     ecx, 4
0x1400c97ed  ja      short loc_1400C97F6
0x1400c97ef  mov     byte ptr [rsp+160h+var_102], 1
0x1400c97f4  jmp     short loc_1400C9815
0x1400c97f6  cmp     ecx, 5
0x1400c97f9  ja      loc_1400C9E96
0x1400c97ff  mov     byte ptr [rsp+160h+var_102+1], 1
0x1400c9804  jmp     short loc_1400C9815
0x1400c9806  jnz     loc_1400C9E8C
0x1400c980c  nop     dword ptr [rax+00h]
0x1400c9810  mov     edi, 0FFFFFFFFh
0x1400c9815  mov     rax, [rbp+60h+var_C0]
0x1400c9819  test    rax, rax
0x1400c981c  jz      short loc_1400C9855
0x1400c981e  mov     rcx, [r13+0CC8h]
0x1400c9825  xor     edx, edx; Tag
0x1400c9827  nop
0x1400c9828  add     rcx, 1E0h; RemoveLock
0x1400c982f  lock dec dword ptr [rax+5Ch]
0x1400c9833  mov     r8d, 20h ; ' '; RemlockSize
0x1400c9839  nop
0x1400c983a  call    cs:__imp_IoReleaseRemoveLockEx
0x1400c9841  nop     dword ptr [rax+rax+00h]
0x1400c9846  dec     dword ptr [r15+160h]
0x1400c984d  mov     [rbp+60h+var_C0], 0
0x1400c9855  test    byte ptr [rbp+60h+var_D0], 4
0x1400c9859  jz      short loc_1400C9890
0x1400c985b  mov     rcx, [rbp+60h+var_E0]
0x1400c985f  mov     eax, edi
0x1400c9861  nop
0x1400c9862  lock xadd [rcx+30h], eax
0x1400c9867  cmp     eax, 1
0x1400c986a  nop
0x1400c986b  jns     short loc_1400C987A
0x1400c986d  mov     rax, cs:KdDebuggerEnabled
0x1400c9874  cmp     byte ptr [rax], 0
0x1400c9877  jz      short loc_1400C987A
0x1400c9879  int     3; Trap to Debugger
0x1400c987a  add     rcx, 28h ; '('
0x1400c987e  xor     edx, edx
0x1400c9880  call    cs:__imp_ExReleasePushLockEx
0x1400c9887  nop     dword ptr [rax+rax+00h]
0x1400c988c  and     byte ptr [rbp+60h+var_D0], 0FBh
0x1400c9890  mov     rax, [rsp+160h+var_F8]
0x1400c9895  movzx   ecx, byte ptr [rbp+60h+var_D0]
0x1400c9899  lea     r9, [rax+8]; struct _RANGE *
0x1400c989d  xor     cl, [r9+17h]
0x1400c98a1  mov     rdx, qword ptr [rsp+160h+var_F0]
0x1400c98a6  and     cl, 1
0x1400c98a9  mov     rdi, [rax]
0x1400c98ac  mov     r10, [rax+20h]
0x1400c98b0  xor     cl, byte ptr [rbp+60h+var_D0]
0x1400c98b3  mov     rax, [rdi+8]
0x1400c98b7  mov     [rbp+60h+arg_18], rax
0x1400c98be  mov     byte ptr [rbp+60h+var_D0], cl
0x1400c98c1  movzx   eax, byte ptr [r9+16h]
0x1400c98c6  add     al, al
0x1400c98c8  mov     [rbp+60h+var_B8], 0
0x1400c98d0  xor     al, cl
0x1400c98d2  and     al, 2
0x1400c98d4  xor     al, cl
0x1400c98d6  mov     byte ptr [rbp+60h+var_D0], al
0x1400c98d9  cmp     byte ptr [r9+15h], 0
0x1400c98de  jz      short loc_1400C991F
0x1400c98e0  mov     rax, [rbp+60h+arg_18]
0x1400c98e7  test    rax, rax
0x1400c98ea  jz      short loc_1400C991F
0x1400c98ec  mov     rax, [rbp+60h+arg_18]
0x1400c98f3  cmp     [rax], rdx
0x1400c98f6  jbe     short loc_1400C991F
0x1400c98f8  mov     rax, [rbp+60h+arg_18]
0x1400c98ff  xor     ebx, ebx
0x1400c9901  mov     rcx, [rbp+60h+arg_18]
0x1400c9908  mov     [rbp+60h+var_E0], rax
0x1400c990c  mov     rax, [rcx]
0x1400c990f  mov     qword ptr [rsp+160h+var_F0], rax
0x1400c9914  mov     rax, [rcx+8]
0x1400c9918  mov     qword ptr [rsp+160h+var_F0+8], rax
0x1400c991d  jmp     short loc_1400C9950
0x1400c991f  cmp     byte ptr [r9+14h], 0
0x1400c9924  lea     rax, [rsp+160h+var_F0]
0x1400c9929  mov     rdx, r10; struct SmsAllocationContext *
0x1400c992c  mov     [rsp+160h+var_140], rax; struct MsAllocator::AllocationCandidate *
0x1400c9931  setz    r8b; bool
0x1400c9935  mov     rcx, r15; struct CmsTransactionContext *
0x1400c9938  call    ?LinearAcquireNextRegion@StrategySupport@MsAllocator@@SAJPEAVCmsTransactionContext@@PEAUSmsAllocationContext@@_NAEBU_RANGE@@AEAUAllocationCandidate@2@@Z; MsAllocator::StrategySupport::LinearAcquireNextRegion(CmsTransactionContext *,SmsAllocationContext *,bool,_RANGE const &,MsAllocator::AllocationCandidate &)
0x1400c993d  mov     ebx, eax
0x1400c993f  test    eax, eax
0x1400c9941  js      loc_1400C99F0
0x1400c9947  nop     word ptr [rax+rax+00000000h]
0x1400c9950  mov     rax, [rdi+10h]
0x1400c9954  xor     r8d, r8d
0x1400c9957  mov     [rbp+60h+var_B8], rax
0x1400c995b  mov     rax, [rbp+60h+var_E0]
0x1400c995f  mov     rcx, [rax+8]
0x1400c9963  add     rcx, [rax]
0x1400c9966  mov     rax, [rbp+60h+var_B8]
0x1400c996a  cmp     rcx, rax
0x1400c996d  jbe     short loc_1400C997E
0x1400c996f  mov     rax, [rbp+60h+var_B8]
0x1400c9973  nop
0x1400c9974  lock cmpxchg [rdi+10h], rcx
0x1400c997a  mov     r8, rax
0x1400c997d  nop
0x1400c997e  mov     rdx, [rbp+60h+var_B8]
0x1400c9982  cmp     rcx, rdx
0x1400c9985  jbe     short loc_1400C9990
0x1400c9987  mov     rcx, [rbp+60h+var_B8]
0x1400c998b  cmp     r8, rcx
0x1400c998e  jnz     short loc_1400C9950
0x1400c9990  mov     rax, [rbp+60h+arg_18]
0x1400c9997  test    rax, rax
0x1400c999a  jz      short loc_1400C99C8
0x1400c999c  mov     rdx, [rbp+60h+arg_18]
0x1400c99a3  test    byte ptr [rdx+24h], 2
0x1400c99a7  movsxd  rcx, dword ptr [rdx+10h]
0x1400c99ab  jz      short loc_1400C99B6
0x1400c99ad  test    rcx, rcx
0x1400c99b0  jz      short loc_1400C99C8
0x1400c99b2  mov     rcx, [rdx+8]
0x1400c99b6  test    rcx, rcx
0x1400c99b9  jz      short loc_1400C99C8
0x1400c99bb  mov     rax, [rbp+60h+arg_18]
0x1400c99c2  test    byte ptr [rax+24h], 20h
0x1400c99c6  jz      short loc_1400C99F0
0x1400c99c8  mov     rax, [rbp+60h+var_E0]
0x1400c99cc  movzx   edx, word ptr [rax+24h]
0x1400c99d0  movsxd  rcx, dword ptr [rax+10h]
0x1400c99d4  test    dl, 2
0x1400c99d7  jz      short loc_1400C99E2
0x1400c99d9  test    rcx, rcx
0x1400c99dc  jz      short loc_1400C99F0
0x1400c99de  mov     rcx, [rax+8]
0x1400c99e2  test    rcx, rcx
0x1400c99e5  jz      short loc_1400C99F0
0x1400c99e7  test    dl, 20h
0x1400c99ea  jnz     short loc_1400C99F0
0x1400c99ec  xchg    rax, [rdi+8]
0x1400c99f0  test    ebx, ebx
0x1400c99f2  js      loc_1400C9DDC
0x1400c99f8  inc     dword ptr [rsi+50h]
0x1400c99fb  cmp     [rbp+60h+arg_10], 0
0x1400c9a02  jz      short loc_1400C9A50
0x1400c9a04  mov     r8, qword ptr [rsp+160h+var_F0]
0x1400c9a09  xor     ecx, ecx
0x1400c9a0b  movsxd  r9, [rbp+60h+arg_8]
0x1400c9a0f  mov     r10, qword ptr [rsp+160h+var_F0+8]
0x1400c9a14  mov     rax, r9
0x1400c9a17  neg     rax
0x1400c9a1a  lea     rdx, [r8-1]
0x1400c9a1e  add     rdx, r9
0x1400c9a21  and     rdx, rax
0x1400c9a24  lea     rax, [r8+r10]
0x1400c9a28  cmp     rax, rdx
0x1400c9a2b  jbe     short loc_1400C9A36
0x1400c9a2d  mov     rcx, r8
0x1400c9a30  sub     rcx, rdx
0x1400c9a33  add     rcx, r10
0x1400c9a36  mov     edi, 0FFFFFFFFh
0x1400c9a3b  cmp     rcx, r9
0x1400c9a3e  jb      loc_1400C9815
0x1400c9a44  mov     qword ptr [rsp+160h+var_F0], rdx
0x1400c9a49  mov     qword ptr [rsp+160h+var_F0+8], rcx
0x1400c9a4e  jmp     short loc_1400C9A55
0x1400c9a50  mov     rcx, qword ptr [rsp+160h+var_F0+8]
0x1400c9a55  mov     rdx, [rbp+60h+var_E0]
0x1400c9a59  movzx   r8d, word ptr [rdx+24h]
0x1400c9a5e  movsxd  rax, dword ptr [rdx+10h]
0x1400c9a62  test    r8b, 2
0x1400c9a66  jz      short loc_1400C9A71
0x1400c9a68  test    rax, rax
0x1400c9a6b  jz      short loc_1400C9A71
0x1400c9a6d  mov     rax, [rdx+8]
0x1400c9a71  cmp     rax, rcx
0x1400c9a74  cmovnb  rax, rcx
0x1400c9a78  test    rax, rax
0x1400c9a7b  jz      loc_1400C9810
0x1400c9a81  mov     ecx, [rsi+44h]
0x1400c9a84  cmp     rax, r12
0x1400c9a87  jnb     short loc_1400C9A92
0x1400c9a89  test    cl, 8
0x1400c9a8c  jnz     loc_1400C9810
0x1400c9a92  test    r8b, 64h
0x1400c9a96  jnz     loc_1400C9810
0x1400c9a9c  test    cl, 40h
0x1400c9a9f  jnz     short loc_1400C9AAB
0x1400c9aa1  test    r8b, 8
0x1400c9aa5  jnz     loc_1400C9810
0x1400c9aab  cmp     byte ptr [r14+1ECh], 2
0x1400c9ab3  jz      short loc_1400C9AEA
0x1400c9ab5  lea     rax, [rbp+60h+var_C0]
0x1400c9ab9  mov     r8, rsi; struct SmsAllocationContext *
0x1400c9abc  mov     [rsp+160h+var_138], rax; struct SmsContainer **
0x1400c9ac1  lea     r9, [rsp+160h+var_F0]; struct MsAllocator::AllocationCandidate *
  ... truncated ...
```
