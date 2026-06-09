# BipTaskCompletionCallback

- ea: `0x18000db40`
- end: `0x18000e357`
- name: `BipTaskCompletionCallback`
- size: `2071`
- prototype: `__int64 __fastcall(void *Source1, void *Source2)`
- caller_count: `3`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ab70`
- `0x18003cec0`
- `0x180054430`

## callees

- `0x180005490`
- `0x180005584`
- `0x1800055e8`
- `0x180005640`
- `0x180005670`
- `0x18000568c`
- `0x18000d50c`
- `0x18000d7c0`
- `0x18000da50`
- `0x18000db40`
- `0x18000e470`
- `0x18000e55c`
- `0x18000e610`
- `0x18000f020`
- `0x18000f334`
- `0x18000fbd0`
- `0x18004eba4`
- `0x180057614`
- `0x18005c25c`
- `0x1800638d8`
- `0x18006a8d4`
- `0x18006d364`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtSetEvent` at `0x18000ddf4`
- `ntdll!NtSetEvent` at `0x18000ddf4`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000dcf2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e262`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000dcf2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e262`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000dc7e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000dc7e`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000dcdf`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000dcdf`
- `ntdll!RtlLookupEntryHashTable` at `0x18000dca0`
- `ntdll!RtlLookupEntryHashTable` at `0x18000dca0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dfa2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dfce`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dfa2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000dfce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000df83`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dfb3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e028`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000df83`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dfb3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e028`
- `ntdll!RtlFreeHeap` at `0x18000e29c`
- `ntdll!RtlFreeHeap` at `0x18000e29c`
- `ntdll!RtlAllocateHeap` at `0x18000e23e`
- `ntdll!RtlAllocateHeap` at `0x18000e23e`
- `ntdll!RtlCopySid` at `0x18000e319`
- `ntdll!RtlCopySid` at `0x18000e319`
- `ntdll!RtlLengthSid` at `0x18000e22a`
- `ntdll!RtlLengthSid` at `0x18000e22a`
- `ntdll!RtlPublishWnfStateData` at `0x18000e183`
- `ntdll!RtlPublishWnfStateData` at `0x18000e183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dfd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dfd4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e2a7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e2a7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000dcc7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000dd22`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000dcc7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000dd22`

## pseudocode

```c
BOOLEAN __fastcall BipTaskCompletionCallback(unsigned __int8 *Source1, void *Source2, unsigned __int8 a3, int a4)
{
  PVOID v8; // r13
  __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 i; // rax
  __int64 v13; // rbx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v14; // rcx
  _QWORD *v15; // rdi
  __int128 *v16; // rbp
  int v17; // ecx
  __int64 v18; // r14
  __int64 v19; // rsi
  int v20; // ecx
  __int64 v21; // r13
  __int64 *j; // rax
  __int64 *k; // rcx
  unsigned int v25; // esi
  int v26; // ecx
  __int64 v27; // rdx
  _OWORD *v28; // rax
  _QWORD *v29; // rcx
  int v30; // ecx
  _OWORD *v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rdx
  __int64 v34; // rdx
  _OWORD *v35; // rax
  _QWORD *v36; // rcx
  int v37; // ecx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v39; // esi
  __int64 v40; // rdi
  _DWORD *v41; // r15
  BOOLEAN result; // al
  unsigned int *v43; // r14
  unsigned int v44; // esi
  DWORD CurrentThreadId; // eax
  _QWORD *v46; // r8
  int v47; // r12d
  int v48; // ecx
  __int64 v49; // r14
  void *v50; // rdi
  __int64 v51; // rsi
  _QWORD *v52; // rbp
  _WORD *v53; // rcx
  __int128 *v54; // rax
  __int64 v55; // rdx
  __int128 v56; // xmm0
  ULONG v57; // esi
  PVOID Heap; // rax
  int v60; // [rsp+38h] [rbp-240h] BYREF
  PVOID P; // [rsp+40h] [rbp-238h]
  __int128 v62; // [rsp+50h] [rbp-228h] BYREF
  __int64 v63; // [rsp+60h] [rbp-218h]
  __int128 v64; // [rsp+68h] [rbp-210h] BYREF
  __int128 v65; // [rsp+78h] [rbp-200h]
  __int64 v66; // [rsp+88h] [rbp-1F0h]
  _BYTE v67[400]; // [rsp+90h] [rbp-1E8h] BYREF

  v60 = a4;
  v66 = 0;
  v64 = 0;
  v65 = 0;
  memset_0(v67, 0, 0x182u);
  v8 = 0;
  P = 0;
  BipAcquireGlobalLock(v9);
  v62 = 0;
  v63 = 0;
  v10 = Source1[15]
      + 39
      * (Source1[14]
       + 39
       * (Source1[13]
        + 39
        * (Source1[12]
         + 39
         * (Source1[11]
          + 39
          * (Source1[10]
           + 39
           * (Source1[9]
            + 39
            * (Source1[8]
             + 39
             * (Source1[7]
              + 39
              * (Source1[6]
               + 39
               * (Source1[5]
                + 39
                * (Source1[4]
                 + 39 * (Source1[3] + 39 * (Source1[2] + 39 * (Source1[1] + 39 * (*Source1 + 39 * qword_1800C4148)))))))))))))));
  RtlAcquireSRWLockShared(&qword_1800C4390);
  v11 = 1;
  if ( v10 )
    v11 = v10;
  for ( i = RtlLookupEntryHashTable(qword_1800C4388, v11, &v62); ; i = RtlGetNextEntryHashTable(qword_1800C4388, &v62) )
  {
    v13 = i;
    if ( !i )
    {
      v16 = 0;
      RtlReleaseSRWLockShared(&qword_1800C4390);
      goto LABEL_50;
    }
    if ( RtlCompareMemory(Source1, (const void *)(i + 32), 0x10u) == 16 )
      break;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v13 + 28));
  RtlReleaseSRWLockShared(&qword_1800C4390);
  v14 = *(struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT **)(v13 + 112);
  v15 = (_QWORD *)(v13 + 112);
  v16 = 0;
  if ( v14 != (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)(v13 + 112) )
    v16 = (__int128 *)((char *)v14 - 16);
  while ( 1 )
  {
    if ( !v16 )
      goto LABEL_50;
    if ( RtlCompareMemory(v16, Source2, 0x10u) == 16 )
      break;
    v52 = (_QWORD *)*((_QWORD *)v16 + 2);
    if ( v52 == v15 )
      v16 = 0;
    else
      v16 = (__int128 *)(v52 - 2);
  }
  v17 = *(_DWORD *)(v13 + 400);
  if ( v17 != 2 && v17 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    BipTraceTaskActivationFailed(v13, Source2, (unsigned int)a4);
  BipFreeWaitableEventsData(v16);
  v18 = *((_QWORD *)v16 + 8);
  v19 = *((_QWORD *)v16 + 9);
  v20 = *(_DWORD *)(v18 + 400);
  v21 = *(_QWORD *)(v18 + 80);
  if ( v20 != 2 && v20 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a3 || a4 == -2130509515 )
  {
    *(_DWORD *)(v18 + 464) = a4;
    if ( a4 < 0 )
    {
      if ( a4 != -2147418104 )
        BipRecordWorkItemFailure(v18, 1);
    }
    else
    {
      *(_DWORD *)(v18 + 460) = 0;
      *(_QWORD *)(v18 + 472) = 0;
    }
  }
  BipSetTaskInstanceCompleted(v16, 0);
  if ( v19 )
  {
    if ( (*(_DWORD *)(v19 + 100))-- == 1 )
      *(_DWORD *)(v19 + 48) &= ~0x1000u;
  }
  for ( j = *(__int64 **)(v21 + 96); j != (__int64 *)(v21 + 96); j = (__int64 *)*j )
  {
    if ( (*((_DWORD *)j + 11) & 0x1000) != 0 )
      goto LABEL_29;
    for ( k = (__int64 *)j[3]; k != j + 3; k = (__int64 *)*k )
    {
      if ( (k[6] & 0x1000) != 0 )
        goto LABEL_29;
    }
  }
  NtSetEvent(*(HANDLE *)(v21 + 560), 0);
LABEL_29:
  if ( a3 )
  {
    if ( (*(_DWORD *)(v13 + 24) & 0x20000000) != 0 )
    {
      if ( !(unsigned __int8)BipUtilActTypeIsDebugSupported(*(unsigned int *)(v13 + 400)) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v25 = a4;
      HIDWORD(v66) = a4;
      LODWORD(v66) = 1;
      v64 = *(_OWORD *)(v13 + 32);
      v65 = *v16;
      RtlPublishWnfStateData(*(_QWORD *)(v13 + 576), 0, &v64, 40, 0);
    }
    else
    {
      v25 = a4;
    }
    v26 = *(_DWORD *)(v13 + 400);
    if ( v26 == 2 || !v26 )
    {
      BipUpdateWorkItemInstanceState(v13, v16, 256, &v60);
      v8 = P;
    }
    else
    {
      v8 = P;
    }
  }
  else
  {
    if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(*(unsigned int *)(v13 + 400)) )
      BipUpdateWorkItemInstanceState(v13, v16, 64, &v60);
    v53 = v67;
    v54 = (__int128 *)(*(_QWORD *)(v13 + 80) + 160LL);
    v55 = 3;
    do
    {
      v53 += 64;
      v56 = *v54;
      v54 += 8;
      *((_OWORD *)v53 - 8) = v56;
      *((_OWORD *)v53 - 7) = *(v54 - 7);
      *((_OWORD *)v53 - 6) = *(v54 - 6);
      *((_OWORD *)v53 - 5) = *(v54 - 5);
      *((_OWORD *)v53 - 4) = *(v54 - 4);
      *((_OWORD *)v53 - 3) = *(v54 - 3);
      *((_OWORD *)v53 - 2) = *(v54 - 2);
      *((_OWORD *)v53 - 1) = *(v54 - 1);
      --v55;
    }
    while ( v55 );
    *v53 = *(_WORD *)v54;
    v57 = RtlLengthSid(*(PSID *)(*(_QWORD *)(v13 + 80) + 24LL));
    Heap = RtlAllocateHeap(BipHeap, 0, v57);
    v8 = Heap;
    if ( Heap )
      RtlCopySid(v57, Heap, *(PSID *)(*(_QWORD *)(v13 + 80) + 24LL));
    v25 = a4;
  }
  BipTraceTaskCompletion(v13, v16, a3, v25);
  v27 = *((_QWORD *)v16 + 2);
  v28 = v16 + 1;
  if ( *(__int128 **)(v27 + 8) != v16 + 1 )
    goto LABEL_99;
  v29 = (_QWORD *)*((_QWORD *)v16 + 3);
  if ( (_OWORD *)*v29 != v28 )
    goto LABEL_99;
  *v29 = v27;
  *(_QWORD *)(v27 + 8) = v29;
  *v28 = 0;
  if ( (_QWORD *)*v15 == v15 && *(_QWORD *)(v13 + 224) && *(_QWORD *)(v13 + 232) )
    CempListEntryRemoveAndClear();
  v30 = *(_DWORD *)(v13 + 400);
  if ( v30 != 2 && v30 || (_QWORD *)*v15 == v15 )
  {
    v31 = (_OWORD *)(v13 + 272);
    v32 = *(_QWORD *)(v13 + 272);
    if ( *(_QWORD *)(v32 + 8) == v13 + 272 )
    {
      v33 = *(_QWORD **)(v13 + 280);
      if ( (_OWORD *)*v33 == v31 )
      {
        *v33 = v32;
        *(_QWORD *)(v32 + 8) = v33;
        *v31 = 0;
        goto LABEL_43;
      }
    }
LABEL_99:
    __fastfail(3u);
  }
LABEL_43:
  v34 = *((_QWORD *)v16 + 4);
  v35 = v16 + 2;
  if ( *(__int128 **)(v34 + 8) != v16 + 2 )
    goto LABEL_99;
  v36 = (_QWORD *)*((_QWORD *)v16 + 5);
  if ( (_OWORD *)*v36 != v35 )
    goto LABEL_99;
  *v36 = v34;
  *(_QWORD *)(v34 + 8) = v36;
  *v35 = 0;
  if ( *(_QWORD *)(v13 + 144) == v13 + 144 )
  {
    if ( (v37 = *(_DWORD *)(v13 + 400), v37 != 2) && v37 || (_QWORD *)*v15 == v15 )
      BipCoalesceEntryClearActivateTime(v13 + 336);
  }
  BipUnbufferPendingActivations(v13);
  if ( *((_QWORD *)v16 + 9) )
  {
    v48 = *(_DWORD *)(v13 + 400);
    if ( v48 != 2 && v48 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v49 = *((_QWORD *)v16 + 9);
    if ( (unsigned __int8)BipOkayToDeleteApplicationInstance(v49) )
    {
      v50 = *(void **)(v49 + 40);
      v51 = *(_QWORD *)(v49 + 16);
      BipDeleteApplicationInstance(v49);
      BipConditionallyDeletePackageApplication(v50);
      BipConditionallyDeletePackageInstance(v51);
    }
  }
  *((_QWORD *)v16 + 9) = 0;
LABEL_50:
  BipLockWatchdogContextDisarmWatchdog(v14);
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v39 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v40 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  v41 = (_DWORD *)(v40 + 8);
  *(_DWORD *)(v40 + 8) &= v39;
  result = RtlReleaseSRWLockExclusive(&BipGlobalLock);
  v43 = (unsigned int *)(v40 + 4);
  *(_DWORD *)(v40 + 4) &= v39;
  if ( v16 )
  {
    RtlAcquireSRWLockExclusive(v16 + 3);
    *((_DWORD *)v16 + 34) |= 0x40u;
    RtlReleaseSRWLockExclusive(v16 + 3);
    v44 = 1 << *(_DWORD *)(v13 + 64);
    if ( *v43 >= v44 && IsDebuggerPresent() )
      BipSyncDebugPrintLockBug((struct _BI_LOCK *)(v13 + 56));
    RtlAcquireSRWLockExclusive(v13 + 56);
    CurrentThreadId = GetCurrentThreadId();
    *v41 |= v44;
    *v43 |= v44;
    *(_DWORD *)(v13 + 68) = CurrentThreadId;
    v46 = *(_QWORD **)(v13 + 496);
    if ( *v46 != v13 + 488 )
      goto LABEL_99;
    *((_QWORD *)v16 + 12) = v13 + 488;
    *((_QWORD *)v16 + 13) = v46;
    *v46 = v16 + 6;
    *(_QWORD *)(v13 + 496) = v16 + 6;
    BipWorkItemTpWorkerQueueNewWork(v13);
    v47 = ~(1 << *(_DWORD *)(v13 + 64));
    *(_DWORD *)(v13 + 68) = 0;
    *v41 &= v47;
    result = RtlReleaseSRWLockExclusive(v13 + 56);
    *v43 &= v47;
  }
  if ( v13 )
    result = BipWorkItemDereference(v13);
  if ( v8 )
  {
    BipPackageCheckUpdateStaleFullName(v67, v8);
    return RtlFreeHeap(BipHeap, 0, v8);
  }
  return result;
}

```

## disassembly

```asm
0x18000db40  push    rbx
0x18000db42  push    rsi
0x18000db43  push    rdi
0x18000db44  push    r12
0x18000db46  push    r13
0x18000db48  push    r14
0x18000db4a  push    r15
0x18000db4c  sub     rsp, 240h
0x18000db53  mov     rax, cs:__security_cookie
0x18000db5a  xor     rax, rsp
0x18000db5d  mov     [rsp+278h+var_58], rax
0x18000db65  xorps   xmm0, xmm0
0x18000db68  mov     [rsp+278h+var_248], r9d
0x18000db6d  movzx   r15d, r8b
0x18000db71  mov     [rsp+278h+var_240], r9d
0x18000db76  mov     r14, rdx
0x18000db79  mov     rdi, rcx
0x18000db7c  xor     eax, eax
0x18000db7e  lea     rcx, [rsp+278h+var_1E8]; void *
0x18000db86  xor     edx, edx; Val
0x18000db88  mov     [rsp+278h+var_1F0], rax
0x18000db90  mov     r8d, 182h; Size
0x18000db96  mov     esi, r9d
0x18000db99  movups  [rsp+278h+var_210], xmm0
0x18000db9e  movups  [rsp+278h+var_200], xmm0
0x18000dba3  call    memset_0
0x18000dba8  xor     r13d, r13d
0x18000dbab  mov     [rsp+278h+P], r13
0x18000dbb0  call    BipAcquireGlobalLock
0x18000dbb5  imul    rcx, cs:qword_1800C4148, 27h ; '''
0x18000dbbd  xorps   xmm0, xmm0
0x18000dbc0  movups  [rsp+278h+var_228], xmm0
0x18000dbc5  xor     eax, eax
0x18000dbc7  mov     [rsp+278h+var_218], rax
0x18000dbcc  movzx   eax, byte ptr [rdi]
0x18000dbcf  add     rcx, rax
0x18000dbd2  movzx   eax, byte ptr [rdi+1]
0x18000dbd6  imul    rdx, rcx, 27h ; '''
0x18000dbda  add     rdx, rax
0x18000dbdd  movzx   eax, byte ptr [rdi+2]
0x18000dbe1  imul    rdx, 27h ; '''
0x18000dbe5  add     rdx, rax
0x18000dbe8  movzx   eax, byte ptr [rdi+3]
0x18000dbec  imul    rdx, 27h ; '''
0x18000dbf0  add     rdx, rax
0x18000dbf3  movzx   eax, byte ptr [rdi+4]
0x18000dbf7  imul    rdx, 27h ; '''
0x18000dbfb  add     rdx, rax
0x18000dbfe  movzx   eax, byte ptr [rdi+5]
0x18000dc02  imul    rdx, 27h ; '''
0x18000dc06  add     rdx, rax
0x18000dc09  movzx   eax, byte ptr [rdi+6]
0x18000dc0d  imul    rdx, 27h ; '''
0x18000dc11  add     rdx, rax
0x18000dc14  movzx   eax, byte ptr [rdi+7]
0x18000dc18  imul    rdx, 27h ; '''
0x18000dc1c  add     rdx, rax
0x18000dc1f  movzx   eax, byte ptr [rdi+8]
0x18000dc23  imul    rdx, 27h ; '''
0x18000dc27  add     rdx, rax
0x18000dc2a  movzx   eax, byte ptr [rdi+9]
0x18000dc2e  imul    rdx, 27h ; '''
0x18000dc32  add     rdx, rax
0x18000dc35  movzx   eax, byte ptr [rdi+0Ah]
0x18000dc39  imul    rdx, 27h ; '''
0x18000dc3d  add     rdx, rax
0x18000dc40  movzx   eax, byte ptr [rdi+0Bh]
0x18000dc44  imul    rdx, 27h ; '''
0x18000dc48  add     rdx, rax
0x18000dc4b  movzx   eax, byte ptr [rdi+0Ch]
0x18000dc4f  imul    rdx, 27h ; '''
0x18000dc53  add     rdx, rax
0x18000dc56  movzx   eax, byte ptr [rdi+0Dh]
0x18000dc5a  imul    rdx, 27h ; '''
0x18000dc5e  add     rdx, rax
0x18000dc61  movzx   eax, byte ptr [rdi+0Eh]
0x18000dc65  imul    rcx, rdx, 27h ; '''
0x18000dc69  add     rcx, rax
0x18000dc6c  movzx   eax, byte ptr [rdi+0Fh]
0x18000dc70  imul    rbx, rcx, 27h ; '''
0x18000dc74  lea     rcx, qword_1800C4390
0x18000dc7b  add     rbx, rax
0x18000dc7e  call    cs:__imp_RtlAcquireSRWLockShared
0x18000dc84  mov     rcx, cs:qword_1800C4388
0x18000dc8b  lea     r8, [rsp+278h+var_228]
0x18000dc90  test    rbx, rbx
0x18000dc93  mov     r12d, 1
0x18000dc99  mov     edx, r12d
0x18000dc9c  cmovnz  rdx, rbx
0x18000dca0  call    cs:__imp_RtlLookupEntryHashTable
0x18000dca6  mov     [rsp+278h+var_40], rbp
0x18000dcae  mov     rbx, rax
0x18000dcb1  test    rbx, rbx
0x18000dcb4  jz      loc_18000E259
0x18000dcba  lea     rdx, [rax+20h]; Source2
0x18000dcbe  mov     r8d, 10h; Length
0x18000dcc4  mov     rcx, rdi; Source1
0x18000dcc7  call    cs:__imp_RtlCompareMemory
0x18000dccd  cmp     rax, 10h
0x18000dcd1  jz      short loc_18000DCE7
0x18000dcd3  mov     rcx, cs:qword_1800C4388
0x18000dcda  lea     rdx, [rsp+278h+var_228]
0x18000dcdf  call    cs:__imp_RtlGetNextEntryHashTable
0x18000dce5  jmp     short loc_18000DCAE
0x18000dce7  lock inc dword ptr [rbx+1Ch]
0x18000dceb  lea     rcx, qword_1800C4390
0x18000dcf2  call    cs:__imp_RtlReleaseSRWLockShared
0x18000dcf8  mov     rcx, [rbx+70h]
0x18000dcfc  lea     rdi, [rbx+70h]
0x18000dd00  xor     ebp, ebp
0x18000dd02  cmp     rcx, rdi
0x18000dd05  lea     rax, [rcx-10h]
0x18000dd09  cmovnz  rbp, rax
0x18000dd0d  test    rbp, rbp
0x18000dd10  jz      loc_18000E07A
0x18000dd16  mov     r8d, 10h; Length
0x18000dd1c  mov     rdx, r14; Source2
0x18000dd1f  mov     rcx, rbp; Source1
0x18000dd22  call    cs:__imp_RtlCompareMemory
0x18000dd28  cmp     rax, 10h
0x18000dd2c  jnz     loc_18000E0E2
0x18000dd32  mov     ecx, [rbx+190h]
0x18000dd38  cmp     ecx, 2
0x18000dd3b  jnz     loc_18000E2CC
0x18000dd41  test    r15b, r15b
0x18000dd44  jz      loc_18000E26D
0x18000dd4a  mov     rcx, rbp
0x18000dd4d  call    BipFreeWaitableEventsData
0x18000dd52  mov     r14, [rbp+40h]
0x18000dd56  mov     rsi, [rbp+48h]
0x18000dd5a  mov     ecx, [r14+190h]
0x18000dd61  mov     r13, [r14+50h]
0x18000dd65  cmp     ecx, 2
0x18000dd68  jnz     loc_18000E2DE
0x18000dd6e  mov     eax, [rsp+278h+var_248]
0x18000dd72  test    r15b, r15b
0x18000dd75  jz      loc_18000E10D
0x18000dd7b  mov     [r14+1D0h], eax
0x18000dd82  test    eax, eax
0x18000dd84  js      loc_18000E07F
0x18000dd8a  xor     eax, eax
0x18000dd8c  mov     [r14+1CCh], eax
0x18000dd93  mov     [r14+1D8h], rax
0x18000dd9a  xor     edx, edx
0x18000dd9c  mov     rcx, rbp
0x18000dd9f  call    ?BipSetTaskInstanceCompleted@@YAXPEAU_BI_ACTIVATED_TASK_INSTANCE@@W4_BI_TASK_COMPLETION_REASON@@@Z; BipSetTaskInstanceCompleted(_BI_ACTIVATED_TASK_INSTANCE *,_BI_TASK_COMPLETION_REASON)
0x18000dda4  test    rsi, rsi
0x18000dda7  jz      short loc_18000DDB6
0x18000dda9  add     dword ptr [rsi+64h], 0FFFFFFFFh
0x18000ddad  jnz     short loc_18000DDB6
0x18000ddaf  and     dword ptr [rsi+30h], 0FFFFEFFFh
0x18000ddb6  mov     rax, [r13+60h]
0x18000ddba  lea     r8, [r13+60h]
0x18000ddbe  cmp     rax, r8
0x18000ddc1  jz      short loc_18000DDEB
0x18000ddc3  test    dword ptr [rax+2Ch], 1000h
0x18000ddca  jnz     short loc_18000DDFA
0x18000ddcc  mov     rcx, [rax+18h]
0x18000ddd0  lea     rdx, [rax+18h]
0x18000ddd4  cmp     rcx, rdx
0x18000ddd7  jz      loc_18000E072
0x18000dddd  test    dword ptr [rcx+30h], 1000h
0x18000dde4  jnz     short loc_18000DDFA
0x18000dde6  mov     rcx, [rcx]
0x18000dde9  jmp     short loc_18000DDD4
0x18000ddeb  mov     rcx, [r13+230h]; EventHandle
0x18000ddf2  xor     edx, edx; PreviousState
0x18000ddf4  call    cs:__imp_NtSetEvent
0x18000ddfa  test    r15b, r15b
0x18000ddfd  jz      loc_18000E18E
0x18000de03  test    dword ptr [rbx+18h], 20000000h
0x18000de0a  jnz     loc_18000E12E
0x18000de10  mov     esi, [rsp+278h+var_248]
0x18000de14  mov     ecx, [rbx+190h]
0x18000de1a  cmp     ecx, 2
0x18000de1d  jnz     loc_18000E2FA
0x18000de23  lea     r9, [rsp+278h+var_240]
0x18000de28  mov     r8d, 100h
0x18000de2e  mov     rdx, rbp
0x18000de31  mov     rcx, rbx
0x18000de34  call    ?BipUpdateWorkItemInstanceState@@YAJPEAU_BI_WORK_ITEM@@PEAU_BI_ACTIVATED_TASK_INSTANCE@@W4_BI_WORK_ITEM_INSTANCE_STATE@@PEAX@Z; BipUpdateWorkItemInstanceState(_BI_WORK_ITEM *,_BI_ACTIVATED_TASK_INSTANCE *,_BI_WORK_ITEM_INSTANCE_STATE,void *)
0x18000de39  mov     r13, [rsp+278h+P]
0x18000de3e  mov     r9d, esi
0x18000de41  movzx   r8d, r15b
0x18000de45  mov     rdx, rbp
0x18000de48  mov     rcx, rbx
0x18000de4b  call    BipTraceTaskCompletion
0x18000de50  mov     rdx, [rbp+10h]
0x18000de54  lea     rax, [rbp+10h]
0x18000de58  cmp     [rdx+8], rax
0x18000de5c  jnz     loc_18000E350
0x18000de62  mov     rcx, [rax+8]
0x18000de66  cmp     [rcx], rax
0x18000de69  jnz     loc_18000E350
0x18000de6f  mov     [rcx], rdx
0x18000de72  xorps   xmm0, xmm0
0x18000de75  mov     [rdx+8], rcx
0x18000de79  movups  xmmword ptr [rax], xmm0
0x18000de7c  cmp     [rdi], rdi
0x18000de7f  jnz     short loc_18000DE94
0x18000de81  lea     rcx, [rbx+0E0h]
0x18000de88  mov     rax, [rcx]
0x18000de8b  test    rax, rax
0x18000de8e  jnz     loc_18000E0F6
0x18000de94  mov     ecx, [rbx+190h]
0x18000de9a  cmp     ecx, 2
0x18000de9d  jnz     loc_18000E324
0x18000dea3  cmp     [rdi], rdi
0x18000dea6  jnz     short loc_18000DED6
0x18000dea8  lea     rax, [rbx+110h]
0x18000deaf  mov     rcx, [rax]
0x18000deb2  cmp     [rcx+8], rax
0x18000deb6  jnz     loc_18000E350
0x18000debc  mov     rdx, [rax+8]
0x18000dec0  cmp     [rdx], rax
0x18000dec3  jnz     loc_18000E350
0x18000dec9  mov     [rdx], rcx
0x18000decc  xorps   xmm0, xmm0
0x18000decf  mov     [rcx+8], rdx
0x18000ded3  movups  xmmword ptr [rax], xmm0
0x18000ded6  mov     rdx, [rbp+20h]
0x18000deda  lea     rax, [rbp+20h]
0x18000dede  cmp     [rdx+8], rax
0x18000dee2  jnz     loc_18000E350
0x18000dee8  mov     rcx, [rax+8]
0x18000deec  cmp     [rcx], rax
0x18000deef  jnz     loc_18000E350
0x18000def5  mov     [rcx], rdx
0x18000def8  xorps   xmm0, xmm0
0x18000defb  mov     [rdx+8], rcx
0x18000deff  movups  xmmword ptr [rax], xmm0
0x18000df02  lea     rax, [rbx+90h]
0x18000df09  cmp     [rax], rax
0x18000df0c  jnz     short loc_18000DF26
0x18000df0e  mov     ecx, [rbx+190h]
0x18000df14  cmp     ecx, 2
0x18000df17  jnz     loc_18000E331
0x18000df1d  cmp     [rdi], rdi
0x18000df20  jz      loc_18000E11D
0x18000df26  mov     rcx, rbx
0x18000df29  call    BipUnbufferPendingActivations
0x18000df2e  cmp     qword ptr [rbp+48h], 0
0x18000df33  jnz     loc_18000E09A
0x18000df39  mov     qword ptr [rbp+48h], 0
0x18000df41  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18000df46  mov     ecx, cs:dword_1800C3CB0
0x18000df4c  mov     esi, r12d
0x18000df4f  mov     rax, gs:58h
0x18000df58  shl     esi, cl
0x18000df5a  mov     ecx, cs:_tls_index
0x18000df60  not     esi
0x18000df62  mov     r15d, 8
0x18000df68  mov     cs:dword_1800C3CB4, 0
0x18000df72  mov     rdi, [rax+rcx*8]
0x18000df76  lea     rcx, BipGlobalLock
0x18000df7d  add     r15, rdi
0x18000df80  and     [r15], esi
0x18000df83  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000df89  mov     r14d, 4
0x18000df8f  add     r14, rdi
0x18000df92  and     [r14], esi
0x18000df95  test    rbp, rbp
0x18000df98  jz      loc_18000E031
0x18000df9e  lea     rcx, [rbp+30h]
0x18000dfa2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000dfa8  or      dword ptr [rbp+88h], 40h
0x18000dfaf  lea     rcx, [rbp+30h]
0x18000dfb3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000dfb9  mov     ecx, [rbx+40h]
0x18000dfbc  mov     esi, r12d
0x18000dfbf  shl     esi, cl
0x18000dfc1  cmp     [r14], esi
0x18000dfc4  jnb     loc_18000E2A7
0x18000dfca  lea     rcx, [rbx+38h]
0x18000dfce  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000dfd4  call    cs:__imp_GetCurrentThreadId
0x18000dfda  or      [r15], esi
0x18000dfdd  lea     rdx, [rbx+1E8h]
0x18000dfe4  or      [r14], esi
0x18000dfe7  mov     [rbx+44h], eax
0x18000dfea  mov     r8, [rdx+8]
0x18000dfee  cmp     [r8], rdx
0x18000dff1  jnz     loc_18000E350
0x18000dff7  lea     rax, [rbp+60h]
0x18000dffb  mov     rcx, rbx
0x18000dffe  mov     [rax], rdx
0x18000e001  mov     [rax+8], r8
0x18000e005  mov     [r8], rax
0x18000e008  mov     [rdx+8], rax
0x18000e00c  call    BipWorkItemTpWorkerQueueNewWork
0x18000e011  mov     ecx, [rbx+40h]
0x18000e014  shl     r12d, cl
0x18000e017  lea     rcx, [rbx+38h]
0x18000e01b  not     r12d
0x18000e01e  mov     dword ptr [rbx+44h], 0
0x18000e025  and     [r15], r12d
0x18000e028  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e02e  and     [r14], r12d
0x18000e031  test    rbx, rbx
0x18000e034  jz      short loc_18000E03E
  ... truncated ...
```
