# GetSignatureInterface

- ea: `0x180056400`
- end: `0x180056512`
- name: `GetSignatureInterface`
- size: `274`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180056400`
- `0x18007f765`

## string_xrefs

- `0x1800564d0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\interface.c`
- `0x1800564b7`: `Composite-ML-DSA`

## pseudocode

```c
__int64 __fastcall GetSignatureInterface(__int64 a1, const wchar_t *a2, __int64 **a3)
{
  __int64 *v5; // rax
  unsigned int v6; // ebx

  if ( !wcscmp_0(a2, L"ECDSA")
    || !wcscmp_0(a2, L"ECDSA_P256")
    || !wcscmp_0(a2, L"ECDSA_P384")
    || !wcscmp_0(a2, L"ECDSA_P521") )
  {
    v5 = &MSEcDsaSignFunctionTable;
    goto LABEL_14;
  }
  if ( !wcscmp_0(a2, L"RSA_SIGN") )
  {
    v5 = &MSRsaSignatureFunctionTable;
LABEL_14:
    *a3 = v5;
    return 0;
  }
  if ( !wcscmp_0(a2, L"DSA") )
  {
    v5 = &MSDsaSignFunctionTable;
    goto LABEL_14;
  }
  if ( !wcscmp_0(a2, L"ML-DSA") || !wcscmp_0(a2, L"Composite-ML-DSA") )
  {
    v5 = &MSPqDsaSignFunctionTable;
    goto LABEL_14;
  }
  v6 = -1073741637;
  DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\interface.c", 188);
  return v6;
}

```

## disassembly

```asm
0x180056400  mov     [rsp+arg_0], rbx
0x180056405  push    rdi
0x180056406  sub     rsp, 20h
0x18005640a  mov     rbx, rdx
0x18005640d  mov     rdi, r8
0x180056410  mov     rcx, rbx; String1
0x180056413  lea     rdx, aEcdsa; "ECDSA"
0x18005641a  call    wcscmp_0
0x18005641f  test    eax, eax
0x180056421  jz      loc_1800564F8
0x180056427  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x18005642e  mov     rcx, rbx; String1
0x180056431  call    wcscmp_0
0x180056436  test    eax, eax
0x180056438  jz      loc_1800564F8
0x18005643e  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x180056445  mov     rcx, rbx; String1
0x180056448  call    wcscmp_0
0x18005644d  test    eax, eax
0x18005644f  jz      loc_1800564F8
0x180056455  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x18005645c  mov     rcx, rbx; String1
0x18005645f  call    wcscmp_0
0x180056464  test    eax, eax
0x180056466  jz      loc_1800564F8
0x18005646c  lea     rdx, aRsaSign; "RSA_SIGN"
0x180056473  mov     rcx, rbx; String1
0x180056476  call    wcscmp_0
0x18005647b  test    eax, eax
0x18005647d  jnz     short loc_180056488
0x18005647f  lea     rax, MSRsaSignatureFunctionTable
0x180056486  jmp     short loc_1800564FF
0x180056488  lea     rdx, aDsa; "DSA"
0x18005648f  mov     rcx, rbx; String1
0x180056492  call    wcscmp_0
0x180056497  test    eax, eax
0x180056499  jnz     short loc_1800564A4
0x18005649b  lea     rax, MSDsaSignFunctionTable
0x1800564a2  jmp     short loc_1800564FF
0x1800564a4  lea     rdx, aMlDsa; "ML-DSA"
0x1800564ab  mov     rcx, rbx; String1
0x1800564ae  call    wcscmp_0
0x1800564b3  test    eax, eax
0x1800564b5  jz      short loc_1800564EF
0x1800564b7  lea     rdx, aCompositeMlDsa; "Composite-ML-DSA"
0x1800564be  mov     rcx, rbx; String1
0x1800564c1  call    wcscmp_0
0x1800564c6  test    eax, eax
0x1800564c8  jz      short loc_1800564EF
0x1800564ca  mov     r9d, 0BCh
0x1800564d0  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800564d7  lea     rdx, aStatus; "Status"
0x1800564de  mov     ecx, 0C00000BBh
0x1800564e3  mov     ebx, 0C00000BBh
0x1800564e8  call    DebugTraceError
0x1800564ed  jmp     short loc_180056504
0x1800564ef  lea     rax, MSPqDsaSignFunctionTable
0x1800564f6  jmp     short loc_1800564FF
0x1800564f8  lea     rax, MSEcDsaSignFunctionTable
0x1800564ff  mov     [rdi], rax
0x180056502  xor     ebx, ebx
0x180056504  mov     eax, ebx
0x180056506  mov     rbx, [rsp+28h+arg_0]
0x18005650b  add     rsp, 20h
0x18005650f  pop     rdi
0x180056510  retn
```
