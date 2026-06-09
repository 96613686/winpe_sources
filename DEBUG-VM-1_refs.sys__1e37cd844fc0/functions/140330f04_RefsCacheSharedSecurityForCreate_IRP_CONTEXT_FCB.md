# RefsCacheSharedSecurityForCreate(_IRP_CONTEXT *,_FCB *)

- ea: `0x140330f04`
- end: `0x14033136c`
- name: `?RefsCacheSharedSecurityForCreate@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_FCB@@@Z`
- size: `1128`
- prototype: `struct _SHARED_SECURITY *__fastcall(struct _IRP_CONTEXT *, struct _FCB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1402986f0`

## callees

- `0x140076ad0`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x14028c008`
- `0x14028e3f8`
- `0x1402d5910`
- `0x1402d5d14`
- `0x140330f04`
- `0x140339524`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x140330f8b`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1403310b6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1403310b6`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140331254`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140331296`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034457c`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140331254`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140331296`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14034457c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140331181`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140331181`
- `ntoskrnl!ExGetPreviousMode` at `0x140330fb4`
- `ntoskrnl!ExGetPreviousMode` at `0x140330fb4`
- `ntoskrnl!SeDeassignSecurity` at `0x140331349`
- `ntoskrnl!SeDeassignSecurity` at `0x14034464b`
- `ntoskrnl!SeDeassignSecurity` at `0x140331349`
- `ntoskrnl!SeDeassignSecurity` at `0x14034464b`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x140330f95`
- `ntoskrnl!SeComputeAutoInheritByObjectType` at `0x140330f95`
- `ntoskrnl!SeAssignSecurityEx` at `0x140331101`
- `ntoskrnl!SeAssignSecurityEx` at `0x140331101`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140331263`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403312a9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034458f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140331263`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403312a9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14034458f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403312de`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403445d8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403312de`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403445d8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403312ea`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403445e4`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403312ea`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403445e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403312c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140331315`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403445ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344619`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403312c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140331315`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403445ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140344619`

## pseudocode

```c
struct _SHARED_SECURITY *__fastcall RefsCacheSharedSecurityForCreate(struct _IRP_CONTEXT *a1, struct _FCB *a2)
{
  struct _SHARED_SECURITY *v4; // r14
  struct _SHARED_SECURITY_FOR_CREATE *v5; // rsi
  char v6; // r12
  char *v7; // rbx
  __int64 v8; // r15
  ULONG v9; // r8d
  __int64 v10; // rcx
  char PreviousMode; // al
  char v12; // al
  int v13; // edx
  unsigned __int64 v14; // rax
  __int64 v15; // r9
  ULONG v16; // r8d
  struct _LIST_ENTRY *Flink; // rax
  PVOID *FileContextSupportPointer; // rcx
  struct _SHARED_SECURITY_FOR_CREATE *Unsafe; // rax
  POOL_TYPE PoolType; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v22; // eax
  unsigned int v23; // r8d
  NTSTATUS v24; // ebx
  ULONG v25; // eax
  unsigned int v26; // r8d
  struct _FAST_MUTEX *v27; // rbx
  struct _FAST_MUTEX *v28; // rbx
  PSECURITY_DESCRIPTOR v30; // rdi
  __int64 v31; // rbx
  void *v32; // rcx
  int v33; // eax
  unsigned int v34; // eax
  char v36; // [rsp+52h] [rbp-66h]
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+58h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-58h] BYREF
  struct _SHARED_SECURITY_FOR_CREATE *v39; // [rsp+68h] [rbp-50h]
  __int64 v40; // [rsp+70h] [rbp-48h]
  BOOLEAN IsDirectoryObject; // [rsp+C8h] [rbp+10h]
  struct _SHARED_SECURITY *v42; // [rsp+D0h] [rbp+18h] BYREF
  ULONG AutoInheritFlags; // [rsp+D8h] [rbp+20h]

  NewDescriptor = 0;
  v4 = 0;
  v42 = 0;
  v5 = 0;
  v39 = 0;
  v6 = 0;
  SecurityDescriptor = 0;
  v36 = 1;
  v7 = *(char **)(*((_QWORD *)a1 + 9) + 184LL);
  IsDirectoryObject = v7[16] & 1;
  v8 = *(_QWORD *)(*((_QWORD *)v7 + 1) + 8LL);
  v40 = v8;
  if ( !a2->ScavengerFinalizationList.Flink )
    RefsLoadSecurityDescriptor(a1, a2);
  v9 = SeComputeAutoInheritByObjectType(
         IoFileObjectType,
         *(PSECURITY_DESCRIPTOR *)(v8 + 64),
         (char *)&a2->ScavengerFinalizationList.Flink[1].Flink + 4);
  AutoInheritFlags = v9;
  v10 = *((_QWORD *)a1 + 9);
  if ( !v10 )
  {
    PreviousMode = ExGetPreviousMode();
    v9 = AutoInheritFlags;
    goto LABEL_18;
  }
  v12 = *v7;
  if ( !*v7 )
  {
LABEL_6:
    if ( (v7[2] & 1) != 0 )
    {
      PreviousMode = 1;
      goto LABEL_18;
    }
LABEL_17:
    PreviousMode = *(_BYTE *)(v10 + 64);
    goto LABEL_18;
  }
  if ( v12 == 6 )
  {
    v13 = *((_DWORD *)v7 + 4);
    v14 = (unsigned int)(v13 - 10);
    if ( (unsigned int)v14 <= 0x3E )
    {
      v15 = 0x4080000000000003LL;
      if ( _bittest64(&v15, v14) )
      {
        PreviousMode = (v7[2] & 1) == 0;
        goto LABEL_18;
      }
    }
    if ( v13 != 71 )
      goto LABEL_17;
    goto LABEL_6;
  }
  if ( v12 != 5 )
    goto LABEL_17;
  if ( *((_DWORD *)v7 + 4) != 71 )
    goto LABEL_17;
  PreviousMode = 1;
  if ( (v7[2] & 1) == 0 )
    goto LABEL_17;
LABEL_18:
  v16 = (PreviousMode != 0 ? 24576 : 16408) | v9;
  AutoInheritFlags = v16;
  if ( !*(_QWORD *)(v8 + 64) )
  {
    Flink = a2->ScavengerFinalizationList.Flink;
    if ( HIDWORD(Flink->Blink) )
    {
      FileContextSupportPointer = a2->Header.FileContextSupportPointer;
      if ( FileContextSupportPointer[22] )
      {
        Unsafe = GetSharedSecurityForCreateUnsafe(
                   (struct _VCB *)FileContextSupportPointer,
                   (struct _SECURITY_HASH_KEY *)&Flink->Blink,
                   v16,
                   (struct _SECURITY_SUBJECT_CONTEXT *)(v8 + 32),
                   IsDirectoryObject);
        v5 = Unsafe;
        v39 = Unsafe;
        if ( Unsafe )
        {
          if ( *((_DWORD *)Unsafe + 3) )
          {
            v4 = (struct _SHARED_SECURITY *)RefsCacheSharedSecurityBySecurityId(
                                              a1,
                                              a2->Header.FileContextSupportPointer,
                                              *((_QWORD *)Unsafe + 1),
                                              &v42);
            v42 = v4;
          }
        }
      }
    }
  }
  if ( !v4 )
  {
    PoolType = ::PoolType;
    GenericMapping = IoGetFileObjectGenericMapping();
    v22 = SeAssignSecurityEx(
            (char *)&a2->ScavengerFinalizationList.Flink[1].Flink + 4,
            *(PSECURITY_DESCRIPTOR *)(v8 + 64),
            &NewDescriptor,
            0,
            IsDirectoryObject,
            AutoInheritFlags,
            (PSECURITY_SUBJECT_CONTEXT)(v8 + 32),
            GenericMapping,
            PoolType);
    v24 = v22;
    if ( v22 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          &WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids,
          (unsigned int)v22);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v24, a1, "SecurSup.c", 0x1257u);
      RefsRaiseStatusInternal(a1, v24, v23);
    }
    v25 = RtlLengthSecurityDescriptor(NewDescriptor);
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, &WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids, 3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811, a1, "SecurSup.c", 0x127Eu);
      RefsRaiseStatusInternal(a1, -1073741811, v26);
    }
    v4 = RefsCacheSharedSecurityByDescriptor(a1, NewDescriptor, v25, 1u);
  }
  if ( v4 )
  {
    SecurityDescriptor = NewDescriptor;
    NewDescriptor = (char *)v4 + 20;
    v36 = 0;
  }
  if ( v5 && !v42 )
  {
    v27 = (struct _FAST_MUTEX *)(*((_QWORD *)a1 + 8) + 728LL);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v27);
    v6 = 1;
    AddCachedSharedSecurityForCreateUnsafe(
      (struct _VCB *)a2->Header.FileContextSupportPointer,
      (struct _SHARED_SECURITY *)((char *)v4 + 8),
      v5);
  }
  if ( v5 )
  {
    if ( !v6 )
    {
      v28 = (struct _FAST_MUTEX *)*((_QWORD *)a1 + 8);
      KeEnterGuardedRegion();
      ExAcquireFastMutexUnsafe(v28 + 13);
      v6 = 1;
    }
    if ( (*(_DWORD *)v5)-- == 1 )
      ExFreePoolWithTag(v5, 0);
  }
  if ( v6 )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*((_QWORD *)a1 + 8) + 728LL));
    KeLeaveGuardedRegion();
  }
  v30 = NewDescriptor;
  v31 = *(_QWORD *)(v8 + 72);
  if ( (*(_DWORD *)(v8 + 12) & 0x4000000) == 0 )
  {
    v32 = *(void **)(v31 + 48);
    if ( v32 )
      ExFreePoolWithTag(v32, 0);
  }
  v33 = *(_DWORD *)(v8 + 12);
  if ( v36 )
    v34 = v33 & 0xFBFFFFFF;
  else
    v34 = v33 | 0x4000000;
  *(_DWORD *)(v8 + 12) = v34;
  *(_QWORD *)(v31 + 48) = v30;
  if ( SecurityDescriptor )
    SeDeassignSecurity(&SecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x140330f04  mov     rax, rsp
0x140330f07  mov     [rax+8], rcx
0x140330f0b  push    rbx
0x140330f0c  push    rsi
0x140330f0d  push    rdi
0x140330f0e  push    r12
0x140330f10  push    r13
0x140330f12  push    r14
0x140330f14  push    r15
0x140330f16  sub     rsp, 80h
0x140330f1d  mov     r13, rdx
0x140330f20  mov     rdi, rcx
0x140330f23  xor     ecx, ecx
0x140330f25  mov     [rax-60h], rcx
0x140330f29  mov     r14d, ecx
0x140330f2c  mov     [rax+18h], rcx
0x140330f30  mov     esi, ecx
0x140330f32  mov     [rax-50h], rcx
0x140330f36  mov     [rax-67h], cl
0x140330f39  mov     r12b, cl
0x140330f3c  mov     [rax-68h], cl
0x140330f3f  mov     [rax-58h], rcx
0x140330f43  mov     byte ptr [rax-66h], 1
0x140330f47  mov     rax, [rdi+48h]
0x140330f4b  mov     rbx, [rax+0B8h]
0x140330f52  mov     al, [rbx+10h]
0x140330f55  and     al, 1
0x140330f57  mov     [rsp+0B8h+arg_8], al
0x140330f5e  mov     rax, [rbx+8]
0x140330f62  mov     r15, [rax+8]
0x140330f66  mov     [rsp+0B8h+var_48], r15
0x140330f6b  cmp     [rdx+0C0h], rcx
0x140330f72  jnz     short loc_140330F7C
0x140330f74  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140330f77  call    ?RefsLoadSecurityDescriptor@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsLoadSecurityDescriptor(_IRP_CONTEXT *,_FCB *)
0x140330f7c  mov     r8, [r13+0C0h]
0x140330f83  add     r8, 14h; ParentSecurityDescriptor
0x140330f87  mov     rdx, [r15+40h]; SecurityDescriptor
0x140330f8b  mov     rcx, cs:__imp_IoFileObjectType
0x140330f92  mov     rcx, [rcx]; ObjectType
0x140330f95  call    cs:__imp_SeComputeAutoInheritByObjectType
0x140330f9c  nop     dword ptr [rax+rax+00h]
0x140330fa1  mov     r8d, eax
0x140330fa4  mov     [rsp+0B8h+arg_18], eax
0x140330fab  mov     rcx, [rdi+48h]
0x140330faf  test    rcx, rcx
0x140330fb2  jnz     short loc_140330FCA
0x140330fb4  call    cs:__imp_ExGetPreviousMode
0x140330fbb  nop     dword ptr [rax+rax+00h]
0x140330fc0  mov     r8d, [rsp+0B8h+arg_18]
0x140330fc8  jmp     short loc_14033101E
0x140330fca  mov     al, [rbx]
0x140330fcc  test    al, al
0x140330fce  jnz     short loc_140330FDA
0x140330fd0  test    byte ptr [rbx+2], 1
0x140330fd4  jz      short loc_14033101B
0x140330fd6  mov     al, 1
0x140330fd8  jmp     short loc_14033101E
0x140330fda  cmp     al, 6
0x140330fdc  jnz     short loc_140331009
0x140330fde  mov     edx, [rbx+10h]
0x140330fe1  lea     eax, [rdx-0Ah]
0x140330fe4  cmp     eax, 3Eh ; '>'
0x140330fe7  ja      short loc_140331002
0x140330fe9  mov     r9, 4080000000000003h
0x140330ff3  bt      r9, rax
0x140330ff7  jnb     short loc_140331002
0x140330ff9  mov     al, [rbx+2]
0x140330ffc  not     al
0x140330ffe  and     al, 1
0x140331000  jmp     short loc_14033101E
0x140331002  cmp     edx, 47h ; 'G'
0x140331005  jnz     short loc_14033101B
0x140331007  jmp     short loc_140330FD0
0x140331009  cmp     al, 5
0x14033100b  jnz     short loc_14033101B
0x14033100d  cmp     dword ptr [rbx+10h], 47h ; 'G'
0x140331011  jnz     short loc_14033101B
0x140331013  test    byte ptr [rbx+2], 1
0x140331017  mov     al, 1
0x140331019  jnz     short loc_14033101E
0x14033101b  mov     al, [rcx+40h]
0x14033101e  neg     al
0x140331020  sbb     eax, eax
0x140331022  and     eax, 1FE8h
0x140331027  add     eax, 4018h
0x14033102c  or      r8d, eax; unsigned int
0x14033102f  mov     [rsp+0B8h+arg_18], r8d
0x140331037  cmp     qword ptr [r15+40h], 0
0x14033103c  jnz     short loc_1403310A7
0x14033103e  mov     rax, [r13+0C0h]
0x140331045  lea     rdx, [rax+8]; struct _SECURITY_HASH_KEY *
0x140331049  cmp     dword ptr [rdx+4], 0
0x14033104d  jz      short loc_1403310A7
0x14033104f  mov     rcx, [r13+50h]; struct _VCB *
0x140331053  cmp     qword ptr [rcx+0B0h], 0
0x14033105b  jz      short loc_1403310A7
0x14033105d  lea     r9, [r15+20h]; struct _SECURITY_SUBJECT_CONTEXT *
0x140331061  mov     al, [rsp+0B8h+arg_8]
0x140331068  mov     [rsp+0B8h+IsDirectoryObject], al; unsigned __int8
0x14033106c  call    ?GetSharedSecurityForCreateUnsafe@@YAPEAU_SHARED_SECURITY_FOR_CREATE@@PEAU_VCB@@PEAU_SECURITY_HASH_KEY@@KPEAU_SECURITY_SUBJECT_CONTEXT@@E@Z; GetSharedSecurityForCreateUnsafe(_VCB *,_SECURITY_HASH_KEY *,ulong,_SECURITY_SUBJECT_CONTEXT *,uchar)
0x140331071  mov     rsi, rax
0x140331074  mov     [rsp+0B8h+var_50], rax
0x140331079  test    rax, rax
0x14033107c  jz      short loc_1403310A7
0x14033107e  cmp     dword ptr [rax+0Ch], 0
0x140331082  jz      short loc_1403310A7
0x140331084  lea     r9, [rsp+0B8h+arg_10]
0x14033108c  mov     r8, [rax+8]
0x140331090  mov     rdx, [r13+50h]
0x140331094  mov     rcx, rdi
0x140331097  call    ?RefsCacheSharedSecurityBySecurityId@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAU_VCB@@U_SECURITY_HASH_KEY@@PEAE@Z; RefsCacheSharedSecurityBySecurityId(_IRP_CONTEXT *,_VCB *,_SECURITY_HASH_KEY,uchar *)
0x14033109c  mov     r14, rax
0x14033109f  mov     [rsp+0B8h+arg_10], rax
0x1403310a7  test    r14, r14
0x1403310aa  jnz     loc_140331217
0x1403310b0  mov     ebx, cs:PoolType
0x1403310b6  call    cs:__imp_IoGetFileObjectGenericMapping
0x1403310bd  nop     dword ptr [rax+rax+00h]
0x1403310c2  lea     rdx, [r15+20h]
0x1403310c6  mov     rcx, [r13+0C0h]
0x1403310cd  add     rcx, 14h; ParentDescriptor
0x1403310d1  mov     [rsp+0B8h+PoolType], ebx; PoolType
0x1403310d5  mov     [rsp+0B8h+GenericMapping], rax; GenericMapping
0x1403310da  mov     [rsp+0B8h+SubjectContext], rdx; SubjectContext
0x1403310df  mov     eax, [rsp+0B8h+arg_18]
0x1403310e6  mov     [rsp+0B8h+AutoInheritFlags], eax; AutoInheritFlags
0x1403310ea  mov     al, [rsp+0B8h+arg_8]
0x1403310f1  mov     [rsp+0B8h+IsDirectoryObject], al; IsDirectoryObject
0x1403310f5  xor     r9d, r9d; ObjectType
0x1403310f8  lea     r8, [rsp+0B8h+NewDescriptor]; NewDescriptor
0x1403310fd  mov     rdx, [r15+40h]; ExplicitDescriptor
0x140331101  call    cs:__imp_SeAssignSecurityEx
0x140331108  nop     dword ptr [rax+rax+00h]
0x14033110d  mov     ebx, eax
0x14033110f  test    eax, eax
0x140331111  jns     short loc_140331177
0x140331113  lea     rdx, WPP_GLOBAL_Control
0x14033111a  mov     rcx, cs:WPP_GLOBAL_Control
0x140331121  cmp     rcx, rdx
0x140331124  jz      short loc_14033114C
0x140331126  test    dword ptr [rcx+2Ch], 100h
0x14033112d  jz      short loc_14033114C
0x14033112f  cmp     byte ptr [rcx+29h], 4
0x140331133  jb      short loc_14033114C
0x140331135  lea     edx, [r14+27h]
0x140331139  mov     r9d, eax
0x14033113c  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x140331143  mov     rcx, [rcx+18h]
0x140331147  call    WPP_SF_d
0x14033114c  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140331152  test    al, al
0x140331154  jz      short loc_14033116D
0x140331156  mov     r9d, 1257h; unsigned int
0x14033115c  lea     r8, aSecursupC; "SecurSup.c"
0x140331163  mov     rdx, rdi; struct _IRP_CONTEXT *
0x140331166  mov     ecx, ebx; Status
0x140331168  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14033116d  mov     edx, ebx; int
0x14033116f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140331172  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x140331177  mov     [rsp+0B8h+var_67], 1
0x14033117c  mov     rcx, [rsp+0B8h+NewDescriptor]; SecurityDescriptor
0x140331181  call    cs:__imp_RtlLengthSecurityDescriptor
0x140331188  nop     dword ptr [rax+rax+00h]
0x14033118d  test    eax, eax
0x14033118f  jnz     short loc_1403311FF
0x140331191  lea     rdx, WPP_GLOBAL_Control
0x140331198  mov     rcx, cs:WPP_GLOBAL_Control
0x14033119f  cmp     rcx, rdx
0x1403311a2  jz      short loc_1403311CE
0x1403311a4  mov     eax, [rcx+2Ch]
0x1403311a7  bt      eax, 8
0x1403311ab  jnb     short loc_1403311CE
0x1403311ad  cmp     byte ptr [rcx+29h], 4
0x1403311b1  jb      short loc_1403311CE
0x1403311b3  mov     edx, 28h ; '('
0x1403311b8  mov     r9d, 0C000000Dh
0x1403311be  lea     r8, WPP_06a29487c6fc32a47e98472eca1e6e04_Traceguids
0x1403311c5  mov     rcx, [rcx+18h]
0x1403311c9  call    WPP_SF_d
0x1403311ce  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1403311d4  test    al, al
0x1403311d6  jz      short loc_1403311F2
0x1403311d8  mov     r9d, 127Eh; unsigned int
0x1403311de  lea     r8, aSecursupC; "SecurSup.c"
0x1403311e5  mov     rdx, rdi; struct _IRP_CONTEXT *
0x1403311e8  mov     ecx, 0C000000Dh; Status
0x1403311ed  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1403311f2  mov     edx, 0C000000Dh; int
0x1403311f7  mov     rcx, rdi; struct _IRP_CONTEXT *
0x1403311fa  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1403311ff  mov     r9b, 1; unsigned __int8
0x140331202  mov     r8d, eax; Size
0x140331205  mov     rdx, [rsp+0B8h+NewDescriptor]; SecurityDescriptor
0x14033120a  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14033120d  call    ?RefsCacheSharedSecurityByDescriptor@@YAPEAU_SHARED_SECURITY@@PEAU_IRP_CONTEXT@@PEAXKE@Z; RefsCacheSharedSecurityByDescriptor(_IRP_CONTEXT *,void *,ulong,uchar)
0x140331212  mov     r14, rax
0x140331215  jmp     short loc_14033121C
0x140331217  mov     [rsp+0B8h+var_67], 1
0x14033121c  test    r14, r14
0x14033121f  jz      short loc_140331239
0x140331221  mov     rax, [rsp+0B8h+NewDescriptor]
0x140331226  mov     [rsp+0B8h+SecurityDescriptor], rax
0x14033122b  lea     rax, [r14+14h]
0x14033122f  mov     [rsp+0B8h+NewDescriptor], rax
0x140331234  mov     [rsp+0B8h+var_66], 0
0x140331239  test    rsi, rsi
0x14033123c  jz      short loc_140331288
0x14033123e  cmp     [rsp+0B8h+arg_10], 0
0x140331247  jnz     short loc_140331288
0x140331249  mov     rax, [rdi+40h]
0x14033124d  lea     rbx, [rax+2D8h]
0x140331254  call    cs:__imp_KeEnterGuardedRegion
0x14033125b  nop     dword ptr [rax+rax+00h]
0x140331260  mov     rcx, rbx; FastMutex
0x140331263  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14033126a  nop     dword ptr [rax+rax+00h]
0x14033126f  mov     r12b, 1
0x140331272  mov     [rsp+0B8h+var_68], r12b
0x140331277  lea     rdx, [r14+8]; struct _SECURITY_HASH_KEY *
0x14033127b  mov     r8, rsi; struct _SHARED_SECURITY_FOR_CREATE *
0x14033127e  mov     rcx, [r13+50h]; struct _VCB *
0x140331282  call    ?AddCachedSharedSecurityForCreateUnsafe@@YAXPEAU_VCB@@PEAU_SECURITY_HASH_KEY@@PEAU_SHARED_SECURITY_FOR_CREATE@@@Z; AddCachedSharedSecurityForCreateUnsafe(_VCB *,_SECURITY_HASH_KEY *,_SHARED_SECURITY_FOR_CREATE *)
0x140331287  nop
0x140331288  test    rsi, rsi
0x14033128b  jz      short loc_1403312CE
0x14033128d  test    r12b, r12b
0x140331290  jnz     short loc_1403312B8
0x140331292  mov     rbx, [rdi+40h]
0x140331296  call    cs:__imp_KeEnterGuardedRegion
0x14033129d  nop     dword ptr [rax+rax+00h]
0x1403312a2  lea     rcx, [rbx+2D8h]; FastMutex
0x1403312a9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1403312b0  nop     dword ptr [rax+rax+00h]
0x1403312b5  mov     r12b, 1
0x1403312b8  add     dword ptr [rsi], 0FFFFFFFFh
0x1403312bb  jnz     short loc_1403312CE
0x1403312bd  xor     edx, edx; Tag
0x1403312bf  mov     rcx, rsi; P
0x1403312c2  call    cs:__imp_ExFreePoolWithTag
0x1403312c9  nop     dword ptr [rax+rax+00h]
0x1403312ce  test    r12b, r12b
0x1403312d1  jz      short loc_1403312F6
0x1403312d3  mov     rcx, [rdi+40h]
0x1403312d7  add     rcx, 2D8h; FastMutex
0x1403312de  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1403312e5  nop     dword ptr [rax+rax+00h]
0x1403312ea  call    cs:__imp_KeLeaveGuardedRegion
0x1403312f1  nop     dword ptr [rax+rax+00h]
0x1403312f6  mov     rdi, [rsp+0B8h+NewDescriptor]
0x1403312fb  mov     rbx, [r15+48h]
0x1403312ff  mov     esi, 4000000h
0x140331304  test    [r15+0Ch], esi
0x140331308  jnz     short loc_140331321
0x14033130a  mov     rcx, [rbx+30h]; P
0x14033130e  test    rcx, rcx
0x140331311  jz      short loc_140331321
0x140331313  xor     edx, edx; Tag
0x140331315  call    cs:__imp_ExFreePoolWithTag
0x14033131c  nop     dword ptr [rax+rax+00h]
0x140331321  mov     eax, [r15+0Ch]
0x140331325  cmp     [rsp+0B8h+var_66], 0
0x14033132a  jz      short loc_140331332
0x14033132c  btr     eax, 1Ah
0x140331330  jmp     short loc_140331334
0x140331332  or      eax, esi
0x140331334  mov     [r15+0Ch], eax
0x140331338  mov     [rbx+30h], rdi
0x14033133c  cmp     [rsp+0B8h+SecurityDescriptor], 0
0x140331342  jz      short loc_140331355
0x140331344  lea     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x140331349  call    cs:__imp_SeDeassignSecurity
0x140331350  nop     dword ptr [rax+rax+00h]
0x140331355  mov     rax, r14
0x140331358  add     rsp, 80h
0x14033135f  pop     r15
0x140331361  pop     r14
0x140331363  pop     r13
0x140331365  pop     r12
0x140331367  pop     rdi
0x140331368  pop     rsi
0x140331369  pop     rbx
0x14033136a  retn
0x140344556  push    rbx
0x140344558  push    rbp
0x140344559  push    rsi
0x14034455a  push    rdi
0x14034455b  sub     rsp, 58h
0x14034455f  mov     rbp, rdx
0x140344562  mov     rdi, [rbp+68h]
0x140344566  test    rdi, rdi
0x140344569  jz      short loc_1403445C0
0x14034456b  cmp     byte ptr [rbp+50h], 0
0x14034456f  jnz     short loc_14034459F
0x140344571  mov     rax, [rbp+0C0h]
0x140344578  mov     rbx, [rax+40h]
0x14034457c  call    cs:__imp_KeEnterGuardedRegion
0x140344583  nop     dword ptr [rax+rax+00h]
0x140344588  lea     rcx, [rbx+2D8h]; FastMutex
  ... truncated ...
```
