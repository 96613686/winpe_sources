# VsmmDaxFilepLockInputValidation

- ea: `0x1400bd32c`
- end: `0x1400bd976`
- name: `VsmmDaxFilepLockInputValidation`
- size: `1610`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400bc0c4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14002140c`
- `0x140021580`
- `0x140021c60`
- `0x140021e00`
- `0x1400386a0`
- `0x1400bc054`
- `0x1400bc9c4`
- `0x1400bd32c`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bd3e1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bd3e1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd7cf`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd7cf`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bd44b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400bd44b`
- `ntoskrnl!IoFileObjectType` at `0x1400bd3b8`
- `ntoskrnl!IoFileObjectType` at `0x1400bd42f`
- `ntoskrnl!ZwClose` at `0x1400bd7bb`
- `ntoskrnl!ZwClose` at `0x1400bd7bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd7f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd7f5`
- `ntoskrnl!FsRtlQueryCachedVdl` at `0x1400bd565`
- `ntoskrnl!FsRtlQueryCachedVdl` at `0x1400bd565`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1400bd4f7`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x1400bd4f7`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400bd48e`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1400bd48e`

## pseudocode

```c
__int64 __fastcall VsmmDaxFilepLockInputValidation(
        __int64 a1,
        void *a2,
        unsigned __int64 a3,
        __int64 a4,
        _QWORD *a5,
        char *a6)
{
  NTSTATUS v9; // eax
  PVOID v10; // r12
  NTSTATUS v11; // edi
  int v12; // eax
  __int64 v13; // r9
  unsigned __int8 v14; // dl
  unsigned __int8 v15; // r8
  void *v16; // rdx
  unsigned __int64 v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // r14
  __int64 v20; // r13
  HANDLE v21; // rax
  _QWORD *AllNodes; // rax
  _QWORD *v23; // rbx
  int Object; // [rsp+20h] [rbp-E0h]
  char v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v33; // [rsp+70h] [rbp-90h] BYREF
  char *v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  _DWORD FsInformation[136]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v39[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v40[16]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v41[16]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int64 *v42; // [rsp+310h] [rbp+210h]
  __int64 v43; // [rsp+318h] [rbp+218h]
  char *v44; // [rsp+320h] [rbp+220h]
  __int64 v45; // [rsp+328h] [rbp+228h]
  char **v46; // [rsp+330h] [rbp+230h]
  __int64 v47; // [rsp+338h] [rbp+238h]
  _QWORD **v48; // [rsp+340h] [rbp+240h]
  __int64 v49; // [rsp+348h] [rbp+248h]
  PVOID *v50; // [rsp+350h] [rbp+250h]
  __int64 v51; // [rsp+358h] [rbp+258h]
  __int64 *v52; // [rsp+360h] [rbp+260h]
  __int64 v53; // [rsp+368h] [rbp+268h]

  v33 = a5;
  v28 = a3;
  v34 = a6;
  v29 = a4;
  v35 = 0;
  v36 = 0;
  IoStatusBlock = 0;
  memset(FsInformation, 0, 0x218u);
  FileHandle = 0;
  DvIntervalInitializeTree(&v36);
  v31 = 0;
  v9 = ObReferenceObjectByHandle(a2, 0x12019Fu, (POBJECT_TYPE)IoFileObjectType, 1, &v31, 0);
  v10 = v31;
  v11 = v9;
  if ( v9 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2524);
    goto LABEL_30;
  }
  v11 = ObOpenObjectByPointer(v31, 0x200u, 0, 0x12019Fu, (POBJECT_TYPE)IoFileObjectType, 0, &FileHandle);
  if ( v11 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2543);
    goto LABEL_30;
  }
  v11 = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation);
  if ( v11 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2555);
    goto LABEL_30;
  }
  if ( (FsInformation[0] & 0x20000000) != 0 )
  {
    v27 = 0;
    LODWORD(v32) = 0;
    v11 = FsRtlKernelFsControlFile(v10, 590804, 0, 0, &v27, 4, &v32);
    if ( v11 < 0 )
    {
      VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2590);
      goto LABEL_30;
    }
    v12 = *(unsigned __int8 *)(a1 + 240);
    v26 = 1;
    if ( v27 != v12 )
    {
      v13 = *(_QWORD *)(a1 + 8);
      v14 = 0;
      v15 = *(_BYTE *)(v13 + 2040);
      if ( v15 )
      {
        while ( *(unsigned __int8 *)(v14 + v13 + 2041) != v27 )
        {
          if ( ++v14 >= v15 )
            goto LABEL_14;
        }
        v11 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v40, "VsmmDaxFilepLockInputValidation");
          tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
          LODWORD(v28) = 2608;
          v42 = &v28;
          v16 = &unk_140050811;
          v26 = *(_BYTE *)(a1 + 240);
          v44 = &v26;
          LODWORD(v29) = v27;
          v46 = (char **)&v29;
          Object = 7;
          v45 = 1;
          v47 = 4;
LABEL_19:
          v43 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v16, 0, 0, Object, v39);
          goto LABEL_30;
        }
        goto LABEL_30;
      }
    }
  }
  else
  {
    v26 = 0;
    if ( !(unsigned __int8)VsmmDaxFileQueryRegistryIsRegularFileEnabled() )
    {
      v11 = -1073741811;
      VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2619);
      goto LABEL_30;
    }
  }
LABEL_14:
  v11 = FsRtlQueryCachedVdl(v10, &v35);
  if ( v11 < 0 )
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockInputValidation", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 2632);
    goto LABEL_30;
  }
  v17 = 0;
  v18 = 0;
  v19 = v35 >> 12;
  if ( a3 )
  {
    while ( 1 )
    {
      v20 = v29 + 24 * v18;
      v11 = VsmmDaxFilepFilePageRangeValidate(v19, v20, &v36);
      if ( v11 < 0 )
        break;
      v17 += *(_QWORD *)(v20 + 8);
      if ( ++v18 >= v28 )
        goto LABEL_25;
    }
  }
  else
  {
LABEL_25:
    if ( v17 == *(_QWORD *)(a1 + 48) )
    {
      v21 = FileHandle;
      v11 = 0;
      FileHandle = 0;
      *v33 = v21;
      *v34 = v26;
    }
    else
    {
      v11 = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v40, "VsmmDaxFilepLockInputValidation");
        tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
        LODWORD(v29) = 2661;
        v42 = (unsigned __int64 *)&v29;
        v16 = &unk_140050875;
        v28 = v17;
        v44 = (char *)&v28;
        Object = 6;
        v45 = 8;
        goto LABEL_19;
      }
    }
  }
LABEL_30:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v10 )
    ObfDereferenceObject(v10);
  AllNodes = (_QWORD *)DvIntervalGetAllNodes(&v36);
  if ( AllNodes )
  {
    do
    {
      v23 = (_QWORD *)AllNodes[6];
      ExFreePoolWithTag(AllNodes, 0x6D4D6456u);
      AllNodes = v23;
    }
    while ( v23 );
  }
  if ( v11 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v40, "VsmmDaxFilepLockInputValidation");
    tlgCreate1Sz_char(v41, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
    LODWORD(v29) = 2692;
    v42 = (unsigned __int64 *)&v29;
    v43 = 4;
    v44 = (char *)&v28;
    v34 = *(char **)(a1 + 24);
    LODWORD(v28) = v11;
    v46 = &v34;
    v33 = *(_QWORD **)(a1 + 40);
    v48 = &v33;
    v31 = *(PVOID *)(a1 + 48);
    v50 = &v31;
    v32 = *(int *)(a1 + 264);
    v52 = &v32;
    v45 = 4;
    v47 = 8;
    v49 = 8;
    v51 = 8;
    v53 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400508BA, 0, 0, 10, v39);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400bd32c  mov     [rsp-8+arg_0], rbx
0x1400bd331  push    rbp
0x1400bd332  push    rsi
0x1400bd333  push    rdi
0x1400bd334  push    r12
0x1400bd336  push    r13
0x1400bd338  push    r14
0x1400bd33a  push    r15
0x1400bd33c  lea     rbp, [rsp-280h]
0x1400bd344  sub     rsp, 380h
0x1400bd34b  mov     rax, cs:__security_cookie
0x1400bd352  xor     rax, rsp
0x1400bd355  mov     [rbp+2B0h+var_40], rax
0x1400bd35c  mov     rax, [rbp+2B0h+arg_20]
0x1400bd363  xorps   xmm0, xmm0
0x1400bd366  mov     [rsp+3B0h+var_340], rax
0x1400bd36b  mov     r13, r8
0x1400bd36e  mov     rax, [rbp+2B0h+arg_28]
0x1400bd375  mov     rbx, rdx
0x1400bd378  mov     [rsp+3B0h+var_368], r8
0x1400bd37d  mov     r15, rcx
0x1400bd380  xor     r14d, r14d
0x1400bd383  mov     [rsp+3B0h+var_338], rax
0x1400bd388  xor     edx, edx; Val
0x1400bd38a  mov     [rsp+3B0h+var_360], r9
0x1400bd38f  mov     r8d, 218h; Size
0x1400bd395  mov     [rbp+2B0h+var_330], r14
0x1400bd399  lea     rcx, [rbp+2B0h+FsInformation]; void *
0x1400bd39d  movups  [rbp+2B0h+var_328], xmm0
0x1400bd3a1  movups  xmmword ptr [rbp+2B0h+IoStatusBlock], xmm0
0x1400bd3a5  call    memset
0x1400bd3aa  lea     rcx, [rbp+2B0h+var_328]
0x1400bd3ae  mov     [rsp+3B0h+FileHandle], r14
0x1400bd3b3  call    DvIntervalInitializeTree
0x1400bd3b8  mov     r8, cs:__imp_IoFileObjectType
0x1400bd3bf  lea     rax, [rsp+3B0h+var_350]
0x1400bd3c4  mov     [rsp+3B0h+HandleInformation], r14; HandleInformation
0x1400bd3c9  mov     r9b, 1; AccessMode
0x1400bd3cc  mov     edx, 12019Fh; DesiredAccess
0x1400bd3d1  mov     [rsp+3B0h+var_350], r14
0x1400bd3d6  mov     rcx, rbx; Handle
0x1400bd3d9  mov     [rsp+3B0h+Object], rax; Object
0x1400bd3de  mov     r8, [r8]; ObjectType
0x1400bd3e1  call    cs:__imp_ObReferenceObjectByHandle
0x1400bd3e8  nop     dword ptr [rax+rax+00h]
0x1400bd3ed  mov     r12, [rsp+3B0h+var_350]
0x1400bd3f2  lea     rbx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bd3f9  lea     rsi, aVsmmdaxfileplo_1; "VsmmDaxFilepLockInputValidation"
0x1400bd400  mov     edi, eax
0x1400bd402  test    eax, eax
0x1400bd404  jns     short loc_1400BD41C
0x1400bd406  mov     r8d, 9DCh
0x1400bd40c  mov     rdx, rbx
0x1400bd40f  mov     rcx, rsi
0x1400bd412  call    VidTraceErrorInternal0
0x1400bd417  jmp     loc_1400BD7B1
0x1400bd41c  lea     rax, [rsp+3B0h+FileHandle]
0x1400bd421  mov     r9d, 12019Fh; DesiredAccess
0x1400bd427  mov     [rsp+3B0h+Handle], rax; Handle
0x1400bd42c  xor     r8d, r8d; PassedAccessState
0x1400bd42f  mov     rax, cs:__imp_IoFileObjectType
0x1400bd436  mov     edx, 200h; HandleAttributes
0x1400bd43b  mov     byte ptr [rsp+3B0h+HandleInformation], r14b; AccessMode
0x1400bd440  mov     rcx, [rax]
0x1400bd443  mov     [rsp+3B0h+Object], rcx; ObjectType
0x1400bd448  mov     rcx, r12; Object
0x1400bd44b  call    cs:__imp_ObOpenObjectByPointer
0x1400bd452  nop     dword ptr [rax+rax+00h]
0x1400bd457  mov     edi, eax
0x1400bd459  test    eax, eax
0x1400bd45b  jns     short loc_1400BD473
0x1400bd45d  mov     r8d, 9EFh
0x1400bd463  mov     rdx, rbx
0x1400bd466  mov     rcx, rsi
0x1400bd469  call    VidTraceErrorInternal0
0x1400bd46e  jmp     loc_1400BD7B1
0x1400bd473  mov     rcx, [rsp+3B0h+FileHandle]; FileHandle
0x1400bd478  lea     r8, [rbp+2B0h+FsInformation]; FsInformation
0x1400bd47c  mov     r9d, 218h; Length
0x1400bd482  mov     dword ptr [rsp+3B0h+Object], 5; FsInformationClass
0x1400bd48a  lea     rdx, [rbp+2B0h+IoStatusBlock]; IoStatusBlock
0x1400bd48e  call    cs:__imp_ZwQueryVolumeInformationFile
0x1400bd495  nop     dword ptr [rax+rax+00h]
0x1400bd49a  mov     edi, eax
0x1400bd49c  test    eax, eax
0x1400bd49e  jns     short loc_1400BD4B6
0x1400bd4a0  mov     r8d, 9FBh
0x1400bd4a6  mov     rdx, rbx
0x1400bd4a9  mov     rcx, rsi
0x1400bd4ac  call    VidTraceErrorInternal0
0x1400bd4b1  jmp     loc_1400BD7B1
0x1400bd4b6  test    [rbp+2B0h+FsInformation], 20000000h
0x1400bd4bd  jz      loc_1400BD66E
0x1400bd4c3  lea     rax, [rsp+3B0h+var_348]
0x1400bd4c8  mov     [rsp+3B0h+var_36C], r14d
0x1400bd4cd  mov     [rsp+3B0h+Handle], rax
0x1400bd4d2  xor     r9d, r9d
0x1400bd4d5  lea     rax, [rsp+3B0h+var_36C]
0x1400bd4da  mov     dword ptr [rsp+3B0h+HandleInformation], 4
0x1400bd4e2  xor     r8d, r8d
0x1400bd4e5  mov     [rsp+3B0h+Object], rax
0x1400bd4ea  mov     edx, 903D4h
0x1400bd4ef  mov     dword ptr [rsp+3B0h+var_348], r14d
0x1400bd4f4  mov     rcx, r12
0x1400bd4f7  call    cs:__imp_FsRtlKernelFsControlFile
0x1400bd4fe  nop     dword ptr [rax+rax+00h]
0x1400bd503  mov     edi, eax
0x1400bd505  test    eax, eax
0x1400bd507  jns     short loc_1400BD51F
0x1400bd509  mov     r8d, 0A1Eh
0x1400bd50f  mov     rdx, rbx
0x1400bd512  mov     rcx, rsi
0x1400bd515  call    VidTraceErrorInternal0
0x1400bd51a  jmp     loc_1400BD7B1
0x1400bd51f  movzx   eax, byte ptr [r15+0F0h]
0x1400bd527  mov     [rsp+3B0h+var_370], 1
0x1400bd52c  cmp     [rsp+3B0h+var_36C], eax
0x1400bd530  jz      short loc_1400BD55E
0x1400bd532  mov     r9, [r15+8]
0x1400bd536  mov     dl, r14b
0x1400bd539  mov     r8b, [r9+7F8h]
0x1400bd540  test    r8b, r8b
0x1400bd543  jz      short loc_1400BD55E
0x1400bd545  movzx   eax, dl
0x1400bd548  movzx   ecx, byte ptr [rax+r9+7F9h]
0x1400bd551  cmp     ecx, [rsp+3B0h+var_36C]
0x1400bd555  jz      short loc_1400BD591
0x1400bd557  inc     dl
0x1400bd559  cmp     dl, r8b
0x1400bd55c  jb      short loc_1400BD545
0x1400bd55e  lea     rdx, [rbp+2B0h+var_330]
0x1400bd562  mov     rcx, r12
0x1400bd565  call    cs:__imp_FsRtlQueryCachedVdl
0x1400bd56c  nop     dword ptr [rax+rax+00h]
0x1400bd571  mov     edi, eax
0x1400bd573  test    eax, eax
0x1400bd575  jns     loc_1400BD69B
0x1400bd57b  mov     r8d, 0A48h
0x1400bd581  mov     rdx, rbx
0x1400bd584  mov     rcx, rsi
0x1400bd587  call    VidTraceErrorInternal0
0x1400bd58c  jmp     loc_1400BD7B1
0x1400bd591  mov     eax, cs:dword_140065110
0x1400bd597  mov     edi, 0C000000Dh
0x1400bd59c  cmp     eax, 2
0x1400bd59f  jbe     loc_1400BD7B1
0x1400bd5a5  mov     edx, 100h
0x1400bd5aa  lea     rcx, dword_140065110
0x1400bd5b1  call    _tlgKeywordOn
0x1400bd5b6  test    al, al
0x1400bd5b8  jz      loc_1400BD7B1
0x1400bd5be  mov     rdx, rsi
0x1400bd5c1  lea     rcx, [rbp+2B0h+var_C0]
0x1400bd5c8  call    _tlgCreate1Sz_char
0x1400bd5cd  mov     rdx, rbx
0x1400bd5d0  lea     rcx, [rbp+2B0h+var_B0]
0x1400bd5d7  call    _tlgCreate1Sz_char
0x1400bd5dc  lea     rax, [rsp+3B0h+var_368]
0x1400bd5e1  mov     dword ptr [rsp+3B0h+var_368], 0A30h
0x1400bd5e9  mov     [rbp+2B0h+var_A0], rax
0x1400bd5f0  lea     rdx, unk_140050811
0x1400bd5f7  mov     al, [r15+0F0h]
0x1400bd5fe  mov     [rsp+3B0h+var_370], al
0x1400bd602  lea     rax, [rsp+3B0h+var_370]
0x1400bd607  mov     [rbp+2B0h+var_90], rax
0x1400bd60e  mov     eax, [rsp+3B0h+var_36C]
0x1400bd612  mov     dword ptr [rsp+3B0h+var_360], eax
0x1400bd616  lea     rax, [rsp+3B0h+var_360]
0x1400bd61b  mov     [rbp+2B0h+var_80], rax
0x1400bd622  lea     rax, [rbp+2B0h+var_E0]
0x1400bd629  mov     [rsp+3B0h+HandleInformation], rax
0x1400bd62e  mov     dword ptr [rsp+3B0h+Object], 7
0x1400bd636  mov     [rbp+2B0h+var_88], 1
0x1400bd641  mov     [rbp+2B0h+var_78], 4
0x1400bd64c  xor     r9d, r9d
0x1400bd64f  mov     [rbp+2B0h+var_98], 4
0x1400bd65a  xor     r8d, r8d
0x1400bd65d  lea     rcx, dword_140065110
0x1400bd664  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400bd669  jmp     loc_1400BD7B1
0x1400bd66e  mov     [rsp+3B0h+var_370], r14b
0x1400bd673  call    VsmmDaxFileQueryRegistryIsRegularFileEnabled
0x1400bd678  test    al, al
0x1400bd67a  jnz     loc_1400BD55E
0x1400bd680  mov     edi, 0C000000Dh
0x1400bd685  mov     r8d, 0A3Bh
0x1400bd68b  mov     rdx, rbx
0x1400bd68e  mov     rcx, rsi
0x1400bd691  call    VidTraceErrorInternal0
0x1400bd696  jmp     loc_1400BD7B1
0x1400bd69b  mov     rsi, r14
0x1400bd69e  xor     ebx, ebx
0x1400bd6a0  mov     r14, [rbp+2B0h+var_330]
0x1400bd6a4  sar     r14, 0Ch
0x1400bd6a8  test    r13, r13
0x1400bd6ab  jz      short loc_1400BD6E1
0x1400bd6ad  mov     rcx, [rsp+3B0h+var_360]
0x1400bd6b2  lea     rax, [rbx+rbx*2]
0x1400bd6b6  lea     r8, [rbp+2B0h+var_328]
0x1400bd6ba  lea     r13, [rcx+rax*8]
0x1400bd6be  mov     rcx, r14
0x1400bd6c1  mov     rdx, r13
0x1400bd6c4  call    VsmmDaxFilepFilePageRangeValidate
0x1400bd6c9  mov     edi, eax
0x1400bd6cb  test    eax, eax
0x1400bd6cd  js      loc_1400BD7B1
0x1400bd6d3  add     rsi, [r13+8]
0x1400bd6d7  inc     rbx
0x1400bd6da  cmp     rbx, [rsp+3B0h+var_368]
0x1400bd6df  jb      short loc_1400BD6AD
0x1400bd6e1  cmp     rsi, [r15+30h]
0x1400bd6e5  jz      loc_1400BD78E
0x1400bd6eb  mov     eax, cs:dword_140065110
0x1400bd6f1  mov     edi, 0C000000Dh
0x1400bd6f6  cmp     eax, 2
0x1400bd6f9  jbe     loc_1400BD7B1
0x1400bd6ff  mov     edx, 100h
0x1400bd704  lea     rcx, dword_140065110
0x1400bd70b  call    _tlgKeywordOn
0x1400bd710  test    al, al
0x1400bd712  jz      loc_1400BD7B1
0x1400bd718  lea     rdx, aVsmmdaxfileplo_1; "VsmmDaxFilepLockInputValidation"
0x1400bd71f  lea     rcx, [rbp+2B0h+var_C0]
0x1400bd726  call    _tlgCreate1Sz_char
0x1400bd72b  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bd732  lea     rcx, [rbp+2B0h+var_B0]
0x1400bd739  call    _tlgCreate1Sz_char
0x1400bd73e  lea     rax, [rsp+3B0h+var_360]
0x1400bd743  mov     dword ptr [rsp+3B0h+var_360], 0A65h
0x1400bd74b  mov     [rbp+2B0h+var_A0], rax
0x1400bd752  lea     rdx, unk_140050875
0x1400bd759  lea     rax, [rsp+3B0h+var_368]
0x1400bd75e  mov     [rsp+3B0h+var_368], rsi
0x1400bd763  mov     [rbp+2B0h+var_90], rax
0x1400bd76a  lea     rax, [rbp+2B0h+var_E0]
0x1400bd771  mov     [rsp+3B0h+HandleInformation], rax
0x1400bd776  mov     dword ptr [rsp+3B0h+Object], 6
0x1400bd77e  mov     [rbp+2B0h+var_88], 8
0x1400bd789  jmp     loc_1400BD64C
0x1400bd78e  mov     rax, [rsp+3B0h+FileHandle]
0x1400bd793  xor     r14d, r14d
0x1400bd796  mov     rcx, [rsp+3B0h+var_340]
0x1400bd79b  mov     edi, r14d
0x1400bd79e  mov     [rsp+3B0h+FileHandle], r14
0x1400bd7a3  mov     [rcx], rax
0x1400bd7a6  mov     rcx, [rsp+3B0h+var_338]
0x1400bd7ab  mov     al, [rsp+3B0h+var_370]
0x1400bd7af  mov     [rcx], al
0x1400bd7b1  mov     rcx, [rsp+3B0h+FileHandle]; Handle
0x1400bd7b6  test    rcx, rcx
0x1400bd7b9  jz      short loc_1400BD7C7
0x1400bd7bb  call    cs:__imp_ZwClose
0x1400bd7c2  nop     dword ptr [rax+rax+00h]
0x1400bd7c7  test    r12, r12
0x1400bd7ca  jz      short loc_1400BD7DB
0x1400bd7cc  mov     rcx, r12; Object
0x1400bd7cf  call    cs:__imp_ObfDereferenceObject
0x1400bd7d6  nop     dword ptr [rax+rax+00h]
0x1400bd7db  lea     rcx, [rbp+2B0h+var_328]
0x1400bd7df  call    DvIntervalGetAllNodes
0x1400bd7e4  test    rax, rax
0x1400bd7e7  jz      short loc_1400BD809
0x1400bd7e9  mov     rbx, [rax+30h]
0x1400bd7ed  mov     edx, 6D4D6456h; Tag
0x1400bd7f2  mov     rcx, rax; P
0x1400bd7f5  call    cs:__imp_ExFreePoolWithTag
0x1400bd7fc  nop     dword ptr [rax+rax+00h]
0x1400bd801  mov     rax, rbx
0x1400bd804  test    rbx, rbx
0x1400bd807  jnz     short loc_1400BD7E9
0x1400bd809  test    edi, edi
0x1400bd80b  jns     loc_1400BD949
0x1400bd811  mov     eax, cs:dword_140065110
0x1400bd817  cmp     eax, 2
0x1400bd81a  jbe     loc_1400BD949
0x1400bd820  mov     edx, 100h
0x1400bd825  lea     rcx, dword_140065110
0x1400bd82c  call    _tlgKeywordOn
0x1400bd831  test    al, al
0x1400bd833  jz      loc_1400BD949
0x1400bd839  lea     rdx, aVsmmdaxfileplo_1; "VsmmDaxFilepLockInputValidation"
0x1400bd840  lea     rcx, [rbp+2B0h+var_C0]
0x1400bd847  call    _tlgCreate1Sz_char
0x1400bd84c  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bd853  lea     rcx, [rbp+2B0h+var_B0]
0x1400bd85a  call    _tlgCreate1Sz_char
0x1400bd85f  lea     rax, [rsp+3B0h+var_360]
0x1400bd864  mov     dword ptr [rsp+3B0h+var_360], 0A84h
0x1400bd86c  mov     [rbp+2B0h+var_A0], rax
0x1400bd873  lea     rdx, unk_1400508BA
0x1400bd87a  lea     rax, [rsp+3B0h+var_368]
0x1400bd87f  mov     [rbp+2B0h+var_98], 4
0x1400bd88a  mov     [rbp+2B0h+var_90], rax
0x1400bd891  lea     rcx, dword_140065110
0x1400bd898  mov     rax, [r15+18h]
0x1400bd89c  xor     r9d, r9d
0x1400bd89f  mov     [rsp+3B0h+var_338], rax
0x1400bd8a4  xor     r8d, r8d
0x1400bd8a7  lea     rax, [rsp+3B0h+var_338]
0x1400bd8ac  mov     dword ptr [rsp+3B0h+var_368], edi
  ... truncated ...
```
