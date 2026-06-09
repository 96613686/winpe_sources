# VidCreateResourcePartition

- ea: `0x1400925c0`
- end: `0x140092ff5`
- name: `VidCreateResourcePartition`
- size: `2613`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x1400071a4`
- `0x140007dbc`
- `0x14000a010`
- `0x140021c60`
- `0x1400309d0`
- `0x140033b00`
- `0x1400778d4`
- `0x140077958`
- `0x1400925c0`
- `0x140095644`
- `0x1400959e8`
- `0x140095c48`
- `0x1400cd8b4`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x140092ec5`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140092ec5`
- `ntoskrnl!KeReadStateEvent` at `0x140092c12`
- `ntoskrnl!KeReadStateEvent` at `0x140092c12`
- `ntoskrnl!KeSetEvent` at `0x140092cf0`
- `ntoskrnl!KeSetEvent` at `0x140092cf0`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400927a3`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400927c8`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400927a3`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400927c8`

## string_xrefs

- `0x140092710`: `VidCreateResourcePartition`
- `0x14009280d`: `VidCreateResourcePartition`
- `0x1400928e5`: `VidCreateResourcePartition`
- `0x140092968`: `VidCreateResourcePartition`
- `0x1400929f8`: `VidCreateResourcePartition`
- `0x140092aa2`: `VidCreateResourcePartition`
- `0x140092b81`: `VidCreateResourcePartition`
- `0x140092c53`: `VidCreateResourcePartition`
- `0x140092d37`: `VidCreateResourcePartition`
- `0x140092dae`: `VidCreateResourcePartition`
- `0x140092f06`: `VidCreateResourcePartition`

## pseudocode

```c
__int64 __fastcall VidCreateResourcePartition(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rsi
  unsigned int v6; // r12d
  __int64 *v7; // rdi
  int v8; // edi
  char *v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // rcx
  unsigned int v14; // r15d
  __int64 v15; // r9
  void *v16; // rdx
  __int64 *v17; // rax
  __int64 JobMemoryPartition; // rax
  void *v19; // rcx
  int v20; // r8d
  char *v21; // r14
  __int64 v22; // rdi
  __int64 v23; // r8
  void *v24; // rdx
  int v25; // r8d
  int v26; // r8d
  int v27; // r8d
  unsigned __int64 *v28; // rsi
  unsigned __int64 v29; // rdi
  int v30; // r14d
  __int64 v31; // rcx
  _QWORD *v32; // rax
  unsigned __int64 v33; // rcx
  int v35; // [rsp+20h] [rbp-A9h]
  __int64 v36; // [rsp+30h] [rbp-99h] BYREF
  __int64 v37; // [rsp+38h] [rbp-91h] BYREF
  __int64 *v38; // [rsp+40h] [rbp-89h] BYREF
  __int128 v39; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v40[32]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v41[16]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v42[16]; // [rsp+90h] [rbp-39h] BYREF
  __int64 *v43; // [rsp+A0h] [rbp-29h]
  __int64 v44; // [rsp+A8h] [rbp-21h]
  __int64 *v45; // [rsp+B0h] [rbp-19h]
  __int64 v46; // [rsp+B8h] [rbp-11h]
  __int128 *v47; // [rsp+C0h] [rbp-9h]
  __int64 v48; // [rsp+C8h] [rbp-1h]
  __int64 *v49; // [rsp+D0h] [rbp+7h]
  __int64 v50; // [rsp+D8h] [rbp+Fh]

  v37 = a4;
  v4 = a4;
  v38 = a1;
  v6 = a2;
  v7 = a1;
  if ( (a4 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    return (unsigned int)-1073741811;
  v9 = (char *)VidDeviceExtension;
  LOBYTE(a2) = 1;
  v11 = VidResourcePartitionpAllocate(a1, a2);
  if ( !v11 )
    return (unsigned int)-1073741670;
  v13 = 0;
  v14 = 0;
  v36 = 0;
  if ( !v6 )
  {
LABEL_39:
    if ( (v4 & 2) != 0 )
    {
      if ( !*(_QWORD *)(v11 + 96) )
      {
        v8 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v37) = 1802;
          v43 = &v37;
          v16 = &unk_140048746;
          v45 = &v36;
          v47 = (__int128 *)(v11 + 8);
          LODWORD(v38) = *(_DWORD *)(a3 + 24LL * v14);
          v17 = (__int64 *)&v38;
LABEL_26:
          LODWORD(v36) = v20;
LABEL_27:
          v15 = 0;
LABEL_28:
          v49 = v17;
          v50 = 4;
          v48 = 16;
          v46 = 4;
          v44 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v16, 0, v15, 8, v40);
        }
        goto LABEL_91;
      }
      *(_DWORD *)(v11 + 56) |= 1u;
    }
    v21 = v9 + 1640;
    *(_QWORD *)&v39 = v9 + 1640;
    VidLockAcquireShared(v9 + 1640, v10, v12, 0);
    VidPushLockAcquireExclusive(v9 + 2200);
    v22 = VidResourcePartitionFindById(v9 + 2200, v7);
    if ( v22 )
    {
      if ( (v4 & 1) == 0 )
      {
        v8 = -1073741771;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v37) = 1831;
          v24 = &unk_14004868C;
          LODWORD(v36) = -1073741771;
LABEL_50:
          v43 = &v37;
          v45 = &v36;
          v47 = (__int128 *)(v11 + 8);
          v35 = 7;
LABEL_51:
          v48 = 16;
          v46 = 4;
          v44 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v24, 0, 0, v35, v40);
          goto LABEL_90;
        }
        goto LABEL_90;
      }
      if ( KeReadStateEvent(*(PRKEVENT *)(v22 + 24)) )
      {
        v8 = -1073741436;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v37) = 1842;
          v24 = &unk_1400485E2;
          LODWORD(v36) = v25;
          goto LABEL_50;
        }
LABEL_90:
        VidPushLockRelease(v9 + 2200);
        VidLockRelease(v21);
        if ( v11 )
          goto LABEL_91;
        return (unsigned int)v8;
      }
      *(_OWORD *)(v22 + 60) = *(_OWORD *)(v11 + 60);
      *(_QWORD *)(v22 + 80) = *(_QWORD *)(v11 + 80);
      *(_QWORD *)(v22 + 88) = *(_QWORD *)(v11 + 88);
      *(_QWORD *)(v22 + 96) = *(_QWORD *)(v11 + 96);
      *(_QWORD *)(v22 + 104) = *(_QWORD *)(v11 + 104);
      *(_QWORD *)(v22 + 112) = *(_QWORD *)(v11 + 112);
      *(_QWORD *)(v22 + 120) = *(_QWORD *)(v11 + 120);
      *(_DWORD *)(v22 + 56) = *(_DWORD *)(v11 + 56);
      *(_QWORD *)(v11 + 80) = 0;
      *(_QWORD *)(v11 + 88) = 0;
      *(_QWORD *)(v11 + 96) = 0;
      *(_QWORD *)(v11 + 104) = 0;
      *(_QWORD *)(v11 + 112) = 0;
      *(_QWORD *)(v11 + 120) = 0;
      *(_DWORD *)(v11 + 56) = 0;
      KeSetEvent(*(PRKEVENT *)(v22 + 24), 0, 0);
    }
    else
    {
      if ( (v4 & 1) != 0 )
      {
        v8 = -1073741436;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v37) = 1861;
          v24 = &unk_140048637;
          LODWORD(v36) = v26;
          goto LABEL_50;
        }
        goto LABEL_90;
      }
      if ( *((_DWORD *)v9 + 409) )
      {
        v8 = -1073741436;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v37) = 1876;
          v43 = &v37;
          v24 = &unk_14004856A;
          LODWORD(v36) = v27;
          v45 = &v36;
          v47 = (__int128 *)(v11 + 8);
          v38 = (__int64 *)*((int *)v9 + 409);
          v49 = (__int64 *)&v38;
          v35 = 8;
          v50 = 8;
          goto LABEL_51;
        }
        goto LABEL_90;
      }
      v28 = (unsigned __int64 *)(v9 + 2208);
      if ( (v9[2216] & 1) != 0 )
      {
        if ( *v28 )
          v29 = *v28 ^ (unsigned __int64)v28;
        else
          v29 = 0;
      }
      else
      {
        v29 = *v28;
      }
      LOBYTE(v23) = 0;
      v30 = v9[2216] & 1;
      if ( v29 )
      {
        while ( 1 )
        {
          if ( (int)VidResourcePartitionCompareById(v11 + 8, v29, v23) < 0 )
          {
            v33 = *(_QWORD *)v29;
            if ( v30 && v33 )
              v32 = (_QWORD *)(v33 ^ v29);
            else
              v32 = *(_QWORD **)v29;
            if ( !v32 )
            {
              LOBYTE(v23) = 0;
              break;
            }
          }
          else
          {
            v31 = *(_QWORD *)(v29 + 8);
            if ( v30 && v31 )
              v32 = (_QWORD *)(v31 ^ v29);
            else
              v32 = *(_QWORD **)(v29 + 8);
            if ( !v32 )
            {
              LOBYTE(v23) = 1;
              break;
            }
          }
          v29 = (unsigned __int64)v32;
        }
      }
      RtlRbInsertNodeEx(v9 + 2208, v29, v23, v11 + 32);
      v4 = v37;
      v11 = 0;
      v21 = (char *)v39;
    }
    if ( (unsigned int)dword_140065110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
      tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      LODWORD(v37) = 1893;
      v43 = &v37;
      v45 = v38;
      *(_QWORD *)&v39 = v36;
      v47 = &v39;
      v49 = &v36;
      v44 = 4;
      v46 = 16;
      v48 = 8;
      v36 = v4;
      v50 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_140048508, 0, 0, 8, v40);
    }
    v8 = 0;
    goto LABEL_90;
  }
  while ( 1 )
  {
    v12 = *(int *)(a3 + 24LL * v14);
    v36 = v13 | (1LL << v12);
    if ( !(_DWORD)v12 )
    {
      v39 = 0;
      if ( !*(_OWORD *)(a3 + 24LL * v14 + 8) )
      {
        v8 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v38) = 1678;
          v43 = (__int64 *)&v38;
          v16 = &unk_140048875;
          v45 = &v36;
          v47 = (__int128 *)(v11 + 8);
          LODWORD(v37) = *(_DWORD *)(a3 + 24LL * v14);
          v17 = &v37;
          goto LABEL_26;
        }
        goto LABEL_91;
      }
      *(_OWORD *)(v11 + 60) = *(_OWORD *)(a3 + 24LL * v14 + 8);
      goto LABEL_9;
    }
    if ( !*(_QWORD *)(a3 + 24LL * v14 + 8) )
      break;
    switch ( (_DWORD)v12 )
    {
      case 1:
        v19 = *(void **)(a3 + 24LL * v14 + 8);
        *(_QWORD *)(v11 + 80) = v19;
        ObfReferenceObjectWithTag(v19, 0x72446456u);
        break;
      case 2:
        JobMemoryPartition = VsmmNtSlatGetJobMemoryPartition(*(_QWORD *)(a3 + 24LL * v14 + 8), v10, v12, 0);
        if ( JobMemoryPartition )
        {
          v8 = VidResourcePartitionpSetMemoryPartitionComponent(v11, JobMemoryPartition, 4);
          if ( v8 < 0 )
          {
            if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
            {
              tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
              tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
              LODWORD(v37) = 1741;
              v43 = &v37;
              v16 = &unk_1400487AB;
              LODWORD(v36) = v8;
              v45 = &v36;
              v47 = (__int128 *)(v11 + 8);
              LODWORD(v38) = *(_DWORD *)(a3 + 24LL * v14);
              v17 = (__int64 *)&v38;
              goto LABEL_27;
            }
            goto LABEL_91;
          }
        }
        ObfReferenceObjectWithTag(*(PVOID *)(a3 + 24LL * v14 + 8), 0x72446456u);
        *(_QWORD *)(v11 + 88) = *(_QWORD *)(a3 + 24LL * v14 + 8);
        break;
      case 3:
        v8 = VidResourcePartitionpSetMemoryPartitionComponent(v11, *(_QWORD *)(a3 + 24LL * v14 + 8), v12);
        if ( v8 < 0 )
        {
          if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          {
            tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
            tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
            LODWORD(v37) = 1769;
            v43 = &v37;
            v16 = &unk_140048810;
            LODWORD(v36) = v8;
            v45 = &v36;
            v47 = (__int128 *)(v11 + 8);
            LODWORD(v38) = *(_DWORD *)(a3 + 24LL * v14);
            v17 = (__int64 *)&v38;
            goto LABEL_28;
          }
          goto LABEL_91;
        }
        break;
      default:
        v8 = -1073741811;
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v37) = 1788;
          v43 = &v37;
          v16 = &unk_1400486E1;
          v45 = &v36;
          v47 = (__int128 *)(v11 + 8);
          LODWORD(v38) = *(_DWORD *)(a3 + 24LL * v14);
          v17 = (__int64 *)&v38;
          goto LABEL_26;
        }
        goto LABEL_91;
    }
LABEL_9:
    if ( ++v14 >= v6 )
    {
      v4 = v37;
      v7 = v38;
      goto LABEL_39;
    }
    v13 = v36;
  }
  v8 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v41, "VidCreateResourcePartition");
    tlgCreate1Sz_char(v42, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
    LODWORD(v37) = 1694;
    v43 = &v37;
    v16 = &unk_1400488DA;
    v45 = &v36;
    v47 = (__int128 *)(v11 + 8);
    LODWORD(v38) = *(_DWORD *)(a3 + 24LL * v14);
    v17 = (__int64 *)&v38;
    goto LABEL_26;
  }
LABEL_91:
  VidResourcePartitionpFree((PVOID)v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400925c0  mov     [rsp-8+arg_8], rbx
0x1400925c5  push    rbp
0x1400925c6  push    rsi
0x1400925c7  push    rdi
0x1400925c8  push    r12
0x1400925ca  push    r13
0x1400925cc  push    r14
0x1400925ce  push    r15
0x1400925d0  lea     rbp, [rsp-27h]
0x1400925d5  sub     rsp, 0F0h
0x1400925dc  mov     rax, cs:__security_cookie
0x1400925e3  xor     rax, rsp
0x1400925e6  mov     [rbp+57h+var_40], rax
0x1400925ea  mov     [rsp+120h+var_E8], r9
0x1400925ef  mov     rsi, r9
0x1400925f2  mov     [rsp+120h+var_E0], rcx
0x1400925f7  mov     r14, r8
0x1400925fa  mov     r12d, edx
0x1400925fd  mov     rdi, rcx
0x140092600  test    r9, 0FFFFFFFFFFFFFFFCh
0x140092607  jz      short loc_140092613
0x140092609  mov     edi, 0C000000Dh
0x14009260e  jmp     loc_140092FCB
0x140092613  mov     r13, cs:VidDeviceExtension
0x14009261a  mov     dl, 1
0x14009261c  call    VidResourcePartitionpAllocate
0x140092621  xor     r9d, r9d
0x140092624  mov     rbx, rax
0x140092627  test    rax, rax
0x14009262a  jnz     short loc_140092636
0x14009262c  mov     edi, 0C000009Ah
0x140092631  jmp     loc_140092FCB
0x140092636  mov     rcx, r9
0x140092639  mov     r15d, r9d
0x14009263c  mov     [rsp+120h+var_F0], rcx
0x140092641  test    r12d, r12d
0x140092644  jz      loc_140092A5D
0x14009264a  mov     eax, r15d
0x14009264d  lea     rsi, [rax+rax*2]
0x140092651  movsxd  r8, dword ptr [r14+rsi*8]
0x140092655  bts     rcx, r8
0x140092659  mov     [rsp+120h+var_F0], rcx
0x14009265e  test    r8d, r8d
0x140092661  jnz     short loc_1400926A4
0x140092663  xorps   xmm0, xmm0
0x140092666  movq    rax, xmm0
0x14009266b  movups  [rsp+120h+var_D8], xmm0
0x140092670  cmp     [r14+rsi*8+8], rax
0x140092675  jnz     short loc_140092686
0x140092677  mov     rax, [r14+rsi*8+10h]
0x14009267c  cmp     rax, qword ptr [rbp+57h+var_D8+8]
0x140092680  jz      loc_1400927DC
0x140092686  movups  xmm0, xmmword ptr [r14+rsi*8+8]
0x14009268c  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x140092691  inc     r15d
0x140092694  cmp     r15d, r12d
0x140092697  jnb     loc_140092A53
0x14009269d  mov     rcx, [rsp+120h+var_F0]
0x1400926a2  jmp     short loc_14009264A
0x1400926a4  cmp     [r14+rsi*8+8], r9
0x1400926a9  jz      loc_1400929C7
0x1400926af  mov     ecx, r8d
0x1400926b2  test    r8d, r8d
0x1400926b5  jz      short loc_140092686
0x1400926b7  sub     ecx, 1
0x1400926ba  jz      loc_1400927BA
0x1400926c0  sub     ecx, 1
0x1400926c3  jz      loc_14009276F
0x1400926c9  cmp     ecx, 1
0x1400926cc  jnz     loc_1400928B4
0x1400926d2  mov     rdx, [r14+rsi*8+8]
0x1400926d7  mov     rcx, rbx
0x1400926da  call    VidResourcePartitionpSetMemoryPartitionComponent
0x1400926df  xor     r9d, r9d
0x1400926e2  mov     edi, eax
0x1400926e4  test    eax, eax
0x1400926e6  jns     short loc_140092691
0x1400926e8  mov     eax, cs:dword_140065110
0x1400926ee  cmp     eax, 2
0x1400926f1  jbe     loc_140092FC3
0x1400926f7  mov     edx, 100h
0x1400926fc  lea     rcx, dword_140065110
0x140092703  call    _tlgKeywordOn
0x140092708  test    al, al
0x14009270a  jz      loc_140092FC3
0x140092710  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x140092717  lea     rcx, [rbp+57h+var_A0]
0x14009271b  call    _tlgCreate1Sz_char
0x140092720  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140092727  lea     rcx, [rbp+57h+var_90]
0x14009272b  call    _tlgCreate1Sz_char
0x140092730  lea     rax, [rsp+120h+var_E8]
0x140092735  mov     dword ptr [rsp+120h+var_E8], 6E9h
0x14009273d  mov     [rbp+57h+var_80], rax
0x140092741  lea     rdx, unk_140048810
0x140092748  lea     rax, [rsp+120h+var_F0]
0x14009274d  mov     dword ptr [rsp+120h+var_F0], edi
0x140092751  mov     [rbp+57h+var_70], rax
0x140092755  lea     rax, [rbx+8]
0x140092759  mov     [rbp+57h+var_60], rax
0x14009275d  mov     eax, [r14+rsi*8]
0x140092761  mov     dword ptr [rsp+120h+var_E0], eax
0x140092765  lea     rax, [rsp+120h+var_E0]
0x14009276a  jmp     loc_14009286B
0x14009276f  mov     rcx, [r14+rsi*8+8]
0x140092774  call    VsmmNtSlatGetJobMemoryPartition
0x140092779  test    rax, rax
0x14009277c  jz      short loc_140092799
0x14009277e  mov     r8d, 4
0x140092784  mov     rdx, rax
0x140092787  mov     rcx, rbx
0x14009278a  call    VidResourcePartitionpSetMemoryPartitionComponent
0x14009278f  mov     edi, eax
0x140092791  test    eax, eax
0x140092793  js      loc_140092940
0x140092799  mov     rcx, [r14+rsi*8+8]; Object
0x14009279e  mov     edx, 72446456h; Tag
0x1400927a3  call    cs:__imp_ObfReferenceObjectWithTag
0x1400927aa  nop     dword ptr [rax+rax+00h]
0x1400927af  mov     rax, [r14+rsi*8+8]
0x1400927b4  mov     [rbx+58h], rax
0x1400927b8  jmp     short loc_1400927D4
0x1400927ba  mov     rcx, [r14+rsi*8+8]; Object
0x1400927bf  mov     edx, 72446456h; Tag
0x1400927c4  mov     [rbx+50h], rcx
0x1400927c8  call    cs:__imp_ObfReferenceObjectWithTag
0x1400927cf  nop     dword ptr [rax+rax+00h]
0x1400927d4  xor     r9d, r9d
0x1400927d7  jmp     loc_140092691
0x1400927dc  mov     eax, cs:dword_140065110
0x1400927e2  mov     r8d, 0C000000Dh
0x1400927e8  mov     edi, r8d
0x1400927eb  cmp     eax, 2
0x1400927ee  jbe     loc_140092FC3
0x1400927f4  mov     edx, 100h
0x1400927f9  lea     rcx, dword_140065110
0x140092800  call    _tlgKeywordOn
0x140092805  test    al, al
0x140092807  jz      loc_140092FC3
0x14009280d  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x140092814  lea     rcx, [rbp+57h+var_A0]
0x140092818  call    _tlgCreate1Sz_char
0x14009281d  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140092824  lea     rcx, [rbp+57h+var_90]
0x140092828  call    _tlgCreate1Sz_char
0x14009282d  lea     rax, [rsp+120h+var_E0]
0x140092832  mov     dword ptr [rsp+120h+var_E0], 68Eh
0x14009283a  mov     [rbp+57h+var_80], rax
0x14009283e  lea     rdx, unk_140048875
0x140092845  lea     rax, [rsp+120h+var_F0]
0x14009284a  mov     [rbp+57h+var_70], rax
0x14009284e  lea     rax, [rbx+8]
0x140092852  mov     [rbp+57h+var_60], rax
0x140092856  mov     eax, [r14+rsi*8]
0x14009285a  mov     dword ptr [rsp+120h+var_E8], eax
0x14009285e  lea     rax, [rsp+120h+var_E8]
0x140092863  mov     dword ptr [rsp+120h+var_F0], r8d
0x140092868  xor     r9d, r9d
0x14009286b  mov     [rbp+57h+var_50], rax
0x14009286f  lea     rcx, dword_140065110
0x140092876  lea     rax, [rbp+57h+var_C0]
0x14009287a  mov     [rbp+57h+var_48], 4
0x140092882  mov     [rsp+120h+var_F8], rax
0x140092887  xor     r8d, r8d
0x14009288a  mov     [rsp+120h+var_100], 8
0x140092892  mov     [rbp+57h+var_58], 10h
0x14009289a  mov     [rbp+57h+var_68], 4
0x1400928a2  mov     [rbp+57h+var_78], 4
0x1400928aa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400928af  jmp     loc_140092FC3
0x1400928b4  mov     eax, cs:dword_140065110
0x1400928ba  mov     r8d, 0C000000Dh
0x1400928c0  mov     edi, r8d
0x1400928c3  cmp     eax, 2
0x1400928c6  jbe     loc_140092FC3
0x1400928cc  mov     edx, 100h
0x1400928d1  lea     rcx, dword_140065110
0x1400928d8  call    _tlgKeywordOn
0x1400928dd  test    al, al
0x1400928df  jz      loc_140092FC3
0x1400928e5  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x1400928ec  lea     rcx, [rbp+57h+var_A0]
0x1400928f0  call    _tlgCreate1Sz_char
0x1400928f5  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400928fc  lea     rcx, [rbp+57h+var_90]
0x140092900  call    _tlgCreate1Sz_char
0x140092905  lea     rax, [rsp+120h+var_E8]
0x14009290a  mov     dword ptr [rsp+120h+var_E8], 6FCh
0x140092912  mov     [rbp+57h+var_80], rax
0x140092916  lea     rdx, unk_1400486E1
0x14009291d  lea     rax, [rsp+120h+var_F0]
0x140092922  mov     [rbp+57h+var_70], rax
0x140092926  lea     rax, [rbx+8]
0x14009292a  mov     [rbp+57h+var_60], rax
0x14009292e  mov     eax, [r14+rsi*8]
0x140092932  mov     dword ptr [rsp+120h+var_E0], eax
0x140092936  lea     rax, [rsp+120h+var_E0]
0x14009293b  jmp     loc_140092863
0x140092940  mov     eax, cs:dword_140065110
0x140092946  cmp     eax, 2
0x140092949  jbe     loc_140092FC3
0x14009294f  mov     edx, 100h
0x140092954  lea     rcx, dword_140065110
0x14009295b  call    _tlgKeywordOn
0x140092960  test    al, al
0x140092962  jz      loc_140092FC3
0x140092968  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x14009296f  lea     rcx, [rbp+57h+var_A0]
0x140092973  call    _tlgCreate1Sz_char
0x140092978  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x14009297f  lea     rcx, [rbp+57h+var_90]
0x140092983  call    _tlgCreate1Sz_char
0x140092988  lea     rax, [rsp+120h+var_E8]
0x14009298d  mov     dword ptr [rsp+120h+var_E8], 6CDh
0x140092995  mov     [rbp+57h+var_80], rax
0x140092999  lea     rdx, unk_1400487AB
0x1400929a0  lea     rax, [rsp+120h+var_F0]
0x1400929a5  mov     dword ptr [rsp+120h+var_F0], edi
0x1400929a9  mov     [rbp+57h+var_70], rax
0x1400929ad  lea     rax, [rbx+8]
0x1400929b1  mov     [rbp+57h+var_60], rax
0x1400929b5  mov     eax, [r14+rsi*8]
0x1400929b9  mov     dword ptr [rsp+120h+var_E0], eax
0x1400929bd  lea     rax, [rsp+120h+var_E0]
0x1400929c2  jmp     loc_140092868
0x1400929c7  mov     eax, cs:dword_140065110
0x1400929cd  mov     r8d, 0C000000Dh
0x1400929d3  mov     edi, r8d
0x1400929d6  cmp     eax, 2
0x1400929d9  jbe     loc_140092FC3
0x1400929df  mov     edx, 100h
0x1400929e4  lea     rcx, dword_140065110
0x1400929eb  call    _tlgKeywordOn
0x1400929f0  test    al, al
0x1400929f2  jz      loc_140092FC3
0x1400929f8  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x1400929ff  lea     rcx, [rbp+57h+var_A0]
0x140092a03  call    _tlgCreate1Sz_char
0x140092a08  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140092a0f  lea     rcx, [rbp+57h+var_90]
0x140092a13  call    _tlgCreate1Sz_char
0x140092a18  lea     rax, [rsp+120h+var_E8]
0x140092a1d  mov     dword ptr [rsp+120h+var_E8], 69Eh
0x140092a25  mov     [rbp+57h+var_80], rax
0x140092a29  lea     rdx, unk_1400488DA
0x140092a30  lea     rax, [rsp+120h+var_F0]
0x140092a35  mov     [rbp+57h+var_70], rax
0x140092a39  lea     rax, [rbx+8]
0x140092a3d  mov     [rbp+57h+var_60], rax
0x140092a41  mov     eax, [r14+rsi*8]
0x140092a45  mov     dword ptr [rsp+120h+var_E0], eax
0x140092a49  lea     rax, [rsp+120h+var_E0]
0x140092a4e  jmp     loc_140092863
0x140092a53  mov     rsi, [rsp+120h+var_E8]
0x140092a58  mov     rdi, [rsp+120h+var_E0]
0x140092a5d  test    sil, 2
0x140092a61  jz      loc_140092B08
0x140092a67  cmp     [rbx+60h], r9
0x140092a6b  jnz     loc_140092B04
0x140092a71  mov     eax, cs:dword_140065110
0x140092a77  mov     r8d, 0C000000Dh
0x140092a7d  mov     edi, r8d
0x140092a80  cmp     eax, 2
0x140092a83  jbe     loc_140092FC3
0x140092a89  mov     edx, 100h
0x140092a8e  lea     rcx, dword_140065110
0x140092a95  call    _tlgKeywordOn
0x140092a9a  test    al, al
0x140092a9c  jz      loc_140092FC3
0x140092aa2  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x140092aa9  lea     rcx, [rbp+57h+var_A0]
0x140092aad  call    _tlgCreate1Sz_char
0x140092ab2  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140092ab9  lea     rcx, [rbp+57h+var_90]
0x140092abd  call    _tlgCreate1Sz_char
0x140092ac2  lea     rax, [rsp+120h+var_E8]
0x140092ac7  mov     dword ptr [rsp+120h+var_E8], 70Ah
0x140092acf  mov     [rbp+57h+var_80], rax
0x140092ad3  lea     rdx, unk_140048746
0x140092ada  lea     rax, [rsp+120h+var_F0]
0x140092adf  mov     [rbp+57h+var_70], rax
0x140092ae3  lea     rax, [rbx+8]
0x140092ae7  mov     [rbp+57h+var_60], rax
0x140092aeb  mov     eax, r15d
0x140092aee  lea     rcx, [rax+rax*2]
0x140092af2  mov     eax, [r14+rcx*8]
0x140092af6  mov     dword ptr [rsp+120h+var_E0], eax
0x140092afa  lea     rax, [rsp+120h+var_E0]
0x140092aff  jmp     loc_140092863
0x140092b04  or      dword ptr [rbx+38h], 1
0x140092b08  lea     r14, [r13+668h]
0x140092b0f  mov     rcx, r14
0x140092b12  mov     qword ptr [rsp+120h+var_D8], r14
0x140092b17  lea     r12, [r13+898h]
0x140092b1e  call    VidLockAcquireShared
0x140092b23  mov     rcx, r12
0x140092b26  call    VidPushLockAcquireExclusive
0x140092b2b  mov     rdx, rdi
0x140092b2e  mov     rcx, r12
0x140092b31  call    VidResourcePartitionFindById
  ... truncated ...
```
