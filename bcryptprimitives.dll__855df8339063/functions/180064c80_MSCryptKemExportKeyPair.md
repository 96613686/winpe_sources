# MSCryptKemExportKeyPair

- ea: `0x180064c80`
- end: `0x180064db2`
- name: `MSCryptKemExportKeyPair`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180063c20`
- `0x180063d2c`
- `0x180064c80`
- `0x180065430`

## string_xrefs

- `0x180064d91`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptKemExportKeyPair(
        _DWORD *a1,
        __int64 a2,
        char *a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v15[7]; // [rsp+30h] [rbp-38h] BYREF

  v15[0] = 0;
  if ( !a6 || !a3 )
  {
    v9 = 2038;
    goto LABEL_22;
  }
  *a6 = 0;
  if ( a2 )
  {
    v9 = 2047;
LABEL_5:
    v10 = -1073741637;
    v11 = 3221225659LL;
LABEL_23:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v9);
    return v10;
  }
  if ( a7 )
  {
    v9 = 2054;
LABEL_22:
    v10 = -1073741811;
    v11 = 3221225485LL;
    goto LABEL_23;
  }
  if ( !a4 )
  {
    if ( !a5 )
      goto LABEL_10;
LABEL_13:
    v9 = 2062;
    goto LABEL_22;
  }
  if ( !a5 )
    goto LABEL_13;
LABEL_10:
  v12 = ValidateKemKey(a1, v15, 1);
  v10 = v12;
  if ( v12 < 0 )
  {
    v9 = 2069;
    v11 = (unsigned int)v12;
    goto LABEL_23;
  }
  if ( *(_DWORD *)(v15[0] + 8) == 458753 )
  {
    v13 = ExportMlKemKeyPair(v15[0], a3, a4, a5, a6);
  }
  else
  {
    if ( *(_DWORD *)(v15[0] + 8) != 458754 )
    {
      v9 = 2088;
      goto LABEL_5;
    }
    v13 = ExportCompositeMlKemKeyPair(v15[0], a3, a4, a5, a6);
  }
  v10 = v13;
  if ( v13 < 0 )
  {
    v9 = 2095;
    v11 = (unsigned int)v13;
    goto LABEL_23;
  }
  return v10;
}

```

## disassembly

```asm
0x180064c80  push    rbx
0x180064c82  push    rbp
0x180064c83  push    rsi
0x180064c84  push    rdi
0x180064c85  push    r14
0x180064c87  sub     rsp, 40h
0x180064c8b  mov     rsi, [rsp+68h+arg_28]
0x180064c93  mov     rbp, r9
0x180064c96  mov     [rsp+68h+var_38], 0
0x180064c9f  mov     r14, r8
0x180064ca2  test    rsi, rsi
0x180064ca5  jz      loc_180064D81
0x180064cab  test    r8, r8
0x180064cae  jz      loc_180064D81
0x180064cb4  mov     dword ptr [rsi], 0
0x180064cba  test    rdx, rdx
0x180064cbd  jz      short loc_180064CD4
0x180064cbf  mov     r9d, 7FFh
0x180064cc5  mov     ebx, 0C00000BBh
0x180064cca  mov     ecx, 0C00000BBh
0x180064ccf  jmp     loc_180064D91
0x180064cd4  cmp     [rsp+68h+arg_30], 0
0x180064cdc  jz      short loc_180064CE9
0x180064cde  mov     r9d, 806h
0x180064ce4  jmp     loc_180064D87
0x180064ce9  mov     edi, [rsp+68h+arg_20]
0x180064cf0  test    rbp, rbp
0x180064cf3  jnz     short loc_180064D19
0x180064cf5  test    edi, edi
0x180064cf7  jnz     short loc_180064D1D
0x180064cf9  mov     r8d, 1
0x180064cff  lea     rdx, [rsp+68h+var_38]
0x180064d04  call    ValidateKemKey
0x180064d09  mov     ebx, eax
0x180064d0b  test    eax, eax
0x180064d0d  jns     short loc_180064D25
0x180064d0f  mov     r9d, 815h
0x180064d15  mov     ecx, eax
0x180064d17  jmp     short loc_180064D91
0x180064d19  test    edi, edi
0x180064d1b  jnz     short loc_180064CF9
0x180064d1d  mov     r9d, 80Eh
0x180064d23  jmp     short loc_180064D87
0x180064d25  mov     r10, [rsp+68h+var_38]
0x180064d2a  mov     ecx, [r10+8]
0x180064d2e  sub     ecx, 70001h
0x180064d34  jz      short loc_180064D5B
0x180064d36  cmp     ecx, 1
0x180064d39  jz      short loc_180064D43
0x180064d3b  mov     r9d, 828h
0x180064d41  jmp     short loc_180064CC5
0x180064d43  mov     r9d, edi
0x180064d46  mov     [rsp+68h+var_48], rsi
0x180064d4b  mov     r8, rbp
0x180064d4e  mov     rdx, r14
0x180064d51  mov     rcx, r10
0x180064d54  call    ExportCompositeMlKemKeyPair
0x180064d59  jmp     short loc_180064D71
0x180064d5b  mov     r9d, edi
0x180064d5e  mov     [rsp+68h+var_48], rsi
0x180064d63  mov     r8, rbp
0x180064d66  mov     rdx, r14
0x180064d69  mov     rcx, r10
0x180064d6c  call    ExportMlKemKeyPair
0x180064d71  mov     ebx, eax
0x180064d73  test    eax, eax
0x180064d75  jns     short loc_180064DA4
0x180064d77  mov     r9d, 82Fh
0x180064d7d  mov     ecx, eax
0x180064d7f  jmp     short loc_180064D91
0x180064d81  mov     r9d, 7F6h
0x180064d87  mov     ebx, 0C000000Dh
0x180064d8c  mov     ecx, 0C000000Dh
0x180064d91  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064d98  lea     rdx, aStatus; "Status"
0x180064d9f  call    DebugTraceError
0x180064da4  mov     eax, ebx
0x180064da6  add     rsp, 40h
0x180064daa  pop     r14
0x180064dac  pop     rdi
0x180064dad  pop     rsi
0x180064dae  pop     rbp
0x180064daf  pop     rbx
0x180064db0  retn
```
