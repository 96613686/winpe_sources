# NtfsDeallocateRecord

- ea: `0x14015b900`
- end: `0x14015c6ee`
- name: `NtfsDeallocateRecord`
- size: `3566`
- prototype: `__int64 __fastcall(int, __int64, ULONG FromIndex, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14015af90`
- `0x14015cbc8`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d510`
- `0x140012e70`
- `0x14002b680`
- `0x14003f72c`
- `0x1400410a8`
- `0x140059440`
- `0x140059740`
- `0x14013c320`
- `0x14013f3c4`
- `0x140143730`
- `0x14014de30`
- `0x140150044`
- `0x140150c10`
- `0x1401597b8`
- `0x14015b900`
- `0x140162110`
- `0x1401623c0`
- `0x140163fc8`
- `0x14016a090`
- `0x14023b8b0`

## import_xrefs

- `ntoskrnl!RtlAreBitsSet` at `0x14015bb94`
- `ntoskrnl!RtlAreBitsSet` at `0x14015bb94`
- `ntoskrnl!RtlClearBits` at `0x14015bd6e`
- `ntoskrnl!RtlClearBits` at `0x14015bd6e`
- `ntoskrnl!RtlFindLastBackwardRunClear` at `0x14015be21`
- `ntoskrnl!RtlFindLastBackwardRunClear` at `0x14015c00e`
- `ntoskrnl!RtlFindLastBackwardRunClear` at `0x14015c463`
- `ntoskrnl!RtlFindLastBackwardRunClear` at `0x14015be21`
- `ntoskrnl!RtlFindLastBackwardRunClear` at `0x14015c00e`
- `ntoskrnl!RtlFindLastBackwardRunClear` at `0x14015c463`
- `ntoskrnl!CcPinRead` at `0x14015bb2a`
- `ntoskrnl!CcPinRead` at `0x14015bb2a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14015c235`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14015c235`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14015bc51`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14015bc51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015c2db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015c2db`
- `ntoskrnl!RtlInitializeBitMap` at `0x14015bb76`
- `ntoskrnl!RtlInitializeBitMap` at `0x14015c0ad`
- `ntoskrnl!RtlInitializeBitMap` at `0x14015c302`
- `ntoskrnl!RtlInitializeBitMap` at `0x14015bb76`
- `ntoskrnl!RtlInitializeBitMap` at `0x14015c0ad`
- `ntoskrnl!RtlInitializeBitMap` at `0x14015c302`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015c132`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14015c132`
- `ntoskrnl!CcUnpinData` at `0x14015bd96`
- `ntoskrnl!CcUnpinData` at `0x14015c057`
- `ntoskrnl!CcUnpinData` at `0x14015c434`
- `ntoskrnl!CcUnpinData` at `0x14015c6dd`
- `ntoskrnl!CcUnpinData` at `0x1402a88dd`
- `ntoskrnl!CcUnpinData` at `0x14015bd96`
- `ntoskrnl!CcUnpinData` at `0x14015c057`
- `ntoskrnl!CcUnpinData` at `0x14015c434`
- `ntoskrnl!CcUnpinData` at `0x14015c6dd`
- `ntoskrnl!CcUnpinData` at `0x1402a88dd`
- `ntoskrnl!ExRaiseStatus` at `0x14015c270`
- `ntoskrnl!ExRaiseStatus` at `0x14015c29e`
- `ntoskrnl!ExRaiseStatus` at `0x14015c270`
- `ntoskrnl!ExRaiseStatus` at `0x14015c29e`
- `ntoskrnl!CcFlushCache` at `0x14015bf01`
- `ntoskrnl!CcFlushCache` at `0x14015bf01`

## pseudocode

```c
__int64 __fastcall NtfsDeallocateRecord(__int64 a1, __int64 a2, ULONG FromIndex, void *a4)
{
  unsigned __int64 v5; // r15
  union _LARGE_INTEGER *v8; // rsi
  union _LARGE_INTEGER v9; // r12
  int v10; // ecx
  __int64 v11; // rdx
  int v12; // r10d
  __int64 v13; // r9
  __int64 v14; // r13
  __int64 v15; // r12
  ULONG v16; // edi
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // r9d
  _QWORD *v21; // rcx
  _QWORD *v22; // r12
  _QWORD *i; // rax
  union _LARGE_INTEGER *v24; // rdi
  union _LARGE_INTEGER **QuadPart; // rcx
  unsigned int v26; // edi
  __int64 LowPart; // rax
  unsigned int v28; // edi
  signed int v29; // edx
  union _LARGE_INTEGER v30; // r9
  union _LARGE_INTEGER v31; // rdi
  ULONG LastBackwardRunClear; // eax
  unsigned __int64 v33; // rax
  unsigned int v34; // ecx
  PVOID PoolWithTag; // rax
  union _LARGE_INTEGER *v36; // rcx
  _QWORD *v37; // rdx
  PVOID *v38; // rax
  _QWORD *v39; // r8
  PVOID *v40; // rdx
  union _LARGE_INTEGER **v41; // rdx
  _QWORD *v42; // rdx
  union _LARGE_INTEGER v43; // rdx
  signed __int64 v44; // rdx
  signed __int64 v45; // r8
  union _LARGE_INTEGER v46; // rdx
  signed __int64 v47; // r8
  signed __int64 v48; // r9
  PVOID *Bcb; // [rsp+20h] [rbp-118h]
  int Buffer; // [rsp+28h] [rbp-110h]
  ULONG StartingIndex; // [rsp+70h] [rbp-C8h]
  PVOID v53; // [rsp+78h] [rbp-C0h] BYREF
  ULONG StartingRunIndex; // [rsp+80h] [rbp-B8h] BYREF
  union _LARGE_INTEGER v55; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+90h] [rbp-A8h] BYREF
  unsigned int v57; // [rsp+98h] [rbp-A0h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+A0h] [rbp-98h] BYREF
  int v59; // [rsp+B0h] [rbp-88h]
  __int64 v60; // [rsp+B8h] [rbp-80h]
  PVOID v61; // [rsp+C0h] [rbp-78h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+C8h] [rbp-70h] BYREF
  unsigned __int64 v63; // [rsp+D0h] [rbp-68h]
  union _LARGE_INTEGER v64; // [rsp+D8h] [rbp-60h]
  union _LARGE_INTEGER *v65; // [rsp+E0h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+E8h] [rbp-50h] BYREF
  unsigned __int64 v67; // [rsp+F8h] [rbp-40h]
  int v68; // [rsp+148h] [rbp+10h] BYREF
  void *v69; // [rsp+158h] [rbp+20h]

  v69 = a4;
  v5 = FromIndex;
  IoStatus = 0;
  v53 = 0;
  v8 = *(union _LARGE_INTEGER **)a2;
  v65 = *(union _LARGE_INTEGER **)a2;
  if ( FromIndex < 0x10 && v8 == *(union _LARGE_INTEGER **)(v8[24].QuadPart + 48) )
  {
    NtfsAttachCorruptionSimple(a1, 1, 2050, 273915, 0, Buffer);
    NtfsAttachRepairInfoPriv(a1, 0, 0, 0xD100042DFBLL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225522LL, 273915);
    NtfsRaiseStatusInternal(a1, -1073741774, 0, 0, 273915);
    __debugbreak();
  }
  NtfsAcquireExclusiveScbEx(a1, v8, 0);
  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  StartingRunIndex = 0;
  v60 = 0;
  v57 = 0;
  LOBYTE(v68) = 0;
  StartingIndex = 0;
  v61 = 0;
  v9 = v8[24];
  v64 = v9;
  v10 = *(_DWORD *)(a2 + 28);
  v59 = v10;
  v11 = *(unsigned int *)(a2 + 36);
  v55.LowPart = *(_DWORD *)(a2 + 36);
  v12 = *(_DWORD *)(a2 + 32);
  v13 = 712;
  if ( *(union _LARGE_INTEGER **)(v9.QuadPart + 48) != v8 )
    v13 = 742;
  if ( !*(_QWORD *)(a2 + 8) && *(_BYTE *)(*(_QWORD *)a4 + 8LL) )
  {
    NtfsUninitializeRecordAllocation(a2, v11, 742, v13);
    v10 = v59;
    LODWORD(v11) = v55.LowPart;
  }
  if ( !*((_BYTE *)&v8->LowPart + v13) )
    NtfsInitializeRecordAllocation(a1, (int)v8, (int)a4, v10, v12, v11, a2);
  v14 = *(_QWORD *)(a2 + 8);
  if ( !v14 )
  {
    RtlInitializeBitMap(
      &BitMapHeader,
      (PULONG)(*(_QWORD *)a4 + *(unsigned __int16 *)(*(_QWORD *)a4 + 20LL)),
      *(_DWORD *)(a2 + 16));
    v21 = (_QWORD *)(v5 >> 3);
    LOBYTE(v68) = *((_BYTE *)BitMapHeader.Buffer + (v5 >> 3)) & ~*((_BYTE *)&BitMask + (v5 & 7));
    goto LABEL_28;
  }
  if ( (*(_DWORD *)(v14 + 200) & 0x20) == 0 )
    NtfsUpdateScbFromAttribute(a1, *(_QWORD *)(a2 + 8), 0);
  if ( v8 != *(union _LARGE_INTEGER **)(v9.QuadPart + 48) )
    NtfsSnapshotScb(a1, v14);
  if ( !*(_QWORD *)(v14 + 280) )
    NtfsCreateInternalAttributeStream(a1, v14, 0, 0, (__int64)L"$&", 0);
  v15 = ((unsigned int)v5 >> 3) & 0x1FFFF000;
  v60 = v15;
  v57 = ((unsigned int)v5 >> 3) & 0x1FFFF000;
  StartingIndex = v5 & 0x7FFF;
  v16 = (*(_DWORD *)(a2 + 16) >> 3) - v15;
  if ( v16 > 0x1000 )
    v16 = 4096;
  FileOffset.QuadPart = ((unsigned int)v5 >> 3) & 0x1FFFF000;
  v17 = *(_QWORD *)(v14 + 24);
  if ( v15 > v17
    || (v18 = *(_QWORD *)(v14 + 192), v19 = *(_QWORD *)(v18 + 7776), v15 > v19)
    || v16 > v17 - v15
    || v16 > v19 - v15 )
  {
    NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 329193, v13, *(_QWORD *)(v14 + 184) + 8LL, *(_QWORD *)(v14 + 184), 0);
    NtfsAttachRepairInfoPriv(a1, 256, 0, 0x64000505E9LL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 329193);
    NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v14 + 184) + 8, *(_QWORD *)(v14 + 184), 329193);
    __debugbreak();
  }
  if ( (*(_DWORD *)(v14 + 512) & 1) != 0 )
    FileOffset.QuadPart = (unsigned int)v15 - *(_QWORD *)(v18 + 1952);
  if ( !CcPinRead(*(PFILE_OBJECT *)(v14 + 280), &FileOffset, v16, *(_DWORD *)(a1 + 12) & 1, &v53, &v61) )
  {
    NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 329219);
    __debugbreak();
  }
  RtlInitializeBitMap(&BitMapHeader, (PULONG)v61, 8 * v16);
  if ( RtlAreBitsSet(&BitMapHeader, StartingIndex, 1u) )
  {
    v56 = v5 & 0x7FFF | 0x100000000LL;
    NtfsWriteLog(
      a1,
      v14,
      (_DWORD)v53,
      22,
      (__int64)&v56,
      8,
      21,
      (__int64)&v56,
      8,
      ((unsigned int)v5 >> 3) & 0x1FFFF000,
      0,
      0,
      v16);
LABEL_28:
    v22 = (_QWORD *)(a1 + 168);
    for ( i = *(_QWORD **)(a1 + 168); ; i = (_QWORD *)*i )
    {
      v24 = 0;
      if ( i == v22 )
        break;
      v24 = (union _LARGE_INTEGER *)(i - 2);
      if ( (union _LARGE_INTEGER *)i[2] == v8 )
        break;
    }
    if ( !v24 )
    {
      v24 = (union _LARGE_INTEGER *)ExAllocateFromLookasideListEx(&NtfsDeallocatedRecordsLookasideList);
      QuadPart = (union _LARGE_INTEGER **)v8[73].QuadPart;
      if ( *QuadPart != &v8[72] )
        goto LABEL_32;
      v24->QuadPart = (LONGLONG)&v8[72];
      v24[1].QuadPart = (LONGLONG)QuadPart;
      *QuadPart = v24;
      v8[73].QuadPart = (LONGLONG)v24;
      v21 = *(_QWORD **)(a1 + 176);
      if ( (_QWORD *)*v21 != v22 )
        goto LABEL_32;
      v24[2].QuadPart = (LONGLONG)v22;
      v24[3].QuadPart = (LONGLONG)v21;
      *v21 = v24 + 2;
      *(_QWORD *)(a1 + 176) = v24 + 2;
      v24[4].QuadPart = (LONGLONG)v8;
      v24[5].QuadPart = 32;
    }
    LowPart = v24[5].LowPart;
    if ( v24[5].HighPart != (_DWORD)LowPart )
      goto LABEL_38;
    v33 = 8 * LowPart;
    v63 = v33;
    v67 = v33;
    if ( v33 > 0xFFFFFFFF )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225859LL, 274210);
      ExRaiseStatus(-1073741437);
    }
    v34 = v33 + 48;
    if ( (int)v33 + 48 < (unsigned int)v33 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225859LL, 274214);
      ExRaiseStatus(-1073741437);
    }
    FileOffset.QuadPart = v34;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x410), v34, 0x4466744Eu);
    v56 = (__int64)PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    {
      memset(PoolWithTag, 0, FileOffset.QuadPart);
      PoolWithTag = (PVOID)v56;
    }
    memmove(PoolWithTag, v24, ((unsigned int)v63 >> 1) + 48);
    v36 = (union _LARGE_INTEGER *)v56;
    *(_DWORD *)(v56 + 40) = 2 * v24[5].LowPart;
    v37 = (_QWORD *)v24->QuadPart;
    if ( *(union _LARGE_INTEGER **)(v24->QuadPart + 8) == v24 )
    {
      v38 = (PVOID *)v24[1].QuadPart;
      if ( *v38 == v24 )
      {
        *v38 = v37;
        v37[1] = v38;
        v39 = (_QWORD *)v24[2].QuadPart;
        if ( (union _LARGE_INTEGER *)v39[1] == &v24[2] )
        {
          v40 = (PVOID *)v24[3].QuadPart;
          if ( *v40 == &v24[2] )
          {
            *v40 = v39;
            v39[1] = v40;
            v41 = (union _LARGE_INTEGER **)v8[73].QuadPart;
            if ( *v41 == &v8[72] )
            {
              v36->QuadPart = (LONGLONG)&v8[72];
              v36[1].QuadPart = (LONGLONG)v41;
              *v41 = v36;
              v8[73].QuadPart = (LONGLONG)v36;
              v42 = *(_QWORD **)(a1 + 176);
              if ( (_QWORD *)*v42 == v22 )
              {
                v36[2].QuadPart = (LONGLONG)v22;
                v36[3].QuadPart = (LONGLONG)v42;
                *v42 = v36 + 2;
                *(_QWORD *)(a1 + 176) = v36 + 2;
                if ( v24[5].LowPart == 32 )
                  ExFreeToLookasideListEx(&NtfsDeallocatedRecordsLookasideList, v24);
                else
                  ExFreePoolWithTag(v24, 0);
                v24 = (union _LARGE_INTEGER *)v56;
LABEL_38:
                *(&v24[6].LowPart + (unsigned int)v24[5].HighPart++) = v5;
                if ( v14 )
                {
                  if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
                    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 4) != 0 )
                  {
                    McTemplateU0ppdd_EtwWriteTransfer(
                      (_DWORD)v21,
                      (unsigned int)"[",
                      a1,
                      (unsigned int)&BitMapHeader,
                      StartingIndex,
                      1);
                  }
                  RtlClearBits(&BitMapHeader, StartingIndex, 1u);
                  if ( (_DWORD)v5 == *(_DWORD *)(a2 + 24) )
                  {
                    LastBackwardRunClear = RtlFindLastBackwardRunClear(&BitMapHeader, StartingIndex, &StartingRunIndex);
                    v28 = v60;
                    while ( LastBackwardRunClear == StartingIndex + 1 && v28 )
                    {
                      v28 -= 4096;
                      v57 = v28;
                      StartingIndex = 0x7FFF;
                      if ( v53 )
                      {
                        CcUnpinData(v53);
                        v53 = 0;
                      }
                      NtfsMapStream(a1, v14, v28);
                      RtlInitializeBitMap(&BitMapHeader, (PULONG)v61, 0x8000u);
                      if ( _bittest64((const signed __int64 *)BitMapHeader.Buffer + 511, 0x3Fu) )
                      {
                        v28 += 4096;
                        v57 = v28;
                        break;
                      }
                      LastBackwardRunClear = RtlFindLastBackwardRunClear(&BitMapHeader, 0x7FFFu, &StartingRunIndex);
                    }
                  }
                  else
                  {
                    v28 = v60;
                  }
                  if ( v53 )
                  {
                    CcUnpinData(v53);
                    v53 = 0;
                  }
                }
                else
                {
                  LODWORD(Bcb) = 1;
                  NtfsChangeAttributeValue(
                    a1,
                    v8[23].QuadPart,
                    (unsigned int)v5 >> 3,
                    (int)&v68,
                    (SIZE_T)Bcb,
                    0,
                    0,
                    0,
                    0,
                    v69);
                  if ( (_DWORD)v5 == *(_DWORD *)(a2 + 24) )
                    RtlFindLastBackwardRunClear(&BitMapHeader, v5, &StartingRunIndex);
                  v28 = v60;
                }
                ++*(_DWORD *)(a2 + 20);
                if ( (_DWORD)v5 != *(_DWORD *)(a2 + 24) )
                  goto LABEL_48;
                v29 = StartingRunIndex + 8 * v28;
                *(_DWORD *)(a2 + 24) = v29 - 1;
                if ( v8 == *(union _LARGE_INTEGER **)(v64.QuadPart + 48) )
                  goto LABEL_48;
                v30 = v8[3];
                if ( v30.QuadPart <= v59 * (__int64)(v55.LowPart + v29) )
                  goto LABEL_48;
                v31.QuadPart = v59 * (__int64)v29;
                if ( v8 == *(union _LARGE_INTEGER **)(v64.QuadPart + 200) && v31.QuadPart < 0x10000 )
                  goto LABEL_48;
                v55.QuadPart = v59 * (__int64)v29;
                if ( (*(_DWORD *)(a1 + 4) & 0x10) == 0 )
                  goto LABEL_59;
                if ( v30.QuadPart + 8 < *(_QWORD *)(v8[62].QuadPart + 24) )
                {
                  v55 = v30;
                }
                else
                {
                  v43.QuadPart = v30.QuadPart - (unsigned int)(*(_DWORD *)(v64.QuadPart + 356) << 7);
                  v55 = v43;
                  if ( v43.QuadPart < v31.QuadPart )
                  {
                    v55 = v31;
LABEL_59:
                    v30.LowPart = v31.LowPart;
                    goto LABEL_60;
                  }
                  v30.LowPart = v43.LowPart;
                }
LABEL_60:
                if ( v8[32].LowPart == 160 )
                {
                  CcFlushCache(
                    (PSECTION_OBJECT_POINTERS)(v8[36].QuadPart + 16),
                    &v55,
                    v8[4].LowPart - v30.LowPart,
                    &IoStatus);
                  NtfsNormalizeAndCleanupTransaction(a1, &IoStatus);
                }
                NtfsDeleteAllocation(a1, 0x7FFFFFFFFFFFFFFFLL, 1, 0);
                if ( (v8[25].LowPart & 0x20000) != 0 )
                {
                  v44 = v8[58].QuadPart;
                  if ( v44 < v31.QuadPart )
                    goto LABEL_113;
                  if ( v8[5].QuadPart <= v31.QuadPart )
                    goto LABEL_63;
                  if ( !*(_QWORD *)(v8[36].QuadPart + 16) || v31.QuadPart == 0x7FFFFFFFFFFFFFFFLL )
                  {
LABEL_113:
                    v8[58] = v31;
                  }
                  else
                  {
                    v45 = (v31.QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL;
                    if ( v45 < v44 )
                      v8[58].QuadPart = v45;
                  }
                }
LABEL_63:
                v8[5] = v31;
                if ( (v8[25].LowPart & 0x20000) == 0 || v8[4].QuadPart >= v31.QuadPart )
                  goto LABEL_64;
                v46 = v31;
                if ( v31.QuadPart >= v8[58].QuadPart )
                  v46 = v8[58];
                if ( v46.QuadPart <= v31.QuadPart )
                  goto LABEL_64;
                if ( (v8[25].LowPart & 0x20000) != 0 )
                {
                  v47 = v8[58].QuadPart;
                  if ( v47 < v46.QuadPart )
                  {
LABEL_125:
                    v8[58] = v46;
                    goto LABEL_126;
                  }
                  if ( v8[5].QuadPart > v46.QuadPart )
                  {
                    if ( *(_QWORD *)(v8[36].QuadPart + 16) && v46.QuadPart != 0x7FFFFFFFFFFFFFFFLL )
                    {
                      v48 = (v46.QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL;
                      if ( v48 < v47 )
                        v8[58].QuadPart = v48;
                      goto LABEL_126;
                    }
                    goto LABEL_125;
                  }
                }
LABEL_126:
                v8[5] = v46;
LABEL_64:
                v8[4] = v31;
                NtfsWriteFileSizes(a1, (_DWORD)v8, 0, 0, 1, 1);
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))NtfsSetCcFileSizes)(
                  (union _LARGE_INTEGER)v8[35].QuadPart,
                  v8,
                  &v8[3]);
                ++v8[84].HighPart;
LABEL_48:
                v26 = 0;
                goto LABEL_127;
              }
            }
          }
        }
      }
    }
LABEL_32:
    __fastfail(3u);
  }
  if ( v53 )
  {
    CcUnpinData(v53);
    v53 = 0;
  }
  NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 274113, v20, *(_QWORD *)(v14 + 184) + 8LL, *(_QWORD *)(v14 + 184), 0);
  NtfsAttachRepairInfoPriv(a1, 256, *(_QWORD *)v69, 0xAA00042EC1LL);
  v26 = -1073741774;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225522LL, 274115);
LABEL_127:
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))NtfsReleaseFcbEx)(a1, (union _LARGE_INTEGER)v8[23].QuadPart, 0);
  if ( v53 )
    CcUnpinData(v53);
  if ( *(_DWORD *)(a2 + 44) > (unsigned int)v5 )
    *(_DWORD *)(a2 + 44) = v5;
  return v26;
}

```

## disassembly

```asm
0x14015b900  mov     [rsp+arg_18], r9
0x14015b905  mov     [rsp+arg_0], rcx
0x14015b90a  push    rbx
0x14015b90b  push    rsi
0x14015b90c  push    rdi
0x14015b90d  push    r12
0x14015b90f  push    r13
0x14015b911  push    r14
0x14015b913  push    r15
0x14015b915  sub     rsp, 100h
0x14015b91c  mov     rdi, r9
0x14015b91f  mov     r15d, r8d
0x14015b922  mov     rbx, rdx
0x14015b925  mov     r14, rcx
0x14015b928  xorps   xmm0, xmm0
0x14015b92b  movups  xmmword ptr [rsp+138h+IoStatus], xmm0
0x14015b933  xor     r12d, r12d
0x14015b936  mov     [rsp+138h+var_C0], r12
0x14015b93b  mov     rsi, [rdx]
0x14015b93e  mov     [rsp+138h+var_58], rsi
0x14015b946  mov     rax, [rsi+0C0h]
0x14015b94d  cmp     r15d, 10h
0x14015b951  jb      loc_14015C667
0x14015b957  mov     [rsp+138h+var_C4], r12d
0x14015b95c  xor     r8d, r8d
0x14015b95f  mov     rdx, rsi
0x14015b962  call    NtfsAcquireExclusiveScbEx
0x14015b967  nop
0x14015b968  xor     eax, eax
0x14015b96a  mov     qword ptr [rsp+138h+BitMapHeader+4], rax
0x14015b972  mov     qword ptr [rsp+138h+BitMapHeader.SizeOfBitMap], rax
0x14015b97a  mov     [rsp+138h+StartingRunIndex], r12d
0x14015b982  mov     eax, r12d
0x14015b985  mov     [rsp+138h+var_80], rax
0x14015b98d  mov     [rsp+138h+var_A0], eax
0x14015b994  mov     byte ptr [rsp+138h+arg_8], al
0x14015b99b  mov     [rsp+138h+StartingIndex], r12d
0x14015b9a0  mov     [rsp+138h+var_78], r12
0x14015b9a8  mov     r12, [rsi+0C0h]
0x14015b9af  mov     [rsp+138h+var_60], r12
0x14015b9b7  mov     ecx, [rbx+1Ch]
0x14015b9ba  mov     [rsp+138h+var_88], ecx
0x14015b9c1  mov     edx, [rbx+24h]
0x14015b9c4  mov     dword ptr [rsp+138h+var_B0], edx
0x14015b9cb  mov     r10d, [rbx+20h]
0x14015b9cf  mov     r9d, 2C8h
0x14015b9d5  mov     r8d, 2E6h
0x14015b9db  cmp     [r12+30h], rsi
0x14015b9e0  cmovnz  r9d, r8d
0x14015b9e4  cmp     [rbx+8], rax
0x14015b9e8  jnz     short loc_14015B9F7
0x14015b9ea  mov     rax, [rdi]
0x14015b9ed  cmp     byte ptr [rax+8], 0
0x14015b9f1  jnz     loc_14015C3E2
0x14015b9f7  cmp     byte ptr [r9+rsi], 0
0x14015b9fc  jz      loc_14015C3FD
0x14015ba02  mov     r13, [rbx+8]
0x14015ba06  test    r13, r13
0x14015ba09  jz      loc_14015C2EC
0x14015ba0f  mov     eax, [r13+0C8h]
0x14015ba16  test    al, 20h
0x14015ba18  jz      loc_14015C421
0x14015ba1e  cmp     rsi, [r12+30h]
0x14015ba23  jnz     loc_14015C34B
0x14015ba29  cmp     qword ptr [r13+118h], 0
0x14015ba31  jnz     short loc_14015BA59
0x14015ba33  mov     [rsp+138h+Buffer], 0
0x14015ba3c  lea     rax, asc_140062090; "$&"
0x14015ba43  mov     [rsp+138h+Bcb], rax
0x14015ba48  xor     r9d, r9d
0x14015ba4b  xor     r8d, r8d
0x14015ba4e  mov     rdx, r13
0x14015ba51  mov     rcx, r14
0x14015ba54  call    NtfsCreateInternalAttributeStream
0x14015ba59  mov     r12d, r15d
0x14015ba5c  shr     r12d, 3
0x14015ba60  and     r12d, 1FFFF000h
0x14015ba67  mov     [rsp+138h+var_80], r12
0x14015ba6f  mov     [rsp+138h+var_A0], r12d
0x14015ba77  mov     eax, r15d
0x14015ba7a  and     eax, 7FFFh
0x14015ba7f  mov     [rsp+138h+StartingIndex], eax
0x14015ba83  mov     edi, [rbx+10h]
0x14015ba86  shr     edi, 3
0x14015ba89  sub     edi, r12d
0x14015ba8c  mov     eax, 1000h
0x14015ba91  cmp     edi, eax
0x14015ba93  cmova   edi, eax
0x14015ba96  mov     qword ptr [rsp+138h+FileOffset], r12
0x14015ba9e  mov     rcx, [r13+18h]
0x14015baa2  cmp     r12, rcx
0x14015baa5  jg      loc_14015C35B
0x14015baab  mov     r8, [r13+0C0h]
0x14015bab2  mov     rax, [r8+1E60h]
0x14015bab9  cmp     r12, rax
0x14015babc  jg      loc_14015C35B
0x14015bac2  mov     edx, edi
0x14015bac4  sub     rcx, r12
0x14015bac7  cmp     rdx, rcx
0x14015baca  jg      loc_14015C35B
0x14015bad0  sub     rax, r12
0x14015bad3  cmp     rdx, rax
0x14015bad6  jg      loc_14015C35B
0x14015badc  mov     eax, [r13+200h]
0x14015bae3  test    al, 1
0x14015bae5  jz      short loc_14015BAF9
0x14015bae7  mov     eax, r12d
0x14015baea  sub     rax, [r8+7A0h]
0x14015baf1  mov     qword ptr [rsp+138h+FileOffset], rax
0x14015baf9  mov     r9d, [r14+0Ch]
0x14015bafd  and     r9d, 1; Flags
0x14015bb01  lea     rax, [rsp+138h+var_78]
0x14015bb09  mov     [rsp+138h+Buffer], rax; Buffer
0x14015bb0e  lea     rax, [rsp+138h+var_C0]
0x14015bb13  mov     [rsp+138h+Bcb], rax; Bcb
0x14015bb18  mov     r8d, edi; Length
0x14015bb1b  lea     rdx, [rsp+138h+FileOffset]; FileOffset
0x14015bb23  mov     rcx, [r13+118h]; FileObject
0x14015bb2a  call    cs:__imp_CcPinRead
0x14015bb31  nop     dword ptr [rax+rax+00h]
0x14015bb36  test    al, al
0x14015bb38  jnz     short loc_14015BB5E
0x14015bb3a  movzx   eax, cs:NtfsStatusDebugFlags
0x14015bb41  mov     [rsp+138h+Bcb], 50603h
0x14015bb4a  xor     r9d, r9d
0x14015bb4d  xor     r8d, r8d
0x14015bb50  mov     edx, 0C00000D8h
0x14015bb55  mov     rcx, r14
0x14015bb58  call    NtfsRaiseStatusInternal
0x14015bb5d  int     3; Trap to Debugger
0x14015bb5e  lea     r8d, ds:0[rdi*8]; SizeOfBitMap
0x14015bb66  mov     rdx, [rsp+138h+var_78]; BitMapBuffer
0x14015bb6e  lea     rcx, [rsp+138h+BitMapHeader]; BitMapHeader
0x14015bb76  call    cs:__imp_RtlInitializeBitMap
0x14015bb7d  nop     dword ptr [rax+rax+00h]
0x14015bb82  mov     r8d, 1; Length
0x14015bb88  mov     edx, [rsp+138h+StartingIndex]; StartingIndex
0x14015bb8c  lea     rcx, [rsp+138h+BitMapHeader]; BitMapHeader
0x14015bb94  call    cs:__imp_RtlAreBitsSet
0x14015bb9b  nop     dword ptr [rax+rax+00h]
0x14015bba0  test    al, al
0x14015bba2  jz      loc_14015BC7B
0x14015bba8  mov     [rsp+138h+var_A8], 0
0x14015bbb4  mov     eax, [rsp+138h+StartingIndex]
0x14015bbb8  mov     dword ptr [rsp+138h+var_A8], eax
0x14015bbbf  mov     dword ptr [rsp+138h+var_A8+4], 1
0x14015bbca  mov     [rsp+138h+var_D8], edi
0x14015bbce  mov     [rsp+138h+var_E0], 0
0x14015bbd6  mov     [rsp+138h+var_E8], 0
0x14015bbde  mov     [rsp+138h+var_F0], r12
0x14015bbe3  mov     dword ptr [rsp+138h+var_F8], 8
0x14015bbeb  lea     rax, [rsp+138h+var_A8]
0x14015bbf3  mov     qword ptr [rsp+138h+var_100], rax
0x14015bbf8  mov     dword ptr [rsp+138h+var_108], 15h
0x14015bc00  mov     dword ptr [rsp+138h+Buffer], 8
0x14015bc08  lea     rax, [rsp+138h+var_A8]
0x14015bc10  mov     [rsp+138h+Bcb], rax
0x14015bc15  mov     r9d, 16h
0x14015bc1b  mov     r8, [rsp+138h+var_C0]
0x14015bc20  mov     rdx, r13
0x14015bc23  mov     rcx, r14
0x14015bc26  call    NtfsWriteLog
0x14015bc2b  lea     r12, [r14+0A8h]
0x14015bc32  mov     rax, [r12]
0x14015bc36  xor     edi, edi
0x14015bc38  cmp     rax, r12
0x14015bc3b  jnz     loc_14015BE3A
0x14015bc41  test    rdi, rdi
0x14015bc44  jnz     loc_14015BD1F
0x14015bc4a  lea     rcx, NtfsDeallocatedRecordsLookasideList; Lookaside
0x14015bc51  call    cs:__imp_ExAllocateFromLookasideListEx
0x14015bc58  nop     dword ptr [rax+rax+00h]
0x14015bc5d  mov     rdi, rax
0x14015bc60  lea     rax, [rsi+240h]
0x14015bc67  mov     rcx, [rax+8]
0x14015bc6b  cmp     [rcx], rax
0x14015bc6e  jz      loc_14015BFD9
0x14015bc74  mov     ecx, 3
0x14015bc79  int     29h; Win8: RtlFailFast(ecx)
0x14015bc7b  mov     rcx, [rsp+138h+var_C0]; Bcb
0x14015bc80  test    rcx, rcx
0x14015bc83  jnz     loc_14015C434
0x14015bc89  mov     rax, [r13+0B8h]
0x14015bc90  lea     rcx, [rax+8]
0x14015bc94  mov     edx, 2
0x14015bc99  mov     [rsp+138h+var_108], 0
0x14015bc9e  mov     [rsp+138h+Buffer], rax
0x14015bca3  mov     [rsp+138h+Bcb], rcx
0x14015bca8  mov     rdi, 0AA00042EC1h
0x14015bcb2  mov     r8, rdi
0x14015bcb5  mov     rcx, r14
0x14015bcb8  call    NtfsAttachCorruption_BadOrOrphanFRS
0x14015bcbd  mov     r9, rdi
0x14015bcc0  mov     rax, [rsp+138h+arg_18]
0x14015bcc8  mov     r8, [rax]
0x14015bccb  mov     edx, 100h
0x14015bcd0  mov     rcx, r14
0x14015bcd3  call    NtfsAttachRepairInfoPriv
0x14015bcd8  movzx   eax, cs:NtfsStatusDebugFlags
0x14015bcdf  mov     edi, 0C0000032h
0x14015bce4  test    al, al
0x14015bce6  jz      loc_14015BDBC
0x14015bcec  mov     r8d, 42EC3h
0x14015bcf2  mov     edx, edi
0x14015bcf4  xor     ecx, ecx
0x14015bcf6  call    NtfsStatusTraceAndDebugInternal
0x14015bcfb  jmp     loc_14015BDBC
0x14015bd00  lea     rax, [rdi+10h]
0x14015bd04  mov     [rax], r12
0x14015bd07  mov     [rax+8], rcx
0x14015bd0b  mov     [rcx], rax
0x14015bd0e  mov     [r12+8], rax
0x14015bd13  mov     [rdi+20h], rsi
0x14015bd17  mov     qword ptr [rdi+28h], 20h ; ' '
0x14015bd1f  mov     eax, [rdi+28h]
0x14015bd22  cmp     [rdi+2Ch], eax
0x14015bd25  jz      loc_14015C0E7
0x14015bd2b  mov     eax, [rdi+2Ch]
0x14015bd2e  mov     [rdi+rax*4+30h], r15d
0x14015bd33  inc     dword ptr [rdi+2Ch]
0x14015bd36  test    r13, r13
0x14015bd39  jz      loc_14015BDC1
0x14015bd3f  test    r14, r14
0x14015bd42  jz      short loc_14015BD4F
0x14015bd44  mov     eax, [r14+10h]
0x14015bd48  bt      rax, 14h
0x14015bd4d  jb      short loc_14015BD5C
0x14015bd4f  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 4
0x14015bd56  jnz     loc_14015C2AA
0x14015bd5c  mov     r8d, 1; NumberToClear
0x14015bd62  mov     edx, [rsp+138h+StartingIndex]; StartingIndex
0x14015bd66  lea     rcx, [rsp+138h+BitMapHeader]; BitMapHeader
0x14015bd6e  call    cs:__imp_RtlClearBits
0x14015bd75  nop     dword ptr [rax+rax+00h]
0x14015bd7a  cmp     r15d, [rbx+18h]
0x14015bd7e  jz      loc_14015BFFA
0x14015bd84  mov     rdi, [rsp+138h+var_80]
0x14015bd8c  mov     rcx, [rsp+138h+var_C0]; Bcb
0x14015bd91  test    rcx, rcx
0x14015bd94  jz      short loc_14015BDAB
0x14015bd96  call    cs:__imp_CcUnpinData
0x14015bd9d  nop     dword ptr [rax+rax+00h]
0x14015bda2  mov     [rsp+138h+var_C0], 0
0x14015bdab  inc     dword ptr [rbx+14h]
0x14015bdae  cmp     r15d, [rbx+18h]
0x14015bdb2  jz      loc_14015BE50
0x14015bdb8  mov     edi, [rsp+138h+var_C4]
0x14015bdbc  jmp     loc_14015C627
0x14015bdc1  mov     r8d, r15d
0x14015bdc4  shr     r8d, 3; int
0x14015bdc8  mov     rax, [rsp+138h+arg_18]
0x14015bdd0  mov     [rsp+138h+var_F0], rax; void *
0x14015bdd5  mov     [rsp+138h+var_F8], 0; char
0x14015bdda  mov     [rsp+138h+var_100], 0; char
0x14015bddf  mov     [rsp+138h+var_108], 0; char
0x14015bde4  mov     byte ptr [rsp+138h+Buffer], 0; char
0x14015bde9  mov     dword ptr [rsp+138h+Bcb], 1; Length
0x14015bdf1  lea     r9, [rsp+138h+arg_8]; int
0x14015bdf9  mov     rdx, [rsi+0B8h]; int
0x14015be00  mov     rcx, r14; int
0x14015be03  call    NtfsChangeAttributeValue
0x14015be08  cmp     r15d, [rbx+18h]
0x14015be0c  jnz     short loc_14015BE2D
0x14015be0e  lea     r8, [rsp+138h+StartingRunIndex]; StartingRunIndex
0x14015be16  mov     edx, r15d; FromIndex
0x14015be19  lea     rcx, [rsp+138h+BitMapHeader]; BitMapHeader
0x14015be21  call    cs:__imp_RtlFindLastBackwardRunClear
0x14015be28  nop     dword ptr [rax+rax+00h]
0x14015be2d  mov     rdi, [rsp+138h+var_80]
0x14015be35  jmp     loc_14015BDAB
0x14015be3a  lea     rdi, [rax-10h]
0x14015be3e  cmp     [rdi+20h], rsi
0x14015be42  jz      loc_14015BC41
0x14015be48  mov     rax, [rax]
0x14015be4b  jmp     loc_14015BC36
0x14015be50  mov     eax, [rsp+138h+StartingRunIndex]
0x14015be57  lea     edx, [rax+rdi*8]
0x14015be5a  lea     eax, [rdx-1]
0x14015be5d  mov     [rbx+18h], eax
0x14015be60  mov     r13, [rsp+138h+var_60]
0x14015be68  cmp     rsi, [r13+30h]
0x14015be6c  jz      loc_14015BDB8
0x14015be72  movsxd  r8, [rsp+138h+var_88]
0x14015be7a  mov     r9, [rsi+18h]
0x14015be7e  mov     ecx, dword ptr [rsp+138h+var_B0]
0x14015be85  inc     ecx
0x14015be87  add     eax, ecx
0x14015be89  movsxd  rcx, eax
0x14015be8c  imul    rcx, r8
0x14015be90  cmp     r9, rcx
0x14015be93  jle     loc_14015BDB8
0x14015be99  movsxd  rdi, edx
0x14015be9c  imul    rdi, r8
0x14015bea0  cmp     rsi, [r13+0C8h]
0x14015bea7  jz      loc_14015C474
0x14015bead  mov     qword ptr [rsp+138h+var_B0], 0
0x14015beb9  mov     rdx, rdi
0x14015bebc  mov     qword ptr [rsp+138h+var_B0], rdx
0x14015bec4  mov     eax, [r14+4]
0x14015bec8  test    al, 10h
  ... truncated ...
```
