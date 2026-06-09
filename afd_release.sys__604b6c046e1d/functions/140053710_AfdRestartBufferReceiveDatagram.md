# AfdRestartBufferReceiveDatagram

- ea: `0x140053710`
- end: `0x1400539b1`
- name: `AfdRestartBufferReceiveDatagram`
- size: `673`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
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
- `0x140053710`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005384f`
- `ntoskrnl!IofCompleteRequest` at `0x140053985`
- `ntoskrnl!IofCompleteRequest` at `0x14005384f`
- `ntoskrnl!IofCompleteRequest` at `0x140053985`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053768`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400537d8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140053768`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400537d8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005374f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140053782`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005374f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140053782`

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
        AFDETW_TRACEBUFFER(v9, v8, *(_QWORD *)(a3 + 56), 0);
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
        AFDETW_TRACEBUFFER(v11, v11 - 21, *(_QWORD *)(a3 + 56), 0);
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
    v16 = AfdIndicatePollEvent(v3, 1u, 0, &LockHandle);
    p_LockHandle = &LockHandle;
    if ( v16 )
      p_LockHandle = 0;
    AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v3, p_LockHandle, 0);
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
0x140053710  mov     [rsp+arg_0], rbx
0x140053715  mov     [rsp+arg_8], rsi
0x14005371a  push    rdi
0x14005371b  sub     rsp, 70h
0x14005371f  mov     rbx, [r8+30h]
0x140053723  xor     eax, eax
0x140053725  xorps   xmm0, xmm0
0x140053728  mov     rdi, r8
0x14005372b  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140053730  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140053735  cmp     [rdx+30h], eax
0x140053738  jge     short loc_140053779
0x14005373a  mov     rdx, [rbx+30h]; Process
0x14005373e  mov     rcx, r8; Entry
0x140053741  call    AfdReturnBuffer
0x140053746  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14005374b  lea     rcx, [rbx+38h]; SpinLock
0x14005374f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140053756  nop     dword ptr [rax+rax+00h]
0x14005375b  bts     dword ptr [rbx+0C0h], 0Fh
0x140053763  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140053768  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005376f  nop     dword ptr [rax+rax+00h]
0x140053774  jmp     loc_140053991
0x140053779  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14005377e  lea     rcx, [rbx+38h]; SpinLock
0x140053782  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140053789  nop     dword ptr [rax+rax+00h]
0x14005378e  lea     rdx, [rbx+60h]
0x140053792  mov     rcx, [rdx]
0x140053795  cmp     rcx, rdx
0x140053798  jz      loc_140053860
0x14005379e  cmp     [rcx+8], rdx
0x1400537a2  jnz     loc_14005390E
0x1400537a8  mov     rax, [rcx]
0x1400537ab  cmp     [rax+8], rcx
0x1400537af  jnz     loc_14005390E
0x1400537b5  mov     [rdx], rax
0x1400537b8  lea     rsi, [rcx-0A8h]
0x1400537bf  mov     [rax+8], rdx
0x1400537c3  xor     eax, eax
0x1400537c5  xchg    rax, [rsi+68h]
0x1400537c9  test    rax, rax
0x1400537cc  jnz     short loc_1400537D3
0x1400537ce  mov     [rcx], rax
0x1400537d1  jmp     short loc_140053792
0x1400537d3  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400537d8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400537df  nop     dword ptr [rax+rax+00h]
0x1400537e4  mov     r8, [rdi+38h]
0x1400537e8  xor     r9d, r9d
0x1400537eb  mov     rdx, rsi
0x1400537ee  call    AFDETW_TRACEBUFFER
0x1400537f3  mov     eax, [rdi+10h]
0x1400537f6  mov     rcx, rsi; Irp
0x1400537f9  mov     rdx, [rdi+70h]; SourceBuffer
0x1400537fd  mov     r8d, [rdi+40h]; SourceBytesToCopy
0x140053801  mov     [rsp+78h+var_30], 0; int
0x140053809  mov     [rsp+78h+var_38], 0; char
0x14005380e  mov     [rsp+78h+var_40], eax; int
0x140053812  mov     eax, [rdi+20h]
0x140053815  lea     r9, [rdx+r8]
0x140053819  mov     [rsp+78h+var_48], eax; int
0x14005381d  mov     rax, [rdi+28h]
0x140053821  mov     [rsp+78h+Src], rax; Src
0x140053826  mov     eax, [rdi+44h]
0x140053829  mov     [rsp+78h+var_58], eax; int
0x14005382d  call    AfdSetupReceiveDatagramIrp
0x140053832  mov     rdx, [rbx+30h]; Process
0x140053836  mov     rcx, rdi; Entry
0x140053839  call    AfdReturnBuffer
0x14005383e  mov     rcx, rbx
0x140053841  call    AfdDereferenceEndpoint
0x140053846  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x14005384c  mov     rcx, rsi; Irp
0x14005384f  call    cs:__imp_IofCompleteRequest
0x140053856  nop     dword ptr [rax+rax+00h]
0x14005385b  jmp     loc_140053999
0x140053860  lea     rdx, [rbx+70h]
0x140053864  mov     rcx, [rdx]
0x140053867  cmp     rcx, rdx
0x14005386a  jz      loc_1400538F5
0x140053870  cmp     [rcx+8], rdx
0x140053874  jnz     loc_14005390E
0x14005387a  mov     rax, [rcx]
0x14005387d  cmp     [rax+8], rcx
0x140053881  jnz     loc_14005390E
0x140053887  mov     [rdx], rax
0x14005388a  lea     rsi, [rcx-0A8h]
0x140053891  mov     [rax+8], rdx
0x140053895  xor     eax, eax
0x140053897  xchg    rax, [rsi+68h]
0x14005389b  test    rax, rax
0x14005389e  jnz     short loc_1400538A5
0x1400538a0  mov     [rcx], rax
0x1400538a3  jmp     short loc_140053864
0x1400538a5  mov     r8, [rdi+38h]
0x1400538a9  xor     r9d, r9d
0x1400538ac  mov     rdx, rsi
0x1400538af  call    AFDETW_TRACEBUFFER
0x1400538b4  mov     eax, [rdi+10h]
0x1400538b7  mov     rcx, rsi; Irp
0x1400538ba  mov     rdx, [rdi+70h]; SourceBuffer
0x1400538be  mov     r8d, [rdi+40h]; SourceBytesToCopy
0x1400538c2  mov     [rsp+78h+var_30], 0; int
0x1400538ca  mov     [rsp+78h+var_38], 0; char
0x1400538cf  mov     [rsp+78h+var_40], eax; int
0x1400538d3  mov     eax, [rdi+20h]
0x1400538d6  lea     r9, [rdx+r8]
0x1400538da  mov     [rsp+78h+var_48], eax; int
0x1400538de  mov     rax, [rdi+28h]
0x1400538e2  mov     [rsp+78h+Src], rax; Src
0x1400538e7  mov     eax, [rdi+44h]
0x1400538ea  mov     [rsp+78h+var_58], eax; int
0x1400538ee  call    AfdSetupReceiveDatagramIrp
0x1400538f3  jmp     short loc_1400538F7
0x1400538f5  xor     esi, esi
0x1400538f7  lea     rax, [rbx+80h]
0x1400538fe  mov     dword ptr [rdi+30h], 0
0x140053905  mov     rcx, [rax+8]
0x140053909  cmp     [rcx], rax
0x14005390c  jz      short loc_140053915
0x14005390e  mov     ecx, 3
0x140053913  int     29h; Win8: RtlFailFast(ecx)
0x140053915  mov     [rdi+8], rcx
0x140053919  xor     r8d, r8d
0x14005391c  mov     [rdi], rax
0x14005391f  mov     [rcx], rdi
0x140053922  mov     rcx, rbx
0x140053925  mov     [rax+8], rdi
0x140053929  inc     dword ptr [rbx+94h]
0x14005392f  lea     edx, [r8+1]
0x140053933  mov     eax, [rdi+40h]
0x140053936  add     [rbx+90h], eax
0x14005393c  mov     byte ptr [rbx+21h], 0
0x140053940  call    AfdNotifySockEventsChangedUnderLock
0x140053945  xor     r8d, r8d
0x140053948  lea     edx, [r8+1]
0x14005394c  call    AfdIndicateEventSelectEvent
0x140053951  xor     r8d, r8d
0x140053954  lea     r9, [rsp+78h+LockHandle]
0x140053959  mov     rcx, rbx
0x14005395c  lea     edx, [r8+1]
0x140053960  call    AfdIndicatePollEvent
0x140053965  xor     r8d, r8d
0x140053968  lea     rdx, [rsp+78h+LockHandle]
0x14005396d  test    al, al
0x14005396f  mov     rcx, rbx
0x140053972  cmovnz  rdx, r8
0x140053976  call    AfdNotifySockIndicateEventsUnlock
0x14005397b  test    rsi, rsi
0x14005397e  jz      short loc_140053991
0x140053980  mov     dl, 2; PriorityBoost
0x140053982  mov     rcx, rsi; Irp
0x140053985  call    cs:__imp_IofCompleteRequest
0x14005398c  nop     dword ptr [rax+rax+00h]
0x140053991  mov     rcx, rbx
0x140053994  call    AfdDereferenceEndpoint
0x140053999  lea     r11, [rsp+78h+var_8]
0x14005399e  mov     eax, 0C0000016h
0x1400539a3  mov     rbx, [r11+10h]
0x1400539a7  mov     rsi, [r11+18h]
0x1400539ab  mov     rsp, r11
0x1400539ae  pop     rdi
0x1400539af  retn
```
