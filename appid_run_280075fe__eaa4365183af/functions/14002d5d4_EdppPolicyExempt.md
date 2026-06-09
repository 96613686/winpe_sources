# EdppPolicyExempt

- ea: `0x14002d5d4`
- end: `0x14002d85f`
- name: `EdppPolicyExempt`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003ec0`

## callees

- `0x140003dd8`
- `0x14002023c`
- `0x140022afc`
- `0x140026088`
- `0x140026140`
- `0x14002d2e0`
- `0x14002d5d4`

## import_xrefs

- `ntoskrnl!SeCompareSigningLevels` at `0x14002d692`
- `ntoskrnl!SeCompareSigningLevels` at `0x14002d71b`
- `ntoskrnl!SeCompareSigningLevels` at `0x14002d692`
- `ntoskrnl!SeCompareSigningLevels` at `0x14002d71b`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x14002d67d`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x14002d706`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x14002d67d`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x14002d706`
- `ntoskrnl!ZwSetCachedSigningLevel` at `0x14002d6de`
- `ntoskrnl!ZwSetCachedSigningLevel` at `0x14002d6de`
- `ntoskrnl!PsIsProtectedProcess` at `0x14002d618`
- `ntoskrnl!PsIsProtectedProcess` at `0x14002d618`

## pseudocode

```c
__int64 __fastcall EdppPolicyExempt(_QWORD *a1, _BYTE *a2, _BYTE *a3, int a4, __int64 a5)
{
  __int64 v6; // rcx
  __int64 result; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  char v17; // al
  __int64 v18; // r9
  __int64 v19; // r9
  char v20; // [rsp+30h] [rbp-30h] BYREF
  char v21; // [rsp+31h] [rbp-2Fh] BYREF
  _BYTE v22[2]; // [rsp+32h] [rbp-2Eh] BYREF
  int v23; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 v24; // [rsp+38h] [rbp-28h] BYREF
  __int128 v25; // [rsp+40h] [rbp-20h] BYREF
  int v26; // [rsp+50h] [rbp-10h]
  int v27; // [rsp+54h] [rbp-Ch]
  __int64 *v28; // [rsp+58h] [rbp-8h]
  char v29; // [rsp+90h] [rbp+30h] BYREF

  v6 = a1[1];
  v24 = 0;
  v29 = 0;
  v23 = 0;
  v22[0] = 0;
  v21 = 0;
  v20 = 0;
  if ( (unsigned int)PsIsProtectedProcess(v6) )
  {
    result = 0;
LABEL_32:
    *a2 = 1;
    return result;
  }
  v11 = (_QWORD *)a1[9];
  v12 = *v11 - 0x4896EF1A58125A50LL;
  if ( *v11 == 0x4896EF1A58125A50LL )
    v12 = v11[1] - 0x6CCAB39AC6D657BALL;
  *a2 = 0;
  if ( v12 )
  {
    v28 = qword_140010260;
    if ( (int)ZwGetCachedSigningLevel(a1[4], &v23, &v29, 0, 0, 0) >= 0 )
    {
      LOBYTE(v14) = v29;
      LOBYTE(v13) = 12;
      if ( (unsigned int)SeCompareSigningLevels(v14, v13) )
      {
        *a2 = 1;
LABEL_9:
        v17 = 0;
        goto LABEL_21;
      }
    }
    AiSigningLevelCacheExists(a1[8], &v20);
    v17 = 0;
    if ( !v20 )
    {
      LOBYTE(v15) = 12;
      if ( (int)ZwSetCachedSigningLevel(5, v15, a1 + 4) >= 0
        && (int)ZwGetCachedSigningLevel(a1[4], &v23, &v29, 0, 0, 0) >= 0 )
      {
        LOBYTE(v16) = v29;
        LOBYTE(v15) = 12;
        if ( (unsigned int)SeCompareSigningLevels(v16, v15) == 1 )
          *a2 = 1;
      }
      if ( *a2 )
        goto LABEL_22;
      AiSetSigningLevelCache(a1[8]);
      goto LABEL_9;
    }
  }
  else
  {
    v28 = qword_140013A30;
    result = EdppIsAppxBroker(a1, &v21);
    if ( (int)result < 0 )
      return result;
    if ( v21 )
      goto LABEL_32;
    result = AiIsAppxInbox(a1[7], v22);
    if ( (int)result < 0 )
      return result;
    *a2 = v22[0];
    v17 = 1;
  }
LABEL_21:
  if ( *a2 )
  {
LABEL_22:
    v18 = a1[5];
    v27 = 1;
    v25 = xmmword_14000E000;
    v26 = 0;
    result = AiEvaluateAppLockerPolicyClass(v16, v15, &v25, v18, &v24);
    if ( (int)result < 0 )
      return result;
    if ( (int)v24 < 0 )
      *a2 = 0;
    goto LABEL_29;
  }
  if ( v17 )
  {
    v19 = a1[5];
    v28 = qword_14000E010;
    v27 = 1;
    v26 = 0;
    v25 = xmmword_14000E000;
    result = AiEvaluateAppLockerPolicyClass(v16, v15, &v25, v19, &v24);
    if ( (int)result < 0 )
      return result;
    if ( (int)v24 >= 0 )
      *a2 = 1;
  }
LABEL_29:
  result = EdppEvaluatePolicies((_DWORD)a1, 1, (unsigned int)&v24, a4, a5);
  if ( (int)result >= 0 && (int)v24 >= 0 )
  {
    *a3 = 1;
    goto LABEL_32;
  }
  return result;
}

```

## disassembly

```asm
0x14002d5d4  mov     [rsp-28h+arg_8], rbx
0x14002d5d9  mov     [rsp-28h+arg_10], rsi
0x14002d5de  push    rbp
0x14002d5df  push    rdi
0x14002d5e0  push    r12
0x14002d5e2  push    r14
0x14002d5e4  push    r15
0x14002d5e6  mov     rbp, rsp
0x14002d5e9  sub     rsp, 60h
0x14002d5ed  xor     r12d, r12d
0x14002d5f0  mov     rdi, rcx
0x14002d5f3  mov     rcx, [rcx+8]
0x14002d5f7  mov     r15, r9
0x14002d5fa  mov     [rbp+var_28], r12
0x14002d5fe  mov     r14, r8
0x14002d601  mov     [rbp+arg_0], r12b
0x14002d605  mov     rbx, rdx
0x14002d608  mov     [rbp+var_2C], r12d
0x14002d60c  mov     [rbp+var_2E], r12b
0x14002d610  mov     [rbp+var_2F], r12b
0x14002d614  mov     [rbp+var_30], r12b
0x14002d618  call    cs:__imp_PsIsProtectedProcess
0x14002d61f  nop     dword ptr [rax+rax+00h]
0x14002d624  test    eax, eax
0x14002d626  jz      short loc_14002D62F
0x14002d628  xor     eax, eax
0x14002d62a  jmp     loc_14002D842
0x14002d62f  mov     rcx, [rdi+48h]
0x14002d633  mov     rax, [rcx]
0x14002d636  sub     rax, cs:qword_14000DFF0
0x14002d63d  jnz     short loc_14002D64A
0x14002d63f  mov     rax, [rcx+8]
0x14002d643  sub     rax, cs:qword_14000DFF8
0x14002d64a  mov     [rbx], r12b
0x14002d64d  test    rax, rax
0x14002d650  jz      loc_14002D744
0x14002d656  lea     rax, qword_140010260
0x14002d65d  mov     [rsp+60h+var_38], r12
0x14002d662  lea     rsi, [rdi+20h]
0x14002d666  mov     [rbp+var_8], rax
0x14002d66a  mov     rcx, [rsi]
0x14002d66d  lea     r8, [rbp+arg_0]
0x14002d671  xor     r9d, r9d
0x14002d674  mov     [rsp+60h+var_40], r12
0x14002d679  lea     rdx, [rbp+var_2C]
0x14002d67d  call    cs:__imp_ZwGetCachedSigningLevel
0x14002d684  nop     dword ptr [rax+rax+00h]
0x14002d689  test    eax, eax
0x14002d68b  js      short loc_14002D6AD
0x14002d68d  mov     cl, [rbp+arg_0]
0x14002d690  mov     dl, 0Ch
0x14002d692  call    cs:__imp_SeCompareSigningLevels
0x14002d699  nop     dword ptr [rax+rax+00h]
0x14002d69e  test    eax, eax
0x14002d6a0  jz      short loc_14002D6AD
0x14002d6a2  mov     byte ptr [rbx], 1
0x14002d6a5  mov     al, r12b
0x14002d6a8  jmp     loc_14002D789
0x14002d6ad  mov     rcx, [rdi+40h]
0x14002d6b1  lea     rdx, [rbp+var_30]
0x14002d6b5  call    AiSigningLevelCacheExists
0x14002d6ba  mov     al, r12b
0x14002d6bd  cmp     [rbp+var_30], r12b
0x14002d6c1  jnz     loc_14002D789
0x14002d6c7  mov     rax, [rsi]
0x14002d6ca  mov     r9d, 1
0x14002d6d0  mov     r8, rsi
0x14002d6d3  mov     [rsp+60h+var_40], rax
0x14002d6d8  mov     dl, 0Ch
0x14002d6da  lea     ecx, [r9+4]
0x14002d6de  call    cs:__imp_ZwSetCachedSigningLevel
0x14002d6e5  nop     dword ptr [rax+rax+00h]
0x14002d6ea  test    eax, eax
0x14002d6ec  js      short loc_14002D72E
0x14002d6ee  mov     rcx, [rsi]
0x14002d6f1  lea     r8, [rbp+arg_0]
0x14002d6f5  mov     [rsp+60h+var_38], r12
0x14002d6fa  lea     rdx, [rbp+var_2C]
0x14002d6fe  xor     r9d, r9d
0x14002d701  mov     [rsp+60h+var_40], r12
0x14002d706  call    cs:__imp_ZwGetCachedSigningLevel
0x14002d70d  nop     dword ptr [rax+rax+00h]
0x14002d712  test    eax, eax
0x14002d714  js      short loc_14002D72E
0x14002d716  mov     cl, [rbp+arg_0]
0x14002d719  mov     dl, 0Ch
0x14002d71b  call    cs:__imp_SeCompareSigningLevels
0x14002d722  nop     dword ptr [rax+rax+00h]
0x14002d727  cmp     eax, 1
0x14002d72a  jnz     short loc_14002D72E
0x14002d72c  mov     [rbx], al
0x14002d72e  mov     al, r12b
0x14002d731  cmp     [rbx], r12b
0x14002d734  jnz     short loc_14002D78E
0x14002d736  mov     rcx, [rdi+40h]
0x14002d73a  call    AiSetSigningLevelCache
0x14002d73f  jmp     loc_14002D6A5
0x14002d744  lea     rax, qword_140013A30
0x14002d74b  mov     rcx, rdi
0x14002d74e  lea     rdx, [rbp+var_2F]
0x14002d752  mov     [rbp+var_8], rax
0x14002d756  call    EdppIsAppxBroker
0x14002d75b  test    eax, eax
0x14002d75d  js      loc_14002D845
0x14002d763  cmp     [rbp+var_2F], r12b
0x14002d767  jnz     loc_14002D842
0x14002d76d  mov     rcx, [rdi+38h]
0x14002d771  lea     rdx, [rbp+var_2E]
0x14002d775  call    AiIsAppxInbox
0x14002d77a  test    eax, eax
0x14002d77c  js      loc_14002D845
0x14002d782  mov     al, [rbp+var_2E]
0x14002d785  mov     [rbx], al
0x14002d787  mov     al, 1
0x14002d789  cmp     [rbx], r12b
0x14002d78c  jz      short loc_14002D7CE
0x14002d78e  movups  xmm0, cs:xmmword_14000E000
0x14002d795  mov     r9, [rdi+28h]
0x14002d799  lea     rax, [rbp+var_28]
0x14002d79d  lea     r8, [rbp+var_20]
0x14002d7a1  mov     [rbp+var_C], 1
0x14002d7a8  movdqu  [rbp+var_20], xmm0
0x14002d7ad  mov     [rbp+var_10], r12d
0x14002d7b1  mov     [rsp+60h+var_40], rax
0x14002d7b6  call    AiEvaluateAppLockerPolicyClass
0x14002d7bb  test    eax, eax
0x14002d7bd  js      loc_14002D845
0x14002d7c3  cmp     dword ptr [rbp+var_28], r12d
0x14002d7c7  jge     short loc_14002D817
0x14002d7c9  mov     [rbx], r12b
0x14002d7cc  jmp     short loc_14002D817
0x14002d7ce  test    al, al
0x14002d7d0  jz      short loc_14002D817
0x14002d7d2  movups  xmm0, cs:xmmword_14000E000
0x14002d7d9  mov     r9, [rdi+28h]
0x14002d7dd  lea     rax, qword_14000E010
0x14002d7e4  mov     [rbp+var_8], rax
0x14002d7e8  lea     r8, [rbp+var_20]
0x14002d7ec  lea     rax, [rbp+var_28]
0x14002d7f0  mov     [rbp+var_C], 1
0x14002d7f7  mov     [rsp+60h+var_40], rax
0x14002d7fc  mov     [rbp+var_10], r12d
0x14002d800  movdqu  [rbp+var_20], xmm0
0x14002d805  call    AiEvaluateAppLockerPolicyClass
0x14002d80a  test    eax, eax
0x14002d80c  js      short loc_14002D845
0x14002d80e  cmp     dword ptr [rbp+var_28], r12d
0x14002d812  jl      short loc_14002D817
0x14002d814  mov     byte ptr [rbx], 1
0x14002d817  mov     rax, [rbp+arg_20]
0x14002d81b  lea     r8, [rbp+var_28]
0x14002d81f  mov     r9, r15
0x14002d822  mov     [rsp+60h+var_40], rax
0x14002d827  mov     edx, 1
0x14002d82c  mov     rcx, rdi
0x14002d82f  call    EdppEvaluatePolicies
0x14002d834  test    eax, eax
0x14002d836  js      short loc_14002D845
0x14002d838  cmp     dword ptr [rbp+var_28], r12d
0x14002d83c  jl      short loc_14002D845
0x14002d83e  mov     byte ptr [r14], 1
0x14002d842  mov     byte ptr [rbx], 1
0x14002d845  lea     r11, [rsp+60h+var_s0]
0x14002d84a  mov     rbx, [r11+38h]
0x14002d84e  mov     rsi, [r11+40h]
0x14002d852  mov     rsp, r11
0x14002d855  pop     r15
0x14002d857  pop     r14
0x14002d859  pop     r12
0x14002d85b  pop     rdi
0x14002d85c  pop     rbp
0x14002d85d  retn
```
