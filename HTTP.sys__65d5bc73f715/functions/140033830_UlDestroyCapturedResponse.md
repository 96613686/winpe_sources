# UlDestroyCapturedResponse

- ea: `0x140033830`
- end: `0x14003424e`
- name: `UlDestroyCapturedResponse`
- size: `2590`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001d270`
- `0x140033310`
- `0x1400354a0`
- `0x1400474d0`
- `0x1400548d4`
- `0x1400ba6bc`
- `0x1400c9ef0`
- `0x1400ca224`
- `0x1400ead00`
- `0x1400eb5e0`
- `0x1400ecea4`
- `0x1400f1b08`
- `0x1400f400c`
- `0x140129028`
- `0x14012af00`
- `0x14012c60c`

## callees

- `0x14000a350`
- `0x14000c390`
- `0x140022610`
- `0x140033830`
- `0x140038e80`
- `0x140049d08`
- `0x14005dfd0`
- `0x14006e4ec`
- `0x140087990`
- `0x1400aece4`
- `0x1400c79c8`
- `0x1400ca7e4`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9e44`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140033b54`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033b54`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033dcc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140033dcc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400339bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033a2a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033a99`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033c2c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400339bb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033a2a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033a99`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140033c2c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033d22`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033d22`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140033d7a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140033d7a`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400341c5`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400341c5`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033b80`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140033b80`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033bbc`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140033bbc`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140033e47`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140033e47`
- `ntoskrnl!KeSetEvent` at `0x140033dea`
- `ntoskrnl!KeSetEvent` at `0x140033dea`
- `ntoskrnl!IoFreeMdl` at `0x1400338da`
- `ntoskrnl!IoFreeMdl` at `0x1400338da`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033d4b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140033d4b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140033ef3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140033ef3`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140033e2a`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140033e2a`
- `ntoskrnl!ObfDereferenceObject` at `0x140033cf8`
- `ntoskrnl!ObfDereferenceObject` at `0x140033cf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033c92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ca8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f57`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400340fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034115`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003412f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034149`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003415e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003417b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033c92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033ca8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033cbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033f57`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400340fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034115`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003412f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034149`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003415e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003417b`

## pseudocode

```c
void __fastcall UlDestroyCapturedResponse(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  volatile signed __int32 *v5; // rcx
  __int64 v6; // rbx
  unsigned int i; // ebp
  __int64 v8; // rdi
  int v9; // eax
  struct _MDL *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rdi
  unsigned __int64 v14; // rsi
  void *v15; // rdi
  unsigned __int64 v16; // rsi
  void *v17; // rdi
  unsigned __int64 v18; // rsi
  __int64 v19; // rax
  volatile signed __int32 *v20; // rdx
  int v21; // r14d
  __int64 v22; // rsi
  __int64 v23; // rdi
  void *CurrentServerSilo; // rsi
  char v25; // bp
  __int64 v26; // rax
  __int64 v27; // r14
  bool v28; // zf
  unsigned __int64 v29; // rdi
  void *v30; // rcx
  ULONG v31; // ebp
  ULONG_PTR v32; // rdx
  int v33; // eax
  __int64 v34; // r14
  __int64 v35; // rcx
  ULONG_PTR v36; // rdx
  __int64 v37; // rdi
  USHORT CurrentNodeNumber; // ax
  int v39; // eax
  __int128 v40; // [rsp+30h] [rbp-98h] BYREF
  _DWORD v41[24]; // [rsp+40h] [rbp-88h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_q(1033, 99, WPP_173ede4a325638307373c19033e5a27a_Traceguids, a1);
  v5 = *(volatile signed __int32 **)(a1 - 472);
  v6 = a1 - 608;
  if ( v5 )
  {
    v39 = _InterlockedDecrement(v5 + 1);
    if ( UxDebugCheckRefcount && v39 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v5 + 1), 0x23u, v39);
    if ( !v39 )
      UcFreeStream((PVOID)v5);
    *(_QWORD *)(v6 + 136) = 0;
  }
  for ( i = 0; i < *(_DWORD *)(v6 + 880); ++i )
  {
    v8 = *(_QWORD *)(v6 + 888) + 80LL * i;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_q(1033, 97, WPP_173ede4a325638307373c19033e5a27a_Traceguids, *(_QWORD *)(v6 + 888) + 80LL * i);
    if ( v8 )
    {
      v9 = *(_DWORD *)v8;
      if ( *(_DWORD *)v8 == 3 )
      {
        v10 = *(struct _MDL **)(v8 + 8);
        if ( v10 )
        {
          IoFreeMdl(v10);
          *(_QWORD *)(v8 + 8) = 0;
        }
        v11 = *(void **)(v8 + 16);
        if ( v11 )
        {
          UlCheckinUriCacheEntry(v11);
          *(_QWORD *)(v8 + 16) = 0;
        }
      }
      else if ( v9 == 2 )
      {
        if ( *(_QWORD *)(v8 + 40) )
        {
          if ( SBYTE8(xmmword_1401A2CA0) < 0 )
            WPP_SF_q(1287, 13, WPP_356047d6fb313977e1ed462fdcc3e5cd_Traceguids, v8 + 24);
          v30 = *(void **)(v8 + 40);
          if ( v30 )
          {
            ObfDereferenceObject(v30);
            *(_QWORD *)(v8 + 40) = 0;
          }
          *(_DWORD *)(v8 + 24) = 1701603686;
        }
      }
      else if ( v9 == 4 )
      {
        v35 = *(_QWORD *)(v8 + 24);
        if ( v35 )
        {
          UlHkeDereferenceCalloutContext(v35, 52, a3);
          *(_QWORD *)(v8 + 24) = 0;
        }
      }
    }
    *(_DWORD *)v8 = 0;
    if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
      WPP_SF_(1033, 98, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
  }
  if ( *(_QWORD *)(v6 + 544) )
    UlHkeBuilderCleanup();
  if ( *(_BYTE *)(v6 + 52) )
    ExFreePoolWithTag(*(PVOID *)(v6 + 192), 0);
  if ( *(_BYTE *)(v6 + 53) )
    ExFreePoolWithTag(*(PVOID *)(v6 + 208), 0);
  if ( *(_BYTE *)(v6 + 54) )
    ExFreePoolWithTag(*(PVOID *)(v6 + 696), 0);
  if ( *(_BYTE *)(v6 + 55) )
  {
    ExFreePoolWithTag(*(PVOID *)(v6 + 736), 0);
    ExFreePoolWithTag(*(PVOID *)(v6 + 672), 0);
  }
  if ( *(_QWORD *)(v6 + 512) )
    UlDestroyLogDataBuffer();
  v12 = *(void **)(v6 + 256);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  v13 = *(void **)(v6 + 336);
  if ( v13 )
  {
    if ( *(_BYTE *)(v6 + 344) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *(_QWORD *)(v6 + 336));
      }
      else
      {
        v14 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 348) + 1) << 7);
        if ( !*(_BYTE *)(v14 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v14 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v14 + 64), v13);
      }
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(v6 + 336), 0);
    }
  }
  *(_OWORD *)(v6 + 328) = 0;
  *(_QWORD *)(v6 + 344) = 0;
  v15 = *(void **)(v6 + 296);
  if ( v15 )
  {
    if ( *(_BYTE *)(v6 + 304) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *(_QWORD *)(v6 + 296));
      }
      else
      {
        v16 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 308) + 1) << 7);
        if ( !*(_BYTE *)(v16 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v16 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 64), v15);
      }
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(v6 + 296), 0);
    }
  }
  *(_OWORD *)(v6 + 288) = 0;
  *(_QWORD *)(v6 + 304) = 0;
  v17 = *(void **)(v6 + 376);
  if ( v17 )
  {
    if ( *(_BYTE *)(v6 + 384) )
    {
      if ( UxCompactMode )
      {
        PnlFreeToLookasideList(qword_1401A0490, *(_QWORD *)(v6 + 376));
      }
      else
      {
        v18 = qword_1401A0490 + ((unsigned __int64)(unsigned int)(*(_DWORD *)(v6 + 388) + 1) << 7);
        if ( !*(_BYTE *)(v18 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0490, v18 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v18 + 64), v17);
      }
    }
    else
    {
      ExFreePoolWithTag(*(PVOID *)(v6 + 376), 0);
    }
  }
  v19 = 0;
  *(_OWORD *)(v6 + 368) = 0;
  *(_QWORD *)(v6 + 384) = 0;
  v20 = (volatile signed __int32 *)(*(_QWORD *)(v6 + 24) + 48LL);
  v21 = _InterlockedDecrement(v20);
  if ( UxDebugCheckRefcount && v21 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v20, 0x17u, v21);
  if ( !v21 )
  {
    v22 = *(_QWORD *)(v6 + 24);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    {
      if ( v22 )
        v19 = *(_QWORD *)(v22 + 64);
      WPP_SF_qq(1032, 40, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v22, v19);
    }
    if ( (*(_DWORD *)(v22 + 2264) & 1) != 0 || *(_QWORD *)(v22 + 2288) || *(_QWORD *)(v22 + 2312) )
    {
      v36 = v22 + 1248;
      if ( *(_QWORD *)(v22 + 1248) || *(_QWORD *)(v22 + 1264) || *(_QWORD *)(v22 + 1280) )
        UlBugCheckEx(1u, v36, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x645u);
      LOBYTE(a4) = 1;
      UlThreadPoolEnqueueWorkItem(0, v36, UlpFreeHttpRequest, a4, *(_QWORD *)(*(_QWORD *)(v22 + 24) + 1088LL), -1);
      goto LABEL_65;
    }
    v23 = v22 + 1248;
    if ( *(_QWORD *)(v22 + 1248) || *(_QWORD *)(v22 + 1264) || *(_QWORD *)(v22 + 1280) )
      UlBugCheckEx(1u, v22 + 1248, (ULONG_PTR)"minio\\http\\sys\\httpconn.c", 0x64Du);
    CurrentServerSilo = *(void **)(*(_QWORD *)(v22 + 24) + 1088LL);
    if ( KeGetCurrentIrql() )
    {
      v31 = 0;
      if ( (unsigned int)dword_1401A3F08 > 1 )
      {
        v31 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F20 )
          v31 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v23 + 32) = CurrentServerSilo;
      *(_QWORD *)&v40 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v40);
      v32 = v40 + 24;
      v33 = _InterlockedIncrement((volatile signed __int32 *)(v40 + 24));
      if ( UxDebugCheckRefcount && v33 <= -1 )
        UlBugCheckEx(3u, v32, 0xDu, v33);
      *(_BYTE *)(v23 + 24) = 1;
      v34 = *(_QWORD *)(qword_1401A3F10 + 8LL * v31);
      *(_QWORD *)(v23 + 16) = UlpFreeHttpRequest;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v34 + 16), (PSLIST_ENTRY)v23) )
      {
        KeSetEvent((PRKEVENT)(v34 + 32), 0, 0);
        if ( *(_BYTE *)(*(_QWORD *)v34 + 33LL) )
        {
          if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v34 + 68), 1, 0) )
          {
            if ( (BYTE11(xmmword_1401A2CA0) & 1) != 0 )
              WPP_SF_Dd(
                1304,
                18,
                WPP_c88c5541e4f33e794c7dde5eb878f2f0_Traceguids,
                *(unsigned int *)(v34 + 8),
                **(_DWORD **)v34);
            _InterlockedIncrement((volatile signed __int32 *)(v34 + 64));
            ExAcquireRundownProtection(&UlThreadPoolIoWorkItemsRundown);
            IoQueueWorkItemEx(*(PIO_WORKITEM *)(v34 + 56), UlpThreadPoolStarter, DelayedWorkQueue, (PVOID)v34);
          }
        }
      }
      goto LABEL_65;
    }
    v25 = 0;
    v40 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v27 = *((_QWORD *)&v40 + 1);
    }
    else
    {
      v26 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v27 = v26;
      v25 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v26, CurrentServerSilo);
        UlpFreeHttpRequest(v23);
        goto LABEL_62;
      }
    }
    UlpFreeHttpRequest(v23);
    if ( !v25 )
    {
LABEL_65:
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_(1032, 41, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
      goto LABEL_67;
    }
LABEL_62:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v27);
    PsDetachSiloFromCurrentThread(v27);
    goto LABEL_65;
  }
LABEL_67:
  *(_QWORD *)(v6 + 24) = 0;
  if ( *(_BYTE *)(v6 + 44) )
  {
    v28 = UxDebugDisableLookaside == 0;
    *(_DWORD *)(v6 + 16) = 1380535413;
    if ( v28 )
    {
      if ( UxCompactMode )
      {
        v37 = qword_1401A0250;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        PplFreeToLookasideListProcessor(v37, v6, CurrentNodeNumber);
      }
      else
      {
        v29 = qword_1401A0250 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v6 + 1) << 7);
        if ( !*(_BYTE *)(v29 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A0250, v29 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v29 + 64), (PVOID)v6);
      }
    }
    else
    {
      memset(v41, 0, sizeof(v41));
      v41[10] = dword_1401A0268;
      ((void (__fastcall *)(__int64, _DWORD *))off_1401A0278)(v6, v41);
    }
  }
  else
  {
    *(_DWORD *)(v6 + 16) = 1919503477;
    ExFreePoolWithTag((PVOID)v6, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1033, 100, WPP_173ede4a325638307373c19033e5a27a_Traceguids);
}

```

## disassembly

```asm
0x140033830  push    rbx
0x140033832  push    r14
0x140033834  push    r15
0x140033836  sub     rsp, 0B0h
0x14003383d  mov     rax, cs:__security_cookie
0x140033844  xor     rax, rsp
0x140033847  mov     [rsp+0C8h+var_28], rax
0x14003384f  mov     rbx, rcx
0x140033852  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033859  jnz     loc_14003405D
0x14003385f  mov     rcx, [rbx-1D8h]; P
0x140033866  add     rbx, 0FFFFFFFFFFFFFDA0h
0x14003386d  xor     r15d, r15d
0x140033870  mov     r14d, 0FFFFFFFFh
0x140033876  test    rcx, rcx
0x140033879  jnz     loc_14003401E
0x14003387f  mov     [rsp+0C8h+arg_8], rbp
0x140033887  mov     ebp, r15d
0x14003388a  mov     [rsp+0C8h+arg_10], rsi
0x140033892  mov     [rsp+0C8h+arg_18], rdi
0x14003389a  cmp     [rbx+370h], r15d
0x1400338a1  jbe     short loc_140033911
0x1400338a3  mov     eax, ebp
0x1400338a5  lea     rdi, [rax+rax*4]
0x1400338a9  shl     rdi, 4
0x1400338ad  add     rdi, [rbx+378h]
0x1400338b4  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400338bb  jnz     loc_140034082
0x1400338c1  test    rdi, rdi
0x1400338c4  jz      short loc_1400338F7
0x1400338c6  mov     eax, [rdi]
0x1400338c8  cmp     eax, 3
0x1400338cb  jnz     loc_140033CCF
0x1400338d1  mov     rcx, [rdi+8]; Mdl
0x1400338d5  test    rcx, rcx
0x1400338d8  jz      short loc_1400338EA
0x1400338da  call    cs:__imp_IoFreeMdl
0x1400338e1  nop     dword ptr [rax+rax+00h]
0x1400338e6  mov     [rdi+8], r15
0x1400338ea  mov     rcx, [rdi+10h]; P
0x1400338ee  test    rcx, rcx
0x1400338f1  jnz     loc_1400340A0
0x1400338f7  mov     [rdi], r15d
0x1400338fa  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033901  jnz     loc_1400340CD
0x140033907  inc     ebp
0x140033909  cmp     ebp, [rbx+370h]
0x14003390f  jb      short loc_1400338A3
0x140033911  mov     rcx, [rbx+220h]
0x140033918  test    rcx, rcx
0x14003391b  jnz     loc_1400340E8
0x140033921  cmp     [rbx+34h], r15b
0x140033925  jnz     loc_1400340F2
0x14003392b  cmp     [rbx+35h], r15b
0x14003392f  jnz     loc_14003410C
0x140033935  cmp     [rbx+36h], r15b
0x140033939  jnz     loc_140034126
0x14003393f  cmp     [rbx+37h], r15b
0x140033943  jnz     loc_140034140
0x140033949  mov     rcx, [rbx+200h]
0x140033950  test    rcx, rcx
0x140033953  jnz     loc_14003416F
0x140033959  mov     rcx, [rbx+100h]; P
0x140033960  test    rcx, rcx
0x140033963  jnz     loc_140034179
0x140033969  mov     rdi, [rbx+150h]
0x140033970  test    rdi, rdi
0x140033973  jz      short loc_1400339C7
0x140033975  cmp     [rbx+158h], r15b
0x14003397c  jz      loc_140033C8D
0x140033982  cmp     cs:UxCompactMode, r15b
0x140033989  mov     rcx, cs:qword_1401A0490
0x140033990  jnz     loc_140033F68
0x140033996  mov     esi, [rbx+15Ch]
0x14003399c  inc     esi
0x14003399e  shl     rsi, 7
0x1400339a2  add     rsi, rcx
0x1400339a5  movzx   eax, byte ptr [rsi+0B0h]
0x1400339ac  test    al, al
0x1400339ae  jz      loc_140033FBB
0x1400339b4  mov     rdx, rdi; Entry
0x1400339b7  lea     rcx, [rsi+40h]; Lookaside
0x1400339bb  call    cs:__imp_ExFreeToLookasideListEx
0x1400339c2  nop     dword ptr [rax+rax+00h]
0x1400339c7  xor     eax, eax
0x1400339c9  xorps   xmm0, xmm0
0x1400339cc  movups  xmmword ptr [rbx+148h], xmm0
0x1400339d3  mov     [rbx+158h], rax
0x1400339da  mov     rdi, [rbx+128h]
0x1400339e1  test    rdi, rdi
0x1400339e4  jz      short loc_140033A36
0x1400339e6  cmp     [rbx+130h], al
0x1400339ec  jz      loc_140033CA3
0x1400339f2  cmp     cs:UxCompactMode, al
0x1400339f8  mov     rcx, cs:qword_1401A0490
0x1400339ff  jnz     loc_140033F75
0x140033a05  mov     esi, [rbx+134h]
0x140033a0b  inc     esi
0x140033a0d  shl     rsi, 7
0x140033a11  add     rsi, rcx
0x140033a14  movzx   eax, byte ptr [rsi+0B0h]
0x140033a1b  test    al, al
0x140033a1d  jz      loc_140033FC9
0x140033a23  mov     rdx, rdi; Entry
0x140033a26  lea     rcx, [rsi+40h]; Lookaside
0x140033a2a  call    cs:__imp_ExFreeToLookasideListEx
0x140033a31  nop     dword ptr [rax+rax+00h]
0x140033a36  xor     eax, eax
0x140033a38  xorps   xmm0, xmm0
0x140033a3b  movups  xmmword ptr [rbx+120h], xmm0
0x140033a42  mov     [rbx+130h], rax
0x140033a49  mov     rdi, [rbx+178h]
0x140033a50  test    rdi, rdi
0x140033a53  jz      short loc_140033AA5
0x140033a55  cmp     [rbx+180h], al
0x140033a5b  jz      loc_140033CB9
0x140033a61  cmp     cs:UxCompactMode, al
0x140033a67  mov     rcx, cs:qword_1401A0490
0x140033a6e  jnz     loc_140033F82
0x140033a74  mov     esi, [rbx+184h]
0x140033a7a  inc     esi
0x140033a7c  shl     rsi, 7
0x140033a80  add     rsi, rcx
0x140033a83  movzx   eax, byte ptr [rsi+0B0h]
0x140033a8a  test    al, al
0x140033a8c  jz      loc_140033FD7
0x140033a92  mov     rdx, rdi; Entry
0x140033a95  lea     rcx, [rsi+40h]; Lookaside
0x140033a99  call    cs:__imp_ExFreeToLookasideListEx
0x140033aa0  nop     dword ptr [rax+rax+00h]
0x140033aa5  xor     eax, eax
0x140033aa7  xorps   xmm0, xmm0
0x140033aaa  movups  xmmword ptr [rbx+170h], xmm0
0x140033ab1  mov     [rbx+180h], rax
0x140033ab8  mov     rdx, [rbx+18h]
0x140033abc  add     rdx, 30h ; '0'; BugCheckParameter2
0x140033ac0  lock xadd [rdx], r14d
0x140033ac5  dec     r14d
0x140033ac8  cmp     cs:UxDebugCheckRefcount, al
0x140033ace  jnz     loc_140033E58
0x140033ad4  test    r14d, r14d
0x140033ad7  jnz     loc_140033BD5
0x140033add  mov     rsi, [rbx+18h]
0x140033ae1  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140033ae8  jnz     loc_140033F8F
0x140033aee  mov     eax, [rsi+8D8h]
0x140033af4  test    al, 1
0x140033af6  jnz     loc_140033EBC
0x140033afc  cmp     [rsi+8F0h], r15
0x140033b03  jnz     loc_140033EBC
0x140033b09  cmp     [rsi+908h], r15
0x140033b10  jnz     loc_140033EBC
0x140033b16  lea     rdi, [rsi+4E0h]
0x140033b1d  cmp     [rdi], r15
0x140033b20  jnz     short loc_140033B2E
0x140033b22  cmp     [rdi+10h], r15
0x140033b26  jnz     short loc_140033B2E
0x140033b28  cmp     [rdi+20h], r15
0x140033b2c  jz      short loc_140033B49
0x140033b2e  mov     r9d, 64Dh; BugCheckParameter4
0x140033b34  lea     r8, aMinioHttpSysHt; "minio\\http\\sys\\httpconn.c"
0x140033b3b  mov     rdx, rdi; BugCheckParameter2
0x140033b3e  mov     ecx, 1; BugCheckParameter1
0x140033b43  call    UlBugCheckEx
0x140033b49  mov     rax, [rsi+18h]
0x140033b4d  mov     rsi, [rax+440h]
0x140033b54  call    cs:__imp_KeGetCurrentIrql
0x140033b5b  nop     dword ptr [rax+rax+00h]
0x140033b60  test    al, al
0x140033b62  jnz     loc_140033D14
0x140033b68  xor     bpl, bpl
0x140033b6b  xorps   xmm0, xmm0
0x140033b6e  movups  [rsp+0C8h+var_98], xmm0
0x140033b73  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140033b77  jz      loc_140033F13
0x140033b7d  mov     rcx, rsi
0x140033b80  call    cs:__imp_PsAttachSiloToCurrentThread
0x140033b87  nop     dword ptr [rax+rax+00h]
0x140033b8c  mov     r14, rax
0x140033b8f  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140033b96  mov     bpl, 1
0x140033b99  jnz     loc_140033FE5
0x140033b9f  mov     rcx, rdi
0x140033ba2  call    UlpFreeHttpRequest
0x140033ba7  test    bpl, bpl
0x140033baa  jz      short loc_140033BC8
0x140033bac  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140033bb3  jnz     loc_14003418C
0x140033bb9  mov     rcx, r14
0x140033bbc  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140033bc3  nop     dword ptr [rax+rax+00h]
0x140033bc8  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140033bcf  jnz     loc_1400341FE
0x140033bd5  mov     [rbx+18h], r15
0x140033bd9  cmp     [rbx+2Ch], r15b
0x140033bdd  jz      loc_140033F4B
0x140033be3  cmp     cs:UxDebugDisableLookaside, r15b
0x140033bea  mov     dword ptr [rbx+10h], 52494C75h
0x140033bf1  jnz     loc_140034219
0x140033bf7  cmp     cs:UxCompactMode, r15b
0x140033bfe  jnz     loc_140033EEC
0x140033c04  mov     edi, [rbx]
0x140033c06  mov     rcx, cs:qword_1401A0250
0x140033c0d  inc     edi
0x140033c0f  shl     rdi, 7
0x140033c13  add     rdi, rcx
0x140033c16  movzx   eax, byte ptr [rdi+0B0h]
0x140033c1d  test    al, al
0x140033c1f  jz      loc_140034010
0x140033c25  mov     rdx, rbx; Entry
0x140033c28  lea     rcx, [rdi+40h]; Lookaside
0x140033c2c  call    cs:__imp_ExFreeToLookasideListEx
0x140033c33  nop     dword ptr [rax+rax+00h]
0x140033c38  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x140033c3f  jz      short loc_140033C57
0x140033c41  mov     edx, 64h ; 'd'
0x140033c46  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x140033c4d  mov     ecx, 409h
0x140033c52  call    WPP_SF_
0x140033c57  mov     rsi, [rsp+0C8h+arg_10]
0x140033c5f  mov     rbp, [rsp+0C8h+arg_8]
0x140033c67  mov     rdi, [rsp+0C8h+arg_18]
0x140033c6f  mov     rcx, [rsp+0C8h+var_28]
0x140033c77  xor     rcx, rsp; StackCookie
0x140033c7a  call    __security_check_cookie
0x140033c7f  add     rsp, 0B0h
0x140033c86  pop     r15
0x140033c88  pop     r14
0x140033c8a  pop     rbx
0x140033c8b  retn
0x140033c8d  xor     edx, edx; Tag
0x140033c8f  mov     rcx, rdi; P
0x140033c92  call    cs:__imp_ExFreePoolWithTag
0x140033c99  nop     dword ptr [rax+rax+00h]
0x140033c9e  jmp     loc_1400339C7
0x140033ca3  xor     edx, edx; Tag
0x140033ca5  mov     rcx, rdi; P
0x140033ca8  call    cs:__imp_ExFreePoolWithTag
0x140033caf  nop     dword ptr [rax+rax+00h]
0x140033cb4  jmp     loc_140033A36
0x140033cb9  xor     edx, edx; Tag
0x140033cbb  mov     rcx, rdi; P
0x140033cbe  call    cs:__imp_ExFreePoolWithTag
0x140033cc5  nop     dword ptr [rax+rax+00h]
0x140033cca  jmp     loc_140033AA5
0x140033ccf  cmp     eax, 2
0x140033cd2  jnz     loc_140033E93
0x140033cd8  cmp     [rdi+28h], r15
0x140033cdc  jz      loc_1400338F7
0x140033ce2  cmp     byte ptr cs:xmmword_1401A2CA0+8, r15b
0x140033ce9  jl      loc_1400340AE
0x140033cef  mov     rcx, [rdi+28h]; Object
0x140033cf3  test    rcx, rcx
0x140033cf6  jz      short loc_140033D08
0x140033cf8  call    cs:__imp_ObfDereferenceObject
0x140033cff  nop     dword ptr [rax+rax+00h]
0x140033d04  mov     [rdi+28h], r15
0x140033d08  mov     dword ptr [rdi+18h], 656C6966h
0x140033d0f  jmp     loc_1400338F7
0x140033d14  cmp     cs:dword_1401A3F08, 1
0x140033d1b  mov     ebp, r15d
0x140033d1e  jbe     short loc_140033D45
0x140033d20  xor     ecx, ecx; ProcNumber
0x140033d22  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140033d29  nop     dword ptr [rax+rax+00h]
0x140033d2e  xor     edx, edx
0x140033d30  div     cs:UxNumberOfProcessors
0x140033d36  cmp     cs:byte_1401A3F20, r15b
0x140033d3d  mov     ebp, edx
0x140033d3f  jnz     loc_1400341AA
0x140033d45  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140033d49  jnz     short loc_140033D5A
0x140033d4b  call    cs:__imp_PsGetCurrentServerSilo
0x140033d52  nop     dword ptr [rax+rax+00h]
0x140033d57  mov     rsi, rax
0x140033d5a  mov     [rdi+20h], rsi
0x140033d5e  mov     qword ptr [rsp+0C8h+var_98], r15
0x140033d63  test    rsi, rsi
0x140033d66  jnz     loc_1400341BD
0x140033d6c  mov     edx, cs:UxPodMonitorSlot
0x140033d72  lea     r8, [rsp+0C8h+var_98]
0x140033d77  mov     rcx, rsi
0x140033d7a  call    cs:__imp_PsGetPermanentSiloContext
0x140033d81  nop     dword ptr [rax+rax+00h]
0x140033d86  mov     rdx, qword ptr [rsp+0C8h+var_98]
0x140033d8b  mov     esi, 1
0x140033d90  add     rdx, 18h; BugCheckParameter2
0x140033d94  mov     eax, esi
0x140033d96  lock xadd [rdx], eax
0x140033d9a  inc     eax
0x140033d9c  cmp     cs:UxDebugCheckRefcount, r15b
0x140033da3  jnz     loc_140033E76
0x140033da9  mov     [rdi+18h], sil
0x140033dad  lea     r8, UlpFreeHttpRequest
0x140033db4  mov     rax, cs:qword_1401A3F10
0x140033dbb  mov     rdx, rdi; ListEntry
0x140033dbe  mov     ecx, ebp
0x140033dc0  mov     r14, [rax+rcx*8]
0x140033dc4  mov     [rdi+10h], r8
0x140033dc8  lea     rcx, [r14+10h]; ListHead
  ... truncated ...
```
