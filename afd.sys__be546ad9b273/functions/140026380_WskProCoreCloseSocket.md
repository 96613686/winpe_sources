# WskProCoreCloseSocket

- ea: `0x140026380`
- end: `0x1400265d5`
- name: `WskProCoreCloseSocket`
- size: `597`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140015ff0`
- `0x140026310`

## callees

- `0x140026380`
- `0x14005feb0`
- `0x140072920`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140078654`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400786e8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140078654`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400786e8`
- `ntoskrnl!IofCompleteRequest` at `0x140026534`
- `ntoskrnl!IofCompleteRequest` at `0x14007866c`
- `ntoskrnl!IofCompleteRequest` at `0x140026534`
- `ntoskrnl!IofCompleteRequest` at `0x14007866c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140078643`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400786d7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140078643`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400786d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026399`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400264bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026544`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026580`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007867c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026399`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400264bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026544`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140026580`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007867c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400263ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002649d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026570`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007861e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400786aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400263ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002649d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140026570`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007861e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400786aa`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400265ae`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400265ae`

## pseudocode

```c
void __fastcall WskProCoreCloseSocket(__int16 *a1)
{
  KIRQL v2; // al
  __int16 v3; // dx
  int v4; // ecx
  _QWORD *v5; // rdi
  _QWORD *v6; // r14
  __int64 v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rcx
  _QWORD **v10; // rdi
  _QWORD *v11; // rcx
  _QWORD *v12; // rdx
  _QWORD *v13; // rcx
  _QWORD *v14; // rdx
  _QWORD **v15; // rdi
  _QWORD *v16; // rbp
  _QWORD *v17; // rbp
  __int64 (__fastcall *v18)(PVOID); // [rsp+20h] [rbp-28h] BYREF
  __int16 *v19; // [rsp+28h] [rbp-20h]
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
  *((_DWORD *)a1 + 1) |= 8u;
  v3 = *a1;
  v4 = *((_DWORD *)a1 + 1);
  Irql = v2;
  switch ( v3 )
  {
    case -21278:
      if ( (v4 & 2) != 0 )
      {
        WskProCloseSocketWhileConnectInProgress(a1, &Irql);
        v2 = Irql;
      }
      if ( *((_QWORD *)a1 + 10) )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, v2);
        v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
      }
      break;
    case -21279:
      v10 = (_QWORD **)(a1 + 40);
      while ( 1 )
      {
        v11 = *v10;
        if ( *v10 == v10 )
          break;
        if ( (_QWORD **)v11[1] != v10 )
          goto LABEL_21;
        v12 = (_QWORD *)*v11;
        if ( *(_QWORD **)(*v11 + 8LL) != v11 )
          goto LABEL_21;
        *v10 = v12;
        v16 = v11 - 21;
        v12[1] = v10;
        *v11 = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, v2);
        if ( !_InterlockedExchange64(v16 + 13, 0) && *((_BYTE *)v16 + 68) )
        {
          Irql = 0;
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
        }
        *((_DWORD *)v16 + 12) = -1073741536;
        IofCompleteRequest((PIRP)v16, 0);
        v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
      }
      break;
    case -21277:
      v15 = (_QWORD **)(a1 + 40);
      while ( 1 )
      {
        v13 = *v15;
        if ( *v15 == v15 )
          break;
        if ( (_QWORD **)v13[1] != v15 || (v14 = (_QWORD *)*v13, *(_QWORD **)(*v13 + 8LL) != v13) )
LABEL_21:
          __fastfail(3u);
        *v15 = v14;
        v17 = v13 - 21;
        v14[1] = v15;
        *v13 = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, v2);
        if ( !_InterlockedExchange64(v17 + 13, 0) && *((_BYTE *)v17 + 68) )
        {
          Irql = 0;
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
        }
        *((_DWORD *)v17 + 12) = -1073741536;
        IofCompleteRequest((PIRP)v17, 0);
        v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
      }
      break;
    default:
      if ( v3 == -21276 && (v4 & 2) != 0 )
      {
        WskProCloseSocketWhileConnectInProgress(a1, &Irql);
        v2 = Irql;
      }
      break;
  }
  v5 = a1 + 60;
  while ( 1 )
  {
    v6 = (_QWORD *)*v5;
    if ( (_QWORD *)*v5 == v5 )
      break;
    if ( (_QWORD *)v6[1] != v5 )
      goto LABEL_21;
    v9 = *v6;
    if ( *(_QWORD **)(*v6 + 8LL) != v6 )
      goto LABEL_21;
    *v5 = v9;
    *(_QWORD *)(v9 + 8) = v5;
    *v6 = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, v2);
    ((void (__fastcall *)(__int16 *, _QWORD *))v6[2])(a1, v6);
    v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 2);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 2, v2);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 3, 0xFFFFFFFF) == 1 )
  {
    v7 = *((_QWORD *)a1 + 6);
    v18 = WskProTLCloseEndpointComplete;
    v19 = a1;
    _InterlockedAdd((volatile signed __int32 *)(v7 + 16), 2u);
    v8 = (**((__int64 (__fastcall ***)(_QWORD, __int64 (__fastcall **)(PVOID)))a1 + 7))(*((_QWORD *)a1 + 5), &v18);
    if ( (__int64 *)v7 != WskTdiTransport
      && _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 16), 0xFFFFFFFE) == 3 )
    {
      NmrClientDetachProviderComplete(*(HANDLE *)(v7 + 64));
    }
    if ( v8 != 259 )
      ((void (__fastcall *)(__int16 *, _QWORD))v18)(v19, v8);
  }
}

```

## disassembly

```asm
0x140026380  mov     [rsp+arg_8], rbx
0x140026385  mov     [rsp+arg_10], rbp
0x14002638a  push    rsi
0x14002638b  push    rdi
0x14002638c  push    r14
0x14002638e  sub     rsp, 30h
0x140026392  mov     rbx, rcx
0x140026395  add     rcx, 10h; SpinLock
0x140026399  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400263a0  nop     dword ptr [rax+rax+00h]
0x1400263a5  or      dword ptr [rbx+4], 8
0x1400263a9  mov     r8d, 0ACE2h
0x1400263af  movzx   edx, word ptr [rbx]
0x1400263b2  mov     ecx, [rbx+4]
0x1400263b5  mov     [rsp+48h+Irql], al
0x1400263b9  cmp     dx, r8w
0x1400263bd  jnz     loc_1400264CD
0x1400263c3  test    cl, 2
0x1400263c6  jnz     loc_140026552
0x1400263cc  cmp     qword ptr [rbx+50h], 0
0x1400263d1  jnz     loc_140026569
0x1400263d7  lea     rdi, [rbx+78h]
0x1400263db  mov     r14, [rdi]
0x1400263de  cmp     r14, rdi
0x1400263e1  jnz     loc_140026479
0x1400263e7  movzx   edx, al; NewIrql
0x1400263ea  lea     rcx, [rbx+10h]; SpinLock
0x1400263ee  call    cs:__imp_KeReleaseSpinLock
0x1400263f5  nop     dword ptr [rax+rax+00h]
0x1400263fa  mov     eax, 0FFFFFFFFh
0x1400263ff  lock xadd [rbx+0Ch], eax
0x140026404  cmp     eax, 1
0x140026407  jnz     short loc_140026465
0x140026409  mov     rdi, [rbx+30h]
0x14002640d  lea     rax, WskProTLCloseEndpointComplete
0x140026414  mov     [rsp+48h+var_28], rax
0x140026419  mov     [rsp+48h+var_20], rbx
0x14002641e  lock add dword ptr [rdi+10h], 2
0x140026423  mov     rax, [rbx+38h]
0x140026427  lea     rdx, [rsp+48h+var_28]
0x14002642c  mov     rcx, [rbx+28h]
0x140026430  mov     rax, [rax]
0x140026433  call    _guard_dispatch_icall
0x140026438  mov     ebx, eax
0x14002643a  lea     rax, WskTdiTransport
0x140026441  cmp     rdi, rax
0x140026444  jz      short loc_140026459
0x140026446  mov     edx, 0FFFFFFFEh
0x14002644b  lock xadd [rdi+10h], edx
0x140026450  cmp     edx, 3
0x140026453  jz      loc_1400265AA
0x140026459  cmp     ebx, 103h
0x14002645f  jnz     loc_1400265BF
0x140026465  mov     rbx, [rsp+48h+arg_8]
0x14002646a  mov     rbp, [rsp+48h+arg_10]
0x14002646f  add     rsp, 30h
0x140026473  pop     r14
0x140026475  pop     rdi
0x140026476  pop     rsi
0x140026477  retn
0x140026479  cmp     [r14+8], rdi
0x14002647d  jnz     short loc_1400264F3
0x14002647f  mov     rcx, [r14]
0x140026482  cmp     [rcx+8], r14
0x140026486  jnz     short loc_1400264F3
0x140026488  mov     [rdi], rcx
0x14002648b  movzx   edx, al; NewIrql
0x14002648e  mov     [rcx+8], rdi
0x140026492  lea     rcx, [rbx+10h]; SpinLock
0x140026496  mov     qword ptr [r14], 0
0x14002649d  call    cs:__imp_KeReleaseSpinLock
0x1400264a4  nop     dword ptr [rax+rax+00h]
0x1400264a9  mov     rax, [r14+10h]
0x1400264ad  mov     rdx, r14
0x1400264b0  mov     rcx, rbx
0x1400264b3  call    _guard_dispatch_icall
0x1400264b8  lea     rcx, [rbx+10h]; SpinLock
0x1400264bc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400264c3  nop     dword ptr [rax+rax+00h]
0x1400264c8  jmp     loc_1400263DB
0x1400264cd  mov     r8d, 0ACE1h
0x1400264d3  cmp     dx, r8w
0x1400264d7  jnz     loc_140026591
0x1400264dd  lea     rdi, [rbx+50h]
0x1400264e1  mov     rcx, [rdi]
0x1400264e4  cmp     rcx, rdi
0x1400264e7  jz      loc_1400263D7
0x1400264ed  cmp     [rcx+8], rdi
0x1400264f1  jz      short loc_1400264FA
0x1400264f3  mov     ecx, 3
0x1400264f8  int     29h; Win8: RtlFailFast(ecx)
0x1400264fa  mov     rdx, [rcx]
0x1400264fd  cmp     [rdx+8], rcx
0x140026501  jnz     short loc_1400264F3
0x140026503  jmp     loc_140078602
0x140026508  mov     rcx, [rdi]
0x14002650b  cmp     rcx, rdi
0x14002650e  jz      loc_1400263D7
0x140026514  cmp     [rcx+8], rdi
0x140026518  jnz     short loc_1400264F3
0x14002651a  mov     rdx, [rcx]
0x14002651d  cmp     [rdx+8], rcx
0x140026521  jnz     short loc_1400264F3
0x140026523  jmp     loc_14007868E
0x140026528  xor     edx, edx; PriorityBoost
0x14002652a  mov     dword ptr [rbp+30h], 0C0000120h
0x140026531  mov     rcx, rbp; Irp
0x140026534  call    cs:__imp_IofCompleteRequest
0x14002653b  nop     dword ptr [rax+rax+00h]
0x140026540  lea     rcx, [rbx+10h]; SpinLock
0x140026544  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002654b  nop     dword ptr [rax+rax+00h]
0x140026550  jmp     short loc_140026508
0x140026552  lea     rdx, [rsp+48h+Irql]
0x140026557  mov     rcx, rbx
0x14002655a  call    WskProCloseSocketWhileConnectInProgress
0x14002655f  movzx   eax, [rsp+48h+Irql]
0x140026564  jmp     loc_1400263CC
0x140026569  movzx   edx, al; NewIrql
0x14002656c  lea     rcx, [rbx+10h]; SpinLock
0x140026570  call    cs:__imp_KeReleaseSpinLock
0x140026577  nop     dword ptr [rax+rax+00h]
0x14002657c  lea     rcx, [rbx+10h]; SpinLock
0x140026580  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140026587  nop     dword ptr [rax+rax+00h]
0x14002658c  jmp     loc_1400263D7
0x140026591  mov     r8d, 0ACE3h
0x140026597  cmp     dx, r8w
0x14002659b  jnz     loc_1400786FA
0x1400265a1  lea     rdi, [rbx+50h]
0x1400265a5  jmp     loc_140026508
0x1400265aa  mov     rcx, [rdi+40h]; NmrBindingHandle
0x1400265ae  call    cs:__imp_NmrClientDetachProviderComplete
0x1400265b5  nop     dword ptr [rax+rax+00h]
0x1400265ba  jmp     loc_140026459
0x1400265bf  mov     rcx, [rsp+48h+var_20]
0x1400265c4  mov     edx, ebx
0x1400265c6  mov     rax, [rsp+48h+var_28]
0x1400265cb  call    _guard_dispatch_icall
0x1400265d0  jmp     loc_140026465
0x140078602  mov     [rdi], rdx
0x140078605  lea     rbp, [rcx-0A8h]
0x14007860c  mov     [rdx+8], rdi
0x140078610  movzx   edx, al; NewIrql
0x140078613  mov     qword ptr [rcx], 0
0x14007861a  lea     rcx, [rbx+10h]; SpinLock
0x14007861e  call    cs:__imp_KeReleaseSpinLock
0x140078625  nop     dword ptr [rax+rax+00h]
0x14007862a  xor     eax, eax
0x14007862c  xchg    rax, [rbp+68h]
0x140078630  test    rax, rax
0x140078633  jnz     short loc_140078660
0x140078635  cmp     [rbp+44h], al
0x140078638  jz      short loc_140078660
0x14007863a  lea     rcx, [rsp+48h+Irql]; Irql
0x14007863f  mov     [rsp+48h+Irql], al
0x140078643  call    cs:__imp_IoAcquireCancelSpinLock
0x14007864a  nop     dword ptr [rax+rax+00h]
0x14007864f  movzx   ecx, [rsp+48h+Irql]; Irql
0x140078654  call    cs:__imp_IoReleaseCancelSpinLock
0x14007865b  nop     dword ptr [rax+rax+00h]
0x140078660  xor     edx, edx; PriorityBoost
0x140078662  mov     dword ptr [rbp+30h], 0C0000120h
0x140078669  mov     rcx, rbp; Irp
0x14007866c  call    cs:__imp_IofCompleteRequest
0x140078673  nop     dword ptr [rax+rax+00h]
0x140078678  lea     rcx, [rbx+10h]; SpinLock
0x14007867c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140078683  nop     dword ptr [rax+rax+00h]
0x140078688  nop
0x140078689  jmp     loc_1400264E1
0x14007868e  mov     [rdi], rdx
0x140078691  lea     rbp, [rcx-0A8h]
0x140078698  mov     [rdx+8], rdi
0x14007869c  movzx   edx, al; NewIrql
0x14007869f  mov     qword ptr [rcx], 0
0x1400786a6  lea     rcx, [rbx+10h]; SpinLock
0x1400786aa  call    cs:__imp_KeReleaseSpinLock
0x1400786b1  nop     dword ptr [rax+rax+00h]
0x1400786b6  xor     eax, eax
0x1400786b8  xchg    rax, [rbp+68h]
0x1400786bc  test    rax, rax
0x1400786bf  jnz     loc_140026528
0x1400786c5  cmp     [rbp+44h], al
0x1400786c8  jz      loc_140026528
0x1400786ce  lea     rcx, [rsp+48h+Irql]; Irql
0x1400786d3  mov     [rsp+48h+Irql], al
0x1400786d7  call    cs:__imp_IoAcquireCancelSpinLock
0x1400786de  nop     dword ptr [rax+rax+00h]
0x1400786e3  movzx   ecx, [rsp+48h+Irql]; Irql
0x1400786e8  call    cs:__imp_IoReleaseCancelSpinLock
0x1400786ef  nop     dword ptr [rax+rax+00h]
0x1400786f4  nop
0x1400786f5  jmp     loc_140026528
0x1400786fa  mov     r8d, 0ACE4h
0x140078700  cmp     dx, r8w
0x140078704  jnz     loc_1400263D7
0x14007870a  test    cl, 2
0x14007870d  jz      loc_1400263D7
0x140078713  lea     rdx, [rsp+48h+Irql]
0x140078718  mov     rcx, rbx
0x14007871b  call    WskProCloseSocketWhileConnectInProgress
0x140078720  movzx   eax, [rsp+48h+Irql]
0x140078725  jmp     loc_1400263D7
```
