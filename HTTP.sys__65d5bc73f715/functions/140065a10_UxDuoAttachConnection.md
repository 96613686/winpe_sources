# UxDuoAttachConnection

- ea: `0x140065a10`
- end: `0x140066eec`
- name: `UxDuoAttachConnection`
- size: `5340`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140009a90`
- `0x140065220`

## callees

- `0x140003ac0`
- `0x14000a350`
- `0x140049d08`
- `0x1400513f0`
- `0x140058520`
- `0x140061e80`
- `0x140064118`
- `0x140065a10`
- `0x140066f00`
- `0x140067160`
- `0x140067230`
- `0x1400a9b00`
- `0x1400d9980`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c3e6c`
- `0x1401c9cbc`
- `0x1401ca158`
- `0x1401d9f54`
- `0x1401da550`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14006614f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140066519`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14006614f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140066519`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x1400666a0`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x1400666a0`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140066e8b`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x140066e8b`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140066a81`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140066a81`
- `ntoskrnl!KeSetEvent` at `0x140066ea9`
- `ntoskrnl!KeSetEvent` at `0x140066ea9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140066b8e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140066bbf`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140066b8e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140066bbf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006601e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006601e`
- `ntoskrnl!ExAllocatePool3` at `0x140065b5b`
- `ntoskrnl!ExAllocatePool3` at `0x140065b5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065f09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140065f09`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140066012`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140066012`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140065f97`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140065f97`
- `ntoskrnl!KeInitializeSpinLock` at `0x140065cf5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140065e07`
- `ntoskrnl!KeInitializeSpinLock` at `0x140065cf5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140065e07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140065f81`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140065f81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065ed8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065ed8`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140065f24`
- `NETIO!RtlInitializeTimerWheelEntry` at `0x140065f24`

## pseudocode

```c
__int64 __fastcall UxDuoAttachConnection(__int64 a1, __int64 a2, __int64 *a3, _QWORD *a4, int a5)
{
  int v9; // edi
  __int64 Pool3; // rax
  __int64 v11; // rbx
  int v12; // ecx
  __int64 v13; // rsi
  __int64 v14; // r15
  unsigned __int16 v15; // r8
  char i; // cl
  __int64 v17; // rdx
  KIRQL v18; // di
  int v19; // eax
  __int64 v20; // rdi
  int v21; // eax
  _DWORD *v22; // r15
  __int64 (__fastcall *v23)(__int64); // rax
  _DWORD *v24; // rax
  _DWORD *v25; // rdi
  __int64 (__fastcall *v26)(__int64); // rax
  _DWORD *v27; // rax
  _DWORD *v28; // rdi
  int LockArray_high; // esi
  unsigned __int64 v30; // rdi
  _DWORD *v31; // rax
  _DWORD *v32; // rdi
  int v33; // eax
  _QWORD *v34; // rsi
  unsigned int v35; // eax
  unsigned int v36; // eax
  __int64 v37; // r8
  unsigned int v38; // ecx
  unsigned int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // r8
  unsigned int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // r8
  int v45; // eax
  __int64 v46; // rax
  __int64 v47; // rcx
  unsigned int v48; // eax
  unsigned int v49; // eax
  int v50; // r15d
  unsigned __int64 v51; // rdi
  _DWORD *v52; // rax
  _DWORD *v53; // rdi
  int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  __int64 v57; // r8
  __int64 v58; // rcx
  __int64 *v59; // r9
  PVOID v60; // rbx
  ULONG_PTR v61; // rdx
  int v62; // r14d
  __int64 v64; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v66; // rdi
  USHORT v67; // ax
  unsigned int v68; // eax
  int v69; // eax
  void *v70; // rcx
  int v71; // eax
  void *v72; // rcx
  char v73[8]; // [rsp+50h] [rbp-81h] BYREF
  __int64 v74; // [rsp+58h] [rbp-79h] BYREF
  unsigned int v75; // [rsp+60h] [rbp-71h] BYREF
  int v76; // [rsp+64h] [rbp-6Dh] BYREF
  int v77; // [rsp+68h] [rbp-69h] BYREF
  __int64 v78; // [rsp+70h] [rbp-61h] BYREF
  PVOID Object; // [rsp+78h] [rbp-59h] BYREF
  __int64 *v80; // [rsp+80h] [rbp-51h]
  _OWORD v81[2]; // [rsp+90h] [rbp-41h] BYREF
  _OWORD v82[2]; // [rsp+B0h] [rbp-21h] BYREF

  v80 = a3;
  v78 = 0;
  Object = 0;
  memset(v81, 0, 28);
  memset(v82, 0, 28);
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v73[0] = 0;
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qqqqL(1051, 48, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, a1, a2, a3, a4, a5);
  *a3 = 0;
  *a4 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, PVOID *, _QWORD, _QWORD))(a2 + 136))(
         a1,
         25,
         &v78,
         &Object,
         0,
         0);
  if ( v9 < 0 )
  {
    v59 = a3;
    goto LABEL_99;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, char *, _QWORD, _QWORD, _QWORD))(a2 + 136))(a1, 6, v73, 0, 0, 0);
  if ( v9 < 0 )
    goto LABEL_92;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _OWORD *, _OWORD *, _QWORD, _QWORD))(a2 + 136))(
         a1,
         0,
         v81,
         v82,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_92;
  if ( !v73[0] || (a5 & 0x20) == 0 )
  {
    v9 = UlHttpAttachConnection(a1, a2, (_DWORD)a3, (_DWORD)a4, a5);
LABEL_92:
    v60 = Object;
    v74 = 0;
    PsGetPermanentSiloContext(Object, (unsigned int)UxPodMonitorSlot, &v74);
    if ( v60 )
      ObfDereferenceObjectWithTag(v60, 0x43546C55u);
    v61 = v74 + 24;
    v62 = _InterlockedDecrement((volatile signed __int32 *)(v74 + 24));
    if ( UxDebugCheckRefcount && v62 <= -1 )
      UlBugCheckEx(3u, v61, 0xFu, v62);
    if ( !v62 )
      KeSetEvent((PRKEVENT)(v74 + 32), 0, 0);
    Object = 0;
    goto LABEL_98;
  }
  Pool3 = ExAllocatePool3(64, 17536, 1096382549, UxLowPriorityPool, 1);
  v11 = Pool3;
  if ( !Pool3 )
  {
    v9 = -1073741670;
    goto LABEL_92;
  }
  *(_DWORD *)(Pool3 + 4) = 1;
  *(_DWORD *)Pool3 = 1096382549;
  *(_DWORD *)(Pool3 + 17232) = _InterlockedIncrement(&UxDuoConnectionId);
  *(_QWORD *)(Pool3 + 40) = Pool3 + 32;
  *(_QWORD *)(Pool3 + 32) = Pool3 + 32;
  *(_QWORD *)(Pool3 + 56) = Pool3 + 48;
  *(_QWORD *)(Pool3 + 48) = Pool3 + 48;
  *(_QWORD *)(Pool3 + 72) = Pool3 + 64;
  *(_QWORD *)(Pool3 + 64) = Pool3 + 64;
  *(_QWORD *)(Pool3 + 88) = Pool3 + 80;
  *(_QWORD *)(Pool3 + 80) = Pool3 + 80;
  *(_QWORD *)(Pool3 + 104) = Pool3 + 96;
  *(_QWORD *)(Pool3 + 96) = Pool3 + 96;
  *(_QWORD *)(Pool3 + 120) = Pool3 + 112;
  *(_QWORD *)(Pool3 + 112) = Pool3 + 112;
  *(_QWORD *)(Pool3 + 136) = Pool3 + 128;
  *(_QWORD *)(Pool3 + 128) = Pool3 + 128;
  *(_QWORD *)(Pool3 + 152) = Pool3 + 144;
  *(_QWORD *)(Pool3 + 144) = Pool3 + 144;
  *(_QWORD *)(Pool3 + 168) = Pool3 + 160;
  *(_QWORD *)(Pool3 + 160) = Pool3 + 160;
  *(_QWORD *)(Pool3 + 184) = Pool3 + 176;
  *(_QWORD *)(Pool3 + 176) = Pool3 + 176;
  *(_QWORD *)(Pool3 + 200) = Pool3 + 192;
  *(_QWORD *)(Pool3 + 192) = Pool3 + 192;
  *(_QWORD *)(Pool3 + 216) = Pool3 + 208;
  *(_QWORD *)(Pool3 + 208) = Pool3 + 208;
  *(_QWORD *)(Pool3 + 232) = Pool3 + 224;
  *(_QWORD *)(Pool3 + 224) = Pool3 + 224;
  *(_QWORD *)(Pool3 + 248) = Pool3 + 240;
  *(_QWORD *)(Pool3 + 240) = Pool3 + 240;
  *(_QWORD *)(Pool3 + 264) = Pool3 + 256;
  *(_QWORD *)(Pool3 + 256) = Pool3 + 256;
  *(_QWORD *)(Pool3 + 280) = Pool3 + 272;
  *(_QWORD *)(Pool3 + 272) = Pool3 + 272;
  *(_QWORD *)(Pool3 + 296) = Pool3 + 288;
  *(_QWORD *)(Pool3 + 288) = Pool3 + 288;
  v12 = *(_DWORD *)(v78 + 7128);
  *(_QWORD *)(Pool3 + 17192) = 0;
  *(_DWORD *)(Pool3 + 17200) = 0;
  *(_QWORD *)(Pool3 + 17208) = 0;
  *(_DWORD *)(Pool3 + 17204) = v12;
  *(_QWORD *)(Pool3 + 17224) = 1398372437;
  *(_QWORD *)(Pool3 + 17216) = 258;
  memset((void *)(Pool3 + 17072), 0, 0x60u);
  *(_QWORD *)(v11 + 17088) = v11 + 17080;
  *(_QWORD *)(v11 + 17080) = v11 + 17080;
  KeInitializeSpinLock((PKSPIN_LOCK)(v11 + 17072));
  *(_QWORD *)(v11 + 17104) = 0;
  *(_QWORD *)(v11 + 17120) = 0;
  *(_QWORD *)(v11 + 17136) = 0;
  *(_QWORD *)(v11 + 344) = MEMORY[0xFFFFF78000000014];
  *(_DWORD *)(v11 + 17020) = 0xFFFF;
  *(_QWORD *)(v11 + 16960) = 0x10000;
  *(_DWORD *)(v11 + 16976) = -1;
  *(_DWORD *)(v11 + 17000) = 0xFFFF;
  *(_DWORD *)(v11 + 17004) = 0xFFFF;
  *(_QWORD *)(v11 + 17008) = 0x4000;
  *(_QWORD *)(v11 + 16992) = v11 + 16984;
  *(_QWORD *)(v11 + 16984) = v11 + 16984;
  *(_BYTE *)(v11 + 338) = 1;
  *(_DWORD *)(v11 + 17040) = 1;
  *(_DWORD *)(v11 + 17044) = 2;
  *(_OWORD *)(v11 + 17472) = v81[0];
  *(_OWORD *)(v11 + 17484) = *(_OWORD *)((char *)v81 + 12);
  *(_OWORD *)(v11 + 17500) = v82[0];
  *(_OWORD *)(v11 + 17512) = *(_OWORD *)((char *)v82 + 12);
  *(_QWORD *)(v11 + 24) = 1;
  *(_QWORD *)(v11 + 8) = a1;
  *(_QWORD *)(v11 + 16) = a2;
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_dqq(1051, 49, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, *(unsigned int *)(v11 + 17232), v11, a1);
  (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
    *(_QWORD *)(v11 + 8),
    5,
    v11 + 16952,
    0,
    0,
    0);
  KeInitializeSpinLock((PKSPIN_LOCK)(v11 + 16936));
  v13 = v78;
  v14 = *(_QWORD *)(v11 + 16952) + 16LL;
  if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qD(1043, 12, WPP_94ca9e589e4f3da486b24c2e49372186_Traceguids, v11 + 16808, 2);
  memset((void *)(v11 + 16808), 0, 0x80u);
  *(__m128i *)(v11 + 16912) = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(_QWORD *)(v11 + 16824) = v11 + 16936;
  *(_QWORD *)(v11 + 16816) = v14;
  v15 = 0;
  *(_BYTE *)(v11 + 16908) = 1;
  *(_DWORD *)(v11 + 16808) = 2;
  for ( i = BYTE4(UlTimersPerBundle); v15 < WORD2(UlTimersPerBundle); i = BYTE4(UlTimersPerBundle) )
  {
    v17 = v15++;
    *(_DWORD *)(v11 + 4 * v17 + 16880) = *(_DWORD *)(v13 + 4LL * *((int *)qword_1401A3DD0 + v17) + 4272);
  }
  *(_DWORD *)(v11 + 16904) = (1 << i) - 1;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v14 + 64)) == 1 )
  {
    v18 = KeAcquireSpinLockRaiseToDpc(&UlHotAddCommitLock);
    if ( ++UlMetronomeCount != 1 )
    {
LABEL_17:
      KeReleaseSpinLock(&UlHotAddCommitLock, v18);
      goto LABEL_18;
    }
    if ( UlMetronomeState )
    {
      if ( UlMetronomeState != 1 )
        goto LABEL_17;
    }
    else
    {
      UlpResumeTimerWheels();
      KeSetCoalescableTimer(&UlMetronomeTimer, (LARGE_INTEGER)-50000000LL, 0, 0x1F4u, &UlMetronomeDpc);
    }
    UlMetronomeState = 2;
    goto LABEL_17;
  }
LABEL_18:
  RtlInitializeTimerWheelEntry(0, v11 + 16832, 0, 0);
  *(_QWORD *)(v11 + 17280) = v78;
  v78 = 0;
  *(_QWORD *)(v11 + 17272) = Object;
  Object = 0;
  v19 = _InterlockedIncrement((volatile signed __int32 *)(v11 + 4));
  if ( UxDebugCheckRefcount && v19 <= -1 )
    UlBugCheckEx(3u, v11 + 4, 0x10u, v19);
  v74 = 0;
  v9 = UxpAllocateOpaqueIdEntry(&v74);
  if ( v9 < 0 )
    goto LABEL_117;
  KeEnterCriticalRegion();
  v20 = v74;
  ExAcquirePushLockExclusiveEx(v74 + 32, 0);
  *(_DWORD *)(v11 + 17292) = *(_DWORD *)(v20 + 40);
  *(_BYTE *)(v11 + 17295) = -85
                          * ((v20
                            - *(_QWORD *)(*((_QWORD *)UxOpaqueIdTable
                                          + 8 * (unsigned __int64)(*(_DWORD *)(v20 + 40) & 0xFFF)
                                          + 2)
                                        + 8LL * ((*(_DWORD *)(v20 + 40) >> 12) & 0xFFF))) >> 4);
  *(_QWORD *)v20 = v11;
  v21 = ++*(_DWORD *)(v20 + 16) & 0xFFFFFFF | 0x50000000;
  *(_DWORD *)(v20 + 40) = v21;
  *(_DWORD *)(v11 + 17288) = v21;
  ExReleasePushLockExclusiveEx(v20 + 32, 0);
  KeLeaveCriticalRegion();
  v22 = (_DWORD *)(v11 + 17232);
  if ( (BYTE11(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qq(1307, 50, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, v11, (unsigned int)*v22);
  v23 = (__int64 (__fastcall *)(__int64))HkAllocate;
  *(_QWORD *)(v11 + 17168) = 0;
  v24 = (_DWORD *)v23(6592);
  v25 = v24;
  if ( !v24 )
    goto LABEL_149;
  memset(v24, 0, 0x19C0u);
  v25[2] = 4096;
  *((_QWORD *)v25 + 3) = v25 + 4;
  *((_QWORD *)v25 + 2) = v25 + 4;
  HkInitializeNameHash(v25);
  v26 = (__int64 (__fastcall *)(__int64))HkAllocate;
  *(_QWORD *)(v11 + 17168) = v25;
  *(_DWORD *)(v11 + 17184) = 4096;
  *(_QWORD *)(v11 + 17176) = 0;
  v27 = (_DWORD *)v26(6592);
  v28 = v27;
  if ( !v27 )
  {
LABEL_149:
    v9 = -1073741670;
    goto LABEL_150;
  }
  memset(v27, 0, 0x19C0u);
  *v28 = 1;
  v28[2] = 4096;
  v28[1646] = 4096;
  *((_QWORD *)v28 + 3) = v28 + 4;
  *((_QWORD *)v28 + 2) = v28 + 4;
  HkInitializeNameHash(v28);
  *(_QWORD *)(v11 + 17176) = v28;
  *(_QWORD *)(v11 + 17056) = 0;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  if ( UxDebugDisableLookaside )
  {
    v31 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A07B0)(
                      (unsigned int)dword_1401A0798,
                      qword_1401A07A0,
                      (unsigned int)dword_1401A07A8,
                      0);
  }
  else if ( UxCompactMode )
  {
    v64 = qword_1401A0790;
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    v31 = (_DWORD *)PplAllocateFromLookasideListProcessor(v64, CurrentNodeNumber);
  }
  else
  {
    v30 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
    if ( !*(_BYTE *)(v30 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A0790, v30 + 64);
    v31 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v30 + 64));
  }
  v32 = v31;
  if ( !v31 )
  {
    v9 = -1073741670;
    goto LABEL_150;
  }
  memset(v31, 0, 0x90u);
  *v32 = LockArray_high;
  v32[4] = 1230600277;
  *((_QWORD *)v32 + 4) = v32 + 6;
  *((_QWORD *)v32 + 3) = v32 + 6;
  *((_QWORD *)v32 + 5) = UxDuoExecuteDetach;
  v32[16] = 4;
  v33 = _InterlockedIncrement((volatile signed __int32 *)(v11 + 4));
  if ( UxDebugCheckRefcount && v33 <= -1 )
    UlBugCheckEx(3u, v11 + 4, 0x2Cu, v33);
  *((_QWORD *)v32 + 7) = v11;
  *(_QWORD *)(v11 + 17056) = v32;
  v34 = (_QWORD *)(v11 + 8);
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 21, v11 + 339, 0, 0, 0);
  v35 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
          *v34,
          21,
          v11 + 339,
          0,
          0,
          0);
  v9 = v35;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v35);
  if ( v9 < 0 )
    goto LABEL_150;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 29, &v75, 0, 0, 0);
  v36 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16)
                                                                                           + 136LL))(
          *v34,
          29,
          &v75,
          0,
          0,
          0);
  v9 = v36;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v36);
  if ( v9 < 0 )
    goto LABEL_150;
  v38 = v75;
  if ( v75 - 0xFFFF > 0x7FFF0000 )
  {
    v9 = -1073741595;
    goto LABEL_150;
  }
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
  {
    WPP_SF_DL(v75, 51, v37, (unsigned int)*v22, v75);
    v38 = v75;
  }
  *(_DWORD *)(v11 + 17028) = v38;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 44, &v76, &v77, 0, 0);
  v39 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, int *, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
          *v34,
          44,
          &v76,
          &v77,
          0,
          0);
  v9 = v39;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v39);
  if ( v9 < 0 )
    goto LABEL_150;
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_DL(v40, 52, v41, (unsigned int)*v22, v76);
  *(_DWORD *)(v11 + 17304) = v76;
  *(_DWORD *)(v11 + 17308) = v77;
  LODWORD(v74) = 0;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 58, &v74, 0, 0, 0);
  v42 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
          *v34,
          58,
          &v74,
          0,
          0,
          0);
  v9 = v42;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v42);
  if ( v9 < 0 )
    goto LABEL_150;
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_DL(v43, 47, v44, (unsigned int)*v22, v74);
  if ( (_DWORD)v74 )
  {
    v45 = 16393;
    if ( (unsigned int)v74 > 0x4009 )
      v45 = v74;
  }
  else
  {
    v45 = 0x10000;
  }
  *(_DWORD *)(v11 + 17468) = v45;
  v46 = MEMORY[0xFFFFF78000000014];
  v47 = *(_QWORD *)(v11 + 17280);
  *(_QWORD *)(v11 + 17336) = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(v11 + 17352) = v46;
  *(_QWORD *)(v11 + 17368) = v46;
  *(_QWORD *)(v11 + 17384) = v46;
  *(_QWORD *)(v11 + 17320) = v46;
  *(_QWORD *)(v11 + 17416) = v46;
  *(_QWORD *)(v11 + 17400) = v46;
  *(_DWORD *)(v11 + 17344) = *(_DWORD *)(v47 + 7156);
  *(_QWORD *)(v11 + 17408) = *(unsigned int *)(v47 + 7172);
  *(_QWORD *)(v11 + 17424) = *(unsigned int *)(v47 + 7176);
  *(_QWORD *)(v11 + 17360) = *(_QWORD *)(v47 + 7184);
  *(_QWORD *)(v11 + 17376) = *(_QWORD *)(v47 + 7200);
  *(_QWORD *)(v11 + 17392) = *(_QWORD *)(v47 + 7192);
  *(_QWORD *)(v11 + 17328) = *(_QWORD *)(v47 + 7216);
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 22, v11 + 17433, 0, 0, 0);
  v48 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
          *v34,
          22,
          v11 + 17433,
          0,
          0,
          0);
  v9 = v48;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v48);
  if ( v9 < 0 )
    goto LABEL_150;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 47, v11 + 17440, 0, 0, 0);
  v49 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
          *v34,
          47,
          v11 + 17440,
          0,
          0,
          0);
  v9 = v49;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v49);
  if ( v9 < 0 )
    goto LABEL_150;
  *(_QWORD *)(v11 + 17064) = 0;
  v50 = HIDWORD(KeGetPcr()[1].LockArray);
  if ( UxDebugDisableLookaside )
  {
    v52 = (_DWORD *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A07B0)(
                      (unsigned int)dword_1401A0798,
                      qword_1401A07A0,
                      (unsigned int)dword_1401A07A8,
                      0);
  }
  else if ( UxCompactMode )
  {
    v66 = qword_1401A0790;
    v67 = KeGetCurrentNodeNumber();
    v52 = (_DWORD *)PplAllocateFromLookasideListProcessor(v66, v67);
  }
  else
  {
    v51 = qword_1401A0790 + ((unsigned __int64)(unsigned int)(v50 + 1) << 7);
    if ( !*(_BYTE *)(v51 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A0790, v51 + 64);
    v52 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v51 + 64));
  }
  v53 = v52;
  if ( !v52 )
  {
    v9 = -1073741670;
LABEL_117:
    v22 = (_DWORD *)(v11 + 17232);
LABEL_150:
    if ( *(_QWORD *)(v11 + 17288) )
    {
      UxFreeOpaqueId();
      *v22 = 0;
    }
    v69 = _InterlockedDecrement((volatile signed __int32 *)(v11 + 4));
    if ( UxDebugCheckRefcount && v69 <= -1 )
      UlBugCheckEx(3u, v11 + 4, 0x10u, v69);
    if ( !v69 )
      UxDuoFreeConnection((PVOID)v11);
    v70 = *(void **)(v11 + 17056);
    if ( v70 )
    {
      UxDuoFreeTask(v70);
      *(_QWORD *)(v11 + 17056) = 0;
    }
    v72 = *(void **)(v11 + 17064);
    if ( v72 )
    {
      UxDuoFreeTask(v72);
      *(_QWORD *)(v11 + 17064) = 0;
    }
    v71 = _InterlockedDecrement((volatile signed __int32 *)(v11 + 4));
    if ( UxDebugCheckRefcount && v71 <= -1 )
      UlBugCheckEx(3u, v11 + 4, 1u, v71);
    if ( !v71 )
      UxDuoFreeConnection((PVOID)v11);
LABEL_98:
    v59 = v80;
    goto LABEL_99;
  }
  memset(v52, 0, 0x90u);
  *v53 = v50;
  v53[4] = 1230600277;
  *((_QWORD *)v53 + 4) = v53 + 6;
  *((_QWORD *)v53 + 3) = v53 + 6;
  *((_QWORD *)v53 + 5) = UxDuoExecuteKillConnection;
  v53[16] = 5;
  v54 = _InterlockedIncrement((volatile signed __int32 *)(v11 + 4));
  if ( UxDebugCheckRefcount && v54 <= -1 )
    UlBugCheckEx(3u, v11 + 4, 0x2Cu, v54);
  *((_QWORD *)v53 + 7) = v11;
  *(_QWORD *)(v11 + 17064) = v53;
  if ( *(_BYTE *)(v11 + 17433) )
  {
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 23, 0, 0, 0, 0);
    v68 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
            *v34,
            23,
            0,
            0,
            0,
            0);
    v9 = v68;
    if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v68);
    if ( v9 < 0 )
      goto LABEL_117;
  }
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 24, 4, 0, 0, 0);
  v55 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
          *v34,
          24,
          4,
          0,
          0,
          0);
  v9 = v55;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v55);
  if ( v9 < 0 )
    goto LABEL_117;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v11 + 8, 43, v11 + 17432, 0, 0, 0);
  v56 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)(v11 + 16) + 136LL))(
          *v34,
          43,
          v11 + 17432,
          0,
          0,
          0);
  v9 = v56;
  if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v56);
  if ( v9 < 0 )
    goto LABEL_117;
  v58 = *(_QWORD *)(v11 + 17280);
  *(_DWORD *)(v11 + 24) = 2;
  if ( (*(_BYTE *)(v58 + 1765) & 0x20) != 0
    && (!*(_QWORD *)(v58 + 1776) || (unsigned __int8)UlEtwEvaluateFilter(v58, v11 + 17472, v11 + 17500, 0, 0, 0, 0, 0)) )
  {
    McTemplateK0px_EtwWriteTransfer(
      *(_QWORD *)(v11 + 17280) + 1688LL,
      HTTP_EVENT_HTTP2_CREATE_CONNECTION,
      v57,
      v11,
      *(unsigned int *)(v11 + 17232));
  }
  v59 = v80;
  *v80 = v11;
  *a4 = &UxDuoDispatch;
LABEL_99:
  if ( (BYTE3(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_qqD(1051, 53, WPP_03a57f2472ee35d9a08fe2d0d8024514_Traceguids, *v59, *a4, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140065a10  push    rbp
0x140065a12  push    rbx
0x140065a13  push    rsi
0x140065a14  push    rdi
0x140065a15  push    r12
0x140065a17  push    r13
0x140065a19  push    r14
0x140065a1b  push    r15
0x140065a1d  lea     rbp, [rsp-17h]
0x140065a22  sub     rsp, 0E8h
0x140065a29  mov     rax, cs:__security_cookie
0x140065a30  xor     rax, rsp
0x140065a33  mov     [rbp+4Fh+var_50], rax
0x140065a37  xor     r14d, r14d
0x140065a3a  mov     [rbp+4Fh+var_A0], r8
0x140065a3e  xorps   xmm0, xmm0
0x140065a41  mov     [rbp+4Fh+var_B0], r14
0x140065a45  xorps   xmm1, xmm1
0x140065a48  mov     [rbp+4Fh+Object], r14
0x140065a4c  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x140065a50  mov     r13, r9
0x140065a53  mov     r12, r8
0x140065a56  movups  xmmword ptr [rbp+4Fh+var_70], xmm1
0x140065a5a  mov     r15, rdx
0x140065a5d  mov     rsi, rcx
0x140065a60  movups  xmmword ptr [rbp+4Fh+var_90+0Ch], xmm0
0x140065a64  mov     [rbp+4Fh+var_C0], r14d
0x140065a68  xor     eax, eax
0x140065a6a  movups  xmmword ptr [rbp+4Fh+var_70+0Ch], xmm1
0x140065a6e  mov     [rbp+4Fh+var_BC], r14d
0x140065a72  mov     [rbp+4Fh+var_B8], r14d
0x140065a76  mov     [rsp+120h+var_D0], r14b
0x140065a7b  test    byte ptr cs:xmmword_1401A2CA0+3, 8
0x140065a82  mov     ebx, [rbp+4Fh+arg_20]
0x140065a85  jnz     loc_140066B32
0x140065a8b  mov     [r12], r14
0x140065a8f  lea     r9, [rbp+4Fh+Object]
0x140065a93  mov     [r13+0], r14
0x140065a97  lea     r8, [rbp+4Fh+var_B0]
0x140065a9b  mov     rax, [r15+88h]
0x140065aa2  mov     edx, 19h
0x140065aa7  mov     [rsp+120h+var_F8], r14
0x140065aac  mov     rcx, rsi
0x140065aaf  mov     [rsp+120h+Dpc], r14
0x140065ab4  call    _guard_dispatch_icall
0x140065ab9  mov     edi, eax
0x140065abb  test    eax, eax
0x140065abd  js      loc_140066EBA
0x140065ac3  mov     rax, [r15+88h]
0x140065aca  lea     r8, [rsp+120h+var_D0]
0x140065acf  mov     [rsp+120h+var_F8], r14
0x140065ad4  xor     r9d, r9d
0x140065ad7  mov     edx, 6
0x140065adc  mov     [rsp+120h+Dpc], r14
0x140065ae1  mov     rcx, rsi
0x140065ae4  call    _guard_dispatch_icall
0x140065ae9  mov     edi, eax
0x140065aeb  mov     r14d, 0FFFFFFFFh
0x140065af1  test    eax, eax
0x140065af3  js      loc_140066689
0x140065af9  mov     rax, [r15+88h]
0x140065b00  lea     r9, [rbp+4Fh+var_70]
0x140065b04  xor     ecx, ecx
0x140065b06  lea     r8, [rbp+4Fh+var_90]
0x140065b0a  mov     [rsp+120h+var_F8], rcx
0x140065b0f  xor     edx, edx
0x140065b11  mov     [rsp+120h+Dpc], rcx
0x140065b16  mov     rcx, rsi
0x140065b19  call    _guard_dispatch_icall
0x140065b1e  mov     edi, eax
0x140065b20  test    eax, eax
0x140065b22  js      loc_140066689
0x140065b28  cmp     [rsp+120h+var_D0], 0
0x140065b2d  jz      loc_14006666B
0x140065b33  test    bl, 20h
0x140065b36  jz      loc_14006666B
0x140065b3c  lea     r9, UxLowPriorityPool
0x140065b43  mov     dword ptr [rsp+120h+Dpc], 1
0x140065b4b  mov     edx, 4480h
0x140065b50  mov     ecx, 40h ; '@'
0x140065b55  mov     r8d, 41597855h
0x140065b5b  call    cs:__imp_ExAllocatePool3
0x140065b62  nop     dword ptr [rax+rax+00h]
0x140065b67  mov     rbx, rax
0x140065b6a  test    rax, rax
0x140065b6d  jz      loc_140066D28
0x140065b73  mov     dword ptr [rax+4], 1
0x140065b7a  mov     dword ptr [rax], 41597855h
0x140065b80  mov     eax, 1
0x140065b85  lock xadd cs:UxDuoConnectionId, eax
0x140065b8d  inc     eax
0x140065b8f  lea     rdi, [rbx+42B0h]
0x140065b96  mov     [rbx+4350h], eax
0x140065b9c  xor     r12d, r12d
0x140065b9f  lea     rax, [rbx+20h]
0x140065ba3  xor     edx, edx; Val
0x140065ba5  mov     [rax+8], rax
0x140065ba9  mov     r8d, 60h ; '`'; Size
0x140065baf  mov     [rax], rax
0x140065bb2  lea     rax, [rbx+30h]
0x140065bb6  mov     [rbx+38h], rax
0x140065bba  mov     [rax], rax
0x140065bbd  lea     rax, [rbx+40h]
0x140065bc1  mov     [rbx+48h], rax
0x140065bc5  mov     [rax], rax
0x140065bc8  lea     rax, [rbx+50h]
0x140065bcc  mov     [rbx+58h], rax
0x140065bd0  mov     [rax], rax
0x140065bd3  lea     rax, [rbx+60h]
0x140065bd7  mov     [rbx+68h], rax
0x140065bdb  mov     [rax], rax
0x140065bde  lea     rax, [rbx+70h]
0x140065be2  mov     [rbx+78h], rax
0x140065be6  mov     [rax], rax
0x140065be9  lea     rax, [rbx+80h]
0x140065bf0  mov     [rbx+88h], rax
0x140065bf7  mov     [rax], rax
0x140065bfa  lea     rax, [rbx+90h]
0x140065c01  mov     [rbx+98h], rax
0x140065c08  mov     [rax], rax
0x140065c0b  lea     rax, [rbx+0A0h]
0x140065c12  mov     [rbx+0A8h], rax
0x140065c19  mov     [rax], rax
0x140065c1c  lea     rax, [rbx+0B0h]
0x140065c23  mov     [rbx+0B8h], rax
0x140065c2a  mov     [rax], rax
0x140065c2d  lea     rax, [rbx+0C0h]
0x140065c34  mov     [rbx+0C8h], rax
0x140065c3b  mov     [rax], rax
0x140065c3e  lea     rax, [rbx+0D0h]
0x140065c45  mov     [rbx+0D8h], rax
0x140065c4c  mov     [rax], rax
0x140065c4f  lea     rax, [rbx+0E0h]
0x140065c56  mov     [rbx+0E8h], rax
0x140065c5d  mov     [rax], rax
0x140065c60  lea     rax, [rbx+0F0h]
0x140065c67  mov     [rbx+0F8h], rax
0x140065c6e  mov     [rax], rax
0x140065c71  lea     rax, [rbx+100h]
0x140065c78  mov     [rbx+108h], rax
0x140065c7f  mov     [rax], rax
0x140065c82  lea     rax, [rbx+110h]
0x140065c89  mov     [rbx+118h], rax
0x140065c90  mov     [rax], rax
0x140065c93  lea     rax, [rbx+120h]
0x140065c9a  mov     [rbx+128h], rax
0x140065ca1  mov     [rax], rax
0x140065ca4  mov     rax, [rbp+4Fh+var_B0]
0x140065ca8  mov     ecx, [rax+1BD8h]
0x140065cae  mov     [rbx+4328h], r12
0x140065cb5  mov     [rbx+4330h], r12d
0x140065cbc  mov     [rbx+4338h], r12
0x140065cc3  mov     [rbx+4334h], ecx
0x140065cc9  mov     rcx, rdi; void *
0x140065ccc  mov     qword ptr [rbx+4348h], 53597855h
0x140065cd7  mov     qword ptr [rbx+4340h], 102h
0x140065ce2  call    memset
0x140065ce7  lea     rax, [rdi+8]
0x140065ceb  mov     rcx, rdi; SpinLock
0x140065cee  mov     [rax+8], rax
0x140065cf2  mov     [rax], rax
0x140065cf5  call    cs:__imp_KeInitializeSpinLock
0x140065cfc  nop     dword ptr [rax+rax+00h]
0x140065d01  mov     [rdi+20h], r12
0x140065d05  mov     [rdi+30h], r12
0x140065d09  mov     [rdi+40h], r12
0x140065d0d  mov     rax, ds:0FFFFF78000000014h
0x140065d17  mov     [rbx+158h], rax
0x140065d1e  mov     dword ptr [rbx+427Ch], 0FFFFh
0x140065d28  mov     qword ptr [rbx+4240h], 10000h
0x140065d33  mov     dword ptr [rbx+4250h], 0FFFFFFFFh
0x140065d3d  mov     dword ptr [rbx+4268h], 0FFFFh
0x140065d47  mov     dword ptr [rbx+426Ch], 0FFFFh
0x140065d51  lea     rax, [rbx+4258h]
0x140065d58  mov     qword ptr [rbx+4270h], 4000h
0x140065d63  xor     ecx, ecx
0x140065d65  mov     [rax+8], rax
0x140065d69  mov     [rax], rax
0x140065d6c  mov     byte ptr [rbx+152h], 1
0x140065d73  mov     dword ptr [rbx+4290h], 1
0x140065d7d  mov     dword ptr [rbx+4294h], 2
0x140065d87  movups  xmm0, xmmword ptr [rbp+4Fh+var_90]
0x140065d8b  movups  xmmword ptr [rbx+4440h], xmm0
0x140065d92  movups  xmm1, xmmword ptr [rbp+4Fh+var_90+0Ch]
0x140065d96  movups  xmmword ptr [rbx+444Ch], xmm1
0x140065d9d  movups  xmm0, xmmword ptr [rbp+4Fh+var_70]
0x140065da1  movups  xmmword ptr [rbx+445Ch], xmm0
0x140065da8  movups  xmm1, xmmword ptr [rbp+4Fh+var_70+0Ch]
0x140065dac  movups  xmmword ptr [rbx+4468h], xmm1
0x140065db3  mov     qword ptr [rbx+18h], 1
0x140065dbb  mov     [rbx+8], rsi
0x140065dbf  mov     [rbx+10h], r15
0x140065dc3  test    byte ptr cs:xmmword_1401A2CA0+3, 8
0x140065dca  jnz     loc_140066D32
0x140065dd0  mov     rax, [rbx+10h]
0x140065dd4  lea     r8, [rbx+4238h]
0x140065ddb  mov     [rsp+120h+var_F8], rcx
0x140065de0  xor     r9d, r9d
0x140065de3  mov     [rsp+120h+Dpc], rcx
0x140065de8  mov     edx, 5
0x140065ded  mov     rcx, [rbx+8]
0x140065df1  mov     rax, [rax+88h]
0x140065df8  call    _guard_dispatch_icall
0x140065dfd  lea     r12, [rbx+4228h]
0x140065e04  mov     rcx, r12; SpinLock
0x140065e07  call    cs:__imp_KeInitializeSpinLock
0x140065e0e  nop     dword ptr [rax+rax+00h]
0x140065e13  mov     r15, [rbx+4238h]
0x140065e1a  mov     rsi, [rbp+4Fh+var_B0]
0x140065e1e  add     r15, 10h
0x140065e22  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140065e29  jnz     loc_140066D60
0x140065e2f  xor     edx, edx; Val
0x140065e31  lea     rcx, [rbx+41A8h]; void *
0x140065e38  mov     r8d, 80h; Size
0x140065e3e  call    memset
0x140065e43  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140065e4b  movups  xmmword ptr [rbx+4210h], xmm0
0x140065e52  mov     [rbx+41B8h], r12
0x140065e59  xor     r12d, r12d
0x140065e5c  mov     [rbx+41B0h], r15
0x140065e63  mov     r8d, r12d
0x140065e66  mov     byte ptr [rbx+420Ch], 1
0x140065e6d  mov     dword ptr [rbx+41A8h], 2
0x140065e77  mov     ecx, dword ptr cs:UlTimersPerBundle+4
0x140065e7d  cmp     r12w, cx
0x140065e81  jnb     short loc_140065EB0
0x140065e83  lea     r9, qword_1401A3DD0
0x140065e8a  movzx   edx, r8w
0x140065e8e  inc     r8w
0x140065e92  movsxd  rax, dword ptr [r9+rdx*4]
0x140065e96  mov     ecx, [rsi+rax*4+10B0h]
0x140065e9d  mov     [rbx+rdx*4+41F0h], ecx
0x140065ea4  mov     ecx, dword ptr cs:UlTimersPerBundle+4
0x140065eaa  cmp     r8w, cx
0x140065eae  jb      short loc_140065E8A
0x140065eb0  mov     eax, 1
0x140065eb5  shl     eax, cl
0x140065eb7  dec     eax
0x140065eb9  mov     [rbx+4208h], eax
0x140065ebf  mov     eax, 1
0x140065ec4  lock xadd [r15+40h], eax
0x140065eca  inc     eax
0x140065ecc  cmp     eax, 1
0x140065ecf  jnz     short loc_140065F15
0x140065ed1  lea     rcx, UlHotAddCommitLock; SpinLock
0x140065ed8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140065edf  nop     dword ptr [rax+rax+00h]
0x140065ee4  mov     ecx, cs:UlMetronomeCount
0x140065eea  movzx   edi, al
0x140065eed  inc     ecx
0x140065eef  mov     cs:UlMetronomeCount, ecx
0x140065ef5  cmp     ecx, 1
0x140065ef8  jz      loc_140066716
0x140065efe  movzx   edx, dil; NewIrql
0x140065f02  lea     rcx, UlHotAddCommitLock; SpinLock
0x140065f09  call    cs:__imp_KeReleaseSpinLock
0x140065f10  nop     dword ptr [rax+rax+00h]
0x140065f15  lea     rdx, [rbx+41C0h]
0x140065f1c  xor     r9d, r9d
0x140065f1f  xor     r8d, r8d
0x140065f22  xor     ecx, ecx
0x140065f24  call    cs:__imp_RtlInitializeTimerWheelEntry
0x140065f2b  nop     dword ptr [rax+rax+00h]
0x140065f30  mov     rax, [rbp+4Fh+var_B0]
0x140065f34  mov     [rbx+4380h], rax
0x140065f3b  mov     rax, [rbp+4Fh+Object]
0x140065f3f  mov     [rbp+4Fh+var_B0], r12
0x140065f43  mov     [rbx+4378h], rax
0x140065f4a  mov     eax, 1
0x140065f4f  mov     [rbp+4Fh+Object], r12
0x140065f53  lock xadd [rbx+4], eax
0x140065f58  inc     eax
0x140065f5a  cmp     cs:UxDebugCheckRefcount, r12b
0x140065f61  jnz     loc_14006673C
0x140065f67  lea     rcx, [rbp+4Fh+var_C8]
0x140065f6b  mov     [rbp+4Fh+var_C8], r12
0x140065f6f  xor     sil, sil
0x140065f72  call    UxpAllocateOpaqueIdEntry
0x140065f77  mov     edi, eax
0x140065f79  test    eax, eax
0x140065f7b  js      loc_140066B6E
0x140065f81  call    cs:__imp_KeEnterCriticalRegion
0x140065f88  nop     dword ptr [rax+rax+00h]
0x140065f8d  mov     rdi, [rbp+4Fh+var_C8]
0x140065f91  xor     edx, edx
0x140065f93  lea     rcx, [rdi+20h]
0x140065f97  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140065f9e  nop     dword ptr [rax+rax+00h]
0x140065fa3  mov     eax, [rdi+28h]
0x140065fa6  mov     [rbx+438Ch], eax
0x140065fac  mov     edx, [rdi+28h]
0x140065faf  mov     rax, cs:UxOpaqueIdTable
0x140065fb6  mov     ecx, edx
0x140065fb8  and     ecx, 0FFFh
0x140065fbe  shr     rdx, 0Ch
0x140065fc2  shl     rcx, 6
0x140065fc6  and     edx, 0FFFh
0x140065fcc  mov     rcx, [rcx+rax+10h]
0x140065fd1  mov     rax, rdi
  ... truncated ...
```
