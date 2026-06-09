# BipWorkItemUpdateCrmActivity

- ea: `0x18005b0d0`
- end: `0x18005b5ee`
- name: `BipWorkItemUpdateCrmActivity`
- size: `1310`
- prototype: `__int64 __fastcall(struct _BI_WORK_ITEM *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180059ad0`

## callees

- `0x18000d7c0`
- `0x18000da50`
- `0x18000f020`
- `0x180015b38`
- `0x180016918`
- `0x180033130`
- `0x180055860`
- `0x180055a9c`
- `0x18005b0d0`
- `0x18006d364`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b2ca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b325`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b2ca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005b325`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b25b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b2ec`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b345`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b458`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b25b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b2ec`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b345`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005b458`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18005b29b`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18005b29b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005b598`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005b598`

## pseudocode

```c
__int64 __fastcall BipWorkItemUpdateCrmActivity(struct _BI_WORK_ITEM *a1)
{
  __int64 v2; // rcx
  __int64 v4; // rcx
  __int64 v5; // rbx
  unsigned int v6; // r14d
  int v7; // r15d
  _QWORD *v8; // r12
  unsigned __int8 PriortizedCrmActivityId; // al
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int8 v12; // di
  __int64 v13; // r8
  __int64 v14; // r14
  int v15; // r15d
  __int64 v16; // rdx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v18; // edi
  __int64 v19; // rbx
  __int64 v20; // rcx
  struct _BI_WORK_ITEM *v21; // rbx
  char *v22; // rbx
  unsigned int v23; // r13d
  unsigned int v24; // r12d
  struct _BI_WORK_ITEM *v25; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v26; // rcx
  __int64 v27; // r9
  _QWORD *v28; // rax
  int v29; // edi
  __int64 v30; // rbx
  __int128 v31; // xmm0
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v33[3]; // [rsp+34h] [rbp-CCh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[464]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+230h] [rbp+130h] BYREF
  char *v38; // [rsp+240h] [rbp+140h]
  int v39; // [rsp+248h] [rbp+148h]
  int v40; // [rsp+24Ch] [rbp+14Ch]
  _DWORD *v41; // [rsp+250h] [rbp+150h]
  __int64 v42; // [rsp+258h] [rbp+158h]
  __int128 *v43; // [rsp+260h] [rbp+160h]
  __int64 v44; // [rsp+268h] [rbp+168h]
  int *v45; // [rsp+270h] [rbp+170h]
  __int64 v46; // [rsp+278h] [rbp+178h]

  memset_0(v36, 0, sizeof(v36));
  v2 = *((unsigned int *)a1 + 100);
  if ( (_DWORD)v2 )
  {
    v2 = (unsigned int)(v2 - 1);
    if ( (_DWORD)v2 != 1 )
      return 0;
  }
  BipAcquireGlobalLock(v2);
  v5 = *((_QWORD *)a1 + 11);
  if ( !v5 )
  {
    v6 = 1601;
    v7 = -1073741275;
LABEL_23:
    BipLockWatchdogContextDisarmWatchdog((struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)v4);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v18 = ~(1 << dword_1800C3CB0);
    dword_1800C3CB4 = 0;
    v19 = ThreadLocalStoragePointer[(unsigned int)tls_index];
    *(_DWORD *)(v19 + 8) &= v18;
    RtlReleaseSRWLockExclusive(&BipGlobalLock);
    *(_DWORD *)(v19 + 4) &= v18;
    if ( v7 < 0 )
      goto LABEL_47;
    return (unsigned int)v7;
  }
  v8 = (_QWORD *)((char *)a1 + 144);
  if ( (_QWORD *)*v8 == v8 )
  {
    if ( (v4 = *((unsigned int *)a1 + 100), (_DWORD)v4) && (v4 = (unsigned int)(v4 - 1), (_DWORD)v4 != 1)
      || *((struct _BI_WORK_ITEM **)a1 + 14) == (struct _BI_WORK_ITEM *)((char *)a1 + 112) )
    {
      v6 = 1601;
LABEL_22:
      v7 = 0;
      goto LABEL_23;
    }
  }
  PriortizedCrmActivityId = BipWorkItemShouldGetPriortizedCrmActivityId(a1);
  v11 = *((unsigned int *)a1 + 100);
  v12 = PriortizedCrmActivityId;
  v13 = (unsigned int)v11;
  if ( (_DWORD)v11 )
  {
    v13 = (unsigned int)(v11 - 1);
    if ( (_DWORD)v11 != 2 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v11, v13);
      LODWORD(v11) = *((_DWORD *)a1 + 100);
    }
  }
  v14 = 604;
  v4 = 604;
  if ( v12 )
    v4 = 600;
  v15 = *(_DWORD *)(v4 + *((_QWORD *)a1 + 9));
  if ( (_DWORD)v11 )
  {
    v16 = (unsigned int)(v11 - 1);
    if ( (_DWORD)v16 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4, v16, v13);
  }
  if ( !v12 )
    v14 = 600;
  v6 = *(_DWORD *)(v14 + *((_QWORD *)a1 + 9));
  if ( v15 == v6 )
    goto LABEL_22;
  v20 = *(_QWORD *)(v5 + 16) + 160LL;
  v32 = 464;
  PsmCreateKey(v20, v5 + 60, v36, &v32);
  v21 = (struct _BI_WORK_ITEM *)*((_QWORD *)a1 + 14);
  v7 = 0;
  if ( v21 == (struct _BI_WORK_ITEM *)((char *)a1 + 112) )
    goto LABEL_40;
  v22 = (char *)v21 - 16;
  if ( !v22 )
    goto LABEL_40;
  while ( 1 )
  {
    v23 = 1601;
    RtlAcquireSRWLockExclusive(v22 + 48);
    if ( *((_DWORD *)v22 + 84) != v6 )
    {
      v23 = *((_DWORD *)v22 + 84);
      *((_DWORD *)v22 + 84) = 1601;
    }
    RtlReleaseSRWLockExclusive(v22 + 48);
    if ( v23 - 26 > 6 )
      goto LABEL_34;
    v7 = BipCrmActivityStart(qword_1800C41E8, a1, v6, v36, v22);
    if ( v7 < 0 )
      break;
    v24 = v6;
    RtlAcquireSRWLockExclusive(v22 + 48);
    if ( (v22[136] & 0x40) == 0 )
    {
      *((_DWORD *)v22 + 84) = v6;
      v24 = 1601;
    }
    RtlReleaseSRWLockExclusive(v22 + 48);
    BipCrmActivityStop(qword_1800C41E8, v23, v22);
    BipCrmActivityStop(qword_1800C41E8, v24, v22);
LABEL_34:
    v25 = (struct _BI_WORK_ITEM *)*((_QWORD *)v22 + 2);
    v22 = 0;
    if ( v25 != (struct _BI_WORK_ITEM *)((char *)a1 + 112) )
      v22 = (char *)v25 - 16;
    if ( !v22 )
      goto LABEL_39;
  }
  BipCrmActivityStop(qword_1800C41E8, v23, v22);
  BipCrmActivityStop(qword_1800C41E8, 1601, v22);
LABEL_39:
  v8 = (_QWORD *)((char *)a1 + 144);
LABEL_40:
  if ( (unsigned int)BipCrmActivityGetActivationAction(qword_1800C41E8, a1, v6) )
  {
    LOBYTE(v27) = 1;
    BipCancelWorkItem(a1, 0xFFFFFFFFLL, (unsigned __int8)v6 | 0x1200u, v27);
  }
  else
  {
    if ( v7 < 0 )
    {
      LOBYTE(v27) = 1;
      BipCancelWorkItem(a1, 0xFFFFFFFFLL, 4608, v27);
    }
    if ( (_QWORD *)*v8 != v8 )
      BipUnbufferPendingActivations(a1);
  }
  BipLockWatchdogContextDisarmWatchdog(v26);
  v28 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v29 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v30 = v28[(unsigned int)tls_index];
  *(_DWORD *)(v30 + 8) &= v29;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  *(_DWORD *)(v30 + 4) &= v29;
  if ( v7 >= 0 )
    return 0;
LABEL_47:
  if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v32 = v7;
    v31 = *((_OWORD *)a1 + 2);
    v33[0] = v6;
    v45 = &v32;
    v35 = v31;
    v46 = 4;
    v43 = &v35;
    v44 = 16;
    v41 = v33;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v42 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v38 = byte_1800B32BB;
    UserData.Reserved = 2;
    v39 = 72;
    v40 = 1;
    v33[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005b0d0  push    rbp
0x18005b0d2  push    rsi
0x18005b0d3  lea     rbp, [rsp-1A8h]
0x18005b0db  sub     rsp, 2A8h
0x18005b0e2  mov     rax, cs:__security_cookie
0x18005b0e9  xor     rax, rsp
0x18005b0ec  mov     [rbp+1B0h+var_30], rax
0x18005b0f3  mov     rsi, rcx
0x18005b0f6  xor     edx, edx; Val
0x18005b0f8  lea     rcx, [rsp+2B0h+var_250]; void *
0x18005b0fd  mov     r8d, 1D0h; Size
0x18005b103  call    memset_0
0x18005b108  mov     ecx, [rsi+190h]
0x18005b10e  test    ecx, ecx
0x18005b110  jz      short loc_18005B123
0x18005b112  sub     ecx, 1
0x18005b115  jz      short loc_18005B11C
0x18005b117  cmp     ecx, 1
0x18005b11a  jz      short loc_18005B123
0x18005b11c  xor     eax, eax
0x18005b11e  jmp     loc_18005B5D5
0x18005b123  mov     [rsp+2B0h+arg_8], rbx
0x18005b12b  mov     [rsp+2B0h+arg_10], rdi
0x18005b133  mov     [rsp+2B0h+arg_18], r12
0x18005b13b  mov     [rsp+2B0h+var_10], r13
0x18005b143  mov     [rsp+2B0h+var_18], r14
0x18005b14b  mov     [rsp+2B0h+var_20], r15
0x18005b153  call    BipAcquireGlobalLock
0x18005b158  mov     rbx, [rsi+58h]
0x18005b15c  test    rbx, rbx
0x18005b15f  jnz     short loc_18005B172
0x18005b161  mov     r14d, 641h
0x18005b167  mov     r15d, 0C0000225h
0x18005b16d  jmp     loc_18005B21B
0x18005b172  lea     r12, [rsi+90h]
0x18005b179  cmp     [r12], r12
0x18005b17d  jnz     short loc_18005B1A4
0x18005b17f  mov     ecx, [rsi+190h]
0x18005b185  test    ecx, ecx
0x18005b187  jz      short loc_18005B193
0x18005b189  sub     ecx, 1
0x18005b18c  jz      short loc_18005B19C
0x18005b18e  cmp     ecx, 1
0x18005b191  jnz     short loc_18005B19C
0x18005b193  lea     rax, [rsi+70h]
0x18005b197  cmp     [rax], rax
0x18005b19a  jnz     short loc_18005B1A4
0x18005b19c  mov     r14d, 641h
0x18005b1a2  jmp     short loc_18005B218
0x18005b1a4  mov     rcx, rsi; struct _BI_WORK_ITEM *
0x18005b1a7  call    ?BipWorkItemShouldGetPriortizedCrmActivityId@@YAEPEAU_BI_WORK_ITEM@@@Z; BipWorkItemShouldGetPriortizedCrmActivityId(_BI_WORK_ITEM *)
0x18005b1ac  mov     edx, [rsi+190h]
0x18005b1b2  movzx   edi, al
0x18005b1b5  mov     r8d, edx
0x18005b1b8  test    edx, edx
0x18005b1ba  jz      short loc_18005B1D3
0x18005b1bc  sub     r8d, 1
0x18005b1c0  jz      short loc_18005B1C8
0x18005b1c2  cmp     r8d, 1
0x18005b1c6  jz      short loc_18005B1D3
0x18005b1c8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b1cd  mov     edx, [rsi+190h]
0x18005b1d3  mov     rax, [rsi+48h]
0x18005b1d7  test    dil, dil
0x18005b1da  mov     r14d, 25Ch
0x18005b1e0  mov     r13d, 258h
0x18005b1e6  mov     ecx, r14d
0x18005b1e9  cmovnz  ecx, r13d
0x18005b1ed  mov     r15d, [rcx+rax]
0x18005b1f1  test    edx, edx
0x18005b1f3  jz      short loc_18005B204
0x18005b1f5  sub     edx, 1
0x18005b1f8  jz      short loc_18005B1FF
0x18005b1fa  cmp     edx, 1
0x18005b1fd  jz      short loc_18005B204
0x18005b1ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b204  mov     rax, [rsi+48h]
0x18005b208  test    dil, dil
0x18005b20b  cmovz   r14, r13
0x18005b20f  mov     r14d, [r14+rax]
0x18005b213  cmp     r15d, r14d
0x18005b216  jnz     short loc_18005B27A
0x18005b218  xor     r15d, r15d
0x18005b21b  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005b220  mov     ecx, cs:dword_1800C3CB0
0x18005b226  mov     edi, 1
0x18005b22b  mov     rax, gs:58h
0x18005b234  shl     edi, cl
0x18005b236  mov     ecx, cs:_tls_index
0x18005b23c  not     edi
0x18005b23e  mov     cs:dword_1800C3CB4, 0
0x18005b248  mov     rbx, [rax+rcx*8]
0x18005b24c  lea     rcx, BipGlobalLock
0x18005b253  mov     eax, 8
0x18005b258  and     [rax+rbx], edi
0x18005b25b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005b261  mov     eax, 4
0x18005b266  and     [rax+rbx], edi
0x18005b269  test    r15d, r15d
0x18005b26c  js      loc_18005B46F
0x18005b272  mov     eax, r15d
0x18005b275  jmp     loc_18005B5A5
0x18005b27a  mov     rcx, [rbx+10h]
0x18005b27e  lea     rdx, [rbx+3Ch]
0x18005b282  add     rcx, 0A0h
0x18005b289  mov     [rsp+2B0h+var_280], 1D0h
0x18005b291  lea     r9, [rsp+2B0h+var_280]
0x18005b296  lea     r8, [rsp+2B0h+var_250]
0x18005b29b  call    cs:__imp_PsmCreateKey
0x18005b2a1  mov     rbx, [rsi+70h]
0x18005b2a5  lea     rax, [rsi+70h]
0x18005b2a9  xor     r15d, r15d
0x18005b2ac  cmp     rbx, rax
0x18005b2af  jz      loc_18005B3BC
0x18005b2b5  add     rbx, 0FFFFFFFFFFFFFFF0h
0x18005b2b9  jz      loc_18005B3BC
0x18005b2bf  nop
0x18005b2c0  lea     rcx, [rbx+30h]
0x18005b2c4  mov     r13d, 641h
0x18005b2ca  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005b2d0  mov     eax, [rbx+150h]
0x18005b2d6  cmp     eax, r14d
0x18005b2d9  jz      short loc_18005B2E8
0x18005b2db  mov     r13d, eax
0x18005b2de  mov     dword ptr [rbx+150h], 641h
0x18005b2e8  lea     rcx, [rbx+30h]
0x18005b2ec  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005b2f2  lea     eax, [r13-1Ah]
0x18005b2f6  cmp     eax, 6
0x18005b2f9  ja      short loc_18005B36F
0x18005b2fb  lea     r9, [rsp+2B0h+var_250]
0x18005b300  mov     qword ptr [rsp+2B0h+UserDataCount], rbx
0x18005b305  mov     r8d, r14d
0x18005b308  lea     rcx, qword_1800C41E8
0x18005b30f  mov     rdx, rsi
0x18005b312  call    ?BipCrmActivityStart@@YAJPEAU_BI_CRM_CONTEXT@@PEAU_BI_WORK_ITEM@@W4_CRM_ACTIVITY_ID@@PEAU_BI_PSM_KEY@@PEAU_GUID@@@Z; BipCrmActivityStart(_BI_CRM_CONTEXT *,_BI_WORK_ITEM *,_CRM_ACTIVITY_ID,_BI_PSM_KEY *,_GUID *)
0x18005b317  mov     r15d, eax
0x18005b31a  test    eax, eax
0x18005b31c  js      short loc_18005B38F
0x18005b31e  lea     rcx, [rbx+30h]
0x18005b322  mov     r12d, r14d
0x18005b325  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005b32b  test    byte ptr [rbx+88h], 40h
0x18005b332  jnz     short loc_18005B341
0x18005b334  mov     [rbx+150h], r14d
0x18005b33b  mov     r12d, 641h
0x18005b341  lea     rcx, [rbx+30h]
0x18005b345  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005b34b  mov     r8, rbx
0x18005b34e  lea     rcx, qword_1800C41E8
0x18005b355  mov     edx, r13d
0x18005b358  call    ?BipCrmActivityStop@@YAXPEAU_BI_CRM_CONTEXT@@W4_CRM_ACTIVITY_ID@@PEAU_GUID@@@Z; BipCrmActivityStop(_BI_CRM_CONTEXT *,_CRM_ACTIVITY_ID,_GUID *)
0x18005b35d  mov     r8, rbx
0x18005b360  lea     rcx, qword_1800C41E8
0x18005b367  mov     edx, r12d
0x18005b36a  call    ?BipCrmActivityStop@@YAXPEAU_BI_CRM_CONTEXT@@W4_CRM_ACTIVITY_ID@@PEAU_GUID@@@Z; BipCrmActivityStop(_BI_CRM_CONTEXT *,_CRM_ACTIVITY_ID,_GUID *)
0x18005b36f  mov     rcx, [rbx+10h]
0x18005b373  lea     rdx, [rsi+70h]
0x18005b377  xor     ebx, ebx
0x18005b379  cmp     rcx, rdx
0x18005b37c  lea     rax, [rcx-10h]
0x18005b380  cmovnz  rbx, rax
0x18005b384  test    rbx, rbx
0x18005b387  jnz     loc_18005B2C0
0x18005b38d  jmp     short loc_18005B3B5
0x18005b38f  mov     r8, rbx
0x18005b392  lea     rcx, qword_1800C41E8
0x18005b399  mov     edx, r13d
0x18005b39c  call    ?BipCrmActivityStop@@YAXPEAU_BI_CRM_CONTEXT@@W4_CRM_ACTIVITY_ID@@PEAU_GUID@@@Z; BipCrmActivityStop(_BI_CRM_CONTEXT *,_CRM_ACTIVITY_ID,_GUID *)
0x18005b3a1  mov     r8, rbx
0x18005b3a4  lea     rcx, qword_1800C41E8
0x18005b3ab  mov     edx, 641h
0x18005b3b0  call    ?BipCrmActivityStop@@YAXPEAU_BI_CRM_CONTEXT@@W4_CRM_ACTIVITY_ID@@PEAU_GUID@@@Z; BipCrmActivityStop(_BI_CRM_CONTEXT *,_CRM_ACTIVITY_ID,_GUID *)
0x18005b3b5  lea     r12, [rsi+90h]
0x18005b3bc  mov     r8d, r14d
0x18005b3bf  lea     rcx, qword_1800C41E8
0x18005b3c6  mov     rdx, rsi
0x18005b3c9  call    ?BipCrmActivityGetActivationAction@@YA?AW4_BI_WORK_ITEM_ACTIVATION_ACTION@@PEAU_BI_CRM_CONTEXT@@PEAU_BI_WORK_ITEM@@W4_CRM_ACTIVITY_ID@@@Z; BipCrmActivityGetActivationAction(_BI_CRM_CONTEXT *,_BI_WORK_ITEM *,_CRM_ACTIVITY_ID)
0x18005b3ce  test    eax, eax
0x18005b3d0  jnz     short loc_18005B3FD
0x18005b3d2  test    r15d, r15d
0x18005b3d5  jns     short loc_18005B3ED
0x18005b3d7  mov     r9b, 1
0x18005b3da  mov     edx, 0FFFFFFFFh
0x18005b3df  mov     r8d, 1200h
0x18005b3e5  mov     rcx, rsi
0x18005b3e8  call    BipCancelWorkItem
0x18005b3ed  cmp     [r12], r12
0x18005b3f1  jz      short loc_18005B418
0x18005b3f3  mov     rcx, rsi
0x18005b3f6  call    BipUnbufferPendingActivations
0x18005b3fb  jmp     short loc_18005B418
0x18005b3fd  movzx   r8d, r14b
0x18005b401  mov     r9b, 1
0x18005b404  or      r8d, 1200h
0x18005b40b  mov     edx, 0FFFFFFFFh
0x18005b410  mov     rcx, rsi
0x18005b413  call    BipCancelWorkItem
0x18005b418  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18005b41d  mov     ecx, cs:dword_1800C3CB0
0x18005b423  mov     edi, 1
0x18005b428  mov     rax, gs:58h
0x18005b431  shl     edi, cl
0x18005b433  mov     ecx, cs:_tls_index
0x18005b439  not     edi
0x18005b43b  mov     cs:dword_1800C3CB4, 0
0x18005b445  mov     rbx, [rax+rcx*8]
0x18005b449  lea     rcx, BipGlobalLock
0x18005b450  mov     eax, 8
0x18005b455  and     [rax+rbx], edi
0x18005b458  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005b45e  mov     eax, 4
0x18005b463  and     [rax+rbx], edi
0x18005b466  test    r15d, r15d
0x18005b469  jns     loc_18005B5A3
0x18005b46f  mov     eax, cs:dword_1800C3098
0x18005b475  cmp     eax, 2
0x18005b478  jbe     loc_18005B59E
0x18005b47e  mov     rcx, cs:qword_1800C30B0
0x18005b485  mov     rax, cs:qword_1800C30A8
0x18005b48c  test    al, 3
0x18005b48e  jz      loc_18005B59E
0x18005b494  mov     rax, rcx
0x18005b497  and     eax, 3
0x18005b49a  cmp     rax, rcx
0x18005b49d  jnz     loc_18005B59E
0x18005b4a3  mov     [rsp+2B0h+var_280], r15d
0x18005b4a8  movups  xmm0, xmmword ptr [rsi+20h]
0x18005b4ac  mov     [rsp+2B0h+var_27C], r14d
0x18005b4b1  lea     rax, [rsp+2B0h+var_280]
0x18005b4b6  mov     [rbp+1B0h+var_40], rax
0x18005b4bd  lea     rcx, _TraceLoggingMetadata
0x18005b4c4  movups  [rsp+2B0h+var_260], xmm0
0x18005b4c9  mov     [rbp+1B0h+var_38], 4
0x18005b4d4  lea     rax, [rsp+2B0h+var_260]
0x18005b4d9  mov     [rbp+1B0h+var_50], rax
0x18005b4e0  lea     rdx, [rsp+2B0h+EventDescriptor]; EventDescriptor
0x18005b4e5  lea     rax, [rsp+2B0h+var_27C]
0x18005b4ea  mov     [rbp+1B0h+var_48], 10h
0x18005b4f5  mov     [rbp+1B0h+var_60], rax
0x18005b4fc  xor     r9d, r9d; RelatedActivityId
0x18005b4ff  movzx   eax, cs:word_1800B32B1
0x18005b506  xor     r8d, r8d; ActivityId
0x18005b509  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], eax
0x18005b50d  mov     rax, cs:off_1800C30A0
0x18005b514  mov     [rbp+1B0h+var_80.Ptr], rax
0x18005b51b  mov     [rbp+1B0h+var_58], 4
0x18005b526  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0B000000h
0x18005b52e  mov     [rsp+2B0h+EventDescriptor.Keyword], 3
0x18005b537  movzx   eax, word ptr [rax]
0x18005b53a  mov     [rbp+1B0h+var_80.Size], eax
0x18005b540  lea     rax, byte_1800B32BB
0x18005b547  mov     [rbp+1B0h+var_70], rax
0x18005b54e  lea     rax, _TraceLoggingMetadataEnd
0x18005b555  sub     eax, ecx
0x18005b557  mov     dword ptr [rbp+1B0h+var_80.0Ch], 2
0x18005b561  mov     [rbp+1B0h+var_68], 48h ; 'H'
0x18005b56b  mov     [rbp+1B0h+var_64], 1
0x18005b575  mov     [rsp+2B0h+var_278], eax
0x18005b579  mov     eax, [rsp+2B0h+var_278]
0x18005b57d  mov     rcx, cs:RegHandle; RegHandle
0x18005b584  lea     rax, [rbp+1B0h+var_80]
0x18005b58b  mov     [rsp+2B0h+UserData], rax; UserData
0x18005b590  mov     [rsp+2B0h+UserDataCount], 5; UserDataCount
0x18005b598  call    cs:__imp_EventWriteTransfer
0x18005b59e  mov     eax, r15d
0x18005b5a1  jmp     short loc_18005B5A5
0x18005b5a3  xor     eax, eax
0x18005b5a5  mov     r14, [rsp+2B0h+var_18]
0x18005b5ad  mov     r13, [rsp+2B0h+var_10]
0x18005b5b5  mov     r12, [rsp+2B0h+arg_18]
0x18005b5bd  mov     rdi, [rsp+2B0h+arg_10]
0x18005b5c5  mov     rbx, [rsp+2B0h+arg_8]
0x18005b5cd  mov     r15, [rsp+2B0h+var_20]
0x18005b5d5  mov     rcx, [rbp+1B0h+var_30]
0x18005b5dc  xor     rcx, rsp; StackCookie
0x18005b5df  call    __security_check_cookie
0x18005b5e4  add     rsp, 2A8h
0x18005b5eb  pop     rsi
0x18005b5ec  pop     rbp
0x18005b5ed  retn
```
