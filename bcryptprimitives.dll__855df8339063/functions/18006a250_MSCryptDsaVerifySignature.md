# MSCryptDsaVerifySignature

- ea: `0x18006a250`
- end: `0x18006a346`
- name: `MSCryptDsaVerifySignature`
- size: `246`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18004f144`
- `0x18005196c`
- `0x180056cf0`
- `0x18006a250`

## string_xrefs

- `0x18006a320`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaVerifySignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  int v8; // esi
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // edx
  unsigned int v14; // eax
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v8 = a3;
  v16 = 0;
  if ( !a1 || !a3 || !a5 || a7 )
  {
    v11 = 1455;
    goto LABEL_14;
  }
  v9 = ValidateDSAKey(a1, 0, &v16);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = 1462;
LABEL_7:
    v12 = (unsigned int)v9;
LABEL_15:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v11);
    return v10;
  }
  v13 = *(_DWORD *)(v16 + 16);
  if ( a6 != 2 * v13 || a4 != v13 )
  {
    v11 = 1470;
LABEL_14:
    v12 = 3221225485LL;
    v10 = -1073741811;
    goto LABEL_15;
  }
  v14 = SymCryptDsaVerify(*(_QWORD *)(v16 + 40), v8, a4, a5, a6, 2, 0);
  if ( v14 )
  {
    v9 = SymcryptErrorCodeToNtStatus(v14);
    v10 = v9;
    v11 = 1485;
    goto LABEL_7;
  }
  return v10;
}

```

## disassembly

```asm
0x18006a250  mov     rax, rsp
0x18006a253  mov     [rax+10h], rbx
0x18006a257  mov     [rax+18h], rbp
0x18006a25b  push    rsi
0x18006a25c  sub     rsp, 40h
0x18006a260  mov     ebp, r9d
0x18006a263  mov     rsi, r8
0x18006a266  mov     qword ptr [rax+8], 0
0x18006a26e  test    rcx, rcx
0x18006a271  jz      loc_18006A310
0x18006a277  test    r8, r8
0x18006a27a  jz      loc_18006A310
0x18006a280  cmp     [rsp+48h+arg_20], 0
0x18006a286  jz      loc_18006A310
0x18006a28c  cmp     [rsp+48h+arg_30], 0
0x18006a294  jnz     short loc_18006A310
0x18006a296  lea     r8, [rax+8]
0x18006a29a  xor     edx, edx
0x18006a29c  call    ValidateDSAKey
0x18006a2a1  mov     ebx, eax
0x18006a2a3  test    eax, eax
0x18006a2a5  jns     short loc_18006A2B1
0x18006a2a7  mov     r9d, 5B6h
0x18006a2ad  mov     ecx, eax
0x18006a2af  jmp     short loc_18006A320
0x18006a2b1  mov     rcx, [rsp+48h+arg_0]
0x18006a2b6  mov     edx, [rcx+10h]
0x18006a2b9  lea     eax, [rdx+rdx]
0x18006a2bc  cmp     [rsp+48h+arg_28], eax
0x18006a2c0  jnz     short loc_18006A308
0x18006a2c2  cmp     ebp, edx
0x18006a2c4  jnz     short loc_18006A308
0x18006a2c6  mov     eax, [rsp+48h+arg_28]
0x18006a2ca  mov     r8, rbp
0x18006a2cd  mov     r9, [rsp+48h+arg_20]
0x18006a2d2  mov     rdx, rsi
0x18006a2d5  mov     rcx, [rcx+28h]
0x18006a2d9  mov     [rsp+48h+var_18], 0
0x18006a2e1  mov     [rsp+48h+var_20], 2
0x18006a2e9  mov     [rsp+48h+var_28], rax
0x18006a2ee  call    SymCryptDsaVerify
0x18006a2f3  test    eax, eax
0x18006a2f5  jz      short loc_18006A333
0x18006a2f7  mov     ecx, eax
0x18006a2f9  call    SymcryptErrorCodeToNtStatus
0x18006a2fe  mov     ebx, eax
0x18006a300  mov     r9d, 5CDh
0x18006a306  jmp     short loc_18006A2AD
0x18006a308  mov     r9d, 5BEh
0x18006a30e  jmp     short loc_18006A316
0x18006a310  mov     r9d, 5AFh
0x18006a316  mov     ecx, 0C000000Dh
0x18006a31b  mov     ebx, 0C000000Dh
0x18006a320  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a327  lea     rdx, aStatus; "Status"
0x18006a32e  call    DebugTraceError
0x18006a333  mov     rbp, [rsp+48h+arg_10]
0x18006a338  mov     eax, ebx
0x18006a33a  mov     rbx, [rsp+48h+arg_8]
0x18006a33f  add     rsp, 40h
0x18006a343  pop     rsi
0x18006a344  retn
```
