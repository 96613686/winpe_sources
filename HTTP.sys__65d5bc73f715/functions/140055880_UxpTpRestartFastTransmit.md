# UxpTpRestartFastTransmit

- ea: `0x140055880`
- end: `0x140055c02`
- name: `UxpTpRestartFastTransmit`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140053710`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140055880`
- `0x140055c08`
- `0x14005e030`
- `0x14013dd68`
- `0x1401678f0`
- `0x1401c3008`
- `0x1401c3f78`
- `0x1401c4a18`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140055985`
- `ntoskrnl!KeGetCurrentIrql` at `0x140055985`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140055aba`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140055aba`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055a11`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140055a11`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140055a6d`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140055a6d`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140055bca`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x140055bca`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400559b2`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400559b2`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400559ee`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400559ee`
- `ntoskrnl!KeSetEvent` at `0x140055ad8`
- `ntoskrnl!KeSetEvent` at `0x140055ad8`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140055a3a`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140055a3a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140055919`
- `ntoskrnl!IoGetCurrentProcess` at `0x140055919`

## pseudocode

```c
__int64 (__fastcall *__fastcall UxpTpRestartFastTransmit(__int64 a1, int a2, __int64 a3))(_QWORD, _QWORD, __int64)
{
  __int64 v6; // rsi
  int v7; // eax
  __int64 (__fastcall *result)(_QWORD, _QWORD, __int64); // rax
  __int64 v9; // r14
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v11; // r9
  void *CurrentServerSilo; // r15
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  char v17; // si
  __int64 v18; // rax
  __int64 v19; // r12
  ULONG v20; // esi
  ULONG_PTR v21; // rdx
  int v22; // ecx
  __int64 v23; // rsi
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // [rsp+70h] [rbp+8h] BYREF

  if ( a2 >= 0 )
    UxpTpDequeueTransmitPacket(*(PKSPIN_LOCK *)a1, *(_DWORD *)(a1 + 8), 0, 1u);
  v6 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  v7 = _InterlockedDecrement((volatile signed __int32 *)(v6 + 40));
  if ( UxDebugCheckRefcount && v7 <= -1 )
    UlBugCheckEx(3u, v6 + 40, 0x2Au, v7);
  if ( !v7 )
  {
    v9 = v6 + 64;
    CurrentProcess = IoGetCurrentProcess();
    CurrentServerSilo = *(void **)(v6 + 1088);
    v13 = *(_QWORD *)(v6 + 64);
    if ( UxSystemProcess != CurrentProcess )
    {
      if ( v13 || *(_QWORD *)(v6 + 80) || *(_QWORD *)(v6 + 96) )
        UlBugCheckEx(1u, v6 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      LOBYTE(v11) = 1;
      UlThreadPoolEnqueueWorkItem(0, v6 + 64, UlFreeHttpConnection, v11, CurrentServerSilo, -1);
      goto LABEL_5;
    }
    if ( v13 || *(_QWORD *)(v6 + 80) || *(_QWORD *)(v6 + 96) )
      UlBugCheckEx(1u, v6 + 64, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
    if ( KeGetCurrentIrql() )
    {
      v20 = 0;
      if ( (unsigned int)dword_1401A3F08 > 1 )
      {
        v20 = KeGetCurrentProcessorNumberEx(0) % UxNumberOfProcessors;
        if ( byte_1401A3F20 )
          v20 = UlpAssignThreadPoolWork(&UlThreadPoolArena);
      }
      if ( CurrentServerSilo == (void *)-1LL )
        CurrentServerSilo = (void *)PsGetCurrentServerSilo();
      *(_QWORD *)(v9 + 32) = CurrentServerSilo;
      v27 = 0;
      if ( CurrentServerSilo )
        ObfReferenceObjectWithTag(CurrentServerSilo, 0x49576C55u);
      PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)UxPodMonitorSlot, &v27);
      v21 = v27 + 24;
      v22 = _InterlockedIncrement((volatile signed __int32 *)(v27 + 24));
      if ( UxDebugCheckRefcount && v22 <= -1 )
        UlBugCheckEx(3u, v21, 0xDu, v22);
      *(_BYTE *)(v9 + 24) = 1;
      v23 = *(_QWORD *)(qword_1401A3F10 + 8LL * v20);
      *(_QWORD *)(v9 + 16) = UlFreeHttpConnection;
      if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)(v23 + 16), (PSLIST_ENTRY)v9) )
      {
        KeSetEvent((PRKEVENT)(v23 + 32), 0, 0);
        UlpActivateThreadPoolQueue((PVOID)v23);
      }
      goto LABEL_5;
    }
    v17 = 0;
    if ( CurrentServerSilo == (void *)-1LL )
    {
      v19 = 0;
    }
    else
    {
      v18 = PsAttachSiloToCurrentThread(CurrentServerSilo);
      v19 = v18;
      v17 = 1;
      if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
      {
        WPP_SF_qq(1308, 25, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v18, CurrentServerSilo);
        UlFreeHttpConnection(v9, v24, v25, v26);
LABEL_21:
        if ( (BYTE11(xmmword_1401A2CA0) & 0x10) != 0 )
          WPP_SF_q(1308, 26, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids, v19);
        PsDetachSiloFromCurrentThread(v19);
        goto LABEL_5;
      }
    }
    UlFreeHttpConnection(v9, v14, v15, v16);
    if ( !v17 )
      goto LABEL_5;
    goto LABEL_21;
  }
LABEL_5:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qdP(1032, 57, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids, a1, a2, a3);
  result = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 16);
  if ( result )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, __int64))result(*(_QWORD *)(a1 + 24), (unsigned int)a2, a3);
  return result;
}

```

## disassembly

```asm
0x140055880  push    rbx
0x140055882  push    rbp
0x140055883  push    rsi
0x140055884  push    rdi
0x140055885  sub     rsp, 48h
0x140055889  mov     rbp, r8
0x14005588c  mov     edi, edx
0x14005588e  mov     rbx, rcx
0x140055891  test    edx, edx
0x140055893  js      short loc_1400558A6
0x140055895  mov     edx, [rcx+8]
0x140055898  mov     r9b, 1
0x14005589b  mov     rcx, [rcx]; SpinLock
0x14005589e  xor     r8d, r8d
0x1400558a1  call    UxpTpDequeueTransmitPacket
0x1400558a6  mov     rax, [rbx]
0x1400558a9  mov     rsi, [rax+8]
0x1400558ad  mov     eax, 0FFFFFFFFh
0x1400558b2  lea     rdx, [rsi+28h]; BugCheckParameter2
0x1400558b6  lock xadd [rdx], eax
0x1400558ba  dec     eax
0x1400558bc  cmp     cs:UxDebugCheckRefcount, 0
0x1400558c3  jnz     loc_140055968
0x1400558c9  mov     [rsp+68h+arg_10], r14
0x1400558d1  mov     [rsp+68h+var_28], r15
0x1400558d6  test    eax, eax
0x1400558d8  jz      short loc_140055915
0x1400558da  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400558e1  jnz     loc_140055BDB
0x1400558e7  mov     rax, [rbx+10h]
0x1400558eb  test    rax, rax
0x1400558ee  jz      short loc_1400558FE
0x1400558f0  mov     rcx, [rbx+18h]
0x1400558f4  mov     r8, rbp
0x1400558f7  mov     edx, edi
0x1400558f9  call    _guard_dispatch_icall
0x1400558fe  mov     r14, [rsp+68h+arg_10]
0x140055906  mov     r15, [rsp+68h+var_28]
0x14005590b  add     rsp, 48h
0x14005590f  pop     rdi
0x140055910  pop     rsi
0x140055911  pop     rbp
0x140055912  pop     rbx
0x140055913  retn
0x140055915  lea     r14, [rsi+40h]
0x140055919  call    cs:__imp_IoGetCurrentProcess
0x140055920  nop     dword ptr [rax+rax+00h]
0x140055925  cmp     cs:UxSystemProcess, rax
0x14005592c  mov     r15, [rsi+440h]
0x140055933  mov     rcx, [r14]
0x140055936  jnz     loc_140055B14
0x14005593c  test    rcx, rcx
0x14005593f  jnz     short loc_14005594D
0x140055941  cmp     [r14+10h], rcx
0x140055945  jnz     short loc_14005594D
0x140055947  cmp     [r14+20h], rcx
0x14005594b  jz      short loc_140055985
0x14005594d  mov     r9d, 0E1h; BugCheckParameter4
0x140055953  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14005595a  mov     rdx, r14; BugCheckParameter2
0x14005595d  mov     ecx, 1; BugCheckParameter1
0x140055962  call    UlBugCheckEx
0x140055968  cmp     eax, 0FFFFFFFFh
0x14005596b  jg      loc_1400558C9
0x140055971  movsxd  r9, eax; BugCheckParameter4
0x140055974  mov     ecx, 3; BugCheckParameter1
0x140055979  mov     r8d, 2Ah ; '*'; BugCheckParameter3
0x14005597f  call    UlBugCheckEx
0x140055985  call    cs:__imp_KeGetCurrentIrql
0x14005598c  nop     dword ptr [rax+rax+00h]
0x140055991  test    al, al
0x140055993  jnz     short loc_140055A04
0x140055995  xor     sil, sil
0x140055998  mov     [rsp+68h+arg_8], r12
0x14005599d  xorps   xmm0, xmm0
0x1400559a0  movups  [rsp+68h+var_38], xmm0
0x1400559a5  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1400559a9  jz      loc_140055B0A
0x1400559af  mov     rcx, r15
0x1400559b2  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400559b9  nop     dword ptr [rax+rax+00h]
0x1400559be  mov     r12, rax
0x1400559c1  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400559c8  mov     sil, 1
0x1400559cb  jnz     loc_140055B66
0x1400559d1  mov     rcx, r14
0x1400559d4  call    UlFreeHttpConnection
0x1400559d9  test    sil, sil
0x1400559dc  jz      short loc_1400559FA
0x1400559de  test    byte ptr cs:xmmword_1401A2CA0+0Bh, 10h
0x1400559e5  jnz     loc_140055B91
0x1400559eb  mov     rcx, r12
0x1400559ee  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400559f5  nop     dword ptr [rax+rax+00h]
0x1400559fa  mov     r12, [rsp+68h+arg_8]
0x1400559ff  jmp     loc_1400558DA
0x140055a04  xor     esi, esi
0x140055a06  cmp     cs:dword_1401A3F08, 1
0x140055a0d  jbe     short loc_140055A34
0x140055a0f  xor     ecx, ecx; ProcNumber
0x140055a11  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140055a18  nop     dword ptr [rax+rax+00h]
0x140055a1d  xor     edx, edx
0x140055a1f  div     cs:UxNumberOfProcessors
0x140055a25  cmp     cs:byte_1401A3F20, 0
0x140055a2c  mov     esi, edx
0x140055a2e  jnz     loc_140055BAF
0x140055a34  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140055a38  jnz     short loc_140055A49
0x140055a3a  call    cs:__imp_PsGetCurrentServerSilo
0x140055a41  nop     dword ptr [rax+rax+00h]
0x140055a46  mov     r15, rax
0x140055a49  mov     [r14+20h], r15
0x140055a4d  mov     [rsp+68h+arg_0], 0
0x140055a56  test    r15, r15
0x140055a59  jnz     loc_140055BC2
0x140055a5f  mov     edx, cs:UxPodMonitorSlot
0x140055a65  lea     r8, [rsp+68h+arg_0]
0x140055a6a  mov     rcx, r15
0x140055a6d  call    cs:__imp_PsGetPermanentSiloContext
0x140055a74  nop     dword ptr [rax+rax+00h]
0x140055a79  mov     rdx, [rsp+68h+arg_0]
0x140055a7e  mov     ecx, 1
0x140055a83  add     rdx, 18h; BugCheckParameter2
0x140055a87  lock xadd [rdx], ecx
0x140055a8b  inc     ecx
0x140055a8d  cmp     cs:UxDebugCheckRefcount, 0
0x140055a94  jnz     short loc_140055AF1
0x140055a96  mov     byte ptr [r14+18h], 1
0x140055a9b  mov     rdx, r14; ListEntry
0x140055a9e  mov     rax, cs:qword_1401A3F10
0x140055aa5  mov     ecx, esi
0x140055aa7  mov     rsi, [rax+rcx*8]
0x140055aab  lea     rax, UlFreeHttpConnection
0x140055ab2  mov     [r14+10h], rax
0x140055ab6  lea     rcx, [rsi+10h]; ListHead
0x140055aba  call    cs:__imp_ExpInterlockedPushEntrySList
0x140055ac1  nop     dword ptr [rax+rax+00h]
0x140055ac6  test    rax, rax
0x140055ac9  jnz     loc_1400558DA
0x140055acf  lea     rcx, [rsi+20h]; Event
0x140055ad3  xor     r8d, r8d; Wait
0x140055ad6  xor     edx, edx; Increment
0x140055ad8  call    cs:__imp_KeSetEvent
0x140055adf  nop     dword ptr [rax+rax+00h]
0x140055ae4  mov     rcx, rsi; Context
0x140055ae7  call    UlpActivateThreadPoolQueue
0x140055aec  jmp     loc_1400558DA
0x140055af1  cmp     ecx, 0FFFFFFFFh
0x140055af4  jg      short loc_140055A96
0x140055af6  movsxd  r9, ecx; BugCheckParameter4
0x140055af9  mov     r8d, 0Dh; BugCheckParameter3
0x140055aff  mov     ecx, 3; BugCheckParameter1
0x140055b04  call    UlBugCheckEx
0x140055b0a  mov     r12, qword ptr [rsp+68h+var_38+8]
0x140055b0f  jmp     loc_1400559D1
0x140055b14  test    rcx, rcx
0x140055b17  jnz     short loc_140055B25
0x140055b19  cmp     [r14+10h], rcx
0x140055b1d  jnz     short loc_140055B25
0x140055b1f  cmp     [r14+20h], rcx
0x140055b23  jz      short loc_140055B40
0x140055b25  mov     r9d, 0DBh; BugCheckParameter4
0x140055b2b  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x140055b32  mov     rdx, r14; BugCheckParameter2
0x140055b35  mov     ecx, 1; BugCheckParameter1
0x140055b3a  call    UlBugCheckEx
0x140055b40  mov     dword ptr [rsp+68h+var_40], 0FFFFFFFFh
0x140055b48  lea     r8, UlFreeHttpConnection
0x140055b4f  mov     r9b, 1
0x140055b52  mov     [rsp+68h+var_48], r15
0x140055b57  mov     rdx, r14
0x140055b5a  xor     ecx, ecx
0x140055b5c  call    UlThreadPoolEnqueueWorkItem
0x140055b61  jmp     loc_1400558DA
0x140055b66  mov     edx, 19h
0x140055b6b  mov     [rsp+68h+var_48], r15
0x140055b70  mov     ecx, 51Ch
0x140055b75  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140055b7c  mov     r9, rax
0x140055b7f  call    WPP_SF_qq
0x140055b84  mov     rcx, r14
0x140055b87  call    UlFreeHttpConnection
0x140055b8c  jmp     loc_1400559DE
0x140055b91  mov     edx, 1Ah
0x140055b96  lea     r8, WPP_9df1ba5ef8e93a254adb0146ceffa569_Traceguids
0x140055b9d  mov     ecx, 51Ch
0x140055ba2  mov     r9, r12
0x140055ba5  call    WPP_SF_q
0x140055baa  jmp     loc_1400559EB
0x140055baf  lea     rcx, UlThreadPoolArena
0x140055bb6  call    UlpAssignThreadPoolWork
0x140055bbb  mov     esi, eax
0x140055bbd  jmp     loc_140055A34
0x140055bc2  mov     edx, 49576C55h; Tag
0x140055bc7  mov     rcx, r15; Object
0x140055bca  call    cs:__imp_ObfReferenceObjectWithTag
0x140055bd1  nop     dword ptr [rax+rax+00h]
0x140055bd6  jmp     loc_140055A5F
0x140055bdb  mov     edx, 39h ; '9'
0x140055be0  mov     [rsp+68h+var_40], rbp
0x140055be5  mov     ecx, 408h
0x140055bea  mov     dword ptr [rsp+68h+var_48], edi
0x140055bee  mov     r9, rbx
0x140055bf1  lea     r8, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids
0x140055bf8  call    WPP_SF_qdP
0x140055bfd  jmp     loc_1400558E7
```
