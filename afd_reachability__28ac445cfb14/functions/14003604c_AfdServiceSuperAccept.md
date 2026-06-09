# AfdServiceSuperAccept

- ea: `0x14003604c`
- end: `0x1400365c9`
- name: `AfdServiceSuperAccept`
- size: `1405`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002d8d0`
- `0x14002e9c0`
- `0x140059910`

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
- `0x14003604c`
- `0x1400366e8`
- `0x1400726d0`
- `0x1400726e0`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036075`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140036075`
- `ntoskrnl!MmMapLockedPages` at `0x140036205`
- `ntoskrnl!MmMapLockedPages` at `0x140036244`
- `ntoskrnl!MmMapLockedPages` at `0x1400362a6`
- `ntoskrnl!MmMapLockedPages` at `0x140036205`
- `ntoskrnl!MmMapLockedPages` at `0x140036244`
- `ntoskrnl!MmMapLockedPages` at `0x1400362a6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036327`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400363b2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400364e6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140036327`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400363b2`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400364e6`
- `ntoskrnl!ExQueryDepthSList` at `0x140036396`
- `ntoskrnl!ExQueryDepthSList` at `0x140036396`
- `ntoskrnl!IoAllocateMdl` at `0x140036174`
- `ntoskrnl!IoAllocateMdl` at `0x140036174`
- `ntoskrnl!IofCompleteRequest` at `0x140036461`
- `ntoskrnl!IofCompleteRequest` at `0x140036535`
- `ntoskrnl!IofCompleteRequest` at `0x14003659b`
- `ntoskrnl!IofCompleteRequest` at `0x140036461`
- `ntoskrnl!IofCompleteRequest` at `0x140036535`
- `ntoskrnl!IofCompleteRequest` at `0x14003659b`

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
0x14003604c  mov     [rsp+arg_8], rbx
0x140036051  mov     [rsp+arg_10], r8
0x140036056  push    rbp
0x140036057  push    rsi
0x140036058  push    rdi
0x140036059  push    r12
0x14003605b  push    r13
0x14003605d  push    r14
0x14003605f  push    r15
0x140036061  sub     rsp, 50h
0x140036065  mov     rbx, rcx
0x140036068  mov     r12, r9
0x14003606b  add     rcx, 0A0h; ListHead
0x140036072  mov     r15, rdx
0x140036075  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003607c  nop     dword ptr [rax+rax+00h]
0x140036081  mov     r13, rax
0x140036084  test    rax, rax
0x140036087  jz      loc_1400365B0
0x14003608d  xor     edi, edi
0x14003608f  lea     rsi, [rax-0B0h]
0x140036096  xchg    rdi, [rsi+28h]
0x14003609a  test    rdi, rdi
0x14003609d  jz      loc_14003636D
0x1400360a3  xor     eax, eax
0x1400360a5  xchg    rax, [rdi+68h]
0x1400360a9  test    rax, rax
0x1400360ac  jz      loc_140036338
0x1400360b2  mov     r14, [rdi+0B8h]
0x1400360b9  mov     rax, [r14+20h]
0x1400360bd  lea     rcx, [r14+10h]
0x1400360c1  mov     [rsp+88h+var_48], rax
0x1400360c6  mov     [rsp+88h+var_50], rcx
0x1400360cb  mov     rax, [rax+18h]
0x1400360cf  mov     [rsp+88h+var_58], rax
0x1400360d4  mov     eax, [rbx+8]
0x1400360d7  bt      eax, 8
0x1400360db  jb      short loc_1400360EA
0x1400360dd  mov     eax, [rcx]
0x1400360df  cmp     [r15+0A0h], eax
0x1400360e6  ja      short loc_140036125
0x1400360e8  jmp     short loc_1400360EF
0x1400360ea  mov     [rsp+88h+var_50], rcx
0x1400360ef  mov     eax, [rbx+8]
0x1400360f2  bt      eax, 8
0x1400360f6  jnb     short loc_140036106
0x1400360f8  mov     eax, [r15+0A0h]
0x1400360ff  add     eax, 6
0x140036102  cmp     eax, [rcx]
0x140036104  ja      short loc_140036125
0x140036106  mov     eax, [rbx+8]
0x140036109  bt      eax, 8
0x14003610d  jnb     short loc_14003612F
0x14003610f  mov     ecx, [r14+18h]
0x140036113  test    ecx, ecx
0x140036115  jz      short loc_14003612F
0x140036117  mov     eax, [r15+0A8h]
0x14003611e  add     eax, 6
0x140036121  cmp     eax, ecx
0x140036123  jbe     short loc_14003612F
0x140036125  mov     ebp, 0C0000023h
0x14003612a  jmp     loc_14003633D
0x14003612f  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140036133  call    AfdMapMdlChain
0x140036138  mov     ebp, eax
0x14003613a  test    eax, eax
0x14003613c  js      loc_14003633D
0x140036142  test    dword ptr [r15+4], 20000000h
0x14003614a  jnz     loc_1400364B2
0x140036150  mov     eax, [rbx+8]
0x140036153  bt      eax, 8
0x140036157  jb      short loc_14003618F
0x140036159  mov     edx, [r14+18h]; Length
0x14003615d  test    edx, edx
0x14003615f  jz      short loc_14003618F
0x140036161  mov     ecx, [r14+8]
0x140036165  xor     r9d, r9d; ChargeQuota
0x140036168  add     rcx, [rdi+70h]; VirtualAddress
0x14003616c  mov     r8b, 1; SecondaryBuffer
0x14003616f  mov     [rsp+88h+Irp], rdi; Irp
0x140036174  call    cs:__imp_IoAllocateMdl
0x14003617b  nop     dword ptr [rax+rax+00h]
0x140036180  test    rax, rax
0x140036183  jnz     short loc_14003618F
0x140036185  mov     ebp, 0C000009Ah
0x14003618a  jmp     loc_14003633D
0x14003618f  mov     eax, [rbx+8]
0x140036192  bt      eax, 8
0x140036196  mov     rbp, [rsp+88h+var_58]
0x14003619b  jnb     short loc_1400361CF
0x14003619d  mov     eax, [r15+0A0h]
0x1400361a4  mov     rcx, rbp
0x1400361a7  mov     r9, [r15+98h]
0x1400361ae  mov     r8d, [r15+0A8h]
0x1400361b5  mov     rdx, [r15+0E0h]
0x1400361bc  mov     [rsp+88h+var_60], rdi
0x1400361c1  mov     dword ptr [rsp+88h+Irp], eax
0x1400361c5  call    AfdTLCopyRemoteAndLocalAddresses
0x1400361ca  jmp     loc_1400362D6
0x1400361cf  cmp     byte ptr [rbp+0BCh], 0
0x1400361d6  jz      loc_140036294
0x1400361dc  mov     rax, [r15+98h]
0x1400361e3  movzx   ecx, word ptr [rax+4]
0x1400361e7  add     cx, 2
0x1400361eb  mov     [rsp+88h+Src], cx
0x1400361f3  mov     rcx, [rdi+8]; MemoryDescriptorList
0x1400361f7  test    byte ptr [rcx+0Ah], 5
0x1400361fb  jz      short loc_140036203
0x1400361fd  mov     rax, [rcx+18h]
0x140036201  jmp     short loc_140036211
0x140036203  xor     edx, edx; AccessMode
0x140036205  call    cs:__imp_MmMapLockedPages
0x14003620c  nop     dword ptr [rax+rax+00h]
0x140036211  mov     rcx, [rsp+88h+var_50]
0x140036216  mov     edx, [r14+18h]
0x14003621a  add     rdx, rax
0x14003621d  mov     eax, [r14+8]
0x140036221  mov     ecx, [rcx]
0x140036223  add     rcx, 0FFFFFFFFFFFFFFFEh
0x140036227  add     rdx, rcx
0x14003622a  mov     rcx, [rdi+8]; MemoryDescriptorList
0x14003622e  add     rax, rdx
0x140036231  mov     [rsp+88h+var_50], rax
0x140036236  test    byte ptr [rcx+0Ah], 5
0x14003623a  jz      short loc_140036242
0x14003623c  mov     r9, [rcx+18h]
0x140036240  jmp     short loc_140036253
0x140036242  xor     edx, edx; AccessMode
0x140036244  call    cs:__imp_MmMapLockedPages
0x14003624b  nop     dword ptr [rax+rax+00h]
0x140036250  mov     r9, rax
0x140036253  mov     eax, [r14+18h]
0x140036257  mov     rdx, [r15+98h]
0x14003625e  add     rax, r9
0x140036261  mov     ecx, [r14+8]
0x140036265  add     rdx, 6; Src
0x140036269  movzx   r8d, [rsp+88h+Src]; Size
0x140036272  add     rcx, rax; void *
0x140036275  call    RtlMoveVolatileMemory
0x14003627a  mov     rcx, [rsp+88h+var_50]; void *
0x14003627f  lea     rdx, [rsp+88h+Src]; Src
0x140036287  mov     r8d, 2; Size
0x14003628d  call    RtlCopyVolatileMemory
0x140036292  jmp     short loc_1400362D6
0x140036294  mov     rcx, [rdi+8]; MemoryDescriptorList
0x140036298  test    byte ptr [rcx+0Ah], 5
0x14003629c  jz      short loc_1400362A4
0x14003629e  mov     rdx, [rcx+18h]
0x1400362a2  jmp     short loc_1400362B5
0x1400362a4  xor     edx, edx; AccessMode
0x1400362a6  call    cs:__imp_MmMapLockedPages
0x1400362ad  nop     dword ptr [rax+rax+00h]
0x1400362b2  mov     rdx, rax
0x1400362b5  mov     eax, [r14+18h]
0x1400362b9  mov     ecx, [r14+8]
0x1400362bd  add     rax, rdx
0x1400362c0  mov     r8d, [r15+0A0h]; Size
0x1400362c7  add     rcx, rax; void *
0x1400362ca  mov     rdx, [r15+98h]; Src
0x1400362d1  call    RtlMoveVolatileMemory
0x1400362d6  mov     r8, r15
0x1400362d9  mov     rdx, rbp
0x1400362dc  mov     rcx, rdi
0x1400362df  call    AfdAcceptCore
0x1400362e4  mov     ebp, eax
0x1400362e6  test    eax, eax
0x1400362e8  jnz     short loc_14003633D
0x1400362ea  mov     rdx, [rsp+88h+arg_10]
0x1400362f2  xor     r8d, r8d
0x1400362f5  mov     rcx, rbx
0x1400362f8  call    AfdNotifySockIndicateEventsUnlock
0x1400362fd  mov     rcx, [rsp+88h+var_58]
0x140036302  mov     eax, [rcx+8]
0x140036305  bt      eax, 0Dh
0x140036309  jnb     short loc_140036310
0x14003630b  call    AfdDerefTLBaseEndpoint
0x140036310  mov     eax, [rbx+8]
0x140036313  bt      eax, 8
0x140036317  jb      loc_140036404
0x14003631d  lea     rcx, [rbx+90h]; ListHead
0x140036324  mov     rdx, r13; ListEntry
0x140036327  call    cs:__imp_ExpInterlockedPushEntrySList
0x14003632e  nop     dword ptr [rax+rax+00h]
0x140036333  jmp     loc_14003642A
0x140036338  mov     ebp, 0C0000120h
0x14003633d  mov     edx, ebp
0x14003633f  mov     rcx, rdi
0x140036342  call    AfdCleanupSuperAccept
0x140036347  mov     rcx, [r12+8]
0x14003634c  cmp     [rcx], r12
0x14003634f  jnz     loc_1400365A9
0x140036355  lea     rax, [rdi+0A8h]
0x14003635c  mov     [rax], r12
0x14003635f  mov     [rax+8], rcx
0x140036363  mov     [rcx], rax
0x140036366  mov     [r12+8], rax
0x14003636b  jmp     short loc_140036372
0x14003636d  mov     ebp, 0C0000120h
0x140036372  mov     eax, [rbx+8]
0x140036375  bt      eax, 8
0x140036379  jb      short loc_1400363C7
0x14003637b  cmp     dword ptr [rbx+0B0h], 0
0x140036382  jl      short loc_1400363C0
0x140036384  cmp     ebp, 0C000009Ah
0x14003638a  jz      short loc_1400363C0
0x14003638c  lea     rdi, [rbx+90h]
0x140036393  mov     rcx, rdi; SListHead
0x140036396  call    cs:__imp_ExQueryDepthSList
0x14003639d  nop     dword ptr [rax+rax+00h]
0x1400363a2  mov     ecx, 7FFFh
0x1400363a7  cmp     ax, cx
0x1400363aa  jnb     short loc_1400363C0
0x1400363ac  mov     rdx, r13; ListEntry
0x1400363af  mov     rcx, rdi; ListHead
0x1400363b2  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400363b9  nop     dword ptr [rax+rax+00h]
0x1400363be  jmp     short loc_1400363F8
0x1400363c0  lock inc dword ptr [rbx+0B0h]
0x1400363c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400363cb  lock xadd [rsi+30h], rax
0x1400363d1  lea     rcx, [rbx+0A0h]
0x1400363d8  sub     rax, 1
0x1400363dc  jg      loc_140036075
0x1400363e2  test    rax, rax
0x1400363e5  jz      short loc_1400363F0
0x1400363e7  mov     ecx, 0Eh
0x1400363ec  int     29h; Win8: RtlFailFast(ecx)
0x1400363ee  jmp     short loc_1400363F8
0x1400363f0  mov     rcx, rsi
0x1400363f3  call    AfdCloseConnection
0x1400363f8  lea     rcx, [rbx+0A0h]
0x1400363ff  jmp     loc_140036075
0x140036404  or      rax, 0FFFFFFFFFFFFFFFFh
0x140036408  lock xadd [rsi+30h], rax
0x14003640e  sub     rax, 1
0x140036412  jg      short loc_14003642A
0x140036414  test    rax, rax
0x140036417  jz      short loc_140036422
0x140036419  mov     ecx, 0Eh
0x14003641e  int     29h; Win8: RtlFailFast(ecx)
0x140036420  jmp     short loc_14003642A
0x140036422  mov     rcx, rsi
0x140036425  call    AfdCloseConnection
0x14003642a  mov     rcx, [r12]
0x14003642e  cmp     rcx, r12
0x140036431  jz      short loc_14003646F
0x140036433  mov     rax, [rcx]
0x140036436  cmp     [rax+8], rcx
0x14003643a  jnz     loc_1400365A9
0x140036440  mov     rdx, [rcx+8]
0x140036444  cmp     [rdx], rcx
0x140036447  jnz     loc_1400365A9
0x14003644d  mov     [rdx], rax
0x140036450  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140036457  mov     [rax+8], rdx
0x14003645b  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140036461  call    cs:__imp_IofCompleteRequest
0x140036468  nop     dword ptr [rax+rax+00h]
0x14003646d  jmp     short loc_14003642A
0x14003646f  mov     rdx, [rdi+8]
0x140036473  mov     dword ptr [rdi+30h], 0
0x14003647a  mov     [r14+20h], rdx
0x14003647e  mov     rdx, [rsp+88h+var_48]
0x140036483  mov     qword ptr [rdi+8], 0
0x14003648b  mov     [r14+30h], rdx
0x14003648f  mov     edx, [rbx+8]
0x140036492  bt      edx, 8
0x140036496  jnb     short loc_1400364A0
0x140036498  mov     dword ptr [r14+18h], 0
0x1400364a0  mov     rdx, r15
0x1400364a3  mov     rcx, rdi; Irp
0x1400364a6  call    AfdRestartSuperAcceptListen
0x1400364ab  mov     al, 1
0x1400364ad  jmp     loc_1400365B0
0x1400364b2  mov     r9, [rsp+88h+arg_10]
0x1400364ba  mov     r8, r15
0x1400364bd  mov     rdx, [rsp+88h+var_48]
0x1400364c2  mov     rcx, rdi
0x1400364c5  call    AfdSanAcceptCore
0x1400364ca  mov     ebp, eax
0x1400364cc  cmp     eax, 103h
0x1400364d1  jnz     short loc_140036512
0x1400364d3  mov     eax, [rbx+8]
0x1400364d6  bt      eax, 8
0x1400364da  jb      short loc_1400364F4
0x1400364dc  lea     rcx, [rbx+90h]; ListHead
0x1400364e3  mov     rdx, r13; ListEntry
0x1400364e6  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400364ed  nop     dword ptr [rax+rax+00h]
0x1400364f2  jmp     short loc_140036568
0x1400364f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400364f8  lock xadd [rsi+30h], rax
0x1400364fe  sub     rax, 1
0x140036502  jg      short loc_140036568
0x140036504  test    rax, rax
0x140036507  jz      short loc_140036560
0x140036509  mov     ecx, 0Eh
0x14003650e  int     29h; Win8: RtlFailFast(ecx)
0x140036510  jmp     short loc_140036568
0x140036512  mov     r9d, ebp
  ... truncated ...
```
