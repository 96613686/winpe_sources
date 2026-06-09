# BipWorkItemCreate

- ea: `0x180008598`
- end: `0x180008f2f`
- name: `BipWorkItemCreate`
- size: `2455`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int64, __int64, __int64, int, PCUNICODE_STRING SourceString, __int64, char, __int64, size_t)`
- caller_count: `3`
- callee_count: `33`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009100`
- `0x18005df20`
- `0x18007fdf8`

## callees

- `0x1800022f4`
- `0x180005360`
- `0x180005670`
- `0x180007dcc`
- `0x180008598`
- `0x1800095b0`
- `0x18000d50c`
- `0x18000d7c0`
- `0x18000da50`
- `0x180010c5c`
- `0x180011e7c`
- `0x1800121b0`
- `0x1800124a0`
- `0x180015930`
- `0x1800247dc`
- `0x18002ba58`
- `0x180037a80`
- `0x18003986c`
- `0x18003e0a8`
- `0x180040b58`
- `0x180041384`
- `0x18004a5d0`
- `0x18004af00`
- `0x180053100`
- `0x180057ce0`
- `0x18005ac30`
- `0x18005ace4`
- `0x180064214`
- `0x18006d364`
- `0x18006dcec`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18000879c`
- `ntdll!RtlCopyUnicodeString` at `0x18000879c`
- `ntdll!RtlInitUnicodeString` at `0x1800087ad`
- `ntdll!RtlInitUnicodeString` at `0x180008aa4`
- `ntdll!RtlInitUnicodeString` at `0x1800087ad`
- `ntdll!RtlInitUnicodeString` at `0x180008aa4`
- `ntdll!RtlStringFromGUIDEx` at `0x180008992`
- `ntdll!RtlStringFromGUIDEx` at `0x180008992`
- `ntdll!RtlAllocateHeap` at `0x180008704`
- `ntdll!RtlAllocateHeap` at `0x180008704`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180008836`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180008863`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180008836`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180008863`
- `RPCRT4!UuidCreate` at `0x180008617`
- `RPCRT4!UuidCreate` at `0x180008617`

## pseudocode

```c
__int64 __fastcall BipWorkItemCreate(
        UUID *a1,
        __int64 a2,
        unsigned int a3,
        UUID *a4,
        unsigned int a5,
        __int128 *a6,
        __int64 a7,
        __int64 a8,
        unsigned int *a9,
        unsigned int a10,
        PCUNICODE_STRING SourceString,
        __int64 a12,
        char a13,
        void *a14,
        size_t a15)
{
  __int64 v16; // r12
  __int64 v17; // r14
  RPC_STATUS v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  char *v21; // rsi
  NTSTATUS AggregatedEvent; // ebx
  int v23; // edi
  int v24; // ebx
  unsigned int v25; // r14d
  int v26; // esi
  unsigned int v27; // r15d
  int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // ecx
  size_t v31; // rbx
  char *Heap; // rax
  int State; // eax
  unsigned int v34; // r12d
  __int64 v35; // rdx
  char IsDebugSupported; // al
  __int64 v37; // r15
  const void *v38; // rdi
  unsigned int v39; // ebx
  char *v40; // rdi
  __int64 v41; // r14
  int v42; // eax
  __int64 v43; // rax
  int v44; // eax
  char v45; // al
  __int128 v46; // xmm0
  _QWORD *v47; // rax
  void *v48; // r9
  NTSTATUS WnfStateName; // eax
  __int64 v50; // rbx
  char *v51; // rdi
  __int64 EntryPoint; // rax
  unsigned int v53; // ecx
  __int64 v54; // rbx
  char *v55; // rdi
  __int64 v56; // r8
  void *v57; // rdi
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  char *v61; // rcx
  unsigned __int64 v62; // rcx
  char v63; // r13
  __int64 v64; // rcx
  __int64 v65; // r8
  unsigned int i; // ebx
  __int64 v67; // rbx
  __int64 v68; // rdx
  unsigned int v69; // edi
  __int64 v70; // rbx
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r9
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v76; // rcx
  __int64 v77; // rdx
  unsigned int v79; // [rsp+40h] [rbp-91h]
  unsigned __int16 v80; // [rsp+58h] [rbp-79h]
  unsigned int v81; // [rsp+5Ch] [rbp-75h] BYREF
  unsigned int v82; // [rsp+60h] [rbp-71h] BYREF
  size_t Size; // [rsp+64h] [rbp-6Dh]
  unsigned int v84; // [rsp+6Ch] [rbp-65h]
  void *Src; // [rsp+70h] [rbp-61h] BYREF
  unsigned int v86; // [rsp+78h] [rbp-59h]
  __int64 v87; // [rsp+80h] [rbp-51h]
  __int64 v88; // [rsp+88h] [rbp-49h] BYREF
  UUID *v89; // [rsp+90h] [rbp-41h]
  UUID v90; // [rsp+A0h] [rbp-31h] BYREF
  UUID Uuid; // [rsp+B0h] [rbp-21h] BYREF

  v16 = (__int64)a6;
  v17 = a7;
  v87 = a8;
  v88 = a12;
  Src = a14;
  v79 = a2;
  v89 = a1;
  Uuid = 0;
  if ( a4 )
  {
    Uuid = *a4;
  }
  else
  {
    v18 = UuidCreate(&Uuid);
    v20 = 0;
    if ( v18 && v18 != 1824 )
    {
      v21 = 0;
      AggregatedEvent = -1073741693;
      v23 = 1280;
      goto LABEL_139;
    }
  }
  v24 = 0;
  v25 = 0;
  Size = 0;
  v26 = 0;
  v84 = 0;
  v80 = 0;
  if ( a5 )
  {
    if ( a5 != 1 )
    {
      if ( a5 == 2 )
        v80 = 78;
      else
        MicrosoftTelemetryAssertTriggeredNoArgs(a5 - 1, a2, 0);
    }
  }
  else
  {
    v24 = *((_DWORD *)a6 + 5);
    v26 = *((_QWORD *)a6 + 2);
    Size = *((_QWORD *)a6 + 2);
  }
  v27 = a10;
  v86 = 32 * a10 + 632;
  v81 = v86 + v80;
  v28 = v26 + v81 + 2;
  if ( !v26 )
    v28 = v81;
  v82 = v28;
  v29 = v28 + v24;
  v30 = v28 + v24 + 2;
  if ( !v24 )
    v30 = v29;
  if ( SourceString && SourceString->Length )
  {
    v25 = v30;
    v30 += SourceString->Length + 2;
  }
  if ( Src && (_DWORD)a15 )
  {
    v84 = v30;
    v30 += a15;
  }
  v31 = v30;
  Heap = (char *)RtlAllocateHeap(BipHeap, 0, v30);
  v21 = Heap;
  if ( !Heap )
  {
    AggregatedEvent = -1073741801;
    v23 = 0x2000;
LABEL_24:
    v17 = a7;
    goto LABEL_139;
  }
  memset_0(Heap, 0, v31);
  v90 = Uuid;
  BipWorkItemInitialize(a3, &v90, a5, a10, v21);
  State = BipWorkItemAllocateState((struct _BI_WORK_ITEM *)v21);
  v20 = 0;
  AggregatedEvent = State;
  if ( State < 0 )
  {
    v23 = 9472;
    goto LABEL_24;
  }
  v34 = 0;
  if ( SourceString && SourceString->Length )
  {
    *((_QWORD *)v21 + 49) = &v21[v25];
    *((_WORD *)v21 + 193) = SourceString->Length + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)v21 + 24, SourceString);
  }
  else
  {
    RtlInitUnicodeString((PUNICODE_STRING)v21 + 24, 0);
  }
  v17 = a7;
  _InterlockedIncrement((volatile signed __int32 *)(a7 + 28));
  *((_QWORD *)v21 + 9) = a7;
  v35 = 0x4000000;
  if ( (*(_DWORD *)(a7 + 24) & 0x200) == 0 )
  {
    v20 = 0;
    goto LABEL_35;
  }
  IsDebugSupported = BipUtilActTypeIsDebugSupported(*((unsigned int *)v21 + 100));
  v20 = 0;
  if ( !IsDebugSupported )
LABEL_35:
    *((_DWORD *)v21 + 6) |= v35;
  if ( (*(_BYTE *)(a7 + 24) & 8) != 0 )
    *((_DWORD *)v21 + 6) |= 0x100u;
  if ( ((unsigned int)v35 & *(_DWORD *)(a7 + 24)) != 0 )
    *((_DWORD *)v21 + 6) |= 0x800u;
  if ( a10 )
  {
    while ( 1 )
    {
      v37 = 2LL * v34;
      v38 = *(const void **)(v87 + 16LL * v34);
      if ( !v38 )
      {
        v23 = 12288;
        goto LABEL_59;
      }
      if ( RtlCompareMemory(*(const void **)(v87 + 16LL * v34), (const void *)(a7 + 32), 0x10u) == 16 )
      {
        v23 = 0x4000;
        goto LABEL_59;
      }
      v39 = 0;
      if ( v34 )
      {
        while ( RtlCompareMemory(*(const void **)(v87 + 16LL * v39), v38, 0x10u) != 16 )
        {
          if ( ++v39 >= v34 )
            goto LABEL_46;
        }
        v23 = 20480;
        goto LABEL_59;
      }
LABEL_46:
      v40 = &v21[32 * v34];
      v41 = v87;
      v42 = BipLookupEventByGuid(*(void **)(v87 + 16LL * v34));
      v20 = 0;
      AggregatedEvent = v42;
      if ( v42 < 0 )
      {
        v23 = 24576;
LABEL_60:
        v17 = a7;
        v16 = (__int64)a6;
LABEL_139:
        v63 = v79;
LABEL_140:
        if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 0x200000000003LL, v20) )
        {
          v88 = 0x1000000;
          Src = (void *)(v17 + 192);
          v82 = v23;
          v81 = AggregatedEvent;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            v19,
            (__int64)word_1800B3252,
            v74,
            v75,
            (__int64 **)&Src,
            (__int64)&v81,
            (__int64)&v82,
            (__int64)&v88);
        }
        if ( v21 )
        {
          BipAcquireGlobalLock(v19);
          if ( (v63 & 1) != 0 )
            *((_DWORD *)v21 + 6) |= 2u;
          if ( a5 == 1 && *(_QWORD *)(v16 + 8) )
            *((_QWORD *)v21 + 52) = 0;
          BipWorkItemBeginDeletion(v21, 0);
          *((_DWORD *)v21 + 6) |= 0x80000000;
          BipLockWatchdogContextDisarmWatchdog(v76);
          LOBYTE(v77) = 1;
          BipSyncReleaseLock(&BipGlobalLock, v77);
          goto LABEL_152;
        }
        return (unsigned int)AggregatedEvent;
      }
      v43 = *((_QWORD *)v40 + 79);
      *((_DWORD *)v40 + 165) = v34;
      v19 = *(unsigned int *)(v43 + 24);
      if ( (v19 & 1) == 0 )
        break;
      v44 = *((_DWORD *)v21 + 6);
      v35 = 2;
      if ( (v44 & 2) == 0 && (v19 & 2) != 0 )
      {
        v23 = 0x8000;
LABEL_59:
        AggregatedEvent = -1073741811;
        goto LABEL_60;
      }
      ++v34;
      if ( (v19 & 8) != 0 )
        *((_DWORD *)v21 + 6) = v44 | 0x100;
      v45 = *(_BYTE *)(v41 + 8 * v37 + 8);
      v27 = a10;
      v40[656] = v45;
      if ( v34 >= a10 )
      {
        v17 = a7;
        goto LABEL_54;
      }
    }
    v23 = 28672;
    goto LABEL_59;
  }
LABEL_54:
  if ( a5 )
  {
    if ( a5 == 1 )
    {
      v16 = (__int64)a6;
      v47 = (_QWORD *)*((_QWORD *)a6 + 1);
      if ( v47 )
      {
        *((_QWORD *)v21 + 52) = *v47;
      }
      else
      {
        v48 = *(void **)(v17 + 168);
        if ( !v48 )
          v48 = (void *)*((_QWORD *)a6 + 2);
        WnfStateName = BipCreateWnfStateName((__int64)(v21 + 416), (a3 & 2) == 0, 0, v48, 0);
        v20 = 0;
        AggregatedEvent = WnfStateName;
        if ( WnfStateName < 0 )
        {
          v23 = 4096;
          goto LABEL_139;
        }
      }
    }
    else if ( a5 == 2 )
    {
      v16 = (__int64)a6;
      v46 = *a6;
      *((_QWORD *)v21 + 55) = &v21[v86];
      *((_OWORD *)v21 + 26) = v46;
      *((_WORD *)v21 + 217) = v80;
      RtlStringFromGUIDEx(a6, v21 + 432, 0);
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(a5 - 1, v35, 0);
      v16 = (__int64)a6;
    }
  }
  else
  {
    v16 = (__int64)a6;
    v50 = (unsigned int)Size;
    v51 = &v21[v81];
    memcpy_0(v51, *(const void **)a6, (unsigned int)Size);
    *(_WORD *)&v51[2 * ((unsigned __int64)(unsigned int)Size >> 1)] = 0;
    EntryPoint = BipWorkItemGetEntryPoint(v21);
    BipConstructUnicodeStringSafe(EntryPoint, v51, (unsigned __int64)(v50 + 2) >> 1);
    v53 = HIDWORD(Size);
    *((_DWORD *)v21 + 112) = 4;
    *((_QWORD *)v21 + 11) = 0;
    if ( v53 )
    {
      v54 = v53;
      v55 = &v21[v82];
      memcpy_0(v55, *((const void **)a6 + 1), v53);
      *(_WORD *)&v55[2 * ((unsigned __int64)(unsigned int)v54 >> 1)] = 0;
      BipConstructUnicodeStringSafe(v21 + 432, v55, (unsigned __int64)(v54 + 2) >> 1);
    }
    else
    {
      RtlInitUnicodeString((PUNICODE_STRING)v21 + 27, 0);
    }
  }
  if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(a5) )
  {
    AggregatedEvent = BipCreateWnfStateName((__int64)(v21 + 592), 0, 1, 0, v56);
    if ( AggregatedEvent < 0 )
    {
      v23 = 36864;
      goto LABEL_24;
    }
  }
  v57 = Src;
  if ( Src && (_DWORD)a15 )
  {
    if ( !(unsigned __int8)BipUtilActTypeIsDebugSupported(a5) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v59, v58, v60);
    v61 = &v21[v84];
    *((_DWORD *)v21 + 152) = a15;
    *((_QWORD *)v21 + 77) = v61;
    memcpy_0(v61, v57, (unsigned int)a15);
  }
  BipAcquireGlobalLock(v19);
  v17 = a7;
  if ( *(int *)(a7 + 24) < 0 )
  {
    v23 = 0x10000;
LABEL_86:
    AggregatedEvent = -1073741275;
LABEL_87:
    v63 = v79;
LABEL_130:
    BipLockWatchdogContextDisarmWatchdog((struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)v62);
    LOBYTE(v72) = 1;
    BipSyncReleaseLock(&BipGlobalLock, v72);
    goto LABEL_140;
  }
  v62 = 0;
  if ( v27 )
  {
    while ( *(int *)(*(_QWORD *)&v21[32 * (unsigned int)v62 + 632] + 24LL) >= 0 )
    {
      v62 = (unsigned int)(v62 + 1);
      if ( (unsigned int)v62 >= v27 )
        goto LABEL_91;
    }
    v23 = 69632;
    goto LABEL_86;
  }
LABEL_91:
  if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(*((unsigned int *)v21 + 100)) )
  {
    AggregatedEvent = BipAddWorkItemToPackage(v21);
    if ( AggregatedEvent < 0 )
    {
      v23 = 73728;
      goto LABEL_87;
    }
  }
  if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(*((unsigned int *)v21 + 100)) )
  {
    AggregatedEvent = BipAddPackageApplicationForWorkItem(v21, v88);
    if ( AggregatedEvent < 0 )
    {
      v23 = 77824;
      goto LABEL_87;
    }
  }
  if ( (unsigned __int8)BipUtilActTypeIsResourceTimerSupported(a5) )
    *((_DWORD *)v21 + 112) = *(_DWORD *)(v16 + 24);
  if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(a5) )
  {
    v64 = *((_QWORD *)v21 + 10);
    if ( (a13 & 1) != 0 )
      BipSetPackageFlags(v64);
    else
      BipClearPackageFlags(v64);
    if ( (a13 & 2) != 0 )
      BipSetPackageFlags(*((_QWORD *)v21 + 10));
  }
  v63 = v79;
  if ( (v21[24] & 2) == 0 && (v79 & 9) != 1 )
  {
    AggregatedEvent = BipSaveWorkItemInStore(v21);
    if ( AggregatedEvent < 0 )
    {
      v23 = 81920;
      goto LABEL_130;
    }
  }
  BipAddWorkItemToEventUnsafe(v21 + 96, a7, 0);
  for ( i = 0; i < v27; ++i )
  {
    LOBYTE(v65) = 1;
    BipAddWorkItemToEventUnsafe(&v21[32 * i + 640], *(_QWORD *)&v21[32 * i + 632], v65);
  }
  if ( a9 )
  {
    v67 = *((_QWORD *)v21 + 9);
    if ( (*(_DWORD *)(v67 + 24) & 0x20000000) == 0 )
    {
      v68 = *a9;
      *(_DWORD *)(v67 + 580) = v68;
      BipTriggerSettingsTableFindById(&qword_1800C3F68, v68, v67 + 584);
      *(_DWORD *)(v67 + 24) |= 0x20000000u;
      if ( (*(_BYTE *)(v67 + 24) & 2) == 0 )
        BipUpdateEventTypeInStore(v67);
    }
    v69 = 0;
    if ( v27 )
    {
      do
      {
        v70 = *(_QWORD *)&v21[32 * v69 + 632];
        if ( (*(_DWORD *)(v70 + 24) & 0x20000000) == 0 )
        {
          v71 = a9[v69 + 1];
          *(_DWORD *)(v70 + 580) = v71;
          BipTriggerSettingsTableFindById(&qword_1800C3F68, v71, v70 + 584);
          *(_DWORD *)(v70 + 24) |= 0x20000000u;
          if ( (*(_BYTE *)(v70 + 24) & 2) == 0 )
            BipUpdateEventTypeInStore(v70);
        }
        ++v69;
      }
      while ( v69 < v27 );
      v16 = (__int64)a6;
    }
  }
  v17 = a7;
  v62 = a5;
  if ( ((unsigned __int8)(1 << a5) & *(_BYTE *)(a7 + 736)) == 0 )
  {
    AggregatedEvent = -1073741637;
    v23 = 83200;
    goto LABEL_130;
  }
  if ( (v21[24] & 1) != 0
    && (unsigned __int8)BipUtilActTypeIsHostedInWinMainApp(*((unsigned int *)v21 + 100))
    && *(char *)(a7 + 588) >= 0 )
  {
    AggregatedEvent = -1073741637;
    v23 = 84480;
    goto LABEL_130;
  }
  ++*((_DWORD *)v21 + 7);
  AggregatedEvent = BipAddObjectToTable(&qword_1800C4388, v21);
  if ( AggregatedEvent < 0 )
  {
    --*((_DWORD *)v21 + 7);
    v23 = 90112;
    goto LABEL_130;
  }
  if ( (v79 & 1) == 0 && (unsigned __int8)BipUtilActTypeIsDebugSupported(*((unsigned int *)v21 + 100)) )
  {
    if ( (*(_BYTE *)(*((_QWORD *)v21 + 10) + 604LL) & 0x20) != 0 )
      BipWorkItemQueueBackgroundAccessStateWorker(v21, 1);
    else
      BipPackageBackgroundAccessQueueQueryState();
  }
  BipLockWatchdogContextDisarmWatchdog((struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)v62);
  LOBYTE(v73) = 1;
  BipSyncReleaseLock(&BipGlobalLock, v73);
  AggregatedEvent = BipWorkItemCreateAggregatedEvent(v21, v79);
  if ( AggregatedEvent < 0 )
  {
    v23 = 86016;
    goto LABEL_139;
  }
  *v89 = Uuid;
  if ( a5 == 1 )
    **(_QWORD **)v16 = *((_QWORD *)v21 + 52);
LABEL_152:
  BipWorkItemDereference(v21);
  return (unsigned int)AggregatedEvent;
}

```

## disassembly

```asm
0x180008598  push    rbp
0x18000859a  push    rbx
0x18000859b  push    rsi
0x18000859c  push    rdi
0x18000859d  push    r12
0x18000859f  push    r13
0x1800085a1  push    r14
0x1800085a3  push    r15
0x1800085a5  lea     rbp, [rsp-7]
0x1800085aa  sub     rsp, 0D8h
0x1800085b1  mov     rax, cs:__security_cookie
0x1800085b8  xor     rax, rsp
0x1800085bb  mov     [rbp+3Fh+var_50], rax
0x1800085bf  mov     rax, [rbp+3Fh+arg_38]
0x1800085c6  mov     r13d, r8d
0x1800085c9  mov     r12, [rbp+3Fh+arg_28]
0x1800085cd  xor     r8d, r8d
0x1800085d0  mov     r14, [rbp+3Fh+arg_30]
0x1800085d4  xorps   xmm0, xmm0
0x1800085d7  mov     rdi, [rbp+3Fh+SourceString]
0x1800085de  mov     [rbp+3Fh+var_90], rax
0x1800085e2  mov     rax, [rbp+3Fh+arg_58]
0x1800085e9  mov     [rbp+3Fh+var_88], rax
0x1800085ed  mov     rax, [rbp+3Fh+arg_68]
0x1800085f4  mov     [rbp+3Fh+Src], rax
0x1800085f8  mov     [rsp+110h+var_D0], edx
0x1800085fc  mov     [rbp+3Fh+var_80], rcx
0x180008600  mov     [rsp+110h+var_C0], r12
0x180008605  mov     [rsp+110h+var_C8], r14
0x18000860a  movups  xmmword ptr [rbp+3Fh+Uuid.Data1], xmm0
0x18000860e  test    r9, r9
0x180008611  jnz     short loc_18000863D
0x180008613  lea     rcx, [rbp+3Fh+Uuid]; Uuid
0x180008617  call    cs:__imp_UuidCreate
0x18000861d  xor     r8d, r8d
0x180008620  test    eax, eax
0x180008622  jz      short loc_180008646
0x180008624  cmp     eax, 720h
0x180008629  jz      short loc_180008646
0x18000862b  mov     esi, r8d
0x18000862e  mov     ebx, 0C0000083h
0x180008633  mov     edi, 500h
0x180008638  jmp     loc_180008E24
0x18000863d  movups  xmm0, xmmword ptr [r9]
0x180008641  movdqu  xmmword ptr [rbp+3Fh+Uuid.Data1], xmm0
0x180008646  mov     ecx, [rbp+3Fh+arg_20]
0x180008649  mov     ebx, r8d
0x18000864c  mov     dword ptr [rbp+3Fh+Size+4], ebx
0x18000864f  mov     r14d, r8d
0x180008652  mov     dword ptr [rbp+3Fh+Size], r8d
0x180008656  mov     esi, r8d
0x180008659  mov     [rbp+3Fh+var_A4], r8d
0x18000865d  mov     [rbp+3Fh+var_B8], r8d
0x180008661  test    ecx, ecx
0x180008663  jz      short loc_180008684
0x180008665  sub     ecx, 1
0x180008668  jz      short loc_180008694
0x18000866a  cmp     ecx, 1
0x18000866d  jz      short loc_180008679
0x18000866f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008674  xor     r8d, r8d
0x180008677  jmp     short loc_180008694
0x180008679  mov     eax, 4Eh ; 'N'
0x18000867e  mov     word ptr [rbp+3Fh+var_B8], ax
0x180008682  jmp     short loc_180008694
0x180008684  mov     ebx, [r12+14h]
0x180008689  mov     esi, [r12+10h]
0x18000868e  mov     dword ptr [rbp+3Fh+Size+4], ebx
0x180008691  mov     dword ptr [rbp+3Fh+Size], esi
0x180008694  mov     r15d, [rbp+3Fh+arg_48]
0x18000869b  mov     ecx, r15d
0x18000869e  movzx   eax, word ptr [rbp+3Fh+var_B8]
0x1800086a2  shl     ecx, 5
0x1800086a5  add     ecx, 278h
0x1800086ab  add     eax, ecx
0x1800086ad  mov     [rbp+3Fh+var_98], ecx
0x1800086b0  mov     [rbp+3Fh+var_B4], eax
0x1800086b3  add     eax, esi
0x1800086b5  test    esi, esi
0x1800086b7  lea     ecx, [rax+2]
0x1800086ba  cmovz   ecx, eax
0x1800086bd  test    ebx, ebx
0x1800086bf  mov     [rbp+3Fh+var_B0], ecx
0x1800086c2  lea     eax, [rcx+rbx]
0x1800086c5  lea     ecx, [rax+2]
0x1800086c8  cmovz   ecx, eax
0x1800086cb  test    rdi, rdi
0x1800086ce  jz      short loc_1800086E1
0x1800086d0  cmp     [rdi], r8w
0x1800086d4  jz      short loc_1800086E1
0x1800086d6  movzx   eax, word ptr [rdi]
0x1800086d9  mov     r14d, ecx
0x1800086dc  add     eax, 2
0x1800086df  add     ecx, eax
0x1800086e1  cmp     [rbp+3Fh+Src], r8
0x1800086e5  jz      short loc_1800086F6
0x1800086e7  mov     eax, dword ptr [rbp+3Fh+arg_70]
0x1800086ed  test    eax, eax
0x1800086ef  jz      short loc_1800086F6
0x1800086f1  mov     [rbp+3Fh+var_A4], ecx
0x1800086f4  add     ecx, eax
0x1800086f6  mov     ebx, ecx
0x1800086f8  xor     edx, edx; Flags
0x1800086fa  mov     r8d, ecx; Size
0x1800086fd  mov     rcx, cs:BipHeap; HeapHandle
0x180008704  call    cs:__imp_RtlAllocateHeap
0x18000870a  mov     rsi, rax
0x18000870d  test    rax, rax
0x180008710  jnz     short loc_180008726
0x180008712  mov     ebx, 0C0000017h
0x180008717  mov     edi, 2000h
0x18000871c  mov     r14, [rsp+110h+var_C8]
0x180008721  jmp     loc_180008E24
0x180008726  mov     r8, rbx; Size
0x180008729  xor     edx, edx; Val
0x18000872b  mov     rcx, rsi; void *
0x18000872e  call    memset_0
0x180008733  movaps  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x180008737  lea     rdx, [rbp+3Fh+var_70]
0x18000873b  mov     r8d, [rbp+3Fh+arg_20]
0x18000873f  mov     r9d, r15d
0x180008742  mov     ecx, r13d
0x180008745  movdqa  [rbp+3Fh+var_70], xmm0
0x18000874a  mov     [rsp+110h+var_F0], rsi
0x18000874f  call    ?BipWorkItemInitialize@@YAXKU_GUID@@W4_BI_WORK_ITEM_ACTIVATION_TYPE@@KPEAU_BI_WORK_ITEM@@@Z; BipWorkItemInitialize(ulong,_GUID,_BI_WORK_ITEM_ACTIVATION_TYPE,ulong,_BI_WORK_ITEM *)
0x180008754  mov     rcx, rsi; struct _BI_WORK_ITEM *
0x180008757  call    ?BipWorkItemAllocateState@@YAJPEAU_BI_WORK_ITEM@@@Z; BipWorkItemAllocateState(_BI_WORK_ITEM *)
0x18000875c  xor     r8d, r8d
0x18000875f  mov     ebx, eax
0x180008761  test    eax, eax
0x180008763  jns     short loc_18000876C
0x180008765  mov     edi, 2500h
0x18000876a  jmp     short loc_18000871C
0x18000876c  mov     r12d, r8d
0x18000876f  test    rdi, rdi
0x180008772  jz      short loc_1800087A4
0x180008774  cmp     [rdi], r8w
0x180008778  jz      short loc_1800087A4
0x18000877a  lea     rcx, [rsi+180h]; DestinationString
0x180008781  mov     eax, r14d
0x180008784  add     rax, rsi
0x180008787  mov     rdx, rdi; SourceString
0x18000878a  mov     [rcx+8], rax
0x18000878e  movzx   eax, word ptr [rdi]
0x180008791  add     ax, 2
0x180008795  mov     [rsi+182h], ax
0x18000879c  call    cs:__imp_RtlCopyUnicodeString
0x1800087a2  jmp     short loc_1800087B3
0x1800087a4  lea     rcx, [rsi+180h]; DestinationString
0x1800087ab  xor     edx, edx; SourceString
0x1800087ad  call    cs:__imp_RtlInitUnicodeString
0x1800087b3  mov     r14, [rsp+110h+var_C8]
0x1800087b8  lock inc dword ptr [r14+1Ch]
0x1800087bd  mov     [rsi+48h], r14
0x1800087c1  mov     edx, 4000000h
0x1800087c6  test    dword ptr [r14+18h], 200h
0x1800087ce  jz      short loc_1800087E4
0x1800087d0  mov     ecx, [rsi+190h]
0x1800087d6  call    BipUtilActTypeIsDebugSupported
0x1800087db  xor     r8d, r8d
0x1800087de  test    al, al
0x1800087e0  jz      short loc_1800087E7
0x1800087e2  jmp     short loc_1800087EA
0x1800087e4  xor     r8d, r8d
0x1800087e7  or      [rsi+18h], edx
0x1800087ea  test    byte ptr [r14+18h], 8
0x1800087ef  jz      short loc_1800087F6
0x1800087f1  bts     dword ptr [rsi+18h], 8
0x1800087f6  test    [r14+18h], edx
0x1800087fa  jz      short loc_180008801
0x1800087fc  bts     dword ptr [rsi+18h], 0Bh
0x180008801  test    r15d, r15d
0x180008804  jz      loc_1800088FB
0x18000880a  mov     rdi, [rbp+3Fh+var_90]
0x18000880e  mov     r15d, r12d
0x180008811  add     r15, r15
0x180008814  mov     r14d, r12d
0x180008817  mov     rdi, [rdi+r15*8]
0x18000881b  test    rdi, rdi
0x18000881e  jz      loc_180008958
0x180008824  mov     rdx, [rsp+110h+var_C8]
0x180008829  mov     r8d, 10h; Length
0x18000882f  add     rdx, 20h ; ' '; Source2
0x180008833  mov     rcx, rdi; Source1
0x180008836  call    cs:__imp_RtlCompareMemory
0x18000883c  cmp     rax, 10h
0x180008840  jz      loc_180008951
0x180008846  xor     ebx, ebx
0x180008848  test    r12d, r12d
0x18000884b  jz      short loc_18000887A
0x18000884d  mov     rax, [rbp+3Fh+var_90]
0x180008851  mov     r8d, 10h; Length
0x180008857  mov     ecx, ebx
0x180008859  mov     rdx, rdi; Source2
0x18000885c  add     rcx, rcx
0x18000885f  mov     rcx, [rax+rcx*8]; Source1
0x180008863  call    cs:__imp_RtlCompareMemory
0x180008869  cmp     rax, 10h
0x18000886d  jz      loc_180008923
0x180008873  inc     ebx
0x180008875  cmp     ebx, r12d
0x180008878  jb      short loc_18000884D
0x18000887a  shl     r14, 5
0x18000887e  lea     rdi, [r14+rsi]
0x180008882  mov     r14, [rbp+3Fh+var_90]
0x180008886  lea     rdx, [rdi+278h]
0x18000888d  mov     rcx, [r14+r15*8]; Source1
0x180008891  call    BipLookupEventByGuid
0x180008896  xor     r8d, r8d
0x180008899  mov     ebx, eax
0x18000889b  test    eax, eax
0x18000889d  js      loc_18000894A
0x1800088a3  mov     rax, [rdi+278h]
0x1800088aa  mov     [rdi+294h], r12d
0x1800088b1  mov     ecx, [rax+18h]
0x1800088b4  test    cl, 1
0x1800088b7  jz      loc_180008943
0x1800088bd  mov     eax, [rsi+18h]
0x1800088c0  lea     edx, [r8+2]
0x1800088c4  test    dl, al
0x1800088c6  jnz     short loc_1800088CC
0x1800088c8  test    dl, cl
0x1800088ca  jnz     short loc_18000893C
0x1800088cc  inc     r12d
0x1800088cf  test    cl, 8
0x1800088d2  jz      short loc_1800088DB
0x1800088d4  bts     eax, 8
0x1800088d8  mov     [rsi+18h], eax
0x1800088db  mov     al, [r14+r15*8+8]
0x1800088e0  mov     r15d, [rbp+3Fh+arg_48]
0x1800088e7  mov     [rdi+290h], al
0x1800088ed  cmp     r12d, r15d
0x1800088f0  jb      loc_18000880A
0x1800088f6  mov     r14, [rsp+110h+var_C8]
0x1800088fb  mov     ecx, [rbp+3Fh+arg_20]
0x1800088fe  test    ecx, ecx
0x180008900  jz      loc_180008A04
0x180008906  sub     ecx, 1
0x180008909  jz      loc_18000899D
0x18000890f  cmp     ecx, 1
0x180008912  jz      short loc_18000895F
0x180008914  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008919  mov     r12, [rsp+110h+var_C0]
0x18000891e  jmp     loc_180008AAA
0x180008923  mov     edi, 5000h
0x180008928  mov     ebx, 0C000000Dh
0x18000892d  mov     r14, [rsp+110h+var_C8]
0x180008932  mov     r12, [rsp+110h+var_C0]
0x180008937  jmp     loc_180008E24
0x18000893c  mov     edi, 8000h
0x180008941  jmp     short loc_180008928
0x180008943  mov     edi, 7000h
0x180008948  jmp     short loc_180008928
0x18000894a  mov     edi, 6000h
0x18000894f  jmp     short loc_18000892D
0x180008951  mov     edi, 4000h
0x180008956  jmp     short loc_180008928
0x180008958  mov     edi, 3000h
0x18000895d  jmp     short loc_180008928
0x18000895f  mov     r12, [rsp+110h+var_C0]
0x180008964  lea     rdx, [rsi+1B0h]
0x18000896b  mov     eax, [rbp+3Fh+var_98]
0x18000896e  xor     r8d, r8d
0x180008971  add     rax, rsi
0x180008974  mov     rcx, r12
0x180008977  movups  xmm0, xmmword ptr [r12]
0x18000897c  mov     [rdx+8], rax
0x180008980  mov     eax, [rbp+3Fh+var_B8]
0x180008983  movdqu  xmmword ptr [rsi+1A0h], xmm0
0x18000898b  mov     [rsi+1B2h], ax
0x180008992  call    cs:__imp_RtlStringFromGUIDEx
0x180008998  jmp     loc_180008AAA
0x18000899d  mov     r12, [rsp+110h+var_C0]
0x1800089a2  mov     rax, [r12+8]
0x1800089a7  test    rax, rax
0x1800089aa  jnz     short loc_1800089F5
0x1800089ac  mov     r9, [r14+0A8h]
0x1800089b3  test    r9, r9
0x1800089b6  jnz     short loc_1800089BD
0x1800089b8  mov     r9, [r12+10h]
0x1800089bd  shr     r13d, 1
0x1800089c0  lea     rcx, [rsi+1A0h]
0x1800089c7  mov     [rsp+110h+var_F0], r8
0x1800089cc  not     r13b
0x1800089cf  and     r13b, 1
0x1800089d3  xor     r8d, r8d
0x1800089d6  mov     dl, r13b
0x1800089d9  call    BipCreateWnfStateName
0x1800089de  xor     r8d, r8d
0x1800089e1  mov     ebx, eax
0x1800089e3  test    eax, eax
0x1800089e5  jns     loc_180008AAD
0x1800089eb  mov     edi, 1000h
0x1800089f0  jmp     loc_180008E24
0x1800089f5  mov     rax, [rax]
0x1800089f8  mov     [rsi+1A0h], rax
0x1800089ff  jmp     loc_180008AAD
0x180008a04  mov     r12, [rsp+110h+var_C0]
0x180008a09  mov     edi, [rbp+3Fh+var_B4]
0x180008a0c  mov     ebx, dword ptr [rbp+3Fh+Size]
  ... truncated ...
```
