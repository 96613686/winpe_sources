# WskProIRPSendTo

- ea: `0x140033170`
- end: `0x140033360`
- name: `WskProIRPSendTo`
- size: `496`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x140005b60`
- `0x140033170`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003332a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003332a`
- `ntoskrnl!IofCompleteRequest` at `0x140033205`
- `ntoskrnl!IofCompleteRequest` at `0x140033345`
- `ntoskrnl!IofCompleteRequest` at `0x140033205`
- `ntoskrnl!IofCompleteRequest` at `0x140033345`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400332cf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003331b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400332cf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14003331b`

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
0x140033170  push    rbp
0x140033172  push    rbx
0x140033173  push    rsi
0x140033174  push    rdi
0x140033175  lea     rbp, [rsp-3Fh]
0x14003317a  sub     rsp, 98h
0x140033181  mov     rdi, rdx
0x140033184  mov     rbx, rcx
0x140033187  xor     edx, edx; Val
0x140033189  lea     rcx, [rbp+57h+var_70]; void *
0x14003318d  lea     r8d, [rdx+48h]; Size
0x140033191  call    memset
0x140033196  mov     qword ptr [rbx+38h], 0
0x14003319e  xorps   xmm0, xmm0
0x1400331a1  mov     r8, [rdi+8]
0x1400331a5  mov     eax, 0ACE3h
0x1400331aa  movups  [rbp+57h+var_90], xmm0
0x1400331ae  movups  [rbp+57h+var_80], xmm0
0x1400331b2  cmp     [r8], ax
0x1400331b6  jz      short loc_1400331BF
0x1400331b8  mov     edi, 0C0000010h
0x1400331bd  jmp     short loc_1400331FD
0x1400331bf  cmp     byte ptr [r8+2], 1
0x1400331c4  jz      short loc_1400331CD
0x1400331c6  mov     edi, 0C0000184h
0x1400331cb  jmp     short loc_1400331FD
0x1400331cd  mov     r9, [rdi+10h]
0x1400331d1  test    r9, r9
0x1400331d4  jnz     short loc_1400331DD
0x1400331d6  mov     edi, 0C000000Dh
0x1400331db  jmp     short loc_1400331FD
0x1400331dd  mov     rdx, [rdi+18h]
0x1400331e1  test    rdx, rdx
0x1400331e4  jz      short loc_140033218
0x1400331e6  movzx   ecx, word ptr [rdx]; af
0x1400331e9  cmp     cx, 23h ; '#'
0x1400331ed  jnb     short loc_1400331F8
0x1400331ef  call    SOCKADDR_SIZE
0x1400331f4  cmp     al, 2
0x1400331f6  ja      short loc_140033218
0x1400331f8  mov     edi, 0C0000141h
0x1400331fd  xor     edx, edx; PriorityBoost
0x1400331ff  mov     [rbx+30h], edi
0x140033202  mov     rcx, rbx; Irp
0x140033205  call    cs:__imp_IofCompleteRequest
0x14003320c  nop     dword ptr [rax+rax+00h]
0x140033211  mov     eax, edi
0x140033213  jmp     loc_140033353
0x140033218  mov     rax, [r9]
0x14003321b  mov     qword ptr [rbp+57h+var_90+8], rax
0x14003321f  mov     eax, [r9+8]
0x140033223  mov     dword ptr [rbp+57h+var_80], eax
0x140033226  mov     rax, [r9+10h]
0x14003322a  mov     qword ptr [rbp+57h+var_80+8], rax
0x14003322e  lea     rax, WskProTLSendToComplete
0x140033235  mov     [rbp+57h+var_70], rax
0x140033239  lea     rax, [rbp+57h+var_90]
0x14003323d  mov     [rbp+57h+var_48], rax
0x140033241  mov     eax, [rdi+20h]
0x140033244  mov     [rbp+57h+var_38], eax
0x140033247  mov     rax, [rbx+80h]
0x14003324e  mov     [rbp+57h+var_50], rdx
0x140033252  lea     rdx, [rbp+57h+var_70]
0x140033256  mov     [rbp+57h+var_40], rax
0x14003325a  mov     [rbp+57h+var_68], rbx
0x14003325e  mov     [rbp+57h+var_58], rbx
0x140033262  mov     qword ptr [rbx+78h], 2
0x14003326a  mov     rax, [r8+38h]
0x14003326e  mov     rcx, [r8+28h]
0x140033272  mov     rax, [rax+18h]
0x140033276  call    _guard_dispatch_icall
0x14003327b  mov     esi, eax
0x14003327d  cmp     eax, 103h
0x140033282  jz      short loc_1400332A4
0x140033284  mov     r8, [rbp+57h+var_30]
0x140033288  mov     edx, eax
0x14003328a  mov     rax, [rbp+57h+var_70]
0x14003328e  mov     rcx, [rbp+57h+var_68]
0x140033292  mov     qword ptr [rbx+78h], 1
0x14003329a  call    _guard_dispatch_icall
0x14003329f  jmp     loc_140033351
0x1400332a4  mov     rax, [rbx+0B8h]
0x1400332ab  or      byte ptr [rax+3], 1
0x1400332af  lea     rax, WskProCANCELSendTo
0x1400332b6  xchg    rax, [rbx+68h]
0x1400332ba  cmp     byte ptr [rbx+44h], 0
0x1400332be  jz      short loc_1400332E8
0x1400332c0  xor     edi, edi
0x1400332c2  xchg    rdi, [rbx+68h]
0x1400332c6  test    rdi, rdi
0x1400332c9  jz      short loc_1400332E8
0x1400332cb  lea     rcx, [rbx+45h]; Irql
0x1400332cf  call    cs:__imp_IoAcquireCancelSpinLock
0x1400332d6  nop     dword ptr [rax+rax+00h]
0x1400332db  mov     rdx, rbx
0x1400332de  xor     ecx, ecx
0x1400332e0  mov     rax, rdi
0x1400332e3  call    _guard_dispatch_icall
0x1400332e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400332ec  lock xadd [rbx+78h], rax
0x1400332f2  sub     rax, 1
0x1400332f6  jg      short loc_140033351
0x1400332f8  test    rax, rax
0x1400332fb  jz      short loc_140033306
0x1400332fd  mov     ecx, 0Eh
0x140033302  int     29h; Win8: RtlFailFast(ecx)
0x140033304  jmp     short loc_140033351
0x140033306  xchg    rax, [rbx+68h]
0x14003330a  test    rax, rax
0x14003330d  jnz     short loc_140033336
0x14003330f  cmp     [rbx+44h], al
0x140033312  jz      short loc_140033336
0x140033314  lea     rcx, [rbp+57h+Irql]; Irql
0x140033318  mov     [rbp+57h+Irql], al
0x14003331b  call    cs:__imp_IoAcquireCancelSpinLock
0x140033322  nop     dword ptr [rax+rax+00h]
0x140033327  mov     cl, [rbp+57h+Irql]; Irql
0x14003332a  call    cs:__imp_IoReleaseCancelSpinLock
0x140033331  nop     dword ptr [rax+rax+00h]
0x140033336  mov     edx, [rbx+30h]
0x140033339  mov     rcx, rbx; Irp
0x14003333c  sar     edx, 1Fh
0x14003333f  and     dl, 0FEh
0x140033342  add     dl, 2; PriorityBoost
0x140033345  call    cs:__imp_IofCompleteRequest
0x14003334c  nop     dword ptr [rax+rax+00h]
0x140033351  mov     eax, esi
0x140033353  add     rsp, 98h
0x14003335a  pop     rdi
0x14003335b  pop     rsi
0x14003335c  pop     rbx
0x14003335d  pop     rbp
0x14003335e  retn
```
