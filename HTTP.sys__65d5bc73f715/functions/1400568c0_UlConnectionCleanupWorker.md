# UlConnectionCleanupWorker

- ea: `0x1400568c0`
- end: `0x140056f68`
- name: `UlConnectionCleanupWorker`
- size: `1704`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140055300`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140035a50`
- `0x1400568c0`
- `0x140056f70`
- `0x140058850`
- `0x14005e0d0`
- `0x140061e80`
- `0x140062bd0`
- `0x14006eaf0`
- `0x140070bf8`
- `0x1400a024c`
- `0x1400a396c`
- `0x1400b103c`
- `0x1401678f0`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140056ad1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056b86`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056c3f`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056ad1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056b86`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056c3f`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056bae`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056c62`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056bae`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140056c62`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400569ca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400569ca`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400569be`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400569be`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056a96`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b07`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b56`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056a96`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b07`
- `ntoskrnl!IoGetCurrentProcess` at `0x140056b56`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005695c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005695c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140056947`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140056947`

## pseudocode

```c
__int64 __fastcall UlConnectionCleanupWorker(__int64 *BugCheckParameter2)
{
  __int64 *v2; // rbx
  volatile signed __int32 *v3; // rdi
  int v4; // eax
  char v5; // r15
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r13
  __int64 result; // rax
  __int64 *v10; // rbx
  int v11; // esi
  int v12; // eax
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v14; // r9
  __int64 v15; // r13
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  struct _KPROCESS *v20; // rax
  __int64 v21; // r9
  __int64 v22; // r12
  __int64 v23; // rcx
  struct _KPROCESS *v24; // rax
  __int64 v25; // r9
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // r15d
  __int64 v39; // r9
  _QWORD *v40; // r15
  __int128 v41; // [rsp+50h] [rbp+7h] BYREF
  char v42; // [rsp+B0h] [rbp+67h] BYREF
  unsigned __int8 v43; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v44; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v45; // [rsp+C8h] [rbp+7Fh] BYREF

  v42 = 0;
  v44 = 0;
  v45 = 0;
  v43 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 24, WPP_682cf469470432b235cb9a4961616e40_Traceguids, BugCheckParameter2);
  v2 = BugCheckParameter2 - 8;
  if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1288, 25, WPP_682cf469470432b235cb9a4961616e40_Traceguids, BugCheckParameter2 - 8);
  UlCleanupBundle(v2 + 81);
  v3 = (volatile signed __int32 *)(v2 + 5);
  v4 = _InterlockedIncrement((volatile signed __int32 *)v2 + 10);
  if ( UxDebugCheckRefcount && v4 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v2 + 5), 0x21u, v4);
  v5 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v2 + 72, 0);
  v8 = v2[71];
  if ( v8 )
  {
    UlQueryRequestQueueRequestState(v2[71], &v42, &v43);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v8 + 2228), 1, 0) && *(_QWORD *)(v8 + 1376) && v42 )
    {
      v5 = 1;
      if ( (int)UlpZombifyHttpConnection(BugCheckParameter2 - 8) >= 0 )
        goto LABEL_7;
      UlErrorLog((_DWORD)BugCheckParameter2 - 64, v8, (unsigned int)"Connection_Dropped_List_Full", 28, 0, 1, 0);
LABEL_93:
      UlUnlinkHttpRequest(v8, v35, v36, v37);
      v5 = 0;
      v2[71] = 0;
      *((_DWORD *)v2 + 158) |= 2u;
      goto LABEL_8;
    }
    if ( (*((_DWORD *)v2 + 86) & 0x80u) != 0 )
    {
      UlpErrorLogConnectionReset(BugCheckParameter2 - 8, v8, v43);
      goto LABEL_93;
    }
    if ( *(_DWORD *)(v8 + 1868) || *(_DWORD *)(v8 + 2116) == 1 )
      goto LABEL_93;
    v40 = v2 + 62;
    if ( UxKirHttpBugFix25Q1 )
    {
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v2 + 62, 12, &v44, &v45, 0, 0);
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, __int64 *, _QWORD, _QWORD))(v2[63] + 136))(
              *v40,
              12,
              &v44,
              &v45,
              0,
              0);
      v38 = v34;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) == 0 )
        goto LABEL_73;
    }
    else
    {
      if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
        WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v2 + 62, 12, &v44, 0, 0, 0);
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, _QWORD, _QWORD, _QWORD))(v2[63] + 136))(
              *v40,
              12,
              &v44,
              0,
              0,
              0);
      v38 = v34;
      if ( (BYTE3(xmmword_1401A2CA0) & 2) == 0 )
        goto LABEL_73;
    }
    WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v34);
LABEL_73:
    if ( v38 >= 0 )
    {
      v36 = v44;
      if ( v44 )
      {
        v39 = -1;
        do
          ++v39;
        while ( *(_BYTE *)(v44 + v39) );
        UlErrorLog((_DWORD)BugCheckParameter2 - 64, v8, v44, v39, v45, 1, 0);
      }
    }
    goto LABEL_93;
  }
LABEL_7:
  *((_DWORD *)v2 + 158) |= 2u;
  if ( v5 )
    goto LABEL_9;
LABEL_8:
  if ( v2[6] )
  {
    UxFreeOpaqueId();
    v2[6] = 0;
    v12 = _InterlockedDecrement(v3);
    if ( UxDebugCheckRefcount && v12 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(v2 + 5), 0x10u, v12);
    if ( !v12 )
    {
      CurrentProcess = IoGetCurrentProcess();
      v15 = v2[136];
      v16 = *BugCheckParameter2;
      if ( UxSystemProcess == CurrentProcess )
      {
        v41 = 0;
        if ( v16 || BugCheckParameter2[2] || BugCheckParameter2[4] )
          goto LABEL_33;
        if ( !KeGetCurrentIrql() )
        {
          UxPodAttachThread(v15, &v41);
          UlFreeHttpConnection((__int64)BugCheckParameter2, v17, v18, v19);
          UxPodDetachThread(&v41);
          goto LABEL_9;
        }
      }
      else if ( v16 || BugCheckParameter2[2] || BugCheckParameter2[4] )
      {
        goto LABEL_61;
      }
      LOBYTE(v14) = 1;
      UlThreadPoolEnqueueWorkItem(0, BugCheckParameter2, UlFreeHttpConnection, v14, v15, -1);
    }
  }
LABEL_9:
  *((_DWORD *)v2 + 158) |= 8u;
  if ( (v2[79] & 0x20) != 0 )
  {
    LOBYTE(v6) = 1;
    UlCompleteWaitForDisconnects((__int64)(BugCheckParameter2 - 8), v6, v7);
  }
  UlCleanupConnectionCouplings((__int64)(BugCheckParameter2 - 8));
  ExReleasePushLockExclusiveEx(v2 + 72, 0);
  KeLeaveCriticalRegion();
  result = (unsigned int)_InterlockedDecrement(v3);
  if ( UxDebugCheckRefcount && (int)result <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v2 + 5), 0x21u, (int)result);
  v10 = v2 + 136;
  if ( !(_DWORD)result )
  {
    v20 = IoGetCurrentProcess();
    v22 = *v10;
    v23 = *BugCheckParameter2;
    if ( UxSystemProcess == v20 )
    {
      if ( v23 || BugCheckParameter2[2] || BugCheckParameter2[4] )
        goto LABEL_33;
      if ( !KeGetCurrentIrql() )
      {
        v41 = 0;
        if ( v22 != -1 )
        {
          LOBYTE(v41) = 1;
          v33 = PsAttachSiloToCurrentThread(v22);
          *((_QWORD *)&v41 + 1) = v33;
          if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
            WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v33, v22);
        }
        UlFreeHttpConnection((__int64)BugCheckParameter2, v31, v32, v21);
        result = UxPodDetachThread(&v41);
        goto LABEL_13;
      }
    }
    else if ( v23 || BugCheckParameter2[2] || BugCheckParameter2[4] )
    {
      goto LABEL_61;
    }
    LOBYTE(v21) = 1;
    result = UlThreadPoolEnqueueWorkItem(0, BugCheckParameter2, UlFreeHttpConnection, v21, v22, -1);
  }
LABEL_13:
  if ( !v5 )
  {
    v11 = _InterlockedDecrement(v3);
    if ( UxDebugCheckRefcount && v11 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v3, 0xDu, v11);
    if ( !v11 )
    {
      v24 = IoGetCurrentProcess();
      v26 = *v10;
      v27 = *BugCheckParameter2;
      if ( UxSystemProcess == v24 )
      {
        if ( !v27 && !BugCheckParameter2[2] && !BugCheckParameter2[4] )
        {
          if ( !KeGetCurrentIrql() )
          {
            v41 = 0;
            if ( v26 != -1 )
            {
              LOBYTE(v41) = 1;
              v30 = PsAttachSiloToCurrentThread(v26);
              *((_QWORD *)&v41 + 1) = v30;
              if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
                WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v30, v26);
            }
            UlFreeHttpConnection((__int64)BugCheckParameter2, v28, v29, v25);
            result = UxPodDetachThread(&v41);
            goto LABEL_16;
          }
LABEL_55:
          LOBYTE(v25) = 1;
          result = UlThreadPoolEnqueueWorkItem(0, BugCheckParameter2, UlFreeHttpConnection, v25, v26, -1);
          goto LABEL_16;
        }
LABEL_33:
        UlBugCheckEx(1u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
      }
      if ( !v27 && !BugCheckParameter2[2] && !BugCheckParameter2[4] )
        goto LABEL_55;
LABEL_61:
      UlBugCheckEx(1u, (ULONG_PTR)BugCheckParameter2, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    }
  }
LABEL_16:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return WPP_SF_(1032, 26, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1400568c0  push    rbp
0x1400568c2  push    rbx
0x1400568c3  push    rdi
0x1400568c4  push    r14
0x1400568c6  lea     rbp, [rsp-3Fh]
0x1400568cb  sub     rsp, 88h
0x1400568d2  xor     eax, eax
0x1400568d4  mov     [rbp+57h+arg_0], 0
0x1400568d8  mov     [rbp+57h+arg_10], rax
0x1400568dc  mov     r14, rcx
0x1400568df  mov     [rbp+57h+arg_18], rax
0x1400568e3  mov     [rbp+57h+arg_8], 0
0x1400568e7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400568ee  jnz     loc_140056F02
0x1400568f4  lea     rbx, [r14-40h]
0x1400568f8  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x1400568ff  jnz     loc_140056F20
0x140056905  lea     rcx, [rbx+288h]
0x14005690c  call    UlCleanupBundle
0x140056911  mov     eax, 1
0x140056916  lea     rdi, [rbx+28h]
0x14005691a  lock xadd [rdi], eax
0x14005691e  inc     eax
0x140056920  cmp     cs:UxDebugCheckRefcount, 0
0x140056927  jnz     loc_140056A4C
0x14005692d  mov     [rsp+0A0h+var_20], rsi
0x140056935  mov     [rsp+0A0h+var_28], r12
0x14005693a  mov     [rsp+0A0h+var_30], r13
0x14005693f  mov     [rsp+0A0h+var_38], r15
0x140056944  xor     r15b, r15b
0x140056947  call    cs:__imp_KeEnterCriticalRegion
0x14005694e  nop     dword ptr [rax+rax+00h]
0x140056953  xor     edx, edx
0x140056955  lea     rcx, [rbx+240h]
0x14005695c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140056963  nop     dword ptr [rax+rax+00h]
0x140056968  mov     r13, [rbx+238h]
0x14005696f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140056976  test    r13, r13
0x140056979  jnz     loc_140177098
0x14005697f  or      dword ptr [rbx+278h], 2
0x140056986  test    r15b, r15b
0x140056989  jnz     short loc_140056998
0x14005698b  mov     rcx, [rbx+30h]
0x14005698f  test    rcx, rcx
0x140056992  jnz     loc_140056A6C
0x140056998  or      dword ptr [rbx+278h], 8
0x14005699f  mov     eax, [rbx+278h]
0x1400569a5  test    al, 20h
0x1400569a7  jnz     loc_140056F3E
0x1400569ad  mov     rcx, rbx
0x1400569b0  call    UlCleanupConnectionCouplings
0x1400569b5  xor     edx, edx
0x1400569b7  lea     rcx, [rbx+240h]
0x1400569be  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400569c5  nop     dword ptr [rax+rax+00h]
0x1400569ca  call    cs:__imp_KeLeaveCriticalRegion
0x1400569d1  nop     dword ptr [rax+rax+00h]
0x1400569d6  mov     eax, esi
0x1400569d8  lock xadd [rdi], eax
0x1400569dc  dec     eax
0x1400569de  cmp     cs:UxDebugCheckRefcount, 0
0x1400569e5  jnz     loc_140056BE1
0x1400569eb  add     rbx, 440h
0x1400569f2  test    eax, eax
0x1400569f4  jz      loc_140056B07
0x1400569fa  test    r15b, r15b
0x1400569fd  jnz     short loc_140056A1A
0x1400569ff  lock xadd [rdi], esi
0x140056a03  dec     esi
0x140056a05  cmp     cs:UxDebugCheckRefcount, r15b
0x140056a0c  jnz     loc_140056C00
0x140056a12  test    esi, esi
0x140056a14  jz      loc_140056B56
0x140056a1a  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140056a21  jnz     loc_140056F4D
0x140056a27  mov     r13, [rsp+0A0h+var_30]
0x140056a2c  mov     r12, [rsp+0A0h+var_28]
0x140056a31  mov     rsi, [rsp+0A0h+var_20]
0x140056a39  mov     r15, [rsp+0A0h+var_38]
0x140056a3e  add     rsp, 88h
0x140056a45  pop     r14
0x140056a47  pop     rdi
0x140056a48  pop     rbx
0x140056a49  pop     rbp
0x140056a4a  retn
0x140056a4c  cmp     eax, 0FFFFFFFFh
0x140056a4f  jg      loc_14005692D
0x140056a55  movsxd  r9, eax; BugCheckParameter4
0x140056a58  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140056a5e  mov     rdx, rdi; BugCheckParameter2
0x140056a61  mov     ecx, 3; BugCheckParameter1
0x140056a66  call    UlBugCheckEx
0x140056a6c  call    UxFreeOpaqueId
0x140056a71  mov     eax, esi
0x140056a73  mov     qword ptr [rbx+30h], 0
0x140056a7b  lock xadd [rdi], eax
0x140056a7f  dec     eax
0x140056a81  cmp     cs:UxDebugCheckRefcount, 0
0x140056a88  jnz     loc_140056C20
0x140056a8e  test    eax, eax
0x140056a90  jnz     loc_140056998
0x140056a96  call    cs:__imp_IoGetCurrentProcess
0x140056a9d  nop     dword ptr [rax+rax+00h]
0x140056aa2  cmp     cs:UxSystemProcess, rax
0x140056aa9  mov     r13, [rbx+440h]
0x140056ab0  mov     rcx, [r14]
0x140056ab3  jnz     loc_140056D55
0x140056ab9  xorps   xmm0, xmm0
0x140056abc  movups  [rbp+57h+var_50], xmm0
0x140056ac0  test    rcx, rcx
0x140056ac3  jnz     short loc_140056B3B
0x140056ac5  cmp     [r14+10h], rcx
0x140056ac9  jnz     short loc_140056B3B
0x140056acb  cmp     [r14+20h], rcx
0x140056acf  jnz     short loc_140056B3B
0x140056ad1  call    cs:__imp_KeGetCurrentIrql
0x140056ad8  nop     dword ptr [rax+rax+00h]
0x140056add  test    al, al
0x140056adf  jnz     loc_140056CE8
0x140056ae5  lea     rdx, [rbp+57h+var_50]
0x140056ae9  mov     rcx, r13
0x140056aec  call    UxPodAttachThread
0x140056af1  mov     rcx, r14
0x140056af4  call    UlFreeHttpConnection
0x140056af9  lea     rcx, [rbp+57h+var_50]
0x140056afd  call    UxPodDetachThread
0x140056b02  jmp     loc_140056998
0x140056b07  call    cs:__imp_IoGetCurrentProcess
0x140056b0e  nop     dword ptr [rax+rax+00h]
0x140056b13  cmp     cs:UxSystemProcess, rax
0x140056b1a  mov     r12, [rbx]
0x140056b1d  mov     rcx, [r14]
0x140056b20  jnz     loc_140056D0E
0x140056b26  test    rcx, rcx
0x140056b29  jnz     short loc_140056B3B
0x140056b2b  cmp     [r14+10h], rcx
0x140056b2f  jnz     short loc_140056B3B
0x140056b31  cmp     [r14+20h], rcx
0x140056b35  jz      loc_140056C3F
0x140056b3b  mov     r9d, 0E1h; BugCheckParameter4
0x140056b41  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140056b48  mov     rdx, r14; BugCheckParameter2
0x140056b4b  mov     ecx, 1; BugCheckParameter1
0x140056b50  call    UlBugCheckEx
0x140056b56  call    cs:__imp_IoGetCurrentProcess
0x140056b5d  nop     dword ptr [rax+rax+00h]
0x140056b62  cmp     cs:UxSystemProcess, rax
0x140056b69  mov     rbx, [rbx]
0x140056b6c  mov     rcx, [r14]
0x140056b6f  jnz     loc_140056D3E
0x140056b75  test    rcx, rcx
0x140056b78  jnz     short loc_140056B3B
0x140056b7a  cmp     [r14+10h], rcx
0x140056b7e  jnz     short loc_140056B3B
0x140056b80  cmp     [r14+20h], rcx
0x140056b84  jnz     short loc_140056B3B
0x140056b86  call    cs:__imp_KeGetCurrentIrql
0x140056b8d  nop     dword ptr [rax+rax+00h]
0x140056b92  test    al, al
0x140056b94  jnz     loc_140056CBB
0x140056b9a  xorps   xmm0, xmm0
0x140056b9d  movups  [rbp+57h+var_50], xmm0
0x140056ba1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140056ba5  jz      short loc_140056BCB
0x140056ba7  mov     rcx, rbx
0x140056baa  mov     byte ptr [rbp+57h+var_50], 1
0x140056bae  call    cs:__imp_PsAttachSiloToCurrentThread
0x140056bb5  nop     dword ptr [rax+rax+00h]
0x140056bba  mov     qword ptr [rbp+57h+var_50+8], rax
0x140056bbe  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140056bc5  jnz     loc_140056D88
0x140056bcb  mov     rcx, r14
0x140056bce  call    UlFreeHttpConnection
0x140056bd3  lea     rcx, [rbp+57h+var_50]
0x140056bd7  call    UxPodDetachThread
0x140056bdc  jmp     loc_140056A1A
0x140056be1  cmp     eax, esi
0x140056be3  jg      loc_1400569EB
0x140056be9  movsxd  r9, eax; BugCheckParameter4
0x140056bec  mov     r8d, 21h ; '!'; BugCheckParameter3
0x140056bf2  mov     rdx, rdi; BugCheckParameter2
0x140056bf5  mov     ecx, 3; BugCheckParameter1
0x140056bfa  call    UlBugCheckEx
0x140056c00  cmp     esi, 0FFFFFFFFh
0x140056c03  jg      loc_140056A12
0x140056c09  movsxd  r9, esi; BugCheckParameter4
0x140056c0c  mov     r8d, 0Dh; BugCheckParameter3
0x140056c12  mov     rdx, rdi; BugCheckParameter2
0x140056c15  mov     ecx, 3; BugCheckParameter1
0x140056c1a  call    UlBugCheckEx
0x140056c20  cmp     eax, esi
0x140056c22  jg      loc_140056A8E
0x140056c28  movsxd  r9, eax; BugCheckParameter4
0x140056c2b  mov     r8d, 10h; BugCheckParameter3
0x140056c31  mov     rdx, rdi; BugCheckParameter2
0x140056c34  mov     ecx, 3; BugCheckParameter1
0x140056c39  call    UlBugCheckEx
0x140056c3f  call    cs:__imp_KeGetCurrentIrql
0x140056c46  nop     dword ptr [rax+rax+00h]
0x140056c4b  test    al, al
0x140056c4d  jnz     short loc_140056C95
0x140056c4f  xorps   xmm0, xmm0
0x140056c52  movups  [rbp+57h+var_50], xmm0
0x140056c56  cmp     r12, rsi
0x140056c59  jz      short loc_140056C7F
0x140056c5b  mov     rcx, r12
0x140056c5e  mov     byte ptr [rbp+57h+var_50], 1
0x140056c62  call    cs:__imp_PsAttachSiloToCurrentThread
0x140056c69  nop     dword ptr [rax+rax+00h]
0x140056c6e  mov     qword ptr [rbp+57h+var_50+8], rax
0x140056c72  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x140056c79  jnz     loc_140056D65
0x140056c7f  mov     rcx, r14
0x140056c82  call    UlFreeHttpConnection
0x140056c87  lea     rcx, [rbp+57h+var_50]
0x140056c8b  call    UxPodDetachThread
0x140056c90  jmp     loc_1400569FA
0x140056c95  mov     dword ptr [rsp+0A0h+var_78], 0FFFFFFFFh
0x140056c9d  lea     r8, UlFreeHttpConnection
0x140056ca4  mov     r9b, 1
0x140056ca7  mov     [rsp+0A0h+var_80], r12
0x140056cac  mov     rdx, r14
0x140056caf  xor     ecx, ecx
0x140056cb1  call    UlThreadPoolEnqueueWorkItem
0x140056cb6  jmp     loc_1400569FA
0x140056cbb  mov     dword ptr [rsp+0A0h+var_78], 0FFFFFFFFh
0x140056cc3  lea     r8, UlFreeHttpConnection
0x140056cca  mov     r9b, 1
0x140056ccd  mov     [rsp+0A0h+var_80], rbx
0x140056cd2  mov     rdx, r14
0x140056cd5  xor     ecx, ecx
0x140056cd7  call    UlThreadPoolEnqueueWorkItem
0x140056cdc  jmp     loc_140056A1A
0x140056ce1  cmp     qword ptr [r14+20h], 0
0x140056ce6  jnz     short loc_140056D23
0x140056ce8  mov     dword ptr [rsp+0A0h+var_78], 0FFFFFFFFh
0x140056cf0  lea     r8, UlFreeHttpConnection
0x140056cf7  mov     r9b, 1
0x140056cfa  mov     [rsp+0A0h+var_80], r13
0x140056cff  mov     rdx, r14
0x140056d02  xor     ecx, ecx
0x140056d04  call    UlThreadPoolEnqueueWorkItem
0x140056d09  jmp     loc_140056998
0x140056d0e  test    rcx, rcx
0x140056d11  jnz     short loc_140056D23
0x140056d13  cmp     [r14+10h], rcx
0x140056d17  jnz     short loc_140056D23
0x140056d19  cmp     [r14+20h], rcx
0x140056d1d  jz      loc_140056C95
0x140056d23  mov     r9d, 0DBh; BugCheckParameter4
0x140056d29  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140056d30  mov     rdx, r14; BugCheckParameter2
0x140056d33  mov     ecx, 1; BugCheckParameter1
0x140056d38  call    UlBugCheckEx
0x140056d3e  test    rcx, rcx
0x140056d41  jnz     short loc_140056D23
0x140056d43  cmp     [r14+10h], rcx
0x140056d47  jnz     short loc_140056D23
0x140056d49  cmp     [r14+20h], rcx
0x140056d4d  jz      loc_140056CBB
0x140056d53  jmp     short loc_140056D23
0x140056d55  test    rcx, rcx
0x140056d58  jnz     short loc_140056D23
0x140056d5a  cmp     [r14+10h], rcx
0x140056d5e  jnz     short loc_140056D23
0x140056d60  jmp     loc_140056CE1
0x140056d65  mov     edx, 19h
0x140056d6a  mov     [rsp+0A0h+var_80], r12
0x140056d6f  mov     ecx, 51Ch
0x140056d74  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140056d7b  mov     r9, rax
0x140056d7e  call    WPP_SF_qq
0x140056d83  jmp     loc_140056C7F
0x140056d88  mov     edx, 19h
0x140056d8d  mov     [rsp+0A0h+var_80], rbx
0x140056d92  mov     ecx, 51Ch
0x140056d97  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140056d9e  mov     r9, rax
0x140056da1  call    WPP_SF_qq
0x140056da6  jmp     loc_140056BCB
0x140056dab  test    byte ptr cs:xmmword_1401A2CA0+3, 2
0x140056db2  jz      short loc_140056DF9
0x140056db4  mov     [rsp+0A0h+var_60], 0
0x140056dbd  lea     rax, [rbp+57h+arg_18]
0x140056dc1  mov     [rsp+0A0h+var_68], 0
0x140056dca  lea     r8, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids
0x140056dd1  mov     [rsp+0A0h+var_70], rax
0x140056dd6  mov     edx, 0Ah
0x140056ddb  lea     rax, [rbp+57h+arg_10]
0x140056ddf  mov     ecx, 419h
0x140056de4  mov     [rsp+0A0h+var_78], rax
0x140056de9  mov     r9, r15
0x140056dec  mov     dword ptr [rsp+0A0h+var_80], 0Ch
0x140056df4  call    WPP_SF_qLqqqq
0x140056df9  mov     rax, [r15+8]
0x140056dfd  lea     r9, [rbp+57h+arg_18]
0x140056e01  mov     rcx, [r15]
0x140056e04  lea     r8, [rbp+57h+arg_10]
0x140056e08  mov     [rsp+0A0h+var_78], 0
  ... truncated ...
```
