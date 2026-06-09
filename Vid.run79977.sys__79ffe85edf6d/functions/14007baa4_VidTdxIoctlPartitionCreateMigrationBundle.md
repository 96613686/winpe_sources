# VidTdxIoctlPartitionCreateMigrationBundle

- ea: `0x14007baa4`
- end: `0x14007c147`
- name: `VidTdxIoctlPartitionCreateMigrationBundle`
- size: `1699`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021e00`
- `0x140024850`
- `0x1400248b8`
- `0x140024e18`
- `0x140030990`
- `0x1400309d0`
- `0x14007b02c`
- `0x14007baa4`
- `0x1400f1ea0`

## import_xrefs

- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14007bd61`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14007bd61`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007bdce`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007bdce`
- `ntoskrnl!ExAllocatePool2` at `0x14007bcba`
- `ntoskrnl!ExAllocatePool2` at `0x14007bcba`
- `winhvr!WinHvCreateTdMigrationBundle` at `0x14007be03`
- `winhvr!WinHvCreateTdMigrationBundle` at `0x14007be03`

## string_xrefs

- `0x14007bb2e`: `VidTdxIoctlPartitionCreateMigrationBundle`

## pseudocode

```c
__int64 __fastcall VidTdxIoctlPartitionCreateMigrationBundle(
        __int64 a1,
        unsigned int a2,
        unsigned __int8 a3,
        __int64 *a4)
{
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 *v9; // r14
  unsigned int v10; // edx
  __int64 *v11; // rcx
  int TdMigrationBundle; // edi
  _QWORD *Pool2; // rax
  _QWORD *v14; // rsi
  _QWORD *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdi
  struct _MDL *NodePagesForMdl; // rax
  int v19; // r8d
  PVOID v20; // rax
  int v21; // r8d
  _OWORD *v22; // rcx
  __int64 v23; // rdx
  _OWORD *v24; // rax
  __int128 v25; // xmm1
  unsigned int v26; // edx
  __int64 *v27; // rcx
  unsigned int v28; // edx
  __int64 *v29; // rcx
  char v31; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v32; // [rsp+41h] [rbp-BFh] BYREF
  unsigned __int8 v33; // [rsp+42h] [rbp-BEh]
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v38; // [rsp+68h] [rbp-98h]
  _QWORD v39[10]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v40[34]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v42[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v43; // [rsp+200h] [rbp+100h] BYREF
  __int64 v44; // [rsp+208h] [rbp+108h]
  __int64 *v45; // [rsp+210h] [rbp+110h]
  __int64 v46; // [rsp+218h] [rbp+118h]
  __int64 *v47; // [rsp+220h] [rbp+120h]
  __int64 v48; // [rsp+228h] [rbp+128h] BYREF
  __int64 *v49; // [rsp+230h] [rbp+130h]
  __int64 v50; // [rsp+238h] [rbp+138h] BYREF
  __int64 *v51; // [rsp+240h] [rbp+140h]
  __int64 v52; // [rsp+248h] [rbp+148h]
  __int64 *v53; // [rsp+250h] [rbp+150h]
  __int64 v54; // [rsp+258h] [rbp+158h]

  v33 = a3;
  LODWORD(v34) = a2;
  v38 = a4;
  memset(v40, 0, sizeof(v40));
  memset(v39, 0, sizeof(v39));
  v31 = 0;
  v7 = -1;
  VidTraceActivityInitialize(v39);
  v8 = a1 + 120;
  v9 = (__int64 *)(a1 + 648);
  v35 = a1 + 120;
  v39[7] = *(_QWORD *)(a1 + 648);
  v39[0] = "VidTdxIoctlPartitionCreateMigrationBundle";
  v39[6] = a1 + 656;
  v39[8] = a1 + 120;
  if ( (unsigned int)dword_140065110 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v42, v39[0]);
      v43 = v39[6];
      v44 = 16;
      v10 = *(unsigned __int16 *)v39[8];
      v11 = *(__int64 **)(v39[8] + 8LL);
      v45 = &v48;
      v37 = v39[7];
      v49 = &v37;
      v51 = (__int64 *)&v36;
      v53 = (__int64 *)&v32;
      v47 = v11;
      v48 = v10;
      v46 = 2;
      v50 = 8;
      v36 = a2;
      v52 = 4;
      v32 = a3;
      v54 = 1;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140046089, &v39[4], &v39[2], 9, v41);
    }
    v8 = a1 + 120;
  }
  LOBYTE(v39[9]) = 1;
  if ( a2 > 1 )
  {
    v14 = 0;
    TdMigrationBundle = -1073741811;
    v21 = 256;
    goto LABEL_23;
  }
  if ( a3 < *(_BYTE *)(a1 + 2040) )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 384, 1917084758);
    v14 = Pool2;
    if ( !Pool2 )
    {
      TdMigrationBundle = -1073741670;
      VidTracePartitionErrorInternal0(
        (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
        276,
        a1 + 656,
        v35,
        *v9,
        -1073741670);
      goto LABEL_28;
    }
    *Pool2 = 0;
    v15 = Pool2 + 35;
    memset(Pool2 + 35, 0, 0x48u);
    v15[6] = v15 + 5;
    v15[5] = v15 + 5;
    v16 = v33;
    v14[1] = -1;
    v17 = (unsigned int)v16;
    v14[46] = 0;
    *((_BYTE *)v14 + 376) = v16;
    NodePagesForMdl = (struct _MDL *)MmAllocateNodePagesForMdlEx(
                                       0,
                                       -1,
                                       0,
                                       4096,
                                       1,
                                       *(unsigned __int8 *)(v16 + a1 + 2041),
                                       20);
    v14[45] = NodePagesForMdl;
    if ( !NodePagesForMdl )
    {
      v19 = 313;
LABEL_13:
      TdMigrationBundle = -1073741670;
      VidTracePartitionErrorInternal0(
        (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
        v19,
        a1 + 656,
        a1 + 120,
        *v9,
        -1073741670);
      goto LABEL_25;
    }
    v20 = MmMapLockedPagesSpecifyCache(NodePagesForMdl, 0, MmCached, 0, 0, 0x40000010u);
    v14[44] = v20;
    if ( !v20 )
    {
      v19 = 328;
      goto LABEL_13;
    }
    TdMigrationBundle = WinHvCreateTdMigrationBundle(*v9, *(unsigned __int8 *)(v17 + a1 + 2041), (unsigned int)v34, v40);
    if ( TdMigrationBundle >= 0 )
    {
      v7 = v40[0];
      v22 = v14 + 2;
      v23 = 2;
      v14[1] = v40[0];
      v24 = &v40[1];
      do
      {
        *v22 = *v24;
        v22[1] = v24[1];
        v22[2] = v24[2];
        v22[3] = v24[3];
        v22[4] = v24[4];
        v22[5] = v24[5];
        v22[6] = v24[6];
        v25 = v24[7];
        v24 += 8;
        v22[7] = v25;
        v22 += 8;
        --v23;
      }
      while ( v23 );
      *(_QWORD *)v22 = *(_QWORD *)v24;
      VidLockAcquireExclusive(a1 + 12760);
      TdMigrationBundle = VidHandleTableAllocateEntry(a1 + 12728, v14, v38);
      if ( TdMigrationBundle >= 0 )
      {
LABEL_27:
        VidLockRelease(a1 + 12760);
        goto LABEL_28;
      }
      v31 = 1;
      v21 = 358;
    }
    else
    {
      v21 = 340;
    }
LABEL_23:
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
      v21,
      a1 + 656,
      a1 + 120,
      *v9,
      TdMigrationBundle);
    if ( !v14 )
    {
LABEL_26:
      if ( !v31 )
        goto LABEL_28;
      goto LABEL_27;
    }
LABEL_25:
    VidTdxMigrationBundleTeardown(a1, v14);
    goto LABEL_26;
  }
  TdMigrationBundle = -1073741811;
  VidTracePartitionErrorInternal0(
    (unsigned int)"VidTdxIoctlPartitionCreateMigrationBundle",
    (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdxioctl.c",
    263,
    a1 + 656,
    v8,
    *v9,
    -1073741811);
LABEL_28:
  if ( LOBYTE(v39[9]) )
  {
    if ( TdMigrationBundle < 0 )
    {
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        v42[0] = &v34;
        LODWORD(v34) = TdMigrationBundle;
        v42[1] = 4;
        tlgCreate1Sz_char(&v43, v39[0]);
        v45 = (__int64 *)v39[6];
        v46 = 16;
        v28 = *(unsigned __int16 *)v39[8];
        v29 = *(__int64 **)(v39[8] + 8LL);
        v47 = &v50;
        v35 = v39[7];
        v51 = &v35;
        v49 = v29;
        v50 = v28;
        v48 = 2;
        v52 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140045F9B, &v39[4], 0, 8, v41);
      }
    }
    else if ( (unsigned int)dword_140065110 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v42, v39[0]);
      v43 = v39[6];
      v44 = 16;
      v26 = *(unsigned __int16 *)v39[8];
      v27 = *(__int64 **)(v39[8] + 8LL);
      v45 = &v48;
      v35 = v39[7];
      v49 = &v35;
      v48 = v26;
      v46 = 2;
      v47 = v27;
      v37 = *v38;
      v51 = &v37;
      v53 = &v34;
      v50 = 8;
      v52 = 8;
      v34 = v7;
      v54 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140046002, &v39[4], 0, 9, v41);
    }
    VidTraceActivityTeardown(v39);
  }
  return (unsigned int)TdMigrationBundle;
}

```

## disassembly

```asm
0x14007baa4  push    rbp
0x14007baa6  push    rbx
0x14007baa7  push    rsi
0x14007baa8  push    rdi
0x14007baa9  push    r12
0x14007baab  push    r13
0x14007baad  push    r14
0x14007baaf  push    r15
0x14007bab1  lea     rbp, [rsp-178h]
0x14007bab9  sub     rsp, 278h
0x14007bac0  mov     rax, cs:__security_cookie
0x14007bac7  xor     rax, rsp
0x14007baca  mov     [rbp+1B0h+var_50], rax
0x14007bad1  mov     dil, r8b
0x14007bad4  mov     [rsp+2B0h+var_26E], r8b
0x14007bad9  mov     esi, edx
0x14007badb  mov     dword ptr [rsp+2B0h+var_268], edx
0x14007badf  mov     r13, rcx
0x14007bae2  mov     [rsp+2B0h+var_248], r9
0x14007bae7  xor     edx, edx; Val
0x14007bae9  lea     rcx, [rbp+1B0h+var_1F0]; void *
0x14007baed  mov     r8d, 110h; Size
0x14007baf3  call    memset
0x14007baf8  xor     edx, edx; Val
0x14007bafa  lea     rcx, [rsp+2B0h+var_240]; void *
0x14007baff  lea     r8d, [rdx+50h]; Size
0x14007bb03  call    memset
0x14007bb08  lea     rcx, [rsp+2B0h+var_240]
0x14007bb0d  mov     [rsp+2B0h+var_270], 0
0x14007bb12  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14007bb16  call    VidTraceActivityInitialize
0x14007bb1b  lea     rcx, [r13+78h]
0x14007bb1f  lea     r14, [r13+288h]
0x14007bb26  mov     [rsp+2B0h+var_260], rcx
0x14007bb2b  mov     rax, [r14]
0x14007bb2e  lea     r15, aVidtdxioctlpar_22
0x14007bb35  mov     [rbp+1B0h+var_208], rax
0x14007bb39  lea     r12, [r13+290h]
0x14007bb40  mov     eax, cs:dword_140065110
0x14007bb46  mov     [rsp+2B0h+var_240], r15
0x14007bb4b  mov     [rbp+1B0h+var_210], r12
0x14007bb4f  mov     [rbp+1B0h+var_200], rcx
0x14007bb53  cmp     eax, 5
0x14007bb56  jbe     loc_14007BC61
0x14007bb5c  mov     edx, 100h
0x14007bb61  lea     rcx, dword_140065110
0x14007bb68  call    _tlgKeywordOn
0x14007bb6d  test    al, al
0x14007bb6f  jz      loc_14007BC5D
0x14007bb75  mov     rdx, [rsp+2B0h+var_240]
0x14007bb7a  lea     rcx, [rbp+1B0h+var_C0]
0x14007bb81  call    _tlgCreate1Sz_char
0x14007bb86  mov     rax, [rbp+1B0h+var_200]
0x14007bb8a  lea     r9, [rbp+1B0h+var_230]
0x14007bb8e  mov     rcx, [rbp+1B0h+var_210]
0x14007bb92  lea     r8, [rbp+1B0h+var_220]
0x14007bb96  mov     [rbp+1B0h+var_B0], rcx
0x14007bb9d  mov     [rbp+1B0h+var_A8], 10h
0x14007bba8  movzx   edx, word ptr [rax]
0x14007bbab  mov     rcx, [rax+8]
0x14007bbaf  lea     rax, [rbp+1B0h+var_88]
0x14007bbb6  mov     [rbp+1B0h+var_A0], rax
0x14007bbbd  mov     rax, [rbp+1B0h+var_208]
0x14007bbc1  mov     [rsp+2B0h+var_250], rax
0x14007bbc6  lea     rax, [rsp+2B0h+var_250]
0x14007bbcb  mov     [rbp+1B0h+var_80], rax
0x14007bbd2  lea     rax, [rsp+2B0h+var_258]
0x14007bbd7  mov     [rbp+1B0h+var_70], rax
0x14007bbde  lea     rax, [rsp+2B0h+var_26F]
0x14007bbe3  mov     [rbp+1B0h+var_60], rax
0x14007bbea  lea     rax, [rbp+1B0h+var_E0]
0x14007bbf1  mov     [rbp+1B0h+var_90], rcx
0x14007bbf8  lea     rcx, dword_140065110
0x14007bbff  mov     dword ptr [rbp+1B0h+var_88], edx
0x14007bc05  lea     rdx, unk_140046089
0x14007bc0c  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007bc11  mov     [rsp+2B0h+BugCheckOnFailure], 9
0x14007bc19  mov     [rbp+1B0h+var_98], 2
0x14007bc24  mov     dword ptr [rbp+1B0h+var_88+4], 0
0x14007bc2e  mov     [rbp+1B0h+var_78], 8
0x14007bc39  mov     [rsp+2B0h+var_258], esi
0x14007bc3d  mov     [rbp+1B0h+var_68], 4
0x14007bc48  mov     [rsp+2B0h+var_26F], dil
0x14007bc4d  mov     [rbp+1B0h+var_58], 1
0x14007bc58  call    _tlgWriteTransfer_EtwWriteTransfer
0x14007bc5d  lea     rcx, [r13+78h]
0x14007bc61  mov     [rbp+1B0h+var_1F8], 1
0x14007bc65  cmp     esi, 1
0x14007bc68  ja      loc_14007BEBC
0x14007bc6e  cmp     dil, [r13+7F8h]
0x14007bc75  jb      short loc_14007BCAA
0x14007bc77  mov     edi, 0C000000Dh
0x14007bc7c  mov     rax, [r14]
0x14007bc7f  mov     r8d, 107h
0x14007bc85  mov     [rsp+2B0h+var_280], edi
0x14007bc89  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007bc8e  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rcx
0x14007bc93  mov     r9, r12
0x14007bc96  lea     rdx, aOnecoreVmVidSy_21
0x14007bc9d  mov     rcx, r15
0x14007bca0  call    VidTracePartitionErrorInternal0
0x14007bca5  jmp     loc_14007BF17
0x14007bcaa  mov     edx, 180h
0x14007bcaf  mov     ecx, 40h ; '@'
0x14007bcb4  mov     r8d, 72446456h
0x14007bcba  call    cs:__imp_ExAllocatePool2
0x14007bcc1  nop     dword ptr [rax+rax+00h]
0x14007bcc6  mov     rsi, rax
0x14007bcc9  test    rax, rax
0x14007bccc  jnz     short loc_14007BCF3
0x14007bcce  mov     eax, 0C000009Ah
0x14007bcd3  mov     edi, eax
0x14007bcd5  mov     [rsp+2B0h+var_280], eax
0x14007bcd9  mov     r8d, 114h
0x14007bcdf  mov     rax, [r14]
0x14007bce2  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007bce7  mov     rax, [rsp+2B0h+var_260]
0x14007bcec  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rax
0x14007bcf1  jmp     short loc_14007BC93
0x14007bcf3  xor     edx, edx; Val
0x14007bcf5  mov     qword ptr [rax], 0
0x14007bcfc  lea     rdi, [rax+118h]
0x14007bd03  mov     rcx, rdi; void *
0x14007bd06  lea     r8d, [rdx+48h]; Size
0x14007bd0a  call    memset
0x14007bd0f  lea     rax, [rdi+28h]
0x14007bd13  mov     [rsp+2B0h+var_280], 14h
0x14007bd1b  mov     [rax+8], rax
0x14007bd1f  xor     ecx, ecx
0x14007bd21  mov     [rax], rax
0x14007bd24  xor     r8d, r8d
0x14007bd27  movzx   eax, [rsp+2B0h+var_26E]
0x14007bd2c  mov     r9d, 1000h
0x14007bd32  mov     [rsi+8], rbx
0x14007bd36  mov     edi, eax
0x14007bd38  mov     qword ptr [rsi+170h], 0
0x14007bd43  mov     rdx, rbx
0x14007bd46  mov     [rsi+178h], al
0x14007bd4c  movzx   eax, byte ptr [rax+r13+7F9h]
0x14007bd55  mov     [rsp+2B0h+Priority], eax
0x14007bd59  mov     [rsp+2B0h+BugCheckOnFailure], 1
0x14007bd61  call    cs:__imp_MmAllocateNodePagesForMdlEx
0x14007bd68  nop     dword ptr [rax+rax+00h]
0x14007bd6d  mov     [rsi+168h], rax
0x14007bd74  test    rax, rax
0x14007bd77  jnz     short loc_14007BDB2
0x14007bd79  mov     r8d, 139h
0x14007bd7f  mov     eax, 0C000009Ah
0x14007bd84  mov     edi, eax
0x14007bd86  mov     [rsp+2B0h+var_280], eax
0x14007bd8a  lea     rdx, aOnecoreVmVidSy_21
0x14007bd91  mov     rax, [r14]
0x14007bd94  mov     r9, r12
0x14007bd97  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007bd9c  mov     rcx, r15
0x14007bd9f  lea     rax, [r13+78h]
0x14007bda3  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rax
0x14007bda8  call    VidTracePartitionErrorInternal0
0x14007bdad  jmp     loc_14007BEF9
0x14007bdb2  xor     r9d, r9d; RequestedAddress
0x14007bdb5  mov     [rsp+2B0h+Priority], 40000010h; Priority
0x14007bdbd  xor     edx, edx; AccessMode
0x14007bdbf  mov     [rsp+2B0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14007bdc7  mov     rcx, rax; MemoryDescriptorList
0x14007bdca  lea     r8d, [r9+1]; CacheType
0x14007bdce  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007bdd5  nop     dword ptr [rax+rax+00h]
0x14007bdda  mov     [rsi+160h], rax
0x14007bde1  test    rax, rax
0x14007bde4  jnz     short loc_14007BDEE
0x14007bde6  mov     r8d, 148h
0x14007bdec  jmp     short loc_14007BD7F
0x14007bdee  movzx   edx, byte ptr [rdi+r13+7F9h]
0x14007bdf7  lea     r9, [rbp+1B0h+var_1F0]
0x14007bdfb  mov     r8d, dword ptr [rsp+2B0h+var_268]
0x14007be00  mov     rcx, [r14]
0x14007be03  call    cs:__imp_WinHvCreateTdMigrationBundle
0x14007be0a  nop     dword ptr [rax+rax+00h]
0x14007be0f  mov     edi, eax
0x14007be11  test    eax, eax
0x14007be13  jns     short loc_14007BE20
0x14007be15  mov     r8d, 154h
0x14007be1b  jmp     loc_14007BEC9
0x14007be20  mov     rbx, [rbp+1B0h+var_1F0]
0x14007be24  lea     rcx, [rsi+10h]
0x14007be28  mov     edx, 2
0x14007be2d  mov     [rsi+8], rbx
0x14007be31  lea     rax, [rbp+1B0h+var_1E8]
0x14007be35  lea     r8d, [rdx+7Eh]
0x14007be39  movups  xmm0, xmmword ptr [rax]
0x14007be3c  movups  xmmword ptr [rcx], xmm0
0x14007be3f  movups  xmm1, xmmword ptr [rax+10h]
0x14007be43  movups  xmmword ptr [rcx+10h], xmm1
0x14007be47  movups  xmm0, xmmword ptr [rax+20h]
0x14007be4b  movups  xmmword ptr [rcx+20h], xmm0
0x14007be4f  movups  xmm1, xmmword ptr [rax+30h]
0x14007be53  movups  xmmword ptr [rcx+30h], xmm1
0x14007be57  movups  xmm0, xmmword ptr [rax+40h]
0x14007be5b  movups  xmmword ptr [rcx+40h], xmm0
0x14007be5f  movups  xmm1, xmmword ptr [rax+50h]
0x14007be63  movups  xmmword ptr [rcx+50h], xmm1
0x14007be67  movups  xmm0, xmmword ptr [rax+60h]
0x14007be6b  movups  xmmword ptr [rcx+60h], xmm0
0x14007be6f  movups  xmm1, xmmword ptr [rax+70h]
0x14007be73  add     rax, r8
0x14007be76  movups  xmmword ptr [rcx+70h], xmm1
0x14007be7a  add     rcx, r8
0x14007be7d  sub     rdx, 1
0x14007be81  jnz     short loc_14007BE39
0x14007be83  mov     rax, [rax]
0x14007be86  mov     [rcx], rax
0x14007be89  lea     rcx, [r13+31D8h]
0x14007be90  call    VidLockAcquireExclusive
0x14007be95  mov     r8, [rsp+2B0h+var_248]
0x14007be9a  lea     rcx, [r13+31B8h]
0x14007bea1  mov     rdx, rsi
0x14007bea4  call    VidHandleTableAllocateEntry
0x14007bea9  mov     edi, eax
0x14007beab  test    eax, eax
0x14007bead  jns     short loc_14007BF0B
0x14007beaf  mov     [rsp+2B0h+var_270], 1
0x14007beb4  mov     r8d, 166h
0x14007beba  jmp     short loc_14007BEC9
0x14007bebc  xor     esi, esi
0x14007bebe  mov     edi, 0C000000Dh
0x14007bec3  mov     r8d, 100h
0x14007bec9  lea     rdx, aOnecoreVmVidSy_21
0x14007bed0  mov     rax, [r14]
0x14007bed3  mov     r9, r12
0x14007bed6  mov     [rsp+2B0h+var_280], edi
0x14007beda  mov     rcx, r15
0x14007bedd  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007bee2  lea     rax, [r13+78h]
0x14007bee6  mov     qword ptr [rsp+2B0h+BugCheckOnFailure], rax
0x14007beeb  call    VidTracePartitionErrorInternal0
0x14007bef0  test    edi, edi
0x14007bef2  jns     short loc_14007BF04
0x14007bef4  test    rsi, rsi
0x14007bef7  jz      short loc_14007BF04
0x14007bef9  mov     rdx, rsi
0x14007befc  mov     rcx, r13
0x14007beff  call    VidTdxMigrationBundleTeardown
0x14007bf04  cmp     [rsp+2B0h+var_270], 0
0x14007bf09  jz      short loc_14007BF17
0x14007bf0b  lea     rcx, [r13+31D8h]
0x14007bf12  call    VidLockRelease
0x14007bf17  xor     esi, esi
0x14007bf19  cmp     [rbp+1B0h+var_1F8], sil
0x14007bf1d  jz      loc_14007C121
0x14007bf23  mov     eax, cs:dword_140065110
0x14007bf29  test    edi, edi
0x14007bf2b  js      loc_14007C031
0x14007bf31  cmp     eax, 5
0x14007bf34  jbe     loc_14007C117
0x14007bf3a  mov     edx, 100h
0x14007bf3f  lea     rcx, dword_140065110
0x14007bf46  call    _tlgKeywordOn
0x14007bf4b  test    al, al
0x14007bf4d  jz      loc_14007C117
0x14007bf53  mov     rdx, [rsp+2B0h+var_240]
0x14007bf58  lea     rcx, [rbp+1B0h+var_C0]
0x14007bf5f  call    _tlgCreate1Sz_char
0x14007bf64  mov     rax, [rbp+1B0h+var_200]
0x14007bf68  mov     rcx, [rbp+1B0h+var_210]
0x14007bf6c  mov     [rbp+1B0h+var_B0], rcx
0x14007bf73  mov     [rbp+1B0h+var_A8], 10h
0x14007bf7e  movzx   edx, word ptr [rax]
0x14007bf81  mov     rcx, [rax+8]
0x14007bf85  lea     rax, [rbp+1B0h+var_88]
0x14007bf8c  mov     [rbp+1B0h+var_A0], rax
0x14007bf93  mov     rax, [rbp+1B0h+var_208]
0x14007bf97  mov     [rsp+2B0h+var_260], rax
0x14007bf9c  lea     rax, [rsp+2B0h+var_260]
0x14007bfa1  mov     [rbp+1B0h+var_80], rax
0x14007bfa8  mov     rax, [rsp+2B0h+var_248]
0x14007bfad  mov     dword ptr [rbp+1B0h+var_88], edx
0x14007bfb3  lea     rdx, unk_140046002
0x14007bfba  mov     [rbp+1B0h+var_98], 2
0x14007bfc5  mov     [rbp+1B0h+var_90], rcx
0x14007bfcc  mov     rax, [rax]
0x14007bfcf  mov     [rsp+2B0h+var_250], rax
0x14007bfd4  lea     rax, [rsp+2B0h+var_250]
0x14007bfd9  mov     [rbp+1B0h+var_70], rax
0x14007bfe0  lea     rax, [rsp+2B0h+var_268]
0x14007bfe5  mov     [rbp+1B0h+var_60], rax
0x14007bfec  lea     rax, [rbp+1B0h+var_E0]
0x14007bff3  mov     qword ptr [rsp+2B0h+Priority], rax
0x14007bff8  mov     [rsp+2B0h+BugCheckOnFailure], 9
0x14007c000  mov     dword ptr [rbp+1B0h+var_88+4], esi
0x14007c006  mov     [rbp+1B0h+var_78], 8
0x14007c011  mov     [rbp+1B0h+var_68], 8
0x14007c01c  mov     [rsp+2B0h+var_268], rbx
0x14007c021  mov     [rbp+1B0h+var_58], 8
0x14007c02c  jmp     loc_14007C104
0x14007c031  cmp     eax, 2
0x14007c034  jbe     loc_14007C117
0x14007c03a  mov     edx, 100h
0x14007c03f  lea     rcx, dword_140065110
0x14007c046  call    _tlgKeywordOn
0x14007c04b  test    al, al
  ... truncated ...
```
