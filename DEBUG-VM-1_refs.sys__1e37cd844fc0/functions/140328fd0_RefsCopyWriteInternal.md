# RefsCopyWriteInternal

- ea: `0x140328fd0`
- end: `0x1403297d7`
- name: `RefsCopyWriteInternal`
- size: `2055`
- prototype: `__int64 __usercall@<rax>(struct _FILE_OBJECT *@<rcx>, PLARGE_INTEGER FileOffset@<rdx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `31`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402eda70`
- `0x1403419a0`

## callees

- `0x140009e40`
- `0x140009ecc`
- `0x140035df0`
- `0x140035f20`
- `0x140050b60`
- `0x140063b10`
- `0x140076ad0`
- `0x1400862c0`
- `0x140086690`
- `0x1400867d0`
- `0x140088990`
- `0x14008ad80`
- `0x140093740`
- `0x140093bc0`
- `0x140096ed0`
- `0x140097fe0`
- `0x1400a7030`
- `0x1400a96e8`
- `0x1400ab7ac`
- `0x1400b5ba0`
- `0x1400d0fd8`
- `0x1400ebe74`
- `0x14010964c`
- `0x1401f3fc0`
- `0x14028e0ec`
- `0x140302dc0`
- `0x140304230`
- `0x1403188bc`
- `0x140328fd0`
- `0x14032c6d0`
- `0x14033ae88`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14032903d`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14032903d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14032932a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140329612`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14032932a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140329612`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14032913a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14032913a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140329723`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140329723`
- `ntoskrnl!CcCopyWrite` at `0x1403293f1`
- `ntoskrnl!CcCopyWrite` at `0x1403293f1`
- `ntoskrnl!CcMdlWriteAbort` at `0x1403294f4`
- `ntoskrnl!CcMdlWriteAbort` at `0x1403294f4`
- `ntoskrnl!CcCanIWrite` at `0x140329085`
- `ntoskrnl!CcCanIWrite` at `0x140329085`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14032966d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14032966d`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1403290a3`
- `ntoskrnl!CcCopyWriteWontFlush` at `0x1403290a3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14032967c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14032967c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343fae`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343fae`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14032941e`
- `ntoskrnl!CcPrepareMdlWrite` at `0x14032941e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403296e7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403296e7`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403296f3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403296f3`

## string_xrefs

- `0x1403294cf`: `write.c`
- `0x1403297aa`: `write.c`

## pseudocode

```c
char __fastcall RefsCopyWriteInternal(
        struct _FILE_OBJECT *a1,
        PLARGE_INTEGER FileOffset,
        BOOLEAN a3,
        unsigned int a4,
        void *a5,
        PMDL *a6,
        struct _IO_STATUS_BLOCK *a7)
{
  char *FsContext; // rdi
  bool v12; // si
  __int64 v13; // rcx
  char v14; // r14
  __int64 v15; // rcx
  _FCB **v16; // rdx
  int v17; // eax
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  DWORD LowPart; // r8d
  struct _CCB *v21; // rbx
  unsigned __int8 v22; // r9
  struct _FAST_MUTEX *v23; // rbx
  int v24; // [rsp+30h] [rbp-3D8h] BYREF
  __int16 v25; // [rsp+34h] [rbp-3D4h]
  unsigned int v26; // [rsp+38h] [rbp-3D0h]
  unsigned int v27; // [rsp+3Ch] [rbp-3CCh]
  PIO_STATUS_BLOCK IoStatus; // [rsp+40h] [rbp-3C8h]
  struct _CCB *FsContext2; // [rsp+48h] [rbp-3C0h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-3B8h]
  PVOID Buffer; // [rsp+58h] [rbp-3B0h]
  PMDL *MdlChain; // [rsp+60h] [rbp-3A8h]
  PMDL *v33; // [rsp+68h] [rbp-3A0h]
  struct _CCB *v34; // [rsp+70h] [rbp-398h]
  char *v35; // [rsp+78h] [rbp-390h]
  PLARGE_INTEGER v36; // [rsp+80h] [rbp-388h]
  struct _FCB **v37; // [rsp+90h] [rbp-378h]
  _BYTE v38[4]; // [rsp+A0h] [rbp-368h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-328h]

  v27 = a4;
  IoStatus = a7;
  FileObject = a1;
  v36 = FileOffset;
  Buffer = a5;
  MdlChain = a6;
  v33 = a6;
  if ( IoGetTopLevelIrp() )
    return 0;
  FsContext = (char *)a1->FsContext;
  FsContext2 = (struct _CCB *)a1->FsContext2;
  v24 = 0;
  if ( (a1->Flags & 0x10) != 0
    || !CcCanIWrite(a1, FileOffset[2].LowPart, a3, 0)
    || !CcCopyWriteWontFlush(a1, 0, FileOffset[2].LowPart)
    || *(_DWORD *)(*((_QWORD *)FsContext + 18) + 556LL)
    || !*((_QWORD *)FsContext + 2)
    || (*((_DWORD *)FsContext + 38) & 0x10) != 0
    && (*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x40000100LL) == 0x40000000
    || a1->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)FsContext + 31) + 8LL) )
  {
    return 0;
  }
  a7->Status = 0;
  if ( a5 )
    a7->Information = FileOffset[2].LowPart;
  if ( FileOffset[2].LowPart )
  {
    v35 = FsContext;
    KeEnterCriticalRegion();
    RefsInitializeLocalIrpContext(0, (struct _LARGE_IRP_CONTEXT *)v38);
    v39 = *((_QWORD *)FsContext + 18);
    if ( a1->PrivateCacheMap == (PVOID)1 )
    {
      if ( (unsigned __int8)RefsAcquirePagingResourceExclusive(v13, FsContext, a3) )
      {
        v14 = 0x80;
        if ( !RefsSetupCacheMapDuringFastIo((struct _IRP_CONTEXT *)v38, a1, (struct DataSCB *)FsContext) )
        {
          v12 = 0;
          goto LABEL_61;
        }
        if ( (*((_DWORD *)FsContext + 38) & 0x10) == 0 || !_FCB::HasPurgeableEAs(*((_FCB **)FsContext + 17)) )
          RefsConvertPagingResourceExclusiveToShared(v38, FsContext);
LABEL_31:
        v14 |= 0x80u;
        LOBYTE(v24) = v14;
        if ( a1->PrivateCacheMap )
        {
          if ( FsContext[5] )
          {
            v37 = (struct _FCB **)(FsContext + 136);
            if ( RefsIsFileOpen(*((const struct _FCB **)FsContext + 17)) )
            {
              v17 = *((_DWORD *)FsContext + 38);
              if ( (v17 & 0x80u) == 0 && ((v17 & 0x10) == 0 || !_FCB::HasPurgeableEAs(*v16)) )
              {
                if ( (int)RefsSetWriteRangeFromEof(v38, FsContext, FileOffset, &v24) < 0
                  || (v34 = FsContext2, FsContext[5] == 2)
                  && !RefsFastIoCheckIfPossibleInternal(
                        a1,
                        (struct _SCB *)FsContext,
                        FileOffset->QuadPart,
                        FileOffset[2].LowPart,
                        v27,
                        0) )
                {
                  v14 = v24;
                }
                else
                {
                  LOBYTE(v25) = 0;
                  IoSetTopLevelIrp((PIRP)4);
                  v14 = v24;
                  v18 = (v24 & 1) != 0;
                  v26 = v18;
                  if ( (v24 & 2) != 0 )
                  {
                    v18 |= 2u;
                    v26 = v18;
                  }
                  RefsPostUsnChange((struct _IRP_CONTEXT *)v38, (struct _FCB *)FsContext, v18, 0);
                  if ( (v14 & 2) != 0 )
                  {
                    RefsInitiateFileExtensionForWrite((struct _IRP_CONTEXT *)v38, (__int64)&v24);
                    v14 = v24;
                  }
                  if ( *((__int16 *)FsContext + 128) < 0
                    && !RefsReserveClusters(
                          (struct _IRP_CONTEXT *)v38,
                          (struct _SCB *)FsContext,
                          FileOffset->QuadPart,
                          FileOffset[2].LowPart) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        57,
                        &WPP_333749fe71273bc3659f43e52285135c_Traceguids,
                        3221225599LL);
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                      RefsStatusDebug(-1073741697, (struct _IRP_CONTEXT *)v38, "write.c", 0xDA1u);
                    RefsRaiseStatusInternal((struct _IRP_CONTEXT *)v38, -1073741697, v19);
                    __debugbreak();
                    JUMPOUT(0x1403297D7LL);
                  }
                  LowPart = FileOffset[2].LowPart;
                  if ( Buffer )
                  {
                    v12 = CcCopyWrite(a1, FileOffset, LowPart, a3, Buffer) != 0;
                    HIBYTE(v25) = v12;
                  }
                  else
                  {
                    CcPrepareMdlWrite(a1, FileOffset, LowPart, MdlChain, IoStatus);
                    v12 = 1;
                    v25 = 257;
                  }
                  if ( v12 )
                  {
                    RefsPostWriteProcessing((struct _IRP_CONTEXT *)v38, a1, (__int64)FileOffset, (__int64)&v24);
                    v14 = v24;
                  }
                  v21 = FsContext2;
                  IoSetTopLevelIrp(0);
                  if ( v12 )
                  {
                    RefsUpdateFileTimestampsForModification(a1, *v37, v21, v22);
                    a1->CurrentByteOffset = FileOffset[1];
LABEL_61:
                    if ( v14 < 0 )
                      RefsReleasePagingResource(v38, FsContext);
                    goto LABEL_63;
                  }
                }
              }
            }
          }
        }
        v12 = 0;
        if ( (v14 & 4) != 0 || (v24 & 0x400) != 0 )
        {
          v23 = (struct _FAST_MUTEX *)*((_QWORD *)FsContext + 6);
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(v23);
          _InterlockedIncrement((volatile signed __int32 *)FsContext + 43);
          if ( (v14 & 4) != 0 )
          {
            RefsCompleteFileSizeExtension((struct _IRP_CONTEXT *)v38, (struct DataSCB *)FsContext, (__int64)&v24);
            v14 = v24 & 0xFB;
          }
          if ( (v24 & 0x400) != 0 )
            RefsFinishIoAtEof((struct _IRP_CONTEXT *)v38, (struct _SCB *)FsContext);
          ++*((_DWORD *)FsContext + 43);
          ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)FsContext + 6));
          KeLeaveGuardedRegion();
        }
        goto LABEL_61;
      }
LABEL_25:
      v12 = 0;
LABEL_63:
      RefsCleanupIrpContext((struct _IRP_CONTEXT *)v38, 0);
      KeLeaveCriticalRegion();
      return v12;
    }
    if ( (*((_DWORD *)FsContext + 38) & 0x10) != 0
      && (*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x40000100LL) == 0x40000000 )
    {
      if ( !(unsigned __int8)RefsAcquirePagingResourceExclusive(0x40000000, FsContext, a3) )
        goto LABEL_25;
    }
    else
    {
      if ( !(unsigned __int8)RefsAcquirePagingResourceShared(v38, FsContext, a3) )
        goto LABEL_25;
      if ( (*((_DWORD *)FsContext + 38) & 0x10) != 0 && _FCB::HasPurgeableEAs(*((_FCB **)FsContext + 17)) )
      {
        RefsReleasePagingResource(v38, FsContext);
        if ( !(unsigned __int8)RefsAcquirePagingResourceExclusive(v15, FsContext, a3) )
          goto LABEL_25;
      }
    }
    v14 = v24;
    goto LABEL_31;
  }
  return 1;
}

```

## disassembly

```asm
0x140328fd0  push    rbx
0x140328fd2  push    rsi
0x140328fd3  push    rdi
0x140328fd4  push    r12
0x140328fd6  push    r13
0x140328fd8  push    r14
0x140328fda  push    r15
0x140328fdc  sub     rsp, 3D0h
0x140328fe3  mov     rax, cs:__security_cookie
0x140328fea  xor     rax, rsp
0x140328fed  mov     [rsp+408h+var_48], rax
0x140328ff5  mov     [rsp+408h+var_3CC], r9d
0x140328ffa  movzx   esi, r8b
0x140328ffe  mov     r12, rdx
0x140329001  mov     r15, rcx
0x140329004  mov     rbx, [rsp+408h+arg_30]
0x14032900c  mov     [rsp+408h+IoStatus], rbx
0x140329011  mov     [rsp+408h+FileObject], rcx
0x140329016  mov     [rsp+408h+var_388], rdx
0x14032901e  mov     r14, [rsp+408h+arg_20]
0x140329026  mov     [rsp+408h+var_3B0], r14
0x14032902b  mov     rax, [rsp+408h+arg_28]
0x140329033  mov     [rsp+408h+MdlChain], rax
0x140329038  mov     [rsp+408h+var_3A0], rax
0x14032903d  call    cs:__imp_IoGetTopLevelIrp
0x140329044  nop     dword ptr [rax+rax+00h]
0x140329049  test    rax, rax
0x14032904c  jz      short loc_140329055
0x14032904e  xor     al, al
0x140329050  jmp     loc_140329738
0x140329055  mov     rdi, [r15+18h]
0x140329059  mov     rax, [r15+20h]
0x14032905d  mov     [rsp+408h+var_3C0], rax
0x140329062  xor     r13d, r13d
0x140329065  mov     dword ptr [rsp+408h+var_3D8], r13d
0x14032906a  mov     eax, [r15+50h]
0x14032906e  test    al, 10h
0x140329070  jnz     loc_140329731
0x140329076  xor     r9d, r9d; Retrying
0x140329079  movzx   r8d, sil; Wait
0x14032907d  mov     edx, [r12+10h]; BytesToWrite
0x140329082  mov     rcx, r15; FileObject
0x140329085  call    cs:__imp_CcCanIWrite
0x14032908c  nop     dword ptr [rax+rax+00h]
0x140329091  test    al, al
0x140329093  jz      loc_140329731
0x140329099  mov     r8d, [r12+10h]; Length
0x14032909e  xor     edx, edx; FileOffset
0x1403290a0  mov     rcx, r15; FileObject
0x1403290a3  call    cs:__imp_CcCopyWriteWontFlush
0x1403290aa  nop     dword ptr [rax+rax+00h]
0x1403290af  test    al, al
0x1403290b1  jz      loc_140329731
0x1403290b7  mov     rax, [rdi+90h]
0x1403290be  cmp     [rax+22Ch], r13d
0x1403290c5  jnz     loc_140329731
0x1403290cb  cmp     [rdi+10h], r13
0x1403290cf  jz      loc_140329731
0x1403290d5  mov     eax, [rdi+98h]
0x1403290db  test    al, 10h
0x1403290dd  jz      short loc_1403290FD
0x1403290df  mov     rax, [rdi+88h]
0x1403290e6  mov     rcx, [rax+8]
0x1403290ea  and     ecx, 40000100h
0x1403290f0  cmp     rcx, 40000000h
0x1403290f7  jz      loc_140329731
0x1403290fd  mov     rax, [rdi+0F8h]
0x140329104  add     rax, 8
0x140329108  cmp     [r15+28h], rax
0x14032910c  jnz     loc_140329731
0x140329112  mov     [rbx], r13d
0x140329115  test    r14, r14
0x140329118  jz      short loc_140329123
0x14032911a  mov     eax, [r12+10h]
0x14032911f  mov     [rbx+8], rax
0x140329123  cmp     [r12+10h], r13d
0x140329128  jnz     short loc_140329132
0x14032912a  mov     sil, 1
0x14032912d  jmp     loc_140329734
0x140329132  mov     r13, rdi
0x140329135  mov     [rsp+408h+var_390], rdi
0x14032913a  call    cs:__imp_KeEnterCriticalRegion
0x140329141  nop     dword ptr [rax+rax+00h]
0x140329146  lea     rdx, [rsp+408h+var_368]; struct _LARGE_IRP_CONTEXT *
0x14032914e  xor     ecx, ecx; struct _IRP *
0x140329150  call    ?RefsInitializeLocalIrpContext@@YAJPEAU_IRP@@PEAU_LARGE_IRP_CONTEXT@@@Z; RefsInitializeLocalIrpContext(_IRP *,_LARGE_IRP_CONTEXT *)
0x140329155  mov     rax, [rdi+90h]
0x14032915c  mov     [rsp+408h+var_328], rax
0x140329164  cmp     qword ptr [r15+30h], 1
0x140329169  jnz     short loc_1403291D4
0x14032916b  movzx   r8d, sil
0x14032916f  mov     rdx, rdi
0x140329172  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140329177  test    al, al
0x140329179  jz      loc_140329208
0x14032917f  mov     r14b, 80h
0x140329182  mov     r8, rdi; struct DataSCB *
0x140329185  mov     rdx, r15; struct _FILE_OBJECT *
0x140329188  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x140329190  call    ?RefsSetupCacheMapDuringFastIo@@YAEPEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@AEAUDataSCB@@@Z; RefsSetupCacheMapDuringFastIo(_IRP_CONTEXT *,_FILE_OBJECT *,DataSCB &)
0x140329195  test    al, al
0x140329197  jnz     short loc_1403291A1
0x140329199  xor     sil, sil
0x14032919c  jmp     loc_1403296FF
0x1403291a1  mov     eax, [rdi+98h]
0x1403291a7  test    al, 10h
0x1403291a9  jz      short loc_1403291BF
0x1403291ab  mov     rcx, [rdi+88h]; this
0x1403291b2  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x1403291b7  test    al, al
0x1403291b9  jnz     loc_140329268
0x1403291bf  mov     rdx, rdi
0x1403291c2  lea     rcx, [rsp+408h+var_368]
0x1403291ca  call    ?RefsConvertPagingResourceExclusiveToShared@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsConvertPagingResourceExclusiveToShared(_IRP_CONTEXT *,PFCBOrSCB)
0x1403291cf  jmp     loc_140329268
0x1403291d4  mov     eax, [rdi+98h]
0x1403291da  test    al, 10h
0x1403291dc  jz      short loc_140329210
0x1403291de  mov     rax, [rdi+88h]
0x1403291e5  mov     rcx, [rax+8]
0x1403291e9  and     ecx, 40000100h
0x1403291ef  cmp     rcx, 40000000h
0x1403291f6  jnz     short loc_140329210
0x1403291f8  movzx   r8d, sil
0x1403291fc  mov     rdx, rdi
0x1403291ff  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140329204  test    al, al
0x140329206  jnz     short loc_140329262
0x140329208  xor     sil, sil
0x14032920b  jmp     loc_140329714
0x140329210  movzx   r8d, sil
0x140329214  mov     rdx, rdi
0x140329217  lea     rcx, [rsp+408h+var_368]
0x14032921f  call    ?RefsAcquirePagingResourceShared@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceShared(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x140329224  test    al, al
0x140329226  jz      short loc_140329208
0x140329228  mov     eax, [rdi+98h]
0x14032922e  test    al, 10h
0x140329230  jz      short loc_140329262
0x140329232  mov     rcx, [rdi+88h]; this
0x140329239  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x14032923e  test    al, al
0x140329240  jz      short loc_140329262
0x140329242  mov     rdx, rdi
0x140329245  lea     rcx, [rsp+408h+var_368]
0x14032924d  call    ?RefsReleasePagingResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleasePagingResource(_IRP_CONTEXT *,PFCBOrSCB)
0x140329252  movzx   r8d, sil
0x140329256  mov     rdx, rdi
0x140329259  call    ?RefsAcquirePagingResourceExclusive@@YAEPEAU_IRP_CONTEXT@@UPFCBOrSCB@@E@Z; RefsAcquirePagingResourceExclusive(_IRP_CONTEXT *,PFCBOrSCB,uchar)
0x14032925e  test    al, al
0x140329260  jz      short loc_140329208
0x140329262  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x140329268  or      r14b, 80h
0x14032926c  mov     byte ptr [rsp+408h+var_3D8], r14b
0x140329271  cmp     qword ptr [r15+30h], 0
0x140329276  jz      loc_14032964D
0x14032927c  cmp     byte ptr [rdi+5], 0
0x140329280  jz      loc_14032964D
0x140329286  lea     rdx, [rdi+88h]
0x14032928d  mov     [rsp+408h+var_378], rdx
0x140329295  mov     rcx, [rdx]; struct _FCB *
0x140329298  call    ?RefsIsFileOpen@@YAEPEBU_FCB@@@Z; RefsIsFileOpen(_FCB const *)
0x14032929d  test    al, al
0x14032929f  jz      loc_14032964D
0x1403292a5  mov     eax, [rdi+98h]
0x1403292ab  test    al, al
0x1403292ad  js      loc_14032964D
0x1403292b3  test    al, 10h
0x1403292b5  jz      short loc_1403292C7
0x1403292b7  mov     rcx, [rdx]; this
0x1403292ba  call    ?HasPurgeableEAs@_FCB@@QEAA_NXZ; _FCB::HasPurgeableEAs(void)
0x1403292bf  test    al, al
0x1403292c1  jnz     loc_14032964D
0x1403292c7  lea     r9, [rsp+408h+var_3D8]
0x1403292cc  mov     r8, r12
0x1403292cf  mov     rdx, rdi
0x1403292d2  lea     rcx, [rsp+408h+var_368]
0x1403292da  call    RefsSetWriteRangeFromEof
0x1403292df  test    eax, eax
0x1403292e1  js      loc_140329647
0x1403292e7  mov     rax, [rsp+408h+var_3C0]
0x1403292ec  mov     [rsp+408h+var_398], rax
0x1403292f1  cmp     byte ptr [rdi+5], 2
0x1403292f5  jnz     short loc_140329320
0x1403292f7  mov     [rsp+408h+var_3E0], 0; unsigned __int8
0x1403292fc  mov     eax, [rsp+408h+var_3CC]
0x140329300  mov     dword ptr [rsp+408h+Buffer], eax; unsigned int
0x140329304  mov     r9d, [r12+10h]; unsigned int
0x140329309  mov     r8, [r12]; __int64
0x14032930d  mov     rdx, rdi; struct _SCB *
0x140329310  mov     rcx, r15; FileObject
0x140329313  call    ?RefsFastIoCheckIfPossibleInternal@@YAEPEAU_FILE_OBJECT@@AEAU_SCB@@_JKKE@Z; RefsFastIoCheckIfPossibleInternal(_FILE_OBJECT *,_SCB &,__int64,ulong,ulong,uchar)
0x140329318  test    al, al
0x14032931a  jz      loc_140329647
0x140329320  mov     byte ptr [rsp+408h+var_3D8+4], 0
0x140329325  mov     ecx, 4; Irp
0x14032932a  call    cs:__imp_IoSetTopLevelIrp
0x140329331  nop     dword ptr [rax+rax+00h]
0x140329336  nop
0x140329337  xor     r8d, r8d
0x14032933a  mov     [rsp+408h+var_3D0], r8d
0x14032933f  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x140329345  test    r14b, 1
0x140329349  mov     eax, 1
0x14032934e  cmovnz  r8d, eax
0x140329352  mov     [rsp+408h+var_3D0], r8d
0x140329357  movzx   ebx, r14b
0x14032935b  shr     bl, 1
0x14032935d  and     bl, al
0x14032935f  jz      short loc_14032936A
0x140329361  or      r8d, 2; unsigned int
0x140329365  mov     [rsp+408h+var_3D0], r8d
0x14032936a  xor     r9d, r9d; struct _FILE_NAME *
0x14032936d  mov     rdx, rdi; struct _FCB *
0x140329370  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x140329378  call    ?RefsPostUsnChange@@YAXPEAU_IRP_CONTEXT@@PEAXKPEBU_FILE_NAME@@@Z; RefsPostUsnChange(_IRP_CONTEXT *,void *,ulong,_FILE_NAME const *)
0x14032937d  test    bl, bl
0x14032937f  jz      short loc_1403293A8
0x140329381  lea     rax, [rsp+408h+var_3D8]
0x140329386  mov     [rsp+408h+Buffer], rax; __int64
0x14032938b  mov     r9, r12
0x14032938e  mov     r8, [r15+20h]
0x140329392  mov     rdx, rdi
0x140329395  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x14032939d  call    RefsInitiateFileExtensionForWrite
0x1403293a2  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x1403293a8  cmp     word ptr [rdi+100h], 0
0x1403293b0  jge     short loc_1403293D3
0x1403293b2  mov     r9d, [r12+10h]; unsigned int
0x1403293b7  mov     r8, [r12]; __int64
0x1403293bb  mov     rdx, rdi; struct _SCB *
0x1403293be  lea     rcx, [rsp+408h+var_368]; struct _IRP_CONTEXT *
0x1403293c6  call    ?RefsReserveClusters@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@_JK@Z; RefsReserveClusters(_IRP_CONTEXT *,_SCB *,__int64,ulong)
0x1403293cb  test    al, al
0x1403293cd  jz      loc_14032975C
0x1403293d3  mov     r8d, [r12+10h]; Length
0x1403293d8  mov     rax, [rsp+408h+var_3B0]
0x1403293dd  mov     rdx, r12; FileOffset
0x1403293e0  mov     rcx, r15; FileObject
0x1403293e3  test    rax, rax
0x1403293e6  jz      short loc_14032940F
0x1403293e8  mov     [rsp+408h+Buffer], rax; Buffer
0x1403293ed  movzx   r9d, sil; Wait
0x1403293f1  call    cs:__imp_CcCopyWrite
0x1403293f8  nop     dword ptr [rax+rax+00h]
0x1403293fd  test    al, al
0x1403293ff  setnz   sil
0x140329403  mov     byte ptr [rsp+408h+var_3D8+5], sil
0x140329408  mov     rbx, [rsp+408h+IoStatus]
0x14032940d  jmp     short loc_140329437
0x14032940f  mov     rbx, [rsp+408h+IoStatus]
0x140329414  mov     [rsp+408h+Buffer], rbx; IoStatus
0x140329419  mov     r9, [rsp+408h+MdlChain]; MdlChain
0x14032941e  call    cs:__imp_CcPrepareMdlWrite
0x140329425  nop     dword ptr [rax+rax+00h]
0x14032942a  mov     sil, 1
0x14032942d  mov     byte ptr [rsp+408h+var_3D8+5], sil
0x140329432  mov     byte ptr [rsp+408h+var_3D8+4], sil
0x140329437  test    sil, sil
0x14032943a  jz      short loc_140329467
0x14032943c  lea     rax, [rsp+408h+var_3D8]
0x140329441  mov     qword ptr [rsp+408h+var_3E0], rax
0x140329446  mov     [rsp+408h+Buffer], r12
0x14032944b  mov     r9, rdi
0x14032944e  mov     r8, rbx
0x140329451  mov     rdx, r15
0x140329454  lea     rcx, [rsp+408h+var_368]
0x14032945c  call    RefsPostWriteProcessing
0x140329461  movzx   r14d, byte ptr [rsp+408h+var_3D8]
0x140329467  mov     rbx, [rsp+408h+var_3C0]
0x14032946c  jmp     loc_140329610
0x140329471  mov     ebx, eax
0x140329473  lea     rax, WPP_GLOBAL_Control
0x14032947a  mov     r10, cs:WPP_GLOBAL_Control
0x140329481  cmp     r10, rax
0x140329484  jz      short loc_1403294BC
0x140329486  test    dword ptr [r10+2Ch], 100h
0x14032948e  jz      short loc_1403294BC
0x140329490  test    ebx, ebx
0x140329492  js      short loc_14032949D
0x140329494  cmp     byte ptr [r10+29h], 5
0x140329499  jnb     short loc_1403294A4
0x14032949b  jmp     short loc_1403294BC
0x14032949d  cmp     byte ptr [r10+29h], 4
0x1403294a2  jb      short loc_1403294BC
0x1403294a4  mov     r9d, ebx
0x1403294a7  mov     edx, 3Ah ; ':'
0x1403294ac  lea     r8, WPP_333749fe71273bc3659f43e52285135c_Traceguids
0x1403294b3  mov     rcx, [r10+18h]
0x1403294b7  call    WPP_SF_d
0x1403294bc  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1403294c3  test    al, al
0x1403294c5  jz      short loc_1403294DD
0x1403294c7  mov     ecx, ebx; Status
0x1403294c9  mov     r9d, 0DC2h; unsigned int
0x1403294cf  lea     r8, aWriteC; "write.c"
0x1403294d6  xor     edx, edx; struct _IRP_CONTEXT *
0x1403294d8  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1403294dd  mov     r15, [rsp+408h+FileObject]
0x1403294e2  cmp     byte ptr [rsp+408h+var_3D8+4], 0
  ... truncated ...
```
