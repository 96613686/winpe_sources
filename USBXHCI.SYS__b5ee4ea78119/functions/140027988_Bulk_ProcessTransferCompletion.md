# Bulk_ProcessTransferCompletion

- ea: `0x140027988`
- end: `0x140027b55`
- name: `Bulk_ProcessTransferCompletion`
- size: `461`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140027950`
- `0x14003b570`

## callees

- `0x140005d48`
- `0x140027988`
- `0x140027b5c`
- `0x140027fcc`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140027a46`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027a9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027afd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027a46`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027a9d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027afd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400279db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027a62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400279db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027a62`

## pseudocode

```c
void __fastcall Bulk_ProcessTransferCompletion(__int64 a1)
{
  __int64 v1; // rbx
  KIRQL v2; // al
  bool v3; // zf
  char v4; // bp
  __int64 v5; // rdi
  KIRQL v6; // al
  int v7; // edx
  int v8; // edx
  _OWORD v9[3]; // [rsp+40h] [rbp-38h] BYREF

  v9[0] = 0;
  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C270);
  *((_QWORD *)&v9[0] + 1) = v9;
  *(_QWORD *)&v9[0] = v9;
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  v3 = *(_BYTE *)(v1 + 336) == 0;
  *(_BYTE *)(v1 + 104) = v2;
  if ( v3 )
  {
    v4 = 0;
    *(_BYTE *)(v1 + 336) = 1;
    v5 = v1 + 408;
    do
    {
      if ( *(_QWORD *)v5 != v5 )
      {
        **((_QWORD **)&v9[0] + 1) = *(_QWORD *)v5;
        *(_QWORD *)(*(_QWORD *)v5 + 8LL) = *((_QWORD *)&v9[0] + 1);
        **(_QWORD **)(v1 + 416) = v9;
        *((_QWORD *)&v9[0] + 1) = *(_QWORD *)(v1 + 416);
        *(_QWORD *)(v1 + 416) = v1 + 408;
        *(_QWORD *)v5 = v5;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), *(_BYTE *)(v1 + 104));
      Bulk_CompleteTransfers(v1, (__int64 ****)v9);
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
      *(_BYTE *)(v1 + 104) = v6;
    }
    while ( *(_QWORD *)v5 != v5 );
    v7 = *(_DWORD *)(v1 + 332);
    if ( (v7 & 0x40) != 0 && *(_QWORD *)(v1 + 376) == v1 + 376 && *(_QWORD *)(v1 + 392) == v1 + 392 )
    {
      v4 = 1;
      *(_DWORD *)(v1 + 332) = v7 & 0xFFFFFFBF;
    }
    *(_BYTE *)(v1 + 336) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v6);
    if ( v4 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v8 = *(unsigned __int8 *)(*(_QWORD *)(v1 + 48) + 143LL);
          LOBYTE(v8) = 5;
          WPP_RECORDER_SF_ddL(
            *(_QWORD *)(*(_QWORD *)(v1 + 56) + 80LL),
            v8,
            14,
            16,
            (__int64)WPP_ca96e44c3422373aa36d221d9452da5a_Traceguids,
            *(_BYTE *)(*(_QWORD *)(v1 + 48) + 143LL),
            *(_DWORD *)(*(_QWORD *)(v1 + 56) + 152LL),
            *(_DWORD *)(v1 + 64));
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
0x140027988  push    rbx
0x14002798a  push    rbp
0x14002798b  push    rsi
0x14002798c  push    rdi
0x14002798d  sub     rsp, 58h
0x140027991  mov     rax, cs:WdfFunctions_01033
0x140027998  xorps   xmm0, xmm0
0x14002799b  mov     r8, cs:off_14006C270
0x1400279a2  mov     rdx, rcx
0x1400279a5  mov     rcx, cs:WdfDriverGlobals
0x1400279ac  movups  [rsp+78h+var_38], xmm0
0x1400279b1  mov     rax, [rax+650h]
0x1400279b8  call    _guard_dispatch_icall
0x1400279bd  mov     rbx, rax
0x1400279c0  lea     rax, [rsp+78h+var_38]
0x1400279c5  mov     qword ptr [rsp+78h+var_38+8], rax
0x1400279ca  lea     rax, [rsp+78h+var_38]
0x1400279cf  mov     qword ptr [rsp+78h+var_38], rax
0x1400279d4  lea     rsi, [rbx+60h]
0x1400279d8  mov     rcx, rsi; SpinLock
0x1400279db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400279e2  nop     dword ptr [rax+rax+00h]
0x1400279e7  cmp     byte ptr [rbx+150h], 0
0x1400279ee  mov     [rbx+68h], al
0x1400279f1  jnz     loc_140027AF8
0x1400279f7  xor     bpl, bpl
0x1400279fa  mov     byte ptr [rbx+150h], 1
0x140027a01  lea     rdi, [rbx+198h]
0x140027a08  mov     rcx, [rdi]
0x140027a0b  cmp     rcx, rdi
0x140027a0e  jz      short loc_140027A40
0x140027a10  mov     rax, qword ptr [rsp+78h+var_38+8]
0x140027a15  mov     [rax], rcx
0x140027a18  mov     rax, qword ptr [rsp+78h+var_38+8]
0x140027a1d  mov     rcx, [rdi]
0x140027a20  mov     [rcx+8], rax
0x140027a24  lea     rcx, [rsp+78h+var_38]
0x140027a29  mov     rax, [rdi+8]
0x140027a2d  mov     [rax], rcx
0x140027a30  mov     rax, [rdi+8]
0x140027a34  mov     qword ptr [rsp+78h+var_38+8], rax
0x140027a39  mov     [rdi+8], rdi
0x140027a3d  mov     [rdi], rdi
0x140027a40  mov     dl, [rbx+68h]; NewIrql
0x140027a43  mov     rcx, rsi; SpinLock
0x140027a46  call    cs:__imp_KeReleaseSpinLock
0x140027a4d  nop     dword ptr [rax+rax+00h]
0x140027a52  lea     rdx, [rsp+78h+var_38]
0x140027a57  mov     rcx, rbx
0x140027a5a  call    Bulk_CompleteTransfers
0x140027a5f  mov     rcx, rsi; SpinLock
0x140027a62  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027a69  nop     dword ptr [rax+rax+00h]
0x140027a6e  mov     [rbx+68h], al
0x140027a71  mov     r8b, al
0x140027a74  cmp     [rdi], rdi
0x140027a77  jnz     short loc_140027A08
0x140027a79  mov     edx, [rbx+14Ch]
0x140027a7f  test    dl, 40h
0x140027a82  jz      short loc_140027A90
0x140027a84  lea     rcx, [rbx+178h]
0x140027a8b  cmp     [rcx], rcx
0x140027a8e  jz      short loc_140027ADE
0x140027a90  mov     dl, r8b; NewIrql
0x140027a93  mov     byte ptr [rbx+150h], 0
0x140027a9a  mov     rcx, rsi; SpinLock
0x140027a9d  call    cs:__imp_KeReleaseSpinLock
0x140027aa4  nop     dword ptr [rax+rax+00h]
0x140027aa9  test    bpl, bpl
0x140027aac  jz      short loc_140027AD4
0x140027aae  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027ab5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027abc  jz      short loc_140027ACC
0x140027abe  mov     rax, cs:WPP_GLOBAL_Control
0x140027ac5  cmp     word ptr [rax+48h], 0
0x140027aca  jnz     short loc_140027B0B
0x140027acc  mov     rcx, rbx
0x140027acf  call    TR_TransfersReclaimed
0x140027ad4  add     rsp, 58h
0x140027ad8  pop     rdi
0x140027ad9  pop     rsi
0x140027ada  pop     rbp
0x140027adb  pop     rbx
0x140027adc  retn
0x140027ade  lea     rax, [rbx+188h]
0x140027ae5  cmp     [rax], rax
0x140027ae8  jnz     short loc_140027A90
0x140027aea  and     edx, 0FFFFFFBFh
0x140027aed  mov     bpl, 1
0x140027af0  mov     [rbx+14Ch], edx
0x140027af6  jmp     short loc_140027A90
0x140027af8  mov     dl, al; NewIrql
0x140027afa  mov     rcx, rsi; SpinLock
0x140027afd  call    cs:__imp_KeReleaseSpinLock
0x140027b04  nop     dword ptr [rax+rax+00h]
0x140027b09  jmp     short loc_140027AD4
0x140027b0b  mov     rax, [rbx+30h]
0x140027b0f  mov     r9d, 10h
0x140027b15  mov     rcx, [rbx+38h]
0x140027b19  movzx   edx, byte ptr [rax+8Fh]
0x140027b20  lea     r8d, [r9-2]
0x140027b24  mov     eax, [rbx+40h]
0x140027b27  mov     [rsp+78h+var_40], eax
0x140027b2b  mov     eax, [rcx+98h]
0x140027b31  mov     rcx, [rcx+50h]
0x140027b35  mov     [rsp+78h+var_48], eax
0x140027b39  lea     rax, WPP_ca96e44c3422373aa36d221d9452da5a_Traceguids
0x140027b40  mov     [rsp+78h+var_50], edx
0x140027b44  mov     dl, 5
0x140027b46  mov     [rsp+78h+var_58], rax
0x140027b4b  call    WPP_RECORDER_SF_ddL
0x140027b50  jmp     loc_140027ACC
```
