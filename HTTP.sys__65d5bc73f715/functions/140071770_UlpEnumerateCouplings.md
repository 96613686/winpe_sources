# UlpEnumerateCouplings

- ea: `0x140071770`
- end: `0x140071f4f`
- name: `UlpEnumerateCouplings`
- size: `2015`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140060e04`
- `0x140062c3c`
- `0x140071678`
- `0x1400ce05c`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d08`
- `0x14005dfd0`
- `0x14005e030`
- `0x1400705d0`
- `0x140071770`
- `0x14009620c`
- `0x1400a031c`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3974`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140071c1a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140071c1a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140071d44`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140071d44`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140071a71`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140071a71`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140071ca0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140071ca0`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140071cf8`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140071cf8`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140071f06`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140071f06`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140071c42`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140071c42`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140071c7e`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140071c7e`
- `ntoskrnl!KeSetEvent` at `0x140071d62`
- `ntoskrnl!KeSetEvent` at `0x140071d62`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140071cc9`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140071cc9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140071bde`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140071bde`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007182e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071898`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007199e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400719c3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007182e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140071898`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007199e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400719c3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400717d5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140071869`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400717d5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140071869`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140071822`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007188c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140071822`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14007188c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071992`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400719b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140071992`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400719b7`
- `ntoskrnl!IoGetCurrentProcess` at `0x140071b0c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140071b0c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007190b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071928`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007190b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140071928`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400717c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071858`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400718f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071917`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400717c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071858`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400718f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140071917`

## pseudocode

```c
void __fastcall UlpEnumerateCouplings(
        __int64 a1,
        __int64 a2,
        void (__fastcall *a3)(char *, _QWORD, __int64),
        __int64 a4,
        __int64 a5)
{
  char *v8; // rbx
  char *i; // rsi
  volatile signed __int32 *v10; // rdx
  signed __int32 v11; // eax
  signed __int32 v12; // ecx
  int v13; // eax
  __int64 v14; // rsi
  __int64 v15; // rdx
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // r8
  _QWORD *v20; // rdx
  volatile signed __int32 *v21; // rdx
  volatile signed __int32 *v22; // rdx
  int v23; // eax
  __int64 v24; // rsi
  int v25; // edi
  bool v26; // zf
  unsigned __int64 v27; // rdi
  int v28; // eax
  __int64 v29; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v31; // r9
  void *CurrentServerSilo; // rbp
  __int64 v33; // rcx
  __int64 v34; // rdi
  USHORT CurrentNodeNumber; // ax
  char v36; // si
  __int64 v37; // rax
  __int64 v38; // r14
  ULONG v39; // esi
  ULONG_PTR v40; // rdx
  int v41; // ecx
  __int64 v42; // rsi
  int v43; // eax
  __int64 v44; // [rsp+40h] [rbp-D8h] BYREF
  __int128 v45; // [rsp+48h] [rbp-D0h]
  _DWORD v46[24]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)&v45 = a4;
  v44 = a5;
  v8 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qPqqq(a5, a2, a3, a1, a2, a3, a4, a5, v44);
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  for ( i = *(char **)(a1 + 8); i != (char *)(a1 + 8); i = *(char **)i )
  {
    v10 = (volatile signed __int32 *)&i[-a2 + 20];
    while ( 1 )
    {
      v11 = *v10;
      if ( !*v10 )
        break;
      v12 = v11 + 1;
      if ( UxDebugCheckRefcount && v12 <= -1 )
        UlBugCheckEx(3u, (ULONG_PTR)v10, 0x21u, v12);
      if ( v11 == _InterlockedCompareExchange(v10, v12, v11) )
      {
        ExReleasePushLockSharedEx(a1, 0);
        KeLeaveCriticalRegion();
        if ( v8 )
        {
          v43 = _InterlockedDecrement((volatile signed __int32 *)v8 + 5);
          if ( UxDebugCheckRefcount && v43 <= -1 )
            UlBugCheckEx(3u, (ULONG_PTR)(v8 + 20), 0x21u, v43);
          if ( !v43 )
            UlpFreeCoupling(v8, 0);
        }
        a3(&i[-a2], v45, v44);
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(a1, 0);
        v8 = &i[-a2];
        break;
      }
    }
  }
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  if ( !v8 )
    goto LABEL_34;
  v13 = _InterlockedDecrement((volatile signed __int32 *)v8 + 5);
  if ( UxDebugCheckRefcount && v13 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v8 + 20), 0x21u, v13);
  if ( v13 )
    goto LABEL_34;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v8, 0);
  v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 8) + 264LL) + 8LL * *(unsigned __int16 *)(*((_QWORD *)v8 + 7) + 56LL));
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*((_QWORD *)v8 + 7) + 944LL, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v14, 0);
  v15 = *((_QWORD *)v8 + 3);
  v16 = v8 + 24;
  if ( *(char **)(v15 + 8) != v8 + 24 )
    goto LABEL_51;
  v17 = (_QWORD *)*((_QWORD *)v8 + 4);
  if ( (_QWORD *)*v17 != v16
    || (*v17 = v15,
        *(_QWORD *)(v15 + 8) = v17,
        *v16 = 0,
        *((_QWORD *)v8 + 4) = 0,
        v18 = v8 + 40,
        v19 = *((_QWORD *)v8 + 5),
        *(char **)(v19 + 8) != v8 + 40)
    || (v20 = (_QWORD *)*((_QWORD *)v8 + 6), (_QWORD *)*v20 != v18) )
  {
LABEL_51:
    __fastfail(3u);
  }
  *v20 = v19;
  *(_QWORD *)(v19 + 8) = v20;
  *v18 = 0;
  *((_QWORD *)v8 + 6) = 0;
  ExReleasePushLockExclusiveEx(v14, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*((_QWORD *)v8 + 7) + 944LL, 0);
  KeLeaveCriticalRegion();
  v21 = (volatile signed __int32 *)*((_QWORD *)v8 + 11);
  if ( v21 )
  {
    v28 = _InterlockedDecrement(v21);
    if ( UxDebugCheckRefcount && v28 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v21, 0xEu, v28);
    if ( !v28 )
      UlConsumerCleanupCompletion(*((_QWORD *)v8 + 11));
    *((_QWORD *)v8 + 11) = 0;
  }
  v22 = (volatile signed __int32 *)*((_QWORD *)v8 + 8);
  v23 = _InterlockedDecrement(v22);
  if ( UxDebugCheckRefcount && v23 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v22, 0xEu, v23);
  if ( !v23 )
    UlFreeRequestQueue(*((PVOID *)v8 + 8));
  v24 = *((_QWORD *)v8 + 7);
  *((_QWORD *)v8 + 8) = 0;
  v25 = _InterlockedDecrement((volatile signed __int32 *)(v24 + 40));
  if ( UxDebugCheckRefcount && v25 <= -1 )
    UlBugCheckEx(3u, v24 + 40, 0xEu, v25);
  if ( v25 )
    goto LABEL_26;
  v29 = v24 + 64;
  CurrentProcess = IoGetCurrentProcess();
  CurrentServerSilo = *(void **)(v24 + 1088);
  v33 = *(_QWORD *)(v24 + 64);
  if ( UxSystemProcess == CurrentProcess )
  {
    if ( v33 || *(_QWORD *)(v24 + 80) || *(_QWORD *)(v24 + 96) )
      UlBugCheckEx(1u, v24 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( !KeGetCurrentIrql() )
    {
      v36 = 0;
      v45 = 0;
      if ( CurrentServerSilo == (void *)-1LL )
      {
        v38 = *((_QWORD *)&v45 + 1);
      }
      else
      {
        v37 = PsAttachSiloToCurrentThread(CurrentServerSilo);
        v38 = v37;
        v36 = 1;
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
        {
          WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v37, CurrentServerSilo);
          UlFreeHttpConnection(v29);
LABEL_61:
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v38);
          PsDetachSiloFromCurrentThread(v38);
          goto LABEL_26;
        }
      }
      UlFreeHttpConnection(v29);
      if ( !v36 )
        goto LABEL_26;
      goto LABEL_61;
    }
    v39 = 0;
    if ( (unsigned int)dword_1401A3F08 > 1 )
    {
      v39 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
      if ( byte_1401A3F20 )
        v39 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
    }
    if ( CurrentServerSilo == (void *)-1LL )
      CurrentServerSilo = (void *)PsGetCurrentServerSilo();
    *(_QWORD *)(v29 + 32) = CurrentServerSilo;
    v44 = 0;
    if ( CurrentServerSilo )
      ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
    PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v44);
    v40 = v44 + 24;
    v41 = _InterlockedIncrement((volatile signed __int32 *)(v44 + 24));
    if ( UxDebugCheckRefcount && v41 <= -1 )
      UlBugCheckEx(3u, v40, 0xDu, v41);
    *(_BYTE *)(v29 + 24) = 1;
    v42 = *(_QWORD *)(qword_1401A3F10 + 8LL * v39);
    *(_QWORD *)(v29 + 16) = UlFreeHttpConnection;
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v42 + 16), (PSLIST_ENTRY)v29) )
    {
      KeSetEvent((PRKEVENT)(v42 + 32), 0, 0);
      UlpActivateThreadPoolQueue((PVOID)v42);
    }
  }
  else
  {
    if ( v33 || *(_QWORD *)(v24 + 80) || *(_QWORD *)(v24 + 96) )
      UlBugCheckEx(1u, v24 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    LOBYTE(v31) = 1;
    UlThreadPoolEnqueueWorkItem(0, v24 + 64, UlFreeHttpConnection, v31, CurrentServerSilo, -1);
  }
LABEL_26:
  v26 = UxDebugDisableLookaside == 0;
  *((_QWORD *)v8 + 7) = 0;
  *((_DWORD *)v8 + 4) = 1969441909;
  if ( v26 )
  {
    if ( UxCompactMode )
    {
      v34 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v34, v8, CurrentNodeNumber);
    }
    else
    {
      v27 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v8 + 1) << 7);
      if ( !*(_BYTE *)(v27 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v27 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v27 + 64), v8);
    }
  }
  else
  {
    memset(v46, 0, sizeof(v46));
    v46[10] = dword_1401A0928;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A0938)(v8, v46);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
LABEL_34:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 33, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  }
}

```

## disassembly

```asm
0x140071770  push    rbx
0x140071772  push    rbp
0x140071773  push    rsi
0x140071774  push    rdi
0x140071775  push    r12
0x140071777  push    r13
0x140071779  push    r14
0x14007177b  push    r15
0x14007177d  sub     rsp, 0D8h
0x140071784  mov     rax, cs:__security_cookie
0x14007178b  xor     rax, rsp
0x14007178e  mov     [rsp+118h+var_58], rax
0x140071796  mov     rbp, rcx
0x140071799  mov     qword ptr [rsp+118h+var_D0], r9
0x14007179e  mov     rcx, [rsp+118h+arg_20]
0x1400717a6  xor     r14d, r14d
0x1400717a9  mov     [rsp+118h+var_D8], rcx
0x1400717ae  mov     r13, r8
0x1400717b1  mov     r12, rdx
0x1400717b4  mov     ebx, r14d
0x1400717b7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400717be  jnz     loc_140071DCA
0x1400717c4  call    cs:__imp_KeEnterCriticalRegion
0x1400717cb  nop     dword ptr [rax+rax+00h]
0x1400717d0  xor     edx, edx
0x1400717d2  mov     rcx, rbp
0x1400717d5  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400717dc  nop     dword ptr [rax+rax+00h]
0x1400717e1  mov     rsi, [rbp+8]
0x1400717e5  lea     r15, [rbp+8]
0x1400717e9  mov     edi, 0FFFFFFFFh
0x1400717ee  cmp     rsi, r15
0x1400717f1  jz      loc_140071887
0x1400717f7  mov     r14, rsi
0x1400717fa  sub     r14, r12
0x1400717fd  lea     rdx, [r14+14h]; BugCheckParameter2
0x140071801  mov     eax, [rdx]
0x140071803  test    eax, eax
0x140071805  jz      short loc_140071878
0x140071807  cmp     cs:UxDebugCheckRefcount, 0
0x14007180e  lea     ecx, [rax+1]
0x140071811  jnz     loc_140071BFE
0x140071817  lock cmpxchg [rdx], ecx
0x14007181b  jnz     short loc_140071801
0x14007181d  xor     edx, edx
0x14007181f  mov     rcx, rbp
0x140071822  call    cs:__imp_ExReleasePushLockSharedEx
0x140071829  nop     dword ptr [rax+rax+00h]
0x14007182e  call    cs:__imp_KeLeaveCriticalRegion
0x140071835  nop     dword ptr [rax+rax+00h]
0x14007183a  test    rbx, rbx
0x14007183d  jnz     loc_140071E6D
0x140071843  mov     r8, [rsp+118h+var_D8]
0x140071848  mov     rcx, r14
0x14007184b  mov     rdx, qword ptr [rsp+118h+var_D0]
0x140071850  mov     rax, r13
0x140071853  call    _guard_dispatch_icall
0x140071858  call    cs:__imp_KeEnterCriticalRegion
0x14007185f  nop     dword ptr [rax+rax+00h]
0x140071864  xor     edx, edx
0x140071866  mov     rcx, rbp
0x140071869  call    cs:__imp_ExAcquirePushLockSharedEx
0x140071870  nop     dword ptr [rax+rax+00h]
0x140071875  mov     rbx, r14
0x140071878  mov     rsi, [rsi]
0x14007187b  cmp     rsi, r15
0x14007187e  jnz     loc_1400717F7
0x140071884  xor     r14d, r14d
0x140071887  xor     edx, edx
0x140071889  mov     rcx, rbp
0x14007188c  call    cs:__imp_ExReleasePushLockSharedEx
0x140071893  nop     dword ptr [rax+rax+00h]
0x140071898  call    cs:__imp_KeLeaveCriticalRegion
0x14007189f  nop     dword ptr [rax+rax+00h]
0x1400718a4  test    rbx, rbx
0x1400718a7  jz      loc_140071AC1
0x1400718ad  lea     rdx, [rbx+14h]; BugCheckParameter2
0x1400718b1  mov     eax, edi
0x1400718b3  lock xadd [rdx], eax
0x1400718b7  dec     eax
0x1400718b9  cmp     cs:UxDebugCheckRefcount, 0
0x1400718c0  jnz     loc_140071B5F
0x1400718c6  test    eax, eax
0x1400718c8  jnz     loc_140071AC1
0x1400718ce  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400718d5  jnz     loc_140071DEB
0x1400718db  mov     rax, [rbx+38h]
0x1400718df  movzx   edx, word ptr [rax+38h]
0x1400718e3  mov     rax, [rbx+40h]
0x1400718e7  mov     rcx, [rax+108h]
0x1400718ee  mov     rsi, [rcx+rdx*8]
0x1400718f2  call    cs:__imp_KeEnterCriticalRegion
0x1400718f9  nop     dword ptr [rax+rax+00h]
0x1400718fe  mov     rcx, [rbx+38h]
0x140071902  xor     edx, edx
0x140071904  add     rcx, 3B0h
0x14007190b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140071912  nop     dword ptr [rax+rax+00h]
0x140071917  call    cs:__imp_KeEnterCriticalRegion
0x14007191e  nop     dword ptr [rax+rax+00h]
0x140071923  xor     edx, edx
0x140071925  mov     rcx, rsi
0x140071928  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14007192f  nop     dword ptr [rax+rax+00h]
0x140071934  mov     rdx, [rbx+18h]
0x140071938  lea     rax, [rbx+18h]
0x14007193c  cmp     [rdx+8], rax
0x140071940  jnz     loc_140071BB4
0x140071946  mov     rcx, [rax+8]
0x14007194a  cmp     [rcx], rax
0x14007194d  jnz     loc_140071BB4
0x140071953  mov     [rcx], rdx
0x140071956  mov     [rdx+8], rcx
0x14007195a  mov     [rax], r14
0x14007195d  mov     [rax+8], r14
0x140071961  lea     rax, [rbx+28h]
0x140071965  mov     r8, [rax]
0x140071968  cmp     [r8+8], rax
0x14007196c  jnz     loc_140071BB4
0x140071972  mov     rdx, [rax+8]
0x140071976  cmp     [rdx], rax
0x140071979  jnz     loc_140071BB4
0x14007197f  mov     [rdx], r8
0x140071982  mov     rcx, rsi
0x140071985  mov     [r8+8], rdx
0x140071989  xor     edx, edx
0x14007198b  mov     [rax], r14
0x14007198e  mov     [rax+8], r14
0x140071992  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140071999  nop     dword ptr [rax+rax+00h]
0x14007199e  call    cs:__imp_KeLeaveCriticalRegion
0x1400719a5  nop     dword ptr [rax+rax+00h]
0x1400719aa  mov     rcx, [rbx+38h]
0x1400719ae  xor     edx, edx
0x1400719b0  add     rcx, 3B0h
0x1400719b7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400719be  nop     dword ptr [rax+rax+00h]
0x1400719c3  call    cs:__imp_KeLeaveCriticalRegion
0x1400719ca  nop     dword ptr [rax+rax+00h]
0x1400719cf  mov     rdx, [rbx+58h]; BugCheckParameter2
0x1400719d3  test    rdx, rdx
0x1400719d6  jnz     loc_140071AE2
0x1400719dc  mov     rdx, [rbx+40h]; BugCheckParameter2
0x1400719e0  mov     eax, edi
0x1400719e2  lock xadd [rdx], eax
0x1400719e6  dec     eax
0x1400719e8  cmp     cs:UxDebugCheckRefcount, 0
0x1400719ef  jnz     loc_140071B7B
0x1400719f5  test    eax, eax
0x1400719f7  jz      loc_140071EBF
0x1400719fd  mov     rsi, [rbx+38h]
0x140071a01  mov     [rbx+40h], r14
0x140071a05  lea     rdx, [rsi+28h]; BugCheckParameter2
0x140071a09  lock xadd [rdx], edi
0x140071a0d  dec     edi
0x140071a0f  cmp     cs:UxDebugCheckRefcount, 0
0x140071a16  jnz     loc_140071B97
0x140071a1c  test    edi, edi
0x140071a1e  jz      loc_140071B08
0x140071a24  cmp     cs:UxDebugDisableLookaside, 0
0x140071a2b  mov     [rbx+38h], r14
0x140071a2f  mov     dword ptr [rbx+10h], 75634C75h
0x140071a36  jnz     loc_140071F17
0x140071a3c  cmp     cs:UxCompactMode, 0
0x140071a43  jnz     loc_140071BD7
0x140071a49  mov     edi, [rbx]
0x140071a4b  mov     rcx, cs:qword_1401A0910
0x140071a52  inc     edi
0x140071a54  shl     rdi, 7
0x140071a58  add     rdi, rcx
0x140071a5b  movzx   eax, byte ptr [rdi+0B0h]
0x140071a62  test    al, al
0x140071a64  jz      loc_140071E5F
0x140071a6a  mov     rdx, rbx; Entry
0x140071a6d  lea     rcx, [rdi+40h]; Lookaside
0x140071a71  call    cs:__imp_ExFreeToLookasideListEx
0x140071a78  nop     dword ptr [rax+rax+00h]
0x140071a7d  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140071a84  jnz     short loc_140071AAB
0x140071a86  mov     rcx, [rsp+118h+var_58]
0x140071a8e  xor     rcx, rsp; StackCookie
0x140071a91  call    __security_check_cookie
0x140071a96  add     rsp, 0D8h
0x140071a9d  pop     r15
0x140071a9f  pop     r14
0x140071aa1  pop     r13
0x140071aa3  pop     r12
0x140071aa5  pop     rdi
0x140071aa6  pop     rsi
0x140071aa7  pop     rbp
0x140071aa8  pop     rbx
0x140071aa9  retn
0x140071aab  mov     edx, 18h
0x140071ab0  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140071ab7  mov     ecx, 408h
0x140071abc  call    WPP_SF_
0x140071ac1  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140071ac8  jz      short loc_140071A86
0x140071aca  mov     edx, 21h ; '!'
0x140071acf  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140071ad6  mov     ecx, 408h
0x140071adb  call    WPP_SF_
0x140071ae0  jmp     short loc_140071A86
0x140071ae2  mov     eax, edi
0x140071ae4  lock xadd [rdx], eax
0x140071ae8  dec     eax
0x140071aea  cmp     cs:UxDebugCheckRefcount, 0
0x140071af1  jnz     loc_140071BBB
0x140071af7  test    eax, eax
0x140071af9  jz      loc_140071EB1
0x140071aff  mov     [rbx+58h], r14
0x140071b03  jmp     loc_1400719DC
0x140071b08  lea     rdi, [rsi+40h]
0x140071b0c  call    cs:__imp_IoGetCurrentProcess
0x140071b13  nop     dword ptr [rax+rax+00h]
0x140071b18  cmp     cs:UxSystemProcess, rax
0x140071b1f  mov     rbp, [rsi+440h]
0x140071b26  mov     rcx, [rdi]
0x140071b29  jnz     loc_140071D9E
0x140071b2f  test    rcx, rcx
0x140071b32  jnz     short loc_140071B44
0x140071b34  cmp     [rdi+10h], rcx
0x140071b38  jnz     short loc_140071B44
0x140071b3a  cmp     [rdi+20h], rcx
0x140071b3e  jz      loc_140071C1A
0x140071b44  mov     r9d, 0E1h; BugCheckParameter4
0x140071b4a  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140071b51  mov     rdx, rdi; BugCheckParameter2
0x140071b54  mov     ecx, 1; BugCheckParameter1
0x140071b59  call    UlBugCheckEx
0x140071b5f  cmp     eax, edi
0x140071b61  jg      loc_1400718C6
0x140071b67  movsxd  r9, eax; BugCheckParameter4
0x140071b6a  mov     ecx, 3; BugCheckParameter1
0x140071b6f  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140071b75  call    UlBugCheckEx
0x140071b7b  cmp     eax, edi
0x140071b7d  jg      loc_1400719F5
0x140071b83  movsxd  r9, eax; BugCheckParameter4
0x140071b86  mov     ecx, 3; BugCheckParameter1
0x140071b8b  mov     r8d, 0Eh; BugCheckParameter3
0x140071b91  call    UlBugCheckEx
0x140071b97  cmp     edi, 0FFFFFFFFh
0x140071b9a  jg      loc_140071A1C
0x140071ba0  movsxd  r9, edi; BugCheckParameter4
0x140071ba3  mov     ecx, 3; BugCheckParameter1
0x140071ba8  mov     r8d, 0Eh; BugCheckParameter3
0x140071bae  call    UlBugCheckEx
0x140071bb4  mov     ecx, 3
0x140071bb9  int     29h; Win8: RtlFailFast(ecx)
0x140071bbb  cmp     eax, edi
0x140071bbd  jg      loc_140071AF7
0x140071bc3  movsxd  r9, eax; BugCheckParameter4
0x140071bc6  mov     ecx, 3; BugCheckParameter1
0x140071bcb  mov     r8d, 0Eh; BugCheckParameter3
0x140071bd1  call    UlBugCheckEx
0x140071bd7  mov     rdi, cs:qword_1401A0910
0x140071bde  call    cs:__imp_KeGetCurrentNodeNumber
0x140071be5  nop     dword ptr [rax+rax+00h]
0x140071bea  movzx   r8d, ax
0x140071bee  mov     rdx, rbx
0x140071bf1  mov     rcx, rdi
0x140071bf4  call    PplFreeToLookasideListProcessor
0x140071bf9  jmp     loc_140071A7D
0x140071bfe  cmp     ecx, edi
0x140071c00  jg      loc_140071817
0x140071c06  movsxd  r9, ecx; BugCheckParameter4
0x140071c09  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140071c0f  mov     ecx, 3; BugCheckParameter1
0x140071c14  call    UlBugCheckEx
0x140071c1a  call    cs:__imp_KeGetCurrentIrql
0x140071c21  nop     dword ptr [rax+rax+00h]
0x140071c26  test    al, al
0x140071c28  jnz     short loc_140071C92
0x140071c2a  xor     sil, sil
0x140071c2d  xorps   xmm0, xmm0
0x140071c30  movups  [rsp+118h+var_D0], xmm0
0x140071c35  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x140071c39  jz      loc_140071D94
0x140071c3f  mov     rcx, rbp
0x140071c42  call    cs:__imp_PsAttachSiloToCurrentThread
0x140071c49  nop     dword ptr [rax+rax+00h]
0x140071c4e  mov     r14, rax
0x140071c51  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140071c58  mov     sil, 1
0x140071c5b  jnz     loc_140071E34
0x140071c61  mov     rcx, rdi
0x140071c64  call    UlFreeHttpConnection
0x140071c69  test    sil, sil
0x140071c6c  jz      short loc_140071C8A
0x140071c6e  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140071c75  jnz     loc_140071ECD
0x140071c7b  mov     rcx, r14
0x140071c7e  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140071c85  nop     dword ptr [rax+rax+00h]
0x140071c8a  xor     r14d, r14d
0x140071c8d  jmp     loc_140071A24
0x140071c92  cmp     cs:dword_1401A3F08, 1
0x140071c99  mov     esi, r14d
0x140071c9c  jbe     short loc_140071CC3
  ... truncated ...
```
