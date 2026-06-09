# AfdTLFastDgramSend

- ea: `0x14000de50`
- end: `0x14000ea3f`
- name: `AfdTLFastDgramSend`
- size: `3055`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14000c0d0`
- `0x1400563d8`

## callees

- `0x14000de50`
- `0x14000f390`
- `0x14000f450`
- `0x14000f744`
- `0x14000f980`
- `0x14000f9c0`
- `0x14000fa00`
- `0x140010948`
- `0x140013990`
- `0x14001b800`
- `0x140031840`
- `0x140050be4`
- `0x14005d8e4`
- `0x1400726a0`
- `0x140072780`
- `0x1400930cc`
- `0x140093658`

## import_xrefs

- `ntoskrnl!PsReturnPoolQuota` at `0x14000e4c0`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000e62f`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000e64a`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000e8b3`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000e4c0`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000e62f`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000e64a`
- `ntoskrnl!PsReturnPoolQuota` at `0x14000e8b3`
- `ntoskrnl!MmSizeOfMdl` at `0x14000e44c`
- `ntoskrnl!MmSizeOfMdl` at `0x14000e44c`
- `ntoskrnl!KeSetEvent` at `0x14000e5f2`
- `ntoskrnl!KeSetEvent` at `0x14000e5f2`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140075aa1`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140075aa1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140075adb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140075adb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e138`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e42e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e570`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e138`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e42e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e570`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000e09d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075ac8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000e09d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075ac8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000e011`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000e011`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e353`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e353`
- `ntoskrnl!EtwWrite` at `0x14000e826`
- `ntoskrnl!EtwWrite` at `0x14000e826`
- `TDI!TdiReturnChainedReceives` at `0x14000e688`
- `TDI!TdiReturnChainedReceives` at `0x14000e688`

## pseudocode

```c
__int64 __fastcall AfdTLFastDgramSend(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v2; // r10
  bool v3; // cc
  __int64 v5; // rax
  unsigned __int64 v6; // rsi
  __int64 v7; // rcx
  int v8; // ecx
  signed __int32 v9; // eax
  int v10; // r14d
  unsigned int v11; // r12d
  __int64 v12; // rcx
  __int64 *v13; // r8
  int v14; // r9d
  int v15; // edi
  int v16; // edx
  int v17; // eax
  signed __int64 v18; // rax
  signed __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  SIZE_T v27; // rdi
  struct _KPROCESS *v28; // rcx
  int v29; // r15d
  _BYTE *v30; // r15
  ULONG_PTR v31; // r8
  unsigned __int64 v32; // rdi
  bool v34; // zf
  __int64 v35; // rbx
  unsigned int v36; // r12d
  bool v37; // zf
  unsigned __int16 v38; // dx
  int v39; // ecx
  __int16 v40; // ax
  _QWORD *v41; // rcx
  _QWORD *v42; // rdi
  char *v43; // rdi
  __int16 v44; // r13
  unsigned int v45; // edx
  char *v46; // r15
  int v47; // edi
  __int64 v48; // r9
  __int64 v49; // [rsp+28h] [rbp-D8h]
  PEPROCESS Process; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+68h] [rbp-98h] BYREF
  int v52; // [rsp+70h] [rbp-90h] BYREF
  int v53; // [rsp+78h] [rbp-88h] BYREF
  int v54; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v55; // [rsp+88h] [rbp-78h]
  __int64 v56; // [rsp+90h] [rbp-70h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+98h] [rbp-68h] BYREF
  signed __int64 v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 *v60; // [rsp+C0h] [rbp-40h]
  _OWORD v61[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v62; // [rsp+F0h] [rbp-10h]
  __int128 v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+110h] [rbp+10h]
  __int128 v65; // [rsp+120h] [rbp+20h] BYREF
  __int128 v66; // [rsp+130h] [rbp+30h]
  __int128 v67; // [rsp+140h] [rbp+40h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+150h] [rbp+50h] BYREF
  __int64 (__fastcall *v69)(); // [rsp+160h] [rbp+60h] BYREF
  __int64 v70; // [rsp+168h] [rbp+68h]
  _QWORD *v71; // [rsp+170h] [rbp+70h]
  GUID ActivityId; // [rsp+178h] [rbp+78h] BYREF
  __int64 v73; // [rsp+188h] [rbp+88h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+190h] [rbp+90h] BYREF
  int *v75; // [rsp+1A0h] [rbp+A0h]
  __int64 v76; // [rsp+1A8h] [rbp+A8h]
  __int64 *v77; // [rsp+1B0h] [rbp+B0h]
  __int64 v78; // [rsp+1B8h] [rbp+B8h]
  signed __int64 *v79; // [rsp+1C0h] [rbp+C0h]
  __int64 v80; // [rsp+1C8h] [rbp+C8h]
  int *v81; // [rsp+1D0h] [rbp+D0h]
  __int64 v82; // [rsp+1D8h] [rbp+D8h]
  __int64 *v83; // [rsp+1E0h] [rbp+E0h]
  __int64 v84; // [rsp+1E8h] [rbp+E8h]
  int *v85; // [rsp+1F0h] [rbp+F0h]
  __int64 v86; // [rsp+1F8h] [rbp+F8h]
  PEPROCESS *p_Process; // [rsp+200h] [rbp+100h]
  __int64 v88; // [rsp+208h] [rbp+108h]

  v2 = (_QWORD *)(a2 + 104);
  v3 = *(_DWORD *)(a2 + 32) <= 0;
  v64 = 0;
  v5 = *(_QWORD *)(a2 + 104);
  v6 = a2;
  memset(v61, 0, sizeof(v61));
  v55 = (_QWORD *)(a2 + 104);
  v62 = 0;
  v65 = 0;
  v66 = 0;
  v63 = 0;
  v7 = *(_QWORD *)(v5 + 8);
  *((_QWORD *)&v66 + 1) = *(unsigned int *)(a2 + 64);
  *(_QWORD *)&v61[0] = AfdTLFastDgramSendComplete;
  *((_QWORD *)&v62 + 1) = &v65;
  *((_QWORD *)&v65 + 1) = v7;
  *((_QWORD *)&v61[0] + 1) = a2;
  if ( !v3 )
    *(_QWORD *)&v62 = *(_QWORD *)(a2 + 40);
  v8 = *(_DWORD *)(a2 + 16);
  if ( v8 > 0 )
  {
    *(_QWORD *)&v63 = *(_QWORD *)(a2 + 24);
    DWORD2(v63) = v8;
  }
  do
  {
    v9 = *(_DWORD *)(a1 + 256);
    if ( v9 <= 0 )
    {
      v10 = -1073741816;
      v11 = -1073741816;
      goto LABEL_10;
    }
  }
  while ( v9 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 256), v9 + 1, v9) );
  v10 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)(a1 + 24) + 24LL))(*(_QWORD *)(a1 + 16), v61);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 256), 0xFFFFFFFF) == 1 )
  {
    v35 = *(_QWORD *)(a1 + 272);
    *(_QWORD *)&v67 = AfdTLCloseEndpointComplete;
    *((_QWORD *)&v67 + 1) = a1;
    _InterlockedAdd((volatile signed __int32 *)(v35 + 16), 2u);
    v36 = (**(__int64 (__fastcall ***)(_QWORD, __int128 *))(a1 + 24))(*(_QWORD *)(a1 + 16), &v67);
    AfdTlDereferenceTransport(v35);
    if ( (*(_DWORD *)(a1 + 8) & 0x4000) != 0 )
      AfdTLSetCloseCompleteEvent(a1);
    if ( v36 != 259 )
      AfdTLCloseEndpointComplete(a1, v36);
  }
  v11 = v10;
  if ( v10 == 259 )
    goto LABEL_39;
  v2 = v55;
LABEL_10:
  v12 = *(_QWORD *)(v6 + 56);
  v13 = (__int64 *)(v6 + 56);
  v14 = v64;
  v15 = *(_DWORD *)(v6 + 64);
  v16 = v10;
  v17 = *(_DWORD *)(v6 + 72);
  v60 = (unsigned __int64 *)(v6 + 56);
  memset(&LockHandle, 0, sizeof(LockHandle));
  *(_DWORD *)(v12 + 40) = v17;
  if ( v10 == -1073741252 )
    goto LABEL_11;
  if ( v10 > -1073741503 )
  {
    if ( v10 <= -1073741251 )
    {
      if ( v10 == -1073741251 || v10 == -1073741306 || v10 == -1073741305 || v10 == -1073741275 )
        goto LABEL_11;
      goto LABEL_58;
    }
    v37 = v10 == 0;
  }
  else
  {
    if ( v10 == -1073741503 )
      goto LABEL_11;
    if ( v10 > -1073741790 )
    {
      if ( v10 == -1073741670 || v10 == -1073741634 || v10 == -1073741536 )
        goto LABEL_11;
      goto LABEL_58;
    }
    if ( v10 == -1073741790 || v10 == -1073741823 || v10 == -1073741811 )
      goto LABEL_11;
    v37 = v10 == -1073741801;
  }
  if ( !v37 )
LABEL_58:
    v16 = 0;
LABEL_11:
  *(_DWORD *)(*v2 + 48LL) = v16;
  v18 = _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + 48), -1, 0);
  v19 = v18;
  if ( !v18 )
    goto LABEL_37;
  if ( *(_QWORD *)(v6 + 24) )
  {
    v49 = *v13;
    AFDETW_TRACESENDMSG(1, 3102, v18);
  }
  else if ( *(_DWORD *)(v6 + 32) )
  {
    v49 = *v13;
    AFDETW_TRACESENDTO(1, 3049, v18);
  }
  else
  {
    v20 = *v13;
    v67 = 0;
    if ( g_AfdEtwTraceEnable || Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v70 = 0;
      v69 = (__int64 (__fastcall *)())v18;
      v67 = v6;
    }
    if ( g_AfdEtwTraceEnable )
    {
      *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_SEND;
      *(_WORD *)&EventDescriptor.Opcode = -5364;
      HIBYTE(EventDescriptor.Task) = 3;
      v34 = *(_WORD *)v18 == 0xAFD1;
      LODWORD(Process) = v16;
      v54 = v14;
      v59 = v20;
      EventDescriptor.Keyword = (!v34 + 17LL) | 0x8000000000000004uLL;
      v56 = 0;
      v53 = 1;
      v58 = v18;
      EventDescriptor.Level = ((v16 >> 31) & 0xFE) + 4;
      v52 = 3403;
      v51 = 1;
      *(_QWORD *)ActivityId.Data4 = 0;
      *(_QWORD *)&ActivityId.Data1 = v6;
      v56 = *(_QWORD *)(v18 + 48);
      UserData.Ptr = (ULONGLONG)&v51;
      v75 = &v52;
      v77 = &v56;
      v79 = &v58;
      v81 = &v53;
      v83 = &v59;
      v85 = &v54;
      p_Process = &Process;
      *(_QWORD *)&UserData.Size = 4;
      v76 = 4;
      v78 = 8;
      v80 = 8;
      v82 = 4;
      v84 = 8;
      v86 = 4;
      v88 = 4;
      EtwWrite(g_AfdEtwHandle, &EventDescriptor, &ActivityId, 8u, &UserData);
      if ( g_AfdEtwTraceEnable )
        goto LABEL_119;
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
LABEL_119:
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
        EtwEx_tidActivityInfo(v20, &ActivityStop, &v67);
    }
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v19 + 56), &LockHandle);
  *(_DWORD *)(v19 + 156) -= v15;
  v24 = *(_DWORD *)(v19 + 156);
  if ( v24 >= *(_DWORD *)(v19 + 160) && v24 )
    goto LABEL_25;
  if ( *(_WORD *)v19 == 6909 )
  {
    v21 = *(unsigned int *)(v19 + 400);
    if ( (int)v21 >= 0 )
    {
      if ( *(_QWORD *)(v19 + 120) )
      {
        AfdSanPollUpdate(v19);
        *(_DWORD *)(v19 + 400) |= 0x80000000;
      }
    }
  }
  v25 = *(_DWORD *)(v19 + 8);
  if ( (v25 & 0x2000000) != 0 )
  {
    *(_DWORD *)(v19 + 8) = v25 & 0xFDFFFFFF;
    v47 = *(_DWORD *)(v19 + 72);
    *(_DWORD *)(v19 + 72) = v47 | 4;
    *(_DWORD *)(v19 + 412) = 0;
    if ( (xmmword_1400875E0 & 0x20) != 0 )
    {
      LODWORD(v49) = *(_DWORD *)(v19 + 400);
      WPP_SF_qqLLL(v22, v21, v23, v19, *(_QWORD *)(v19 + 456), v49, v47 | 4, 4);
    }
    if ( ((unsigned __int8)~(_BYTE)v47 & *(_BYTE *)(v19 + 400) & 4) != 0 )
    {
      v48 = *(_QWORD *)(v19 + 456);
      if ( v48 )
      {
        if ( (xmmword_1400875E0 & 0x20) != 0 )
          WPP_SF_q(1029, 15, WPP_e3713146daf23867649962a1742965d7_Traceguids, v48);
        KeSetEvent(*(PRKEVENT *)(v19 + 456), AfdPriorityBoost, 0);
      }
    }
  }
  v26 = *(_QWORD *)(v19 + 384);
  if ( v26 )
    *(_WORD *)(v26 + 100) |= 4u;
  if ( (unsigned __int8)AfdIndicatePollEvent(v19, 4, 0, &LockHandle) )
  {
    AfdNotifySockIndicateEventsUnlock(v19, 0, 0);
    goto LABEL_26;
  }
  ActivityId = 0;
  v73 = 0;
  if ( !*(_QWORD *)(v19 + 384) || !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(v19 + 392)) )
  {
LABEL_25:
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_26;
  }
  AfdNotifyPostEvents(v19, &LockHandle, 0);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v19 + 392));
LABEL_26:
  v27 = *(unsigned int *)(v6 + 72);
  v28 = *(struct _KPROCESS **)(v19 + 48);
  Process = v28;
  if ( (_DWORD)v27 == AfdBufferTagSize )
  {
    v40 = *(_WORD *)(v6 + 96);
    if ( (v40 & 0x10) != 0 )
    {
      v71 = *(_QWORD **)(v6 + 48);
      v70 = 0;
      v41 = (_QWORD *)*v71;
      *v71 = 0;
      *(_WORD *)(v6 + 96) &= 0xFFEDu;
      v69 = AfdTLDontCareIOCompletion;
      (*(void (__fastcall **)(_QWORD, __int64 (__fastcall **)()))(v41[1] + 48LL))(*v41, &v69);
    }
    else
    {
      if ( (v40 & 8) == 0 )
        goto LABEL_80;
      *(_WORD *)(v6 + 96) = v40 & 0xFFF7;
      TdiReturnChainedReceives((PVOID *)(v6 + 48), 1u);
    }
    v28 = Process;
LABEL_80:
    v42 = *(_QWORD **)(v6 + 40);
    if ( v42 != v55 )
    {
      if ( v42 )
      {
        v46 = (char *)PplAddressPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
        if ( !v46[176] )
          PplpLazyInitializeLookasideList(PplAddressPool, v46 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v46 + 64), v42);
        *(_QWORD *)(v6 + 40) = 0;
      }
      if ( (*(_WORD *)(v6 + 96) & 0x100) == 0 )
      {
        if ( Process )
          PsReturnPoolQuota(Process, (POOL_TYPE)512, *(unsigned __int16 *)(v6 + 98) + 104LL);
        *(_WORD *)(v6 + 96) |= 0x100u;
      }
      v43 = (char *)AfdPplBufferTagPool + 128 * (unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 92) + 1);
      if ( !v43[176] )
        PplpLazyInitializeLookasideList(AfdPplBufferTagPool, v43 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v43 + 64), (PVOID)v6);
      goto LABEL_36;
    }
    if ( v28 )
      PsReturnPoolQuota(v28, (POOL_TYPE)512, *(unsigned __int16 *)(v6 + 98) + 104LL);
    goto LABEL_73;
  }
  v29 = *(unsigned __int16 *)(v6 + 98);
  if ( v29 == (_DWORD)AfdStandardAddressLength && (unsigned int)v27 <= (unsigned int)AfdHugeBufferSize )
  {
    if ( (_DWORD)v27 == (_DWORD)AfdSmallBufferSize )
    {
      v30 = AfdPplSmallBufferPool;
      v31 = AfdPplSmallBufferSize;
    }
    else if ( (_DWORD)v27 == (_DWORD)AfdMediumBufferSize )
    {
      v30 = AfdPplMediumBufferPool;
      v31 = AfdPplMediumBufferSize;
    }
    else if ( (_DWORD)v27 == (_DWORD)AfdLargeBufferSize )
    {
      v30 = AfdPplLargeBufferPool;
      v31 = AfdPplLargeBufferSize;
    }
    else
    {
      v30 = AfdPplHugeBufferPool;
      v31 = AfdPplHugeBufferSize;
    }
    if ( (*(_WORD *)(v6 + 96) & 0x100) == 0 )
    {
      if ( v28 )
        PsReturnPoolQuota(v28, (POOL_TYPE)512, v31);
      *(_WORD *)(v6 + 96) |= 0x100u;
    }
    v32 = (unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 92) + 1) << 7;
    if ( !v30[v32 + 176] )
      PplpLazyInitializeLookasideList(v30, &v30[v32 + 64]);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)&v30[v32 + 64], (PVOID)v6);
    goto LABEL_36;
  }
  if ( v28 )
  {
    v44 = AfdTdiStackSize;
    v45 = ((v27 + 15) & 0xFFFFFFF0)
        + 128
        + ((MmSizeOfMdl(0, v27) + 15) & 0xFFFFFFF0)
        + v29
        + (((unsigned __int16)(72 * v44 + 208) + 15) & 0xFFFFFFF0);
    if ( v45 < 0x1000 )
    {
      v45 += (_BYTE)v44 == AfdTdiStackSize ? AfdAlignmentOverhead : AfdBufferAlignment - 16;
      if ( v45 >= 0x1000 )
        v45 = 4096;
    }
    PsReturnPoolQuota(Process, (POOL_TYPE)512, v45);
  }
  v38 = *(_WORD *)(v6 + 96);
  v39 = (v38 >> 5) & 3;
  if ( v39 == 1 )
  {
    v6 = *v55;
  }
  else if ( v39 )
  {
    if ( v39 == 2 )
      v6 = *v60;
    else
      v6 = *(_QWORD *)(v6 + 112);
  }
  if ( (v38 & 0x80u) != 0 )
    v6 -= *(_QWORD *)(v6 - 8);
LABEL_73:
  ExFreePoolWithTag((PVOID)v6, 0x42646641u);
LABEL_36:
  AfdDereferenceEndpoint(v19);
LABEL_37:
  if ( v10 == -1073741252 )
    return v11;
LABEL_39:
  if ( v10 <= -1073741503 )
  {
    if ( v10 == -1073741503 )
      return v11;
    if ( v10 > -1073741790 )
    {
      if ( v10 != -1073741670 && v10 != -1073741634 && v10 != -1073741536 )
        return 0;
      return v11;
    }
    if ( v10 == -1073741790 || v10 == -1073741823 || v10 == -1073741811 )
      return v11;
    v34 = v10 == -1073741801;
  }
  else
  {
    if ( v10 <= -1073741251 )
    {
      if ( v10 != -1073741251 && v10 != -1073741306 && v10 != -1073741305 && v10 != -1073741275 )
        return 0;
      return v11;
    }
    if ( !v10 )
      return v11;
    v34 = v10 == 259;
  }
  if ( !v34 )
    return 0;
  return v11;
}

```

## disassembly

```asm
0x14000de50  push    rbp
0x14000de52  push    rsi
0x14000de53  push    rdi
0x14000de54  push    r12
0x14000de56  lea     rbp, [rsp-138h]
0x14000de5e  sub     rsp, 238h
0x14000de65  mov     rax, cs:__security_cookie
0x14000de6c  xor     rax, rsp
0x14000de6f  mov     [rbp+150h+var_40], rax
0x14000de76  xor     eax, eax
0x14000de78  lea     r10, [rdx+68h]
0x14000de7c  cmp     dword ptr [rdx+20h], 0
0x14000de80  xorps   xmm0, xmm0
0x14000de83  mov     [rbp+150h+var_140], rax
0x14000de87  mov     rdi, rcx
0x14000de8a  mov     rax, [r10]
0x14000de8d  mov     rsi, rdx
0x14000de90  movups  [rbp+150h+var_180], xmm0
0x14000de94  mov     [rbp+150h+var_1C8], r10
0x14000de98  movups  [rbp+150h+var_160], xmm0
0x14000de9c  movups  [rbp+150h+var_130], xmm0
0x14000dea0  movups  [rbp+150h+var_120], xmm0
0x14000dea4  movups  [rbp+150h+var_170], xmm0
0x14000dea8  movups  [rbp+150h+var_150], xmm0
0x14000deac  mov     rcx, [rax+8]
0x14000deb0  mov     eax, [rdx+40h]
0x14000deb3  mov     qword ptr [rbp+150h+var_120+8], rax
0x14000deb7  lea     rax, AfdTLFastDgramSendComplete
0x14000debe  mov     qword ptr [rbp+150h+var_180], rax
0x14000dec2  lea     rax, [rbp+150h+var_130]
0x14000dec6  mov     qword ptr [rbp+150h+var_160+8], rax
0x14000deca  mov     qword ptr [rbp+150h+var_130+8], rcx
0x14000dece  mov     qword ptr [rbp+150h+var_180+8], rdx
0x14000ded2  jle     short loc_14000DEDC
0x14000ded4  mov     rax, [rdx+28h]
0x14000ded8  mov     qword ptr [rbp+150h+var_160], rax
0x14000dedc  mov     ecx, [rdx+10h]
0x14000dedf  test    ecx, ecx
0x14000dee1  jg      loc_14000E22A
0x14000dee7  mov     [rsp+250h+arg_10], rbx
0x14000deef  mov     [rsp+250h+var_28], r14
0x14000def7  mov     [rsp+250h+var_30], r15
0x14000deff  nop
0x14000df00  mov     eax, [rdi+100h]
0x14000df06  test    eax, eax
0x14000df08  jle     loc_14000E603
0x14000df0e  lea     ecx, [rax+1]
0x14000df11  lock cmpxchg [rdi+100h], ecx
0x14000df19  jnz     short loc_14000DF00
0x14000df1b  mov     rax, [rdi+18h]
0x14000df1f  lea     rdx, [rbp+150h+var_180]
0x14000df23  mov     rcx, [rdi+10h]
0x14000df27  mov     rax, [rax+18h]
0x14000df2b  call    _guard_dispatch_icall
0x14000df30  mov     r15, 0FFFFFFFFFFFFFFFFh
0x14000df37  mov     r14d, eax
0x14000df3a  mov     ecx, r15d
0x14000df3d  lock xadd [rdi+100h], ecx
0x14000df45  cmp     ecx, 1
0x14000df48  jz      loc_14000E1C2
0x14000df4e  mov     r12d, r14d
0x14000df51  cmp     r14d, 103h
0x14000df58  jz      loc_14000E195
0x14000df5e  mov     r10, [rbp+150h+var_1C8]
0x14000df62  mov     rcx, [rsi+38h]
0x14000df66  lea     r8, [rsi+38h]
0x14000df6a  mov     r9, [rbp+150h+var_140]
0x14000df6e  xor     eax, eax
0x14000df70  mov     edi, [rsi+40h]
0x14000df73  xorps   xmm0, xmm0
0x14000df76  mov     qword ptr [rbp+150h+LockHandle.OldIrql], rax
0x14000df7a  mov     edx, r14d
0x14000df7d  mov     eax, [rsi+48h]
0x14000df80  mov     [rsp+250h+var_20], r13
0x14000df88  mov     [rbp+150h+var_190], r8
0x14000df8c  movups  xmmword ptr [rbp+150h+LockHandle.LockQueue.Next], xmm0
0x14000df90  mov     [rcx+28h], eax
0x14000df93  cmp     r14d, 0C000023Ch
0x14000df9a  jnz     loc_14000E27C
0x14000dfa0  mov     rax, [r10]
0x14000dfa3  mov     [rax+30h], edx
0x14000dfa6  xor     eax, eax
0x14000dfa8  lock cmpxchg [rsi+30h], r15
0x14000dfae  mov     rbx, rax
0x14000dfb1  jz      loc_14000E14C
0x14000dfb7  cmp     qword ptr [rsi+18h], 0
0x14000dfbc  jnz     loc_14000E23A
0x14000dfc2  cmp     dword ptr [rsi+20h], 0
0x14000dfc6  jnz     loc_14000E4D1
0x14000dfcc  cmp     cs:g_AfdEtwTraceEnable, 0
0x14000dfd3  mov     rcx, [r8]
0x14000dfd6  movups  [rbp+150h+var_110], xmm0
0x14000dfda  jnz     loc_14000E87E
0x14000dfe0  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000dfe6  test    eax, eax
0x14000dfe8  jnz     loc_14000E87E
0x14000dfee  cmp     cs:g_AfdEtwTraceEnable, 0
0x14000dff5  jnz     loc_14000E6BC
0x14000dffb  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000e001  test    eax, eax
0x14000e003  jnz     loc_14000E83F
0x14000e009  lea     rcx, [rbx+38h]; SpinLock
0x14000e00d  lea     rdx, [rbp+150h+LockHandle]; LockHandle
0x14000e011  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000e018  nop     dword ptr [rax+rax+00h]
0x14000e01d  sub     [rbx+9Ch], edi
0x14000e023  mov     eax, [rbx+9Ch]
0x14000e029  cmp     eax, [rbx+0A0h]
0x14000e02f  jnb     loc_14000E513
0x14000e035  mov     eax, 1AFDh
0x14000e03a  cmp     [rbx], ax
0x14000e03d  jz      loc_14000E94C
0x14000e043  mov     eax, [rbx+8]
0x14000e046  bt      eax, 19h
0x14000e04a  jb      loc_14000E589
0x14000e050  mov     rax, [rbx+180h]
0x14000e057  test    rax, rax
0x14000e05a  jnz     loc_14000E8C8
0x14000e060  lea     r9, [rbp+150h+LockHandle]
0x14000e064  xor     r8d, r8d
0x14000e067  mov     edx, 4
0x14000e06c  mov     rcx, rbx
0x14000e06f  call    AfdIndicatePollEvent
0x14000e074  test    al, al
0x14000e076  jnz     loc_14000E9C6
0x14000e07c  xor     eax, eax
0x14000e07e  xorps   xmm0, xmm0
0x14000e081  movups  xmmword ptr [rbp+150h+ActivityId.Data1], xmm0
0x14000e085  mov     [rbp+150h+var_C8], rax
0x14000e08c  cmp     [rbx+180h], rax
0x14000e093  jnz     loc_140075A9A
0x14000e099  lea     rcx, [rbp+150h+LockHandle]; LockHandle
0x14000e09d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000e0a4  nop     dword ptr [rax+rax+00h]
0x14000e0a9  mov     edi, [rsi+48h]
0x14000e0ac  cmp     edi, cs:AfdBufferTagSize
0x14000e0b2  mov     rcx, [rbx+30h]; Process
0x14000e0b6  mov     [rsp+250h+Process], rcx
0x14000e0bb  jz      loc_14000E38C
0x14000e0c1  movzx   r15d, word ptr [rsi+62h]
0x14000e0c6  cmp     r15d, cs:AfdStandardAddressLength
0x14000e0cd  jnz     loc_14000E30F
0x14000e0d3  cmp     edi, cs:AfdHugeBufferSize
0x14000e0d9  ja      loc_14000E30F
0x14000e0df  cmp     edi, cs:AfdSmallBufferSize
0x14000e0e5  jz      loc_14000E379
0x14000e0eb  cmp     edi, cs:AfdMediumBufferSize
0x14000e0f1  jnz     loc_14000E520
0x14000e0f7  mov     r15, cs:AfdPplMediumBufferPool
0x14000e0fe  mov     r8, cs:AfdPplMediumBufferSize; Amount
0x14000e105  mov     edi, 100h
0x14000e10a  test    [rsi+60h], di
0x14000e10e  jz      loc_14000E640
0x14000e114  mov     edi, [rsi+5Ch]
0x14000e117  inc     edi
0x14000e119  shl     rdi, 7
0x14000e11d  movzx   eax, byte ptr [rdi+r15+0B0h]
0x14000e126  test    al, al
0x14000e128  jz      loc_14000E86A
0x14000e12e  lea     rcx, [rdi+40h]
0x14000e132  mov     rdx, rsi; Entry
0x14000e135  add     rcx, r15; Lookaside
0x14000e138  call    cs:__imp_ExFreeToLookasideListEx
0x14000e13f  nop     dword ptr [rax+rax+00h]
0x14000e144  mov     rcx, rbx
0x14000e147  call    AfdDereferenceEndpoint
0x14000e14c  mov     r13, [rsp+250h+var_20]
0x14000e154  cmp     r14d, 0C000023Ch
0x14000e15b  jnz     short loc_14000E195
0x14000e15d  mov     r15, [rsp+250h+var_30]
0x14000e165  mov     eax, r12d
0x14000e168  mov     r14, [rsp+250h+var_28]
0x14000e170  mov     rbx, [rsp+250h+arg_10]
0x14000e178  mov     rcx, [rbp+150h+var_40]
0x14000e17f  xor     rcx, rsp; StackCookie
0x14000e182  call    __security_check_cookie
0x14000e187  add     rsp, 238h
0x14000e18e  pop     r12
0x14000e190  pop     rdi
0x14000e191  pop     rsi
0x14000e192  pop     rbp
0x14000e193  retn
0x14000e195  cmp     r14d, 0C0000141h
0x14000e19c  jle     loc_14000E2D0
0x14000e1a2  cmp     r14d, 0C000023Dh
0x14000e1a9  jle     loc_14000EA0D
0x14000e1af  test    r14d, r14d
0x14000e1b2  jz      short loc_14000E15D
0x14000e1b4  cmp     r14d, 103h
0x14000e1bb  jz      short loc_14000E15D
0x14000e1bd  xor     r12d, r12d
0x14000e1c0  jmp     short loc_14000E15D
0x14000e1c2  mov     rbx, [rdi+110h]
0x14000e1c9  lea     rax, AfdTLCloseEndpointComplete
0x14000e1d0  mov     qword ptr [rbp+150h+var_110], rax
0x14000e1d4  mov     qword ptr [rbp+150h+var_110+8], rdi
0x14000e1d8  lock add dword ptr [rbx+10h], 2
0x14000e1dd  mov     rax, [rdi+18h]
0x14000e1e1  lea     rdx, [rbp+150h+var_110]
0x14000e1e5  mov     rcx, [rdi+10h]
0x14000e1e9  mov     rax, [rax]
0x14000e1ec  call    _guard_dispatch_icall
0x14000e1f1  mov     rcx, rbx
0x14000e1f4  mov     r12d, eax
0x14000e1f7  call    AfdTlDereferenceTransport
0x14000e1fc  mov     edx, [rdi+8]
0x14000e1ff  bt      edx, 0Eh
0x14000e203  jnb     short loc_14000E20D
0x14000e205  mov     rcx, rdi
0x14000e208  call    AfdTLSetCloseCompleteEvent
0x14000e20d  cmp     r12d, 103h
0x14000e214  jz      loc_14000DF4E
0x14000e21a  mov     edx, r12d
0x14000e21d  mov     rcx, rdi
0x14000e220  call    AfdTLCloseEndpointComplete
0x14000e225  jmp     loc_14000DF4E
0x14000e22a  mov     rax, [rdx+18h]
0x14000e22e  mov     qword ptr [rbp+150h+var_150], rax
0x14000e232  mov     dword ptr [rbp+150h+var_150+8], ecx
0x14000e235  jmp     loc_14000DEE7
0x14000e23a  mov     rcx, [rsi+28h]
0x14000e23e  mov     [rsp+250h+var_208], rsi
0x14000e243  mov     [rsp+250h+var_210], rcx
0x14000e248  mov     rcx, [r8]
0x14000e24b  mov     r8, rbx
0x14000e24e  mov     [rsp+250h+var_218], edx
0x14000e252  mov     edx, 0C1Eh
0x14000e257  mov     [rsp+250h+var_220], r9d
0x14000e25c  mov     r9d, 1
0x14000e262  mov     [rsp+250h+var_228], rcx
0x14000e267  mov     ecx, r9d
0x14000e26a  mov     dword ptr [rsp+250h+UserData], 1
0x14000e272  call    AFDETW_TRACESENDMSG
0x14000e277  jmp     loc_14000E009
0x14000e27c  cmp     r14d, 0C0000141h
0x14000e283  jg      loc_14000E364
0x14000e289  jz      loc_14000DFA0
0x14000e28f  cmp     r14d, 0C0000022h
0x14000e296  jg      loc_14000E8EE
0x14000e29c  jz      loc_14000DFA0
0x14000e2a2  cmp     r14d, 0C0000001h
0x14000e2a9  jz      loc_14000DFA0
0x14000e2af  cmp     r14d, 0C000000Dh
0x14000e2b6  jz      loc_14000DFA0
0x14000e2bc  cmp     r14d, 0C0000017h
0x14000e2c3  jz      loc_14000DFA0
0x14000e2c9  xor     edx, edx
0x14000e2cb  jmp     loc_14000DFA0
0x14000e2d0  jz      loc_14000E15D
0x14000e2d6  cmp     r14d, 0C0000022h
0x14000e2dd  jg      loc_14000E9E1
0x14000e2e3  jz      loc_14000E15D
0x14000e2e9  cmp     r14d, 0C0000001h
0x14000e2f0  jz      loc_14000E15D
0x14000e2f6  cmp     r14d, 0C000000Dh
0x14000e2fd  jz      loc_14000E15D
0x14000e303  cmp     r14d, 0C0000017h
0x14000e30a  jmp     loc_14000E1BB
0x14000e30f  test    rcx, rcx
0x14000e312  jnz     loc_14000E43F
0x14000e318  movzx   edx, word ptr [rsi+60h]
0x14000e31c  mov     ecx, edx
0x14000e31e  shr     ecx, 5
0x14000e321  and     ecx, 3
0x14000e324  cmp     ecx, 1
0x14000e327  jz      short loc_14000E33C
0x14000e329  test    ecx, ecx
0x14000e32b  jz      short loc_14000E343
0x14000e32d  cmp     ecx, 2
0x14000e330  jz      loc_14000E65F
0x14000e336  mov     rsi, [rsi+70h]
0x14000e33a  jmp     short loc_14000E343
0x14000e33c  mov     rax, [rbp+150h+var_1C8]
0x14000e340  mov     rsi, [rax]
0x14000e343  test    dl, dl
0x14000e345  js      loc_14000E9D8
0x14000e34b  mov     edx, 42646641h; Tag
0x14000e350  mov     rcx, rsi; P
0x14000e353  call    cs:__imp_ExFreePoolWithTag
0x14000e35a  nop     dword ptr [rax+rax+00h]
0x14000e35f  jmp     loc_14000E144
0x14000e364  cmp     r14d, 0C000023Dh
0x14000e36b  jle     loc_14000E91A
0x14000e371  test    r14d, r14d
0x14000e374  jmp     loc_14000E2C3
0x14000e379  mov     r15, cs:AfdPplSmallBufferPool
0x14000e380  mov     r8, cs:AfdPplSmallBufferSize
0x14000e387  jmp     loc_14000E105
0x14000e38c  movzx   eax, word ptr [rsi+60h]
0x14000e390  test    al, 10h
0x14000e392  jz      loc_14000E66B
0x14000e398  mov     rax, [rsi+30h]
0x14000e39c  mov     edx, 0FFEDh
0x14000e3a1  mov     [rbp+150h+var_E0], rax
0x14000e3a5  mov     [rbp+150h+var_E8], 0
0x14000e3ad  mov     rcx, [rax]
0x14000e3b0  mov     qword ptr [rax], 0
0x14000e3b7  lea     rax, AfdTLDontCareIOCompletion
0x14000e3be  and     [rsi+60h], dx
0x14000e3c2  lea     rdx, [rbp+150h+var_F0]
  ... truncated ...
```
