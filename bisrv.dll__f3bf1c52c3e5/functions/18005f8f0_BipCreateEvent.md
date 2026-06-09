# BipCreateEvent

- ea: `0x18005f8f0`
- end: `0x180060191`
- name: `BipCreateEvent`
- size: `2209`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, PSID Sid, PSID, int, void *Src, size_t Size, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800317f0`

## callees

- `0x1800075f8`
- `0x180007dcc`
- `0x18000d7c0`
- `0x18000da50`
- `0x18001027c`
- `0x18002bcb8`
- `0x180034ae0`
- `0x180037a80`
- `0x18005f150`
- `0x18005f8f0`
- `0x180063ee0`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005fd7c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005fe74`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800600fe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005fd7c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005fe74`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800600fe`
- `ntdll!RtlFreeHeap` at `0x18005fdb9`
- `ntdll!RtlFreeHeap` at `0x18005fdd4`
- `ntdll!RtlFreeHeap` at `0x180060137`
- `ntdll!RtlFreeHeap` at `0x18006013f`
- `ntdll!RtlFreeHeap` at `0x18005fdb9`
- `ntdll!RtlFreeHeap` at `0x18005fdd4`
- `ntdll!RtlFreeHeap` at `0x180060137`
- `ntdll!RtlFreeHeap` at `0x18006013f`
- `ntdll!TpAllocWork` at `0x18005fc24`
- `ntdll!TpAllocWork` at `0x18005fc24`
- `ntdll!RtlAllocateHeap` at `0x18005fa19`
- `ntdll!RtlAllocateHeap` at `0x18005fb70`
- `ntdll!RtlAllocateHeap` at `0x18005fbd0`
- `ntdll!RtlAllocateHeap` at `0x18005fa19`
- `ntdll!RtlAllocateHeap` at `0x18005fb70`
- `ntdll!RtlAllocateHeap` at `0x18005fbd0`
- `ntdll!RtlLengthSid` at `0x18005f974`
- `ntdll!RtlLengthSid` at `0x18005f98a`
- `ntdll!RtlLengthSid` at `0x18005f974`
- `ntdll!RtlLengthSid` at `0x18005f98a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800600a5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800600a5`
- `RPCRT4!UuidCreate` at `0x18005f9cc`
- `RPCRT4!UuidCreate` at `0x18005f9cc`

## pseudocode

```c
__int64 __fastcall BipCreateEvent(
        __int64 a1,
        unsigned int a2,
        int a3,
        _OWORD *a4,
        UUID *a5,
        __int64 *a6,
        PSID Sid,
        PSID a8,
        unsigned int a9,
        void *Src,
        size_t Size,
        void *a12)
{
  ULONG v12; // r15d
  RPC_STATUS v13; // eax
  __int64 v14; // rcx
  int BrokerEvent; // r14d
  __int64 v16; // rsi
  char v17; // r9
  int v18; // r15d
  PVOID Heap; // rax
  int v20; // eax
  UUID v21; // xmm0
  _OWORD *v22; // rax
  __int64 *v23; // rdi
  _WORD *v24; // rcx
  __int64 *v25; // rax
  __int64 v26; // rdx
  __int128 v27; // xmm0
  void *v28; // r14
  PVOID v29; // rax
  void *v30; // r14
  size_t v31; // rbx
  PVOID v32; // rax
  unsigned int v33; // ebx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v34; // rcx
  _QWORD *v35; // rax
  int v36; // r12d
  __int64 v37; // rbx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v40; // edi
  __int64 v41; // rbx
  __int64 *v42; // r8
  __int64 *v43; // rdx
  __int64 v44; // rax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v49; // rcx
  _QWORD *v50; // rax
  int v51; // r12d
  __int64 v52; // rbx
  char v53; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v54; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v55; // [rsp+38h] [rbp-C8h] BYREF
  int v56; // [rsp+3Ch] [rbp-C4h] BYREF
  void *v57; // [rsp+40h] [rbp-C0h]
  _OWORD *v58; // [rsp+48h] [rbp-B8h] BYREF
  void *v59; // [rsp+50h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  void *v61; // [rsp+68h] [rbp-98h]
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  GUID v63; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  char *v65; // [rsp+A0h] [rbp-60h]
  int v66; // [rsp+A8h] [rbp-58h]
  int v67; // [rsp+ACh] [rbp-54h]
  UUID *p_Uuid; // [rsp+B0h] [rbp-50h]
  __int64 v69; // [rsp+B8h] [rbp-48h]
  __int64 *v70; // [rsp+C0h] [rbp-40h]
  int v71; // [rsp+C8h] [rbp-38h]
  int v72; // [rsp+CCh] [rbp-34h]
  __int64 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  GUID *v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  ULONG *v81; // [rsp+100h] [rbp+0h]
  __int64 v82; // [rsp+108h] [rbp+8h]
  int *v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  unsigned int *v85; // [rsp+120h] [rbp+20h]
  __int64 v86; // [rsp+128h] [rbp+28h]
  char *v87; // [rsp+130h] [rbp+30h]
  __int64 v88; // [rsp+138h] [rbp+38h]
  _OWORD **v89; // [rsp+140h] [rbp+40h]
  __int64 v90; // [rsp+148h] [rbp+48h]
  void **v91; // [rsp+150h] [rbp+50h]
  __int64 v92; // [rsp+158h] [rbp+58h]

  *(_QWORD *)&EventDescriptor.Id = a1;
  v61 = a12;
  v58 = a4;
  v56 = a3;
  v54 = a2;
  v59 = a8;
  v57 = Sid;
  v53 = 0;
  v63 = 0;
  Uuid = GUID_NULL;
  if ( Sid )
    v12 = RtlLengthSid(Sid);
  else
    v12 = 0;
  if ( a8 )
    v55 = RtlLengthSid(a8);
  else
    v55 = 0;
  if ( a5 )
  {
    Uuid = *a5;
  }
  else
  {
    v13 = UuidCreate(&Uuid);
    if ( v13 && v13 != 1824 )
    {
      BrokerEvent = -1073741693;
      v16 = 0;
      v17 = 0;
      v18 = 2000;
LABEL_60:
      v23 = a6;
      goto LABEL_61;
    }
  }
  Heap = RtlAllocateHeap(BipHeap, 0, (unsigned int)(Size + 796));
  v16 = (__int64)Heap;
  if ( !Heap )
  {
    BrokerEvent = -1073741801;
    v18 = 1000;
    v17 = 0;
    goto LABEL_60;
  }
  memset_0(Heap, 0, (unsigned int)(Size + 796));
  *(_OWORD *)v16 = 0;
  *(_OWORD *)(v16 + 16) = 0;
  *(_OWORD *)(v16 + 32) = 0;
  *(_QWORD *)(v16 + 48) = 0;
  v20 = v56;
  *(_DWORD *)(v16 + 28) = 1;
  v21 = Uuid;
  *(_DWORD *)(v16 + 24) = v20;
  v22 = v58;
  *(UUID *)(v16 + 32) = v21;
  *(_DWORD *)(v16 + 48) = 1;
  *(_OWORD *)(v16 + 128) = *v22;
  *(_QWORD *)(v16 + 64) = v16 + 56;
  *(_QWORD *)(v16 + 56) = v16 + 56;
  *(_QWORD *)(v16 + 80) = v16 + 72;
  *(_QWORD *)(v16 + 72) = v16 + 72;
  *(_QWORD *)(v16 + 120) = 0;
  *(_DWORD *)(v16 + 748) = 0;
  BipTriggerSettingsInitialize(v16 + 584);
  if ( (_DWORD)Size )
  {
    *(_DWORD *)(v16 + 792) = Size;
    memcpy_0((void *)(v16 + 796), Src, (unsigned int)Size);
  }
  v23 = a6;
  v24 = (_WORD *)(v16 + 192);
  if ( a6 )
  {
    v25 = a6;
    v26 = 3;
    do
    {
      v24 += 64;
      v27 = *(_OWORD *)v25;
      v25 += 16;
      *((_OWORD *)v24 - 8) = v27;
      *((_OWORD *)v24 - 7) = *((_OWORD *)v25 - 7);
      *((_OWORD *)v24 - 6) = *((_OWORD *)v25 - 6);
      *((_OWORD *)v24 - 5) = *((_OWORD *)v25 - 5);
      *((_OWORD *)v24 - 4) = *((_OWORD *)v25 - 4);
      *((_OWORD *)v24 - 3) = *((_OWORD *)v25 - 3);
      *((_OWORD *)v24 - 2) = *((_OWORD *)v25 - 2);
      *((_OWORD *)v24 - 1) = *((_OWORD *)v25 - 1);
      --v26;
    }
    while ( v26 );
    *v24 = *(_WORD *)v25;
  }
  else
  {
    memset_0(v24, 0, 0x182u);
  }
  v28 = v57;
  if ( v57 )
  {
    v29 = RtlAllocateHeap(BipHeap, 0, v12);
    *(_QWORD *)(v16 + 168) = v29;
    if ( !v29 )
    {
      v17 = 0;
      BrokerEvent = -1073741801;
      v18 = 3000;
LABEL_61:
      v33 = v54;
      goto LABEL_62;
    }
    memcpy_0(v29, v28, v12);
  }
  else
  {
    *(_QWORD *)(v16 + 168) = 0;
  }
  v30 = v59;
  if ( v59 )
  {
    v31 = v55;
    v32 = RtlAllocateHeap(BipHeap, 0, v55);
    *(_QWORD *)(v16 + 176) = v32;
    if ( !v32 )
    {
      v17 = 0;
      BrokerEvent = -1073741801;
      v18 = 4000;
      goto LABEL_61;
    }
    memcpy_0(v32, v30, v31);
  }
  else
  {
    *(_QWORD *)(v16 + 176) = 0;
  }
  v33 = v54;
  BrokerEvent = TpAllocWork(v16 + 160, BipCreateBrokerEventCallback, v16, 0);
  if ( BrokerEvent >= 0 )
  {
    BrokerEvent = BipCreateBrokerEvent(v61, v54, v16);
    if ( BrokerEvent < 0 )
    {
      if ( (v54 & 1) != 0 )
      {
        v18 = 6000;
        v17 = 1;
      }
      else
      {
        v17 = 0;
        v18 = 5000;
      }
      goto LABEL_62;
    }
    if ( (v54 & 4) != 0 )
    {
      *(_DWORD *)(v16 + 580) = 0;
    }
    else
    {
      *(_DWORD *)(v16 + 580) = a9;
      BipTriggerSettingsTableFindById(&qword_1800C3F68, a9, v16 + 584);
      *(_DWORD *)(v16 + 24) |= 0x20000000u;
    }
    BipAcquireGlobalLock(v14);
    if ( *(_WORD *)(v16 + 192) )
    {
      if ( *(_QWORD *)(v16 + 168) )
      {
        BrokerEvent = BipAddEventToPackage(v16);
        if ( BrokerEvent < 0 )
        {
          v18 = 7000;
LABEL_59:
          BipLockWatchdogContextDisarmWatchdog(v34);
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v40 = ~(1 << dword_1800C3CB0);
          dword_1800C3CB4 = 0;
          v41 = ThreadLocalStoragePointer[(unsigned int)tls_index];
          *(_DWORD *)(v41 + 8) &= v40;
          RtlReleaseSRWLockExclusive(&BipGlobalLock);
          v14 = 4;
          *(_DWORD *)(v41 + 4) &= v40;
          v17 = v53;
          goto LABEL_60;
        }
      }
    }
    if ( (*(_BYTE *)(v16 + 24) & 2) == 0 && (v33 & 9) != 1 )
    {
      BrokerEvent = BipSaveEventInStore(v16, (v33 >> 4) & 1);
      if ( BrokerEvent < 0 )
      {
        v18 = 8000;
        goto LABEL_59;
      }
      v53 = 1;
    }
    BrokerEvent = BipAddObjectToTable(&qword_1800C4368, v16);
    if ( BrokerEvent >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 28));
      BipLockWatchdogContextDisarmWatchdog(v34);
      v35 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v36 = ~(1 << dword_1800C3CB0);
      dword_1800C3CB4 = 0;
      v37 = v35[(unsigned int)tls_index];
      *(_DWORD *)(v37 + 8) &= v36;
      RtlReleaseSRWLockExclusive(&BipGlobalLock);
      *(_DWORD *)(v37 + 4) &= v36;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 28), 0xFFFFFFFF) == 1 )
      {
        if ( *(_DWORD *)(v16 + 48) != 1 )
        {
          if ( *(_DWORD *)(v16 + 48) == 2 )
            BipWorkItemCheckQueueDestroy((struct _BI_WORK_ITEM *)v16);
          else
            RtlFreeHeap(BipHeap, 0, (PVOID)v16);
          *(UUID *)*(_QWORD *)&EventDescriptor.Id = Uuid;
          return 0;
        }
        BipEventQueueDestroy((struct _BI_LOCK *)&qword_1800C4600);
      }
      *(UUID *)*(_QWORD *)&EventDescriptor.Id = Uuid;
      return 0;
    }
    v18 = 9000;
    goto LABEL_59;
  }
  v17 = 0;
  v18 = 4500;
LABEL_62:
  v42 = (__int64 *)v57;
  v43 = (__int64 *)v59;
  if ( !v57 )
    v42 = &BipTraceLoggingNullSid;
  if ( !v59 )
    v43 = &BipTraceLoggingNullSid;
  v63 = GUID_NULL;
  if ( v58 )
    v63 = (GUID)*v58;
  if ( (unsigned int)dword_1800C3098 > 2 )
  {
    v14 = qword_1800C30B0;
    if ( (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
    {
      v69 = 16;
      p_Uuid = &Uuid;
      if ( v23 )
      {
        v44 = -1;
        while ( *((_WORD *)v23 + ++v44) != 0 )
          ;
        v46 = 2 * v44 + 2;
      }
      else
      {
        v23 = &qword_1800A1670;
        v46 = 2;
      }
      v71 = v46;
      v47 = *((unsigned __int8 *)v42 + 1);
      v73 = v42;
      v76 = v43;
      v53 = v17;
      v70 = v23;
      v74 = 4 * v47 + 8;
      v48 = *((unsigned __int8 *)v43 + 1);
      v72 = 0;
      v75 = 0;
      v78 = 0;
      v80 = 16;
      v77 = 4 * v48 + 8;
      v79 = &v63;
      v81 = &v55;
      v83 = &v56;
      v54 = a9;
      v85 = &v54;
      v87 = &v53;
      v89 = &v58;
      v91 = &v59;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_1800C30A0;
      v55 = v33;
      v82 = 4;
      v84 = 4;
      v86 = 4;
      v88 = 1;
      LODWORD(v58) = BrokerEvent;
      v90 = 4;
      LODWORD(v59) = v18;
      v92 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 3;
      UserData.Size = *(unsigned __int16 *)off_1800C30A0;
      v65 = byte_1800B121B;
      UserData.Reserved = 2;
      v66 = 170;
      v67 = 1;
      LODWORD(v57) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xDu, &UserData);
    }
  }
  if ( v16 )
  {
    BipAcquireGlobalLock(v14);
    *(_DWORD *)(v16 + 24) |= 0x80000000;
    BipLockWatchdogContextDisarmWatchdog(v49);
    v50 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v51 = ~(1 << dword_1800C3CB0);
    dword_1800C3CB4 = 0;
    v52 = v50[(unsigned int)tls_index];
    *(_DWORD *)(v52 + 8) &= v51;
    RtlReleaseSRWLockExclusive(&BipGlobalLock);
    *(_DWORD *)(v52 + 4) &= v51;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 28), 0xFFFFFFFF) == 1 )
    {
      if ( *(_DWORD *)(v16 + 48) == 1 )
      {
        BipEventQueueDestroy((struct _BI_LOCK *)&qword_1800C4600);
      }
      else if ( *(_DWORD *)(v16 + 48) == 2 )
      {
        BipWorkItemCheckQueueDestroy((struct _BI_WORK_ITEM *)v16);
      }
      else
      {
        RtlFreeHeap(BipHeap, 0, (PVOID)v16);
      }
    }
  }
  return (unsigned int)BrokerEvent;
}

```

## disassembly

```asm
0x18005f8f0  push    rbp
0x18005f8f2  push    rbx
0x18005f8f3  push    r12
0x18005f8f5  push    r13
0x18005f8f7  push    r14
0x18005f8f9  push    r15
0x18005f8fb  lea     rbp, [rsp-78h]
0x18005f900  sub     rsp, 178h
0x18005f907  mov     rax, cs:__security_cookie
0x18005f90e  xor     rax, rsp
0x18005f911  mov     [rbp+0A0h+var_40], rax
0x18005f915  mov     rax, [rbp+0A0h+Sid]
0x18005f91c  xorps   xmm0, xmm0
0x18005f91f  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18005f926  mov     rbx, [rbp+0A0h+arg_38]
0x18005f92d  mov     r14, [rbp+0A0h+Src]
0x18005f934  mov     qword ptr [rsp+1A0h+EventDescriptor.Id], rcx
0x18005f939  mov     rcx, [rbp+0A0h+arg_58]
0x18005f940  mov     [rsp+1A0h+var_138], rcx
0x18005f945  xor     cl, cl
0x18005f947  mov     [rsp+1A0h+var_158], r9
0x18005f94c  mov     dword ptr [rsp+1A0h+var_168+4], r8d
0x18005f951  mov     [rsp+1A0h+var_16C], edx
0x18005f955  mov     [rsp+1A0h+var_150], rbx
0x18005f95a  mov     [rsp+1A0h+var_160], rax
0x18005f95f  mov     [rsp+1A0h+var_170], cl
0x18005f963  movups  [rbp+0A0h+var_120], xmm0
0x18005f967  movups  xmmword ptr [rsp+1A0h+Uuid.Data1], xmm1
0x18005f96c  test    rax, rax
0x18005f96f  jz      short loc_18005F97F
0x18005f971  mov     rcx, rax; Sid
0x18005f974  call    cs:__imp_RtlLengthSid
0x18005f97a  mov     r15d, eax
0x18005f97d  jmp     short loc_18005F982
0x18005f97f  xor     r15d, r15d
0x18005f982  test    rbx, rbx
0x18005f985  jz      short loc_18005F996
0x18005f987  mov     rcx, rbx; Sid
0x18005f98a  call    cs:__imp_RtlLengthSid
0x18005f990  mov     dword ptr [rsp+1A0h+var_168], eax
0x18005f994  jmp     short loc_18005F99E
0x18005f996  mov     dword ptr [rsp+1A0h+var_168], 0
0x18005f99e  mov     rax, [rbp+0A0h+arg_20]
0x18005f9a5  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18005f9ac  mov     [rsp+1A0h+arg_10], rsi
0x18005f9b4  mov     r12d, 1
0x18005f9ba  mov     [rsp+1A0h+var_30], rdi
0x18005f9c2  test    rax, rax
0x18005f9c5  jnz     short loc_18005F9F7
0x18005f9c7  lea     rcx, [rsp+1A0h+Uuid]; Uuid
0x18005f9cc  call    cs:__imp_UuidCreate
0x18005f9d2  test    eax, eax
0x18005f9d4  jz      short loc_18005F9FF
0x18005f9d6  cmp     eax, 720h
0x18005f9db  jz      short loc_18005F9FF
0x18005f9dd  xor     r10d, r10d
0x18005f9e0  mov     r14d, 0C0000083h
0x18005f9e6  mov     esi, r10d
0x18005f9e9  xor     r9b, r9b
0x18005f9ec  mov     r15d, 7D0h
0x18005f9f2  jmp     loc_18005FE94
0x18005f9f7  movups  xmm0, xmmword ptr [rax]
0x18005f9fa  movups  xmmword ptr [rsp+1A0h+Uuid.Data1], xmm0
0x18005f9ff  mov     ebx, dword ptr [rbp+0A0h+Size]
0x18005fa05  xor     edx, edx; Flags
0x18005fa07  mov     rcx, cs:BipHeap; HeapHandle
0x18005fa0e  lea     eax, [rbx+31Ch]
0x18005fa14  mov     r8d, eax; Size
0x18005fa17  mov     edi, eax
0x18005fa19  call    cs:__imp_RtlAllocateHeap
0x18005fa1f  mov     rsi, rax
0x18005fa22  test    rax, rax
0x18005fa25  jnz     short loc_18005FA3B
0x18005fa27  mov     r14d, 0C0000017h
0x18005fa2d  mov     r15d, 3E8h
0x18005fa33  xor     r9b, r9b
0x18005fa36  jmp     loc_18005FE91
0x18005fa3b  mov     r8, rdi; Size
0x18005fa3e  xor     edx, edx; Val
0x18005fa40  mov     rcx, rsi; void *
0x18005fa43  call    memset_0
0x18005fa48  xor     eax, eax
0x18005fa4a  lea     rcx, [rsi+248h]
0x18005fa51  xorps   xmm0, xmm0
0x18005fa54  movups  xmmword ptr [rsi], xmm0
0x18005fa57  movups  xmmword ptr [rsi+10h], xmm0
0x18005fa5b  movups  xmmword ptr [rsi+20h], xmm0
0x18005fa5f  mov     [rsi+30h], rax
0x18005fa63  mov     eax, dword ptr [rsp+1A0h+var_168+4]
0x18005fa67  mov     [rsi+1Ch], r12d
0x18005fa6b  movups  xmm0, xmmword ptr [rsp+1A0h+Uuid.Data1]
0x18005fa70  mov     [rsi+18h], eax
0x18005fa73  mov     rax, [rsp+1A0h+var_158]
0x18005fa78  movups  xmmword ptr [rsi+20h], xmm0
0x18005fa7c  mov     [rsi+30h], r12d
0x18005fa80  movups  xmm0, xmmword ptr [rax]
0x18005fa83  lea     rax, [rsi+38h]
0x18005fa87  movups  xmmword ptr [rsi+80h], xmm0
0x18005fa8e  mov     [rax+8], rax
0x18005fa92  mov     [rax], rax
0x18005fa95  lea     rax, [rsi+48h]
0x18005fa99  mov     [rax+8], rax
0x18005fa9d  mov     [rax], rax
0x18005faa0  xor     eax, eax
0x18005faa2  mov     [rsi+78h], rax
0x18005faa6  mov     [rsi+2ECh], eax
0x18005faac  call    BipTriggerSettingsInitialize
0x18005fab1  test    ebx, ebx
0x18005fab3  jz      short loc_18005FACD
0x18005fab5  mov     r8, rbx; Size
0x18005fab8  mov     [rsi+318h], ebx
0x18005fabe  lea     rcx, [rsi+31Ch]; void *
0x18005fac5  mov     rdx, r14; Src
0x18005fac8  call    memcpy_0
0x18005facd  mov     rdi, [rbp+0A0h+arg_28]
0x18005fad4  lea     rcx, [rsi+0C0h]; void *
0x18005fadb  test    rdi, rdi
0x18005fade  jz      short loc_18005FB4A
0x18005fae0  mov     rax, rdi
0x18005fae3  mov     edx, 3
0x18005fae8  nop     dword ptr [rax+rax+00000000h]
0x18005faf0  lea     rcx, [rcx+80h]
0x18005faf7  movups  xmm0, xmmword ptr [rax]
0x18005fafa  lea     rax, [rax+80h]
0x18005fb01  movups  xmmword ptr [rcx-80h], xmm0
0x18005fb05  movups  xmm1, xmmword ptr [rax-70h]
0x18005fb09  movups  xmmword ptr [rcx-70h], xmm1
0x18005fb0d  movups  xmm0, xmmword ptr [rax-60h]
0x18005fb11  movups  xmmword ptr [rcx-60h], xmm0
0x18005fb15  movups  xmm1, xmmword ptr [rax-50h]
0x18005fb19  movups  xmmword ptr [rcx-50h], xmm1
0x18005fb1d  movups  xmm0, xmmword ptr [rax-40h]
0x18005fb21  movups  xmmword ptr [rcx-40h], xmm0
0x18005fb25  movups  xmm1, xmmword ptr [rax-30h]
0x18005fb29  movups  xmmword ptr [rcx-30h], xmm1
0x18005fb2d  movups  xmm0, xmmword ptr [rax-20h]
0x18005fb31  movups  xmmword ptr [rcx-20h], xmm0
0x18005fb35  movups  xmm1, xmmword ptr [rax-10h]
0x18005fb39  movups  xmmword ptr [rcx-10h], xmm1
0x18005fb3d  sub     rdx, r12
0x18005fb40  jnz     short loc_18005FAF0
0x18005fb42  movzx   eax, word ptr [rax]
0x18005fb45  mov     [rcx], ax
0x18005fb48  jmp     short loc_18005FB57
0x18005fb4a  xor     edx, edx; Val
0x18005fb4c  mov     r8d, 182h; Size
0x18005fb52  call    memset_0
0x18005fb57  mov     r14, [rsp+1A0h+var_160]
0x18005fb5c  test    r14, r14
0x18005fb5f  jz      short loc_18005FBAC
0x18005fb61  mov     rcx, cs:BipHeap; HeapHandle
0x18005fb68  xor     edx, edx; Flags
0x18005fb6a  mov     r8d, r15d; Size
0x18005fb6d  mov     ebx, r15d
0x18005fb70  call    cs:__imp_RtlAllocateHeap
0x18005fb76  mov     [rsi+0A8h], rax
0x18005fb7d  test    rax, rax
0x18005fb80  jnz     short loc_18005FB99
0x18005fb82  xor     r9b, r9b
0x18005fb85  mov     r14d, 0C0000017h
0x18005fb8b  xor     r10d, r10d
0x18005fb8e  mov     r15d, 0BB8h
0x18005fb94  jmp     loc_18005FE9B
0x18005fb99  mov     r8, rbx; Size
0x18005fb9c  mov     rdx, r14; Src
0x18005fb9f  mov     rcx, rax; void *
0x18005fba2  call    memcpy_0
0x18005fba7  xor     r15d, r15d
0x18005fbaa  jmp     short loc_18005FBB6
0x18005fbac  xor     r15d, r15d
0x18005fbaf  mov     [rsi+0A8h], r15
0x18005fbb6  mov     r14, [rsp+1A0h+var_150]
0x18005fbbb  test    r14, r14
0x18005fbbe  jz      short loc_18005FC09
0x18005fbc0  mov     ebx, dword ptr [rsp+1A0h+var_168]
0x18005fbc4  xor     edx, edx; Flags
0x18005fbc6  mov     rcx, cs:BipHeap; HeapHandle
0x18005fbcd  mov     r8d, ebx; Size
0x18005fbd0  call    cs:__imp_RtlAllocateHeap
0x18005fbd6  mov     [rsi+0B0h], rax
0x18005fbdd  test    rax, rax
0x18005fbe0  jnz     short loc_18005FBF9
0x18005fbe2  xor     r9b, r9b
0x18005fbe5  mov     r14d, 0C0000017h
0x18005fbeb  xor     r10d, r10d
0x18005fbee  mov     r15d, 0FA0h
0x18005fbf4  jmp     loc_18005FE9B
0x18005fbf9  mov     r8, rbx; Size
0x18005fbfc  mov     rdx, r14; Src
0x18005fbff  mov     rcx, rax; void *
0x18005fc02  call    memcpy_0
0x18005fc07  jmp     short loc_18005FC10
0x18005fc09  mov     [rsi+0B0h], r15
0x18005fc10  lea     rcx, [rsi+0A0h]
0x18005fc17  xor     r9d, r9d
0x18005fc1a  mov     r8, rsi
0x18005fc1d  lea     rdx, BipCreateBrokerEventCallback
0x18005fc24  call    cs:__imp_TpAllocWork
0x18005fc2a  mov     ebx, [rsp+1A0h+var_16C]
0x18005fc2e  mov     r14d, eax
0x18005fc31  test    eax, eax
0x18005fc33  jns     short loc_18005FC46
0x18005fc35  xor     r9b, r9b
0x18005fc38  mov     r15d, 1194h
0x18005fc3e  xor     r10d, r10d
0x18005fc41  jmp     loc_18005FE9F
0x18005fc46  mov     rcx, [rsp+1A0h+var_138]
0x18005fc4b  mov     r8, rsi
0x18005fc4e  mov     edx, ebx
0x18005fc50  call    BipCreateBrokerEvent
0x18005fc55  mov     r14d, eax
0x18005fc58  test    eax, eax
0x18005fc5a  jns     short loc_18005FC84
0x18005fc5c  test    r12b, bl
0x18005fc5f  jz      short loc_18005FC73
0x18005fc61  mov     r15d, 1770h
0x18005fc67  movzx   r9d, r12b
0x18005fc6b  xor     r10d, r10d
0x18005fc6e  jmp     loc_18005FE9F
0x18005fc73  xor     r9b, r9b
0x18005fc76  mov     r15d, 1388h
0x18005fc7c  xor     r10d, r10d
0x18005fc7f  jmp     loc_18005FE9F
0x18005fc84  test    bl, 4
0x18005fc87  jnz     short loc_18005FCB3
0x18005fc89  mov     eax, [rbp+0A0h+arg_40]
0x18005fc8f  lea     r8, [rsi+248h]
0x18005fc96  mov     edx, eax
0x18005fc98  mov     [rsi+244h], eax
0x18005fc9e  lea     rcx, qword_1800C3F68
0x18005fca5  call    BipTriggerSettingsTableFindById
0x18005fcaa  or      dword ptr [rsi+18h], 20000000h
0x18005fcb1  jmp     short loc_18005FCBA
0x18005fcb3  mov     [rsi+244h], r15d
0x18005fcba  call    BipAcquireGlobalLock
0x18005fcbf  cmp     word ptr [rsi+0C0h], 0
0x18005fcc7  jz      short loc_18005FCED
0x18005fcc9  cmp     qword ptr [rsi+0A8h], 0
0x18005fcd1  jz      short loc_18005FCED
0x18005fcd3  mov     rcx, rsi
0x18005fcd6  call    BipAddEventToPackage
0x18005fcdb  mov     r14d, eax
0x18005fcde  test    eax, eax
0x18005fce0  jns     short loc_18005FCED
0x18005fce2  mov     r15d, 1B58h
0x18005fce8  jmp     loc_18005FE36
0x18005fced  test    byte ptr [rsi+18h], 2
0x18005fcf1  jnz     short loc_18005FD23
0x18005fcf3  mov     eax, ebx
0x18005fcf5  and     al, 9
0x18005fcf7  cmp     al, r12b
0x18005fcfa  jz      short loc_18005FD23
0x18005fcfc  mov     edx, ebx
0x18005fcfe  mov     rcx, rsi
0x18005fd01  shr     edx, 4
0x18005fd04  and     edx, r12d
0x18005fd07  call    BipSaveEventInStore
0x18005fd0c  mov     r14d, eax
0x18005fd0f  test    eax, eax
0x18005fd11  jns     short loc_18005FD1E
0x18005fd13  mov     r15d, 1F40h
0x18005fd19  jmp     loc_18005FE36
0x18005fd1e  mov     [rsp+1A0h+var_170], r12b
0x18005fd23  mov     rdx, rsi
0x18005fd26  lea     rcx, qword_1800C4368
0x18005fd2d  call    BipAddObjectToTable
0x18005fd32  mov     r14d, eax
0x18005fd35  test    eax, eax
0x18005fd37  js      loc_18005FE30
0x18005fd3d  lock inc dword ptr [rsi+1Ch]
0x18005fd41  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005fd46  mov     ecx, cs:dword_1800C3CB0
0x18005fd4c  mov     edx, cs:_tls_index
0x18005fd52  mov     rax, gs:58h
0x18005fd5b  shl     r12d, cl
0x18005fd5e  lea     rcx, BipGlobalLock
0x18005fd65  not     r12d
0x18005fd68  mov     cs:dword_1800C3CB4, r15d
0x18005fd6f  mov     rbx, [rax+rdx*8]
0x18005fd73  mov     eax, 8
0x18005fd78  and     [rax+rbx], r12d
0x18005fd7c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005fd82  mov     ecx, 4
0x18005fd87  and     [rcx+rbx], r12d
0x18005fd8b  lock xadd [rsi+1Ch], r13d
0x18005fd91  cmp     r13d, 1
0x18005fd95  jnz     loc_18005FE1B
0x18005fd9b  mov     ecx, [rsi+30h]
0x18005fd9e  sub     ecx, r13d
0x18005fda1  jz      short loc_18005FE0C
0x18005fda3  sub     ecx, r13d
0x18005fda6  jz      short loc_18005FDEF
0x18005fda8  xor     edx, edx; Flags
0x18005fdaa  mov     r8, rsi; P
0x18005fdad  cmp     ecx, r13d
0x18005fdb0  mov     rcx, cs:BipHeap; HeapHandle
0x18005fdb7  jz      short loc_18005FDD4
0x18005fdb9  call    cs:__imp_RtlFreeHeap
0x18005fdbf  mov     rax, qword ptr [rsp+1A0h+EventDescriptor.Id]
0x18005fdc4  movups  xmm0, xmmword ptr [rsp+1A0h+Uuid.Data1]
  ... truncated ...
```
