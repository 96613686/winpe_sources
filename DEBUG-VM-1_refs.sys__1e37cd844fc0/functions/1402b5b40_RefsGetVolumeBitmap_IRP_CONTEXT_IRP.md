# RefsGetVolumeBitmap(_IRP_CONTEXT *,_IRP *)

- ea: `0x1402b5b40`
- end: `0x1402b6472`
- name: `?RefsGetVolumeBitmap@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `2354`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140323dd8`

## callees

- `0x14000e0e0`
- `0x14002b340`
- `0x140076ad0`
- `0x14007cdb0`
- `0x140085570`
- `0x1400862c0`
- `0x140090c50`
- `0x1400d0fd8`
- `0x1400fe714`
- `0x14011a708`
- `0x140294944`
- `0x140294980`
- `0x1402b5b40`
- `0x14031def0`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1402b5dc2`
- `ntoskrnl!IoAllocateMdl` at `0x1402b5dc2`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402b5df3`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402b5df3`
- `ntoskrnl!IoFreeMdl` at `0x1402b5e76`
- `ntoskrnl!IoFreeMdl` at `0x1402b6145`
- `ntoskrnl!IoFreeMdl` at `0x140347caf`
- `ntoskrnl!IoFreeMdl` at `0x1402b5e76`
- `ntoskrnl!IoFreeMdl` at `0x1402b6145`
- `ntoskrnl!IoFreeMdl` at `0x140347caf`
- `ntoskrnl!MmUnlockPages` at `0x1402b5e67`
- `ntoskrnl!MmUnlockPages` at `0x1402b6136`
- `ntoskrnl!MmUnlockPages` at `0x140347ca0`
- `ntoskrnl!MmUnlockPages` at `0x1402b5e67`
- `ntoskrnl!MmUnlockPages` at `0x1402b6136`
- `ntoskrnl!MmUnlockPages` at `0x140347ca0`
- `ntoskrnl!ProbeForRead` at `0x1402b5d0b`
- `ntoskrnl!ProbeForRead` at `0x1402b5d0b`
- `ntoskrnl!ProbeForWrite` at `0x1402b5d24`
- `ntoskrnl!ProbeForWrite` at `0x1402b5d24`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402b5e23`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1402b5e23`
- `ntoskrnl!RtlInitializeBitMap` at `0x1402b5ff3`
- `ntoskrnl!RtlInitializeBitMap` at `0x1402b5ff3`

## pseudocode

```c
__int64 __fastcall RefsGetVolumeBitmap(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  unsigned int VolumeBitmap; // edi
  struct _MDL *v5; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int v7; // edx
  ULONG *MappedSystemVa; // rbx
  unsigned int v9; // r9d
  __int64 ULong64FromUser; // r13
  char *v11; // rax
  int *v12; // rcx
  int v13; // eax
  bool v14; // zf
  int v15; // eax
  struct _MDL *Mdl; // rax
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  struct _VCB *v19; // rdi
  unsigned int v20; // r9d
  int v21; // eax
  unsigned __int64 v22; // r13
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  struct _VCB *v25; // rdx
  BOOL v26; // eax
  unsigned int v28; // r8d
  SIZE_T *Irpa; // [rsp+20h] [rbp-B8h]
  char v30; // [rsp+40h] [rbp-98h]
  struct _VCB *v31; // [rsp+48h] [rbp-90h] BYREF
  __int64 v32; // [rsp+50h] [rbp-88h]
  unsigned int Length; // [rsp+58h] [rbp-80h]
  int Length_4; // [rsp+5Ch] [rbp-7Ch]
  volatile void *Address; // [rsp+60h] [rbp-78h] BYREF
  ULONG *v36; // [rsp+68h] [rbp-70h]
  unsigned __int64 v37; // [rsp+70h] [rbp-68h]
  PULONG BitMapBuffer; // [rsp+78h] [rbp-60h]
  PMDL MemoryDescriptorList; // [rsp+80h] [rbp-58h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+88h] [rbp-50h] BYREF
  SIZE_T v43; // [rsp+F0h] [rbp+18h] BYREF
  int v44; // [rsp+F8h] [rbp+20h]

  VolumeBitmap = 0;
  v31 = 0;
  v43 = 0;
  v32 = 0;
  v36 = 0;
  BitMapBuffer = 0;
  v5 = 0;
  MemoryDescriptorList = 0;
  v37 = 0;
  BitMapHeader = 0;
  v44 = 0;
  Length_4 = 0;
  *((_QWORD *)a1 + 1) |= 1uLL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Irpa = &v43;
  RefsDecodeFileObject(a1, CurrentStackLocation->FileObject, &v31, &Address);
  Length = CurrentStackLocation->Parameters.Create.Options;
  Address = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  LODWORD(v43) = CurrentStackLocation->Parameters.Read.Length;
  MappedSystemVa = (ULONG *)RefsMapUserBuffer(Irp, v7);
  v36 = MappedSystemVa;
  if ( !v32 || !_bittest16((const signed __int16 *)(v32 + 88), 9u) )
  {
    VolumeBitmap = -1073741790;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 97, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v9 = 5989;
      goto LABEL_79;
    }
    return VolumeBitmap;
  }
  if ( (unsigned int)v43 < 0x18 )
  {
    VolumeBitmap = -1073741789;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741789);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225507LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v9 = 5994;
LABEL_79:
      RefsStatusDebug(VolumeBitmap, 0, "FsCtrl.c", v9);
      return VolumeBitmap;
    }
    return VolumeBitmap;
  }
  LODWORD(v32) = v43;
  if ( Length >= 8 )
  {
    if ( Irp->RequestorMode
      && (ProbeForRead(Address, Length, 1u), ProbeForWrite(MappedSystemVa, (unsigned int)v43, 1u), Irp->RequestorMode) )
    {
      ULong64FromUser = RtlReadULong64FromUser(Address);
      v11 = (char *)Address;
    }
    else
    {
      v11 = (char *)Address;
      ULong64FromUser = *(_QWORD *)Address;
    }
    v37 = ULong64FromUser;
    BitMapBuffer = MappedSystemVa + 4;
    if ( Length >= 0x10 )
    {
      v12 = (int *)(v11 + 8);
      if ( Irp->RequestorMode )
        LOBYTE(v13) = RtlReadULongFromUser(v12);
      else
        v13 = *v12;
      v14 = (v13 & 1) == 0;
      v15 = v44;
      if ( !v14 )
        v15 = 1;
      v44 = v15;
      Length_4 = v15;
    }
    if ( Irp->RequestorMode )
    {
      Mdl = IoAllocateMdl(MappedSystemVa, v43, 0, 0, 0);
      v5 = Mdl;
      MemoryDescriptorList = Mdl;
      if ( Mdl )
      {
        MmProbeAndLockPages(Mdl, Irp->RequestorMode, IoWriteAccess);
        if ( (v5->MdlFlags & 5) != 0 )
          MappedSystemVa = (ULONG *)v5->MappedSystemVa;
        else
          MappedSystemVa = (ULONG *)MmMapLockedPagesSpecifyCache(v5, 0, MmCached, 0, 0, 0x40000010u);
        v36 = MappedSystemVa;
        if ( MappedSystemVa )
        {
          BitMapBuffer = MappedSystemVa + 4;
          goto LABEL_35;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            100,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, a1, "FsCtrl.c", 0x1795u);
        RefsRaiseStatusInternal(a1, -1073741670, v17);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          101,
          &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
          3221225626LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741670, a1, "FsCtrl.c", 0x179Fu);
      RefsRaiseStatusInternal(a1, -1073741670, v18);
      goto LABEL_95;
    }
LABEL_35:
    v19 = v31;
    RefsAcquireSharedVcb(a1, v31, 1u);
    v30 = 1;
    if ( (*((_DWORD *)v19 + 6) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        VolumeBitmap = -1073741202;
      }
      else
      {
        VolumeBitmap = -1073741202;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            103,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221226094LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v20 = 6081;
LABEL_58:
        RefsStatusDebug(VolumeBitmap, 0, "FsCtrl.c", v20);
        goto LABEL_59;
      }
      goto LABEL_59;
    }
    if ( ULong64FromUser < 0 || ULong64FromUser >= *((_QWORD *)v19 + 30) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        VolumeBitmap = -1073741811;
      }
      else
      {
        VolumeBitmap = -1073741811;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            104,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v20 = 6088;
        goto LABEL_58;
      }
LABEL_59:
      if ( v30 )
        RefsReleaseVcb(a1, v31);
      if ( v5 )
      {
        MmUnlockPages(v5);
        IoFreeMdl(v5);
      }
      RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, VolumeBitmap);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
LABEL_71:
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v9 = 6197;
          goto LABEL_79;
        }
        return VolumeBitmap;
      }
      if ( (VolumeBitmap & 0x80000000) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
LABEL_70:
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            108,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            VolumeBitmap);
          goto LABEL_71;
        }
        v26 = 0;
      }
      else
      {
        v26 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      }
      if ( !v26 )
        goto LABEL_71;
      goto LABEL_70;
    }
    v21 = v43 - 16;
    if ( (unsigned int)(v43 - 16) > 0x1FFFFFFF )
      v21 = 0x1FFFFFFF;
    LODWORD(v43) = v21;
    v22 = ULong64FromUser & 0xFFFFFFFFFFFFFFF8uLL;
    v37 = v22;
    LODWORD(v32) = 8 * v21;
    RtlInitializeBitMap(&BitMapHeader, BitMapBuffer, 8 * v21);
    VolumeBitmap = RefsBindMinstoreTransactionNoRaise(a1);
    if ( (VolumeBitmap & 0x80000000) != 0 )
      goto LABEL_59;
    VolumeBitmap = MsQueryVolumeBitmap(
                     *((struct CmsTransactionContext **)a1 + 3),
                     *((CmsVolume **)v31 + 14),
                     (_DWORD)Irpa,
                     v44);
    if ( (VolumeBitmap & 0x80000000) == 0 )
    {
      RefsReleaseVcb(a1, v31);
      v30 = 0;
      *(_QWORD *)MappedSystemVa = v22;
      v25 = v31;
      *((_QWORD *)MappedSystemVa + 1) = *((_QWORD *)v31 + 30) - v22;
      Irp->IoStatus.Information = (unsigned int)(v43 + 16);
      if ( *((_QWORD *)v25 + 30) <= (signed __int64)(v22 + (unsigned int)v32) )
        goto LABEL_59;
LABEL_102:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          107,
          &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
          2147483653LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-2147483643, a1, "FsCtrl.c", 0x1823u);
      RefsRaiseStatusInternal(a1, -2147483643, v24);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          106,
          &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
          3221225704LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741592, a1, "FsCtrl.c", 0x1819u);
      RefsRaiseStatusInternal(a1, -1073741592, v28);
      JUMPOUT(0x1402B6472LL);
    }
LABEL_95:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 105, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, VolumeBitmap);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(VolumeBitmap, a1, "FsCtrl.c", 0x17F4u);
    RefsRaiseStatusInternal(a1, VolumeBitmap, v23);
    goto LABEL_102;
  }
  VolumeBitmap = -1073741811;
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741811);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 99, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225485LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v9 = 5999;
    goto LABEL_79;
  }
  return VolumeBitmap;
}

```

## disassembly

```asm
0x1402b5b40  mov     r11, rsp
0x1402b5b43  mov     [r11+10h], rdx
0x1402b5b47  mov     [r11+8], rcx
0x1402b5b4b  push    rbx
0x1402b5b4c  push    rsi
0x1402b5b4d  push    rdi
0x1402b5b4e  push    r12
0x1402b5b50  push    r13
0x1402b5b52  push    r14
0x1402b5b54  push    r15
0x1402b5b56  sub     rsp, 0A0h
0x1402b5b5d  mov     r13, rdx
0x1402b5b60  mov     r14, rcx
0x1402b5b63  xor     esi, esi
0x1402b5b65  mov     edi, esi
0x1402b5b67  mov     [rsp+0D8h+var_90], rsi
0x1402b5b6c  mov     [r11+18h], rsi
0x1402b5b70  mov     [rsp+0D8h+var_88], rsi
0x1402b5b75  mov     [r11-70h], rsi
0x1402b5b79  mov     [r11-60h], rsi
0x1402b5b7d  mov     r15d, esi
0x1402b5b80  mov     [r11-58h], rsi
0x1402b5b84  mov     [r11-68h], rsi
0x1402b5b88  xorps   xmm0, xmm0
0x1402b5b8b  movups  xmmword ptr [r11-50h], xmm0
0x1402b5b90  mov     eax, esi
0x1402b5b92  mov     [r11+20h], eax
0x1402b5b96  mov     dword ptr [rsp+0D8h+Length+4], eax
0x1402b5b9a  lea     r12d, [rsi+1]
0x1402b5b9e  or      [rcx+8], r12
0x1402b5ba2  mov     rbx, [rdx+0B8h]
0x1402b5ba9  mov     [rsp+0D8h+var_A8], sil
0x1402b5bae  lea     rax, [rsp+0D8h+var_88]
0x1402b5bb3  mov     qword ptr [rsp+0D8h+Priority], rax
0x1402b5bb8  lea     rax, [r11+18h]
0x1402b5bbc  mov     [rsp+0D8h+Irp], rax
0x1402b5bc1  lea     r9, [r11-78h]
0x1402b5bc5  lea     r8, [rsp+0D8h+var_90]
0x1402b5bca  mov     rdx, [rbx+30h]
0x1402b5bce  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402b5bd3  mov     ecx, [rbx+10h]
0x1402b5bd6  mov     dword ptr [rsp+0D8h+Length], ecx
0x1402b5bda  mov     rax, [rbx+20h]
0x1402b5bde  mov     [rsp+0D8h+Address], rax
0x1402b5be3  mov     eax, [rbx+8]
0x1402b5be6  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1402b5bed  mov     rcx, r13; struct _IRP *
0x1402b5bf0  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x1402b5bf5  mov     rbx, rax
0x1402b5bf8  mov     [rsp+0D8h+var_70], rax
0x1402b5bfd  mov     rax, [rsp+0D8h+var_88]
0x1402b5c02  test    rax, rax
0x1402b5c05  jz      loc_1402B61C7
0x1402b5c0b  bt      word ptr [rax+58h], 9
0x1402b5c11  jnb     loc_1402B61C7
0x1402b5c17  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x1402b5c1e  cmp     eax, 18h
0x1402b5c21  jnb     short loc_1402B5C87
0x1402b5c23  mov     edi, 0C0000023h
0x1402b5c28  mov     r8d, edi; Status
0x1402b5c2b  mov     rdx, r13; Irp
0x1402b5c2e  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402b5c31  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402b5c36  lea     rbx, WPP_GLOBAL_Control
0x1402b5c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b5c44  cmp     rcx, rbx
0x1402b5c47  jz      short loc_1402B5C6E
0x1402b5c49  test    dword ptr [rcx+2Ch], 100h
0x1402b5c50  jz      short loc_1402B5C6E
0x1402b5c52  cmp     byte ptr [rcx+29h], 4
0x1402b5c56  jb      short loc_1402B5C6E
0x1402b5c58  lea     edx, [rsi+62h]
0x1402b5c5b  mov     r9d, edi
0x1402b5c5e  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b5c65  mov     rcx, [rcx+18h]
0x1402b5c69  call    WPP_SF_d
0x1402b5c6e  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b5c74  test    al, al
0x1402b5c76  jz      loc_1402B6234
0x1402b5c7c  mov     r9d, 176Ah
0x1402b5c82  jmp     loc_1402B6224
0x1402b5c87  mov     dword ptr [rsp+0D8h+var_88], eax
0x1402b5c8b  mov     eax, dword ptr [rsp+0D8h+Length]
0x1402b5c8f  cmp     eax, 8
0x1402b5c92  jnb     short loc_1402B5CFA
0x1402b5c94  mov     edi, 0C000000Dh
0x1402b5c99  mov     r8d, edi; Status
0x1402b5c9c  mov     rdx, r13; Irp
0x1402b5c9f  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402b5ca2  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402b5ca7  lea     rbx, WPP_GLOBAL_Control
0x1402b5cae  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b5cb5  cmp     rcx, rbx
0x1402b5cb8  jz      short loc_1402B5CE1
0x1402b5cba  test    dword ptr [rcx+2Ch], 100h
0x1402b5cc1  jz      short loc_1402B5CE1
0x1402b5cc3  cmp     byte ptr [rcx+29h], 4
0x1402b5cc7  jb      short loc_1402B5CE1
0x1402b5cc9  mov     edx, 63h ; 'c'
0x1402b5cce  mov     r9d, edi
0x1402b5cd1  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b5cd8  mov     rcx, [rcx+18h]
0x1402b5cdc  call    WPP_SF_d
0x1402b5ce1  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b5ce7  test    al, al
0x1402b5ce9  jz      loc_1402B6234
0x1402b5cef  mov     r9d, 176Fh
0x1402b5cf5  jmp     loc_1402B6224
0x1402b5cfa  cmp     [r13+40h], sil
0x1402b5cfe  jz      short loc_1402B5D4A
0x1402b5d00  mov     rdx, rax; Length
0x1402b5d03  mov     r8d, r12d; Alignment
0x1402b5d06  mov     rcx, [rsp+0D8h+Address]; Address
0x1402b5d0b  call    cs:__imp_ProbeForRead
0x1402b5d12  nop     dword ptr [rax+rax+00h]
0x1402b5d17  mov     edx, dword ptr [rsp+0D8h+arg_10]; Length
0x1402b5d1e  mov     r8d, r12d; Alignment
0x1402b5d21  mov     rcx, rbx; Address
0x1402b5d24  call    cs:__imp_ProbeForWrite
0x1402b5d2b  nop     dword ptr [rax+rax+00h]
0x1402b5d30  cmp     [r13+40h], sil
0x1402b5d34  jz      short loc_1402B5D4A
0x1402b5d36  mov     rcx, [rsp+0D8h+Address]
0x1402b5d3b  call    RtlReadULong64FromUser
0x1402b5d40  mov     r13, rax
0x1402b5d43  mov     rax, [rsp+0D8h+Address]
0x1402b5d48  jmp     short loc_1402B5D52
0x1402b5d4a  mov     rax, [rsp+0D8h+Address]
0x1402b5d4f  mov     r13, [rax]
0x1402b5d52  mov     [rsp+0D8h+var_68], r13
0x1402b5d57  lea     rcx, [rbx+10h]
0x1402b5d5b  mov     [rsp+0D8h+BitMapBuffer], rcx
0x1402b5d60  cmp     dword ptr [rsp+0D8h+Length], 10h
0x1402b5d65  jb      short loc_1402B5D9B
0x1402b5d67  lea     rcx, [rax+8]
0x1402b5d6b  mov     rax, [rsp+0D8h+arg_8]
0x1402b5d73  cmp     [rax+40h], sil
0x1402b5d77  jz      short loc_1402B5D80
0x1402b5d79  call    RtlReadULongFromUser
0x1402b5d7e  jmp     short loc_1402B5D82
0x1402b5d80  mov     eax, [rcx]
0x1402b5d82  test    r12b, al
0x1402b5d85  mov     eax, [rsp+0D8h+arg_18]
0x1402b5d8c  cmovnz  eax, r12d
0x1402b5d90  mov     [rsp+0D8h+arg_18], eax
0x1402b5d97  mov     dword ptr [rsp+0D8h+Length+4], eax
0x1402b5d9b  mov     rax, [rsp+0D8h+arg_8]
0x1402b5da3  cmp     [rax+40h], sil
0x1402b5da7  jz      loc_1402B5E49
0x1402b5dad  mov     [rsp+0D8h+Irp], rsi; Irp
0x1402b5db2  xor     r9d, r9d; ChargeQuota
0x1402b5db5  xor     r8d, r8d; SecondaryBuffer
0x1402b5db8  mov     edx, dword ptr [rsp+0D8h+arg_10]; Length
0x1402b5dbf  mov     rcx, rbx; VirtualAddress
0x1402b5dc2  call    cs:__imp_IoAllocateMdl
0x1402b5dc9  nop     dword ptr [rax+rax+00h]
0x1402b5dce  mov     r15, rax
0x1402b5dd1  mov     [rsp+0D8h+MemoryDescriptorList], rax
0x1402b5dd9  test    rax, rax
0x1402b5ddc  jz      loc_1402B624A
0x1402b5de2  mov     r8d, r12d; Operation
0x1402b5de5  mov     rax, [rsp+0D8h+arg_8]
0x1402b5ded  mov     dl, [rax+40h]; AccessMode
0x1402b5df0  mov     rcx, r15; MemoryDescriptorList
0x1402b5df3  call    cs:__imp_MmProbeAndLockPages
0x1402b5dfa  nop     dword ptr [rax+rax+00h]
0x1402b5dff  test    byte ptr [r15+0Ah], 5
0x1402b5e04  jz      short loc_1402B5E0C
0x1402b5e06  mov     rbx, [r15+18h]
0x1402b5e0a  jmp     short loc_1402B5E32
0x1402b5e0c  mov     [rsp+0D8h+Priority], 40000010h; Priority
0x1402b5e14  mov     dword ptr [rsp+0D8h+Irp], esi; BugCheckOnFailure
0x1402b5e18  xor     r9d, r9d; RequestedAddress
0x1402b5e1b  mov     r8d, r12d; CacheType
0x1402b5e1e  xor     edx, edx; AccessMode
0x1402b5e20  mov     rcx, r15; MemoryDescriptorList
0x1402b5e23  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1402b5e2a  nop     dword ptr [rax+rax+00h]
0x1402b5e2f  mov     rbx, rax
0x1402b5e32  mov     [rsp+0D8h+var_70], rbx
0x1402b5e37  test    rbx, rbx
0x1402b5e3a  jz      loc_1402B62B6
0x1402b5e40  lea     rax, [rbx+10h]
0x1402b5e44  mov     [rsp+0D8h+BitMapBuffer], rax
0x1402b5e49  jmp     loc_1402B5F16
0x1402b5e4e  mov     edi, eax
0x1402b5e50  mov     r15, [rsp+0D8h+MemoryDescriptorList]
0x1402b5e58  test    r15, r15
0x1402b5e5b  jz      short loc_1402B5E82
0x1402b5e5d  test    byte ptr [r15+0Ah], 2
0x1402b5e62  jz      short loc_1402B5E73
0x1402b5e64  mov     rcx, r15; MemoryDescriptorList
0x1402b5e67  call    cs:__imp_MmUnlockPages
0x1402b5e6e  nop     dword ptr [rax+rax+00h]
0x1402b5e73  mov     rcx, r15; Mdl
0x1402b5e76  call    cs:__imp_IoFreeMdl
0x1402b5e7d  nop     dword ptr [rax+rax+00h]
0x1402b5e82  lea     rax, WPP_GLOBAL_Control
0x1402b5e89  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b5e90  cmp     rcx, rax
0x1402b5e93  jz      short loc_1402B5EC8
0x1402b5e95  test    dword ptr [rcx+2Ch], 100h
0x1402b5e9c  jz      short loc_1402B5EC8
0x1402b5e9e  test    edi, edi
0x1402b5ea0  js      short loc_1402B5EAA
0x1402b5ea2  cmp     byte ptr [rcx+29h], 5
0x1402b5ea6  jnb     short loc_1402B5EB0
0x1402b5ea8  jmp     short loc_1402B5EC8
0x1402b5eaa  cmp     byte ptr [rcx+29h], 4
0x1402b5eae  jb      short loc_1402B5EC8
0x1402b5eb0  mov     r9d, edi
0x1402b5eb3  mov     edx, 66h ; 'f'
0x1402b5eb8  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b5ebf  mov     rcx, [rcx+18h]
0x1402b5ec3  call    WPP_SF_d
0x1402b5ec8  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b5ece  test    al, al
0x1402b5ed0  jz      short loc_1402B5EE8
0x1402b5ed2  mov     ecx, edi; Status
0x1402b5ed4  mov     r9d, 17ADh; unsigned int
0x1402b5eda  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b5ee1  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b5ee3  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b5ee8  xor     esi, esi
0x1402b5eea  lea     r12d, [rsi+1]
0x1402b5eee  mov     r14, [rsp+0D8h+arg_0]
0x1402b5ef6  mov     rbx, [rsp+0D8h+var_70]
0x1402b5efb  mov     eax, dword ptr [rsp+0D8h+var_88]
0x1402b5eff  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1402b5f06  mov     r13, [rsp+0D8h+var_68]
0x1402b5f0b  mov     eax, dword ptr [rsp+0D8h+Length+4]
0x1402b5f0f  mov     [rsp+0D8h+arg_18], eax
0x1402b5f16  test    edi, edi
0x1402b5f18  js      loc_1402B6153
0x1402b5f1e  mov     [rsp+0D8h+var_97], sil
0x1402b5f23  mov     r8b, r12b; unsigned __int8
0x1402b5f26  mov     rdi, [rsp+0D8h+var_90]
0x1402b5f2b  mov     rdx, rdi; struct _VCB *
0x1402b5f2e  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402b5f31  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x1402b5f36  mov     [rsp+0D8h+var_98], r12b
0x1402b5f3b  mov     eax, [rdi+18h]
0x1402b5f3e  test    r12b, al
0x1402b5f41  jnz     short loc_1402B5FA2
0x1402b5f43  lea     rbx, WPP_GLOBAL_Control
0x1402b5f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b5f51  cmp     rcx, rbx
0x1402b5f54  jz      short loc_1402B5F84
0x1402b5f56  mov     eax, [rcx+2Ch]
0x1402b5f59  bt      eax, 8
0x1402b5f5d  jnb     short loc_1402B5F84
0x1402b5f5f  mov     edi, 0C000026Eh
0x1402b5f64  cmp     byte ptr [rcx+29h], 4
0x1402b5f68  jb      short loc_1402B5F89
0x1402b5f6a  mov     edx, 67h ; 'g'
0x1402b5f6f  mov     r9d, edi
0x1402b5f72  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b5f79  mov     rcx, [rcx+18h]
0x1402b5f7d  call    WPP_SF_d
0x1402b5f82  jmp     short loc_1402B5F89
0x1402b5f84  mov     edi, 0C000026Eh
0x1402b5f89  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b5f8f  test    al, al
0x1402b5f91  jz      loc_1402B6116
0x1402b5f97  mov     r9d, 17C1h
0x1402b5f9d  jmp     loc_1402B6106
0x1402b5fa2  test    r13, r13
0x1402b5fa5  js      loc_1402B60B0
0x1402b5fab  cmp     r13, [rdi+0F0h]
0x1402b5fb2  jge     loc_1402B60B0
0x1402b5fb8  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x1402b5fbf  add     eax, 0FFFFFFF0h
0x1402b5fc2  mov     ecx, 1FFFFFFFh
0x1402b5fc7  cmp     eax, ecx
0x1402b5fc9  cmova   eax, ecx
0x1402b5fcc  mov     dword ptr [rsp+0D8h+arg_10], eax
0x1402b5fd3  and     r13, 0FFFFFFFFFFFFFFF8h
0x1402b5fd7  mov     [rsp+0D8h+var_68], r13
0x1402b5fdc  shl     eax, 3
0x1402b5fdf  mov     dword ptr [rsp+0D8h+var_88], eax
0x1402b5fe3  mov     r8d, eax; SizeOfBitMap
0x1402b5fe6  mov     rdx, [rsp+0D8h+BitMapBuffer]; BitMapBuffer
0x1402b5feb  lea     rcx, [rsp+0D8h+BitMapHeader]; BitMapHeader
0x1402b5ff3  call    cs:__imp_RtlInitializeBitMap
0x1402b5ffa  nop     dword ptr [rax+rax+00h]
0x1402b5fff  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402b6002  call    ?RefsBindMinstoreTransactionNoRaise@@YAJPEAU_IRP_CONTEXT@@@Z; RefsBindMinstoreTransactionNoRaise(_IRP_CONTEXT *)
0x1402b6007  mov     edi, eax
0x1402b6009  mov     [rsp+0D8h+var_94], eax
0x1402b600d  test    eax, eax
0x1402b600f  js      loc_1402B60A7
0x1402b6015  mov     eax, [rsp+0D8h+arg_18]
0x1402b601c  mov     [rsp+0D8h+Priority], eax
0x1402b6020  lea     r9, [rsp+0D8h+BitMapHeader]
0x1402b6028  mov     r8, r13
0x1402b602b  mov     rdx, [rsp+0D8h+var_90]
0x1402b6030  mov     rdx, [rdx+70h]
0x1402b6034  mov     rcx, [r14+18h]
0x1402b6038  call    MsQueryVolumeBitmap
0x1402b603d  mov     edi, eax
  ... truncated ...
```
