# RefsMinstoreRead

- ea: `0x14000d820`
- end: `0x14000dfcf`
- name: `RefsMinstoreRead`
- size: `1967`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, struct REFS_IO_CONTEXT *@<rdx>, struct _IRP *@<r8>, unsigned __int64 LowLimit)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1400ba4d0`

## callees

- `0x14000d820`
- `0x14000e0e0`
- `0x14000f090`
- `0x14000f3f0`
- `0x14002b3e0`
- `0x140047580`
- `0x14005c048`
- `0x140076ad0`
- `0x1400862c0`
- `0x140089a80`
- `0x1400d0fd8`
- `0x1400e7edc`
- `0x1400e8a2c`
- `0x1400f1788`
- `0x14011a9ac`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000dd58`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000dd58`
- `ntoskrnl!IofCompleteRequest` at `0x14000dd1c`
- `ntoskrnl!IofCompleteRequest` at `0x14000dd1c`
- `ntoskrnl!IoGetStackLimits` at `0x14000d9d4`
- `ntoskrnl!IoGetStackLimits` at `0x14000d9d4`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000dc40`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401f8276`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000dc40`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401f8276`
- `ntoskrnl!DbgPrintEx` at `0x14000df6b`
- `ntoskrnl!DbgPrintEx` at `0x14000df6b`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14000dc5c`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x14000dc5c`
- `ntoskrnl!_strnicmp` at `0x1401f82a1`
- `ntoskrnl!_strnicmp` at `0x1401f82a1`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401f8285`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401f8285`
- `ntoskrnl!IofCallDriver` at `0x14000d9fa`
- `ntoskrnl!IofCallDriver` at `0x14000d9fa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000dcc1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000dcc1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000da29`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000da29`
- `ntoskrnl!KeInitializeEvent` at `0x14000d94c`
- `ntoskrnl!KeInitializeEvent` at `0x14000d94c`

## string_xrefs

- `0x14000d864`: `Read.c`
- `0x14000db3c`: `Read.c`
- `0x14000de1b`: `Read.c`
- `0x1401f82d1`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsMinstoreRead(
        struct _IRP_CONTEXT *a1,
        struct REFS_IO_CONTEXT *a2,
        struct _IRP *a3,
        int a4,
        char *LowLimit)
{
  int v8; // eax
  unsigned __int64 v9; // rsi
  struct _VCB **v10; // r15
  __int64 v11; // rcx
  __int64 v12; // r13
  __int64 v13; // r8
  int Status; // ebx
  unsigned int v15; // r8d
  ULONG_PTR v16; // r13
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  UCHAR MajorFunction; // al
  bool v20; // zf
  struct _IO_STACK_LOCATION *v21; // rax
  NTSTATUS v22; // eax
  unsigned int v23; // ecx
  __int64 v24; // rax
  volatile unsigned int v25; // edi
  __int64 v27; // rcx
  struct _KPROCESS *v28; // rdi
  ULONG Priority; // r8d
  struct CmsTransactionContext *v30; // r10
  PMDL MdlAddress; // rcx
  PVOID v32; // rax
  PVOID MappedSystemVa; // rbx
  __int64 v34; // rdx
  NTSTATUS v35; // eax
  int TransactionContext; // eax
  unsigned int v37; // eax
  int v38; // ecx
  int CompressedContainerRange; // eax
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  unsigned __int64 v42; // [rsp+30h] [rbp-A1h]
  char v43; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v44; // [rsp+54h] [rbp-7Dh] BYREF
  int *v45; // [rsp+58h] [rbp-79h]
  unsigned int v46; // [rsp+60h] [rbp-71h]
  PVOID Context; // [rsp+68h] [rbp-69h] BYREF
  struct CmsTransactionContext *v48; // [rsp+70h] [rbp-61h] BYREF
  struct _FCB *v49; // [rsp+78h] [rbp-59h]
  LARGE_INTEGER v50; // [rsp+80h] [rbp-51h] BYREF
  __int64 v51; // [rsp+88h] [rbp-49h] BYREF
  union SmsBigIdentifier *v52; // [rsp+90h] [rbp-41h] BYREF
  __int64 v53; // [rsp+98h] [rbp-39h]
  unsigned __int64 HighLimit; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-29h]
  struct _KEVENT Event; // [rsp+B0h] [rbp-21h] BYREF
  __int128 Parameter; // [rsp+C8h] [rbp-9h] BYREF
  __int128 v58; // [rsp+D8h] [rbp+7h]
  char v59; // [rsp+130h] [rbp+5Fh]

  v51 = 0;
  v8 = a4;
  v52 = 0;
  v50.QuadPart = 0;
  v44 = 0;
  memset(&Event, 0, sizeof(Event));
  v43 = 0;
  v48 = 0;
  if ( *((_QWORD *)a1 + 84) )
  {
    v9 = (unsigned __int64)LowLimit;
    v10 = (struct _VCB **)((char *)a1 + 64);
    v11 = *((_QWORD *)a1 + 8);
    v49 = 0;
    v46 = 0;
    v12 = *(_QWORD *)LowLimit;
    v59 = 0;
    v13 = *(_QWORD *)LowLimit;
    v55 = *(_QWORD *)LowLimit;
    v53 = v11;
    while ( 1 )
    {
      Status = MsConvertVboToLboPagingRead(
                 *((_QWORD *)a1 + 84),
                 v8,
                 v13,
                 *(_DWORD *)(v9 + 16),
                 (__int64)&v50,
                 (__int64)&v44,
                 (__int64)&v43,
                 (__int64)&v51,
                 (__int64)&v52,
                 (__int64)&v48);
      if ( Status < 0 )
        break;
      if ( !v59 )
      {
        if ( v51 )
        {
          v49 = (struct _FCB *)v51;
          if ( *(_WORD *)v51 != 2050 )
            v49 = *(struct _FCB **)(v51 + 136);
        }
        if ( (*(_DWORD *)(v53 + 28) & 2) != 0 )
          RefsInsertDebugInfoIrpImplementation(0, a3, 0, v49, v52, 0x6174654Du, v42);
        v59 = 1;
      }
      if ( *(_QWORD *)v9 != v12 )
      {
        Status = RefsAdvanceMdl(a1, a2, a3->MdlAddress, (unsigned int)*(_QWORD *)v9 - (unsigned int)v12);
        if ( Status < 0 )
          break;
      }
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      v16 = v44;
      p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a3->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
      MajorFunction = CurrentStackLocation->MajorFunction;
      CurrentStackLocation[-1].Flags |= 2u;
      v20 = v43 == 0;
      CurrentStackLocation[-1].MajorFunction = MajorFunction;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset = v50;
      CurrentStackLocation[-1].Parameters.Read.Length = v16;
      v21 = a3->Tail.Overlay.CurrentStackLocation;
      v21[-1].CompletionRoutine = RefsVerifyReadCompletionRoutine;
      v21[-1].Context = &Event;
      v21[-1].Control = -32;
      if ( v20 )
      {
        Context = RefsReserveStackStorage;
        Parameter = 0;
        v58 = 0;
        v16 = *(_QWORD *)(v53 + 192);
        HighLimit = 0;
        LowLimit = 0;
        IoGetStackLimits((PULONG_PTR)&LowLimit, &HighLimit);
        if ( (unsigned __int64)((char *)&HighLimit - LowLimit) <= 0x4800 )
        {
          *(_QWORD *)&Parameter = v16;
          *((_QWORD *)&Parameter + 1) = a3;
          v35 = KeExpandKernelStackAndCalloutEx(RefsStorageDriverCallout, &Parameter, 0x6000u, 0, Context);
          LODWORD(v16) = v44;
          if ( v35 >= 0 )
            Status = DWORD2(v58);
        }
        else
        {
          v22 = IofCallDriver((PDEVICE_OBJECT)v16, a3);
          LODWORD(v16) = v44;
          Status = v22;
        }
      }
      else
      {
        Priority = 1073741856;
        v30 = v48;
        MdlAddress = a3->MdlAddress;
        if ( (a3->Flags & 2) == 0 )
          Priority = 1073741840;
        v45 = (int *)v48;
        Context = v48;
        if ( MdlAddress )
        {
          if ( (MdlAddress->MdlFlags & 5) != 0 )
          {
            MappedSystemVa = MdlAddress->MappedSystemVa;
          }
          else
          {
            v32 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, Priority);
            v30 = (struct CmsTransactionContext *)v45;
            MappedSystemVa = v32;
          }
          p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a3->Tail.Overlay.CurrentStackLocation;
        }
        else
        {
          MappedSystemVa = a3->UserBuffer;
        }
        if ( MappedSystemVa )
        {
          if ( v48
            || (TransactionContext = MsCreateTransactionContext(
                                       (PSLIST_ENTRY *)&Context,
                                       *(_QWORD *)(MEMORY[0x90] + 112LL)),
                v30 = (struct CmsTransactionContext *)Context,
                v45 = (int *)Context,
                LODWORD(LowLimit) = TransactionContext,
                TransactionContext >= 0) )
          {
            CompressedContainerRange = MsReadCompressedContainerRange(v30);
            v30 = (struct CmsTransactionContext *)v45;
            LODWORD(LowLimit) = CompressedContainerRange;
          }
          p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a3->Tail.Overlay.CurrentStackLocation;
        }
        else
        {
          LODWORD(LowLimit) = -1073741670;
        }
        --p_CurrentStackLocation->CurrentStackLocation;
        --a3->CurrentLocation;
        v20 = v48 == 0;
        v34 = (unsigned int)LowLimit;
        a3->IoStatus.Status = (int)LowLimit;
        if ( v20 && v30 )
        {
          if ( (int)v34 < 0 )
            MsAbortTransaction(v30);
          else
            MsCommitTransaction(v30, v34, 0);
          MsDeleteTransactionContext(v45);
          LODWORD(v34) = (_DWORD)LowLimit;
          v45 = (int *)&a3->IoStatus.0;
        }
        else
        {
          v45 = (int *)&a3->IoStatus.0;
        }
        if ( (int)v34 >= 0 )
          a3->IoStatus.Information = v16;
        else
          v45 = (int *)&a3->IoStatus.0;
        IofCompleteRequest(a3, 1);
        Status = *v45;
      }
      if ( Status == 259 )
      {
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        Status = a3->IoStatus.Status;
      }
      if ( *(_QWORD *)v9 == v55 )
      {
        if ( Status < 0 )
          break;
      }
      else
      {
        Status = RefsRestoreMdl(a1, a2, a3->MdlAddress, *(_QWORD *)v9 - v55);
        if ( Status < 0 )
          break;
      }
      v23 = v16 + v46;
      *(_QWORD *)v9 += (unsigned int)v16;
      v20 = *(_DWORD *)(v9 + 16) == (_DWORD)v16;
      *(_DWORD *)(v9 + 16) -= v16;
      v13 = *(_QWORD *)v9;
      v46 = v23;
      if ( v20 )
      {
        a3->IoStatus.Information = v23;
        goto LABEL_22;
      }
      v12 = v55;
      v8 = a4;
    }
    if ( Status == -1073741608 || Status == -1073741400 || Status == -1073741432 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
          (unsigned int)Status);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(Status, a1, "Read.c", 0x263u);
      RefsRaiseStatusInternal(a1, Status, v15);
      JUMPOUT(0x1401F82ECLL);
    }
  }
  else
  {
    Status = -1073741808;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221225488LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741808, 0, "Read.c", 0x1D0u);
    v10 = (struct _VCB **)((char *)a1 + 64);
  }
LABEL_22:
  v24 = *((_QWORD *)a1 + 1);
  if ( (v24 & 0x100000000LL) != 0 )
  {
    *((_QWORD *)a1 + 1) = v24 | 0x200000000LL;
  }
  else
  {
    if ( Status >= 0 && *((_BYTE *)*v10 + 10304) && *((__int64 *)a1 + 86) > 23 )
    {
      RefsIoPerfCollectReadWriteData(*v10, a3, a1, a2);
      *((_QWORD *)a1 + 1) |= 0x8000uLL;
    }
    else
    {
      *((_QWORD *)a1 + 1) |= 0x8000uLL;
      if ( Status < 0 )
      {
        v37 = *((unsigned __int8 *)a1 + 40);
        if ( (unsigned __int8)v37 <= 0x12u )
        {
          v38 = 262685;
          if ( _bittest(&v38, v37) )
          {
            if ( *v10
              && *((_BYTE *)*v10 + 10304)
              && (*((_DWORD *)a1 + 1) & 0x400) == 0
              && (*((_DWORD *)a1 + 2) & 0x10000) == 0 )
            {
              *((_QWORD *)a1 + 86) = 7;
            }
          }
        }
      }
    }
    *((_DWORD *)a2 + 199) &= ~1u;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, a3, Status);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    if ( Status < 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
LABEL_111:
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids,
          (unsigned int)Status);
    }
    else if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      goto LABEL_111;
    }
  }
  if ( (_BYTE)RefsStatusDebugEnabled && Status != 259 && Status != -1073741802 )
  {
    if ( RefsStatusDisplayStatus && RefsStatusDisplayStatus == Status )
      DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), Status, "Read.c", 615);
    v25 = RefsStatusBreakOnWin32Error;
    if ( RefsStatusBreakOnStatus && RefsStatusBreakOnStatus == Status
      || RefsStatusBreakOnWin32Error && v25 == RtlNtStatusToDosErrorNoTeb(Status) )
    {
      v28 = RefsStatusBreakForProcess;
      if ( !RefsStatusBreakForThread
        || RefsStatusBreakForThread == KeGetCurrentThread()
        && (!RefsStatusBreakForProcess || v28 == IoGetCurrentProcess())
        && (!RefsStatusBreakForImage
         || (CurrentProcess = IoGetCurrentProcess(),
             ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
             !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
      {
        __int2c();
      }
    }
    if ( Status && Status != -2147483643 )
    {
      v27 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v27) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v27 + 8) = Status;
      *(_QWORD *)((char *)&RefsStatusQueue + v27 + 16) = "Read.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v27 + 24) = 615;
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000d820  mov     [rsp-8+arg_8], rbx
0x14000d825  mov     [rsp-8+arg_18], r9
0x14000d82a  push    rbp
0x14000d82b  push    rsi
0x14000d82c  push    rdi
0x14000d82d  push    r12
0x14000d82f  push    r13
0x14000d831  push    r14
0x14000d833  push    r15
0x14000d835  lea     rbp, [rsp-1Fh]
0x14000d83a  sub     rsp, 0F0h
0x14000d841  mov     rdi, rcx
0x14000d844  lea     r13, WPP_GLOBAL_Control
0x14000d84b  xor     ecx, ecx
0x14000d84d  mov     r14, r8
0x14000d850  xor     r8d, r8d
0x14000d853  mov     [rbp+4Fh+Event.Header.WaitListHead.Blink], rcx
0x14000d857  xorps   xmm0, xmm0
0x14000d85a  mov     [rbp+4Fh+var_98], r8
0x14000d85e  mov     r12, rdx
0x14000d861  mov     rax, r9
0x14000d864  lea     rdx, aReadC; "Read.c"
0x14000d86b  mov     [rbp+4Fh+var_90], r8
0x14000d86f  mov     esi, 1
0x14000d874  mov     [rbp+4Fh+var_A0], r8
0x14000d878  mov     dword ptr [rbp+4Fh+var_D0+4], r8d
0x14000d87c  movups  xmmword ptr [rbp+4Fh+Event.Header], xmm0
0x14000d880  mov     byte ptr [rsp+120h+var_D0], cl
0x14000d884  mov     [rbp+4Fh+var_B0], r8
0x14000d888  cmp     [rdi+2A0h], rcx
0x14000d88f  jz      loc_14000DDD7
0x14000d895  mov     rsi, [rbp+4Fh+LowLimit]
0x14000d899  lea     r15, [rdi+40h]
0x14000d89d  mov     rcx, [r15]
0x14000d8a0  mov     [rbp+4Fh+var_A8], r8
0x14000d8a4  mov     [rbp+4Fh+var_C0], r8d
0x14000d8a8  mov     r13, [rsi]
0x14000d8ab  mov     [rbp+4Fh+arg_0], r8b
0x14000d8af  mov     r8, r13
0x14000d8b2  mov     [rbp+4Fh+var_78], r13
0x14000d8b6  mov     [rbp+4Fh+var_88], rcx
0x14000d8ba  mov     r9d, [rsi+10h]
0x14000d8be  lea     rcx, [rbp+4Fh+var_B0]
0x14000d8c2  mov     [rsp+120h+var_D8], rcx
0x14000d8c7  mov     rdx, rax
0x14000d8ca  lea     rcx, [rbp+4Fh+var_90]
0x14000d8ce  mov     [rsp+120h+var_E0], rcx
0x14000d8d3  lea     rcx, [rbp+4Fh+var_98]
0x14000d8d7  mov     [rsp+120h+var_E8], rcx
0x14000d8dc  lea     rcx, [rsp+120h+var_D0]
0x14000d8e1  mov     [rsp+120h+var_F0], rcx; unsigned __int64
0x14000d8e6  lea     rcx, [rbp+4Fh+var_D0+4]
0x14000d8ea  mov     qword ptr [rsp+120h+Priority], rcx
0x14000d8ef  lea     rcx, [rbp+4Fh+var_A0]
0x14000d8f3  mov     [rsp+120h+Timeout], rcx
0x14000d8f8  mov     rcx, [rdi+2A0h]
0x14000d8ff  call    MsConvertVboToLboPagingRead
0x14000d904  mov     ebx, eax
0x14000d906  test    eax, eax
0x14000d908  js      loc_14000DA71
0x14000d90e  cmp     [rbp+4Fh+arg_0], 0
0x14000d912  jnz     short loc_14000D934
0x14000d914  mov     rax, [rbp+4Fh+var_98]
0x14000d918  test    rax, rax
0x14000d91b  jnz     loc_14000DD97
0x14000d921  mov     rax, [rbp+4Fh+var_88]
0x14000d925  mov     eax, [rax+1Ch]
0x14000d928  test    al, 2
0x14000d92a  jnz     loc_14000DE27
0x14000d930  mov     [rbp+4Fh+arg_0], 1
0x14000d934  mov     r9, [rsi]
0x14000d937  cmp     r9, r13
0x14000d93a  jnz     loc_14000DE4F
0x14000d940  xor     r8d, r8d; State
0x14000d943  lea     rcx, [rbp+4Fh+Event]; Event
0x14000d947  mov     edx, 1; Type
0x14000d94c  call    cs:__imp_KeInitializeEvent
0x14000d953  nop     dword ptr [rax+rax+00h]
0x14000d958  mov     r13d, dword ptr [rbp+4Fh+var_D0+4]
0x14000d95c  lea     rdx, [r14+0B8h]
0x14000d963  mov     rcx, [rdx]
0x14000d966  movzx   eax, byte ptr [rcx]
0x14000d969  or      byte ptr [rcx-46h], 2
0x14000d96d  cmp     byte ptr [rsp+120h+var_D0], 0
0x14000d972  mov     [rcx-48h], al
0x14000d975  mov     rax, [rbp+4Fh+var_A0]
0x14000d979  mov     [rcx-30h], rax
0x14000d97d  mov     [rcx-40h], r13d
0x14000d981  lea     rcx, ?RefsVerifyReadCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; RefsVerifyReadCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14000d988  mov     rax, [rdx]
0x14000d98b  mov     [rax-10h], rcx
0x14000d98f  lea     rcx, [rbp+4Fh+Event]
0x14000d993  mov     [rax-8], rcx
0x14000d997  mov     byte ptr [rax-45h], 0E0h
0x14000d99b  jnz     loc_14000DC71
0x14000d9a1  mov     rax, cs:?RefsReserveStackStorage@@3PEAXEA; void * RefsReserveStackStorage
0x14000d9a8  lea     rdx, [rbp+4Fh+HighLimit]; HighLimit
0x14000d9ac  mov     [rbp+4Fh+Context], rax
0x14000d9b0  lea     rcx, [rbp+4Fh+LowLimit]; LowLimit
0x14000d9b4  mov     rax, [rbp+4Fh+var_88]
0x14000d9b8  xorps   xmm0, xmm0
0x14000d9bb  movups  [rbp+4Fh+Parameter], xmm0
0x14000d9bf  movups  [rbp+4Fh+var_48], xmm0
0x14000d9c3  mov     r13, [rax+0C0h]
0x14000d9ca  xor     eax, eax
0x14000d9cc  mov     [rbp+4Fh+HighLimit], rax
0x14000d9d0  mov     [rbp+4Fh+LowLimit], rax
0x14000d9d4  call    cs:__imp_IoGetStackLimits
0x14000d9db  nop     dword ptr [rax+rax+00h]
0x14000d9e0  lea     rax, [rbp+4Fh+HighLimit]
0x14000d9e4  sub     rax, [rbp+4Fh+LowLimit]
0x14000d9e8  cmp     rax, 4800h
0x14000d9ee  jbe     loc_14000DD33
0x14000d9f4  mov     rdx, r14; Irp
0x14000d9f7  mov     rcx, r13; DeviceObject
0x14000d9fa  call    cs:__imp_IofCallDriver
0x14000da01  nop     dword ptr [rax+rax+00h]
0x14000da06  mov     r13d, dword ptr [rbp+4Fh+var_D0+4]
0x14000da0a  mov     ebx, eax
0x14000da0c  cmp     ebx, 103h
0x14000da12  jnz     short loc_14000DA39
0x14000da14  xor     r9d, r9d; Alertable
0x14000da17  mov     [rsp+120h+Timeout], 0; Timeout
0x14000da20  xor     r8d, r8d; WaitMode
0x14000da23  lea     rcx, [rbp+4Fh+Event]; Object
0x14000da27  xor     edx, edx; WaitReason
0x14000da29  call    cs:__imp_KeWaitForSingleObject
0x14000da30  nop     dword ptr [rax+rax+00h]
0x14000da35  mov     ebx, [r14+30h]
0x14000da39  mov     r9, [rsi]
0x14000da3c  mov     rax, [rbp+4Fh+var_78]
0x14000da40  cmp     r9, rax
0x14000da43  jnz     loc_14000DED3
0x14000da49  test    ebx, ebx
0x14000da4b  js      short loc_14000DA71
0x14000da4d  mov     ecx, [rbp+4Fh+var_C0]
0x14000da50  add     ecx, r13d
0x14000da53  mov     eax, r13d
0x14000da56  add     [rsi], rax
0x14000da59  sub     [rsi+10h], r13d
0x14000da5d  mov     r8, [rsi]
0x14000da60  mov     [rbp+4Fh+var_C0], ecx
0x14000da63  jnz     loc_14000DD78
0x14000da69  mov     eax, ecx
0x14000da6b  mov     [r14+38h], rax
0x14000da6f  jmp     short loc_14000DA96
0x14000da71  cmp     ebx, 0C00000D8h
0x14000da77  jz      loc_14000DF83
0x14000da7d  mov     eax, ebx
0x14000da7f  cmp     ebx, 0C00001A8h
0x14000da85  jz      loc_14000DF83
0x14000da8b  cmp     eax, 0C0000188h
0x14000da90  jz      loc_14000DF83
0x14000da96  lea     r13, WPP_GLOBAL_Control
0x14000da9d  mov     esi, 1
0x14000daa2  mov     rax, [rdi+8]
0x14000daa6  bt      rax, 20h ; ' '
0x14000daab  jb      loc_14000DBF0
0x14000dab1  test    ebx, ebx
0x14000dab3  js      short loc_14000DAE8
0x14000dab5  mov     rax, [r15]
0x14000dab8  movzx   edx, byte ptr [rax+2840h]
0x14000dabf  test    dl, dl
0x14000dac1  jz      short loc_14000DAE8
0x14000dac3  cmp     qword ptr [rdi+2B0h], 17h
0x14000dacb  jle     short loc_14000DAE8
0x14000dacd  mov     rcx, [r15]; struct _VCB *
0x14000dad0  mov     r9, r12; struct REFS_IO_CONTEXT *
0x14000dad3  mov     r8, rdi; struct _IRP_CONTEXT *
0x14000dad6  mov     rdx, r14; struct _IRP *
0x14000dad9  call    ?RefsIoPerfCollectReadWriteData@@YAXPEAU_VCB@@PEAU_IRP@@PEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@@Z; RefsIoPerfCollectReadWriteData(_VCB *,_IRP *,_IRP_CONTEXT *,REFS_IO_CONTEXT *)
0x14000dade  or      qword ptr [rdi+8], 8000h
0x14000dae6  jmp     short loc_14000DAF8
0x14000dae8  or      qword ptr [rdi+8], 8000h
0x14000daf0  test    ebx, ebx
0x14000daf2  js      loc_14000DEF4
0x14000daf8  and     dword ptr [r12+31Ch], 0FFFFFFFEh
0x14000db01  mov     r8d, ebx; Status
0x14000db04  mov     rdx, r14; Irp
0x14000db07  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14000db0a  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14000db0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db16  cmp     rcx, r13
0x14000db19  jnz     short loc_14000DB89
0x14000db1b  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14000db22  test    al, al
0x14000db24  jz      short loc_14000DB6B
0x14000db26  cmp     ebx, 103h
0x14000db2c  jz      short loc_14000DB6B
0x14000db2e  cmp     ebx, 0C0000016h
0x14000db34  jz      short loc_14000DB6B
0x14000db36  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x14000db3c  lea     r14, aReadC; "Read.c"
0x14000db43  test    eax, eax
0x14000db45  jnz     loc_14000DF3B
0x14000db4b  mov     eax, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x14000db51  mov     edi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x14000db57  test    eax, eax
0x14000db59  jnz     loc_14000DC06
0x14000db5f  test    edi, edi
0x14000db61  jnz     loc_14000DC5A
0x14000db67  test    ebx, ebx
0x14000db69  jnz     short loc_14000DBA9
0x14000db6b  mov     eax, ebx
0x14000db6d  mov     rbx, [rsp+120h+arg_8]
0x14000db75  add     rsp, 0F0h
0x14000db7c  pop     r15
0x14000db7e  pop     r14
0x14000db80  pop     r13
0x14000db82  pop     r12
0x14000db84  pop     rdi
0x14000db85  pop     rsi
0x14000db86  pop     rbp
0x14000db87  retn
0x14000db89  test    dword ptr [rcx+2Ch], 100h
0x14000db90  jz      short loc_14000DB1B
0x14000db92  test    ebx, ebx
0x14000db94  js      loc_1401F8245
0x14000db9a  cmp     byte ptr [rcx+29h], 5
0x14000db9e  jb      loc_14000DB1B
0x14000dba4  jmp     loc_1401F824F
0x14000dba9  cmp     ebx, 80000005h
0x14000dbaf  jz      short loc_14000DB6B
0x14000dbb1  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, esi; ulong RefsStatusNextQueueEntry
0x14000dbb9  mov     rax, gs:188h
0x14000dbc2  lea     rdx, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x14000dbc9  lea     ecx, [rsi+1]
0x14000dbcc  and     ecx, 0FFFh
0x14000dbd2  shl     rcx, 5
0x14000dbd6  mov     [rcx+rdx], rax
0x14000dbda  mov     [rcx+rdx+8], ebx
0x14000dbde  mov     [rcx+rdx+10h], r14
0x14000dbe3  mov     dword ptr [rcx+rdx+18h], 267h
0x14000dbeb  jmp     loc_14000DB6B
0x14000dbf0  mov     rcx, 200000000h
0x14000dbfa  or      rax, rcx
0x14000dbfd  mov     [rdi+8], rax
0x14000dc01  jmp     loc_14000DB0F
0x14000dc06  cmp     eax, ebx
0x14000dc08  jnz     loc_14000DB5F
0x14000dc0e  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x14000dc15  mov     rdi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x14000dc1c  test    rcx, rcx
0x14000dc1f  jz      loc_14000DF7C
0x14000dc25  mov     rax, gs:188h
0x14000dc2e  cmp     rcx, rax
0x14000dc31  jnz     loc_14000DB67
0x14000dc37  test    rdi, rdi
0x14000dc3a  jz      loc_1401F826D
0x14000dc40  call    cs:__imp_IoGetCurrentProcess
0x14000dc47  nop     dword ptr [rax+rax+00h]
0x14000dc4c  cmp     rdi, rax
0x14000dc4f  jnz     loc_14000DB67
0x14000dc55  jmp     loc_1401F826D
0x14000dc5a  mov     ecx, ebx; Status
0x14000dc5c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14000dc63  nop     dword ptr [rax+rax+00h]
0x14000dc68  cmp     edi, eax
0x14000dc6a  jz      short loc_14000DC0E
0x14000dc6c  jmp     loc_14000DB67
0x14000dc71  mov     eax, [r14+10h]
0x14000dc75  mov     r8d, 40000020h
0x14000dc7b  mov     r10, [rbp+4Fh+var_B0]
0x14000dc7f  test    al, 2
0x14000dc81  mov     rcx, [r14+8]; MemoryDescriptorList
0x14000dc85  mov     eax, 40000010h
0x14000dc8a  cmovz   r8d, eax
0x14000dc8e  mov     [rbp+4Fh+var_C8], r10
0x14000dc92  mov     [rbp+4Fh+Context], r10
0x14000dc96  test    rcx, rcx
0x14000dc99  jz      loc_14000DD85
0x14000dc9f  test    byte ptr [rcx+0Ah], 5
0x14000dca3  jnz     loc_14000DD8E
0x14000dca9  mov     [rsp+120h+Priority], r8d; Priority
0x14000dcae  xor     r9d, r9d; RequestedAddress
0x14000dcb1  mov     r8d, 1; CacheType
0x14000dcb7  mov     dword ptr [rsp+120h+Timeout], 0; BugCheckOnFailure
0x14000dcbf  xor     edx, edx; AccessMode
0x14000dcc1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000dcc8  nop     dword ptr [rax+rax+00h]
0x14000dccd  mov     r10, [rbp+4Fh+var_C8]
0x14000dcd1  mov     rbx, rax
0x14000dcd4  lea     rdx, [r14+0B8h]
0x14000dcdb  test    rbx, rbx
0x14000dcde  jnz     loc_14000DE70
0x14000dce4  mov     dword ptr [rbp+4Fh+LowLimit], 0C000009Ah
0x14000dceb  add     qword ptr [rdx], 0FFFFFFFFFFFFFFB8h
0x14000dcef  lea     rbx, [r14+30h]
0x14000dcf3  dec     byte ptr [r14+43h]
0x14000dcf7  cmp     [rbp+4Fh+var_B0], 0
0x14000dcfc  mov     edx, dword ptr [rbp+4Fh+LowLimit]
0x14000dcff  mov     [rbx], edx
0x14000dd01  jz      loc_14000DEA8
0x14000dd07  mov     [rbp+4Fh+var_C8], rbx
0x14000dd0b  test    edx, edx
0x14000dd0d  jns     loc_14000DECA
0x14000dd13  mov     [rbp+4Fh+var_C8], rbx
0x14000dd17  mov     dl, 1; PriorityBoost
0x14000dd19  mov     rcx, r14; Irp
0x14000dd1c  call    cs:__imp_IofCompleteRequest
  ... truncated ...
```
