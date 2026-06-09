# ApplySignaturePadding

- ea: `0x180016b60`
- end: `0x180016ef4`
- name: `ApplySignaturePadding`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800101c0`

## callees

- `0x180004200`
- `0x180005060`
- `0x1800066f0`
- `0x180009430`
- `0x18000f6a8`
- `0x18001620c`
- `0x180016298`
- `0x1800168c8`
- `0x180016b60`

## string_xrefs

- `0x180016bb8`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180016be8`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180016cea`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180016db6`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`
- `0x180016eb8`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall ApplySignaturePadding(char a1, _QWORD *a2, __int64 a3, int a4, __int64 a5, int a6)
{
  BCRYPT_HANDLE v6; // rsi
  __int64 v7; // rdi
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  NTSTATUS Property; // eax
  __int64 v13; // rcx
  NTSTATUS v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-10h] BYREF
  UCHAR v19[4]; // [rsp+54h] [rbp-Ch] BYREF
  BCRYPT_HANDLE hObject; // [rsp+58h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+90h] [rbp+30h] BYREF

  v6 = 0;
  v7 = 0;
  hObject = 0;
  *(_DWORD *)v19 = 0;
  *(_DWORD *)pbOutput = 0;
  cbOutput = 0;
  if ( (a1 & 2) == 0 )
  {
    if ( (a1 & 8) != 0 )
    {
      if ( !a2 || !*a2 )
        goto LABEL_3;
      if ( (int)CachedOpenAlgorithmProvider(&hObject) < 0 )
      {
        v9 = -1073741637;
        DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
        goto LABEL_8;
      }
      v6 = hObject;
      Property = BCryptGetProperty(hObject, L"ObjectLength", v19, 4u, &cbOutput, 0);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_10;
      Property = BCryptGetProperty(v6, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_10;
      Property = ApplyPSSPaddingSalted(v6, *(unsigned int *)pbOutput, *(unsigned int *)v19);
      v9 = Property;
      if ( Property < 0 )
        goto LABEL_10;
      goto LABEL_32;
    }
    goto LABEL_35;
  }
  if ( !a2 )
  {
LABEL_3:
    v9 = -1073741811;
    v10 = 3221225485LL;
LABEL_4:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
    return v9;
  }
  if ( !*a2 )
  {
    v16 = ApplyPKCS1SigningFormat(0, 0, a5, a6, 0);
    v9 = v16;
    if ( v16 < 0 )
    {
      v10 = (unsigned int)v16;
      goto LABEL_4;
    }
    goto LABEL_32;
  }
  v11 = CachedOpenAlgorithmProvider(&hObject);
  if ( v11 < 0 )
  {
    DebugTraceError((unsigned int)v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
    v9 = -1073741637;
LABEL_8:
    v6 = hObject;
    goto LABEL_37;
  }
  v6 = hObject;
  Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &cbOutput, 0);
  v9 = Property;
  if ( Property < 0 )
    goto LABEL_10;
  if ( *(_DWORD *)pbOutput != a4 )
  {
LABEL_35:
    v13 = 3221225485LL;
    v9 = -1073741811;
    goto LABEL_36;
  }
  Property = BCryptGetProperty(v6, L"HashOIDList", 0, 0, &cbOutput, 0);
  v9 = Property;
  if ( Property >= 0 )
  {
    v7 = SafeAllocaAllocateFromHeap(cbOutput);
    if ( !v7 )
    {
      v9 = -1073741801;
      v13 = 3221225495LL;
      goto LABEL_36;
    }
    v14 = BCryptGetProperty(v6, L"HashOIDList", (PUCHAR)v7, cbOutput, &cbOutput, 0);
    v9 = v14;
    if ( v14 < 0 )
      goto LABEL_16;
    if ( !*(_DWORD *)v7 )
    {
      v9 = -1073741595;
      v15 = 3221225701LL;
      goto LABEL_17;
    }
    v14 = ApplyPKCS1SigningFormat(*(void **)(*(_QWORD *)(v7 + 8) + 8LL), **(unsigned int **)(v7 + 8), a5, a6, 1);
    v9 = v14;
    if ( v14 < 0 )
    {
LABEL_16:
      v15 = (unsigned int)v14;
LABEL_17:
      DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
LABEL_33:
      MSCryptFree(v7);
      goto LABEL_37;
    }
LABEL_32:
    v9 = 0;
    if ( !v7 )
      goto LABEL_37;
    goto LABEL_33;
  }
LABEL_10:
  v13 = (unsigned int)Property;
LABEL_36:
  DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
LABEL_37:
  if ( v6 )
    CachedCloseAlgorithmProvider(v6);
  return v9;
}

```

## disassembly

```asm
0x180016b60  mov     [rsp-28h+arg_8], rbx
0x180016b65  mov     [rsp-28h+arg_10], rsi
0x180016b6a  push    rbp
0x180016b6b  push    rdi
0x180016b6c  push    r12
0x180016b6e  push    r14
0x180016b70  push    r15
0x180016b72  mov     rbp, rsp
0x180016b75  sub     rsp, 60h
0x180016b79  xor     esi, esi
0x180016b7b  xor     edi, edi
0x180016b7d  mov     [rbp+hObject], rsi
0x180016b81  mov     r15d, r9d
0x180016b84  mov     dword ptr [rbp+var_C], esi
0x180016b87  mov     r12, r8
0x180016b8a  mov     dword ptr [rbp+pbOutput], esi
0x180016b8d  mov     r14, rdx
0x180016b90  mov     [rbp+cbOutput], esi
0x180016b93  test    cl, 2
0x180016b96  jz      loc_180016D85
0x180016b9c  test    rdx, rdx
0x180016b9f  jnz     short loc_180016BC9
0x180016ba1  mov     r9d, 531h
0x180016ba7  mov     ebx, 0C000000Dh
0x180016bac  mov     ecx, 0C000000Dh
0x180016bb1  lea     rdx, aStatus; "Status"
0x180016bb8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016bbf  call    DebugTraceError
0x180016bc4  jmp     loc_180016ED8
0x180016bc9  mov     rdx, [rdx]
0x180016bcc  test    rdx, rdx
0x180016bcf  jz      loc_180016D51
0x180016bd5  lea     rcx, [rbp+hObject]
0x180016bd9  call    CachedOpenAlgorithmProvider
0x180016bde  test    eax, eax
0x180016be0  jns     short loc_180016C0B
0x180016be2  mov     r9d, 53Eh
0x180016be8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016bef  lea     rdx, aStatus; "Status"
0x180016bf6  mov     ecx, eax
0x180016bf8  call    DebugTraceError
0x180016bfd  mov     ebx, 0C00000BBh
0x180016c02  mov     rsi, [rbp+hObject]
0x180016c06  jmp     loc_180016ECB
0x180016c0b  mov     [rsp+60h+dwFlags], esi; dwFlags
0x180016c0f  lea     rax, [rbp+cbOutput]
0x180016c13  mov     rsi, [rbp+hObject]
0x180016c17  lea     r8, [rbp+pbOutput]; pbOutput
0x180016c1b  mov     rcx, rsi; hObject
0x180016c1e  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180016c23  mov     r9d, 4; cbOutput
0x180016c29  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180016c30  call    BCryptGetProperty
0x180016c35  mov     ebx, eax
0x180016c37  test    eax, eax
0x180016c39  jns     short loc_180016C48
0x180016c3b  mov     r9d, 54Bh
0x180016c41  mov     ecx, eax
0x180016c43  jmp     loc_180016EB8
0x180016c48  cmp     dword ptr [rbp+pbOutput], r15d
0x180016c4c  jz      short loc_180016C59
0x180016c4e  mov     r9d, 551h
0x180016c54  jmp     loc_180016EAE
0x180016c59  lea     rax, [rbp+cbOutput]
0x180016c5d  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180016c61  xor     r9d, r9d; cbOutput
0x180016c64  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180016c69  xor     r8d, r8d; pbOutput
0x180016c6c  lea     rdx, aHashoidlist; "HashOIDList"
0x180016c73  mov     rcx, rsi; hObject
0x180016c76  call    BCryptGetProperty
0x180016c7b  mov     ebx, eax
0x180016c7d  test    eax, eax
0x180016c7f  jns     short loc_180016C89
0x180016c81  mov     r9d, 55Dh
0x180016c87  jmp     short loc_180016C41
0x180016c89  mov     ecx, [rbp+cbOutput]
0x180016c8c  call    SafeAllocaAllocateFromHeap
0x180016c91  mov     rdi, rax
0x180016c94  test    rax, rax
0x180016c97  jnz     short loc_180016CAE
0x180016c99  mov     ebx, 0C0000017h
0x180016c9e  mov     r9d, 567h
0x180016ca4  mov     ecx, 0C0000017h
0x180016ca9  jmp     loc_180016EB8
0x180016cae  mov     r9d, [rbp+cbOutput]; cbOutput
0x180016cb2  lea     rax, [rbp+cbOutput]
0x180016cb6  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180016cbe  lea     rdx, aHashoidlist; "HashOIDList"
0x180016cc5  mov     r8, rdi; pbOutput
0x180016cc8  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180016ccd  mov     rcx, rsi; hObject
0x180016cd0  call    BCryptGetProperty
0x180016cd5  mov     ebx, eax
0x180016cd7  test    eax, eax
0x180016cd9  jns     short loc_180016CFB
0x180016cdb  mov     r9d, 573h
0x180016ce1  mov     ecx, eax
0x180016ce3  lea     rdx, aStatus; "Status"
0x180016cea  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016cf1  call    DebugTraceError
0x180016cf6  jmp     loc_180016E93
0x180016cfb  cmp     dword ptr [rdi], 0
0x180016cfe  jnz     short loc_180016D12
0x180016d00  mov     ebx, 0C00000E5h
0x180016d05  mov     r9d, 57Ch
0x180016d0b  mov     ecx, 0C00000E5h
0x180016d10  jmp     short loc_180016CE3
0x180016d12  mov     rcx, [rdi+8]
0x180016d16  mov     r9d, r15d
0x180016d19  mov     eax, [rbp+arg_28]
0x180016d1c  mov     r8, r12
0x180016d1f  mov     [rsp+60h+var_30], 1; int
0x180016d27  mov     [rsp+60h+dwFlags], eax; int
0x180016d2b  mov     edx, [rcx]; Size
0x180016d2d  mov     rax, [rbp+arg_20]
0x180016d31  mov     rcx, [rcx+8]; Src
0x180016d35  mov     [rsp+60h+pcbResult], rax; __int64
0x180016d3a  call    ApplyPKCS1SigningFormat
0x180016d3f  mov     ebx, eax
0x180016d41  test    eax, eax
0x180016d43  jns     loc_180016E8C
0x180016d49  mov     r9d, 58Ah
0x180016d4f  jmp     short loc_180016CE1
0x180016d51  mov     eax, [rbp+arg_28]
0x180016d54  xor     edx, edx; Size
0x180016d56  mov     [rsp+60h+var_30], esi; int
0x180016d5a  xor     ecx, ecx; Src
0x180016d5c  mov     [rsp+60h+dwFlags], eax; int
0x180016d60  mov     rax, [rbp+arg_20]
0x180016d64  mov     [rsp+60h+pcbResult], rax; __int64
0x180016d69  call    ApplyPKCS1SigningFormat
0x180016d6e  mov     ebx, eax
0x180016d70  test    eax, eax
0x180016d72  jns     loc_180016E8C
0x180016d78  mov     r9d, 59Ah
0x180016d7e  mov     ecx, eax
0x180016d80  jmp     loc_180016BB1
0x180016d85  test    cl, 8
0x180016d88  jz      loc_180016EA8
0x180016d8e  test    r14, r14
0x180016d91  jz      loc_180016E9D
0x180016d97  mov     rdx, [rdx]
0x180016d9a  test    rdx, rdx
0x180016d9d  jz      loc_180016E9D
0x180016da3  lea     rcx, [rbp+hObject]
0x180016da7  call    CachedOpenAlgorithmProvider
0x180016dac  test    eax, eax
0x180016dae  jns     short loc_180016DD8
0x180016db0  mov     r9d, 5B3h
0x180016db6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016dbd  lea     rdx, aStatus; "Status"
0x180016dc4  mov     ecx, 0C00000BBh
0x180016dc9  mov     ebx, 0C00000BBh
0x180016dce  call    DebugTraceError
0x180016dd3  jmp     loc_180016C02
0x180016dd8  mov     [rsp+60h+dwFlags], esi; dwFlags
0x180016ddc  lea     rax, [rbp+cbOutput]
0x180016de0  mov     rsi, [rbp+hObject]
0x180016de4  lea     r8, [rbp+var_C]; pbOutput
0x180016de8  mov     rcx, rsi; hObject
0x180016deb  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180016df0  mov     r9d, 4; cbOutput
0x180016df6  lea     rdx, aObjectlength; "ObjectLength"
0x180016dfd  call    BCryptGetProperty
0x180016e02  mov     ebx, eax
0x180016e04  test    eax, eax
0x180016e06  jns     short loc_180016E13
0x180016e08  mov     r9d, 5BFh
0x180016e0e  jmp     loc_180016C41
0x180016e13  lea     rax, [rbp+cbOutput]
0x180016e17  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180016e1b  mov     r9d, 4; cbOutput
0x180016e21  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180016e26  lea     r8, [rbp+pbOutput]; pbOutput
0x180016e2a  mov     rcx, rsi; hObject
0x180016e2d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180016e34  call    BCryptGetProperty
0x180016e39  mov     ebx, eax
0x180016e3b  test    eax, eax
0x180016e3d  jns     short loc_180016E4A
0x180016e3f  mov     r9d, 5CBh
0x180016e45  jmp     loc_180016C41
0x180016e4a  mov     eax, [rbp+arg_28]
0x180016e4d  mov     rcx, rsi
0x180016e50  mov     r8d, dword ptr [rbp+var_C]
0x180016e54  mov     edx, dword ptr [rbp+pbOutput]
0x180016e57  mov     [rsp+60h+var_20], eax
0x180016e5b  mov     rax, [rbp+arg_20]
0x180016e5f  mov     [rsp+60h+var_28], rax
0x180016e64  mov     eax, [r14+8]
0x180016e68  mov     [rsp+60h+var_30], r15d
0x180016e6d  mov     qword ptr [rsp+60h+dwFlags], r12
0x180016e72  mov     dword ptr [rsp+60h+pcbResult], eax
0x180016e76  call    ApplyPSSPaddingSalted
0x180016e7b  mov     ebx, eax
0x180016e7d  test    eax, eax
0x180016e7f  jns     short loc_180016E8C
0x180016e81  mov     r9d, 5D9h
0x180016e87  jmp     loc_180016C41
0x180016e8c  xor     ebx, ebx
0x180016e8e  test    rdi, rdi
0x180016e91  jz      short loc_180016ECB
0x180016e93  mov     rcx, rdi
0x180016e96  call    MSCryptFree
0x180016e9b  jmp     short loc_180016ECB
0x180016e9d  mov     r9d, 5A7h
0x180016ea3  jmp     loc_180016BA7
0x180016ea8  mov     r9d, 5E0h
0x180016eae  mov     ecx, 0C000000Dh
0x180016eb3  mov     ebx, 0C000000Dh
0x180016eb8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016ebf  lea     rdx, aStatus; "Status"
0x180016ec6  call    DebugTraceError
0x180016ecb  test    rsi, rsi
0x180016ece  jz      short loc_180016ED8
0x180016ed0  mov     rcx, rsi; hAlgorithm
0x180016ed3  call    CachedCloseAlgorithmProvider
0x180016ed8  lea     r11, [rsp+60h+var_s0]
0x180016edd  mov     eax, ebx
0x180016edf  mov     rbx, [r11+38h]
0x180016ee3  mov     rsi, [r11+40h]
0x180016ee7  mov     rsp, r11
0x180016eea  pop     r15
0x180016eec  pop     r14
0x180016eee  pop     r12
0x180016ef0  pop     rdi
0x180016ef1  pop     rbp
0x180016ef2  retn
```
