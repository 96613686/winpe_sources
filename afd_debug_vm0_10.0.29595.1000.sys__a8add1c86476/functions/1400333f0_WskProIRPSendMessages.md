# WskProIRPSendMessages

- ea: `0x1400333f0`
- end: `0x1400335b3`
- name: `WskProIRPSendMessages`
- size: `451`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140032db0`

## callees

- `0x140005b60`
- `0x1400333f0`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033580`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140033580`
- `ntoskrnl!IofCompleteRequest` at `0x140033475`
- `ntoskrnl!IofCompleteRequest` at `0x14003359b`
- `ntoskrnl!IofCompleteRequest` at `0x140033475`
- `ntoskrnl!IofCompleteRequest` at `0x14003359b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033525`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033571`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033525`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140033571`

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
0x1400333f0  push    rbp
0x1400333f2  push    rbx
0x1400333f3  push    rsi
0x1400333f4  push    rdi
0x1400333f5  mov     rbp, rsp
0x1400333f8  sub     rsp, 78h
0x1400333fc  mov     rdi, rdx
0x1400333ff  mov     rbx, rcx
0x140033402  xor     edx, edx; Val
0x140033404  lea     rcx, [rbp+var_58]; void *
0x140033408  lea     r8d, [rdx+48h]; Size
0x14003340c  call    memset
0x140033411  mov     qword ptr [rbx+38h], 0
0x140033419  mov     eax, 0ACE3h
0x14003341e  mov     r8, [rdi+8]
0x140033422  cmp     [r8], ax
0x140033426  jz      short loc_14003342F
0x140033428  mov     edi, 0C0000010h
0x14003342d  jmp     short loc_14003346D
0x14003342f  cmp     byte ptr [r8+2], 1
0x140033434  jz      short loc_14003343D
0x140033436  mov     edi, 0C0000184h
0x14003343b  jmp     short loc_14003346D
0x14003343d  mov     r9, [rdi+10h]
0x140033441  test    r9, r9
0x140033444  jnz     short loc_14003344D
0x140033446  mov     edi, 0C000000Dh
0x14003344b  jmp     short loc_14003346D
0x14003344d  mov     rdx, [rdi+18h]
0x140033451  test    rdx, rdx
0x140033454  jz      short loc_140033488
0x140033456  movzx   ecx, word ptr [rdx]; af
0x140033459  cmp     cx, 23h ; '#'
0x14003345d  jnb     short loc_140033468
0x14003345f  call    SOCKADDR_SIZE
0x140033464  cmp     al, 2
0x140033466  ja      short loc_140033488
0x140033468  mov     edi, 0C0000141h
0x14003346d  xor     edx, edx; PriorityBoost
0x14003346f  mov     [rbx+30h], edi
0x140033472  mov     rcx, rbx; Irp
0x140033475  call    cs:__imp_IofCompleteRequest
0x14003347c  nop     dword ptr [rax+rax+00h]
0x140033481  mov     eax, edi
0x140033483  jmp     loc_1400335A9
0x140033488  mov     [rbp+var_38], rdx
0x14003348c  lea     rax, WskProTLSendToComplete
0x140033493  mov     [rbp+var_58], rax
0x140033497  lea     rdx, [rbp+var_58]
0x14003349b  mov     eax, [rdi+20h]
0x14003349e  mov     [rbp+var_20], eax
0x1400334a1  mov     rax, [rbx+80h]
0x1400334a8  mov     [rbp+var_28], rax
0x1400334ac  mov     [rbp+var_50], rbx
0x1400334b0  mov     [rbp+var_30], r9
0x1400334b4  mov     [rbp+var_40], rbx
0x1400334b8  mov     qword ptr [rbx+78h], 2
0x1400334c0  mov     rax, [r8+38h]
0x1400334c4  mov     rcx, [r8+28h]
0x1400334c8  mov     rax, [rax+18h]
0x1400334cc  call    _guard_dispatch_icall
0x1400334d1  mov     esi, eax
0x1400334d3  cmp     eax, 103h
0x1400334d8  jz      short loc_1400334FA
0x1400334da  mov     r8, [rbp+var_18]
0x1400334de  mov     edx, eax
0x1400334e0  mov     rax, [rbp+var_58]
0x1400334e4  mov     rcx, [rbp+var_50]
0x1400334e8  mov     qword ptr [rbx+78h], 1
0x1400334f0  call    _guard_dispatch_icall
0x1400334f5  jmp     loc_1400335A7
0x1400334fa  mov     rax, [rbx+0B8h]
0x140033501  or      byte ptr [rax+3], 1
0x140033505  lea     rax, WskProCANCELSendTo
0x14003350c  xchg    rax, [rbx+68h]
0x140033510  cmp     byte ptr [rbx+44h], 0
0x140033514  jz      short loc_14003353E
0x140033516  xor     edi, edi
0x140033518  xchg    rdi, [rbx+68h]
0x14003351c  test    rdi, rdi
0x14003351f  jz      short loc_14003353E
0x140033521  lea     rcx, [rbx+45h]; Irql
0x140033525  call    cs:__imp_IoAcquireCancelSpinLock
0x14003352c  nop     dword ptr [rax+rax+00h]
0x140033531  mov     rdx, rbx
0x140033534  xor     ecx, ecx
0x140033536  mov     rax, rdi
0x140033539  call    _guard_dispatch_icall
0x14003353e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140033542  lock xadd [rbx+78h], rax
0x140033548  sub     rax, 1
0x14003354c  jg      short loc_1400335A7
0x14003354e  test    rax, rax
0x140033551  jz      short loc_14003355C
0x140033553  mov     ecx, 0Eh
0x140033558  int     29h; Win8: RtlFailFast(ecx)
0x14003355a  jmp     short loc_1400335A7
0x14003355c  xchg    rax, [rbx+68h]
0x140033560  test    rax, rax
0x140033563  jnz     short loc_14003358C
0x140033565  cmp     [rbx+44h], al
0x140033568  jz      short loc_14003358C
0x14003356a  lea     rcx, [rbp+Irql]; Irql
0x14003356e  mov     [rbp+Irql], al
0x140033571  call    cs:__imp_IoAcquireCancelSpinLock
0x140033578  nop     dword ptr [rax+rax+00h]
0x14003357d  mov     cl, [rbp+Irql]; Irql
0x140033580  call    cs:__imp_IoReleaseCancelSpinLock
0x140033587  nop     dword ptr [rax+rax+00h]
0x14003358c  mov     edx, [rbx+30h]
0x14003358f  mov     rcx, rbx; Irp
0x140033592  sar     edx, 1Fh
0x140033595  and     dl, 0FEh
0x140033598  add     dl, 2; PriorityBoost
0x14003359b  call    cs:__imp_IofCompleteRequest
0x1400335a2  nop     dword ptr [rax+rax+00h]
0x1400335a7  mov     eax, esi
0x1400335a9  add     rsp, 78h
0x1400335ad  pop     rdi
0x1400335ae  pop     rsi
0x1400335af  pop     rbx
0x1400335b0  pop     rbp
0x1400335b1  retn
```
