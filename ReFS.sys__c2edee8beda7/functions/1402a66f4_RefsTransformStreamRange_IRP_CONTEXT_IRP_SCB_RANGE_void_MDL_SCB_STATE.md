# RefsTransformStreamRange(_IRP_CONTEXT *,_IRP *,_SCB *,_RANGE,void *,_MDL *,SCB_STATE)

- ea: `0x1402a66f4`
- end: `0x1402a7117`
- name: `?RefsTransformStreamRange@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SCB@@U_RANGE@@PEAXPEAU_MDL@@W4SCB_STATE@@@Z`
- size: `2595`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1402a2e00`

## callees

- `0x140011c60`
- `0x140018860`
- `0x1400199c0`
- `0x140075ff0`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400892a0`
- `0x1400961f0`
- `0x1400a73b4`
- `0x1400aa590`
- `0x1400d0fd8`
- `0x1400d4d08`
- `0x1400f4c8c`
- `0x14011b024`
- `0x1401f3fc0`
- `0x1401f4400`
- `0x1402a66f4`
- `0x14032fac0`
- `0x140330b20`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1402a6e2e`
- `ntoskrnl!IoBuildPartialMdl` at `0x1402a6e2e`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402a6df2`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402a6df2`
- `ntoskrnl!IoAllocateMdl` at `0x1402a6d58`
- `ntoskrnl!IoAllocateMdl` at `0x1402a6d58`
- `ntoskrnl!IoFreeMdl` at `0x1402a70a5`
- `ntoskrnl!IoFreeMdl` at `0x140347155`
- `ntoskrnl!IoFreeMdl` at `0x1402a70a5`
- `ntoskrnl!IoFreeMdl` at `0x140347155`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a69a3`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a6ae9`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a6ee0`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a70b4`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14034716c`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a69a3`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a6ae9`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a6ee0`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a70b4`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14034716c`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a69b9`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a6afe`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a6ef3`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a70c7`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14034717f`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a69b9`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a6afe`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a6ef3`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a70c7`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14034717f`

## pseudocode

```c
void __fastcall RefsTransformStreamRange(
        struct _IRP_CONTEXT *a1,
        struct _IRP *a2,
        __int64 a3,
        __int64 *a4,
        char *a5,
        struct _MDL *a6,
        int a7)
{
  PMDL Mdl; // r15
  __int64 v12; // r14
  CmsStream *v13; // rdx
  struct CmsTransactionContext *v14; // rcx
  int v15; // eax
  unsigned int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // r14
  unsigned int v19; // r12d
  unsigned __int8 v20; // r8
  int v21; // r9d
  __int64 v22; // r12
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r10
  __int64 v26; // r11
  __int64 v27; // r8
  __int64 v28; // r14
  int v29; // r9d
  __int16 v30; // ax
  __int16 v31; // ax
  int v32; // eax
  unsigned int v33; // r8d
  NTSTATUS v34; // r14d
  __int64 v35; // r14
  unsigned int v36; // r8d
  __int64 v37; // r10
  unsigned __int8 v38; // r8
  int v39; // r9d
  int v40; // r9d
  unsigned int v41; // r8d
  struct CmsTransactionContext *v42; // rdx
  CmsStream *v43; // rcx
  int Checksum; // eax
  unsigned int v45; // r8d
  NTSTATUS v46; // r14d
  __int64 v47; // rax
  __int64 v48; // [rsp+28h] [rbp-520h]
  __int64 v49; // [rsp+28h] [rbp-520h]
  int v50; // [rsp+38h] [rbp-510h]
  int v51; // [rsp+38h] [rbp-510h]
  int v52; // [rsp+40h] [rbp-508h]
  int v53; // [rsp+60h] [rbp-4E8h]
  __int64 v54; // [rsp+70h] [rbp-4D8h]
  __int64 v55; // [rsp+78h] [rbp-4D0h] BYREF
  __int64 v56; // [rsp+80h] [rbp-4C8h]
  __int64 v57; // [rsp+88h] [rbp-4C0h] BYREF
  PMDL SourceMdl; // [rsp+90h] [rbp-4B8h]
  __int64 v59; // [rsp+98h] [rbp-4B0h]
  __int64 v60; // [rsp+A0h] [rbp-4A8h]
  __int64 v61; // [rsp+A8h] [rbp-4A0h]
  __int64 v62; // [rsp+B0h] [rbp-498h]
  PMDL v63; // [rsp+B8h] [rbp-490h]
  __int64 v64; // [rsp+C0h] [rbp-488h] BYREF
  __int64 v65; // [rsp+C8h] [rbp-480h]
  __int64 v66; // [rsp+D0h] [rbp-478h]
  __int64 v67; // [rsp+D8h] [rbp-470h]
  __int64 v68; // [rsp+E0h] [rbp-468h] BYREF
  struct _MDL *MdlAddress; // [rsp+E8h] [rbp-460h]
  struct _IRP *v70; // [rsp+F0h] [rbp-458h]
  struct _MDL *v71; // [rsp+F8h] [rbp-450h]
  struct _IRP_CONTEXT *v72; // [rsp+100h] [rbp-448h]
  __int128 Context; // [rsp+108h] [rbp-440h] BYREF
  __int128 v74; // [rsp+118h] [rbp-430h]
  __int128 v75; // [rsp+128h] [rbp-420h]
  __int64 v76; // [rsp+138h] [rbp-410h]
  __int128 v77; // [rsp+140h] [rbp-408h]
  _QWORD v78[2]; // [rsp+150h] [rbp-3F8h] BYREF
  __int128 v79; // [rsp+160h] [rbp-3E8h]
  _OWORD v80[3]; // [rsp+170h] [rbp-3D8h] BYREF
  _DWORD v81[32]; // [rsp+1A0h] [rbp-3A8h] BYREF
  __int64 v82; // [rsp+220h] [rbp-328h]
  __int64 v83; // [rsp+228h] [rbp-320h]
  __int128 v84; // [rsp+230h] [rbp-318h]
  _DWORD v85[176]; // [rsp+240h] [rbp-308h] BYREF

  v72 = a1;
  v70 = a2;
  SourceMdl = a6;
  v57 = 0;
  v55 = 0;
  v56 = 0;
  MdlAddress = a2->MdlAddress;
  v71 = MdlAddress;
  Mdl = 0;
  v63 = 0;
  memset(v81, 0, sizeof(v81));
  v82 = 0;
  v83 = 0;
  v84 = 0;
  memset(v85, 0, sizeof(v85));
  RefsInitializeIoContext(a1, (struct REFS_IO_CONTEXT *)v81, a3, 0);
  while ( a4[1] )
  {
    v80[0] = *(_OWORD *)a4;
    if ( !(unsigned __int8)RefsLookupAllocation(a1, a3, v80, 1, &v55, &v57, 0) && !BYTE1(v57) )
      goto LABEL_76;
    v12 = *a4;
    v59 = *a4;
    if ( !(_BYTE)v57 )
    {
      *(_QWORD *)&v77 = v12;
      *((_QWORD *)&v77 + 1) = v56;
      v13 = *(CmsStream **)(a3 + 432);
      v14 = (struct CmsTransactionContext *)*((_QWORD *)a1 + 3);
      v80[1] = v77;
      v15 = MsSetRangeEncryptedState(v14, v13);
      v12 = (unsigned int)v15;
      if ( v15 >= 0 )
        goto LABEL_76;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          102,
          WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
          (unsigned int)v15);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v12, a1, "Efssup.c", 0x1554u);
      RefsRaiseStatusInternal(a1, v12, v16);
    }
    v17 = *(_QWORD *)(a3 + 144);
    v18 = v12 << *(_BYTE *)(v17 + 552);
    v19 = (_DWORD)v56 << *(_DWORD *)(v17 + 552);
    if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
      IoClearFsTrackOffsetState(a2);
    a2->MdlAddress = SourceMdl;
    if ( v55 >= 0 )
    {
      LOBYTE(v52) = 0;
      LOBYTE(v50) = 3;
      LODWORD(v48) = v19;
      RefsSingleAsync(
        a1,
        v81,
        *(_QWORD *)(*(_QWORD *)(a3 + 144) + 192LL),
        v18,
        v55 << *(_BYTE *)(*(_QWORD *)(a3 + 144) + 552LL),
        v48,
        a2,
        v50,
        v52,
        a3,
        0);
    }
    else
    {
      Context = 0;
      v74 = 0;
      v75 = 0;
      v76 = 0;
      *(_QWORD *)&Context = *((_QWORD *)a1 + 3);
      *(_QWORD *)&v74 = a2;
      DWORD2(v74) = v19;
      *(_QWORD *)&v75 = v55 << *(_BYTE *)(*(_QWORD *)(a3 + 144) + 552LL);
      *((_QWORD *)&v75 + 1) = v18;
      *((_QWORD *)&Context + 1) = a3;
      RefsPreProcessIo(a1, (struct REFS_IO_CONTEXT *)v81, a2, 0);
      RefsDecompressWorker(0, (unsigned int *)&Context, 0);
    }
    RefsWaitOnIo((struct REFS_IO_CONTEXT *)v81);
    a2->IoStatus.Information = 0;
    RefsNormalizeAndCleanupTransaction(a1, (int *)&a2->IoStatus.0, v20, v21);
    if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
      IoClearFsTrackOffsetState(a2);
    if ( _bittest16((const signed __int16 *)(a3 + 256), 0xEu) && *(_QWORD *)(a3 + 288) && *(int *)(a3 + 152) >= 0 )
    {
      if ( (a7 & 0x4000000) != 0 )
        RefsDecryptBuffer((struct _SCB *)a3, v18, v19, a5);
      else
        RefsEncryptBuffer((struct _SCB *)a3, v18, v19, a5, a5);
    }
    v22 = v59;
    v23 = v56;
    v60 = v56;
    v54 = v56;
    v53 = 0;
    v24 = v56;
    v25 = v56;
    v61 = v56;
    v26 = v56;
    v62 = v56;
    v27 = v56;
    v66 = v56;
    v28 = v56;
    v59 = v56;
    while ( v24 )
    {
      v64 = 0;
      v65 = 0;
      v68 = 0;
      v29 = (a7 & 0x2000000) != 0 ? 4194320 : 16;
      if ( (a7 & 0x2000000) == 0 )
      {
        v25 = v61;
        v26 = v62;
        v27 = v66;
        v28 = v59;
      }
      v30 = *(_WORD *)(a3 + 256);
      if ( v30 >= 0 )
      {
        v25 = v26;
        v27 = v28;
      }
      v31 = (unsigned __int16)v30 >> 15;
      if ( (_BYTE)v31 )
        v29 |= 2u;
      v78[0] = v22;
      if ( !(_BYTE)v31 )
        v27 = v25;
      v78[1] = v27;
      v32 = MsPrepareVRangeForWrite(
              *((_QWORD *)a1 + 3),
              *(_QWORD *)(a3 + 432),
              (unsigned int)v78,
              v29,
              (__int64)&v64,
              (__int64)&v68,
              0,
              0);
      v34 = v32;
      if ( v32 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            103,
            WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            (unsigned int)v32);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v34, a1, "Efssup.c", 0x15EFu);
        RefsRaiseStatusInternal(a1, v34, v33);
      }
      if ( !v53 )
      {
        a2->MdlAddress = SourceMdl;
        v35 = v65;
        goto LABEL_59;
      }
      if ( Mdl )
        goto LABEL_56;
      Mdl = IoAllocateMdl(a5, *((_DWORD *)a4 + 2) << *(_DWORD *)(*(_QWORD *)(a3 + 144) + 552LL), 0, 0, 0);
      v63 = Mdl;
      if ( !Mdl )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            104,
            WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741670, a1, "Efssup.c", 0x1612u);
        RefsRaiseStatusInternal(a1, -1073741670, v36);
LABEL_56:
        if ( (Mdl->MdlFlags & 0x20) != 0 )
          MmUnmapLockedPages(Mdl->MappedSystemVa, Mdl);
      }
      v35 = v65;
      IoBuildPartialMdl(SourceMdl, Mdl, &a5[v53], (_DWORD)v65 << *(_DWORD *)(*(_QWORD *)(a3 + 144) + 552LL));
      a2->MdlAddress = Mdl;
LABEL_59:
      v37 = *(_QWORD *)(a3 + 144);
      LOBYTE(v52) = 0;
      LOBYTE(v51) = 4;
      LODWORD(v49) = (_DWORD)v35 << *(_DWORD *)(v37 + 552);
      RefsSingleAsync(
        a1,
        v81,
        *(_QWORD *)(v37 + 192),
        v22 << *(_BYTE *)(v37 + 552),
        v64 << *(_BYTE *)(v37 + 552),
        v49,
        a2,
        v51,
        v52,
        a3,
        (*(_DWORD *)(a3 + 152) & 0x2000000) != 0 ? 8 : 4);
      RefsWaitOnIo((struct REFS_IO_CONTEXT *)v81);
      a2->IoStatus.Information = 0;
      RefsNormalizeAndCleanupTransaction(a1, (int *)&a2->IoStatus.0, v38, v39);
      if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
        IoClearFsTrackOffsetState(a2);
      v53 += (_DWORD)v35 << *(_DWORD *)(*(_QWORD *)(a3 + 144) + 552LL);
      v22 += v35;
      v54 -= v35;
      v67 = v54;
      v24 = v54;
      v25 = v54;
      v61 = v54;
      v26 = v54;
      v62 = v54;
      v27 = v54;
      v66 = v54;
      v28 = v54;
      v59 = v54;
      v23 = v56;
    }
    if ( *(_WORD *)a3 != 2053 || !*(_QWORD *)(a3 + 432) || (v40 = 32, !*(_WORD *)(a3 + 260)) )
      v40 = 0;
    if ( *(__int16 *)(a3 + 256) < 0 )
      v40 |= 2u;
    v41 = (_DWORD)v23 << *(_DWORD *)(*(_QWORD *)(a3 + 144) + 552LL);
    *(_QWORD *)&v79 = *a4;
    *((_QWORD *)&v79 + 1) = v23;
    v42 = (struct CmsTransactionContext *)*((_QWORD *)a1 + 3);
    v43 = *(CmsStream **)(a3 + 432);
    v80[2] = v79;
    Checksum = MsPersistReserveAllocationAndGenerateChecksum(v43, v42, v40, 0, a5, v41);
    v46 = Checksum;
    if ( Checksum < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          105,
          WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
          (unsigned int)Checksum);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v46, a1, "Efssup.c", 0x166Au);
      RefsRaiseStatusInternal(a1, v46, v45);
    }
LABEL_76:
    v47 = v56;
    *a4 += v56;
    a4[1] -= v47;
  }
  if ( Mdl )
    IoFreeMdl(Mdl);
  if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
    IoClearFsTrackOffsetState(a2);
  a2->MdlAddress = MdlAddress;
  RefsCleanupIoContext(a1, (struct REFS_IO_CONTEXT *)v81, a2->IoStatus.Status);
}

```

## disassembly

```asm
0x1402a66f4  mov     r11, rsp
0x1402a66f7  push    rbx
0x1402a66f8  push    rsi
0x1402a66f9  push    rdi
0x1402a66fa  push    r12
0x1402a66fc  push    r13
0x1402a66fe  push    r14
0x1402a6700  push    r15
0x1402a6702  sub     rsp, 510h
0x1402a6709  mov     rax, cs:__security_cookie
0x1402a6710  xor     rax, rsp
0x1402a6713  mov     [rsp+548h+var_48], rax
0x1402a671b  mov     r13, r9
0x1402a671e  mov     rdi, r8
0x1402a6721  mov     rsi, rdx
0x1402a6724  mov     rbx, rcx
0x1402a6727  mov     [rsp+548h+var_448], rcx
0x1402a672f  mov     [rsp+548h+var_458], rdx
0x1402a6737  mov     rax, [rsp+548h+arg_20]
0x1402a673f  mov     [rsp+548h+VirtualAddress], rax
0x1402a6744  mov     rax, [rsp+548h+arg_28]
0x1402a674c  mov     [rsp+548h+SourceMdl], rax
0x1402a6754  xor     r12d, r12d
0x1402a6757  mov     [r11-4C0h], r12
0x1402a675e  mov     [rsp+548h+var_4D0], r12
0x1402a6763  mov     [r11-4C8h], r12
0x1402a676a  mov     r14, [rdx+8]
0x1402a676e  mov     [rsp+548h+var_460], r14
0x1402a6776  mov     [rsp+548h+var_450], r14
0x1402a677e  mov     r15d, r12d
0x1402a6781  mov     [r11-490h], r12
0x1402a6788  xor     eax, eax
0x1402a678a  mov     [rsp+548h+var_3A4], eax
0x1402a6791  mov     [rsp+548h+var_36F], eax
0x1402a6798  mov     [rsp+548h+var_36B], ax
0x1402a67a0  mov     [rsp+548h+var_369], al
0x1402a67a7  lea     r14d, [r12+40h]
0x1402a67ac  mov     r8d, r14d; Size
0x1402a67af  xor     edx, edx; Val
0x1402a67b1  lea     rcx, [r11-3A8h]; void *
0x1402a67b8  call    memset
0x1402a67bd  xor     eax, eax
0x1402a67bf  mov     [rsp+548h+var_34C], eax
0x1402a67c6  mov     [rsp+548h+var_33C], eax
0x1402a67cd  mov     r8d, r14d; Size
0x1402a67d0  xor     edx, edx; Val
0x1402a67d2  lea     rcx, [rsp+548h+var_368]; void *
0x1402a67da  call    memset
0x1402a67df  mov     [rsp+548h+var_328], r12
0x1402a67e7  mov     [rsp+548h+var_320], r12
0x1402a67ef  xorps   xmm0, xmm0
0x1402a67f2  movups  [rsp+548h+var_318], xmm0
0x1402a67fa  xor     edx, edx; Val
0x1402a67fc  mov     r8d, 1C0h; Size
0x1402a6802  lea     rcx, [rsp+548h+var_308]; void *
0x1402a680a  call    memset
0x1402a680f  xor     eax, eax
0x1402a6811  mov     [rsp+548h+var_144], eax
0x1402a6818  xor     edx, edx; Val
0x1402a681a  mov     r8d, 100h; Size
0x1402a6820  lea     rcx, [rsp+548h+var_148]; void *
0x1402a6828  call    memset
0x1402a682d  xor     r9d, r9d; bool
0x1402a6830  lea     rdx, [rsp+548h+var_3A8]; struct REFS_IO_CONTEXT *
0x1402a6838  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1402a683b  call    ?RefsInitializeIoContext@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@_N2@Z; RefsInitializeIoContext(_IRP_CONTEXT *,REFS_IO_CONTEXT *,bool,bool)
0x1402a6840  nop
0x1402a6841  cmp     [r13+8], r12
0x1402a6845  jz      loc_1402A709D
0x1402a684b  movaps  xmm0, xmmword ptr [r13+0]
0x1402a6850  movdqa  [rsp+548h+var_3D8], xmm0
0x1402a6859  mov     dword ptr [rsp+548h+var_518], r12d
0x1402a685e  lea     rax, [rsp+548h+var_4C0]
0x1402a6866  mov     [rsp+548h+var_520], rax
0x1402a686b  lea     rax, [rsp+548h+var_4D0]
0x1402a6870  mov     [rsp+548h+Irp], rax
0x1402a6875  mov     r9d, 1
0x1402a687b  lea     r8, [rsp+548h+var_3D8]
0x1402a6883  mov     rdx, rdi
0x1402a6886  mov     rcx, rbx
0x1402a6889  call    ?RefsLookupAllocation@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@U_RANGE@@W4RefsLookupAllocationFlags@@PEAU3@PEAU_MS_STREAM_RUN_PROPERTIES@@K@Z; RefsLookupAllocation(_IRP_CONTEXT *,_SCB *,_RANGE,RefsLookupAllocationFlags,_RANGE *,_MS_STREAM_RUN_PROPERTIES *,ulong)
0x1402a688e  test    al, al
0x1402a6890  jnz     short loc_1402A68A0
0x1402a6892  cmp     [rsp+548h+var_4BF], r12b
0x1402a689a  jz      loc_1402A7088
0x1402a68a0  mov     r14, [r13+0]
0x1402a68a4  mov     [rsp+548h+var_4B0], r14
0x1402a68ac  cmp     [rsp+548h+var_4C0], r12b
0x1402a68b4  jnz     loc_1402A697F
0x1402a68ba  mov     eax, [rsp+548h+arg_30]
0x1402a68c1  and     eax, 2000000h
0x1402a68c6  setnz   r9b
0x1402a68ca  mov     qword ptr [rsp+548h+var_408], r14
0x1402a68d2  mov     rax, [rsp+548h+var_4C8]
0x1402a68da  mov     qword ptr [rsp+548h+var_408+8], rax
0x1402a68e2  mov     rdx, [rdi+1B0h]
0x1402a68e9  mov     rcx, [rbx+18h]
0x1402a68ed  movaps  xmm0, [rsp+548h+var_408]
0x1402a68f5  movdqa  [rsp+548h+var_3C8], xmm0
0x1402a68fe  lea     r8, [rsp+548h+var_3C8]
0x1402a6906  call    MsSetRangeEncryptedState
0x1402a690b  mov     r14d, eax
0x1402a690e  test    eax, eax
0x1402a6910  jns     loc_1402A7088
0x1402a6916  lea     rdx, WPP_GLOBAL_Control
0x1402a691d  mov     r10, cs:WPP_GLOBAL_Control
0x1402a6924  cmp     r10, rdx
0x1402a6927  jz      short loc_1402A6952
0x1402a6929  test    dword ptr [r10+2Ch], 100h
0x1402a6931  jz      short loc_1402A6952
0x1402a6933  cmp     byte ptr [r10+29h], 4
0x1402a6938  jb      short loc_1402A6952
0x1402a693a  mov     edx, 66h ; 'f'
0x1402a693f  mov     r9d, eax
0x1402a6942  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x1402a6949  mov     rcx, [r10+18h]
0x1402a694d  call    WPP_SF_d
0x1402a6952  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a6958  test    al, al
0x1402a695a  jz      short loc_1402A6974
0x1402a695c  mov     r9d, 1554h; unsigned int
0x1402a6962  lea     r8, aEfssupC; "Efssup.c"
0x1402a6969  mov     rdx, rbx; struct _IRP_CONTEXT *
0x1402a696c  mov     ecx, r14d; Status
0x1402a696f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a6974  mov     edx, r14d; int
0x1402a6977  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1402a697a  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1402a697f  mov     rax, [rdi+90h]
0x1402a6986  mov     cl, [rax+228h]
0x1402a698c  shl     r14, cl
0x1402a698f  mov     ecx, [rax+228h]
0x1402a6995  mov     r12, [rsp+548h+var_4C8]
0x1402a699d  shl     r12d, cl
0x1402a69a0  mov     rcx, rsi
0x1402a69a3  call    cs:__imp_IoIrpHasFsTrackOffsetExtensionType
0x1402a69aa  nop     dword ptr [rax+rax+00h]
0x1402a69af  xor     r9d, r9d
0x1402a69b2  test    al, al
0x1402a69b4  jz      short loc_1402A69C8
0x1402a69b6  mov     rcx, rsi
0x1402a69b9  call    cs:__imp_IoClearFsTrackOffsetState
0x1402a69c0  nop     dword ptr [rax+rax+00h]
0x1402a69c5  xor     r9d, r9d
0x1402a69c8  mov     rax, [rsp+548h+SourceMdl]
0x1402a69d0  mov     [rsi+8], rax
0x1402a69d4  mov     rdx, [rsp+548h+var_4D0]
0x1402a69d9  bt      rdx, 3Fh ; '?'
0x1402a69de  jnb     loc_1402A6A77
0x1402a69e4  xorps   xmm0, xmm0
0x1402a69e7  xor     eax, eax
0x1402a69e9  movups  [rsp+548h+Context], xmm0
0x1402a69f1  movups  [rsp+548h+var_430], xmm0
0x1402a69f9  movups  [rsp+548h+var_420], xmm0
0x1402a6a01  mov     [rsp+548h+var_410], rax
0x1402a6a09  mov     rax, [rbx+18h]
0x1402a6a0d  mov     qword ptr [rsp+548h+Context], rax
0x1402a6a15  mov     qword ptr [rsp+548h+var_430], rsi
0x1402a6a1d  mov     dword ptr [rsp+548h+var_430+8], r12d
0x1402a6a25  mov     rcx, [rdi+90h]
0x1402a6a2c  mov     cl, [rcx+228h]
0x1402a6a32  shl     rdx, cl
0x1402a6a35  mov     qword ptr [rsp+548h+var_420], rdx
0x1402a6a3d  mov     qword ptr [rsp+548h+var_420+8], r14
0x1402a6a45  mov     qword ptr [rsp+548h+Context+8], rdi
0x1402a6a4d  xor     r9d, r9d; unsigned int
0x1402a6a50  mov     r8, rsi; struct _IRP *
0x1402a6a53  lea     rdx, [rsp+548h+var_3A8]; struct REFS_IO_CONTEXT *
0x1402a6a5b  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1402a6a5e  call    ?RefsPreProcessIo@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@K@Z; RefsPreProcessIo(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,ulong)
0x1402a6a63  xor     r8d, r8d; IoWorkItem
0x1402a6a66  lea     rdx, [rsp+548h+Context]; Context
0x1402a6a6e  xor     ecx, ecx; IoObject
0x1402a6a70  call    ?RefsDecompressWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; RefsDecompressWorker(void *,void *,_IO_WORKITEM *)
0x1402a6a75  jmp     short loc_1402A6AC5
0x1402a6a77  mov     r8, [rdi+90h]
0x1402a6a7e  mov     cl, [r8+228h]
0x1402a6a85  shl     rdx, cl
0x1402a6a88  mov     [rsp+548h+var_4F8], r9d
0x1402a6a8d  mov     [rsp+548h+var_500], rdi
0x1402a6a92  mov     [rsp+548h+var_508], r9b
0x1402a6a97  mov     byte ptr [rsp+548h+var_510], 3
0x1402a6a9c  mov     [rsp+548h+var_518], rsi
0x1402a6aa1  mov     dword ptr [rsp+548h+var_520], r12d
0x1402a6aa6  mov     [rsp+548h+Irp], rdx
0x1402a6aab  mov     r9, r14
0x1402a6aae  mov     r8, [r8+0C0h]
0x1402a6ab5  lea     rdx, [rsp+548h+var_3A8]
0x1402a6abd  mov     rcx, rbx
0x1402a6ac0  call    ?RefsSingleAsync@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_DEVICE_OBJECT@@_J3KPEAU_IRP@@EEPEAU_SCB@@W4RefsIoStreamFlags@@@Z; RefsSingleAsync(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_DEVICE_OBJECT *,__int64,__int64,ulong,_IRP *,uchar,uchar,_SCB *,RefsIoStreamFlags)
0x1402a6ac5  lea     rcx, [rsp+548h+var_3A8]; struct REFS_IO_CONTEXT *
0x1402a6acd  call    ?RefsWaitOnIo@@YAXPEAUREFS_IO_CONTEXT@@@Z; RefsWaitOnIo(REFS_IO_CONTEXT *)
0x1402a6ad2  lea     rdx, [rsi+30h]; int *
0x1402a6ad6  mov     qword ptr [rsi+38h], 0
0x1402a6ade  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1402a6ae1  call    ?RefsNormalizeAndCleanupTransaction@@YAXPEAU_IRP_CONTEXT@@PEAJEJ@Z; RefsNormalizeAndCleanupTransaction(_IRP_CONTEXT *,long *,uchar,long)
0x1402a6ae6  mov     rcx, rsi
0x1402a6ae9  call    cs:__imp_IoIrpHasFsTrackOffsetExtensionType
0x1402a6af0  nop     dword ptr [rax+rax+00h]
0x1402a6af5  xor     edx, edx
0x1402a6af7  test    al, al
0x1402a6af9  jz      short loc_1402A6B0C
0x1402a6afb  mov     rcx, rsi
0x1402a6afe  call    cs:__imp_IoClearFsTrackOffsetState
0x1402a6b05  nop     dword ptr [rax+rax+00h]
0x1402a6b0a  xor     edx, edx
0x1402a6b0c  bt      word ptr [rdi+100h], 0Eh
0x1402a6b15  jnb     short loc_1402A6B5D
0x1402a6b17  cmp     [rdi+120h], rdx
0x1402a6b1e  jz      short loc_1402A6B5D
0x1402a6b20  cmp     [rdi+98h], edx
0x1402a6b26  jl      short loc_1402A6B5D
0x1402a6b28  mov     eax, [rsp+548h+arg_30]
0x1402a6b2f  and     eax, 4000000h
0x1402a6b34  mov     r8d, r12d; unsigned int
0x1402a6b37  mov     rdx, r14; __int64
0x1402a6b3a  mov     rcx, rdi; struct _SCB *
0x1402a6b3d  jz      short loc_1402A6B4B
0x1402a6b3f  mov     r9, [rsp+548h+VirtualAddress]; void *
0x1402a6b44  call    ?RefsDecryptBuffer@@YAXPEAU_SCB@@_JKPEAX@Z; RefsDecryptBuffer(_SCB *,__int64,ulong,void *)
0x1402a6b49  jmp     short loc_1402A6B5D
0x1402a6b4b  mov     rax, [rsp+548h+VirtualAddress]
0x1402a6b50  mov     [rsp+548h+Irp], rax; void *
0x1402a6b55  mov     r9, rax; void *
0x1402a6b58  call    ?RefsEncryptBuffer@@YAXPEAU_SCB@@_JKPEAX2@Z; RefsEncryptBuffer(_SCB *,__int64,ulong,void *,void *)
0x1402a6b5d  mov     r12, [rsp+548h+var_4B0]
0x1402a6b65  mov     [rsp+548h+var_4B0], r12
0x1402a6b6d  mov     rdx, [rsp+548h+var_4C8]
0x1402a6b75  mov     [rsp+548h+var_4A8], rdx
0x1402a6b7d  mov     [rsp+548h+var_4D8], rdx
0x1402a6b82  mov     [rsp+548h+var_4E8], 0
0x1402a6b8a  mov     rax, rdx
0x1402a6b8d  mov     r10, rdx
0x1402a6b90  mov     [rsp+548h+var_4A0], rdx
0x1402a6b98  mov     r11, rdx
0x1402a6b9b  mov     [rsp+548h+var_498], rdx
0x1402a6ba3  mov     r8, rdx
0x1402a6ba6  mov     [rsp+548h+var_478], rdx
0x1402a6bae  mov     r14, rdx
0x1402a6bb1  mov     [rsp+548h+var_4B0], rdx
0x1402a6bb9  test    rax, rax
0x1402a6bbc  jz      loc_1402A6F71
0x1402a6bc2  xor     edx, edx
0x1402a6bc4  mov     [rsp+548h+var_488], rdx
0x1402a6bcc  mov     [rsp+548h+var_480], rdx
0x1402a6bd4  mov     [rsp+548h+var_468], rdx
0x1402a6bdc  mov     ecx, [rsp+548h+arg_30]
0x1402a6be3  and     ecx, 2000000h
0x1402a6be9  mov     eax, ecx
0x1402a6beb  neg     eax
0x1402a6bed  sbb     r9d, r9d
0x1402a6bf0  and     r9d, 400000h
0x1402a6bf7  add     r9d, 10h
0x1402a6bfb  mov     [rsp+548h+var_4E4], r9d
0x1402a6c00  test    ecx, ecx
0x1402a6c02  cmovz   r10, [rsp+548h+var_4A0]
0x1402a6c0b  cmovz   r11, [rsp+548h+var_498]
0x1402a6c14  cmovz   r8, [rsp+548h+var_478]
0x1402a6c1d  cmovz   r14, [rsp+548h+var_4B0]
0x1402a6c26  movzx   eax, word ptr [rdi+100h]
0x1402a6c2d  test    ax, ax
0x1402a6c30  js      short loc_1402A6C38
0x1402a6c32  mov     r10, r11
0x1402a6c35  mov     r8, r14
0x1402a6c38  shr     ax, 0Fh
0x1402a6c3c  test    al, al
0x1402a6c3e  jz      short loc_1402A6C49
0x1402a6c40  or      r9d, 2
0x1402a6c44  mov     [rsp+548h+var_4E4], r9d
0x1402a6c49  mov     [rsp+548h+var_3F8], r12
0x1402a6c51  test    al, al
0x1402a6c53  cmovz   r8, r10
0x1402a6c57  mov     [rsp+548h+var_3F0], r8
0x1402a6c5f  mov     qword ptr [rsp+548h+var_510], rdx
0x1402a6c64  mov     [rsp+548h+var_518], rdx
0x1402a6c69  lea     rax, [rsp+548h+var_468]
0x1402a6c71  mov     [rsp+548h+var_520], rax
0x1402a6c76  lea     rax, [rsp+548h+var_488]
0x1402a6c7e  mov     [rsp+548h+Irp], rax
0x1402a6c83  lea     r8, [rsp+548h+var_3F8]
0x1402a6c8b  mov     rdx, [rdi+1B0h]
0x1402a6c92  mov     rcx, [rbx+18h]
0x1402a6c96  call    MsPrepareVRangeForWrite
0x1402a6c9b  mov     r14d, eax
0x1402a6c9e  test    eax, eax
0x1402a6ca0  jns     short loc_1402A6D09
0x1402a6ca2  lea     rdx, WPP_GLOBAL_Control
0x1402a6ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a6cb0  cmp     rcx, rdx
0x1402a6cb3  jz      short loc_1402A6CDC
0x1402a6cb5  test    dword ptr [rcx+2Ch], 100h
0x1402a6cbc  jz      short loc_1402A6CDC
0x1402a6cbe  cmp     byte ptr [rcx+29h], 4
0x1402a6cc2  jb      short loc_1402A6CDC
0x1402a6cc4  mov     edx, 67h ; 'g'
0x1402a6cc9  mov     r9d, eax
0x1402a6ccc  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x1402a6cd3  mov     rcx, [rcx+18h]
0x1402a6cd7  call    WPP_SF_d
0x1402a6cdc  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
  ... truncated ...
```
