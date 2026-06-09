# RefsCommonClose(_IRP_CONTEXT *,_SCB *,_FCB *,_VCB *,_CCB * *,_TYPE_OF_OPEN,uchar,AsyncCloseFlags)

- ea: `0x1403058c0`
- end: `0x140306288`
- name: `?RefsCommonClose@@YAJPEAU_IRP_CONTEXT@@PEAU_SCB@@PEAU_FCB@@PEAU_VCB@@PEAPEAU_CCB@@W4_TYPE_OF_OPEN@@EW4AsyncCloseFlags@@@Z`
- size: `2504`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1403053a0`
- `0x14033b510`

## callees

- `0x14000e0e0`
- `0x14002b620`
- `0x14003bf40`
- `0x14004ffc0`
- `0x14006bf10`
- `0x140071ba0`
- `0x1400757c0`
- `0x140076ad0`
- `0x140085570`
- `0x1400862c0`
- `0x1400889f0`
- `0x1400894e0`
- `0x1400aecd8`
- `0x1400cedec`
- `0x1400d0fd8`
- `0x14028debc`
- `0x1402977e8`
- `0x140302e10`
- `0x140304230`
- `0x140304a70`
- `0x1403058c0`
- `0x140306290`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140305e11`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140305e11`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140305d17`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140305d17`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140305ae6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140305ae6`
- `ntoskrnl!MmBadPointer` at `0x140305b30`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140305c7f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140305d41`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140305c7f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140305d41`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140305af6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140305af6`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140341dc4`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140341e10`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140341dc4`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140341e10`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140305b4a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140305b4a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140305b56`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140305b56`
- `ntoskrnl!ExReleaseFastResource` at `0x140306004`
- `ntoskrnl!ExReleaseFastResource` at `0x140306004`
- `ntoskrnl!ExFreePoolWithTag` at `0x140305c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306026`
- `ntoskrnl!ExFreePoolWithTag` at `0x140305c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140306026`

## pseudocode

```c
__int64 __fastcall RefsCommonClose(
        __int64 a1,
        struct _SCB *a2,
        __int64 a3,
        struct _VCB *a4,
        struct _CCB **a5,
        char a6,
        char a7,
        char a8)
{
  struct _VCB *v8; // r10
  char v11; // di
  unsigned int v12; // ebx
  unsigned int v13; // r13d
  _QWORD *v14; // r12
  __int64 v15; // rdx
  __int64 v16; // r8
  struct _SCB *v17; // r8
  struct _VCB *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  struct _CCB *v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // rax
  _QWORD *v25; // rcx
  union _LARGE_INTEGER v26; // rbx
  void *v27; // rcx
  bool v28; // zf
  __int64 *i; // rbx
  __int16 v30; // ax
  SECTION_OBJECT_POINTERS *v31; // rcx
  bool v32; // r8
  char v33; // dl
  _QWORD *j; // rax
  __int64 v35; // r8
  int v36; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned int v40; // r9d
  int v41; // [rsp+20h] [rbp-98h]
  char v42; // [rsp+40h] [rbp-78h]
  bool v43; // [rsp+41h] [rbp-77h]
  struct _LCB *QuadPart; // [rsp+50h] [rbp-68h] BYREF
  int v45; // [rsp+58h] [rbp-60h]
  union _LARGE_INTEGER NewFileSize; // [rsp+60h] [rbp-58h] BYREF
  struct IndexSCB *v47[10]; // [rsp+68h] [rbp-50h] BYREF
  struct _SCB *v48; // [rsp+C8h] [rbp+10h]

  v48 = a2;
  v8 = a4;
  v42 = 0;
  v11 = 0;
  v12 = 1;
  v45 = 1;
  v13 = 0;
  v14 = (_QWORD *)(a1 + 8);
  v47[1] = (struct IndexSCB *)(a1 + 8);
  if ( (*(_BYTE *)(a1 + 8) & 1) == 0 )
  {
    v12 = 3;
    v45 = 3;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      if ( (*v14 & 0x800000LL) == 0 )
      {
        if ( (*((_DWORD *)v8 + 6) & 0x800) == 0 && (*v14 & 0x100LL) == 0 )
        {
          v15 = *(_QWORD *)(a1 + 104);
          if ( (*(_QWORD *)(v15 + 8) & 0x20000000000LL) == 0 )
          {
            MsInitializeFastResourceOwnerEntry(v15 + 160);
            *(_QWORD *)(v15 + 8) |= v16;
          }
          if ( !(unsigned __int8)MsAcquireFastResourceSharedInternal<0>(
                                   (char *)v8 + 1312,
                                   v15 + 160,
                                   *(_BYTE *)(a1 + 8) & 1) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              return 259;
            v40 = 1152;
LABEL_146:
            RefsStatusDebug(259, 0, "Close.c", v40);
            return 259;
          }
        }
        else
        {
          if ( !RefsAcquireExclusiveVcb((struct _IRP_CONTEXT *)a1, v8, 0) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              return 259;
            v40 = 1145;
            goto LABEL_146;
          }
          v42 = 1;
        }
        a2 = v48;
      }
      if ( (*(_DWORD *)(a1 + 4) & 0x10000) == 0 && !*((_DWORD *)a2 + 40) )
      {
        if ( (*((_DWORD *)a2 + 38) & 0x100) != 0
          && (v38 = *((_QWORD *)a2 + 31), !*(_QWORD *)(v38 + 8))
          && !*(_QWORD *)(v38 + 24)
          || !*(_DWORD *)(a3 + 16) && *(_QWORD *)(a3 + 232) )
        {
          *(_DWORD *)(a1 + 4) |= 0x10000u;
        }
      }
      if ( !(unsigned __int8)RefsAcquireFcbWithPaging(a1, a3, 0, v12) )
      {
        if ( (*(_DWORD *)v14 & 0x800000) == 0 )
          RefsReleaseVcb((struct _IRP_CONTEXT *)a1, a4);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, &WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v40 = 1196;
          goto LABEL_146;
        }
        return 259;
      }
      v17 = v48;
      if ( (*(_DWORD *)(a1 + 4) & 0x10000) != 0 || *((_DWORD *)v48 + 40) )
        break;
      if ( (*((_DWORD *)v48 + 38) & 0x100) == 0
        || (v39 = *((_QWORD *)v48 + 31), *(_QWORD *)(v39 + 8))
        || *(_QWORD *)(v39 + 24) )
      {
        if ( *(_DWORD *)(a3 + 16) || !*(_QWORD *)(a3 + 232) )
          break;
      }
      *(_DWORD *)(a1 + 4) |= 0x10000u;
      RefsReleaseFcbWithPaging((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
      a2 = v48;
      v8 = a4;
      if ( (*(_DWORD *)v14 & 0x800000) == 0 )
        goto LABEL_132;
    }
    v18 = a4;
    if ( v42 || (*(_DWORD *)v14 & 0x800000) != 0 || (*((_DWORD *)a4 + 6) & 0x800) == 0 )
      break;
    RefsReleaseFcbWithPaging((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
    a2 = v48;
    if ( (*(_DWORD *)v14 & 0x800000) == 0 )
    {
LABEL_132:
      RefsReleaseVcb((struct _IRP_CONTEXT *)a1, a4);
      a2 = v48;
    }
    v8 = a4;
  }
  *v14 |= 1uLL;
  if ( (*((_DWORD *)v48 + 38) & 0x100) == 0
    || (a8 & 4) != 0
    || (v19 = *((_QWORD *)v48 + 31), *(_QWORD *)(v19 + 8))
    || *(_QWORD *)(v19 + 24)
    || (v20 = *(_QWORD *)(a3 + 8), (v20 & 1) != 0)
    || (v20 & 0x800) == 0 )
  {
LABEL_23:
    if ( !*(_DWORD *)(a3 + 16) )
    {
      v21 = *(_QWORD *)(a3 + 232);
      if ( v21 )
      {
        if ( *(_DWORD *)(v21 + 104)
          && (*((_DWORD *)v18 + 6) & 2) == 0
          && (*((_DWORD *)v17 + 75) & 0x4000) == 0
          && (*(_BYTE *)v14 & 4) == 0
          && (*(_BYTE *)(a3 + 8) & 1) == 0 )
        {
          for ( i = *(__int64 **)(a3 + 48); i != (__int64 *)(a3 + 48); i = (__int64 *)*i )
          {
            v30 = *((_WORD *)i + 48);
            if ( v30 == 128 || v30 == 176 )
            {
              v31 = (SECTION_OBJECT_POINTERS *)(i[16] + 8);
              if ( v31->DataSectionObject )
              {
                NewFileSize.QuadPart = 0;
                if ( !MmCanFileBeTruncated(v31, &NewFileSize) )
                  goto LABEL_25;
              }
            }
          }
          if ( (v45 & 2) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, &WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(259, 0, "Close.c", 0x53Eu);
            v13 = 259;
            v11 = 0;
            goto LABEL_93;
          }
          RefsPostUsnChange((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3, 0x80000000, 0);
          RefsWriteUsnJournalChanges((struct _IRP_CONTEXT *)a1);
          RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
          v36 = *(_DWORD *)(a1 + 4);
          if ( (v36 & 0x2000) != 0 )
          {
            *(_DWORD *)(a1 + 4) = v36 & 0xFFFFCFFF;
            ExReleaseFastResource(*(_QWORD *)(a3 + 80) + 1208LL, 0);
          }
          RefsReleaseAllExclusiveFcbs((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
        }
      }
    }
    goto LABEL_25;
  }
  if ( *(_DWORD *)(a3 + 16) )
  {
LABEL_25:
    v43 = (*(_BYTE *)(a3 + 8) & 4) != 0 || a6 == 5 || *a5 && (*((_DWORD *)*a5 + 1) & 0x20000000) != 0;
    v22 = *a5;
    if ( *a5 )
    {
      NewFileSize = *(union _LARGE_INTEGER *)((char *)v22 + 72);
      QuadPart = (struct _LCB *)NewFileSize.QuadPart;
      if ( *(_WORD *)v22 == 2056 )
      {
        CmsRowWithBuffer::Reset((struct _CCB *)((char *)v22 + 384));
        v27 = (void *)*((_QWORD *)v22 + 59);
        if ( v27 )
        {
          ExFreePoolWithTag(v27, 0);
          *((_QWORD *)v22 + 59) = 0;
        }
        RefsCleanupIndexCursor(v22);
      }
      if ( (*((_DWORD *)v22 + 1) & 0x4000) != 0 )
        ExFreePoolWithTag(*((PVOID *)v22 + 3), 0);
      v23 = *(_QWORD *)(a3 + 88);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v23 + 8));
      v24 = *((_QWORD *)v22 + 9);
      *((_QWORD *)v22 + 9) = 0;
      if ( v24 )
      {
        ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence((char *)v22 + 56);
        v25[1] = 0;
        *v25 = 0;
      }
      ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence((char *)v22 + 40);
      *((_QWORD *)v22 + 6) = 0;
      *((_QWORD *)v22 + 5) = 0;
      *((_QWORD *)v22 + 6) = MmBadPointer;
      *((_QWORD *)v22 + 5) = MmBadPointer;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a3 + 88) + 8LL));
      KeLeaveGuardedRegion();
      if ( v22 == (struct _CCB *)(a3 + 864) || v22 == (struct _CCB *)(a3 + 800) )
      {
        *(_WORD *)v22 = 0;
      }
      else
      {
        v28 = *(_WORD *)v22 == 2056;
        *(_WORD *)v22 = 0;
        if ( v28 )
          ExFreeToLookasideListEx(&RefsCcbLookasideList, v22);
        else
          ExFreeToLookasideListEx(&RefsCcbDataLookasideList, v22);
      }
      *a5 = 0;
      v26 = NewFileSize;
    }
    else
    {
      v26.QuadPart = 0;
      QuadPart = 0;
    }
    RefsFlushForWriteThrough(a1, a3, 0);
    LOBYTE(v41) = a7;
    v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))RefsDecrementCloseCounts)(
            a1,
            v48,
            (union _LARGE_INTEGER)v26.QuadPart,
            v43,
            v41,
            0);
    goto LABEL_93;
  }
  if ( (*((_DWORD *)a4 + 6) & 0x8000823) != 1 )
    goto LABEL_23;
  v33 = 0;
  for ( j = *(_QWORD **)(a3 + 48); j != (_QWORD *)(a3 + 48); j = (_QWORD *)*j )
  {
    v35 = j[16];
    v32 = *(_QWORD *)(v35 + 8) || *(_QWORD *)(v35 + 24);
    v33 |= v32;
  }
  if ( v33 )
  {
LABEL_81:
    v17 = v48;
    goto LABEL_23;
  }
  if ( a1 == *(_QWORD *)(a1 + 104) && LOBYTE(IoGetTopLevelIrp()->Type) && (v12 & 2) == 0 )
  {
    v47[0] = 0;
    QuadPart = 0;
    RefsCompleteFileDeletion((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3, v48, *a5, v47, &QuadPart, 0);
    v18 = a4;
    goto LABEL_81;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(259, 0, "Close.c", 0x4FAu);
  v13 = 259;
LABEL_93:
  if ( !v11 )
    RefsReleaseFcbWithPaging((struct _IRP_CONTEXT *)a1, (struct _FCB *)a3);
  if ( (*(_DWORD *)v14 & 0x800000) == 0 )
  {
    if ( v42 )
      RefsReleaseVcbCheckDelete((struct _IRP_CONTEXT *)a1, a4);
    else
      RefsReleaseVcb((struct _IRP_CONTEXT *)a1, a4);
  }
  if ( v13 != 259 )
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, 0, v13);
  return v13;
}

```

## disassembly

```asm
0x1403058c0  mov     [rsp+arg_18], r9
0x1403058c5  mov     [rsp+arg_10], r8
0x1403058ca  mov     [rsp+arg_8], rdx
0x1403058cf  mov     [rsp+arg_0], rcx
0x1403058d4  push    rbx
0x1403058d5  push    rsi
0x1403058d6  push    rdi
0x1403058d7  push    r12
0x1403058d9  push    r13
0x1403058db  push    r14
0x1403058dd  push    r15
0x1403058df  sub     rsp, 80h
0x1403058e6  mov     r10, r9
0x1403058e9  mov     rsi, r8
0x1403058ec  mov     r14, rcx
0x1403058ef  mov     [rsp+0B8h+var_78], 0
0x1403058f4  xor     dil, dil
0x1403058f7  mov     [rsp+0B8h+var_76], dil
0x1403058fc  mov     ebx, 1
0x140305901  mov     [rsp+0B8h+var_60], ebx
0x140305905  xor     r15d, r15d
0x140305908  mov     r13d, r15d
0x14030590b  mov     [rsp+0B8h+var_74], r15d
0x140305910  lea     r12, [rcx+8]
0x140305914  mov     [rsp+0B8h+var_48], r12
0x140305919  test    [r12], bl
0x14030591d  jnz     short loc_140305928
0x14030591f  mov     ebx, 3
0x140305924  mov     [rsp+0B8h+var_60], ebx
0x140305928  mov     r8, 20000000000h
0x140305932  mov     rax, [r12]
0x140305936  bt      rax, 17h
0x14030593b  jb      short loc_14030599E
0x14030593d  test    dword ptr [r10+18h], 800h
0x140305945  setz    cl
0x140305948  bt      rax, 8
0x14030594d  setnb   al
0x140305950  test    al, cl
0x140305952  jz      loc_1403061D0
0x140305958  mov     rdx, [r14+68h]
0x14030595c  test    [rdx+8], r8
0x140305960  jnz     short loc_140305972
0x140305962  lea     rcx, [rdx+0A0h]
0x140305969  call    MsInitializeFastResourceOwnerEntry
0x14030596e  or      [rdx+8], r8
0x140305972  movzx   r8d, byte ptr [r14+8]
0x140305977  and     r8b, 1
0x14030597b  lea     rcx, [r10+520h]
0x140305982  add     rdx, 0A0h
0x140305989  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x14030598e  test    al, al
0x140305990  jz      loc_140306156
0x140305996  mov     rdx, [rsp+0B8h+arg_8]
0x14030599e  test    dword ptr [r14+4], 10000h
0x1403059a6  jz      loc_14030609A
0x1403059ac  mov     r9d, ebx
0x1403059af  xor     r8d, r8d
0x1403059b2  mov     rdx, rsi
0x1403059b5  mov     rcx, r14
0x1403059b8  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x1403059bd  test    al, al
0x1403059bf  jz      loc_140306263
0x1403059c5  mov     r8, [rsp+0B8h+arg_8]
0x1403059cd  test    dword ptr [r14+4], 10000h
0x1403059d5  jz      loc_1403060DD
0x1403059db  mov     r9, [rsp+0B8h+arg_18]
0x1403059e3  cmp     [rsp+0B8h+var_78], dil
0x1403059e8  jnz     short loc_140305A03
0x1403059ea  mov     eax, [r12]
0x1403059ee  bt      rax, 17h
0x1403059f3  jb      short loc_140305A03
0x1403059f5  test    dword ptr [r9+18h], 800h
0x1403059fd  jnz     loc_1403061F0
0x140305a03  or      qword ptr [r12], 1
0x140305a08  test    dword ptr [r8+98h], 100h
0x140305a13  jz      short loc_140305A5D
0x140305a15  mov     eax, [rsp+0B8h+arg_38]
0x140305a1c  and     eax, 4
0x140305a1f  jnz     short loc_140305A5D
0x140305a21  mov     rax, [r8+0F8h]
0x140305a28  cmp     qword ptr [rax+8], 0
0x140305a2d  jnz     short loc_140305A5D
0x140305a2f  cmp     qword ptr [rax+18h], 0
0x140305a34  jnz     short loc_140305A5D
0x140305a36  mov     rax, [rsi+8]
0x140305a3a  test    al, 1
0x140305a3c  jnz     short loc_140305A5D
0x140305a3e  bt      rax, 0Bh
0x140305a43  jnb     short loc_140305A5D
0x140305a45  cmp     dword ptr [rsi+10h], 0
0x140305a49  jnz     short loc_140305A73
0x140305a4b  mov     eax, [r9+18h]
0x140305a4f  and     eax, 8000823h
0x140305a54  cmp     eax, 1
0x140305a57  jz      loc_140305E06
0x140305a5d  cmp     dword ptr [rsi+10h], 0
0x140305a61  jnz     short loc_140305A73
0x140305a63  mov     rax, [rsi+0E8h]
0x140305a6a  test    rax, rax
0x140305a6d  jnz     loc_140305C9D
0x140305a73  mov     rcx, [rsp+0B8h+arg_20]
0x140305a7b  test    byte ptr [rsi+8], 4
0x140305a7f  jnz     loc_140305C1F
0x140305a85  cmp     [rsp+0B8h+arg_28], 5
0x140305a8d  jz      loc_140305C1F
0x140305a93  mov     rax, [rcx]
0x140305a96  test    rax, rax
0x140305a99  jz      short loc_140305AA8
0x140305a9b  test    dword ptr [rax+4], 20000000h
0x140305aa2  jnz     loc_140305C1F
0x140305aa8  mov     [rsp+0B8h+var_77], 0
0x140305aad  mov     rbx, [rcx]
0x140305ab0  test    rbx, rbx
0x140305ab3  jz      loc_140305C90
0x140305ab9  mov     rax, [rbx+48h]
0x140305abd  mov     qword ptr [rsp+0B8h+NewFileSize], rax
0x140305ac2  mov     [rsp+0B8h+var_68], rax
0x140305ac7  mov     eax, 808h
0x140305acc  cmp     [rbx], ax
0x140305acf  jz      loc_140305C29
0x140305ad5  test    dword ptr [rbx+4], 4000h
0x140305adc  jnz     loc_140306020
0x140305ae2  mov     rdi, [rsi+58h]
0x140305ae6  call    cs:__imp_KeEnterGuardedRegion
0x140305aed  nop     dword ptr [rax+rax+00h]
0x140305af2  lea     rcx, [rdi+8]; FastMutex
0x140305af6  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140305afd  nop     dword ptr [rax+rax+00h]
0x140305b02  mov     rax, [rbx+48h]
0x140305b06  mov     [rbx+48h], r15
0x140305b0a  test    rax, rax
0x140305b0d  jz      short loc_140305B1F
0x140305b0f  lea     rcx, [rbx+38h]
0x140305b13  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140305b18  mov     [rcx+8], r15
0x140305b1c  mov     [rcx], r15
0x140305b1f  lea     rcx, [rbx+28h]
0x140305b23  call    ?RemoveEntryListWriteNoFence@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAEPEAU_LIST_ENTRY@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveEntryListWriteNoFence(_LIST_ENTRY *)
0x140305b28  mov     [rbx+30h], r15
0x140305b2c  mov     [rbx+28h], r15
0x140305b30  mov     rax, cs:MmBadPointer
0x140305b37  mov     rcx, [rax]
0x140305b3a  mov     [rbx+30h], rcx
0x140305b3e  mov     [rbx+28h], rcx
0x140305b42  mov     rcx, [rsi+58h]
0x140305b46  add     rcx, 8; FastMutex
0x140305b4a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140305b51  nop     dword ptr [rax+rax+00h]
0x140305b56  call    cs:__imp_KeLeaveGuardedRegion
0x140305b5d  nop     dword ptr [rax+rax+00h]
0x140305b62  lea     rax, [rsi+360h]
0x140305b69  cmp     rbx, rax
0x140305b6c  jz      short loc_140305B7E
0x140305b6e  lea     rax, [rsi+320h]
0x140305b75  cmp     rbx, rax
0x140305b78  jnz     loc_140305C63
0x140305b7e  mov     [rbx], r15w
0x140305b82  mov     rax, [rsp+0B8h+arg_20]
0x140305b8a  mov     [rax], r15
0x140305b8d  mov     rbx, qword ptr [rsp+0B8h+NewFileSize]
0x140305b92  xor     r8d, r8d
0x140305b95  mov     rdx, rsi
0x140305b98  mov     rcx, r14
0x140305b9b  call    ?RefsFlushForWriteThrough@@YAXPEAU_IRP_CONTEXT@@PEAXW4REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS@@@Z; RefsFlushForWriteThrough(_IRP_CONTEXT *,void *,REFS_FLUSH_FOR_WRITE_THROUGH_FLAGS)
0x140305ba0  jmp     short loc_140305BE9
0x140305ba2  mov     r14, [rsp+0B8h+arg_0]
0x140305baa  test    r14, r14
0x140305bad  jz      short loc_140305BBF
0x140305baf  and     dword ptr [r14+4], 0FFFFFEFFh
0x140305bb7  mov     dword ptr [r14+10h], 0
0x140305bbf  mov     dword ptr [r14+10h], 0
0x140305bc7  and     qword ptr [r14+8], 0FFFFFFFFFFFFFBFFh
0x140305bcf  xor     r15d, r15d
0x140305bd2  mov     rsi, [rsp+0B8h+arg_10]
0x140305bda  mov     r13d, [rsp+0B8h+var_74]
0x140305bdf  mov     rbx, [rsp+0B8h+var_68]
0x140305be4  mov     r12, [rsp+0B8h+var_48]
0x140305be9  mov     dword ptr [rsp+0B8h+var_90], r15d
0x140305bee  movzx   eax, [rsp+0B8h+arg_30]
0x140305bf6  mov     byte ptr [rsp+0B8h+var_98], al
0x140305bfa  movzx   r9d, [rsp+0B8h+var_77]
0x140305c00  mov     r8, rbx
0x140305c03  mov     rdx, [rsp+0B8h+arg_8]
0x140305c0b  mov     rcx, r14
0x140305c0e  call    ?RefsDecrementCloseCounts@@YA_NPEAU_IRP_CONTEXT@@AEAU_SCB@@PEAU_LCB@@EEW4CloseCountFlags@@@Z; RefsDecrementCloseCounts(_IRP_CONTEXT *,_SCB &,_LCB *,uchar,uchar,CloseCountFlags)
0x140305c13  movzx   edi, al
0x140305c16  mov     [rsp+0B8h+var_76], al
0x140305c1a  jmp     loc_140306037
0x140305c1f  mov     [rsp+0B8h+var_77], 1
0x140305c24  jmp     loc_140305AAD
0x140305c29  lea     rcx, [rbx+180h]; this
0x140305c30  call    ?Reset@CmsRowWithBuffer@@QEAAXXZ; CmsRowWithBuffer::Reset(void)
0x140305c35  mov     rcx, [rbx+1D8h]; P
0x140305c3c  test    rcx, rcx
0x140305c3f  jz      short loc_140305C56
0x140305c41  xor     edx, edx; Tag
0x140305c43  call    cs:__imp_ExFreePoolWithTag
0x140305c4a  nop     dword ptr [rax+rax+00h]
0x140305c4f  mov     [rbx+1D8h], r15
0x140305c56  mov     rcx, rbx; struct _CCB *
0x140305c59  call    ?RefsCleanupIndexCursor@@YAXAEAU_CCB@@@Z; RefsCleanupIndexCursor(_CCB &)
0x140305c5e  jmp     loc_140305AD5
0x140305c63  mov     eax, 808h
0x140305c68  mov     rdx, rbx; Entry
0x140305c6b  cmp     [rbx], ax
0x140305c6e  mov     [rbx], r15w
0x140305c72  jz      loc_140305D3A
0x140305c78  lea     rcx, ?RefsCcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140305c7f  call    cs:__imp_ExFreeToLookasideListEx
0x140305c86  nop     dword ptr [rax+rax+00h]
0x140305c8b  jmp     loc_140305B82
0x140305c90  mov     rbx, r15
0x140305c93  mov     [rsp+0B8h+var_68], rbx
0x140305c98  jmp     loc_140305B92
0x140305c9d  cmp     dword ptr [rax+68h], 0
0x140305ca1  jz      loc_140305A73
0x140305ca7  mov     eax, [r9+18h]
0x140305cab  test    al, 2
0x140305cad  jnz     loc_140305A73
0x140305cb3  test    dword ptr [r8+12Ch], 4000h
0x140305cbe  jnz     loc_140305A73
0x140305cc4  test    byte ptr [r12], 4
0x140305cc9  jnz     loc_140305A73
0x140305ccf  test    byte ptr [rsi+8], 1
0x140305cd3  jnz     loc_140305A73
0x140305cd9  lea     rdi, [rsi+30h]
0x140305cdd  mov     rbx, [rdi]
0x140305ce0  mov     ecx, 80h
0x140305ce5  mov     edx, 0B0h
0x140305cea  cmp     rbx, rdi
0x140305ced  jz      short loc_140305D52
0x140305cef  movzx   eax, word ptr [rbx+60h]
0x140305cf3  cmp     ax, cx
0x140305cf6  jnz     loc_140305ED4
0x140305cfc  mov     rcx, [rbx+80h]
0x140305d03  add     rcx, 8; SectionPointer
0x140305d07  cmp     qword ptr [rcx], 0
0x140305d0b  jz      short loc_140305D30
0x140305d0d  mov     qword ptr [rsp+0B8h+NewFileSize], r15
0x140305d12  lea     rdx, [rsp+0B8h+NewFileSize]; NewFileSize
0x140305d17  call    cs:__imp_MmCanFileBeTruncated
0x140305d1e  nop     dword ptr [rax+rax+00h]
0x140305d23  test    al, al
0x140305d25  jz      loc_140305A73
0x140305d2b  mov     edx, 0B0h
0x140305d30  mov     ecx, 80h
0x140305d35  mov     rbx, [rbx]
0x140305d38  jmp     short loc_140305CEA
0x140305d3a  lea     rcx, ?RefsCcbLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140305d41  call    cs:__imp_ExFreeToLookasideListEx
0x140305d48  nop     dword ptr [rax+rax+00h]
0x140305d4d  jmp     loc_140305B82
0x140305d52  mov     eax, [rsp+0B8h+var_60]
0x140305d56  and     eax, 2
0x140305d59  jz      loc_140305F37
0x140305d5f  lea     rax, WPP_GLOBAL_Control
0x140305d66  mov     rcx, cs:WPP_GLOBAL_Control
0x140305d6d  cmp     rcx, rax
0x140305d70  jnz     loc_140305EE2
0x140305d76  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140305d7d  test    al, al
0x140305d7f  jnz     loc_140305F19
0x140305d85  mov     r13d, 103h
0x140305d8b  mov     [rsp+0B8h+var_74], r13d
0x140305d90  xor     dil, dil
0x140305d93  jmp     loc_140306037
0x140305d98  cmp     rax, rcx
0x140305d9b  jnz     short loc_140305DF3
0x140305d9d  test    dl, dl
0x140305d9f  jnz     loc_140305E72
0x140305da5  cmp     r14, [r14+68h]
0x140305da9  jz      short loc_140305E11
0x140305dab  lea     rax, WPP_GLOBAL_Control
0x140305db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140305db9  cmp     rcx, rax
0x140305dbc  jnz     loc_140305E7F
0x140305dc2  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140305dc9  test    al, al
0x140305dcb  jnz     loc_140305EB6
0x140305dd1  mov     r13d, 103h
0x140305dd7  mov     [rsp+0B8h+var_74], r13d
0x140305ddc  jmp     loc_140306037
0x140305de1  cmp     qword ptr [r8+18h], 0
0x140305de6  jnz     short loc_140305E01
0x140305de8  xor     r8b, r8b
0x140305deb  or      dl, r8b
0x140305dee  mov     rax, [rax]
0x140305df1  jmp     short loc_140305D98
0x140305df3  mov     r8, [rax+80h]
0x140305dfa  cmp     qword ptr [r8+8], 0
0x140305dff  jz      short loc_140305DE1
0x140305e01  mov     r8b, 1
0x140305e04  jmp     short loc_140305DEB
0x140305e06  xor     dl, dl
0x140305e08  lea     rcx, [rsi+30h]
0x140305e0c  mov     rax, [rcx]
0x140305e0f  jmp     short loc_140305D98
0x140305e11  call    cs:__imp_IoGetTopLevelIrp
0x140305e18  nop     dword ptr [rax+rax+00h]
0x140305e1d  cmp     byte ptr [rax], 0
  ... truncated ...
```
