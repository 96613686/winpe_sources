# AfdRestartBufferReceiveDatagram

- ea: `0x1400537b0`
- end: `0x140053a51`
- name: `AfdRestartBufferReceiveDatagram`
- size: `673`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008fb0`
- `0x14000f390`
- `0x14000f450`
- `0x140012610`
- `0x1400137a0`
- `0x140013dc0`
- `0x14001b0d0`
- `0x14001b800`
- `0x1400537b0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400538ef`
- `ntoskrnl!IofCompleteRequest` at `0x140053a25`
- `ntoskrnl!IofCompleteRequest` at `0x1400538ef`
- `ntoskrnl!IofCompleteRequest` at `0x140053a25`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053808`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053878`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053808`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053878`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400537ef`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140053822`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400537ef`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140053822`

## pseudocode

```c
__int64 __fastcall AfdRestartBufferReceiveDatagram(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  _QWORD **v5; // rdx
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  IRP *v8; // rsi
  __int64 v9; // rcx
  _QWORD **v10; // rdx
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  IRP *v13; // rsi
  _QWORD *v14; // rcx
  __int64 v15; // rcx
  char v16; // al
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  v3 = *(_QWORD *)(a3 + 48);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( *(int *)(a2 + 48) >= 0 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
    v5 = (_QWORD **)(v3 + 96);
    while ( 1 )
    {
      v6 = *v5;
      if ( *v5 == v5 )
        break;
      if ( (_QWORD **)v6[1] != v5 )
        goto LABEL_19;
      v7 = (_QWORD *)*v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 )
        goto LABEL_19;
      *v5 = v7;
      v8 = (IRP *)(v6 - 21);
      v7[1] = v5;
      if ( _InterlockedExchange64(v6 - 8, 0) )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AFDETW_TRACEBUFFER(v9, (__int64)v8, *(_QWORD *)(a3 + 56), 0);
        AfdSetupReceiveDatagramIrp(
          v8,
          *(PVOID *)(a3 + 112),
          *(_DWORD *)(a3 + 64),
          (void *)(*(_QWORD *)(a3 + 112) + *(unsigned int *)(a3 + 64)),
          *(_DWORD *)(a3 + 68),
          *(unsigned __int16 **)(a3 + 40),
          *(_DWORD *)(a3 + 32),
          *(_DWORD *)(a3 + 16),
          0,
          0);
        AfdReturnBuffer((unsigned __int16 *)a3, *(PEPROCESS *)(v3 + 48));
        AfdDereferenceEndpoint(v3);
        IofCompleteRequest(v8, AfdPriorityBoost);
        return 3221225494LL;
      }
      *v6 = 0;
    }
    v10 = (_QWORD **)(v3 + 112);
    while ( 1 )
    {
      v11 = *v10;
      if ( *v10 == v10 )
        break;
      if ( (_QWORD **)v11[1] != v10 )
        goto LABEL_19;
      v12 = (_QWORD *)*v11;
      if ( *(_QWORD **)(*v11 + 8LL) != v11 )
        goto LABEL_19;
      *v10 = v12;
      v13 = (IRP *)(v11 - 21);
      v12[1] = v10;
      if ( _InterlockedExchange64(v11 - 8, 0) )
      {
        AFDETW_TRACEBUFFER((__int64)v11, (__int64)(v11 - 21), *(_QWORD *)(a3 + 56), 0);
        AfdSetupReceiveDatagramIrp(
          v13,
          *(PVOID *)(a3 + 112),
          *(_DWORD *)(a3 + 64),
          (void *)(*(_QWORD *)(a3 + 112) + *(unsigned int *)(a3 + 64)),
          *(_DWORD *)(a3 + 68),
          *(unsigned __int16 **)(a3 + 40),
          *(_DWORD *)(a3 + 32),
          *(_DWORD *)(a3 + 16),
          0,
          0);
        goto LABEL_18;
      }
      *v11 = 0;
    }
    v13 = 0;
LABEL_18:
    *(_DWORD *)(a3 + 48) = 0;
    v14 = *(_QWORD **)(v3 + 136);
    if ( *v14 != v3 + 128 )
LABEL_19:
      __fastfail(3u);
    *(_QWORD *)(a3 + 8) = v14;
    *(_QWORD *)a3 = v3 + 128;
    *v14 = a3;
    *(_QWORD *)(v3 + 136) = a3;
    ++*(_DWORD *)(v3 + 148);
    *(_DWORD *)(v3 + 144) += *(_DWORD *)(a3 + 64);
    *(_BYTE *)(v3 + 33) = 0;
    AfdNotifySockEventsChangedUnderLock(v3, 1, 0);
    AfdIndicateEventSelectEvent(v15, 1, 0);
    v16 = AfdIndicatePollEvent(v3, 1, 0, &LockHandle);
    p_LockHandle = &LockHandle;
    if ( v16 )
      p_LockHandle = 0;
    AfdNotifySockIndicateEventsUnlock(v3, p_LockHandle, 0);
    if ( v13 )
      IofCompleteRequest(v13, 2);
  }
  else
  {
    AfdReturnBuffer((unsigned __int16 *)a3, *(PEPROCESS *)(v3 + 48));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v3 + 56), &LockHandle);
    *(_DWORD *)(v3 + 192) |= 0x8000u;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  AfdDereferenceEndpoint(v3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400537b0  mov     [rsp+arg_0], rbx
0x1400537b5  mov     [rsp+arg_8], rsi
0x1400537ba  push    rdi
0x1400537bb  sub     rsp, 70h
0x1400537bf  mov     rbx, [r8+30h]
0x1400537c3  xor     eax, eax
0x1400537c5  xorps   xmm0, xmm0
0x1400537c8  mov     rdi, r8
0x1400537cb  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400537d0  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400537d5  cmp     [rdx+30h], eax
0x1400537d8  jge     short loc_140053819
0x1400537da  mov     rdx, [rbx+30h]; Process
0x1400537de  mov     rcx, r8; Entry
0x1400537e1  call    AfdReturnBuffer
0x1400537e6  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400537eb  lea     rcx, [rbx+38h]; SpinLock
0x1400537ef  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400537f6  nop     dword ptr [rax+rax+00h]
0x1400537fb  bts     dword ptr [rbx+0C0h], 0Fh
0x140053803  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140053808  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005380f  nop     dword ptr [rax+rax+00h]
0x140053814  jmp     loc_140053A31
0x140053819  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14005381e  lea     rcx, [rbx+38h]; SpinLock
0x140053822  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140053829  nop     dword ptr [rax+rax+00h]
0x14005382e  lea     rdx, [rbx+60h]
0x140053832  mov     rcx, [rdx]
0x140053835  cmp     rcx, rdx
0x140053838  jz      loc_140053900
0x14005383e  cmp     [rcx+8], rdx
0x140053842  jnz     loc_1400539AE
0x140053848  mov     rax, [rcx]
0x14005384b  cmp     [rax+8], rcx
0x14005384f  jnz     loc_1400539AE
0x140053855  mov     [rdx], rax
0x140053858  lea     rsi, [rcx-0A8h]
0x14005385f  mov     [rax+8], rdx
0x140053863  xor     eax, eax
0x140053865  xchg    rax, [rsi+68h]
0x140053869  test    rax, rax
0x14005386c  jnz     short loc_140053873
0x14005386e  mov     [rcx], rax
0x140053871  jmp     short loc_140053832
0x140053873  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140053878  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005387f  nop     dword ptr [rax+rax+00h]
0x140053884  mov     r8, [rdi+38h]
0x140053888  xor     r9d, r9d
0x14005388b  mov     rdx, rsi
0x14005388e  call    AFDETW_TRACEBUFFER
0x140053893  mov     eax, [rdi+10h]
0x140053896  mov     rcx, rsi; Irp
0x140053899  mov     rdx, [rdi+70h]; SourceBuffer
0x14005389d  mov     r8d, [rdi+40h]; SourceBytesToCopy
0x1400538a1  mov     [rsp+78h+var_30], 0; int
0x1400538a9  mov     [rsp+78h+var_38], 0; char
0x1400538ae  mov     [rsp+78h+var_40], eax; int
0x1400538b2  mov     eax, [rdi+20h]
0x1400538b5  lea     r9, [rdx+r8]
0x1400538b9  mov     [rsp+78h+var_48], eax; int
0x1400538bd  mov     rax, [rdi+28h]
0x1400538c1  mov     [rsp+78h+Src], rax; Src
0x1400538c6  mov     eax, [rdi+44h]
0x1400538c9  mov     [rsp+78h+var_58], eax; int
0x1400538cd  call    AfdSetupReceiveDatagramIrp
0x1400538d2  mov     rdx, [rbx+30h]; Process
0x1400538d6  mov     rcx, rdi; Entry
0x1400538d9  call    AfdReturnBuffer
0x1400538de  mov     rcx, rbx
0x1400538e1  call    AfdDereferenceEndpoint
0x1400538e6  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400538ec  mov     rcx, rsi; Irp
0x1400538ef  call    cs:__imp_IofCompleteRequest
0x1400538f6  nop     dword ptr [rax+rax+00h]
0x1400538fb  jmp     loc_140053A39
0x140053900  lea     rdx, [rbx+70h]
0x140053904  mov     rcx, [rdx]
0x140053907  cmp     rcx, rdx
0x14005390a  jz      loc_140053995
0x140053910  cmp     [rcx+8], rdx
0x140053914  jnz     loc_1400539AE
0x14005391a  mov     rax, [rcx]
0x14005391d  cmp     [rax+8], rcx
0x140053921  jnz     loc_1400539AE
0x140053927  mov     [rdx], rax
0x14005392a  lea     rsi, [rcx-0A8h]
0x140053931  mov     [rax+8], rdx
0x140053935  xor     eax, eax
0x140053937  xchg    rax, [rsi+68h]
0x14005393b  test    rax, rax
0x14005393e  jnz     short loc_140053945
0x140053940  mov     [rcx], rax
0x140053943  jmp     short loc_140053904
0x140053945  mov     r8, [rdi+38h]
0x140053949  xor     r9d, r9d
0x14005394c  mov     rdx, rsi
0x14005394f  call    AFDETW_TRACEBUFFER
0x140053954  mov     eax, [rdi+10h]
0x140053957  mov     rcx, rsi; Irp
0x14005395a  mov     rdx, [rdi+70h]; SourceBuffer
0x14005395e  mov     r8d, [rdi+40h]; SourceBytesToCopy
0x140053962  mov     [rsp+78h+var_30], 0; int
0x14005396a  mov     [rsp+78h+var_38], 0; char
0x14005396f  mov     [rsp+78h+var_40], eax; int
0x140053973  mov     eax, [rdi+20h]
0x140053976  lea     r9, [rdx+r8]
0x14005397a  mov     [rsp+78h+var_48], eax; int
0x14005397e  mov     rax, [rdi+28h]
0x140053982  mov     [rsp+78h+Src], rax; Src
0x140053987  mov     eax, [rdi+44h]
0x14005398a  mov     [rsp+78h+var_58], eax; int
0x14005398e  call    AfdSetupReceiveDatagramIrp
0x140053993  jmp     short loc_140053997
0x140053995  xor     esi, esi
0x140053997  lea     rax, [rbx+80h]
0x14005399e  mov     dword ptr [rdi+30h], 0
0x1400539a5  mov     rcx, [rax+8]
0x1400539a9  cmp     [rcx], rax
0x1400539ac  jz      short loc_1400539B5
0x1400539ae  mov     ecx, 3
0x1400539b3  int     29h; Win8: RtlFailFast(ecx)
0x1400539b5  mov     [rdi+8], rcx
0x1400539b9  xor     r8d, r8d
0x1400539bc  mov     [rdi], rax
0x1400539bf  mov     [rcx], rdi
0x1400539c2  mov     rcx, rbx
0x1400539c5  mov     [rax+8], rdi
0x1400539c9  inc     dword ptr [rbx+94h]
0x1400539cf  lea     edx, [r8+1]
0x1400539d3  mov     eax, [rdi+40h]
0x1400539d6  add     [rbx+90h], eax
0x1400539dc  mov     byte ptr [rbx+21h], 0
0x1400539e0  call    AfdNotifySockEventsChangedUnderLock
0x1400539e5  xor     r8d, r8d
0x1400539e8  lea     edx, [r8+1]
0x1400539ec  call    AfdIndicateEventSelectEvent
0x1400539f1  xor     r8d, r8d
0x1400539f4  lea     r9, [rsp+78h+LockHandle]
0x1400539f9  mov     rcx, rbx
0x1400539fc  lea     edx, [r8+1]
0x140053a00  call    AfdIndicatePollEvent
0x140053a05  xor     r8d, r8d
0x140053a08  lea     rdx, [rsp+78h+LockHandle]
0x140053a0d  test    al, al
0x140053a0f  mov     rcx, rbx
0x140053a12  cmovnz  rdx, r8
0x140053a16  call    AfdNotifySockIndicateEventsUnlock
0x140053a1b  test    rsi, rsi
0x140053a1e  jz      short loc_140053A31
0x140053a20  mov     dl, 2; PriorityBoost
0x140053a22  mov     rcx, rsi; Irp
0x140053a25  call    cs:__imp_IofCompleteRequest
0x140053a2c  nop     dword ptr [rax+rax+00h]
0x140053a31  mov     rcx, rbx
0x140053a34  call    AfdDereferenceEndpoint
0x140053a39  lea     r11, [rsp+78h+var_8]
0x140053a3e  mov     eax, 0C0000016h
0x140053a43  mov     rbx, [r11+10h]
0x140053a47  mov     rsi, [r11+18h]
0x140053a4b  mov     rsp, r11
0x140053a4e  pop     rdi
0x140053a4f  retn
```
