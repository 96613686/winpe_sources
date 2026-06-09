# BipEventCleanup

- ea: `0x1800603d0`
- end: `0x1800608d5`
- name: `BipEventCleanup`
- size: `1285`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800608e0`

## callees

- `0x1800056fc`
- `0x18000d7c0`
- `0x18000da50`
- `0x180025834`
- `0x18003a024`
- `0x1800603d0`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180060467`
- `ntdll!NtDeleteWnfStateName` at `0x180060467`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180060635`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180060635`
- `ntdll!RtlFreeHeap` at `0x1800605ba`
- `ntdll!RtlFreeHeap` at `0x1800607b3`
- `ntdll!RtlFreeHeap` at `0x1800607ce`
- `ntdll!RtlFreeHeap` at `0x1800607e9`
- `ntdll!RtlFreeHeap` at `0x1800605ba`
- `ntdll!RtlFreeHeap` at `0x1800607b3`
- `ntdll!RtlFreeHeap` at `0x1800607ce`
- `ntdll!RtlFreeHeap` at `0x1800607e9`
- `ntdll!TpReleaseWork` at `0x18006040c`
- `ntdll!TpReleaseWork` at `0x18006040c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006047b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006047b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180060589`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180060798`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800608b3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180060589`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180060798`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800608b3`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x18006048a`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x18006048a`
- `EventAggregation!BriUnregisterFromBrokerAvailability` at `0x1800605a4`
- `EventAggregation!BriUnregisterFromBrokerAvailability` at `0x1800605a4`

## pseudocode

```c
int __fastcall BipEventCleanup(__int64 a1)
{
  __int64 v2; // rcx
  unsigned int v3; // eax
  int *v4; // r14
  int v5; // eax
  __int64 v6; // rax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v7; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v9; // edi
  __int64 v10; // rbx
  __int128 v11; // xmm1
  int v12; // eax
  void *v13; // r8
  void *v14; // r8
  void *v15; // r8
  __int64 v16; // rax
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-CCh]
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+3Ch] [rbp-C4h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR v23; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+70h] [rbp-90h] BYREF
  __int128 v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  char *v31; // [rsp+B0h] [rbp-50h]
  int v32; // [rsp+B8h] [rbp-48h]
  int v33; // [rsp+BCh] [rbp-44h]
  __int64 v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  int *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  int *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+F0h] [rbp-10h] BYREF
  __int16 *v41; // [rsp+100h] [rbp+0h]
  int v42; // [rsp+108h] [rbp+8h]
  int v43; // [rsp+10Ch] [rbp+Ch]
  __int128 *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  struct _EVENT_DATA_DESCRIPTOR *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  unsigned int *v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+138h] [rbp+38h]
  int *v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]

  v2 = *(_QWORD *)(a1 + 160);
  if ( v2 )
    TpReleaseWork();
  v3 = *(_DWORD *)(a1 + 148);
  v25 = 0;
  if ( __PAIR64__(*(_DWORD *)(a1 + 152), v3) )
  {
    v4 = (int *)(a1 + 748);
    if ( (*(_BYTE *)(a1 + 748) & 0x20) != 0 )
    {
      LODWORD(v25) = v3;
      HIDWORD(v25) = *(_DWORD *)(a1 + 152);
      v5 = NtDeleteWnfStateName(&v25);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 784) )
        RtlUnsubscribeWnfNotificationWaitForCompletion();
      v5 = BriDeleteBrokeredEvent(a1 + 148, 0);
    }
    if ( v5 < 0 && (unsigned int)dword_1800C3098 > 2 )
    {
      v2 = qword_1800C30B0;
      if ( (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
      {
        v20 = v5;
        v34 = a1 + 32;
        v35 = 16;
        v36 = &v20;
        v21 = *v4;
        v38 = &v21;
        *(_DWORD *)&EventDescriptor.Level = 2;
        UserData.Ptr = (ULONGLONG)off_1800C30A0;
        v37 = 4;
        v39 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 3;
        UserData.Size = *(unsigned __int16 *)off_1800C30A0;
        v31 = byte_1800B10FD;
        UserData.Reserved = 2;
        v32 = 67;
        v33 = 1;
        v18 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
  }
  else
  {
    v4 = (int *)(a1 + 748);
  }
  v6 = *(_QWORD *)(a1 + 752);
  if ( v6 )
  {
    if ( *(_QWORD *)(v6 + 8) )
      BriUnregisterFromBrokerAvailability();
    RtlFreeHeap(BipHeap, 0, *(PVOID *)(a1 + 752));
    *(_QWORD *)(a1 + 752) = 0;
  }
  if ( (*(_BYTE *)(a1 + 24) & 2) == 0 )
    BipDeleteEventFromSelectedStore(KeyHandle, a1 + 32);
  if ( *(_QWORD *)(a1 + 120) )
  {
    BipAcquireGlobalLock(v2);
    BipRemoveEventFromPackage(a1);
    BipLockWatchdogContextDisarmWatchdog(v7);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v9 = ~(1 << dword_1800C3CB0);
    dword_1800C3CB4 = 0;
    v10 = ThreadLocalStoragePointer[(unsigned int)tls_index];
    *(_DWORD *)(v10 + 8) &= v9;
    RtlReleaseSRWLockExclusive(&BipGlobalLock);
    *(_DWORD *)(v10 + 4) &= v9;
  }
  if ( (*(_BYTE *)v4 & 0x20) != 0 )
  {
    v11 = *(_OWORD *)(a1 + 32);
    v26 = *(struct _EVENT_DATA_DESCRIPTOR *)(a1 + 128);
    v27 = v11;
    v12 = BipNotifyAllSubscribers(8, &v26, 32);
    if ( v12 < 0
      && (unsigned int)dword_1800C3098 > 2
      && (qword_1800C30A8 & 3) != 0
      && (qword_1800C30B0 & 3) == qword_1800C30B0 )
    {
      v22 = v12;
      v44 = &v27;
      v50 = &v22;
      *(_DWORD *)&v23.Level = 2;
      v40.Ptr = (ULONGLONG)off_1800C30A0;
      v46 = &v26;
      v48 = &v18;
      v45 = 16;
      v47 = 16;
      v18 = 8;
      v49 = 4;
      v51 = 4;
      *(_DWORD *)&v23.Id = 184549376;
      v23.Keyword = 3;
      v40.Size = *(unsigned __int16 *)off_1800C30A0;
      v41 = word_1800AF29A;
      v40.Reserved = 2;
      v42 = 61;
      v43 = 1;
      v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v23, 0, 0, 6u, &v40);
    }
  }
  v13 = *(void **)(a1 + 168);
  if ( v13 )
    RtlFreeHeap(BipHeap, 0, v13);
  v14 = *(void **)(a1 + 176);
  if ( v14 )
    RtlFreeHeap(BipHeap, 0, v14);
  v15 = *(void **)(a1 + 184);
  if ( v15 )
    RtlFreeHeap(BipHeap, 0, v15);
  LODWORD(v16) = dword_1800C3098;
  if ( (unsigned int)dword_1800C3098 > 5 )
  {
    LODWORD(v16) = qword_1800C30A8;
    if ( (qword_1800C30A8 & 2) != 0 )
    {
      v16 = qword_1800C30B0 & 2;
      if ( v16 == qword_1800C30B0 )
      {
        v29 = 16;
        v28 = a1 + 32;
        *(_DWORD *)&v23.Level = 517;
        v26.Ptr = (ULONGLONG)off_1800C30A0;
        *(_DWORD *)&v23.Id = 184549376;
        v23.Keyword = 2;
        v26.Size = *(unsigned __int16 *)off_1800C30A0;
        *(_QWORD *)&v27 = &byte_1800B0FDF;
        v26.Reserved = 2;
        *((_QWORD *)&v27 + 1) = 0x10000001ALL;
        v19 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v16) = EventWriteTransfer(RegHandle, &v23, 0, 0, 3u, &v26);
      }
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1800603d0  mov     r11, rsp
0x1800603d3  push    rbp
0x1800603d4  push    rsi
0x1800603d5  push    r12
0x1800603d7  push    r13
0x1800603d9  push    r15
0x1800603db  lea     rbp, [rsp-60h]
0x1800603e0  sub     rsp, 160h
0x1800603e7  mov     rax, cs:__security_cookie
0x1800603ee  xor     rax, rsp
0x1800603f1  mov     [rbp+80h+var_30], rax
0x1800603f5  mov     rsi, rcx
0x1800603f8  mov     [r11+10h], rbx
0x1800603fc  mov     rcx, [rcx+0A0h]
0x180060403  mov     [r11+20h], r14
0x180060407  test    rcx, rcx
0x18006040a  jz      short loc_180060412
0x18006040c  call    cs:__imp_TpReleaseWork
0x180060412  mov     eax, [rsi+94h]
0x180060418  lea     r15, _TraceLoggingMetadataEnd
0x18006041f  xor     r12d, r12d
0x180060422  lea     r13, _TraceLoggingMetadata
0x180060429  mov     [rsp+180h+var_118], r12
0x18006042e  test    eax, eax
0x180060430  jnz     short loc_180060447
0x180060432  cmp     [rsi+98h], r12d
0x180060439  jnz     short loc_180060447
0x18006043b  lea     r14, [rsi+2ECh]
0x180060442  jmp     loc_18006058F
0x180060447  lea     r14, [rsi+2ECh]
0x18006044e  test    byte ptr [r14], 20h
0x180060452  jz      short loc_18006046F
0x180060454  mov     dword ptr [rsp+180h+var_118], eax
0x180060458  lea     rcx, [rsp+180h+var_118]
0x18006045d  mov     eax, [rsi+98h]
0x180060463  mov     dword ptr [rsp+180h+var_118+4], eax
0x180060467  call    cs:__imp_NtDeleteWnfStateName
0x18006046d  jmp     short loc_180060490
0x18006046f  mov     rcx, [rsi+310h]
0x180060476  test    rcx, rcx
0x180060479  jz      short loc_180060481
0x18006047b  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180060481  xor     edx, edx
0x180060483  lea     rcx, [rsi+94h]
0x18006048a  call    cs:__imp_BriDeleteBrokeredEvent
0x180060490  mov     edx, eax
0x180060492  test    eax, eax
0x180060494  jns     loc_18006058F
0x18006049a  mov     eax, cs:dword_1800C3098
0x1800604a0  cmp     eax, 2
0x1800604a3  jbe     loc_18006058F
0x1800604a9  mov     rcx, cs:qword_1800C30B0
0x1800604b0  mov     rax, cs:qword_1800C30A8
0x1800604b7  test    al, 3
0x1800604b9  jz      loc_18006058F
0x1800604bf  mov     rax, rcx
0x1800604c2  and     eax, 3
0x1800604c5  cmp     rax, rcx
0x1800604c8  jnz     loc_18006058F
0x1800604ce  mov     [rsp+180h+var_148], edx
0x1800604d2  lea     rax, [rsi+20h]
0x1800604d6  mov     [rbp+80h+var_C0], rax
0x1800604da  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x1800604df  lea     rax, [rsp+180h+var_148]
0x1800604e4  mov     [rbp+80h+var_B8], 10h
0x1800604ec  mov     [rbp+80h+var_B0], rax
0x1800604f0  xor     r9d, r9d; RelatedActivityId
0x1800604f3  mov     eax, [r14]
0x1800604f6  xor     r8d, r8d; ActivityId
0x1800604f9  mov     [rsp+180h+var_144], eax
0x1800604fd  lea     rax, [rsp+180h+var_144]
0x180060502  mov     [rbp+80h+var_A0], rax
0x180060506  movzx   eax, cs:word_1800B10F3
0x18006050d  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180060511  mov     rax, cs:off_1800C30A0
0x180060518  mov     [rbp+80h+var_E0.Ptr], rax
0x18006051c  mov     [rbp+80h+var_A8], 4
0x180060524  mov     [rbp+80h+var_98], 4
0x18006052c  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180060534  mov     [rsp+180h+EventDescriptor.Keyword], 3
0x18006053d  movzx   eax, word ptr [rax]
0x180060540  mov     [rbp+80h+var_E0.Size], eax
0x180060543  lea     rax, byte_1800B10FD
0x18006054a  mov     [rbp+80h+var_D0], rax
0x18006054e  mov     rax, r15
0x180060551  sub     eax, r13d
0x180060554  mov     dword ptr [rbp+80h+var_E0.0Ch], 2
0x18006055b  mov     [rbp+80h+var_C8], 43h ; 'C'
0x180060562  mov     [rbp+80h+var_C4], 1
0x180060569  mov     [rsp+180h+var_150], eax
0x18006056d  mov     eax, [rsp+180h+var_150]
0x180060571  mov     rcx, cs:RegHandle; RegHandle
0x180060578  lea     rax, [rbp+80h+var_E0]
0x18006057c  mov     [rsp+180h+UserData], rax; UserData
0x180060581  mov     [rsp+180h+UserDataCount], 5; UserDataCount
0x180060589  call    cs:__imp_EventWriteTransfer
0x18006058f  mov     rax, [rsi+2F0h]
0x180060596  test    rax, rax
0x180060599  jz      short loc_1800605C7
0x18006059b  mov     rcx, [rax+8]
0x18006059f  test    rcx, rcx
0x1800605a2  jz      short loc_1800605AA
0x1800605a4  call    cs:__imp_BriUnregisterFromBrokerAvailability
0x1800605aa  mov     r8, [rsi+2F0h]; P
0x1800605b1  xor     edx, edx; Flags
0x1800605b3  mov     rcx, cs:BipHeap; HeapHandle
0x1800605ba  call    cs:__imp_RtlFreeHeap
0x1800605c0  mov     [rsi+2F0h], r12
0x1800605c7  test    byte ptr [rsi+18h], 2
0x1800605cb  jnz     short loc_1800605DD
0x1800605cd  mov     rcx, cs:KeyHandle
0x1800605d4  lea     rdx, [rsi+20h]
0x1800605d8  call    BipDeleteEventFromSelectedStore
0x1800605dd  cmp     [rsi+78h], r12
0x1800605e1  jz      short loc_18006064B
0x1800605e3  mov     [rsp+180h+arg_10], rdi
0x1800605eb  call    BipAcquireGlobalLock
0x1800605f0  mov     rcx, rsi
0x1800605f3  call    BipRemoveEventFromPackage
0x1800605f8  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x1800605fd  mov     ecx, cs:dword_1800C3CB0
0x180060603  mov     edi, 1
0x180060608  mov     rax, gs:58h
0x180060611  shl     edi, cl
0x180060613  mov     ecx, cs:_tls_index
0x180060619  not     edi
0x18006061b  mov     cs:dword_1800C3CB4, r12d
0x180060622  mov     rbx, [rax+rcx*8]
0x180060626  lea     rcx, BipGlobalLock
0x18006062d  mov     eax, 8
0x180060632  and     [rax+rbx], edi
0x180060635  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18006063b  mov     eax, 4
0x180060640  and     [rax+rbx], edi
0x180060643  mov     rdi, [rsp+180h+arg_10]
0x18006064b  test    byte ptr [r14], 20h
0x18006064f  mov     r14, [rsp+180h+arg_18]
0x180060657  mov     rbx, [rsp+180h+arg_8]
0x18006065f  jz      loc_18006079E
0x180060665  movups  xmm0, xmmword ptr [rsi+80h]
0x18006066c  mov     r8d, 20h ; ' '
0x180060672  lea     rdx, [rsp+180h+var_110]
0x180060677  movups  xmm1, xmmword ptr [rsi+20h]
0x18006067b  mov     ecx, 8
0x180060680  movups  xmmword ptr [rsp+180h+var_110.Ptr], xmm0
0x180060685  movups  [rbp+80h+var_100], xmm1
0x180060689  call    BipNotifyAllSubscribers
0x18006068e  test    eax, eax
0x180060690  jns     loc_18006079E
0x180060696  mov     ecx, cs:dword_1800C3098
0x18006069c  cmp     ecx, 2
0x18006069f  jbe     loc_18006079E
0x1800606a5  mov     rdx, cs:qword_1800C30B0
0x1800606ac  mov     rcx, cs:qword_1800C30A8
0x1800606b3  test    cl, 3
0x1800606b6  jz      loc_18006079E
0x1800606bc  mov     rcx, rdx
0x1800606bf  and     ecx, 3
0x1800606c2  cmp     rcx, rdx
0x1800606c5  jnz     loc_18006079E
0x1800606cb  mov     [rsp+180h+var_140], eax
0x1800606cf  lea     rcx, [rbp+80h+var_100]
0x1800606d3  mov     [rbp+80h+var_70], rcx
0x1800606d7  lea     rax, [rsp+180h+var_140]
0x1800606dc  mov     [rbp+80h+var_40], rax
0x1800606e0  lea     rcx, [rsp+180h+var_110]
0x1800606e5  movzx   eax, cs:word_1800AF290
0x1800606ec  lea     rdx, [rsp+180h+var_138]; EventDescriptor
0x1800606f1  mov     dword ptr [rsp+180h+var_138.Level], eax
0x1800606f5  xor     r9d, r9d; RelatedActivityId
0x1800606f8  mov     rax, cs:off_1800C30A0
0x1800606ff  xor     r8d, r8d; ActivityId
0x180060702  mov     [rbp+80h+var_90.Ptr], rax
0x180060706  mov     [rbp+80h+var_60], rcx
0x18006070a  lea     rcx, [rsp+180h+var_150]
0x18006070f  mov     [rbp+80h+var_50], rcx
0x180060713  mov     [rbp+80h+var_68], 10h
0x18006071b  mov     [rbp+80h+var_58], 10h
0x180060723  mov     [rsp+180h+var_150], 8
0x18006072b  mov     [rbp+80h+var_48], 4
0x180060733  mov     [rbp+80h+var_38], 4
0x18006073b  mov     dword ptr [rsp+180h+var_138.Id], 0B000000h
0x180060743  mov     [rsp+180h+var_138.Keyword], 3
0x18006074c  movzx   eax, word ptr [rax]
0x18006074f  mov     [rbp+80h+var_90.Size], eax
0x180060752  lea     rax, word_1800AF29A
0x180060759  mov     [rbp+80h+var_80], rax
0x18006075d  mov     rax, r15
0x180060760  sub     eax, r13d
0x180060763  mov     dword ptr [rbp+80h+var_90.0Ch], 2
0x18006076a  mov     [rbp+80h+var_78], 3Dh ; '='
0x180060771  mov     [rbp+80h+var_74], 1
0x180060778  mov     [rsp+180h+var_14C], eax
0x18006077c  mov     eax, [rsp+180h+var_14C]
0x180060780  mov     rcx, cs:RegHandle; RegHandle
0x180060787  lea     rax, [rbp+80h+var_90]
0x18006078b  mov     [rsp+180h+UserData], rax; UserData
0x180060790  mov     [rsp+180h+UserDataCount], 6; UserDataCount
0x180060798  call    cs:__imp_EventWriteTransfer
0x18006079e  mov     r8, [rsi+0A8h]; P
0x1800607a5  test    r8, r8
0x1800607a8  jz      short loc_1800607B9
0x1800607aa  mov     rcx, cs:BipHeap; HeapHandle
0x1800607b1  xor     edx, edx; Flags
0x1800607b3  call    cs:__imp_RtlFreeHeap
0x1800607b9  mov     r8, [rsi+0B0h]; P
0x1800607c0  test    r8, r8
0x1800607c3  jz      short loc_1800607D4
0x1800607c5  mov     rcx, cs:BipHeap; HeapHandle
0x1800607cc  xor     edx, edx; Flags
0x1800607ce  call    cs:__imp_RtlFreeHeap
0x1800607d4  mov     r8, [rsi+0B8h]; P
0x1800607db  test    r8, r8
0x1800607de  jz      short loc_1800607EF
0x1800607e0  mov     rcx, cs:BipHeap; HeapHandle
0x1800607e7  xor     edx, edx; Flags
0x1800607e9  call    cs:__imp_RtlFreeHeap
0x1800607ef  mov     eax, cs:dword_1800C3098
0x1800607f5  cmp     eax, 5
0x1800607f8  jbe     loc_1800608B9
0x1800607fe  mov     rcx, cs:qword_1800C30B0
0x180060805  mov     rax, cs:qword_1800C30A8
0x18006080c  test    al, 2
0x18006080e  jz      loc_1800608B9
0x180060814  mov     rax, rcx
0x180060817  and     eax, 2
0x18006081a  cmp     rax, rcx
0x18006081d  jnz     loc_1800608B9
0x180060823  lea     rax, [rsi+20h]
0x180060827  mov     [rbp+80h+var_E8], 10h
0x18006082f  mov     [rbp+80h+var_F0], rax
0x180060833  lea     rdx, [rsp+180h+var_138]; EventDescriptor
0x180060838  movzx   eax, cs:word_1800B0FD5
0x18006083f  sub     r15d, r13d
0x180060842  mov     dword ptr [rsp+180h+var_138.Level], eax
0x180060846  xor     r9d, r9d; RelatedActivityId
0x180060849  mov     rax, cs:off_1800C30A0
0x180060850  xor     r8d, r8d; ActivityId
0x180060853  mov     [rsp+180h+var_110.Ptr], rax
0x180060858  mov     dword ptr [rsp+180h+var_138.Id], 0B000000h
0x180060860  mov     [rsp+180h+var_138.Keyword], 2
0x180060869  movzx   eax, word ptr [rax]
0x18006086c  mov     [rsp+180h+var_110.Size], eax
0x180060870  lea     rax, byte_1800B0FDF
0x180060877  mov     qword ptr [rbp+80h+var_100], rax
0x18006087b  mov     dword ptr [rsp+180h+var_110.0Ch], 2
0x180060883  mov     dword ptr [rbp+80h+var_100+8], 1Ah
0x18006088a  mov     dword ptr [rbp+80h+var_100+0Ch], 1
0x180060891  mov     [rsp+180h+var_14C], r15d
0x180060896  mov     eax, [rsp+180h+var_14C]
0x18006089a  mov     rcx, cs:RegHandle; RegHandle
0x1800608a1  lea     rax, [rsp+180h+var_110]
0x1800608a6  mov     [rsp+180h+UserData], rax; UserData
0x1800608ab  mov     [rsp+180h+UserDataCount], 3; UserDataCount
0x1800608b3  call    cs:__imp_EventWriteTransfer
0x1800608b9  mov     rcx, [rbp+80h+var_30]
0x1800608bd  xor     rcx, rsp; StackCookie
0x1800608c0  call    __security_check_cookie
0x1800608c5  add     rsp, 160h
0x1800608cc  pop     r15
0x1800608ce  pop     r13
0x1800608d0  pop     r12
0x1800608d2  pop     rsi
0x1800608d3  pop     rbp
0x1800608d4  retn
```
