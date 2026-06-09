# MSCryptPqDsaGetProperty

- ea: `0x18006ab70`
- end: `0x18006aea7`
- name: `MSCryptPqDsaGetProperty`
- size: `823`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180063170`
- `0x18006ab70`
- `0x18006bcc4`
- `0x18006bcf8`
- `0x18007f765`

## string_xrefs

- `0x18006ae80`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaGetProperty(
        __int64 a1,
        const wchar_t *a2,
        _QWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  unsigned int *v6; // r12
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // rbp
  unsigned __int64 v15; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rbp
  unsigned int v18; // esi
  __int64 v19; // rsi
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // r15
  unsigned __int64 v23; // rdx
  int v24; // r8d
  unsigned int v25; // r9d
  unsigned __int64 i; // rcx
  __int64 v27; // rax
  _QWORD *v28; // r12
  char *v29; // rsi
  __int64 v30; // rbx
  int v32; // [rsp+20h] [rbp-68h] BYREF
  unsigned int v33; // [rsp+24h] [rbp-64h]
  unsigned __int64 v34; // [rsp+38h] [rbp-50h]

  v6 = a5;
  v32 = 0;
  if ( !a5 )
  {
    v10 = 660;
LABEL_3:
    v11 = -1073741811;
    v12 = 3221225485LL;
LABEL_57:
    DebugTraceError(v12, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v10);
    return v11;
  }
  *a5 = 0;
  if ( !a1 )
  {
    v10 = 669;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v10 = 676;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    if ( !a4 )
      goto LABEL_10;
LABEL_13:
    v10 = 684;
    goto LABEL_3;
  }
  if ( !a4 )
    goto LABEL_13;
LABEL_10:
  if ( a6 )
  {
    v10 = 691;
    goto LABEL_3;
  }
  v13 = 2;
  v14 = validatePqDsaKey(a1, 2);
  if ( v14 )
  {
    if ( !wcscmp_0(a2, L"AlgorithmName") )
    {
      v16 = *(_QWORD *)(v14 + 16);
      v17 = *(_QWORD *)(v16 + 8);
      v18 = *(_DWORD *)(v16 + 16);
      goto LABEL_17;
    }
    v19 = *(_QWORD *)(v14 + 24);
    if ( !v19 )
    {
      v10 = 716;
LABEL_56:
      v12 = 3221225480LL;
      v11 = -1073741816;
      goto LABEL_57;
    }
    if ( !wcscmp_0(a2, L"ParameterSetName") )
    {
      v17 = *(_QWORD *)v19;
      v18 = *(_DWORD *)(v19 + 8);
      goto LABEL_17;
    }
    if ( !wcscmp_0(a2, L"SignatureLength") )
    {
      v17 = v19 + 20;
LABEL_33:
      v13 = 4;
      v18 = 4;
      goto LABEL_17;
    }
    if ( !wcscmp_0(a2, L"PublicKeyLength") )
    {
      v20 = *(_DWORD *)(v19 + 16);
LABEL_32:
      v17 = (unsigned __int64)&v32;
      v32 = 8 * v20;
      goto LABEL_33;
    }
    if ( !wcscmp_0(a2, L"KeyLength") )
    {
      if ( *(_DWORD *)(v14 + 8) == 196620 )
      {
        v20 = *(_DWORD *)(v19 + 12);
        goto LABEL_32;
      }
      v10 = 758;
    }
    else
    {
      v10 = 774;
    }
LABEL_30:
    v11 = -1073741637;
    v12 = 3221225659LL;
    goto LABEL_57;
  }
  v21 = validatePqDsaAlgorithm(v15);
  if ( !v21 )
  {
    v10 = 846;
    goto LABEL_56;
  }
  v22 = *(_QWORD *)(v21 + 16);
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v17 = *(_QWORD *)(v22 + 8);
    v18 = *(_DWORD *)(v22 + 16);
    goto LABEL_17;
  }
  if ( wcscmp_0(a2, L"ParameterSetNameList") )
  {
    v10 = 839;
    goto LABEL_30;
  }
  v23 = *(unsigned int *)(v22 + 32);
  v17 = 0;
  v34 = 0;
  v24 = 0;
  v25 = v23;
  if ( v23 )
  {
    for ( i = 0; i < v23; ++i )
    {
      v27 = 3 * i;
      v24 += *(_DWORD *)(16 * v27 + *(_QWORD *)(v22 + 24) + 8);
    }
  }
  v13 = 8;
  v18 = v24 + v25 * 8 + 16;
  v33 = v18;
  if ( a4 < v18 || ((unsigned __int8)a3 & 7) != 0 || (*(_DWORD *)a3 = v23, a3[1] = a3 + 2, !*(_DWORD *)(v22 + 32)) )
  {
LABEL_17:
    if ( !a3 )
      goto LABEL_18;
    goto LABEL_48;
  }
  v28 = a3 + 2;
  v29 = (char *)&a3[v25 + 2];
  do
  {
    *v28 = v29;
    v30 = 6 * v17;
    ++v28;
    memcpy_0(
      v29,
      *(const void **)(*(_QWORD *)(v22 + 24) + 48 * v17),
      *(unsigned int *)(*(_QWORD *)(v22 + 24) + 48 * v17 + 8));
    ++v17;
    v29 += *(unsigned int *)(*(_QWORD *)(v22 + 24) + 8 * v30 + 8);
  }
  while ( v17 < *(unsigned int *)(v22 + 32) );
  v18 = v33;
  v17 = v34;
  v6 = a5;
LABEL_48:
  if ( ((v13 - 1) & (unsigned int)a3) != 0 )
  {
    v11 = -2147483646;
    v10 = 864;
    v12 = 2147483650LL;
    goto LABEL_57;
  }
  if ( a4 < v18 )
  {
    v11 = -1073741789;
    v10 = 871;
    v12 = 3221225507LL;
    goto LABEL_57;
  }
  if ( v17 )
    memcpy_0(a3, (const void *)v17, v18);
LABEL_18:
  *v6 = v18;
  return 0;
}

```

## disassembly

```asm
0x18006ab70  push    rbx
0x18006ab72  push    rbp
0x18006ab73  push    rsi
0x18006ab74  push    rdi
0x18006ab75  push    r12
0x18006ab77  push    r13
0x18006ab79  push    r14
0x18006ab7b  push    r15
0x18006ab7d  sub     rsp, 48h
0x18006ab81  mov     r12, [rsp+88h+arg_20]
0x18006ab89  xor     esi, esi
0x18006ab8b  mov     [rsp+88h+var_68], esi
0x18006ab8f  mov     r14, r8
0x18006ab92  mov     r13d, r9d
0x18006ab95  mov     rbx, rdx
0x18006ab98  mov     r8, rcx
0x18006ab9b  test    r12, r12
0x18006ab9e  jnz     short loc_18006ABB5
0x18006aba0  mov     r9d, 294h
0x18006aba6  mov     ebx, 0C000000Dh
0x18006abab  mov     ecx, 0C000000Dh
0x18006abb0  jmp     loc_18006AE80
0x18006abb5  mov     [r12], esi
0x18006abb9  test    r8, r8
0x18006abbc  jnz     short loc_18006ABC6
0x18006abbe  mov     r9d, 29Dh
0x18006abc4  jmp     short loc_18006ABA6
0x18006abc6  test    rbx, rbx
0x18006abc9  jnz     short loc_18006ABD3
0x18006abcb  mov     r9d, 2A4h
0x18006abd1  jmp     short loc_18006ABA6
0x18006abd3  test    r14, r14
0x18006abd6  jnz     short loc_18006ABEE
0x18006abd8  test    r13d, r13d
0x18006abdb  jnz     short loc_18006ABF3
0x18006abdd  cmp     [rsp+88h+arg_28], esi
0x18006abe4  jz      short loc_18006ABFB
0x18006abe6  mov     r9d, 2B3h
0x18006abec  jmp     short loc_18006ABA6
0x18006abee  test    r13d, r13d
0x18006abf1  jnz     short loc_18006ABDD
0x18006abf3  mov     r9d, 2ACh
0x18006abf9  jmp     short loc_18006ABA6
0x18006abfb  mov     edi, 2
0x18006ac00  mov     edx, edi
0x18006ac02  call    validatePqDsaKey
0x18006ac07  mov     rbp, rax
0x18006ac0a  test    rax, rax
0x18006ac0d  jz      loc_18006ACF9
0x18006ac13  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18006ac1a  mov     rcx, rbx; String1
0x18006ac1d  call    wcscmp_0
0x18006ac22  test    eax, eax
0x18006ac24  jnz     short loc_18006AC45
0x18006ac26  mov     rax, [rbp+10h]
0x18006ac2a  mov     rbp, [rax+8]
0x18006ac2e  mov     esi, [rax+10h]
0x18006ac31  test    r14, r14
0x18006ac34  jnz     loc_18006AE18
0x18006ac3a  mov     [r12], esi
0x18006ac3e  xor     ebx, ebx
0x18006ac40  jmp     loc_18006AE93
0x18006ac45  mov     rsi, [rbp+18h]
0x18006ac49  test    rsi, rsi
0x18006ac4c  jnz     short loc_18006AC59
0x18006ac4e  mov     r9d, 2CCh
0x18006ac54  jmp     loc_18006AE76
0x18006ac59  lea     rdx, aParametersetna; "ParameterSetName"
0x18006ac60  mov     rcx, rbx; String1
0x18006ac63  call    wcscmp_0
0x18006ac68  test    eax, eax
0x18006ac6a  jnz     short loc_18006AC74
0x18006ac6c  mov     rbp, [rsi]
0x18006ac6f  mov     esi, [rsi+8]
0x18006ac72  jmp     short loc_18006AC31
0x18006ac74  lea     rdx, aSignaturelengt; "SignatureLength"
0x18006ac7b  mov     rcx, rbx; String1
0x18006ac7e  call    wcscmp_0
0x18006ac83  test    eax, eax
0x18006ac85  jnz     short loc_18006AC8D
0x18006ac87  lea     rbp, [rsi+14h]
0x18006ac8b  jmp     short loc_18006ACE5
0x18006ac8d  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x18006ac94  mov     rcx, rbx; String1
0x18006ac97  call    wcscmp_0
0x18006ac9c  test    eax, eax
0x18006ac9e  jnz     short loc_18006ACA5
0x18006aca0  mov     eax, [rsi+10h]
0x18006aca3  jmp     short loc_18006ACD9
0x18006aca5  lea     rdx, aKeylength; "KeyLength"
0x18006acac  mov     rcx, rbx; String1
0x18006acaf  call    wcscmp_0
0x18006acb4  test    eax, eax
0x18006acb6  jnz     short loc_18006ACF1
0x18006acb8  cmp     dword ptr [rbp+8], 3000Ch
0x18006acbf  jz      short loc_18006ACD6
0x18006acc1  mov     r9d, 2F6h
0x18006acc7  mov     ebx, 0C00000BBh
0x18006accc  mov     ecx, 0C00000BBh
0x18006acd1  jmp     loc_18006AE80
0x18006acd6  mov     eax, [rsi+0Ch]
0x18006acd9  shl     eax, 3
0x18006acdc  lea     rbp, [rsp+88h+var_68]
0x18006ace1  mov     [rsp+88h+var_68], eax
0x18006ace5  mov     edi, 4
0x18006acea  mov     esi, edi
0x18006acec  jmp     loc_18006AC31
0x18006acf1  mov     r9d, 306h
0x18006acf7  jmp     short loc_18006ACC7
0x18006acf9  mov     rcx, r8
0x18006acfc  call    validatePqDsaAlgorithm
0x18006ad01  test    rax, rax
0x18006ad04  jz      loc_18006AE70
0x18006ad0a  mov     r15, [rax+10h]
0x18006ad0e  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18006ad15  mov     rcx, rbx; String1
0x18006ad18  call    wcscmp_0
0x18006ad1d  test    eax, eax
0x18006ad1f  jnz     short loc_18006AD2E
0x18006ad21  mov     rbp, [r15+8]
0x18006ad25  mov     esi, [r15+10h]
0x18006ad29  jmp     loc_18006AC31
0x18006ad2e  lea     rdx, aParametersetna_0; "ParameterSetNameList"
0x18006ad35  mov     rcx, rbx; String1
0x18006ad38  call    wcscmp_0
0x18006ad3d  test    eax, eax
0x18006ad3f  jnz     loc_18006AE65
0x18006ad45  mov     edx, [r15+20h]
0x18006ad49  mov     rbp, rsi
0x18006ad4c  mov     [rsp+88h+var_50], rsi
0x18006ad51  mov     r8d, esi
0x18006ad54  lea     r9d, ds:0[rdx*8]
0x18006ad5c  test    rdx, rdx
0x18006ad5f  jz      short loc_18006AD7D
0x18006ad61  mov     r10, [r15+18h]
0x18006ad65  mov     rcx, rsi
0x18006ad68  lea     rax, [rcx+rcx*2]
0x18006ad6c  inc     rcx
0x18006ad6f  shl     rax, 4
0x18006ad73  add     r8d, [rax+r10+8]
0x18006ad78  cmp     rcx, rdx
0x18006ad7b  jb      short loc_18006AD68
0x18006ad7d  lea     esi, [r9+10h]
0x18006ad81  mov     edi, 8
0x18006ad86  add     esi, r8d
0x18006ad89  mov     [rsp+88h+var_64], esi
0x18006ad8d  cmp     r13d, esi
0x18006ad90  jb      loc_18006AC31
0x18006ad96  test    r14b, 7
0x18006ad9a  jnz     loc_18006AC31
0x18006ada0  mov     r8d, r9d
0x18006ada3  lea     rcx, [r14+10h]
0x18006ada7  add     r8, 10h
0x18006adab  mov     [r14], edx
0x18006adae  add     r8, r14
0x18006adb1  mov     [r14+8], rcx
0x18006adb5  cmp     [r15+20h], ebp
0x18006adb9  jbe     loc_18006AC31
0x18006adbf  lea     r12, [r14+10h]
0x18006adc3  mov     rsi, r8
0x18006adc6  mov     [r12], rsi
0x18006adca  lea     rbx, ds:0[rbp*2]
0x18006add2  mov     rdx, [r15+18h]
0x18006add6  add     rbx, rbp
0x18006add9  add     rbx, rbx
0x18006addc  mov     rcx, rsi; void *
0x18006addf  add     r12, rdi
0x18006ade2  mov     r8d, [rdx+rbx*8+8]; Size
0x18006ade7  mov     rdx, [rdx+rbx*8]; Src
0x18006adeb  call    memcpy_0
0x18006adf0  mov     rax, [r15+18h]
0x18006adf4  inc     rbp
0x18006adf7  mov     ecx, [rax+rbx*8+8]
0x18006adfb  mov     eax, [r15+20h]
0x18006adff  add     rsi, rcx
0x18006ae02  cmp     rbp, rax
0x18006ae05  jb      short loc_18006ADC6
0x18006ae07  mov     esi, [rsp+88h+var_64]
0x18006ae0b  mov     rbp, [rsp+88h+var_50]
0x18006ae10  mov     r12, [rsp+88h+arg_20]
0x18006ae18  lea     ecx, [rdi-1]
0x18006ae1b  test    r14, rcx
0x18006ae1e  jz      short loc_18006AE32
0x18006ae20  mov     ebx, 80000002h
0x18006ae25  mov     r9d, 360h
0x18006ae2b  mov     ecx, 80000002h
0x18006ae30  jmp     short loc_18006AE80
0x18006ae32  cmp     r13d, esi
0x18006ae35  jnb     short loc_18006AE49
0x18006ae37  mov     ebx, 0C0000023h
0x18006ae3c  mov     r9d, 367h
0x18006ae42  mov     ecx, 0C0000023h
0x18006ae47  jmp     short loc_18006AE80
0x18006ae49  test    rbp, rbp
0x18006ae4c  jz      loc_18006AC3A
0x18006ae52  mov     r8d, esi; Size
0x18006ae55  mov     rdx, rbp; Src
0x18006ae58  mov     rcx, r14; void *
0x18006ae5b  call    memcpy_0
0x18006ae60  jmp     loc_18006AC3A
0x18006ae65  mov     r9d, 347h
0x18006ae6b  jmp     loc_18006ACC7
0x18006ae70  mov     r9d, 34Eh
0x18006ae76  mov     ecx, 0C0000008h
0x18006ae7b  mov     ebx, 0C0000008h
0x18006ae80  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006ae87  lea     rdx, aStatus_0; "status"
0x18006ae8e  call    DebugTraceError
0x18006ae93  mov     eax, ebx
0x18006ae95  add     rsp, 48h
0x18006ae99  pop     r15
0x18006ae9b  pop     r14
0x18006ae9d  pop     r13
0x18006ae9f  pop     r12
0x18006aea1  pop     rdi
0x18006aea2  pop     rsi
0x18006aea3  pop     rbp
0x18006aea4  pop     rbx
0x18006aea5  retn
```
