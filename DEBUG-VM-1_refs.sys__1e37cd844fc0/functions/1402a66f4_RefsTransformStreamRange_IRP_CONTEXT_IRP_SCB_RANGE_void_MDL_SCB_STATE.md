# RefsTransformStreamRange(_IRP_CONTEXT *,_IRP *,_SCB *,_RANGE,void *,_MDL *,SCB_STATE)

- ea: `0x1402a66f4`
- end: `0x1402a7117`
- name: `?RefsTransformStreamRange@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SCB@@U_RANGE@@PEAXPEAU_MDL@@W4SCB_STATE@@@Z`
- size: `2595`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, loader_planting`

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
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        void *a5,
        struct _MDL *a6,
        int a7)
{
  unsigned __int64 v11; // r14
  CmsStream *v12; // rdx
  struct CmsTransactionContext *v13; // rcx
  int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // r14
  unsigned __int8 v17; // r8
  int v18; // r9d
  int v19; // r9d
  struct CmsTransactionContext *v20; // rdx
  CmsStream *v21; // rcx
  int Checksum; // eax
  unsigned int v23; // r8d
  NTSTATUS v24; // r14d
  __int64 *v25; // [rsp+28h] [rbp-520h]
  int v26; // [rsp+38h] [rbp-510h]
  int v27; // [rsp+40h] [rbp-508h]
  __int64 v28; // [rsp+88h] [rbp-4C0h] BYREF
  PMDL SourceMdl; // [rsp+90h] [rbp-4B8h]
  unsigned __int64 v30; // [rsp+98h] [rbp-4B0h]
  __int64 v31; // [rsp+A0h] [rbp-4A8h]
  __int64 v32; // [rsp+A8h] [rbp-4A0h]
  __int64 v33; // [rsp+B0h] [rbp-498h]
  __int64 v34; // [rsp+B8h] [rbp-490h]
  __int64 v35; // [rsp+D0h] [rbp-478h]
  __int64 v36; // [rsp+E8h] [rbp-460h]
  __int64 v37; // [rsp+F0h] [rbp-458h]
  __int64 v38; // [rsp+F8h] [rbp-450h]
  struct _IRP_CONTEXT *v39; // [rsp+100h] [rbp-448h]
  __int128 v40; // [rsp+140h] [rbp-408h]
  __int128 v41; // [rsp+160h] [rbp-3E8h]
  _OWORD v42[3]; // [rsp+170h] [rbp-3D8h] BYREF
  _DWORD v43[32]; // [rsp+1A0h] [rbp-3A8h] BYREF
  __int64 v44; // [rsp+220h] [rbp-328h]
  __int64 v45; // [rsp+228h] [rbp-320h]
  __int128 v46; // [rsp+230h] [rbp-318h]
  _DWORD v47[176]; // [rsp+240h] [rbp-308h] BYREF

  v39 = a1;
  v37 = a2;
  SourceMdl = a6;
  v28 = 0;
  v36 = *(_QWORD *)(a2 + 8);
  v38 = v36;
  v34 = 0;
  memset(v43, 0, sizeof(v43));
  v44 = 0;
  v45 = 0;
  v46 = 0;
  memset(v47, 0, sizeof(v47));
  RefsInitializeIoContext(a1, (struct REFS_IO_CONTEXT *)v43, a3, 0);
  while ( a4[1] )
  {
    v42[0] = *(_OWORD *)a4;
    v25 = &v28;
    if ( (unsigned __int8)RefsLookupAllocation(a1, a3, v42, 1) || BYTE1(v28) )
    {
      v11 = *a4;
      v30 = *a4;
      if ( !(_BYTE)v28 )
      {
        v40 = v11;
        v12 = *(CmsStream **)(a3 + 432);
        v13 = (struct CmsTransactionContext *)*((_QWORD *)a1 + 3);
        v42[1] = v11;
        v14 = MsSetRangeEncryptedState(v13, v12);
        v11 = (unsigned int)v14;
        if ( v14 >= 0 )
          goto LABEL_38;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            102,
            &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            (unsigned int)v14);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v11, a1, "Efssup.c", 0x1554u);
        RefsRaiseStatusInternal(a1, v11, v15);
      }
      v16 = v11 << *(_BYTE *)(*(_QWORD *)(a3 + 144) + 552LL);
      if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
        IoClearFsTrackOffsetState(a2);
      *(_QWORD *)(a2 + 8) = SourceMdl;
      LOBYTE(v27) = 0;
      LOBYTE(v26) = 3;
      LODWORD(v25) = 0;
      RefsSingleAsync(a1, v43, *(_QWORD *)(*(_QWORD *)(a3 + 144) + 192LL), v16, 0, v25, a2, v26, v27, a3, 0);
      RefsWaitOnIo((struct REFS_IO_CONTEXT *)v43);
      *(_QWORD *)(a2 + 56) = 0;
      RefsNormalizeAndCleanupTransaction(a1, (int *)(a2 + 48), v17, v18);
      if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
        IoClearFsTrackOffsetState(a2);
      if ( _bittest16((const signed __int16 *)(a3 + 256), 0xEu) && *(_QWORD *)(a3 + 288) && *(int *)(a3 + 152) >= 0 )
      {
        if ( (a7 & 0x4000000) != 0 )
          RefsDecryptBuffer((struct _SCB *)a3, v16, 0, a5);
        else
          RefsEncryptBuffer((struct _SCB *)a3, v16, 0, a5, a5);
      }
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v35 = 0;
      v30 = 0;
      if ( *(_WORD *)a3 != 2053 || !*(_QWORD *)(a3 + 432) || (v19 = 32, !*(_WORD *)(a3 + 260)) )
        v19 = 0;
      if ( *(__int16 *)(a3 + 256) < 0 )
        v19 |= 2u;
      v41 = *a4;
      v20 = (struct CmsTransactionContext *)*((_QWORD *)a1 + 3);
      v21 = *(CmsStream **)(a3 + 432);
      v42[2] = v41;
      Checksum = MsPersistReserveAllocationAndGenerateChecksum(v21, v20, v19, 0, a5, 0);
      v24 = Checksum;
      if ( Checksum < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            (unsigned int)Checksum);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v24, a1, "Efssup.c", 0x166Au);
        RefsRaiseStatusInternal(a1, v24, v23);
      }
    }
LABEL_38:
    *a4 = *a4;
    a4[1] = a4[1];
  }
  if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
    IoClearFsTrackOffsetState(a2);
  *(_QWORD *)(a2 + 8) = v36;
  RefsCleanupIoContext(a1, (struct REFS_IO_CONTEXT *)v43, *(_DWORD *)(a2 + 48));
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
