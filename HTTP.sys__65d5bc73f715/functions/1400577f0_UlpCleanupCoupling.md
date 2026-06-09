# UlpCleanupCoupling

- ea: `0x1400577f0`
- end: `0x140057f39`
- name: `UlpCleanupCoupling`
- size: `1865`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056f70`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d08`
- `0x1400577f0`
- `0x14005dfd0`
- `0x14005e030`
- `0x14009620c`
- `0x1400a031c`
- `0x14013dd68`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401d9c5c`
- `0x1401d9f54`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140057bfa`
- `ntoskrnl!KeGetCurrentIrql` at `0x140057bfa`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140057d31`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140057d31`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140057a59`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140057a59`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140057c8d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140057c8d`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140057ce5`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140057ce5`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140057ef3`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140057ef3`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140057c2a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140057c2a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140057c66`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140057c66`
- `ntoskrnl!KeSetEvent` at `0x140057d4f`
- `ntoskrnl!KeSetEvent` at `0x140057d4f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140057cb6`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140057cb6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140057bda`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140057bda`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057874`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057986`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400579ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057ab1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057874`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057986`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400579ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140057ab1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057868`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005797a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005799f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057aa5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057868`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005797a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005799f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057aa5`
- `ntoskrnl!IoGetCurrentProcess` at `0x140057b08`
- `ntoskrnl!IoGetCurrentProcess` at `0x140057b08`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057849`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400578f3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057910`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057849`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400578f3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057910`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140057837`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400578da`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400578ff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140057837`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400578da`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400578ff`

## pseudocode

```c
void __fastcall UlpCleanupCoupling(char *Entry, __int64 a2, __int64 a3)
{
  char *v4; // rcx
  int v5; // eax
  __int64 v6; // rsi
  __int64 v7; // rdx
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // r8
  _QWORD *v12; // rdx
  volatile signed __int32 *v13; // rdx
  volatile signed __int32 *v14; // rdx
  int v15; // eax
  __int64 v16; // rsi
  int v17; // edi
  bool v18; // zf
  unsigned __int64 v19; // rdi
  int v20; // eax
  ULONG_PTR v21; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v23; // r9
  void *CurrentServerSilo; // rsi
  __int64 v25; // rcx
  __int64 v26; // rdi
  USHORT CurrentNodeNumber; // ax
  char v28; // bp
  __int64 v29; // rax
  __int64 v30; // r14
  ULONG v31; // ebp
  ULONG_PTR v32; // rdx
  int v33; // ecx
  __int64 v34; // rsi
  __int128 v35; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v36[24]; // [rsp+40h] [rbp-98h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qqP(1032, 29, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, Entry, a2, a3);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(Entry + 72, 0);
  v4 = Entry + 72;
  if ( Entry[80] )
  {
    ExReleasePushLockExclusiveEx(v4, 0);
    KeLeaveCriticalRegion();
    goto LABEL_28;
  }
  Entry[80] = 1;
  ExReleasePushLockExclusiveEx(v4, 0);
  KeLeaveCriticalRegion();
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_q(1046, 30, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, Entry);
  v5 = _InterlockedDecrement((volatile signed __int32 *)Entry + 5);
  if ( UxDebugCheckRefcount && v5 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(Entry + 20), 1u, v5);
  if ( v5 )
    goto LABEL_28;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 23, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, Entry, 0);
  v6 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)Entry + 8) + 264LL)
                 + 8LL * *(unsigned __int16 *)(*((_QWORD *)Entry + 7) + 56LL));
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*((_QWORD *)Entry + 7) + 944LL, 0);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6, 0);
  v7 = *((_QWORD *)Entry + 3);
  v8 = Entry + 24;
  if ( *(char **)(v7 + 8) != Entry + 24 )
    goto LABEL_45;
  v9 = (_QWORD *)*((_QWORD *)Entry + 4);
  if ( (_QWORD *)*v9 != v8
    || (*v9 = v7,
        *(_QWORD *)(v7 + 8) = v9,
        *v8 = 0,
        *((_QWORD *)Entry + 4) = 0,
        v10 = Entry + 40,
        v11 = *((_QWORD *)Entry + 5),
        *(char **)(v11 + 8) != Entry + 40)
    || (v12 = (_QWORD *)*((_QWORD *)Entry + 6), (_QWORD *)*v12 != v10) )
  {
LABEL_45:
    __fastfail(3u);
  }
  *v12 = v11;
  *(_QWORD *)(v11 + 8) = v12;
  *v10 = 0;
  *((_QWORD *)Entry + 6) = 0;
  ExReleasePushLockExclusiveEx(v6, 0);
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*((_QWORD *)Entry + 7) + 944LL, 0);
  KeLeaveCriticalRegion();
  v13 = (volatile signed __int32 *)*((_QWORD *)Entry + 11);
  if ( v13 )
  {
    v20 = _InterlockedDecrement(v13);
    if ( UxDebugCheckRefcount && v20 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v13, 0xEu, v20);
    if ( !v20 )
      UlConsumerCleanupCompletion(*((_QWORD *)Entry + 11));
    *((_QWORD *)Entry + 11) = 0;
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)Entry + 8);
  v15 = _InterlockedDecrement(v14);
  if ( UxDebugCheckRefcount && v15 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)v14, 0xEu, v15);
  if ( !v15 )
    UlFreeRequestQueue(*((PVOID *)Entry + 8));
  v16 = *((_QWORD *)Entry + 7);
  *((_QWORD *)Entry + 8) = 0;
  v17 = _InterlockedDecrement((volatile signed __int32 *)(v16 + 40));
  if ( UxDebugCheckRefcount && v17 <= -1 )
    UlBugCheckEx(3u, v16 + 40, 0xEu, v17);
  if ( !v17 )
  {
    v21 = v16 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(v16 + 1088);
    v25 = *(_QWORD *)v21;
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v25 || *(_QWORD *)(v21 + 16) || *(_QWORD *)(v21 + 32) )
        UlBugCheckEx(1u, v21, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v23) = 1;
      UlThreadPoolEnqueueWorkItem(0, v21, UlFreeHttpConnection, v23, CurrentServerSilo, -1);
      goto LABEL_20;
    }
    if ( v25 || *(_QWORD *)(v21 + 16) || *(_QWORD *)(v21 + 32) )
      UlBugCheckEx(1u, v21, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
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
      *(_QWORD *)(v21 + 32) = CurrentServerSilo;
      *(_QWORD *)&v35 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v35);
      v32 = v35 + 24;
      v33 = _InterlockedIncrement((volatile signed __int32 *)(v35 + 24));
      if ( UxDebugCheckRefcount && v33 <= -1 )
        UlBugCheckEx(3u, v32, 0xDu, v33);
      *(_BYTE *)(v21 + 24) = 1;
      v34 = *(_QWORD *)(qword_1401A3F10 + 8LL * v31);
      *(_QWORD *)(v21 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v34 + 16), (PSLIST_ENTRY)v21) )
      {
        KeSetEvent((PRKEVENT)(v34 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v34);
      }
      goto LABEL_20;
    }
    v28 = 0;
    v35 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v30 = *((_QWORD *)&v35 + 1);
    }
    else
    {
      v29 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v30 = v29;
      v28 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v29, CurrentServerSilo);
        UlFreeHttpConnection(v21);
LABEL_53:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v30);
        PsDetachSiloFromCurrentThread(v30);
        goto LABEL_20;
      }
    }
    UlFreeHttpConnection(v21);
    if ( !v28 )
      goto LABEL_20;
    goto LABEL_53;
  }
LABEL_20:
  v18 = UxDebugDisableLookaside == 0;
  *((_QWORD *)Entry + 7) = 0;
  *((_DWORD *)Entry + 4) = 1969441909;
  if ( v18 )
  {
    if ( UxCompactMode )
    {
      v26 = qword_1401A0910;
      CurrentNodeNumber = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v26, Entry, CurrentNodeNumber);
    }
    else
    {
      v19 = qword_1401A0910 + ((unsigned __int64)(unsigned int)(*(_DWORD *)Entry + 1) << 7);
      if ( !*(_BYTE *)(v19 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A0910, v19 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v19 + 64), Entry);
    }
  }
  else
  {
    memset(v36, 0, sizeof(v36));
    v36[10] = dword_1401A0928;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A0938)(Entry, v36);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 24, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
LABEL_28:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 31, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  }
}

```

## disassembly

```asm
0x1400577f0  push    rbx
0x1400577f2  push    rdi
0x1400577f3  sub     rsp, 0C8h
0x1400577fa  mov     rax, cs:__security_cookie
0x140057801  xor     rax, rsp
0x140057804  mov     [rsp+0D8h+var_38], rax
0x14005780c  mov     r9, rdx
0x14005780f  mov     rbx, rcx
0x140057812  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140057819  jnz     loc_140057DF9
0x14005781f  mov     [rsp+0D8h+arg_18], rbp
0x140057827  mov     [rsp+0D8h+var_18], rsi
0x14005782f  mov     [rsp+0D8h+var_28], r15
0x140057837  call    cs:__imp_KeEnterCriticalRegion
0x14005783e  nop     dword ptr [rax+rax+00h]
0x140057843  xor     edx, edx
0x140057845  lea     rcx, [rbx+48h]
0x140057849  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140057850  nop     dword ptr [rax+rax+00h]
0x140057855  xor     edx, edx
0x140057857  lea     rcx, [rbx+48h]
0x14005785b  cmp     [rbx+50h], dl
0x14005785e  jnz     loc_140057AA5
0x140057864  mov     byte ptr [rbx+50h], 1
0x140057868  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005786f  nop     dword ptr [rax+rax+00h]
0x140057874  call    cs:__imp_KeLeaveCriticalRegion
0x14005787b  nop     dword ptr [rax+rax+00h]
0x140057880  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x140057887  jnz     loc_140057E80
0x14005788d  mov     edi, 0FFFFFFFFh
0x140057892  lea     rdx, [rbx+14h]; BugCheckParameter2
0x140057896  mov     eax, edi
0x140057898  lock xadd [rdx], eax
0x14005789c  dec     eax
0x14005789e  cmp     cs:UxDebugCheckRefcount, 0
0x1400578a5  jnz     loc_140057B5B
0x1400578ab  test    eax, eax
0x1400578ad  jnz     loc_140057ABD
0x1400578b3  xor     r15d, r15d
0x1400578b6  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400578bd  jnz     loc_140057DBB
0x1400578c3  mov     rax, [rbx+38h]
0x1400578c7  movzx   edx, word ptr [rax+38h]
0x1400578cb  mov     rax, [rbx+40h]
0x1400578cf  mov     rcx, [rax+108h]
0x1400578d6  mov     rsi, [rcx+rdx*8]
0x1400578da  call    cs:__imp_KeEnterCriticalRegion
0x1400578e1  nop     dword ptr [rax+rax+00h]
0x1400578e6  mov     rcx, [rbx+38h]
0x1400578ea  xor     edx, edx
0x1400578ec  add     rcx, 3B0h
0x1400578f3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400578fa  nop     dword ptr [rax+rax+00h]
0x1400578ff  call    cs:__imp_KeEnterCriticalRegion
0x140057906  nop     dword ptr [rax+rax+00h]
0x14005790b  xor     edx, edx
0x14005790d  mov     rcx, rsi
0x140057910  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140057917  nop     dword ptr [rax+rax+00h]
0x14005791c  mov     rdx, [rbx+18h]
0x140057920  lea     rax, [rbx+18h]
0x140057924  cmp     [rdx+8], rax
0x140057928  jnz     loc_140057BB0
0x14005792e  mov     rcx, [rax+8]
0x140057932  cmp     [rcx], rax
0x140057935  jnz     loc_140057BB0
0x14005793b  mov     [rcx], rdx
0x14005793e  mov     [rdx+8], rcx
0x140057942  mov     [rax], r15
0x140057945  mov     [rax+8], r15
0x140057949  lea     rax, [rbx+28h]
0x14005794d  mov     r8, [rax]
0x140057950  cmp     [r8+8], rax
0x140057954  jnz     loc_140057BB0
0x14005795a  mov     rdx, [rax+8]
0x14005795e  cmp     [rdx], rax
0x140057961  jnz     loc_140057BB0
0x140057967  mov     [rdx], r8
0x14005796a  mov     rcx, rsi
0x14005796d  mov     [r8+8], rdx
0x140057971  xor     edx, edx
0x140057973  mov     [rax], r15
0x140057976  mov     [rax+8], r15
0x14005797a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140057981  nop     dword ptr [rax+rax+00h]
0x140057986  call    cs:__imp_KeLeaveCriticalRegion
0x14005798d  nop     dword ptr [rax+rax+00h]
0x140057992  mov     rcx, [rbx+38h]
0x140057996  xor     edx, edx
0x140057998  add     rcx, 3B0h
0x14005799f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400579a6  nop     dword ptr [rax+rax+00h]
0x1400579ab  call    cs:__imp_KeLeaveCriticalRegion
0x1400579b2  nop     dword ptr [rax+rax+00h]
0x1400579b7  mov     rdx, [rbx+58h]; BugCheckParameter2
0x1400579bb  test    rdx, rdx
0x1400579be  jnz     loc_140057ADE
0x1400579c4  mov     rdx, [rbx+40h]; BugCheckParameter2
0x1400579c8  mov     eax, edi
0x1400579ca  lock xadd [rdx], eax
0x1400579ce  dec     eax
0x1400579d0  cmp     cs:UxDebugCheckRefcount, r15b
0x1400579d7  jnz     loc_140057B77
0x1400579dd  test    eax, eax
0x1400579df  jz      loc_140057EAC
0x1400579e5  mov     rsi, [rbx+38h]
0x1400579e9  mov     [rbx+40h], r15
0x1400579ed  lea     rdx, [rsi+28h]; BugCheckParameter2
0x1400579f1  lock xadd [rdx], edi
0x1400579f5  dec     edi
0x1400579f7  cmp     cs:UxDebugCheckRefcount, r15b
0x1400579fe  jnz     loc_140057B93
0x140057a04  test    edi, edi
0x140057a06  jz      loc_140057B04
0x140057a0c  cmp     cs:UxDebugDisableLookaside, r15b
0x140057a13  mov     [rbx+38h], r15
0x140057a17  mov     dword ptr [rbx+10h], 75634C75h
0x140057a1e  jnz     loc_140057F04
0x140057a24  cmp     cs:UxCompactMode, r15b
0x140057a2b  jnz     loc_140057BD3
0x140057a31  mov     edi, [rbx]
0x140057a33  mov     rcx, cs:qword_1401A0910
0x140057a3a  inc     edi
0x140057a3c  shl     rdi, 7
0x140057a40  add     rdi, rcx
0x140057a43  movzx   eax, byte ptr [rdi+0B0h]
0x140057a4a  test    al, al
0x140057a4c  jz      loc_140057E72
0x140057a52  mov     rdx, rbx; Entry
0x140057a55  lea     rcx, [rdi+40h]; Lookaside
0x140057a59  call    cs:__imp_ExFreeToLookasideListEx
0x140057a60  nop     dword ptr [rax+rax+00h]
0x140057a65  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140057a6c  jnz     loc_140057DDE
0x140057a72  mov     r15, [rsp+0D8h+var_28]
0x140057a7a  mov     rsi, [rsp+0D8h+var_18]
0x140057a82  mov     rbp, [rsp+0D8h+arg_18]
0x140057a8a  mov     rcx, [rsp+0D8h+var_38]
0x140057a92  xor     rcx, rsp; StackCookie
0x140057a95  call    __security_check_cookie
0x140057a9a  add     rsp, 0C8h
0x140057aa1  pop     rdi
0x140057aa2  pop     rbx
0x140057aa3  retn
0x140057aa5  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140057aac  nop     dword ptr [rax+rax+00h]
0x140057ab1  call    cs:__imp_KeLeaveCriticalRegion
0x140057ab8  nop     dword ptr [rax+rax+00h]
0x140057abd  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140057ac4  jz      short loc_140057A72
0x140057ac6  mov     edx, 1Fh
0x140057acb  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140057ad2  mov     ecx, 408h
0x140057ad7  call    WPP_SF_
0x140057adc  jmp     short loc_140057A72
0x140057ade  mov     eax, edi
0x140057ae0  lock xadd [rdx], eax
0x140057ae4  dec     eax
0x140057ae6  cmp     cs:UxDebugCheckRefcount, r15b
0x140057aed  jnz     loc_140057BB7
0x140057af3  test    eax, eax
0x140057af5  jz      loc_140057E9E
0x140057afb  mov     [rbx+58h], r15
0x140057aff  jmp     loc_1400579C4
0x140057b04  lea     rdi, [rsi+40h]
0x140057b08  call    cs:__imp_IoGetCurrentProcess
0x140057b0f  nop     dword ptr [rax+rax+00h]
0x140057b14  cmp     cs:UxSystemProcess, rax
0x140057b1b  mov     rsi, [rsi+440h]
0x140057b22  mov     rcx, [rdi]
0x140057b25  jnz     loc_140057D8B
0x140057b2b  test    rcx, rcx
0x140057b2e  jnz     short loc_140057B40
0x140057b30  cmp     [rdi+10h], r15
0x140057b34  jnz     short loc_140057B40
0x140057b36  cmp     [rdi+20h], r15
0x140057b3a  jz      loc_140057BFA
0x140057b40  mov     r9d, 0E1h; BugCheckParameter4
0x140057b46  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140057b4d  mov     rdx, rdi; BugCheckParameter2
0x140057b50  mov     ecx, 1; BugCheckParameter1
0x140057b55  call    UlBugCheckEx
0x140057b5b  cmp     eax, edi
0x140057b5d  jg      loc_1400578AB
0x140057b63  movsxd  r9, eax; BugCheckParameter4
0x140057b66  mov     ecx, 3; BugCheckParameter1
0x140057b6b  mov     r8d, 1; BugCheckParameter3
0x140057b71  call    UlBugCheckEx
0x140057b77  cmp     eax, edi
0x140057b79  jg      loc_1400579DD
0x140057b7f  movsxd  r9, eax; BugCheckParameter4
0x140057b82  mov     ecx, 3; BugCheckParameter1
0x140057b87  mov     r8d, 0Eh; BugCheckParameter3
0x140057b8d  call    UlBugCheckEx
0x140057b93  cmp     edi, 0FFFFFFFFh
0x140057b96  jg      loc_140057A04
0x140057b9c  movsxd  r9, edi; BugCheckParameter4
0x140057b9f  mov     ecx, 3; BugCheckParameter1
0x140057ba4  mov     r8d, 0Eh; BugCheckParameter3
0x140057baa  call    UlBugCheckEx
0x140057bb0  mov     ecx, 3
0x140057bb5  int     29h; Win8: RtlFailFast(ecx)
0x140057bb7  cmp     eax, edi
0x140057bb9  jg      loc_140057AF3
0x140057bbf  movsxd  r9, eax; BugCheckParameter4
0x140057bc2  mov     ecx, 3; BugCheckParameter1
0x140057bc7  mov     r8d, 0Eh; BugCheckParameter3
0x140057bcd  call    UlBugCheckEx
0x140057bd3  mov     rdi, cs:qword_1401A0910
0x140057bda  call    cs:__imp_KeGetCurrentNodeNumber
0x140057be1  nop     dword ptr [rax+rax+00h]
0x140057be6  movzx   r8d, ax
0x140057bea  mov     rdx, rbx
0x140057bed  mov     rcx, rdi
0x140057bf0  call    PplFreeToLookasideListProcessor
0x140057bf5  jmp     loc_140057A65
0x140057bfa  call    cs:__imp_KeGetCurrentIrql
0x140057c01  nop     dword ptr [rax+rax+00h]
0x140057c06  test    al, al
0x140057c08  jnz     short loc_140057C7F
0x140057c0a  xor     bpl, bpl
0x140057c0d  mov     [rsp+0D8h+var_20], r14
0x140057c15  xorps   xmm0, xmm0
0x140057c18  movups  [rsp+0D8h+var_A8], xmm0
0x140057c1d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140057c21  jz      loc_140057D81
0x140057c27  mov     rcx, rsi
0x140057c2a  call    cs:__imp_PsAttachSiloToCurrentThread
0x140057c31  nop     dword ptr [rax+rax+00h]
0x140057c36  mov     r14, rax
0x140057c39  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140057c40  mov     bpl, 1
0x140057c43  jnz     loc_140057E47
0x140057c49  mov     rcx, rdi
0x140057c4c  call    UlFreeHttpConnection
0x140057c51  test    bpl, bpl
0x140057c54  jz      short loc_140057C72
0x140057c56  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140057c5d  jnz     loc_140057EBA
0x140057c63  mov     rcx, r14
0x140057c66  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140057c6d  nop     dword ptr [rax+rax+00h]
0x140057c72  mov     r14, [rsp+0D8h+var_20]
0x140057c7a  jmp     loc_140057A0C
0x140057c7f  cmp     cs:dword_1401A3F08, 1
0x140057c86  mov     ebp, r15d
0x140057c89  jbe     short loc_140057CB0
0x140057c8b  xor     ecx, ecx; ProcNumber
0x140057c8d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140057c94  nop     dword ptr [rax+rax+00h]
0x140057c99  xor     edx, edx
0x140057c9b  div     cs:UxNumberOfProcessors
0x140057ca1  cmp     cs:byte_1401A3F20, r15b
0x140057ca8  mov     ebp, edx
0x140057caa  jnz     loc_140057ED8
0x140057cb0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140057cb4  jnz     short loc_140057CC5
0x140057cb6  call    cs:__imp_PsGetCurrentServerSilo
0x140057cbd  nop     dword ptr [rax+rax+00h]
0x140057cc2  mov     rsi, rax
0x140057cc5  mov     [rdi+20h], rsi
0x140057cc9  mov     qword ptr [rsp+0D8h+var_A8], r15
0x140057cce  test    rsi, rsi
0x140057cd1  jnz     loc_140057EEB
0x140057cd7  mov     edx, cs:UxPodMonitorSlot
0x140057cdd  lea     r8, [rsp+0D8h+var_A8]
0x140057ce2  mov     rcx, rsi
0x140057ce5  call    cs:__imp_PsGetPermanentSiloContext
0x140057cec  nop     dword ptr [rax+rax+00h]
0x140057cf1  mov     rdx, qword ptr [rsp+0D8h+var_A8]
0x140057cf6  mov     ecx, 1
0x140057cfb  add     rdx, 18h; BugCheckParameter2
0x140057cff  lock xadd [rdx], ecx
0x140057d03  inc     ecx
0x140057d05  cmp     cs:UxDebugCheckRefcount, r15b
0x140057d0c  jnz     short loc_140057D68
0x140057d0e  mov     byte ptr [rdi+18h], 1
0x140057d12  mov     rdx, rdi; ListEntry
0x140057d15  mov     rax, cs:qword_1401A3F10
0x140057d1c  mov     ecx, ebp
0x140057d1e  mov     rsi, [rax+rcx*8]
0x140057d22  lea     rax, UlFreeHttpConnection
0x140057d29  mov     [rdi+10h], rax
0x140057d2d  lea     rcx, [rsi+10h]; ListHead
0x140057d31  call    cs:__imp_ExpInterlockedPushEntrySList
0x140057d38  nop     dword ptr [rax+rax+00h]
0x140057d3d  test    rax, rax
0x140057d40  jnz     loc_140057A0C
0x140057d46  lea     rcx, [rsi+20h]; Event
0x140057d4a  xor     r8d, r8d; Wait
0x140057d4d  xor     edx, edx; Increment
0x140057d4f  call    cs:__imp_KeSetEvent
0x140057d56  nop     dword ptr [rax+rax+00h]
0x140057d5b  mov     rcx, rsi; Context
0x140057d5e  call    UlpActivateThreadPoolQueue
0x140057d63  jmp     loc_140057A0C
0x140057d68  cmp     ecx, 0FFFFFFFFh
0x140057d6b  jg      short loc_140057D0E
0x140057d6d  movsxd  r9, ecx; BugCheckParameter4
  ... truncated ...
```
