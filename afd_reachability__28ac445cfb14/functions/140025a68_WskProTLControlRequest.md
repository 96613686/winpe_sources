# WskProTLControlRequest

- ea: `0x140025a68`
- end: `0x140025cd4`
- name: `WskProTLControlRequest`
- size: `620`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, int, PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140025720`

## callees

- `0x140025a68`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140025c9a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140025c9a`
- `ntoskrnl!IofCompleteRequest` at `0x140025bed`
- `ntoskrnl!IofCompleteRequest` at `0x140025cb5`
- `ntoskrnl!IofCompleteRequest` at `0x140025bed`
- `ntoskrnl!IofCompleteRequest` at `0x140025cb5`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140025c36`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140025c88`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140025c36`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140025c88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025b29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025ba0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025b29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140025ba0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025b3f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025bbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025bd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025b3f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025bbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140025bd4`

## pseudocode

```c
__int64 __fastcall WskProTLControlRequest(
        __int64 a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        PIRP Irp)
{
  PIRP v14; // rdi
  char v16; // al
  char v17; // bl
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // r14d
  KIRQL v21; // al
  __int64 v22; // r8
  __int64 v23; // rcx
  void (__fastcall *v24)(__int64, _QWORD, __int64); // rax
  KIRQL v25; // al
  int v26; // edx
  KSPIN_LOCK *v27; // rcx
  void (__fastcall *v28)(_QWORD, PIRP); // rbx
  signed __int64 v29; // rax
  bool v30; // cc
  signed __int64 v31; // rax
  _QWORD v32[10]; // [rsp+20h] [rbp-50h] BYREF

  memset(v32, 0, sizeof(v32));
  v14 = Irp;
  if ( !Irp )
    return 3221225485LL;
  v16 = *(_BYTE *)(a1 + 2);
  if ( v16 )
  {
    v17 = 0;
    if ( v16 != 1 || ((*(_WORD *)a1 + 21278) & 0xFFFD) != 0 )
      goto LABEL_6;
  }
  else if ( *(_WORD *)a1 == 0xACE0 )
  {
    v17 = 0;
    goto LABEL_6;
  }
  v25 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
  v26 = *(_DWORD *)(a1 + 4);
  v27 = (KSPIN_LOCK *)(a1 + 16);
  if ( (v26 & 7) != 0 )
  {
    KeReleaseSpinLock(v27, v25);
    v14->IoStatus.Status = -1073741436;
    IofCompleteRequest(v14, 0);
    return 3221225860LL;
  }
  *(_DWORD *)(a1 + 4) = v26 | 4;
  KeReleaseSpinLock(v27, v25);
  v17 = 1;
LABEL_6:
  v18 = *(_QWORD *)(a1 + 56);
  v19 = *(_QWORD *)(a1 + 40);
  v32[0] = WskProTLControlRequestCompletion;
  v32[4] = a6;
  v32[5] = a5;
  v32[6] = a8;
  v32[7] = a7;
  v32[1] = v14;
  v32[2] = __PAIR64__(a4, a2);
  LODWORD(v32[3]) = a3;
  v14->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)2;
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(v18 + 8))(v19, v32);
  if ( v17 )
  {
    v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
    *(_DWORD *)(a1 + 4) &= ~4u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v21);
  }
  if ( v20 == 259 )
  {
    v14->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v14->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)v32[8];
    _InterlockedExchange64((volatile __int64 *)&v14->CancelRoutine, (__int64)WskProCANCELTLGeneric);
    if ( v14->Cancel )
    {
      v28 = (void (__fastcall *)(_QWORD, PIRP))_InterlockedExchange64((volatile __int64 *)&v14->CancelRoutine, 0);
      if ( v28 )
      {
        IoAcquireCancelSpinLock(&v14->CancelIrql);
        v28(0, v14);
      }
    }
    v29 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v14->Tail, 0xFFFFFFFFFFFFFFFFuLL);
    v30 = v29 <= 1;
    v31 = v29 - 1;
    if ( v30 )
    {
      if ( v31 )
        __fastfail(0xEu);
      if ( !_InterlockedExchange64((volatile __int64 *)&v14->CancelRoutine, 0) )
      {
        if ( v14->Cancel )
        {
          LOBYTE(Irp) = 0;
          IoAcquireCancelSpinLock((PKIRQL)&Irp);
          IoReleaseCancelSpinLock((KIRQL)Irp);
        }
      }
      IofCompleteRequest(v14, ((v14->IoStatus.Status >> 31) & 0xFE) + 2);
    }
  }
  else
  {
    v22 = v32[9];
    v23 = v32[1];
    v24 = (void (__fastcall *)(__int64, _QWORD, __int64))v32[0];
    v14->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)1;
    v24(v23, v20, v22);
  }
  return v20;
}

```

## disassembly

```asm
0x140025a68  push    rbp
0x140025a6a  push    rbx
0x140025a6b  push    rsi
0x140025a6c  push    rdi
0x140025a6d  push    r12
0x140025a6f  push    r14
0x140025a71  push    r15
0x140025a73  mov     rbp, rsp
0x140025a76  sub     rsp, 70h
0x140025a7a  mov     r12d, edx
0x140025a7d  mov     r15d, r8d
0x140025a80  xor     edx, edx; Val
0x140025a82  mov     rsi, rcx
0x140025a85  lea     rcx, [rbp+var_50]; void *
0x140025a89  mov     r14d, r9d
0x140025a8c  lea     r8d, [rdx+50h]; Size
0x140025a90  call    memset
0x140025a95  mov     rdi, [rbp+Irp]
0x140025a9c  test    rdi, rdi
0x140025a9f  jnz     short loc_140025AAB
0x140025aa1  mov     eax, 0C000000Dh
0x140025aa6  jmp     loc_140025CC4
0x140025aab  mov     al, [rsi+2]
0x140025aae  test    al, al
0x140025ab0  jnz     loc_140025B79
0x140025ab6  mov     eax, 0ACE0h
0x140025abb  cmp     [rsi], ax
0x140025abe  jnz     loc_140025B99
0x140025ac4  xor     bl, bl
0x140025ac6  mov     rdx, [rsi+38h]
0x140025aca  lea     rax, WskProTLControlRequestCompletion
0x140025ad1  mov     rcx, [rsi+28h]
0x140025ad5  mov     [rbp+var_50], rax
0x140025ad9  mov     rax, [rbp+arg_28]
0x140025add  mov     [rbp+var_30], rax
0x140025ae1  mov     rax, [rbp+arg_20]
0x140025ae5  mov     [rbp+var_28], rax
0x140025ae9  mov     rax, [rbp+arg_38]
0x140025aed  mov     [rbp+var_20], rax
0x140025af1  mov     rax, [rbp+arg_30]
0x140025af5  mov     [rbp+var_18], rax
0x140025af9  mov     [rbp+var_48], rdi
0x140025afd  mov     [rbp+var_40], r12d
0x140025b01  mov     [rbp+var_3C], r14d
0x140025b05  mov     [rbp+var_38], r15d
0x140025b09  mov     qword ptr [rdi+78h], 2
0x140025b11  mov     rax, [rdx+8]
0x140025b15  lea     rdx, [rbp+var_50]
0x140025b19  call    _guard_dispatch_icall
0x140025b1e  mov     r14d, eax
0x140025b21  test    bl, bl
0x140025b23  jz      short loc_140025B4B
0x140025b25  lea     rcx, [rsi+10h]; SpinLock
0x140025b29  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025b30  nop     dword ptr [rax+rax+00h]
0x140025b35  and     dword ptr [rsi+4], 0FFFFFFFBh
0x140025b39  lea     rcx, [rsi+10h]; SpinLock
0x140025b3d  mov     dl, al; NewIrql
0x140025b3f  call    cs:__imp_KeReleaseSpinLock
0x140025b46  nop     dword ptr [rax+rax+00h]
0x140025b4b  cmp     r14d, 103h
0x140025b52  jz      loc_140025C00
0x140025b58  mov     r8, [rbp+var_8]
0x140025b5c  mov     edx, r14d
0x140025b5f  mov     rcx, [rbp+var_48]
0x140025b63  mov     rax, [rbp+var_50]
0x140025b67  mov     qword ptr [rdi+78h], 1
0x140025b6f  call    _guard_dispatch_icall
0x140025b74  jmp     loc_140025CC1
0x140025b79  xor     bl, bl
0x140025b7b  cmp     al, 1
0x140025b7d  jnz     loc_140025AC6
0x140025b83  mov     eax, 531Eh
0x140025b88  mov     ecx, 0FFFDh
0x140025b8d  add     ax, [rsi]
0x140025b90  test    cx, ax
0x140025b93  jnz     loc_140025AC6
0x140025b99  lea     rbx, [rsi+10h]
0x140025b9d  mov     rcx, rbx; SpinLock
0x140025ba0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140025ba7  nop     dword ptr [rax+rax+00h]
0x140025bac  mov     edx, [rsi+4]
0x140025baf  mov     rcx, rbx; SpinLock
0x140025bb2  test    dl, 7
0x140025bb5  jnz     short loc_140025BD2
0x140025bb7  or      edx, 4
0x140025bba  mov     [rsi+4], edx
0x140025bbd  mov     dl, al; NewIrql
0x140025bbf  call    cs:__imp_KeReleaseSpinLock
0x140025bc6  nop     dword ptr [rax+rax+00h]
0x140025bcb  mov     bl, 1
0x140025bcd  jmp     loc_140025AC6
0x140025bd2  mov     dl, al; NewIrql
0x140025bd4  call    cs:__imp_KeReleaseSpinLock
0x140025bdb  nop     dword ptr [rax+rax+00h]
0x140025be0  mov     ebx, 0C0000184h
0x140025be5  xor     edx, edx; PriorityBoost
0x140025be7  mov     rcx, rdi; Irp
0x140025bea  mov     [rdi+30h], ebx
0x140025bed  call    cs:__imp_IofCompleteRequest
0x140025bf4  nop     dword ptr [rax+rax+00h]
0x140025bf9  mov     eax, ebx
0x140025bfb  jmp     loc_140025CC4
0x140025c00  mov     rax, [rdi+0B8h]
0x140025c07  or      byte ptr [rax+3], 1
0x140025c0b  mov     rax, [rbp+var_10]
0x140025c0f  mov     [rdi+80h], rax
0x140025c16  lea     rax, WskProCANCELTLGeneric
0x140025c1d  xchg    rax, [rdi+68h]
0x140025c21  cmp     byte ptr [rdi+44h], 0
0x140025c25  jz      short loc_140025C4F
0x140025c27  xor     ebx, ebx
0x140025c29  xchg    rbx, [rdi+68h]
0x140025c2d  test    rbx, rbx
0x140025c30  jz      short loc_140025C4F
0x140025c32  lea     rcx, [rdi+45h]; Irql
0x140025c36  call    cs:__imp_IoAcquireCancelSpinLock
0x140025c3d  nop     dword ptr [rax+rax+00h]
0x140025c42  mov     rdx, rdi
0x140025c45  xor     ecx, ecx
0x140025c47  mov     rax, rbx
0x140025c4a  call    _guard_dispatch_icall
0x140025c4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025c53  lock xadd [rdi+78h], rax
0x140025c59  sub     rax, 1
0x140025c5d  jg      short loc_140025CC1
0x140025c5f  test    rax, rax
0x140025c62  jz      short loc_140025C6D
0x140025c64  mov     ecx, 0Eh
0x140025c69  int     29h; Win8: RtlFailFast(ecx)
0x140025c6b  jmp     short loc_140025CC1
0x140025c6d  xchg    rax, [rdi+68h]
0x140025c71  test    rax, rax
0x140025c74  jnz     short loc_140025CA6
0x140025c76  cmp     [rdi+44h], al
0x140025c79  jz      short loc_140025CA6
0x140025c7b  lea     rcx, [rbp+Irp]; Irql
0x140025c82  mov     byte ptr [rbp+Irp], al
0x140025c88  call    cs:__imp_IoAcquireCancelSpinLock
0x140025c8f  nop     dword ptr [rax+rax+00h]
0x140025c94  mov     cl, byte ptr [rbp+Irp]; Irql
0x140025c9a  call    cs:__imp_IoReleaseCancelSpinLock
0x140025ca1  nop     dword ptr [rax+rax+00h]
0x140025ca6  mov     edx, [rdi+30h]
0x140025ca9  mov     rcx, rdi; Irp
0x140025cac  sar     edx, 1Fh
0x140025caf  and     dl, 0FEh
0x140025cb2  add     dl, 2; PriorityBoost
0x140025cb5  call    cs:__imp_IofCompleteRequest
0x140025cbc  nop     dword ptr [rax+rax+00h]
0x140025cc1  mov     eax, r14d
0x140025cc4  add     rsp, 70h
0x140025cc8  pop     r15
0x140025cca  pop     r14
0x140025ccc  pop     r12
0x140025cce  pop     rdi
0x140025ccf  pop     rsi
0x140025cd0  pop     rbx
0x140025cd1  pop     rbp
0x140025cd2  retn
```
