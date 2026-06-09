# BipWorkItemPendingInstanceProcessHamActivities(_BI_WORK_ITEM *)

- ea: `0x180058370`
- end: `0x180058b12`
- name: `?BipWorkItemPendingInstanceProcessHamActivities@@YAJPEAU_BI_WORK_ITEM@@@Z`
- size: `1954`
- prototype: `__int64 __fastcall(struct _BI_WORK_ITEM *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180059ad0`

## callees

- `0x18000d7c0`
- `0x18000da50`
- `0x18000f020`
- `0x180015744`
- `0x180035740`
- `0x180037260`
- `0x180037500`
- `0x180058370`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800584f8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800586c7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058760`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058778`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800587fc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005888a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800588d7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800584f8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800586c7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058760`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180058778`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800587fc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18005888a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800588d7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058516`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058690`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800586f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800587c3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005882b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800588a6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800588ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058993`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058516`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058690`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800586f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800587c3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005882b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800588a6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800588ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180058993`
- `ntdll!RtlFreeHeap` at `0x1800589cb`
- `ntdll!RtlFreeHeap` at `0x1800589cb`
- `ntdll!RtlCopySid` at `0x18005855b`
- `ntdll!RtlCopySid` at `0x18005855b`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180058600`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x180058600`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058aed`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180058aed`
- `RMCLIENT!HamCloseActivity` at `0x180058904`
- `RMCLIENT!HamCloseActivity` at `0x180058904`
- `RMCLIENT!HamStartActivityAsync` at `0x1800588c0`
- `RMCLIENT!HamStartActivityAsync` at `0x1800588c0`

## pseudocode

```c
__int64 __fastcall BipWorkItemPendingInstanceProcessHamActivities(struct _BI_WORK_ITEM *a1)
{
  struct _BI_WORK_ITEM *v1; // r14
  __int64 v2; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v3; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v4; // r15
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v5; // rbx
  int v6; // esi
  unsigned int v7; // r13d
  __int64 v8; // rdi
  unsigned int v9; // r14d
  __int64 v10; // rcx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT **v11; // rsi
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v12; // rbx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v13; // rax
  _WORD *v14; // rcx
  __int128 *v15; // rax
  __int64 v16; // rdx
  __int128 v17; // xmm0
  __int64 v18; // rax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v19; // rcx
  _WORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v23; // rax
  _QWORD *ThreadLocalStoragePointer; // rax
  int v25; // edi
  __int64 v26; // rbx
  __int64 v27; // rax
  char v28; // di
  __int64 v29; // rsi
  _DWORD *v30; // rbx
  char v31; // r15
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rdx
  int v35; // ecx
  __int64 v36; // r13
  char v37; // r15
  __int64 v38; // r12
  __int64 v39; // rcx
  bool v40; // di
  int v41; // r13d
  __int64 v42; // rax
  _QWORD *v43; // rax
  int v44; // edi
  __int64 v45; // rbx
  PVOID v46; // r8
  __int128 v47; // xmm0
  int v49; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v50; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v51; // [rsp+50h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-B0h] BYREF
  struct _BI_WORK_ITEM *v53; // [rsp+68h] [rbp-A0h]
  _BYTE v54[88]; // [rsp+70h] [rbp-98h] BYREF
  PVOID P[2]; // [rsp+C8h] [rbp-40h]
  __int128 v56; // [rsp+D8h] [rbp-30h] BYREF
  _OWORD DestinationSid[4]; // [rsp+E8h] [rbp-20h] BYREF
  int v58; // [rsp+128h] [rbp+20h]
  _OWORD v59[8]; // [rsp+138h] [rbp+30h] BYREF
  __int16 v60; // [rsp+1B8h] [rbp+B0h]
  _BYTE v61[256]; // [rsp+1C8h] [rbp+C0h] BYREF
  unsigned __int16 v62[232]; // [rsp+358h] [rbp+250h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+528h] [rbp+420h] BYREF
  char *v64; // [rsp+538h] [rbp+430h]
  int v65; // [rsp+540h] [rbp+438h]
  int v66; // [rsp+544h] [rbp+43Ch]
  __int64 *v67; // [rsp+548h] [rbp+440h]
  __int64 v68; // [rsp+550h] [rbp+448h]
  __int128 *v69; // [rsp+558h] [rbp+450h]
  __int64 v70; // [rsp+560h] [rbp+458h]

  v1 = a1;
  v53 = a1;
  v58 = 0;
  memset(DestinationSid, 0, sizeof(DestinationSid));
  memset_0(v61, 0, 0x182u);
  memset_0(v62, 0, sizeof(v62));
  *(_OWORD *)P = 0;
  LODWORD(P[1]) = 10;
  memset(v59, 0, sizeof(v59));
  v60 = 0;
  memset(&v54[8], 0, 80);
  BipAcquireGlobalLock(v2);
  v4 = (struct _BI_WORK_ITEM *)((char *)v1 + 144);
  v5 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)*((_QWORD *)v1 + 18);
  v6 = 0;
  if ( v5 == (struct _BI_WORK_ITEM *)((char *)v1 + 144) )
    goto LABEL_54;
  v7 = 0;
  *(_QWORD *)&v56 = 0;
  LODWORD(v51) = 0;
  if ( !v5 )
    goto LABEL_54;
  do
  {
    v8 = *((_QWORD *)v5 + 2);
    if ( (*(_DWORD *)(v8 + 136) & 0x8000) != 0 )
    {
      v9 = v7 + 1;
      v6 = BipTaskInstanceVariableArrayEnsureCapacity(v7 + 1, &v54[8], &v56);
      if ( v6 < 0 )
        break;
      v10 = v7++;
      LODWORD(v51) = v9;
      *(_QWORD *)(v56 + 8 * v10) = v8;
    }
    v3 = *(struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT **)v5;
    v5 = 0;
    if ( v3 != v4 )
      v5 = v3;
  }
  while ( v5 );
  if ( !v7 )
  {
    v1 = v53;
    goto LABEL_54;
  }
  if ( v6 < 0 )
  {
    v11 = *(struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT ***)v4;
    if ( *(struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT **)v4 != v4 && v11 )
    {
      do
      {
        v12 = v11[2];
        RtlAcquireSRWLockExclusive((char *)v12 + 48);
        *((_DWORD *)v12 + 34) |= 0x4000u;
        *((_DWORD *)v12 + 71) = 43526;
        RtlReleaseSRWLockExclusive((char *)v12 + 48);
        v13 = *v11;
        v11 = 0;
        if ( v13 != v4 )
          v11 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT **)v13;
      }
      while ( v11 );
    }
    v1 = v53;
    BipUnbufferPendingActivations(v53);
    v6 = -1073741801;
    goto LABEL_54;
  }
  v1 = v53;
  RtlCopySid(0x44u, DestinationSid, *(PSID *)(*((_QWORD *)v53 + 10) + 24LL));
  v14 = v61;
  v15 = (__int128 *)(*((_QWORD *)v53 + 10) + 160LL);
  v16 = 3;
  do
  {
    v14 += 64;
    v17 = *v15;
    v15 += 8;
    *((_OWORD *)v14 - 8) = v17;
    *((_OWORD *)v14 - 7) = *(v15 - 7);
    *((_OWORD *)v14 - 6) = *(v15 - 6);
    *((_OWORD *)v14 - 5) = *(v15 - 5);
    *((_OWORD *)v14 - 4) = *(v15 - 4);
    *((_OWORD *)v14 - 3) = *(v15 - 3);
    *((_OWORD *)v14 - 2) = *(v15 - 2);
    *((_OWORD *)v14 - 1) = *(v15 - 1);
    --v16;
  }
  while ( v16 );
  *v14 = *(_WORD *)v15;
  v18 = *((_QWORD *)v1 + 11);
  v50 = 464;
  PsmCreateKey(*(_QWORD *)(v18 + 16) + 160LL, v18 + 60, v62, &v50);
  v19 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)v59;
  v20 = (_WORD *)(*((_QWORD *)v1 + 11) + 60LL);
  v21 = 2147483646;
  v22 = 65;
  do
  {
    if ( !v21 )
      break;
    if ( !*v20 )
      break;
    *(_WORD *)v19 = *v20++;
    v19 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)((char *)v19 + 2);
    --v21;
    --v22;
  }
  while ( v22 );
  v23 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)((char *)v19 - 2);
  if ( v22 )
    v23 = v19;
  *(_WORD *)v23 = 0;
  BipLockWatchdogContextDisarmWatchdog(v19);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v25 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v26 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  *(_DWORD *)(v26 + 8) &= v25;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  v27 = 0;
  v50 = 0;
  *(_DWORD *)(v26 + 4) &= v25;
  v28 = 0;
  do
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    LOBYTE(v49) = 0;
    v29 = *(_QWORD *)(v56 + 8 * v27);
    RtlAcquireSRWLockExclusive(v29 + 48);
    v30 = (_DWORD *)(v29 + 136);
    if ( *(_QWORD *)(v29 + 320) != -1 )
    {
LABEL_34:
      v31 = 0;
      goto LABEL_35;
    }
    if ( (*v30 & 0x4000) != 0 )
    {
      v31 = 1;
    }
    else
    {
      RtlReleaseSRWLockExclusive(v29 + 48);
      BipPackageEnsureIsRegistered(*(_DWORD *)(v29 + 140), DestinationSid);
      v32 = BipSystemHamHostIdFindOrCreate(
              *(_QWORD *)(v29 + 64),
              *(_DWORD *)(v29 + 140),
              (unsigned int)DestinationSid,
              (unsigned int)v61,
              (__int64)v62,
              (__int64)v59,
              (__int64)&v49,
              (__int64)&EventDescriptor);
      v33 = v29 + 48;
      if ( v32 >= 0 )
      {
        RtlAcquireSRWLockExclusive(v33);
        v34 = *(_QWORD *)(v29 + 64);
        v35 = (*v30 ^ ((unsigned __int8)v49 << 17)) & 0x20000;
        *(_QWORD *)(v29 + 320) = *(_QWORD *)&EventDescriptor.Id;
        *v30 ^= v35;
        if ( *(_DWORD *)(v34 + 400) || (*(_BYTE *)(*(_QWORD *)(v34 + 72) + 588LL) & 4) == 0 )
          goto LABEL_34;
        v31 = 1;
      }
      else
      {
        v31 = 1;
        RtlAcquireSRWLockExclusive(v33);
        *v30 |= 0x4000u;
        *(_DWORD *)(v29 + 284) = 43521;
      }
    }
LABEL_35:
    RtlReleaseSRWLockExclusive(v29 + 48);
    v36 = *(_QWORD *)(v29 + 64);
    v37 = v28 | v31;
    v38 = -1;
    *(_QWORD *)&EventDescriptor.Id = -1;
    v39 = *(unsigned int *)(v36 + 400);
    if ( !(_DWORD)v39 && (*(_BYTE *)(*(_QWORD *)(v36 + 72) + 588LL) & 4) != 0 )
    {
LABEL_48:
      v40 = 0;
      goto LABEL_49;
    }
    RtlAcquireSRWLockExclusive(v29 + 48);
    if ( (*v30 & 0x4000) != 0 )
    {
      v40 = 0;
    }
    else if ( *(_QWORD *)(v29 + 328) == -1 )
    {
      RtlReleaseSRWLockExclusive(v29 + 48);
      if ( (int)BipSystemHamActivityCreate(
                  qword_1800C4338,
                  v36,
                  v29,
                  *(_DWORD *)(v29 + 140),
                  DestinationSid,
                  (struct _BI_PACKAGE_ID *)v61,
                  v62,
                  (__int64 *)&EventDescriptor) >= 0 )
      {
        RtlAcquireSRWLockExclusive(v29 + 48);
        v42 = *(_QWORD *)&EventDescriptor.Id;
        *v30 |= 0x1000u;
        *(_QWORD *)(v29 + 328) = v42;
        RtlReleaseSRWLockExclusive(v29 + 48);
        if ( (int)HamStartActivityAsync(qword_1800C4338, *(_QWORD *)(v29 + 328), 0, 0) >= 0 )
          goto LABEL_48;
        v41 = 43523;
      }
      else
      {
        v38 = *(_QWORD *)&EventDescriptor.Id;
        v41 = 43522;
      }
      v40 = 1;
      RtlAcquireSRWLockExclusive(v29 + 48);
      *v30 |= 0x4000u;
      *(_DWORD *)(v29 + 284) = v41;
    }
    else
    {
      v40 = (*v30 & 0x2000) != 0;
    }
    RtlReleaseSRWLockExclusive(v29 + 48);
    if ( v38 != -1 )
      HamCloseActivity(qword_1800C4338);
LABEL_49:
    v28 = v37 | v40;
    v27 = v50 + 1;
    v50 = v27;
  }
  while ( (unsigned int)v27 < (unsigned int)v51 );
  BipAcquireGlobalLock(v39);
  if ( !v28 || (v6 = BipUnbufferPendingActivations(v1), v6 >= 0) )
    v6 = 0;
LABEL_54:
  BipLockWatchdogContextDisarmWatchdog(v3);
  v43 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v44 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v45 = v43[(unsigned int)tls_index];
  *(_DWORD *)(v45 + 8) &= v44;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  v46 = P[0];
  *(_DWORD *)(v45 + 4) &= v44;
  if ( v46 )
    RtlFreeHeap(BipHeap, 0, v46);
  if ( v6 < 0
    && (unsigned int)dword_1800C3098 > 2
    && (qword_1800C30A8 & 3) != 0
    && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v47 = 0;
    if ( v1 )
      v47 = *((_OWORD *)v1 + 2);
    v56 = v47;
    v69 = &v56;
    LODWORD(v51) = v6;
    v67 = &v51;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v70 = 16;
    v68 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v64 = byte_1800B3111;
    UserData.Reserved = 2;
    v65 = 75;
    v66 = 1;
    v50 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180058370  mov     r11, rsp
0x180058373  push    rbp
0x180058374  push    rsi
0x180058375  push    r12
0x180058377  push    r14
0x180058379  lea     rbp, [r11-498h]
0x180058380  sub     rsp, 578h
0x180058387  mov     rax, cs:__security_cookie
0x18005838e  xor     rax, rsp
0x180058391  mov     [rbp+490h+var_30], rax
0x180058398  xorps   xmm0, xmm0
0x18005839b  mov     [r11+10h], rbx
0x18005839f  mov     r14, rcx
0x1800583a2  mov     [rsp+590h+var_530], rcx
0x1800583a7  xor     eax, eax
0x1800583a9  mov     [r11+18h], rdi
0x1800583ad  lea     rcx, [rbp+490h+var_3D0]; void *
0x1800583b4  mov     [r11-28h], r15
0x1800583b8  xor     edx, edx; Val
0x1800583ba  mov     [rbp+490h+var_470], eax
0x1800583bd  mov     r8d, 182h; Size
0x1800583c3  movups  [rbp+490h+DestinationSid], xmm0
0x1800583c7  movups  [rbp+490h+var_4A0], xmm0
0x1800583cb  movups  [rbp+490h+var_490], xmm0
0x1800583cf  movups  [rbp+490h+var_480], xmm0
0x1800583d3  call    memset_0
0x1800583d8  xor     edx, edx; Val
0x1800583da  lea     rcx, [rbp+490h+var_240]; void *
0x1800583e1  mov     r8d, 1D0h; Size
0x1800583e7  call    memset_0
0x1800583ec  xorps   xmm0, xmm0
0x1800583ef  xor     eax, eax
0x1800583f1  movups  xmmword ptr [rbp+490h+P], xmm0
0x1800583f5  mov     dword ptr [rbp+490h+P+8], 0Ah
0x1800583fc  movups  [rbp+490h+var_460], xmm0
0x180058400  mov     [rbp+490h+var_3E0], ax
0x180058407  movups  [rbp+490h+var_450], xmm0
0x18005840b  movups  [rbp+490h+var_440], xmm0
0x18005840f  movups  [rbp+490h+var_430], xmm0
0x180058413  movups  [rbp+490h+var_420], xmm0
0x180058417  movups  [rbp+490h+var_410], xmm0
0x18005841e  movups  [rbp+490h+var_400], xmm0
0x180058425  movups  [rbp+490h+var_3F0], xmm0
0x18005842c  movups  [rsp+590h+var_528+8], xmm0
0x180058431  movups  [rbp+490h+var_510], xmm0
0x180058435  movups  [rbp+490h+var_500], xmm0
0x180058439  movups  [rbp+490h+var_4F0], xmm0
0x18005843d  movups  [rbp+490h+var_4E0], xmm0
0x180058441  call    BipAcquireGlobalLock
0x180058446  lea     r15, [r14+90h]
0x18005844d  xor     r12d, r12d
0x180058450  mov     rbx, [r15]
0x180058453  mov     esi, r12d
0x180058456  cmp     rbx, r15
0x180058459  jz      loc_180058956
0x18005845f  mov     [rsp+590h+arg_18], r13
0x180058467  mov     r13d, r12d
0x18005846a  mov     qword ptr [rbp+490h+var_4C0], r12
0x18005846e  mov     dword ptr [rsp+590h+var_548], r12d
0x180058473  test    rbx, rbx
0x180058476  jz      loc_18005894E
0x18005847c  nop     dword ptr [rax+00h]
0x180058480  mov     rdi, [rbx+10h]
0x180058484  test    dword ptr [rdi+88h], 8000h
0x18005848e  jz      short loc_1800584BE
0x180058490  lea     r14d, [r13+1]
0x180058494  mov     ecx, r14d
0x180058497  lea     r8, [rbp+490h+var_4C0]
0x18005849b  lea     rdx, [rsp+590h+var_528+8]
0x1800584a0  call    BipTaskInstanceVariableArrayEnsureCapacity
0x1800584a5  mov     esi, eax
0x1800584a7  test    eax, eax
0x1800584a9  js      short loc_1800584D0
0x1800584ab  mov     rax, qword ptr [rbp+490h+var_4C0]
0x1800584af  mov     ecx, r13d
0x1800584b2  mov     r13d, r14d
0x1800584b5  mov     dword ptr [rsp+590h+var_548], r14d
0x1800584ba  mov     [rax+rcx*8], rdi
0x1800584be  mov     rcx, [rbx]; struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *
0x1800584c1  mov     rbx, r12
0x1800584c4  cmp     rcx, r15
0x1800584c7  cmovnz  rbx, rcx
0x1800584cb  test    rbx, rbx
0x1800584ce  jnz     short loc_180058480
0x1800584d0  test    r13d, r13d
0x1800584d3  jz      loc_180058949
0x1800584d9  test    esi, esi
0x1800584db  jns     short loc_180058545
0x1800584dd  mov     rsi, [r15]
0x1800584e0  cmp     rsi, r15
0x1800584e3  jz      short loc_18005852E
0x1800584e5  test    rsi, rsi
0x1800584e8  jz      short loc_18005852E
0x1800584ea  nop     word ptr [rax+rax+00h]
0x1800584f0  mov     rbx, [rsi+10h]
0x1800584f4  lea     rcx, [rbx+30h]
0x1800584f8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800584fe  or      dword ptr [rbx+88h], 4000h
0x180058508  lea     rcx, [rbx+30h]
0x18005850c  mov     dword ptr [rbx+11Ch], 0AA06h
0x180058516  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005851c  mov     rax, [rsi]
0x18005851f  mov     rsi, r12
0x180058522  cmp     rax, r15
0x180058525  cmovnz  rsi, rax
0x180058529  test    rsi, rsi
0x18005852c  jnz     short loc_1800584F0
0x18005852e  mov     r14, [rsp+590h+var_530]
0x180058533  mov     rcx, r14
0x180058536  call    BipUnbufferPendingActivations
0x18005853b  mov     esi, 0C0000017h
0x180058540  jmp     loc_18005894E
0x180058545  mov     r14, [rsp+590h+var_530]
0x18005854a  lea     rdx, [rbp+490h+DestinationSid]; DestinationSid
0x18005854e  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180058553  mov     r8, [r14+50h]
0x180058557  mov     r8, [r8+18h]; SourceSid
0x18005855b  call    cs:__imp_RtlCopySid
0x180058561  mov     rax, [r14+50h]
0x180058565  lea     rcx, [rbp+490h+var_3D0]
0x18005856c  add     rax, 0A0h
0x180058572  mov     edx, 3
0x180058577  nop     word ptr [rax+rax+00000000h]
0x180058580  lea     rcx, [rcx+80h]
0x180058587  movups  xmm0, xmmword ptr [rax]
0x18005858a  lea     rax, [rax+80h]
0x180058591  movups  xmmword ptr [rcx-80h], xmm0
0x180058595  movups  xmm1, xmmword ptr [rax-70h]
0x180058599  movups  xmmword ptr [rcx-70h], xmm1
0x18005859d  movups  xmm0, xmmword ptr [rax-60h]
0x1800585a1  movups  xmmword ptr [rcx-60h], xmm0
0x1800585a5  movups  xmm1, xmmword ptr [rax-50h]
0x1800585a9  movups  xmmword ptr [rcx-50h], xmm1
0x1800585ad  movups  xmm0, xmmword ptr [rax-40h]
0x1800585b1  movups  xmmword ptr [rcx-40h], xmm0
0x1800585b5  movups  xmm1, xmmword ptr [rax-30h]
0x1800585b9  movups  xmmword ptr [rcx-30h], xmm1
0x1800585bd  movups  xmm0, xmmword ptr [rax-20h]
0x1800585c1  movups  xmmword ptr [rcx-20h], xmm0
0x1800585c5  movups  xmm1, xmmword ptr [rax-10h]
0x1800585c9  movups  xmmword ptr [rcx-10h], xmm1
0x1800585cd  sub     rdx, 1
0x1800585d1  jnz     short loc_180058580
0x1800585d3  movzx   eax, word ptr [rax]
0x1800585d6  lea     r9, [rsp+590h+var_54C]
0x1800585db  mov     [rcx], ax
0x1800585de  lea     r8, [rbp+490h+var_240]
0x1800585e5  mov     rax, [r14+58h]
0x1800585e9  mov     [rsp+590h+var_54C], 1D0h
0x1800585f1  mov     rcx, [rax+10h]
0x1800585f5  lea     rdx, [rax+3Ch]
0x1800585f9  add     rcx, 0A0h
0x180058600  call    cs:__imp_PsmCreateKey
0x180058606  mov     rax, [r14+58h]
0x18005860a  lea     rcx, [rbp+490h+var_460]
0x18005860e  add     rax, 3Ch ; '<'
0x180058612  mov     r8d, 7FFFFFFEh
0x180058618  mov     edx, 41h ; 'A'
0x18005861d  nop     dword ptr [rax]
0x180058620  test    r8, r8
0x180058623  jz      short loc_180058644
0x180058625  movzx   r9d, word ptr [rax]
0x180058629  test    r9w, r9w
0x18005862d  jz      short loc_180058644
0x18005862f  mov     [rcx], r9w
0x180058633  add     rax, 2
0x180058637  add     rcx, 2; struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *
0x18005863b  dec     r8
0x18005863e  sub     rdx, 1
0x180058642  jnz     short loc_180058620
0x180058644  test    rdx, rdx
0x180058647  lea     rax, [rcx-2]
0x18005864b  cmovnz  rax, rcx
0x18005864f  mov     [rax], r12w
0x180058653  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180058658  mov     ecx, cs:dword_1800C3CB0
0x18005865e  mov     edi, 1
0x180058663  mov     rax, gs:58h
0x18005866c  shl     edi, cl
0x18005866e  mov     ecx, cs:_tls_index
0x180058674  not     edi
0x180058676  mov     cs:dword_1800C3CB4, r12d
0x18005867d  mov     rbx, [rax+rcx*8]
0x180058681  lea     rcx, BipGlobalLock
0x180058688  mov     eax, 8
0x18005868d  and     [rax+rbx], edi
0x180058690  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180058696  mov     ecx, 4
0x18005869b  mov     eax, r12d
0x18005869e  mov     [rsp+590h+var_54C], eax
0x1800586a2  and     [rcx+rbx], edi
0x1800586a5  xor     dil, dil
0x1800586a8  test    r13d, r13d
0x1800586ab  jz      loc_18005892C
0x1800586b1  mov     rcx, qword ptr [rbp+490h+var_4C0]
0x1800586b5  mov     qword ptr [rsp+590h+EventDescriptor.Id], r12
0x1800586ba  mov     byte ptr [rsp+590h+var_550], 0
0x1800586bf  mov     rsi, [rcx+rax*8]
0x1800586c3  lea     rcx, [rsi+30h]
0x1800586c7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800586cd  cmp     qword ptr [rsi+140h], 0FFFFFFFFFFFFFFFFh
0x1800586d5  lea     rbx, [rsi+88h]
0x1800586dc  jnz     loc_1800587BC
0x1800586e2  test    dword ptr [rbx], 4000h
0x1800586e8  jz      short loc_1800586F2
0x1800586ea  mov     r15b, 1
0x1800586ed  jmp     loc_1800587BF
0x1800586f2  lea     rcx, [rsi+30h]
0x1800586f6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800586fc  mov     ecx, [rsi+8Ch]; SessionId
0x180058702  lea     r8, [rbp+490h+var_2D0]
0x180058709  lea     rdx, [rbp+490h+DestinationSid]; Sid1
0x18005870d  call    BipPackageEnsureIsRegistered
0x180058712  mov     edx, [rsi+8Ch]
0x180058718  lea     rax, [rsp+590h+EventDescriptor]
0x18005871d  mov     rcx, [rsi+40h]
0x180058721  lea     r9, [rbp+490h+var_3D0]
0x180058728  mov     qword ptr [rsp+590h+var_558], rax
0x18005872d  lea     r8, [rbp+490h+DestinationSid]
0x180058731  lea     rax, [rsp+590h+var_550]
0x180058736  mov     [rsp+590h+var_560], rax
0x18005873b  lea     rax, [rbp+490h+var_460]
0x18005873f  mov     [rsp+590h+UserData], rax
0x180058744  lea     rax, [rbp+490h+var_240]
0x18005874b  mov     qword ptr [rsp+590h+UserDataCount], rax
0x180058750  call    BipSystemHamHostIdFindOrCreate
0x180058755  lea     rcx, [rsi+30h]
0x180058759  test    eax, eax
0x18005875b  jns     short loc_180058778
0x18005875d  mov     r15b, 1
0x180058760  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180058766  or      dword ptr [rbx], 4000h
0x18005876c  mov     dword ptr [rsi+11Ch], 0AA01h
0x180058776  jmp     short loc_1800587BF
0x180058778  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18005877e  movzx   ecx, byte ptr [rsp+590h+var_550]
0x180058783  mov     rdx, [rsi+40h]
0x180058787  mov     rax, qword ptr [rsp+590h+EventDescriptor.Id]
0x18005878c  shl     ecx, 11h
0x18005878f  xor     ecx, [rbx]
0x180058791  and     ecx, 20000h
0x180058797  mov     [rsi+140h], rax
0x18005879e  xor     [rbx], ecx
0x1800587a0  mov     ecx, [rdx+190h]
0x1800587a6  test    ecx, ecx
0x1800587a8  jnz     short loc_1800587BC
0x1800587aa  mov     rax, [rdx+48h]
0x1800587ae  test    byte ptr [rax+24Ch], 4
0x1800587b5  jz      short loc_1800587BC
0x1800587b7  mov     r15b, 1
0x1800587ba  jmp     short loc_1800587BF
0x1800587bc  xor     r15b, r15b
0x1800587bf  lea     rcx, [rsi+30h]
0x1800587c3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800587c9  mov     r13, [rsi+40h]
0x1800587cd  or      r15b, dil
0x1800587d0  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800587d7  mov     qword ptr [rsp+590h+EventDescriptor.Id], r12
0x1800587dc  mov     ecx, [r13+190h]
0x1800587e3  test    ecx, ecx
0x1800587e5  jnz     short loc_1800587F8
0x1800587e7  mov     rax, [r13+48h]
0x1800587eb  test    byte ptr [rax+24Ch], 4
0x1800587f2  jnz     loc_18005890C
0x1800587f8  lea     rcx, [rsi+30h]
0x1800587fc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180058802  mov     edi, [rbx]
0x180058804  bt      edi, 0Eh
0x180058808  jnb     short loc_180058812
0x18005880a  xor     dil, dil
0x18005880d  jmp     loc_1800588EA
0x180058812  cmp     [rsi+148h], r12
0x180058819  jz      short loc_180058827
0x18005881b  shr     edi, 0Dh
0x18005881e  and     dil, 1
0x180058822  jmp     loc_1800588EA
0x180058827  lea     rcx, [rsi+30h]
0x18005882b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180058831  mov     r9d, [rsi+8Ch]
0x180058838  lea     rax, [rsp+590h+EventDescriptor]
0x18005883d  mov     rcx, cs:qword_1800C4338
0x180058844  mov     r8, rsi
0x180058847  mov     qword ptr [rsp+590h+var_558], rax
0x18005884c  mov     rdx, r13
0x18005884f  lea     rax, [rbp+490h+var_240]
0x180058856  mov     [rsp+590h+var_560], rax
0x18005885b  lea     rax, [rbp+490h+var_3D0]
0x180058862  mov     [rsp+590h+UserData], rax
0x180058867  lea     rax, [rbp+490h+DestinationSid]
0x18005886b  mov     qword ptr [rsp+590h+UserDataCount], rax
0x180058870  call    BipSystemHamActivityCreate
0x180058875  test    eax, eax
0x180058877  jns     short loc_180058886
0x180058879  mov     r12, qword ptr [rsp+590h+EventDescriptor.Id]
0x18005887e  mov     r13d, 0AA02h
0x180058884  jmp     short loc_1800588D0
0x180058886  lea     rcx, [rsi+30h]
0x18005888a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180058890  mov     rax, qword ptr [rsp+590h+EventDescriptor.Id]
0x180058895  lea     rcx, [rsi+30h]
  ... truncated ...
```
