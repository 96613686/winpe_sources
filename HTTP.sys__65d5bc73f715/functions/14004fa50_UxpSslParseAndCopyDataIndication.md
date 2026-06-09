# UxpSslParseAndCopyDataIndication

- ea: `0x14004fa50`
- end: `0x1400508ec`
- name: `UxpSslParseAndCopyDataIndication`
- size: `3740`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004edd0`

## callees

- `0x14000a350`
- `0x140049d08`
- `0x14004fa50`
- `0x1400513f0`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x14008e210`
- `0x140167810`
- `0x1401678f0`
- `0x140167940`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3878`
- `0x1401c3e00`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c49c4`
- `0x1401c4b0c`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400500d4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400500d4`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004fe66`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14005022d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004fe66`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14005022d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140050422`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140050456`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140050474`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400505be`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140050422`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140050456`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140050474`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400505be`
- `ntoskrnl!ExAllocatePool3` at `0x140176a7e`
- `ntoskrnl!ExAllocatePool3` at `0x140176a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005089c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005089c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400507ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400507ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004fede`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004fede`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140050793`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140050793`

## pseudocode

```c
__int64 __fastcall UxpSslParseAndCopyDataIndication(
        __int64 a1,
        __int64 *a2,
        unsigned int a3,
        __int64 a4,
        __int64 *a5,
        PVOID *a6)
{
  __int64 *v6; // r15
  __int64 v7; // r13
  unsigned int v8; // r11d
  __int64 *v9; // rsi
  struct _MDL *Next; // r10
  unsigned __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // r14d
  unsigned int v14; // r12d
  PVOID v15; // rbx
  unsigned __int8 v16; // di
  KIRQL v17; // dl
  bool v18; // al
  __int64 **v19; // rcx
  __int64 **v20; // rax
  __int64 *v21; // rax
  __int64 *v22; // rax
  ULONG ByteCount; // eax
  char *MappedSystemVa; // rax
  unsigned __int64 v26; // r8
  char *v27; // rdi
  char *v28; // r13
  unsigned int v29; // r14d
  unsigned __int8 v30; // r12
  __int64 v31; // r15
  int v32; // ecx
  __int64 v33; // rax
  unsigned int v34; // edi
  int v35; // ebx
  size_t v36; // r8
  unsigned int v37; // r12d
  unsigned int v38; // edi
  int v39; // r12d
  int v40; // r14d
  unsigned __int64 v41; // rbx
  char *v42; // rax
  _QWORD *Pool3; // rbx
  __int64 **v44; // rcx
  unsigned int v45; // edx
  unsigned int v46; // ecx
  unsigned int v47; // edx
  __int64 *v48; // rcx
  unsigned int *v49; // rbx
  char *v50; // rdx
  int v51; // eax
  unsigned int v52; // eax
  __int64 v53; // rcx
  char *v54; // rbx
  char *v55; // rdi
  __int64 **v56; // rax
  int v57; // r14d
  unsigned __int64 v58; // rbx
  char *v59; // rax
  unsigned int LockArray_high; // r14d
  __int64 v61; // rcx
  __int64 CurrentNodeNumber; // rdx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rbx
  USHORT v66; // ax
  __int64 v67; // rbx
  __int64 v68; // rbx
  USHORT v69; // ax
  int v70; // eax
  __int64 **v71; // rcx
  char *v72; // rax
  void *v73; // rcx
  unsigned int v74; // r14d
  __int64 v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // rcx
  int v78; // eax
  int v79; // eax
  volatile signed __int32 *v80; // r8
  unsigned __int8 v81[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v82; // [rsp+54h] [rbp-ACh]
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v84; // [rsp+60h] [rbp-A0h] BYREF
  __int64 **v85; // [rsp+68h] [rbp-98h]
  unsigned int v86; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v87; // [rsp+74h] [rbp-8Ch]
  unsigned int v88; // [rsp+78h] [rbp-88h]
  unsigned int v89; // [rsp+7Ch] [rbp-84h]
  unsigned __int64 v90; // [rsp+80h] [rbp-80h]
  struct _MDL *v91; // [rsp+88h] [rbp-78h]
  void *v92; // [rsp+90h] [rbp-70h]
  __int64 v93; // [rsp+98h] [rbp-68h]
  unsigned __int64 v94; // [rsp+A0h] [rbp-60h]
  __int64 v95; // [rsp+A8h] [rbp-58h]
  void *Src; // [rsp+B0h] [rbp-50h]
  __int64 *v97; // [rsp+B8h] [rbp-48h]
  __int64 *v98; // [rsp+C0h] [rbp-40h]
  PVOID *v99; // [rsp+C8h] [rbp-38h]
  _DWORD v100[24]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = a5;
  v84 = (__int64 *)&v84;
  v7 = a4;
  v93 = a4;
  v85 = &v84;
  v8 = a3;
  v88 = a3;
  v9 = a2;
  v97 = a2;
  v95 = a1;
  v98 = a5;
  v99 = a6;
  v86 = 0;
  v81 = 0;
  P = 0;
  v89 = 0;
  v92 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
  {
    WPP_SF_qqLqqq(1041, 18, WPP_6033a49e77e7395416619077875677ff_Traceguids, a1, a2, a3, a4, a5, a6);
    v8 = v88;
  }
  *a6 = 0;
  Next = (struct _MDL *)v9[1];
  v11 = v9[3];
  v12 = *((_DWORD *)v9 + 4);
  v91 = Next;
  v90 = v11;
  if ( v7 )
  {
    P = (PVOID)v7;
    v70 = _InterlockedIncrement((volatile signed __int32 *)(v7 + 20));
    if ( UxDebugCheckRefcount && v70 <= -1 )
      UlBugCheckEx(3u, v7 + 20, 0x1Du, v70);
    v71 = v85;
    if ( *v85 != (__int64 *)&v84 )
      goto LABEL_73;
    v72 = (char *)P + 32;
    *((_QWORD *)P + 4) = &v84;
    v11 = v90;
    *((_QWORD *)v72 + 1) = v71;
    *v71 = (__int64 *)v72;
    v73 = (void *)(*(_QWORD *)(v7 + 96) + *(unsigned int *)(v7 + 104));
    v85 = (__int64 **)v72;
    LODWORD(v72) = *(_DWORD *)(v7 + 108);
    v92 = v73;
    v89 = (unsigned int)v72;
  }
  v13 = 0;
  v87 = 0;
  v14 = 0;
  while ( 1 )
  {
    if ( !v9 || !v8 )
    {
LABEL_6:
      v15 = P;
      if ( P )
      {
        v16 = v81;
        if ( v7 )
          v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 3);
        else
          v17 = 0;
        *((_DWORD *)v15 + 27) -= v14;
        *((_DWORD *)v15 + 26) += v14;
        v18 = v16 || !*((_DWORD *)v15 + 27);
        *((_BYTE *)v15 + 116) = v18;
        if ( v7 )
          KeReleaseSpinLock((PKSPIN_LOCK)v15 + 3, v17);
        if ( !v81 )
        {
          v80 = (volatile signed __int32 *)P;
          if ( (PVOID)v7 != P )
          {
            if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
            {
              WPP_SF_qq(1041, 19, WPP_6033a49e77e7395416619077875677ff_Traceguids, v95, P);
              v80 = (volatile signed __int32 *)P;
            }
            v78 = _InterlockedIncrement(v80 + 5);
            if ( UxDebugCheckRefcount && v78 <= -1 )
              UlBugCheckEx(3u, (ULONG_PTR)(v80 + 5), 0x23u, v78);
            *v99 = P;
          }
        }
        P = 0;
      }
      if ( *(__int64 **)(*v6 + 8) == v6 )
      {
        v19 = (__int64 **)v6[1];
        if ( *v19 == v6 && (__int64 **)v84[1] == &v84 && *v85 == (__int64 *)&v84 )
        {
          *v19 = (__int64 *)&v84;
          v20 = v85;
          v6[1] = (__int64)v85;
          *v20 = v6;
          v21 = v84;
          v85 = v19;
          if ( (__int64 **)v84[1] == &v84 && *v19 == (__int64 *)&v84 )
          {
            *v19 = v84;
            v21[1] = (__int64)v19;
            v85 = &v84;
            v84 = (__int64 *)&v84;
            goto LABEL_22;
          }
        }
      }
LABEL_73:
      __fastfail(3u);
    }
LABEL_27:
    if ( v11 && v8 )
      break;
    v9 = (__int64 *)*v9;
    v97 = v9;
    if ( !v9 )
      goto LABEL_6;
    Next = (struct _MDL *)v9[1];
    v11 = v9[3];
    v12 = *((_DWORD *)v9 + 4);
    v91 = Next;
    v90 = v11;
  }
  if ( !Next )
  {
    v13 = -1073741436;
    goto LABEL_22;
  }
  ByteCount = Next->ByteCount;
  if ( v12 >= ByteCount )
  {
    Next = Next->Next;
    v13 = 0;
    v91 = Next;
    v12 -= ByteCount;
    goto LABEL_27;
  }
  if ( (Next->MdlFlags & 5) != 0 )
  {
    MappedSystemVa = (char *)Next->MappedSystemVa;
  }
  else
  {
    MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(Next, 0, MmCached, 0, 0, 0x40000000u);
    Next = v91;
    v11 = v90;
    v8 = v88;
  }
  if ( !MappedSystemVa )
  {
    v13 = -1073741670;
    goto LABEL_22;
  }
  v13 = 0;
  v26 = Next->ByteCount - v12;
  v82 = 0;
  v27 = &MappedSystemVa[v12];
  Src = v27;
  if ( v26 > v11 )
    v26 = (unsigned int)v11;
  if ( (unsigned int)v26 > v8 )
    v26 = v8;
  v94 = v26;
  while ( 2 )
  {
    if ( !(_DWORD)v26 )
    {
      v11 = v90;
      v12 = 0;
      v8 = v88;
      Next = v91->Next;
      v91 = v91->Next;
      goto LABEL_27;
    }
    v28 = v27;
    v29 = v26;
    v30 = 0;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qqLqq(1041, 49, WPP_6033a49e77e7395416619077875677ff_Traceguids, v95, v27, v26, &v86, &v81);
    v31 = v95;
    v86 = 0;
    v81 = 0;
    do
    {
      if ( v30 )
        break;
      v32 = *(_DWORD *)(v31 + 1520);
      if ( v32 )
      {
        if ( v32 == 1 )
        {
          v45 = *(_DWORD *)(v31 + 1516);
          v46 = v29;
          if ( v29 > v45 )
            v46 = *(_DWORD *)(v31 + 1516);
          v29 -= v46;
          v28 += v46;
          v47 = v45 - v46;
          *(_DWORD *)(v31 + 1516) = v47;
          if ( !v47 )
          {
            v30 = 1;
            *(_DWORD *)(v31 + 1520) = 0;
            *(_DWORD *)(v31 + 1512) = 0;
          }
        }
      }
      else
      {
        v33 = *(unsigned int *)(v31 + 1512);
        v34 = 5 - v33;
        if ( 5 - (int)v33 > v29 )
          v34 = v29;
        memmove((void *)(v31 + v33 + 1504), v28, v34);
        *(_DWORD *)(v31 + 1512) += v34;
        v28 += v34;
        v29 -= v34;
        if ( *(_DWORD *)(v31 + 1512) == 5 )
        {
          *(_DWORD *)(v31 + 1520) = 1;
          *(_DWORD *)(v31 + 1516) = *(unsigned __int8 *)(v31 + 1508) | (*(unsigned __int8 *)(v31 + 1507) << 8);
        }
      }
    }
    while ( v29 );
    v35 = *(_DWORD *)(v31 + 1516);
    v6 = v98;
    v9 = v97;
    if ( !v30 )
    {
      v79 = *(_DWORD *)(v95 + 1512);
      if ( v79 != 5 )
        v35 = 16645 - v79;
    }
    v36 = (unsigned int)v94 - v29;
    v81 = v30;
    v86 = v94 - v29;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    {
      WPP_SF_Dd(1041, 50, WPP_6033a49e77e7395416619077875677ff_Traceguids, (unsigned int)v36, v30);
      v36 = v86;
    }
    v37 = v89;
    v38 = v35 + v36;
    if ( v89 >= v35 + (int)v36 )
    {
      v13 = v82;
      v54 = (char *)v92;
      goto LABEL_98;
    }
    if ( P )
    {
      LOBYTE(v36) = 1;
      UxpSslCompletionIndicationCopy(P, v87, v36);
      v93 = 0;
      v87 = 0;
      P = 0;
    }
    if ( v38 > 0x905 )
    {
      if ( v38 > 0x2105 )
      {
        if ( v38 <= 0x4105 )
          v38 = 16645;
      }
      else
      {
        v38 = 8453;
      }
    }
    else
    {
      v38 = 2309;
    }
    v39 = 2;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_dq(1041, 14, WPP_6033a49e77e7395416619077875677ff_Traceguids, v38, &P);
    P = 0;
    if ( v38 > 0x905 )
    {
      if ( v38 <= 0x2105 )
      {
        LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
        if ( UxDebugDisableLookaside )
        {
          v63 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0660)(
                  (unsigned int)dword_1401A0648,
                  qword_1401A0650,
                  (unsigned int)dword_1401A0658,
                  0);
        }
        else
        {
          if ( UxCompactMode )
          {
            v67 = qword_1401A0640;
            CurrentNodeNumber = KeGetCurrentNodeNumber();
            v61 = v67;
          }
          else
          {
            v61 = qword_1401A0640;
            CurrentNodeNumber = LockArray_high;
          }
          v63 = PplAllocateFromLookasideListProcessor(v61, CurrentNodeNumber);
        }
        Pool3 = (_QWORD *)v63;
        if ( v63 )
        {
          *(_QWORD *)(v63 + 4) = 0;
          v39 = 1;
          *(_DWORD *)(v63 + 12) = 0;
          *(_QWORD *)(v63 + 24) = 0;
          *(_OWORD *)(v63 + 96) = 0;
          *(_OWORD *)(v63 + 112) = 0;
          *(_DWORD *)v63 = LockArray_high;
          goto LABEL_68;
        }
      }
      else if ( v38 > 0x4105 )
      {
        if ( UxSslLargeBufferEnabled && v38 <= 0x820A )
        {
          v74 = HIDWORD(KeGetPcr()[1].LockArray);
          if ( UxDebugDisableLookaside )
          {
            v64 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A06C0)(
                    (unsigned int)dword_1401A06A8,
                    qword_1401A06B0,
                    (unsigned int)dword_1401A06B8,
                    0);
          }
          else
          {
            if ( UxCompactMode )
            {
              v75 = qword_1401A06A0;
              v76 = KeGetCurrentNodeNumber();
              v77 = v75;
            }
            else
            {
              v77 = qword_1401A06A0;
              v76 = v74;
            }
            v64 = PplAllocateFromLookasideListProcessor(v77, v76);
          }
          Pool3 = (_QWORD *)v64;
          if ( v64 )
          {
            *(_QWORD *)(v64 + 4) = 0;
            v39 = 3;
            *(_DWORD *)(v64 + 12) = 0;
            *(_QWORD *)(v64 + 24) = 0;
            *(_OWORD *)(v64 + 96) = 0;
            *(_OWORD *)(v64 + 112) = 0;
            *(_DWORD *)v64 = v74;
            goto LABEL_68;
          }
        }
        else
        {
          Pool3 = (_QWORD *)ExAllocatePool3(66, v38 + 128LL, 1280538709, UxLowPriorityPool, 1);
          if ( Pool3 )
          {
            *(_OWORD *)Pool3 = 0;
            v39 = 4;
            Pool3[3] = 0;
            *((_OWORD *)Pool3 + 6) = 0;
            *((_OWORD *)Pool3 + 7) = 0;
            goto LABEL_68;
          }
        }
      }
      else
      {
        v57 = HIDWORD(KeGetPcr()[1].LockArray);
        if ( UxDebugDisableLookaside )
        {
          v59 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0690)(
                          (unsigned int)dword_1401A0678,
                          qword_1401A0680,
                          (unsigned int)dword_1401A0688,
                          0);
        }
        else if ( UxCompactMode )
        {
          v68 = qword_1401A0670;
          v69 = KeGetCurrentNodeNumber();
          v59 = (char *)PplAllocateFromLookasideListProcessor(v68, v69);
        }
        else
        {
          v58 = qword_1401A0670 + ((unsigned __int64)(unsigned int)(v57 + 1) << 7);
          if ( !*(_BYTE *)(v58 + 176) )
            PplpLazyInitializeLookasideList(qword_1401A0670, v58 + 64);
          v59 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v58 + 64));
        }
        Pool3 = v59;
        if ( v59 )
        {
          *(_QWORD *)(v59 + 4) = 0;
          *((_DWORD *)v59 + 3) = 0;
          *((_QWORD *)v59 + 3) = 0;
          *((_OWORD *)v59 + 6) = 0;
          *((_OWORD *)v59 + 7) = 0;
          *(_DWORD *)v59 = v57;
          goto LABEL_68;
        }
      }
    }
    else
    {
      v40 = HIDWORD(KeGetPcr()[1].LockArray);
      if ( UxDebugDisableLookaside )
      {
        v42 = (char *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0630)(
                        (unsigned int)dword_1401A0618,
                        qword_1401A0620,
                        (unsigned int)dword_1401A0628,
                        0);
      }
      else if ( UxCompactMode )
      {
        v65 = qword_1401A0610;
        v66 = KeGetCurrentNodeNumber();
        v42 = (char *)PplAllocateFromLookasideListProcessor(v65, v66);
      }
      else
      {
        v41 = qword_1401A0610 + ((unsigned __int64)(unsigned int)(v40 + 1) << 7);
        if ( !*(_BYTE *)(v41 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0610, v41 + 64);
        v42 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v41 + 64));
      }
      Pool3 = v42;
      if ( v42 )
      {
        *(_QWORD *)(v42 + 4) = 0;
        v39 = 0;
        *((_DWORD *)v42 + 3) = 0;
        *((_QWORD *)v42 + 3) = 0;
        *((_OWORD *)v42 + 6) = 0;
        *((_OWORD *)v42 + 7) = 0;
        *(_DWORD *)v42 = v40;
LABEL_68:
        *((_DWORD *)Pool3 + 5) = 1;
        *((_DWORD *)Pool3 + 4) = 1280538709;
        v82 = 0;
        Pool3[5] = Pool3 + 4;
        Pool3[4] = Pool3 + 4;
        Pool3[7] = Pool3 + 6;
        Pool3[6] = Pool3 + 6;
        Pool3[9] = Pool3 + 8;
        Pool3[8] = Pool3 + 8;
        Pool3[11] = Pool3 + 10;
        Pool3[10] = Pool3 + 10;
        KeInitializeSpinLock(Pool3 + 3);
        v13 = v82;
        Pool3[12] = Pool3 + 16;
        *((_DWORD *)Pool3 + 30) = v39;
        *((_DWORD *)Pool3 + 27) = v38;
        P = Pool3;
        goto LABEL_69;
      }
    }
    v13 = -1073741670;
    v82 = -1073741670;
LABEL_69:
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_LqL(1041, 15, WPP_6033a49e77e7395416619077875677ff_Traceguids, v13, P, v39);
    if ( (v13 & 0x80000000) == 0 )
    {
      v44 = v85;
      if ( *v85 != (__int64 *)&v84 )
        goto LABEL_73;
      v56 = (__int64 **)P;
      *((_QWORD *)P + 4) = &v84;
      v56 += 4;
      v56[1] = (__int64 *)v44;
      *v44 = (__int64 *)v56;
      v36 = v86;
      v85 = v56;
      v54 = (char *)(*((_QWORD *)P + 12) + *((unsigned int *)P + 26));
      v37 = *((_DWORD *)P + 27);
LABEL_98:
      v55 = (char *)Src;
      memmove(v54, Src, v36);
      v90 -= v86;
      v88 -= v86;
      v27 = &v55[v86];
      v7 = v93;
      LODWORD(v26) = v94 - v86;
      v89 = v37 - v86;
      v14 = v86 + v87;
      v92 = &v54[v86];
      Src = v27;
      v94 = (unsigned int)v94 - v86;
      v87 += v86;
      if ( v93 && v81 )
      {
        v92 = 0;
        v89 = 0;
        UxpSslCompletionIndicationCopy(P, v14, 1);
        LODWORD(v26) = v94;
        v7 = 0;
        v14 = 0;
        v93 = 0;
        v87 = 0;
        P = 0;
      }
      continue;
    }
    break;
  }
LABEL_22:
  while ( 1 )
  {
    v22 = v84;
    if ( v84 == (__int64 *)&v84 )
      break;
    if ( (__int64 **)v84[1] != &v84 )
      goto LABEL_73;
    v48 = (__int64 *)*v84;
    if ( *(__int64 **)(*v84 + 8) != v84 )
      goto LABEL_73;
    v84 = (__int64 *)*v84;
    v48[1] = (__int64)&v84;
    P = v22 - 4;
    v22[1] = (__int64)v22;
    *v22 = (__int64)v22;
    v49 = (unsigned int *)P;
    v50 = (char *)P + 20;
    v51 = _InterlockedDecrement((volatile signed __int32 *)P + 5);
    if ( UxDebugCheckRefcount && v51 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v50, 0x1Du, v51);
    if ( !v51 )
    {
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v49);
      v52 = v49[30];
      v49[4] = 1819498613;
      if ( v52 )
      {
        switch ( v52 )
        {
          case 1u:
            memset(v100, 0, sizeof(v100));
            if ( !UxDebugDisableLookaside )
            {
              v53 = qword_1401A0640;
              goto LABEL_92;
            }
            v100[10] = dword_1401A0658;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0668)(v49, v100);
            break;
          case 2u:
            memset(v100, 0, sizeof(v100));
            if ( !UxDebugDisableLookaside )
            {
              v53 = qword_1401A0670;
              goto LABEL_92;
            }
            v100[10] = dword_1401A0688;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0698)(v49, v100);
            break;
          case 3u:
            memset(v100, 0, sizeof(v100));
            if ( !UxDebugDisableLookaside )
            {
              v53 = qword_1401A06A0;
LABEL_92:
              if ( UxCompactMode )
                PnlFreeToLookasideList(v53, v49);
              else
                PplFreeToLookasideListProcessor(v53, v49, *v49);
              break;
            }
            v100[10] = dword_1401A06B8;
            ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A06C8)(v49, v100);
            break;
          default:
            ExFreePoolWithTag(v49, 0);
            break;
        }
      }
      else
      {
        memset(v100, 0, sizeof(v100));
        if ( !UxDebugDisableLookaside )
        {
          v53 = qword_1401A0610;
          goto LABEL_92;
        }
        v100[10] = dword_1401A0628;
        ((void (__fastcall *)(unsigned int *, _DWORD *))off_1401A0638)(v49, v100);
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
    }
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 20, WPP_6033a49e77e7395416619077875677ff_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x14004fa50  push    rbp
0x14004fa52  push    rbx
0x14004fa53  push    rsi
0x14004fa54  push    rdi
0x14004fa55  push    r13
0x14004fa57  push    r15
0x14004fa59  lea     rbp, [rsp-58h]
0x14004fa5e  sub     rsp, 158h
0x14004fa65  mov     rax, cs:__security_cookie
0x14004fa6c  xor     rax, rsp
0x14004fa6f  mov     [rbp+80h+var_50], rax
0x14004fa73  mov     r15, [rbp+80h+arg_20]
0x14004fa7a  lea     rax, [rsp+180h+var_120]
0x14004fa7f  mov     rbx, [rbp+80h+arg_28]
0x14004fa86  xor     edi, edi
0x14004fa88  mov     [rsp+180h+var_120], rax
0x14004fa8d  mov     r13, r9
0x14004fa90  lea     rax, [rsp+180h+var_120]
0x14004fa95  mov     [rbp+80h+var_E8], r9
0x14004fa99  mov     [rsp+180h+var_118], rax
0x14004fa9e  mov     r11d, r8d
0x14004faa1  mov     [rsp+180h+var_108], r8d
0x14004faa6  mov     rsi, rdx
0x14004faa9  mov     [rbp+80h+var_C8], rdx
0x14004faad  mov     r9, rcx
0x14004fab0  mov     [rbp+80h+var_D8], rcx
0x14004fab4  mov     [rbp+80h+var_C0], r15
0x14004fab8  mov     [rbp+80h+var_B8], rbx
0x14004fabc  mov     [rsp+180h+var_110], edi
0x14004fac0  mov     [rsp+180h+var_130], dil
0x14004fac5  mov     [rsp+180h+P], rdi
0x14004faca  mov     [rsp+180h+var_104], edi
0x14004face  mov     [rbp+80h+var_F0], rdi
0x14004fad2  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004fad9  jnz     loc_1400503A8
0x14004fadf  mov     [rbx], rdi
0x14004fae2  mov     r8d, 1; CacheType
0x14004fae8  mov     r10, [rsi+8]
0x14004faec  mov     rdx, [rsi+18h]
0x14004faf0  mov     ebx, [rsi+10h]
0x14004faf3  mov     [rsp+180h+var_30], r12
0x14004fafb  mov     [rbp+80h+var_F8], r10
0x14004faff  mov     [rbp+80h+var_100], rdx
0x14004fb03  mov     [rsp+180h+var_38], r14
0x14004fb0b  test    r13, r13
0x14004fb0e  jnz     loc_140050517
0x14004fb14  mov     r14d, edi
0x14004fb17  mov     [rsp+180h+var_10C], edi
0x14004fb1b  mov     r12d, edi
0x14004fb1e  test    rsi, rsi
0x14004fb21  jnz     loc_14004FC5E
0x14004fb27  mov     rbx, [rsp+180h+P]
0x14004fb2c  test    rbx, rbx
0x14004fb2f  jz      short loc_14004FB77
0x14004fb31  movzx   edi, [rsp+180h+var_130]
0x14004fb36  test    r13, r13
0x14004fb39  jnz     loc_14005078F
0x14004fb3f  xor     dl, dl; NewIrql
0x14004fb41  sub     [rbx+6Ch], r12d
0x14004fb45  add     [rbx+68h], r12d
0x14004fb49  mov     eax, [rbx+6Ch]
0x14004fb4c  test    dil, dil
0x14004fb4f  jz      loc_1400507A7
0x14004fb55  mov     al, 1
0x14004fb57  mov     [rbx+74h], al
0x14004fb5a  test    r13, r13
0x14004fb5d  jnz     loc_1400507B6
0x14004fb63  cmp     [rsp+180h+var_130], 0
0x14004fb68  jz      loc_1400507CB
0x14004fb6e  mov     [rsp+180h+P], 0
0x14004fb77  mov     rax, [r15]
0x14004fb7a  cmp     [rax+8], r15
0x14004fb7e  jnz     loc_14004FF2F
0x14004fb84  mov     rcx, [r15+8]
0x14004fb88  cmp     [rcx], r15
0x14004fb8b  jnz     loc_14004FF2F
0x14004fb91  mov     rax, [rsp+180h+var_120]
0x14004fb96  lea     rdx, [rsp+180h+var_120]
0x14004fb9b  cmp     [rax+8], rdx
0x14004fb9f  jnz     loc_14004FF2F
0x14004fba5  mov     rax, [rsp+180h+var_118]
0x14004fbaa  lea     rdx, [rsp+180h+var_120]
0x14004fbaf  cmp     [rax], rdx
0x14004fbb2  jnz     loc_14004FF2F
0x14004fbb8  lea     rax, [rsp+180h+var_120]
0x14004fbbd  mov     [rcx], rax
0x14004fbc0  lea     rdx, [rsp+180h+var_120]
0x14004fbc5  mov     rax, [rsp+180h+var_118]
0x14004fbca  mov     [r15+8], rax
0x14004fbce  mov     [rax], r15
0x14004fbd1  mov     rax, [rsp+180h+var_120]
0x14004fbd6  mov     [rsp+180h+var_118], rcx
0x14004fbdb  cmp     [rax+8], rdx
0x14004fbdf  jnz     loc_14004FF2F
0x14004fbe5  lea     rdx, [rsp+180h+var_120]
0x14004fbea  cmp     [rcx], rdx
0x14004fbed  jnz     loc_14004FF2F
0x14004fbf3  mov     [rcx], rax
0x14004fbf6  mov     [rax+8], rcx
0x14004fbfa  lea     rax, [rsp+180h+var_120]
0x14004fbff  mov     [rsp+180h+var_118], rax
0x14004fc04  lea     rax, [rsp+180h+var_120]
0x14004fc09  mov     [rsp+180h+var_120], rax
0x14004fc0e  mov     rax, [rsp+180h+var_120]
0x14004fc13  lea     rcx, [rsp+180h+var_120]
0x14004fc18  cmp     rax, rcx
0x14004fc1b  jnz     loc_14004FFCF
0x14004fc21  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004fc28  jnz     loc_1400508CE
0x14004fc2e  mov     r12, [rsp+180h+var_30]
0x14004fc36  mov     eax, r14d
0x14004fc39  mov     r14, [rsp+180h+var_38]
0x14004fc41  mov     rcx, [rbp+80h+var_50]
0x14004fc45  xor     rcx, rsp; StackCookie
0x14004fc48  call    __security_check_cookie
0x14004fc4d  add     rsp, 158h
0x14004fc54  pop     r15
0x14004fc56  pop     r13
0x14004fc58  pop     rdi
0x14004fc59  pop     rsi
0x14004fc5a  pop     rbx
0x14004fc5b  pop     rbp
0x14004fc5c  retn
0x14004fc5e  test    r11d, r11d
0x14004fc61  jz      loc_14004FB27
0x14004fc67  test    rdx, rdx
0x14004fc6a  jz      loc_14004FF59
0x14004fc70  test    r11d, r11d
0x14004fc73  jz      loc_14004FF59
0x14004fc79  test    r10, r10
0x14004fc7c  jz      loc_1400502B2
0x14004fc82  mov     eax, [r10+28h]
0x14004fc86  cmp     ebx, eax
0x14004fc88  jnb     loc_1400502BD
0x14004fc8e  test    byte ptr [r10+0Ah], 5
0x14004fc93  jz      loc_1400500C0
0x14004fc99  mov     rax, [r10+18h]
0x14004fc9d  test    rax, rax
0x14004fca0  jz      loc_140050784
0x14004fca6  mov     r8d, [r10+28h]
0x14004fcaa  mov     r14d, edi
0x14004fcad  sub     r8d, ebx
0x14004fcb0  mov     [rsp+180h+var_12C], edi
0x14004fcb4  mov     edi, ebx
0x14004fcb6  add     rdi, rax
0x14004fcb9  cmp     r8, rdx
0x14004fcbc  mov     [rbp+80h+Src], rdi
0x14004fcc0  cmova   r8d, edx
0x14004fcc4  cmp     r8d, r11d
0x14004fcc7  cmova   r8d, r11d
0x14004fccb  mov     [rbp+80h+var_E0], r8
0x14004fccf  test    r8d, r8d
0x14004fcd2  jz      loc_14004FF36
0x14004fcd8  mov     r13, rdi
0x14004fcdb  mov     r14d, r8d
0x14004fcde  xor     r12b, r12b
0x14004fce1  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004fce8  jnz     loc_140050650
0x14004fcee  mov     r15, [rbp+80h+var_D8]
0x14004fcf2  mov     [rsp+180h+var_110], 0
0x14004fcfa  mov     [rsp+180h+var_130], r12b
0x14004fcff  test    r12b, r12b
0x14004fd02  jnz     loc_14004FD8A
0x14004fd08  mov     ecx, [r15+5F0h]
0x14004fd0f  test    ecx, ecx
0x14004fd11  jnz     loc_14004FF81
0x14004fd17  mov     eax, [r15+5E8h]
0x14004fd1e  mov     edi, 5
0x14004fd23  sub     edi, eax
0x14004fd25  mov     rdx, r13; Src
0x14004fd28  cmp     edi, r14d
0x14004fd2b  cmova   edi, r14d
0x14004fd2f  lea     rcx, [rax+5E0h]
0x14004fd36  mov     r8d, edi; Size
0x14004fd39  add     rcx, r15; void *
0x14004fd3c  mov     ebx, edi
0x14004fd3e  call    memmove
0x14004fd43  add     [r15+5E8h], edi
0x14004fd4a  add     r13, rbx
0x14004fd4d  sub     r14d, edi
0x14004fd50  cmp     dword ptr [r15+5E8h], 5
0x14004fd58  jnz     short loc_14004FD81
0x14004fd5a  mov     dword ptr [r15+5F0h], 1
0x14004fd65  movzx   ecx, byte ptr [r15+5E3h]
0x14004fd6d  movzx   eax, byte ptr [r15+5E4h]
0x14004fd75  shl     ecx, 8
0x14004fd78  or      ecx, eax
0x14004fd7a  mov     [r15+5ECh], ecx
0x14004fd81  test    r14d, r14d
0x14004fd84  jnz     loc_14004FCFF
0x14004fd8a  mov     ebx, [r15+5ECh]
0x14004fd91  mov     edx, 4105h
0x14004fd96  mov     r15, [rbp+80h+var_C0]
0x14004fd9a  mov     rsi, [rbp+80h+var_C8]
0x14004fd9e  test    r12b, r12b
0x14004fda1  jz      loc_14005068D
0x14004fda7  mov     r8d, dword ptr [rbp+80h+var_E0]
0x14004fdab  sub     r8d, r14d; Size
0x14004fdae  mov     [rsp+180h+var_130], r12b
0x14004fdb3  mov     [rsp+180h+var_110], r8d
0x14004fdb8  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004fdbf  jnz     loc_1400506A9
0x14004fdc5  mov     r12d, [rsp+180h+var_104]
0x14004fdca  lea     edi, [rbx+r8]
0x14004fdce  cmp     r12d, edi
0x14004fdd1  jnb     loc_1400500F2
0x14004fdd7  mov     rcx, [rsp+180h+P]
0x14004fddc  test    rcx, rcx
0x14004fddf  jnz     loc_1400506D9
0x14004fde5  cmp     edi, 905h
0x14004fdeb  ja      loc_14005032E
0x14004fdf1  mov     edi, 905h
0x14004fdf6  mov     r12d, 2
0x14004fdfc  test    byte ptr cs:xmmword_1401A2CA0+2, r12b
0x14004fe03  jnz     loc_140050713
0x14004fe09  mov     [rsp+180h+P], 0
0x14004fe12  cmp     edi, 905h
0x14004fe18  ja      loc_1400501D1
0x14004fe1e  mov     r14d, gs:1A4h
0x14004fe27  cmp     cs:UxDebugDisableLookaside, 0
0x14004fe2e  jnz     loc_140050265
0x14004fe34  cmp     cs:UxCompactMode, 0
0x14004fe3b  jnz     loc_14005041B
0x14004fe41  mov     r8, cs:qword_1401A0610
0x14004fe48  lea     ebx, [r14+1]
0x14004fe4c  shl     rbx, 7
0x14004fe50  add     rbx, r8
0x14004fe53  movzx   eax, byte ptr [rbx+0B0h]
0x14004fe5a  test    al, al
0x14004fe5c  jz      loc_14005043E
0x14004fe62  lea     rcx, [rbx+40h]; Lookaside
0x14004fe66  call    cs:__imp_ExAllocateFromLookasideListEx
0x14004fe6d  nop     dword ptr [rax+rax+00h]
0x14004fe72  mov     rbx, rax
0x14004fe75  test    rax, rax
0x14004fe78  jz      loc_140050398
0x14004fe7e  xor     eax, eax
0x14004fe80  xorps   xmm0, xmm0
0x14004fe83  mov     [rbx+4], rax
0x14004fe87  xor     r12d, r12d
0x14004fe8a  mov     [rbx+0Ch], eax
0x14004fe8d  mov     [rbx+18h], rax
0x14004fe91  movups  xmmword ptr [rbx+60h], xmm0
0x14004fe95  movups  xmmword ptr [rbx+70h], xmm0
0x14004fe99  mov     [rbx], r14d
0x14004fe9c  mov     dword ptr [rbx+14h], 1
0x14004fea3  lea     rcx, [rbx+18h]; SpinLock
0x14004fea7  mov     dword ptr [rbx+10h], 4C537855h
0x14004feae  mov     [rsp+180h+var_12C], eax
0x14004feb2  lea     rax, [rbx+20h]
0x14004feb6  mov     [rbx+28h], rax
0x14004feba  mov     [rax], rax
0x14004febd  lea     rax, [rbx+30h]
0x14004fec1  mov     [rbx+38h], rax
0x14004fec5  mov     [rax], rax
0x14004fec8  lea     rax, [rbx+40h]
0x14004fecc  mov     [rbx+48h], rax
0x14004fed0  mov     [rax], rax
0x14004fed3  lea     rax, [rbx+50h]
0x14004fed7  mov     [rbx+58h], rax
0x14004fedb  mov     [rax], rax
0x14004fede  call    cs:__imp_KeInitializeSpinLock
0x14004fee5  nop     dword ptr [rax+rax+00h]
0x14004feea  mov     r14d, [rsp+180h+var_12C]
0x14004feef  lea     rax, [rbx+80h]
0x14004fef6  mov     [rbx+60h], rax
0x14004fefa  mov     [rbx+78h], r12d
0x14004fefe  mov     [rbx+6Ch], edi
0x14004ff01  mov     [rsp+180h+P], rbx
0x14004ff06  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14004ff0d  jnz     loc_1400503E1
0x14004ff13  test    r14d, r14d
0x14004ff16  js      loc_14004FC0E
0x14004ff1c  mov     rcx, [rsp+180h+var_118]
0x14004ff21  lea     rax, [rsp+180h+var_120]
0x14004ff26  cmp     [rcx], rax
0x14004ff29  jz      loc_140050199
0x14004ff2f  mov     ecx, 3
0x14004ff34  int     29h; Win8: RtlFailFast(ecx)
0x14004ff36  mov     r10, [rbp+80h+var_F8]
0x14004ff3a  xor     edi, edi
0x14004ff3c  mov     rdx, [rbp+80h+var_100]
0x14004ff40  mov     ebx, edi
0x14004ff42  mov     r11d, [rsp+180h+var_108]
0x14004ff47  mov     r8d, 1
0x14004ff4d  mov     r10, [r10]
0x14004ff50  mov     [rbp+80h+var_F8], r10
0x14004ff54  jmp     loc_14004FC67
0x14004ff59  mov     rsi, [rsi]
0x14004ff5c  mov     [rbp+80h+var_C8], rsi
0x14004ff60  test    rsi, rsi
0x14004ff63  jz      loc_14004FB27
0x14004ff69  mov     r10, [rsi+8]
0x14004ff6d  mov     rdx, [rsi+18h]
0x14004ff71  mov     ebx, [rsi+10h]
0x14004ff74  mov     [rbp+80h+var_F8], r10
0x14004ff78  mov     [rbp+80h+var_100], rdx
0x14004ff7c  jmp     loc_14004FB1E
0x14004ff81  cmp     ecx, 1
0x14004ff84  jnz     loc_14004FD81
  ... truncated ...
```
