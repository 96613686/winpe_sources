# RefsPrePostIrpInternal(_IRP_CONTEXT *,_IRP *,uchar,uchar,uchar)

- ea: `0x14000c3c0`
- end: `0x14000c99d`
- name: `?RefsPrePostIrpInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@EEE@Z`
- size: `1501`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct _IRP *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, unsigned __int8)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a590`
- `0x14000acf0`
- `0x14000c180`
- `0x14010b460`
- `0x14010b4c0`
- `0x1402ab030`
- `0x1402ac460`
- `0x1402e7e98`

## callees

- `0x14000c3c0`
- `0x14000c9b0`
- `0x14000cf40`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x1402e7094`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c605`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c644`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c605`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c644`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000c61d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000c65c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000c61d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000c65c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c53c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c82d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c53c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c82d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000c8df`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000c8df`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000c77b`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14000c77b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000c78a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000c78a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000c7ca`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000c7ca`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000c7d6`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000c7d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c907`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c907`

## pseudocode

```c
__int64 __fastcall RefsPrePostIrpInternal(
        PSECURITY_SUBJECT_CONTEXT *a1,
        struct _SECURITY_SUBJECT_CONTEXT *a2,
        char a3,
        char a4,
        unsigned __int8 a5)
{
  struct _IRP_CONTEXT *v9; // r14
  struct _IRP_CONTEXT *v10; // rax
  PSECURITY_SUBJECT_CONTEXT *v11; // rbp
  PSECURITY_SUBJECT_CONTEXT *j; // rcx
  int v13; // ecx
  unsigned __int64 v14; // rax
  _QWORD **v15; // rdi
  _QWORD *v16; // rcx
  bool v17; // zf
  int v18; // eax
  PSECURITY_SUBJECT_CONTEXT v19; // rcx
  unsigned int v20; // eax
  struct _NPAGED_LOOKASIDE_LIST *v21; // r9
  NTSTATUS v22; // edi
  struct _IRP_CONTEXT *v23; // rcx
  struct _IO_STACK_LOCATION *ProcessAuditId; // r9
  unsigned int v25; // r8d
  _QWORD *v27; // rax
  PIRP v28; // rax
  IRP *v29; // rcx
  PIRP TopLevelIrp; // rax
  IRP *MdlAddress; // rcx
  unsigned int v32; // r8d
  PSECURITY_SUBJECT_CONTEXT *v33; // r13
  struct _IRP_CONTEXT **v34; // r12
  struct _IRP_CONTEXT *i; // rax
  PSECURITY_SUBJECT_CONTEXT v36; // rcx
  struct _FAST_MUTEX *PrimaryToken; // rdi
  struct _IRP_CONTEXT *v38; // rcx
  struct _IRP_CONTEXT **v39; // rax
  unsigned int v40; // eax
  DWORD LowPart; // eax
  unsigned int v42; // r8d
  unsigned int Options; // r9d
  unsigned int v44; // r8d

  if ( a1[3] )
    RefsCleanupFailedTransaction((struct _IRP_CONTEXT *)a1, 1u);
  if ( !a4 && ((_DWORD)a1[1] & 0x100000) != 0 )
  {
    TopLevelIrp = IoGetTopLevelIrp();
    MdlAddress = (IRP *)TopLevelIrp->MdlAddress;
    *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
    *(_QWORD *)&TopLevelIrp->Flags = 0;
    IoSetTopLevelIrp(MdlAddress);
    a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
  }
  *((_DWORD *)a1 + 1) |= 0x400u;
  RefsReleaseAllResources((struct _IRP_CONTEXT *)a1);
  v9 = (struct _IRP_CONTEXT *)(a1 + 80);
  v10 = (struct _IRP_CONTEXT *)a1[80];
  if ( v10 != (struct _IRP_CONTEXT *)(a1 + 80) )
  {
    v11 = 0;
    while ( v10 != v9 )
    {
      if ( *((_WORD *)v10 - 4) == 2087 )
      {
        v11 = (PSECURITY_SUBJECT_CONTEXT *)((char *)v10 - 8);
        break;
      }
      v10 = *(struct _IRP_CONTEXT **)v10;
    }
    if ( v11 )
    {
      while ( 1 )
      {
        v33 = 0;
        v34 = (struct _IRP_CONTEXT **)(v11 + 1);
        if ( *(struct _IRP_CONTEXT **)v9 != v9 )
        {
          for ( i = *v34; ; i = *(struct _IRP_CONTEXT **)i )
          {
            v34 = (struct _IRP_CONTEXT **)(v11 + 1);
            if ( i == v9 )
              break;
            if ( *((_WORD *)i - 4) == 2087 )
            {
              v33 = (PSECURITY_SUBJECT_CONTEXT *)((char *)i - 8);
              break;
            }
          }
        }
        v36 = v11[6];
        if ( v36 )
        {
          if ( ((__int64)v36[4].ProcessAuditId & 0x2000) != 0 )
            _InterlockedAnd((volatile signed __int32 *)&v36[4].ProcessAuditId, 0xFFFFDFFF);
          PrimaryToken = (struct _FAST_MUTEX *)v11[6][1].PrimaryToken;
          KeEnterGuardedRegion();
          ExAcquireFastMutexUnsafe(PrimaryToken);
          _InterlockedIncrement((volatile signed __int32 *)&v11[6][5].ImpersonationLevel + 1);
          v11[6][8].ProcessAuditId = 0;
          ++*((_DWORD *)&v11[6][5].ImpersonationLevel + 1);
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)v11[6][1].PrimaryToken);
          KeLeaveGuardedRegion();
        }
        v38 = *v34;
        if ( *((struct _IRP_CONTEXT ***)*v34 + 1) != v34
          || (v39 = (struct _IRP_CONTEXT **)v11[2], *v39 != (struct _IRP_CONTEXT *)v34) )
        {
LABEL_74:
          __fastfail(3u);
        }
        *v39 = v38;
        *((_QWORD *)v38 + 1) = v39;
        if ( v11 != a1 + 91 )
        {
          v40 = *((_DWORD *)v11 - 2);
          if ( v40 >= RefsNumberProcessors )
            v40 %= RefsNumberProcessors;
          ExFreeToNPagedLookasideList(&RefsScbSnapshotLookasideList[(unsigned __int64)v40], v11 - 1);
        }
        if ( !v33 )
          break;
        v11 = v33;
      }
    }
  }
  for ( j = (PSECURITY_SUBJECT_CONTEXT *)a1[75]; j; j = (PSECURITY_SUBJECT_CONTEXT *)a1[75] )
  {
    a1[75] = *j;
    ExFreePoolWithTag(j, 0);
  }
  v13 = *((_DWORD *)a1 + 1);
  if ( (v13 & 0x400) != 0 || (v14 = (unsigned __int64)a1[1], (v14 & 0x10000) != 0) )
  {
    if ( (v13 & 0x40000) != 0 )
    {
      *((_DWORD *)a1 + 1) = v13 & 0xFFFBFBFF;
    }
    else
    {
      *((_DWORD *)a1 + 1) = v13 & 0xF779C0CD;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFFFFBFFuLL);
    }
    *((_DWORD *)a1 + 4) = 0;
  }
  else
  {
    if ( (v14 & 0x20000000000LL) != 0 )
    {
      *((_DWORD *)a1 + 59) &= ~1u;
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)(v14 & 0xFFFFFDFFFFFFFFFFuLL);
    }
    if ( a1[42] )
    {
      *((_DWORD *)a1 + 81) &= ~1u;
      a1[42] = 0;
    }
    v15 = (_QWORD **)(a1 + 72);
    while ( 1 )
    {
      v16 = *v15;
      if ( *v15 == v15 )
        break;
      if ( (_QWORD **)v16[1] != v15 )
        goto LABEL_74;
      v27 = (_QWORD *)*v16;
      if ( *(_QWORD **)(*v16 + 8LL) != v16 )
        goto LABEL_74;
      *v15 = v27;
      v27[1] = v15;
      ExFreePoolWithTag(v16 - 12, 0);
    }
    a1[44] = 0;
    a1[58] = 0;
    v17 = ((_BYTE)a1[1] & 0x20) == 0;
    *((_DWORD *)a1 + 148) = 0;
    if ( !v17 )
    {
      SeReleaseSubjectContext(a1[18]);
      ExFreePoolWithTag(a1[18], 0);
    }
    v18 = *((_DWORD *)a1 + 2);
    a1[18] = 0;
    if ( (*(_QWORD *)&v18 & 0x100000LL) != 0 )
    {
      v28 = IoGetTopLevelIrp();
      v29 = (IRP *)v28->MdlAddress;
      *(_DWORD *)(&v28->Size + 1) = 0;
      *(_QWORD *)&v28->Flags = 0;
      IoSetTopLevelIrp(v29);
      a1[1] = (PSECURITY_SUBJECT_CONTEXT)((unsigned __int64)a1[1] & 0xFFFFFFFFFFEFFFFFuLL);
    }
    v19 = a1[89];
    if ( v19 )
    {
      ExFreePoolWithTag(v19, 0);
      a1[89] = 0;
    }
    if ( ((_DWORD)a1[1] & 0x80000) != 0 )
    {
      v20 = *((_DWORD *)a1 - 2);
      if ( *((_WORD *)a1 + 1) == 1664 )
      {
        v21 = RefsIrpAndIoContextLookasideList;
        if ( v20 < RefsNumberProcessors )
          goto LABEL_28;
      }
      else
      {
        v21 = RefsIrpContextLookasideList;
        if ( v20 < RefsNumberProcessors )
        {
LABEL_28:
          ExFreeToNPagedLookasideList(&v21[(unsigned __int64)v20], a1 - 1);
          goto LABEL_29;
        }
      }
      v20 %= RefsNumberProcessors;
      goto LABEL_28;
    }
  }
LABEL_29:
  a1[9] = a2;
  v22 = 0;
  if ( a2 && LOWORD(a2->ClientToken) == 6 )
  {
    v23 = (struct _IRP_CONTEXT *)*((unsigned __int8 *)a1 + 40);
    ProcessAuditId = (struct _IO_STACK_LOCATION *)a2[5].ProcessAuditId;
    if ( (unsigned __int8)((_BYTE)v23 - 3) > 1u )
    {
      switch ( (_BYTE)v23 )
      {
        case 0xC:
          if ( *((_BYTE *)a1 + 41) == 1 )
          {
            v22 = RefsLockUserBuffer(v23, (struct _IRP *)a2, IoWriteAccess, ProcessAuditId->Parameters.Read.Length);
            if ( v22 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  13,
                  &WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                  (unsigned int)v22);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x1F1u);
              RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v32);
              __debugbreak();
            }
          }
          break;
        case 0xD:
          if ( !*((_BYTE *)a1 + 41) )
          {
            LowPart = ProcessAuditId->Parameters.Read.ByteOffset.LowPart;
            if ( LowPart == 590011 || LowPart == 589939 )
            {
              v22 = RefsLockUserBuffer(v23, (struct _IRP *)a2, IoWriteAccess, ProcessAuditId->Parameters.Read.Length);
              if ( v22 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    14,
                    &WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                    (unsigned int)v22);
                }
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x202u);
                RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v42);
                __debugbreak();
              }
            }
          }
          break;
        case 0x14:
          Options = ProcessAuditId->Parameters.Create.Options;
          if ( Options )
          {
            v22 = RefsLockUserBuffer(v23, (struct _IRP *)a2, IoWriteAccess, Options);
            if ( v22 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  15,
                  &WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                  (unsigned int)v22);
              }
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x211u);
              RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v44);
              __debugbreak();
            }
          }
          break;
      }
    }
    else
    {
      *((_BYTE *)a1 + 41) &= ~1u;
      if ( (*((_BYTE *)a1 + 41) & 2) == 0 )
      {
        if ( a5 )
        {
          v22 = RefsLockUserBuffer(
                  v23,
                  (struct _IRP *)a2,
                  (enum _LOCK_OPERATION)((_BYTE)v23 == 3),
                  ProcessAuditId->Parameters.Read.Length);
          if ( v22 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                12,
                &WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids,
                (unsigned int)v22);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(v22, (struct _IRP_CONTEXT *)a1, "workque.c", 0x1E0u);
            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v22, v25);
            __debugbreak();
          }
        }
      }
    }
    if ( a3 )
      *((_BYTE *)a2[5].ProcessAuditId + 3) |= 1u;
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x14000c3c0  mov     [rsp+arg_10], rbx
0x14000c3c5  push    rsi
0x14000c3c6  push    rdi
0x14000c3c7  push    r12
0x14000c3c9  push    r14
0x14000c3cb  push    r15
0x14000c3cd  sub     rsp, 20h
0x14000c3d1  cmp     qword ptr [rcx+18h], 0
0x14000c3d6  movzx   edi, r9b
0x14000c3da  movzx   r15d, r8b
0x14000c3de  mov     rsi, rdx
0x14000c3e1  mov     rbx, rcx
0x14000c3e4  jnz     loc_14000C898
0x14000c3ea  xor     r12d, r12d
0x14000c3ed  test    dil, dil
0x14000c3f0  jz      loc_14000C636
0x14000c3f6  or      dword ptr [rbx+4], 400h
0x14000c3fd  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14000c400  mov     [rsp+48h+arg_0], rbp
0x14000c405  mov     [rsp+48h+arg_8], r13
0x14000c40a  call    ?RefsReleaseAllResources@@YAXPEAU_IRP_CONTEXT@@@Z; RefsReleaseAllResources(_IRP_CONTEXT *)
0x14000c40f  lea     r14, [rbx+280h]
0x14000c416  mov     rax, [r14]
0x14000c419  cmp     rax, r14
0x14000c41c  jz      short loc_14000C444
0x14000c41e  mov     rbp, r12
0x14000c421  mov     r8d, 827h
0x14000c427  cmp     rax, r14
0x14000c42a  jz      short loc_14000C43B
0x14000c42c  cmp     [rax-8], r8w
0x14000c431  jnz     loc_14000C861
0x14000c437  lea     rbp, [rax-8]
0x14000c43b  test    rbp, rbp
0x14000c43e  jnz     loc_14000C730
0x14000c444  mov     rcx, [rbx+258h]; P
0x14000c44b  test    rcx, rcx
0x14000c44e  jnz     loc_14000C8AF
0x14000c454  mov     ecx, [rbx+4]
0x14000c457  bt      ecx, 0Ah
0x14000c45b  jb      loc_14000C675
0x14000c461  mov     rax, [rbx+8]
0x14000c465  bt      rax, 10h
0x14000c46a  jb      loc_14000C675
0x14000c470  bt      rax, 29h ; ')'
0x14000c475  jnb     short loc_14000C48F
0x14000c477  and     dword ptr [rbx+0ECh], 0FFFFFFFEh
0x14000c47e  mov     rcx, 0FFFFFDFFFFFFFFFFh
0x14000c488  and     rax, rcx
0x14000c48b  mov     [rbx+8], rax
0x14000c48f  cmp     qword ptr [rbx+150h], 0
0x14000c497  jz      short loc_14000C4A7
0x14000c499  and     dword ptr [rbx+144h], 0FFFFFFFEh
0x14000c4a0  mov     [rbx+150h], r12
0x14000c4a7  lea     rdi, [rbx+240h]
0x14000c4ae  mov     rcx, [rdi]
0x14000c4b1  cmp     rcx, rdi
0x14000c4b4  jnz     loc_14000C5D0
0x14000c4ba  mov     [rbx+160h], r12
0x14000c4c1  mov     [rbx+1D0h], r12
0x14000c4c8  test    byte ptr [rbx+8], 20h
0x14000c4cc  mov     [rbx+250h], r12d
0x14000c4d3  jnz     loc_14000C8D8
0x14000c4d9  mov     eax, [rbx+8]
0x14000c4dc  mov     [rbx+90h], r12
0x14000c4e3  bt      rax, 14h
0x14000c4e8  jb      loc_14000C605
0x14000c4ee  mov     rcx, [rbx+2C8h]; P
0x14000c4f5  test    rcx, rcx
0x14000c4f8  jnz     loc_14000C905
0x14000c4fe  mov     eax, [rbx+8]
0x14000c501  bt      rax, 13h
0x14000c506  jnb     short loc_14000C548
0x14000c508  mov     eax, [rbx-8]
0x14000c50b  mov     ecx, 680h
0x14000c510  cmp     [rbx+2], cx
0x14000c514  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14000c51a  jz      loc_14000C699
0x14000c520  mov     r9, cs:?RefsIrpContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpContextLookasideList
0x14000c527  cmp     eax, ecx
0x14000c529  jnb     loc_14000C6A8
0x14000c52f  mov     ecx, eax
0x14000c531  lea     rdx, [rbx-8]; Entry
0x14000c535  shl     rcx, 7
0x14000c539  add     rcx, r9; Lookaside
0x14000c53c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000c543  nop     dword ptr [rax+rax+00h]
0x14000c548  mov     [rbx+48h], rsi
0x14000c54c  mov     edi, r12d
0x14000c54f  test    rsi, rsi
0x14000c552  jz      short loc_14000C5B1
0x14000c554  cmp     word ptr [rsi], 6
0x14000c558  jnz     short loc_14000C5B1
0x14000c55a  movzx   ecx, byte ptr [rbx+28h]; struct _IRP_CONTEXT *
0x14000c55e  mov     r9, [rsi+0B8h]
0x14000c565  lea     eax, [rcx-3]
0x14000c568  cmp     al, 1
0x14000c56a  ja      loc_14000C6B3
0x14000c570  and     byte ptr [rbx+29h], 0FEh
0x14000c574  test    byte ptr [rbx+29h], 2
0x14000c578  jnz     short loc_14000C5A1
0x14000c57a  cmp     [rsp+48h+arg_20], 0
0x14000c57f  jz      short loc_14000C5A1
0x14000c581  mov     r9d, [r9+8]; unsigned int
0x14000c585  cmp     cl, 3
0x14000c588  mov     r8d, r12d
0x14000c58b  mov     rdx, rsi; struct _IRP *
0x14000c58e  setz    r8b; enum _LOCK_OPERATION
0x14000c592  call    ?RefsLockUserBuffer@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@W4_LOCK_OPERATION@@K@Z; RefsLockUserBuffer(_IRP_CONTEXT *,_IRP *,_LOCK_OPERATION,ulong)
0x14000c597  mov     edi, eax
0x14000c599  test    eax, eax
0x14000c59b  js      loc_14000C951
0x14000c5a1  test    r15b, r15b
0x14000c5a4  jz      short loc_14000C5B1
0x14000c5a6  mov     rax, [rsi+0B8h]
0x14000c5ad  or      byte ptr [rax+3], 1
0x14000c5b1  mov     r13, [rsp+48h+arg_8]
0x14000c5b6  mov     eax, edi
0x14000c5b8  mov     rbp, [rsp+48h+arg_0]
0x14000c5bd  mov     rbx, [rsp+48h+arg_10]
0x14000c5c2  add     rsp, 20h
0x14000c5c6  pop     r15
0x14000c5c8  pop     r14
0x14000c5ca  pop     r12
0x14000c5cc  pop     rdi
0x14000c5cd  pop     rsi
0x14000c5ce  retn
0x14000c5d0  cmp     [rcx+8], rdi
0x14000c5d4  jnz     loc_14000C869
0x14000c5da  mov     rax, [rcx]
0x14000c5dd  cmp     [rax+8], rcx
0x14000c5e1  jnz     loc_14000C869
0x14000c5e7  mov     [rdi], rax
0x14000c5ea  add     rcx, 0FFFFFFFFFFFFFFA0h; P
0x14000c5ee  xor     edx, edx; Tag
0x14000c5f0  mov     [rax+8], rdi
0x14000c5f4  call    cs:__imp_ExFreePoolWithTag
0x14000c5fb  nop     dword ptr [rax+rax+00h]
0x14000c600  jmp     loc_14000C4AE
0x14000c605  call    cs:__imp_IoGetTopLevelIrp
0x14000c60c  nop     dword ptr [rax+rax+00h]
0x14000c611  mov     rcx, [rax+8]; Irp
0x14000c615  mov     [rax+4], r12d
0x14000c619  mov     [rax+10h], r12
0x14000c61d  call    cs:__imp_IoSetTopLevelIrp
0x14000c624  nop     dword ptr [rax+rax+00h]
0x14000c629  and     qword ptr [rbx+8], 0FFFFFFFFFFEFFFFFh
0x14000c631  jmp     loc_14000C4EE
0x14000c636  mov     eax, [rbx+8]
0x14000c639  bt      rax, 14h
0x14000c63e  jnb     loc_14000C3F6
0x14000c644  call    cs:__imp_IoGetTopLevelIrp
0x14000c64b  nop     dword ptr [rax+rax+00h]
0x14000c650  mov     rcx, [rax+8]; Irp
0x14000c654  mov     [rax+4], r12d
0x14000c658  mov     [rax+10h], r12
0x14000c65c  call    cs:__imp_IoSetTopLevelIrp
0x14000c663  nop     dword ptr [rax+rax+00h]
0x14000c668  and     qword ptr [rbx+8], 0FFFFFFFFFFEFFFFFh
0x14000c670  jmp     loc_14000C3F6
0x14000c675  bt      ecx, 12h
0x14000c679  jb      loc_14000C853
0x14000c67f  and     ecx, 0F779C0CDh
0x14000c685  mov     [rbx+4], ecx
0x14000c688  and     qword ptr [rbx+8], 0FFFFFFFFFFFFFBFFh
0x14000c690  mov     [rbx+10h], r12d
0x14000c694  jmp     loc_14000C548
0x14000c699  mov     r9, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsIrpAndIoContextLookasideList
0x14000c6a0  cmp     eax, ecx
0x14000c6a2  jb      loc_14000C52F
0x14000c6a8  xor     edx, edx
0x14000c6aa  div     ecx
0x14000c6ac  mov     eax, edx
0x14000c6ae  jmp     loc_14000C52F
0x14000c6b3  cmp     cl, 0Ch
0x14000c6b6  jnz     loc_14000C91F
0x14000c6bc  cmp     byte ptr [rbx+29h], 1
0x14000c6c0  jnz     loc_14000C5A1
0x14000c6c6  mov     r9d, [r9+8]; unsigned int
0x14000c6ca  mov     r8d, 1; enum _LOCK_OPERATION
0x14000c6d0  mov     rdx, rsi; struct _IRP *
0x14000c6d3  call    ?RefsLockUserBuffer@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@W4_LOCK_OPERATION@@K@Z; RefsLockUserBuffer(_IRP_CONTEXT *,_IRP *,_LOCK_OPERATION,ulong)
0x14000c6d8  mov     edi, eax
0x14000c6da  test    eax, eax
0x14000c6dc  jns     loc_14000C5A1
0x14000c6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6e9  lea     rax, WPP_GLOBAL_Control
0x14000c6f0  cmp     rcx, rax
0x14000c6f3  jz      loc_1401F803C
0x14000c6f9  test    dword ptr [rcx+2Ch], 100h
0x14000c700  jz      loc_1401F803C
0x14000c706  cmp     byte ptr [rcx+29h], 4
0x14000c70a  jb      loc_1401F803C
0x14000c710  mov     rcx, [rcx+18h]
0x14000c714  lea     r8, WPP_7b63daa3b97b323a6f61c0f7953a892c_Traceguids
0x14000c71b  mov     edx, 0Dh
0x14000c720  mov     r9d, edi
0x14000c723  call    WPP_SF_d
0x14000c728  nop
0x14000c729  jmp     loc_1401F803C
0x14000c730  mov     r13, r12
0x14000c733  lea     r12, [rbp+8]
0x14000c737  cmp     [r14], r14
0x14000c73a  jz      short loc_14000C75A
0x14000c73c  mov     rax, [r12]
0x14000c740  mov     rdx, r12
0x14000c743  mov     r12, rdx
0x14000c746  cmp     rax, r14
0x14000c749  jz      short loc_14000C75A
0x14000c74b  cmp     [rax-8], r8w
0x14000c750  jnz     loc_14000C890
0x14000c756  lea     r13, [rax-8]
0x14000c75a  mov     rcx, [rbp+30h]
0x14000c75e  test    rcx, rcx
0x14000c761  jz      short loc_14000C7E2
0x14000c763  test    dword ptr [rcx+98h], 2000h
0x14000c76d  jnz     loc_14000C870
0x14000c773  mov     rax, [rbp+30h]
0x14000c777  mov     rdi, [rax+30h]
0x14000c77b  call    cs:__imp_KeEnterGuardedRegion
0x14000c782  nop     dword ptr [rax+rax+00h]
0x14000c787  mov     rcx, rdi; FastMutex
0x14000c78a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000c791  nop     dword ptr [rax+rax+00h]
0x14000c796  mov     rax, [rbp+30h]
0x14000c79a  lock inc dword ptr [rax+0ACh]
0x14000c7a1  mov     rax, [rbp+30h]
0x14000c7a5  mov     qword ptr [rax+118h], 0
0x14000c7b0  mov     rcx, [rbp+30h]
0x14000c7b4  mov     eax, [rcx+0ACh]
0x14000c7ba  inc     eax
0x14000c7bc  mov     [rcx+0ACh], eax
0x14000c7c2  mov     rcx, [rbp+30h]
0x14000c7c6  mov     rcx, [rcx+30h]; FastMutex
0x14000c7ca  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14000c7d1  nop     dword ptr [rax+rax+00h]
0x14000c7d6  call    cs:__imp_KeLeaveGuardedRegion
0x14000c7dd  nop     dword ptr [rax+rax+00h]
0x14000c7e2  mov     rcx, [r12]
0x14000c7e6  cmp     [rcx+8], r12
0x14000c7ea  jnz     short loc_14000C869
0x14000c7ec  mov     rax, [rbp+10h]
0x14000c7f0  cmp     [rax], r12
0x14000c7f3  jnz     short loc_14000C869
0x14000c7f5  mov     [rax], rcx
0x14000c7f8  mov     [rcx+8], rax
0x14000c7fc  lea     rax, [rbx+2D8h]
0x14000c803  cmp     rbp, rax
0x14000c806  jz      short loc_14000C839
0x14000c808  mov     eax, [rbp-8]
0x14000c80b  mov     ecx, cs:?RefsNumberProcessors@@3KA; ulong RefsNumberProcessors
0x14000c811  mov     r8, cs:?RefsScbSnapshotLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; _NPAGED_LOOKASIDE_LIST * RefsScbSnapshotLookasideList
0x14000c818  cmp     eax, ecx
0x14000c81a  jnb     loc_14000C8A4
0x14000c820  mov     ecx, eax
0x14000c822  lea     rdx, [rbp-8]; Entry
0x14000c826  shl     rcx, 7
0x14000c82a  add     rcx, r8; Lookaside
0x14000c82d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000c834  nop     dword ptr [rax+rax+00h]
0x14000c839  xor     r12d, r12d
0x14000c83c  test    r13, r13
0x14000c83f  jz      loc_14000C444
0x14000c845  mov     rbp, r13
0x14000c848  mov     r8d, 827h
0x14000c84e  jmp     loc_14000C730
0x14000c853  and     ecx, 0FFFBFBFFh
0x14000c859  mov     [rbx+4], ecx
0x14000c85c  jmp     loc_14000C690
0x14000c861  mov     rax, [rax]
0x14000c864  jmp     loc_14000C427
0x14000c869  mov     ecx, 3; struct _IRP_CONTEXT *
0x14000c86e  int     29h; Win8: RtlFailFast(ecx)
0x14000c870  mov     eax, [rcx+98h]
0x14000c876  bt      eax, 0Dh
0x14000c87a  jnb     loc_14000C773
0x14000c880  lock and dword ptr [rcx+98h], 0FFFFDFFFh
0x14000c88b  jmp     loc_14000C773
0x14000c890  mov     rax, [rax]
0x14000c893  jmp     loc_14000C743
0x14000c898  mov     dl, 1; unsigned __int8
0x14000c89a  call    ?RefsCleanupFailedTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCleanupFailedTransaction(_IRP_CONTEXT *,uchar)
0x14000c89f  jmp     loc_14000C3EA
0x14000c8a4  xor     edx, edx
0x14000c8a6  div     ecx
0x14000c8a8  mov     eax, edx
0x14000c8aa  jmp     loc_14000C820
0x14000c8af  mov     rax, [rcx]
0x14000c8b2  xor     edx, edx; Tag
0x14000c8b4  mov     [rbx+258h], rax
0x14000c8bb  call    cs:__imp_ExFreePoolWithTag
0x14000c8c2  nop     dword ptr [rax+rax+00h]
0x14000c8c7  mov     rcx, [rbx+258h]
0x14000c8ce  test    rcx, rcx
0x14000c8d1  jnz     short loc_14000C8AF
0x14000c8d3  jmp     loc_14000C454
0x14000c8d8  mov     rcx, [rbx+90h]; SubjectContext
0x14000c8df  call    cs:__imp_SeReleaseSubjectContext
0x14000c8e6  nop     dword ptr [rax+rax+00h]
0x14000c8eb  mov     rcx, [rbx+90h]; P
0x14000c8f2  xor     edx, edx; Tag
  ... truncated ...
```
