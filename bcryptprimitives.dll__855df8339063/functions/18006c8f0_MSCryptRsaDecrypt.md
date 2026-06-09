# MSCryptRsaDecrypt

- ea: `0x18006c8f0`
- end: `0x18006caf3`
- name: `MSCryptRsaDecrypt`
- size: `515`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, __int64, int, unsigned int *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180067358`

## callees

- `0x18000ecb0`
- `0x18003cfd4`
- `0x18003d968`
- `0x18003ded4`
- `0x18003dfe4`
- `0x180054120`
- `0x18006c8f0`
- `0x180075424`

## string_xrefs

- `0x18006cac6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaDecrypt(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        unsigned int *a9,
        int a10)
{
  unsigned int v10; // esi
  __int64 v14; // r9
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // r8d
  __int64 v19; // rbp
  __int64 v20; // r9
  unsigned int v21; // ebx
  unsigned int v22; // eax
  __int64 SymCryptHashAlgorithm; // r9

  v10 = 0;
  if ( (a10 & 0xFFFFFFF8) != 0 )
  {
    v14 = 1882;
LABEL_3:
    v15 = -1073741811;
    v16 = 3221225485LL;
LABEL_32:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v14);
    goto LABEL_33;
  }
  v17 = validateMSCryptRsaKey();
  v19 = v17;
  if ( !v17 || !*(_DWORD *)(v17 + 16) )
  {
    v15 = -1073741816;
    v14 = 1892;
    v16 = 3221225480LL;
    goto LABEL_32;
  }
  if ( !a2 || (v20 = *(_QWORD *)(v17 + 32), v21 = (unsigned int)(*(_DWORD *)(v20 + 16) + 7) >> 3, a3 < v21) )
  {
    v14 = 1902;
    goto LABEL_3;
  }
  if ( v18 && (v18 & 1) == 0 )
  {
    if ( (v18 & 2) != 0 )
    {
      if ( a3 > v21 )
        a3 = (unsigned int)(*(_DWORD *)(v20 + 16) + 7) >> 3;
      v22 = SymCryptRsaPkcs1Decrypt(v20, a2, a3, v20);
    }
    else
    {
      v22 = 0;
      if ( (v18 & 4) == 0 )
        goto LABEL_29;
      if ( !a4 || !*(_QWORD *)a4 )
      {
        v14 = 1949;
        goto LABEL_3;
      }
      SymCryptHashAlgorithm = GetSymCryptHashAlgorithm(*(_QWORD *)a4);
      if ( !SymCryptHashAlgorithm )
      {
        v14 = 1957;
        goto LABEL_3;
      }
      if ( a3 > v21 )
        a3 = v21;
      v22 = SymCryptRsaOaepDecrypt(
              *(_QWORD *)(v19 + 32),
              a2,
              a3,
              SymCryptHashAlgorithm,
              SymCryptHashAlgorithm,
              *(_QWORD *)(a4 + 8),
              *(unsigned int *)(a4 + 16));
    }
    v10 = 0;
LABEL_29:
    v15 = SymcryptErrorCodeToNtStatusScs(v22);
    goto LABEL_33;
  }
  v10 = (unsigned int)(*(_DWORD *)(v20 + 16) + 7) >> 3;
  if ( a7 )
  {
    if ( a3 > v21 )
      a3 = (unsigned int)(*(_DWORD *)(v20 + 16) + 7) >> 3;
    v22 = SymCryptRsaRawDecrypt(v20, a2, a3, v20);
    goto LABEL_29;
  }
  v15 = 0;
LABEL_33:
  *a9 = v10;
  return v15;
}

```

## disassembly

```asm
0x18006c8f0  push    rbx
0x18006c8f2  push    rbp
0x18006c8f3  push    rsi
0x18006c8f4  push    rdi
0x18006c8f5  push    r14
0x18006c8f7  push    r15
0x18006c8f9  sub     rsp, 78h
0x18006c8fd  xor     esi, esi
0x18006c8ff  mov     edi, r8d
0x18006c902  mov     r8d, [rsp+0A8h+arg_48]
0x18006c90a  mov     r14, r9
0x18006c90d  mov     [rsp+0A8h+var_48], rsi
0x18006c912  mov     r15, rdx
0x18006c915  test    r8d, 0FFFFFFF8h
0x18006c91c  jz      short loc_18006C933
0x18006c91e  mov     r9d, 75Ah
0x18006c924  mov     ebx, 0C000000Dh
0x18006c929  mov     ecx, 0C000000Dh
0x18006c92e  jmp     loc_18006CAC6
0x18006c933  call    validateMSCryptRsaKey
0x18006c938  mov     rbp, rax
0x18006c93b  test    rax, rax
0x18006c93e  jz      loc_18006CAB6
0x18006c944  cmp     [rax+10h], esi
0x18006c947  jz      loc_18006CAB6
0x18006c94d  test    r15, r15
0x18006c950  jz      loc_18006CAAB
0x18006c956  mov     r9, [rax+20h]
0x18006c95a  mov     ebx, [r9+10h]
0x18006c95e  add     ebx, 7
0x18006c961  shr     ebx, 3
0x18006c964  cmp     edi, ebx
0x18006c966  jb      loc_18006CAAB
0x18006c96c  test    r8d, r8d
0x18006c96f  jz      loc_18006CA62
0x18006c975  test    r8b, 1
0x18006c979  jnz     loc_18006CA62
0x18006c97f  test    r8b, 2
0x18006c983  jz      short loc_18006C9CC
0x18006c985  mov     eax, [rsp+0A8h+arg_38]
0x18006c98c  mov     rcx, r9
0x18006c98f  cmp     eax, ebx
0x18006c991  cmova   eax, ebx
0x18006c994  cmp     edi, ebx
0x18006c996  mov     edx, eax
0x18006c998  lea     rax, [rsp+0A8h+var_48]
0x18006c99d  mov     [rsp+0A8h+var_70], rax
0x18006c9a2  cmova   edi, ebx
0x18006c9a5  mov     rax, [rsp+0A8h+arg_30]
0x18006c9ad  mov     [rsp+0A8h+var_78], rdx
0x18006c9b2  mov     rdx, r15
0x18006c9b5  mov     r8d, edi
0x18006c9b8  mov     [rsp+0A8h+var_80], rax
0x18006c9bd  call    SymCryptRsaPkcs1Decrypt
0x18006c9c2  mov     rsi, [rsp+0A8h+var_48]
0x18006c9c7  jmp     loc_18006CAA0
0x18006c9cc  xor     eax, eax
0x18006c9ce  test    r8b, 4
0x18006c9d2  jz      loc_18006CAA0
0x18006c9d8  test    r14, r14
0x18006c9db  jz      short loc_18006CA57
0x18006c9dd  mov     rcx, [r14]
0x18006c9e0  test    rcx, rcx
0x18006c9e3  jz      short loc_18006CA57
0x18006c9e5  call    GetSymCryptHashAlgorithm
0x18006c9ea  mov     r9, rax
0x18006c9ed  test    rax, rax
0x18006c9f0  jnz     short loc_18006C9FD
0x18006c9f2  mov     r9d, 7A5h
0x18006c9f8  jmp     loc_18006C924
0x18006c9fd  mov     eax, [rsp+0A8h+arg_38]
0x18006ca04  cmp     eax, ebx
0x18006ca06  mov     ecx, [r14+10h]
0x18006ca0a  cmova   eax, ebx
0x18006ca0d  cmp     edi, ebx
0x18006ca0f  mov     edx, eax
0x18006ca11  lea     rax, [rsp+0A8h+var_48]
0x18006ca16  mov     [rsp+0A8h+var_58], rax
0x18006ca1b  cmova   edi, ebx
0x18006ca1e  mov     rax, [rsp+0A8h+arg_30]
0x18006ca26  mov     [rsp+0A8h+var_60], rdx
0x18006ca2b  mov     rdx, r15
0x18006ca2e  mov     [rsp+0A8h+var_68], rax
0x18006ca33  mov     rax, [r14+8]
0x18006ca37  mov     [rsp+0A8h+var_78], rcx
0x18006ca3c  mov     rcx, [rbp+20h]
0x18006ca40  mov     [rsp+0A8h+var_80], rax
0x18006ca45  mov     r8d, edi
0x18006ca48  mov     [rsp+0A8h+var_88], r9
0x18006ca4d  call    SymCryptRsaOaepDecrypt
0x18006ca52  jmp     loc_18006C9C2
0x18006ca57  mov     r9d, 79Dh
0x18006ca5d  jmp     loc_18006C924
0x18006ca62  mov     rdx, [rsp+0A8h+arg_30]
0x18006ca6a  mov     esi, ebx
0x18006ca6c  test    rdx, rdx
0x18006ca6f  jnz     short loc_18006CA75
0x18006ca71  xor     ebx, ebx
0x18006ca73  jmp     short loc_18006CAD9
0x18006ca75  mov     eax, [rsp+0A8h+arg_38]
0x18006ca7c  cmp     eax, ebx
0x18006ca7e  cmova   eax, ebx
0x18006ca81  cmp     edi, ebx
0x18006ca83  mov     ecx, eax
0x18006ca85  mov     [rsp+0A8h+var_78], rcx
0x18006ca8a  cmova   edi, ebx
0x18006ca8d  mov     [rsp+0A8h+var_80], rdx
0x18006ca92  mov     rcx, r9
0x18006ca95  mov     r8d, edi
0x18006ca98  mov     rdx, r15
0x18006ca9b  call    SymCryptRsaRawDecrypt
0x18006caa0  mov     ecx, eax
0x18006caa2  call    SymcryptErrorCodeToNtStatusScs
0x18006caa7  mov     ebx, eax
0x18006caa9  jmp     short loc_18006CAD9
0x18006caab  mov     r9d, 76Eh
0x18006cab1  jmp     loc_18006C924
0x18006cab6  mov     ebx, 0C0000008h
0x18006cabb  mov     r9d, 764h
0x18006cac1  mov     ecx, 0C0000008h
0x18006cac6  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006cacd  lea     rdx, aStatus; "Status"
0x18006cad4  call    DebugTraceError
0x18006cad9  mov     rax, [rsp+0A8h+arg_40]
0x18006cae1  mov     [rax], esi
0x18006cae3  mov     eax, ebx
0x18006cae5  add     rsp, 78h
0x18006cae9  pop     r15
0x18006caeb  pop     r14
0x18006caed  pop     rdi
0x18006caee  pop     rsi
0x18006caef  pop     rbp
0x18006caf0  pop     rbx
0x18006caf1  retn
```
