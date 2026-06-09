# CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)

- ea: `0x140016440`
- end: `0x140016f4d`
- name: `?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z`
- size: `2829`
- prototype: `void(CmsVolume *__hidden this, struct CmsTransactionCore *, struct SmsPage *, unsigned int)`
- caller_count: `165`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012760`
- `0x140014100`
- `0x140014d60`
- `0x140015380`
- `0x14001593c`
- `0x1400176e0`
- `0x140017870`
- `0x140019c20`
- `0x14001aaf0`
- `0x14001b5e8`
- `0x14001be70`
- `0x14001c950`
- `0x14001d0e0`
- `0x14001d5e0`
- `0x14001db20`
- `0x1400206c0`
- `0x140024cd4`
- `0x140025140`
- `0x140025500`
- `0x140026320`
- `0x140029df0`
- `0x14002a850`
- `0x14002b680`
- `0x14002b870`
- `0x1400385c4`
- `0x140039660`
- `0x14003b090`
- `0x14003b6e0`
- `0x14003ca00`
- `0x14003f39c`
- `0x14003f780`
- `0x140040610`
- `0x140041414`
- `0x140041e70`
- `0x1400423d0`
- `0x14004331c`
- `0x1400444f8`
- `0x14004dfd0`
- `0x14004e5d0`
- `0x140051e70`
- `0x140052030`
- `0x140052db0`
- `0x1400539f0`
- `0x1400568e0`
- `0x14005afa0`
- `0x14005bed0`
- `0x14005c6c0`
- `0x14005d060`
- `0x14005e540`
- `0x14005f30c`

## callees

- `0x140016440`
- `0x140016f60`
- `0x140016f80`
- `0x140016f90`
- `0x140017020`
- `0x140017060`
- `0x1400173c0`
- `0x140018360`
- `0x14001f970`
- `0x140021720`
- `0x140021b70`
- `0x1400222e0`
- `0x140093290`
- `0x140097af0`
- `0x14012ccf0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140016aaf`
- `ntoskrnl!KeSetEvent` at `0x140016cdf`
- `ntoskrnl!KeSetEvent` at `0x140016d6b`
- `ntoskrnl!KeSetEvent` at `0x140016aaf`
- `ntoskrnl!KeSetEvent` at `0x140016cdf`
- `ntoskrnl!KeSetEvent` at `0x140016d6b`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400167e7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016a69`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140016a69`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140016de1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140016de1`
- `ntoskrnl!ExDeleteFastResource` at `0x140016842`
- `ntoskrnl!ExDeleteFastResource` at `0x140016842`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400169bd`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400169bd`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016b4e`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016b70`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016b92`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016bb4`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016b4e`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016b70`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016b92`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140016bb4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9686`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f9686`
- `ntoskrnl!ExReleaseFastResource` at `0x140016503`
- `ntoskrnl!ExReleaseFastResource` at `0x140016b0a`
- `ntoskrnl!ExReleaseFastResource` at `0x140016503`
- `ntoskrnl!ExReleaseFastResource` at `0x140016b0a`
- `ntoskrnl!ExReleasePushLockEx` at `0x140016cfc`
- `ntoskrnl!ExReleasePushLockEx` at `0x140016d88`
- `ntoskrnl!ExReleasePushLockEx` at `0x140016e1e`
- `ntoskrnl!ExReleasePushLockEx` at `0x140016cfc`
- `ntoskrnl!ExReleasePushLockEx` at `0x140016d88`
- `ntoskrnl!ExReleasePushLockEx` at `0x140016e1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016869`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016869`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f3c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016c8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016d1d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016c8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140016d1d`

## pseudocode

```c
void __fastcall CmsVolume::UnpinInternal(CmsVolume *this, struct CmsTransactionCore *a2, struct SmsPage *a3, char a4)
{
  __int64 v5; // r8
  struct CmsTransactionCore *v7; // r13
  CmsVolumeContainer **v8; // r15
  __int64 v9; // r14
  int v10; // eax
  char *v11; // rdi
  _QWORD **v12; // rdx
  _QWORD *i; // rax
  bool v14; // zf
  __int64 v15; // rax
  signed __int32 v16; // eax
  int v17; // r15d
  unsigned __int64 v18; // rdi
  bool v19; // cf
  struct SmsHashEntry *v20; // rax
  struct SmsHashEntry *v21; // rdi
  __int64 v22; // rdx
  __int16 v23; // cx
  __int16 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // eax
  struct SmsHashEntry *v29; // rsi
  __int64 v30; // rax
  struct _MDL *v31; // rcx
  int v32; // edi
  struct CmsTransactionCore *v33; // rdx
  __int64 v34; // rcx
  unsigned __int8 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r15
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  void *v42; // rcx
  unsigned __int64 v43; // rdx
  struct SmsHashEntry *v44; // rax
  struct SmsHashEntry *v45; // rdi
  __int64 v46; // rdx
  __int16 v47; // cx
  __int16 v48; // r8
  __int64 v49; // rcx
  __int64 v50; // rax
  int v51; // r8d
  __int64 v52; // rcx
  void *v53; // rsi
  __int64 v54; // r14
  struct SmsHashEntry *v55; // rbx
  __int64 v56; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v57; // rcx
  void *v58; // rdx
  _QWORD *v59; // rbx
  _QWORD *v60; // rcx
  int v61; // eax
  __int64 v62; // rax
  CmsVolume **v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 *v66; // rdi
  __int64 **v67; // rcx
  struct _KEVENT *v68; // rcx
  __int64 v69; // rax
  __int64 *v70; // rdi
  __int64 **v71; // rcx
  struct _KEVENT *v72; // rcx
  __int64 v73; // rax
  char v74; // al
  __int64 v75; // rcx
  struct _SmsHashLocation *v76; // [rsp+38h] [rbp-71h]
  struct SmsHashEntry **v77; // [rsp+40h] [rbp-69h]
  __int128 v78; // [rsp+50h] [rbp-59h] BYREF
  __int64 v79; // [rsp+60h] [rbp-49h]
  __int128 v80; // [rsp+68h] [rbp-41h] BYREF
  int v81; // [rsp+78h] [rbp-31h]
  int v82; // [rsp+7Ch] [rbp-2Dh]
  __int64 v83; // [rsp+80h] [rbp-29h]
  __int128 v84; // [rsp+88h] [rbp-21h] BYREF
  __int64 v85; // [rsp+98h] [rbp-11h]
  __int128 v86; // [rsp+A8h] [rbp-1h] BYREF
  int v87; // [rsp+B8h] [rbp+Fh]
  int v88; // [rsp+BCh] [rbp+13h]
  __int64 v89; // [rsp+C0h] [rbp+17h]
  struct CmsVolume *v90; // [rsp+110h] [rbp+67h]
  struct SmsHashEntry *v91; // [rsp+120h] [rbp+77h] BYREF
  char v92; // [rsp+128h] [rbp+7Fh] BYREF

  v90 = this;
  v92 = 122;
  v5 = *((_QWORD *)a3 + 12);
  v7 = a2;
  v8 = (CmsVolumeContainer **)this;
  v9 = *(_QWORD *)(*(_QWORD *)(v5 + 32) + 40LL);
  if ( (a4 & 4) != 0 )
    --*((_DWORD *)a3 + 97);
  if ( (a4 & 1) != 0 )
  {
    if ( *(char *)(v5 + 14) >= 0 )
      --*((_DWORD *)a2 + 49);
    v10 = *((_DWORD *)a3 + 96);
    if ( !v10 )
    {
      v11 = (char *)a2 + 664;
      this = (struct SmsPage *)((char *)a3 + 560);
      while ( v11 != (char *)a2 + 792 )
      {
        if ( *(CmsVolume **)v11 == this )
          goto LABEL_14;
        v11 += 32;
      }
      v12 = (_QWORD **)((char *)a2 + 792);
      for ( i = *v12; i != v12; i = (_QWORD *)*i )
      {
        v11 = (char *)(i - 2);
        if ( (CmsVolume *)*(i - 2) == this )
          goto LABEL_14;
      }
      v11 = 0;
LABEL_14:
      a2 = (struct CmsTransactionCore *)*((_QWORD *)v11 + 1);
      if ( a2 )
      {
        v14 = (*((_DWORD *)a2 + 18))-- == 1;
        if ( !v14 )
          goto LABEL_18;
        *((_DWORD *)a2 + 19) &= ~2u;
      }
      ExReleaseFastResource(this, a2);
LABEL_18:
      v15 = *((_QWORD *)v11 + 1);
      if ( !*(_DWORD *)(v15 + 72) )
      {
        a2 = (struct CmsTransactionCore *)*((_QWORD *)v11 + 2);
        this = (CmsVolume *)(v11 + 16);
        if ( a2 )
        {
          if ( *((CmsVolume **)a2 + 1) != this || (v63 = (CmsVolume **)*((_QWORD *)v11 + 3), *v63 != this) )
LABEL_134:
            __fastfail(3u);
          *v63 = a2;
          *((_QWORD *)a2 + 1) = v63;
          v64 = *((_QWORD *)v11 + 1);
          if ( v64 )
            *(_DWORD *)(v64 + 76) &= ~1u;
          *((_QWORD *)v11 + 1) = 0;
          *(_QWORD *)v11 = 0;
          ExFreePoolWithTag(v11, 0);
        }
        else
        {
          if ( v15 )
            *(_DWORD *)(v15 + 76) &= ~1u;
          *((_QWORD *)v11 + 1) = 0;
          *(_QWORD *)v11 = 0;
        }
      }
      goto LABEL_23;
    }
    v61 = v10 - 1;
    *((_DWORD *)a3 + 96) = v61;
    if ( !v61 )
      ExReleaseFastResource((char *)a3 + 560, 0);
  }
LABEL_23:
  if ( (a4 & 8) != 0 && !*((_QWORD *)a3 + 42) && (*((_DWORD *)a3 + 138) & 0x10) != 0 )
  {
    if ( *((_QWORD *)a3 + 16) )
      MmSetAddressRangeModified(*((PVOID *)a3 + 15), *((unsigned int *)a3 + 34));
    if ( *((_QWORD *)a3 + 20) )
      MmSetAddressRangeModified(*((PVOID *)a3 + 19), *((unsigned int *)a3 + 42));
    if ( *((_QWORD *)a3 + 24) )
      MmSetAddressRangeModified(*((PVOID *)a3 + 23), *((unsigned int *)a3 + 50));
    if ( *((_QWORD *)a3 + 28) )
      MmSetAddressRangeModified(*((PVOID *)a3 + 27), *((unsigned int *)a3 + 58));
    CmsVolume::CleanBackingPage((CmsVolume *)v8, a2, a3);
    _InterlockedAnd((volatile signed __int32 *)a3 + 138, 0xFFFFFFEF);
  }
  if ( (a4 & 2) != 0 )
  {
    if ( (*((_DWORD *)a3 + 138) & 0x4000) != 0 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)a3 + 95, 0xFFFFFFFF) == 1 )
      {
        *((_BYTE *)a3 + 393) = 1;
        v74 = 116;
      }
      else
      {
        v74 = 45;
      }
      v92 = v74;
    }
    else
    {
      while ( 1 )
      {
        v16 = *((_DWORD *)a3 + 95);
        if ( v16 <= 1 )
          break;
        if ( v16 == _InterlockedCompareExchange((volatile signed __int32 *)a3 + 95, v16 - 1, v16) )
          return;
      }
      v17 = 9;
      v18 = *(_QWORD *)a3;
      v19 = (*(_DWORD *)v7 & 0x8000LL) != 0;
      v91 = 0;
      if ( v19 )
        v17 = 1;
      v79 = 0;
      v78 = 0;
      if ( (v17 & 8) != 0 )
        ExAcquirePushLockSharedEx(v9 + 56, 4);
      v20 = CmsHashTable::FindAndLockEntryInternal(
              (CmsHashTable *)(v9 + 16),
              v18,
              0,
              0,
              *(_QWORD *)(v9 + 32) != 0,
              (struct _SmsHashLocation *)&v78,
              &v91,
              v76,
              v77);
      v21 = v20;
      if ( v20 )
      {
        v22 = *((_QWORD *)v20 + 1);
        v81 = 0;
        v80 = 0;
        v83 = 0;
        v23 = *(_WORD *)(v22 + 8);
        v24 = v23 & 3;
        if ( (v23 & 0x40) != 0 )
        {
          WORD2(v84) = v23 & 3;
          v27 = *(unsigned __int16 *)(v22 + 10);
          WORD3(v84) = WORD3(v78);
          LODWORD(v84) = 12;
          *((_QWORD *)&v84 + 1) = v22 + 12;
        }
        else
        {
          v25 = *(unsigned __int16 *)(v22 + 10);
          LODWORD(v84) = *(unsigned __int16 *)(v22 + 6);
          WORD3(v84) = WORD3(v78);
          v26 = v22 + *(unsigned __int16 *)(v22 + 4);
          WORD2(v84) = v24 | 4;
          v27 = *(_DWORD *)(v22 + 12);
          v22 += v25;
          *((_QWORD *)&v84 + 1) = v26;
        }
        v81 = v27;
        v83 = v22;
        v80 = v84;
        v82 = DWORD1(v78);
        v28 = DerefPageOrEnterTeardownState(v7, (struct _CmsRow *)&v80, &v92);
        v29 = v91;
        if ( v28 == -1073741444 )
          CmsHashTable::DeleteInternal(v9 + 16, &v78, v21, v91, v17, 0);
        v30 = _InterlockedExchange64((volatile __int64 *)v29, v78);
        *(_QWORD *)&v78 = 0;
        if ( v30 == -3 )
        {
          ExAcquirePushLockExclusiveEx(&qword_14026C3C0, 0);
          v65 = qword_14026C3C8;
          if ( (__int64 *)qword_14026C3C8 != &qword_14026C3C8 )
          {
            do
            {
              v66 = *(__int64 **)v65;
              if ( *(struct SmsHashEntry **)(v65 + 24) == v29 )
              {
                if ( v66[1] != v65 )
                  goto LABEL_134;
                v67 = *(__int64 ***)(v65 + 8);
                if ( *v67 != (__int64 *)v65 )
                  goto LABEL_134;
                *v67 = v66;
                v66[1] = (__int64)v67;
                v68 = *(struct _KEVENT **)(v65 + 16);
                *(_QWORD *)v65 = 0;
                KeSetEvent(v68, 0, 0);
              }
              v65 = (__int64)v66;
            }
            while ( v66 != &qword_14026C3C8 );
          }
          ExReleasePushLockEx(&qword_14026C3C0, 0);
        }
      }
      if ( (v17 & 8) != 0 )
        ExReleasePushLockEx(v9 + 56, 0);
      v8 = (CmsVolumeContainer **)v90;
    }
    if ( v92 == 116 )
    {
      if ( !*((_QWORD *)a3 + 42) && (*((_DWORD *)a3 + 138) & 0x10) != 0 )
        CmsVolume::CleanInternalBeforeUnmap(this, a2, a3);
      v31 = (struct _MDL *)*((_QWORD *)a3 + 84);
      if ( v31 )
      {
        MsKmeUnlockPages(v31);
        *((_QWORD *)a3 + 84) = 0;
      }
      _InterlockedAnd((volatile signed __int32 *)a3 + 138, 0xFFFFFFFB);
      v32 = 0;
      CmsChecksum::GenerateChecksum(*((_QWORD *)a3 + 13), (char *)a3 + 120);
      if ( *((_QWORD *)a3 + 16) )
      {
        ((void (*)(void))MsKmeUnpinData)();
        *((_QWORD *)a3 + 16) = 0;
        v32 = 1;
        *((_QWORD *)a3 + 15) = 0;
      }
      if ( *((_QWORD *)a3 + 20) )
      {
        ((void (*)(void))MsKmeUnpinData)();
        *((_QWORD *)a3 + 20) = 0;
        ++v32;
        *((_QWORD *)a3 + 19) = 0;
      }
      if ( *((_QWORD *)a3 + 24) )
      {
        ((void (*)(void))MsKmeUnpinData)();
        *((_QWORD *)a3 + 24) = 0;
        ++v32;
        *((_QWORD *)a3 + 23) = 0;
      }
      if ( *((_QWORD *)a3 + 28) )
      {
        ((void (*)(void))MsKmeUnpinData)();
        *((_QWORD *)a3 + 28) = 0;
        ++v32;
        *((_QWORD *)a3 + 27) = 0;
      }
      if ( v32 )
      {
        _InterlockedAnd((volatile signed __int32 *)a3 + 138, 0xFFFFFFFD);
        MsKmeFreeBaseAddressFromTuple(*((void **)a3 + 13), *((void **)a3 + 14), (struct SmsPage *)((char *)a3 + 120));
        *((_QWORD *)a3 + 13) = 0;
        *((_QWORD *)a3 + 14) = 0;
        _InterlockedDecrement((volatile signed __int32 *)&DbgCounts);
      }
      if ( !*((_QWORD *)a3 + 42) && (*((_DWORD *)a3 + 138) & 0x10) != 0 )
      {
        CmsVolume::CleanBackingPage((CmsVolume *)v8, v33, a3);
        _InterlockedAnd((volatile signed __int32 *)a3 + 138, 0xFFFFFFEF);
      }
      if ( (*((_DWORD *)a3 + 138) & 0x80u) != 0 )
      {
        v34 = *((_QWORD *)a3 + 12);
        v35 = (*(_BYTE *)(v34 + 14) & 0x40) != 0 || (*(_DWORD *)(*(_QWORD *)(v34 + 24) + 44LL) & 0x80u) != 0;
        MspDeductDirtyPageCount((struct CmsVolume *)v8, *((_DWORD *)a3 + 94), v35);
        _InterlockedAnd((volatile signed __int32 *)a3 + 138, 0xFFFFFF7F);
      }
      if ( byte_140268FDB )
        CmsVolume::TrimPage((CmsVolume *)v8, v33, a3);
      v36 = *((unsigned int *)a3 + 138);
      if ( (v36 & 0x40) != 0 )
      {
        CmsVolumeContainer::SetContainerStationaryVolatile(v8[409], v7, a3, 0, 0);
        v36 = *((unsigned int *)a3 + 138);
      }
      v37 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a3 + 12) + 32LL) + 40LL);
      if ( (_BYTE)KdDebuggerEnabled && (v36 & 0x3000) != 0 )
        __debugbreak();
      v38 = *((_QWORD *)a3 + 16);
      if ( v38 )
      {
        MsKmeUnpinData(v38, v36);
        *((_QWORD *)a3 + 16) = 0;
        *((_QWORD *)a3 + 15) = 0;
        *((_DWORD *)a3 + 34) = 0;
      }
      v39 = *((_QWORD *)a3 + 20);
      if ( v39 )
      {
        MsKmeUnpinData(v39, v36);
        *((_QWORD *)a3 + 20) = 0;
        *((_QWORD *)a3 + 19) = 0;
        *((_DWORD *)a3 + 42) = 0;
      }
      v40 = *((_QWORD *)a3 + 24);
      if ( v40 )
      {
        MsKmeUnpinData(v40, v36);
        *((_QWORD *)a3 + 24) = 0;
        *((_QWORD *)a3 + 23) = 0;
        *((_DWORD *)a3 + 50) = 0;
      }
      v41 = *((_QWORD *)a3 + 28);
      if ( v41 )
      {
        MsKmeUnpinData(v41, v36);
        *((_QWORD *)a3 + 28) = 0;
        *((_QWORD *)a3 + 27) = 0;
        *((_DWORD *)a3 + 58) = 0;
      }
      ExDeleteFastResource((char *)a3 + 560);
      v42 = (void *)*((_QWORD *)a3 + 35);
      if ( v42 != (void *)-1LL )
      {
        *((_QWORD *)a3 + 36) = v42;
        if ( v42 )
          ExFreePoolWithTag(v42, 0);
      }
      v14 = (*((_DWORD *)a3 + 138) & 0x4000) == 0;
      *(_QWORD *)&v78 = 0;
      if ( v14 )
      {
        v43 = *(_QWORD *)a3;
        v14 = *(_QWORD *)(v37 + 32) == 0;
        v85 = 0;
        v91 = 0;
        v84 = 0;
        v44 = CmsHashTable::FindAndLockEntryInternal(
                (CmsHashTable *)(v37 + 16),
                v43,
                0,
                0,
                !v14,
                (struct _SmsHashLocation *)&v84,
                &v91,
                v76,
                v77);
        v45 = v44;
        if ( v44 )
        {
          v46 = *((_QWORD *)v44 + 1);
          v86 = 0;
          v87 = 0;
          v89 = 0;
          v47 = *(_WORD *)(v46 + 8);
          v48 = v47 & 3;
          if ( (v47 & 0x40) != 0 )
          {
            WORD2(v80) = v47 & 3;
            v51 = *(unsigned __int16 *)(v46 + 10);
            WORD3(v80) = WORD3(v78);
            LODWORD(v80) = 12;
            *((_QWORD *)&v80 + 1) = v46 + 12;
          }
          else
          {
            v49 = *(unsigned __int16 *)(v46 + 10);
            LODWORD(v80) = *(unsigned __int16 *)(v46 + 6);
            WORD3(v80) = WORD3(v78);
            v50 = v46 + *(unsigned __int16 *)(v46 + 4);
            WORD2(v80) = v48 | 4;
            v51 = *(_DWORD *)(v46 + 12);
            v46 += v49;
            *((_QWORD *)&v80 + 1) = v50;
          }
          v87 = v51;
          v89 = v46;
          v86 = v80;
          v88 = DWORD1(v78);
          if ( !(unsigned int)DequeueTeardownWaiters(v7, &v86, &v78) )
          {
            v52 = v84;
            v53 = 0;
            v54 = *((_QWORD *)v45 + 1);
            v55 = v91;
            *((_QWORD *)v45 + 1) = 0;
            if ( v52 == -1 )
            {
              *(_QWORD *)v45 = 0;
              v62 = *((_QWORD *)v55 + 1);
              v14 = (*(_DWORD *)(v62 + 4))-- == 1;
              if ( !v14 )
                goto LABEL_87;
              v53 = (void *)*((_QWORD *)v55 + 1);
              *((_QWORD *)v55 + 1) = 0;
            }
            v52 = 0;
LABEL_87:
            if ( _InterlockedExchange64((volatile __int64 *)v55, v52) == -3 )
            {
              ExAcquirePushLockExclusiveEx(&qword_14026C3C0, 0);
              v69 = qword_14026C3C8;
              if ( (__int64 *)qword_14026C3C8 != &qword_14026C3C8 )
              {
                do
                {
                  v70 = *(__int64 **)v69;
                  if ( *(struct SmsHashEntry **)(v69 + 24) == v55 )
                  {
                    if ( v70[1] != v69 )
                      goto LABEL_134;
                    v71 = *(__int64 ***)(v69 + 8);
                    if ( *v71 != (__int64 *)v69 )
                      goto LABEL_134;
                    *v71 = v70;
                    v70[1] = (__int64)v71;
                    v72 = *(struct _KEVENT **)(v69 + 16);
                    *(_QWORD *)v69 = 0;
                    KeSetEvent(v72, 0, 0);
                  }
                  v69 = (__int64)v70;
                }
                while ( v70 != &qword_14026C3C8 );
              }
              ExReleasePushLockEx(&qword_14026C3C0, 0);
            }
            if ( !v54 )
              goto LABEL_96;
            v56 = *(_QWORD *)(v54 - 16);
            if ( !v56 )
              goto LABEL_150;
            if ( *(_BYTE *)(v56 + 8) )
            {
              v57 = (struct _NPAGED_LOOKASIDE_LIST *)(v56 + 64);
              v58 = (void *)(v54 - 16);
              if ( *(_BYTE *)(v56 + 9) )
                ExFreeToNPagedLookasideList(v57, v58);
              else
                ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v57, v58);
              goto LABEL_96;
            }
            v75 = *(_QWORD *)(v56 + 88);
            if ( (int)v75 < *(_DWORD *)(v56 + 80) || SHIDWORD(v75) >= (int)v75 )
            {
              ExpInterlockedPushEntrySList((PSLIST_HEADER)(v56 + 64), (PSLIST_ENTRY)(v54 - 16));
              _InterlockedIncrement((volatile signed __int32 *)(v56 + 88));
            }
            else
            {
LABEL_150:
              ExFreePoolWithTag((PVOID)(v54 - 16), 0);
            }
LABEL_96:
            if ( v53 )
              ExFreePoolWithTag(v53, 0);
            _InterlockedDecrement((volatile signed __int32 *)(16LL * DWORD2(v84) + v37 + 28));
          }
        }
      }
      else
      {
        v73 = *((_QWORD *)a3 + 8);
        *((_QWORD *)a3 + 8) = 0;
        *(_QWORD *)&v78 = v73;
        CmsHashTable::FreeIndexEntry((struct SmsPage *)((char *)a3 - 16));
      }
      v59 = (_QWORD *)v78;
      while ( v59 )
      {
        v60 = v59;
        v59 = (_QWORD *)*v59;
        KeSetEvent((PRKEVENT)(v60 + 1), 0, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x140016440  mov     [rsp-8+arg_0], rcx
0x140016445  push    rbp
0x140016446  push    rbx
0x140016447  push    rsi
0x140016448  push    r12
0x14001644a  push    r13
0x14001644c  push    r14
0x14001644e  push    r15
0x140016450  lea     rbp, [rsp-27h]
0x140016455  sub     rsp, 0D0h
0x14001645c  mov     [rbp+57h+arg_18], 7Ah ; 'z'
0x140016460  mov     rbx, r8
0x140016463  mov     r8, [r8+60h]
0x140016467  mov     esi, r9d
0x14001646a  mov     r13, rdx
0x14001646d  mov     r15, rcx
0x140016470  mov     rax, [r8+20h]
0x140016474  mov     r14, [rax+28h]
0x140016478  test    r9b, 4
0x14001647c  jnz     loc_1400169CE
0x140016482  xor     r12d, r12d
0x140016485  mov     [rsp+100h+arg_8], rdi
0x14001648d  test    sil, 1
0x140016491  jz      loc_14001653A
0x140016497  cmp     [r8+0Eh], r12b
0x14001649b  jl      short loc_1400164A3
0x14001649d  dec     dword ptr [rdx+0C4h]
0x1400164a3  mov     eax, [rbx+180h]
0x1400164a9  test    eax, eax
0x1400164ab  jnz     loc_140016AF2
0x1400164b1  lea     rdi, [rdx+298h]
0x1400164b8  lea     rax, [rdi+80h]
0x1400164bf  lea     rcx, [rbx+230h]
0x1400164c6  cmp     rdi, rax
0x1400164c9  jz      short loc_1400164D6
0x1400164cb  cmp     [rdi], rcx
0x1400164ce  jz      short loc_1400164EC
0x1400164d0  add     rdi, 20h ; ' '
0x1400164d4  jmp     short loc_1400164C6
0x1400164d6  add     rdx, 318h
0x1400164dd  mov     rax, [rdx]
0x1400164e0  cmp     rax, rdx
0x1400164e3  jnz     loc_140016ADC
0x1400164e9  mov     rdi, r12
0x1400164ec  mov     rdx, [rdi+8]
0x1400164f0  test    rdx, rdx
0x1400164f3  jz      loc_140016B1B
0x1400164f9  add     dword ptr [rdx+48h], 0FFFFFFFFh
0x1400164fd  jnz     short loc_14001650F
0x1400164ff  and     dword ptr [rdx+4Ch], 0FFFFFFFDh
0x140016503  call    cs:__imp_ExReleaseFastResource
0x14001650a  nop     dword ptr [rax+rax+00h]
0x14001650f  mov     rax, [rdi+8]
0x140016513  cmp     [rax+48h], r12d
0x140016517  jnz     short loc_14001653A
0x140016519  mov     rdx, [rdi+10h]
0x14001651d  lea     rcx, [rdi+10h]
0x140016521  test    rdx, rdx
0x140016524  jnz     loc_140016C3C
0x14001652a  test    rax, rax
0x14001652d  jz      short loc_140016533
0x14001652f  and     dword ptr [rax+4Ch], 0FFFFFFFEh
0x140016533  mov     [rdi+8], r12
0x140016537  mov     [rdi], r12
0x14001653a  test    sil, 8
0x14001653e  jnz     loc_140016B20
0x140016544  test    sil, 2
0x140016548  jz      loc_140016AC0
0x14001654e  test    dword ptr [rbx+228h], 4000h
0x140016558  jnz     loc_140016DB3
0x14001655e  mov     eax, [rbx+17Ch]
0x140016564  cmp     eax, 1
0x140016567  jle     short loc_14001657D
0x140016569  nop
0x14001656a  lea     ecx, [rax-1]
0x14001656d  lock cmpxchg [rbx+17Ch], ecx
0x140016575  nop
0x140016576  jnz     short loc_14001655E
0x140016578  jmp     loc_140016AC0
0x14001657d  mov     eax, [r13+0]
0x140016581  mov     r15d, 9
0x140016587  mov     rdi, [rbx]
0x14001658a  bt      rax, 0Fh
0x14001658f  mov     eax, 1
0x140016594  mov     [rbp+57h+arg_10], r12
0x140016598  cmovb   r15d, eax
0x14001659c  xorps   xmm0, xmm0
0x14001659f  xor     eax, eax
0x1400165a1  mov     r12d, r15d
0x1400165a4  mov     [rbp+57h+var_A0], rax
0x1400165a8  movups  [rbp+57h+var_B0], xmm0
0x1400165ac  and     r12d, 8
0x1400165b0  jnz     loc_140016DD8
0x1400165b6  cmp     qword ptr [r14+20h], 0
0x1400165bb  lea     rcx, [rbp+57h+arg_10]
0x1400165bf  mov     [rsp+100h+var_D0], rcx; struct SmsHashEntry **
0x1400165c4  mov     rdx, rdi; unsigned __int64
0x1400165c7  setnz   al
0x1400165ca  lea     rcx, [rbp+57h+var_B0]
0x1400165ce  mov     [rsp+100h+var_D8], rcx; struct _SmsHashLocation *
0x1400165d3  xor     r9d, r9d; unsigned __int8
0x1400165d6  lea     rcx, [r14+10h]; this
0x1400165da  mov     byte ptr [rsp+100h+var_E0], al; char
0x1400165de  xor     r8d, r8d; unsigned __int8
0x1400165e1  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x1400165e6  mov     rdi, rax
0x1400165e9  test    rax, rax
0x1400165ec  jz      loc_14001669C
0x1400165f2  mov     rdx, [rdi+8]
0x1400165f6  xor     eax, eax
0x1400165f8  xorps   xmm0, xmm0
0x1400165fb  mov     [rbp+57h+var_88], eax
0x1400165fe  movups  [rbp+57h+var_98], xmm0
0x140016602  mov     [rbp+57h+var_80], rax
0x140016606  movzx   ecx, word ptr [rdx+8]
0x14001660a  lea     r9, [rdx+0Ch]
0x14001660e  movzx   r8d, cx
0x140016612  and     r8w, 3
0x140016617  test    cl, 40h
0x14001661a  jnz     loc_140016BDA
0x140016620  movzx   eax, word ptr [rdx+6]
0x140016624  or      r8w, 4
0x140016629  movzx   ecx, word ptr [rdx+0Ah]
0x14001662d  mov     dword ptr [rbp+57h+var_78], eax
0x140016630  movzx   eax, word ptr [rbp+57h+var_B0+6]
0x140016634  mov     word ptr [rbp+57h+var_78+6], ax
0x140016638  movzx   eax, word ptr [rdx+4]
0x14001663c  add     rax, rdx
0x14001663f  mov     word ptr [rbp+57h+var_78+4], r8w
0x140016644  mov     r8d, [r9]
0x140016647  add     rdx, rcx
0x14001664a  mov     qword ptr [rbp+57h+var_78+8], rax
0x14001664e  movups  xmm0, [rbp+57h+var_78]
0x140016652  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x140016655  mov     rcx, r13; struct CmsTransactionCore *
0x140016658  mov     [rbp+57h+var_88], r8d
0x14001665c  lea     r8, [rbp+57h+arg_18]; void *
0x140016660  mov     [rbp+57h+var_80], rdx
0x140016664  lea     rdx, [rbp+57h+var_98]; struct _CmsRow *
0x140016668  movups  [rbp+57h+var_98], xmm0
0x14001666c  mov     [rbp+57h+var_84], eax
0x14001666f  call    ?DerefPageOrEnterTeardownState@@YAJPEAVCmsTransactionCore@@PEAU_CmsRow@@PEAX@Z; DerefPageOrEnterTeardownState(CmsTransactionCore *,_CmsRow *,void *)
0x140016674  mov     rsi, [rbp+57h+arg_10]
0x140016678  cmp     eax, 0C000017Ch
0x14001667d  jz      loc_140016DF2
0x140016683  mov     rax, qword ptr [rbp+57h+var_B0]
0x140016687  xchg    rax, [rsi]
0x14001668a  mov     qword ptr [rbp+57h+var_B0], 0
0x140016692  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140016696  jz      loc_140016C84
0x14001669c  test    r12d, r12d
0x14001669f  jnz     loc_140016E18
0x1400166a5  mov     r15, [rbp+57h+arg_0]
0x1400166a9  xor     r12d, r12d
0x1400166ac  cmp     [rbp+57h+arg_18], 74h ; 't'
0x1400166b0  jnz     loc_140016AC0
0x1400166b6  cmp     qword ptr [rbx+150h], 0
0x1400166be  jnz     short loc_1400166CE
0x1400166c0  mov     eax, [rbx+228h]
0x1400166c6  test    al, 10h
0x1400166c8  jnz     loc_140016E2F
0x1400166ce  mov     rcx, [rbx+2A0h]; Mdl
0x1400166d5  test    rcx, rcx
0x1400166d8  jz      short loc_1400166E6
0x1400166da  call    ?MsKmeUnlockPages@@YAXPEAX@Z; MsKmeUnlockPages(void *)
0x1400166df  mov     [rbx+2A0h], r12
0x1400166e6  nop
0x1400166e7  lock and dword ptr [rbx+228h], 0FFFFFFFBh
0x1400166ef  nop
0x1400166f0  lea     rdx, [rbx+78h]
0x1400166f4  mov     rcx, [rbx+68h]
0x1400166f8  mov     edi, r12d
0x1400166fb  call    ?GenerateChecksum@CmsChecksum@@UEBAXV?$span@$$CBW4byte@utl@@$0?0@utl@@V?$span@W4byte@utl@@$0?0@3@@Z; CmsChecksum::GenerateChecksum(utl::span<utl::byte const,-1>,utl::span<utl::byte,-1>)
0x140016700  mov     rcx, [rbx+80h]
0x140016707  test    rcx, rcx
0x14001670a  jnz     loc_1400169D9
0x140016710  mov     rcx, [rbx+0A0h]
0x140016717  test    rcx, rcx
0x14001671a  jnz     loc_1400169F3
0x140016720  mov     rcx, [rbx+0C0h]
0x140016727  test    rcx, rcx
0x14001672a  jnz     loc_140016A0D
0x140016730  mov     rcx, [rbx+0E0h]
0x140016737  test    rcx, rcx
0x14001673a  jnz     loc_140016A27
0x140016740  test    edi, edi
0x140016742  jz      short loc_140016770
0x140016744  nop
0x140016745  lock and dword ptr [rbx+228h], 0FFFFFFFDh
0x14001674d  nop
0x14001674e  lea     r8, [rbx+78h]; struct _MS_CC_DATA_TUPLE *
0x140016752  mov     rdx, [rbx+70h]; void *
0x140016756  mov     rcx, [rbx+68h]; void *
0x14001675a  call    ?MsKmeFreeBaseAddressFromTuple@@YAXPEAX0PEAU_MS_CC_DATA_TUPLE@@@Z; MsKmeFreeBaseAddressFromTuple(void *,void *,_MS_CC_DATA_TUPLE *)
0x14001675f  mov     [rbx+68h], r12
0x140016763  mov     [rbx+70h], r12
0x140016767  nop
0x140016768  lock dec cs:?DbgCounts@@3U_SmsDebugCounts@@A; _SmsDebugCounts DbgCounts
0x14001676f  nop
0x140016770  cmp     qword ptr [rbx+150h], 0
0x140016778  jz      loc_140016A41
0x14001677e  mov     eax, [rbx+228h]
0x140016784  test    al, al
0x140016786  jns     short loc_1400167C3
0x140016788  mov     rcx, [rbx+60h]
0x14001678c  test    byte ptr [rcx+0Eh], 40h
0x140016790  jnz     loc_140016E3C
0x140016796  mov     rax, [rcx+18h]
0x14001679a  mov     ecx, [rax+2Ch]
0x14001679d  test    cl, cl
0x14001679f  js      loc_140016E3C
0x1400167a5  xor     r8b, r8b; unsigned __int8
0x1400167a8  mov     edx, [rbx+178h]; int
0x1400167ae  mov     rcx, r15; struct CmsVolume *
0x1400167b1  call    ?MspDeductDirtyPageCount@@YAXPEAVCmsVolume@@JE@Z; MspDeductDirtyPageCount(CmsVolume *,long,uchar)
0x1400167b6  nop
0x1400167b7  lock and dword ptr [rbx+228h], 0FFFFFF7Fh
0x1400167c2  nop
0x1400167c3  cmp     cs:byte_140268FDB, 0
0x1400167ca  jnz     loc_140016E44
0x1400167d0  mov     edx, [rbx+228h]
0x1400167d6  test    dl, 40h
0x1400167d9  jnz     loc_140016E54
0x1400167df  mov     rax, [rbx+60h]
0x1400167e3  mov     rcx, [rax+20h]
0x1400167e7  mov     rax, cs:KdDebuggerEnabled
0x1400167ee  mov     r15, [rcx+28h]
0x1400167f2  cmp     byte ptr [rax], 0
0x1400167f5  jnz     loc_140016E79
0x1400167fb  mov     rcx, [rbx+80h]
0x140016802  test    rcx, rcx
0x140016805  jnz     loc_140016E8B
0x14001680b  mov     rcx, [rbx+0A0h]
0x140016812  test    rcx, rcx
0x140016815  jnz     loc_140016EA7
0x14001681b  mov     rcx, [rbx+0C0h]
0x140016822  test    rcx, rcx
0x140016825  jnz     loc_140016EC6
0x14001682b  mov     rcx, [rbx+0E0h]
0x140016832  test    rcx, rcx
0x140016835  jnz     loc_140016EE5
0x14001683b  lea     rcx, [rbx+230h]
0x140016842  call    cs:__imp_ExDeleteFastResource
0x140016849  nop     dword ptr [rax+rax+00h]
0x14001684e  mov     rcx, [rbx+118h]; P
0x140016855  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140016859  jz      short loc_140016875
0x14001685b  mov     [rbx+120h], rcx
0x140016862  test    rcx, rcx
0x140016865  jz      short loc_140016875
0x140016867  xor     edx, edx; Tag
0x140016869  call    cs:__imp_ExFreePoolWithTag
0x140016870  nop     dword ptr [rax+rax+00h]
0x140016875  test    dword ptr [rbx+228h], 4000h
0x14001687f  mov     qword ptr [rbp+57h+var_B0], r12
0x140016883  jnz     loc_140016D99
0x140016889  mov     rdx, [rbx]; unsigned __int64
0x14001688c  lea     rcx, [rbp+57h+arg_10]
0x140016890  mov     [rsp+100h+var_D0], rcx; struct SmsHashEntry **
0x140016895  xor     eax, eax
0x140016897  cmp     [r15+20h], rax
0x14001689b  lea     rcx, [rbp+57h+var_78]
0x14001689f  mov     [rsp+100h+var_D8], rcx; struct _SmsHashLocation *
0x1400168a4  xorps   xmm0, xmm0
0x1400168a7  mov     [rbp+57h+var_68], rax
0x1400168ab  lea     rcx, [r15+10h]; this
0x1400168af  setnz   al
0x1400168b2  mov     [rbp+57h+arg_10], r12
0x1400168b6  xor     r9d, r9d; unsigned __int8
0x1400168b9  mov     byte ptr [rsp+100h+var_E0], al; char
0x1400168bd  xor     r8d, r8d; unsigned __int8
0x1400168c0  movups  [rbp+57h+var_78], xmm0
0x1400168c4  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x1400168c9  mov     rdi, rax
0x1400168cc  test    rax, rax
0x1400168cf  jz      loc_140016A8D
0x1400168d5  mov     rdx, [rax+8]
0x1400168d9  xorps   xmm0, xmm0
0x1400168dc  movups  [rbp+57h+var_58], xmm0
0x1400168e0  mov     [rbp+57h+var_48], r12d
0x1400168e4  mov     [rbp+57h+var_40], r12
0x1400168e8  movzx   ecx, word ptr [rdx+8]
0x1400168ec  lea     r9, [rdx+0Ch]
0x1400168f0  movzx   r8d, cx
0x1400168f4  and     r8w, 3
0x1400168f9  test    cl, 40h
0x1400168fc  jnz     loc_140016C1A
0x140016902  movzx   eax, word ptr [rdx+6]
0x140016906  or      r8w, 4
0x14001690b  movzx   ecx, word ptr [rdx+0Ah]
0x14001690f  mov     dword ptr [rbp+57h+var_98], eax
0x140016912  movzx   eax, word ptr [rbp+57h+var_B0+6]
0x140016916  mov     word ptr [rbp+57h+var_98+6], ax
0x14001691a  movzx   eax, word ptr [rdx+4]
0x14001691e  add     rax, rdx
0x140016921  mov     word ptr [rbp+57h+var_98+4], r8w
0x140016926  mov     r8d, [r9]
0x140016929  add     rdx, rcx
0x14001692c  mov     qword ptr [rbp+57h+var_98+8], rax
0x140016930  movups  xmm0, [rbp+57h+var_98]
  ... truncated ...
```
