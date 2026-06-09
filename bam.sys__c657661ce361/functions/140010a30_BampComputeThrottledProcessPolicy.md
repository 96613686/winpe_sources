# BampComputeThrottledProcessPolicy

- ea: `0x140010a30`
- end: `0x140010c9b`
- name: `BampComputeThrottledProcessPolicy`
- size: `619`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010990`
- `0x140015100`

## callees

- `0x140010a30`
- `0x140010cb0`
- `0x140010e20`
- `0x140011010`
- `0x140011090`
- `0x1400110d8`

## pseudocode

```c
__int64 __fastcall BampComputeThrottledProcessPolicy(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 result; // rax
  int v6; // edi
  char v7; // r12
  unsigned int v8; // r15d
  __int64 v9; // rdx
  char v10; // r13
  char v11; // cl
  bool IsPerMechanismExemptionActive; // al
  unsigned int v13; // ebx
  unsigned int v14; // r15d
  bool v15; // al
  int v16; // ebx
  int v17; // ecx
  bool v18; // al
  int v19; // r15d
  __int64 v20; // [rsp+20h] [rbp-40h]
  __int128 v21; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h]
  unsigned int v23; // [rsp+98h] [rbp+38h] BYREF
  int v24; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+48h]

  v2 = 0;
  result = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v24 = 0;
  v6 = 0;
  v20 = 0;
  if ( !byte_1400075E8 )
    goto LABEL_22;
  v7 = 0;
  BampGetThrottledProcessExemptionState(a1, &v23, (unsigned int *)&v24);
  v6 = 1;
  if ( v23 )
    goto LABEL_23;
  v8 = *(_DWORD *)(a1 + 376);
  LODWORD(v20) = v8;
  LOBYTE(v23) = 0;
  BampThrottledProcessGetEffectiveState(a1, &v21);
  v10 = BYTE12(v21);
  v11 = v22;
  if ( (BYTE12(v21) & 1) != 0 )
  {
    v9 = v22 & 1;
    v13 = v9 | v8 & 0xFFFFFFFE;
    v25 = v22 & 1;
    LODWORD(v20) = v13;
  }
  else
  {
    LOBYTE(v9) = 0;
    v25 = v9;
    if ( (v8 & 1) != 0 )
    {
      IsPerMechanismExemptionActive = BampIsPerMechanismExemptionActive(a1, 0, &v24);
      v11 = v22;
      v9 = v25;
      LOBYTE(v2) = !IsPerMechanismExemptionActive;
      v13 = v8 & 0xFFFFFFFE | v2;
      LODWORD(v20) = v13;
    }
    else
    {
      v13 = v8;
    }
    if ( (v13 & 1) != 0 )
      LOBYTE(v23) = v21 & 1;
  }
  if ( (v10 & 2) != 0 )
  {
    v14 = v11 & 2 | v13 & 0xFFFFFFFD;
  }
  else
  {
    if ( (v13 & 2) == 0 )
    {
      v14 = v13;
      goto LABEL_11;
    }
    v18 = BampIsPerMechanismExemptionActive(a1, 1, &v24);
    v11 = v22;
    v19 = 0;
    v9 = v25;
    if ( !v18 )
      v19 = 2;
    v14 = v13 & 0xFFFFFFFD | v19;
  }
  LODWORD(v20) = v14;
LABEL_11:
  if ( (v10 & 4) != 0 )
  {
    v17 = v11 & 4;
    LOBYTE(v2) = v17 | v14 & 0xFB;
    LODWORD(v20) = v17 | v14 & 0xFFFFFFFB;
  }
  else
  {
    if ( (v14 & 4) != 0 )
    {
      v15 = BampIsPerMechanismExemptionActive(a1, 2, &v24);
      v9 = v25;
      v16 = 0;
      if ( !v15 )
        v16 = 4;
      v2 = v14 & 0xFFFFFFFB | v16;
      LODWORD(v20) = v2;
    }
    else
    {
      LOBYTE(v2) = v14;
    }
    if ( (v2 & 4) != 0 )
      v7 = v21 & 1;
  }
  if ( (v2 & 1) != 0 )
  {
    if ( (_BYTE)v23 )
    {
      result = BampComputePpmPolicyFromWindowState(a1, v9);
    }
    else
    {
      result = 1;
      if ( (_BYTE)v9 )
        result = 8;
    }
    goto LABEL_21;
  }
LABEL_23:
  result = BampComputeExemptProcessPpmPolicy(a1);
LABEL_21:
  HIDWORD(v20) = result;
  if ( (v2 & 4) != 0 )
  {
    if ( v7 )
    {
      v21 = 0;
      v22 = 0;
      BampThrottledProcessGetEffectiveState(a1, &v21);
      result = 0;
      if ( (v21 & 6) == 0 )
        v6 = 0;
    }
    else
    {
      v6 = 0;
    }
  }
LABEL_22:
  *(_QWORD *)a2 = v20;
  *(_DWORD *)(a2 + 8) = v6;
  return result;
}

```

## disassembly

```asm
0x140010a30  push    rbp
0x140010a32  push    rbx
0x140010a33  push    rsi
0x140010a34  push    rdi
0x140010a35  push    r14
0x140010a37  mov     rbp, rsp
0x140010a3a  sub     rsp, 60h
0x140010a3e  xor     ebx, ebx
0x140010a40  xor     eax, eax
0x140010a42  cmp     cs:byte_1400075E8, al
0x140010a48  xorps   xmm0, xmm0
0x140010a4b  mov     rsi, rdx
0x140010a4e  mov     [rbp+arg_8], ebx
0x140010a51  mov     r14, rcx
0x140010a54  mov     [rbp+var_20], rax
0x140010a58  movups  [rbp+var_30], xmm0
0x140010a5c  mov     [rbp+arg_10], ebx
0x140010a5f  mov     edi, ebx
0x140010a61  mov     [rbp+var_40], rax
0x140010a65  jz      loc_140010B8F
0x140010a6b  mov     [rsp+60h+arg_0], r12
0x140010a73  lea     r8, [rbp+arg_10]
0x140010a77  lea     rdx, [rbp+arg_8]
0x140010a7b  xor     r12b, r12b
0x140010a7e  call    BampGetThrottledProcessExemptionState
0x140010a83  mov     edi, 1
0x140010a88  cmp     [rbp+arg_8], ebx
0x140010a8b  jnz     loc_140010BA7
0x140010a91  mov     [rsp+60h+var_8], r13
0x140010a96  lea     rdx, [rbp+var_30]
0x140010a9a  mov     [rsp+60h+var_10], r15
0x140010a9f  mov     rcx, r14
0x140010aa2  mov     r15d, [r14+178h]
0x140010aa9  mov     dword ptr [rbp+var_40], r15d
0x140010aad  mov     byte ptr [rbp+arg_8], bl
0x140010ab0  call    BampThrottledProcessGetEffectiveState
0x140010ab5  mov     r13d, dword ptr [rbp+var_30+0Ch]
0x140010ab9  mov     rcx, [rbp+var_20]
0x140010abd  test    dil, r13b
0x140010ac0  jnz     loc_140010C0F
0x140010ac6  xor     dl, dl
0x140010ac8  mov     [rbp+arg_18], edx
0x140010acb  test    dil, r15b
0x140010ace  jz      loc_140010C4B
0x140010ad4  lea     r8, [rbp+arg_10]
0x140010ad8  xor     edx, edx
0x140010ada  mov     rcx, r14
0x140010add  call    BampIsPerMechanismExemptionActive
0x140010ae2  mov     rcx, [rbp+var_20]
0x140010ae6  test    al, al
0x140010ae8  mov     edx, [rbp+arg_18]
0x140010aeb  setz    bl
0x140010aee  and     r15d, 0FFFFFFFEh
0x140010af2  or      ebx, r15d
0x140010af5  mov     dword ptr [rbp+var_40], ebx
0x140010af8  test    dil, bl
0x140010afb  jnz     loc_140010BDE
0x140010b01  mov     eax, 2
0x140010b06  test    al, r13b
0x140010b09  jnz     loc_140010C7E
0x140010b0f  test    al, bl
0x140010b11  jnz     loc_140010C53
0x140010b17  mov     r15d, ebx
0x140010b1a  test    r13b, 4
0x140010b1e  mov     r13, [rsp+60h+var_8]
0x140010b23  jnz     loc_140010BFC
0x140010b29  test    r15b, 4
0x140010b2d  jz      loc_140010C43
0x140010b33  lea     r8, [rbp+arg_10]
0x140010b37  mov     edx, eax
0x140010b39  mov     rcx, r14
0x140010b3c  call    BampIsPerMechanismExemptionActive
0x140010b41  mov     edx, [rbp+arg_18]
0x140010b44  xor     ebx, ebx
0x140010b46  test    al, al
0x140010b48  mov     ecx, 4
0x140010b4d  cmovz   ebx, ecx
0x140010b50  and     r15d, 0FFFFFFFBh
0x140010b54  or      ebx, r15d
0x140010b57  mov     dword ptr [rbp+var_40], ebx
0x140010b5a  test    bl, 4
0x140010b5d  jnz     loc_140010BEF
0x140010b63  mov     r15, [rsp+60h+var_10]
0x140010b68  test    dil, bl
0x140010b6b  jz      short loc_140010BA7
0x140010b6d  cmp     byte ptr [rbp+arg_8], 0
0x140010b71  jz      loc_140010C2B
0x140010b77  mov     rcx, r14
0x140010b7a  call    BampComputePpmPolicyFromWindowState
0x140010b7f  mov     dword ptr [rbp+var_40+4], eax
0x140010b82  test    bl, 4
0x140010b85  jnz     short loc_140010BB1
0x140010b87  mov     r12, [rsp+60h+arg_0]
0x140010b8f  movsd   xmm0, [rbp+var_40]
0x140010b94  movsd   qword ptr [rsi], xmm0
0x140010b98  mov     [rsi+8], edi
0x140010b9b  add     rsp, 60h
0x140010b9f  pop     r14
0x140010ba1  pop     rdi
0x140010ba2  pop     rsi
0x140010ba3  pop     rbx
0x140010ba4  pop     rbp
0x140010ba5  retn
0x140010ba7  mov     rcx, r14
0x140010baa  call    BampComputeExemptProcessPpmPolicy
0x140010baf  jmp     short loc_140010B7F
0x140010bb1  test    r12b, r12b
0x140010bb4  jz      loc_140010C3C
0x140010bba  xorps   xmm0, xmm0
0x140010bbd  lea     rdx, [rbp+var_30]
0x140010bc1  xor     eax, eax
0x140010bc3  mov     rcx, r14
0x140010bc6  movups  [rbp+var_30], xmm0
0x140010bca  mov     [rbp+var_20], rax
0x140010bce  call    BampThrottledProcessGetEffectiveState
0x140010bd3  xor     eax, eax
0x140010bd5  test    byte ptr [rbp+var_30], 6
0x140010bd9  cmovz   edi, eax
0x140010bdc  jmp     short loc_140010B87
0x140010bde  movzx   r8d, byte ptr [rbp+var_30]
0x140010be3  and     r8b, dil
0x140010be6  mov     byte ptr [rbp+arg_8], r8b
0x140010bea  jmp     loc_140010B01
0x140010bef  movzx   r12d, byte ptr [rbp+var_30]
0x140010bf4  and     r12b, dil
0x140010bf7  jmp     loc_140010B63
0x140010bfc  mov     ebx, r15d
0x140010bff  and     ecx, 4
0x140010c02  and     ebx, 0FFFFFFFBh
0x140010c05  or      ebx, ecx
0x140010c07  mov     dword ptr [rbp+var_40], ebx
0x140010c0a  jmp     loc_140010B63
0x140010c0f  movzx   eax, cl
0x140010c12  mov     ebx, r15d
0x140010c15  and     al, dil
0x140010c18  and     ebx, 0FFFFFFFEh
0x140010c1b  movzx   edx, al
0x140010c1e  or      ebx, edx
0x140010c20  mov     [rbp+arg_18], edx
0x140010c23  mov     dword ptr [rbp+var_40], ebx
0x140010c26  jmp     loc_140010B01
0x140010c2b  test    dl, dl
0x140010c2d  mov     eax, edi
0x140010c2f  mov     ecx, 8
0x140010c34  cmovnz  eax, ecx
0x140010c37  jmp     loc_140010B7F
0x140010c3c  xor     edi, edi
0x140010c3e  jmp     loc_140010B87
0x140010c43  mov     ebx, r15d
0x140010c46  jmp     loc_140010B5A
0x140010c4b  mov     ebx, r15d
0x140010c4e  jmp     loc_140010AF8
0x140010c53  lea     r8, [rbp+arg_10]
0x140010c57  mov     edx, edi
0x140010c59  mov     rcx, r14
0x140010c5c  call    BampIsPerMechanismExemptionActive
0x140010c61  mov     rcx, [rbp+var_20]
0x140010c65  xor     r15d, r15d
0x140010c68  mov     edx, [rbp+arg_18]
0x140010c6b  test    al, al
0x140010c6d  mov     eax, 2
0x140010c72  cmovz   r15d, eax
0x140010c76  and     ebx, 0FFFFFFFDh
0x140010c79  or      r15d, ebx
0x140010c7c  jmp     short loc_140010C92
0x140010c7e  mov     r15d, ebx
0x140010c81  mov     eax, ecx
0x140010c83  and     eax, 2
0x140010c86  and     r15d, 0FFFFFFFDh
0x140010c8a  or      r15d, eax
0x140010c8d  mov     eax, 2
0x140010c92  mov     dword ptr [rbp+var_40], r15d
0x140010c96  jmp     loc_140010B1A
```
