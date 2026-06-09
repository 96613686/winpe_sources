# AfdServiceSuperAccept

- ea: `0x14003606c`
- end: `0x1400365e9`
- name: `AfdServiceSuperAccept`
- size: `1405`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002d8d0`
- `0x14002e9c0`
- `0x140059ab0`

## callees

- `0x140004848`
- `0x1400049b0`
- `0x140009fb0`
- `0x14000dc90`
- `0x14001a030`
- `0x14001aabc`
- `0x14001b800`
- `0x14001c708`
- `0x14002e7a8`
- `0x14003606c`
- `0x140036708`
- `0x140072870`
- `0x140072880`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036095`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036095`
- `ntoskrnl!MmMapLockedPages` at `0x140036225`
- `ntoskrnl!MmMapLockedPages` at `0x140036264`
- `ntoskrnl!MmMapLockedPages` at `0x1400362c6`
- `ntoskrnl!MmMapLockedPages` at `0x140036225`
- `ntoskrnl!MmMapLockedPages` at `0x140036264`
- `ntoskrnl!MmMapLockedPages` at `0x1400362c6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036347`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400363d2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036506`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036347`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400363d2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036506`
- `ntoskrnl!ExQueryDepthSList` at `0x1400363b6`
- `ntoskrnl!ExQueryDepthSList` at `0x1400363b6`
- `ntoskrnl!IoAllocateMdl` at `0x140036194`
- `ntoskrnl!IoAllocateMdl` at `0x140036194`
- `ntoskrnl!IofCompleteRequest` at `0x140036481`
- `ntoskrnl!IofCompleteRequest` at `0x140036555`
- `ntoskrnl!IofCompleteRequest` at `0x1400365bb`
- `ntoskrnl!IofCompleteRequest` at `0x140036481`
- `ntoskrnl!IofCompleteRequest` at `0x140036555`
- `ntoskrnl!IofCompleteRequest` at `0x1400365bb`

## pseudocode

```c
char __fastcall AfdServiceSuperAccept(__int64 a1, __int64 a2, struct _KLOCK_QUEUE_HANDLE *a3, __int64 a4)
{
  union _SLIST_HEADER *v6; // rcx
  PSLIST_ENTRY v8; // rax
  struct _SLIST_ENTRY *v9; // r13
  PSLIST_ENTRY v10; // rsi
  __int64 Irp; // rdi
  __int64 v12; // r14
  _DWORD *v13; // rcx
  unsigned int v14; // ecx
  int v15; // ebp
  ULONG v16; // edx
  __int64 v17; // rcx
  char *v18; // rax
  __int64 v19; // rcx
  char *v20; // r9
  __int64 v21; // rcx
  char *v22; // rdx
  _QWORD *v23; // rcx
  signed __int64 v24; // rax
  bool v25; // cc
  signed __int64 v26; // rax
  signed __int64 v27; // rax
  signed __int64 v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rax
  _QWORD *v31; // rdx
  __int64 v32; // rdx
  unsigned int v33; // eax
  __int64 v34; // rcx
  unsigned int v35; // ebp
  signed __int64 v36; // rax
  signed __int64 v37; // rax
  char v38; // of
  int v39; // et0
  _QWORD *v40; // rcx
  __int64 v41; // rax
  _QWORD *v42; // rdx
  __int64 v44; // [rsp+30h] [rbp-58h]
  unsigned int *v45; // [rsp+38h] [rbp-50h]
  char *v46; // [rsp+38h] [rbp-50h]
  __int64 v47; // [rsp+40h] [rbp-48h]
  unsigned __int16 Src; // [rsp+90h] [rbp+8h] BYREF
  struct _KLOCK_QUEUE_HANDLE *v49; // [rsp+A0h] [rbp+18h]

  v49 = a3;
  v6 = (union _SLIST_HEADER *)(a1 + 160);
  while ( 1 )
  {
    v8 = ExpInterlockedPopEntrySList(v6);
    v9 = v8;
    if ( !v8 )
      return (char)v8;
    v10 = v8 - 11;
    Irp = _InterlockedExchange64((volatile __int64 *)&v8[-9].Next + 1, 0);
    if ( !Irp )
    {
      v15 = -1073741536;
      goto LABEL_44;
    }
    if ( !_InterlockedExchange64((volatile __int64 *)(Irp + 104), 0) )
    {
      v15 = -1073741536;
      goto LABEL_41;
    }
    v12 = *(_QWORD *)(Irp + 184);
    v13 = (_DWORD *)(v12 + 16);
    v47 = *(_QWORD *)(v12 + 32);
    v45 = (unsigned int *)(v12 + 16);
    v44 = *(_QWORD *)(v47 + 24);
    if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
      break;
    if ( *(_DWORD *)(a2 + 160) <= *v13 )
      goto LABEL_9;
LABEL_14:
    v15 = -1073741789;
LABEL_41:
    AfdCleanupSuperAccept(Irp, (unsigned int)v15);
    v23 = *(_QWORD **)(a4 + 8);
    if ( *v23 != a4 )
LABEL_81:
      __fastfail(3u);
    *(_QWORD *)(Irp + 168) = a4;
    *(_QWORD *)(Irp + 176) = v23;
    *v23 = Irp + 168;
    *(_QWORD *)(a4 + 8) = Irp + 168;
LABEL_44:
    if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
    {
      if ( *(int *)(a1 + 176) >= 0 && v15 != -1073741670 && ExQueryDepthSList((PSLIST_HEADER)(a1 + 144)) < 0x7FFFu )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 144), v9);
        goto LABEL_54;
      }
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 176));
    }
    v24 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v10[3], 0xFFFFFFFFFFFFFFFFuLL);
    v6 = (union _SLIST_HEADER *)(a1 + 160);
    v25 = v24 <= 1;
    v26 = v24 - 1;
    if ( v25 )
    {
      if ( v26 )
        __fastfail(0xEu);
      AfdCloseConnection(v10);
LABEL_54:
      v6 = (union _SLIST_HEADER *)(a1 + 160);
    }
  }
  v45 = (unsigned int *)(v12 + 16);
LABEL_9:
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 && (unsigned int)(*(_DWORD *)(a2 + 160) + 6) > *v13 )
    goto LABEL_14;
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    v14 = *(_DWORD *)(v12 + 24);
    if ( v14 )
    {
      if ( *(_DWORD *)(a2 + 168) + 6 > v14 )
        goto LABEL_14;
    }
  }
  v15 = AfdMapMdlChain(*(PMDL *)(Irp + 8));
  if ( v15 < 0 )
    goto LABEL_41;
  if ( (*(_DWORD *)(a2 + 4) & 0x20000000) != 0 )
  {
    v33 = AfdSanAcceptCore(Irp, (char *)v47, a2, v49);
    v35 = v33;
    if ( v33 == 259 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
      {
LABEL_69:
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 144), v9);
        goto LABEL_77;
      }
    }
    else
    {
      AFDETW_TRACEACCEPT_ERROR(v34, 6204, Irp, v33);
      AfdCleanupSuperAccept(Irp, v35);
      IofCompleteRequest((PIRP)Irp, AfdPriorityBoost);
      if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
      {
        v39 = _InterlockedAdd((volatile signed __int32 *)(a1 + 176), 1u);
        if ( !((v39 < 0) ^ v38 | (v39 == 0)) )
        {
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 176));
          goto LABEL_69;
        }
      }
    }
    v36 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v10[3], 0xFFFFFFFFFFFFFFFFuLL);
    v25 = v36 <= 1;
    v37 = v36 - 1;
    if ( v25 )
    {
      if ( v37 )
        __fastfail(0xEu);
      AfdCloseConnection(v10);
    }
LABEL_77:
    while ( 1 )
    {
      v40 = *(_QWORD **)a4;
      if ( *(_QWORD *)a4 == a4 )
        goto LABEL_66;
      v41 = *v40;
      if ( *(_QWORD **)(*v40 + 8LL) != v40 )
        goto LABEL_81;
      v42 = (_QWORD *)v40[1];
      if ( (_QWORD *)*v42 != v40 )
        goto LABEL_81;
      *v42 = v41;
      *(_QWORD *)(v41 + 8) = v42;
      IofCompleteRequest((PIRP)(v40 - 21), AfdPriorityBoost);
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
  {
    v16 = *(_DWORD *)(v12 + 24);
    if ( v16 )
    {
      if ( !IoAllocateMdl((PVOID)(*(_QWORD *)(Irp + 112) + *(unsigned int *)(v12 + 8)), v16, 1u, 0, (PIRP)Irp) )
      {
        v15 = -1073741670;
        goto LABEL_41;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    AfdTLCopyRemoteAndLocalAddresses(
      v44,
      *(_QWORD *)(a2 + 224),
      *(unsigned int *)(a2 + 168),
      *(_QWORD *)(a2 + 152),
      *(_DWORD *)(a2 + 160),
      Irp);
  }
  else if ( *(_BYTE *)(v44 + 188) )
  {
    Src = *(_WORD *)(*(_QWORD *)(a2 + 152) + 4LL) + 2;
    v17 = *(_QWORD *)(Irp + 8);
    if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
      v18 = *(char **)(v17 + 24);
    else
      v18 = (char *)MmMapLockedPages((PMDL)v17, 0);
    v19 = *(_QWORD *)(Irp + 8);
    v46 = &v18[*(unsigned int *)(v12 + 24) - 2 + *v45 + *(unsigned int *)(v12 + 8)];
    if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
      v20 = *(char **)(v19 + 24);
    else
      v20 = (char *)MmMapLockedPages((PMDL)v19, 0);
    RtlMoveVolatileMemory(
      &v20[*(unsigned int *)(v12 + 24) + *(unsigned int *)(v12 + 8)],
      (const void *)(*(_QWORD *)(a2 + 152) + 6LL),
      Src);
    RtlCopyVolatileMemory(v46, &Src, 2u);
  }
  else
  {
    v21 = *(_QWORD *)(Irp + 8);
    if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
      v22 = *(char **)(v21 + 24);
    else
      v22 = (char *)MmMapLockedPages((PMDL)v21, 0);
    RtlMoveVolatileMemory(
      &v22[*(unsigned int *)(v12 + 24) + *(unsigned int *)(v12 + 8)],
      *(const void **)(a2 + 152),
      *(unsigned int *)(a2 + 160));
  }
  v15 = AfdAcceptCore(Irp, v44, a2);
  if ( v15 )
    goto LABEL_41;
  AfdNotifySockIndicateEventsUnlock(a1, v49, 0);
  if ( (*(_DWORD *)(v44 + 8) & 0x2000) != 0 )
    AfdDerefTLBaseEndpoint(v44);
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    v27 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v10[3], 0xFFFFFFFFFFFFFFFFuLL);
    v25 = v27 <= 1;
    v28 = v27 - 1;
    if ( v25 )
    {
      if ( v28 )
        __fastfail(0xEu);
      AfdCloseConnection(v10);
    }
  }
  else
  {
    ExpInterlockedPushEntrySList((PSLIST_HEADER)(a1 + 144), v9);
  }
  while ( 1 )
  {
    v29 = *(_QWORD **)a4;
    if ( *(_QWORD *)a4 == a4 )
      break;
    v30 = *v29;
    if ( *(_QWORD **)(*v29 + 8LL) != v29 )
      goto LABEL_81;
    v31 = (_QWORD *)v29[1];
    if ( (_QWORD *)*v31 != v29 )
      goto LABEL_81;
    *v31 = v30;
    *(_QWORD *)(v30 + 8) = v31;
    IofCompleteRequest((PIRP)(v29 - 21), AfdPriorityBoost);
  }
  v32 = *(_QWORD *)(Irp + 8);
  *(_DWORD *)(Irp + 48) = 0;
  *(_QWORD *)(v12 + 32) = v32;
  *(_QWORD *)(Irp + 8) = 0;
  *(_QWORD *)(v12 + 48) = v47;
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
    *(_DWORD *)(v12 + 24) = 0;
  AfdRestartSuperAcceptListen((PIRP)Irp);
LABEL_66:
  LOBYTE(v8) = 1;
  return (char)v8;
}

```

## disassembly

```asm
0x14003606c  mov     [rsp+arg_8], rbx
0x140036071  mov     [rsp+arg_10], r8
0x140036076  push    rbp
0x140036077  push    rsi
0x140036078  push    rdi
0x140036079  push    r12
0x14003607b  push    r13
0x14003607d  push    r14
0x14003607f  push    r15
0x140036081  sub     rsp, 50h
0x140036085  mov     rbx, rcx
0x140036088  mov     r12, r9
0x14003608b  add     rcx, 0A0h; ListHead
0x140036092  mov     r15, rdx
0x140036095  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003609c  nop     dword ptr [rax+rax+00h]
0x1400360a1  mov     r13, rax
0x1400360a4  test    rax, rax
0x1400360a7  jz      loc_1400365D0
0x1400360ad  xor     edi, edi
0x1400360af  lea     rsi, [rax-0B0h]
0x1400360b6  xchg    rdi, [rsi+28h]
0x1400360ba  test    rdi, rdi
0x1400360bd  jz      loc_14003638D
0x1400360c3  xor     eax, eax
0x1400360c5  xchg    rax, [rdi+68h]
0x1400360c9  test    rax, rax
0x1400360cc  jz      loc_140036358
0x1400360d2  mov     r14, [rdi+0B8h]
0x1400360d9  mov     rax, [r14+20h]
0x1400360dd  lea     rcx, [r14+10h]
0x1400360e1  mov     [rsp+88h+var_48], rax
0x1400360e6  mov     [rsp+88h+var_50], rcx
0x1400360eb  mov     rax, [rax+18h]
0x1400360ef  mov     [rsp+88h+var_58], rax
0x1400360f4  mov     eax, [rbx+8]
0x1400360f7  bt      eax, 8
0x1400360fb  jb      short loc_14003610A
0x1400360fd  mov     eax, [rcx]
0x1400360ff  cmp     [r15+0A0h], eax
0x140036106  ja      short loc_140036145
0x140036108  jmp     short loc_14003610F
0x14003610a  mov     [rsp+88h+var_50], rcx
0x14003610f  mov     eax, [rbx+8]
0x140036112  bt      eax, 8
0x140036116  jnb     short loc_140036126
0x140036118  mov     eax, [r15+0A0h]
0x14003611f  add     eax, 6
0x140036122  cmp     eax, [rcx]
0x140036124  ja      short loc_140036145
0x140036126  mov     eax, [rbx+8]
0x140036129  bt      eax, 8
0x14003612d  jnb     short loc_14003614F
0x14003612f  mov     ecx, [r14+18h]
0x140036133  test    ecx, ecx
0x140036135  jz      short loc_14003614F
0x140036137  mov     eax, [r15+0A8h]
0x14003613e  add     eax, 6
0x140036141  cmp     eax, ecx
0x140036143  jbe     short loc_14003614F
0x140036145  mov     ebp, 0C0000023h
0x14003614a  jmp     loc_14003635D
0x14003614f  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140036153  call    AfdMapMdlChain
0x140036158  mov     ebp, eax
0x14003615a  test    eax, eax
0x14003615c  js      loc_14003635D
0x140036162  test    dword ptr [r15+4], 20000000h
0x14003616a  jnz     loc_1400364D2
0x140036170  mov     eax, [rbx+8]
0x140036173  bt      eax, 8
0x140036177  jb      short loc_1400361AF
0x140036179  mov     edx, [r14+18h]; Length
0x14003617d  test    edx, edx
0x14003617f  jz      short loc_1400361AF
0x140036181  mov     ecx, [r14+8]
0x140036185  xor     r9d, r9d; ChargeQuota
0x140036188  add     rcx, [rdi+70h]; VirtualAddress
0x14003618c  mov     r8b, 1; SecondaryBuffer
0x14003618f  mov     [rsp+88h+Irp], rdi; Irp
0x140036194  call    cs:__imp_IoAllocateMdl
0x14003619b  nop     dword ptr [rax+rax+00h]
0x1400361a0  test    rax, rax
0x1400361a3  jnz     short loc_1400361AF
0x1400361a5  mov     ebp, 0C000009Ah
0x1400361aa  jmp     loc_14003635D
0x1400361af  mov     eax, [rbx+8]
0x1400361b2  bt      eax, 8
0x1400361b6  mov     rbp, [rsp+88h+var_58]
0x1400361bb  jnb     short loc_1400361EF
0x1400361bd  mov     eax, [r15+0A0h]
0x1400361c4  mov     rcx, rbp
0x1400361c7  mov     r9, [r15+98h]
0x1400361ce  mov     r8d, [r15+0A8h]
0x1400361d5  mov     rdx, [r15+0E0h]
0x1400361dc  mov     [rsp+88h+var_60], rdi
0x1400361e1  mov     dword ptr [rsp+88h+Irp], eax
0x1400361e5  call    AfdTLCopyRemoteAndLocalAddresses
0x1400361ea  jmp     loc_1400362F6
0x1400361ef  cmp     byte ptr [rbp+0BCh], 0
0x1400361f6  jz      loc_1400362B4
0x1400361fc  mov     rax, [r15+98h]
0x140036203  movzx   ecx, word ptr [rax+4]
0x140036207  add     cx, 2
0x14003620b  mov     [rsp+88h+Src], cx
0x140036213  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140036217  test    byte ptr [rcx+0Ah], 5
0x14003621b  jz      short loc_140036223
0x14003621d  mov     rax, [rcx+18h]
0x140036221  jmp     short loc_140036231
0x140036223  xor     edx, edx; AccessMode
0x140036225  call    cs:__imp_MmMapLockedPages
0x14003622c  nop     dword ptr [rax+rax+00h]
0x140036231  mov     rcx, [rsp+88h+var_50]
0x140036236  mov     edx, [r14+18h]
0x14003623a  add     rdx, rax
0x14003623d  mov     eax, [r14+8]
0x140036241  mov     ecx, [rcx]
0x140036243  add     rcx, 0FFFFFFFFFFFFFFFEh
0x140036247  add     rdx, rcx
0x14003624a  mov     rcx, [rdi+8]; MemoryDescriptorList
0x14003624e  add     rax, rdx
0x140036251  mov     [rsp+88h+var_50], rax
0x140036256  test    byte ptr [rcx+0Ah], 5
0x14003625a  jz      short loc_140036262
0x14003625c  mov     r9, [rcx+18h]
0x140036260  jmp     short loc_140036273
0x140036262  xor     edx, edx; AccessMode
0x140036264  call    cs:__imp_MmMapLockedPages
0x14003626b  nop     dword ptr [rax+rax+00h]
0x140036270  mov     r9, rax
0x140036273  mov     eax, [r14+18h]
0x140036277  mov     rdx, [r15+98h]
0x14003627e  add     rax, r9
0x140036281  mov     ecx, [r14+8]
0x140036285  add     rdx, 6; Src
0x140036289  movzx   r8d, [rsp+88h+Src]; Size
0x140036292  add     rcx, rax; void *
0x140036295  call    RtlMoveVolatileMemory
0x14003629a  mov     rcx, [rsp+88h+var_50]; void *
0x14003629f  lea     rdx, [rsp+88h+Src]; Src
0x1400362a7  mov     r8d, 2; Size
0x1400362ad  call    RtlCopyVolatileMemory
0x1400362b2  jmp     short loc_1400362F6
0x1400362b4  mov     rcx, [rdi+8]; MemoryDescriptorList
0x1400362b8  test    byte ptr [rcx+0Ah], 5
0x1400362bc  jz      short loc_1400362C4
0x1400362be  mov     rdx, [rcx+18h]
0x1400362c2  jmp     short loc_1400362D5
0x1400362c4  xor     edx, edx; AccessMode
0x1400362c6  call    cs:__imp_MmMapLockedPages
0x1400362cd  nop     dword ptr [rax+rax+00h]
0x1400362d2  mov     rdx, rax
0x1400362d5  mov     eax, [r14+18h]
0x1400362d9  mov     ecx, [r14+8]
0x1400362dd  add     rax, rdx
0x1400362e0  mov     r8d, [r15+0A0h]; Size
0x1400362e7  add     rcx, rax; void *
0x1400362ea  mov     rdx, [r15+98h]; Src
0x1400362f1  call    RtlMoveVolatileMemory
0x1400362f6  mov     r8, r15
0x1400362f9  mov     rdx, rbp
0x1400362fc  mov     rcx, rdi
0x1400362ff  call    AfdAcceptCore
0x140036304  mov     ebp, eax
0x140036306  test    eax, eax
0x140036308  jnz     short loc_14003635D
0x14003630a  mov     rdx, [rsp+88h+arg_10]
0x140036312  xor     r8d, r8d
0x140036315  mov     rcx, rbx
0x140036318  call    AfdNotifySockIndicateEventsUnlock
0x14003631d  mov     rcx, [rsp+88h+var_58]
0x140036322  mov     eax, [rcx+8]
0x140036325  bt      eax, 0Dh
0x140036329  jnb     short loc_140036330
0x14003632b  call    AfdDerefTLBaseEndpoint
0x140036330  mov     eax, [rbx+8]
0x140036333  bt      eax, 8
0x140036337  jb      loc_140036424
0x14003633d  lea     rcx, [rbx+90h]; ListHead
0x140036344  mov     rdx, r13; ListEntry
0x140036347  call    cs:__imp_ExpInterlockedPushEntrySList
0x14003634e  nop     dword ptr [rax+rax+00h]
0x140036353  jmp     loc_14003644A
0x140036358  mov     ebp, 0C0000120h
0x14003635d  mov     edx, ebp
0x14003635f  mov     rcx, rdi
0x140036362  call    AfdCleanupSuperAccept
0x140036367  mov     rcx, [r12+8]
0x14003636c  cmp     [rcx], r12
0x14003636f  jnz     loc_1400365C9
0x140036375  lea     rax, [rdi+0A8h]
0x14003637c  mov     [rax], r12
0x14003637f  mov     [rax+8], rcx
0x140036383  mov     [rcx], rax
0x140036386  mov     [r12+8], rax
0x14003638b  jmp     short loc_140036392
0x14003638d  mov     ebp, 0C0000120h
0x140036392  mov     eax, [rbx+8]
0x140036395  bt      eax, 8
0x140036399  jb      short loc_1400363E7
0x14003639b  cmp     dword ptr [rbx+0B0h], 0
0x1400363a2  jl      short loc_1400363E0
0x1400363a4  cmp     ebp, 0C000009Ah
0x1400363aa  jz      short loc_1400363E0
0x1400363ac  lea     rdi, [rbx+90h]
0x1400363b3  mov     rcx, rdi; SListHead
0x1400363b6  call    cs:__imp_ExQueryDepthSList
0x1400363bd  nop     dword ptr [rax+rax+00h]
0x1400363c2  mov     ecx, 7FFFh
0x1400363c7  cmp     ax, cx
0x1400363ca  jnb     short loc_1400363E0
0x1400363cc  mov     rdx, r13; ListEntry
0x1400363cf  mov     rcx, rdi; ListHead
0x1400363d2  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400363d9  nop     dword ptr [rax+rax+00h]
0x1400363de  jmp     short loc_140036418
0x1400363e0  lock inc dword ptr [rbx+0B0h]
0x1400363e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400363eb  lock xadd [rsi+30h], rax
0x1400363f1  lea     rcx, [rbx+0A0h]
0x1400363f8  sub     rax, 1
0x1400363fc  jg      loc_140036095
0x140036402  test    rax, rax
0x140036405  jz      short loc_140036410
0x140036407  mov     ecx, 0Eh
0x14003640c  int     29h; Win8: RtlFailFast(ecx)
0x14003640e  jmp     short loc_140036418
0x140036410  mov     rcx, rsi
0x140036413  call    AfdCloseConnection
0x140036418  lea     rcx, [rbx+0A0h]
0x14003641f  jmp     loc_140036095
0x140036424  or      rax, 0FFFFFFFFFFFFFFFFh
0x140036428  lock xadd [rsi+30h], rax
0x14003642e  sub     rax, 1
0x140036432  jg      short loc_14003644A
0x140036434  test    rax, rax
0x140036437  jz      short loc_140036442
0x140036439  mov     ecx, 0Eh
0x14003643e  int     29h; Win8: RtlFailFast(ecx)
0x140036440  jmp     short loc_14003644A
0x140036442  mov     rcx, rsi
0x140036445  call    AfdCloseConnection
0x14003644a  mov     rcx, [r12]
0x14003644e  cmp     rcx, r12
0x140036451  jz      short loc_14003648F
0x140036453  mov     rax, [rcx]
0x140036456  cmp     [rax+8], rcx
0x14003645a  jnz     loc_1400365C9
0x140036460  mov     rdx, [rcx+8]
0x140036464  cmp     [rdx], rcx
0x140036467  jnz     loc_1400365C9
0x14003646d  mov     [rdx], rax
0x140036470  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140036477  mov     [rax+8], rdx
0x14003647b  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140036481  call    cs:__imp_IofCompleteRequest
0x140036488  nop     dword ptr [rax+rax+00h]
0x14003648d  jmp     short loc_14003644A
0x14003648f  mov     rdx, [rdi+8]
0x140036493  mov     dword ptr [rdi+30h], 0
0x14003649a  mov     [r14+20h], rdx
0x14003649e  mov     rdx, [rsp+88h+var_48]
0x1400364a3  mov     qword ptr [rdi+8], 0
0x1400364ab  mov     [r14+30h], rdx
0x1400364af  mov     edx, [rbx+8]
0x1400364b2  bt      edx, 8
0x1400364b6  jnb     short loc_1400364C0
0x1400364b8  mov     dword ptr [r14+18h], 0
0x1400364c0  mov     rdx, r15
0x1400364c3  mov     rcx, rdi; Irp
0x1400364c6  call    AfdRestartSuperAcceptListen
0x1400364cb  mov     al, 1
0x1400364cd  jmp     loc_1400365D0
0x1400364d2  mov     r9, [rsp+88h+arg_10]
0x1400364da  mov     r8, r15
0x1400364dd  mov     rdx, [rsp+88h+var_48]
0x1400364e2  mov     rcx, rdi
0x1400364e5  call    AfdSanAcceptCore
0x1400364ea  mov     ebp, eax
0x1400364ec  cmp     eax, 103h
0x1400364f1  jnz     short loc_140036532
0x1400364f3  mov     eax, [rbx+8]
0x1400364f6  bt      eax, 8
0x1400364fa  jb      short loc_140036514
0x1400364fc  lea     rcx, [rbx+90h]; ListHead
0x140036503  mov     rdx, r13; ListEntry
0x140036506  call    cs:__imp_ExpInterlockedPushEntrySList
0x14003650d  nop     dword ptr [rax+rax+00h]
0x140036512  jmp     short loc_140036588
0x140036514  or      rax, 0FFFFFFFFFFFFFFFFh
0x140036518  lock xadd [rsi+30h], rax
0x14003651e  sub     rax, 1
0x140036522  jg      short loc_140036588
0x140036524  test    rax, rax
0x140036527  jz      short loc_140036580
0x140036529  mov     ecx, 0Eh
0x14003652e  int     29h; Win8: RtlFailFast(ecx)
0x140036530  jmp     short loc_140036588
0x140036532  mov     r9d, ebp
  ... truncated ...
```
