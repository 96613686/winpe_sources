# MSCryptEccGetAlgProperty

- ea: `0x18004490c`
- end: `0x180044b8c`
- name: `MSCryptEccGetAlgProperty`
- size: `640`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180043fa0`
- `0x180044180`

## callees

- `0x18000ecb0`
- `0x18004490c`
- `0x180047ab0`
- `0x18004d844`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x180044b6b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccGetAlgProperty(
        __int64 a1,
        const wchar_t *a2,
        int *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6,
        int a7)
{
  int CurveNameList; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  _DWORD *v15; // rdx
  unsigned int v16; // r8d
  int *v17; // rcx
  size_t v18; // r8
  const void *v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  __int64 v25; // rax
  int v26; // eax
  int v27; // edx
  int v28; // ecx
  __int64 v30[7]; // [rsp+30h] [rbp-38h] BYREF

  v30[0] = 0;
  a6 = 0;
  CurveNameList = ValidateEccAlgorithm(a1, 0, a7, &a6, v30);
  v11 = CurveNameList;
  if ( CurveNameList < 0 )
  {
    v12 = 3286;
LABEL_3:
    v13 = (unsigned int)CurveNameList;
LABEL_40:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
    return v11;
  }
  if ( !wcscmp_0(a2, L"ECCParameters") )
  {
    v14 = *(_QWORD **)(v30[0] + 16);
    if ( !v14 )
    {
      v12 = 3295;
LABEL_7:
      v11 = -1073741811;
      v13 = 3221225485LL;
      goto LABEL_40;
    }
    v15 = (_DWORD *)*v14;
    if ( !v15 )
    {
      v12 = 3303;
      goto LABEL_7;
    }
    v16 = v15[5] + v15[6] + 5 * v15[3] + v15[4] + 28;
    *a5 = v16;
    if ( !a3 )
    {
      v11 = 0;
      v12 = 3316;
      v13 = 0;
      goto LABEL_40;
    }
    if ( a4 < v16 )
      return (unsigned int)-1073741789;
    *a3 = 1;
    v17 = a3 + 7;
    a3[1] = v15[1];
    a3[2] = v15[2];
    a3[3] = v15[3];
    a3[4] = v15[4];
    a3[5] = v15[5];
    a3[6] = v15[6];
    v18 = (unsigned int)(v15[4] + v15[5] + v15[6] + 5 * v15[3]);
    v19 = v15 + 7;
    goto LABEL_24;
  }
  if ( wcscmp_0(a2, L"ECCCurveName") )
  {
    if ( !wcscmp_0(a2, L"ECCCurveNameList") )
    {
      CurveNameList = GetCurveNameList((__int64)a3, a4, a5);
      v11 = CurveNameList;
      if ( CurveNameList < 0 )
      {
        v12 = 3379;
        goto LABEL_3;
      }
      return 0;
    }
    if ( !wcscmp_0(a2, L"KeyLengths") )
    {
      *a5 = 12;
      if ( !a3 )
        return 0;
      if ( a4 < 0xC )
        return (unsigned int)-1073741789;
      v25 = *(_QWORD *)(v30[0] + 16);
      if ( !v25 )
      {
        v26 = 112;
        v27 = 528;
        v28 = 1;
LABEL_37:
        *a3 = v26;
        a3[1] = v27;
        a3[2] = v28;
        return 0;
      }
      v26 = *(_DWORD *)(*(_QWORD *)(v25 + 8) + 12LL);
      if ( v26 )
      {
        v27 = v26;
        v28 = 0;
        goto LABEL_37;
      }
      v12 = 3421;
    }
    else
    {
      v12 = 3433;
    }
    v13 = 3221225659LL;
    v11 = -1073741637;
    goto LABEL_40;
  }
  v20 = v30[0];
  v21 = *(_QWORD *)(v30[0] + 16);
  if ( !v21 || (v22 = *(_QWORD *)(v21 + 16)) == 0 )
  {
    v12 = 3351;
    goto LABEL_7;
  }
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)(v22 + 2 * v23) );
  v24 = 2 * v23 + 2;
  *a5 = v24;
  if ( !a3 )
    return 0;
  if ( a4 >= v24 )
  {
    v18 = v24;
    v17 = a3;
    v19 = *(const void **)(*(_QWORD *)(v20 + 16) + 16LL);
LABEL_24:
    memcpy_0(v17, v19, v18);
    return 0;
  }
  return (unsigned int)-1073741789;
}

```

## disassembly

```asm
0x18004490c  mov     r11, rsp
0x18004490f  push    rbx
0x180044910  push    rbp
0x180044911  push    rsi
0x180044912  push    rdi
0x180044913  push    r14
0x180044915  sub     rsp, 40h
0x180044919  mov     ebp, r9d
0x18004491c  lea     rax, [r11-38h]
0x180044920  mov     rdi, r8
0x180044923  mov     [r11-48h], rax
0x180044927  mov     r8d, [rsp+68h+arg_30]
0x18004492f  lea     r9, [r11+30h]
0x180044933  mov     rsi, rdx
0x180044936  xor     r14d, r14d
0x180044939  xor     edx, edx
0x18004493b  mov     [r11-38h], r14
0x18004493f  mov     [r11+30h], r14d
0x180044943  call    ValidateEccAlgorithm
0x180044948  mov     ebx, eax
0x18004494a  test    eax, eax
0x18004494c  jns     short loc_18004495B
0x18004494e  mov     r9d, 0CD6h
0x180044954  mov     ecx, eax
0x180044956  jmp     loc_180044B6B
0x18004495b  lea     rdx, aEccparameters; "ECCParameters"
0x180044962  mov     rcx, rsi; String1
0x180044965  call    wcscmp_0
0x18004496a  test    eax, eax
0x18004496c  jnz     loc_180044A32
0x180044972  mov     rax, [rsp+68h+var_38]
0x180044977  mov     rdx, [rax+10h]
0x18004497b  test    rdx, rdx
0x18004497e  jnz     short loc_180044995
0x180044980  mov     r9d, 0CDFh
0x180044986  mov     ebx, 0C000000Dh
0x18004498b  mov     ecx, 0C000000Dh
0x180044990  jmp     loc_180044B6B
0x180044995  mov     rdx, [rdx]
0x180044998  test    rdx, rdx
0x18004499b  jnz     short loc_1800449A5
0x18004499d  mov     r9d, 0CE7h
0x1800449a3  jmp     short loc_180044986
0x1800449a5  mov     eax, [rdx+0Ch]
0x1800449a8  mov     r8d, [rdx+10h]
0x1800449ac  add     r8d, 1Ch
0x1800449b0  lea     ecx, [rax+rax*4]
0x1800449b3  mov     rax, [rsp+68h+arg_20]
0x1800449bb  add     ecx, [rdx+18h]
0x1800449be  add     ecx, [rdx+14h]
0x1800449c1  add     r8d, ecx
0x1800449c4  mov     [rax], r8d
0x1800449c7  test    rdi, rdi
0x1800449ca  jnz     short loc_1800449DC
0x1800449cc  mov     ebx, r14d
0x1800449cf  mov     r9d, 0CF4h
0x1800449d5  xor     ecx, ecx
0x1800449d7  jmp     loc_180044B6B
0x1800449dc  cmp     ebp, r8d
0x1800449df  jnb     short loc_1800449EB
0x1800449e1  mov     ebx, 0C0000023h
0x1800449e6  jmp     loc_180044B7E
0x1800449eb  mov     dword ptr [rdi], 1
0x1800449f1  lea     rcx, [rdi+1Ch]
0x1800449f5  mov     eax, [rdx+4]
0x1800449f8  mov     [rdi+4], eax
0x1800449fb  mov     eax, [rdx+8]
0x1800449fe  mov     [rdi+8], eax
0x180044a01  mov     eax, [rdx+0Ch]
0x180044a04  mov     [rdi+0Ch], eax
0x180044a07  mov     eax, [rdx+10h]
0x180044a0a  mov     [rdi+10h], eax
0x180044a0d  mov     eax, [rdx+14h]
0x180044a10  mov     [rdi+14h], eax
0x180044a13  mov     eax, [rdx+18h]
0x180044a16  mov     [rdi+18h], eax
0x180044a19  mov     eax, [rdx+0Ch]
0x180044a1c  lea     r8d, [rax+rax*4]
0x180044a20  add     r8d, [rdx+18h]
0x180044a24  add     r8d, [rdx+14h]
0x180044a28  add     r8d, [rdx+10h]
0x180044a2c  add     rdx, 1Ch
0x180044a30  jmp     short loc_180044A9E
0x180044a32  lea     rdx, aEcccurvename; "ECCCurveName"
0x180044a39  mov     rcx, rsi; String1
0x180044a3c  call    wcscmp_0
0x180044a41  test    eax, eax
0x180044a43  jnz     short loc_180044AB0
0x180044a45  mov     rdx, [rsp+68h+var_38]
0x180044a4a  mov     rax, [rdx+10h]
0x180044a4e  test    rax, rax
0x180044a51  jz      short loc_180044AA5
0x180044a53  mov     rcx, [rax+10h]
0x180044a57  test    rcx, rcx
0x180044a5a  jz      short loc_180044AA5
0x180044a5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044a60  inc     rax
0x180044a63  cmp     [rcx+rax*2], r14w
0x180044a68  jnz     short loc_180044A60
0x180044a6a  lea     ecx, ds:2[rax*2]
0x180044a71  mov     rax, [rsp+68h+arg_20]
0x180044a79  mov     [rax], ecx
0x180044a7b  test    rdi, rdi
0x180044a7e  jnz     short loc_180044A88
0x180044a80  mov     ebx, r14d
0x180044a83  jmp     loc_180044B7E
0x180044a88  cmp     ebp, ecx
0x180044a8a  jb      loc_1800449E1
0x180044a90  mov     rdx, [rdx+10h]
0x180044a94  mov     r8d, ecx; Size
0x180044a97  mov     rcx, rdi; void *
0x180044a9a  mov     rdx, [rdx+10h]; Src
0x180044a9e  call    memcpy_0
0x180044aa3  jmp     short loc_180044A80
0x180044aa5  mov     r9d, 0D17h
0x180044aab  jmp     loc_180044986
0x180044ab0  lea     rdx, aEcccurvenameli; "ECCCurveNameList"
0x180044ab7  mov     rcx, rsi; String1
0x180044aba  call    wcscmp_0
0x180044abf  test    eax, eax
0x180044ac1  jnz     short loc_180044AE6
0x180044ac3  mov     r8, [rsp+68h+arg_20]
0x180044acb  mov     edx, ebp
0x180044acd  mov     rcx, rdi
0x180044ad0  call    GetCurveNameList
0x180044ad5  mov     ebx, eax
0x180044ad7  test    eax, eax
0x180044ad9  jns     short loc_180044A80
0x180044adb  mov     r9d, 0D33h
0x180044ae1  jmp     loc_180044954
0x180044ae6  lea     rdx, aKeylengths; "KeyLengths"
0x180044aed  mov     rcx, rsi; String1
0x180044af0  call    wcscmp_0
0x180044af5  test    eax, eax
0x180044af7  jnz     short loc_180044B5B
0x180044af9  mov     rax, [rsp+68h+arg_20]
0x180044b01  mov     dword ptr [rax], 0Ch
0x180044b07  test    rdi, rdi
0x180044b0a  jz      loc_180044A80
0x180044b10  cmp     ebp, 0Ch
0x180044b13  jb      loc_1800449E1
0x180044b19  mov     rax, [rsp+68h+var_38]
0x180044b1e  mov     rax, [rax+10h]
0x180044b22  test    rax, rax
0x180044b25  jnz     short loc_180044B36
0x180044b27  mov     eax, 70h ; 'p'
0x180044b2c  mov     edx, 210h
0x180044b31  lea     ecx, [rax-6Fh]
0x180044b34  jmp     short loc_180044B4E
0x180044b36  mov     rax, [rax+8]
0x180044b3a  mov     eax, [rax+0Ch]
0x180044b3d  test    eax, eax
0x180044b3f  jnz     short loc_180044B49
0x180044b41  mov     r9d, 0D5Dh
0x180044b47  jmp     short loc_180044B61
0x180044b49  mov     edx, eax
0x180044b4b  mov     ecx, r14d
0x180044b4e  mov     [rdi], eax
0x180044b50  mov     [rdi+4], edx
0x180044b53  mov     [rdi+8], ecx
0x180044b56  jmp     loc_180044A80
0x180044b5b  mov     r9d, 0D69h
0x180044b61  mov     ecx, 0C00000BBh
0x180044b66  mov     ebx, 0C00000BBh
0x180044b6b  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044b72  lea     rdx, aStatus; "Status"
0x180044b79  call    DebugTraceError
0x180044b7e  mov     eax, ebx
0x180044b80  add     rsp, 40h
0x180044b84  pop     r14
0x180044b86  pop     rdi
0x180044b87  pop     rsi
0x180044b88  pop     rbp
0x180044b89  pop     rbx
0x180044b8a  retn
```
