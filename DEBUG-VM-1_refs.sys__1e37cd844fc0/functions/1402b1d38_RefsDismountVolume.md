# RefsDismountVolume

- ea: `0x1402b1d38`
- end: `0x1402b2760`
- name: `RefsDismountVolume`
- size: `2600`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140323dd8`

## callees

- `0x14000e0e0`
- `0x140076ad0`
- `0x14007cdb0`
- `0x140085570`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x1400f662c`
- `0x1400f7648`
- `0x1400f77f0`
- `0x1400f8184`
- `0x140118e60`
- `0x1401f3fc0`
- `0x14028debc`
- `0x14028ed0c`
- `0x1402b1d38`
- `0x1402c20f8`
- `0x1402de8dc`
- `0x1402eb144`
- `0x14032ab00`
- `0x140334b60`
- `0x1403366e0`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1402b1e78`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402b1e78`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402b20b6`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402b262a`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140347a0f`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402b20b6`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1402b262a`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140347a0f`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402b1f54`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402b20c2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402b1f54`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402b20c2`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402b2593`
- `ntoskrnl!FsRtlDismountComplete` at `0x14034792c`
- `ntoskrnl!FsRtlDismountComplete` at `0x1402b2593`
- `ntoskrnl!FsRtlDismountComplete` at `0x14034792c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402b1f48`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402b1f48`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b25f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403479aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b25f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403479aa`

## pseudocode

```c
__int64 __fastcall RefsDismountVolume(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  PIRP v2; // r14
  struct _FILE_OBJECT *FileObject; // rdi
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rax
  _QWORD *ActivityIdThread; // rax
  char v10; // si
  char v11; // bl
  struct _VCB *v12; // r13
  __int64 v13; // rdx
  ULONGLONG UnbiasedInterruptTime; // rbx
  __int64 v15; // r8
  const CHAR *v16; // rbx
  int v17; // r14d
  int v18; // edi
  char DeveloperVolumeState; // al
  int v20; // edx
  const CHAR *v21; // rsi
  ULONGLONG v22; // rdi
  unsigned __int64 v23; // r15
  __int64 v24; // rdx
  __int64 v25; // r8
  int v26; // esi
  int v27; // ebx
  char v28; // al
  int v29; // edx
  __int64 v30; // rax
  __int64 v31; // r15
  int v32; // edx
  unsigned int v33; // ebx
  __int64 v34; // rcx
  unsigned int v35; // r8d
  __int64 v36; // rcx
  unsigned int v37; // r9d
  void *v38; // rcx
  ULONGLONG v40; // [rsp+D0h] [rbp-108h] BYREF
  struct _VCB *v41; // [rsp+D8h] [rbp-100h] BYREF
  struct _FILE_OBJECT *v42; // [rsp+E0h] [rbp-F8h]
  const CHAR *v43; // [rsp+E8h] [rbp-F0h] BYREF
  PIRP v44; // [rsp+F0h] [rbp-E8h]
  __int64 v45; // [rsp+F8h] [rbp-E0h]
  struct _IRP_CONTEXT *v46; // [rsp+100h] [rbp-D8h]
  ULONGLONG v47; // [rsp+108h] [rbp-D0h]
  struct _FILE_OBJECT *v48; // [rsp+110h] [rbp-C8h] BYREF
  __int128 v49; // [rsp+118h] [rbp-C0h] BYREF
  __int64 v50; // [rsp+128h] [rbp-B0h]
  _BYTE v51[112]; // [rsp+130h] [rbp-A8h] BYREF

  v2 = Irp;
  v44 = Irp;
  v46 = a1;
  v41 = 0;
  v43 = 0;
  v40 = 0;
  v49 = 0;
  v50 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225473LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741823, 0, "FsCtrl.c", 0xF3Bu);
  *((_QWORD *)a1 + 1) &= ~8uLL;
  FileObject = v2->Tail.Overlay.CurrentStackLocation->FileObject;
  v42 = FileObject;
  RefsDecodeFileObject(a1, FileObject, &v41, &v48);
  if ( a1 )
  {
    v6 = (_QWORD *)*((_QWORD *)a1 + 10);
    if ( v6 )
    {
      *((_QWORD *)&v49 + 1) = *v6;
      v8 = v6[1];
LABEL_12:
      v50 = v8;
      *(_QWORD *)&v49 = (char *)&v49 + 8;
      goto LABEL_14;
    }
  }
  ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v6, v5);
  if ( ActivityIdThread )
  {
    *((_QWORD *)&v49 + 1) = *ActivityIdThread;
    v8 = ActivityIdThread[1];
    goto LABEL_12;
  }
  *(_QWORD *)&v49 = 0;
LABEL_14:
  if ( !v40 || !_bittest16((const signed __int16 *)(v40 + 88), 9u) )
  {
    v33 = -1073741790;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, v2, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790, 0, "FsCtrl.c", 0xF50u);
    return v33;
  }
  v48 = FileObject;
  v10 = 0;
  v11 = 1;
  v45 = 0;
  v12 = v41;
  if ( (*((_DWORD *)a1 + 2) & 0x40000LL) == 0 )
  {
    RefsSendBeginDismountEvent(a1, v41, v7, 0, &v43, &v40, 1);
    KeWaitForSingleObject((char *)v12 + 6128, Executive, 0, 0, 0);
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    v40 = UnbiasedInterruptTime;
    if ( (Microsoft_Windows_ReFSEnableBits & 0x400) != 0 )
    {
      v16 = &File;
      if ( *((_QWORD *)v12 + 1280) )
        v16 = (const CHAR *)*((_QWORD *)v12 + 1280);
      v17 = *((_DWORD *)v12 + 7);
      v18 = *((_DWORD *)v12 + 1572);
      DeveloperVolumeState = RefsGetDeveloperVolumeState(v12, v13, v15);
      v20 = v18 - 1;
      if ( (unsigned int)(v18 - 1) > 0x13 )
        LOBYTE(v18) = 0;
      McTemplateK0jmzuuhtqzzzzzqjqtjs_EtwWriteTransfer(
        0,
        v20,
        v49,
        (_DWORD)v12 + 6064,
        (__int64)v12 + 6704,
        *((_QWORD *)v12 + 770),
        *((_BYTE *)v12 + 792),
        *((_BYTE *)v12 + 793),
        *((_WORD *)v12 + 3364),
        (v17 & 0x1000) != 0,
        DeveloperVolumeState,
        *((_QWORD *)v12 + 103),
        *((_QWORD *)v12 + 788),
        *((_QWORD *)v12 + 790),
        *((_QWORD *)v12 + 792),
        *((_QWORD *)v12 + 794),
        v18,
        (__int64)v12 + 6376,
        *((_DWORD *)v12 + 1593),
        (v17 & 0x20000000) != 0,
        (__int64)v12 + 13080,
        (__int64)v16);
      UnbiasedInterruptTime = v40;
      FileObject = v42;
    }
    v21 = &File;
    FsRtlNotifyVolumeEvent(FileObject, 1u);
    v22 = KeQueryUnbiasedInterruptTime();
    v47 = v22;
    v23 = (v22 - UnbiasedInterruptTime) / 0xA / 0x3E8;
    IoPerfPrintTimeInterval(v23, 2, v51);
    if ( (Microsoft_Windows_ReFSEnableBits & 0x400) != 0 )
    {
      if ( *((_QWORD *)v12 + 1280) )
        v21 = (const CHAR *)*((_QWORD *)v12 + 1280);
      v43 = v21;
      v26 = *((_DWORD *)v12 + 7);
      v27 = *((_DWORD *)v12 + 1572);
      v28 = RefsGetDeveloperVolumeState(v12, v24, v25);
      v29 = v27 - 1;
      if ( (unsigned int)(v27 - 1) > 0x13 )
        LOBYTE(v27) = 0;
      McTemplateK0jmzuuhtqzzzzzqjqtjszx_EtwWriteTransfer(
        0,
        v29,
        v49,
        (_DWORD)v12 + 6064,
        (__int64)v12 + 6704,
        *((_QWORD *)v12 + 770),
        *((_BYTE *)v12 + 792),
        *((_BYTE *)v12 + 793),
        *((_WORD *)v12 + 3364),
        (v26 & 0x1000) != 0,
        v28,
        *((_QWORD *)v12 + 103),
        *((_QWORD *)v12 + 788),
        *((_QWORD *)v12 + 790),
        *((_QWORD *)v12 + 792),
        *((_QWORD *)v12 + 794),
        v27,
        (__int64)v12 + 6376,
        *((_DWORD *)v12 + 1593),
        (v26 & 0x20000000) != 0,
        (__int64)v12 + 13080,
        (__int64)v43,
        (__int64)v51,
        v23);
      UnbiasedInterruptTime = v40;
      v22 = v47;
    }
    v30 = *((_QWORD *)a1 + 89);
    v10 = 0;
    v2 = v44;
    if ( v30 )
    {
      *(_QWORD *)(v30 + 8) = UnbiasedInterruptTime;
      *(_QWORD *)(v30 + 16) = v22;
    }
    FileObject = v42;
    v11 = 1;
  }
  v31 = MEMORY[0xFFFFF78000000320];
  v45 = MEMORY[0xFFFFF78000000320];
  while ( 1 )
  {
    RefsAcquireExclusiveVcb(a1, v12, 1u);
    if ( *((_DWORD *)v12 + 58) )
    {
      if ( (*((_DWORD *)v12 + 6) & 2) != 0 )
      {
        if ( *((_DWORD *)v12 + 56) == *((_DWORD *)v12 + 55) + ~*((_DWORD *)v12 + 57) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 0);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(0, 0, "FsCtrl.c", 0xFBEu);
          goto LABEL_70;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v33 = -1073741790;
        }
        else
        {
          v33 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            57,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_81;
        v37 = 4038;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v33 = -1073741790;
        }
        else
        {
          v33 = -1073741790;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            55,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225506LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_81;
        v37 = 4021;
      }
      RefsStatusDebug(-1073741790, 0, "FsCtrl.c", v37);
      goto LABEL_81;
    }
    v10 = 1;
    v32 = *((_DWORD *)v12 + 6);
    if ( (v32 & 1) == 0 )
      break;
    if ( !v11 )
    {
      v34 = *((_QWORD *)a1 + 1);
      v35 = 0x40000;
      if ( (v34 & 0x40000) == 0 && (v32 & 0x2000000) == 0 )
      {
        *((_DWORD *)a1 + 166) = 8;
        *((_QWORD *)a1 + 1) = v34 | 0x40000;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            59,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225864LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741432, a1, "FsCtrl.c", 0x1000u);
        RefsRaiseStatusInternal(a1, -1073741432, v35);
        __debugbreak();
        JUMPOUT(0x1402B2760LL);
      }
      if ( RefsUseFlushVolumeParallel )
        RefsFlushVolumeParallel(a1, v12, 95);
      else
        RefsFlushVolumeOriginal(a1, v12, 95);
      v36 = *((_QWORD *)v12 + 14);
      if ( v36 )
        MsDrainLWQueue(v36);
      RefsPerformDismountOnVcb((CHAR *)a1, (unsigned __int64)v12, 0, 0, 0, 0);
      *((_DWORD *)v12 + 6) |= 2u;
      *((_QWORD *)v12 + 109) = (char *)&FileObject->Type + 1;
      RefsSetDirectWritesAllowed(*((struct _VPB **)v12 + 26));
      v33 = 0;
      goto LABEL_53;
    }
    RefsReleaseVcb(a1, v12);
    v11 = 0;
  }
  if ( (v32 & 0x800000) == 0 )
  {
LABEL_70:
    v33 = 0;
    goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221226094LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741202, 0, "FsCtrl.c", 0xFE0u);
  v33 = -1073741202;
LABEL_53:
  if ( v33 )
    goto LABEL_81;
LABEL_71:
  if ( v10 )
    *((_DWORD *)v12 + 6) |= 0x800000u;
LABEL_81:
  FsRtlDismountComplete(*((_QWORD *)v12 + 24), v33);
  RefsTelemetryDismountTimeTracker(v31, MEMORY[0xFFFFF78000000320], v12, v33);
  RefsReleaseVcb(a1, v12);
  if ( (int)(v33 + 0x80000000) >= 0 && v33 != -1073741202 )
  {
    if ( (*((_DWORD *)a1 + 2) & 0x40000) == 0 )
    {
      v38 = (void *)*((_QWORD *)a1 + 89);
      if ( v38 )
      {
        ExFreePoolWithTag(v38, 0);
        *((_QWORD *)a1 + 89) = 0;
      }
    }
    RefsSendDismountFailedEvent(a1, v12, (struct _REFS_ACTIVITY_ID *)&v49, v33);
    FsRtlNotifyVolumeEvent(FileObject, 2u);
  }
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, v2, v33);
  return v33;
}

```

## disassembly

```asm
0x1402b1d38  mov     r11, rsp
0x1402b1d3b  mov     [r11+18h], rbx
0x1402b1d3f  mov     [r11+20h], rsi
0x1402b1d43  push    rdi
0x1402b1d44  push    r12
0x1402b1d46  push    r13
0x1402b1d48  push    r14
0x1402b1d4a  push    r15
0x1402b1d4c  sub     rsp, 1B0h
0x1402b1d53  mov     rax, cs:__security_cookie
0x1402b1d5a  xor     rax, rsp
0x1402b1d5d  mov     [rsp+1D8h+var_38], rax
0x1402b1d65  mov     r14, rdx
0x1402b1d68  mov     [rsp+1D8h+var_E8], rdx
0x1402b1d70  mov     r12, rcx
0x1402b1d73  mov     [rsp+1D8h+var_D8], rcx
0x1402b1d7b  xor     r15d, r15d
0x1402b1d7e  mov     [r11-100h], r15
0x1402b1d85  mov     [r11-0F0h], r15
0x1402b1d8c  mov     [r11-108h], r15
0x1402b1d93  xorps   xmm0, xmm0
0x1402b1d96  xor     eax, eax
0x1402b1d98  movups  [rsp+1D8h+var_C0], xmm0
0x1402b1da0  mov     [r11-0B0h], rax
0x1402b1da7  lea     rsi, WPP_GLOBAL_Control
0x1402b1dae  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b1db5  cmp     rcx, rsi
0x1402b1db8  jz      short loc_1402B1DE2
0x1402b1dba  test    dword ptr [rcx+2Ch], 100h
0x1402b1dc1  jz      short loc_1402B1DE2
0x1402b1dc3  cmp     byte ptr [rcx+29h], 4
0x1402b1dc7  jb      short loc_1402B1DE2
0x1402b1dc9  lea     edx, [rax+35h]
0x1402b1dcc  mov     r9d, 0C0000001h
0x1402b1dd2  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b1dd9  mov     rcx, [rcx+18h]
0x1402b1ddd  call    WPP_SF_d
0x1402b1de2  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b1de8  test    al, al
0x1402b1dea  jz      short loc_1402B1E05
0x1402b1dec  mov     r9d, 0F3Bh; unsigned int
0x1402b1df2  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b1df9  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b1dfb  mov     ecx, 0C0000001h; Status
0x1402b1e00  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402b1e05  and     qword ptr [r12+8], 0FFFFFFFFFFFFFFF7h
0x1402b1e0b  mov     rax, [r14+0B8h]
0x1402b1e12  mov     rdi, [rax+30h]
0x1402b1e16  mov     [rsp+1D8h+var_F8], rdi
0x1402b1e1e  mov     [rsp+1D8h+var_1A8], 1
0x1402b1e23  lea     rax, [rsp+1D8h+var_108]
0x1402b1e2b  mov     [rsp+1D8h+var_1B0], rax
0x1402b1e30  lea     rax, [rsp+1D8h+var_F0]
0x1402b1e38  mov     [rsp+1D8h+Timeout], rax
0x1402b1e3d  lea     r9, [rsp+1D8h+var_C8]
0x1402b1e45  lea     r8, [rsp+1D8h+var_100]
0x1402b1e4d  mov     rdx, rdi
0x1402b1e50  mov     rcx, r12
0x1402b1e53  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402b1e58  test    r12, r12
0x1402b1e5b  jz      short loc_1402B1E78
0x1402b1e5d  mov     rcx, [r12+50h]
0x1402b1e62  test    rcx, rcx
0x1402b1e65  jz      short loc_1402B1E78
0x1402b1e67  mov     rax, [rcx]
0x1402b1e6a  mov     qword ptr [rsp+1D8h+var_C0+8], rax
0x1402b1e72  mov     rax, [rcx+8]
0x1402b1e76  jmp     short loc_1402B1E98
0x1402b1e78  call    cs:__imp_IoGetActivityIdThread
0x1402b1e7f  nop     dword ptr [rax+rax+00h]
0x1402b1e84  test    rax, rax
0x1402b1e87  jz      short loc_1402B1EB2
0x1402b1e89  mov     rcx, [rax]
0x1402b1e8c  mov     qword ptr [rsp+1D8h+var_C0+8], rcx
0x1402b1e94  mov     rax, [rax+8]
0x1402b1e98  mov     [rsp+1D8h+var_B0], rax
0x1402b1ea0  lea     rax, [rsp+1D8h+var_C0+8]
0x1402b1ea8  mov     qword ptr [rsp+1D8h+var_C0], rax
0x1402b1eb0  jmp     short loc_1402B1EBA
0x1402b1eb2  mov     qword ptr [rsp+1D8h+var_C0], r15
0x1402b1eba  mov     rax, [rsp+1D8h+var_108]
0x1402b1ec2  test    rax, rax
0x1402b1ec5  jz      loc_1402B2646
0x1402b1ecb  bt      word ptr [rax+58h], 9
0x1402b1ed1  jnb     loc_1402B2646
0x1402b1ed7  mov     [rsp+1D8h+var_C8], rdi
0x1402b1edf  mov     [rsp+1D8h+var_118], r15b
0x1402b1ee7  mov     sil, r15b
0x1402b1eea  mov     [rsp+1D8h+var_116], r15b
0x1402b1ef2  mov     bl, 1
0x1402b1ef4  mov     [rsp+1D8h+var_117], bl
0x1402b1efb  mov     [rsp+1D8h+var_E0], r15
0x1402b1f03  mov     [rsp+1D8h+var_114], 0C0000001h
0x1402b1f0e  mov     eax, [r12+8]
0x1402b1f13  mov     r13, [rsp+1D8h+var_100]
0x1402b1f1b  bt      rax, 12h
0x1402b1f20  jb      loc_1402B22B0
0x1402b1f26  xor     r9d, r9d
0x1402b1f29  mov     rdx, r13
0x1402b1f2c  mov     rcx, r12
0x1402b1f2f  call    ?RefsSendBeginDismountEvent@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_REFS_ACTIVITY_ID@@W4_REFS_DISMOUNT_REASON@@@Z; RefsSendBeginDismountEvent(_IRP_CONTEXT *,_VCB *,_REFS_ACTIVITY_ID *,_REFS_DISMOUNT_REASON)
0x1402b1f34  lea     rcx, [r13+17F0h]; Object
0x1402b1f3b  mov     [rsp+1D8h+Timeout], r15; Timeout
0x1402b1f40  xor     r9d, r9d; Alertable
0x1402b1f43  xor     r8d, r8d; WaitMode
0x1402b1f46  xor     edx, edx; WaitReason
0x1402b1f48  call    cs:__imp_KeWaitForSingleObject
0x1402b1f4f  nop     dword ptr [rax+rax+00h]
0x1402b1f54  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1402b1f5b  nop     dword ptr [rax+rax+00h]
0x1402b1f60  mov     rbx, rax
0x1402b1f63  mov     [rsp+1D8h+var_108], rax
0x1402b1f6b  test    byte ptr cs:Microsoft_Windows_ReFSEnableBits+1, 4
0x1402b1f72  jz      loc_1402B20A7
0x1402b1f78  lea     r15, [r13+1A30h]
0x1402b1f7f  mov     rcx, [r15+0DD0h]
0x1402b1f86  lea     rbx, File
0x1402b1f8d  test    rcx, rcx
0x1402b1f90  cmovnz  rbx, rcx
0x1402b1f94  mov     r14d, [r13+1Ch]
0x1402b1f98  mov     edi, [r13+1890h]
0x1402b1f9f  mov     rcx, r13
0x1402b1fa2  call    ?RefsGetDeveloperVolumeState@@YA?AW4REFS_DEV_VOL_STATE@@PEAU_VCB@@@Z; RefsGetDeveloperVolumeState(_VCB *)
0x1402b1fa7  mov     esi, eax
0x1402b1fa9  lea     r10, [r13+3318h]
0x1402b1fb0  mov     r11d, r14d
0x1402b1fb3  shr     r11d, 1Dh
0x1402b1fb7  and     r11d, 1
0x1402b1fbb  lea     r8, [r13+18E8h]
0x1402b1fc2  lea     edx, [rdi-1]
0x1402b1fc5  xor     ecx, ecx
0x1402b1fc7  cmp     edx, 13h
0x1402b1fca  cmova   edi, ecx
0x1402b1fcd  shr     r14d, 0Ch
0x1402b1fd1  and     r14d, 1
0x1402b1fd5  lea     r9, [r13+17B0h]
0x1402b1fdc  mov     [rsp+1D8h+var_130], rbx
0x1402b1fe4  mov     [rsp+1D8h+var_138], r10
0x1402b1fec  mov     [rsp+1D8h+var_140], r11d
0x1402b1ff4  mov     eax, [r13+18E4h]
0x1402b1ffb  mov     [rsp+1D8h+var_148], eax
0x1402b2002  mov     [rsp+1D8h+var_150], r8
0x1402b200a  mov     [rsp+1D8h+var_158], edi
0x1402b2011  mov     rax, [r13+18D0h]
0x1402b2018  mov     [rsp+1D8h+var_160], rax
0x1402b201d  mov     rax, [r13+18C0h]
0x1402b2024  mov     [rsp+1D8h+var_168], rax
0x1402b2029  mov     rax, [r13+18B0h]
0x1402b2030  mov     [rsp+1D8h+var_170], rax
0x1402b2035  mov     rax, [r13+18A0h]
0x1402b203c  mov     [rsp+1D8h+var_178], rax
0x1402b2041  mov     rax, [r13+338h]
0x1402b2048  mov     [rsp+1D8h+var_180], rax
0x1402b204d  mov     [rsp+1D8h+var_188], esi
0x1402b2051  mov     [rsp+1D8h+var_190], r14d
0x1402b2056  movzx   eax, word ptr [r13+1A48h]
0x1402b205e  mov     [rsp+1D8h+var_198], ax
0x1402b2063  mov     al, [r13+319h]
0x1402b206a  mov     [rsp+1D8h+var_1A0], al
0x1402b206e  mov     al, [r13+318h]
0x1402b2075  mov     [rsp+1D8h+var_1A8], al
0x1402b2079  mov     rax, [r13+1810h]
0x1402b2080  mov     [rsp+1D8h+var_1B0], rax
0x1402b2085  mov     [rsp+1D8h+Timeout], r15
0x1402b208a  mov     r8, qword ptr [rsp+1D8h+var_C0]
0x1402b2092  call    McTemplateK0jmzuuhtqzzzzzqjqtjs_EtwWriteTransfer
0x1402b2097  mov     rbx, [rsp+1D8h+var_108]
0x1402b209f  mov     rdi, [rsp+1D8h+var_F8]
0x1402b20a7  lea     rsi, File
0x1402b20ae  mov     edx, 1; EventCode
0x1402b20b3  mov     rcx, rdi; FileObject
0x1402b20b6  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1402b20bd  nop     dword ptr [rax+rax+00h]
0x1402b20c2  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1402b20c9  nop     dword ptr [rax+rax+00h]
0x1402b20ce  mov     rdi, rax
0x1402b20d1  mov     [rsp+1D8h+var_D0], rax
0x1402b20d9  mov     rcx, rax
0x1402b20dc  sub     rcx, rbx
0x1402b20df  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1402b20e9  mul     rcx
0x1402b20ec  mov     r15, rdx
0x1402b20ef  shr     r15, 3
0x1402b20f3  mov     rax, 624DD2F1A9FBE77h
0x1402b20fd  mul     r15
0x1402b2100  sub     r15, rdx
0x1402b2103  shr     r15, 1
0x1402b2106  add     r15, rdx
0x1402b2109  shr     r15, 9
0x1402b210d  lea     r8, [rsp+1D8h+var_A8]
0x1402b2115  mov     edx, 2
0x1402b211a  mov     rcx, r15
0x1402b211d  call    IoPerfPrintTimeInterval
0x1402b2122  test    byte ptr cs:Microsoft_Windows_ReFSEnableBits+1, 4
0x1402b2129  jz      loc_1402B227C
0x1402b212f  lea     r14, [r13+1A30h]
0x1402b2136  mov     rax, [r14+0DD0h]
0x1402b213d  test    rax, rax
0x1402b2140  cmovnz  rsi, rax
0x1402b2144  mov     [rsp+1D8h+var_F0], rsi
0x1402b214c  mov     esi, [r13+1Ch]
0x1402b2150  mov     ebx, [r13+1890h]
0x1402b2157  mov     rcx, r13
0x1402b215a  call    ?RefsGetDeveloperVolumeState@@YA?AW4REFS_DEV_VOL_STATE@@PEAU_VCB@@@Z; RefsGetDeveloperVolumeState(_VCB *)
0x1402b215f  mov     edi, eax
0x1402b2161  lea     r10, [r13+3318h]
0x1402b2168  mov     r11d, esi
0x1402b216b  shr     r11d, 1Dh
0x1402b216f  and     r11d, 1
0x1402b2173  lea     r8, [r13+18E8h]
0x1402b217a  lea     edx, [rbx-1]
0x1402b217d  xor     ecx, ecx
0x1402b217f  cmp     edx, 13h
0x1402b2182  cmova   ebx, ecx
0x1402b2185  shr     esi, 0Ch
0x1402b2188  and     esi, 1
0x1402b218b  lea     r9, [r13+17B0h]
0x1402b2192  mov     [rsp+1D8h+var_120], r15
0x1402b219a  lea     rax, [rsp+1D8h+var_A8]
0x1402b21a2  mov     [rsp+1D8h+var_128], rax
0x1402b21aa  mov     rax, [rsp+1D8h+var_F0]
0x1402b21b2  mov     [rsp+1D8h+var_130], rax
0x1402b21ba  mov     [rsp+1D8h+var_138], r10
0x1402b21c2  mov     [rsp+1D8h+var_140], r11d
0x1402b21ca  mov     eax, [r13+18E4h]
0x1402b21d1  mov     [rsp+1D8h+var_148], eax
0x1402b21d8  mov     [rsp+1D8h+var_150], r8
0x1402b21e0  mov     [rsp+1D8h+var_158], ebx
0x1402b21e7  mov     rax, [r13+18D0h]
0x1402b21ee  mov     [rsp+1D8h+var_160], rax
0x1402b21f3  mov     rax, [r13+18C0h]
0x1402b21fa  mov     [rsp+1D8h+var_168], rax
0x1402b21ff  mov     rax, [r13+18B0h]
0x1402b2206  mov     [rsp+1D8h+var_170], rax
0x1402b220b  mov     rax, [r13+18A0h]
0x1402b2212  mov     [rsp+1D8h+var_178], rax
0x1402b2217  mov     rax, [r13+338h]
0x1402b221e  mov     [rsp+1D8h+var_180], rax
0x1402b2223  mov     [rsp+1D8h+var_188], edi
0x1402b2227  mov     [rsp+1D8h+var_190], esi
0x1402b222b  movzx   eax, word ptr [r13+1A48h]
0x1402b2233  mov     [rsp+1D8h+var_198], ax
0x1402b2238  mov     al, [r13+319h]
0x1402b223f  mov     [rsp+1D8h+var_1A0], al
0x1402b2243  mov     al, [r13+318h]
0x1402b224a  mov     [rsp+1D8h+var_1A8], al
0x1402b224e  mov     rax, [r13+1810h]
0x1402b2255  mov     [rsp+1D8h+var_1B0], rax
0x1402b225a  mov     [rsp+1D8h+Timeout], r14
0x1402b225f  mov     r8, qword ptr [rsp+1D8h+var_C0]
0x1402b2267  call    McTemplateK0jmzuuhtqzzzzzqjqtjszx_EtwWriteTransfer
0x1402b226c  mov     rbx, [rsp+1D8h+var_108]
0x1402b2274  mov     rdi, [rsp+1D8h+var_D0]
0x1402b227c  mov     rax, [r12+2C8h]
0x1402b2284  mov     sil, [rsp+1D8h+var_116]
0x1402b228c  mov     r14, [rsp+1D8h+var_E8]
0x1402b2294  test    rax, rax
0x1402b2297  jz      short loc_1402B22A1
0x1402b2299  mov     [rax+8], rbx
0x1402b229d  mov     [rax+10h], rdi
0x1402b22a1  mov     rdi, [rsp+1D8h+var_F8]
0x1402b22a9  mov     bl, [rsp+1D8h+var_117]
0x1402b22b0  mov     rax, 0FFFFF78000000320h
0x1402b22ba  mov     r15, [rax]
0x1402b22bd  mov     [rsp+1D8h+var_E0], r15
0x1402b22c5  mov     r8b, 1; unsigned __int8
0x1402b22c8  mov     rdx, r13; struct _VCB *
0x1402b22cb  mov     rcx, r12; struct _IRP_CONTEXT *
0x1402b22ce  call    ?RefsAcquireExclusiveVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireExclusiveVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x1402b22d3  mov     [rsp+1D8h+var_118], 1
0x1402b22db  cmp     dword ptr [r13+0E8h], 0
0x1402b22e3  jnz     loc_1402B242D
0x1402b22e9  mov     sil, 1
0x1402b22ec  mov     [rsp+1D8h+var_110], sil
0x1402b22f4  mov     edx, [r13+18h]
0x1402b22f8  test    sil, dl
0x1402b22fb  jnz     short loc_1402B2371
0x1402b22fd  bt      edx, 17h
0x1402b2301  jnb     loc_1402B2507
0x1402b2307  mov     rcx, cs:WPP_GLOBAL_Control
0x1402b230e  lea     rax, WPP_GLOBAL_Control
0x1402b2315  cmp     rcx, rax
0x1402b2318  jz      short loc_1402B2344
0x1402b231a  test    dword ptr [rcx+2Ch], 100h
0x1402b2321  jz      short loc_1402B2344
0x1402b2323  cmp     byte ptr [rcx+29h], 4
0x1402b2327  jb      short loc_1402B2344
0x1402b2329  mov     edx, 3Ah ; ':'
0x1402b232e  mov     r9d, 0C000026Eh
0x1402b2334  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402b233b  mov     rcx, [rcx+18h]
0x1402b233f  call    WPP_SF_d
0x1402b2344  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402b234a  test    al, al
0x1402b234c  jz      short loc_1402B2367
0x1402b234e  mov     r9d, 0FE0h; unsigned int
0x1402b2354  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402b235b  xor     edx, edx; struct _IRP_CONTEXT *
0x1402b235d  mov     ecx, 0C000026Eh; Status
0x1402b2362  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
  ... truncated ...
```
