# Isoch_CompleteTransfers

- ea: `0x14000cb4c`
- end: `0x14000cccf`
- name: `Isoch_CompleteTransfers`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004caf4`

## callees

- `0x14000cb4c`
- `0x14000d5c0`
- `0x140013e24`
- `0x1400146f0`
- `0x140014d30`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14000cb9d`
- `ntoskrnl!KfRaiseIrql` at `0x14000cb9d`
- `ntoskrnl!KeLowerIrql` at `0x14000cbcf`
- `ntoskrnl!KeLowerIrql` at `0x14000cbcf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc41`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cca7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cc41`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cca7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cc21`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cc6c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cc21`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cc6c`

## pseudocode

```c
void __fastcall Isoch_CompleteTransfers(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rax
  KIRQL v6; // bl
  int v7; // r12d
  __int64 NextStage; // r14
  KSPIN_LOCK *v9; // rbx
  KIRQL v10; // dl

  while ( 1 )
  {
    v4 = (_QWORD *)*a2;
    if ( (_QWORD *)*a2 == a2 )
      break;
    if ( (_QWORD *)v4[1] != a2 || (v5 = *v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *a2 = v5;
    *(_QWORD *)(v5 + 8) = a2;
    v4[1] = v4;
    *v4 = v4;
    if ( *((_DWORD *)v4 + 17) == 259 )
    {
      *((_BYTE *)v4 + 133) = *((_BYTE *)v4 + 132);
      v7 = 0;
      *((_BYTE *)v4 + 134) = *((_BYTE *)v4 + 130);
      NextStage = StageQueue_ForwardScanGetNextStage(v4 + 16);
      if ( NextStage )
      {
        do
        {
          Isoch_Stage_FreeScatterGatherList(a1, NextStage);
          v9 = (KSPIN_LOCK *)(a1 + 96);
          *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
          Isoch_Stage_Release(a1, NextStage);
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
          ++*((_DWORD *)v4 + 28);
          ++v7;
          NextStage = StageQueue_ForwardScanGetNextStage(v4 + 16);
        }
        while ( NextStage );
      }
      else
      {
        v9 = (KSPIN_LOCK *)(a1 + 96);
      }
      *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc(v9);
      Isoch_Transfer_CompleteCancelable(a1, v4, -1, -1073676288, 1, 0);
      v10 = *(_BYTE *)(a1 + 104);
      *(_DWORD *)(a1 + 384) -= v7;
      KeReleaseSpinLock(v9, v10);
    }
    else
    {
      v6 = KfRaiseIrql(2u);
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01033 + 2104))(
        WdfDriverGlobals,
        v4[3],
        *((unsigned int *)v4 + 17));
      KeLowerIrql(v6);
    }
  }
}

```

## disassembly

```asm
0x14000cb4c  push    rbx
0x14000cb4e  push    rbp
0x14000cb4f  push    rsi
0x14000cb50  push    rdi
0x14000cb51  push    r12
0x14000cb53  push    r14
0x14000cb55  push    r15
0x14000cb57  sub     rsp, 30h
0x14000cb5b  mov     rsi, rdx
0x14000cb5e  mov     rbp, rcx
0x14000cb61  mov     rdi, [rsi]
0x14000cb64  cmp     rdi, rsi
0x14000cb67  jz      loc_14000CCBF
0x14000cb6d  cmp     [rdi+8], rsi
0x14000cb71  jnz     loc_14000CCB8
0x14000cb77  mov     rax, [rdi]
0x14000cb7a  cmp     [rax+8], rdi
0x14000cb7e  jnz     loc_14000CCB8
0x14000cb84  mov     [rsi], rax
0x14000cb87  mov     [rax+8], rsi
0x14000cb8b  mov     [rdi+8], rdi
0x14000cb8f  mov     [rdi], rdi
0x14000cb92  cmp     dword ptr [rdi+44h], 103h
0x14000cb99  jz      short loc_14000CBDD
0x14000cb9b  mov     cl, 2; NewIrql
0x14000cb9d  call    cs:__imp_KfRaiseIrql
0x14000cba4  nop     dword ptr [rax+rax+00h]
0x14000cba9  mov     rcx, cs:WdfFunctions_01033
0x14000cbb0  mov     bl, al
0x14000cbb2  mov     r8d, [rdi+44h]
0x14000cbb6  mov     rdx, [rdi+18h]
0x14000cbba  mov     rax, [rcx+838h]
0x14000cbc1  mov     rcx, cs:WdfDriverGlobals
0x14000cbc8  call    _guard_dispatch_icall
0x14000cbcd  mov     cl, bl; NewIrql
0x14000cbcf  call    cs:__imp_KeLowerIrql
0x14000cbd6  nop     dword ptr [rax+rax+00h]
0x14000cbdb  jmp     short loc_14000CB61
0x14000cbdd  mov     al, [rdi+84h]
0x14000cbe3  lea     r15, [rdi+80h]
0x14000cbea  mov     [rdi+85h], al
0x14000cbf0  mov     rcx, r15
0x14000cbf3  mov     al, [rdi+82h]
0x14000cbf9  xor     r12d, r12d
0x14000cbfc  mov     [rdi+86h], al
0x14000cc02  call    StageQueue_ForwardScanGetNextStage
0x14000cc07  mov     r14, rax
0x14000cc0a  test    rax, rax
0x14000cc0d  jz      short loc_14000CC65
0x14000cc0f  mov     rdx, r14
0x14000cc12  mov     rcx, rbp
0x14000cc15  call    Isoch_Stage_FreeScatterGatherList
0x14000cc1a  lea     rbx, [rbp+60h]
0x14000cc1e  mov     rcx, rbx; SpinLock
0x14000cc21  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cc28  nop     dword ptr [rax+rax+00h]
0x14000cc2d  mov     rdx, r14
0x14000cc30  mov     rcx, rbp
0x14000cc33  mov     [rbp+68h], al
0x14000cc36  call    Isoch_Stage_Release
0x14000cc3b  mov     dl, [rbp+68h]; NewIrql
0x14000cc3e  mov     rcx, rbx; SpinLock
0x14000cc41  call    cs:__imp_KeReleaseSpinLock
0x14000cc48  nop     dword ptr [rax+rax+00h]
0x14000cc4d  inc     dword ptr [rdi+70h]
0x14000cc50  mov     rcx, r15
0x14000cc53  inc     r12d
0x14000cc56  call    StageQueue_ForwardScanGetNextStage
0x14000cc5b  mov     r14, rax
0x14000cc5e  test    rax, rax
0x14000cc61  jnz     short loc_14000CC0F
0x14000cc63  jmp     short loc_14000CC69
0x14000cc65  lea     rbx, [rbp+60h]
0x14000cc69  mov     rcx, rbx; SpinLock
0x14000cc6c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cc73  nop     dword ptr [rax+rax+00h]
0x14000cc78  mov     r9d, 0C0010000h
0x14000cc7e  mov     [rsp+68h+var_40], 0
0x14000cc83  or      r8d, 0FFFFFFFFh
0x14000cc87  mov     [rbp+68h], al
0x14000cc8a  mov     rdx, rdi
0x14000cc8d  mov     [rsp+68h+var_48], 1
0x14000cc92  mov     rcx, rbp
0x14000cc95  call    Isoch_Transfer_CompleteCancelable
0x14000cc9a  mov     dl, [rbp+68h]; NewIrql
0x14000cc9d  mov     rcx, rbx; SpinLock
0x14000cca0  sub     [rbp+180h], r12d
0x14000cca7  call    cs:__imp_KeReleaseSpinLock
0x14000ccae  nop     dword ptr [rax+rax+00h]
0x14000ccb3  jmp     loc_14000CB61
0x14000ccb8  mov     ecx, 3
0x14000ccbd  int     29h; Win8: RtlFailFast(ecx)
0x14000ccbf  add     rsp, 30h
0x14000ccc3  pop     r15
0x14000ccc5  pop     r14
0x14000ccc7  pop     r12
0x14000ccc9  pop     rdi
0x14000ccca  pop     rsi
0x14000cccb  pop     rbp
0x14000cccc  pop     rbx
0x14000cccd  retn
```
