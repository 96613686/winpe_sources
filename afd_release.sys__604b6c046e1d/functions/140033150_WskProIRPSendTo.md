# WskProIRPSendTo

- ea: `0x140033150`
- end: `0x140033340`
- name: `WskProIRPSendTo`
- size: `496`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140005b60`
- `0x140033150`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003330a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003330a`
- `ntoskrnl!IofCompleteRequest` at `0x1400331e5`
- `ntoskrnl!IofCompleteRequest` at `0x140033325`
- `ntoskrnl!IofCompleteRequest` at `0x1400331e5`
- `ntoskrnl!IofCompleteRequest` at `0x140033325`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400332af`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400332fb`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400332af`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400332fb`

## pseudocode

```c
__int64 __fastcall WskProIRPSendTo(PIRP Irp, __int64 a2)
{
  __int64 v4; // r8
  unsigned int v5; // edi
  __int64 v6; // r9
  ADDRESS_FAMILY *v7; // rdx
  struct _LIST_ENTRY *Blink; // rax
  unsigned int v10; // eax
  unsigned int v11; // esi
  __int64 v12; // r8
  __int64 v13; // rdx
  void (__fastcall *v14)(__int64, __int64, __int64); // rax
  __int64 v15; // rcx
  void (__fastcall *v16)(_QWORD, PIRP); // rdi
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  __int128 v20; // [rsp+20h] [rbp-39h] BYREF
  __int128 v21; // [rsp+30h] [rbp-29h]
  _QWORD v22[14]; // [rsp+40h] [rbp-19h] BYREF
  KIRQL Irql; // [rsp+C0h] [rbp+67h] BYREF

  memset(v22, 0, 0x48u);
  Irp->IoStatus.Information = 0;
  v4 = *(_QWORD *)(a2 + 8);
  v20 = 0;
  v21 = 0;
  if ( *(_WORD *)v4 != 0xACE3 )
  {
    v5 = -1073741808;
LABEL_11:
    Irp->IoStatus.Status = v5;
    IofCompleteRequest(Irp, 0);
    return v5;
  }
  if ( *(_BYTE *)(v4 + 2) != 1 )
  {
    v5 = -1073741436;
    goto LABEL_11;
  }
  v6 = *(_QWORD *)(a2 + 16);
  if ( !v6 )
  {
    v5 = -1073741811;
    goto LABEL_11;
  }
  v7 = *(ADDRESS_FAMILY **)(a2 + 24);
  if ( v7 && (*v7 >= 0x23u || SOCKADDR_SIZE(*v7) <= 2u) )
  {
    v5 = -1073741503;
    goto LABEL_11;
  }
  *((_QWORD *)&v20 + 1) = *(_QWORD *)v6;
  LODWORD(v21) = *(_DWORD *)(v6 + 8);
  *((_QWORD *)&v21 + 1) = *(_QWORD *)(v6 + 16);
  v22[0] = WskProTLSendToComplete;
  v22[5] = &v20;
  LODWORD(v22[7]) = *(_DWORD *)(a2 + 32);
  Blink = Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
  v22[4] = v7;
  v22[6] = Blink;
  v22[1] = Irp;
  v22[3] = Irp;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)2;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v4 + 56) + 24LL))(*(_QWORD *)(v4 + 40), v22);
  v11 = v10;
  if ( v10 == 259 )
  {
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)WskProCANCELSendTo);
    if ( Irp->Cancel )
    {
      v16 = (void (__fastcall *)(_QWORD, PIRP))_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0);
      if ( v16 )
      {
        IoAcquireCancelSpinLock(&Irp->CancelIrql);
        v16(0, Irp);
      }
    }
    v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)&Irp->Tail, 0xFFFFFFFFFFFFFFFFuLL);
    v18 = v17 <= 1;
    v19 = v17 - 1;
    if ( v18 )
    {
      if ( v19 )
        __fastfail(0xEu);
      if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      {
        if ( Irp->Cancel )
        {
          Irql = 0;
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
        }
      }
      IofCompleteRequest(Irp, ((Irp->IoStatus.Status >> 31) & 0xFE) + 2);
    }
  }
  else
  {
    v12 = v22[8];
    v13 = v10;
    v14 = (void (__fastcall *)(__int64, __int64, __int64))v22[0];
    v15 = v22[1];
    Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)1;
    v14(v15, v13, v12);
  }
  return v11;
}

```

## disassembly

```asm
0x140033150  push    rbp
0x140033152  push    rbx
0x140033153  push    rsi
0x140033154  push    rdi
0x140033155  lea     rbp, [rsp-3Fh]
0x14003315a  sub     rsp, 98h
0x140033161  mov     rdi, rdx
0x140033164  mov     rbx, rcx
0x140033167  xor     edx, edx; Val
0x140033169  lea     rcx, [rbp+57h+var_70]; void *
0x14003316d  lea     r8d, [rdx+48h]; Size
0x140033171  call    memset
0x140033176  mov     qword ptr [rbx+38h], 0
0x14003317e  xorps   xmm0, xmm0
0x140033181  mov     r8, [rdi+8]
0x140033185  mov     eax, 0ACE3h
0x14003318a  movups  [rbp+57h+var_90], xmm0
0x14003318e  movups  [rbp+57h+var_80], xmm0
0x140033192  cmp     [r8], ax
0x140033196  jz      short loc_14003319F
0x140033198  mov     edi, 0C0000010h
0x14003319d  jmp     short loc_1400331DD
0x14003319f  cmp     byte ptr [r8+2], 1
0x1400331a4  jz      short loc_1400331AD
0x1400331a6  mov     edi, 0C0000184h
0x1400331ab  jmp     short loc_1400331DD
0x1400331ad  mov     r9, [rdi+10h]
0x1400331b1  test    r9, r9
0x1400331b4  jnz     short loc_1400331BD
0x1400331b6  mov     edi, 0C000000Dh
0x1400331bb  jmp     short loc_1400331DD
0x1400331bd  mov     rdx, [rdi+18h]
0x1400331c1  test    rdx, rdx
0x1400331c4  jz      short loc_1400331F8
0x1400331c6  movzx   ecx, word ptr [rdx]; af
0x1400331c9  cmp     cx, 23h ; '#'
0x1400331cd  jnb     short loc_1400331D8
0x1400331cf  call    SOCKADDR_SIZE
0x1400331d4  cmp     al, 2
0x1400331d6  ja      short loc_1400331F8
0x1400331d8  mov     edi, 0C0000141h
0x1400331dd  xor     edx, edx; PriorityBoost
0x1400331df  mov     [rbx+30h], edi
0x1400331e2  mov     rcx, rbx; Irp
0x1400331e5  call    cs:__imp_IofCompleteRequest
0x1400331ec  nop     dword ptr [rax+rax+00h]
0x1400331f1  mov     eax, edi
0x1400331f3  jmp     loc_140033333
0x1400331f8  mov     rax, [r9]
0x1400331fb  mov     qword ptr [rbp+57h+var_90+8], rax
0x1400331ff  mov     eax, [r9+8]
0x140033203  mov     dword ptr [rbp+57h+var_80], eax
0x140033206  mov     rax, [r9+10h]
0x14003320a  mov     qword ptr [rbp+57h+var_80+8], rax
0x14003320e  lea     rax, WskProTLSendToComplete
0x140033215  mov     [rbp+57h+var_70], rax
0x140033219  lea     rax, [rbp+57h+var_90]
0x14003321d  mov     [rbp+57h+var_48], rax
0x140033221  mov     eax, [rdi+20h]
0x140033224  mov     [rbp+57h+var_38], eax
0x140033227  mov     rax, [rbx+80h]
0x14003322e  mov     [rbp+57h+var_50], rdx
0x140033232  lea     rdx, [rbp+57h+var_70]
0x140033236  mov     [rbp+57h+var_40], rax
0x14003323a  mov     [rbp+57h+var_68], rbx
0x14003323e  mov     [rbp+57h+var_58], rbx
0x140033242  mov     qword ptr [rbx+78h], 2
0x14003324a  mov     rax, [r8+38h]
0x14003324e  mov     rcx, [r8+28h]
0x140033252  mov     rax, [rax+18h]
0x140033256  call    _guard_dispatch_icall
0x14003325b  mov     esi, eax
0x14003325d  cmp     eax, 103h
0x140033262  jz      short loc_140033284
0x140033264  mov     r8, [rbp+57h+var_30]
0x140033268  mov     edx, eax
0x14003326a  mov     rax, [rbp+57h+var_70]
0x14003326e  mov     rcx, [rbp+57h+var_68]
0x140033272  mov     qword ptr [rbx+78h], 1
0x14003327a  call    _guard_dispatch_icall
0x14003327f  jmp     loc_140033331
0x140033284  mov     rax, [rbx+0B8h]
0x14003328b  or      byte ptr [rax+3], 1
0x14003328f  lea     rax, WskProCANCELSendTo
0x140033296  xchg    rax, [rbx+68h]
0x14003329a  cmp     byte ptr [rbx+44h], 0
0x14003329e  jz      short loc_1400332C8
0x1400332a0  xor     edi, edi
0x1400332a2  xchg    rdi, [rbx+68h]
0x1400332a6  test    rdi, rdi
0x1400332a9  jz      short loc_1400332C8
0x1400332ab  lea     rcx, [rbx+45h]; Irql
0x1400332af  call    cs:__imp_IoAcquireCancelSpinLock
0x1400332b6  nop     dword ptr [rax+rax+00h]
0x1400332bb  mov     rdx, rbx
0x1400332be  xor     ecx, ecx
0x1400332c0  mov     rax, rdi
0x1400332c3  call    _guard_dispatch_icall
0x1400332c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400332cc  lock xadd [rbx+78h], rax
0x1400332d2  sub     rax, 1
0x1400332d6  jg      short loc_140033331
0x1400332d8  test    rax, rax
0x1400332db  jz      short loc_1400332E6
0x1400332dd  mov     ecx, 0Eh
0x1400332e2  int     29h; Win8: RtlFailFast(ecx)
0x1400332e4  jmp     short loc_140033331
0x1400332e6  xchg    rax, [rbx+68h]
0x1400332ea  test    rax, rax
0x1400332ed  jnz     short loc_140033316
0x1400332ef  cmp     [rbx+44h], al
0x1400332f2  jz      short loc_140033316
0x1400332f4  lea     rcx, [rbp+57h+Irql]; Irql
0x1400332f8  mov     [rbp+57h+Irql], al
0x1400332fb  call    cs:__imp_IoAcquireCancelSpinLock
0x140033302  nop     dword ptr [rax+rax+00h]
0x140033307  mov     cl, [rbp+57h+Irql]; Irql
0x14003330a  call    cs:__imp_IoReleaseCancelSpinLock
0x140033311  nop     dword ptr [rax+rax+00h]
0x140033316  mov     edx, [rbx+30h]
0x140033319  mov     rcx, rbx; Irp
0x14003331c  sar     edx, 1Fh
0x14003331f  and     dl, 0FEh
0x140033322  add     dl, 2; PriorityBoost
0x140033325  call    cs:__imp_IofCompleteRequest
0x14003332c  nop     dword ptr [rax+rax+00h]
0x140033331  mov     eax, esi
0x140033333  add     rsp, 98h
0x14003333a  pop     rdi
0x14003333b  pop     rsi
0x14003333c  pop     rbx
0x14003333d  pop     rbp
0x14003333e  retn
```
