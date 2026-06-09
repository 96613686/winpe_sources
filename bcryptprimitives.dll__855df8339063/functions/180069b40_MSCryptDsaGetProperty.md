# MSCryptDsaGetProperty

- ea: `0x180069b40`
- end: `0x180069c6f`
- name: `MSCryptDsaGetProperty`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180051820`
- `0x1800699e4`
- `0x180069b40`
- `0x18007f765`

## string_xrefs

- `0x180069c07`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaGetProperty(__int64 a1, const wchar_t *a2, int *a3, unsigned int a4, _DWORD *a5, int a6)
{
  unsigned int v10; // ebx
  int AlgProperty; // eax
  __int64 v12; // r9
  __int64 v13; // rcx

  if ( !a1 || !a2 || !a5 || a6 )
    return (unsigned int)-1073741811;
  if ( wcscmp_0(a2, L"AlgorithmName") )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297301836 )
    {
      AlgProperty = MSCryptDsaGetAlgProperty(a1, a2, a3, a4, a5, 0);
      v10 = AlgProperty;
      if ( AlgProperty >= 0 )
        return v10;
      v12 = 542;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 4) != 1297304409 )
      {
        v10 = -1073741811;
        v12 = 563;
        v13 = 3221225485LL;
        goto LABEL_14;
      }
      AlgProperty = MSCryptDsaGetKeyPairProperty(a1, a2, a3, a4, a5, 0);
      v10 = AlgProperty;
      if ( AlgProperty >= 0 )
        return v10;
      v12 = 556;
    }
    v13 = (unsigned int)AlgProperty;
LABEL_14:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v12);
    return v10;
  }
  v10 = 0;
  *a5 = 8;
  if ( a3 )
  {
    if ( a4 >= 8 )
      wcscpy((wchar_t *)a3, L"DSA");
    else
      return (unsigned int)-1073741789;
  }
  return v10;
}

```

## disassembly

```asm
0x180069b40  push    rbx
0x180069b42  push    rbp
0x180069b43  push    rsi
0x180069b44  push    rdi
0x180069b45  push    r14
0x180069b47  sub     rsp, 30h
0x180069b4b  mov     r14d, r9d
0x180069b4e  mov     rsi, r8
0x180069b51  mov     rbx, rdx
0x180069b54  mov     rbp, rcx
0x180069b57  test    rcx, rcx
0x180069b5a  jz      loc_180069C5C
0x180069b60  test    rdx, rdx
0x180069b63  jz      loc_180069C5C
0x180069b69  mov     rdi, [rsp+58h+arg_20]
0x180069b71  test    rdi, rdi
0x180069b74  jz      loc_180069C5C
0x180069b7a  cmp     [rsp+58h+arg_28], 0
0x180069b82  jnz     loc_180069C5C
0x180069b88  lea     rdx, aAlgorithmname; "AlgorithmName"
0x180069b8f  mov     rcx, rbx; String1
0x180069b92  call    wcscmp_0
0x180069b97  test    eax, eax
0x180069b99  jnz     short loc_180069BCB
0x180069b9b  xor     ebx, ebx
0x180069b9d  mov     dword ptr [rdi], 8
0x180069ba3  test    rsi, rsi
0x180069ba6  jz      loc_180069C61
0x180069bac  cmp     r14d, 8
0x180069bb0  jnb     short loc_180069BBC
0x180069bb2  mov     ebx, 0C0000023h
0x180069bb7  jmp     loc_180069C61
0x180069bbc  mov     rax, qword ptr cs:aDsa; "DSA"
0x180069bc3  mov     [rsi], rax
0x180069bc6  jmp     loc_180069C61
0x180069bcb  cmp     dword ptr [rbp+4], 4D53414Ch
0x180069bd2  jnz     short loc_180069C15
0x180069bd4  mov     [rsp+58h+var_30], 0
0x180069bdc  mov     r9d, r14d
0x180069bdf  mov     r8, rsi
0x180069be2  mov     [rsp+58h+var_38], rdi
0x180069be7  mov     rdx, rbx
0x180069bea  mov     rcx, rbp
0x180069bed  call    MSCryptDsaGetAlgProperty
0x180069bf2  mov     ebx, eax
0x180069bf4  test    eax, eax
0x180069bf6  jns     short loc_180069C61
0x180069bf8  mov     r9d, 21Eh
0x180069bfe  mov     ecx, eax
0x180069c00  lea     rdx, aStatus; "Status"
0x180069c07  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069c0e  call    DebugTraceError
0x180069c13  jmp     short loc_180069C61
0x180069c15  cmp     dword ptr [rbp+4], 4D534B59h
0x180069c1c  jnz     short loc_180069C4A
0x180069c1e  mov     [rsp+58h+var_30], 0
0x180069c26  mov     r9d, r14d
0x180069c29  mov     r8, rsi
0x180069c2c  mov     [rsp+58h+var_38], rdi
0x180069c31  mov     rdx, rbx
0x180069c34  mov     rcx, rbp
0x180069c37  call    MSCryptDsaGetKeyPairProperty
0x180069c3c  mov     ebx, eax
0x180069c3e  test    eax, eax
0x180069c40  jns     short loc_180069C61
0x180069c42  mov     r9d, 22Ch
0x180069c48  jmp     short loc_180069BFE
0x180069c4a  mov     ebx, 0C000000Dh
0x180069c4f  mov     r9d, 233h
0x180069c55  mov     ecx, 0C000000Dh
0x180069c5a  jmp     short loc_180069C00
0x180069c5c  mov     ebx, 0C000000Dh
0x180069c61  mov     eax, ebx
0x180069c63  add     rsp, 30h
0x180069c67  pop     r14
0x180069c69  pop     rdi
0x180069c6a  pop     rsi
0x180069c6b  pop     rbp
0x180069c6c  pop     rbx
0x180069c6d  retn
```
