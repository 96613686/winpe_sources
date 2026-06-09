# AfdTransmitFile

- ea: `0x140057060`
- end: `0x140057939`
- name: `AfdTransmitFile`
- size: `2265`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14001ebf4`
- `0x14002fd5c`
- `0x14003f8b8`
- `0x14003fc3c`
- `0x140042250`
- `0x1400428ec`
- `0x140043698`
- `0x1400445b8`
- `0x1400557d0`
- `0x140055d68`
- `0x140056e80`
- `0x140057060`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072b00`
- `0x1400921c4`
- `0x140094900`

## import_xrefs

- `ntoskrnl!IoQueryFileInformation` at `0x1400574c6`
- `ntoskrnl!IoQueryFileInformation` at `0x1400574c6`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057382`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057612`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057382`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057612`
- `ntoskrnl!IoAllocateMdl` at `0x14005734e`
- `ntoskrnl!IoAllocateMdl` at `0x1400575dd`
- `ntoskrnl!IoAllocateMdl` at `0x14005734e`
- `ntoskrnl!IoAllocateMdl` at `0x1400575dd`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057176`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057225`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057176`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140057225`
- `ntoskrnl!IofCompleteRequest` at `0x1400578fd`
- `ntoskrnl!IofCompleteRequest` at `0x1400578fd`
- `ntoskrnl!IoFileObjectType` at `0x1400573c1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400573ef`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400573ef`
- `ntoskrnl!IoIs32bitProcess` at `0x14005710b`
- `ntoskrnl!IoIs32bitProcess` at `0x14005713a`
- `ntoskrnl!IoIs32bitProcess` at `0x14005710b`
- `ntoskrnl!IoIs32bitProcess` at `0x14005713a`

## pseudocode

```c
__int64 __fastcall AfdTransmitFile(PIRP Irp, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r15
  char v6; // r13
  __int64 v7; // r14
  unsigned int v8; // esi
  __int64 v9; // r12
  BOOLEAN v10; // al
  unsigned int v11; // ecx
  bool v12; // cf
  BOOLEAN v13; // al
  KPROCESSOR_MODE RequestorMode; // cl
  void *v15; // rdx
  int v16; // ecx
  void *v17; // rdx
  __int64 TpInfo; // rax
  __int64 v19; // rsi
  struct _MDL *Mdl; // rax
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 v23; // r12
  KPROCESSOR_MODE v24; // r9
  NTSTATUS v25; // eax
  struct _FILE_OBJECT *v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rsi
  __int64 v31; // r12
  struct _MDL *v32; // rax
  int v33; // eax
  __int64 v34; // r8
  NTSTATUS v36; // [rsp+30h] [rbp-108h]
  NTSTATUS v37; // [rsp+30h] [rbp-108h]
  char v38; // [rsp+35h] [rbp-103h]
  _OWORD v40[4]; // [rsp+50h] [rbp-E8h] BYREF
  ULONG ReturnedLength; // [rsp+90h] [rbp-A8h] BYREF
  PVOID Object; // [rsp+98h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-98h]
  __int128 v44; // [rsp+A8h] [rbp-90h] BYREF
  __int128 v45; // [rsp+B8h] [rbp-80h]
  __int128 v46; // [rsp+C8h] [rbp-70h]
  __int64 v47; // [rsp+D8h] [rbp-60h]
  PIRP v48; // [rsp+E0h] [rbp-58h]
  __int64 v49; // [rsp+E8h] [rbp-50h]
  __int128 FileInformation; // [rsp+F0h] [rbp-48h] BYREF
  __int64 v51; // [rsp+100h] [rbp-38h]

  v48 = Irp;
  v49 = a2;
  memset(v40, 0, sizeof(v40));
  v5 = 0;
  v43 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v47 = v7;
  if ( (*(_BYTE *)(v7 + 7) & 0x10) != 0 )
  {
    v8 = -1073741816;
LABEL_3:
    v9 = a2;
    goto LABEL_112;
  }
  if ( *(_WORD *)v7 == 6909 )
  {
    v8 = -1073741574;
    goto LABEL_3;
  }
  v10 = IoIs32bitProcess(Irp);
  v11 = *(_DWORD *)(a2 + 16);
  if ( v10 )
    v12 = v11 < 0x30;
  else
    v12 = v11 < 0x40;
  if ( v12 )
  {
    v8 = -1073741811;
    goto LABEL_3;
  }
  v38 = 0;
  v13 = IoIs32bitProcess(Irp);
  RequestorMode = Irp->RequestorMode;
  if ( v13 )
  {
    v44 = 0;
    v45 = 0;
    v46 = 0;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v15 = *(void **)(a2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(&v44, v15, 0x30u);
    else
      RtlCopyVolatileMemory(&v44, v15, 0x30u);
    v40[0] = v44;
    LODWORD(v40[1]) = v45;
    *((_QWORD *)&v40[1] + 1) = SDWORD1(v45);
    *(_QWORD *)&v40[2] = DWORD2(v45);
    DWORD2(v40[2]) = HIDWORD(v45);
    *(_QWORD *)&v40[3] = (unsigned int)v46;
    *((_QWORD *)&v40[3] + 1) = *(_QWORD *)((char *)&v46 + 4);
    v16 = DWORD2(v46);
  }
  else
  {
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v17 = *(void **)(a2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(v40, v17, 0x40u);
    else
      RtlCopyVolatileMemory(v40, v17, 0x40u);
    v16 = HIDWORD(v40[3]);
  }
  if ( (v16 & 0xFFFFFFC8) != 0 || (v16 & 0x30) == 0x30 || *((_QWORD *)&v40[1] + 1) && *(__int64 *)&v40[0] < 0 )
  {
    v8 = -1073741811;
    v9 = a2;
LABEL_112:
    if ( v6 && *(_DWORD *)(v9 + 8) )
    {
      if ( Irp->RequestorMode )
      {
        LOBYTE(v4) = 1;
        RtlWriteUCharToUser(Irp->UserBuffer, v4);
      }
      else
      {
        *(_BYTE *)Irp->UserBuffer = 1;
      }
    }
    if ( v5 )
      AfdReturnTpInfo((unsigned __int16 *)v5, BYTE1(*(_DWORD *)(v7 + 8)) & 1);
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qqD(1042, 59, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, Irp, v7, v8);
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v8;
    IofCompleteRequest(Irp, 0);
    return v8;
  }
  if ( (v16 & 0x30) == 0 )
    HIDWORD(v40[3]) = AfdDefaultTransmitWorker | v16;
  if ( (*(_DWORD *)(v7 + 8) & 0x100) != 0 )
    TpInfo = (__int64)AfdTliGetTpInfo(3u);
  else
    TpInfo = AfdTdiGetTpInfo(3u);
  v5 = TpInfo;
  v43 = TpInfo;
  if ( !TpInfo )
  {
    v8 = -1073741670;
    v9 = a2;
    goto LABEL_112;
  }
  *(_DWORD *)(TpInfo + 76) = 0;
  *(_DWORD *)(TpInfo + 92) = v40[1];
  if ( LODWORD(v40[1]) )
    v38 = 1;
  else
    *(_DWORD *)(TpInfo + 92) = AfdTransmitIoLength;
  if ( DWORD2(v40[2]) )
  {
    v19 = *(_QWORD *)(TpInfo + 64);
    *(_DWORD *)(TpInfo + 76) = 1;
    *(_QWORD *)(v19 + 8) = *(_QWORD *)&v40[2];
    *(_DWORD *)(v19 + 4) = DWORD2(v40[2]);
    *(_DWORD *)v19 = 1;
    if ( (BYTE12(v40[3]) & 0x10) != 0 )
    {
      *(_DWORD *)v19 = -2147483647;
      Mdl = IoAllocateMdl(*(PVOID *)&v40[2], DWORD2(v40[2]), 0, 1u, 0);
      *(_QWORD *)(v19 + 16) = Mdl;
      if ( !Mdl )
      {
        v8 = -1073741670;
        v9 = a2;
        goto LABEL_112;
      }
      MmProbeAndLockPages(Mdl, Irp->RequestorMode, IoReadAccess);
    }
  }
  if ( *((_QWORD *)&v40[1] + 1) )
  {
    v21 = *(unsigned int *)(v5 + 76);
    v22 = 3 * v21;
    v23 = *(_QWORD *)(v5 + 64);
    *(_DWORD *)(v5 + 76) = v21 + 1;
    *(_DWORD *)(v23 + 8 * v22) = 2;
    *(_QWORD *)(v23 + 8 * v22 + 8) = *(_QWORD *)&v40[0];
    v24 = Irp->RequestorMode;
    Object = 0;
    v25 = ObReferenceObjectByHandle(*((HANDLE *)&v40[1] + 1), 1u, (POBJECT_TYPE)IoFileObjectType, v24, &Object, 0);
    *(_QWORD *)(v23 + 8 * v22 + 16) = Object;
    v36 = v25;
    if ( v25 < 0 )
    {
      --*(_DWORD *)(v5 + 76);
      v9 = a2;
      if ( *(_DWORD *)(a2 + 8) )
      {
        if ( Irp->RequestorMode )
        {
          LOBYTE(v4) = 1;
          RtlWriteUCharToUser(Irp->UserBuffer, v4);
        }
        else
        {
          *(_BYTE *)Irp->UserBuffer = 1;
        }
      }
      v8 = v36;
      goto LABEL_112;
    }
    if ( !LODWORD(v40[1]) && (*(_DWORD *)(*(_QWORD *)(v23 + 8 * v22 + 16) + 80LL) & 0x40) == 0 )
      *(_DWORD *)(v5 + 92) = AfdLargeBufferSize;
    v26 = *(struct _FILE_OBJECT **)(v23 + 8 * v22 + 16);
    if ( (v26->Flags & 2) != 0 && !*(_QWORD *)(v23 + 8 * v22 + 8) )
      *(_QWORD *)(v23 + 8 * v22 + 8) = v26->CurrentByteOffset.QuadPart;
    if ( *((_QWORD *)&v40[0] + 1) )
    {
      if ( *((__int64 *)&v40[0] + 1) > 0x7FFFFFFF || *(__int64 *)(v23 + 8 * v22 + 8) < 0 )
      {
        v6 = 1;
        v8 = -1073741811;
        v9 = a2;
        goto LABEL_112;
      }
      v28 = DWORD2(v40[0]);
    }
    else
    {
      FileInformation = 0;
      v51 = 0;
      ReturnedLength = 0;
      v37 = IoQueryFileInformation(v26, FileStandardInformation, 0x18u, &FileInformation, &ReturnedLength);
      if ( v37 < 0 )
      {
        v6 = 1;
        v8 = v37;
        v9 = a2;
        goto LABEL_112;
      }
      v27 = *(_QWORD *)(v23 + 8 * v22 + 8);
      if ( v27 < 0
        || v27 > *((__int64 *)&FileInformation + 1)
        || (v28 = DWORD2(FileInformation) - v27, *((_QWORD *)&FileInformation + 1) - v27 > 0x7FFFFFFF) )
      {
        v6 = 1;
        v8 = -1073741811;
        v9 = a2;
        goto LABEL_112;
      }
    }
    *(_DWORD *)(v23 + 8 * v22 + 4) = v28;
  }
  if ( DWORD2(v40[3]) )
  {
    v29 = *(unsigned int *)(v5 + 76);
    v30 = 3 * v29;
    v31 = *(_QWORD *)(v5 + 64);
    *(_DWORD *)(v5 + 76) = v29 + 1;
    *(_QWORD *)(v31 + 8 * v30 + 8) = *(_QWORD *)&v40[3];
    *(_DWORD *)(v31 + 8 * v30 + 4) = DWORD2(v40[3]);
    *(_DWORD *)(v31 + 8 * v30) = 1;
    if ( (BYTE12(v40[3]) & 0x10) != 0 )
    {
      *(_DWORD *)(v31 + 24 * v29) = -2147483647;
      v32 = IoAllocateMdl(*(PVOID *)&v40[3], DWORD2(v40[3]), 0, 1u, 0);
      *(_QWORD *)(v31 + 8 * v30 + 16) = v32;
      if ( !v32 )
      {
        v8 = -1073741670;
        v9 = a2;
        goto LABEL_112;
      }
      MmProbeAndLockPages(v32, Irp->RequestorMode, IoReadAccess);
    }
  }
  *((_DWORD *)&Irp->Tail.CompletionKey + 2) = HIDWORD(v40[3]);
  if ( (BYTE12(v40[3]) & 3) == 0 )
  {
    while ( 1 )
    {
      v4 = *(unsigned int *)(v7 + 368);
      if ( (int)v4 > 0 )
        goto LABEL_77;
      if ( (_DWORD)v4 == _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 368), v4 - 1, v4) )
      {
        if ( *(_WORD *)v7 != 0xAFD2 || *(_BYTE *)(v7 + 2) != 4 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v7 + 368));
          goto LABEL_77;
        }
        v34 = *(_QWORD *)(v7 + 192);
        *(_QWORD *)(v5 + 16) = v34;
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v34 + 48)) <= 1 )
          __fastfail(0xEu);
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 368));
        goto LABEL_92;
      }
    }
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 368), *(unsigned __int8 *)(v7 + 2), 0) )
  {
LABEL_77:
    v8 = -1073741504;
    goto LABEL_3;
  }
  if ( *(_WORD *)v7 != 0xAFD2 || *(_BYTE *)(v7 + 2) != 4 )
  {
    v8 = -1073741504;
    _InterlockedExchange((volatile __int32 *)(v7 + 368), 0);
    goto LABEL_3;
  }
  v33 = *((_DWORD *)&Irp->Tail.CompletionKey + 2);
  if ( (v33 & 2) != 0 )
  {
    *((_DWORD *)&Irp->Tail.CompletionKey + 2) = v33 | 1;
    *(_BYTE *)(v7 + 2) = 7;
  }
  v34 = *(_QWORD *)(v7 + 192);
  *(_QWORD *)(v5 + 16) = v34;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v34 + 48)) <= 1 )
    __fastfail(0xEu);
LABEL_92:
  if ( (*(_DWORD *)(v7 + 8) & 0x100) != 0 )
  {
    *(_QWORD *)v5 = Irp;
  }
  else
  {
    *(_QWORD *)v5 = *(_QWORD *)(v34 + 16);
    *(_QWORD *)(v5 + 8) = *(_QWORD *)(v34 + 24);
  }
  if ( !v38
    && ((*(_DWORD *)(v7 + 8) & 0x100) != 0 || (*(_DWORD *)(v7 + 8) & 0x200) != 0)
    && (int)AfdCheckISBEvents(v34, AfdTLSockOptEnable) >= 0 )
  {
    *((_DWORD *)&Irp->Tail.CompletionKey + 2) |= 0x40u;
  }
  Irp->AssociatedIrp.MasterIrp = (struct _IRP *)v5;
  Irp->Tail.Overlay.ListEntry.Flink = 0;
  Irp->Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)1;
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  *((_DWORD *)&Irp->Tail.CompletionKey + 3) = 1;
  Irp->Tail.Overlay.DeviceQueueEntry.SortKey = 2;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(v7 + 360), (signed __int64)Irp, 0)
    || !AfdEnqueueTPacketsIrp(v7, (signed __int64)Irp) )
  {
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)AfdCancelTPackets);
    if ( (*(_DWORD *)(v7 + 8) & 0x800) != 0 || Irp->Cancel )
    {
      AfdAbortTPackets((__int64)Irp, -1073741536);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Irp->Tail.CompletionKey + 3, 0xFFFFFFFF) == 1 )
        AfdCompleteTPackets(Irp);
    }
    else if ( !AfdMaxActiveTransmitFileCount || !AfdQueueTransmit(Irp) )
    {
      AfdTPacketsWorker(Irp, v4, v34);
    }
  }
  return 259;
}

```

## disassembly

```asm
0x140057060  mov     [rsp+arg_10], rbx
0x140057065  mov     [rsp+arg_18], rsi
0x14005706a  push    rdi
0x14005706b  push    r12
0x14005706d  push    r13
0x14005706f  push    r14
0x140057071  push    r15
0x140057073  sub     rsp, 110h
0x14005707a  mov     rax, cs:__security_cookie
0x140057081  xor     rax, rsp
0x140057084  mov     [rsp+138h+var_30], rax
0x14005708c  mov     rsi, rdx
0x14005708f  mov     [rsp+138h+var_100], rdx
0x140057094  mov     rdi, rcx
0x140057097  mov     [rsp+138h+var_58], rcx
0x14005709f  mov     [rsp+138h+var_50], rdx
0x1400570a7  mov     r12d, 40h ; '@'
0x1400570ad  mov     r8d, r12d; Size
0x1400570b0  xor     edx, edx; Val
0x1400570b2  lea     rcx, [rsp+138h+var_E8]; void *
0x1400570b7  call    memset
0x1400570bc  xor     ebx, ebx
0x1400570be  mov     r15d, ebx
0x1400570c1  mov     [rsp+138h+var_98], rbx
0x1400570c9  mov     r13b, bl
0x1400570cc  mov     [rsp+138h+var_104], bl
0x1400570d0  mov     rax, [rsi+30h]
0x1400570d4  mov     r14, [rax+18h]
0x1400570d8  mov     [rsp+138h+var_60], r14
0x1400570e0  test    byte ptr [r14+7], 10h
0x1400570e5  jz      short loc_1400570F6
0x1400570e7  mov     esi, 0C0000008h
0x1400570ec  mov     r12, [rsp+138h+var_100]
0x1400570f1  jmp     loc_14005788A
0x1400570f6  mov     eax, 1AFDh
0x1400570fb  cmp     [r14], ax
0x1400570ff  jnz     short loc_140057108
0x140057101  mov     esi, 0C00000FAh
0x140057106  jmp     short loc_1400570EC
0x140057108  mov     rcx, rdi; Irp
0x14005710b  call    cs:__imp_IoIs32bitProcess
0x140057112  nop     dword ptr [rax+rax+00h]
0x140057117  mov     ecx, [rsi+10h]
0x14005711a  test    al, al
0x14005711c  jz      short loc_14005712A
0x14005711e  cmp     ecx, 30h ; '0'
0x140057121  jnb     short loc_14005712F
0x140057123  mov     esi, 0C000000Dh
0x140057128  jmp     short loc_1400570EC
0x14005712a  cmp     ecx, r12d
0x14005712d  jmp     short loc_140057121
0x14005712f  mov     [rsp+138h+var_103], bl
0x140057133  mov     [rsp+138h+var_108], ebx
0x140057137  mov     rcx, rdi; Irp
0x14005713a  call    cs:__imp_IoIs32bitProcess
0x140057141  nop     dword ptr [rax+rax+00h]
0x140057146  mov     cl, [rdi+40h]
0x140057149  test    al, al
0x14005714b  jz      loc_14005721B
0x140057151  xorps   xmm0, xmm0
0x140057154  movups  [rsp+138h+var_90], xmm0
0x14005715c  movups  [rsp+138h+var_80], xmm0
0x140057164  movups  [rsp+138h+var_70], xmm0
0x14005716c  test    cl, cl
0x14005716e  jz      short loc_140057183
0x140057170  test    byte ptr [rsi+20h], 3
0x140057174  jz      short loc_140057183
0x140057176  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005717d  nop     dword ptr [rax+rax+00h]
0x140057182  int     3; Trap to Debugger
0x140057183  mov     rdx, [rsi+20h]; Src
0x140057187  mov     r8d, 30h ; '0'; Size
0x14005718d  test    cl, cl
0x14005718f  lea     rcx, [rsp+138h+var_90]; void *
0x140057197  jz      short loc_1400571A0
0x140057199  call    RtlCopyFromUser
0x14005719e  jmp     short loc_1400571A5
0x1400571a0  call    RtlCopyVolatileMemory
0x1400571a5  mov     rax, qword ptr [rsp+138h+var_90]
0x1400571ad  mov     qword ptr [rsp+138h+var_E8], rax
0x1400571b2  mov     rax, qword ptr [rsp+138h+var_90+8]
0x1400571ba  mov     qword ptr [rsp+138h+var_E8+8], rax
0x1400571bf  mov     eax, dword ptr [rsp+138h+var_80]
0x1400571c6  mov     [rsp+138h+var_D8], eax
0x1400571ca  movsxd  rax, dword ptr [rsp+138h+var_80+4]
0x1400571d2  mov     [rsp+138h+Handle], rax
0x1400571d7  mov     eax, dword ptr [rsp+138h+var_80+8]
0x1400571de  mov     [rsp+138h+VirtualAddress], rax
0x1400571e3  mov     eax, dword ptr [rsp+138h+var_80+0Ch]
0x1400571ea  mov     [rsp+138h+Length], eax
0x1400571ee  mov     eax, dword ptr [rsp+138h+var_70]
0x1400571f5  mov     [rsp+138h+var_B8], rax
0x1400571fd  mov     eax, dword ptr [rsp+138h+var_70+4]
0x140057204  mov     dword ptr [rsp+138h+var_B0], eax
0x14005720b  mov     ecx, dword ptr [rsp+138h+var_70+8]
0x140057212  mov     dword ptr [rsp+138h+var_B0+4], ecx
0x140057219  jmp     short loc_140057255
0x14005721b  test    cl, cl
0x14005721d  jz      short loc_140057232
0x14005721f  test    byte ptr [rsi+20h], 3
0x140057223  jz      short loc_140057232
0x140057225  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14005722c  nop     dword ptr [rax+rax+00h]
0x140057231  int     3; Trap to Debugger
0x140057232  mov     rdx, [rsi+20h]; Src
0x140057236  mov     r8, r12; Size
0x140057239  test    cl, cl
0x14005723b  lea     rcx, [rsp+138h+var_E8]; void *
0x140057240  jz      short loc_140057249
0x140057242  call    RtlCopyFromUser
0x140057247  jmp     short loc_14005724E
0x140057249  call    RtlCopyVolatileMemory
0x14005724e  mov     ecx, dword ptr [rsp+138h+var_B0+4]
0x140057255  test    ecx, 0FFFFFFC8h
0x14005725b  jnz     loc_14005784B
0x140057261  mov     eax, ecx
0x140057263  and     eax, 30h
0x140057266  cmp     eax, 30h ; '0'
0x140057269  jz      loc_14005784B
0x14005726f  cmp     [rsp+138h+Handle], rbx
0x140057274  jz      short loc_140057281
0x140057276  cmp     qword ptr [rsp+138h+var_E8], rbx
0x14005727b  jl      loc_14005784B
0x140057281  test    eax, eax
0x140057283  jnz     short loc_140057292
0x140057285  or      ecx, cs:AfdDefaultTransmitWorker
0x14005728b  mov     dword ptr [rsp+138h+var_B0+4], ecx
0x140057292  mov     eax, [r14+8]
0x140057296  mov     ecx, 3
0x14005729b  bt      eax, 8
0x14005729f  jnb     short loc_1400572A8
0x1400572a1  call    AfdTliGetTpInfo
0x1400572a6  jmp     short loc_1400572AD
0x1400572a8  call    AfdTdiGetTpInfo
0x1400572ad  mov     r15, rax
0x1400572b0  mov     [rsp+138h+var_98], rax
0x1400572b8  test    rax, rax
0x1400572bb  jnz     short loc_1400572D3
0x1400572bd  mov     [rsp+138h+var_108], 0C000009Ah
0x1400572c5  mov     esi, [rsp+138h+var_108]
0x1400572c9  mov     r12, [rsp+138h+var_100]
0x1400572ce  jmp     loc_14005788A
0x1400572d3  mov     [r15+4Ch], ebx
0x1400572d7  mov     eax, [rsp+138h+var_D8]
0x1400572db  mov     [r15+5Ch], eax
0x1400572df  cmp     [rsp+138h+var_D8], ebx
0x1400572e3  jnz     short loc_1400572F1
0x1400572e5  mov     eax, cs:AfdTransmitIoLength
0x1400572eb  mov     [r15+5Ch], eax
0x1400572ef  jmp     short loc_1400572FE
0x1400572f1  mov     r12b, 1
0x1400572f4  mov     [rsp+138h+var_103], r12b
0x1400572f9  mov     [rsp+138h+var_F8], r12b
0x1400572fe  cmp     [rsp+138h+Length], ebx
0x140057302  jbe     loc_14005738E
0x140057308  mov     rsi, [r15+40h]
0x14005730c  mov     dword ptr [r15+4Ch], 1
0x140057314  mov     rax, [rsp+138h+VirtualAddress]
0x140057319  mov     [rsi+8], rax
0x14005731d  mov     eax, [rsp+138h+Length]
0x140057321  mov     [rsi+4], eax
0x140057324  mov     dword ptr [rsi], 1
0x14005732a  test    byte ptr [rsp+138h+var_B0+4], 10h
0x140057332  jz      short loc_14005738E
0x140057334  mov     dword ptr [rsi], 80000001h
0x14005733a  mov     [rsp+138h+Irp], rbx; Irp
0x14005733f  mov     r9b, 1; ChargeQuota
0x140057342  xor     r8d, r8d; SecondaryBuffer
0x140057345  mov     edx, [rsp+138h+Length]; Length
0x140057349  mov     rcx, [rsp+138h+VirtualAddress]; VirtualAddress
0x14005734e  call    cs:__imp_IoAllocateMdl
0x140057355  nop     dword ptr [rax+rax+00h]
0x14005735a  mov     [rsi+10h], rax
0x14005735e  test    rax, rax
0x140057361  jnz     short loc_140057379
0x140057363  mov     [rsp+138h+var_108], 0C000009Ah
0x14005736b  mov     esi, [rsp+138h+var_108]
0x14005736f  mov     r12, [rsp+138h+var_100]
0x140057374  jmp     loc_14005788A
0x140057379  xor     r8d, r8d; Operation
0x14005737c  mov     dl, [rdi+40h]; AccessMode
0x14005737f  mov     rcx, rax; MemoryDescriptorList
0x140057382  call    cs:__imp_MmProbeAndLockPages
0x140057389  nop     dword ptr [rax+rax+00h]
0x14005738e  cmp     [rsp+138h+Handle], rbx
0x140057393  jz      loc_140057571
0x140057399  mov     eax, [r15+4Ch]
0x14005739d  lea     rsi, [rax+rax*2]
0x1400573a1  mov     r12, [r15+40h]
0x1400573a5  inc     eax
0x1400573a7  mov     [r15+4Ch], eax
0x1400573ab  mov     dword ptr [r12+rsi*8], 2
0x1400573b3  mov     rax, qword ptr [rsp+138h+var_E8]
0x1400573b8  mov     [r12+rsi*8+8], rax
0x1400573bd  mov     r9b, [rdi+40h]; AccessMode
0x1400573c1  mov     rax, cs:__imp_IoFileObjectType
0x1400573c8  mov     r8, [rax]; ObjectType
0x1400573cb  mov     [rsp+138h+Object], rbx
0x1400573d3  mov     [rsp+138h+HandleInformation], rbx; HandleInformation
0x1400573d8  lea     rax, [rsp+138h+Object]
0x1400573e0  mov     [rsp+138h+Irp], rax; Object
0x1400573e5  mov     edx, 1; DesiredAccess
0x1400573ea  mov     rcx, [rsp+138h+Handle]; Handle
0x1400573ef  call    cs:__imp_ObReferenceObjectByHandle
0x1400573f6  nop     dword ptr [rax+rax+00h]
0x1400573fb  mov     ecx, eax
0x1400573fd  mov     rax, [rsp+138h+Object]
0x140057405  mov     [r12+rsi*8+10h], rax
0x14005740a  mov     [rsp+138h+var_108], ecx
0x14005740e  mov     eax, [rsp+138h+var_108]
0x140057412  test    eax, eax
0x140057414  jns     short loc_140057448
0x140057416  dec     dword ptr [r15+4Ch]
0x14005741a  mov     r12, [rsp+138h+var_100]
0x14005741f  cmp     dword ptr [r12+8], 1
0x140057425  jb      short loc_14005743F
0x140057427  mov     rax, [rdi+70h]
0x14005742b  cmp     [rdi+40h], bl
0x14005742e  jz      short loc_14005743C
0x140057430  mov     dl, 1
0x140057432  mov     rcx, rax
0x140057435  call    RtlWriteUCharToUser
0x14005743a  jmp     short loc_14005743F
0x14005743c  mov     byte ptr [rax], 1
0x14005743f  mov     esi, [rsp+138h+var_108]
0x140057443  jmp     loc_14005788A
0x140057448  cmp     [rsp+138h+var_D8], ebx
0x14005744c  jnz     short loc_140057465
0x14005744e  mov     rax, [r12+rsi*8+10h]
0x140057453  mov     ecx, [rax+50h]
0x140057456  test    cl, 40h
0x140057459  jnz     short loc_140057465
0x14005745b  mov     eax, cs:AfdLargeBufferSize
0x140057461  mov     [r15+5Ch], eax
0x140057465  mov     rcx, [r12+rsi*8+10h]; FileObject
0x14005746a  mov     eax, [rcx+50h]
0x14005746d  test    al, 2
0x14005746f  jz      short loc_140057481
0x140057471  cmp     [r12+rsi*8+8], rbx
0x140057476  jnz     short loc_140057481
0x140057478  mov     rax, [rcx+68h]
0x14005747c  mov     [r12+rsi*8+8], rax
0x140057481  cmp     qword ptr [rsp+138h+var_E8+8], rbx
0x140057486  jnz     loc_140057535
0x14005748c  xorps   xmm0, xmm0
0x14005748f  xor     eax, eax
0x140057491  movups  [rsp+138h+FileInformation], xmm0
0x140057499  mov     [rsp+138h+var_38], rax
0x1400574a1  mov     [rsp+138h+ReturnedLength], ebx
0x1400574a8  lea     rax, [rsp+138h+ReturnedLength]
0x1400574b0  mov     [rsp+138h+Irp], rax; ReturnedLength
0x1400574b5  lea     r9, [rsp+138h+FileInformation]; FileInformation
0x1400574bd  mov     edx, 5; FileInformationClass
0x1400574c2  lea     r8d, [rdx+13h]; Length
0x1400574c6  call    cs:__imp_IoQueryFileInformation
0x1400574cd  nop     dword ptr [rax+rax+00h]
0x1400574d2  mov     [rsp+138h+var_108], eax
0x1400574d6  mov     eax, [rsp+138h+var_108]
0x1400574da  test    eax, eax
0x1400574dc  jns     short loc_1400574F4
0x1400574de  mov     r13b, 1
0x1400574e1  mov     [rsp+138h+var_104], r13b
0x1400574e6  mov     esi, [rsp+138h+var_108]
0x1400574ea  mov     r12, [rsp+138h+var_100]
0x1400574ef  jmp     loc_14005788A
0x1400574f4  mov     rcx, [r12+rsi*8+8]
0x1400574f9  test    rcx, rcx
0x1400574fc  js      short loc_140057516
0x1400574fe  mov     rax, qword ptr [rsp+138h+FileInformation+8]
0x140057506  cmp     rcx, rax
0x140057509  jg      short loc_140057516
0x14005750b  sub     rax, rcx
0x14005750e  cmp     rax, 7FFFFFFFh
0x140057514  jle     short loc_14005754B
0x140057516  mov     esi, 0C000000Dh
0x14005751b  mov     [rsp+138h+var_108], esi
0x14005751f  mov     r13b, 1
0x140057522  mov     [rsp+138h+var_104], r13b
0x140057527  mov     esi, [rsp+138h+var_108]
0x14005752b  mov     r12, [rsp+138h+var_100]
0x140057530  jmp     loc_14005788A
0x140057535  cmp     qword ptr [rsp+138h+var_E8+8], 7FFFFFFFh
0x14005753e  jg      short loc_140057552
0x140057540  cmp     [r12+rsi*8+8], rbx
0x140057545  jl      short loc_140057552
0x140057547  mov     eax, dword ptr [rsp+138h+var_E8+8]
0x14005754b  mov     [r12+rsi*8+4], eax
0x140057550  jmp     short loc_140057571
0x140057552  mov     esi, 0C000000Dh
0x140057557  mov     [rsp+138h+var_108], esi
0x14005755b  mov     r13b, 1
0x14005755e  mov     [rsp+138h+var_104], r13b
0x140057563  mov     esi, [rsp+138h+var_108]
0x140057567  mov     r12, [rsp+138h+var_100]
0x14005756c  jmp     loc_14005788A
0x140057571  cmp     dword ptr [rsp+138h+var_B0], ebx
0x140057578  jbe     loc_14005761E
0x14005757e  mov     eax, [r15+4Ch]
0x140057582  lea     rsi, [rax+rax*2]
0x140057586  mov     r12, [r15+40h]
  ... truncated ...
```
