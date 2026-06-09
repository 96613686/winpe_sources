# UlpScavengerThread

- ea: `0x140099af0`
- end: `0x140099ee3`
- name: `UlpScavengerThread`
- size: `1011`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140099af0`
- `0x140099eec`
- `0x140167810`
- `0x1401678f0`
- `0x1401c3f58`
- `0x1401d9e44`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140099d16`
- `ntoskrnl!KeCancelTimer` at `0x140099d16`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140099d02`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140099d02`
- `ntoskrnl!PsTerminateSystemThread` at `0x140099e68`
- `ntoskrnl!PsTerminateSystemThread` at `0x140099e68`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140099ccc`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140099ccc`
- `ntoskrnl!KeReadStateEvent` at `0x140099b4d`
- `ntoskrnl!KeReadStateEvent` at `0x140099b4d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140099dd2`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140099dd2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099b74`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099d2e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099b74`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140099d2e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099c98`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099d59`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099c98`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140099d59`

## pseudocode

```c
void __fastcall UlpScavengerThread(PVOID StartContext)
{
  unsigned __int64 v1; // r14
  unsigned __int64 v2; // r9
  __int64 *v3; // r8
  __int64 v4; // rdi
  int v5; // r11d
  unsigned __int64 v6; // r10
  unsigned __int64 v7; // rax
  char v8; // si
  LARGE_INTEGER v9; // rbx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  unsigned int *v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Object[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  struct _KWAIT_BLOCK WaitBlockArray; // [rsp+90h] [rbp-70h] BYREF

  v19 = 0;
  *(_OWORD *)Object = 0;
  v18 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v15 = 0;
  v1 = MEMORY[0xFFFFF78000000008];
  while ( !KeReadStateEvent(&UlScavengerTerminateThreadEvent) )
  {
    KeAcquireInStackQueuedSpinLock(&UlScavengerListLock, &LockHandle);
    v2 = -1;
    v3 = (__int64 *)UlScavengerEnabledList;
    v4 = 0;
    v5 = 8;
    v6 = (-(__int64)(UlPartitionsActiveCount != 0) & 0xFFFFFFFF502A9280uLL) + 3000000000u;
    if ( (__int64 *)UlScavengerEnabledList == &UlScavengerEnabledList )
      goto LABEL_14;
    do
    {
      if ( *((_DWORD *)v3 - 15) == 1 )
      {
        v7 = *(v3 - 5);
        if ( v1 < v7 )
        {
          if ( v7 < v2 )
          {
            v2 = *(v3 - 5);
            goto LABEL_35;
          }
        }
        else if ( (unsigned int)v4 < 5 )
        {
          Object[v4] = (PVOID)*(v3 - 7);
          v4 = (unsigned int)(v4 + 1);
        }
      }
      else
      {
        v13 = *(v3 - 6);
        if ( v13 < v2 )
        {
          v14 = *((_BYTE *)v3 - 40) ? 50000000 * ((v13 + 49999999) / 0x2FAF080) : v13 + v6 - 1 - (v13 + v6 - 1) % v6;
          if ( v14 < v2 )
          {
            v2 = v14;
LABEL_35:
            v5 = *((_DWORD *)v3 - 16);
          }
        }
      }
      v3 = (__int64 *)*v3;
    }
    while ( v3 != &UlScavengerEnabledList );
    if ( v2 != -1 )
    {
      v8 = 1;
      v9.QuadPart = (v1 - v2) & ((v1 - (unsigned __int128)v2) >> 64);
      if ( (unsigned int)v4 < 5 )
      {
        Object[v4] = &UlScavengerWaitTimer;
        v4 = (unsigned int)(v4 + 1);
      }
      if ( (BYTE10(xmmword_1401A2CA0) & 8) != 0 )
        WPP_SF_Dd(1299, 14, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids, v9.QuadPart / -10000, v5);
      goto LABEL_16;
    }
LABEL_14:
    v8 = 0;
    v9.QuadPart = 0;
    if ( (BYTE10(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_(1299, 15, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids);
LABEL_16:
    if ( (unsigned int)v4 < 5 )
    {
      Object[v4] = &UlScavengerTerminateThreadEvent;
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 < 5 )
      {
        Object[v4] = &UlScavengerRefreshEvent;
        LODWORD(v4) = v4 + 1;
      }
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v8 )
      KeSetCoalescableTimer(&UlScavengerWaitTimer, v9, 0, 0x3E8u, 0);
    KeWaitForMultipleObjects(v4, Object, WaitAny, Executive, 0, 0, 0, &WaitBlockArray);
    if ( v8 )
      KeCancelTimer(&UlScavengerWaitTimer);
    KeAcquireInStackQueuedSpinLock(&UlScavengerListLock, &LockHandle);
    v1 = MEMORY[0xFFFFF78000000008];
    UlpProcessExpiredScavengers(MEMORY[0xFFFFF78000000008], &v15);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    while ( 1 )
    {
      v10 = (_QWORD *)v15;
      if ( (__int128 *)v15 == &v15 )
        break;
      if ( *(__int128 **)(v15 + 8) != &v15 || (v11 = *(_QWORD *)v15, *(_QWORD *)(*(_QWORD *)v15 + 8LL) != (_QWORD)v15) )
        __fastfail(3u);
      *(_QWORD *)&v15 = *(_QWORD *)v15;
      *(_QWORD *)(v11 + 8) = &v15;
      v12 = (unsigned int *)(v10 - 10);
      *v10 = 0;
      v10[1] = 0;
      if ( (BYTE10(xmmword_1401A2CA0) & 8) != 0 )
        WPP_SF_d(1299, 16, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids, *v12);
      (*((void (__fastcall **)(unsigned int *))v12 + 5))(v12);
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)v12 + 13);
    }
  }
  if ( (BYTE2(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_(1043, 17, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140099af0  push    rbp
0x140099af2  push    rbx
0x140099af3  push    rsi
0x140099af4  push    rdi
0x140099af5  push    r14
0x140099af7  lea     rbp, [rsp-90h]
0x140099aff  sub     rsp, 190h
0x140099b06  mov     rax, cs:__security_cookie
0x140099b0d  xor     rax, rsp
0x140099b10  mov     [rbp+0B0h+var_30], rax
0x140099b17  xorps   xmm0, xmm0
0x140099b1a  xor     eax, eax
0x140099b1c  mov     [rbp+0B0h+var_128], rax
0x140099b20  mov     qword ptr [rsp+1B0h+LockHandle.OldIrql], rax
0x140099b25  mov     rax, 0FFFFF78000000008h
0x140099b2f  movups  xmmword ptr [rsp+1B0h+Object], xmm0
0x140099b34  movups  [rsp+1B0h+var_138], xmm0
0x140099b39  movups  xmmword ptr [rsp+1B0h+LockHandle.LockQueue.Next], xmm0
0x140099b3e  movups  [rsp+1B0h+var_170], xmm0
0x140099b43  mov     r14, [rax]
0x140099b46  lea     rcx, UlScavengerTerminateThreadEvent; Event
0x140099b4d  call    cs:__imp_KeReadStateEvent
0x140099b54  nop     dword ptr [rax+rax+00h]
0x140099b59  test    eax, eax
0x140099b5b  jnz     loc_140099E5D
0x140099b61  lea     rdx, [rsp+1B0h+LockHandle]; LockHandle
0x140099b66  lea     rcx, UlScavengerListLock; SpinLock
0x140099b6d  lea     rsi, UlScavengerEnabledList
0x140099b74  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140099b7b  nop     dword ptr [rax+rax+00h]
0x140099b80  mov     eax, cs:UlPartitionsActiveCount
0x140099b86  or      r9, 0FFFFFFFFFFFFFFFFh
0x140099b8a  mov     r8, cs:UlScavengerEnabledList
0x140099b91  xor     edi, edi
0x140099b93  neg     eax
0x140099b95  mov     r11d, 8
0x140099b9b  mov     rax, 0FFFFFFFF502A9280h
0x140099ba5  sbb     r10, r10
0x140099ba8  and     r10, rax
0x140099bab  mov     eax, 0B2D05E00h
0x140099bb0  add     r10, rax
0x140099bb3  cmp     r8, rsi
0x140099bb6  jz      loc_140099C5B
0x140099bbc  cmp     dword ptr [r8-3Ch], 1
0x140099bc1  jnz     loc_140099DE0
0x140099bc7  mov     rax, [r8-28h]
0x140099bcb  cmp     r14, rax
0x140099bce  jb      loc_140099E1B
0x140099bd4  cmp     edi, 5
0x140099bd7  jnb     short loc_140099BE4
0x140099bd9  mov     rax, [r8-38h]
0x140099bdd  mov     [rsp+rdi*8+1B0h+Object], rax
0x140099be2  inc     edi
0x140099be4  mov     r8, [r8]
0x140099be7  cmp     r8, rsi
0x140099bea  jnz     short loc_140099BBC
0x140099bec  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x140099bf0  jz      short loc_140099C5B
0x140099bf2  mov     rax, r14
0x140099bf5  mov     sil, 1
0x140099bf8  sub     rax, r9
0x140099bfb  cmp     r14, r9
0x140099bfe  sbb     rbx, rbx
0x140099c01  and     rbx, rax
0x140099c04  cmp     edi, 5
0x140099c07  jnb     short loc_140099C17
0x140099c09  lea     rcx, UlScavengerWaitTimer
0x140099c10  mov     [rsp+rdi*8+1B0h+Object], rcx
0x140099c15  inc     edi
0x140099c17  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 8
0x140099c1e  jz      short loc_140099C6D
0x140099c20  mov     rax, 0CB923A29C779A6B5h
0x140099c2a  mov     dword ptr [rsp+1B0h+Dpc], r11d
0x140099c2f  imul    rbx
0x140099c32  mov     ecx, 513h
0x140099c37  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099c3e  mov     r9, rdx
0x140099c41  mov     edx, 0Eh
0x140099c46  sar     r9, 0Bh
0x140099c4a  mov     rax, r9
0x140099c4d  shr     rax, 3Fh
0x140099c51  add     r9, rax
0x140099c54  call    WPP_SF_Dd
0x140099c59  jmp     short loc_140099C6D
0x140099c5b  xor     sil, sil
0x140099c5e  xor     ebx, ebx
0x140099c60  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 8
0x140099c67  jnz     loc_140099E92
0x140099c6d  cmp     edi, 5
0x140099c70  jnb     short loc_140099C93
0x140099c72  lea     rcx, UlScavengerTerminateThreadEvent
0x140099c79  mov     [rsp+rdi*8+1B0h+Object], rcx
0x140099c7e  inc     edi
0x140099c80  cmp     edi, 5
0x140099c83  jnb     short loc_140099C93
0x140099c85  lea     rcx, UlScavengerRefreshEvent
0x140099c8c  mov     [rsp+rdi*8+1B0h+Object], rcx
0x140099c91  inc     edi
0x140099c93  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x140099c98  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140099c9f  nop     dword ptr [rax+rax+00h]
0x140099ca4  test    sil, sil
0x140099ca7  jz      loc_140099E4A
0x140099cad  mov     rdx, rbx; DueTime
0x140099cb0  mov     [rsp+1B0h+Dpc], 0; Dpc
0x140099cb9  lea     rbx, UlScavengerWaitTimer
0x140099cc0  mov     r9d, 3E8h; TolerableDelay
0x140099cc6  mov     rcx, rbx; Timer
0x140099cc9  xor     r8d, r8d; Period
0x140099ccc  call    cs:__imp_KeSetCoalescableTimer
0x140099cd3  nop     dword ptr [rax+rax+00h]
0x140099cd8  xor     r9d, r9d; WaitReason
0x140099cdb  lea     rax, [rbp+0B0h+var_120]
0x140099cdf  mov     [rsp+1B0h+WaitBlockArray], rax; WaitBlockArray
0x140099ce4  lea     rdx, [rsp+1B0h+Object]; Object
0x140099ce9  mov     [rsp+1B0h+Timeout], 0; Timeout
0x140099cf2  mov     ecx, edi; Count
0x140099cf4  mov     [rsp+1B0h+Alertable], 0; Alertable
0x140099cf9  lea     r8d, [r9+1]; WaitType
0x140099cfd  mov     byte ptr [rsp+1B0h+Dpc], 0; WaitMode
0x140099d02  call    cs:__imp_KeWaitForMultipleObjects
0x140099d09  nop     dword ptr [rax+rax+00h]
0x140099d0e  test    sil, sil
0x140099d11  jz      short loc_140099D22
0x140099d13  mov     rcx, rbx; PKTIMER
0x140099d16  call    cs:__imp_KeCancelTimer
0x140099d1d  nop     dword ptr [rax+rax+00h]
0x140099d22  lea     rdx, [rsp+1B0h+LockHandle]; LockHandle
0x140099d27  lea     rcx, UlScavengerListLock; SpinLock
0x140099d2e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140099d35  nop     dword ptr [rax+rax+00h]
0x140099d3a  mov     rax, 0FFFFF78000000008h
0x140099d44  lea     rdx, [rsp+1B0h+var_170]
0x140099d49  mov     r14, [rax]
0x140099d4c  mov     rcx, r14
0x140099d4f  call    UlpProcessExpiredScavengers
0x140099d54  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x140099d59  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140099d60  nop     dword ptr [rax+rax+00h]
0x140099d65  mov     rax, qword ptr [rsp+1B0h+var_170]
0x140099d6a  lea     rcx, [rsp+1B0h+var_170]
0x140099d6f  cmp     rax, rcx
0x140099d72  jz      loc_140099B46
0x140099d78  lea     rcx, [rsp+1B0h+var_170]
0x140099d7d  cmp     [rax+8], rcx
0x140099d81  jnz     loc_140099E56
0x140099d87  mov     rcx, [rax]
0x140099d8a  cmp     [rcx+8], rax
0x140099d8e  jnz     loc_140099E56
0x140099d94  mov     qword ptr [rsp+1B0h+var_170], rcx
0x140099d99  lea     rdx, [rsp+1B0h+var_170]
0x140099d9e  mov     [rcx+8], rdx
0x140099da2  lea     rbx, [rax-50h]
0x140099da6  mov     qword ptr [rax], 0
0x140099dad  mov     qword ptr [rax+8], 0
0x140099db5  test    byte ptr cs:xmmword_1401A2CA0+0Ah, 8
0x140099dbc  jnz     loc_140099EAD
0x140099dc2  mov     rax, [rbx+28h]
0x140099dc6  mov     rcx, rbx
0x140099dc9  call    _guard_dispatch_icall
0x140099dce  lea     rcx, [rbx+68h]; RunRef
0x140099dd2  call    cs:__imp_ExReleaseRundownProtection
0x140099dd9  nop     dword ptr [rax+rax+00h]
0x140099dde  jmp     short loc_140099D65
0x140099de0  mov     rax, [r8-30h]
0x140099de4  cmp     rax, r9
0x140099de7  jnb     loc_140099BE4
0x140099ded  cmp     byte ptr [r8-28h], 0
0x140099df2  jnz     short loc_140099E29
0x140099df4  xor     edx, edx
0x140099df6  lea     rcx, [r10-1]
0x140099dfa  add     rcx, rax
0x140099dfd  mov     rax, rcx
0x140099e00  div     r10
0x140099e03  sub     rcx, rdx
0x140099e06  cmp     rcx, r9
0x140099e09  jnb     loc_140099BE4
0x140099e0f  mov     r9, rcx
0x140099e12  mov     r11d, [r8-40h]
0x140099e16  jmp     loc_140099BE4
0x140099e1b  cmp     rax, r9
0x140099e1e  jnb     loc_140099BE4
0x140099e24  mov     r9, rax
0x140099e27  jmp     short loc_140099E12
0x140099e29  lea     rcx, [rax+2FAF07Fh]
0x140099e30  mov     rax, 0ABCC77118461CEFDh
0x140099e3a  mul     rcx
0x140099e3d  shr     rdx, 19h
0x140099e41  imul    rcx, rdx, 2FAF080h
0x140099e48  jmp     short loc_140099E06
0x140099e4a  lea     rbx, UlScavengerWaitTimer
0x140099e51  jmp     loc_140099CD8
0x140099e56  mov     ecx, 3
0x140099e5b  int     29h; Win8: RtlFailFast(ecx)
0x140099e5d  test    byte ptr cs:xmmword_1401A2CA0+2, 8
0x140099e64  jnz     short loc_140099ECB
0x140099e66  xor     ecx, ecx; ExitStatus
0x140099e68  call    cs:__imp_PsTerminateSystemThread
0x140099e6f  nop     dword ptr [rax+rax+00h]
0x140099e74  mov     rcx, [rbp+0B0h+var_30]
0x140099e7b  xor     rcx, rsp; StackCookie
0x140099e7e  call    __security_check_cookie
0x140099e83  add     rsp, 190h
0x140099e8a  pop     r14
0x140099e8c  pop     rdi
0x140099e8d  pop     rsi
0x140099e8e  pop     rbx
0x140099e8f  pop     rbp
0x140099e90  retn
0x140099e92  mov     edx, 0Fh
0x140099e97  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099e9e  mov     ecx, 513h
0x140099ea3  call    WPP_SF_
0x140099ea8  jmp     loc_140099C6D
0x140099ead  mov     r9d, [rbx]
0x140099eb0  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099eb7  mov     edx, 10h
0x140099ebc  mov     ecx, 513h
0x140099ec1  call    WPP_SF_d
0x140099ec6  jmp     loc_140099DC2
0x140099ecb  mov     edx, 11h
0x140099ed0  lea     r8, WPP_1dca8244180d3b1ea15b016826925d39_Traceguids
0x140099ed7  mov     ecx, 413h
0x140099edc  call    WPP_SF_
0x140099ee1  jmp     short loc_140099E66
```
