# AfdTransmitFile

- ea: `0x140057100`
- end: `0x140057a28`
- name: `AfdTransmitFile`
- size: `2344`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14001ebf4`
- `0x14002fd7c`
- `0x14003f8d8`
- `0x14003fc5c`
- `0x140042270`
- `0x14004290c`
- `0x1400436b8`
- `0x1400445d8`
- `0x140055870`
- `0x140055e08`
- `0x140056f20`
- `0x140057100`
- `0x140058bf0`
- `0x140072840`
- `0x140072870`
- `0x140072c80`
- `0x1400921c4`
- `0x140094900`

## import_xrefs

- `ntoskrnl!IoQueryFileInformation` at `0x140057568`
- `ntoskrnl!IoQueryFileInformation` at `0x140057568`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057424`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057711`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057424`
- `ntoskrnl!MmProbeAndLockPages` at `0x140057711`
- `ntoskrnl!IoAllocateMdl` at `0x1400573f5`
- `ntoskrnl!IoAllocateMdl` at `0x1400576dc`
- `ntoskrnl!IoAllocateMdl` at `0x1400573f5`
- `ntoskrnl!IoAllocateMdl` at `0x1400576dc`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005721a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400572cb`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14005721a`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400572cb`
- `ntoskrnl!IofCompleteRequest` at `0x1400579ec`
- `ntoskrnl!IofCompleteRequest` at `0x1400579ec`
- `ntoskrnl!IoFileObjectType` at `0x140057463`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057491`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140057491`
- `ntoskrnl!IoIs32bitProcess` at `0x1400571a9`
- `ntoskrnl!IoIs32bitProcess` at `0x1400571dc`
- `ntoskrnl!IoIs32bitProcess` at `0x1400571a9`
- `ntoskrnl!IoIs32bitProcess` at `0x1400571dc`

## pseudocode

```c
__int64 __fastcall AfdTransmitFile(PIRP Irp, __int64 a2)
{
  __int64 v2; // r12
  __int64 v4; // rdx
  __int64 v5; // r15
  char v6; // r13
  __int64 v7; // r14
  unsigned int v8; // edi
  BOOLEAN v9; // al
  unsigned int v10; // ecx
  bool v11; // cf
  BOOLEAN v12; // al
  KPROCESSOR_MODE RequestorMode; // cl
  void *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  void *v17; // rdx
  __int64 TpInfo; // rax
  __int64 v19; // rdi
  struct _MDL *Mdl; // rax
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // r12
  KPROCESSOR_MODE v24; // r9
  NTSTATUS v25; // eax
  struct _FILE_OBJECT *v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v30; // rax
  __int64 v31; // rdi
  __int64 v32; // r12
  struct _MDL *v33; // rax
  int v34; // eax
  __int64 v35; // r8
  NTSTATUS v37; // [rsp+34h] [rbp-114h]
  NTSTATUS v38; // [rsp+34h] [rbp-114h]
  char v39; // [rsp+38h] [rbp-110h]
  _OWORD v41[4]; // [rsp+50h] [rbp-F8h] BYREF
  ULONG ReturnedLength; // [rsp+90h] [rbp-B8h] BYREF
  PVOID Object; // [rsp+98h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-A8h]
  __int128 v45; // [rsp+A8h] [rbp-A0h] BYREF
  __int128 v46; // [rsp+B8h] [rbp-90h]
  __int128 v47; // [rsp+C8h] [rbp-80h]
  __int64 v48; // [rsp+D8h] [rbp-70h]
  __int64 v49; // [rsp+E0h] [rbp-68h]
  PIRP v50; // [rsp+E8h] [rbp-60h]
  __int64 v51; // [rsp+F0h] [rbp-58h]
  __int128 FileInformation; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v53; // [rsp+108h] [rbp-40h]

  v2 = a2;
  v50 = Irp;
  v51 = a2;
  memset(v41, 0, sizeof(v41));
  v5 = 0;
  v44 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(v2 + 48) + 24LL);
  v49 = v7;
  if ( (*(_BYTE *)(v7 + 7) & 0x10) != 0 )
  {
    v8 = -1073741816;
    goto LABEL_116;
  }
  if ( *(_WORD *)v7 == 6909 )
  {
    v8 = -1073741574;
    goto LABEL_116;
  }
  v9 = IoIs32bitProcess(Irp);
  v10 = *(_DWORD *)(v2 + 16);
  if ( v9 )
    v11 = v10 < 0x30;
  else
    v11 = v10 < 0x40;
  if ( v11 )
  {
    v8 = -1073741811;
    goto LABEL_116;
  }
  v39 = 0;
  v12 = IoIs32bitProcess(Irp);
  RequestorMode = Irp->RequestorMode;
  if ( v12 )
  {
    v45 = 0;
    v46 = 0;
    v47 = 0;
    if ( RequestorMode && (*(_BYTE *)(v2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v14 = *(void **)(v2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(&v45, v14, 0x30u);
    else
      RtlCopyVolatileMemory(&v45, v14, 0x30u);
    v15 = v45;
    v41[0] = v45;
    LODWORD(v41[1]) = v46;
    v16 = SDWORD1(v46);
    *((_QWORD *)&v41[1] + 1) = SDWORD1(v46);
    *(_QWORD *)&v41[2] = DWORD2(v46);
    DWORD2(v41[2]) = HIDWORD(v46);
    *(_QWORD *)&v41[3] = (unsigned int)v47;
    *((_QWORD *)&v41[3] + 1) = *(_QWORD *)((char *)&v47 + 4);
    v4 = DWORD2(v47);
  }
  else
  {
    if ( RequestorMode && (*(_BYTE *)(v2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v17 = *(void **)(v2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(v41, v17, 0x40u);
    else
      RtlCopyVolatileMemory(v41, v17, 0x40u);
    v4 = HIDWORD(v41[3]);
    v16 = *((_QWORD *)&v41[1] + 1);
    v15 = *(_QWORD *)&v41[0];
  }
  if ( (v4 & 0xFFFFFFC8) != 0 || (v4 & 0x30) == 0x30 || v16 && v15 < 0 )
  {
    v8 = -1073741811;
LABEL_116:
    if ( v6 && *(_DWORD *)(v2 + 8) )
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
      WPP_SF_qqD(1042, 59, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, Irp, v7, v8);
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v8;
    IofCompleteRequest(Irp, 0);
    return v8;
  }
  if ( (v4 & 0x30) == 0 )
    HIDWORD(v41[3]) = AfdDefaultTransmitWorker | v4;
  if ( (*(_DWORD *)(v7 + 8) & 0x100) != 0 )
    TpInfo = AfdTliGetTpInfo(3);
  else
    TpInfo = AfdTdiGetTpInfo(3);
  v5 = TpInfo;
  v44 = TpInfo;
  if ( !TpInfo )
  {
    v8 = -1073741670;
    goto LABEL_116;
  }
  *(_DWORD *)(TpInfo + 76) = 0;
  *(_DWORD *)(TpInfo + 92) = v41[1];
  if ( LODWORD(v41[1]) )
    v39 = 1;
  else
    *(_DWORD *)(TpInfo + 92) = AfdTransmitIoLength;
  if ( DWORD2(v41[2]) )
  {
    v19 = *(_QWORD *)(TpInfo + 64);
    *(_DWORD *)(TpInfo + 76) = 1;
    *(_QWORD *)(v19 + 8) = *(_QWORD *)&v41[2];
    *(_DWORD *)(v19 + 4) = DWORD2(v41[2]);
    *(_DWORD *)v19 = 1;
    if ( (BYTE12(v41[3]) & 0x10) != 0 )
    {
      *(_DWORD *)v19 = -2147483647;
      Mdl = IoAllocateMdl(*(PVOID *)&v41[2], DWORD2(v41[2]), 0, 1u, 0);
      *(_QWORD *)(v19 + 16) = Mdl;
      if ( !Mdl )
      {
        v8 = -1073741670;
        goto LABEL_116;
      }
      MmProbeAndLockPages(Mdl, Irp->RequestorMode, IoReadAccess);
    }
  }
  if ( *((_QWORD *)&v41[1] + 1) )
  {
    v21 = *(unsigned int *)(v5 + 76);
    v22 = 3 * v21;
    v23 = *(_QWORD *)(v5 + 64);
    *(_DWORD *)(v5 + 76) = v21 + 1;
    *(_DWORD *)(v23 + 8 * v22) = 2;
    *(_QWORD *)(v23 + 8 * v22 + 8) = *(_QWORD *)&v41[0];
    v24 = Irp->RequestorMode;
    Object = 0;
    v25 = ObReferenceObjectByHandle(*((HANDLE *)&v41[1] + 1), 1u, (POBJECT_TYPE)IoFileObjectType, v24, &Object, 0);
    *(_QWORD *)(v23 + 8 * v22 + 16) = Object;
    v37 = v25;
    if ( v25 < 0 )
    {
      --*(_DWORD *)(v5 + 76);
      v2 = a2;
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
      v8 = v37;
      goto LABEL_116;
    }
    if ( !LODWORD(v41[1]) && (*(_DWORD *)(*(_QWORD *)(v23 + 8 * v22 + 16) + 80LL) & 0x40) == 0 )
      *(_DWORD *)(v5 + 92) = AfdLargeBufferSize;
    v26 = *(struct _FILE_OBJECT **)(v23 + 8 * v22 + 16);
    if ( (v26->Flags & 2) != 0 && !*(_QWORD *)(v23 + 8 * v22 + 8) )
      *(_QWORD *)(v23 + 8 * v22 + 8) = v26->CurrentByteOffset.QuadPart;
    if ( *((_QWORD *)&v41[0] + 1) )
    {
      if ( *((__int64 *)&v41[0] + 1) > 0x7FFFFFFF || *(__int64 *)(v23 + 8 * v22 + 8) < 0 )
      {
        v6 = 1;
        v8 = -1073741811;
        v2 = a2;
        goto LABEL_116;
      }
      v28 = DWORD2(v41[0]);
    }
    else
    {
      FileInformation = 0;
      v53 = 0;
      ReturnedLength = 0;
      v38 = IoQueryFileInformation(v26, FileStandardInformation, 0x18u, &FileInformation, &ReturnedLength);
      if ( v38 < 0 )
      {
        v6 = 1;
        v8 = v38;
        v2 = a2;
        goto LABEL_116;
      }
      v27 = *(_QWORD *)(v23 + 8 * v22 + 8);
      if ( v27 < 0
        || v27 > *((__int64 *)&FileInformation + 1)
        || (v28 = DWORD2(FileInformation) - v27, *((_QWORD *)&FileInformation + 1) - v27 > 0x7FFFFFFF) )
      {
        v6 = 1;
        v8 = -1073741811;
        v2 = a2;
        goto LABEL_116;
      }
    }
    *(_DWORD *)(v23 + 8 * v22 + 4) = v28;
    v48 = (unsigned int)Feature_AfdtransmitFile_Overflow_Fix__private_featureState;
    if ( (Feature_AfdtransmitFile_Overflow_Fix__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_AfdtransmitFile_Overflow_Fix__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_AfdtransmitFile_Overflow_Fix__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline
      && 0x7FFFFFFFFFFFFFFFLL - *(_QWORD *)(v23 + 8 * v22 + 8) < *(unsigned int *)(v23 + 8 * v22 + 4) )
    {
      v6 = 1;
      v8 = -1073741811;
      v2 = a2;
      goto LABEL_116;
    }
  }
  if ( DWORD2(v41[3]) )
  {
    v30 = *(unsigned int *)(v5 + 76);
    v31 = 3 * v30;
    v32 = *(_QWORD *)(v5 + 64);
    *(_DWORD *)(v5 + 76) = v30 + 1;
    *(_QWORD *)(v32 + 8 * v31 + 8) = *(_QWORD *)&v41[3];
    *(_DWORD *)(v32 + 8 * v31 + 4) = DWORD2(v41[3]);
    *(_DWORD *)(v32 + 8 * v31) = 1;
    if ( (BYTE12(v41[3]) & 0x10) != 0 )
    {
      *(_DWORD *)(v32 + 24 * v30) = -2147483647;
      v33 = IoAllocateMdl(*(PVOID *)&v41[3], DWORD2(v41[3]), 0, 1u, 0);
      *(_QWORD *)(v32 + 8 * v31 + 16) = v33;
      if ( !v33 )
      {
        v8 = -1073741670;
        v2 = a2;
        goto LABEL_116;
      }
      MmProbeAndLockPages(v33, Irp->RequestorMode, IoReadAccess);
    }
  }
  *((_DWORD *)&Irp->Tail.CompletionKey + 2) = HIDWORD(v41[3]);
  if ( (BYTE12(v41[3]) & 3) == 0 )
  {
    while ( 1 )
    {
      v4 = *(unsigned int *)(v7 + 368);
      if ( (int)v4 > 0 )
        goto LABEL_81;
      if ( (_DWORD)v4 == _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 368), v4 - 1, v4) )
      {
        if ( *(_WORD *)v7 != 0xAFD2 || *(_BYTE *)(v7 + 2) != 4 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v7 + 368));
          goto LABEL_81;
        }
        v35 = *(_QWORD *)(v7 + 192);
        *(_QWORD *)(v5 + 16) = v35;
        if ( _InterlockedIncrement64((volatile signed __int64 *)(v35 + 48)) <= 1 )
          __fastfail(0xEu);
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 368));
        goto LABEL_96;
      }
    }
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 368), *(unsigned __int8 *)(v7 + 2), 0) )
  {
LABEL_81:
    v8 = -1073741504;
    v2 = a2;
    goto LABEL_116;
  }
  if ( *(_WORD *)v7 != 0xAFD2 || *(_BYTE *)(v7 + 2) != 4 )
  {
    _InterlockedExchange((volatile __int32 *)(v7 + 368), 0);
    goto LABEL_81;
  }
  v34 = *((_DWORD *)&Irp->Tail.CompletionKey + 2);
  if ( (v34 & 2) != 0 )
  {
    *((_DWORD *)&Irp->Tail.CompletionKey + 2) = v34 | 1;
    *(_BYTE *)(v7 + 2) = 7;
  }
  v35 = *(_QWORD *)(v7 + 192);
  *(_QWORD *)(v5 + 16) = v35;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v35 + 48)) <= 1 )
    __fastfail(0xEu);
LABEL_96:
  if ( (*(_DWORD *)(v7 + 8) & 0x100) != 0 )
  {
    *(_QWORD *)v5 = Irp;
  }
  else
  {
    *(_QWORD *)v5 = *(_QWORD *)(v35 + 16);
    *(_QWORD *)(v5 + 8) = *(_QWORD *)(v35 + 24);
  }
  if ( !v39
    && ((*(_DWORD *)(v7 + 8) & 0x100) != 0 || (*(_DWORD *)(v7 + 8) & 0x200) != 0)
    && (int)AfdCheckISBEvents(v35, (unsigned int)AfdTLSockOptEnable) >= 0 )
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
    || !(unsigned __int8)AfdEnqueueTPacketsIrp(v7, Irp) )
  {
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)AfdCancelTPackets);
    if ( (*(_DWORD *)(v7 + 8) & 0x800) != 0 || Irp->Cancel )
    {
      AfdAbortTPackets((__int64)Irp, -1073741536);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Irp->Tail.CompletionKey + 3, 0xFFFFFFFF) == 1 )
        AfdCompleteTPackets(Irp);
    }
    else if ( !AfdMaxActiveTransmitFileCount || !(unsigned __int8)AfdQueueTransmit(Irp) )
    {
      AfdTPacketsWorker(Irp);
    }
  }
  return 259;
}

```

## disassembly

```asm
0x140057100  mov     [rsp+arg_10], rbx
0x140057105  mov     [rsp+arg_18], rsi
0x14005710a  push    rdi
0x14005710b  push    r12
0x14005710d  push    r13
0x14005710f  push    r14
0x140057111  push    r15
0x140057113  sub     rsp, 120h
0x14005711a  mov     rax, cs:__security_cookie
0x140057121  xor     rax, rsp
0x140057124  mov     [rsp+148h+var_38], rax
0x14005712c  mov     r12, rdx
0x14005712f  mov     [rsp+148h+var_108], rdx
0x140057134  mov     rsi, rcx
0x140057137  mov     [rsp+148h+var_60], rcx
0x14005713f  mov     [rsp+148h+var_58], rdx
0x140057147  mov     edi, 40h ; '@'
0x14005714c  mov     r8d, edi; Size
0x14005714f  xor     edx, edx; Val
0x140057151  lea     rcx, [rsp+148h+var_F8]; void *
0x140057156  call    memset
0x14005715b  xor     ebx, ebx
0x14005715d  mov     r15d, ebx
0x140057160  mov     [rsp+148h+var_A8], rbx
0x140057168  mov     r13b, bl
0x14005716b  mov     [rsp+148h+var_118], bl
0x14005716f  mov     rax, [r12+30h]
0x140057174  mov     r14, [rax+18h]
0x140057178  mov     [rsp+148h+var_68], r14
0x140057180  test    byte ptr [r14+7], 10h
0x140057185  jz      short loc_140057191
0x140057187  mov     edi, 0C0000008h
0x14005718c  jmp     loc_140057979
0x140057191  mov     eax, 1AFDh
0x140057196  cmp     [r14], ax
0x14005719a  jnz     short loc_1400571A6
0x14005719c  mov     edi, 0C00000FAh
0x1400571a1  jmp     loc_140057979
0x1400571a6  mov     rcx, rsi; Irp
0x1400571a9  call    cs:__imp_IoIs32bitProcess
0x1400571b0  nop     dword ptr [rax+rax+00h]
0x1400571b5  mov     ecx, [r12+10h]
0x1400571ba  test    al, al
0x1400571bc  jz      short loc_1400571CD
0x1400571be  cmp     ecx, 30h ; '0'
0x1400571c1  jnb     short loc_1400571D1
0x1400571c3  mov     edi, 0C000000Dh
0x1400571c8  jmp     loc_140057979
0x1400571cd  cmp     ecx, edi
0x1400571cf  jmp     short loc_1400571C1
0x1400571d1  mov     [rsp+148h+var_110], bl
0x1400571d5  mov     [rsp+148h+var_114], ebx
0x1400571d9  mov     rcx, rsi; Irp
0x1400571dc  call    cs:__imp_IoIs32bitProcess
0x1400571e3  nop     dword ptr [rax+rax+00h]
0x1400571e8  mov     cl, [rsi+40h]
0x1400571eb  test    al, al
0x1400571ed  jz      loc_1400572BF
0x1400571f3  xorps   xmm0, xmm0
0x1400571f6  movups  [rsp+148h+var_A0], xmm0
0x1400571fe  movups  [rsp+148h+var_90], xmm0
0x140057206  movups  [rsp+148h+var_80], xmm0
0x14005720e  test    cl, cl
0x140057210  jz      short loc_140057226
0x140057212  test    byte ptr [r12+20h], 3
0x140057218  jz      short loc_140057226
0x14005721a  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140057221  nop     dword ptr [rax+rax+00h]
0x140057226  mov     rdx, [r12+20h]; Src
0x14005722b  mov     r8d, 30h ; '0'; Size
0x140057231  test    cl, cl
0x140057233  lea     rcx, [rsp+148h+var_A0]; void *
0x14005723b  jz      short loc_140057244
0x14005723d  call    RtlCopyFromUser
0x140057242  jmp     short loc_140057249
0x140057244  call    RtlCopyVolatileMemory
0x140057249  mov     rcx, qword ptr [rsp+148h+var_A0]
0x140057251  mov     qword ptr [rsp+148h+var_F8], rcx
0x140057256  mov     rax, qword ptr [rsp+148h+var_A0+8]
0x14005725e  mov     qword ptr [rsp+148h+var_F8+8], rax
0x140057263  mov     eax, dword ptr [rsp+148h+var_90]
0x14005726a  mov     [rsp+148h+var_E8], eax
0x14005726e  movsxd  r8, dword ptr [rsp+148h+var_90+4]
0x140057276  mov     [rsp+148h+Handle], r8
0x14005727b  mov     eax, dword ptr [rsp+148h+var_90+8]
0x140057282  mov     [rsp+148h+VirtualAddress], rax
0x140057287  mov     eax, dword ptr [rsp+148h+var_90+0Ch]
0x14005728e  mov     [rsp+148h+Length], eax
0x140057292  mov     eax, dword ptr [rsp+148h+var_80]
0x140057299  mov     [rsp+148h+var_C8], rax
0x1400572a1  mov     eax, dword ptr [rsp+148h+var_80+4]
0x1400572a8  mov     dword ptr [rsp+148h+var_C0], eax
0x1400572af  mov     edx, dword ptr [rsp+148h+var_80+8]
0x1400572b6  mov     dword ptr [rsp+148h+var_C0+4], edx
0x1400572bd  jmp     short loc_140057305
0x1400572bf  test    cl, cl
0x1400572c1  jz      short loc_1400572D7
0x1400572c3  test    byte ptr [r12+20h], 3
0x1400572c9  jz      short loc_1400572D7
0x1400572cb  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400572d2  nop     dword ptr [rax+rax+00h]
0x1400572d7  mov     rdx, [r12+20h]; Src
0x1400572dc  mov     r8, rdi; Size
0x1400572df  test    cl, cl
0x1400572e1  lea     rcx, [rsp+148h+var_F8]; void *
0x1400572e6  jz      short loc_1400572EF
0x1400572e8  call    RtlCopyFromUser
0x1400572ed  jmp     short loc_1400572F4
0x1400572ef  call    RtlCopyVolatileMemory
0x1400572f4  mov     edx, dword ptr [rsp+148h+var_C0+4]
0x1400572fb  mov     r8, [rsp+148h+Handle]
0x140057300  mov     rcx, qword ptr [rsp+148h+var_F8]
0x140057305  test    edx, 0FFFFFFC8h
0x14005730b  jnz     loc_14005793F
0x140057311  mov     eax, edx
0x140057313  and     eax, 30h
0x140057316  cmp     eax, 30h ; '0'
0x140057319  jz      loc_14005793F
0x14005731f  test    r8, r8
0x140057322  jz      short loc_14005732D
0x140057324  test    rcx, rcx
0x140057327  js      loc_14005793F
0x14005732d  test    eax, eax
0x14005732f  jnz     short loc_14005733E
0x140057331  or      edx, cs:AfdDefaultTransmitWorker
0x140057337  mov     dword ptr [rsp+148h+var_C0+4], edx
0x14005733e  mov     eax, [r14+8]
0x140057342  mov     ecx, 3
0x140057347  bt      eax, 8
0x14005734b  jnb     short loc_140057354
0x14005734d  call    AfdTliGetTpInfo
0x140057352  jmp     short loc_140057359
0x140057354  call    AfdTdiGetTpInfo
0x140057359  mov     r15, rax
0x14005735c  mov     [rsp+148h+var_A8], rax
0x140057364  test    rax, rax
0x140057367  jnz     short loc_14005737A
0x140057369  mov     [rsp+148h+var_114], 0C000009Ah
0x140057371  mov     edi, [rsp+148h+var_114]
0x140057375  jmp     loc_140057979
0x14005737a  mov     [r15+4Ch], ebx
0x14005737e  mov     eax, [rsp+148h+var_E8]
0x140057382  mov     [r15+5Ch], eax
0x140057386  cmp     [rsp+148h+var_E8], ebx
0x14005738a  jnz     short loc_140057398
0x14005738c  mov     eax, cs:AfdTransmitIoLength
0x140057392  mov     [r15+5Ch], eax
0x140057396  jmp     short loc_1400573A5
0x140057398  mov     dil, 1
0x14005739b  mov     [rsp+148h+var_110], dil
0x1400573a0  mov     [rsp+148h+var_100], dil
0x1400573a5  cmp     [rsp+148h+Length], ebx
0x1400573a9  jbe     loc_140057430
0x1400573af  mov     rdi, [r15+40h]
0x1400573b3  mov     dword ptr [r15+4Ch], 1
0x1400573bb  mov     rax, [rsp+148h+VirtualAddress]
0x1400573c0  mov     [rdi+8], rax
0x1400573c4  mov     eax, [rsp+148h+Length]
0x1400573c8  mov     [rdi+4], eax
0x1400573cb  mov     dword ptr [rdi], 1
0x1400573d1  test    byte ptr [rsp+148h+var_C0+4], 10h
0x1400573d9  jz      short loc_140057430
0x1400573db  mov     dword ptr [rdi], 80000001h
0x1400573e1  mov     [rsp+148h+Irp], rbx; Irp
0x1400573e6  mov     r9b, 1; ChargeQuota
0x1400573e9  xor     r8d, r8d; SecondaryBuffer
0x1400573ec  mov     edx, [rsp+148h+Length]; Length
0x1400573f0  mov     rcx, [rsp+148h+VirtualAddress]; VirtualAddress
0x1400573f5  call    cs:__imp_IoAllocateMdl
0x1400573fc  nop     dword ptr [rax+rax+00h]
0x140057401  mov     [rdi+10h], rax
0x140057405  test    rax, rax
0x140057408  jnz     short loc_14005741B
0x14005740a  mov     [rsp+148h+var_114], 0C000009Ah
0x140057412  mov     edi, [rsp+148h+var_114]
0x140057416  jmp     loc_140057979
0x14005741b  xor     r8d, r8d; Operation
0x14005741e  mov     dl, [rsi+40h]; AccessMode
0x140057421  mov     rcx, rax; MemoryDescriptorList
0x140057424  call    cs:__imp_MmProbeAndLockPages
0x14005742b  nop     dword ptr [rax+rax+00h]
0x140057430  cmp     [rsp+148h+Handle], rbx
0x140057435  jz      loc_140057670
0x14005743b  mov     eax, [r15+4Ch]
0x14005743f  lea     rdi, [rax+rax*2]
0x140057443  mov     r12, [r15+40h]
0x140057447  inc     eax
0x140057449  mov     [r15+4Ch], eax
0x14005744d  mov     dword ptr [r12+rdi*8], 2
0x140057455  mov     rax, qword ptr [rsp+148h+var_F8]
0x14005745a  mov     [r12+rdi*8+8], rax
0x14005745f  mov     r9b, [rsi+40h]; AccessMode
0x140057463  mov     rax, cs:__imp_IoFileObjectType
0x14005746a  mov     r8, [rax]; ObjectType
0x14005746d  mov     [rsp+148h+Object], rbx
0x140057475  mov     [rsp+148h+HandleInformation], rbx; HandleInformation
0x14005747a  lea     rax, [rsp+148h+Object]
0x140057482  mov     [rsp+148h+Irp], rax; Object
0x140057487  mov     edx, 1; DesiredAccess
0x14005748c  mov     rcx, [rsp+148h+Handle]; Handle
0x140057491  call    cs:__imp_ObReferenceObjectByHandle
0x140057498  nop     dword ptr [rax+rax+00h]
0x14005749d  mov     ecx, eax
0x14005749f  mov     rax, [rsp+148h+Object]
0x1400574a7  mov     [r12+rdi*8+10h], rax
0x1400574ac  mov     [rsp+148h+var_114], ecx
0x1400574b0  mov     eax, [rsp+148h+var_114]
0x1400574b4  test    eax, eax
0x1400574b6  jns     short loc_1400574EA
0x1400574b8  dec     dword ptr [r15+4Ch]
0x1400574bc  mov     r12, [rsp+148h+var_108]
0x1400574c1  cmp     dword ptr [r12+8], 1
0x1400574c7  jb      short loc_1400574E1
0x1400574c9  mov     rax, [rsi+70h]
0x1400574cd  cmp     [rsi+40h], bl
0x1400574d0  jz      short loc_1400574DE
0x1400574d2  mov     dl, 1
0x1400574d4  mov     rcx, rax
0x1400574d7  call    RtlWriteUCharToUser
0x1400574dc  jmp     short loc_1400574E1
0x1400574de  mov     byte ptr [rax], 1
0x1400574e1  mov     edi, [rsp+148h+var_114]
0x1400574e5  jmp     loc_140057979
0x1400574ea  cmp     [rsp+148h+var_E8], ebx
0x1400574ee  jnz     short loc_140057507
0x1400574f0  mov     rax, [r12+rdi*8+10h]
0x1400574f5  mov     ecx, [rax+50h]
0x1400574f8  test    cl, 40h
0x1400574fb  jnz     short loc_140057507
0x1400574fd  mov     eax, cs:AfdLargeBufferSize
0x140057503  mov     [r15+5Ch], eax
0x140057507  mov     rcx, [r12+rdi*8+10h]; FileObject
0x14005750c  mov     eax, [rcx+50h]
0x14005750f  test    al, 2
0x140057511  jz      short loc_140057523
0x140057513  cmp     [r12+rdi*8+8], rbx
0x140057518  jnz     short loc_140057523
0x14005751a  mov     rax, [rcx+68h]
0x14005751e  mov     [r12+rdi*8+8], rax
0x140057523  cmp     qword ptr [rsp+148h+var_F8+8], rbx
0x140057528  jnz     loc_1400575D7
0x14005752e  xorps   xmm0, xmm0
0x140057531  xor     eax, eax
0x140057533  movups  [rsp+148h+FileInformation], xmm0
0x14005753b  mov     [rsp+148h+var_40], rax
0x140057543  mov     [rsp+148h+ReturnedLength], ebx
0x14005754a  lea     rax, [rsp+148h+ReturnedLength]
0x140057552  mov     [rsp+148h+Irp], rax; ReturnedLength
0x140057557  lea     r9, [rsp+148h+FileInformation]; FileInformation
0x14005755f  mov     edx, 5; FileInformationClass
0x140057564  lea     r8d, [rdx+13h]; Length
0x140057568  call    cs:__imp_IoQueryFileInformation
0x14005756f  nop     dword ptr [rax+rax+00h]
0x140057574  mov     [rsp+148h+var_114], eax
0x140057578  mov     eax, [rsp+148h+var_114]
0x14005757c  test    eax, eax
0x14005757e  jns     short loc_140057596
0x140057580  mov     r13b, 1
0x140057583  mov     [rsp+148h+var_118], r13b
0x140057588  mov     edi, [rsp+148h+var_114]
0x14005758c  mov     r12, [rsp+148h+var_108]
0x140057591  jmp     loc_140057979
0x140057596  mov     rcx, [r12+rdi*8+8]
0x14005759b  test    rcx, rcx
0x14005759e  js      short loc_1400575B8
0x1400575a0  mov     rax, qword ptr [rsp+148h+FileInformation+8]
0x1400575a8  cmp     rcx, rax
0x1400575ab  jg      short loc_1400575B8
0x1400575ad  sub     rax, rcx
0x1400575b0  cmp     rax, 7FFFFFFFh
0x1400575b6  jle     short loc_1400575ED
0x1400575b8  mov     edi, 0C000000Dh
0x1400575bd  mov     [rsp+148h+var_114], edi
0x1400575c1  mov     r13b, 1
0x1400575c4  mov     [rsp+148h+var_118], r13b
0x1400575c9  mov     edi, [rsp+148h+var_114]
0x1400575cd  mov     r12, [rsp+148h+var_108]
0x1400575d2  jmp     loc_140057979
0x1400575d7  cmp     qword ptr [rsp+148h+var_F8+8], 7FFFFFFFh
0x1400575e0  jg      short loc_140057651
0x1400575e2  cmp     [r12+rdi*8+8], rbx
0x1400575e7  jl      short loc_140057651
0x1400575e9  mov     eax, dword ptr [rsp+148h+var_F8+8]
0x1400575ed  mov     [r12+rdi*8+4], eax
0x1400575f2  mov     [rsp+148h+var_70], rbx
0x1400575fa  mov     eax, cs:Feature_AfdtransmitFile_Overflow_Fix__private_featureState
0x140057600  mov     dword ptr [rsp+148h+var_70], eax
0x140057607  test    al, 10h
0x140057609  jz      short loc_140057610
0x14005760b  and     eax, 1
0x14005760e  jmp     short loc_140057615
0x140057610  call    Feature_AfdtransmitFile_Overflow_Fix__private_IsEnabledDeviceUsageNoInline
0x140057615  test    eax, eax
0x140057617  jz      short loc_140057670
0x140057619  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140057623  sub     rcx, [r12+rdi*8+8]
0x140057628  mov     eax, [r12+rdi*8+4]
0x14005762d  cmp     rcx, rax
0x140057630  jge     short loc_140057670
0x140057632  mov     edi, 0C000000Dh
  ... truncated ...
```
