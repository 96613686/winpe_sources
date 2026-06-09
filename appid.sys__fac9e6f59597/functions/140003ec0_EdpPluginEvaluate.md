# EdpPluginEvaluate

- ea: `0x140003ec0`
- end: `0x140004216`
- name: `EdpPluginEvaluate`
- size: `854`
- prototype: `__int64 __fastcall(_QWORD *, int *, __int64 *, const UNICODE_STRING **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14002b5e0`
- `0x14002cd1c`

## callees

- `0x140003ec0`
- `0x140004a70`
- `0x140020288`
- `0x14002bbf8`
- `0x14002bd3c`
- `0x14002bdf0`
- `0x14002d2e0`
- `0x14002d390`
- `0x14002d5d4`
- `0x14002d868`
- `0x14002da5c`
- `0x14002f2a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400041f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400041f6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140004043`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140004060`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000417c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140004043`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140004060`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000417c`

## pseudocode

```c
__int64 __fastcall EdpPluginEvaluate(_QWORD *a1, int *a2, __int64 *a3, const UNICODE_STRING **a4, unsigned int *a5)
{
  unsigned int *v5; // r13
  int v7; // r14d
  __int64 v8; // rax
  int v9; // r15d
  __int64 *v10; // rbx
  int IsApplicationClaimSet; // edi
  char v12; // al
  UNICODE_STRING *v13; // r14
  char v14; // r12
  char v15; // r15
  char v16; // dl
  unsigned int v17; // r12d
  __int64 v18; // rax
  BOOLEAN IsExplicitDeny; // al
  __int64 v20; // rax
  char v21; // cl
  _QWORD *v22; // rdx
  __int64 v23; // rax
  const UNICODE_STRING **v24; // r15
  int v25; // eax
  int *v26; // rcx
  const UNICODE_STRING *v27; // r15
  const UNICODE_STRING **v28; // rbx
  char v30; // [rsp+30h] [rbp-48h] BYREF
  char v31; // [rsp+31h] [rbp-47h] BYREF
  char v32; // [rsp+32h] [rbp-46h] BYREF
  char v33[5]; // [rsp+33h] [rbp-45h] BYREF
  _DWORD v34[2]; // [rsp+38h] [rbp-40h] BYREF
  PCUNICODE_STRING String1; // [rsp+40h] [rbp-38h] BYREF
  __int128 v36; // [rsp+48h] [rbp-30h] BYREF
  __int64 v37; // [rsp+58h] [rbp-20h]
  __int64 v38; // [rsp+60h] [rbp-18h]
  char v39; // [rsp+C0h] [rbp+48h] BYREF
  int *v40; // [rsp+C8h] [rbp+50h]
  __int64 *v41; // [rsp+D0h] [rbp+58h]
  const UNICODE_STRING **v42; // [rsp+D8h] [rbp+60h]

  v42 = a4;
  v41 = a3;
  v40 = a2;
  v5 = a5;
  v34[1] = 0;
  *a2 = -1073741823;
  v34[0] = -1073741823;
  v7 = (int)a2;
  v8 = a1[6];
  v33[0] = 0;
  v39 = 0;
  if ( !v8 )
    v8 = -6;
  v32 = 0;
  v38 = v8;
  v30 = 0;
  v9 = (int)a4;
  v31 = 0;
  v10 = a3;
  String1 = 0;
  IsApplicationClaimSet = 0;
  *a3 = 0;
  *a4 = 0;
  *v5 = 0;
  v36 = 0;
  v37 = 0;
  GetIntentEnterpriseId(&v36, &String1);
  v12 = EdppPolicyOverride((_DWORD)a1, v7, (_DWORD)v10, v9, (__int64)v5);
  v13 = (UNICODE_STRING *)String1;
  if ( v12 )
    goto LABEL_60;
  IsApplicationClaimSet = EdppIsApplicationClaimSet(0, (__int64)a1, &v39);
  if ( IsApplicationClaimSet < 0 )
    goto LABEL_62;
  IsApplicationClaimSet = EdppServiceExempt(a1, &v31);
  if ( IsApplicationClaimSet < 0 )
    goto LABEL_62;
  v14 = v31;
  if ( v31 )
  {
    v15 = 1;
  }
  else
  {
    IsApplicationClaimSet = EdppPolicyExempt((_DWORD)a1, (unsigned int)&v32, (unsigned int)&v30, v9, (__int64)v5);
    if ( IsApplicationClaimSet < 0 )
      goto LABEL_62;
    v15 = v32;
  }
  v16 = v30;
  if ( v39 && v15 && !v30 )
    v15 = v14 != 0 ? v15 : 0;
  if ( v13 )
  {
    v17 = 0;
    *v10 = 0;
  }
  else if ( v15 )
  {
    *v10 |= 1uLL;
    v18 = *v10;
    if ( v16 )
    {
      v18 |= 0x20uLL;
      *v10 = v18;
    }
    if ( v14 )
      *v10 = v18 | 0x10;
    v17 = 0;
  }
  else
  {
    v17 = 0;
    if ( !v39 )
      goto LABEL_30;
    *v10 |= 2uLL;
    IsApplicationClaimSet = EdppIsApplicationClaimSet(1, (__int64)a1, v33);
    if ( IsApplicationClaimSet < 0 )
      goto LABEL_62;
    if ( !v33[0] )
      goto LABEL_30;
    *v10 |= 8uLL;
  }
  if ( v15 )
    goto LABEL_60;
  if ( v13 && RtlEqualUnicodeString(v13, &EdppPersonalName, 1u) )
  {
    IsExplicitDeny = RtlEqualUnicodeString(v13, &EdppPersonalName, 1u);
    goto LABEL_58;
  }
LABEL_30:
  v20 = *a1;
  v21 = 0;
  LOBYTE(a5) = 0;
  if ( *(_BYTE *)(v20 + 1) && !v39 )
  {
    IsApplicationClaimSet = SrpIsApplicationAutoProtectionAllowed(a1[4], &a5);
    if ( IsApplicationClaimSet < 0 )
      goto LABEL_62;
    v21 = (char)a5;
    if ( !(_BYTE)a5 )
    {
      v22 = (_QWORD *)a1[9];
      v23 = *v22 - 0x4896EF1A58125A50LL;
      if ( *v22 == 0x4896EF1A58125A50LL )
        v23 = v22[1] - 0x6CCAB39AC6D657BALL;
      if ( !v23 )
      {
        IsApplicationClaimSet = EdppIsAppxLineOfBusiness((__int64)a1, (bool *)&a5);
        if ( IsApplicationClaimSet < 0 )
          goto LABEL_62;
        v21 = (char)a5;
      }
    }
  }
  if ( !*(_BYTE *)(*a1 + 1LL) || v21 || v39 )
  {
    v24 = v42;
    v25 = EdppEvaluatePolicies((_DWORD)a1, 0, (unsigned int)v34, (_DWORD)v42, (__int64)v5);
    v26 = v40;
    IsApplicationClaimSet = v25;
    *v40 = v34[0];
    if ( v25 < 0 )
      goto LABEL_62;
  }
  else
  {
    v24 = v42;
    v26 = v40;
  }
  if ( v13 )
  {
    if ( *v26 >= 0 )
    {
      v27 = *v24;
      if ( *v5 )
      {
        v28 = v42;
        do
        {
          if ( RtlEqualUnicodeString(v13, v27, 1u) )
          {
            *v28 = v27;
            *v5 = 1;
          }
          ++v17;
          ++v27;
        }
        while ( v17 < *v5 );
        v10 = v41;
      }
    }
  }
  if ( *v5 || *v10 || !EdppIsDisallowedExempt((__int64)a1) )
  {
    IsExplicitDeny = AiResultIsExplicitDeny(v34);
LABEL_58:
    if ( IsExplicitDeny )
      *v10 |= 0x40uLL;
    goto LABEL_60;
  }
  *v10 = 17;
LABEL_60:
  if ( !v13 )
    return (unsigned int)IsApplicationClaimSet;
  IsApplicationClaimSet = EdppRemoveIntentEnterpriseIdToken(a1[6]);
LABEL_62:
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  return (unsigned int)IsApplicationClaimSet;
}

```

## disassembly

```asm
0x140003ec0  mov     [rsp-40h+arg_18], r9
0x140003ec5  mov     [rsp-40h+arg_10], r8
0x140003eca  mov     [rsp-40h+arg_8], rdx
0x140003ecf  push    rbp
0x140003ed0  push    rbx
0x140003ed1  push    rsi
0x140003ed2  push    rdi
0x140003ed3  push    r12
0x140003ed5  push    r13
0x140003ed7  push    r14
0x140003ed9  push    r15
0x140003edb  mov     rbp, rsp
0x140003ede  sub     rsp, 78h
0x140003ee2  mov     r13, [rbp+arg_20]
0x140003ee6  xor     r12d, r12d
0x140003ee9  mov     eax, 0C0000001h
0x140003eee  mov     [rbp+var_40], r12
0x140003ef2  mov     [rdx], eax
0x140003ef4  mov     rsi, rcx
0x140003ef7  mov     dword ptr [rbp+var_40], eax
0x140003efa  mov     r14, rdx
0x140003efd  mov     rax, [rcx+30h]
0x140003f01  lea     rdx, [rbp+String1]
0x140003f05  test    rax, rax
0x140003f08  mov     [rbp+var_45], r12b
0x140003f0c  lea     rcx, [r12-6]
0x140003f11  mov     [rbp+arg_0], r12b
0x140003f15  cmovz   rax, rcx
0x140003f19  mov     [rbp+var_46], r12b
0x140003f1d  xorps   xmm0, xmm0
0x140003f20  mov     [rbp+var_18], rax
0x140003f24  lea     rcx, [rbp+var_30]
0x140003f28  mov     [rbp+var_48], r12b
0x140003f2c  mov     r15, r9
0x140003f2f  mov     [rbp+var_47], r12b
0x140003f33  mov     rbx, r8
0x140003f36  mov     [rbp+String1], r12
0x140003f3a  mov     edi, r12d
0x140003f3d  mov     [r8], r12
0x140003f40  mov     [r9], r12
0x140003f43  mov     [r13+0], r12d
0x140003f47  movdqu  [rbp+var_30], xmm0
0x140003f4c  mov     [rbp+var_20], r12
0x140003f50  call    GetIntentEnterpriseId
0x140003f55  mov     r9, r15
0x140003f58  mov     [rsp+78h+var_58], r13
0x140003f5d  mov     r8, rbx
0x140003f60  mov     rdx, r14
0x140003f63  mov     rcx, rsi
0x140003f66  call    EdppPolicyOverride
0x140003f6b  mov     r14, [rbp+String1]
0x140003f6f  test    al, al
0x140003f71  jnz     loc_1400041DC
0x140003f77  lea     r8, [rbp+arg_0]
0x140003f7b  mov     rdx, rsi
0x140003f7e  xor     ecx, ecx
0x140003f80  call    EdppIsApplicationClaimSet
0x140003f85  mov     edi, eax
0x140003f87  test    eax, eax
0x140003f89  js      loc_1400041EC
0x140003f8f  lea     rdx, [rbp+var_47]
0x140003f93  mov     rcx, rsi
0x140003f96  call    EdppServiceExempt
0x140003f9b  mov     edi, eax
0x140003f9d  test    eax, eax
0x140003f9f  js      loc_1400041EC
0x140003fa5  mov     r12b, [rbp+var_47]
0x140003fa9  test    r12b, r12b
0x140003fac  jz      short loc_140003FB3
0x140003fae  mov     r15b, 1
0x140003fb1  jmp     short loc_140003FD9
0x140003fb3  mov     r9, r15
0x140003fb6  mov     [rsp+78h+var_58], r13
0x140003fbb  lea     r8, [rbp+var_48]
0x140003fbf  mov     rcx, rsi
0x140003fc2  lea     rdx, [rbp+var_46]
0x140003fc6  call    EdppPolicyExempt
0x140003fcb  mov     edi, eax
0x140003fcd  test    eax, eax
0x140003fcf  js      loc_1400041EC
0x140003fd5  mov     r15b, [rbp+var_46]
0x140003fd9  cmp     [rbp+arg_0], 0
0x140003fdd  mov     dl, [rbp+var_48]
0x140003fe0  jz      short loc_140003FF5
0x140003fe2  test    r15b, r15b
0x140003fe5  jz      short loc_140003FF5
0x140003fe7  test    dl, dl
0x140003fe9  jnz     short loc_140003FF5
0x140003feb  mov     al, r12b
0x140003fee  neg     al
0x140003ff0  sbb     cl, cl
0x140003ff2  and     r15b, cl
0x140003ff5  test    r14, r14
0x140003ff8  jz      short loc_140004002
0x140003ffa  xor     r12d, r12d
0x140003ffd  mov     [rbx], r12
0x140004000  jmp     short loc_140004028
0x140004002  test    r15b, r15b
0x140004005  jz      short loc_140004071
0x140004007  or      qword ptr [rbx], 1
0x14000400b  mov     rax, [rbx]
0x14000400e  test    dl, dl
0x140004010  jz      short loc_140004019
0x140004012  or      rax, 20h
0x140004016  mov     [rbx], rax
0x140004019  test    r12b, r12b
0x14000401c  jz      short loc_140004025
0x14000401e  or      rax, 10h
0x140004022  mov     [rbx], rax
0x140004025  xor     r12d, r12d
0x140004028  test    r15b, r15b
0x14000402b  jnz     loc_1400041DC
0x140004031  test    r14, r14
0x140004034  jz      short loc_1400040A5
0x140004036  mov     r8b, 1; CaseInSensitive
0x140004039  lea     rdx, EdppPersonalName; String2
0x140004040  mov     rcx, r14; String1
0x140004043  call    cs:__imp_RtlEqualUnicodeString
0x14000404a  nop     dword ptr [rax+rax+00h]
0x14000404f  test    al, al
0x140004051  jz      short loc_1400040A5
0x140004053  mov     r8b, 1; CaseInSensitive
0x140004056  lea     rdx, EdppPersonalName; String2
0x14000405d  mov     rcx, r14; String1
0x140004060  call    cs:__imp_RtlEqualUnicodeString
0x140004067  nop     dword ptr [rax+rax+00h]
0x14000406c  jmp     loc_1400041D4
0x140004071  xor     r12d, r12d
0x140004074  cmp     [rbp+arg_0], r12b
0x140004078  jz      short loc_1400040A5
0x14000407a  or      qword ptr [rbx], 2
0x14000407e  lea     r8, [rbp+var_45]
0x140004082  mov     rdx, rsi
0x140004085  lea     ecx, [r12+1]
0x14000408a  call    EdppIsApplicationClaimSet
0x14000408f  mov     edi, eax
0x140004091  test    eax, eax
0x140004093  js      loc_1400041EC
0x140004099  cmp     [rbp+var_45], r12b
0x14000409d  jz      short loc_1400040A5
0x14000409f  or      qword ptr [rbx], 8
0x1400040a3  jmp     short loc_140004028
0x1400040a5  mov     rax, [rsi]
0x1400040a8  mov     cl, r12b
0x1400040ab  mov     byte ptr [rbp+arg_20], cl
0x1400040ae  cmp     [rax+1], r12b
0x1400040b2  jz      short loc_140004111
0x1400040b4  cmp     [rbp+arg_0], r12b
0x1400040b8  jnz     short loc_140004111
0x1400040ba  mov     rcx, [rsi+20h]
0x1400040be  lea     rdx, [rbp+arg_20]
0x1400040c2  call    SrpIsApplicationAutoProtectionAllowed
0x1400040c7  mov     edi, eax
0x1400040c9  test    eax, eax
0x1400040cb  js      loc_1400041EC
0x1400040d1  mov     cl, byte ptr [rbp+arg_20]
0x1400040d4  test    cl, cl
0x1400040d6  jnz     short loc_140004111
0x1400040d8  mov     rdx, [rsi+48h]
0x1400040dc  mov     rax, [rdx]
0x1400040df  sub     rax, cs:qword_14000DFD0
0x1400040e6  jnz     short loc_1400040F3
0x1400040e8  mov     rax, [rdx+8]
0x1400040ec  sub     rax, cs:qword_14000DFD8
0x1400040f3  test    rax, rax
0x1400040f6  jnz     short loc_140004111
0x1400040f8  lea     rdx, [rbp+arg_20]
0x1400040fc  mov     rcx, rsi
0x1400040ff  call    EdppIsAppxLineOfBusiness
0x140004104  mov     edi, eax
0x140004106  test    eax, eax
0x140004108  js      loc_1400041EC
0x14000410e  mov     cl, byte ptr [rbp+arg_20]
0x140004111  mov     rax, [rsi]
0x140004114  cmp     [rax+1], r12b
0x140004118  jz      short loc_140004124
0x14000411a  test    cl, cl
0x14000411c  jnz     short loc_140004124
0x14000411e  cmp     [rbp+arg_0], r12b
0x140004122  jz      short loc_140004153
0x140004124  mov     r15, [rbp+arg_18]
0x140004128  lea     r8, [rbp+var_40]
0x14000412c  mov     r9, r15
0x14000412f  mov     [rsp+78h+var_58], r13
0x140004134  xor     edx, edx
0x140004136  mov     rcx, rsi
0x140004139  call    EdppEvaluatePolicies
0x14000413e  mov     rcx, [rbp+arg_8]
0x140004142  mov     edi, eax
0x140004144  mov     eax, dword ptr [rbp+var_40]
0x140004147  mov     [rcx], eax
0x140004149  test    edi, edi
0x14000414b  js      loc_1400041EC
0x140004151  jmp     short loc_14000415B
0x140004153  mov     r15, [rbp+arg_18]
0x140004157  mov     rcx, [rbp+arg_8]
0x14000415b  test    r14, r14
0x14000415e  jz      short loc_1400041AB
0x140004160  cmp     [rcx], r12d
0x140004163  jl      short loc_1400041AB
0x140004165  cmp     dword ptr [r13+0], 0
0x14000416a  mov     r15, [r15]
0x14000416d  jbe     short loc_1400041A8
0x14000416f  mov     rbx, [rbp+arg_18]
0x140004173  mov     r8b, 1; CaseInSensitive
0x140004176  mov     rdx, r15; String2
0x140004179  mov     rcx, r14; String1
0x14000417c  call    cs:__imp_RtlEqualUnicodeString
0x140004183  nop     dword ptr [rax+rax+00h]
0x140004188  test    al, al
0x14000418a  jz      short loc_140004197
0x14000418c  mov     [rbx], r15
0x14000418f  mov     dword ptr [r13+0], 1
0x140004197  inc     r12d
0x14000419a  add     r15, 10h
0x14000419e  cmp     r12d, [r13+0]
0x1400041a2  jb      short loc_140004173
0x1400041a4  mov     rbx, [rbp+arg_10]
0x1400041a8  xor     r12d, r12d
0x1400041ab  cmp     [r13+0], r12d
0x1400041af  jnz     short loc_1400041CB
0x1400041b1  cmp     [rbx], r12
0x1400041b4  jnz     short loc_1400041CB
0x1400041b6  mov     rcx, rsi
0x1400041b9  call    EdppIsDisallowedExempt
0x1400041be  test    al, al
0x1400041c0  jz      short loc_1400041CB
0x1400041c2  mov     qword ptr [rbx], 11h
0x1400041c9  jmp     short loc_1400041DC
0x1400041cb  lea     rcx, [rbp+var_40]
0x1400041cf  call    AiResultIsExplicitDeny
0x1400041d4  test    al, al
0x1400041d6  jz      short loc_1400041DC
0x1400041d8  or      qword ptr [rbx], 40h
0x1400041dc  test    r14, r14
0x1400041df  jz      short loc_140004202
0x1400041e1  mov     rcx, [rsi+30h]
0x1400041e5  call    EdppRemoveIntentEnterpriseIdToken
0x1400041ea  mov     edi, eax
0x1400041ec  test    r14, r14
0x1400041ef  jz      short loc_140004202
0x1400041f1  xor     edx, edx; Tag
0x1400041f3  mov     rcx, r14; P
0x1400041f6  call    cs:__imp_ExFreePoolWithTag
0x1400041fd  nop     dword ptr [rax+rax+00h]
0x140004202  mov     eax, edi
0x140004204  add     rsp, 78h
0x140004208  pop     r15
0x14000420a  pop     r14
0x14000420c  pop     r13
0x14000420e  pop     r12
0x140004210  pop     rdi
0x140004211  pop     rsi
0x140004212  pop     rbx
0x140004213  pop     rbp
0x140004214  retn
```
