# UlpCompleteSendCacheEntryWorker

- ea: `0x1400384e0`
- end: `0x140038d42`
- name: `UlpCompleteSendCacheEntryWorker`
- size: `2146`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000a350`
- `0x14000a520`
- `0x14000c390`
- `0x140022610`
- `0x1400384e0`
- `0x140038d48`
- `0x140038e80`
- `0x140038f70`
- `0x140039340`
- `0x140049d08`
- `0x14005dfd0`
- `0x1400b1acc`
- `0x1400ca724`
- `0x1400ca7e4`
- `0x1400e3628`
- `0x1400e8f0c`
- `0x14011bcc4`
- `0x14013dd68`
- `0x14014b110`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4b0c`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140038769`
- `ntoskrnl!KeGetCurrentIrql` at `0x140038769`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400388c8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400388c8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400386a1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400386a1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140038825`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140038825`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003887b`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14003887b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140038cd3`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140038cd3`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140038794`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140038794`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400387d0`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400387d0`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140038942`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140038942`
- `ntoskrnl!KeSetEvent` at `0x1400388e6`
- `ntoskrnl!KeSetEvent` at `0x1400388e6`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003884e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14003884e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400389fb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400389fb`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140038925`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140038925`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c5c`

## string_xrefs

- `0x140175701`: `SendCacheEntryFailed`

## pseudocode

```c
void __fastcall UlpCompleteSendCacheEntryWorker(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v4; // r12
  int v5; // edi
  void *v6; // r14
  unsigned int v7; // r15d
  __int64 HkeContextFromRequest; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rdi
  void *v14; // rcx
  bool v15; // zf
  unsigned __int64 v16; // rdi
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rdi
  void *CurrentServerSilo; // rbx
  char v21; // si
  __int64 v22; // rax
  __int64 v23; // r14
  ULONG v24; // esi
  ULONG_PTR v25; // rdx
  int v26; // eax
  __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  ULONG_PTR v30; // rdx
  __int64 v31; // rdi
  USHORT CurrentNodeNumber; // ax
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // r8
  char v36; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int8 v37; // [rsp+41h] [rbp-88h] BYREF
  _BYTE v38[6]; // [rsp+42h] [rbp-87h] BYREF
  __int128 v39; // [rsp+48h] [rbp-81h] BYREF
  __int64 v40; // [rsp+58h] [rbp-71h]
  __int128 v41; // [rsp+60h] [rbp-69h] BYREF
  _DWORD v42[24]; // [rsp+70h] [rbp-59h] BYREF

  v37 = 0;
  v36 = 0;
  v38[0] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 196, WPP_173ede4a325638307373c19033e5a27a_Traceguids, a1);
  v2 = *(_QWORD *)(a1 + 96);
  v3 = a1 - 32;
  v4 = *(_QWORD *)(v2 + 24);
  v5 = *(_DWORD *)(v3 + 160);
  v6 = *(void **)(v3 + 80);
  v36 = 0;
  v37 = 0;
  if ( v5 < 0 )
  {
    v28 = *(_QWORD *)(v2 + 24);
    if ( v28 )
    {
      v29 = *(_QWORD *)(v28 + 1096);
      if ( (*(_BYTE *)(v29 + 1760) & 0x20) != 0
        && (!*(_QWORD *)(v29 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v2, v28, 0)) )
      {
        McTemplateK0xsq_EtwWriteTransfer(
          *(_QWORD *)(*(_QWORD *)(v2 + 24) + 1096LL) + 1688,
          v28,
          v2 + 72,
          *(_QWORD *)(v2 + 56),
          (__int64)"SendCacheEntryFailed",
          v5);
      }
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_dq(1040, 197, WPP_173ede4a325638307373c19033e5a27a_Traceguids, (unsigned int)v5, *(_QWORD *)(v2 + 56));
    UlCloseConnection(v4);
  }
  UlSetSendCompleteState(v2, 1, 0, (unsigned int)&v36, (__int64)&v37, (__int64)v38, *(_QWORD *)(v3 + 168), (__int64)v6);
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 80) + 576LL) )
    UlLogHttpCacheResponse(v3, 0);
  if ( v38[0] && (*(_DWORD *)(v2 + 2216) & 7) != 0 )
  {
    v39 = 0;
    v40 = 0;
    v7 = 0;
    v41 = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_qq(1033, 220, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v2, *(_QWORD *)(v2 + 64));
    HkeContextFromRequest = UlGetHkeContextFromRequest(v2, 0);
    v9 = HkeContextFromRequest;
    if ( HkeContextFromRequest )
    {
      if ( !*(_DWORD *)(HkeContextFromRequest + 136) && *(_DWORD *)(HkeContextFromRequest + 256) == 1 )
      {
        *(_QWORD *)&v39 = 0;
        v40 = 0;
        DWORD2(v39) = 0;
        v7 = UlHkeIndicatePublishEntityRequest(HkeContextFromRequest, &v39, 1, &v41);
      }
      UlHkeCancelCalloutContext(v9, 0);
      UlHkeDereferenceCalloutContext(v9, 10, v35);
    }
    v10 = UlGetHkeContextFromRequest(v2, 1);
    v11 = v10;
    if ( v10 )
    {
      UlHkeCancelCalloutContext(v10, 0);
      UlHkeDereferenceCalloutContext(v11, 10, v33);
    }
    v12 = UlGetHkeContextFromRequest(v2, 2);
    v13 = v12;
    if ( v12 )
    {
      UlHkeCancelCalloutContext(v12, 0);
      UlHkeDereferenceCalloutContext(v13, 10, v34);
    }
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_d(1033, 221, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v7);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 203, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v3);
  v14 = *(void **)(v3 + 144);
  if ( v14 )
  {
    UlCleanupRangeCacheTracker(v14);
    *(_QWORD *)(v3 + 144) = 0;
  }
  if ( *(_BYTE *)(v3 + 20) )
  {
    v15 = UxDebugDisableLookaside == 0;
    *(_DWORD *)(v3 + 16) = 1094929525;
    if ( v15 )
    {
      if ( UxCompactMode )
      {
        v31 = qword_1401A01F0;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        PplFreeToLookasideListProcessor(v31, v3, CurrentNodeNumber);
      }
      else
      {
        v16 = qword_1401A01F0 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v3 + 1) << 7);
        if ( !*(_BYTE *)(v16 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A01F0, v16 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 64), (PVOID)v3);
      }
    }
    else
    {
      memset(v42, 0, sizeof(v42));
      v42[10] = dword_1401A0208;
      ((void (__fastcall *)(__int64, _DWORD *))off_1401A0218)(v3, v42);
    }
  }
  else
  {
    *(_DWORD *)(v3 + 16) = 1633897589;
    ExFreePoolWithTag((PVOID)v3, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 204, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
  *(_QWORD *)(v2 + 1696) = 0;
  UlCheckinUriCacheEntry(v6);
  if ( v36 )
    UlResumeParsing(v4, v37);
  v18 = _InterlockedDecrement((volatile signed __int32 *)(v2 + 48));
  if ( UxDebugCheckRefcount && v18 <= -1 )
    UlBugCheckEx(3u, v2 + 48, 0x22u, v18);
  if ( !v18 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_qq(1032, 40, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v2, *(_QWORD *)(v2 + 64));
    if ( (*(_DWORD *)(v2 + 2264) & 1) != 0 || *(_QWORD *)(v2 + 2288) || *(_QWORD *)(v2 + 2312) )
    {
      v30 = v2 + 1248;
      if ( *(_QWORD *)(v2 + 1248) || *(_QWORD *)(v2 + 1264) || *(_QWORD *)(v2 + 1280) )
        UlBugCheckEx(1u, v30, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x645u);
      LOBYTE(v17) = 1;
      UlThreadPoolEnqueueWorkItem(0, v30, UlpFreeHttpRequest, v17, *(_QWORD *)(*(_QWORD *)(v2 + 24) + 1088LL), -1);
      goto LABEL_49;
    }
    v19 = v2 + 1248;
    if ( *(_QWORD *)(v2 + 1248) || *(_QWORD *)(v2 + 1264) || *(_QWORD *)(v2 + 1280) )
      UlBugCheckEx(1u, v2 + 1248, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x64Du);
    CurrentServerSilo = *(void **)(*(_QWORD *)(v2 + 24) + 1088LL);
    if ( KeGetCurrentIrql() )
    {
      v24 = 0;
      if ( (unsigned int)dword_1401A3F08 > 1 )
      {
        v24 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F20 )
          v24 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v19 + 32) = CurrentServerSilo;
      *(_QWORD *)&v41 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v41);
      v25 = v41 + 24;
      v26 = _InterlockedIncrement((volatile signed __int32 *)(v41 + 24));
      if ( UxDebugCheckRefcount && v26 <= -1 )
        UlBugCheckEx(3u, v25, 0xDu, v26);
      *(_BYTE *)(v19 + 24) = 1;
      v27 = *(_QWORD *)(qword_1401A3F10 + 8LL * v24);
      *(_QWORD *)(v19 + 16) = UlpFreeHttpRequest;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v27 + 16), (PSLIST_ENTRY)v19) )
      {
        KeSetEvent((PRKEVENT)(v27 + 32), 0, 0);
        if ( *(_BYTE *)(*(_QWORD *)v27 + 33LL) )
        {
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v27 + 68), 1, 0) )
          {
            if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_Dd(
                1304,
                18,
                WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
                *(unsigned int *)(v27 + 8),
                **(_DWORD **)v27);
            _InterlockedIncrement((volatile signed __int32 *)(v27 + 64));
            ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
            IoQueueWorkItemEx(*(PIO_WORKITEM *)(v27 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v27);
          }
        }
      }
      goto LABEL_49;
    }
    v21 = 0;
    v41 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v23 = *((_QWORD *)&v41 + 1);
    }
    else
    {
      v22 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v23 = v22;
      v21 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v22, CurrentServerSilo);
        UlpFreeHttpRequest(v19);
        goto LABEL_46;
      }
    }
    UlpFreeHttpRequest(v19);
    if ( !v21 )
    {
LABEL_49:
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 41, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
      goto LABEL_51;
    }
LABEL_46:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v23);
    PsDetachSiloFromCurrentThread(v23);
    goto LABEL_49;
  }
LABEL_51:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 198, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
}

```

## disassembly

```asm
0x1400384e0  push    rbp
0x1400384e2  push    rbx
0x1400384e3  push    rsi
0x1400384e4  push    rdi
0x1400384e5  push    r12
0x1400384e7  push    r13
0x1400384e9  push    r14
0x1400384eb  push    r15
0x1400384ed  lea     rbp, [rsp-1Fh]
0x1400384f2  sub     rsp, 0E8h
0x1400384f9  mov     rax, cs:__security_cookie
0x140038500  xor     rax, rsp
0x140038503  mov     [rbp+57h+var_50], rax
0x140038507  mov     rsi, rcx
0x14003850a  mov     [rsp+120h+var_DF], 0
0x14003850f  mov     [rsp+120h+var_E0], 0
0x140038514  mov     [rsp+120h+var_DE], 0
0x140038519  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140038520  jnz     loc_140038A52
0x140038526  mov     rbx, [rsi+60h]
0x14003852a  add     rsi, 0FFFFFFFFFFFFFFE0h
0x14003852e  mov     r12, [rbx+18h]
0x140038532  mov     edi, [rsi+0A0h]
0x140038538  mov     r14, [rsi+50h]
0x14003853c  mov     [rsp+120h+var_E0], 0
0x140038541  mov     [rsp+120h+var_DF], 0
0x140038546  test    edi, edi
0x140038548  js      loc_140038953
0x14003854e  mov     rax, [rsi+0A8h]
0x140038555  lea     r9, [rsp+120h+var_E0]
0x14003855a  mov     [rsp+120h+var_E8], r14
0x14003855f  xor     r8d, r8d
0x140038562  mov     [rsp+120h+var_F0], rax
0x140038567  mov     dl, 1
0x140038569  lea     rax, [rsp+120h+var_DE]
0x14003856e  mov     rcx, rbx
0x140038571  mov     [rsp+120h+var_F8], rax
0x140038576  lea     rax, [rsp+120h+var_DF]
0x14003857b  mov     [rsp+120h+var_100], rax
0x140038580  call    UlSetSendCompleteState
0x140038585  mov     rax, [rsi+50h]
0x140038589  cmp     byte ptr [rax+240h], 0
0x140038590  jnz     loc_140038B1D
0x140038596  xor     r13d, r13d
0x140038599  mov     r15d, 1
0x14003859f  cmp     [rsp+120h+var_DE], r13b
0x1400385a4  jz      loc_140038631
0x1400385aa  mov     eax, [rbx+8A8h]
0x1400385b0  test    al, 7
0x1400385b2  jz      short loc_140038631
0x1400385b4  xorps   xmm0, xmm0
0x1400385b7  xor     eax, eax
0x1400385b9  movups  [rsp+120h+var_D8], xmm0
0x1400385be  mov     [rbp+57h+var_C8], rax
0x1400385c2  mov     r15d, r13d
0x1400385c5  movups  [rbp+57h+var_C0], xmm0
0x1400385c9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400385d0  jnz     loc_140038B2C
0x1400385d6  xor     edx, edx
0x1400385d8  mov     rcx, rbx
0x1400385db  call    UlGetHkeContextFromRequest
0x1400385e0  mov     rdi, rax
0x1400385e3  test    rax, rax
0x1400385e6  jnz     loc_140038B53
0x1400385ec  mov     edx, 1
0x1400385f1  mov     rcx, rbx
0x1400385f4  call    UlGetHkeContextFromRequest
0x1400385f9  mov     rdi, rax
0x1400385fc  test    rax, rax
0x1400385ff  jnz     loc_140038B99
0x140038605  mov     edx, 2
0x14003860a  mov     rcx, rbx
0x14003860d  call    UlGetHkeContextFromRequest
0x140038612  mov     rdi, rax
0x140038615  test    rax, rax
0x140038618  jnz     loc_140038BB5
0x14003861e  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140038625  jnz     loc_140038BD1
0x14003862b  mov     r15d, 1
0x140038631  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140038638  jnz     loc_140038BEF
0x14003863e  mov     rcx, [rsi+90h]; P
0x140038645  test    rcx, rcx
0x140038648  jnz     loc_140038C0D
0x14003864e  cmp     [rsi+14h], r13b
0x140038652  jz      loc_140038C50
0x140038658  cmp     cs:UxDebugDisableLookaside, r13b
0x14003865f  mov     dword ptr [rsi+10h], 41434C75h
0x140038666  jnz     loc_140038C1E
0x14003866c  cmp     cs:UxCompactMode, r13b
0x140038673  jnz     loc_1400389F4
0x140038679  mov     edi, [rsi]
0x14003867b  mov     rcx, cs:qword_1401A01F0
0x140038682  inc     edi
0x140038684  shl     rdi, 7
0x140038688  add     rdi, rcx
0x14003868b  movzx   eax, byte ptr [rdi+0B0h]
0x140038692  test    al, al
0x140038694  jz      loc_140038A97
0x14003869a  mov     rdx, rsi; Entry
0x14003869d  lea     rcx, [rdi+40h]; Lookaside
0x1400386a1  call    cs:__imp_ExFreeToLookasideListEx
0x1400386a8  nop     dword ptr [rax+rax+00h]
0x1400386ad  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400386b4  jnz     loc_140038C6D
0x1400386ba  mov     rcx, r14; P
0x1400386bd  mov     [rbx+6A0h], r13
0x1400386c4  call    UlCheckinUriCacheEntry
0x1400386c9  cmp     [rsp+120h+var_E0], r13b
0x1400386ce  jnz     loc_140038C88
0x1400386d4  lea     rdx, [rbx+30h]; BugCheckParameter2
0x1400386d8  mov     eax, 0FFFFFFFFh
0x1400386dd  lock xadd [rdx], eax
0x1400386e1  dec     eax
0x1400386e3  cmp     cs:UxDebugCheckRefcount, r13b
0x1400386ea  jnz     loc_14003898C
0x1400386f0  test    eax, eax
0x1400386f2  jnz     loc_1400387E9
0x1400386f8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400386ff  jnz     loc_140038AA5
0x140038705  mov     eax, [rbx+8D8h]
0x14003870b  test    al, 1
0x14003870d  jnz     loc_1400389C6
0x140038713  cmp     [rbx+8F0h], r13
0x14003871a  jnz     loc_1400389C6
0x140038720  cmp     [rbx+908h], r13
0x140038727  jnz     loc_1400389C6
0x14003872d  lea     rdi, [rbx+4E0h]
0x140038734  cmp     [rdi], r13
0x140038737  jnz     short loc_140038745
0x140038739  cmp     [rdi+10h], r13
0x14003873d  jnz     short loc_140038745
0x14003873f  cmp     [rdi+20h], r13
0x140038743  jz      short loc_14003875E
0x140038745  mov     r9d, 64Dh; BugCheckParameter4
0x14003874b  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x140038752  mov     rdx, rdi; BugCheckParameter2
0x140038755  mov     rcx, r15; BugCheckParameter1
0x140038758  call    UlBugCheckEx
0x14003875e  mov     rax, [rbx+18h]
0x140038762  mov     rbx, [rax+440h]
0x140038769  call    cs:__imp_KeGetCurrentIrql
0x140038770  nop     dword ptr [rax+rax+00h]
0x140038775  test    al, al
0x140038777  jnz     loc_140038817
0x14003877d  xor     sil, sil
0x140038780  xorps   xmm0, xmm0
0x140038783  movups  [rbp+57h+var_C0], xmm0
0x140038787  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14003878b  jz      loc_140038A1B
0x140038791  mov     rcx, rbx
0x140038794  call    cs:__imp_PsAttachSiloToCurrentThread
0x14003879b  nop     dword ptr [rax+rax+00h]
0x1400387a0  mov     r14, rax
0x1400387a3  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400387aa  mov     sil, 1
0x1400387ad  jnz     loc_140038ACC
0x1400387b3  mov     rcx, rdi
0x1400387b6  call    UlpFreeHttpRequest
0x1400387bb  test    sil, sil
0x1400387be  jz      short loc_1400387DC
0x1400387c0  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400387c7  jnz     loc_140038C9A
0x1400387cd  mov     rcx, r14
0x1400387d0  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400387d7  nop     dword ptr [rax+rax+00h]
0x1400387dc  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400387e3  jnz     loc_140038D0C
0x1400387e9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400387f0  jnz     loc_140038D27
0x1400387f6  mov     rcx, [rbp+57h+var_50]
0x1400387fa  xor     rcx, rsp; StackCookie
0x1400387fd  call    __security_check_cookie
0x140038802  add     rsp, 0E8h
0x140038809  pop     r15
0x14003880b  pop     r14
0x14003880d  pop     r13
0x14003880f  pop     r12
0x140038811  pop     rdi
0x140038812  pop     rsi
0x140038813  pop     rbx
0x140038814  pop     rbp
0x140038815  retn
0x140038817  cmp     cs:dword_1401A3F08, 1
0x14003881e  mov     esi, r13d
0x140038821  jbe     short loc_140038848
0x140038823  xor     ecx, ecx; ProcNumber
0x140038825  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14003882c  nop     dword ptr [rax+rax+00h]
0x140038831  xor     edx, edx
0x140038833  div     cs:UxNumberOfProcessors
0x140038839  cmp     cs:byte_1401A3F20, r13b
0x140038840  mov     esi, edx
0x140038842  jnz     loc_140038CB8
0x140038848  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14003884c  jnz     short loc_14003885D
0x14003884e  call    cs:__imp_PsGetCurrentServerSilo
0x140038855  nop     dword ptr [rax+rax+00h]
0x14003885a  mov     rbx, rax
0x14003885d  mov     [rdi+20h], rbx
0x140038861  mov     qword ptr [rbp+57h+var_C0], r13
0x140038865  test    rbx, rbx
0x140038868  jnz     loc_140038CCB
0x14003886e  mov     edx, cs:UxPodMonitorSlot
0x140038874  lea     r8, [rbp+57h+var_C0]
0x140038878  mov     rcx, rbx
0x14003887b  call    cs:__imp_PsGetPermanentSiloContext
0x140038882  nop     dword ptr [rax+rax+00h]
0x140038887  mov     rdx, qword ptr [rbp+57h+var_C0]
0x14003888b  mov     eax, r15d
0x14003888e  add     rdx, 18h; BugCheckParameter2
0x140038892  lock xadd [rdx], eax
0x140038896  inc     eax
0x140038898  cmp     cs:UxDebugCheckRefcount, r13b
0x14003889f  jnz     loc_1400389A9
0x1400388a5  mov     byte ptr [rdi+18h], 1
0x1400388a9  lea     r8, UlpFreeHttpRequest
0x1400388b0  mov     rax, cs:qword_1401A3F10
0x1400388b7  mov     rdx, rdi; ListEntry
0x1400388ba  mov     ecx, esi
0x1400388bc  mov     rbx, [rax+rcx*8]
0x1400388c0  mov     [rdi+10h], r8
0x1400388c4  lea     rcx, [rbx+10h]; ListHead
0x1400388c8  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400388cf  nop     dword ptr [rax+rax+00h]
0x1400388d4  test    rax, rax
0x1400388d7  jnz     loc_1400387DC
0x1400388dd  lea     rcx, [rbx+20h]; Event
0x1400388e1  xor     r8d, r8d; Wait
0x1400388e4  xor     edx, edx; Increment
0x1400388e6  call    cs:__imp_KeSetEvent
0x1400388ed  nop     dword ptr [rax+rax+00h]
0x1400388f2  mov     rax, [rbx]
0x1400388f5  cmp     [rax+21h], r13b
0x1400388f9  jz      loc_1400387DC
0x1400388ff  xor     eax, eax
0x140038901  lock cmpxchg [rbx+44h], r15d
0x140038907  jnz     loc_1400387DC
0x14003890d  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 1
0x140038914  jnz     loc_140038CE4
0x14003891a  lock inc dword ptr [rbx+40h]
0x14003891e  lea     rcx, UlThreadPoolIoWorkItemsRundown; RunRef
0x140038925  call    cs:__imp_ExAcquireRundownProtection
0x14003892c  nop     dword ptr [rax+rax+00h]
0x140038931  mov     rcx, [rbx+38h]; IoWorkItem
0x140038935  lea     rdx, UlpThreadPoolStarter; WorkerRoutine
0x14003893c  mov     r9, rbx; Context
0x14003893f  mov     r8d, r15d; QueueType
0x140038942  call    cs:__imp_IoQueueWorkItemEx
0x140038949  nop     dword ptr [rax+rax+00h]
0x14003894e  jmp     loc_1400387DC
0x140038953  mov     rdx, [rbx+18h]
0x140038957  test    rdx, rdx
0x14003895a  jz      short loc_140038970
0x14003895c  mov     rcx, [rdx+448h]
0x140038963  test    byte ptr [rcx+6E0h], 20h
0x14003896a  jnz     loc_140038AF7
0x140038970  test    byte ptr cs:xmmword_1401A2CA0+2, 1
0x140038977  jnz     loc_140038A70
0x14003897d  mov     dl, 1
0x14003897f  mov     rcx, r12
0x140038982  call    UlCloseConnection
0x140038987  jmp     loc_14003854E
0x14003898c  cmp     eax, 0FFFFFFFFh
0x14003898f  jg      loc_1400386F0
0x140038995  movsxd  r9, eax; BugCheckParameter4
0x140038998  mov     ecx, 3; BugCheckParameter1
0x14003899d  mov     r8d, 22h ; '"'; BugCheckParameter3
0x1400389a3  call    UlBugCheckEx
0x1400389a9  cmp     eax, 0FFFFFFFFh
0x1400389ac  jg      loc_1400388A5
0x1400389b2  movsxd  r9, eax; BugCheckParameter4
0x1400389b5  mov     ecx, 3; BugCheckParameter1
0x1400389ba  mov     r8d, 0Dh; BugCheckParameter3
0x1400389c0  call    UlBugCheckEx
0x1400389c6  lea     rdx, [rbx+4E0h]; BugCheckParameter2
0x1400389cd  cmp     [rdx], r13
0x1400389d0  jnz     short loc_1400389DE
0x1400389d2  cmp     [rdx+10h], r13
0x1400389d6  jnz     short loc_1400389DE
0x1400389d8  cmp     [rdx+20h], r13
0x1400389dc  jz      short loc_140038A24
0x1400389de  mov     r9d, 645h; BugCheckParameter4
0x1400389e4  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x1400389eb  mov     rcx, r15; BugCheckParameter1
0x1400389ee  call    UlBugCheckEx
0x1400389f4  mov     rdi, cs:qword_1401A01F0
0x1400389fb  call    cs:__imp_KeGetCurrentNodeNumber
0x140038a02  nop     dword ptr [rax+rax+00h]
0x140038a07  movzx   r8d, ax
0x140038a0b  mov     rdx, rsi
0x140038a0e  mov     rcx, rdi
0x140038a11  call    PplFreeToLookasideListProcessor
0x140038a16  jmp     loc_1400386AD
0x140038a1b  mov     r14, qword ptr [rbp+57h+var_C0+8]
0x140038a1f  jmp     loc_1400387B3
0x140038a24  mov     rax, [rbx+18h]
0x140038a28  lea     r8, UlpFreeHttpRequest
0x140038a2f  mov     dword ptr [rsp+120h+var_F8], 0FFFFFFFFh
0x140038a37  mov     r9b, 1
  ... truncated ...
```
