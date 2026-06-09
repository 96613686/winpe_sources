# BipPackageBackgroundAccessWorker

- ea: `0x180056ff0`
- end: `0x18005760d`
- name: `BipPackageBackgroundAccessWorker`
- size: `1565`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d7c0`
- `0x18000da50`
- `0x18000fda0`
- `0x180013c70`
- `0x18002b100`
- `0x18002e2d8`
- `0x180051fa0`
- `0x180056ff0`
- `0x18005db80`
- `0x1800617d0`
- `0x18006d364`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180057194`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180057465`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180057194`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180057465`
- `ntdll!RtlWakeAddressAll` at `0x18005747a`
- `ntdll!RtlWakeAddressAll` at `0x18005747a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800570dd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180057357`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800575dd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800570dd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180057357`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800575dd`

## pseudocode

```c
int __fastcall BipPackageBackgroundAccessWorker(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  __int64 v4; // r12
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v5; // rcx
  __int64 v6; // rdx
  _DWORD *v7; // rdi
  _DWORD *v8; // r14
  int v9; // ebx
  unsigned int v10; // r13d
  unsigned int v11; // edi
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rbx
  int v15; // r14d
  int v16; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  bool v19; // zf
  int v20; // eax
  __int64 *v21; // rax
  __int64 *v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v25; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v27; // edi
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 *v30; // rax
  int v31; // r12d
  __int64 *v32; // rcx
  __int64 *v33; // rax
  int v34; // eax
  unsigned int v36; // [rsp+38h] [rbp-D0h] BYREF
  int v37; // [rsp+3Ch] [rbp-CCh] BYREF
  int v38; // [rsp+40h] [rbp-C8h] BYREF
  int v39; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v40; // [rsp+48h] [rbp-C0h]
  __int64 v41; // [rsp+50h] [rbp-B8h]
  __int64 v42; // [rsp+58h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD *i; // [rsp+70h] [rbp-98h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v46; // [rsp+88h] [rbp-80h]
  int v47; // [rsp+90h] [rbp-78h]
  int v48; // [rsp+94h] [rbp-74h]
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+98h] [rbp-70h] BYREF
  int *v50; // [rsp+A8h] [rbp-60h]
  int v51; // [rsp+B0h] [rbp-58h]
  int v52; // [rsp+B4h] [rbp-54h]
  __int64 *v53; // [rsp+B8h] [rbp-50h]
  int v54; // [rsp+C0h] [rbp-48h]
  int v55; // [rsp+C4h] [rbp-44h]
  __int64 *v56; // [rsp+C8h] [rbp-40h]
  int v57; // [rsp+D0h] [rbp-38h]
  int v58; // [rsp+D4h] [rbp-34h]
  int *v59; // [rsp+D8h] [rbp-30h]
  __int64 v60; // [rsp+E0h] [rbp-28h]
  int *v61; // [rsp+E8h] [rbp-20h]
  __int64 v62; // [rsp+F0h] [rbp-18h]

  if ( (unsigned int)dword_1800C3098 > 5 )
  {
    a1 = qword_1800C30B0;
    if ( (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
    {
      *(_DWORD *)&EventDescriptor.Level = 261;
      UserData.Ptr = (ULONGLONG)off_1800C30A0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 2;
      UserData.Size = *(unsigned __int16 *)off_1800C30A0;
      v46 = qword_1800AF868;
      UserData.Reserved = 2;
      v47 = 19;
      v48 = 1;
      v36 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
    }
  }
  BipAcquireGlobalLock(a1);
  LOBYTE(v3) = *(_BYTE *)(a2 + 604);
  v4 = -1;
  v40 = 8;
  v41 = 4;
  if ( (v3 & 4) != 0 )
  {
    v5 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)(unsigned int)tls_index;
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v7 = (_DWORD *)(v6 + 8);
    v8 = (_DWORD *)(v6 + 4);
    *(_QWORD *)&EventDescriptor.Id = v6 + 8;
    for ( i = (_DWORD *)(v6 + 4); ; v8 = i )
    {
      *(_BYTE *)(a2 + 604) = v3 & 0xFB;
      BipLockWatchdogContextDisarmWatchdog(v5);
      v9 = ~(1 << dword_1800C3CB0);
      dword_1800C3CB4 = 0;
      *v7 &= v9;
      RtlReleaseSRWLockExclusive(&BipGlobalLock);
      *v8 &= v9;
      v42 = 0;
      v10 = 0;
      v36 = 0;
      v11 = 0;
      v12 = BipSessionBackgroundAccessServiceFindOrCreateForPackage(a2, &v42);
      v14 = v42;
      v15 = v12;
      if ( v12 >= 0 )
      {
        v16 = BipSystemBackgroundAccessQueryPackageState(v42, *(_QWORD *)(a2 + 24), a2 + 160, &v36);
        v11 = v36;
        v15 = v16;
        if ( v16 >= 0 )
        {
          v10 = v36;
          v15 = 0;
        }
      }
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      if ( (unsigned int)dword_1800C3098 > 5 )
      {
        v13 = qword_1800C30B0;
        if ( (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
        {
          v17 = (__int64 *)(a2 + 416);
          if ( a2 == -416 )
          {
            v17 = &qword_1800A1670;
            v20 = 2;
          }
          else
          {
            v18 = -1;
            do
              v19 = *((_WORD *)v17 + ++v18) == 0;
            while ( !v19 );
            v20 = 2 * v18 + 2;
          }
          v54 = v20;
          v21 = *(__int64 **)(a2 + 24);
          v53 = v17;
          v55 = 0;
          v22 = &BipTraceLoggingNullSid;
          if ( v21 )
            v22 = v21;
          UserData.Ptr = 0x50B000000LL;
          *(_QWORD *)&UserData.Size = 2;
          v23 = *((unsigned __int8 *)v22 + 1);
          v56 = v22;
          v58 = 0;
          v38 = v15;
          v60 = 4;
          v57 = 4 * v23 + 8;
          v59 = &v38;
          v61 = &v39;
          v49.Ptr = (ULONGLONG)off_1800C30A0;
          v39 = v11;
          v62 = 4;
          v49.Size = *(unsigned __int16 *)off_1800C30A0;
          v50 = (int *)&byte_1800AF887;
          v49.Reserved = 2;
          v51 = 79;
          v52 = 1;
          v36 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 6u, &v49);
        }
      }
      if ( v15 >= 0 )
        BipEnergyBudgetBamSettingChanged(qword_1800C45C0, (__int64 *)(a2 + 160), *(void **)(a2 + 24));
      BipAcquireGlobalLock(v13);
      v3 = *(unsigned __int8 *)(a2 + 604);
      v7 = *(_DWORD **)&EventDescriptor.Id;
      if ( (v3 & 4) == 0 )
        break;
    }
    LOBYTE(v3) = v3 | 0x20;
    *(_DWORD *)(a2 + 600) = v10;
    *(_BYTE *)(a2 + 604) = v3;
    if ( (v10 & 2) != 0 && (v10 & 0x31) != 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v5, v24, v3);
    }
    else
    {
      v40 = 8;
      v41 = 4;
    }
  }
  else
  {
    v40 = 8;
    *(_BYTE *)(a2 + 604) = v3 | 0x20;
    v10 = 0;
    v15 = 259;
    v41 = 4;
    *(_DWORD *)(a2 + 600) = 0;
  }
  BipPackageBackgroundAccessProcessStateChange(a2);
  BipPackageCrmPolicyQueueProcessStateChange(a2);
  LOBYTE(v37) = BipSystemStateSnapshot();
  BipPackageEnergySaverProcessStateChange(a2, &v37);
  *(_BYTE *)(a2 + 604) &= ~8u;
  --dword_1800C4654;
  BipLockWatchdogContextDisarmWatchdog(v25);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v27 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v28 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  *(_DWORD *)(v40 + v28) &= v27;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  *(_DWORD *)(v41 + v28) &= v27;
  RtlWakeAddressAll(&dword_1800C4654);
  LODWORD(v29) = dword_1800C3098;
  if ( (unsigned int)dword_1800C3098 > 4 )
  {
    LODWORD(v29) = qword_1800C30A8;
    if ( (qword_1800C30A8 & 3) != 0 )
    {
      v29 = qword_1800C30B0 & 3;
      if ( v29 == qword_1800C30B0 )
      {
        v30 = (__int64 *)(a2 + 416);
        if ( a2 == -416 )
        {
          v30 = &qword_1800A1670;
          v31 = 2;
        }
        else
        {
          do
            v19 = *((_WORD *)v30 + ++v4) == 0;
          while ( !v19 );
          v31 = 2 * v4 + 2;
        }
        v53 = v30;
        v32 = &BipTraceLoggingNullSid;
        v33 = *(__int64 **)(a2 + 24);
        v54 = v31;
        v55 = 0;
        if ( v33 )
          v32 = v33;
        UserData.Ptr = 0x2040B000000LL;
        *(_QWORD *)&UserData.Size = 3;
        v34 = *((unsigned __int8 *)v32 + 1);
        v56 = v32;
        v58 = 0;
        v39 = v15;
        v60 = 4;
        v57 = 4 * v34 + 8;
        v59 = &v39;
        v61 = &v38;
        v49.Ptr = (ULONGLONG)off_1800C30A0;
        v38 = v10;
        v62 = 4;
        v49.Size = *(unsigned __int16 *)off_1800C30A0;
        v50 = &dword_1800AF814;
        v49.Reserved = 2;
        v51 = 72;
        v52 = 1;
        v36 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        LODWORD(v29) = EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 6u, &v49);
      }
    }
  }
  return v29;
}

```

## disassembly

```asm
0x180056ff0  mov     r11, rsp
0x180056ff3  push    rbp
0x180056ff4  push    rsi
0x180056ff5  push    r12
0x180056ff7  push    r15
0x180056ff9  lea     rbp, [r11-28h]
0x180056ffd  sub     rsp, 108h
0x180057004  mov     rax, cs:__security_cookie
0x18005700b  xor     rax, rsp
0x18005700e  mov     [rbp+20h+var_30], rax
0x180057012  mov     eax, cs:dword_1800C3098
0x180057018  mov     rsi, rdx
0x18005701b  mov     [r11+8], rbx
0x18005701f  lea     rdx, _TraceLoggingMetadata
0x180057026  mov     [r11+18h], rdi
0x18005702a  cmp     eax, 5
0x18005702d  jbe     loc_1800570E3
0x180057033  mov     rcx, cs:qword_1800C30B0
0x18005703a  mov     rax, cs:qword_1800C30A8
0x180057041  test    al, 2
0x180057043  jz      loc_1800570E3
0x180057049  mov     rax, rcx
0x18005704c  and     eax, 2
0x18005704f  cmp     rax, rcx
0x180057052  jnz     loc_1800570E3
0x180057058  movzx   eax, cs:word_1800AF85E
0x18005705f  xor     r9d, r9d; RelatedActivityId
0x180057062  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x180057066  xor     r8d, r8d; ActivityId
0x180057069  mov     rax, cs:off_1800C30A0
0x180057070  mov     [rsp+120h+var_B0.Ptr], rax
0x180057075  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x18005707d  mov     [rsp+120h+EventDescriptor.Keyword], 2
0x180057086  movzx   eax, word ptr [rax]
0x180057089  mov     [rsp+120h+var_B0.Size], eax
0x18005708d  lea     rax, qword_1800AF868
0x180057094  mov     [rbp+20h+var_A0], rax
0x180057098  lea     rax, _TraceLoggingMetadataEnd
0x18005709f  sub     eax, edx
0x1800570a1  mov     dword ptr [rsp+120h+var_B0.0Ch], 2
0x1800570a9  mov     [rbp+20h+var_98], 13h
0x1800570b0  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1800570b5  mov     [rbp+20h+var_94], 1
0x1800570bc  mov     [rsp+120h+var_F0], eax
0x1800570c0  mov     eax, [rsp+120h+var_F0]
0x1800570c4  mov     rcx, cs:RegHandle; RegHandle
0x1800570cb  lea     rax, [rsp+120h+var_B0]
0x1800570d0  mov     [rsp+120h+UserData], rax; UserData
0x1800570d5  mov     [rsp+120h+UserDataCount], 2; UserDataCount
0x1800570dd  call    cs:__imp_EventWriteTransfer
0x1800570e3  mov     [rsp+120h+arg_18], r13
0x1800570eb  mov     [rsp+100h], r14
0x1800570f3  call    BipAcquireGlobalLock
0x1800570f8  movzx   r8d, byte ptr [rsi+25Ch]
0x180057100  xor     r15d, r15d
0x180057103  mov     r9d, 8
0x180057109  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180057110  mov     r10d, 4
0x180057116  mov     [rsp+120h+var_E0], r9
0x18005711b  mov     [rsp+120h+var_D8], r10
0x180057120  test    r8b, 4
0x180057124  jz      loc_1800573D0
0x18005712a  mov     ecx, cs:_tls_index
0x180057130  mov     rax, gs:58h
0x180057139  mov     rdx, [rax+rcx*8]
0x18005713d  lea     rdi, [r9+rdx]
0x180057141  lea     r14, [r10+rdx]
0x180057145  mov     qword ptr [rsp+120h+EventDescriptor.Id], rdi
0x18005714a  mov     [rsp+120h+var_B8], r14
0x18005714f  jmp     short loc_180057165
0x180057160  mov     r14, [rsp+120h+var_B8]
0x180057165  and     r8b, 0FBh
0x180057169  mov     [rsi+25Ch], r8b
0x180057170  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180057175  mov     ecx, cs:dword_1800C3CB0
0x18005717b  mov     ebx, 1
0x180057180  shl     ebx, cl
0x180057182  lea     rcx, BipGlobalLock
0x180057189  not     ebx
0x18005718b  mov     cs:dword_1800C3CB4, r15d
0x180057192  and     [rdi], ebx
0x180057194  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005719a  and     [r14], ebx
0x18005719d  lea     rdx, [rsp+120h+var_D0]
0x1800571a2  mov     rcx, rsi
0x1800571a5  mov     [rsp+120h+var_D0], r15
0x1800571aa  mov     r13d, r15d
0x1800571ad  mov     [rsp+120h+var_F0], r15d
0x1800571b2  mov     edi, r15d
0x1800571b5  call    BipSessionBackgroundAccessServiceFindOrCreateForPackage
0x1800571ba  mov     rbx, [rsp+120h+var_D0]
0x1800571bf  mov     r14d, eax
0x1800571c2  test    eax, eax
0x1800571c4  js      short loc_1800571EF
0x1800571c6  mov     rdx, [rsi+18h]
0x1800571ca  lea     r8, [rsi+0A0h]
0x1800571d1  lea     r9, [rsp+120h+var_F0]
0x1800571d6  mov     rcx, rbx
0x1800571d9  call    BipSystemBackgroundAccessQueryPackageState
0x1800571de  mov     edi, [rsp+120h+var_F0]
0x1800571e2  mov     r14d, eax
0x1800571e5  test    eax, eax
0x1800571e7  js      short loc_1800571EF
0x1800571e9  mov     r13d, edi
0x1800571ec  mov     r14d, r15d
0x1800571ef  test    rbx, rbx
0x1800571f2  jz      short loc_180057203
0x1800571f4  mov     rax, [rbx]
0x1800571f7  mov     rcx, rbx
0x1800571fa  mov     rax, [rax+10h]
0x1800571fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057203  mov     eax, cs:dword_1800C3098
0x180057209  cmp     eax, 5
0x18005720c  jbe     loc_18005735D
0x180057212  mov     rcx, cs:qword_1800C30B0
0x180057219  mov     rax, cs:qword_1800C30A8
0x180057220  test    al, 2
0x180057222  jz      loc_18005735D
0x180057228  mov     rax, rcx
0x18005722b  and     eax, 2
0x18005722e  cmp     rax, rcx
0x180057231  jnz     loc_18005735D
0x180057237  lea     rcx, [rsi+1A0h]
0x18005723e  test    rcx, rcx
0x180057241  jz      short loc_180057265
0x180057243  mov     rax, r12
0x180057246  nop     word ptr [rax+rax+00000000h]
0x180057250  cmp     [rcx+rax*2+2], r15w
0x180057256  lea     rax, [rax+1]
0x18005725a  jnz     short loc_180057250
0x18005725c  lea     eax, ds:2[rax*2]
0x180057263  jmp     short loc_180057271
0x180057265  lea     rcx, qword_1800A1670
0x18005726c  mov     eax, 2
0x180057271  mov     [rbp+20h+var_68], eax
0x180057274  lea     rdx, [rsp+120h+var_B0]; EventDescriptor
0x180057279  mov     rax, [rsi+18h]
0x18005727d  test    rax, rax
0x180057280  mov     [rbp+20h+var_70], rcx
0x180057284  mov     [rbp+20h+var_64], r15d
0x180057288  lea     rcx, BipTraceLoggingNullSid
0x18005728f  cmovnz  rcx, rax
0x180057293  mov     dword ptr [rsp+120h+var_B0.Ptr], 0B000000h
0x18005729b  mov     qword ptr [rsp+120h+var_B0.Size], 2
0x1800572a4  xor     r9d, r9d; RelatedActivityId
0x1800572a7  xor     r8d, r8d; ActivityId
0x1800572aa  movzx   eax, byte ptr [rcx+1]
0x1800572ae  mov     [rbp+20h+var_60], rcx
0x1800572b2  lea     rcx, _TraceLoggingMetadata
0x1800572b9  mov     [rbp+20h+var_54], r15d
0x1800572bd  mov     dword ptr [rsp+120h+var_E8], r14d
0x1800572c2  lea     eax, ds:8[rax*4]
0x1800572c9  mov     [rbp+20h+var_48], 4
0x1800572d1  mov     [rbp+20h+var_58], eax
0x1800572d4  lea     rax, [rsp+120h+var_E8]
0x1800572d9  mov     [rbp+20h+var_50], rax
0x1800572dd  lea     rax, [rsp+120h+var_E8+4]
0x1800572e2  mov     [rbp+20h+var_40], rax
0x1800572e6  movzx   eax, cs:word_1800AF87D
0x1800572ed  mov     dword ptr [rsp+120h+var_B0.Ptr+4], eax
0x1800572f1  mov     rax, cs:off_1800C30A0
0x1800572f8  mov     [rbp+20h+var_90.Ptr], rax
0x1800572fc  mov     dword ptr [rsp+120h+var_E8+4], edi
0x180057300  mov     [rbp+20h+var_38], 4
0x180057308  movzx   eax, word ptr [rax]
0x18005730b  mov     [rbp+20h+var_90.Size], eax
0x18005730e  lea     rax, byte_1800AF887
0x180057315  mov     [rbp+20h+var_80], rax
0x180057319  lea     rax, _TraceLoggingMetadataEnd
0x180057320  sub     eax, ecx
0x180057322  mov     dword ptr [rbp+20h+var_90.0Ch], 2
0x180057329  mov     [rbp+20h+var_78], 4Fh ; 'O'
0x180057330  mov     [rbp+20h+var_74], 1
0x180057337  mov     [rsp+120h+var_F0], eax
0x18005733b  mov     eax, [rsp+120h+var_F0]
0x18005733f  mov     rcx, cs:RegHandle; RegHandle
0x180057346  lea     rax, [rbp+20h+var_90]
0x18005734a  mov     [rsp+120h+UserData], rax; UserData
0x18005734f  mov     [rsp+120h+UserDataCount], 6; UserDataCount
0x180057357  call    cs:__imp_EventWriteTransfer
0x18005735d  test    r14d, r14d
0x180057360  js      short loc_180057379
0x180057362  mov     r8, [rsi+18h]
0x180057366  lea     rdx, [rsi+0A0h]
0x18005736d  mov     rcx, cs:qword_1800C45C0; struct _BI_LOCK *
0x180057374  call    BipEnergyBudgetBamSettingChanged
0x180057379  call    BipAcquireGlobalLock
0x18005737e  movzx   r8d, byte ptr [rsi+25Ch]
0x180057386  mov     rdi, qword ptr [rsp+120h+EventDescriptor.Id]
0x18005738b  test    r8b, 4
0x18005738f  jnz     loc_180057160
0x180057395  or      r8b, 20h
0x180057399  mov     [rsi+258h], r13d
0x1800573a0  mov     [rsi+25Ch], r8b
0x1800573a7  test    r13b, 2
0x1800573ab  jz      short loc_1800573BA
0x1800573ad  test    r13b, 31h
0x1800573b1  jz      short loc_1800573BA
0x1800573b3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800573b8  jmp     short loc_1800573F5
0x1800573ba  mov     eax, 8
0x1800573bf  mov     ecx, 4
0x1800573c4  mov     [rsp+120h+var_E0], rax
0x1800573c9  mov     [rsp+120h+var_D8], rcx
0x1800573ce  jmp     short loc_1800573F5
0x1800573d0  or      r8b, 20h
0x1800573d4  mov     [rsp+120h+var_E0], r9
0x1800573d9  mov     [rsi+25Ch], r8b
0x1800573e0  mov     r13d, r15d
0x1800573e3  mov     r14d, 103h
0x1800573e9  mov     [rsp+120h+var_D8], r10
0x1800573ee  mov     [rsi+258h], r15d
0x1800573f5  mov     rcx, rsi
0x1800573f8  call    BipPackageBackgroundAccessProcessStateChange
0x1800573fd  mov     rcx, rsi
0x180057400  call    BipPackageCrmPolicyQueueProcessStateChange
0x180057405  call    BipSystemStateSnapshot
0x18005740a  lea     rdx, [rsp+120h+var_EC]
0x18005740f  mov     byte ptr [rsp+120h+var_EC], al
0x180057413  mov     rcx, rsi
0x180057416  call    BipPackageEnergySaverProcessStateChange
0x18005741b  and     byte ptr [rsi+25Ch], 0F7h
0x180057422  dec     cs:dword_1800C4654
0x180057428  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005742d  mov     ecx, cs:dword_1800C3CB0
0x180057433  mov     edi, 1
0x180057438  mov     edx, cs:_tls_index
0x18005743e  mov     rax, gs:58h
0x180057447  shl     edi, cl
0x180057449  lea     rcx, BipGlobalLock
0x180057450  not     edi
0x180057452  mov     cs:dword_1800C3CB4, r15d
0x180057459  mov     rbx, [rax+rdx*8]
0x18005745d  mov     rax, [rsp+120h+var_E0]
0x180057462  and     [rax+rbx], edi
0x180057465  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005746b  mov     rax, [rsp+120h+var_D8]
0x180057470  lea     rcx, dword_1800C4654
0x180057477  and     [rax+rbx], edi
0x18005747a  call    cs:__imp_RtlWakeAddressAll
0x180057480  mov     eax, cs:dword_1800C3098
0x180057486  mov     rdi, [rsp+120h+arg_10]
0x18005748e  mov     rbx, [rsp+120h+arg_0]
0x180057496  cmp     eax, 4
0x180057499  jbe     loc_1800575E3
0x18005749f  mov     rcx, cs:qword_1800C30B0
0x1800574a6  mov     rax, cs:qword_1800C30A8
0x1800574ad  test    al, 3
0x1800574af  jz      loc_1800575E3
0x1800574b5  mov     rax, rcx
0x1800574b8  and     eax, 3
0x1800574bb  cmp     rax, rcx
0x1800574be  jnz     loc_1800575E3
0x1800574c4  lea     rax, [rsi+1A0h]
0x1800574cb  test    rax, rax
0x1800574ce  jz      short loc_1800574E8
0x1800574d0  cmp     word ptr [rax+r12*2+2], 0
0x1800574d7  lea     r12, [r12+1]
0x1800574dc  jnz     short loc_1800574D0
0x1800574de  lea     r12d, ds:2[r12*2]
0x1800574e6  jmp     short loc_1800574F5
0x1800574e8  lea     rax, qword_1800A1670
0x1800574ef  mov     r12d, 2
0x1800574f5  mov     [rbp+20h+var_70], rax
0x1800574f9  lea     rcx, BipTraceLoggingNullSid
0x180057500  mov     rax, [rsi+18h]
0x180057504  lea     rdx, [rsp+120h+var_B0]; EventDescriptor
0x180057509  test    rax, rax
0x18005750c  mov     [rbp+20h+var_68], r12d
0x180057510  mov     [rbp+20h+var_64], r15d
0x180057514  cmovnz  rcx, rax
0x180057518  mov     dword ptr [rsp+120h+var_B0.Ptr], 0B000000h
0x180057520  mov     qword ptr [rsp+120h+var_B0.Size], 3
0x180057529  xor     r9d, r9d; RelatedActivityId
0x18005752c  xor     r8d, r8d; ActivityId
0x18005752f  movzx   eax, byte ptr [rcx+1]
0x180057533  mov     [rbp+20h+var_60], rcx
0x180057537  lea     rcx, _TraceLoggingMetadata
0x18005753e  mov     [rbp+20h+var_54], r15d
0x180057542  mov     dword ptr [rsp+120h+var_E8+4], r14d
0x180057547  lea     eax, ds:8[rax*4]
0x18005754e  mov     [rbp+20h+var_48], 4
0x180057556  mov     [rbp+20h+var_58], eax
0x180057559  lea     rax, [rsp+120h+var_E8+4]
0x18005755e  mov     [rbp+20h+var_50], rax
0x180057562  lea     rax, [rsp+120h+var_E8]
0x180057567  mov     [rbp+20h+var_40], rax
0x18005756b  movzx   eax, cs:word_1800AF80A
0x180057572  mov     dword ptr [rsp+120h+var_B0.Ptr+4], eax
0x180057576  mov     rax, cs:off_1800C30A0
0x18005757d  mov     [rbp+20h+var_90.Ptr], rax
0x180057581  mov     dword ptr [rsp+120h+var_E8], r13d
0x180057586  mov     [rbp+20h+var_38], 4
0x18005758e  movzx   eax, word ptr [rax]
0x180057591  mov     [rbp+20h+var_90.Size], eax
0x180057594  lea     rax, dword_1800AF814
0x18005759b  mov     [rbp+20h+var_80], rax
0x18005759f  lea     rax, _TraceLoggingMetadataEnd
0x1800575a6  sub     eax, ecx
0x1800575a8  mov     dword ptr [rbp+20h+var_90.0Ch], 2
  ... truncated ...
```
