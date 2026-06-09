# BipCreateBrokerEvent

- ea: `0x18005f150`
- end: `0x18005f8e4`
- name: `BipCreateBrokerEvent`
- size: `1940`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005f8f0`
- `0x1800802c0`

## callees

- `0x18000d7c0`
- `0x18000da50`
- `0x1800326a0`
- `0x180037a80`
- `0x18005f150`
- `0x18006d364`
- `0x180080538`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x18005f83f`
- `ntdll!NtCreateWnfStateName` at `0x18005f83f`
- `ntdll!NtDeleteWnfStateName` at `0x18005f6de`
- `ntdll!NtDeleteWnfStateName` at `0x18005f6de`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005f521`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005f575`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005f521`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005f575`
- `ntdll!RtlFreeHeap` at `0x18005f28d`
- `ntdll!RtlFreeHeap` at `0x18005f813`
- `ntdll!RtlFreeHeap` at `0x18005f28d`
- `ntdll!RtlFreeHeap` at `0x18005f813`
- `ntdll!RtlAllocateHeap` at `0x18005f2a0`
- `ntdll!RtlAllocateHeap` at `0x18005f2a0`
- `ntdll!RtlEqualSid` at `0x18005f205`
- `ntdll!RtlEqualSid` at `0x18005f219`
- `ntdll!RtlEqualSid` at `0x18005f205`
- `ntdll!RtlEqualSid` at `0x18005f219`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18005f441`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18005f441`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005f5bc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005f5bc`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005f6ba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005f7ef`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005f6ba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005f7ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f6c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f6c8`
- `RPCRT4!RpcRevertToSelf` at `0x18005f396`
- `RPCRT4!RpcRevertToSelf` at `0x18005f396`
- `RPCRT4!RpcImpersonateClient` at `0x18005f2fb`
- `RPCRT4!RpcImpersonateClient` at `0x18005f2fb`
- `EventAggregation!BriCreateBrokeredEventEx` at `0x18005f389`
- `EventAggregation!BriCreateBrokeredEventEx` at `0x18005f389`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x18005f8c3`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x18005f8c3`
- `EventAggregation!BriGetBrokerAvailabilityChangeStamp` at `0x18005f46d`
- `EventAggregation!BriGetBrokerAvailabilityChangeStamp` at `0x18005f46d`
- `EventAggregation!BriIsBrokerRegistered` at `0x18005f1d9`
- `EventAggregation!BriIsBrokerRegistered` at `0x18005f1d9`

## pseudocode

```c
__int64 __fastcall BipCreateBrokerEvent(void *a1, unsigned int a2, __int64 a3)
{
  int v3; // eax
  RPC_BINDING_HANDLE v4; // rbx
  _BYTE *Heap; // r15
  __int64 v8; // rsi
  int v9; // edi
  void *v10; // rbx
  unsigned __int16 v11; // bx
  int v12; // esi
  int v13; // eax
  RPC_BINDING_HANDLE v14; // rbx
  int v15; // r12d
  __int64 v16; // rdx
  __int64 v17; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v22; // edi
  __int64 v23; // rbx
  _QWORD *v24; // rax
  unsigned int v25; // eax
  int v27; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v29; // [rsp+60h] [rbp-A8h] BYREF
  RPC_BINDING_HANDLE BindingHandle; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD v31[2]; // [rsp+70h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR v33; // [rsp+88h] [rbp-80h] BYREF
  __int64 v34; // [rsp+98h] [rbp-70h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v38; // [rsp+C0h] [rbp-48h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D8h] [rbp-30h] BYREF
  char *v40; // [rsp+E8h] [rbp-20h]
  int v41; // [rsp+F0h] [rbp-18h]
  int v42; // [rsp+F4h] [rbp-14h]
  __int64 v43; // [rsp+F8h] [rbp-10h]
  __int64 v44; // [rsp+100h] [rbp-8h]
  int *v45; // [rsp+108h] [rbp+0h]
  __int64 v46; // [rsp+110h] [rbp+8h]
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+118h] [rbp+10h] BYREF
  __int16 *v48; // [rsp+128h] [rbp+20h]
  int v49; // [rsp+130h] [rbp+28h]
  int v50; // [rsp+134h] [rbp+2Ch]
  __int64 v51; // [rsp+138h] [rbp+30h]
  __int64 v52; // [rsp+140h] [rbp+38h]
  __int64 v53; // [rsp+148h] [rbp+40h]
  __int64 v54; // [rsp+150h] [rbp+48h]
  unsigned int *v55; // [rsp+158h] [rbp+50h]
  __int64 v56; // [rsp+160h] [rbp+58h]
  _DWORD *v57; // [rsp+168h] [rbp+60h]
  __int64 v58; // [rsp+170h] [rbp+68h]
  _BYTE P[512]; // [rsp+178h] [rbp+70h] BYREF

  v3 = *(_DWORD *)(a3 + 24);
  v4 = 0;
  Heap = 0;
  BindingHandle = a1;
  LODWORD(v29) = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  DWORD2(v37) = v3 & 0x1FFFFFFF;
  v38 = 0;
  if ( (a2 & 0x10) == 0 || (v8 = a3 + 128, !(unsigned __int8)BriIsBrokerRegistered(a3 + 128)) )
  {
    v34 = 0;
    BindingHandle = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;;GA;;;S-1-5-18)", 1u, &BindingHandle, 0)
      && (v4 = BindingHandle) != 0 )
    {
      v12 = NtCreateWnfStateName(&v34, 3, 0, 0, 0, 4096, BindingHandle);
      if ( v12 >= 0 )
      {
        v25 = v34;
        v12 = 0;
        *(_DWORD *)(a3 + 748) |= 0x20u;
        *(_QWORD *)(a3 + 148) = __PAIR64__(HIDWORD(v34), v25);
        v34 = 0;
        *(_DWORD *)(a3 + 144) = 0;
LABEL_64:
        LocalFree(v4);
LABEL_65:
        if ( v34 )
          NtDeleteWnfStateName(&v34);
        if ( v12 >= 0 )
        {
          v12 = 0;
          goto LABEL_79;
        }
        v15 = 10;
        goto LABEL_69;
      }
    }
    else
    {
      v12 = -1073741801;
    }
    if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
    {
      v43 = a3 + 32;
      v45 = &v27;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_1800C30A0;
      v44 = 16;
      v27 = v12;
      v46 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 3;
      UserData.Size = *(unsigned __int16 *)off_1800C30A0;
      v40 = byte_1800B1181;
      UserData.Reserved = 2;
      v41 = 57;
      v42 = 1;
      v28 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
    if ( !v4 )
      goto LABEL_65;
    goto LABEL_64;
  }
  v9 = 0;
  v10 = *(void **)(a3 + 168);
  if ( v10 && !RtlEqualSid(*(PSID *)(a3 + 168), &dword_1800C44E4) && !RtlEqualSid(v10, qword_1800C4528) )
    v9 = 2;
  v34 = *(_QWORD *)(a3 + 176);
  if ( !v34 )
    v34 = *(_QWORD *)(a3 + 168);
  if ( (a2 & 1) != 0 && (a2 & 0x40) != 0 )
    v9 |= 1u;
  if ( *(_DWORD *)(a3 + 792) )
  {
    v11 = 512;
    Heap = P;
    LOWORD(v27) = 512;
    v12 = 0;
    while ( 1 )
    {
      if ( v12 == -1073741789 )
      {
        if ( Heap != P )
          RtlFreeHeap(BipHeap, 0, Heap);
        Heap = RtlAllocateHeap(BipHeap, 0, v11);
      }
      if ( !Heap )
      {
        v12 = -1073741801;
        goto LABEL_27;
      }
      v13 = BrpDecodeBrokeredEvent_V1((int)a3 + 796, *(unsigned __int16 *)(a3 + 792), v11, (_DWORD)Heap, (__int64)&v27);
      v12 = v13;
      if ( v13 != -1073741789 )
        break;
      v11 = v27;
    }
    if ( v13 >= 0 )
    {
      v8 = a3 + 128;
      goto LABEL_23;
    }
LABEL_27:
    v15 = 20;
    goto LABEL_69;
  }
LABEL_23:
  v14 = BindingHandle;
  if ( BindingHandle && RpcImpersonateClient(BindingHandle) )
  {
    v12 = -1073741555;
    v15 = 30;
LABEL_69:
    if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
    {
      v52 = 16;
      v51 = a3 + 32;
      v54 = 16;
      v53 = a3 + 128;
      v28 = v12;
      v55 = &v28;
      v56 = 4;
      v57 = v31;
      *(_DWORD *)&v33.Level = 2;
      v47.Ptr = (ULONGLONG)off_1800C30A0;
      v31[0] = v15;
      v58 = 4;
      *(_DWORD *)&v33.Id = 184549376;
      v33.Keyword = 3;
      v47.Size = *(unsigned __int16 *)off_1800C30A0;
      v48 = &word_1800B11C6;
      v47.Reserved = 2;
      v49 = 73;
      v50 = 1;
      v31[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v33, 0, 0, 6u, &v47);
    }
    goto LABEL_73;
  }
  v16 = a3 + 192;
  if ( !*(_WORD *)(a3 + 192) )
    v16 = 0;
  v12 = BriCreateBrokeredEventEx(v8, v16, v34, Heap, v9, a3 + 32, &v35, &v37, &v36);
  if ( v14 && RpcRevertToSelf() )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  BipAcquireGlobalLock(v17);
  if ( v12 == -1073610729 )
  {
    if ( (a2 & 1) != 0 && (a2 & 0x40) != 0 && *(int *)(a3 + 24) >= 0 )
    {
      v12 = BipRegisterForBrokerAvailability(a3, a2);
      if ( v12 >= 0 )
      {
        v12 = 259;
        v15 = 50;
      }
      else
      {
        v15 = 40;
      }
      goto LABEL_52;
    }
    goto LABEL_41;
  }
  if ( v12 < 0 )
  {
LABEL_41:
    v15 = 60;
LABEL_52:
    BipLockWatchdogContextDisarmWatchdog(v18);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v22 = ~(1 << dword_1800C3CB0);
    dword_1800C3CB4 = 0;
    v23 = ThreadLocalStoragePointer[(unsigned int)tls_index];
    *(_DWORD *)(v23 + 8) &= v22;
    RtlReleaseSRWLockExclusive(&BipGlobalLock);
    goto LABEL_54;
  }
  v19 = v36;
  if ( v36 != __PAIR64__(v36, 0) )
  {
    *(_QWORD *)(a3 + 776) = v36;
    v12 = RtlSubscribeWnfStateChangeNotification(a3 + 784, v19, 0, BipEventControlNotificationCallback, a3, 0, 0, 0);
    if ( v12 < 0 )
    {
      v15 = 70;
      goto LABEL_52;
    }
  }
  if ( (a2 & 0x40) != 0 && !(unsigned int)BriGetBrokerAvailabilityChangeStamp(a3 + 128, &v29) )
    v18 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)(unsigned int)_InterlockedExchange(
                                                                     *(volatile __int32 **)(a3 + 752),
                                                                     v29);
  *(_DWORD *)(a3 + 24) &= 0xE0000000;
  *(_DWORD *)(a3 + 24) |= DWORD2(v37);
  v20 = DWORD2(v38);
  *(_DWORD *)(a3 + 760) = HIDWORD(v37);
  *(_QWORD *)(a3 + 764) = v38;
  if ( (_DWORD)v20 )
  {
    *(_DWORD *)(a3 + 772) = v20;
    BipTriggerSettingsTableFindById(&qword_1800C3F68, v20, a3 + 584);
  }
  if ( *(int *)(a3 + 24) < 0 )
  {
    v12 = -1073741738;
    v15 = 80;
    goto LABEL_52;
  }
  *(_QWORD *)(a3 + 148) = v35;
  v35 = 0;
  BipLockWatchdogContextDisarmWatchdog(v18);
  v24 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v22 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v23 = v24[(unsigned int)tls_index];
  *(_DWORD *)(v23 + 8) &= v22;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  v15 = 0;
LABEL_54:
  *(_DWORD *)(v23 + 4) &= v22;
  if ( v12 < 0 )
    goto LABEL_69;
LABEL_73:
  if ( Heap && Heap != P )
    RtlFreeHeap(BipHeap, 0, Heap);
LABEL_79:
  if ( v35 )
    BriDeleteBrokeredEvent(&v35, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005f150  mov     r11, rsp
0x18005f153  push    rbp
0x18005f154  push    rsi
0x18005f155  lea     rbp, [r11-2B8h]
0x18005f15c  sub     rsp, 3A8h
0x18005f163  mov     rax, cs:__security_cookie
0x18005f16a  xor     rax, rsp
0x18005f16d  mov     [rbp+2B0h+var_40], rax
0x18005f174  mov     eax, [r8+18h]
0x18005f178  xorps   xmm0, xmm0
0x18005f17b  mov     [r11+10h], rbx
0x18005f17f  and     eax, 1FFFFFFFh
0x18005f184  xor     ebx, ebx
0x18005f186  mov     [r11-18h], rdi
0x18005f18a  mov     [r11-20h], r12
0x18005f18e  mov     r12d, edx
0x18005f191  mov     [r11-28h], r13
0x18005f195  lea     r13, _TraceLoggingMetadataEnd
0x18005f19c  mov     [r11-30h], r14
0x18005f1a0  mov     r14, r8
0x18005f1a3  mov     [r11-38h], r15
0x18005f1a7  mov     r15d, ebx
0x18005f1aa  mov     [rsp+3B0h+BindingHandle], rcx
0x18005f1af  mov     dword ptr [rsp+3B0h+var_358], ebx
0x18005f1b3  mov     [rbp+2B0h+var_318], rbx
0x18005f1b7  mov     [rbp+2B0h+var_310], rbx
0x18005f1bb  movups  [rbp+2B0h+var_308], xmm0
0x18005f1bf  mov     dword ptr [rbp+2B0h+var_308+8], eax
0x18005f1c2  movups  [rbp+2B0h+var_2F8], xmm0
0x18005f1c6  test    dl, 10h
0x18005f1c9  jz      loc_18005F59F
0x18005f1cf  lea     rsi, [r8+80h]
0x18005f1d6  mov     rcx, rsi
0x18005f1d9  call    cs:__imp_BriIsBrokerRegistered
0x18005f1df  test    al, al
0x18005f1e1  jz      loc_18005F59F
0x18005f1e7  mov     edi, ebx
0x18005f1e9  mov     r13d, 2
0x18005f1ef  mov     rbx, [r14+0A8h]
0x18005f1f6  test    rbx, rbx
0x18005f1f9  jz      short loc_18005F225
0x18005f1fb  lea     rdx, dword_1800C44E4; Sid2
0x18005f202  mov     rcx, rbx; Sid1
0x18005f205  call    cs:__imp_RtlEqualSid
0x18005f20b  test    al, al
0x18005f20d  jnz     short loc_18005F225
0x18005f20f  lea     rdx, qword_1800C4528; Sid2
0x18005f216  mov     rcx, rbx; Sid1
0x18005f219  call    cs:__imp_RtlEqualSid
0x18005f21f  test    al, al
0x18005f221  cmovz   edi, r13d
0x18005f225  mov     rax, [r14+0B0h]
0x18005f22c  mov     [rbp+2B0h+var_320], rax
0x18005f230  test    rax, rax
0x18005f233  jnz     short loc_18005F240
0x18005f235  mov     rax, [r14+0A8h]
0x18005f23c  mov     [rbp+2B0h+var_320], rax
0x18005f240  mov     r13d, r12d
0x18005f243  and     r13d, 1
0x18005f247  jz      short loc_18005F252
0x18005f249  test    r12b, 40h
0x18005f24d  jz      short loc_18005F252
0x18005f24f  or      edi, 1
0x18005f252  cmp     [r14+318h], r15d
0x18005f259  jz      loc_18005F2EE
0x18005f25f  mov     ebx, 200h
0x18005f264  lea     r15, [rbp+2B0h+P]
0x18005f268  mov     word ptr [rsp+3B0h+var_360], bx
0x18005f26d  xor     esi, esi
0x18005f26f  nop
0x18005f270  cmp     esi, 0C0000023h
0x18005f276  jnz     short loc_18005F2A9
0x18005f278  lea     rax, [rbp+2B0h+P]
0x18005f27c  cmp     r15, rax
0x18005f27f  jz      short loc_18005F293
0x18005f281  mov     rcx, cs:BipHeap; HeapHandle
0x18005f288  mov     r8, r15; P
0x18005f28b  xor     edx, edx; Flags
0x18005f28d  call    cs:__imp_RtlFreeHeap
0x18005f293  mov     rcx, cs:BipHeap; HeapHandle
0x18005f29a  xor     edx, edx; Flags
0x18005f29c  movzx   r8d, bx; Size
0x18005f2a0  call    cs:__imp_RtlAllocateHeap
0x18005f2a6  mov     r15, rax
0x18005f2a9  test    r15, r15
0x18005f2ac  jz      short loc_18005F321
0x18005f2ae  movzx   edx, word ptr [r14+318h]
0x18005f2b6  lea     rax, [rsp+3B0h+var_360]
0x18005f2bb  lea     rcx, [r14+31Ch]
0x18005f2c2  mov     qword ptr [rsp+3B0h+UserDataCount], rax
0x18005f2c7  mov     r9, r15
0x18005f2ca  movzx   r8d, bx
0x18005f2ce  call    BrpDecodeBrokeredEvent_V1
0x18005f2d3  mov     esi, eax
0x18005f2d5  cmp     eax, 0C0000023h
0x18005f2da  jnz     short loc_18005F2E3
0x18005f2dc  movzx   ebx, word ptr [rsp+3B0h+var_360]
0x18005f2e1  jmp     short loc_18005F270
0x18005f2e3  test    eax, eax
0x18005f2e5  js      short loc_18005F326
0x18005f2e7  lea     rsi, [r14+80h]
0x18005f2ee  mov     rbx, [rsp+3B0h+BindingHandle]
0x18005f2f3  test    rbx, rbx
0x18005f2f6  jz      short loc_18005F33D
0x18005f2f8  mov     rcx, rbx; BindingHandle
0x18005f2fb  call    cs:__imp_RpcImpersonateClient
0x18005f301  test    eax, eax
0x18005f303  jz      short loc_18005F33D
0x18005f305  mov     esi, 0C000010Dh
0x18005f30a  lea     r13, _TraceLoggingMetadataEnd
0x18005f311  mov     edi, 2
0x18005f316  mov     r12d, 1Eh
0x18005f31c  jmp     loc_18005F6F2
0x18005f321  mov     esi, 0C0000017h
0x18005f326  mov     edi, 2
0x18005f32b  lea     r13, _TraceLoggingMetadataEnd
0x18005f332  mov     r12d, 14h
0x18005f338  jmp     loc_18005F6F2
0x18005f33d  mov     r8, [rbp+2B0h+var_320]
0x18005f341  lea     rdx, [r14+0C0h]
0x18005f348  mov     al, 1
0x18005f34a  lea     r9, [r14+20h]
0x18005f34e  movzx   ecx, al
0x18005f351  xor     eax, eax
0x18005f353  cmp     [rdx], ax
0x18005f356  cmovz   ecx, eax
0x18005f359  test    cl, cl
0x18005f35b  mov     rcx, rsi
0x18005f35e  cmovz   rdx, rax
0x18005f362  lea     rax, [rbp+2B0h+var_310]
0x18005f366  mov     [rsp+40h], rax
0x18005f36b  lea     rax, [rbp+2B0h+var_308]
0x18005f36f  mov     [rsp+3B0h+var_378], rax
0x18005f374  lea     rax, [rbp+2B0h+var_318]
0x18005f378  mov     [rsp+3B0h+var_380], rax
0x18005f37d  mov     [rsp+3B0h+UserData], r9
0x18005f382  mov     r9, r15
0x18005f385  mov     [rsp+3B0h+UserDataCount], edi
0x18005f389  call    cs:__imp_BriCreateBrokeredEventEx
0x18005f38f  mov     esi, eax
0x18005f391  test    rbx, rbx
0x18005f394  jz      short loc_18005F3A5
0x18005f396  call    cs:__imp_RpcRevertToSelf
0x18005f39c  test    eax, eax
0x18005f39e  jz      short loc_18005F3A5
0x18005f3a0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005f3a5  call    BipAcquireGlobalLock
0x18005f3aa  cmp     esi, 0C0020017h
0x18005f3b0  jnz     short loc_18005F3F3
0x18005f3b2  test    r13d, r13d
0x18005f3b5  jz      short loc_18005F3F7
0x18005f3b7  test    r12b, 40h
0x18005f3bb  jz      short loc_18005F3F7
0x18005f3bd  cmp     dword ptr [r14+18h], 0
0x18005f3c2  jl      short loc_18005F3F7
0x18005f3c4  mov     edx, r12d
0x18005f3c7  mov     rcx, r14
0x18005f3ca  call    BipRegisterForBrokerAvailability
0x18005f3cf  xor     r13d, r13d
0x18005f3d2  mov     esi, eax
0x18005f3d4  test    eax, eax
0x18005f3d6  jns     short loc_18005F3E3
0x18005f3d8  mov     r12d, 28h ; '('
0x18005f3de  jmp     loc_18005F4E4
0x18005f3e3  mov     esi, 103h
0x18005f3e8  mov     r12d, 32h ; '2'
0x18005f3ee  jmp     loc_18005F4E4
0x18005f3f3  test    esi, esi
0x18005f3f5  jns     short loc_18005F405
0x18005f3f7  mov     r12d, 3Ch ; '<'
0x18005f3fd  xor     r13d, r13d
0x18005f400  jmp     loc_18005F4E4
0x18005f405  mov     rdx, [rbp+2B0h+var_310]
0x18005f409  test    edx, edx
0x18005f40b  jnz     short loc_18005F412
0x18005f40d  cmp     dword ptr [rbp+2B0h+var_310+4], edx
0x18005f410  jz      short loc_18005F458
0x18005f412  xor     r13d, r13d
0x18005f415  mov     [r14+308h], rdx
0x18005f41c  mov     dword ptr [rsp+3B0h+var_378], r13d
0x18005f421  lea     rcx, [r14+310h]
0x18005f428  mov     dword ptr [rsp+3B0h+var_380], r13d
0x18005f42d  lea     r9, BipEventControlNotificationCallback
0x18005f434  mov     [rsp+3B0h+UserData], r13
0x18005f439  xor     r8d, r8d
0x18005f43c  mov     qword ptr [rsp+3B0h+UserDataCount], r14
0x18005f441  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18005f447  mov     esi, eax
0x18005f449  test    eax, eax
0x18005f44b  jns     short loc_18005F45B
0x18005f44d  mov     r12d, 46h ; 'F'
0x18005f453  jmp     loc_18005F4E4
0x18005f458  xor     r13d, r13d
0x18005f45b  test    r12b, 40h
0x18005f45f  jz      short loc_18005F484
0x18005f461  lea     rdx, [rsp+3B0h+var_358]
0x18005f466  lea     rcx, [r14+80h]
0x18005f46d  call    cs:__imp_BriGetBrokerAvailabilityChangeStamp
0x18005f473  test    eax, eax
0x18005f475  jnz     short loc_18005F484
0x18005f477  mov     rax, [r14+2F0h]
0x18005f47e  mov     ecx, dword ptr [rsp+3B0h+var_358]
0x18005f482  xchg    ecx, [rax]
0x18005f484  and     dword ptr [r14+18h], 0E0000000h
0x18005f48c  mov     eax, dword ptr [rbp+2B0h+var_308+8]
0x18005f48f  or      [r14+18h], eax
0x18005f493  mov     eax, dword ptr [rbp+2B0h+var_308+0Ch]
0x18005f496  mov     edx, dword ptr [rbp+2B0h+var_2F8+8]
0x18005f499  mov     [r14+2F8h], eax
0x18005f4a0  mov     eax, dword ptr [rbp+2B0h+var_2F8]
0x18005f4a3  mov     [r14+2FCh], eax
0x18005f4aa  mov     eax, dword ptr [rbp+2B0h+var_2F8+4]
0x18005f4ad  mov     [r14+300h], eax
0x18005f4b4  test    edx, edx
0x18005f4b6  jz      short loc_18005F4D2
0x18005f4b8  lea     r8, [r14+248h]
0x18005f4bf  mov     [r14+304h], edx
0x18005f4c6  lea     rcx, qword_1800C3F68
0x18005f4cd  call    BipTriggerSettingsTableFindById
0x18005f4d2  cmp     dword ptr [r14+18h], 0
0x18005f4d7  jge     short loc_18005F529
0x18005f4d9  mov     esi, 0C0000056h
0x18005f4de  mov     r12d, 50h ; 'P'
0x18005f4e4  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005f4e9  mov     ecx, cs:dword_1800C3CB0
0x18005f4ef  mov     edi, 1
0x18005f4f4  mov     rax, gs:58h
0x18005f4fd  shl     edi, cl
0x18005f4ff  mov     ecx, cs:_tls_index
0x18005f505  not     edi
0x18005f507  mov     cs:dword_1800C3CB4, r13d
0x18005f50e  mov     rbx, [rax+rcx*8]
0x18005f512  lea     rcx, BipGlobalLock
0x18005f519  mov     eax, 8
0x18005f51e  and     [rax+rbx], edi
0x18005f521  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005f527  jmp     short loc_18005F57E
0x18005f529  mov     rax, [rbp+2B0h+var_318]
0x18005f52d  mov     [r14+94h], rax
0x18005f534  mov     [rbp+2B0h+var_318], r13
0x18005f538  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005f53d  mov     ecx, cs:dword_1800C3CB0
0x18005f543  mov     edi, 1
0x18005f548  mov     rax, gs:58h
0x18005f551  shl     edi, cl
0x18005f553  mov     ecx, cs:_tls_index
0x18005f559  not     edi
0x18005f55b  mov     cs:dword_1800C3CB4, r13d
0x18005f562  mov     rbx, [rax+rcx*8]
0x18005f566  lea     rcx, BipGlobalLock
0x18005f56d  mov     eax, 8
0x18005f572  and     [rax+rbx], edi
0x18005f575  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005f57b  mov     r12d, r13d
0x18005f57e  mov     eax, 4
0x18005f583  and     [rax+rbx], edi
0x18005f586  test    esi, esi
0x18005f588  jns     loc_18005F7F5
0x18005f58e  mov     edi, 2
0x18005f593  lea     r13, _TraceLoggingMetadataEnd
0x18005f59a  jmp     loc_18005F6F2
0x18005f59f  xor     r9d, r9d; SecurityDescriptorSize
0x18005f5a2  mov     [rbp+2B0h+var_320], rbx
0x18005f5a6  lea     r8, [rsp+3B0h+BindingHandle]; SecurityDescriptor
0x18005f5ab  mov     [rsp+3B0h+BindingHandle], rbx
0x18005f5b0  mov     edx, 1; StringSDRevision
0x18005f5b5  lea     rcx, aDPAGaS1518; "D:P(A;;GA;;;S-1-5-18)"
0x18005f5bc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005f5c2  mov     edi, 2
0x18005f5c7  cmp     eax, 1
0x18005f5ca  jnz     short loc_18005F5DA
0x18005f5cc  mov     rbx, [rsp+3B0h+BindingHandle]
0x18005f5d1  test    rbx, rbx
0x18005f5d4  jnz     loc_18005F81B
0x18005f5da  mov     esi, 0C0000017h
0x18005f5df  xor     r12d, r12d
0x18005f5e2  mov     eax, cs:dword_1800C3098
0x18005f5e8  lea     rdx, [r14+20h]
0x18005f5ec  cmp     eax, edi
0x18005f5ee  jbe     loc_18005F6C0
0x18005f5f4  mov     rcx, cs:qword_1800C30B0
0x18005f5fb  mov     rax, cs:qword_1800C30A8
0x18005f602  test    al, 3
0x18005f604  jz      loc_18005F6C0
0x18005f60a  mov     rax, rcx
0x18005f60d  and     eax, 3
0x18005f610  cmp     rax, rcx
0x18005f613  jnz     loc_18005F6C0
0x18005f619  mov     [rbp+2B0h+var_2C0], rdx
0x18005f61d  lea     rax, [rsp+3B0h+var_360]
0x18005f622  mov     [rbp+2B0h+var_2B0], rax
0x18005f626  lea     rcx, _TraceLoggingMetadata
0x18005f62d  movzx   eax, cs:word_1800B1177
0x18005f634  lea     rdx, [rsp+3B0h+EventDescriptor]; EventDescriptor
0x18005f639  mov     dword ptr [rsp+3B0h+EventDescriptor.Level], eax
0x18005f63d  xor     r9d, r9d; RelatedActivityId
0x18005f640  mov     rax, cs:off_1800C30A0
0x18005f647  xor     r8d, r8d; ActivityId
0x18005f64a  mov     [rbp+2B0h+var_2E0.Ptr], rax
0x18005f64e  mov     [rbp+2B0h+var_2B8], 10h
  ... truncated ...
```
