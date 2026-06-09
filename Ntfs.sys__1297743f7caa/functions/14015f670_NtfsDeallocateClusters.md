# NtfsDeallocateClusters

- ea: `0x14015f670`
- end: `0x140160296`
- name: `NtfsDeallocateClusters`
- size: `3110`
- prototype: ``
- caller_count: `5`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1400cf580`
- `0x1401602a0`
- `0x140162a4c`
- `0x1401700f0`
- `0x1401e26f0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x140012e70`
- `0x140014e74`
- `0x1400211b0`
- `0x1400286d0`
- `0x14003c210`
- `0x14003c34c`
- `0x14003ecfc`
- `0x14003f474`
- `0x14003f7cc`
- `0x14003fc48`
- `0x140040210`
- `0x14004062c`
- `0x140059740`
- `0x14015f670`
- `0x1401652c8`
- `0x140173140`
- `0x1401c0ba0`
- `0x1401fd190`
- `0x1401fdae0`
- `0x140215770`
- `0x140223ab0`

## import_xrefs

- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14015fffb`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14015fffb`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14015fa4e`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x14015fa4e`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14015fcf7`
- `ntoskrnl!RtlGetCompressionWorkSpaceSize` at `0x14015fcf7`
- `ntoskrnl!RtlCompressBuffer` at `0x14015fdd3`
- `ntoskrnl!RtlCompressBuffer` at `0x14015fdd3`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140160053`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402a8db3`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140160053`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x1402a8db3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015fe16`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401600c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a8e4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015fe16`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401600c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a8e4e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015fd5d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015fd5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14015fc94`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8d47`
- `ntoskrnl!ExReleaseResourceLite` at `0x14015fc94`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8d47`
- `ntoskrnl!ExRaiseStatus` at `0x14015fe93`
- `ntoskrnl!ExRaiseStatus` at `0x14015fec1`
- `ntoskrnl!ExRaiseStatus` at `0x14015fe93`
- `ntoskrnl!ExRaiseStatus` at `0x14015fec1`

## pseudocode

```c
__int64 __fastcall NtfsDeallocateClusters(__int64 a1, __int64 a2, __int64 a3, LONGLONG a4, __int64 a5, __int64 *a6)
{
  __int64 v6; // r12
  __int64 v10; // rdi
  _DWORD *v11; // r13
  _QWORD *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  LONGLONG v18; // r12
  int v19; // ecx
  char v20; // r15
  __int64 DeallocatedClusters; // rax
  __int64 v22; // rcx
  __int64 v23; // r8
  int v24; // edx
  __int64 v25; // rcx
  LONGLONG v26; // r12
  _QWORD *v27; // rdi
  _WORD *v28; // rcx
  struct _ERESOURCE *v29; // rcx
  __int16 v30; // cx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  SIZE_T v33; // rdx
  unsigned int v34; // edi
  char *PoolWithTag; // rax
  char *v36; // r15
  __int64 v37; // r8
  char *v38; // rdi
  LONGLONG v39; // r8
  int v40; // ecx
  int v41; // eax
  __int64 v42; // r9
  int v43; // ecx
  _DWORD *v44; // rcx
  int v45; // edx
  int v46; // r8d
  LONGLONG v47; // rax
  bool v48; // sf
  __int64 v49; // rcx
  __int64 v50; // rdi
  __int64 v51; // r15
  int v52; // ecx
  PVOID v53; // rcx
  _DWORD *v54; // rdi
  unsigned __int8 v55; // r13
  __int64 v56; // rcx
  __int64 v58; // rcx
  unsigned __int8 v59; // [rsp+A8h] [rbp-E8h]
  char v60; // [rsp+A9h] [rbp-E7h]
  LONGLONG SectorCount; // [rsp+B0h] [rbp-E0h] BYREF
  char v62; // [rsp+B8h] [rbp-D8h]
  char v63[4]; // [rsp+BCh] [rbp-D4h]
  ULONG CompressBufferWorkSpaceSize; // [rsp+C0h] [rbp-D0h] BYREF
  ULONG CompressFragmentWorkSpaceSize; // [rsp+C4h] [rbp-CCh] BYREF
  __int64 v66; // [rsp+C8h] [rbp-C8h]
  __int64 v67; // [rsp+D0h] [rbp-C0h]
  PVOID P; // [rsp+D8h] [rbp-B8h]
  _QWORD *v69; // [rsp+E0h] [rbp-B0h]
  LONGLONG Vbn; // [rsp+E8h] [rbp-A8h] BYREF
  LONGLONG v71; // [rsp+F0h] [rbp-A0h]
  __int64 v72; // [rsp+F8h] [rbp-98h]
  _QWORD *v73; // [rsp+100h] [rbp-90h]
  __int64 v74; // [rsp+108h] [rbp-88h]
  __int64 v75; // [rsp+110h] [rbp-80h]
  __int64 v76; // [rsp+118h] [rbp-78h]
  _DWORD *v77; // [rsp+120h] [rbp-70h]
  _DWORD *v78; // [rsp+128h] [rbp-68h]
  _DWORD *v79; // [rsp+130h] [rbp-60h]
  _DWORD *v80; // [rsp+138h] [rbp-58h]
  __int64 v81; // [rsp+140h] [rbp-50h]
  __int64 v82; // [rsp+148h] [rbp-48h]
  LONGLONG v83; // [rsp+1B0h] [rbp+20h]

  v83 = a4;
  v6 = a4;
  v81 = a3;
  Vbn = 0;
  SectorCount = 0;
  v10 = 0;
  v66 = 0;
  v75 = -1;
  v76 = -1;
  v59 = 0;
  v60 = 0;
  v67 = 0;
  P = 0;
  v11 = (_DWORD *)(a1 + 16);
  if ( (!a1 || (*v11 & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
  {
    McTemplateU0ppppii_EtwWriteTransfer(a5, (unsigned int)bitmpsup_c3189, a1, a2, a3, a3 - 112, a4, a5);
  }
  v79 = v11;
  if ( (!a1 || (*v11 & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
  {
    McTemplateU0pppi_EtwWriteTransfer(
      a1,
      (unsigned int)bitmpsup_c3201,
      a2,
      *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
      v6,
      a5);
  }
  v73 = (_QWORD *)(a2 + 48);
  v12 = (_QWORD *)(a3 + 184);
  v69 = (_QWORD *)(a3 + 184);
  if ( *(_QWORD *)(a3 + 184) == *(_QWORD *)(*(_QWORD *)(a2 + 48) + 184LL)
    && *(_DWORD *)(a3 + 256) == 32
    && (!a1 || (*v11 & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
  {
    McTemplateU0ppppii_EtwWriteTransfer(a5, (unsigned int)bitmpsup_c3212, a1, a2, a3, a3 - 112, v6, a5);
    v12 = v69;
  }
  v78 = (_DWORD *)(a3 + 256);
  if ( *(_DWORD *)(a3 + 256) != 128
    || (v13 = *v12, *(_DWORD *)(*v12 + 8LL) < 0x10u)
    || (v14 = *(_QWORD *)(a2 + 40)) != 0 && v13 == *(_QWORD *)(v14 + 184)
    || (*(_DWORD *)v63 = 0, (*(_DWORD *)(v13 + 4) & 0x8000) != 0) )
  {
    *(_DWORD *)v63 = 2;
  }
  NtfsAcquireExclusiveScbEx(a1, *(_QWORD *)(a2 + 72), 0);
  if ( NtfsTrimListLengthThreshold )
  {
    v16 = *(_QWORD *)(a1 + 104);
    v17 = *(unsigned int *)(v16 + 1512);
    if ( (unsigned int)v17 > NtfsTrimListLengthThreshold && (*(_BYTE *)(a1 + 32) != 13 || *(_BYTE *)(a1 + 33) == 2) )
    {
      if ( (*v11 & 0x100000) == 0 && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        McTemplateU0pd_EtwWriteTransfer(v15, delnotify_c2941, v16, v17);
      v58 = a1;
      if ( a1 != *(_QWORD *)(a1 + 144) )
        v58 = *(_QWORD *)(a1 + 144);
      *(_QWORD *)(v58 + 16) |= 0x20000uLL;
      NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 3738516);
LABEL_128:
      if ( (!a1 || (*v11 & 0x100000) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v22, bitmpsup_c3360, a2);
      }
      *(_DWORD *)(a1 + 392) = 6;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225864LL, 265511);
      NtfsRaiseStatusInternal(a1, -1073741432, 0, 0, 265511);
LABEL_135:
      if ( NtfsStatusDebugFlags
        && (unsigned int)v10 < 0xFFFFFFED
        && (_DWORD)v10 != -1073741802
        && (unsigned int)(v10 + 2147483643) > 1
        && (_DWORD)v10 != -1073741807
        && (_DWORD)v10 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v10, 265660);
      }
      NtfsRaiseStatusInternal(a1, v10, 0, 0, 265660);
      __debugbreak();
      JUMPOUT(0x140160296LL);
    }
  }
  v80 = (_DWORD *)(a2 + 4);
  if ( (*(_DWORD *)(a2 + 4) & 0x80u) != 0 )
    NtfsScanEntireBitmap(a1, a2, 10, 2);
  while ( 1 )
  {
    v74 = v6;
    if ( v6 > a5 )
      break;
    v82 = a3 + 400;
    if ( !(unsigned __int8)NtfsLookupNtfsMcbEntryWithSyncFlag(a3 + 400, v6, &Vbn, &SectorCount, 0, 0, 0, 0) )
      break;
    v18 = Vbn;
    if ( Vbn == -1 )
    {
      v26 = v83;
      goto LABEL_99;
    }
    v71 = 0;
    v72 = 0;
    v10 = SectorCount;
    v19 = v83;
    if ( SectorCount + v83 > a5 )
    {
      v10 = a5 - v83 + 1;
      SectorCount = v10;
    }
    v77 = (_DWORD *)(a3 + 512);
    if ( (*(_DWORD *)(a3 + 512) & 0x800000) != 0
      || *v78 == 128 && *(_DWORD *)(a3 + 452) && (*(_BYTE *)(a3 + 4) & 0x20) != 0 )
    {
      v19 = *(unsigned __int8 *)(a2 + 488);
      if ( (unsigned __int64)(v10 << v19) > 0xFFFFFFFF )
      {
        v19 = *(_DWORD *)(a2 + 488);
        v10 = 0xFFFFFFFFuLL >> v19;
        SectorCount = 0xFFFFFFFFuLL >> v19;
      }
    }
    v71 = Vbn;
    v72 = v10;
    if ( (!a1 || (*v11 & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0pppi_EtwWriteTransfer(v19, (unsigned int)bitmpsup_c3317, a2, *(_QWORD *)(*v69 + 8LL), Vbn, v10);
    }
    v20 = 0;
    DeallocatedClusters = NtfsGetDeallocatedClusters(a1, a2, 0);
    v67 = DeallocatedClusters;
    if ( DeallocatedClusters )
      FsRtlAddBaseMcbEntry((PBASE_MCB)(DeallocatedClusters + 16), v18, v18, v10);
    else
      v20 = 1;
    if ( v20 )
      goto LABEL_128;
    v23 = v67;
    *(_QWORD *)(v67 + 48) += v10;
    if ( (!a1 || (*v11 & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0ppiidii_EtwWriteTransfer(
        *(_QWORD *)(a2 + 312),
        (unsigned int)bitmpsup_c3377,
        a2,
        v23,
        *(_QWORD *)(v23 + 40),
        *(_QWORD *)(v23 + 48),
        *(_DWORD *)(v23 + 56),
        *(_QWORD *)(a2 + 312),
        *(_QWORD *)(a2 + 312) + v10);
    }
    *(_QWORD *)(a2 + 312) += v10;
    *(_QWORD *)(a1 + 184) += v10;
    v66 = v10;
    v75 = v10 + v18;
    v76 = v10 + v18;
    *(_DWORD *)(a1 + 4) |= 0x1000u;
    NtfsFreeBitmapRun(a1, a2, v18, v63[0]);
    v59 = 1;
    v62 = 1;
    if ( !*(_DWORD *)(a3 + 452) || *(_BYTE *)(a3 + 460) )
    {
      v26 = v83;
    }
    else
    {
      v26 = v83;
      if ( (*(_BYTE *)(a3 + 4) & 0x20) != 0 )
        NtfsReserveClusters(a1, 1);
    }
    if ( (*v80 & 0x4000) != 0 && *(__int64 *)(a2 + 296) >> 4 < *(_QWORD *)(a2 + 304) )
    {
      v27 = v73;
      if ( (unsigned __int8)NtfsAcquireResourceExclusive(v25, *v73, 0) )
      {
        NtfsScanEntireBitmap(a1, a2, 8, 4);
        NtfsInitializeMftZone(a1, a2, 0, 0);
        v28 = (_WORD *)*v27;
        if ( *(_WORD *)*v27 == 1794 )
          v29 = (struct _ERESOURCE *)(*((_QWORD *)v28 + 13) + 64LL);
        else
          v29 = (struct _ERESOURCE *)*((_QWORD *)v28 + 1);
        ExReleaseResourceLite(v29);
      }
    }
    if ( (*v77 & 0x800000) == 0 )
      goto LABEL_83;
    if ( (*(_QWORD *)v11 & 0x40000LL) == 0 )
    {
      *(_QWORD *)v11 |= 0x40000uLL;
      v60 = 1;
    }
    v30 = (unsigned __int8)*(_WORD *)(a3 + 460);
    if ( !(unsigned __int8)*(_WORD *)(a3 + 460) )
    {
      v43 = *(_DWORD *)(a2 + 488);
      v41 = (_DWORD)SectorCount << v43;
      v42 = v26 << v43;
      goto LABEL_75;
    }
    CompressBufferWorkSpaceSize = 0;
    CompressFragmentWorkSpaceSize = 0;
    LODWORD(v10) = RtlGetCompressionWorkSpaceSize(v30 + 1, &CompressBufferWorkSpaceSize, &CompressFragmentWorkSpaceSize);
    if ( (int)v10 < 0 )
      goto LABEL_135;
    v31 = *(_DWORD *)(a2 + 356);
    v77 = (_DWORD *)(2LL * v31);
    if ( (unsigned __int64)v77 > 0xFFFFFFFF )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225859LL, 265665);
      ExRaiseStatus(-1073741437);
    }
    v32 = 2 * v31;
    v33 = v32 + CompressBufferWorkSpaceSize;
    if ( (unsigned int)v33 < v32 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225859LL, 265669);
      ExRaiseStatus(-1073741437);
    }
    v34 = v32 + CompressBufferWorkSpaceSize;
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x410), v33, 0x5043744Eu);
    v36 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v34);
    P = v36;
    v37 = *(unsigned int *)(a2 + 356);
    v38 = &v36[v37];
    RtlCompressBuffer(
      (unsigned __int8)*(_WORD *)(a3 + 460) + 1,
      (PUCHAR)v36,
      v37,
      (PUCHAR)&v36[v37],
      *(_DWORD *)(a2 + 356),
      0x1000u,
      &CompressFragmentWorkSpaceSize,
      &v36[v37 + v37]);
    NtfsWriteBytes(a1, a2, a3, v26 << *(_BYTE *)(a2 + 488), v38, *(_DWORD *)(a2 + 356), 256);
    ExFreePoolWithTag(v36, 0);
    P = 0;
    v39 = SectorCount;
    if ( SectorCount > 1 )
    {
      v40 = *(_DWORD *)(a2 + 488);
      v41 = ((_DWORD)SectorCount - 1) << v40;
      v42 = (v26 + 1) << v40;
LABEL_75:
      NtfsWriteBytes(a1, a2, a3, v42, 0, v41, 256);
LABEL_83:
      v39 = SectorCount;
    }
    if ( !a6 )
    {
      v44 = (_DWORD *)(v81 + 200);
LABEL_92:
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
        McTemplateU0ippdi_EtwWriteTransfer((_DWORD)v44, v24, v39, a3, (char)a6, *v44, *(_QWORD *)v11);
      goto LABEL_94;
    }
    v44 = (_DWORD *)(a3 + 200);
    if ( (*(_DWORD *)(a3 + 200) & 0x6000000) != 0 && (*v11 & 0x80000000) != 0 )
      goto LABEL_92;
    NtfsAdjustFcbAllocatedClusterCount(a1, *v69, -v39);
    v46 = SectorCount;
    v47 = SectorCount << *(_BYTE *)(a2 + 488);
    v48 = *a6 - v47 < 0;
    *a6 -= v47;
    v49 = *a6;
    if ( v48 )
    {
      *a6 = 0;
      LODWORD(v49) = 0;
    }
    if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
      McTemplateU0ipip_EtwWriteTransfer(v49, v45, v46, a3, v49, (char)a6);
LABEL_94:
    v50 = v82;
    NtfsRemoveNtfsMcbEntry(v82, v26);
    if ( v50 == *v73 + 400LL || v50 == *(_QWORD *)(a2 + 208) + 400LL )
    {
      FsRtlAddLargeMcbEntry((PLARGE_MCB)(a3 + 672), v26, Vbn, SectorCount);
      v10 = v66;
    }
    else
    {
      v10 = v66;
    }
LABEL_99:
    v6 = SectorCount + v26;
    v83 = v6;
  }
  if ( v60 )
    *(_QWORD *)v11 &= ~0x40000uLL;
  if ( v10 )
  {
    v51 = v67;
    FsRtlRemoveBaseMcbEntry((PBASE_MCB)(v67 + 16), v75 - v10, v10);
    if ( (!a1 || (*v11 & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0ppp_EtwWriteTransfer(
        v52,
        (unsigned int)bitmpsup_c3672,
        a2,
        *(_QWORD *)(a2 + 312),
        *(_QWORD *)(a2 + 312) - v10);
    }
    *(_QWORD *)(v51 + 48) -= v10;
    *(_QWORD *)(a2 + 312) -= v10;
  }
  NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(a2 + 72) + 184LL), 0);
  v53 = P;
  if ( P )
    ExFreePoolWithTag(P, 0);
  v54 = (_DWORD *)(a1 + 16);
  if ( a1 && (*v54 & 0x100000) != 0 || (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) == 0 )
  {
    v55 = v59;
  }
  else
  {
    v55 = v59;
    McTemplateU0pd_EtwWriteTransfer(v53, bitmpsup_c3693, a1, v59);
  }
  v56 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 184LL);
  if ( *(_QWORD *)(a3 + 184) == v56 && *(_DWORD *)(a3 + 256) == 32 )
  {
    if ( !a1 || (v56 = (unsigned int)*v54, (v56 & 0x100000) == 0) )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
        McTemplateU0pd_EtwWriteTransfer(v56, bitmpsup_c3702, a1, v55);
    }
  }
  return v55;
}

```

## disassembly

```asm
0x14015f670  mov     rax, rsp
0x14015f673  mov     [rax+20h], r9
0x14015f677  mov     [rax+18h], r8
0x14015f67b  mov     [rax+10h], rdx
0x14015f67f  mov     [rax+8], rcx
0x14015f683  push    rbx
0x14015f684  push    rsi
0x14015f685  push    rdi
0x14015f686  push    r12
0x14015f688  push    r13
0x14015f68a  push    r14
0x14015f68c  push    r15
0x14015f68e  sub     rsp, 100h
0x14015f695  mov     r12, r9
0x14015f698  mov     r14, r8
0x14015f69b  mov     rsi, rdx
0x14015f69e  mov     rbx, rcx
0x14015f6a1  mov     [rsp+138h+var_50], r8
0x14015f6a9  xor     r15d, r15d
0x14015f6ac  mov     [rax-0A8h], r15
0x14015f6b3  mov     [rsp+138h+SectorCount], r15
0x14015f6b8  mov     edi, r15d
0x14015f6bb  mov     [rsp+138h+var_C8], r15
0x14015f6c0  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14015f6c7  mov     [rax-80h], rdx
0x14015f6cb  mov     [rax-78h], rdx
0x14015f6cf  xor     r13b, r13b
0x14015f6d2  mov     [rsp+138h+var_E8], r13b
0x14015f6d7  mov     [rsp+138h+var_E7], dil
0x14015f6dc  mov     [rsp+138h+var_C0], r15
0x14015f6e1  mov     [rax-0B8h], r15
0x14015f6e8  lea     r13, [rcx+10h]
0x14015f6ec  test    rcx, rcx
0x14015f6ef  jz      short loc_14015F6FC
0x14015f6f1  mov     eax, [r13+0]
0x14015f6f5  bt      rax, 14h
0x14015f6fa  jb      short loc_14015F73A
0x14015f6fc  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 4
0x14015f703  jz      short loc_14015F73A
0x14015f705  lea     rax, [r8+190h]
0x14015f70c  mov     rcx, [rsp+138h+arg_20]
0x14015f714  mov     [rsp+138h+WorkSpace], rcx
0x14015f719  mov     [rsp+138h+FinalCompressedSize], r12
0x14015f71e  mov     qword ptr [rsp+138h+UncompressedChunkSize], rax
0x14015f723  mov     qword ptr [rsp+138h+CompressedBufferSize], r14
0x14015f728  mov     r9, rsi
0x14015f72b  mov     r8, rbx
0x14015f72e  lea     rdx, bitmpsup_c3189
0x14015f735  call    McTemplateU0ppppii_EtwWriteTransfer
0x14015f73a  mov     [rsp+138h+var_60], r13
0x14015f742  test    rbx, rbx
0x14015f745  jz      short loc_14015F752
0x14015f747  mov     eax, [r13+0]
0x14015f74b  bt      rax, 14h
0x14015f750  jb      short loc_14015F787
0x14015f752  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14015f759  jz      short loc_14015F787
0x14015f75b  mov     r9, [r14+0B8h]
0x14015f762  mov     rax, [rsp+138h+arg_20]
0x14015f76a  mov     qword ptr [rsp+138h+UncompressedChunkSize], rax
0x14015f76f  mov     qword ptr [rsp+138h+CompressedBufferSize], r12
0x14015f774  mov     r9, [r9+8]
0x14015f778  mov     r8, rsi
0x14015f77b  lea     rdx, bitmpsup_c3201
0x14015f782  call    McTemplateU0pppi_EtwWriteTransfer
0x14015f787  lea     rax, [rsi+30h]
0x14015f78b  mov     [rsp+138h+var_90], rax
0x14015f793  lea     rdx, [r14+0B8h]
0x14015f79a  mov     [rsp+138h+var_B0], rdx
0x14015f7a2  mov     rax, [rax]
0x14015f7a5  mov     rcx, [rax+0B8h]
0x14015f7ac  cmp     [rdx], rcx
0x14015f7af  jnz     short loc_14015F811
0x14015f7b1  cmp     dword ptr [r14+100h], 20h ; ' '
0x14015f7b9  jnz     short loc_14015F811
0x14015f7bb  test    rbx, rbx
0x14015f7be  jz      short loc_14015F7CB
0x14015f7c0  mov     eax, [r13+0]
0x14015f7c4  bt      rax, 14h
0x14015f7c9  jb      short loc_14015F811
0x14015f7cb  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 2
0x14015f7d2  jz      short loc_14015F811
0x14015f7d4  lea     rax, [r14+190h]
0x14015f7db  mov     rcx, [rsp+138h+arg_20]
0x14015f7e3  mov     [rsp+138h+WorkSpace], rcx
0x14015f7e8  mov     [rsp+138h+FinalCompressedSize], r12
0x14015f7ed  mov     qword ptr [rsp+138h+UncompressedChunkSize], rax
0x14015f7f2  mov     qword ptr [rsp+138h+CompressedBufferSize], r14
0x14015f7f7  mov     r9, rsi
0x14015f7fa  mov     r8, rbx
0x14015f7fd  lea     rdx, bitmpsup_c3212
0x14015f804  call    McTemplateU0ppppii_EtwWriteTransfer
0x14015f809  mov     rdx, [rsp+138h+var_B0]
0x14015f811  lea     rax, [r14+100h]
0x14015f818  mov     [rsp+138h+var_68], rax
0x14015f820  cmp     dword ptr [rax], 80h
0x14015f826  jnz     short loc_14015F851
0x14015f828  mov     rax, [rdx]
0x14015f82b  cmp     dword ptr [rax+8], 10h
0x14015f82f  jb      short loc_14015F851
0x14015f831  mov     rcx, [rsi+28h]
0x14015f835  test    rcx, rcx
0x14015f838  jz      short loc_14015F843
0x14015f83a  cmp     rax, [rcx+0B8h]
0x14015f841  jz      short loc_14015F851
0x14015f843  mov     dword ptr [rsp+138h+var_D4], r15d
0x14015f848  test    dword ptr [rax+4], 8000h
0x14015f84f  jz      short loc_14015F859
0x14015f851  mov     dword ptr [rsp+138h+var_D4], 2
0x14015f859  xor     r8d, r8d
0x14015f85c  mov     rdx, [rsi+48h]
0x14015f860  mov     rcx, rbx
0x14015f863  call    NtfsAcquireExclusiveScbEx
0x14015f868  nop
0x14015f869  mov     eax, cs:NtfsTrimListLengthThreshold
0x14015f86f  test    eax, eax
0x14015f871  jz      short loc_14015F897
0x14015f873  mov     r8, [rbx+68h]
0x14015f877  mov     r9d, [r8+5E8h]
0x14015f87e  cmp     r9d, eax
0x14015f881  jbe     short loc_14015F897
0x14015f883  cmp     byte ptr [rbx+20h], 0Dh
0x14015f887  jnz     loc_140160170
0x14015f88d  cmp     byte ptr [rbx+21h], 2
0x14015f891  jz      loc_140160170
0x14015f897  lea     rax, [rsi+4]
0x14015f89b  mov     [rsp+138h+var_58], rax
0x14015f8a3  mov     eax, [rax]
0x14015f8a5  test    al, al
0x14015f8a7  jns     short loc_14015F8C0
0x14015f8a9  mov     r9d, 2
0x14015f8af  mov     r8d, 0Ah
0x14015f8b5  mov     rdx, rsi
0x14015f8b8  mov     rcx, rbx
0x14015f8bb  call    NtfsScanEntireBitmap
0x14015f8c0  mov     [rsp+138h+var_88], r12
0x14015f8c8  cmp     r12, [rsp+138h+arg_20]
0x14015f8d0  jg      loc_140160028
0x14015f8d6  lea     rax, [r14+190h]
0x14015f8dd  mov     [rsp+138h+var_48], rax
0x14015f8e5  mov     [rsp+138h+WorkSpace], r15
0x14015f8ea  mov     [rsp+138h+FinalCompressedSize], r15
0x14015f8ef  mov     qword ptr [rsp+138h+UncompressedChunkSize], r15
0x14015f8f4  mov     qword ptr [rsp+138h+CompressedBufferSize], r15
0x14015f8f9  lea     r9, [rsp+138h+SectorCount]
0x14015f8fe  lea     r8, [rsp+138h+Vbn]
0x14015f906  mov     rdx, r12
0x14015f909  mov     rcx, rax
0x14015f90c  call    NtfsLookupNtfsMcbEntryWithSyncFlag
0x14015f911  test    al, al
0x14015f913  jz      loc_140160028
0x14015f919  mov     r12, [rsp+138h+Vbn]
0x14015f921  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14015f925  jz      loc_14016000E
0x14015f92b  mov     [rsp+138h+var_A0], r15
0x14015f933  mov     [rsp+138h+var_98], r15
0x14015f93b  mov     rdi, [rsp+138h+SectorCount]
0x14015f940  mov     rcx, [rsp+138h+arg_18]
0x14015f948  lea     rax, [rdi+rcx]
0x14015f94c  mov     rdx, [rsp+138h+arg_20]
0x14015f954  cmp     rax, rdx
0x14015f957  jle     short loc_14015F967
0x14015f959  mov     rdi, rdx
0x14015f95c  sub     rdi, rcx
0x14015f95f  inc     rdi
0x14015f962  mov     [rsp+138h+SectorCount], rdi
0x14015f967  lea     rax, [r14+200h]
0x14015f96e  mov     [rsp+138h+var_70], rax
0x14015f976  test    dword ptr [rax], 800000h
0x14015f97c  jnz     short loc_14015F99F
0x14015f97e  mov     rax, [rsp+138h+var_68]
0x14015f986  cmp     dword ptr [rax], 80h
0x14015f98c  jnz     short loc_14015F9C6
0x14015f98e  cmp     dword ptr [r14+1C4h], 0
0x14015f996  jz      short loc_14015F9C6
0x14015f998  test    byte ptr [r14+4], 20h
0x14015f99d  jz      short loc_14015F9C6
0x14015f99f  movzx   ecx, byte ptr [rsi+1E8h]
0x14015f9a6  mov     rax, rdi
0x14015f9a9  shl     rax, cl
0x14015f9ac  mov     edx, 0FFFFFFFFh
0x14015f9b1  cmp     rax, rdx
0x14015f9b4  jbe     short loc_14015F9C6
0x14015f9b6  mov     ecx, [rsi+1E8h]
0x14015f9bc  mov     edi, edx
0x14015f9be  shr     rdi, cl
0x14015f9c1  mov     [rsp+138h+SectorCount], rdi
0x14015f9c6  mov     [rsp+138h+var_A0], r12
0x14015f9ce  mov     [rsp+138h+var_98], rdi
0x14015f9d6  test    rbx, rbx
0x14015f9d9  jz      short loc_14015F9E6
0x14015f9db  mov     eax, [r13+0]
0x14015f9df  bt      rax, 14h
0x14015f9e4  jb      short loc_14015FA17
0x14015f9e6  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14015f9ed  jz      short loc_14015FA17
0x14015f9ef  mov     rax, [rsp+138h+var_B0]
0x14015f9f7  mov     r9, [rax]
0x14015f9fa  mov     qword ptr [rsp+138h+UncompressedChunkSize], rdi
0x14015f9ff  mov     qword ptr [rsp+138h+CompressedBufferSize], r12
0x14015fa04  mov     r9, [r9+8]
0x14015fa08  mov     r8, rsi
0x14015fa0b  lea     rdx, bitmpsup_c3317
0x14015fa12  call    McTemplateU0pppi_EtwWriteTransfer
0x14015fa17  xor     r15b, r15b
0x14015fa1a  mov     [rsp+138h+var_E6], r15b
0x14015fa1f  xor     r8d, r8d
0x14015fa22  mov     rdx, rsi
0x14015fa25  mov     rcx, rbx
0x14015fa28  call    NtfsGetDeallocatedClusters
0x14015fa2d  mov     [rsp+138h+var_C0], rax
0x14015fa32  test    rax, rax
0x14015fa35  jnz     short loc_14015FA41
0x14015fa37  mov     r15b, 1
0x14015fa3a  mov     [rsp+138h+var_E6], r15b
0x14015fa3f  jmp     short loc_14015FA5A
0x14015fa41  lea     rcx, [rax+10h]; Mcb
0x14015fa45  mov     r9, rdi; SectorCount
0x14015fa48  mov     r8, r12; Lbn
0x14015fa4b  mov     rdx, r12; Vbn
0x14015fa4e  call    cs:__imp_FsRtlAddBaseMcbEntry
0x14015fa55  nop     dword ptr [rax+rax+00h]
0x14015fa5a  jmp     loc_14015FB08
0x14015fa5f  mov     edx, eax
0x14015fa61  movzx   eax, cs:NtfsStatusDebugFlags
0x14015fa68  test    al, al
0x14015fa6a  jz      short loc_14015FAC0
0x14015fa6c  test    edx, edx
0x14015fa6e  jz      short loc_14015FAC0
0x14015fa70  cmp     edx, 126h
0x14015fa76  jz      short loc_14015FAC0
0x14015fa78  lea     eax, [rdx-12Ah]
0x14015fa7e  cmp     eax, 1
0x14015fa81  jbe     short loc_14015FAC0
0x14015fa83  cmp     edx, 0FFFFFFEDh
0x14015fa86  jnb     short loc_14015FAC0
0x14015fa88  cmp     edx, 0C0000016h
0x14015fa8e  jz      short loc_14015FAC0
0x14015fa90  lea     eax, [rdx+7FFFFFFBh]
0x14015fa96  cmp     eax, 1
0x14015fa99  jbe     short loc_14015FAC0
0x14015fa9b  cmp     edx, 0C0000011h
0x14015faa1  jz      short loc_14015FAC0
0x14015faa3  cmp     edx, 103h
0x14015faa9  jz      short loc_14015FAC0
0x14015faab  cmp     edx, 0C00000D8h
0x14015fab1  jz      short loc_14015FAC0
0x14015fab3  xor     ecx, ecx
0x14015fab5  mov     r8d, 40D1Ah
0x14015fabb  call    NtfsStatusTraceAndDebugInternal
0x14015fac0  mov     r15b, 1
0x14015fac3  mov     [rsp+138h+var_E6], r15b
0x14015fac8  mov     r14, [rsp+138h+arg_10]
0x14015fad0  mov     rsi, [rsp+138h+arg_8]
0x14015fad8  mov     rbx, [rsp+138h+arg_0]
0x14015fae0  mov     rcx, [rsp+138h+var_88]
0x14015fae8  mov     [rsp+138h+arg_18], rcx
0x14015faf0  mov     r12, [rsp+138h+var_A0]
0x14015faf8  mov     rdi, [rsp+138h+var_98]
0x14015fb00  mov     r13, [rsp+138h+var_60]
0x14015fb08  test    r15b, r15b
0x14015fb0b  jnz     loc_1401601CC
0x14015fb11  mov     r8, [rsp+138h+var_C0]
0x14015fb16  add     [r8+30h], rdi
0x14015fb1a  mov     rdx, [r8+30h]
0x14015fb1e  test    rbx, rbx
0x14015fb21  jz      short loc_14015FB2E
0x14015fb23  mov     eax, [r13+0]
0x14015fb27  bt      rax, 14h
0x14015fb2c  jb      short loc_14015FB74
0x14015fb2e  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14015fb35  jz      short loc_14015FB74
0x14015fb37  mov     rcx, [rsi+138h]
0x14015fb3e  lea     rax, [rcx+rdi]
0x14015fb42  mov     [rsp+138h+var_F8], rax
0x14015fb47  mov     [rsp+138h+WorkSpace], rcx
0x14015fb4c  mov     eax, [r8+38h]
0x14015fb50  mov     dword ptr [rsp+138h+FinalCompressedSize], eax
0x14015fb54  mov     qword ptr [rsp+138h+UncompressedChunkSize], rdx
0x14015fb59  mov     rax, [r8+28h]
0x14015fb5d  mov     qword ptr [rsp+138h+CompressedBufferSize], rax
0x14015fb62  mov     r9, r8
0x14015fb65  mov     r8, rsi
0x14015fb68  lea     rdx, bitmpsup_c3377
0x14015fb6f  call    McTemplateU0ppiidii_EtwWriteTransfer
0x14015fb74  add     [rsi+138h], rdi
0x14015fb7b  add     [rbx+0B8h], rdi
0x14015fb82  mov     [rsp+138h+var_C8], rdi
0x14015fb87  lea     rax, [rdi+r12]
0x14015fb8b  mov     [rsp+138h+var_80], rax
0x14015fb93  mov     [rsp+138h+var_78], rax
0x14015fb9b  or      dword ptr [rbx+4], 1000h
0x14015fba2  mov     eax, dword ptr [rsp+138h+var_D4]
0x14015fba6  mov     [rsp+138h+CompressedBufferSize], eax; char
0x14015fbaa  lea     r9, [rsp+138h+var_C8]
0x14015fbaf  mov     r8, r12; int
0x14015fbb2  mov     rdx, rsi; int
0x14015fbb5  mov     rcx, rbx; int
0x14015fbb8  call    NtfsFreeBitmapRun
0x14015fbbd  mov     al, 1
  ... truncated ...
```
