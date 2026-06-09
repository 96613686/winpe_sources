# MSCryptEcDhGetProperty

- ea: `0x180043fa0`
- end: `0x18004416e`
- name: `MSCryptEcDhGetProperty`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180043fa0`
- `0x180044350`
- `0x18004490c`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x18004410e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044141`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800824bb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800824d7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcDhGetProperty(
        _DWORD *a1,
        const wchar_t *a2,
        int *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  int v10; // ebx
  int AlgProperty; // edi
  __int64 v13; // r9
  __int64 v14; // r9
  wchar_t *v15; // rdx
  unsigned int i; // ecx
  __int64 v17; // rax
  unsigned int v19; // eax
  __int64 v20; // [rsp+28h] [rbp-40h]

  if ( a6 )
  {
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3654);
    return 3221225485LL;
  }
  if ( !a1 || *a1 < 0xCu )
  {
    v13 = 445;
    goto LABEL_28;
  }
  v10 = a1[1];
  if ( v10 == 1297304409 || v10 == 1297301836 )
  {
    if ( wcscmp_0(a2, L"AlgorithmName") )
    {
      if ( v10 == 1297301836 )
      {
        AlgProperty = MSCryptEccGetAlgProperty(a1, a2, a3, a4, a5);
        if ( AlgProperty >= 0 )
          return 0;
        v14 = 3700;
      }
      else
      {
        AlgProperty = MSCryptEccGetKeyProperty((__int64)a1, (__int64)a2, a3, a4, a5, v20, 0);
        if ( AlgProperty >= 0 )
          return 0;
        v14 = 3715;
      }
      DebugTraceError(
        (unsigned int)AlgProperty,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        v14);
      return (unsigned int)AlgProperty;
    }
    v15 = 0;
    for ( i = 0; i < 4; ++i )
    {
      if ( a1[2] == *((_DWORD *)&off_1800847D0 + 12 * i + 2) )
      {
        v15 = (&off_1800847D0)[6 * i];
        break;
      }
    }
    v17 = -1;
    while ( v15[++v17] != 0 )
      ;
    v19 = 2 * v17 + 2;
    *a5 = v19;
    if ( a3 )
    {
      if ( a4 < v19 )
        return 3221225507LL;
      memcpy_0(a3, v15, v19);
    }
    return 0;
  }
  v13 = 453;
LABEL_28:
  DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v13);
  return 3221225480LL;
}

```

## disassembly

```asm
0x180043fa0  push    rbp
0x180043fa2  push    rsi
0x180043fa3  push    rdi
0x180043fa4  push    r14
0x180043fa6  sub     rsp, 48h
0x180043faa  cmp     [rsp+68h+arg_28], 0
0x180043fb2  mov     r14d, r9d
0x180043fb5  mov     rbp, r8
0x180043fb8  mov     rsi, rdx
0x180043fbb  mov     rdi, rcx
0x180043fbe  jnz     loc_180044108
0x180043fc4  mov     [rsp+68h+arg_0], rbx
0x180043fc9  test    rcx, rcx
0x180043fcc  jz      loc_180044163
0x180043fd2  cmp     dword ptr [rcx], 0Ch
0x180043fd5  jb      loc_180044163
0x180043fdb  mov     ebx, [rcx+4]
0x180043fde  cmp     ebx, 4D534B59h
0x180043fe4  jnz     short loc_180044051
0x180043fe6  lea     rdx, aAlgorithmname; "AlgorithmName"
0x180043fed  mov     rcx, rsi; String1
0x180043ff0  call    wcscmp_0
0x180043ff5  test    eax, eax
0x180043ff7  jz      loc_180044099
0x180043ffd  cmp     ebx, 4D53414Ch
0x180044003  jz      short loc_180044064
0x180044005  cmp     ebx, 4D534B59h
0x18004400b  jnz     loc_18004413B
0x180044011  mov     rax, [rsp+68h+arg_20]
0x180044019  xor     ebx, ebx
0x18004401b  mov     [rsp+68h+var_38], ebx
0x18004401f  mov     r9d, r14d
0x180044022  mov     r8, rbp
0x180044025  mov     [rsp+68h+var_48], rax
0x18004402a  mov     rdx, rsi
0x18004402d  mov     rcx, rdi
0x180044030  call    MSCryptEccGetKeyProperty
0x180044035  mov     edi, eax
0x180044037  test    eax, eax
0x180044039  js      loc_180044130
0x18004403f  mov     eax, ebx
0x180044041  mov     rbx, [rsp+68h+arg_0]
0x180044046  add     rsp, 48h
0x18004404a  pop     r14
0x18004404c  pop     rdi
0x18004404d  pop     rsi
0x18004404e  pop     rbp
0x18004404f  retn
0x180044051  cmp     ebx, 4D53414Ch
0x180044057  jz      short loc_180043FE6
0x180044059  mov     r9d, 1C5h
0x18004405f  jmp     loc_1800824D7
0x180044064  mov     rax, [rsp+68h+arg_20]
0x18004406c  xor     ebx, ebx
0x18004406e  mov     [rsp+68h+var_38], ebx
0x180044072  mov     r9d, r14d
0x180044075  mov     r8, rbp
0x180044078  mov     [rsp+68h+var_48], rax
0x18004407d  mov     rdx, rsi
0x180044080  mov     rcx, rdi
0x180044083  call    MSCryptEccGetAlgProperty
0x180044088  mov     edi, eax
0x18004408a  test    eax, eax
0x18004408c  jns     short loc_18004403F
0x18004408e  mov     r9d, 0E74h
0x180044094  jmp     loc_1800824BB
0x180044099  xor     ebx, ebx
0x18004409b  lea     r9, off_1800847D0; "ECDH_P256"
0x1800440a2  mov     edx, ebx
0x1800440a4  mov     ecx, ebx
0x1800440a6  cmp     ecx, 4
0x1800440a9  jnb     short loc_1800440C6
0x1800440ab  mov     eax, ecx
0x1800440ad  lea     r8, [rax+rax*2]
0x1800440b1  add     r8, r8
0x1800440b4  mov     eax, [r9+r8*8+8]
0x1800440b9  cmp     [rdi+8], eax
0x1800440bc  jz      short loc_1800440C2
0x1800440be  inc     ecx
0x1800440c0  jmp     short loc_1800440A6
0x1800440c2  mov     rdx, [r9+r8*8]; Src
0x1800440c6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800440cd  nop     dword ptr [rax]
0x1800440d0  cmp     [rdx+rax*2+2], bx
0x1800440d5  lea     rax, [rax+1]
0x1800440d9  jnz     short loc_1800440D0
0x1800440db  mov     rcx, [rsp+68h+arg_20]
0x1800440e3  lea     eax, ds:2[rax*2]
0x1800440ea  mov     [rcx], eax
0x1800440ec  test    rbp, rbp
0x1800440ef  jz      loc_18004403F
0x1800440f5  cmp     r14d, eax
0x1800440f8  jnb     loc_1800824AA
0x1800440fe  mov     eax, 0C0000023h
0x180044103  jmp     loc_180044041
0x180044108  mov     r9d, 0E46h
0x18004410e  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044115  lea     rdx, aStatus; "Status"
0x18004411c  mov     ecx, 0C000000Dh
0x180044121  call    DebugTraceError
0x180044126  mov     eax, 0C000000Dh
0x18004412b  jmp     loc_180044046
0x180044130  mov     r9d, 0E83h
0x180044136  jmp     loc_1800824BB
0x18004413b  mov     r9d, 0E8Ah
0x180044141  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044148  lea     rdx, aStatus; "Status"
0x18004414f  mov     ecx, 0C000000Dh
0x180044154  call    DebugTraceError
0x180044159  mov     eax, 0C000000Dh
0x18004415e  jmp     loc_180044041
0x180044163  mov     r9d, 1BDh
0x180044169  jmp     loc_1800824D7
0x1800824aa  mov     r8d, eax; Size
0x1800824ad  mov     rcx, rbp; void *
0x1800824b0  call    memcpy_0
0x1800824b5  nop
0x1800824b6  jmp     loc_18004403F
0x1800824bb  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800824c2  mov     ecx, edi
0x1800824c4  lea     rdx, aStatus; "Status"
0x1800824cb  call    DebugTraceError
0x1800824d0  mov     eax, edi
0x1800824d2  jmp     loc_180044041
0x1800824d7  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800824de  mov     ecx, 0C0000008h
0x1800824e3  lea     rdx, aStatus; "Status"
0x1800824ea  call    DebugTraceError
0x1800824ef  mov     eax, 0C0000008h
0x1800824f4  jmp     loc_180044041
```
