# BfsInsertDirectoryEntry

- ea: `0x140011d18`
- end: `0x140012191`
- name: `BfsInsertDirectoryEntry`
- size: `1145`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x14001033c`
- `0x14001079c`
- `0x140012478`

## callees

- `0x140001008`
- `0x1400105ac`
- `0x140011458`
- `0x1400117a4`
- `0x140011d18`
- `0x140012ab0`
- `0x140013730`
- `0x140013840`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011d6e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011f81`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011d6e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011f81`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012054`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012116`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012133`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012154`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012054`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012116`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012133`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012154`
- `ntoskrnl!RtlFindClearBits` at `0x140011ddc`
- `ntoskrnl!RtlFindClearBits` at `0x140011f0a`
- `ntoskrnl!RtlFindClearBits` at `0x140011ddc`
- `ntoskrnl!RtlFindClearBits` at `0x140011f0a`
- `ntoskrnl!RtlSetBits` at `0x140011e0b`
- `ntoskrnl!RtlSetBits` at `0x140011e0b`
- `ntoskrnl!RtlClearBits` at `0x1400120ea`
- `ntoskrnl!RtlClearBits` at `0x1400120ea`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011dc7`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011ef5`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011dc7`
- `ntoskrnl!RtlInitializeBitMap` at `0x140011ef5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fe9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012100`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011fe9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012100`
- `ntoskrnl!ExAllocatePool2` at `0x140011e68`
- `ntoskrnl!ExAllocatePool2` at `0x140011e68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011d5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011f70`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011d5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011f70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012060`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012122`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001213f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012160`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012060`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012122`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001213f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012160`

## pseudocode

```c
ULONG *__fastcall BfsInsertDirectoryEntry(__int64 a1, ULONG a2, NTSTATUS a3, ULONG a4, __int64 a5)
{
  __int64 **v8; // rax
  __int64 *v9; // r12
  ULONG *v10; // r13
  __int64 *v11; // rax
  ULONG v12; // ecx
  __int64 v13; // rbx
  ULONG *v14; // r15
  const void **v15; // rax
  __int64 v16; // rcx
  _DWORD *Pool2; // rsi
  __int64 v18; // r8
  __int64 v19; // r9
  char v20; // bl
  signed int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  ULONG ClearBits; // eax
  __int64 *v25; // rdi
  __int64 v26; // rbx
  int v27; // eax
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  NTSTATUS v31; // eax
  __int64 v32; // rcx
  NTSTATUS v33; // eax
  __int64 v34; // r8
  __int64 v35; // r9
  int v37; // [rsp+20h] [rbp-71h]
  NTSTATUS v38; // [rsp+30h] [rbp-61h] BYREF
  char v39; // [rsp+34h] [rbp-5Dh]
  ULONG StartingIndex; // [rsp+38h] [rbp-59h] BYREF
  unsigned int v41; // [rsp+3Ch] [rbp-55h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+40h] [rbp-51h] BYREF
  int v43[2]; // [rsp+50h] [rbp-41h] BYREF
  ULONG *v44; // [rsp+58h] [rbp-39h] BYREF
  __int64 v45; // [rsp+60h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+68h] [rbp-29h] BYREF
  ULONG *p_StartingIndex; // [rsp+88h] [rbp-9h]
  __int64 v48; // [rsp+90h] [rbp-1h]

  v45 = a5;
  v38 = a3;
  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  v8 = *(__int64 ***)(a1 + 16);
  v41 = 0;
  v9 = *v8;
  *(_QWORD *)v43 = v9;
  v10 = (ULONG *)v9[2];
LABEL_4:
  v44 = v10;
  do
  {
    RtlInitializeBitMap(&BitMapHeader, v10 + 3992, 0x1Eu);
    StartingIndex = RtlFindClearBits(&BitMapHeader, 1u, 0);
    v12 = StartingIndex;
    if ( StartingIndex != -1 )
      break;
    v11 = (__int64 *)*v9;
    if ( *v9 != *(_QWORD *)(a1 + 16) )
    {
      v10 = (ULONG *)v11[2];
      v9 = (__int64 *)*v9;
      *(_QWORD *)v43 = v11;
      goto LABEL_4;
    }
    v21 = BfsExpandDirectory(a1, (_DWORD)v10, (_DWORD)v9, (unsigned int)&v44, (__int64)v43);
    if ( v21 < 0 )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        StartingIndex = v21;
        p_StartingIndex = &StartingIndex;
        v48 = 4;
        tlgWriteTransfer_EtwWriteTransfer((unsigned int)v21, (unsigned __int8 *)&byte_140016D91, v22, v23, v37, &v46);
      }
      goto LABEL_34;
    }
    v10 = v44;
    RtlInitializeBitMap(&BitMapHeader, v44 + 3992, 0x1Eu);
    ClearBits = RtlFindClearBits(&BitMapHeader, 1u, 0);
    v9 = *(__int64 **)v43;
    v12 = ClearBits;
    StartingIndex = ClearBits;
  }
  while ( ClearBits == -1 );
  v13 = 133LL * v12;
  v14 = &v10[v13];
  RtlSetBits(&BitMapHeader, v12, 1u);
  memset(&v10[v13 + 4], 0, 0x20Cu);
  v14[3] = v38;
  v15 = (const void **)v45;
  v14[2] = a2;
  memmove(&v10[v13 + 7], v15[1], *(unsigned __int16 *)v15);
  if ( a2 == 2 )
  {
    v14[4] = a4;
    Pool2 = (_DWORD *)ExAllocatePool2(256, 0x4000, 1651729986);
    if ( !Pool2 )
    {
      v20 = 0;
      if ( (unsigned int)dword_140019000 <= 3 )
      {
LABEL_30:
        RtlClearBits(&BitMapHeader, StartingIndex, 1u);
        if ( Pool2 )
          ExFreePoolWithTag(Pool2, 0);
        if ( v20 )
        {
          ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 8), 0);
          KeLeaveCriticalRegion();
        }
LABEL_34:
        ExReleasePushLockExclusiveEx(a1, 0);
        KeLeaveCriticalRegion();
        return 0;
      }
      v38 = -1073741801;
LABEL_10:
      v48 = 4;
      p_StartingIndex = (ULONG *)&v38;
      tlgWriteTransfer_EtwWriteTransfer(v16, (unsigned __int8 *)&byte_140016D91, v18, v19, v37, &v46);
      goto LABEL_30;
    }
    v25 = (__int64 *)(a1 + 8);
    v26 = *(_QWORD *)(a1 + 8);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v26, 0);
    v20 = 1;
    v27 = BfsAllocateBlock(*(_QWORD *)(a1 + 8), &v41);
    if ( v27 < 0 )
    {
      v16 = (unsigned int)dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_30;
      v38 = v27;
      goto LABEL_10;
    }
    memset(Pool2 + 1, 0, 0x3FFCu);
    v28 = v41;
    *Pool2 = 1148413506;
    v14[5] = v28;
    v38 = BfsWriteBlock(*v25, v28, Pool2);
    ExFreePoolWithTag(Pool2, 0);
    v31 = v38;
    Pool2 = 0;
    if ( v38 < 0 || (v31 = BfsWriteBlock(*v25, 0, *(void **)(*v25 + 16)), v31 < 0) )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v38 = v31;
        v48 = 4;
        p_StartingIndex = (ULONG *)&v38;
        tlgWriteTransfer_EtwWriteTransfer(
          (unsigned int)dword_140019000,
          (unsigned __int8 *)&byte_140016D91,
          v29,
          v30,
          v37,
          &v46);
      }
LABEL_29:
      BfsFreeBlock(*v25, v41);
      goto LABEL_30;
    }
    v32 = *v25;
    v39 = 1;
    ExReleasePushLockExclusiveEx(v32, 0);
    KeLeaveCriticalRegion();
  }
  else
  {
    v39 = 0;
    v25 = (__int64 *)(a1 + 8);
    v14[4] = 0;
  }
  v33 = BfsWriteBlock(*v25, *((_DWORD *)v9 + 6), v10);
  if ( v33 < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v38 = v33;
      v48 = 4;
      p_StartingIndex = (ULONG *)&v38;
      tlgWriteTransfer_EtwWriteTransfer(
        (unsigned int)dword_140019000,
        (unsigned __int8 *)&byte_140016D91,
        v34,
        v35,
        v37,
        &v46);
    }
    v20 = 0;
    Pool2 = 0;
    if ( !v39 )
      goto LABEL_30;
    goto LABEL_29;
  }
  ExReleasePushLockExclusiveEx(a1, 0);
  KeLeaveCriticalRegion();
  return v14 + 2;
}

```

## disassembly

```asm
0x140011d18  push    rbp
0x140011d1a  push    rbx
0x140011d1b  push    rsi
0x140011d1c  push    rdi
0x140011d1d  push    r12
0x140011d1f  push    r13
0x140011d21  push    r14
0x140011d23  push    r15
0x140011d25  lea     rbp, [rsp-17h]
0x140011d2a  sub     rsp, 0A8h
0x140011d31  mov     rax, cs:__security_cookie
0x140011d38  xor     rax, rsp
0x140011d3b  mov     [rbp+4Fh+var_48], rax
0x140011d3f  mov     rax, [rbp+4Fh+arg_20]
0x140011d43  mov     edi, r9d
0x140011d46  mov     [rbp+4Fh+var_80], rax
0x140011d4a  mov     esi, edx
0x140011d4c  xor     eax, eax
0x140011d4e  mov     [rbp+4Fh+var_B0], r8d
0x140011d52  mov     qword ptr [rbp+4Fh+BitMapHeader+4], rax
0x140011d56  mov     r14, rcx
0x140011d59  mov     [rbp-51h], rax
0x140011d5d  call    cs:__imp_KeEnterCriticalRegion
0x140011d64  nop     dword ptr [rax+rax+00h]
0x140011d69  xor     edx, edx
0x140011d6b  mov     rcx, r14
0x140011d6e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011d75  nop     dword ptr [rax+rax+00h]
0x140011d7a  mov     rax, [r14+10h]
0x140011d7e  mov     ebx, 1
0x140011d83  mov     [rbp+4Fh+var_A4], 0
0x140011d8a  mov     r12, [rax]
0x140011d8d  lea     r15d, [rbx+1Dh]
0x140011d91  mov     qword ptr [rbp+4Fh+var_90], r12
0x140011d95  mov     r13, [r12+10h]
0x140011d9a  jmp     short loc_140011DB5
0x140011d9c  mov     rax, [r12]
0x140011da0  cmp     rax, [r14+10h]
0x140011da4  jz      loc_140011EC2
0x140011daa  mov     r13, [rax+10h]
0x140011dae  mov     r12, rax
0x140011db1  mov     qword ptr [rbp+4Fh+var_90], rax
0x140011db5  mov     [rbp+4Fh+var_88], r13
0x140011db9  mov     r8d, r15d; SizeOfBitMap
0x140011dbc  lea     rdx, [r13+3E60h]; BitMapBuffer
0x140011dc3  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011dc7  call    cs:__imp_RtlInitializeBitMap
0x140011dce  nop     dword ptr [rax+rax+00h]
0x140011dd3  xor     r8d, r8d; HintIndex
0x140011dd6  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011dda  mov     edx, ebx; NumberToFind
0x140011ddc  call    cs:__imp_RtlFindClearBits
0x140011de3  nop     dword ptr [rax+rax+00h]
0x140011de8  mov     [rbp+4Fh+StartingIndex], eax
0x140011deb  mov     ecx, eax
0x140011ded  cmp     eax, 0FFFFFFFFh
0x140011df0  jz      short loc_140011D9C
0x140011df2  mov     eax, ecx
0x140011df4  mov     edx, ecx; StartingIndex
0x140011df6  imul    rbx, rax, 214h
0x140011dfd  mov     r8d, 1; NumberToSet
0x140011e03  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011e07  lea     r15, [rbx+r13]
0x140011e0b  call    cs:__imp_RtlSetBits
0x140011e12  nop     dword ptr [rax+rax+00h]
0x140011e17  lea     rcx, [r13+10h]
0x140011e1b  xor     edx, edx; Val
0x140011e1d  add     rcx, rbx; void *
0x140011e20  mov     r8d, 20Ch; Size
0x140011e26  call    memset
0x140011e2b  mov     eax, [rbp+4Fh+var_B0]
0x140011e2e  lea     rcx, [r15+1Ch]; void *
0x140011e32  mov     [r15+0Ch], eax
0x140011e36  mov     rax, [rbp+4Fh+var_80]
0x140011e3a  mov     [r15+8], esi
0x140011e3e  movzx   r8d, word ptr [rax]; Size
0x140011e42  mov     rdx, [rax+8]; Src
0x140011e46  call    memmove
0x140011e4b  cmp     esi, 2
0x140011e4e  jnz     loc_14001206E
0x140011e54  mov     edx, 4000h
0x140011e59  mov     [r15+10h], edi
0x140011e5d  mov     ecx, 100h
0x140011e62  mov     r8d, 62736642h
0x140011e68  call    cs:__imp_ExAllocatePool2
0x140011e6f  nop     dword ptr [rax+rax+00h]
0x140011e74  mov     rsi, rax
0x140011e77  test    rax, rax
0x140011e7a  jnz     loc_140011F69
0x140011e80  mov     eax, cs:dword_140019000
0x140011e86  xor     bl, bl
0x140011e88  cmp     eax, 3
0x140011e8b  jbe     loc_1400120DD
0x140011e91  mov     [rbp+4Fh+var_B0], 0C0000017h
0x140011e98  lea     rax, [rbp+4Fh+var_B0]
0x140011e9c  mov     [rbp+4Fh+var_50], 4
0x140011ea4  mov     [rbp+4Fh+var_58], rax
0x140011ea8  lea     rdx, byte_140016D91; int
0x140011eaf  lea     rax, [rbp+4Fh+var_78]
0x140011eb3  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140011eb8  call    _tlgWriteTransfer_EtwWriteTransfer
0x140011ebd  jmp     loc_1400120DD
0x140011ec2  lea     rax, [rbp+4Fh+var_90]
0x140011ec6  mov     r8, r12
0x140011ec9  lea     r9, [rbp+4Fh+var_88]
0x140011ecd  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x140011ed2  mov     rdx, r13
0x140011ed5  mov     rcx, r14
0x140011ed8  call    BfsExpandDirectory
0x140011edd  mov     ecx, eax; int
0x140011edf  test    eax, eax
0x140011ee1  js      short loc_140011F2D
0x140011ee3  mov     r13, [rbp+4Fh+var_88]
0x140011ee7  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011eeb  mov     r8d, r15d; SizeOfBitMap
0x140011eee  lea     rdx, [r13+3E60h]; BitMapBuffer
0x140011ef5  call    cs:__imp_RtlInitializeBitMap
0x140011efc  nop     dword ptr [rax+rax+00h]
0x140011f01  xor     r8d, r8d; HintIndex
0x140011f04  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x140011f08  mov     edx, ebx; NumberToFind
0x140011f0a  call    cs:__imp_RtlFindClearBits
0x140011f11  nop     dword ptr [rax+rax+00h]
0x140011f16  mov     r12, qword ptr [rbp+4Fh+var_90]
0x140011f1a  mov     ecx, eax
0x140011f1c  mov     [rbp+4Fh+StartingIndex], eax
0x140011f1f  cmp     eax, 0FFFFFFFFh
0x140011f22  jz      loc_140011DB9
0x140011f28  jmp     loc_140011DF2
0x140011f2d  mov     eax, cs:dword_140019000
0x140011f33  cmp     eax, 3
0x140011f36  jbe     loc_14001212E
0x140011f3c  lea     rax, [rbp+4Fh+StartingIndex]
0x140011f40  mov     [rbp+4Fh+StartingIndex], ecx
0x140011f43  mov     [rbp+4Fh+var_58], rax
0x140011f47  lea     rdx, byte_140016D91; int
0x140011f4e  lea     rax, [rbp+4Fh+var_78]
0x140011f52  mov     [rbp+4Fh+var_50], 4
0x140011f5a  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140011f5f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140011f64  jmp     loc_14001212E
0x140011f69  lea     rdi, [r14+8]
0x140011f6d  mov     rbx, [rdi]
0x140011f70  call    cs:__imp_KeEnterCriticalRegion
0x140011f77  nop     dword ptr [rax+rax+00h]
0x140011f7c  xor     edx, edx
0x140011f7e  mov     rcx, rbx
0x140011f81  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011f88  nop     dword ptr [rax+rax+00h]
0x140011f8d  mov     rcx, [rdi]
0x140011f90  lea     rdx, [rbp+4Fh+var_A4]
0x140011f94  mov     bl, 1
0x140011f96  call    BfsAllocateBlock
0x140011f9b  test    eax, eax
0x140011f9d  jns     short loc_140011FB6
0x140011f9f  mov     ecx, cs:dword_140019000
0x140011fa5  cmp     ecx, 3
0x140011fa8  jbe     loc_1400120DD
0x140011fae  mov     [rbp+4Fh+var_B0], eax
0x140011fb1  jmp     loc_140011E98
0x140011fb6  lea     rcx, [rsi+4]; void *
0x140011fba  xor     edx, edx; Val
0x140011fbc  mov     r8d, 3FFCh; Size
0x140011fc2  call    memset
0x140011fc7  mov     eax, [rbp+4Fh+var_A4]
0x140011fca  mov     r8, rsi
0x140011fcd  mov     dword ptr [rsi], 44736642h
0x140011fd3  mov     edx, eax
0x140011fd5  mov     [r15+14h], eax
0x140011fd9  mov     rcx, [rdi]
0x140011fdc  call    BfsWriteBlock
0x140011fe1  xor     edx, edx; Tag
0x140011fe3  mov     [rbp+4Fh+var_B0], eax
0x140011fe6  mov     rcx, rsi; P
0x140011fe9  call    cs:__imp_ExFreePoolWithTag
0x140011ff0  nop     dword ptr [rax+rax+00h]
0x140011ff5  mov     eax, [rbp+4Fh+var_B0]
0x140011ff8  xor     esi, esi
0x140011ffa  test    eax, eax
0x140011ffc  jns     short loc_14001203A
0x140011ffe  mov     ecx, cs:dword_140019000; int
0x140012004  cmp     ecx, 3
0x140012007  jbe     loc_1400120D2
0x14001200d  mov     [rbp+4Fh+var_B0], eax
0x140012010  lea     rdx, byte_140016D91; int
0x140012017  lea     rax, [rbp+4Fh+var_B0]
0x14001201b  mov     [rbp+4Fh+var_50], 4
0x140012023  mov     [rbp+4Fh+var_58], rax
0x140012027  lea     rax, [rbp+4Fh+var_78]
0x14001202b  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140012030  call    _tlgWriteTransfer_EtwWriteTransfer
0x140012035  jmp     loc_1400120D2
0x14001203a  mov     rcx, [rdi]
0x14001203d  xor     edx, edx
0x14001203f  mov     r8, [rcx+10h]
0x140012043  call    BfsWriteBlock
0x140012048  test    eax, eax
0x14001204a  js      short loc_140011FFE
0x14001204c  mov     rcx, [rdi]
0x14001204f  xor     edx, edx
0x140012051  mov     [rbp+4Fh+var_AC], bl
0x140012054  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001205b  nop     dword ptr [rax+rax+00h]
0x140012060  call    cs:__imp_KeLeaveCriticalRegion
0x140012067  nop     dword ptr [rax+rax+00h]
0x14001206c  jmp     short loc_14001207E
0x14001206e  mov     [rbp+4Fh+var_AC], 0
0x140012072  lea     rdi, [r14+8]
0x140012076  mov     dword ptr [r15+10h], 0
0x14001207e  mov     edx, [r12+18h]
0x140012083  mov     r8, r13
0x140012086  mov     rcx, [rdi]
0x140012089  call    BfsWriteBlock
0x14001208e  test    eax, eax
0x140012090  jns     loc_14001214F
0x140012096  mov     ecx, cs:dword_140019000; int
0x14001209c  cmp     ecx, 3
0x14001209f  jbe     short loc_1400120C9
0x1400120a1  mov     [rbp+4Fh+var_B0], eax
0x1400120a4  lea     rdx, byte_140016D91; int
0x1400120ab  lea     rax, [rbp+4Fh+var_B0]
0x1400120af  mov     [rbp+4Fh+var_50], 4
0x1400120b7  mov     [rbp+4Fh+var_58], rax
0x1400120bb  lea     rax, [rbp+4Fh+var_78]
0x1400120bf  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1400120c4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400120c9  xor     bl, bl
0x1400120cb  xor     esi, esi
0x1400120cd  cmp     [rbp+4Fh+var_AC], bl
0x1400120d0  jz      short loc_1400120DD
0x1400120d2  mov     edx, [rbp+4Fh+var_A4]
0x1400120d5  mov     rcx, [rdi]
0x1400120d8  call    BfsFreeBlock
0x1400120dd  mov     edx, [rbp+4Fh+StartingIndex]; StartingIndex
0x1400120e0  lea     rcx, [rbp+4Fh+BitMapHeader]; BitMapHeader
0x1400120e4  mov     r8d, 1; NumberToClear
0x1400120ea  call    cs:__imp_RtlClearBits
0x1400120f1  nop     dword ptr [rax+rax+00h]
0x1400120f6  test    rsi, rsi
0x1400120f9  jz      short loc_14001210C
0x1400120fb  xor     edx, edx; Tag
0x1400120fd  mov     rcx, rsi; P
0x140012100  call    cs:__imp_ExFreePoolWithTag
0x140012107  nop     dword ptr [rax+rax+00h]
0x14001210c  test    bl, bl
0x14001210e  jz      short loc_14001212E
0x140012110  mov     rcx, [r14+8]
0x140012114  xor     edx, edx
0x140012116  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001211d  nop     dword ptr [rax+rax+00h]
0x140012122  call    cs:__imp_KeLeaveCriticalRegion
0x140012129  nop     dword ptr [rax+rax+00h]
0x14001212e  xor     edx, edx
0x140012130  mov     rcx, r14
0x140012133  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001213a  nop     dword ptr [rax+rax+00h]
0x14001213f  call    cs:__imp_KeLeaveCriticalRegion
0x140012146  nop     dword ptr [rax+rax+00h]
0x14001214b  xor     eax, eax
0x14001214d  jmp     short loc_140012170
0x14001214f  xor     edx, edx
0x140012151  mov     rcx, r14
0x140012154  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001215b  nop     dword ptr [rax+rax+00h]
0x140012160  call    cs:__imp_KeLeaveCriticalRegion
0x140012167  nop     dword ptr [rax+rax+00h]
0x14001216c  lea     rax, [r15+8]
0x140012170  mov     rcx, [rbp+4Fh+var_48]
0x140012174  xor     rcx, rsp; StackCookie
0x140012177  call    __security_check_cookie
0x14001217c  add     rsp, 0A8h
0x140012183  pop     r15
0x140012185  pop     r14
0x140012187  pop     r13
0x140012189  pop     r12
0x14001218b  pop     rdi
0x14001218c  pop     rsi
0x14001218d  pop     rbx
0x14001218e  pop     rbp
0x14001218f  retn
```
