# AfdExtractAfdSendMsgInfo

- ea: `0x1400542c8`
- end: `0x1400547ec`
- name: `AfdExtractAfdSendMsgInfo`
- size: `1316`
- prototype: `__int64 __fastcall(IRP *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140054a50`

## callees

- `0x140008064`
- `0x14000f744`
- `0x14002fd7c`
- `0x1400308c8`
- `0x140032bf4`
- `0x1400445d8`
- `0x14004df28`
- `0x14004e040`
- `0x1400542c8`
- `0x140072840`
- `0x140072870`
- `0x140072980`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400546de`
- `ntoskrnl!ProbeForRead` at `0x1400546de`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400543be`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400544d8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400543be`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400544d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400547b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400547b2`
- `ntoskrnl!IoIs32bitProcess` at `0x140054361`
- `ntoskrnl!IoIs32bitProcess` at `0x140054361`
- `NDIS!NdisReleaseRWLock` at `0x14005465d`
- `NDIS!NdisReleaseRWLock` at `0x140054695`
- `NDIS!NdisReleaseRWLock` at `0x14005465d`
- `NDIS!NdisReleaseRWLock` at `0x140054695`
- `NDIS!NdisAcquireRWLockRead` at `0x14005463c`
- `NDIS!NdisAcquireRWLockRead` at `0x14005463c`

## pseudocode

```c
__int64 __fastcall AfdExtractAfdSendMsgInfo(IRP *a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // r13
  volatile void *v6; // r12
  __int64 v7; // rdi
  BOOLEAN v8; // al
  unsigned int v9; // r14d
  KPROCESSOR_MODE RequestorMode; // cl
  void *v11; // rdx
  ULONG v12; // r14d
  unsigned int v13; // esi
  KPROCESSOR_MODE v14; // cl
  void *v15; // rdx
  void *v16; // rax
  __int64 v17; // rdx
  void *v18; // rcx
  void *v19; // rcx
  int v21; // [rsp+60h] [rbp-C8h]
  char v22; // [rsp+64h] [rbp-C4h]
  struct _LOCK_STATE_EX LockState; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v24; // [rsp+6Ch] [rbp-BCh] BYREF
  void *Src; // [rsp+70h] [rbp-B8h]
  unsigned int v26; // [rsp+78h] [rbp-B0h]
  unsigned int v27; // [rsp+7Ch] [rbp-ACh] BYREF
  int v28; // [rsp+80h] [rbp-A8h]
  int v29; // [rsp+84h] [rbp-A4h]
  __int64 v30; // [rsp+88h] [rbp-A0h]
  int v31; // [rsp+90h] [rbp-98h]
  unsigned __int64 v32; // [rsp+98h] [rbp-90h]
  unsigned __int64 v33; // [rsp+A0h] [rbp-88h]
  __int64 *v34; // [rsp+A8h] [rbp-80h]
  _OWORD v35[4]; // [rsp+B0h] [rbp-78h] BYREF

  v34 = a3;
  v32 = 0;
  v28 = 0;
  v33 = 0;
  v26 = 0;
  *a3 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v6 = 0;
  v32 = 0;
  Src = 0;
  v33 = 0;
  v24 = 0;
  v7 = 0;
  v30 = 0;
  v27 = 0;
  v8 = IoIs32bitProcess(a1);
  v9 = *(_DWORD *)(a2 + 16);
  if ( v8 )
  {
    memset(v35, 0, 36);
    if ( v9 < 0x24 )
    {
LABEL_3:
      v21 = -1073741811;
      goto LABEL_58;
    }
    RequestorMode = a1->RequestorMode;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v11 = *(void **)(a2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(v35, v11, 0x24u);
    else
      RtlCopyVolatileMemory(v35, v11, 0x24u);
    v12 = HIDWORD(v35[1]);
    v28 = HIDWORD(v35[1]);
    if ( HIDWORD(v35[1]) )
    {
      v6 = (volatile void *)DWORD2(v35[1]);
      v32 = DWORD2(v35[1]);
      v21 = AfdComputeCMSGLength((char *)DWORD2(v35[1]), HIDWORD(v35[1]), a1->RequestorMode, &v27);
      if ( v21 < 0 )
        goto LABEL_58;
    }
    v13 = DWORD1(v35[1]);
    v26 = DWORD1(v35[1]);
    if ( DWORD1(v35[1]) )
    {
      Src = (void *)LODWORD(v35[1]);
      v33 = LODWORD(v35[1]);
    }
    v29 = DWORD1(v35[0]);
    v31 = DWORD1(v35[0]);
    v21 = AfdAllocateMdlChain32((__int64)a1, (ULONG *)LODWORD(v35[0]), DWORD1(v35[0]), IoReadAccess, &v24);
    if ( v21 < 0 )
      goto LABEL_58;
  }
  else
  {
    memset(v35, 0, sizeof(v35));
    if ( v9 < 0x40 )
      goto LABEL_3;
    v14 = a1->RequestorMode;
    if ( v14 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v15 = *(void **)(a2 + 32);
    if ( v14 )
      RtlCopyFromUser(v35, v15, 0x40u);
    else
      RtlCopyVolatileMemory(v35, v15, 0x40u);
    v12 = v35[3];
    v28 = v35[3];
    if ( LODWORD(v35[3]) )
      v6 = (volatile void *)*((_QWORD *)&v35[2] + 1);
    v32 = (unsigned __int64)v6;
    v29 = DWORD2(v35[0]);
    v31 = DWORD2(v35[0]);
    v13 = v35[2];
    v26 = v35[2];
    v16 = Src;
    if ( LODWORD(v35[2]) )
      v16 = (void *)*((_QWORD *)&v35[1] + 1);
    Src = v16;
    v33 = (unsigned __int64)v16;
    v21 = AfdAllocateMdlChain((__int64)a1, *(_QWORD **)&v35[0], DWORD2(v35[0]), IoReadAccess, &v24);
    if ( v21 < 0 )
      goto LABEL_58;
  }
  if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 16) & 0x8000) == 0 && *(_BYTE *)(v5 + 2) == 4 && !Src
    || (v22 = 0, !Src) && v6 )
  {
    v22 = 1;
    v13 = *(_DWORD *)(v5 + 176);
    v26 = v13;
  }
  v17 = v12;
  if ( v27 )
    v17 = v27;
  v7 = AfdBuildSendMsgTracker(v13, v17);
  v30 = v7;
  if ( !v7 )
  {
    v21 = -1073741670;
    goto LABEL_58;
  }
  *(_QWORD *)(v7 + 24) = v24;
  if ( v22 )
  {
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState, 0);
    if ( v13 != *(_DWORD *)(v5 + 176) )
    {
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState);
      v21 = -1073741811;
      goto LABEL_58;
    }
    memmove(*(void **)(v7 + 72), *(const void **)(v5 + 184), v13);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState);
  }
  else if ( v13 )
  {
    v18 = *(void **)(v7 + 72);
    if ( a1->RequestorMode )
      RtlCopyFromUser(v18, Src, v13);
    else
      RtlCopyVolatileMemory(v18, Src, v13);
  }
  if ( !v12 )
  {
LABEL_57:
    AFDETW_TRACESENDMSG(0, 3044, v5, 0, v29, a1->MdlAddress, v24, 0, *(_QWORD *)(v7 + 72), a1);
    *v34 = v7;
    return (unsigned int)v21;
  }
  if ( a1->RequestorMode )
    ProbeForRead(v6, v12, 1u);
  v19 = *(void **)(v7 + 56);
  if ( !v27 )
  {
    if ( a1->RequestorMode )
      RtlCopyFromUser(v19, (void *)v6, v12);
    else
      RtlCopyVolatileMemory(v19, (const void *)v6, v12);
    goto LABEL_56;
  }
  v21 = AfdCopyCMSGBuffer((__int64)v19, v27, (char *)v6, v12, a1->RequestorMode);
  if ( v21 >= 0 )
  {
LABEL_56:
    *(_QWORD *)(v7 + 40) = 8937731;
    goto LABEL_57;
  }
LABEL_58:
  if ( v7 )
  {
    *(_DWORD *)v7 = 2020896115;
    ExFreePoolWithTag((PVOID)v7, 0x4D646641u);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1400542c8  mov     r11, rsp
0x1400542cb  mov     [r11+20h], rsi
0x1400542cf  push    rdi
0x1400542d0  push    r12
0x1400542d2  push    r13
0x1400542d4  push    r14
0x1400542d6  push    r15
0x1400542d8  sub     rsp, 100h
0x1400542df  mov     rax, cs:__security_cookie
0x1400542e6  xor     rax, rsp
0x1400542e9  mov     [rsp+128h+var_38], rax
0x1400542f1  mov     [rsp+128h+var_80], r8
0x1400542f9  mov     rsi, rdx
0x1400542fc  mov     r15, rcx
0x1400542ff  mov     qword ptr [r11-90h], 0
0x14005430a  mov     [rsp+128h+var_A8], 0
0x140054315  mov     qword ptr [r11-88h], 0
0x140054320  mov     [rsp+128h+var_B0], 0
0x140054328  mov     qword ptr [r8], 0
0x14005432f  mov     rax, [rdx+30h]
0x140054333  mov     r13, [rax+18h]
0x140054337  xor     r12d, r12d
0x14005433a  mov     [r11-90h], r12
0x140054341  xor     eax, eax
0x140054343  mov     [rsp+128h+Src], rax
0x140054348  mov     [r11-88h], rax
0x14005434f  mov     [rsp+128h+var_BC], eax
0x140054353  xor     edi, edi
0x140054355  mov     [rsp+128h+var_A0], rdi
0x14005435d  mov     [rsp+128h+var_AC], eax
0x140054361  call    cs:__imp_IoIs32bitProcess
0x140054368  nop     dword ptr [rax+rax+00h]
0x14005436d  mov     r14d, [rsi+10h]
0x140054371  test    al, al
0x140054373  jz      loc_1400544A9
0x140054379  xorps   xmm0, xmm0
0x14005437c  xor     eax, eax
0x14005437e  movups  [rsp+128h+var_78], xmm0
0x140054386  movups  xmmword ptr [rsp+128h+Size], xmm0
0x14005438e  mov     dword ptr [rsp+128h+var_58], eax
0x140054395  lea     r8d, [r12+24h]
0x14005439a  cmp     r14d, r8d
0x14005439d  jnb     short loc_1400543AC
0x14005439f  mov     [rsp+128h+var_C8], 0C000000Dh
0x1400543a7  jmp     loc_14005479F
0x1400543ac  mov     [rsp+128h+var_C8], eax
0x1400543b0  mov     cl, [r15+40h]
0x1400543b4  test    cl, cl
0x1400543b6  jz      short loc_1400543CB
0x1400543b8  test    byte ptr [rsi+20h], 3
0x1400543bc  jz      short loc_1400543CB
0x1400543be  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400543c5  nop     dword ptr [rax+rax+00h]
0x1400543ca  int     3; Trap to Debugger
0x1400543cb  mov     rdx, [rsi+20h]; Src
0x1400543cf  test    cl, cl
0x1400543d1  lea     rcx, [rsp+128h+var_78]; void *
0x1400543d9  jz      short loc_1400543E2
0x1400543db  call    RtlCopyFromUser
0x1400543e0  jmp     short loc_1400543E7
0x1400543e2  call    RtlCopyVolatileMemory
0x1400543e7  mov     r14d, dword ptr [rsp+128h+Size+0Ch]
0x1400543ef  mov     [rsp+128h+var_A8], r14d
0x1400543f7  test    r14d, r14d
0x1400543fa  jz      short loc_140054430
0x1400543fc  mov     r12d, dword ptr [rsp+128h+Size+8]
0x140054404  mov     [rsp+128h+var_90], r12
0x14005440c  lea     r9, [rsp+128h+var_AC]
0x140054411  mov     r8b, [r15+40h]
0x140054415  mov     edx, r14d; ulMinuend
0x140054418  mov     ecx, r12d; Src
0x14005441b  call    AfdComputeCMSGLength
0x140054420  mov     [rsp+128h+var_C8], eax
0x140054424  mov     eax, [rsp+128h+var_C8]
0x140054428  test    eax, eax
0x14005442a  js      loc_14005479F
0x140054430  mov     esi, dword ptr [rsp+128h+Size+4]
0x140054437  mov     [rsp+128h+var_B0], esi
0x14005443b  test    esi, esi
0x14005443d  jz      short loc_140054453
0x14005443f  mov     eax, dword ptr [rsp+128h+Size]
0x140054446  mov     [rsp+128h+Src], rax
0x14005444b  mov     [rsp+128h+var_88], rax
0x140054453  mov     edx, dword ptr [rsp+128h+var_78]
0x14005445a  mov     eax, dword ptr [rsp+128h+var_78+4]
0x140054461  mov     [rsp+128h+var_A4], eax
0x140054468  mov     [rsp+128h+var_98], eax
0x14005446f  lea     rcx, [rsp+128h+var_BC]
0x140054474  mov     [rsp+128h+var_108], rcx
0x140054479  xor     r9d, r9d
0x14005447c  mov     r8d, eax
0x14005447f  mov     rcx, r15
0x140054482  call    AfdAllocateMdlChain32
0x140054487  mov     [rsp+128h+var_C8], eax
0x14005448b  mov     eax, [rsp+128h+var_C8]
0x14005448f  test    eax, eax
0x140054491  js      loc_14005479F
0x140054497  jmp     loc_140054599
0x14005449c  mov     rdi, [rsp+128h+var_A0]
0x1400544a4  jmp     loc_14005479F
0x1400544a9  xor     edx, edx; Val
0x1400544ab  lea     r8d, [rdx+40h]; Size
0x1400544af  lea     rcx, [rsp+128h+var_78]; void *
0x1400544b7  call    memset
0x1400544bc  cmp     r14d, 40h ; '@'
0x1400544c0  jb      loc_14005439F
0x1400544c6  mov     [rsp+128h+var_C8], edi
0x1400544ca  mov     cl, [r15+40h]
0x1400544ce  test    cl, cl
0x1400544d0  jz      short loc_1400544E5
0x1400544d2  test    byte ptr [rsi+20h], 3
0x1400544d6  jz      short loc_1400544E5
0x1400544d8  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400544df  nop     dword ptr [rax+rax+00h]
0x1400544e4  int     3; Trap to Debugger
0x1400544e5  mov     rdx, [rsi+20h]; Src
0x1400544e9  mov     r8d, 40h ; '@'; Size
0x1400544ef  test    cl, cl
0x1400544f1  lea     rcx, [rsp+128h+var_78]; void *
0x1400544f9  jz      short loc_140054502
0x1400544fb  call    RtlCopyFromUser
0x140054500  jmp     short loc_140054507
0x140054502  call    RtlCopyVolatileMemory
0x140054507  mov     r14, [rsp+128h+var_48]
0x14005450f  mov     [rsp+128h+var_A8], r14d
0x140054517  test    r14d, r14d
0x14005451a  cmovnz  r12, [rsp+128h+var_50]
0x140054523  mov     [rsp+128h+var_90], r12
0x14005452b  mov     ecx, dword ptr [rsp+128h+var_78+8]
0x140054532  mov     [rsp+128h+var_A4], ecx
0x140054539  mov     [rsp+128h+var_98], ecx
0x140054540  mov     rsi, [rsp+128h+var_58]
0x140054548  mov     [rsp+128h+var_B0], esi
0x14005454c  mov     rax, [rsp+128h+Src]
0x140054551  test    esi, esi
0x140054553  cmovnz  rax, [rsp+128h+Size+8]
0x14005455c  mov     [rsp+128h+Src], rax
0x140054561  mov     [rsp+128h+var_88], rax
0x140054569  lea     rax, [rsp+128h+var_BC]
0x14005456e  mov     [rsp+128h+var_108], rax
0x140054573  xor     r9d, r9d
0x140054576  mov     r8d, ecx
0x140054579  mov     rdx, qword ptr [rsp+128h+var_78]
0x140054581  mov     rcx, r15
0x140054584  call    AfdAllocateMdlChain
0x140054589  mov     [rsp+128h+var_C8], eax
0x14005458d  mov     eax, [rsp+128h+var_C8]
0x140054591  test    eax, eax
0x140054593  js      loc_14005479F
0x140054599  mov     eax, [r13+8]
0x14005459d  bt      eax, 8
0x1400545a1  mov     rax, [rsp+128h+Src]
0x1400545a6  jb      short loc_1400545BE
0x1400545a8  test    dword ptr [r13+10h], 8000h
0x1400545b0  jnz     short loc_1400545BE
0x1400545b2  cmp     byte ptr [r13+2], 4
0x1400545b7  jnz     short loc_1400545BE
0x1400545b9  test    rax, rax
0x1400545bc  jz      short loc_1400545CD
0x1400545be  mov     [rsp+128h+var_C4], 0
0x1400545c3  test    rax, rax
0x1400545c6  jnz     short loc_1400545DF
0x1400545c8  test    r12, r12
0x1400545cb  jz      short loc_1400545DF
0x1400545cd  mov     [rsp+128h+var_C4], 1
0x1400545d2  mov     eax, [r13+0B0h]
0x1400545d9  mov     esi, eax
0x1400545db  mov     [rsp+128h+var_B0], eax
0x1400545df  mov     edx, r14d
0x1400545e2  mov     eax, [rsp+128h+var_AC]
0x1400545e6  test    eax, eax
0x1400545e8  cmovnz  edx, eax
0x1400545eb  mov     ecx, esi
0x1400545ed  call    AfdBuildSendMsgTracker
0x1400545f2  mov     rdi, rax
0x1400545f5  mov     [rsp+128h+var_A0], rax
0x1400545fd  test    rax, rax
0x140054600  jnz     short loc_14005460F
0x140054602  mov     [rsp+128h+var_C8], 0C000009Ah
0x14005460a  jmp     loc_14005479F
0x14005460f  mov     eax, [rsp+128h+var_BC]
0x140054613  mov     [rdi+18h], rax
0x140054617  cmp     [rsp+128h+var_C4], 0
0x14005461c  jz      loc_1400546A3
0x140054622  xor     eax, eax
0x140054624  mov     word ptr [rsp+128h+LockState.OldIrql], ax
0x140054629  mov     [rsp+128h+LockState.Flags], al
0x14005462d  xor     r8d, r8d; Flags
0x140054630  lea     rdx, [rsp+128h+LockState]; LockState
0x140054635  mov     rcx, [r13+0A8h]; Lock
0x14005463c  call    cs:__imp_NdisAcquireRWLockRead
0x140054643  nop     dword ptr [rax+rax+00h]
0x140054648  cmp     esi, [r13+0B0h]
0x14005464f  jz      short loc_140054676
0x140054651  lea     rdx, [rsp+128h+LockState]; LockState
0x140054656  mov     rcx, [r13+0A8h]; Lock
0x14005465d  call    cs:__imp_NdisReleaseRWLock
0x140054664  nop     dword ptr [rax+rax+00h]
0x140054669  mov     [rsp+128h+var_C8], 0C000000Dh
0x140054671  jmp     loc_14005479F
0x140054676  mov     r8d, esi; Size
0x140054679  mov     rdx, [r13+0B8h]; Src
0x140054680  mov     rcx, [rdi+48h]; void *
0x140054684  call    memmove
0x140054689  lea     rdx, [rsp+128h+LockState]; LockState
0x14005468e  mov     rcx, [r13+0A8h]; Lock
0x140054695  call    cs:__imp_NdisReleaseRWLock
0x14005469c  nop     dword ptr [rax+rax+00h]
0x1400546a1  jmp     short loc_1400546C6
0x1400546a3  test    esi, esi
0x1400546a5  jz      short loc_1400546C6
0x1400546a7  mov     rcx, [rdi+48h]; void *
0x1400546ab  mov     r8d, esi; Size
0x1400546ae  mov     rdx, [rsp+128h+Src]; Src
0x1400546b3  cmp     byte ptr [r15+40h], 0
0x1400546b8  jz      short loc_1400546C1
0x1400546ba  call    RtlCopyFromUser
0x1400546bf  jmp     short loc_1400546C6
0x1400546c1  call    RtlCopyVolatileMemory
0x1400546c6  test    r14d, r14d
0x1400546c9  jz      short loc_14005473C
0x1400546cb  cmp     byte ptr [r15+40h], 0
0x1400546d0  jz      short loc_1400546EA
0x1400546d2  mov     edx, r14d; Length
0x1400546d5  mov     r8d, 1; Alignment
0x1400546db  mov     rcx, r12; Address
0x1400546de  call    cs:__imp_ProbeForRead
0x1400546e5  nop     dword ptr [rax+rax+00h]
0x1400546ea  mov     r9b, [r15+40h]
0x1400546ee  mov     rcx, [rdi+38h]; void *
0x1400546f2  mov     eax, [rsp+128h+var_AC]
0x1400546f6  test    eax, eax
0x1400546f8  jz      short loc_14005471D
0x1400546fa  mov     edx, eax
0x1400546fc  mov     byte ptr [rsp+128h+var_108], r9b
0x140054701  mov     r9d, r14d
0x140054704  mov     r8, r12
0x140054707  call    AfdCopyCMSGBuffer
0x14005470c  mov     [rsp+128h+var_C8], eax
0x140054710  mov     eax, [rsp+128h+var_C8]
0x140054714  test    eax, eax
0x140054716  jns     short loc_140054734
0x140054718  jmp     loc_14005479F
0x14005471d  mov     r8d, r14d; Size
0x140054720  mov     rdx, r12; Src
0x140054723  test    r9b, r9b
0x140054726  jz      short loc_14005472F
0x140054728  call    RtlCopyFromUser
0x14005472d  jmp     short loc_140054734
0x14005472f  call    RtlCopyVolatileMemory
0x140054734  mov     qword ptr [rdi+28h], 886103h
0x14005473c  mov     [rsp+128h+var_E0], r15
0x140054741  mov     rax, [rdi+48h]
0x140054745  mov     [rsp+128h+var_E8], rax
0x14005474a  mov     [rsp+128h+var_F0], 0
0x140054752  mov     eax, [rsp+128h+var_BC]
0x140054756  mov     [rsp+128h+var_F8], eax
0x14005475a  mov     rax, [r15+8]
0x14005475e  mov     [rsp+128h+var_100], rax
0x140054763  mov     eax, [rsp+128h+var_A4]
0x14005476a  mov     dword ptr [rsp+128h+var_108], eax
0x14005476e  xor     r9d, r9d
0x140054771  mov     r8, r13
0x140054774  mov     edx, 0BE4h
0x140054779  xor     ecx, ecx
0x14005477b  call    AFDETW_TRACESENDMSG
0x140054780  mov     rax, [rsp+128h+var_80]
0x140054788  mov     [rax], rdi
0x14005478b  jmp     short loc_1400547BE
0x14005478d  mov     rdi, [rsp+128h+var_A0]
0x140054795  jmp     short loc_14005479F
0x140054797  mov     rdi, [rsp+128h+var_A0]
0x14005479f  test    rdi, rdi
0x1400547a2  jz      short loc_1400547BE
0x1400547a4  mov     dword ptr [rdi], 78746D73h
0x1400547aa  mov     edx, 4D646641h; Tag
0x1400547af  mov     rcx, rdi; P
0x1400547b2  call    cs:__imp_ExFreePoolWithTag
0x1400547b9  nop     dword ptr [rax+rax+00h]
0x1400547be  mov     eax, [rsp+128h+var_C8]
0x1400547c2  mov     rcx, [rsp+128h+var_38]
0x1400547ca  xor     rcx, rsp; StackCookie
0x1400547cd  call    __security_check_cookie
0x1400547d2  mov     rsi, [rsp+128h+arg_18]
0x1400547da  add     rsp, 100h
0x1400547e1  pop     r15
0x1400547e3  pop     r14
0x1400547e5  pop     r13
0x1400547e7  pop     r12
0x1400547e9  pop     rdi
0x1400547ea  retn
0x140074173  push    rbp
0x140074175  sub     rsp, 60h
0x140074179  mov     rbp, rdx
0x14007417c  mov     r8, rcx
0x14007417f  lea     r9, [rbp+60h]
0x140074183  mov     edx, 1118h
0x140074188  lea     rcx, aMinioSocketsWi_1; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007418f  call    AfdExceptionFilter
0x140074194  nop
  ... truncated ...
```
