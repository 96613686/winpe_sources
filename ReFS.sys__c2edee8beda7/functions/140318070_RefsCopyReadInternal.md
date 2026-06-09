# RefsCopyReadInternal

- ea: `0x140318070`
- end: `0x1403188b3`
- name: `RefsCopyReadInternal`
- size: `2115`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, __int64, __int64, PIO_STATUS_BLOCK)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1402d2d20`
- `0x140317ff0`

## callees

- `0x140050ba0`
- `0x140063b10`
- `0x1400757c0`
- `0x1400801d0`
- `0x1400862c0`
- `0x140088990`
- `0x1400889f0`
- `0x14008c720`
- `0x1400a0cf0`
- `0x1400a780c`
- `0x1400a7af8`
- `0x1400a8a5c`
- `0x1400d0fd8`
- `0x1401f3fc0`
- `0x140318070`
- `0x1403188bc`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1403180cb`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1403180cb`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14031825e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1403184fb`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14031825e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1403184fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140318106`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140318106`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140318557`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140318557`
- `ntoskrnl!IoGetCurrentProcess` at `0x1403186f9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1403186f9`
- `ntoskrnl!CcCopyRead` at `0x14031829c`
- `ntoskrnl!CcCopyRead` at `0x14031829c`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140318725`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140318725`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140318596`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140318596`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x140318154`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x140318154`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x14031880f`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x14031880f`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1403185f6`
- `ntoskrnl!FsRtlIncrementCcFastMdlReadWait` at `0x1403185f6`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x140318823`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x140318823`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140318739`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140318834`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140318739`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x140318834`
- `ntoskrnl!CcMdlRead` at `0x140318468`
- `ntoskrnl!CcMdlRead` at `0x140318468`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403185a5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403185a5`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034321e`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14034321e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403185b9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403185b9`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403185c5`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403185c5`

## string_xrefs

- `0x140318799`: `Read.c`

## pseudocode

```c
BOOLEAN __fastcall RefsCopyReadInternal(
        struct _FILE_OBJECT *a1,
        PLARGE_INTEGER FileOffset,
        BOOLEAN a3,
        ULONG a4,
        void *a5,
        PMDL *a6,
        PIO_STATUS_BLOCK IoStatus)
{
  char *v10; // rbx
  __int64 v11; // rax
  struct _IRP_CONTEXT *v12; // r14
  __int16 v13; // ax
  char *v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rax
  char v20; // al
  union _LARGE_INTEGER v21; // rdi
  DWORD LowPart; // r8d
  BOOLEAN v23; // di
  __int64 v24; // r8
  int v25; // ecx
  _DWORD *v26; // r15
  char v27; // r9
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // edx
  __int64 v31; // r11
  __int64 v32; // rax
  DWORD v33; // edx
  char v34; // r10
  unsigned int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  struct _FAST_MUTEX *v40; // rdi
  char *v41; // rcx
  char *v42; // rdx
  __int64 v43; // r9
  __int64 v44; // rax
  __int64 v45; // r8
  __int64 v46; // rcx
  LONGLONG QuadPart; // rax
  PEPROCESS CurrentProcess; // rax
  _DWORD *FsContext2; // [rsp+38h] [rbp-360h]
  union _LARGE_INTEGER Length; // [rsp+40h] [rbp-358h] BYREF
  struct _IRP_CONTEXT *v53; // [rsp+48h] [rbp-350h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-348h]
  union _LARGE_INTEGER StartingByte; // [rsp+58h] [rbp-340h] BYREF
  PMDL *MdlChain; // [rsp+60h] [rbp-338h]
  char *FsContext; // [rsp+68h] [rbp-330h]
  char v58; // [rsp+70h] [rbp-328h] BYREF

  Buffer = a5;
  MdlChain = a6;
  if ( !IoGetTopLevelIrp() )
  {
    if ( !FileOffset[2].LowPart )
    {
      v23 = 0;
      IoStatus->Status = 0;
      IoStatus->Information = 0;
      return v23;
    }
    v53 = (struct _IRP_CONTEXT *)&v58;
    FsContext = (char *)a1->FsContext;
    v10 = FsContext;
    FsContext2 = a1->FsContext2;
    KeEnterCriticalRegion();
    RefsInitializeIrpContext(0, 1u, 1u, &v53);
    v11 = *((_QWORD *)v10 + 18);
    v12 = v53;
    *((_QWORD *)v53 + 8) = v11;
    if ( *(_DWORD *)(v11 + 556) )
    {
      v23 = 0;
LABEL_80:
      RefsCleanupIrpContext(v12, 0);
      KeLeaveCriticalRegion();
      return v23;
    }
    if ( a6 )
    {
      FsRtlIncrementCcFastMdlReadWait();
    }
    else if ( a3 )
    {
      FsRtlIncrementCcFastReadWait();
    }
    else
    {
      FsRtlIncrementCcFastReadNoWait();
    }
    if ( !*((_QWORD *)v10 + 2) )
      goto LABEL_122;
    v13 = *(_WORD *)v10;
    if ( a1->PrivateCacheMap != (PVOID)1 )
    {
      if ( v13 == 2050 )
        v14 = v10;
      else
        v14 = (char *)*((_QWORD *)v10 + 17);
      if ( !v12 )
        goto LABEL_107;
      v15 = *((_QWORD *)v14 + 12);
      v16 = *((_QWORD *)v12 + 13);
      v17 = *(_QWORD *)(v16 + 336);
      v18 = v16 + 248;
      if ( !v17 )
      {
        *(_QWORD *)(v16 + 336) = v15;
        MsInitializeFastResourceOwnerEntry(v18);
        goto LABEL_14;
      }
      if ( v17 != v15 )
      {
        if ( *(_DWORD *)(v16 + 320) )
        {
LABEL_107:
          v18 = 0;
          goto LABEL_14;
        }
        *(_QWORD *)(v16 + 336) = v15;
      }
LABEL_14:
      v19 = *((_QWORD *)v14 + 12);
      if ( v18 )
        v20 = MsAcquireFastResourceSharedInternal<0>(v19, v18, a3);
      else
        v20 = MsAcquireFastResourceSharedLegacy<0>(v19, a3);
      if ( v20 )
        goto LABEL_17;
LABEL_122:
      v23 = 0;
LABEL_123:
      FsRtlIncrementCcFastReadResourceMiss();
      goto LABEL_80;
    }
    if ( v13 == 2050 )
      v41 = v10;
    else
      v41 = (char *)*((_QWORD *)v10 + 17);
    v23 = MsAcquireFastResourceExclusive(*((_QWORD *)v41 + 12), 0, a3);
    if ( !v23 )
      goto LABEL_123;
    v23 = RefsSetupCacheMapDuringFastIo(v12, a1, (struct DataSCB *)v10);
    if ( !v23 )
    {
      FsRtlIncrementCcFastReadNotPossible();
      goto LABEL_73;
    }
    if ( *(_WORD *)v10 == 2050 )
      v42 = v10;
    else
      v42 = (char *)*((_QWORD *)v10 + 17);
    if ( !v12 )
      goto LABEL_118;
    v43 = *((_QWORD *)v42 + 12);
    v44 = *((_QWORD *)v12 + 13);
    v45 = *(_QWORD *)(v44 + 336);
    v46 = v44 + 248;
    if ( !v45 )
    {
      *(_QWORD *)(v44 + 336) = v43;
      MsInitializeFastResourceOwnerEntry(v46);
      goto LABEL_96;
    }
    if ( v45 != v43 )
    {
      if ( *(_DWORD *)(v44 + 320) )
      {
LABEL_118:
        v46 = 0;
        goto LABEL_96;
      }
      *(_QWORD *)(v44 + 336) = v43;
    }
LABEL_96:
    if ( v46 )
      MsConvertFastResourceExclusiveToShared(*((_QWORD *)v42 + 12), v46);
    else
      MsConvertFastResourceExclusiveToSharedLegacy(*((_QWORD *)v42 + 12));
LABEL_17:
    if ( !a1->PrivateCacheMap || !v10[5] )
      goto LABEL_103;
    if ( !RefsIsFileOpen(*((const struct _FCB **)v10 + 17))
      || a1->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v10 + 31) + 8LL) )
    {
      goto LABEL_104;
    }
    if ( v10[5] == 2 )
    {
      StartingByte = *FileOffset;
      Length.QuadPart = FileOffset[2].LowPart;
      if ( *((_QWORD *)v10 + 48) )
      {
        CurrentProcess = IoGetCurrentProcess();
        if ( !FsRtlFastCheckLockForRead(*((PFILE_LOCK *)v10 + 48), &StartingByte, &Length, a4, a1, CurrentProcess) )
        {
LABEL_103:
          FsRtlIncrementCcFastReadNotPossible();
LABEL_104:
          v23 = 0;
          goto LABEL_73;
        }
      }
    }
    if ( (*((_DWORD *)v10 + 43) & 1) != 0 )
    {
      v40 = (struct _FAST_MUTEX *)*((_QWORD *)v10 + 6);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(v40);
      v21 = *(union _LARGE_INTEGER *)(v10 + 32);
      ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)v10 + 6));
      KeLeaveGuardedRegion();
    }
    else
    {
      v21 = *(union _LARGE_INTEGER *)(v10 + 32);
    }
    if ( FileOffset[1].QuadPart > v21.QuadPart )
    {
      QuadPart = FileOffset->QuadPart;
      if ( FileOffset->QuadPart >= v21.QuadPart )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
            3221225489LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741807, 0, "Read.c", 0x2ABu);
        IoStatus->Status = -1073741807;
        IoStatus->Information = 0;
        v23 = 1;
        goto LABEL_73;
      }
      FileOffset[1] = v21;
      FileOffset[2].LowPart = v21.LowPart - QuadPart;
    }
    IoSetTopLevelIrp((PIRP)4);
    IoStatus->Status = 0;
    LowPart = FileOffset[2].LowPart;
    if ( MdlChain )
    {
      CcMdlRead(a1, FileOffset, LowPart, MdlChain, IoStatus);
      v23 = 1;
    }
    else
    {
      v23 = CcCopyRead(a1, FileOffset, LowPart, a3, Buffer, IoStatus);
      if ( !v23 )
      {
LABEL_72:
        IoSetTopLevelIrp(0);
LABEL_73:
        if ( *(_WORD *)v10 != 2050 )
          v10 = (char *)*((_QWORD *)v10 + 17);
        if ( !v12
          || (v36 = *((_QWORD *)v12 + 13), *(_QWORD *)(v36 + 336) != *((_QWORD *)v10 + 12))
          || (v37 = v36 + 248, !*(_DWORD *)(v36 + 320)) )
        {
          v37 = 0;
        }
        v38 = *((_QWORD *)v10 + 12);
        if ( v37 )
          MsReleaseFastResource(v38, v37);
        else
          MsReleaseFastResourceLegacy(v38);
        goto LABEL_80;
      }
      a1->CurrentByteOffset.QuadPart = FileOffset->QuadPart + IoStatus->Information;
    }
    v24 = *((_QWORD *)v10 + 17);
    Buffer = 0;
    v25 = *(_DWORD *)(*(_QWORD *)(v24 + 88) + 296LL);
    v26 = FsContext2;
    if ( FsContext2
      && (FsContext2[1] & 0x40) == 0
      && (((unsigned __int8)dword_1402682AC & 0x40) == 0 || BYTE1(v25)
                                                         || BYTE2(v25)
                                                         || (*(_BYTE *)(v24 + 8) & 0x10) != 0) )
    {
      v31 = MEMORY[0xFFFFF78000000014];
      Buffer = (PVOID)MEMORY[0xFFFFF78000000014];
      Length.LowPart = 0;
      v27 = 0;
      v32 = *(_QWORD *)(v24 + 88);
      v33 = *(_DWORD *)(v32 + 296);
      *(_DWORD *)(v32 + 296) = 0;
      Length.LowPart = v33;
      if ( (_BYTE)v33 || BYTE2(v33) || BYTE1(v33) )
      {
        if ( BYTE1(v33) )
        {
          *(_QWORD *)(v24 + 112) = v31;
          v27 = 1;
        }
        if ( BYTE2(v33) )
        {
          *(_QWORD *)(v24 + 120) = v31;
          v27 = 1;
        }
        if ( (_BYTE)v33
          && (((unsigned __int8)dword_1402682AC & 0x40) == 0
           || BYTE1(v33)
           || BYTE2(v33)
           || (*(_BYTE *)(v24 + 8) & 0x10) != 0) )
        {
          *(_QWORD *)(v24 + 184) = v31;
        }
        v26 = FsContext2;
      }
      if ( (_BYTE)v25 )
        goto LABEL_37;
    }
    else
    {
      v27 = 0;
      v28 = *(_QWORD *)(v24 + 88);
      v29 = *(_DWORD *)(v28 + 296);
      *(_DWORD *)(v28 + 296) = 0;
      v30 = v29 >> 8;
      if ( (_BYTE)v29 )
      {
        v34 = v29;
      }
      else
      {
        if ( !BYTE2(v29) && !BYTE1(v29) )
          goto LABEL_37;
        v34 = 0;
      }
      v31 = MEMORY[0xFFFFF78000000014];
      if ( BYTE1(v29) )
      {
        *(_QWORD *)(v24 + 112) = MEMORY[0xFFFFF78000000014];
        v27 = 1;
      }
      v35 = HIWORD(v29);
      if ( (_BYTE)v35 )
      {
        *(_QWORD *)(v24 + 120) = v31;
        v27 = 1;
      }
      if ( !v34
        || ((unsigned __int8)dword_1402682AC & 0x40) != 0
        && !(_BYTE)v30
        && !(_BYTE)v35
        && (*(_BYTE *)(v24 + 8) & 0x10) == 0 )
      {
        goto LABEL_37;
      }
    }
    *(_QWORD *)(v24 + 184) = v31;
LABEL_37:
    if ( v26 && *((_BYTE *)v26 + 80) != 4 && v27 )
      v26[1] |= 0x10000u;
    a1->Flags |= 0x80000u;
    goto LABEL_72;
  }
  return 0;
}

```

## disassembly

```asm
0x140318070  push    rbx
0x140318072  push    rsi
0x140318073  push    rdi
0x140318074  push    r12
0x140318076  push    r13
0x140318078  push    r14
0x14031807a  push    r15
0x14031807c  sub     rsp, 360h
0x140318083  mov     rax, cs:__security_cookie
0x14031808a  xor     rax, rsp
0x14031808d  mov     [rsp+398h+var_48], rax
0x140318095  mov     [rsp+398h+Key], r9d
0x14031809a  movzx   edi, r8b
0x14031809e  mov     [rsp+398h+var_365], r8b
0x1403180a3  mov     r15, rdx
0x1403180a6  mov     rsi, rcx
0x1403180a9  mov     r13, [rsp+398h+arg_30]
0x1403180b1  mov     rax, [rsp+398h+arg_20]
0x1403180b9  mov     [rsp+398h+var_348], rax
0x1403180be  mov     r12, [rsp+398h+arg_28]
0x1403180c6  mov     [rsp+398h+MdlChain], r12
0x1403180cb  call    cs:__imp_IoGetTopLevelIrp
0x1403180d2  nop     dword ptr [rax+rax+00h]
0x1403180d7  test    rax, rax
0x1403180da  jnz     loc_140318800
0x1403180e0  cmp     [r15+10h], eax
0x1403180e4  jz      loc_1403188A0
0x1403180ea  lea     rax, [rsp+398h+var_328]
0x1403180ef  mov     [rsp+398h+var_350], rax
0x1403180f4  mov     rbx, [rsi+18h]
0x1403180f8  mov     [rsp+398h+var_330], rbx
0x1403180fd  mov     rax, [rsi+20h]
0x140318101  mov     [rsp+398h+var_360], rax
0x140318106  call    cs:__imp_KeEnterCriticalRegion
0x14031810d  nop     dword ptr [rax+rax+00h]
0x140318112  lea     r9, [rsp+398h+var_350]; struct _IRP_CONTEXT **
0x140318117  mov     r8b, 1; unsigned __int8
0x14031811a  movzx   edx, r8b; unsigned __int8
0x14031811e  xor     ecx, ecx; Irp
0x140318120  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x140318125  mov     rax, [rbx+90h]
0x14031812c  mov     r14, [rsp+398h+var_350]
0x140318131  mov     [r14+40h], rax
0x140318135  cmp     dword ptr [rax+22Ch], 0
0x14031813c  ja      loc_140318807
0x140318142  test    r12, r12
0x140318145  jnz     loc_1403185F6
0x14031814b  test    dil, dil
0x14031814e  jz      loc_14031880F
0x140318154  call    cs:__imp_FsRtlIncrementCcFastReadWait
0x14031815b  nop     dword ptr [rax+rax+00h]
0x140318160  cmp     qword ptr [rbx+10h], 0
0x140318165  jz      loc_140318820
0x14031816b  movzx   eax, word ptr [rbx]
0x14031816e  cmp     qword ptr [rsi+30h], 1
0x140318173  jz      loc_140318607
0x140318179  mov     ecx, 802h
0x14031817e  cmp     ax, cx
0x140318181  jnz     loc_1403185EA
0x140318187  mov     rdx, rbx
0x14031818a  test    r14, r14
0x14031818d  jz      loc_14031875D
0x140318193  mov     r9, [rdx+60h]
0x140318197  mov     rax, [r14+68h]
0x14031819b  mov     r8, [rax+150h]
0x1403181a2  lea     rcx, [rax+0F8h]
0x1403181a9  test    r8, r8
0x1403181ac  jnz     loc_14031874A
0x1403181b2  mov     [rax+150h], r9
0x1403181b9  call    MsInitializeFastResourceOwnerEntry
0x1403181be  xor     r12d, r12d
0x1403181c1  mov     rax, [rdx+60h]
0x1403181c5  test    rcx, rcx
0x1403181c8  jz      loc_1403186C9
0x1403181ce  movzx   r8d, dil
0x1403181d2  mov     rdx, rcx
0x1403181d5  mov     rcx, rax
0x1403181d8  call    ??$MsAcquireFastResourceSharedInternal@$0A@@@YAEPEAU_MS_FAST_RESOURCE@@PEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@E@Z; MsAcquireFastResourceSharedInternal<0>(_MS_FAST_RESOURCE *,_MS_FAST_RESOURCE_OWNER_ENTRY *,uchar)
0x1403181dd  test    al, al
0x1403181df  jz      loc_140318820
0x1403181e5  cmp     qword ptr [rsi+30h], 0
0x1403181ea  jz      loc_140318739
0x1403181f0  cmp     byte ptr [rbx+5], 0
0x1403181f4  jz      loc_140318739
0x1403181fa  mov     rcx, [rbx+88h]; struct _FCB *
0x140318201  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x140318206  test    al, al
0x140318208  jz      loc_140318745
0x14031820e  mov     rax, [rbx+0F8h]
0x140318215  add     rax, 8
0x140318219  cmp     [rsi+28h], rax
0x14031821d  jnz     loc_140318745
0x140318223  cmp     byte ptr [rbx+5], 2
0x140318227  jz      loc_1403186DA
0x14031822d  mov     ecx, [rbx+0ACh]
0x140318233  test    cl, 1
0x140318236  jnz     loc_140318592
0x14031823c  mov     rdi, [rbx+20h]
0x140318240  nop
0x140318241  mov     eax, [rbx+0ACh]
0x140318247  cmp     ecx, eax
0x140318249  jnz     loc_140318592
0x14031824f  cmp     [r15+8], rdi
0x140318253  jg      loc_1403186AE
0x140318259  mov     ecx, 4; Irp
0x14031825e  call    cs:__imp_IoSetTopLevelIrp
0x140318265  nop     dword ptr [rax+rax+00h]
0x14031826a  nop
0x14031826b  mov     [r13+0], r12d
0x14031826f  mov     r8d, [r15+10h]; Length
0x140318273  mov     r9, [rsp+398h+MdlChain]; MdlChain
0x140318278  mov     rdx, r15; FileOffset
0x14031827b  mov     rcx, rsi; FileObject
0x14031827e  test    r9, r9
0x140318281  jnz     loc_140318463
0x140318287  mov     [rsp+398h+IoStatus], r13; IoStatus
0x14031828c  mov     rax, [rsp+398h+var_348]
0x140318291  mov     [rsp+398h+Buffer], rax; Buffer
0x140318296  movzx   r9d, [rsp+398h+var_365]; Wait
0x14031829c  call    cs:__imp_CcCopyRead
0x1403182a3  nop     dword ptr [rax+rax+00h]
0x1403182a8  movzx   edi, al
0x1403182ab  mov     [rsp+398h+var_366], al
0x1403182af  test    al, al
0x1403182b1  jz      short loc_1403182BE
0x1403182b3  mov     rax, [r13+8]
0x1403182b7  add     rax, [r15]
0x1403182ba  mov     [rsi+68h], rax
0x1403182be  test    dil, dil
0x1403182c1  jz      loc_1403184D8
0x1403182c7  mov     r8, [rbx+88h]
0x1403182ce  mov     [rsp+398h+var_348], r12
0x1403182d3  mov     [rsp+398h+Key], r12d
0x1403182d8  mov     rax, [r8+58h]
0x1403182dc  mov     ecx, [rax+128h]
0x1403182e2  mov     [rsp+398h+Key], ecx
0x1403182e6  mov     r15, [rsp+398h+var_360]
0x1403182eb  test    r15, r15
0x1403182ee  jz      short loc_14031831B
0x1403182f0  mov     eax, [r15+4]
0x1403182f4  test    al, 40h
0x1403182f6  jnz     short loc_14031831B
0x1403182f8  mov     eax, cs:dword_1402682AC
0x1403182fe  test    al, 40h
0x140318300  jz      short loc_14031837F
0x140318302  mov     eax, ecx
0x140318304  shr     eax, 8
0x140318307  test    al, al
0x140318309  jnz     short loc_14031837F
0x14031830b  mov     eax, ecx
0x14031830d  shr     eax, 10h
0x140318310  test    al, al
0x140318312  jnz     short loc_14031837F
0x140318314  test    byte ptr [r8+8], 10h
0x140318319  jnz     short loc_14031837F
0x14031831b  mov     dword ptr [rsp+398h+var_360], r12d
0x140318320  xor     r9b, r9b
0x140318323  mov     [rsp+398h+var_367], r9b
0x140318328  mov     rax, [r8+58h]
0x14031832c  mov     ecx, [rax+128h]
0x140318332  mov     [rax+128h], r12d
0x140318339  mov     dword ptr [rsp+398h+var_360], ecx
0x14031833d  mov     edx, ecx
0x14031833f  shr     edx, 8
0x140318342  test    cl, cl
0x140318344  jnz     loc_140318424
0x14031834a  mov     eax, ecx
0x14031834c  shr     eax, 10h
0x14031834f  test    al, al
0x140318351  jnz     loc_1403183D9
0x140318357  test    dl, dl
0x140318359  jnz     short loc_1403183D9
0x14031835b  test    r15, r15
0x14031835e  jz      short loc_140318370
0x140318360  cmp     byte ptr [r15+50h], 4
0x140318365  jz      short loc_140318370
0x140318367  test    r9b, r9b
0x14031836a  jnz     loc_1403184CB
0x140318370  mov     eax, [rsi+50h]
0x140318373  bts     eax, 13h
0x140318377  mov     [rsi+50h], eax
0x14031837a  jmp     loc_1403184D8
0x14031837f  mov     rax, 0FFFFF78000000014h
0x140318389  mov     r11, [rax]
0x14031838c  mov     [rsp+398h+var_348], r11
0x140318391  mov     dword ptr [rsp+398h+Length], r12d
0x140318396  xor     r9b, r9b
0x140318399  mov     [rsp+398h+var_368], r9b
0x14031839e  mov     rax, [r8+58h]
0x1403183a2  mov     edx, [rax+128h]
0x1403183a8  mov     [rax+128h], r12d
0x1403183af  mov     dword ptr [rsp+398h+Length], edx
0x1403183b3  mov     r10d, edx
0x1403183b6  shr     r10d, 8
0x1403183ba  test    dl, dl
0x1403183bc  jnz     short loc_14031842A
0x1403183be  mov     eax, edx
0x1403183c0  shr     eax, 10h
0x1403183c3  test    al, al
0x1403183c5  jnz     short loc_14031842A
0x1403183c7  test    r10b, r10b
0x1403183ca  jnz     short loc_14031842A
0x1403183cc  test    cl, cl
0x1403183ce  jnz     short loc_14031835B
0x1403183d0  mov     [r8+0B8h], r11
0x1403183d7  jmp     short loc_14031835B
0x1403183d9  xor     r10b, r10b
0x1403183dc  mov     rax, 0FFFFF78000000014h
0x1403183e6  mov     r11, [rax]
0x1403183e9  test    dl, dl
0x1403183eb  jnz     loc_1403184A9
0x1403183f1  shr     ecx, 10h
0x1403183f4  test    cl, cl
0x1403183f6  jnz     loc_1403184BA
0x1403183fc  test    r10b, r10b
0x1403183ff  jz      loc_14031835B
0x140318405  mov     eax, cs:dword_1402682AC
0x14031840b  test    al, 40h
0x14031840d  jz      short loc_1403183D0
0x14031840f  test    dl, dl
0x140318411  jnz     short loc_1403183D0
0x140318413  test    cl, cl
0x140318415  jnz     short loc_1403183D0
0x140318417  test    byte ptr [r8+8], 10h
0x14031841c  jz      loc_14031835B
0x140318422  jmp     short loc_1403183D0
0x140318424  movzx   r10d, cl
0x140318428  jmp     short loc_1403183DC
0x14031842a  test    r10b, r10b
0x14031842d  jnz     short loc_140318481
0x14031842f  mov     r15d, edx
0x140318432  shr     r15d, 10h
0x140318436  test    r15b, r15b
0x140318439  jnz     short loc_14031848F
0x14031843b  test    dl, dl
0x14031843d  jz      short loc_140318459
0x14031843f  mov     eax, cs:dword_1402682AC
0x140318445  test    al, 40h
0x140318447  jnz     short loc_14031849D
0x140318449  mov     [r8+0B8h], r11
0x140318450  jmp     short loc_140318459
0x140318452  test    byte ptr [r8+8], 10h
0x140318457  jnz     short loc_140318449
0x140318459  mov     r15, [rsp+398h+var_360]
0x14031845e  jmp     loc_1403183CC
0x140318463  mov     [rsp+398h+Buffer], r13; IoStatus
0x140318468  call    cs:__imp_CcMdlRead
0x14031846f  nop     dword ptr [rax+rax+00h]
0x140318474  mov     dil, 1
0x140318477  mov     [rsp+398h+var_366], dil
0x14031847c  jmp     loc_1403182C7
0x140318481  mov     [r8+70h], r11
0x140318485  mov     r9b, 1
0x140318488  mov     [rsp+398h+var_368], r9b
0x14031848d  jmp     short loc_14031842F
0x14031848f  mov     [r8+78h], r11
0x140318493  mov     r9b, 1
0x140318496  mov     [rsp+398h+var_368], r9b
0x14031849b  jmp     short loc_14031843B
0x14031849d  test    r10b, r10b
0x1403184a0  jnz     short loc_140318449
0x1403184a2  test    r15b, r15b
0x1403184a5  jnz     short loc_140318449
0x1403184a7  jmp     short loc_140318452
0x1403184a9  mov     [r8+70h], r11
0x1403184ad  mov     r9b, 1
0x1403184b0  mov     [rsp+398h+var_367], r9b
0x1403184b5  jmp     loc_1403183F1
0x1403184ba  mov     [r8+78h], r11
0x1403184be  mov     r9b, 1
0x1403184c1  mov     [rsp+398h+var_367], r9b
0x1403184c6  jmp     loc_1403183FC
0x1403184cb  or      dword ptr [r15+4], 10000h
0x1403184d3  jmp     loc_140318370
0x1403184d8  mov     esi, 802h
0x1403184dd  jmp     short loc_1403184F9
0x1403184df  xor     dil, dil
0x1403184e2  mov     [rsp+398h+var_366], dil
0x1403184e7  mov     esi, 802h
0x1403184ec  xor     r12d, r12d
0x1403184ef  mov     r14, [rsp+398h+var_350]
0x1403184f4  mov     rbx, [rsp+398h+var_330]
0x1403184f9  xor     ecx, ecx; Irp
0x1403184fb  call    cs:__imp_IoSetTopLevelIrp
0x140318502  nop     dword ptr [rax+rax+00h]
0x140318507  cmp     [rbx], si
0x14031850a  jnz     loc_1403185DE
0x140318510  test    r14, r14
0x140318513  jz      loc_1403185D6
0x140318519  mov     rcx, [r14+68h]
0x14031851d  mov     rax, [rbx+60h]
0x140318521  cmp     [rcx+150h], rax
0x140318528  jnz     loc_1403185D6
0x14031852e  lea     rdx, [rcx+0F8h]
0x140318535  cmp     dword ptr [rdx+48h], 0
0x140318539  jz      loc_1403185D6
0x14031853f  mov     rcx, [rbx+60h]
0x140318543  test    rdx, rdx
0x140318546  jz      short loc_14031858B
0x140318548  call    MsReleaseFastResource
  ... truncated ...
```
