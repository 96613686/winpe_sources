# AiGetNextDelimitedUninstallString

- ea: `0x140020930`
- end: `0x140020a6a`
- name: `AiGetNextDelimitedUninstallString`
- size: `314`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140020c28`

## callees

- `0x140020930`
- `0x140021298`

## pseudocode

```c
__int64 __fastcall AiGetNextDelimitedUninstallString(__int64 a1, __int64 a2, _OWORD *a3)
{
  int CharInUnicodeString; // eax
  int v7; // r8d
  __int128 v8; // xmm1
  __int64 v9; // xmm6_8
  int v10; // r15d
  __int16 v11; // r14
  __int16 v12; // r12
  __int16 v13; // ax
  __int16 v14; // cx
  __int128 v15; // xmm0
  __int128 v17; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 v18; // [rsp+A8h] [rbp+60h] BYREF

  v18 = 0;
  v17 = 0;
  CharInUnicodeString = AiRtlFindCharInUnicodeString(0, a1, &qword_140009288, &v18);
  v7 = CharInUnicodeString;
  if ( CharInUnicodeString == -1073741275 )
  {
    v7 = 0;
    v8 = v17;
    *(_OWORD *)a2 = *(_OWORD *)a1;
    *a3 = v8;
  }
  else if ( CharInUnicodeString >= 0 )
  {
    v9 = *(_QWORD *)(a1 + 2);
    v10 = *(_DWORD *)(a1 + 10);
    v11 = v18 - 2;
    v12 = *(_WORD *)(a1 + 14);
    v13 = *(_WORD *)(a1 + 2);
    *((_QWORD *)&v17 + 1) = *(_QWORD *)(a1 + 8) + 2 * ((unsigned __int64)v18 >> 1);
    v14 = *(_WORD *)a1 - v18;
    WORD1(v17) = v13 - v18;
    LOWORD(v17) = v14;
    if ( v14 )
    {
      v7 = AiRtlFindCharInUnicodeString(2, &v17, &qword_140009288, &v18);
      if ( v7 < 0 )
      {
        LOWORD(v17) = 0;
        v7 = 0;
      }
      else
      {
        LOWORD(v17) = v17 - (v18 - 2);
        WORD1(v17) -= v18 - 2;
        *((_QWORD *)&v17 + 1) += 2 * ((unsigned __int64)(unsigned __int16)(v18 - 2) >> 1);
      }
    }
    v15 = v17;
    *(_WORD *)a2 = v11;
    *(_QWORD *)(a2 + 2) = v9;
    *(_DWORD *)(a2 + 10) = v10;
    *a3 = v15;
    *(_WORD *)(a2 + 14) = v12;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140020930  push    rbp
0x140020932  push    rbx
0x140020933  push    rsi
0x140020934  push    rdi
0x140020935  push    r12
0x140020937  push    r13
0x140020939  push    r14
0x14002093b  push    r15
0x14002093d  mov     rbp, rsp
0x140020940  sub     rsp, 48h
0x140020944  mov     rbx, rdx
0x140020947  movaps  [rsp+48h+var_18], xmm6
0x14002094c  mov     rdx, rcx
0x14002094f  lea     r9, [rbp+arg_18]
0x140020953  mov     rsi, r8
0x140020956  mov     rdi, rcx
0x140020959  xorps   xmm0, xmm0
0x14002095c  lea     r8, qword_140009288
0x140020963  xor     r13d, r13d
0x140020966  xor     ecx, ecx
0x140020968  mov     [rbp+arg_18], r13w
0x14002096d  movups  [rbp+var_28], xmm0
0x140020971  call    AiRtlFindCharInUnicodeString
0x140020976  mov     r8d, eax
0x140020979  cmp     eax, 0C0000225h
0x14002097e  jnz     short loc_140020997
0x140020980  movups  xmm0, xmmword ptr [rdi]
0x140020983  mov     r8d, r13d
0x140020986  movups  xmm1, [rbp+var_28]
0x14002098a  movdqu  xmmword ptr [rbx], xmm0
0x14002098e  movdqu  xmmword ptr [rsi], xmm1
0x140020992  jmp     loc_140020A50
0x140020997  test    eax, eax
0x140020999  js      loc_140020A50
0x14002099f  movzx   edx, [rbp+arg_18]
0x1400209a3  mov     r10d, 2
0x1400209a9  mov     rax, [rdi+8]
0x1400209ad  mov     ecx, edx
0x1400209af  movsd   xmm6, qword ptr [rdi+2]
0x1400209b4  movzx   r14d, dx
0x1400209b8  mov     r15d, [rdi+0Ah]
0x1400209bc  sub     r14w, r10w
0x1400209c0  movzx   r12d, word ptr [rdi+0Eh]
0x1400209c5  shr     rcx, 1
0x1400209c8  lea     rcx, [rax+rcx*2]
0x1400209cc  movzx   eax, word ptr [rdi+2]
0x1400209d0  mov     qword ptr [rbp+var_28+8], rcx
0x1400209d4  sub     ax, dx
0x1400209d7  movzx   ecx, word ptr [rdi]
0x1400209da  sub     cx, dx
0x1400209dd  mov     word ptr [rbp+var_28+2], ax
0x1400209e1  mov     word ptr [rbp+var_28], cx
0x1400209e5  test    cx, cx
0x1400209e8  jz      short loc_140020A36
0x1400209ea  lea     r9, [rbp+arg_18]
0x1400209ee  mov     ecx, r10d
0x1400209f1  lea     r8, qword_140009288
0x1400209f8  lea     rdx, [rbp+var_28]
0x1400209fc  call    AiRtlFindCharInUnicodeString
0x140020a01  mov     r8d, eax
0x140020a04  test    eax, eax
0x140020a06  js      short loc_140020A2E
0x140020a08  movzx   eax, [rbp+arg_18]
0x140020a0c  sub     ax, 2
0x140020a10  movzx   edx, ax
0x140020a13  mov     rax, qword ptr [rbp+var_28+8]
0x140020a17  mov     ecx, edx
0x140020a19  sub     word ptr [rbp+var_28], dx
0x140020a1d  shr     rcx, 1
0x140020a20  sub     word ptr [rbp+var_28+2], dx
0x140020a24  lea     rcx, [rax+rcx*2]
0x140020a28  mov     qword ptr [rbp+var_28+8], rcx
0x140020a2c  jmp     short loc_140020A36
0x140020a2e  mov     word ptr [rbp+var_28], r13w
0x140020a33  mov     r8d, r13d
0x140020a36  movups  xmm0, [rbp+var_28]
0x140020a3a  mov     [rbx], r14w
0x140020a3e  movsd   qword ptr [rbx+2], xmm6
0x140020a43  mov     [rbx+0Ah], r15d
0x140020a47  movdqu  xmmword ptr [rsi], xmm0
0x140020a4b  mov     [rbx+0Eh], r12w
0x140020a50  movaps  xmm6, [rsp+48h+var_18]
0x140020a55  mov     eax, r8d
0x140020a58  add     rsp, 48h
0x140020a5c  pop     r15
0x140020a5e  pop     r14
0x140020a60  pop     r13
0x140020a62  pop     r12
0x140020a64  pop     rdi
0x140020a65  pop     rsi
0x140020a66  pop     rbx
0x140020a67  pop     rbp
0x140020a68  retn
```
