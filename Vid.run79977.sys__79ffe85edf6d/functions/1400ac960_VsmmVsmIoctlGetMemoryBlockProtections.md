# VsmmVsmIoctlGetMemoryBlockProtections

- ea: `0x1400ac960`
- end: `0x1400ad4e7`
- name: `VsmmVsmIoctlGetMemoryBlockProtections`
- size: `2951`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400305c0`
- `0x1400347a4`
- `0x1400347d4`
- `0x1400ac960`
- `0x1400b0480`
- `0x1400f6da8`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400aca93`
- `ntoskrnl!ProbeForWrite` at `0x1400aca93`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400acc63`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400acc63`
- `ntoskrnl!IoFreeMdl` at `0x1400ad1ab`
- `ntoskrnl!IoFreeMdl` at `0x1400ad1ab`
- `ntoskrnl!IoAllocateMdl` at `0x1400acab1`
- `ntoskrnl!IoAllocateMdl` at `0x1400acab1`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400acc2e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400acc2e`
- `ntoskrnl!MmUnlockPages` at `0x1400ad197`
- `ntoskrnl!MmUnlockPages` at `0x1400ad197`

## pseudocode

```c
__int64 __fastcall VsmmVsmIoctlGetMemoryBlockProtections(
        SIZE_T a1,
        SIZE_T a2,
        SIZE_T a3,
        SIZE_T a4,
        volatile void *Address)
{
  __int64 v7; // rsi
  struct _MDL *v8; // r14
  int VsmMbpArray; // edi
  int v10; // eax
  SIZE_T v11; // rax
  struct _MDL *Mdl; // rax
  int v13; // r8d
  __int64 v14; // rax
  SIZE_T *v15; // rcx
  void *v16; // rdx
  SIZE_T v17; // rcx
  PVOID MappedSystemVa; // rax
  int v19; // r8d
  __int64 v20; // rax
  __int64 v21; // rax
  char v22; // al
  int v24; // [rsp+34h] [rbp-164h] BYREF
  int v25; // [rsp+38h] [rbp-160h] BYREF
  char v26; // [rsp+3Ch] [rbp-15Ch]
  char v27; // [rsp+3Dh] [rbp-15Bh]
  SIZE_T v28; // [rsp+40h] [rbp-158h] BYREF
  __int64 v29; // [rsp+48h] [rbp-150h] BYREF
  SIZE_T v30; // [rsp+50h] [rbp-148h]
  SIZE_T v31; // [rsp+58h] [rbp-140h] BYREF
  SIZE_T v32; // [rsp+60h] [rbp-138h] BYREF
  SIZE_T v33; // [rsp+68h] [rbp-130h] BYREF
  SIZE_T v34; // [rsp+70h] [rbp-128h]
  PMDL MemoryDescriptorList; // [rsp+78h] [rbp-120h]
  _BYTE v36[24]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v37[16]; // [rsp+A0h] [rbp-F8h] BYREF
  _BYTE v38[16]; // [rsp+B0h] [rbp-E8h] BYREF
  int *v39; // [rsp+C0h] [rbp-D8h]
  __int64 v40; // [rsp+C8h] [rbp-D0h]
  int *v41; // [rsp+D0h] [rbp-C8h]
  __int64 v42; // [rsp+D8h] [rbp-C0h]
  SIZE_T *v43; // [rsp+E0h] [rbp-B8h]
  __int64 v44; // [rsp+E8h] [rbp-B0h]
  __int64 *v45; // [rsp+F0h] [rbp-A8h]
  __int64 v46; // [rsp+F8h] [rbp-A0h]
  SIZE_T *v47; // [rsp+100h] [rbp-98h]
  __int64 v48; // [rsp+108h] [rbp-90h] BYREF
  SIZE_T *v49; // [rsp+110h] [rbp-88h]
  __int64 v50; // [rsp+118h] [rbp-80h]
  __int64 *v51; // [rsp+120h] [rbp-78h]
  __int64 v52; // [rsp+128h] [rbp-70h]
  SIZE_T *v53; // [rsp+130h] [rbp-68h]
  __int64 v54; // [rsp+138h] [rbp-60h]
  SIZE_T *v55; // [rsp+140h] [rbp-58h]
  __int64 v56; // [rsp+148h] [rbp-50h]

  v34 = a3;
  v30 = a2;
  v31 = a1;
  v32 = a2;
  v33 = a3;
  v28 = a4;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  v27 = 0;
  if ( (*(_BYTE *)(a1 + 16) & 8) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 32) & 0x31E0LL) != 0 )
    {
      VsmMbpArray = -1073741790;
      goto LABEL_33;
    }
    if ( !a4 || !Address || ((a4 + ((unsigned __int16)Address & 0xFFF) + 4095LL) & 0xFFFFFFFFFFFFF000uLL) > 0xFFFFF000 )
    {
      VsmMbpArray = -1073741811;
      goto LABEL_33;
    }
    v10 = VsmmMemoryBlockLookupByHandle(a1, a2, 0, 0, (__int64)&v29);
    v7 = v29;
    if ( v10 < 0 || (*(_DWORD *)(v29 + 264) & 1) == 0 )
    {
      VsmMbpArray = -1070137326;
      goto LABEL_33;
    }
    VidObjectLockAcquireShared(a1 + 3736);
    v26 = 1;
    v11 = *(_QWORD *)(v7 + 48);
    if ( a4 > v11 || v34 > v11 - a4 )
    {
      VsmMbpArray = -1073741811;
      goto LABEL_30;
    }
    ProbeForWrite(Address, a4, 1u);
    Mdl = IoAllocateMdl((PVOID)Address, a4, 0, 0, 0);
    v8 = Mdl;
    MemoryDescriptorList = Mdl;
    if ( Mdl )
    {
      MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
      v27 = 1;
      if ( (v8->MdlFlags & 5) != 0 )
        MappedSystemVa = v8->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000010u);
      if ( MappedSystemVa )
      {
        VsmMbpArray = VsmmVsmpQueryVsmMbpArray(v7, v34, a4, MappedSystemVa);
        if ( VsmMbpArray >= 0 )
        {
          VsmMbpArray = 0;
          goto LABEL_30;
        }
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_30;
        tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
        v25 = 952;
        v39 = &v25;
        v40 = 4;
        v24 = VsmMbpArray;
        v41 = &v24;
        v42 = 4;
        v43 = (SIZE_T *)(*(_QWORD *)(v7 + 8) + 656LL);
        v44 = 16;
        v21 = *(_QWORD *)(v7 + 8);
        v15 = *(SIZE_T **)(v21 + 128);
        LODWORD(v48) = *(unsigned __int16 *)(v21 + 120);
        v16 = &unk_14004E0C9;
      }
      else
      {
        VsmMbpArray = -1073741670;
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_30;
        tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
        v25 = 937;
        v39 = &v25;
        v40 = 4;
        v24 = v19;
        v41 = &v24;
        v42 = 4;
        v43 = (SIZE_T *)(*(_QWORD *)(v7 + 8) + 656LL);
        v44 = 16;
        v20 = *(_QWORD *)(v7 + 8);
        v15 = *(SIZE_T **)(v20 + 128);
        LODWORD(v48) = *(unsigned __int16 *)(v20 + 120);
        v16 = &unk_14004E400;
      }
    }
    else
    {
      VsmMbpArray = -1073741670;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_30;
      tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
      v24 = 914;
      v39 = &v24;
      v40 = 4;
      v25 = v13;
      v41 = &v25;
      v42 = 4;
      v43 = (SIZE_T *)(*(_QWORD *)(v7 + 8) + 656LL);
      v44 = 16;
      v14 = *(_QWORD *)(v7 + 8);
      v15 = *(SIZE_T **)(v14 + 128);
      LODWORD(v48) = *(unsigned __int16 *)(v14 + 120);
      v16 = &unk_14004E324;
    }
    v45 = &v48;
    v46 = 2;
    v47 = v15;
    HIDWORD(v48) = 0;
    v17 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 648LL);
    v49 = &v28;
    v28 = v17;
    v50 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v16, 0, 0, 10, v36);
LABEL_30:
    v22 = 1;
    goto LABEL_34;
  }
  VsmMbpArray = -1073741637;
LABEL_33:
  v22 = 0;
LABEL_34:
  if ( v22 )
    VidObjectLockRelease(a1 + 3736);
  if ( v27 )
    MmUnlockPages(v8);
  if ( v8 )
    IoFreeMdl(v8);
  if ( v7 )
  {
    if ( VsmMbpArray < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
      v25 = 976;
      v39 = &v25;
      v40 = 4;
      v24 = VsmMbpArray;
      v41 = &v24;
      v42 = 4;
      v28 = *(_QWORD *)(v7 + 24);
      v43 = &v28;
      v44 = 8;
      v33 = *(_QWORD *)(v7 + 40);
      v45 = (__int64 *)&v33;
      v46 = 8;
      v32 = *(_QWORD *)(v7 + 48);
      v47 = &v32;
      v48 = 8;
      v31 = *(int *)(v7 + 264);
      v49 = &v31;
      v50 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004E137, 0, 0, 10, v36);
    }
    VidOpCtrlFinish(v7 + 128);
  }
  if ( VsmMbpArray < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
    tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
    v25 = 986;
    v39 = &v25;
    v40 = 4;
    v24 = VsmMbpArray;
    v41 = &v24;
    v42 = 4;
    v43 = (SIZE_T *)(a1 + 656);
    v44 = 16;
    v45 = &v48;
    v46 = 2;
    v47 = *(SIZE_T **)(a1 + 128);
    v48 = *(unsigned __int16 *)(a1 + 120);
    v28 = *(_QWORD *)(a1 + 648);
    v49 = &v28;
    v50 = 8;
    v33 = v30;
    v51 = (__int64 *)&v33;
    v52 = 8;
    v32 = v34;
    v53 = &v32;
    v54 = 8;
    v31 = a4;
    v55 = &v31;
    v56 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004E1A9, 0, 0, 13, v36);
  }
  return (unsigned int)VsmMbpArray;
}

```

## disassembly

```asm
0x1400ac960  push    rbx
0x1400ac962  push    rsi
0x1400ac963  push    rdi
0x1400ac964  push    r12
0x1400ac966  push    r13
0x1400ac968  push    r14
0x1400ac96a  push    r15
0x1400ac96c  sub     rsp, 160h
0x1400ac973  mov     rax, cs:__security_cookie
0x1400ac97a  xor     rax, rsp
0x1400ac97d  mov     [rsp+198h+var_48], rax
0x1400ac985  mov     r15, r9
0x1400ac988  mov     [rsp+198h+var_128], r8
0x1400ac98d  mov     [rsp+198h+var_148], rdx
0x1400ac992  mov     r13, rcx
0x1400ac995  mov     [rsp+198h+var_140], rcx
0x1400ac99a  mov     [rsp+198h+var_138], rdx
0x1400ac99f  mov     [rsp+198h+var_130], r8
0x1400ac9a4  mov     [rsp+198h+var_158], r9
0x1400ac9a9  mov     rdi, [rsp+198h+Address]
0x1400ac9b1  xor     ebx, ebx
0x1400ac9b3  mov     esi, ebx
0x1400ac9b5  mov     [rsp+198h+var_150], rbx
0x1400ac9ba  mov     r14d, ebx
0x1400ac9bd  mov     [rsp+198h+var_15B], bl
0x1400ac9c1  lea     r12d, [rbx+8]
0x1400ac9c5  test    [rcx+10h], r12b
0x1400ac9c9  jnz     short loc_1400AC9D5
0x1400ac9cb  mov     edi, 0C00000BBh
0x1400ac9d0  jmp     loc_1400AD17C
0x1400ac9d5  mov     eax, [rcx+20h]
0x1400ac9d8  test    rax, 31E0h
0x1400ac9de  jz      short loc_1400AC9EA
0x1400ac9e0  mov     edi, 0C0000022h
0x1400ac9e5  jmp     loc_1400AD17C
0x1400ac9ea  test    r15, r15
0x1400ac9ed  jz      loc_1400AD177
0x1400ac9f3  test    rdi, rdi
0x1400ac9f6  jz      loc_1400AD177
0x1400ac9fc  mov     ecx, edi
0x1400ac9fe  and     ecx, 0FFFh
0x1400aca04  add     rcx, 0FFFh
0x1400aca0b  add     rcx, r15
0x1400aca0e  and     rcx, 0FFFFFFFFFFFFF000h
0x1400aca15  mov     eax, 0FFFFF000h
0x1400aca1a  cmp     rcx, rax
0x1400aca1d  ja      loc_1400AD177
0x1400aca23  lea     rax, [rsp+198h+var_150]
0x1400aca28  mov     [rsp+198h+Irp], rax
0x1400aca2d  xor     r9d, r9d
0x1400aca30  xor     r8d, r8d
0x1400aca33  mov     rcx, r13
0x1400aca36  call    VsmmMemoryBlockLookupByHandle
0x1400aca3b  mov     rsi, [rsp+198h+var_150]
0x1400aca40  test    eax, eax
0x1400aca42  js      loc_1400AD170
0x1400aca48  mov     eax, [rsi+108h]
0x1400aca4e  test    al, 1
0x1400aca50  jz      loc_1400AD170
0x1400aca56  lea     rcx, [r13+0E98h]
0x1400aca5d  call    VidObjectLockAcquireShared
0x1400aca62  mov     al, 1
0x1400aca64  mov     [rsp+198h+var_168], al
0x1400aca68  mov     [rsp+198h+var_15C], al
0x1400aca6c  mov     rax, [rsi+30h]
0x1400aca70  cmp     r15, rax
0x1400aca73  ja      loc_1400AD165
0x1400aca79  sub     rax, r15
0x1400aca7c  cmp     [rsp+198h+var_128], rax
0x1400aca81  ja      loc_1400AD165
0x1400aca87  mov     r8d, 1; Alignment
0x1400aca8d  mov     rdx, r15; Length
0x1400aca90  mov     rcx, rdi; Address
0x1400aca93  call    cs:__imp_ProbeForWrite
0x1400aca9a  nop     dword ptr [rax+rax+00h]
0x1400aca9f  nop
0x1400acaa0  mov     edx, r15d; Length
0x1400acaa3  mov     [rsp+198h+Irp], rbx; Irp
0x1400acaa8  xor     r9d, r9d; ChargeQuota
0x1400acaab  xor     r8d, r8d; SecondaryBuffer
0x1400acaae  mov     rcx, rdi; VirtualAddress
0x1400acab1  call    cs:__imp_IoAllocateMdl
0x1400acab8  nop     dword ptr [rax+rax+00h]
0x1400acabd  mov     r14, rax
0x1400acac0  mov     [rsp+198h+MemoryDescriptorList], rax
0x1400acac5  test    rax, rax
0x1400acac8  jnz     loc_1400ACC21
0x1400acace  mov     r8d, 0C000009Ah
0x1400acad4  mov     edi, r8d
0x1400acad7  mov     ecx, cs:dword_140065110
0x1400acadd  cmp     ecx, 2
0x1400acae0  jbe     loc_1400AD16A
0x1400acae6  mov     edx, 100h
0x1400acaeb  lea     rcx, dword_140065110
0x1400acaf2  call    _tlgKeywordOn
0x1400acaf7  test    al, al
0x1400acaf9  jz      loc_1400AD16A
0x1400acaff  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400acb06  lea     rcx, [rsp+198h+var_F8]
0x1400acb0e  call    _tlgCreate1Sz_char
0x1400acb13  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400acb1a  lea     rcx, [rsp+198h+var_E8]
0x1400acb22  call    _tlgCreate1Sz_char
0x1400acb27  mov     [rsp+198h+var_164], 392h
0x1400acb2f  lea     rax, [rsp+198h+var_164]
0x1400acb34  mov     [rsp+198h+var_D8], rax
0x1400acb3c  mov     [rsp+198h+var_D0], 4
0x1400acb48  mov     [rsp+198h+var_160], r8d
0x1400acb4d  lea     rax, [rsp+198h+var_160]
0x1400acb52  mov     [rsp+198h+var_C8], rax
0x1400acb5a  mov     [rsp+198h+var_C0], 4
0x1400acb66  mov     rax, [rsi+8]
0x1400acb6a  add     rax, 290h
0x1400acb70  mov     [rsp+198h+var_B8], rax
0x1400acb78  mov     [rsp+198h+var_B0], 10h
0x1400acb84  mov     rax, [rsi+8]
0x1400acb88  movzx   edx, word ptr [rax+78h]
0x1400acb8c  mov     rcx, [rax+80h]
0x1400acb93  mov     dword ptr [rsp+198h+var_90], edx
0x1400acb9a  lea     rdx, unk_14004E324
0x1400acba1  lea     rax, [rsp+198h+var_90]
0x1400acba9  mov     [rsp+198h+var_A8], rax
0x1400acbb1  mov     [rsp+198h+var_A0], 2
0x1400acbbd  mov     [rsp+198h+var_98], rcx
0x1400acbc5  mov     dword ptr [rsp+198h+var_90+4], ebx
0x1400acbcc  mov     rax, [rsi+8]
0x1400acbd0  mov     rcx, [rax+288h]
0x1400acbd7  lea     rax, [rsp+198h+var_158]
0x1400acbdc  mov     [rsp+198h+var_88], rax
0x1400acbe4  lea     rax, [rsp+198h+var_118]
0x1400acbec  mov     qword ptr [rsp+198h+Priority], rax
0x1400acbf1  xor     r9d, r9d
0x1400acbf4  mov     [rsp+198h+var_158], rcx
0x1400acbf9  mov     [rsp+198h+var_80], 8
0x1400acc05  mov     dword ptr [rsp+198h+Irp], 0Ah
0x1400acc0d  xor     r8d, r8d
0x1400acc10  lea     rcx, dword_140065110
0x1400acc17  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400acc1c  jmp     loc_1400AD16A
0x1400acc21  mov     edi, 1
0x1400acc26  mov     r8d, edi; Operation
0x1400acc29  xor     edx, edx; AccessMode
0x1400acc2b  mov     rcx, r14; MemoryDescriptorList
0x1400acc2e  call    cs:__imp_MmProbeAndLockPages
0x1400acc35  nop     dword ptr [rax+rax+00h]
0x1400acc3a  mov     [rsp+198h+var_15B], dil
0x1400acc3f  test    byte ptr [r14+0Ah], 5
0x1400acc44  jz      short loc_1400ACC4C
0x1400acc46  mov     rax, [r14+18h]
0x1400acc4a  jmp     short loc_1400ACC6F
0x1400acc4c  mov     [rsp+198h+Priority], 40000010h; Priority
0x1400acc54  mov     dword ptr [rsp+198h+Irp], ebx; BugCheckOnFailure
0x1400acc58  xor     r9d, r9d; RequestedAddress
0x1400acc5b  mov     r8d, edi; CacheType
0x1400acc5e  xor     edx, edx; AccessMode
0x1400acc60  mov     rcx, r14; MemoryDescriptorList
0x1400acc63  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400acc6a  nop     dword ptr [rax+rax+00h]
0x1400acc6f  test    rax, rax
0x1400acc72  jnz     loc_1400ACD50
0x1400acc78  mov     r8d, 0C000009Ah
0x1400acc7e  mov     edi, r8d
0x1400acc81  mov     eax, cs:dword_140065110
0x1400acc87  cmp     eax, 2
0x1400acc8a  jbe     loc_1400AD16A
0x1400acc90  mov     edx, 100h
0x1400acc95  lea     rcx, dword_140065110
0x1400acc9c  call    _tlgKeywordOn
0x1400acca1  test    al, al
0x1400acca3  jz      loc_1400AD16A
0x1400acca9  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400accb0  lea     rcx, [rsp+198h+var_F8]
0x1400accb8  call    _tlgCreate1Sz_char
0x1400accbd  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400accc4  lea     rcx, [rsp+198h+var_E8]
0x1400acccc  call    _tlgCreate1Sz_char
0x1400accd1  mov     [rsp+198h+var_160], 3A9h
0x1400accd9  lea     rax, [rsp+198h+var_160]
0x1400accde  mov     [rsp+198h+var_D8], rax
0x1400acce6  mov     [rsp+198h+var_D0], 4
0x1400accf2  mov     [rsp+198h+var_164], r8d
0x1400accf7  lea     rax, [rsp+198h+var_164]
0x1400accfc  mov     [rsp+198h+var_C8], rax
0x1400acd04  mov     [rsp+198h+var_C0], 4
0x1400acd10  mov     rax, [rsi+8]
0x1400acd14  add     rax, 290h
0x1400acd1a  mov     [rsp+198h+var_B8], rax
0x1400acd22  mov     [rsp+198h+var_B0], 10h
0x1400acd2e  mov     rax, [rsi+8]
0x1400acd32  movzx   edx, word ptr [rax+78h]
0x1400acd36  mov     rcx, [rax+80h]
0x1400acd3d  mov     dword ptr [rsp+198h+var_90], edx
0x1400acd44  lea     rdx, unk_14004E400
0x1400acd4b  jmp     loc_1400ACBA1
0x1400acd50  mov     r9, rax
0x1400acd53  mov     r8, r15
0x1400acd56  mov     rdx, [rsp+198h+var_128]
0x1400acd5b  mov     rcx, rsi
0x1400acd5e  call    VsmmVsmpQueryVsmMbpArray
0x1400acd63  mov     edi, eax
0x1400acd65  test    eax, eax
0x1400acd67  jns     loc_1400ACE3B
0x1400acd6d  mov     ecx, cs:dword_140065110
0x1400acd73  cmp     ecx, 2
0x1400acd76  jbe     loc_1400AD16A
0x1400acd7c  mov     edx, 100h
0x1400acd81  lea     rcx, dword_140065110
0x1400acd88  call    _tlgKeywordOn
0x1400acd8d  test    al, al
0x1400acd8f  jz      loc_1400AD16A
0x1400acd95  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400acd9c  lea     rcx, [rsp+198h+var_F8]
0x1400acda4  call    _tlgCreate1Sz_char
0x1400acda9  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400acdb0  lea     rcx, [rsp+198h+var_E8]
0x1400acdb8  call    _tlgCreate1Sz_char
0x1400acdbd  mov     [rsp+198h+var_160], 3B8h
0x1400acdc5  lea     rax, [rsp+198h+var_160]
0x1400acdca  mov     [rsp+198h+var_D8], rax
0x1400acdd2  mov     [rsp+198h+var_D0], 4
0x1400acdde  mov     [rsp+198h+var_164], edi
0x1400acde2  lea     rax, [rsp+198h+var_164]
0x1400acde7  mov     [rsp+198h+var_C8], rax
0x1400acdef  mov     [rsp+198h+var_C0], 4
0x1400acdfb  mov     rax, [rsi+8]
0x1400acdff  add     rax, 290h
0x1400ace05  mov     [rsp+198h+var_B8], rax
0x1400ace0d  mov     [rsp+198h+var_B0], 10h
0x1400ace19  mov     rax, [rsi+8]
0x1400ace1d  movzx   edx, word ptr [rax+78h]
0x1400ace21  mov     rcx, [rax+80h]
0x1400ace28  mov     dword ptr [rsp+198h+var_90], edx
0x1400ace2f  lea     rdx, unk_14004E0C9
0x1400ace36  jmp     loc_1400ACBA1
0x1400ace3b  mov     edi, ebx
0x1400ace3d  jmp     loc_1400AD16A
0x1400ace42  mov     edi, eax
0x1400ace44  mov     eax, cs:dword_140065110
0x1400ace4a  cmp     eax, 2
0x1400ace4d  jbe     loc_1400ACFA3
0x1400ace53  mov     edx, 100h
0x1400ace58  lea     rcx, dword_140065110
0x1400ace5f  call    _tlgKeywordOn
0x1400ace64  test    al, al
0x1400ace66  jz      loc_1400ACFA3
0x1400ace6c  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400ace73  lea     rcx, [rsp+198h+var_F8]
0x1400ace7b  call    _tlgCreate1Sz_char
0x1400ace80  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ace87  lea     rcx, [rsp+198h+var_E8]
0x1400ace8f  call    _tlgCreate1Sz_char
0x1400ace94  mov     [rsp+198h+var_160], 39Eh
0x1400ace9c  lea     rax, [rsp+198h+var_160]
0x1400acea1  mov     [rsp+198h+var_D8], rax
0x1400acea9  mov     [rsp+198h+var_D0], 4
0x1400aceb5  mov     [rsp+198h+var_164], edi
0x1400aceb9  lea     rax, [rsp+198h+var_164]
0x1400acebe  mov     [rsp+198h+var_C8], rax
0x1400acec6  mov     [rsp+198h+var_C0], 4
0x1400aced2  mov     rsi, [rsp+198h+var_150]
0x1400aced7  mov     rax, [rsi+8]
0x1400acedb  add     rax, 290h
0x1400acee1  mov     [rsp+198h+var_B8], rax
0x1400acee9  mov     [rsp+198h+var_B0], 10h
0x1400acef5  mov     r8d, 7
0x1400acefb  mov     rax, [rsi+8]
0x1400aceff  movzx   edx, word ptr [rax+78h]
0x1400acf03  mov     rcx, [rax+80h]
0x1400acf0a  mov     eax, r8d
0x1400acf0d  shl     rax, 4
0x1400acf11  lea     r9, [rsp+198h+var_100]
0x1400acf19  add     rax, r9
0x1400acf1c  mov     [rsp+198h+var_A8], rax
0x1400acf24  mov     [rsp+198h+var_A0], 2
0x1400acf30  mov     [rsp+198h+var_98], rcx
0x1400acf38  mov     dword ptr [rsp+198h+var_90], edx
0x1400acf3f  mov     dword ptr [rsp+198h+var_90+4], 0
0x1400acf4a  mov     rax, [rsi+8]
0x1400acf4e  mov     rcx, [rax+288h]
0x1400acf55  mov     [rsp+198h+var_148], rcx
0x1400acf5a  lea     rax, [rsp+198h+var_148]
0x1400acf5f  mov     [rsp+198h+var_88], rax
0x1400acf67  mov     [rsp+198h+var_80], 8
0x1400acf73  lea     eax, [r8+3]
0x1400acf77  lea     rcx, [rsp+198h+var_118]
0x1400acf7f  mov     qword ptr [rsp+198h+Priority], rcx
0x1400acf84  mov     dword ptr [rsp+198h+Irp], eax
0x1400acf88  xor     r9d, r9d
0x1400acf8b  xor     r8d, r8d
0x1400acf8e  lea     rdx, unk_14004E392
0x1400acf95  lea     rcx, dword_140065110
0x1400acf9c  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400acfa1  jmp     short loc_1400ACFA8
0x1400acfa3  mov     rsi, [rsp+198h+var_150]
0x1400acfa8  xor     ebx, ebx
0x1400acfaa  mov     r14, [rsp+198h+MemoryDescriptorList]
0x1400acfaf  mov     al, [rsp+198h+var_15C]
0x1400acfb3  mov     r13, [rsp+198h+var_140]
0x1400acfb8  mov     rdx, [rsp+198h+var_138]
0x1400acfbd  mov     [rsp+198h+var_148], rdx
  ... truncated ...
```
