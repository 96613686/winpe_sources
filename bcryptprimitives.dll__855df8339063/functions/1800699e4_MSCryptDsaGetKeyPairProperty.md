# MSCryptDsaGetKeyPairProperty

- ea: `0x1800699e4`
- end: `0x180069b2c`
- name: `MSCryptDsaGetKeyPairProperty`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180069b40`

## callees

- `0x18000ecb0`
- `0x18005196c`
- `0x1800699e4`
- `0x18007f765`

## string_xrefs

- `0x180069b03`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaGetKeyPairProperty(
        __int64 a1,
        const wchar_t *a2,
        int *a3,
        unsigned int a4,
        _DWORD *a5,
        int a6)
{
  _DWORD *v9; // r14
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // ecx
  __int64 v16; // [rsp+40h] [rbp+8h] BYREF

  v16 = 0;
  if ( !a1 || !a2 || (v9 = a5) == 0 || a6 )
  {
    v11 = -1073741811;
    v12 = 410;
    v13 = 3221225485LL;
    goto LABEL_21;
  }
  v10 = ValidateDSAKey(a1, 0, &v16);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 417;
    v13 = (unsigned int)v10;
LABEL_21:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v12);
    return v11;
  }
  if ( !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"KeyStrength") || !wcscmp_0(a2, L"PublicKeyLength") )
  {
    *v9 = 4;
    if ( !a3 )
      return v11;
    if ( a4 >= 4 )
    {
      v14 = 8 * *(_DWORD *)(v16 + 12);
      goto LABEL_14;
    }
    return (unsigned int)-1073741789;
  }
  if ( wcscmp_0(a2, L"SignatureLength") )
  {
    v11 = -1073741637;
    v12 = 473;
    v13 = 3221225659LL;
    goto LABEL_21;
  }
  *v9 = 4;
  if ( a3 )
  {
    if ( a4 >= 4 )
    {
      v14 = 2 * *(_DWORD *)(v16 + 16);
LABEL_14:
      *a3 = v14;
      return v11;
    }
    return (unsigned int)-1073741789;
  }
  return v11;
}

```

## disassembly

```asm
0x1800699e4  mov     rax, rsp
0x1800699e7  mov     [rax+10h], rbx
0x1800699eb  mov     [rax+18h], rbp
0x1800699ef  push    rsi
0x1800699f0  push    rdi
0x1800699f1  push    r14
0x1800699f3  sub     rsp, 20h
0x1800699f7  mov     qword ptr [rax+8], 0
0x1800699ff  mov     ebp, r9d
0x180069a02  mov     rdi, r8
0x180069a05  mov     rsi, rdx
0x180069a08  test    rcx, rcx
0x180069a0b  jz      loc_180069AF3
0x180069a11  test    rdx, rdx
0x180069a14  jz      loc_180069AF3
0x180069a1a  mov     r14, [rsp+38h+arg_20]
0x180069a1f  test    r14, r14
0x180069a22  jz      loc_180069AF3
0x180069a28  cmp     [rsp+38h+arg_28], 0
0x180069a2d  jnz     loc_180069AF3
0x180069a33  lea     r8, [rax+8]
0x180069a37  xor     edx, edx
0x180069a39  call    ValidateDSAKey
0x180069a3e  mov     ebx, eax
0x180069a40  test    eax, eax
0x180069a42  jns     short loc_180069A51
0x180069a44  mov     r9d, 1A1h
0x180069a4a  mov     ecx, eax
0x180069a4c  jmp     loc_180069B03
0x180069a51  lea     rdx, aKeylength; "KeyLength"
0x180069a58  mov     rcx, rsi; String1
0x180069a5b  call    wcscmp_0
0x180069a60  test    eax, eax
0x180069a62  jz      short loc_180069ACE
0x180069a64  lea     rdx, aKeystrength; "KeyStrength"
0x180069a6b  mov     rcx, rsi; String1
0x180069a6e  call    wcscmp_0
0x180069a73  test    eax, eax
0x180069a75  jz      short loc_180069ACE
0x180069a77  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x180069a7e  mov     rcx, rsi; String1
0x180069a81  call    wcscmp_0
0x180069a86  test    eax, eax
0x180069a88  jz      short loc_180069ACE
0x180069a8a  lea     rdx, aSignaturelengt; "SignatureLength"
0x180069a91  mov     rcx, rsi; String1
0x180069a94  call    wcscmp_0
0x180069a99  test    eax, eax
0x180069a9b  jnz     short loc_180069ABC
0x180069a9d  mov     dword ptr [r14], 4
0x180069aa4  test    rdi, rdi
0x180069aa7  jz      short loc_180069B16
0x180069aa9  cmp     ebp, 4
0x180069aac  jb      short loc_180069ADF
0x180069aae  mov     rax, [rsp+38h+arg_0]
0x180069ab3  mov     ecx, [rax+10h]
0x180069ab6  add     ecx, ecx
0x180069ab8  mov     [rdi], ecx
0x180069aba  jmp     short loc_180069B16
0x180069abc  mov     ebx, 0C00000BBh
0x180069ac1  mov     r9d, 1D9h
0x180069ac7  mov     ecx, 0C00000BBh
0x180069acc  jmp     short loc_180069B03
0x180069ace  mov     dword ptr [r14], 4
0x180069ad5  test    rdi, rdi
0x180069ad8  jz      short loc_180069B16
0x180069ada  cmp     ebp, 4
0x180069add  jnb     short loc_180069AE6
0x180069adf  mov     ebx, 0C0000023h
0x180069ae4  jmp     short loc_180069B16
0x180069ae6  mov     rax, [rsp+38h+arg_0]
0x180069aeb  mov     ecx, [rax+0Ch]
0x180069aee  shl     ecx, 3
0x180069af1  jmp     short loc_180069AB8
0x180069af3  mov     ebx, 0C000000Dh
0x180069af8  mov     r9d, 19Ah
0x180069afe  mov     ecx, 0C000000Dh
0x180069b03  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069b0a  lea     rdx, aStatus; "Status"
0x180069b11  call    DebugTraceError
0x180069b16  mov     rbp, [rsp+38h+arg_10]
0x180069b1b  mov     eax, ebx
0x180069b1d  mov     rbx, [rsp+38h+arg_8]
0x180069b22  add     rsp, 20h
0x180069b26  pop     r14
0x180069b28  pop     rdi
0x180069b29  pop     rsi
0x180069b2a  retn
```
