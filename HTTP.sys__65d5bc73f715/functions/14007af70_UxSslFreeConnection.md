# UxSslFreeConnection

- ea: `0x14007af70`
- end: `0x14007b985`
- name: `UxSslFreeConnection`
- size: `2581`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14000a350`
- `0x140018f04`
- `0x140022610`
- `0x140049d08`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x14007982c`
- `0x14007af70`
- `0x14007eba0`
- `0x140097b1c`
- `0x1400eda4c`
- `0x140133a90`
- `0x1401387cc`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007b36a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14007b36a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14007b2b9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14007b2b9`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14007b8fa`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14007b8fa`
- `ntoskrnl!KeSetEvent` at `0x14007b919`
- `ntoskrnl!KeSetEvent` at `0x14007b919`
- `ntoskrnl!ZwClose` at `0x14007b684`
- `ntoskrnl!ZwClose` at `0x14007b684`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007b415`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14007b415`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140178d75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140178d75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b098`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b258`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b6e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b70a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b85c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b8bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b098`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b0b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b258`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b6e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b70a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b85c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b8bf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140178d69`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140178d69`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140178d16`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140178d16`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140178d04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140178d04`
- `ksecdd!SspiFreeAsyncContext` at `0x14007b077`
- `ksecdd!SspiFreeAsyncContext` at `0x14007b077`
- `ksecdd!SspiDeleteSecurityContextAsync` at `0x14007b011`
- `ksecdd!SspiDeleteSecurityContextAsync` at `0x14007b011`
- `ksecdd!FreeContextBuffer` at `0x14007b247`
- `ksecdd!FreeContextBuffer` at `0x14007b66c`
- `ksecdd!FreeContextBuffer` at `0x14007b8d7`
- `ksecdd!FreeContextBuffer` at `0x14007b247`
- `ksecdd!FreeContextBuffer` at `0x14007b66c`
- `ksecdd!FreeContextBuffer` at `0x14007b8d7`

## pseudocode

```c
void __fastcall UxSslFreeConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // rbx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  SspiAsyncContext *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rsi
  __int64 v16; // rax
  _OWORD *v17; // r12
  char v18; // r13
  int v19; // ebp
  signed __int32 v20; // r15d
  int v21; // eax
  volatile signed __int32 *v22; // rsi
  volatile signed __int32 *v23; // rdx
  int v24; // eax
  _QWORD *v25; // rsi
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  void *v29; // rsi
  __int64 v30; // rdx
  ULONG_PTR v31; // rdx
  int v32; // edi
  __int64 v33; // rbp
  void (__fastcall *v34)(__int64); // rsi
  bool v35; // zf
  unsigned __int64 v36; // rdi
  __int64 v37; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v39; // rcx
  int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v44[24]; // [rsp+40h] [rbp-98h] BYREF

  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 17, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, a1);
  v5 = (char *)(a1 - 160);
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 18, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, v5);
  if ( *(_BYTE *)(*((_QWORD *)v5 + 212) + 8162LL)
    && !v5[1366]
    && *((_QWORD *)v5 + 55) != -1
    && *((_QWORD *)v5 + 56) != -1
    && !v5[1368] )
  {
    UxSslConnectionDisableReconnects((PCtxtHandle)(v5 + 440));
  }
  v6 = (void *)*((_QWORD *)v5 + 158);
  if ( v6 )
  {
    FreeContextBuffer(v6);
    *((_QWORD *)v5 + 158) = 0;
  }
  v7 = (void *)*((_QWORD *)v5 + 160);
  if ( v7 )
  {
    ZwClose(v7);
    *((_QWORD *)v5 + 160) = 0;
  }
  if ( *((_QWORD *)v5 + 55) != -1 && *((_QWORD *)v5 + 56) != -1 )
  {
    SspiDeleteSecurityContextAsync(*((SspiAsyncContext **)v5 + 196), (PCtxtHandle)(v5 + 440));
    *((_QWORD *)v5 + 56) = -1;
    *((_QWORD *)v5 + 55) = -1;
  }
  if ( *((_QWORD *)v5 + 227) )
  {
    UxWfpFreeThrottleContext();
    *((_QWORD *)v5 + 227) = 0;
  }
  v8 = (void *)*((_QWORD *)v5 + 193);
  if ( v8 )
  {
    UxSslFreeAchContext(v8);
    *((_QWORD *)v5 + 193) = 0;
  }
  v9 = (void *)*((_QWORD *)v5 + 194);
  if ( v9 )
  {
    UxSslFreeAscContext(v9);
    *((_QWORD *)v5 + 194) = 0;
  }
  v10 = (void *)*((_QWORD *)v5 + 195);
  if ( v10 )
  {
    UxSslFreeAscContext(v10);
    *((_QWORD *)v5 + 195) = 0;
  }
  v11 = (SspiAsyncContext *)*((_QWORD *)v5 + 196);
  if ( v11 )
  {
    SspiFreeAsyncContext(v11);
    *((_QWORD *)v5 + 196) = 0;
  }
  v12 = (void *)*((_QWORD *)v5 + 202);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  *((_QWORD *)v5 + 202) = 0;
  v13 = (void *)*((_QWORD *)v5 + 207);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  *((_QWORD *)v5 + 207) = 0;
  if ( *((_DWORD *)v5 + 410) )
  {
    ExFreePoolWithTag(*((PVOID *)v5 + 204), 0);
    *((_QWORD *)v5 + 204) = 0;
    *((_DWORD *)v5 + 410) = 0;
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1041, 197, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, v5);
  v14 = (void *)*((_QWORD *)v5 + 197);
  if ( v14 )
  {
    ExFreePoolWithTag(v14, 0);
    *((_QWORD *)v5 + 197) = 0;
    *((_DWORD *)v5 + 396) = 0;
    *((_QWORD *)v5 + 199) = 0;
    *((_DWORD *)v5 + 400) = 0;
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 198, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids);
  v15 = *((_QWORD *)v5 + 54);
  if ( v15 )
  {
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qD(1041, 53, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, v15, 0);
    v16 = *(_QWORD *)(v15 + 856);
    v17 = 0;
    v18 = *(_BYTE *)(v16 + 8165);
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qD(1041, 148, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids, v15 + 16, *(unsigned __int8 *)(v16 + 8165));
    LODWORD(v43) = *(_DWORD *)(v15 + 104);
    do
    {
      v19 = v43;
      if ( (_DWORD)v43 == 1 )
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v15 + 16, 0);
        v20 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 104), 0, 1);
        LODWORD(v43) = v20;
        if ( v20 == 1 )
        {
          v17 = *(_OWORD **)(v15 + 24);
          v17[3] = *(_OWORD *)(v15 + 88);
          *((_DWORD *)v17 + 16) = *(_DWORD *)(v15 + 112);
          v42 = *(unsigned int *)(v15 + 112);
          *(_QWORD *)(v15 + 24) = 0;
          UxpSslEndpointInvalidateCertificate(v15 + 88, v42);
          _InterlockedExchange((volatile __int32 *)(v15 + 108), 0);
        }
        ExReleasePushLockExclusiveEx(v15 + 16, 0);
        KeLeaveCriticalRegion();
      }
      else
      {
        v20 = _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 104), v43 - 1, v43);
        LODWORD(v43) = v20;
      }
    }
    while ( v20 != v19 );
    if ( v17 )
    {
      *(_QWORD *)v17 = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 4) = 0;
      if ( v18 )
      {
        UxpSslUnloadEndpointCertificateWorker(v17);
      }
      else
      {
        LOBYTE(a4) = 1;
        UlThreadPoolEnqueueWorkItem(1, v17, UxpSslUnloadEndpointCertificateWorker, a4, -1, -1);
      }
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 149, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids);
    v21 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 4));
    if ( UxDebugCheckRefcount && v21 <= -1 )
      UlBugCheckEx(3u, v15 + 4, 0xFu, v21);
    if ( !v21 )
      UxSslDestroyConfiguration(v15);
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 54, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids);
    *((_QWORD *)v5 + 54) = 0;
  }
  v22 = (volatile signed __int32 *)*((_QWORD *)v5 + 192);
  if ( v22 )
  {
    v40 = _InterlockedDecrement(v22 + 5);
    if ( UxDebugCheckRefcount && v40 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v22 + 5), 1u, v40);
    if ( v40 )
      goto LABEL_98;
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1041, 10, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids, v22);
    v41 = *((_DWORD *)v22 + 30);
    *((_DWORD *)v22 + 4) = 1819498613;
    if ( v41 )
    {
      switch ( v41 )
      {
        case 1u:
          if ( UxDebugDisableLookaside )
          {
            memset(v44, 0, sizeof(v44));
            v44[10] = dword_1401A0658;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0668)(v22, v44);
            goto LABEL_96;
          }
          v39 = qword_1401A0640;
          break;
        case 2u:
          if ( UxDebugDisableLookaside )
          {
            memset(v44, 0, sizeof(v44));
            v44[10] = dword_1401A0688;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0698)(v22, v44);
            goto LABEL_96;
          }
          v39 = qword_1401A0670;
          break;
        case 3u:
          if ( UxDebugDisableLookaside )
          {
            memset(v44, 0, sizeof(v44));
            v44[10] = dword_1401A06B8;
            ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A06C8)(v22, v44);
            goto LABEL_96;
          }
          v39 = qword_1401A06A0;
          break;
        default:
          ExFreePoolWithTag((PVOID)v22, 0);
          goto LABEL_96;
      }
    }
    else
    {
      if ( UxDebugDisableLookaside )
      {
        memset(v44, 0, sizeof(v44));
        v44[10] = dword_1401A0628;
        ((void (__fastcall *)(volatile signed __int32 *, _DWORD *))off_1401A0638)(v22, v44);
        goto LABEL_96;
      }
      v39 = qword_1401A0610;
    }
    if ( UxCompactMode )
      PnlFreeToLookasideList(v39, v22);
    else
      PplFreeToLookasideListProcessor(v39, v22, *(unsigned int *)v22);
LABEL_96:
    if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1041, 11, WPP_17ba6440ec9a3614c322bdbfedc6ad67_Traceguids);
LABEL_98:
    *((_QWORD *)v5 + 192) = 0;
  }
  v23 = (volatile signed __int32 *)*((_QWORD *)v5 + 48);
  if ( v23 )
  {
    v24 = _InterlockedDecrement(v23);
    if ( UxDebugCheckRefcount && v24 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v23, 0xAu, v24);
    if ( !v24 )
    {
      v25 = (_QWORD *)*((_QWORD *)v5 + 48);
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_q(1041, 117, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids, *((_QWORD *)v5 + 48));
      v26 = (void *)v25[2];
      if ( v26 )
        FreeContextBuffer(v26);
      ExFreePoolWithTag(v25, 0);
      if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_(1041, 118, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
    }
    *((_QWORD *)v5 + 48) = 0;
  }
  v27 = (void *)*((_QWORD *)v5 + 50);
  if ( v27 )
  {
    ExFreePoolWithTag(v27, 0);
    *((_QWORD *)v5 + 50) = 0;
  }
  v28 = (void *)*((_QWORD *)v5 + 53);
  if ( v28 )
  {
    FreeContextBuffer(v28);
    *((_OWORD *)v5 + 26) = 0;
  }
  v29 = (void *)*((_QWORD *)v5 + 211);
  v30 = (unsigned int)UxPodMonitorSlot;
  *((_QWORD *)v5 + 212) = 0;
  v43 = 0;
  PsGetPermanentSiloContext(v29, v30, &v43);
  if ( v29 )
    ObfDereferenceObjectWithTag(v29, 0x43546C55u);
  v31 = v43 + 24;
  v32 = _InterlockedDecrement((volatile signed __int32 *)(v43 + 24));
  if ( UxDebugCheckRefcount && v32 <= -1 )
    UlBugCheckEx(3u, v31, 0xFu, v32);
  if ( !v32 )
    KeSetEvent((PRKEVENT)(v43 + 32), 0, 0);
  *((_QWORD *)v5 + 211) = 0;
  *((_DWORD *)v5 + 10) = 7;
  if ( *((_DWORD *)v5 + 16) == 4 )
  {
    v33 = *((_QWORD *)v5 + 6);
    v34 = *(void (__fastcall **)(__int64))(*((_QWORD *)v5 + 7) + 16LL);
  }
  else
  {
    v34 = 0;
    v33 = 0;
  }
  v35 = UxDebugDisableLookaside == 0;
  *((_DWORD *)v5 + 16) = 5;
  *((_QWORD *)v5 + 7) = 0;
  *((_DWORD *)v5 + 4) = 1634949237;
  if ( v35 )
  {
    if ( UxCompactMode )
    {
      v37 = qword_1401A03D0;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v37, v5, CurrentNodeNumber);
    }
    else
    {
      v36 = qword_1401A03D0 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v5 + 1) << 7);
      if ( !*(_BYTE *)(v36 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A03D0, v36 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v36 + 64), v5);
    }
  }
  else
  {
    memset(v44, 0, sizeof(v44));
    v44[10] = dword_1401A03E8;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A03F8)(v5, v44);
  }
  if ( v34 )
    v34(v33);
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 19, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids);
}

```

## disassembly

```asm
0x14007af70  push    rbx
0x14007af72  push    rsi
0x14007af73  push    rdi
0x14007af74  push    r15
0x14007af76  sub     rsp, 0B8h
0x14007af7d  mov     rax, cs:__security_cookie
0x14007af84  xor     rax, rsp
0x14007af87  mov     [rsp+0D8h+var_38], rax
0x14007af8f  mov     rbx, rcx
0x14007af92  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007af99  jnz     loc_14007B5ED
0x14007af9f  add     rbx, 0FFFFFFFFFFFFFF60h
0x14007afa6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007afad  jnz     loc_14007B60B
0x14007afb3  mov     rax, [rbx+6A0h]
0x14007afba  cmp     byte ptr [rax+1FE2h], 0
0x14007afc1  jnz     loc_14007B629
0x14007afc7  mov     rcx, [rbx+4F0h]; pvContextBuffer
0x14007afce  xor     r15d, r15d
0x14007afd1  test    rcx, rcx
0x14007afd4  jnz     loc_14007B66C
0x14007afda  mov     rcx, [rbx+500h]; Handle
0x14007afe1  test    rcx, rcx
0x14007afe4  jnz     loc_14007B684
0x14007afea  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x14007aff1  cmp     [rbx+1B8h], rdi
0x14007aff8  jz      short loc_14007B02B
0x14007affa  cmp     [rbx+1C0h], rdi
0x14007b001  jz      short loc_14007B02B
0x14007b003  mov     rcx, [rbx+620h]; AsyncContext
0x14007b00a  lea     rdx, [rbx+1B8h]; phContext
0x14007b011  call    cs:__imp_SspiDeleteSecurityContextAsync
0x14007b018  nop     dword ptr [rax+rax+00h]
0x14007b01d  mov     [rbx+1C0h], rdi
0x14007b024  mov     [rbx+1B8h], rdi
0x14007b02b  mov     rcx, [rbx+718h]
0x14007b032  test    rcx, rcx
0x14007b035  jnz     loc_14007B69C
0x14007b03b  mov     rcx, [rbx+608h]; P
0x14007b042  test    rcx, rcx
0x14007b045  jnz     loc_14007B6AD
0x14007b04b  mov     rcx, [rbx+610h]; P
0x14007b052  test    rcx, rcx
0x14007b055  jnz     loc_14007B6BE
0x14007b05b  mov     rcx, [rbx+618h]; P
0x14007b062  test    rcx, rcx
0x14007b065  jnz     loc_14007B6CF
0x14007b06b  mov     rcx, [rbx+620h]; Handle
0x14007b072  test    rcx, rcx
0x14007b075  jz      short loc_14007B08A
0x14007b077  call    cs:__imp_SspiFreeAsyncContext
0x14007b07e  nop     dword ptr [rax+rax+00h]
0x14007b083  mov     [rbx+620h], r15
0x14007b08a  mov     rcx, [rbx+650h]; P
0x14007b091  test    rcx, rcx
0x14007b094  jz      short loc_14007B0A4
0x14007b096  xor     edx, edx; Tag
0x14007b098  call    cs:__imp_ExFreePoolWithTag
0x14007b09f  nop     dword ptr [rax+rax+00h]
0x14007b0a4  mov     [rbx+650h], r15
0x14007b0ab  mov     rcx, [rbx+678h]; P
0x14007b0b2  test    rcx, rcx
0x14007b0b5  jz      short loc_14007B0C5
0x14007b0b7  xor     edx, edx; Tag
0x14007b0b9  call    cs:__imp_ExFreePoolWithTag
0x14007b0c0  nop     dword ptr [rax+rax+00h]
0x14007b0c5  mov     [rbx+678h], r15
0x14007b0cc  cmp     [rbx+668h], r15d
0x14007b0d3  jnz     loc_14007B6E0
0x14007b0d9  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b0e0  jnz     loc_14007B458
0x14007b0e6  mov     rcx, [rbx+628h]; P
0x14007b0ed  test    rcx, rcx
0x14007b0f0  jnz     loc_14007B708
0x14007b0f6  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b0fd  jnz     loc_14007B737
0x14007b103  mov     rsi, [rbx+1B0h]
0x14007b10a  mov     [rsp+0D8h+arg_8], rbp
0x14007b112  test    rsi, rsi
0x14007b115  jz      loc_14007B1F5
0x14007b11b  mov     [rsp+0D8h+arg_10], r12
0x14007b123  mov     [rsp+0D8h+arg_18], r13
0x14007b12b  mov     [rsp+0D8h+var_28], r14
0x14007b133  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b13a  jnz     loc_14007B435
0x14007b140  mov     rax, [rsi+358h]
0x14007b147  mov     r12, r15
0x14007b14a  movzx   r13d, byte ptr [rax+1FE5h]
0x14007b152  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b159  jnz     loc_14007B476
0x14007b15f  mov     eax, [rsi+68h]
0x14007b162  mov     dword ptr [rsp+0D8h+var_A8], eax
0x14007b166  mov     ebp, dword ptr [rsp+0D8h+var_A8]
0x14007b16a  lea     ecx, [rbp-1]
0x14007b16d  test    ecx, ecx
0x14007b16f  jz      loc_140178D04
0x14007b175  mov     eax, ebp
0x14007b177  lock cmpxchg [rsi+68h], ecx
0x14007b17c  mov     r15d, eax
0x14007b17f  mov     dword ptr [rsp+0D8h+var_A8], eax
0x14007b183  cmp     r15d, ebp
0x14007b186  mov     r15d, 0
0x14007b18c  jnz     short loc_14007B166
0x14007b18e  mov     r14, [rsp+0D8h+var_28]
0x14007b196  test    r12, r12
0x14007b199  jnz     loc_14007B752
0x14007b19f  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b1a6  mov     r13, [rsp+0D8h+arg_18]
0x14007b1ae  mov     r12, [rsp+0D8h+arg_10]
0x14007b1b6  jnz     loc_14007B49A
0x14007b1bc  lea     rdx, [rsi+4]; BugCheckParameter2
0x14007b1c0  mov     eax, edi
0x14007b1c2  lock xadd [rdx], eax
0x14007b1c6  dec     eax
0x14007b1c8  cmp     cs:UxDebugCheckRefcount, 0
0x14007b1cf  jnz     loc_14007B3F2
0x14007b1d5  test    eax, eax
0x14007b1d7  jnz     short loc_14007B1E1
0x14007b1d9  mov     rcx, rsi
0x14007b1dc  call    UxSslDestroyConfiguration
0x14007b1e1  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b1e8  jnz     loc_14007B776
0x14007b1ee  mov     [rbx+1B0h], r15
0x14007b1f5  mov     rsi, [rbx+600h]
0x14007b1fc  test    rsi, rsi
0x14007b1ff  jnz     loc_14007B544
0x14007b205  mov     rdx, [rbx+180h]; BugCheckParameter2
0x14007b20c  test    rdx, rdx
0x14007b20f  jz      short loc_14007B278
0x14007b211  mov     eax, edi
0x14007b213  lock xadd [rdx], eax
0x14007b217  dec     eax
0x14007b219  cmp     cs:UxDebugCheckRefcount, 0
0x14007b220  jnz     loc_14007B3D6
0x14007b226  test    eax, eax
0x14007b228  jnz     short loc_14007B271
0x14007b22a  mov     rsi, [rbx+180h]
0x14007b231  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b238  jnz     loc_14007B4B5
0x14007b23e  mov     rcx, [rsi+10h]; pvContextBuffer
0x14007b242  test    rcx, rcx
0x14007b245  jz      short loc_14007B253
0x14007b247  call    cs:__imp_FreeContextBuffer
0x14007b24e  nop     dword ptr [rax+rax+00h]
0x14007b253  xor     edx, edx; Tag
0x14007b255  mov     rcx, rsi; P
0x14007b258  call    cs:__imp_ExFreePoolWithTag
0x14007b25f  nop     dword ptr [rax+rax+00h]
0x14007b264  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b26b  jnz     loc_14007B4D3
0x14007b271  mov     [rbx+180h], r15
0x14007b278  mov     rcx, [rbx+190h]; P
0x14007b27f  test    rcx, rcx
0x14007b282  jnz     loc_14007B8BD
0x14007b288  mov     rcx, [rbx+1A8h]; pvContextBuffer
0x14007b28f  test    rcx, rcx
0x14007b292  jnz     loc_14007B8D7
0x14007b298  mov     rsi, [rbx+698h]
0x14007b29f  lea     r8, [rsp+0D8h+var_A8]
0x14007b2a4  mov     edx, cs:UxPodMonitorSlot
0x14007b2aa  mov     rcx, rsi
0x14007b2ad  mov     [rbx+6A0h], r15
0x14007b2b4  mov     [rsp+0D8h+var_A8], r15
0x14007b2b9  call    cs:__imp_PsGetPermanentSiloContext
0x14007b2c0  nop     dword ptr [rax+rax+00h]
0x14007b2c5  test    rsi, rsi
0x14007b2c8  jnz     loc_14007B8F2
0x14007b2ce  mov     rdx, [rsp+0D8h+var_A8]
0x14007b2d3  add     rdx, 18h; BugCheckParameter2
0x14007b2d7  lock xadd [rdx], edi
0x14007b2db  dec     edi
0x14007b2dd  cmp     cs:UxDebugCheckRefcount, 0
0x14007b2e4  jnz     loc_14007B3B9
0x14007b2ea  test    edi, edi
0x14007b2ec  jz      loc_14007B90B
0x14007b2f2  mov     [rbx+698h], r15
0x14007b2f9  mov     dword ptr [rbx+28h], 7
0x14007b300  cmp     dword ptr [rbx+40h], 4
0x14007b304  jnz     loc_14007B92A
0x14007b30a  mov     rax, [rbx+38h]
0x14007b30e  mov     rbp, [rbx+30h]
0x14007b312  mov     rsi, [rax+10h]
0x14007b316  cmp     cs:UxDebugDisableLookaside, 0
0x14007b31d  mov     dword ptr [rbx+40h], 5
0x14007b324  mov     [rbx+38h], r15
0x14007b328  mov     dword ptr [rbx+10h], 61735875h
0x14007b32f  jnz     loc_14007B935
0x14007b335  cmp     cs:UxCompactMode, 0
0x14007b33c  jnz     loc_14007B40E
0x14007b342  mov     edi, [rbx]
0x14007b344  mov     rcx, cs:qword_1401A03D0
0x14007b34b  inc     edi
0x14007b34d  shl     rdi, 7
0x14007b351  add     rdi, rcx
0x14007b354  movzx   eax, byte ptr [rdi+0B0h]
0x14007b35b  test    al, al
0x14007b35d  jz      loc_14007B4EE
0x14007b363  mov     rdx, rbx; Entry
0x14007b366  lea     rcx, [rdi+40h]; Lookaside
0x14007b36a  call    cs:__imp_ExFreeToLookasideListEx
0x14007b371  nop     dword ptr [rax+rax+00h]
0x14007b376  test    rsi, rsi
0x14007b379  jz      short loc_14007B386
0x14007b37b  mov     rcx, rbp
0x14007b37e  mov     rax, rsi
0x14007b381  call    _guard_dispatch_icall
0x14007b386  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b38d  jnz     loc_14007B96A
0x14007b393  mov     rbp, [rsp+0D8h+arg_8]
0x14007b39b  mov     rcx, [rsp+0D8h+var_38]
0x14007b3a3  xor     rcx, rsp; StackCookie
0x14007b3a6  call    __security_check_cookie
0x14007b3ab  add     rsp, 0B8h
0x14007b3b2  pop     r15
0x14007b3b4  pop     rdi
0x14007b3b5  pop     rsi
0x14007b3b6  pop     rbx
0x14007b3b7  retn
0x14007b3b9  cmp     edi, 0FFFFFFFFh
0x14007b3bc  jg      loc_14007B2EA
0x14007b3c2  movsxd  r9, edi; BugCheckParameter4
0x14007b3c5  mov     ecx, 3; BugCheckParameter1
0x14007b3ca  mov     r8d, 0Fh; BugCheckParameter3
0x14007b3d0  call    UlBugCheckEx
0x14007b3d6  cmp     eax, edi
0x14007b3d8  jg      loc_14007B226
0x14007b3de  movsxd  r9, eax; BugCheckParameter4
0x14007b3e1  mov     ecx, 3; BugCheckParameter1
0x14007b3e6  mov     r8d, 0Ah; BugCheckParameter3
0x14007b3ec  call    UlBugCheckEx
0x14007b3f2  cmp     eax, edi
0x14007b3f4  jg      loc_14007B1D5
0x14007b3fa  movsxd  r9, eax; BugCheckParameter4
0x14007b3fd  mov     ecx, 3; BugCheckParameter1
0x14007b402  mov     r8d, 0Fh; BugCheckParameter3
0x14007b408  call    UlBugCheckEx
0x14007b40e  mov     rdi, cs:qword_1401A03D0
0x14007b415  call    cs:__imp_KeGetCurrentNodeNumber
0x14007b41c  nop     dword ptr [rax+rax+00h]
0x14007b421  movzx   r8d, ax
0x14007b425  mov     rdx, rbx
0x14007b428  mov     rcx, rdi
0x14007b42b  call    PplFreeToLookasideListProcessor
0x14007b430  jmp     loc_14007B376
0x14007b435  mov     edx, 35h ; '5'
0x14007b43a  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x14007b43f  mov     ecx, 411h
0x14007b444  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b44b  mov     r9, rsi
0x14007b44e  call    WPP_SF_qD
0x14007b453  jmp     loc_14007B140
0x14007b458  mov     edx, 0C5h
0x14007b45d  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b464  mov     ecx, 411h
0x14007b469  mov     r9, rbx
0x14007b46c  call    WPP_SF_q
0x14007b471  jmp     loc_14007B0E6
0x14007b476  mov     edx, 94h
0x14007b47b  mov     dword ptr [rsp+0D8h+var_B8], r13d
0x14007b480  mov     ecx, 411h
0x14007b485  lea     r9, [rsi+10h]
0x14007b489  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b490  call    WPP_SF_qD
0x14007b495  jmp     loc_14007B15F
0x14007b49a  mov     edx, 95h
0x14007b49f  lea     r8, WPP_a0bbab1c49533d3bb0a964c309c0a4fe_Traceguids
0x14007b4a6  mov     ecx, 411h
0x14007b4ab  call    WPP_SF_
0x14007b4b0  jmp     loc_14007B1BC
0x14007b4b5  mov     edx, 75h ; 'u'
0x14007b4ba  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14007b4c1  mov     ecx, 411h
0x14007b4c6  mov     r9, rsi
0x14007b4c9  call    WPP_SF_q
0x14007b4ce  jmp     loc_14007B23E
0x14007b4d3  mov     edx, 76h ; 'v'
0x14007b4d8  lea     r8, WPP_6e841a355e49390d9c664d29a1157c63_Traceguids
0x14007b4df  mov     ecx, 411h
0x14007b4e4  call    WPP_SF_
0x14007b4e9  jmp     loc_14007B271
0x14007b4ee  lea     rdx, [rdi+40h]
0x14007b4f2  call    PplpLazyInitializeLookasideList
0x14007b4f7  jmp     loc_14007B363
0x14007b4fc  cmp     cs:UxDebugDisableLookaside, 0
0x14007b503  jnz     loc_14007B7E4
0x14007b509  mov     rcx, cs:qword_1401A0640
0x14007b510  cmp     cs:UxCompactMode, 0
0x14007b517  mov     rdx, rsi
0x14007b51a  jz      short loc_14007B53A
0x14007b51c  call    PnlFreeToLookasideList
0x14007b521  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14007b528  jnz     loc_14007B8A2
0x14007b52e  mov     [rbx+600h], r15
0x14007b535  jmp     loc_14007B205
0x14007b53a  mov     r8d, [rsi]
0x14007b53d  call    PplFreeToLookasideListProcessor
0x14007b542  jmp     short loc_14007B521
0x14007b544  lea     rdx, [rsi+14h]; BugCheckParameter2
0x14007b548  mov     eax, edi
0x14007b54a  lock xadd [rdx], eax
  ... truncated ...
```
