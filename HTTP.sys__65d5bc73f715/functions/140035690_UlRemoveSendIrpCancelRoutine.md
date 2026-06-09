# UlRemoveSendIrpCancelRoutine

- ea: `0x140035690`
- end: `0x140035a3c`
- name: `UlRemoveSendIrpCancelRoutine`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400354a0`
- `0x1400371fc`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140035690`
- `0x14005e030`
- `0x14013dd68`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401d9c5c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140035773`
- `ntoskrnl!KeGetCurrentIrql` at `0x140035773`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003589d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003589d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400357f9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400357f9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140035851`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140035851`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140035a2b`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140035a2b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003579b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14003579b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400357db`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400357db`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400358f2`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400358f2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035903`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140035903`
- `ntoskrnl!KeSetEvent` at `0x1400358bb`
- `ntoskrnl!KeSetEvent` at `0x1400358bb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140035822`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140035822`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003570b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003570b`

## pseudocode

```c
__int64 __fastcall UlRemoveSendIrpCancelRoutine(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned __int8 v5; // bl
  __int64 v7; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v9; // r9
  void *CurrentServerSilo; // rsi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  char v15; // di
  __int64 v16; // rax
  __int64 v17; // rbp
  ULONG v18; // edi
  ULONG_PTR v19; // rdx
  int v20; // ecx
  __int64 v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  KIRQL Irql; // [rsp+68h] [rbp+10h] BYREF
  __int64 v27; // [rsp+70h] [rbp+18h] BYREF

  Irql = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
  {
    if ( a1 )
      v22 = *(_QWORD *)(a1 + 48);
    else
      v22 = 0;
    WPP_SF_qqP(1033, 77, WPP_173ede4a325638307373c19033e5a27a_Traceguids, a1, v22, a2);
  }
  if ( _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
  {
    *(_QWORD *)(a2 + 120) = 0;
    v4 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 40));
    if ( UxDebugCheckRefcount && v4 <= -1 )
      UlBugCheckEx(3u, a1 + 40, 0x25u, v4);
    if ( v4 )
      goto LABEL_5;
    v7 = a1 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(a1 + 1088);
    v11 = *(_QWORD *)(a1 + 64);
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v11 || *(_QWORD *)(a1 + 80) || *(_QWORD *)(a1 + 96) )
        UlBugCheckEx(1u, a1 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v9) = 1;
      UlThreadPoolEnqueueWorkItem(0, a1 + 64, UlFreeHttpConnection, v9, CurrentServerSilo, -1);
      goto LABEL_5;
    }
    if ( v11 || *(_QWORD *)(a1 + 80) || *(_QWORD *)(a1 + 96) )
      UlBugCheckEx(1u, a1 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v18 = 0;
      if ( (unsigned int)dword_1401A3F08 > 1 )
      {
        v18 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F20 )
          v18 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v7 + 32) = CurrentServerSilo;
      v27 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v27);
      v19 = v27 + 24;
      v20 = _InterlockedIncrement((volatile signed __int32 *)(v27 + 24));
      if ( UxDebugCheckRefcount && v20 <= -1 )
        UlBugCheckEx(3u, v19, 0xDu, v20);
      *(_BYTE *)(v7 + 24) = 1;
      v21 = *(_QWORD *)(qword_1401A3F10 + 8LL * v18);
      *(_QWORD *)(v7 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v21 + 16), (PSLIST_ENTRY)v7) )
      {
        KeSetEvent((PRKEVENT)(v21 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v21);
      }
      goto LABEL_5;
    }
    v15 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v17 = 0;
    }
    else
    {
      v16 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v17 = v16;
      v15 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v16, CurrentServerSilo);
        UlFreeHttpConnection(v7, v23, v24, v25);
        goto LABEL_20;
      }
    }
    UlFreeHttpConnection(v7, v12, v13, v14);
    if ( !v15 )
    {
LABEL_5:
      v5 = 1;
      goto LABEL_6;
    }
LABEL_20:
    if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v17);
    PsDetachSiloFromCurrentThread(v17);
    goto LABEL_5;
  }
  IoAcquireCancelSpinLock(&Irql);
  IoReleaseCancelSpinLock(Irql);
  v5 = 0;
LABEL_6:
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 78, WPP_173ede4a325638307373c19033e5a27a_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x140035690  push    rbx
0x140035692  push    rbp
0x140035693  push    rdi
0x140035694  sub     rsp, 40h
0x140035698  mov     rbx, rdx
0x14003569b  mov     [rsp+58h+Irql], 0
0x1400356a0  mov     rdi, rcx
0x1400356a3  xor     ebp, ebp
0x1400356a5  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400356ac  jnz     loc_14003594C
0x1400356b2  mov     rax, rbp
0x1400356b5  mov     [rsp+58h+arg_0], rsi
0x1400356ba  xchg    rax, [rbx+68h]
0x1400356be  test    rax, rax
0x1400356c1  jz      loc_1400358ED
0x1400356c7  mov     [rbx+78h], rbp
0x1400356cb  lea     rdx, [rdi+28h]; BugCheckParameter2
0x1400356cf  mov     eax, 0FFFFFFFFh
0x1400356d4  lock xadd [rdx], eax
0x1400356d8  dec     eax
0x1400356da  cmp     cs:UxDebugCheckRefcount, bpl
0x1400356e1  jnz     short loc_14003575A
0x1400356e3  test    eax, eax
0x1400356e5  jz      short loc_140035707
0x1400356e7  mov     bl, 1
0x1400356e9  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400356f0  jnz     loc_14003597D
0x1400356f6  mov     rsi, [rsp+58h+arg_0]
0x1400356fb  movzx   eax, bl
0x1400356fe  add     rsp, 40h
0x140035702  pop     rdi
0x140035703  pop     rbp
0x140035704  pop     rbx
0x140035705  retn
0x140035707  lea     rbx, [rdi+40h]
0x14003570b  call    cs:__imp_IoGetCurrentProcess
0x140035712  nop     dword ptr [rax+rax+00h]
0x140035717  cmp     cs:UxSystemProcess, rax
0x14003571e  mov     rsi, [rdi+440h]
0x140035725  mov     rcx, [rbx]
0x140035728  jnz     loc_140035920
0x14003572e  test    rcx, rcx
0x140035731  jnz     short loc_14003573F
0x140035733  cmp     [rbx+10h], rbp
0x140035737  jnz     short loc_14003573F
0x140035739  cmp     [rbx+20h], rbp
0x14003573d  jz      short loc_140035773
0x14003573f  mov     r9d, 0E1h; BugCheckParameter4
0x140035745  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003574c  mov     rdx, rbx; BugCheckParameter2
0x14003574f  mov     ecx, 1; BugCheckParameter1
0x140035754  call    UlBugCheckEx
0x14003575a  cmp     eax, 0FFFFFFFFh
0x14003575d  jg      short loc_1400356E3
0x14003575f  movsxd  r9, eax; BugCheckParameter4
0x140035762  mov     ecx, 3; BugCheckParameter1
0x140035767  mov     r8d, 25h ; '%'; BugCheckParameter3
0x14003576d  call    UlBugCheckEx
0x140035773  call    cs:__imp_KeGetCurrentIrql
0x14003577a  nop     dword ptr [rax+rax+00h]
0x14003577f  test    al, al
0x140035781  jnz     short loc_1400357EC
0x140035783  xor     dil, dil
0x140035786  xorps   xmm0, xmm0
0x140035789  movups  [rsp+58h+var_28], xmm0
0x14003578e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140035792  jz      loc_140035916
0x140035798  mov     rcx, rsi
0x14003579b  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400357a2  nop     dword ptr [rax+rax+00h]
0x1400357a7  mov     rbp, rax
0x1400357aa  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400357b1  mov     dil, 1
0x1400357b4  jnz     loc_1400359C7
0x1400357ba  mov     rcx, rbx
0x1400357bd  call    UlFreeHttpConnection
0x1400357c2  test    dil, dil
0x1400357c5  jz      loc_1400356E7
0x1400357cb  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400357d2  jnz     loc_1400359F2
0x1400357d8  mov     rcx, rbp
0x1400357db  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400357e2  nop     dword ptr [rax+rax+00h]
0x1400357e7  jmp     loc_1400356E7
0x1400357ec  cmp     cs:dword_1401A3F08, 1
0x1400357f3  mov     edi, ebp
0x1400357f5  jbe     short loc_14003581C
0x1400357f7  xor     ecx, ecx; ProcNumber
0x1400357f9  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140035800  nop     dword ptr [rax+rax+00h]
0x140035805  xor     edx, edx
0x140035807  div     cs:UxNumberOfProcessors
0x14003580d  cmp     cs:byte_1401A3F20, bpl
0x140035814  mov     edi, edx
0x140035816  jnz     loc_140035A10
0x14003581c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140035820  jnz     short loc_140035831
0x140035822  call    cs:__imp_PsGetCurrentServerSilo
0x140035829  nop     dword ptr [rax+rax+00h]
0x14003582e  mov     rsi, rax
0x140035831  mov     [rbx+20h], rsi
0x140035835  mov     [rsp+58h+arg_10], rbp
0x14003583a  test    rsi, rsi
0x14003583d  jnz     loc_140035A23
0x140035843  mov     edx, cs:UxPodMonitorSlot
0x140035849  lea     r8, [rsp+58h+arg_10]
0x14003584e  mov     rcx, rsi
0x140035851  call    cs:__imp_PsGetPermanentSiloContext
0x140035858  nop     dword ptr [rax+rax+00h]
0x14003585d  mov     rdx, [rsp+58h+arg_10]
0x140035862  mov     ecx, 1
0x140035867  add     rdx, 18h; BugCheckParameter2
0x14003586b  lock xadd [rdx], ecx
0x14003586f  inc     ecx
0x140035871  cmp     cs:UxDebugCheckRefcount, bpl
0x140035878  jnz     short loc_1400358D4
0x14003587a  mov     byte ptr [rbx+18h], 1
0x14003587e  mov     rdx, rbx; ListEntry
0x140035881  mov     rax, cs:qword_1401A3F10
0x140035888  mov     ecx, edi
0x14003588a  mov     rdi, [rax+rcx*8]
0x14003588e  lea     rax, UlFreeHttpConnection
0x140035895  mov     [rbx+10h], rax
0x140035899  lea     rcx, [rdi+10h]; ListHead
0x14003589d  call    cs:__imp_ExpInterlockedPushEntrySList
0x1400358a4  nop     dword ptr [rax+rax+00h]
0x1400358a9  test    rax, rax
0x1400358ac  jnz     loc_1400356E7
0x1400358b2  lea     rcx, [rdi+20h]; Event
0x1400358b6  xor     r8d, r8d; Wait
0x1400358b9  xor     edx, edx; Increment
0x1400358bb  call    cs:__imp_KeSetEvent
0x1400358c2  nop     dword ptr [rax+rax+00h]
0x1400358c7  mov     rcx, rdi; Context
0x1400358ca  call    UlpActivateThreadPoolQueue
0x1400358cf  jmp     loc_1400356E7
0x1400358d4  cmp     ecx, 0FFFFFFFFh
0x1400358d7  jg      short loc_14003587A
0x1400358d9  movsxd  r9, ecx; BugCheckParameter4
0x1400358dc  mov     r8d, 0Dh; BugCheckParameter3
0x1400358e2  mov     ecx, 3; BugCheckParameter1
0x1400358e7  call    UlBugCheckEx
0x1400358ed  lea     rcx, [rsp+58h+Irql]; Irql
0x1400358f2  call    cs:__imp_IoAcquireCancelSpinLock
0x1400358f9  nop     dword ptr [rax+rax+00h]
0x1400358fe  movzx   ecx, [rsp+58h+Irql]; Irql
0x140035903  call    cs:__imp_IoReleaseCancelSpinLock
0x14003590a  nop     dword ptr [rax+rax+00h]
0x14003590f  xor     bl, bl
0x140035911  jmp     loc_1400356E9
0x140035916  mov     rbp, qword ptr [rsp+58h+var_28+8]
0x14003591b  jmp     loc_1400357BA
0x140035920  test    rcx, rcx
0x140035923  jnz     short loc_140035931
0x140035925  cmp     [rbx+10h], rbp
0x140035929  jnz     short loc_140035931
0x14003592b  cmp     [rbx+20h], rbp
0x14003592f  jz      short loc_1400359A1
0x140035931  mov     r9d, 0DBh; BugCheckParameter4
0x140035937  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14003593e  mov     rdx, rbx; BugCheckParameter2
0x140035941  mov     ecx, 1; BugCheckParameter1
0x140035946  call    UlBugCheckEx
0x14003594c  test    rdi, rdi
0x14003594f  jz      short loc_14003599C
0x140035951  mov     rax, [rcx+30h]
0x140035955  mov     edx, 4Dh ; 'M'
0x14003595a  mov     [rsp+58h+var_30], rbx
0x14003595f  mov     ecx, 409h
0x140035964  mov     [rsp+58h+var_38], rax
0x140035969  mov     r9, rdi
0x14003596c  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x140035973  call    WPP_SF_qqP
0x140035978  jmp     loc_1400356B2
0x14003597d  movzx   r9d, bl
0x140035981  lea     r8, WPP_173ede4a325638307373c19033e5a27a_Traceguids
0x140035988  mov     edx, 4Eh ; 'N'
0x14003598d  mov     ecx, 409h
0x140035992  call    WPP_SF_d
0x140035997  jmp     loc_1400356F6
0x14003599c  mov     rax, rbp
0x14003599f  jmp     short loc_140035955
0x1400359a1  mov     dword ptr [rsp+58h+var_30], 0FFFFFFFFh
0x1400359a9  lea     r8, UlFreeHttpConnection
0x1400359b0  mov     r9b, 1
0x1400359b3  mov     [rsp+58h+var_38], rsi
0x1400359b8  mov     rdx, rbx
0x1400359bb  xor     ecx, ecx
0x1400359bd  call    UlThreadPoolEnqueueWorkItem
0x1400359c2  jmp     loc_1400356E7
0x1400359c7  mov     edx, 19h
0x1400359cc  mov     [rsp+58h+var_38], rsi
0x1400359d1  mov     ecx, 51Ch
0x1400359d6  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x1400359dd  mov     r9, rax
0x1400359e0  call    WPP_SF_qq
0x1400359e5  mov     rcx, rbx
0x1400359e8  call    UlFreeHttpConnection
0x1400359ed  jmp     loc_1400357CB
0x1400359f2  mov     edx, 1Ah
0x1400359f7  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x1400359fe  mov     ecx, 51Ch
0x140035a03  mov     r9, rbp
0x140035a06  call    WPP_SF_q
0x140035a0b  jmp     loc_1400357D8
0x140035a10  lea     rcx, UlThreadPoolArena
0x140035a17  call    UlpAssignThreadPoolWork
0x140035a1c  mov     edi, eax
0x140035a1e  jmp     loc_14003581C
0x140035a23  mov     edx, 49576C55h; Tag
0x140035a28  mov     rcx, rsi; Object
0x140035a2b  call    cs:__imp_ObfReferenceObjectWithTag
0x140035a32  nop     dword ptr [rax+rax+00h]
0x140035a37  jmp     loc_140035843
```
