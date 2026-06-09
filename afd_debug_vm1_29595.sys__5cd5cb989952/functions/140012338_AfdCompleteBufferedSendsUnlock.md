# AfdCompleteBufferedSendsUnlock

- ea: `0x140012338`
- end: `0x140012601`
- name: `AfdCompleteBufferedSendsUnlock`
- size: `713`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140011230`
- `0x140011380`
- `0x140011670`
- `0x140011bf0`

## callees

- `0x14000d070`
- `0x14000f450`
- `0x140012338`
- `0x1400137a0`
- `0x14001b0d0`
- `0x14001b800`
- `0x14001ccdc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140012518`
- `ntoskrnl!IofCompleteRequest` at `0x140012518`
- `ntoskrnl!IofCallDriver` at `0x1400125a6`
- `ntoskrnl!IofCallDriver` at `0x1400125a6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001238b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001247f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012593`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075e16`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001238b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001247f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012593`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140075e16`

## pseudocode

```c
void __fastcall AfdCompleteBufferedSendsUnlock(__int64 a1, struct _KLOCK_QUEUE_HANDLE *a2)
{
  __int64 v2; // rsi
  unsigned int v4; // ecx
  bool v6; // r8
  _QWORD **v7; // rdx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  _QWORD *v14; // rax
  IRP *v15; // r14
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int128 v18; // [rsp+50h] [rbp-10h] BYREF

  v2 = *(_QWORD *)(a1 + 8);
  v4 = *(_DWORD *)(a1 + 148);
  v18 = 0;
  v6 = *(_DWORD *)(a1 + 120) < v4 || (*(_DWORD *)(v2 + 8) & 0x10) != 0 && v4 && *(_DWORD *)(a1 + 124) <= 1u;
  v7 = (_QWORD **)(a1 + 104);
  if ( *v7 == v7 )
  {
    if ( (*(_DWORD *)(a1 + 4) & 0x10000) != 0 )
    {
      v15 = *(IRP **)(a1 + 128);
      if ( !v15 || *(_DWORD *)(a1 + 124) )
      {
        if ( v6 )
        {
          AfdIndicateEventSelectEvent(v2, 4, 0);
          AfdNotifySockEventsChangedUnderLock(v2, 4, 0);
          if ( (unsigned __int8)AfdIndicatePollEvent(v17, 4, 0, a2) )
            a2 = 0;
          AfdNotifySockIndicateEventsUnlock(v2, a2, 0);
        }
        else
        {
          KeReleaseInStackQueuedSpinLock(a2);
        }
      }
      else
      {
        *(_QWORD *)(a1 + 128) = 0;
        KeReleaseInStackQueuedSpinLock(a2);
        IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 24), v15);
      }
      AfdDeleteConnectedReference(a1, 0);
    }
    else if ( v6 )
    {
      AfdIndicateEventSelectEvent(v2, 4, 0);
      AfdNotifySockEventsChangedUnderLock(v2, 4, 0);
      if ( (unsigned __int8)AfdIndicatePollEvent(v10, 4, 0, a2) )
        a2 = 0;
      AfdNotifySockIndicateEventsUnlock(v2, a2, 0);
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(a2);
    }
  }
  else
  {
    *((_QWORD *)&v18 + 1) = &v18;
    *(_QWORD *)&v18 = &v18;
    while ( *(_DWORD *)(a1 + 120) <= *(_DWORD *)(a1 + 148)
         || *v7 == *(_QWORD **)(a1 + 112)
         || *(_DWORD *)(a1 + 124) <= 1u )
    {
      v8 = *v7;
      if ( *v7 == v7 )
        break;
      if ( (_QWORD **)v8[1] != v7 || (v9 = (_QWORD *)*v8, *(_QWORD **)(*v8 + 8LL) != v8) )
LABEL_31:
        __fastfail(3u);
      *v7 = v9;
      v9[1] = v7;
      if ( _InterlockedExchange64(v8 - 8, 0) )
      {
        v14 = (_QWORD *)*((_QWORD *)&v18 + 1);
        if ( **((__int128 ***)&v18 + 1) != &v18 )
          goto LABEL_31;
        v8[1] = *((_QWORD *)&v18 + 1);
        *v8 = &v18;
        *v14 = v8;
        *((_QWORD *)&v18 + 1) = v8;
      }
      else
      {
        *v8 = 0;
      }
    }
    if ( v6 )
    {
      AfdIndicateEventSelectEvent(v2, 4, 0);
      AfdNotifySockEventsChangedUnderLock(v2, 4, 0);
      if ( (unsigned __int8)AfdIndicatePollEvent(v16, 4, 0, a2) )
        a2 = 0;
      AfdNotifySockIndicateEventsUnlock(v2, a2, 0);
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(a2);
    }
    while ( 1 )
    {
      v11 = v18;
      if ( (__int128 *)v18 == &v18 )
        break;
      if ( *(__int128 **)(v18 + 8) != &v18 )
        goto LABEL_31;
      v12 = *(_QWORD *)v18;
      if ( *(_QWORD *)(*(_QWORD *)v18 + 8LL) != (_QWORD)v18 )
        goto LABEL_31;
      v13 = v18 - 168;
      *(_QWORD *)&v18 = *(_QWORD *)v18;
      *(_QWORD *)(v12 + 8) = &v18;
      if ( _InterlockedExchange64((volatile __int64 *)(v11 - 168 + 120), -1) )
      {
        AFDETW_TRACESEND(1, 3025, v2, 0, 1, *(_QWORD *)(v13 + 8), *(_DWORD *)(v13 + 56), *(_DWORD *)(v13 + 48), v13);
        IofCompleteRequest((PIRP)v13, AfdPriorityBoost);
      }
    }
  }
}

```

## disassembly

```asm
0x140012338  push    rbp
0x14001233a  push    rbx
0x14001233b  push    rsi
0x14001233c  push    rdi
0x14001233d  push    r14
0x14001233f  mov     rbp, rsp
0x140012342  sub     rsp, 60h
0x140012346  mov     rsi, [rcx+8]
0x14001234a  mov     rbx, rcx
0x14001234d  mov     ecx, [rcx+94h]
0x140012353  xorps   xmm0, xmm0
0x140012356  mov     rdi, rdx
0x140012359  movups  [rbp+var_10], xmm0
0x14001235d  cmp     [rbx+78h], ecx
0x140012360  jnb     loc_140012400
0x140012366  mov     r8b, 1
0x140012369  lea     rdx, [rbx+68h]
0x14001236d  cmp     [rdx], rdx
0x140012370  jnz     short loc_1400123A3
0x140012372  test    dword ptr [rbx+4], 10000h
0x140012379  jnz     loc_14001256B
0x14001237f  test    r8b, r8b
0x140012382  jnz     loc_140012413
0x140012388  mov     rcx, rdi; LockHandle
0x14001238b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140012392  nop     dword ptr [rax+rax+00h]
0x140012397  add     rsp, 60h
0x14001239b  pop     r14
0x14001239d  pop     rdi
0x14001239e  pop     rsi
0x14001239f  pop     rbx
0x1400123a0  pop     rbp
0x1400123a1  retn
0x1400123a3  lea     rax, [rbp+var_10]
0x1400123a7  mov     qword ptr [rbp+var_10+8], rax
0x1400123ab  lea     rax, [rbp+var_10]
0x1400123af  mov     qword ptr [rbp+var_10], rax
0x1400123b3  mov     eax, [rbx+94h]
0x1400123b9  cmp     [rbx+78h], eax
0x1400123bc  ja      loc_14001245C
0x1400123c2  mov     rcx, [rdx]
0x1400123c5  cmp     rcx, rdx
0x1400123c8  jz      loc_140012473
0x1400123ce  cmp     [rcx+8], rdx
0x1400123d2  jnz     loc_14001254D
0x1400123d8  mov     rax, [rcx]
0x1400123db  cmp     [rax+8], rcx
0x1400123df  jnz     loc_14001254D
0x1400123e5  mov     [rdx], rax
0x1400123e8  mov     [rax+8], rdx
0x1400123ec  xor     eax, eax
0x1400123ee  xchg    rax, [rcx-40h]
0x1400123f2  test    rax, rax
0x1400123f5  jnz     loc_140012529
0x1400123fb  mov     [rcx], rax
0x1400123fe  jmp     short loc_1400123B3
0x140012400  mov     eax, [rsi+8]
0x140012403  test    al, 10h
0x140012405  jnz     loc_140012554
0x14001240b  xor     r8b, r8b
0x14001240e  jmp     loc_140012369
0x140012413  xor     r8d, r8d
0x140012416  mov     rcx, rsi
0x140012419  lea     r14d, [r8+4]
0x14001241d  mov     edx, r14d
0x140012420  call    AfdIndicateEventSelectEvent
0x140012425  xor     r8d, r8d
0x140012428  mov     edx, r14d
0x14001242b  mov     rcx, rsi
0x14001242e  call    AfdNotifySockEventsChangedUnderLock
0x140012433  xor     r8d, r8d
0x140012436  mov     edx, r14d
0x140012439  mov     r9, rdi
0x14001243c  call    AfdIndicatePollEvent
0x140012441  xor     ecx, ecx
0x140012443  test    al, al
0x140012445  cmovnz  rdi, rcx
0x140012449  xor     r8d, r8d
0x14001244c  mov     rdx, rdi
0x14001244f  mov     rcx, rsi
0x140012452  call    AfdNotifySockIndicateEventsUnlock
0x140012457  jmp     loc_140012397
0x14001245c  mov     rax, [rbx+70h]
0x140012460  cmp     [rdx], rax
0x140012463  jz      loc_1400123C2
0x140012469  cmp     dword ptr [rbx+7Ch], 1
0x14001246d  jbe     loc_1400123C2
0x140012473  test    r8b, r8b
0x140012476  jnz     loc_1400125B8
0x14001247c  mov     rcx, rdi; LockHandle
0x14001247f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140012486  nop     dword ptr [rax+rax+00h]
0x14001248b  mov     rax, qword ptr [rbp+var_10]
0x14001248f  lea     rcx, [rbp+var_10]
0x140012493  cmp     rax, rcx
0x140012496  jz      loc_140012397
0x14001249c  lea     rcx, [rbp+var_10]
0x1400124a0  cmp     [rax+8], rcx
0x1400124a4  jnz     loc_14001254D
0x1400124aa  mov     rcx, [rax]
0x1400124ad  cmp     [rcx+8], rax
0x1400124b1  jnz     loc_14001254D
0x1400124b7  lea     rbx, [rax-0A8h]
0x1400124be  mov     qword ptr [rbp+var_10], rcx
0x1400124c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400124c6  lea     rdx, [rbp+var_10]
0x1400124ca  mov     [rcx+8], rdx
0x1400124ce  xchg    rax, [rbx+78h]
0x1400124d2  test    rax, rax
0x1400124d5  jz      short loc_14001248B
0x1400124d7  mov     eax, [rbx+30h]
0x1400124da  xor     r9d, r9d
0x1400124dd  mov     [rsp+60h+var_20], rbx
0x1400124e2  mov     r8, rsi
0x1400124e5  mov     [rsp+60h+var_28], eax
0x1400124e9  mov     edx, 0BD1h
0x1400124ee  mov     eax, [rbx+38h]
0x1400124f1  mov     [rsp+60h+var_30], eax
0x1400124f5  lea     ecx, [r9+1]
0x1400124f9  mov     rax, [rbx+8]
0x1400124fd  mov     [rsp+60h+var_38], rax
0x140012502  mov     [rsp+60h+var_40], 1
0x14001250a  call    AFDETW_TRACESEND
0x14001250f  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140012515  mov     rcx, rbx; Irp
0x140012518  call    cs:__imp_IofCompleteRequest
0x14001251f  nop     dword ptr [rax+rax+00h]
0x140012524  jmp     loc_14001248B
0x140012529  mov     rax, qword ptr [rbp+var_10+8]
0x14001252d  lea     r9, [rbp+var_10]
0x140012531  cmp     [rax], r9
0x140012534  jnz     short loc_14001254D
0x140012536  mov     [rcx+8], rax
0x14001253a  lea     r9, [rbp+var_10]
0x14001253e  mov     [rcx], r9
0x140012541  mov     [rax], rcx
0x140012544  mov     qword ptr [rbp+var_10+8], rcx
0x140012548  jmp     loc_1400123B3
0x14001254d  mov     ecx, 3
0x140012552  int     29h; Win8: RtlFailFast(ecx)
0x140012554  test    ecx, ecx
0x140012556  jz      loc_14001240B
0x14001255c  cmp     dword ptr [rbx+7Ch], 1
0x140012560  jbe     loc_140012366
0x140012566  jmp     loc_14001240B
0x14001256b  mov     r14, [rbx+80h]
0x140012572  test    r14, r14
0x140012575  jz      loc_140075DC8
0x14001257b  cmp     dword ptr [rbx+7Ch], 0
0x14001257f  jnz     loc_140075DC8
0x140012585  mov     rcx, rdi; LockHandle
0x140012588  mov     qword ptr [rbx+80h], 0
0x140012593  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001259a  nop     dword ptr [rax+rax+00h]
0x14001259f  mov     rcx, [rbx+18h]; DeviceObject
0x1400125a3  mov     rdx, r14; Irp
0x1400125a6  call    cs:__imp_IofCallDriver
0x1400125ad  nop     dword ptr [rax+rax+00h]
0x1400125b2  nop
0x1400125b3  jmp     loc_140075E22
0x1400125b8  xor     r8d, r8d
0x1400125bb  mov     rcx, rsi
0x1400125be  lea     r14d, [r8+4]
0x1400125c2  mov     edx, r14d
0x1400125c5  call    AfdIndicateEventSelectEvent
0x1400125ca  xor     r8d, r8d
0x1400125cd  mov     edx, r14d
0x1400125d0  mov     rcx, rsi
0x1400125d3  call    AfdNotifySockEventsChangedUnderLock
0x1400125d8  xor     r8d, r8d
0x1400125db  mov     edx, r14d
0x1400125de  mov     r9, rdi
0x1400125e1  call    AfdIndicatePollEvent
0x1400125e6  xor     ecx, ecx
0x1400125e8  test    al, al
0x1400125ea  cmovnz  rdi, rcx
0x1400125ee  xor     r8d, r8d
0x1400125f1  mov     rdx, rdi
0x1400125f4  mov     rcx, rsi
0x1400125f7  call    AfdNotifySockIndicateEventsUnlock
0x1400125fc  jmp     loc_14001248B
0x140075dc8  test    r8b, r8b
0x140075dcb  jz      short loc_140075E13
0x140075dcd  xor     r8d, r8d
0x140075dd0  mov     rcx, rsi
0x140075dd3  lea     r14d, [r8+4]
0x140075dd7  mov     edx, r14d
0x140075dda  call    AfdIndicateEventSelectEvent
0x140075ddf  xor     r8d, r8d
0x140075de2  mov     edx, r14d
0x140075de5  mov     rcx, rsi
0x140075de8  call    AfdNotifySockEventsChangedUnderLock
0x140075ded  xor     r8d, r8d
0x140075df0  mov     edx, r14d
0x140075df3  mov     r9, rdi
0x140075df6  call    AfdIndicatePollEvent
0x140075dfb  xor     ecx, ecx
0x140075dfd  test    al, al
0x140075dff  cmovnz  rdi, rcx
0x140075e03  xor     r8d, r8d
0x140075e06  mov     rdx, rdi
0x140075e09  mov     rcx, rsi
0x140075e0c  call    AfdNotifySockIndicateEventsUnlock
0x140075e11  jmp     short loc_140075E22
0x140075e13  mov     rcx, rdi; LockHandle
0x140075e16  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140075e1d  nop     dword ptr [rax+rax+00h]
0x140075e22  xor     edx, edx
0x140075e24  mov     rcx, rbx
0x140075e27  call    AfdDeleteConnectedReference
0x140075e2c  nop
0x140075e2d  jmp     loc_140012397
```
