# AfdExtractAfdSendMsgInfo

- ea: `0x140054228`
- end: `0x14005474c`
- name: `AfdExtractAfdSendMsgInfo`
- size: `1316`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400549b0`

## callees

- `0x140008064`
- `0x14000f744`
- `0x14002fd5c`
- `0x1400308a8`
- `0x140032bd4`
- `0x1400445b8`
- `0x14004de88`
- `0x14004dfa0`
- `0x140054228`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072800`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14005463e`
- `ntoskrnl!ProbeForRead` at `0x14005463e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005431e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140054438`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005431e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140054438`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054712`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054712`
- `ntoskrnl!IoIs32bitProcess` at `0x1400542c1`
- `ntoskrnl!IoIs32bitProcess` at `0x1400542c1`
- `NDIS!NdisReleaseRWLock` at `0x1400545bd`
- `NDIS!NdisReleaseRWLock` at `0x1400545f5`
- `NDIS!NdisReleaseRWLock` at `0x1400545bd`
- `NDIS!NdisReleaseRWLock` at `0x1400545f5`
- `NDIS!NdisAcquireRWLockRead` at `0x14005459c`
- `NDIS!NdisAcquireRWLockRead` at `0x14005459c`

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
  unsigned int v12; // r14d
  unsigned int v13; // esi
  KPROCESSOR_MODE v14; // cl
  void *v15; // rdx
  void *v16; // rax
  __int64 v17; // rdx
  void *v18; // rcx
  void *v19; // rcx
  int v21; // [rsp+20h] [rbp-108h]
  int v22; // [rsp+60h] [rbp-C8h]
  char v23; // [rsp+64h] [rbp-C4h]
  struct _LOCK_STATE_EX LockState; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+6Ch] [rbp-BCh] BYREF
  void *Src; // [rsp+70h] [rbp-B8h]
  unsigned int v27; // [rsp+78h] [rbp-B0h]
  unsigned int v28; // [rsp+7Ch] [rbp-ACh]
  int v29; // [rsp+80h] [rbp-A8h]
  int v30; // [rsp+84h] [rbp-A4h]
  __int64 v31; // [rsp+88h] [rbp-A0h]
  int v32; // [rsp+90h] [rbp-98h]
  unsigned __int64 v33; // [rsp+98h] [rbp-90h]
  unsigned __int64 v34; // [rsp+A0h] [rbp-88h]
  __int64 *v35; // [rsp+A8h] [rbp-80h]
  _OWORD v36[4]; // [rsp+B0h] [rbp-78h] BYREF

  v35 = a3;
  v33 = 0;
  v29 = 0;
  v34 = 0;
  v27 = 0;
  *a3 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v6 = 0;
  v33 = 0;
  Src = 0;
  v34 = 0;
  v25 = 0;
  v7 = 0;
  v31 = 0;
  v28 = 0;
  v8 = IoIs32bitProcess(a1);
  v9 = *(_DWORD *)(a2 + 16);
  if ( v8 )
  {
    memset(v36, 0, 36);
    if ( v9 < 0x24 )
    {
LABEL_3:
      v22 = -1073741811;
      goto LABEL_58;
    }
    RequestorMode = a1->RequestorMode;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v11 = *(void **)(a2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(v36, v11, 0x24u);
    else
      RtlCopyVolatileMemory(v36, v11, 0x24u);
    v12 = HIDWORD(v36[1]);
    v29 = HIDWORD(v36[1]);
    if ( HIDWORD(v36[1]) )
    {
      v6 = (volatile void *)DWORD2(v36[1]);
      v33 = DWORD2(v36[1]);
      v22 = AfdComputeCMSGLength((void *)DWORD2(v36[1]), HIDWORD(v36[1]));
      if ( v22 < 0 )
        goto LABEL_58;
    }
    v13 = DWORD1(v36[1]);
    v27 = DWORD1(v36[1]);
    if ( DWORD1(v36[1]) )
    {
      Src = (void *)LODWORD(v36[1]);
      v34 = LODWORD(v36[1]);
    }
    v30 = DWORD1(v36[0]);
    v32 = DWORD1(v36[0]);
    v22 = AfdAllocateMdlChain32(a1, LODWORD(v36[0]), DWORD1(v36[0]), 0, &v25);
    if ( v22 < 0 )
      goto LABEL_58;
  }
  else
  {
    memset(v36, 0, sizeof(v36));
    if ( v9 < 0x40 )
      goto LABEL_3;
    v14 = a1->RequestorMode;
    if ( v14 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v15 = *(void **)(a2 + 32);
    if ( v14 )
      RtlCopyFromUser(v36, v15, 0x40u);
    else
      RtlCopyVolatileMemory(v36, v15, 0x40u);
    v12 = v36[3];
    v29 = v36[3];
    if ( LODWORD(v36[3]) )
      v6 = (volatile void *)*((_QWORD *)&v36[2] + 1);
    v33 = (unsigned __int64)v6;
    v30 = DWORD2(v36[0]);
    v32 = DWORD2(v36[0]);
    v13 = v36[2];
    v27 = v36[2];
    v16 = Src;
    if ( LODWORD(v36[2]) )
      v16 = (void *)*((_QWORD *)&v36[1] + 1);
    Src = v16;
    v34 = (unsigned __int64)v16;
    v22 = AfdAllocateMdlChain(a1, *(_QWORD *)&v36[0], DWORD2(v36[0]), 0, &v25);
    if ( v22 < 0 )
      goto LABEL_58;
  }
  if ( (*(_DWORD *)(v5 + 8) & 0x100) == 0 && (*(_DWORD *)(v5 + 16) & 0x8000) == 0 && *(_BYTE *)(v5 + 2) == 4 && !Src
    || (v23 = 0, !Src) && v6 )
  {
    v23 = 1;
    v13 = *(_DWORD *)(v5 + 176);
    v27 = v13;
  }
  v17 = v12;
  if ( v28 )
    v17 = v28;
  v7 = AfdBuildSendMsgTracker(v13, v17);
  v31 = v7;
  if ( !v7 )
  {
    v22 = -1073741670;
    goto LABEL_58;
  }
  *(_QWORD *)(v7 + 24) = v25;
  if ( v23 )
  {
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState, 0);
    if ( v13 != *(_DWORD *)(v5 + 176) )
    {
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v5 + 168), &LockState);
      v22 = -1073741811;
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
    AFDETW_TRACESENDMSG(0, 3044, v5);
    *v35 = v7;
    return (unsigned int)v22;
  }
  if ( a1->RequestorMode )
    ProbeForRead(v6, v12, 1u);
  v19 = *(void **)(v7 + 56);
  if ( !v28 )
  {
    if ( a1->RequestorMode )
      RtlCopyFromUser(v19, (void *)v6, v12);
    else
      RtlCopyVolatileMemory(v19, (const void *)v6, v12);
    goto LABEL_56;
  }
  LOBYTE(v21) = a1->RequestorMode;
  v22 = AfdCopyCMSGBuffer(v19, v28, v6, v12, v21);
  if ( v22 >= 0 )
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
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140054228  mov     r11, rsp
0x14005422b  mov     [r11+20h], rsi
0x14005422f  push    rdi
0x140054230  push    r12
0x140054232  push    r13
0x140054234  push    r14
0x140054236  push    r15
0x140054238  sub     rsp, 100h
0x14005423f  mov     rax, cs:__security_cookie
0x140054246  xor     rax, rsp
0x140054249  mov     [rsp+128h+var_38], rax
0x140054251  mov     [rsp+128h+var_80], r8
0x140054259  mov     rsi, rdx
0x14005425c  mov     r15, rcx
0x14005425f  mov     qword ptr [r11-90h], 0
0x14005426a  mov     [rsp+128h+var_A8], 0
0x140054275  mov     qword ptr [r11-88h], 0
0x140054280  mov     [rsp+128h+var_B0], 0
0x140054288  mov     qword ptr [r8], 0
0x14005428f  mov     rax, [rdx+30h]
0x140054293  mov     r13, [rax+18h]
0x140054297  xor     r12d, r12d
0x14005429a  mov     [r11-90h], r12
0x1400542a1  xor     eax, eax
0x1400542a3  mov     [rsp+128h+Src], rax
0x1400542a8  mov     [r11-88h], rax
0x1400542af  mov     [rsp+128h+var_BC], eax
0x1400542b3  xor     edi, edi
0x1400542b5  mov     [rsp+128h+var_A0], rdi
0x1400542bd  mov     [rsp+128h+var_AC], eax
0x1400542c1  call    cs:__imp_IoIs32bitProcess
0x1400542c8  nop     dword ptr [rax+rax+00h]
0x1400542cd  mov     r14d, [rsi+10h]
0x1400542d1  test    al, al
0x1400542d3  jz      loc_140054409
0x1400542d9  xorps   xmm0, xmm0
0x1400542dc  xor     eax, eax
0x1400542de  movups  [rsp+128h+var_78], xmm0
0x1400542e6  movups  xmmword ptr [rsp+128h+Size], xmm0
0x1400542ee  mov     dword ptr [rsp+128h+var_58], eax
0x1400542f5  lea     r8d, [r12+24h]
0x1400542fa  cmp     r14d, r8d
0x1400542fd  jnb     short loc_14005430C
0x1400542ff  mov     [rsp+128h+var_C8], 0C000000Dh
0x140054307  jmp     loc_1400546FF
0x14005430c  mov     [rsp+128h+var_C8], eax
0x140054310  mov     cl, [r15+40h]
0x140054314  test    cl, cl
0x140054316  jz      short loc_14005432B
0x140054318  test    byte ptr [rsi+20h], 3
0x14005431c  jz      short loc_14005432B
0x14005431e  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140054325  nop     dword ptr [rax+rax+00h]
0x14005432a  int     3; Trap to Debugger
0x14005432b  mov     rdx, [rsi+20h]; Src
0x14005432f  test    cl, cl
0x140054331  lea     rcx, [rsp+128h+var_78]; void *
0x140054339  jz      short loc_140054342
0x14005433b  call    RtlCopyFromUser
0x140054340  jmp     short loc_140054347
0x140054342  call    RtlCopyVolatileMemory
0x140054347  mov     r14d, dword ptr [rsp+128h+Size+0Ch]
0x14005434f  mov     [rsp+128h+var_A8], r14d
0x140054357  test    r14d, r14d
0x14005435a  jz      short loc_140054390
0x14005435c  mov     r12d, dword ptr [rsp+128h+Size+8]
0x140054364  mov     [rsp+128h+var_90], r12
0x14005436c  lea     r9, [rsp+128h+var_AC]
0x140054371  mov     r8b, [r15+40h]
0x140054375  mov     edx, r14d; ulMinuend
0x140054378  mov     ecx, r12d; Src
0x14005437b  call    AfdComputeCMSGLength
0x140054380  mov     [rsp+128h+var_C8], eax
0x140054384  mov     eax, [rsp+128h+var_C8]
0x140054388  test    eax, eax
0x14005438a  js      loc_1400546FF
0x140054390  mov     esi, dword ptr [rsp+128h+Size+4]
0x140054397  mov     [rsp+128h+var_B0], esi
0x14005439b  test    esi, esi
0x14005439d  jz      short loc_1400543B3
0x14005439f  mov     eax, dword ptr [rsp+128h+Size]
0x1400543a6  mov     [rsp+128h+Src], rax
0x1400543ab  mov     [rsp+128h+var_88], rax
0x1400543b3  mov     edx, dword ptr [rsp+128h+var_78]
0x1400543ba  mov     eax, dword ptr [rsp+128h+var_78+4]
0x1400543c1  mov     [rsp+128h+var_A4], eax
0x1400543c8  mov     [rsp+128h+var_98], eax
0x1400543cf  lea     rcx, [rsp+128h+var_BC]
0x1400543d4  mov     [rsp+128h+var_108], rcx
0x1400543d9  xor     r9d, r9d
0x1400543dc  mov     r8d, eax
0x1400543df  mov     rcx, r15
0x1400543e2  call    AfdAllocateMdlChain32
0x1400543e7  mov     [rsp+128h+var_C8], eax
0x1400543eb  mov     eax, [rsp+128h+var_C8]
0x1400543ef  test    eax, eax
0x1400543f1  js      loc_1400546FF
0x1400543f7  jmp     loc_1400544F9
0x1400543fc  mov     rdi, [rsp+128h+var_A0]
0x140054404  jmp     loc_1400546FF
0x140054409  xor     edx, edx; Val
0x14005440b  lea     r8d, [rdx+40h]; Size
0x14005440f  lea     rcx, [rsp+128h+var_78]; void *
0x140054417  call    memset
0x14005441c  cmp     r14d, 40h ; '@'
0x140054420  jb      loc_1400542FF
0x140054426  mov     [rsp+128h+var_C8], edi
0x14005442a  mov     cl, [r15+40h]
0x14005442e  test    cl, cl
0x140054430  jz      short loc_140054445
0x140054432  test    byte ptr [rsi+20h], 3
0x140054436  jz      short loc_140054445
0x140054438  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005443f  nop     dword ptr [rax+rax+00h]
0x140054444  int     3; Trap to Debugger
0x140054445  mov     rdx, [rsi+20h]; Src
0x140054449  mov     r8d, 40h ; '@'; Size
0x14005444f  test    cl, cl
0x140054451  lea     rcx, [rsp+128h+var_78]; void *
0x140054459  jz      short loc_140054462
0x14005445b  call    RtlCopyFromUser
0x140054460  jmp     short loc_140054467
0x140054462  call    RtlCopyVolatileMemory
0x140054467  mov     r14, [rsp+128h+var_48]
0x14005446f  mov     [rsp+128h+var_A8], r14d
0x140054477  test    r14d, r14d
0x14005447a  cmovnz  r12, [rsp+128h+var_50]
0x140054483  mov     [rsp+128h+var_90], r12
0x14005448b  mov     ecx, dword ptr [rsp+128h+var_78+8]
0x140054492  mov     [rsp+128h+var_A4], ecx
0x140054499  mov     [rsp+128h+var_98], ecx
0x1400544a0  mov     rsi, [rsp+128h+var_58]
0x1400544a8  mov     [rsp+128h+var_B0], esi
0x1400544ac  mov     rax, [rsp+128h+Src]
0x1400544b1  test    esi, esi
0x1400544b3  cmovnz  rax, [rsp+128h+Size+8]
0x1400544bc  mov     [rsp+128h+Src], rax
0x1400544c1  mov     [rsp+128h+var_88], rax
0x1400544c9  lea     rax, [rsp+128h+var_BC]
0x1400544ce  mov     [rsp+128h+var_108], rax
0x1400544d3  xor     r9d, r9d
0x1400544d6  mov     r8d, ecx
0x1400544d9  mov     rdx, qword ptr [rsp+128h+var_78]
0x1400544e1  mov     rcx, r15
0x1400544e4  call    AfdAllocateMdlChain
0x1400544e9  mov     [rsp+128h+var_C8], eax
0x1400544ed  mov     eax, [rsp+128h+var_C8]
0x1400544f1  test    eax, eax
0x1400544f3  js      loc_1400546FF
0x1400544f9  mov     eax, [r13+8]
0x1400544fd  bt      eax, 8
0x140054501  mov     rax, [rsp+128h+Src]
0x140054506  jb      short loc_14005451E
0x140054508  test    dword ptr [r13+10h], 8000h
0x140054510  jnz     short loc_14005451E
0x140054512  cmp     byte ptr [r13+2], 4
0x140054517  jnz     short loc_14005451E
0x140054519  test    rax, rax
0x14005451c  jz      short loc_14005452D
0x14005451e  mov     [rsp+128h+var_C4], 0
0x140054523  test    rax, rax
0x140054526  jnz     short loc_14005453F
0x140054528  test    r12, r12
0x14005452b  jz      short loc_14005453F
0x14005452d  mov     [rsp+128h+var_C4], 1
0x140054532  mov     eax, [r13+0B0h]
0x140054539  mov     esi, eax
0x14005453b  mov     [rsp+128h+var_B0], eax
0x14005453f  mov     edx, r14d
0x140054542  mov     eax, [rsp+128h+var_AC]
0x140054546  test    eax, eax
0x140054548  cmovnz  edx, eax
0x14005454b  mov     ecx, esi
0x14005454d  call    AfdBuildSendMsgTracker
0x140054552  mov     rdi, rax
0x140054555  mov     [rsp+128h+var_A0], rax
0x14005455d  test    rax, rax
0x140054560  jnz     short loc_14005456F
0x140054562  mov     [rsp+128h+var_C8], 0C000009Ah
0x14005456a  jmp     loc_1400546FF
0x14005456f  mov     eax, [rsp+128h+var_BC]
0x140054573  mov     [rdi+18h], rax
0x140054577  cmp     [rsp+128h+var_C4], 0
0x14005457c  jz      loc_140054603
0x140054582  xor     eax, eax
0x140054584  mov     word ptr [rsp+128h+LockState.OldIrql], ax
0x140054589  mov     [rsp+128h+LockState.Flags], al
0x14005458d  xor     r8d, r8d; Flags
0x140054590  lea     rdx, [rsp+128h+LockState]; LockState
0x140054595  mov     rcx, [r13+0A8h]; Lock
0x14005459c  call    cs:__imp_NdisAcquireRWLockRead
0x1400545a3  nop     dword ptr [rax+rax+00h]
0x1400545a8  cmp     esi, [r13+0B0h]
0x1400545af  jz      short loc_1400545D6
0x1400545b1  lea     rdx, [rsp+128h+LockState]; LockState
0x1400545b6  mov     rcx, [r13+0A8h]; Lock
0x1400545bd  call    cs:__imp_NdisReleaseRWLock
0x1400545c4  nop     dword ptr [rax+rax+00h]
0x1400545c9  mov     [rsp+128h+var_C8], 0C000000Dh
0x1400545d1  jmp     loc_1400546FF
0x1400545d6  mov     r8d, esi; Size
0x1400545d9  mov     rdx, [r13+0B8h]; Src
0x1400545e0  mov     rcx, [rdi+48h]; void *
0x1400545e4  call    memmove
0x1400545e9  lea     rdx, [rsp+128h+LockState]; LockState
0x1400545ee  mov     rcx, [r13+0A8h]; Lock
0x1400545f5  call    cs:__imp_NdisReleaseRWLock
0x1400545fc  nop     dword ptr [rax+rax+00h]
0x140054601  jmp     short loc_140054626
0x140054603  test    esi, esi
0x140054605  jz      short loc_140054626
0x140054607  mov     rcx, [rdi+48h]; void *
0x14005460b  mov     r8d, esi; Size
0x14005460e  mov     rdx, [rsp+128h+Src]; Src
0x140054613  cmp     byte ptr [r15+40h], 0
0x140054618  jz      short loc_140054621
0x14005461a  call    RtlCopyFromUser
0x14005461f  jmp     short loc_140054626
0x140054621  call    RtlCopyVolatileMemory
0x140054626  test    r14d, r14d
0x140054629  jz      short loc_14005469C
0x14005462b  cmp     byte ptr [r15+40h], 0
0x140054630  jz      short loc_14005464A
0x140054632  mov     edx, r14d; Length
0x140054635  mov     r8d, 1; Alignment
0x14005463b  mov     rcx, r12; Address
0x14005463e  call    cs:__imp_ProbeForRead
0x140054645  nop     dword ptr [rax+rax+00h]
0x14005464a  mov     r9b, [r15+40h]
0x14005464e  mov     rcx, [rdi+38h]; void *
0x140054652  mov     eax, [rsp+128h+var_AC]
0x140054656  test    eax, eax
0x140054658  jz      short loc_14005467D
0x14005465a  mov     edx, eax
0x14005465c  mov     byte ptr [rsp+128h+var_108], r9b
0x140054661  mov     r9d, r14d
0x140054664  mov     r8, r12
0x140054667  call    AfdCopyCMSGBuffer
0x14005466c  mov     [rsp+128h+var_C8], eax
0x140054670  mov     eax, [rsp+128h+var_C8]
0x140054674  test    eax, eax
0x140054676  jns     short loc_140054694
0x140054678  jmp     loc_1400546FF
0x14005467d  mov     r8d, r14d; Size
0x140054680  mov     rdx, r12; Src
0x140054683  test    r9b, r9b
0x140054686  jz      short loc_14005468F
0x140054688  call    RtlCopyFromUser
0x14005468d  jmp     short loc_140054694
0x14005468f  call    RtlCopyVolatileMemory
0x140054694  mov     qword ptr [rdi+28h], 886103h
0x14005469c  mov     [rsp+128h+var_E0], r15
0x1400546a1  mov     rax, [rdi+48h]
0x1400546a5  mov     [rsp+128h+var_E8], rax
0x1400546aa  mov     [rsp+128h+var_F0], 0
0x1400546b2  mov     eax, [rsp+128h+var_BC]
0x1400546b6  mov     [rsp+128h+var_F8], eax
0x1400546ba  mov     rax, [r15+8]
0x1400546be  mov     [rsp+128h+var_100], rax
0x1400546c3  mov     eax, [rsp+128h+var_A4]
0x1400546ca  mov     dword ptr [rsp+128h+var_108], eax
0x1400546ce  xor     r9d, r9d
0x1400546d1  mov     r8, r13
0x1400546d4  mov     edx, 0BE4h
0x1400546d9  xor     ecx, ecx
0x1400546db  call    AFDETW_TRACESENDMSG
0x1400546e0  mov     rax, [rsp+128h+var_80]
0x1400546e8  mov     [rax], rdi
0x1400546eb  jmp     short loc_14005471E
0x1400546ed  mov     rdi, [rsp+128h+var_A0]
0x1400546f5  jmp     short loc_1400546FF
0x1400546f7  mov     rdi, [rsp+128h+var_A0]
0x1400546ff  test    rdi, rdi
0x140054702  jz      short loc_14005471E
0x140054704  mov     dword ptr [rdi], 78746D73h
0x14005470a  mov     edx, 4D646641h; Tag
0x14005470f  mov     rcx, rdi; P
0x140054712  call    cs:__imp_ExFreePoolWithTag
0x140054719  nop     dword ptr [rax+rax+00h]
0x14005471e  mov     eax, [rsp+128h+var_C8]
0x140054722  mov     rcx, [rsp+128h+var_38]
0x14005472a  xor     rcx, rsp; StackCookie
0x14005472d  call    __security_check_cookie
0x140054732  mov     rsi, [rsp+128h+arg_18]
0x14005473a  add     rsp, 100h
0x140054741  pop     r15
0x140054743  pop     r14
0x140054745  pop     r13
0x140054747  pop     r12
0x140054749  pop     rdi
0x14005474a  retn
0x140073ff3  push    rbp
0x140073ff5  sub     rsp, 60h
0x140073ff9  mov     rbp, rdx
0x140073ffc  mov     r8, rcx
0x140073fff  lea     r9, [rbp+60h]
0x140074003  mov     edx, 1118h
0x140074008  lea     rcx, aMinioSocketsWi_1; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007400f  call    AfdExceptionFilter
0x140074014  nop
  ... truncated ...
```
