# MSCryptEccGetProperty

- ea: `0x180044180`
- end: `0x18004433f`
- name: `MSCryptEccGetProperty`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180043f70`

## callees

- `0x18000ecb0`
- `0x180044180`
- `0x180044350`
- `0x18004490c`
- `0x180044ba0`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x1800442df`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044312`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18008250b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180082527`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccGetProperty(
        _DWORD *a1,
        const wchar_t *a2,
        int *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6,
        unsigned int a7)
{
  int v11; // ebx
  int AlgProperty; // ebx
  __int64 v14; // r9
  __int64 v15; // r9
  _WORD *v16; // rax
  __int64 v17; // rcx
  unsigned int v19; // ecx
  __int64 v20; // [rsp+28h] [rbp-40h]

  if ( a6 )
  {
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3654);
    return 3221225485LL;
  }
  if ( !a1 || *a1 < 0xCu )
  {
    v14 = 445;
    goto LABEL_23;
  }
  v11 = a1[1];
  if ( v11 == 1297304409 || v11 == 1297301836 )
  {
    if ( wcscmp_0(a2, L"AlgorithmName") )
    {
      if ( v11 == 1297301836 )
      {
        AlgProperty = MSCryptEccGetAlgProperty(a1, a2, a3, a4, a5);
        if ( AlgProperty >= 0 )
          return 0;
        v15 = 3700;
      }
      else
      {
        AlgProperty = MSCryptEccGetKeyProperty((__int64)a1, (__int64)a2, a3, a4, a5, v20, a7);
        if ( AlgProperty >= 0 )
          return 0;
        v15 = 3715;
      }
      DebugTraceError(
        (unsigned int)AlgProperty,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        v15);
      return (unsigned int)AlgProperty;
    }
    v16 = (_WORD *)CryptAuditTranslateAlgID((unsigned int)a1[2], a7);
    v17 = -1;
    while ( v16[++v17] != 0 )
      ;
    v19 = 2 * v17 + 2;
    *a5 = v19;
    if ( a3 )
    {
      if ( a4 < v19 )
        return 3221225507LL;
      memcpy_0(a3, v16, v19);
    }
    return 0;
  }
  v14 = 453;
LABEL_23:
  DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v14);
  return 3221225480LL;
}

```

## disassembly

```asm
0x180044180  push    rbp
0x180044182  push    rsi
0x180044183  push    rdi
0x180044184  push    r14
0x180044186  sub     rsp, 48h
0x18004418a  cmp     [rsp+68h+arg_28], 0
0x180044192  mov     r14d, r9d
0x180044195  mov     rbp, r8
0x180044198  mov     rsi, rdx
0x18004419b  mov     rdi, rcx
0x18004419e  jnz     loc_1800442D9
0x1800441a4  mov     [rsp+68h+arg_0], rbx
0x1800441a9  test    rcx, rcx
0x1800441ac  jz      loc_180044334
0x1800441b2  cmp     dword ptr [rcx], 0Ch
0x1800441b5  jb      loc_180044334
0x1800441bb  mov     ebx, [rcx+4]
0x1800441be  cmp     ebx, 4D534B59h
0x1800441c4  jnz     short loc_180044236
0x1800441c6  lea     rdx, aAlgorithmname; "AlgorithmName"
0x1800441cd  mov     rcx, rsi; String1
0x1800441d0  call    wcscmp_0
0x1800441d5  test    eax, eax
0x1800441d7  jz      loc_180044283
0x1800441dd  cmp     ebx, 4D53414Ch
0x1800441e3  jz      short loc_180044249
0x1800441e5  cmp     ebx, 4D534B59h
0x1800441eb  jnz     loc_18004430C
0x1800441f1  mov     eax, [rsp+68h+arg_30]
0x1800441f8  mov     r9d, r14d
0x1800441fb  mov     [rsp+68h+var_38], eax
0x1800441ff  mov     r8, rbp
0x180044202  mov     rax, [rsp+68h+arg_20]
0x18004420a  mov     rdx, rsi
0x18004420d  mov     rcx, rdi
0x180044210  mov     [rsp+68h+var_48], rax
0x180044215  call    MSCryptEccGetKeyProperty
0x18004421a  mov     ebx, eax
0x18004421c  test    eax, eax
0x18004421e  js      loc_180044301
0x180044224  xor     eax, eax
0x180044226  mov     rbx, [rsp+68h+arg_0]
0x18004422b  add     rsp, 48h
0x18004422f  pop     r14
0x180044231  pop     rdi
0x180044232  pop     rsi
0x180044233  pop     rbp
0x180044234  retn
0x180044236  cmp     ebx, 4D53414Ch
0x18004423c  jz      short loc_1800441C6
0x18004423e  mov     r9d, 1C5h
0x180044244  jmp     loc_180082527
0x180044249  mov     eax, [rsp+68h+arg_30]
0x180044250  mov     r9d, r14d
0x180044253  mov     [rsp+68h+var_38], eax
0x180044257  mov     r8, rbp
0x18004425a  mov     rax, [rsp+68h+arg_20]
0x180044262  mov     rdx, rsi
0x180044265  mov     rcx, rdi
0x180044268  mov     [rsp+68h+var_48], rax
0x18004426d  call    MSCryptEccGetAlgProperty
0x180044272  mov     ebx, eax
0x180044274  test    eax, eax
0x180044276  jns     short loc_180044224
0x180044278  mov     r9d, 0E74h
0x18004427e  jmp     loc_18008250B
0x180044283  mov     ecx, [rdi+8]
0x180044286  mov     edx, [rsp+68h+arg_30]
0x18004428d  call    CryptAuditTranslateAlgID
0x180044292  mov     rdx, rax; Src
0x180044295  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004429c  nop     dword ptr [rax+00h]
0x1800442a0  cmp     word ptr [rax+rcx*2+2], 0
0x1800442a6  lea     rcx, [rcx+1]
0x1800442aa  jnz     short loc_1800442A0
0x1800442ac  mov     rax, [rsp+68h+arg_20]
0x1800442b4  lea     ecx, ds:2[rcx*2]
0x1800442bb  mov     [rax], ecx
0x1800442bd  test    rbp, rbp
0x1800442c0  jz      loc_180044224
0x1800442c6  cmp     r14d, ecx
0x1800442c9  jnb     loc_1800824FA
0x1800442cf  mov     eax, 0C0000023h
0x1800442d4  jmp     loc_180044226
0x1800442d9  mov     r9d, 0E46h
0x1800442df  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800442e6  lea     rdx, aStatus; "Status"
0x1800442ed  mov     ecx, 0C000000Dh
0x1800442f2  call    DebugTraceError
0x1800442f7  mov     eax, 0C000000Dh
0x1800442fc  jmp     loc_18004422B
0x180044301  mov     r9d, 0E83h
0x180044307  jmp     loc_18008250B
0x18004430c  mov     r9d, 0E8Ah
0x180044312  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044319  lea     rdx, aStatus; "Status"
0x180044320  mov     ecx, 0C000000Dh
0x180044325  call    DebugTraceError
0x18004432a  mov     eax, 0C000000Dh
0x18004432f  jmp     loc_180044226
0x180044334  mov     r9d, 1BDh
0x18004433a  jmp     loc_180082527
0x1800824fa  mov     r8d, ecx; Size
0x1800824fd  mov     rcx, rbp; void *
0x180082500  call    memcpy_0
0x180082505  nop
0x180082506  jmp     loc_180044224
0x18008250b  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180082512  mov     ecx, ebx
0x180082514  lea     rdx, aStatus; "Status"
0x18008251b  call    DebugTraceError
0x180082520  mov     eax, ebx
0x180082522  jmp     loc_180044226
0x180082527  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008252e  mov     ecx, 0C0000008h
0x180082533  lea     rdx, aStatus; "Status"
0x18008253a  call    DebugTraceError
0x18008253f  mov     eax, 0C0000008h
0x180082544  jmp     loc_180044226
```
