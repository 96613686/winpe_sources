# WskProIRPSendMessages

- ea: `0x1400333d0`
- end: `0x140033593`
- name: `WskProIRPSendMessages`
- size: `451`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140032d90`

## callees

- `0x140005b60`
- `0x1400333d0`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033560`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033560`
- `ntoskrnl!IofCompleteRequest` at `0x140033455`
- `ntoskrnl!IofCompleteRequest` at `0x14003357b`
- `ntoskrnl!IofCompleteRequest` at `0x140033455`
- `ntoskrnl!IofCompleteRequest` at `0x14003357b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033505`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033551`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033505`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033551`

## pseudocode

```c
__int64 __fastcall WskProIRPSendMessages(PIRP Irp, __int64 a2)
{
  __int64 v4; // r8
  unsigned int v5; // edi
  __int64 v6; // r9
  ADDRESS_FAMILY *v7; // rdx
  unsigned int v9; // eax
  unsigned int v10; // esi
  __int64 v11; // r8
  __int64 v12; // rdx
  void (__fastcall *v13)(__int64, __int64, __int64); // rax
  __int64 v14; // rcx
  void (__fastcall *v15)(_QWORD, PIRP); // rdi
  signed __int64 v16; // rax
  bool v17; // cc
  signed __int64 v18; // rax
  _QWORD v19[11]; // [rsp+20h] [rbp-58h] BYREF
  KIRQL Irql; // [rsp+A0h] [rbp+28h] BYREF

  memset(v19, 0, 0x48u);
  Irp->IoStatus.Information = 0;
  v4 = *(_QWORD *)(a2 + 8);
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
  v19[4] = v7;
  v19[0] = WskProTLSendToComplete;
  LODWORD(v19[7]) = *(_DWORD *)(a2 + 32);
  v19[6] = Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink;
  v19[1] = Irp;
  v19[5] = v6;
  v19[3] = Irp;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)2;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)(v4 + 56) + 24LL))(*(_QWORD *)(v4 + 40), v19);
  v10 = v9;
  if ( v9 == 259 )
  {
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)WskProCANCELSendTo);
    if ( Irp->Cancel )
    {
      v15 = (void (__fastcall *)(_QWORD, PIRP))_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0);
      if ( v15 )
      {
        IoAcquireCancelSpinLock(&Irp->CancelIrql);
        v15(0, Irp);
      }
    }
    v16 = _InterlockedExchangeAdd64((volatile signed __int64 *)&Irp->Tail, 0xFFFFFFFFFFFFFFFFuLL);
    v17 = v16 <= 1;
    v18 = v16 - 1;
    if ( v17 )
    {
      if ( v18 )
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
    v11 = v19[8];
    v12 = v9;
    v13 = (void (__fastcall *)(__int64, __int64, __int64))v19[0];
    v14 = v19[1];
    Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)1;
    v13(v14, v12, v11);
  }
  return v10;
}

```

## disassembly

```asm
0x1400333d0  push    rbp
0x1400333d2  push    rbx
0x1400333d3  push    rsi
0x1400333d4  push    rdi
0x1400333d5  mov     rbp, rsp
0x1400333d8  sub     rsp, 78h
0x1400333dc  mov     rdi, rdx
0x1400333df  mov     rbx, rcx
0x1400333e2  xor     edx, edx; Val
0x1400333e4  lea     rcx, [rbp+var_58]; void *
0x1400333e8  lea     r8d, [rdx+48h]; Size
0x1400333ec  call    memset
0x1400333f1  mov     qword ptr [rbx+38h], 0
0x1400333f9  mov     eax, 0ACE3h
0x1400333fe  mov     r8, [rdi+8]
0x140033402  cmp     [r8], ax
0x140033406  jz      short loc_14003340F
0x140033408  mov     edi, 0C0000010h
0x14003340d  jmp     short loc_14003344D
0x14003340f  cmp     byte ptr [r8+2], 1
0x140033414  jz      short loc_14003341D
0x140033416  mov     edi, 0C0000184h
0x14003341b  jmp     short loc_14003344D
0x14003341d  mov     r9, [rdi+10h]
0x140033421  test    r9, r9
0x140033424  jnz     short loc_14003342D
0x140033426  mov     edi, 0C000000Dh
0x14003342b  jmp     short loc_14003344D
0x14003342d  mov     rdx, [rdi+18h]
0x140033431  test    rdx, rdx
0x140033434  jz      short loc_140033468
0x140033436  movzx   ecx, word ptr [rdx]; af
0x140033439  cmp     cx, 23h ; '#'
0x14003343d  jnb     short loc_140033448
0x14003343f  call    SOCKADDR_SIZE
0x140033444  cmp     al, 2
0x140033446  ja      short loc_140033468
0x140033448  mov     edi, 0C0000141h
0x14003344d  xor     edx, edx; PriorityBoost
0x14003344f  mov     [rbx+30h], edi
0x140033452  mov     rcx, rbx; Irp
0x140033455  call    cs:__imp_IofCompleteRequest
0x14003345c  nop     dword ptr [rax+rax+00h]
0x140033461  mov     eax, edi
0x140033463  jmp     loc_140033589
0x140033468  mov     [rbp+var_38], rdx
0x14003346c  lea     rax, WskProTLSendToComplete
0x140033473  mov     [rbp+var_58], rax
0x140033477  lea     rdx, [rbp+var_58]
0x14003347b  mov     eax, [rdi+20h]
0x14003347e  mov     [rbp+var_20], eax
0x140033481  mov     rax, [rbx+80h]
0x140033488  mov     [rbp+var_28], rax
0x14003348c  mov     [rbp+var_50], rbx
0x140033490  mov     [rbp+var_30], r9
0x140033494  mov     [rbp+var_40], rbx
0x140033498  mov     qword ptr [rbx+78h], 2
0x1400334a0  mov     rax, [r8+38h]
0x1400334a4  mov     rcx, [r8+28h]
0x1400334a8  mov     rax, [rax+18h]
0x1400334ac  call    _guard_dispatch_icall
0x1400334b1  mov     esi, eax
0x1400334b3  cmp     eax, 103h
0x1400334b8  jz      short loc_1400334DA
0x1400334ba  mov     r8, [rbp+var_18]
0x1400334be  mov     edx, eax
0x1400334c0  mov     rax, [rbp+var_58]
0x1400334c4  mov     rcx, [rbp+var_50]
0x1400334c8  mov     qword ptr [rbx+78h], 1
0x1400334d0  call    _guard_dispatch_icall
0x1400334d5  jmp     loc_140033587
0x1400334da  mov     rax, [rbx+0B8h]
0x1400334e1  or      byte ptr [rax+3], 1
0x1400334e5  lea     rax, WskProCANCELSendTo
0x1400334ec  xchg    rax, [rbx+68h]
0x1400334f0  cmp     byte ptr [rbx+44h], 0
0x1400334f4  jz      short loc_14003351E
0x1400334f6  xor     edi, edi
0x1400334f8  xchg    rdi, [rbx+68h]
0x1400334fc  test    rdi, rdi
0x1400334ff  jz      short loc_14003351E
0x140033501  lea     rcx, [rbx+45h]; Irql
0x140033505  call    cs:__imp_IoAcquireCancelSpinLock
0x14003350c  nop     dword ptr [rax+rax+00h]
0x140033511  mov     rdx, rbx
0x140033514  xor     ecx, ecx
0x140033516  mov     rax, rdi
0x140033519  call    _guard_dispatch_icall
0x14003351e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140033522  lock xadd [rbx+78h], rax
0x140033528  sub     rax, 1
0x14003352c  jg      short loc_140033587
0x14003352e  test    rax, rax
0x140033531  jz      short loc_14003353C
0x140033533  mov     ecx, 0Eh
0x140033538  int     29h; Win8: RtlFailFast(ecx)
0x14003353a  jmp     short loc_140033587
0x14003353c  xchg    rax, [rbx+68h]
0x140033540  test    rax, rax
0x140033543  jnz     short loc_14003356C
0x140033545  cmp     [rbx+44h], al
0x140033548  jz      short loc_14003356C
0x14003354a  lea     rcx, [rbp+Irql]; Irql
0x14003354e  mov     [rbp+Irql], al
0x140033551  call    cs:__imp_IoAcquireCancelSpinLock
0x140033558  nop     dword ptr [rax+rax+00h]
0x14003355d  mov     cl, [rbp+Irql]; Irql
0x140033560  call    cs:__imp_IoReleaseCancelSpinLock
0x140033567  nop     dword ptr [rax+rax+00h]
0x14003356c  mov     edx, [rbx+30h]
0x14003356f  mov     rcx, rbx; Irp
0x140033572  sar     edx, 1Fh
0x140033575  and     dl, 0FEh
0x140033578  add     dl, 2; PriorityBoost
0x14003357b  call    cs:__imp_IofCompleteRequest
0x140033582  nop     dword ptr [rax+rax+00h]
0x140033587  mov     eax, esi
0x140033589  add     rsp, 78h
0x14003358d  pop     rdi
0x14003358e  pop     rsi
0x14003358f  pop     rbx
0x140033590  pop     rbp
0x140033591  retn
```
