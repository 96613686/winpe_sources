# CheckEncryptionPadding

- ea: `0x180014d6c`
- end: `0x180014f91`
- name: `CheckEncryptionPadding`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000fb30`

## callees

- `0x180005060`
- `0x1800066f0`
- `0x180014d6c`
- `0x18001620c`
- `0x180016298`
- `0x180016efc`
- `0x18001aae4`

## string_xrefs

- `0x180014da0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180014e65`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180014f61`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall CheckEncryptionPadding(
        char a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8)
{
  BCRYPT_HANDLE v8; // rdi
  unsigned int v12; // ebx
  __int64 v13; // r8
  unsigned __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  NTSTATUS Property; // eax
  __int64 v19; // rcx
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-18h] BYREF
  UCHAR v22[4]; // [rsp+54h] [rbp-14h] BYREF
  BCRYPT_HANDLE hObject[2]; // [rsp+58h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+B8h] [rbp+50h] BYREF

  v8 = 0;
  hObject[0] = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v22 = 0;
  pcbResult = 0;
  if ( a5 < a4 )
    goto LABEL_2;
  if ( (a1 & 2) != 0 )
  {
    hObject[0] = 0;
    v13 = (unsigned int)SymCryptRsaPkcs1RemoveEncryptionPadding(a3, a4, a5, a6, a7, (__int64)hObject);
    v14 = 0;
    v12 = -1073741811;
    do
    {
      v15 = HIDWORD(symmErrorsMap[v14]) ^ v12;
      v16 = -(v13 ^ LODWORD(symmErrorsMap[v14++]));
      v12 ^= v15 & ~HIDWORD(v16);
    }
    while ( v14 < 3 );
    *a8 = hObject[0];
    return v12;
  }
  if ( (a1 & 4) == 0 )
  {
    v12 = -1073741811;
    v19 = 3221225485LL;
    goto LABEL_19;
  }
  if ( !a2 || !*(_QWORD *)a2 )
  {
LABEL_2:
    v12 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    return v12;
  }
  v17 = CachedOpenAlgorithmProvider(hObject);
  v12 = v17;
  if ( v17 < 0 )
  {
    DebugTraceError((unsigned int)v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
    v8 = hObject[0];
    goto LABEL_20;
  }
  v8 = hObject[0];
  Property = BCryptGetProperty(hObject[0], L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  v12 = Property;
  if ( Property < 0
    || (Property = BCryptGetProperty(v8, L"HashDigestLength", v22, 4u, &pcbResult, 0), v12 = Property, Property < 0)
    || (Property = CheckOAEPPadding(
                     v8,
                     *(unsigned int *)v22,
                     *(unsigned int *)pbOutput,
                     *(_QWORD *)(a2 + 8),
                     *(_DWORD *)(a2 + 16),
                     a3,
                     a4,
                     a6,
                     a7,
                     a8),
        v12 = Property,
        Property < 0) )
  {
    v19 = (unsigned int)Property;
LABEL_19:
    DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
  }
LABEL_20:
  if ( v8 )
    CachedCloseAlgorithmProvider(v8);
  return v12;
}

```

## disassembly

```asm
0x180014d6c  push    rbp
0x180014d6e  push    rbx
0x180014d6f  push    rsi
0x180014d70  push    rdi
0x180014d71  push    r14
0x180014d73  push    r15
0x180014d75  mov     rbp, rsp
0x180014d78  sub     rsp, 68h
0x180014d7c  xor     edi, edi
0x180014d7e  mov     r14d, r9d
0x180014d81  mov     r15, r8
0x180014d84  mov     rsi, rdx
0x180014d87  mov     [rbp+hObject], rdi
0x180014d8b  mov     dword ptr [rbp+pbOutput], edi
0x180014d8e  mov     dword ptr [rbp+var_14], edi
0x180014d91  mov     [rbp+arg_18], edi
0x180014d94  cmp     [rbp+arg_20], r9d
0x180014d98  jnb     short loc_180014DC2
0x180014d9a  mov     r9d, 0EC7h
0x180014da0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014da7  mov     ecx, 0C000000Dh
0x180014dac  lea     rdx, aStatus; "Status"
0x180014db3  mov     ebx, 0C000000Dh
0x180014db8  call    DebugTraceError
0x180014dbd  jmp     loc_180014F81
0x180014dc2  test    cl, 2
0x180014dc5  jz      short loc_180014E32
0x180014dc7  mov     eax, [rbp+arg_30]
0x180014dca  lea     rcx, [rbp+hObject]
0x180014dce  mov     r8d, [rbp+arg_20]
0x180014dd2  mov     rdx, r14
0x180014dd5  mov     r9, [rbp+arg_28]
0x180014dd9  mov     qword ptr [rsp+68h+dwFlags], rcx
0x180014dde  mov     rcx, r15
0x180014de1  mov     [rbp+hObject], rdi
0x180014de5  mov     [rsp+68h+pcbResult], rax
0x180014dea  call    SymCryptRsaPkcs1RemoveEncryptionPadding
0x180014def  mov     r8d, eax
0x180014df2  lea     r9, symmErrorsMap
0x180014df9  xor     edx, edx
0x180014dfb  mov     ebx, 0C000000Dh
0x180014e00  mov     ecx, [r9+rdx*8]
0x180014e04  mov     eax, ebx
0x180014e06  xor     eax, [r9+rdx*8+4]
0x180014e0b  xor     rcx, r8
0x180014e0e  neg     rcx
0x180014e11  inc     rdx
0x180014e14  sar     rcx, 20h
0x180014e18  not     ecx
0x180014e1a  and     ecx, eax
0x180014e1c  xor     ebx, ecx
0x180014e1e  cmp     rdx, 3
0x180014e22  jb      short loc_180014E00
0x180014e24  mov     rcx, [rbp+arg_38]
0x180014e28  mov     eax, dword ptr [rbp+hObject]
0x180014e2b  mov     [rcx], eax
0x180014e2d  jmp     loc_180014F81
0x180014e32  test    cl, 4
0x180014e35  jz      loc_180014F51
0x180014e3b  test    rsi, rsi
0x180014e3e  jz      loc_180014F46
0x180014e44  mov     rdx, [rdx]
0x180014e47  test    rdx, rdx
0x180014e4a  jz      loc_180014F46
0x180014e50  lea     rcx, [rbp+hObject]
0x180014e54  call    CachedOpenAlgorithmProvider
0x180014e59  mov     ebx, eax
0x180014e5b  test    eax, eax
0x180014e5d  jns     short loc_180014E83
0x180014e5f  mov     r9d, 0EF0h
0x180014e65  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014e6c  lea     rdx, aStatus; "Status"
0x180014e73  mov     ecx, eax
0x180014e75  call    DebugTraceError
0x180014e7a  mov     rdi, [rbp+hObject]
0x180014e7e  jmp     loc_180014F74
0x180014e83  mov     [rsp+68h+dwFlags], edi; dwFlags
0x180014e87  lea     rax, [rbp+arg_18]
0x180014e8b  mov     rdi, [rbp+hObject]
0x180014e8f  lea     r8, [rbp+pbOutput]; pbOutput
0x180014e93  mov     rcx, rdi; hObject
0x180014e96  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180014e9b  mov     r9d, 4; cbOutput
0x180014ea1  lea     rdx, aObjectlength; "ObjectLength"
0x180014ea8  call    BCryptGetProperty
0x180014ead  mov     ebx, eax
0x180014eaf  test    eax, eax
0x180014eb1  jns     short loc_180014EC0
0x180014eb3  mov     r9d, 0EFCh
0x180014eb9  mov     ecx, eax
0x180014ebb  jmp     loc_180014F61
0x180014ec0  lea     rax, [rbp+arg_18]
0x180014ec4  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180014ecc  mov     r9d, 4; cbOutput
0x180014ed2  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180014ed7  lea     r8, [rbp+var_14]; pbOutput
0x180014edb  mov     rcx, rdi; hObject
0x180014ede  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180014ee5  call    BCryptGetProperty
0x180014eea  mov     ebx, eax
0x180014eec  test    eax, eax
0x180014eee  jns     short loc_180014EF8
0x180014ef0  mov     r9d, 0F08h
0x180014ef6  jmp     short loc_180014EB9
0x180014ef8  mov     rax, [rbp+arg_38]
0x180014efc  mov     rcx, rdi
0x180014eff  mov     r9, [rsi+8]
0x180014f03  mov     r8d, dword ptr [rbp+pbOutput]
0x180014f07  mov     edx, dword ptr [rbp+var_14]
0x180014f0a  mov     [rsp+68h+var_20], rax
0x180014f0f  mov     eax, [rbp+arg_30]
0x180014f12  mov     [rsp+68h+var_28], eax
0x180014f16  mov     rax, [rbp+arg_28]
0x180014f1a  mov     [rsp+68h+var_30], rax
0x180014f1f  mov     eax, [rsi+10h]
0x180014f22  mov     [rsp+68h+var_38], r14d
0x180014f27  mov     qword ptr [rsp+68h+dwFlags], r15
0x180014f2c  mov     dword ptr [rsp+68h+pcbResult], eax
0x180014f30  call    CheckOAEPPadding
0x180014f35  mov     ebx, eax
0x180014f37  test    eax, eax
0x180014f39  jns     short loc_180014F74
0x180014f3b  mov     r9d, 0F18h
0x180014f41  jmp     loc_180014EB9
0x180014f46  mov     r9d, 0EE5h
0x180014f4c  jmp     loc_180014DA0
0x180014f51  mov     ebx, 0C000000Dh
0x180014f56  mov     r9d, 0F1Fh
0x180014f5c  mov     ecx, 0C000000Dh
0x180014f61  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014f68  lea     rdx, aStatus; "Status"
0x180014f6f  call    DebugTraceError
0x180014f74  test    rdi, rdi
0x180014f77  jz      short loc_180014F81
0x180014f79  mov     rcx, rdi; hAlgorithm
0x180014f7c  call    CachedCloseAlgorithmProvider
0x180014f81  mov     eax, ebx
0x180014f83  add     rsp, 68h
0x180014f87  pop     r15
0x180014f89  pop     r14
0x180014f8b  pop     rdi
0x180014f8c  pop     rsi
0x180014f8d  pop     rbx
0x180014f8e  pop     rbp
0x180014f8f  retn
```
