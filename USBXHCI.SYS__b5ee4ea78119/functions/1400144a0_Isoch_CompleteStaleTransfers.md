# Isoch_CompleteStaleTransfers

- ea: `0x1400144a0`
- end: `0x1400146e6`
- name: `Isoch_CompleteStaleTransfers`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140015bf0`
- `0x140016218`

## callees

- `0x14000d5c0`
- `0x140013e24`
- `0x1400144a0`
- `0x1400146f0`
- `0x140014d30`
- `0x14004c834`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400144f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400144f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400144cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014581`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001469d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400144cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014581`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001469d`

## pseudocode

```c
__int64 **__fastcall Isoch_CompleteStaleTransfers(__int64 a1, __int64 ***a2)
{
  __int64 ****v4; // rsi
  __int64 ***v5; // r14
  __int64 *v6; // rsi
  __int64 **result; // rax
  __int64 *v8; // rax
  int v9; // ebp
  __int64 i; // r14
  __int64 **v11; // r15
  __int64 **v12; // rdx
  int v13; // eax
  __int64 **v14; // rax
  __int64 ****v15; // rcx
  _QWORD *v16; // rax
  __int64 *v17; // [rsp+50h] [rbp-58h] BYREF
  __int64 **v18; // [rsp+58h] [rbp-50h]

  v18 = &v17;
  v17 = (__int64 *)&v17;
  v4 = (__int64 ****)(a1 + 392);
  *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v5 = *v4;
  if ( *v4 != (__int64 ***)v4 )
  {
    while ( 1 )
    {
      if ( v5 == a2 )
        goto LABEL_2;
      v11 = *v5;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = v5[6];
        v13 = *((_DWORD *)v12 + 32);
        LOBYTE(v12) = 4;
        WPP_RECORDER_SF_DDqD(
          *(_QWORD *)(*(_QWORD *)(a1 + 56) + 80LL),
          (_DWORD)v12,
          *(unsigned __int8 *)(*(_QWORD *)(a1 + 48) + 143LL),
          23,
          (__int64)WPP_3bb012812b813cd0ec02732545724755_Traceguids,
          *(_BYTE *)(*(_QWORD *)(a1 + 48) + 143LL),
          *(_DWORD *)(*(_QWORD *)(a1 + 56) + 152LL),
          (char)v5[3],
          v13);
      }
      v14 = *v5;
      if ( (*v5)[1] != (__int64 *)v5 )
        break;
      v15 = (__int64 ****)v5[1];
      if ( *v15 != v5 )
        break;
      *v15 = (__int64 ***)v14;
      v14[1] = (__int64 *)v15;
      v16 = v18;
      if ( *v18 != (__int64 *)&v17 )
        break;
      v5[1] = v18;
      *v5 = &v17;
      *v16 = v5;
      v18 = (__int64 **)v5;
      v5 = (__int64 ***)v11;
      if ( v11 == (__int64 **)v4 )
        goto LABEL_2;
    }
LABEL_16:
    __fastfail(3u);
  }
LABEL_2:
  while ( 1 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
    v6 = v17;
    result = &v17;
    if ( v17 == (__int64 *)&v17 )
      return result;
    if ( (__int64 **)v17[1] != &v17 )
      goto LABEL_16;
    v8 = (__int64 *)*v17;
    if ( *(__int64 **)(*v17 + 8) != v17 )
      goto LABEL_16;
    v17 = (__int64 *)*v17;
    v8[1] = (__int64)&v17;
    v9 = 0;
    v6[1] = (__int64)v6;
    *v6 = (__int64)v6;
    *((_BYTE *)v6 + 133) = *((_BYTE *)v6 + 132);
    *((_BYTE *)v6 + 134) = *((_BYTE *)v6 + 130);
    for ( i = StageQueue_ForwardScanGetNextStage(v6 + 16); i; i = StageQueue_ForwardScanGetNextStage(v6 + 16) )
    {
      Isoch_Stage_FreeScatterGatherList(a1, i);
      *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
      Isoch_Stage_Release(a1, i);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
      ++v9;
    }
    *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    Isoch_Transfer_CompleteCancelable(a1, v6, -1, -1, 1, 0);
    *(_DWORD *)(a1 + 384) -= v9;
  }
}

```

## disassembly

```asm
0x1400144a0  push    rbx
0x1400144a2  push    rbp
0x1400144a3  push    rsi
0x1400144a4  push    rdi
0x1400144a5  push    r12
0x1400144a7  push    r13
0x1400144a9  push    r14
0x1400144ab  push    r15
0x1400144ad  sub     rsp, 68h
0x1400144b1  lea     rax, [rsp+0A8h+var_58]
0x1400144b6  mov     rbx, rcx
0x1400144b9  mov     [rsp+0A8h+var_50], rax
0x1400144be  add     rcx, 60h ; '`'; SpinLock
0x1400144c2  lea     rax, [rsp+0A8h+var_58]
0x1400144c7  mov     rbp, rdx
0x1400144ca  mov     [rsp+0A8h+var_58], rax
0x1400144cf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400144d6  nop     dword ptr [rax+rax+00h]
0x1400144db  lea     rsi, [rbx+188h]
0x1400144e2  mov     [rbx+68h], al
0x1400144e5  mov     r14, [rsi]
0x1400144e8  cmp     r14, rsi
0x1400144eb  jnz     loc_1400145CB
0x1400144f1  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x1400144f5  lea     rcx, [rbx+60h]; SpinLock
0x1400144f9  call    cs:__imp_KeReleaseSpinLock
0x140014500  nop     dword ptr [rax+rax+00h]
0x140014505  mov     rsi, [rsp+0A8h+var_58]
0x14001450a  lea     rax, [rsp+0A8h+var_58]
0x14001450f  cmp     rsi, rax
0x140014512  jz      loc_1400145B9
0x140014518  lea     rax, [rsp+0A8h+var_58]
0x14001451d  cmp     [rsi+8], rax
0x140014521  jnz     loc_140014687
0x140014527  mov     rax, [rsi]
0x14001452a  cmp     [rax+8], rsi
0x14001452e  jnz     loc_140014687
0x140014534  mov     [rsp+0A8h+var_58], rax
0x140014539  lea     rcx, [rsp+0A8h+var_58]
0x14001453e  mov     [rax+8], rcx
0x140014542  xor     ebp, ebp
0x140014544  mov     [rsi+8], rsi
0x140014548  lea     rcx, [rsi+80h]
0x14001454f  mov     [rsi], rsi
0x140014552  movzx   eax, byte ptr [rsi+84h]
0x140014559  mov     [rsi+85h], al
0x14001455f  movzx   eax, byte ptr [rsi+82h]
0x140014566  mov     [rsi+86h], al
0x14001456c  call    StageQueue_ForwardScanGetNextStage
0x140014571  mov     r14, rax
0x140014574  test    rax, rax
0x140014577  jnz     loc_14001468E
0x14001457d  lea     rcx, [rbx+60h]; SpinLock
0x140014581  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014588  nop     dword ptr [rax+rax+00h]
0x14001458d  mov     r9d, 0FFFFFFFFh
0x140014593  mov     byte ptr [rsp+0A8h+var_80], 0
0x140014598  mov     r8d, r9d
0x14001459b  mov     [rbx+68h], al
0x14001459e  mov     rdx, rsi
0x1400145a1  mov     byte ptr [rsp+0A8h+var_88], 1
0x1400145a6  mov     rcx, rbx
0x1400145a9  call    Isoch_Transfer_CompleteCancelable
0x1400145ae  sub     [rbx+180h], ebp
0x1400145b4  jmp     loc_1400144F1
0x1400145b9  add     rsp, 68h
0x1400145bd  pop     r15
0x1400145bf  pop     r14
0x1400145c1  pop     r13
0x1400145c3  pop     r12
0x1400145c5  pop     rdi
0x1400145c6  pop     rsi
0x1400145c7  pop     rbp
0x1400145c8  pop     rbx
0x1400145c9  retn
0x1400145cb  lea     r12, WPP_RECORDER_INITIALIZED
0x1400145d2  lea     r13, WPP_3bb012812b813cd0ec02732545724755_Traceguids
0x1400145d9  cmp     r14, rbp
0x1400145dc  jz      loc_1400144F1
0x1400145e2  mov     r15, [r14]
0x1400145e5  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400145ec  jz      short loc_14001463A
0x1400145ee  mov     rax, [rbx+30h]
0x1400145f2  mov     r9d, 17h
0x1400145f8  mov     rdx, [r14+30h]
0x1400145fc  mov     rcx, [rbx+38h]
0x140014600  movzx   r8d, byte ptr [rax+8Fh]
0x140014608  mov     eax, [rdx+80h]
0x14001460e  mov     dl, 4
0x140014610  mov     [rsp+0A8h+var_68], eax
0x140014614  mov     rax, [r14+18h]
0x140014618  mov     [rsp+0A8h+var_70], rax
0x14001461d  mov     eax, [rcx+98h]
0x140014623  mov     rcx, [rcx+50h]
0x140014627  mov     [rsp+0A8h+var_78], eax
0x14001462b  mov     [rsp+0A8h+var_80], r8d
0x140014630  mov     [rsp+0A8h+var_88], r13
0x140014635  call    WPP_RECORDER_SF_DDqD
0x14001463a  mov     rax, [r14]
0x14001463d  cmp     [rax+8], r14
0x140014641  jnz     short loc_140014687
0x140014643  mov     rcx, [r14+8]
0x140014647  cmp     [rcx], r14
0x14001464a  jnz     short loc_140014687
0x14001464c  mov     [rcx], rax
0x14001464f  mov     [rax+8], rcx
0x140014653  lea     rcx, [rsp+0A8h+var_58]
0x140014658  mov     rax, [rsp+0A8h+var_50]
0x14001465d  cmp     [rax], rcx
0x140014660  jnz     short loc_140014687
0x140014662  mov     [r14+8], rax
0x140014666  lea     rcx, [rsp+0A8h+var_58]
0x14001466b  mov     [r14], rcx
0x14001466e  mov     [rax], r14
0x140014671  mov     [rsp+0A8h+var_50], r14
0x140014676  mov     r14, r15
0x140014679  cmp     r15, rsi
0x14001467c  jnz     loc_1400145D9
0x140014682  jmp     loc_1400144F1
0x140014687  mov     ecx, 3
0x14001468c  int     29h; Win8: RtlFailFast(ecx)
0x14001468e  mov     rdx, r14
0x140014691  mov     rcx, rbx
0x140014694  call    Isoch_Stage_FreeScatterGatherList
0x140014699  lea     rcx, [rbx+60h]; SpinLock
0x14001469d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400146a4  nop     dword ptr [rax+rax+00h]
0x1400146a9  mov     rdx, r14
0x1400146ac  mov     rcx, rbx
0x1400146af  mov     [rbx+68h], al
0x1400146b2  call    Isoch_Stage_Release
0x1400146b7  movzx   edx, byte ptr [rbx+68h]; NewIrql
0x1400146bb  lea     rcx, [rbx+60h]; SpinLock
0x1400146bf  call    cs:__imp_KeReleaseSpinLock
0x1400146c6  nop     dword ptr [rax+rax+00h]
0x1400146cb  lea     rcx, [rsi+80h]
0x1400146d2  inc     ebp
0x1400146d4  call    StageQueue_ForwardScanGetNextStage
0x1400146d9  mov     r14, rax
0x1400146dc  test    rax, rax
0x1400146df  jnz     short loc_14001468E
0x1400146e1  jmp     loc_14001457D
```
