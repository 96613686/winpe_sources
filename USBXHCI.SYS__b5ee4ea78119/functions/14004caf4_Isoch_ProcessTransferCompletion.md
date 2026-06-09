# Isoch_ProcessTransferCompletion

- ea: `0x14004caf4`
- end: `0x14004cca6`
- name: `Isoch_ProcessTransferCompletion`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004ccb0`
- `0x14004cf70`

## callees

- `0x140002568`
- `0x14000cb4c`
- `0x140027fcc`
- `0x14003c698`
- `0x14004caf4`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004cb64`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cbc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cc27`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cb64`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cbc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004cc27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cb47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cbe0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cb47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004cbe0`

## pseudocode

```c
void __fastcall Isoch_ProcessTransferCompletion(__int64 a1)
{
  __int64 v1; // rbx
  KIRQL v2; // al
  bool v3; // zf
  char v4; // bp
  __int64 v5; // rdi
  KIRQL v6; // al
  __int64 v7; // r8
  __int64 v8; // rdx
  int v9; // edx
  int v10; // edx
  _OWORD v11[3]; // [rsp+40h] [rbp-38h] BYREF

  v11[0] = 0;
  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C270);
  *((_QWORD *)&v11[0] + 1) = v11;
  *(_QWORD *)&v11[0] = v11;
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  v3 = *(_BYTE *)(v1 + 340) == 0;
  *(_BYTE *)(v1 + 104) = v2;
  if ( v3 )
  {
    v4 = 0;
    *(_BYTE *)(v1 + 340) = 1;
    v5 = v1 + 424;
    do
    {
      if ( *(_QWORD *)v5 != v5 )
      {
        **((_QWORD **)&v11[0] + 1) = *(_QWORD *)v5;
        *(_QWORD *)(*(_QWORD *)v5 + 8LL) = *((_QWORD *)&v11[0] + 1);
        **(_QWORD **)(v1 + 432) = v11;
        *((_QWORD *)&v11[0] + 1) = *(_QWORD *)(v1 + 432);
        *(_QWORD *)(v1 + 432) = v1 + 424;
        *(_QWORD *)v5 = v5;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), *(_BYTE *)(v1 + 104));
      Isoch_CompleteTransfers(v1, v11);
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
      *(_BYTE *)(v1 + 104) = v6;
      LOBYTE(v7) = v6;
    }
    while ( *(_QWORD *)v5 != v5 );
    v8 = *(unsigned int *)(v1 + 336);
    if ( (v8 & 8) != 0 && !(unsigned __int8)Isoch_DoesDriverOwnRequests(v1, v8, v7) )
    {
      v4 = 1;
      *(_DWORD *)(v1 + 336) = v9 & 0xFFFFFFF7;
    }
    *(_BYTE *)(v1 + 340) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v7);
    if ( v4 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v10 = *(unsigned __int8 *)(*(_QWORD *)(v1 + 48) + 143LL);
          LOBYTE(v10) = 5;
          WPP_RECORDER_SF_DD(
            *(_QWORD *)(*(_QWORD *)(v1 + 56) + 80LL),
            v10,
            14,
            43,
            (__int64)WPP_3bb012812b813cd0ec02732545724755_Traceguids,
            *(_BYTE *)(*(_QWORD *)(v1 + 48) + 143LL),
            *(_DWORD *)(*(_QWORD *)(v1 + 56) + 152LL));
        }
      }
      TR_TransfersReclaimed(v1);
    }
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v2);
  }
}

```

## disassembly

```asm
0x14004caf4  push    rbx
0x14004caf6  push    rbp
0x14004caf7  push    rsi
0x14004caf8  push    rdi
0x14004caf9  sub     rsp, 58h
0x14004cafd  mov     rax, cs:WdfFunctions_01033
0x14004cb04  xorps   xmm0, xmm0
0x14004cb07  mov     r8, cs:off_14006C270
0x14004cb0e  mov     rdx, rcx
0x14004cb11  mov     rcx, cs:WdfDriverGlobals
0x14004cb18  movups  [rsp+78h+var_38], xmm0
0x14004cb1d  mov     rax, [rax+650h]
0x14004cb24  call    _guard_dispatch_icall
0x14004cb29  mov     rbx, rax
0x14004cb2c  lea     rax, [rsp+78h+var_38]
0x14004cb31  mov     qword ptr [rsp+78h+var_38+8], rax
0x14004cb36  lea     rax, [rsp+78h+var_38]
0x14004cb3b  mov     qword ptr [rsp+78h+var_38], rax
0x14004cb40  lea     rsi, [rbx+60h]
0x14004cb44  mov     rcx, rsi; SpinLock
0x14004cb47  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004cb4e  nop     dword ptr [rax+rax+00h]
0x14004cb53  cmp     byte ptr [rbx+154h], 0
0x14004cb5a  mov     [rbx+68h], al
0x14004cb5d  jz      short loc_14004CB75
0x14004cb5f  mov     dl, al; NewIrql
0x14004cb61  mov     rcx, rsi; SpinLock
0x14004cb64  call    cs:__imp_KeReleaseSpinLock
0x14004cb6b  nop     dword ptr [rax+rax+00h]
0x14004cb70  jmp     loc_14004CC9C
0x14004cb75  xor     bpl, bpl
0x14004cb78  mov     byte ptr [rbx+154h], 1
0x14004cb7f  lea     rdi, [rbx+1A8h]
0x14004cb86  mov     rcx, [rdi]
0x14004cb89  cmp     rcx, rdi
0x14004cb8c  jz      short loc_14004CBBE
0x14004cb8e  mov     rax, qword ptr [rsp+78h+var_38+8]
0x14004cb93  mov     [rax], rcx
0x14004cb96  mov     rax, qword ptr [rsp+78h+var_38+8]
0x14004cb9b  mov     rcx, [rdi]
0x14004cb9e  mov     [rcx+8], rax
0x14004cba2  lea     rcx, [rsp+78h+var_38]
0x14004cba7  mov     rax, [rdi+8]
0x14004cbab  mov     [rax], rcx
0x14004cbae  mov     rax, [rdi+8]
0x14004cbb2  mov     qword ptr [rsp+78h+var_38+8], rax
0x14004cbb7  mov     [rdi+8], rdi
0x14004cbbb  mov     [rdi], rdi
0x14004cbbe  mov     dl, [rbx+68h]; NewIrql
0x14004cbc1  mov     rcx, rsi; SpinLock
0x14004cbc4  call    cs:__imp_KeReleaseSpinLock
0x14004cbcb  nop     dword ptr [rax+rax+00h]
0x14004cbd0  lea     rdx, [rsp+78h+var_38]
0x14004cbd5  mov     rcx, rbx
0x14004cbd8  call    Isoch_CompleteTransfers
0x14004cbdd  mov     rcx, rsi; SpinLock
0x14004cbe0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004cbe7  nop     dword ptr [rax+rax+00h]
0x14004cbec  mov     [rbx+68h], al
0x14004cbef  mov     r8b, al
0x14004cbf2  cmp     [rdi], rdi
0x14004cbf5  jnz     short loc_14004CB86
0x14004cbf7  mov     edx, [rbx+150h]
0x14004cbfd  test    dl, 8
0x14004cc00  jz      short loc_14004CC1A
0x14004cc02  mov     rcx, rbx
0x14004cc05  call    Isoch_DoesDriverOwnRequests
0x14004cc0a  test    al, al
0x14004cc0c  jnz     short loc_14004CC1A
0x14004cc0e  and     edx, 0FFFFFFF7h
0x14004cc11  mov     bpl, 1
0x14004cc14  mov     [rbx+150h], edx
0x14004cc1a  mov     dl, r8b; NewIrql
0x14004cc1d  mov     byte ptr [rbx+154h], 0
0x14004cc24  mov     rcx, rsi; SpinLock
0x14004cc27  call    cs:__imp_KeReleaseSpinLock
0x14004cc2e  nop     dword ptr [rax+rax+00h]
0x14004cc33  test    bpl, bpl
0x14004cc36  jz      short loc_14004CC9C
0x14004cc38  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14004cc3f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004cc46  jz      short loc_14004CC94
0x14004cc48  mov     rax, cs:WPP_GLOBAL_Control
0x14004cc4f  cmp     word ptr [rax+48h], 0
0x14004cc54  jz      short loc_14004CC94
0x14004cc56  mov     rax, [rbx+30h]
0x14004cc5a  mov     r9d, 2Bh ; '+'
0x14004cc60  mov     rcx, [rbx+38h]
0x14004cc64  movzx   edx, byte ptr [rax+8Fh]
0x14004cc6b  lea     r8d, [r9-1Dh]
0x14004cc6f  mov     eax, [rcx+98h]
0x14004cc75  mov     rcx, [rcx+50h]
0x14004cc79  mov     [rsp+78h+var_48], eax
0x14004cc7d  lea     rax, WPP_3bb012812b813cd0ec02732545724755_Traceguids
0x14004cc84  mov     [rsp+78h+var_50], edx
0x14004cc88  mov     dl, 5
0x14004cc8a  mov     [rsp+78h+var_58], rax
0x14004cc8f  call    WPP_RECORDER_SF_DD
0x14004cc94  mov     rcx, rbx
0x14004cc97  call    TR_TransfersReclaimed
0x14004cc9c  add     rsp, 58h
0x14004cca0  pop     rdi
0x14004cca1  pop     rsi
0x14004cca2  pop     rbp
0x14004cca3  pop     rbx
0x14004cca4  retn
```
