# FltpProcessOperationStatusCallbacks

- ea: `0x18001b2a0`
- end: `0x18001b415`
- name: `FltpProcessOperationStatusCallbacks`
- size: `373`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180007500`
- `0x180007d80`
- `0x1800126a0`

## callees

- `0x18001b2a0`
- `0x1800248e0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18001b375`
- `ntoskrnl!ObfDereferenceObject` at `0x18001b375`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001b3a0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001b3a0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18001b38a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18001b38a`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x18001b30d`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x18001b30d`

## pseudocode

```c
void __fastcall FltpProcessOperationStatusCallbacks(__int64 a1, unsigned int a2)
{
  void *v4; // rbx
  void *v5; // rsi
  __int64 v6; // rbp
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rax
  USHORT TxFsContext; // ax
  __int128 v9; // [rsp+30h] [rbp-48h] BYREF
  __int128 v10; // [rsp+40h] [rbp-38h]
  __int128 v11; // [rsp+50h] [rbp-28h]

  v9 = 0;
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    v4 = *(void **)(a1 + 32);
    if ( !v4 )
      break;
    *(_QWORD *)(a1 + 32) = *(_QWORD *)v4;
    v5 = (void *)*((_QWORD *)v4 + 4);
    v6 = *((_QWORD *)v4 + 5);
    if ( !v5 || *(_DWORD *)(*(_QWORD *)(v6 + 64) + 60LL) != 2 )
    {
      LOWORD(v9) = 48;
      *((_QWORD *)&v9 + 1) = *(_QWORD *)(v6 + 72);
      *(_QWORD *)&v10 = *(_QWORD *)(v6 + 64);
      *((_QWORD *)&v10 + 1) = v6;
      *(_QWORD *)&v11 = v5;
LABEL_6:
      *((_QWORD *)&v11 + 1) = 0;
      TxFsContext = 0;
      goto LABEL_7;
    }
    TransactionParameterBlock = IoGetTransactionParameterBlock(*((PFILE_OBJECT *)v4 + 4));
    LOWORD(v9) = 48;
    *((_QWORD *)&v9 + 1) = *(_QWORD *)(v6 + 72);
    *(_QWORD *)&v10 = *(_QWORD *)(v6 + 64);
    *((_QWORD *)&v10 + 1) = v6;
    *(_QWORD *)&v11 = v5;
    if ( !TransactionParameterBlock )
      goto LABEL_6;
    *((_QWORD *)&v11 + 1) = TransactionParameterBlock->TransactionObject;
    TxFsContext = TransactionParameterBlock->TxFsContext;
LABEL_7:
    WORD1(v9) = TxFsContext;
    (*((void (__fastcall **)(__int128 *, __int64, _QWORD, _QWORD))v4 + 1))(
      &v9,
      (__int64)v4 + 24,
      a2,
      *((_QWORD *)v4 + 2));
    if ( v5 )
      ObfDereferenceObject(v5);
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v6 + 56), 1u);
    ExFreeToNPagedLookasideList(&stru_18003F3C0, v4);
  }
}

```

## disassembly

```asm
0x18001b2a0  mov     rax, rsp
0x18001b2a3  mov     [rax+20h], rbx
0x18001b2a7  push    rdi
0x18001b2a8  push    r12
0x18001b2aa  push    r15
0x18001b2ac  sub     rsp, 60h
0x18001b2b0  xorps   xmm0, xmm0
0x18001b2b3  mov     [rax+8], rbp
0x18001b2b7  mov     [rax+10h], rsi
0x18001b2bb  mov     r15d, edx
0x18001b2be  movups  xmmword ptr [rax-48h], xmm0
0x18001b2c2  mov     [rax+18h], r14
0x18001b2c6  mov     rdi, rcx
0x18001b2c9  movups  xmmword ptr [rax-38h], xmm0
0x18001b2cd  mov     r12d, 30h ; '0'
0x18001b2d3  movups  xmmword ptr [rax-28h], xmm0
0x18001b2d7  mov     rbx, [rdi+20h]
0x18001b2db  test    rbx, rbx
0x18001b2de  jz      loc_18001B3D8
0x18001b2e4  mov     rax, [rbx]
0x18001b2e7  mov     [rdi+20h], rax
0x18001b2eb  mov     rsi, [rbx+20h]
0x18001b2ef  mov     rbp, [rbx+28h]
0x18001b2f3  test    rsi, rsi
0x18001b2f6  jz      loc_18001B3B1
0x18001b2fc  mov     rax, [rbp+40h]
0x18001b300  cmp     dword ptr [rax+3Ch], 2
0x18001b304  jnz     loc_18001B3B1
0x18001b30a  mov     rcx, rsi; FileObject
0x18001b30d  call    cs:__imp_IoGetTransactionParameterBlock
0x18001b314  nop     dword ptr [rax+rax+00h]
0x18001b319  mov     [rsp+78h+var_48], r12w
0x18001b31f  mov     rcx, [rbp+48h]
0x18001b323  mov     [rsp+78h+var_40], rcx
0x18001b328  mov     rcx, [rbp+40h]
0x18001b32c  mov     [rsp+78h+var_38], rcx
0x18001b331  mov     [rsp+78h+var_30], rbp
0x18001b336  mov     [rsp+78h+var_28], rsi
0x18001b33b  test    rax, rax
0x18001b33e  jnz     loc_18001B403
0x18001b344  mov     [rsp+78h+var_20], 0
0x18001b34d  xor     eax, eax
0x18001b34f  mov     [rsp+78h+var_46], ax
0x18001b354  lea     rdx, [rbx+18h]
0x18001b358  mov     rax, [rbx+8]
0x18001b35c  lea     rcx, [rsp+78h+var_48]
0x18001b361  mov     r9, [rbx+10h]
0x18001b365  mov     r8d, r15d
0x18001b368  call    _guard_dispatch_icall
0x18001b36d  test    rsi, rsi
0x18001b370  jz      short loc_18001B381
0x18001b372  mov     rcx, rsi; Object
0x18001b375  call    cs:__imp_ObfDereferenceObject
0x18001b37c  nop     dword ptr [rax+rax+00h]
0x18001b381  mov     rcx, [rbp+38h]; RunRef
0x18001b385  mov     edx, 1; Count
0x18001b38a  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18001b391  nop     dword ptr [rax+rax+00h]
0x18001b396  mov     rdx, rbx; Entry
0x18001b399  lea     rcx, stru_18003F3C0; Lookaside
0x18001b3a0  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001b3a7  nop     dword ptr [rax+rax+00h]
0x18001b3ac  jmp     loc_18001B2D7
0x18001b3b1  mov     [rsp+78h+var_48], r12w
0x18001b3b7  mov     rax, [rbp+48h]
0x18001b3bb  mov     [rsp+78h+var_40], rax
0x18001b3c0  mov     rax, [rbp+40h]
0x18001b3c4  mov     [rsp+78h+var_38], rax
0x18001b3c9  mov     [rsp+78h+var_30], rbp
0x18001b3ce  mov     [rsp+78h+var_28], rsi
0x18001b3d3  jmp     loc_18001B344
0x18001b3d8  mov     r14, [rsp+78h+arg_10]
0x18001b3e0  mov     rsi, [rsp+78h+arg_8]
0x18001b3e8  mov     rbp, [rsp+78h+arg_0]
0x18001b3f0  mov     rbx, [rsp+78h+arg_18]
0x18001b3f8  add     rsp, 60h
0x18001b3fc  pop     r15
0x18001b3fe  pop     r12
0x18001b400  pop     rdi
0x18001b401  retn
0x18001b403  mov     rcx, [rax+8]
0x18001b407  mov     [rsp+78h+var_20], rcx
0x18001b40c  movzx   eax, word ptr [rax+2]
0x18001b410  jmp     loc_18001B34F
```
