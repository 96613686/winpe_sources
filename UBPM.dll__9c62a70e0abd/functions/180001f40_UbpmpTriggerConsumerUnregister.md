# UbpmpTriggerConsumerUnregister

- ea: `0x180001f40`
- end: `0x180002607`
- name: `UbpmpTriggerConsumerUnregister`
- size: `1735`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001dc0`
- `0x180001e80`
- `0x1800136b0`

## callees

- `0x180001f40`
- `0x1800053a0`
- `0x18000a230`
- `0x18000fea0`
- `0x18001af64`
- `0x18002702c`
- `0x180035184`
- `0x1800373c0`
- `0x1800378e8`
- `0x180040260`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002387`
- `ntdll!RtlFreeHeap` at `0x18000248c`
- `ntdll!RtlFreeHeap` at `0x180002387`
- `ntdll!RtlFreeHeap` at `0x18000248c`
- `ntdll!RtlNtStatusToDosError` at `0x180002431`
- `ntdll!RtlNtStatusToDosError` at `0x180002431`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800022ac`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800022ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800020e4`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800020e4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f8b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001fb2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800022bb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000231e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000239d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800023d8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001f8b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001fb2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800022bb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000231e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000239d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800023d8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001fdc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000203e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800020cc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800022e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002360`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800024a6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800025df`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001fdc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000203e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800020cc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800022e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002360`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800024a6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800025df`
- `ntdll!NtDeleteWnfStateName` at `0x18000240d`
- `ntdll!NtDeleteWnfStateName` at `0x18000240d`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002285`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002285`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002268`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002268`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800022c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000232a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800022c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000232a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180002308`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180002308`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800022f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800022f9`

## string_xrefs

- `0x1800024fd`: `delete`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerUnregister(__int64 a1, _DWORD *a2, unsigned int a3, char a4, char a5)
{
  __int64 v5; // r12
  _DWORD *v6; // r13
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  int v12; // edx
  __int64 v13; // rax
  bool v14; // r12
  _BYTE *v15; // rcx
  __int64 v16; // r15
  int v17; // eax
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v22; // eax
  struct _TP_CLEANUP_GROUP *v23; // rdi
  void *v24; // r8
  _QWORD *v25; // rdi
  NTSTATUS v26; // eax
  char v27; // al
  void *v28; // r8
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  const wchar_t *v31; // r10
  const wchar_t *v32; // r8
  int UserDataCount; // [rsp+20h] [rbp-A1h]
  bool v36; // [rsp+44h] [rbp-7Dh]
  int v38; // [rsp+50h] [rbp-71h] BYREF
  __int64 v39; // [rsp+58h] [rbp-69h] BYREF
  _DWORD *v40; // [rsp+60h] [rbp-61h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-41h] BYREF
  __int16 *v43; // [rsp+90h] [rbp-31h]
  int v44; // [rsp+98h] [rbp-29h]
  int v45; // [rsp+9Ch] [rbp-25h]
  __int64 *v46; // [rsp+A0h] [rbp-21h]
  __int64 v47; // [rsp+A8h] [rbp-19h]
  __int64 *v48; // [rsp+B0h] [rbp-11h]
  int v49; // [rsp+B8h] [rbp-9h]
  int v50; // [rsp+BCh] [rbp-5h]
  int *v51; // [rsp+C0h] [rbp-1h]
  __int64 v52; // [rsp+C8h] [rbp+7h]
  __int64 v53; // [rsp+F0h] [rbp+2Fh]

  v6 = a2;
  v40 = a2;
  *a2 = 0;
  if ( !a5 )
  {
    RtlAcquireSRWLockExclusive(a1 + 48);
    *(_DWORD *)(a1 + 56) = GetCurrentThreadId();
  }
  RtlAcquireSRWLockExclusive(a1 + 72);
  *(_DWORD *)(a1 + 80) = GetCurrentThreadId();
  v8 = a1 + 72;
  v9 = *(_DWORD *)(a1 + 92);
  if ( (v9 & 1) != 0 )
  {
    *(_DWORD *)(a1 + 80) = 0;
    RtlReleaseSRWLockExclusive(v8);
    v10 = 4320;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 64;
LABEL_7:
      WPP_SF_Sd(
        v11[2],
        v12,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
        224);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 92) = v9 | 1;
    *(_DWORD *)(a1 + 80) = 0;
    RtlReleaseSRWLockExclusive(v8);
    if ( (*(_BYTE *)(a1 + 41) & 1) != 0 )
    {
      v13 = *(_QWORD *)(a1 + 24);
      v53 = v5;
      v14 = 0;
      v36 = 0;
      if ( *(_QWORD *)(v13 + 48) )
      {
        v15 = *(_BYTE **)(*(_QWORD *)(v13 + 40) + 32LL);
        if ( v15 )
        {
          v14 = (*v15 & 0x10) != 0;
          v36 = v14;
        }
      }
      v16 = a1 + 48;
      *(_DWORD *)(a1 + 56) = 0;
      RtlReleaseSRWLockExclusive(a1 + 48);
      UbpmUnsubscribeFromBrokerNotifications(a1);
      RtlAcquireSRWLockShared(a1 + 72);
      v17 = *(_DWORD *)(a1 + 88);
      if ( v17 )
      {
        do
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              66,
              (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
              *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
              v17);
          if ( (unsigned int)dword_18004F0F0 > 5
            && (qword_18004F100 & 1) != 0
            && (qword_18004F108 & 1) == qword_18004F108 )
          {
            v38 = *(_DWORD *)(a1 + 88);
            v18 = *(_QWORD *)(a1 + 24);
            v52 = 4;
            v19 = *(__int64 **)(v18 + 8);
            v51 = &v38;
            v39 = a1;
            if ( v19 )
            {
              v20 = -1;
              while ( *((_WORD *)v19 + ++v20) != 0 )
                ;
              v22 = 2 * v20 + 2;
            }
            else
            {
              v19 = &qword_1800439C0;
              v22 = 2;
            }
            v49 = v22;
            v48 = v19;
            v46 = &v39;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_18004F0F8;
            v50 = 0;
            v47 = 8;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 1;
            UserData.Size = *(unsigned __int16 *)off_18004F0F8;
            UserData.Reserved = 2;
            v43 = word_18004625A;
            v44 = 82;
            v45 = 1;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
          }
          SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 96), (PSRWLOCK)(a1 + 72), 0xFFFFFFFF, 1u);
          v17 = *(_DWORD *)(a1 + 88);
        }
        while ( v17 );
        v14 = v36;
        v16 = a1 + 48;
        v6 = v40;
      }
      RtlReleaseSRWLockShared(a1 + 72);
      RtlAcquireSRWLockExclusive(v16);
      GetCurrentThreadId();
      v23 = *(struct _TP_CLEANUP_GROUP **)(a1 + 112);
      *(_QWORD *)(a1 + 112) = 0;
      *(_DWORD *)(v16 + 8) = 0;
      RtlReleaseSRWLockExclusive(v16);
      CloseThreadpoolCleanupGroupMembers(v23, 1, 0);
      CloseThreadpoolCleanupGroup(v23);
      RtlAcquireSRWLockExclusive(a1 + 208);
      *(_DWORD *)(a1 + 216) = GetCurrentThreadId();
      LOBYTE(UserDataCount) = a4;
      UbpmTerminateActionsForConsumer(a1, 0, a3, 0, UserDataCount, 0);
      *(_DWORD *)(a1 + 216) = 0;
      RtlReleaseSRWLockExclusive(a1 + 208);
      v24 = *(void **)(a1 + 288);
      if ( v24 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
        *(_QWORD *)(a1 + 288) = 0;
      }
      RtlAcquireSRWLockExclusive(v16);
      *(_DWORD *)(v16 + 8) = GetCurrentThreadId();
      _InterlockedExchange64(
        (volatile __int64 *)(a1 + 64),
        _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), 0, 0)
      - *(unsigned int *)(*(_QWORD *)(a1 + 24) + 20LL));
      RtlAcquireSRWLockExclusive(a1 + 208);
      v25 = (_QWORD *)(a1 + 336);
      *(_DWORD *)(a1 + 216) = GetCurrentThreadId();
      if ( a1 != -336 && *(_DWORD *)v25 || *(_DWORD *)(a1 + 340) )
      {
        v26 = NtDeleteWnfStateName(a1 + 336);
        if ( v26 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v27 = RtlNtStatusToDosError(v26);
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
            v27);
        }
        *v25 = 0;
        *(_DWORD *)(a1 + 344) = 0;
      }
      v28 = *(void **)(a1 + 352);
      if ( v28 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
      *(_QWORD *)(a1 + 352) = 0;
      *(_DWORD *)(a1 + 216) = 0;
      RtlReleaseSRWLockExclusive(a1 + 208);
      v29 = *(_QWORD *)(a1 + 328);
      if ( v29 )
      {
        v30 = *(wchar_t **)(v29 + 64);
        if ( !v30 )
          v30 = *(wchar_t **)(*(_QWORD *)(a1 + 24) + 8LL);
        UbpmHardeningListRemove(v30);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v31 = L"delete";
        if ( !a3 )
          v31 = L"keep";
        v32 = L"orphan";
        if ( !a4 )
          v32 = L"terminate";
        WPP_SF_SiSSq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          (_DWORD)v32,
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
          _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), 0, 0),
          (__int64)v32,
          (__int64)v31,
          a1);
      }
      if ( !*(_BYTE *)(a1 + 104) && !_InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), 0, 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
            *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
        *v6 = 1;
      }
      if ( v14 )
        UbpmUtilsSubmitThreadPoolWork(UbpmMaintenanceEvaluateWakePolicy, 0, 1, 0, 0);
      v10 = 0;
    }
    else
    {
      v10 = 4320;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 65;
        goto LABEL_7;
      }
    }
  }
  if ( !a5 )
  {
    *(_DWORD *)(a1 + 56) = 0;
    RtlReleaseSRWLockExclusive(a1 + 48);
  }
  return v10;
}

```

## disassembly

```asm
0x180001f40  push    rbp
0x180001f42  push    rbx
0x180001f43  push    rdi
0x180001f44  push    r15
0x180001f46  lea     rbp, [rsp-37h]
0x180001f4b  sub     rsp, 0F8h
0x180001f52  mov     rax, cs:__security_cookie
0x180001f59  xor     rax, rsp
0x180001f5c  mov     [rbp+4Fh+var_40], rax
0x180001f60  xor     r15d, r15d
0x180001f63  mov     [rsp+110h+var_28], r13
0x180001f6b  mov     r13, rdx
0x180001f6e  mov     [rsp+110h+var_D0], r9b
0x180001f73  mov     rbx, rcx
0x180001f76  mov     [rbp+4Fh+var_C8], r8d
0x180001f7a  mov     [rbp+4Fh+var_B0], rdx
0x180001f7e  mov     [rdx], r15d
0x180001f81  cmp     [rbp+4Fh+arg_20], r15b
0x180001f85  jnz     short loc_180001FA6
0x180001f87  add     rcx, 30h ; '0'
0x180001f8b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001f92  nop     dword ptr [rax+rax+00h]
0x180001f97  call    cs:__imp_GetCurrentThreadId
0x180001f9e  nop     dword ptr [rax+rax+00h]
0x180001fa3  mov     [rbx+38h], eax
0x180001fa6  lea     rcx, [rbx+48h]
0x180001faa  mov     [rsp+110h+var_30], r14
0x180001fb2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001fb9  nop     dword ptr [rax+rax+00h]
0x180001fbe  call    cs:__imp_GetCurrentThreadId
0x180001fc5  nop     dword ptr [rax+rax+00h]
0x180001fca  mov     [rbx+50h], eax
0x180001fcd  lea     rcx, [rbx+48h]
0x180001fd1  mov     eax, [rbx+5Ch]
0x180001fd4  test    al, 1
0x180001fd6  jz      short loc_180002034
0x180001fd8  mov     [rbx+50h], r15d
0x180001fdc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001fe3  nop     dword ptr [rax+rax+00h]
0x180001fe8  mov     edi, 10E0h
0x180001fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ff4  lea     r14, WPP_GLOBAL_Control
0x180001ffb  cmp     rcx, r14
0x180001ffe  jz      loc_1800025C1
0x180002004  test    byte ptr [rcx+1Ch], 1
0x180002008  jz      loc_1800025C1
0x18000200e  mov     edx, 40h ; '@'
0x180002013  mov     r9, [rbx+18h]
0x180002017  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000201e  mov     rcx, [rcx+10h]
0x180002022  mov     [rsp+110h+UserDataCount], edi
0x180002026  mov     r9, [r9+8]
0x18000202a  call    WPP_SF_Sd
0x18000202f  jmp     loc_1800025C1
0x180002034  or      eax, 1
0x180002037  mov     [rbx+5Ch], eax
0x18000203a  mov     [rbx+50h], r15d
0x18000203e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002045  nop     dword ptr [rax+rax+00h]
0x18000204a  test    byte ptr [rbx+29h], 1
0x18000204e  jnz     short loc_18000207D
0x180002050  mov     edi, 10E0h
0x180002055  mov     rcx, cs:WPP_GLOBAL_Control
0x18000205c  lea     r14, WPP_GLOBAL_Control
0x180002063  cmp     rcx, r14
0x180002066  jz      loc_1800025C1
0x18000206c  test    byte ptr [rcx+1Ch], 1
0x180002070  jz      loc_1800025C1
0x180002076  mov     edx, 41h ; 'A'
0x18000207b  jmp     short loc_180002013
0x18000207d  mov     rax, [rbx+18h]
0x180002081  mov     edx, 1
0x180002086  mov     [rsp+110h+arg_10], rsi
0x18000208e  mov     [rsp+110h+var_20], r12
0x180002096  xor     r12b, r12b
0x180002099  mov     [rbp+4Fh+var_CC], r12d
0x18000209d  cmp     [rax+30h], r15
0x1800020a1  jz      short loc_1800020BF
0x1800020a3  mov     rax, [rax+28h]
0x1800020a7  mov     rcx, [rax+20h]
0x1800020ab  test    rcx, rcx
0x1800020ae  jz      short loc_1800020BF
0x1800020b0  test    byte ptr [rcx], 10h
0x1800020b3  movzx   r12d, r12b
0x1800020b7  cmovnz  r12d, edx
0x1800020bb  mov     [rbp+4Fh+var_CC], r12d
0x1800020bf  lea     r15, [rbx+30h]
0x1800020c3  xor     esi, esi
0x1800020c5  mov     rcx, r15
0x1800020c8  mov     [r15+8], esi
0x1800020cc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800020d3  nop     dword ptr [rax+rax+00h]
0x1800020d8  mov     rcx, rbx
0x1800020db  call    UbpmUnsubscribeFromBrokerNotifications
0x1800020e0  lea     rcx, [rbx+48h]
0x1800020e4  call    cs:__imp_RtlAcquireSRWLockShared
0x1800020eb  nop     dword ptr [rax+rax+00h]
0x1800020f0  mov     eax, [rbx+58h]
0x1800020f3  lea     r14, WPP_GLOBAL_Control
0x1800020fa  test    eax, eax
0x1800020fc  jz      loc_1800022A8
0x180002102  lea     r13, word_18004625A
0x180002109  mov     r15d, 1
0x18000210f  lea     r12, _TraceLoggingMetadata
0x180002116  nop     word ptr [rax+rax+00000000h]
0x180002120  mov     rcx, cs:WPP_GLOBAL_Control
0x180002127  cmp     rcx, r14
0x18000212a  jz      short loc_180002153
0x18000212c  test    byte ptr [rcx+1Ch], 4
0x180002130  jz      short loc_180002153
0x180002132  mov     r9, [rbx+18h]
0x180002136  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18000213d  mov     rcx, [rcx+10h]
0x180002141  mov     edx, 42h ; 'B'
0x180002146  mov     [rsp+110h+UserDataCount], eax
0x18000214a  mov     r9, [r9+8]
0x18000214e  call    WPP_SF_SL
0x180002153  mov     eax, cs:dword_18004F0F0
0x180002159  cmp     eax, 5
0x18000215c  jbe     loc_180002274
0x180002162  mov     rcx, cs:qword_18004F108
0x180002169  mov     rax, cs:qword_18004F100
0x180002170  test    r15b, al
0x180002173  jz      loc_180002274
0x180002179  mov     rax, rcx
0x18000217c  and     eax, r15d
0x18000217f  cmp     rax, rcx
0x180002182  jnz     loc_180002274
0x180002188  mov     eax, [rbx+58h]
0x18000218b  xor     edx, edx
0x18000218d  mov     [rbp+4Fh+var_C0], eax
0x180002190  mov     rax, [rbx+18h]
0x180002194  mov     [rbp+4Fh+var_48], 4
0x18000219c  mov     rcx, [rax+8]
0x1800021a0  lea     rax, [rbp+4Fh+var_C0]
0x1800021a4  mov     [rbp+4Fh+var_50], rax
0x1800021a8  mov     [rbp+4Fh+var_B8], rbx
0x1800021ac  test    rcx, rcx
0x1800021af  jz      short loc_1800021D4
0x1800021b1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800021b8  nop     dword ptr [rax+rax+00000000h]
0x1800021c0  cmp     [rcx+rax*2+2], dx
0x1800021c5  lea     rax, [rax+1]
0x1800021c9  jnz     short loc_1800021C0
0x1800021cb  lea     eax, ds:2[rax*2]
0x1800021d2  jmp     short loc_1800021E0
0x1800021d4  lea     rcx, qword_1800439C0
0x1800021db  mov     eax, 2
0x1800021e0  mov     [rbp+4Fh+var_58], eax
0x1800021e3  xor     r9d, r9d; RelatedActivityId
0x1800021e6  mov     [rbp+4Fh+var_60], rcx
0x1800021ea  lea     rax, [rbp+4Fh+var_B8]
0x1800021ee  mov     [rbp+4Fh+var_70], rax
0x1800021f2  xor     r8d, r8d; ActivityId
0x1800021f5  movzx   eax, cs:word_180046250
0x1800021fc  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x1800021ff  mov     rax, cs:off_18004F0F8
0x180002206  mov     [rbp+4Fh+var_90.Ptr], rax
0x18000220a  mov     [rbp+4Fh+var_54], edx
0x18000220d  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180002211  mov     [rbp+4Fh+var_68], 8
0x180002219  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x180002220  mov     [rbp+4Fh+EventDescriptor.Keyword], r15
0x180002224  movzx   eax, word ptr [rax]
0x180002227  mov     [rbp+4Fh+var_90.Size], eax
0x18000222a  lea     rax, _TraceLoggingMetadataEnd
0x180002231  sub     eax, r12d
0x180002234  mov     dword ptr [rbp+4Fh+var_90.0Ch], 2
0x18000223b  mov     [rbp+4Fh+var_80], r13
0x18000223f  mov     [rbp+4Fh+var_78], 52h ; 'R'
0x180002246  mov     [rbp+4Fh+var_74], r15d
0x18000224a  mov     [rbp+4Fh+var_C4], eax
0x18000224d  mov     eax, [rbp+4Fh+var_C4]
0x180002250  mov     rcx, cs:RegHandle; RegHandle
0x180002257  lea     rax, [rbp+4Fh+var_90]
0x18000225b  mov     [rsp+110h+UserData], rax; UserData
0x180002260  mov     [rsp+110h+UserDataCount], 5; UserDataCount
0x180002268  call    cs:__imp_EventWriteTransfer
0x18000226f  nop     dword ptr [rax+rax+00h]
0x180002274  mov     r9d, r15d; Flags
0x180002277  lea     rdx, [rbx+48h]; SRWLock
0x18000227b  mov     r8d, 0FFFFFFFFh; dwMilliseconds
0x180002281  lea     rcx, [rbx+60h]; ConditionVariable
0x180002285  call    cs:__imp_SleepConditionVariableSRW
0x18000228c  nop     dword ptr [rax+rax+00h]
0x180002291  mov     eax, [rbx+58h]
0x180002294  test    eax, eax
0x180002296  jnz     loc_180002120
0x18000229c  mov     r12d, [rbp+4Fh+var_CC]
0x1800022a0  lea     r15, [rbx+30h]
0x1800022a4  mov     r13, [rbp+4Fh+var_B0]
0x1800022a8  lea     rcx, [rbx+48h]
0x1800022ac  call    cs:__imp_RtlReleaseSRWLockShared
0x1800022b3  nop     dword ptr [rax+rax+00h]
0x1800022b8  mov     rcx, r15
0x1800022bb  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800022c2  nop     dword ptr [rax+rax+00h]
0x1800022c7  call    cs:__imp_GetCurrentThreadId
0x1800022ce  nop     dword ptr [rax+rax+00h]
0x1800022d3  mov     rdi, [rbx+70h]
0x1800022d7  mov     rcx, r15
0x1800022da  mov     [rbx+70h], rsi
0x1800022de  mov     [r15+8], esi
0x1800022e2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800022e9  nop     dword ptr [rax+rax+00h]
0x1800022ee  xor     r8d, r8d; pvCleanupContext
0x1800022f1  mov     edx, 1; fCancelPendingCallbacks
0x1800022f6  mov     rcx, rdi; ptpcg
0x1800022f9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180002300  nop     dword ptr [rax+rax+00h]
0x180002305  mov     rcx, rdi; ptpcg
0x180002308  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000230f  nop     dword ptr [rax+rax+00h]
0x180002314  lea     rsi, [rbx+0D0h]
0x18000231b  mov     rcx, rsi
0x18000231e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002325  nop     dword ptr [rax+rax+00h]
0x18000232a  call    cs:__imp_GetCurrentThreadId
0x180002331  nop     dword ptr [rax+rax+00h]
0x180002336  mov     r8d, [rbp+4Fh+var_C8]
0x18000233a  xor     edi, edi
0x18000233c  mov     [rsi+8], eax
0x18000233f  xor     r9d, r9d
0x180002342  movzx   eax, [rsp+110h+var_D0]
0x180002347  xor     edx, edx
0x180002349  mov     [rsp+110h+UserData], rdi
0x18000234e  mov     rcx, rbx
0x180002351  mov     byte ptr [rsp+110h+UserDataCount], al
0x180002355  call    UbpmTerminateActionsForConsumer
0x18000235a  mov     rcx, rsi
0x18000235d  mov     [rsi+8], edi
0x180002360  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002367  nop     dword ptr [rax+rax+00h]
0x18000236c  mov     r8, [rbx+120h]; P
0x180002373  test    r8, r8
0x180002376  jz      short loc_18000239A
0x180002378  mov     rcx, gs:60h
0x180002381  xor     edx, edx; Flags
0x180002383  mov     rcx, [rcx+30h]; HeapHandle
0x180002387  call    cs:__imp_RtlFreeHeap
0x18000238e  nop     dword ptr [rax+rax+00h]
0x180002393  mov     [rbx+120h], rdi
0x18000239a  mov     rcx, r15
0x18000239d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800023a4  nop     dword ptr [rax+rax+00h]
0x1800023a9  call    cs:__imp_GetCurrentThreadId
0x1800023b0  nop     dword ptr [rax+rax+00h]
0x1800023b5  mov     [r15+8], eax
0x1800023b9  xor     r15d, r15d
0x1800023bc  mov     ecx, r15d
0x1800023bf  xor     eax, eax
0x1800023c1  lock cmpxchg [rbx+40h], rcx
0x1800023c7  mov     rcx, [rbx+18h]
0x1800023cb  mov     edx, [rcx+14h]
0x1800023ce  mov     rcx, rsi
0x1800023d1  sub     rax, rdx
0x1800023d4  xchg    rax, [rbx+40h]
0x1800023d8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800023df  nop     dword ptr [rax+rax+00h]
0x1800023e4  call    cs:__imp_GetCurrentThreadId
0x1800023eb  nop     dword ptr [rax+rax+00h]
0x1800023f0  lea     rdi, [rbx+150h]
0x1800023f7  mov     [rsi+8], eax
0x1800023fa  test    rdi, rdi
0x1800023fd  jz      short loc_180002404
0x1800023ff  cmp     [rdi], r15d
0x180002402  jnz     short loc_18000240A
0x180002404  cmp     [rdi+4], r15d
0x180002408  jz      short loc_180002471
0x18000240a  mov     rcx, rdi
0x18000240d  call    cs:__imp_NtDeleteWnfStateName
0x180002414  nop     dword ptr [rax+rax+00h]
0x180002419  test    eax, eax
0x18000241b  jns     short loc_180002465
0x18000241d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002424  cmp     rcx, r14
0x180002427  jz      short loc_180002465
0x180002429  test    byte ptr [rcx+1Ch], 1
0x18000242d  jz      short loc_180002465
0x18000242f  mov     ecx, eax; Status
0x180002431  call    cs:__imp_RtlNtStatusToDosError
0x180002438  nop     dword ptr [rax+rax+00h]
0x18000243d  mov     r9, [rbx+18h]
0x180002441  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180002448  mov     rcx, cs:WPP_GLOBAL_Control
0x18000244f  mov     edx, 43h ; 'C'
0x180002454  mov     [rsp+110h+UserDataCount], eax
0x180002458  mov     r9, [r9+8]
0x18000245c  mov     rcx, [rcx+10h]
0x180002460  call    WPP_SF_Sd
0x180002465  xor     eax, eax
0x180002467  mov     [rdi], rax
0x18000246a  mov     [rbx+158h], r15d
0x180002471  mov     r8, [rbx+160h]; P
0x180002478  test    r8, r8
0x18000247b  jz      short loc_180002498
0x18000247d  mov     rcx, gs:60h
0x180002486  xor     edx, edx; Flags
0x180002488  mov     rcx, [rcx+30h]; HeapHandle
0x18000248c  call    cs:__imp_RtlFreeHeap
  ... truncated ...
```
