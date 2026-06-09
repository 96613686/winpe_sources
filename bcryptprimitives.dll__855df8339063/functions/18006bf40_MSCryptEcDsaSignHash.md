# MSCryptEcDsaSignHash

- ea: `0x18006bf40`
- end: `0x18006c078`
- name: `MSCryptEcDsaSignHash`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18001ffa0`
- `0x180056cf0`
- `0x18006bf40`
- `0x180075390`

## string_xrefs

- `0x18006c052`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcDsaSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        int a8)
{
  int v9; // esi
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rcx
  unsigned int v16; // edx
  unsigned int v17; // eax
  int v19; // [rsp+20h] [rbp-28h]
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v9 = a3;
  v20 = 0;
  if ( !a3 || !a4 || a2 || (a8 & 0xFFFFFFF5) != 0 )
  {
    v11 = -1073741811;
    v12 = 4179;
    v13 = 3221225485LL;
    goto LABEL_17;
  }
  v10 = ValidateEccKey(a1, 1, 1, 1, &v20);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 4187;
LABEL_7:
    v13 = (unsigned int)v10;
LABEL_17:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v12);
    return v11;
  }
  v14 = v20;
  if ( (*(_BYTE *)(v20 + 32) & 2) == 0 )
  {
    v11 = -1073741816;
    v12 = 4194;
    v13 = 3221225480LL;
    goto LABEL_17;
  }
  v15 = a5;
  v16 = 2 * *(_DWORD *)(**(_QWORD **)(v20 + 16) + 16LL);
  *a7 = v16;
  if ( v15 )
  {
    if ( a6 < v16 )
    {
      v11 = -1073741789;
      v12 = 4209;
      v13 = 3221225507LL;
      goto LABEL_17;
    }
    v17 = SymCryptEcDsaSign(*(_QWORD *)(v14 + 24), v9, a4, v14, v19, v15, v16);
    if ( v17 )
    {
      v10 = SymcryptErrorCodeToNtStatus(v17);
      v11 = v10;
      v12 = 4224;
      goto LABEL_7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006bf40  mov     r11, rsp
0x18006bf43  mov     [r11+8], rbx
0x18006bf47  mov     [r11+10h], rsi
0x18006bf4b  push    rdi
0x18006bf4c  sub     rsp, 40h
0x18006bf50  mov     edi, r9d
0x18006bf53  mov     rsi, r8
0x18006bf56  mov     qword ptr [r11+18h], 0
0x18006bf5e  test    r8, r8
0x18006bf61  jz      loc_18006C042
0x18006bf67  test    r9d, r9d
0x18006bf6a  jz      loc_18006C042
0x18006bf70  test    rdx, rdx
0x18006bf73  jnz     loc_18006C042
0x18006bf79  test    [rsp+48h+arg_38], 0FFFFFFF5h
0x18006bf84  jnz     loc_18006C042
0x18006bf8a  mov     edx, 1
0x18006bf8f  lea     rax, [r11+18h]
0x18006bf93  mov     r9d, edx
0x18006bf96  mov     [r11-28h], rax
0x18006bf9a  mov     r8d, edx
0x18006bf9d  call    ValidateEccKey
0x18006bfa2  mov     ebx, eax
0x18006bfa4  test    eax, eax
0x18006bfa6  jns     short loc_18006BFB5
0x18006bfa8  mov     r9d, 105Bh
0x18006bfae  mov     ecx, eax
0x18006bfb0  jmp     loc_18006C052
0x18006bfb5  mov     r9, [rsp+48h+arg_10]
0x18006bfba  test    byte ptr [r9+20h], 2
0x18006bfbf  jnz     short loc_18006BFD3
0x18006bfc1  mov     ebx, 0C0000008h
0x18006bfc6  mov     r9d, 1062h
0x18006bfcc  mov     ecx, 0C0000008h
0x18006bfd1  jmp     short loc_18006C052
0x18006bfd3  mov     rax, [r9+10h]
0x18006bfd7  mov     rcx, [rax]
0x18006bfda  mov     rax, [rsp+48h+arg_30]
0x18006bfe2  mov     edx, [rcx+10h]
0x18006bfe5  mov     rcx, [rsp+48h+arg_20]
0x18006bfea  add     edx, edx
0x18006bfec  mov     [rax], edx
0x18006bfee  test    rcx, rcx
0x18006bff1  jnz     short loc_18006BFF7
0x18006bff3  xor     ebx, ebx
0x18006bff5  jmp     short loc_18006C065
0x18006bff7  cmp     [rsp+48h+arg_28], edx
0x18006bffb  jnb     short loc_18006C00F
0x18006bffd  mov     ebx, 0C0000023h
0x18006c002  mov     r9d, 1071h
0x18006c008  mov     ecx, 0C0000023h
0x18006c00d  jmp     short loc_18006C052
0x18006c00f  mov     eax, edx
0x18006c011  mov     r8, rdi
0x18006c014  mov     [rsp+48h+var_18], rax
0x18006c019  mov     rdx, rsi
0x18006c01c  mov     [rsp+48h+var_20], rcx
0x18006c021  mov     rcx, [r9+18h]
0x18006c025  call    SymCryptEcDsaSign
0x18006c02a  test    eax, eax
0x18006c02c  jz      short loc_18006BFF3
0x18006c02e  mov     ecx, eax
0x18006c030  call    SymcryptErrorCodeToNtStatus
0x18006c035  mov     ebx, eax
0x18006c037  mov     r9d, 1080h
0x18006c03d  jmp     loc_18006BFAE
0x18006c042  mov     ebx, 0C000000Dh
0x18006c047  mov     r9d, 1053h
0x18006c04d  mov     ecx, 0C000000Dh
0x18006c052  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c059  lea     rdx, aStatus; "Status"
0x18006c060  call    DebugTraceError
0x18006c065  mov     rsi, [rsp+48h+arg_8]
0x18006c06a  mov     eax, ebx
0x18006c06c  mov     rbx, [rsp+48h+arg_0]
0x18006c071  add     rsp, 40h
0x18006c075  pop     rdi
0x18006c076  retn
```
