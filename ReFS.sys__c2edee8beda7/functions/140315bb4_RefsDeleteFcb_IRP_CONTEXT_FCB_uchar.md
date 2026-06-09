# RefsDeleteFcb(_IRP_CONTEXT *,_FCB *,uchar *)

- ea: `0x140315bb4`
- end: `0x140315f2a`
- name: `?RefsDeleteFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAE@Z`
- size: `886`
- prototype: `void __fastcall(struct _IRP_CONTEXT *, struct _FCB *, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14000b1b0`
- `0x140307728`
- `0x140307db0`
- `0x140314690`
- `0x1403407b0`

## callees

- `0x140036670`
- `0x140072a40`
- `0x1400801d0`
- `0x1400891f0`
- `0x1400926e0`
- `0x14009e0f0`
- `0x1400a0cf0`
- `0x140103428`
- `0x140114834`
- `0x1402e7da4`
- `0x1403032f0`
- `0x140315bb4`
- `0x140315f30`
- `0x140315fa0`
- `0x140327c50`

## import_xrefs

- `ntoskrnl!ExIsFastResourceHeld` at `0x140315c6a`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140315c6a`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140315dec`
- `ntoskrnl!KeEnterGuardedRegion` at `0x140315dec`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140315f04`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140315f04`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140315d6c`
- `ntoskrnl!RtlAvlRemoveNode` at `0x140315d6c`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140315ec5`
- `ntoskrnl!FsRtlTeardownPerFileContexts` at `0x140315ec5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140315dff`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140315dff`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140315e3c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140315e3c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140315e48`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140315e48`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140315c4f`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140315c4f`
- `ntoskrnl!ExReleaseFastResource` at `0x140315da4`
- `ntoskrnl!ExReleaseFastResource` at `0x140315da4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315ede`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140315ede`

## pseudocode

```c
void __fastcall RefsDeleteFcb(struct _IRP_CONTEXT *a1, struct _FCB *a2, unsigned __int8 *a3)
{
  char v5; // r15
  struct _IRP_CONTEXT *v6; // rbx
  struct _FCB **v7; // r14
  int v8; // ebp
  struct _FCB *v9; // rcx
  struct _IRP_CONTEXT *v10; // rax
  __int64 v11; // rax
  PVOID Context; // rcx
  struct _MS_FAST_RESOURCE_OWNER_ENTRY *IrpContextPagingIoOwnerEntryRelease; // rax
  __int64 v14; // r8
  PVOID v15; // rcx
  PVOID *FileContextSupportPointer; // rbx
  PVOID *v17; // rbx
  struct _LIST_ENTRY *Flink; // rcx
  struct _ROLLBACK_STRUCT *v19; // rax
  struct _IRP_CONTEXT *v20; // rcx
  struct _IRP_CONTEXT *v21; // rcx
  struct _ROLLBACK_STRUCT *v22; // rax
  struct _IRP_CONTEXT *v23; // rcx
  struct _LIST_ENTRY *v24; // rax
  PERESOURCE Resource; // rax
  struct _LOOKASIDE_LIST_EX *v26; // rcx

  if ( !_bittest64((const signed __int64 *)a1 + 1, 0x25u) || (v5 = 1, ((__int64)a2->spacer.Resource & 0x2000000) == 0) )
    v5 = 0;
  if ( ((_DWORD)a2->Header.FileContextSupportPointer[3] & 0x2000) != 0 && (*((_DWORD *)a1 + 1) & 0x40000000) == 0 )
    __int2c();
  RefsFreeSnapshotsForFcb(a1, a2);
  if ( !v5 && a2->Header.FilterContexts.Blink )
    ListHeadBase<_FCB,64,ListEntryLinks>::RemoveFromAnyList(a2);
  v6 = a1;
  do
  {
    v7 = (struct _FCB **)*((_QWORD *)v6 + 6);
    if ( v7 )
    {
      v8 = *((unsigned __int16 *)v6 + 21);
      if ( v8 == 1 )
        v7 = (struct _FCB **)((char *)v6 + 48);
      do
      {
        v9 = *v7;
        if ( *v7 && v9 == a2 )
        {
          if ( (unsigned __int8)ExIsFastResourceHeldExclusive(&v9->pNetRoot->InnerNamePrefix)
            && (unsigned __int8)ExIsFastResourceHeld(&(*v7)->pNetRoot->InnerNamePrefix) == 1 )
          {
            RefsFreeSnapshotsForFcb(v6, *v7);
          }
          RefsReleaseResource(v6, *v7);
          *v7 = 0;
          if ( *((_WORD *)v6 + 21) == 1 )
            *((_WORD *)v6 + 21) = 0;
        }
        ++v7;
        --v8;
      }
      while ( v8 );
    }
    v10 = (struct _IRP_CONTEXT *)*((_QWORD *)v6 + 13);
    if ( v6 == v10 )
      break;
    v6 = (struct _IRP_CONTEXT *)*((_QWORD *)v6 + 13);
  }
  while ( v10 );
  if ( !v5 )
  {
    if ( *((struct _FCB **)a1 + 7) == a2 )
    {
      *((_QWORD *)a1 + 7) = 0;
    }
    else
    {
      v11 = *((_QWORD *)a1 + 13);
      if ( *(struct _FCB **)(v11 + 56) == a2 )
        *(_QWORD *)(v11 + 56) = 0;
    }
    Context = a2->Context;
    if ( Context )
    {
      while ( (unsigned __int8)MsIsFastResourceHeld(Context) )
      {
        IrpContextPagingIoOwnerEntryRelease = RefsGetIrpContextPagingIoOwnerEntryRelease(
                                                a1,
                                                (struct _MS_FAST_RESOURCE *)a2->Context);
        if ( IrpContextPagingIoOwnerEntryRelease && *((_DWORD *)IrpContextPagingIoOwnerEntryRelease + 18) )
          MsReleaseFastResource(v14, IrpContextPagingIoOwnerEntryRelease);
        else
          MsReleaseFastResourceLegacy(v14);
        Context = a2->Context;
      }
    }
    if ( a2->pNetRoot->NodeTypeCode == 2117 )
    {
      v15 = a2->Context;
      if ( v15 )
      {
        RefsFreeEresource(v15);
        a2->Context = 0;
      }
    }
    if ( ((__int64)a2->spacer.Resource & 0x40) != 0 )
    {
      FileContextSupportPointer = a2->Header.FileContextSupportPointer;
      RtlAvlRemoveNode(FileContextSupportPointer + 104, &a2->pNetRoot[2].Flags);
      --*((_DWORD *)FileContextSupportPointer + 210);
      a2->Header.Resource = (PERESOURCE)((unsigned __int64)a2->Header.Resource & ~0x40uLL);
    }
  }
  if ( *(_QWORD *)&a2->FcbTableEntry.Path.Length )
    RefsFreeFcbUsnRecord(a1, a2);
  ExReleaseFastResource(a2->Header.FileContextSupportPointer + 78, 0);
  *a3 = 0;
  RefsReleaseAllDataStreamSets(a2);
  if ( !v5 )
  {
    RefsDeleteNonpagedFcb((char *)a2->pNetRoot);
    a2->pNetRoot = 0;
  }
  if ( *(_QWORD *)&a2->FcbTableEntry.Lookups )
    RefsCloseFcbTable(a2);
  if ( a2->ScavengerFinalizationList.Flink )
  {
    v17 = a2->Header.FileContextSupportPointer;
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)v17 + 13);
    --LODWORD(a2->ScavengerFinalizationList.Flink->Flink);
    Flink = a2->ScavengerFinalizationList.Flink;
    if ( !LODWORD(Flink->Flink) )
      ExFreePoolWithTag(Flink, 0);
    a2->ScavengerFinalizationList.Flink = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)v17 + 13);
    KeLeaveGuardedRegion();
  }
  v19 = RefsAddStructToRollbackList(a1, 0x823u, a2, 0);
  if ( v19 )
    RefsProcessRollbackStruct(v20, v19, 0x10u);
  v21 = (struct _IRP_CONTEXT *)*((_QWORD *)a1 + 13);
  if ( a1 != v21 )
  {
    v22 = RefsAddStructToRollbackList(v21, 0x823u, a2, 0);
    if ( v22 )
      RefsProcessRollbackStruct(v23, v22, 0x10u);
  }
  if ( v5 )
  {
    a2->Header.Resource = (PERESOURCE)((unsigned __int64)a2->Header.Resource | 0x4000000);
  }
  else
  {
    v24 = a2->FcbTableEntry.HashLinks.Flink;
    if ( v24 )
      LOBYTE(v24->Flink) = 1;
    if ( ((__int64)a2->spacer.Resource & 4) == 0 )
      FsRtlTeardownPerFileContexts((PVOID *)&a2->FcbTableEntry.HashLinks.Blink);
    Resource = a2->Header.Resource;
    if ( ((unsigned __int8)Resource & 2) != 0 )
    {
      ExFreePoolWithTag(a2, 0);
    }
    else
    {
      v26 = &RefsFcbIndexLookasideList;
      if ( ((unsigned __int16)Resource & 0x400) == 0 )
        v26 = &RefsFcbDataLookasideList;
      ExFreeToLookasideListEx(v26, a2);
    }
  }
}

```

## disassembly

```asm
0x140315bb4  mov     [rsp+arg_10], r8
0x140315bb9  push    rbx
0x140315bba  push    rbp
0x140315bbb  push    rsi
0x140315bbc  push    rdi
0x140315bbd  push    r12
0x140315bbf  push    r13
0x140315bc1  push    r14
0x140315bc3  push    r15
0x140315bc5  sub     rsp, 28h
0x140315bc9  xor     r13d, r13d
0x140315bcc  mov     rdi, rdx
0x140315bcf  bt      qword ptr [rcx+8], 25h ; '%'
0x140315bd5  mov     rsi, rcx
0x140315bd8  jnb     short loc_140315BE7
0x140315bda  mov     eax, [rdx+8]
0x140315bdd  mov     r15b, 1
0x140315be0  bt      rax, 19h
0x140315be5  jb      short loc_140315BEA
0x140315be7  mov     r15b, r13b
0x140315bea  mov     rax, [rdx+50h]
0x140315bee  test    dword ptr [rax+18h], 2000h
0x140315bf5  jz      short loc_140315C02
0x140315bf7  test    dword ptr [rcx+4], 40000000h
0x140315bfe  jnz     short loc_140315C02
0x140315c00  int     2Ch; Windows NT - assertion failure
0x140315c02  call    ?RefsFreeSnapshotsForFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsFreeSnapshotsForFcb(_IRP_CONTEXT *,_FCB *)
0x140315c07  test    r15b, r15b
0x140315c0a  jnz     short loc_140315C1A
0x140315c0c  cmp     [rdi+40h], r13
0x140315c10  jz      short loc_140315C1A
0x140315c12  mov     rcx, rdi
0x140315c15  call    ?RemoveFromAnyList@?$ListHeadBase@U_FCB@@$0EA@VListEntryLinks@@@@SAXAEAU_FCB@@@Z; ListHeadBase<_FCB,64,ListEntryLinks>::RemoveFromAnyList(_FCB &)
0x140315c1a  mov     rbx, rsi
0x140315c1d  mov     r12d, 1
0x140315c23  lea     rax, [rbx+30h]
0x140315c27  mov     r14, [rax]
0x140315c2a  test    r14, r14
0x140315c2d  jz      short loc_140315CA9
0x140315c2f  movzx   ebp, word ptr [rbx+2Ah]
0x140315c33  cmp     ebp, r12d
0x140315c36  cmovz   r14, rax
0x140315c3a  mov     rcx, [r14]
0x140315c3d  test    rcx, rcx
0x140315c40  jz      short loc_140315CA0
0x140315c42  cmp     rcx, rdi
0x140315c45  jnz     short loc_140315CA0
0x140315c47  mov     rcx, [rcx+58h]
0x140315c4b  add     rcx, 40h ; '@'
0x140315c4f  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140315c56  nop     dword ptr [rax+rax+00h]
0x140315c5b  test    al, al
0x140315c5d  jz      short loc_140315C86
0x140315c5f  mov     rax, [r14]
0x140315c62  mov     rcx, [rax+58h]
0x140315c66  add     rcx, 40h ; '@'
0x140315c6a  call    cs:__imp_ExIsFastResourceHeld
0x140315c71  nop     dword ptr [rax+rax+00h]
0x140315c76  cmp     al, r12b
0x140315c79  jnz     short loc_140315C86
0x140315c7b  mov     rdx, [r14]; struct _FCB *
0x140315c7e  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140315c81  call    ?RefsFreeSnapshotsForFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsFreeSnapshotsForFcb(_IRP_CONTEXT *,_FCB *)
0x140315c86  mov     rdx, [r14]
0x140315c89  mov     rcx, rbx
0x140315c8c  call    ?RefsReleaseResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleaseResource(_IRP_CONTEXT *,PFCBOrSCB)
0x140315c91  mov     [r14], r13
0x140315c94  cmp     [rbx+2Ah], r12w
0x140315c99  jnz     short loc_140315CA0
0x140315c9b  mov     [rbx+2Ah], r13w
0x140315ca0  add     r14, 8
0x140315ca4  add     ebp, 0FFFFFFFFh
0x140315ca7  jnz     short loc_140315C3A
0x140315ca9  mov     rax, [rbx+68h]
0x140315cad  cmp     rbx, rax
0x140315cb0  jz      short loc_140315CBE
0x140315cb2  mov     rbx, rax
0x140315cb5  test    rax, rax
0x140315cb8  jnz     loc_140315C23
0x140315cbe  mov     r12, [rsp+68h+arg_10]
0x140315cc6  test    r15b, r15b
0x140315cc9  jnz     loc_140315D83
0x140315ccf  cmp     [rsi+38h], rdi
0x140315cd3  jnz     short loc_140315CDB
0x140315cd5  mov     [rsi+38h], r13
0x140315cd9  jmp     short loc_140315CE9
0x140315cdb  mov     rax, [rsi+68h]
0x140315cdf  cmp     [rax+38h], rdi
0x140315ce3  jnz     short loc_140315CE9
0x140315ce5  mov     [rax+38h], r13
0x140315ce9  mov     rcx, [rdi+60h]
0x140315ced  test    rcx, rcx
0x140315cf0  jnz     short loc_140315D27
0x140315cf2  jmp     short loc_140315D30
0x140315cf4  mov     r8, [rdi+60h]
0x140315cf8  mov     rcx, rsi; struct _IRP_CONTEXT *
0x140315cfb  mov     rdx, r8; struct _MS_FAST_RESOURCE *
0x140315cfe  call    ?RefsGetIrpContextPagingIoOwnerEntryRelease@@YAPEAU_MS_FAST_RESOURCE_OWNER_ENTRY@@PEAU_IRP_CONTEXT@@PEAU_MS_FAST_RESOURCE@@@Z; RefsGetIrpContextPagingIoOwnerEntryRelease(_IRP_CONTEXT *,_MS_FAST_RESOURCE *)
0x140315d03  test    rax, rax
0x140315d06  jz      short loc_140315D1B
0x140315d08  cmp     [rax+48h], r13d
0x140315d0c  jz      short loc_140315D1B
0x140315d0e  mov     rdx, rax
0x140315d11  mov     rcx, r8
0x140315d14  call    MsReleaseFastResource
0x140315d19  jmp     short loc_140315D23
0x140315d1b  mov     rcx, r8
0x140315d1e  call    MsReleaseFastResourceLegacy
0x140315d23  mov     rcx, [rdi+60h]
0x140315d27  call    MsIsFastResourceHeld
0x140315d2c  test    al, al
0x140315d2e  jnz     short loc_140315CF4
0x140315d30  mov     rax, [rdi+58h]
0x140315d34  mov     ecx, 845h
0x140315d39  cmp     [rax], cx
0x140315d3c  jnz     short loc_140315D50
0x140315d3e  mov     rcx, [rdi+60h]; P
0x140315d42  test    rcx, rcx
0x140315d45  jz      short loc_140315D50
0x140315d47  call    ?RefsFreeEresource@@YAXPEAU_MS_FAST_RESOURCE@@@Z; RefsFreeEresource(_MS_FAST_RESOURCE *)
0x140315d4c  mov     [rdi+60h], r13
0x140315d50  test    byte ptr [rdi+8], 40h
0x140315d54  jz      short loc_140315D83
0x140315d56  mov     rbx, [rdi+50h]
0x140315d5a  mov     rdx, [rdi+58h]
0x140315d5e  add     rdx, 110h
0x140315d65  lea     rcx, [rbx+340h]
0x140315d6c  call    cs:__imp_RtlAvlRemoveNode
0x140315d73  nop     dword ptr [rax+rax+00h]
0x140315d78  dec     dword ptr [rbx+348h]
0x140315d7e  and     qword ptr [rdi+8], 0FFFFFFFFFFFFFFBFh
0x140315d83  cmp     [rdi+0E8h], r13
0x140315d8a  jz      short loc_140315D97
0x140315d8c  mov     rdx, rdi; struct _FCB *
0x140315d8f  mov     rcx, rsi; struct _IRP_CONTEXT *
0x140315d92  call    ?RefsFreeFcbUsnRecord@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@@Z; RefsFreeFcbUsnRecord(_IRP_CONTEXT *,_FCB *)
0x140315d97  mov     rcx, [rdi+50h]
0x140315d9b  xor     edx, edx
0x140315d9d  add     rcx, 270h
0x140315da4  call    cs:__imp_ExReleaseFastResource
0x140315dab  nop     dword ptr [rax+rax+00h]
0x140315db0  mov     rcx, rdi; struct _FCB *
0x140315db3  mov     [r12], r13b
0x140315db7  call    ?RefsReleaseAllDataStreamSets@@YAXPEAU_FCB@@@Z; RefsReleaseAllDataStreamSets(_FCB *)
0x140315dbc  test    r15b, r15b
0x140315dbf  jnz     short loc_140315DCE
0x140315dc1  mov     rcx, [rdi+58h]; Entry
0x140315dc5  call    RefsDeleteNonpagedFcb
0x140315dca  mov     [rdi+58h], r13
0x140315dce  cmp     [rdi+108h], r13
0x140315dd5  jz      short loc_140315DDF
0x140315dd7  mov     rcx, rdi; struct _FCB *
0x140315dda  call    ?RefsCloseFcbTable@@YAXPEAU_FCB@@@Z; RefsCloseFcbTable(_FCB *)
0x140315ddf  cmp     [rdi+0C0h], r13
0x140315de6  jz      short loc_140315E54
0x140315de8  mov     rbx, [rdi+50h]
0x140315dec  call    cs:__imp_KeEnterGuardedRegion
0x140315df3  nop     dword ptr [rax+rax+00h]
0x140315df8  lea     rcx, [rbx+2D8h]; FastMutex
0x140315dff  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140315e06  nop     dword ptr [rax+rax+00h]
0x140315e0b  mov     rax, [rdi+0C0h]
0x140315e12  dec     dword ptr [rax]
0x140315e14  mov     rcx, [rdi+0C0h]; P
0x140315e1b  cmp     [rcx], r13d
0x140315e1e  jnz     short loc_140315E2E
0x140315e20  xor     edx, edx; Tag
0x140315e22  call    cs:__imp_ExFreePoolWithTag
0x140315e29  nop     dword ptr [rax+rax+00h]
0x140315e2e  lea     rcx, [rbx+2D8h]; FastMutex
0x140315e35  mov     [rdi+0C0h], r13
0x140315e3c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140315e43  nop     dword ptr [rax+rax+00h]
0x140315e48  call    cs:__imp_KeLeaveGuardedRegion
0x140315e4f  nop     dword ptr [rax+rax+00h]
0x140315e54  mov     ebp, 823h
0x140315e59  xor     r9d, r9d; unsigned int
0x140315e5c  mov     edx, ebp; unsigned __int16
0x140315e5e  mov     r8, rdi; void *
0x140315e61  mov     rcx, rsi; struct _IRP_CONTEXT *
0x140315e64  call    ?RefsAddStructToRollbackList@@YAPEAU_ROLLBACK_STRUCT@@PEAU_IRP_CONTEXT@@GPEAXK@Z; RefsAddStructToRollbackList(_IRP_CONTEXT *,ushort,void *,ulong)
0x140315e69  mov     ebx, 10h
0x140315e6e  test    rax, rax
0x140315e71  jz      short loc_140315E7E
0x140315e73  mov     r8d, ebx; unsigned int
0x140315e76  mov     rdx, rax; struct _ROLLBACK_STRUCT *
0x140315e79  call    ?RefsProcessRollbackStruct@@YAXPEAU_IRP_CONTEXT@@PEAU_ROLLBACK_STRUCT@@K@Z; RefsProcessRollbackStruct(_IRP_CONTEXT *,_ROLLBACK_STRUCT *,ulong)
0x140315e7e  mov     rcx, [rsi+68h]; struct _IRP_CONTEXT *
0x140315e82  cmp     rsi, rcx
0x140315e85  jz      short loc_140315EA4
0x140315e87  mov     edx, ebp; unsigned __int16
0x140315e89  xor     r9d, r9d; unsigned int
0x140315e8c  mov     r8, rdi; void *
0x140315e8f  call    ?RefsAddStructToRollbackList@@YAPEAU_ROLLBACK_STRUCT@@PEAU_IRP_CONTEXT@@GPEAXK@Z; RefsAddStructToRollbackList(_IRP_CONTEXT *,ushort,void *,ulong)
0x140315e94  test    rax, rax
0x140315e97  jz      short loc_140315EA4
0x140315e99  mov     r8d, ebx; unsigned int
0x140315e9c  mov     rdx, rax; struct _ROLLBACK_STRUCT *
0x140315e9f  call    ?RefsProcessRollbackStruct@@YAXPEAU_IRP_CONTEXT@@PEAU_ROLLBACK_STRUCT@@K@Z; RefsProcessRollbackStruct(_IRP_CONTEXT *,_ROLLBACK_STRUCT *,ulong)
0x140315ea4  test    r15b, r15b
0x140315ea7  jnz     short loc_140315F12
0x140315ea9  mov     rax, [rdi+0F8h]
0x140315eb0  test    rax, rax
0x140315eb3  jz      short loc_140315EB8
0x140315eb5  mov     byte ptr [rax], 1
0x140315eb8  test    byte ptr [rdi+8], 4
0x140315ebc  jnz     short loc_140315ED1
0x140315ebe  lea     rcx, [rdi+100h]; PerFileContextPointer
0x140315ec5  call    cs:__imp_FsRtlTeardownPerFileContexts
0x140315ecc  nop     dword ptr [rax+rax+00h]
0x140315ed1  mov     rax, [rdi+8]
0x140315ed5  test    al, 2
0x140315ed7  jz      short loc_140315EEC
0x140315ed9  xor     edx, edx; Tag
0x140315edb  mov     rcx, rdi; P
0x140315ede  call    cs:__imp_ExFreePoolWithTag
0x140315ee5  nop     dword ptr [rax+rax+00h]
0x140315eea  jmp     short loc_140315F18
0x140315eec  lea     rcx, ?RefsFcbIndexLookasideList@@3U_LOOKASIDE_LIST_EX@@A; _LOOKASIDE_LIST_EX RefsFcbIndexLookasideList
0x140315ef3  mov     rdx, rdi; Entry
0x140315ef6  bt      rax, 0Ah
0x140315efb  jb      short loc_140315F04
0x140315efd  lea     rcx, ?RefsFcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140315f04  call    cs:__imp_ExFreeToLookasideListEx
0x140315f0b  nop     dword ptr [rax+rax+00h]
0x140315f10  jmp     short loc_140315F18
0x140315f12  bts     qword ptr [rdi+8], 1Ah
0x140315f18  add     rsp, 28h
0x140315f1c  pop     r15
0x140315f1e  pop     r14
0x140315f20  pop     r13
0x140315f22  pop     r12
0x140315f24  pop     rdi
0x140315f25  pop     rsi
0x140315f26  pop     rbp
0x140315f27  pop     rbx
0x140315f28  retn
```
