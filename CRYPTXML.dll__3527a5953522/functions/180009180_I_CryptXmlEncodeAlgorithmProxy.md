# I_CryptXmlEncodeAlgorithmProxy

- ea: `0x180009180`
- end: `0x180009309`
- name: `I_CryptXmlEncodeAlgorithmProxy`
- size: `393`
- prototype: `__int64 __usercall@<rax>(CRYPT_XML_ALGORITHM *pXmlAlgorithm@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003650`
- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x180008b10`
- `0x180009180`
- `0x180009310`
- `0x180014ce0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092d5`

## string_xrefs

- `0x1800091d5`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180009244`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000928c`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlEncodeAlgorithmProxy(
        CRYPT_XML_ALGORITHM *pXmlAlgorithm,
        int a2,
        unsigned int a3,
        _QWORD *a4,
        _DWORD *a5)
{
  _DWORD *v5; // r14
  int CryptoInterface; // ebx
  const char *v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(CRYPT_XML_ALGORITHM *, CRYPT_XML_ALGORITHM_INFO **); // rax
  HRESULT AlgorithmInfo; // eax
  const char *v14; // rax
  const char *v15; // rax
  __int128 v17; // [rsp+30h] [rbp-38h] BYREF
  CRYPT_XML_ALGORITHM_INFO *ppAlgInfo; // [rsp+70h] [rbp+8h] BYREF
  __int64 v19; // [rsp+88h] [rbp+20h] BYREF

  v5 = a5;
  v19 = 0;
  *a5 = 0;
  ppAlgInfo = 0;
  v17 = 0;
  *a4 = 0;
  if ( pXmlAlgorithm->Encoded.cbData )
    return 1;
  CryptoInterface = I_CryptXmlGetCryptoInterface((__int64)pXmlAlgorithm, a2, &v19);
  if ( CryptoInterface >= 0 )
  {
    v11 = v19;
    if ( *(_QWORD *)(v19 + 8) )
    {
      v12 = *(__int64 (__fastcall **)(CRYPT_XML_ALGORITHM *, CRYPT_XML_ALGORITHM_INFO **))(v19 + 64);
      if ( v12 )
        AlgorithmInfo = v12(pXmlAlgorithm, &ppAlgInfo);
      else
        AlgorithmInfo = CryptXmlGetAlgorithmInfo(pXmlAlgorithm, 0x10000000u, &ppAlgInfo);
      CryptoInterface = AlgorithmInfo;
      if ( AlgorithmInfo < 0 )
      {
        v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v14, 1857);
        goto LABEL_13;
      }
      CryptoInterface = (*(__int64 (__fastcall **)(CRYPT_XML_ALGORITHM_INFO *, _QWORD, __int128 *, void *))(v11 + 8))(
                          ppAlgInfo,
                          a3,
                          &v17,
                          &CRYPT_XML_ENCODE_ALGORITHM_CALLBACK);
      if ( CryptoInterface < 0 )
      {
        v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v15, 1869);
        goto LABEL_13;
      }
    }
    CryptoInterface = 0;
    *a4 = v17;
    *v5 = DWORD2(v17);
    goto LABEL_13;
  }
  v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v10, 1829);
LABEL_13:
  if ( ppAlgInfo )
    LocalFree(ppAlgInfo);
  return (unsigned int)CryptoInterface;
}

```

## disassembly

```asm
0x180009180  mov     rax, rsp
0x180009183  push    rbp
0x180009184  push    rsi
0x180009185  push    r12
0x180009187  push    r14
0x180009189  push    r15
0x18000918b  sub     rsp, 40h
0x18000918f  mov     r14, [rsp+68h+arg_20]
0x180009197  xor     r12d, r12d
0x18000919a  xorps   xmm0, xmm0
0x18000919d  mov     rsi, r9
0x1800091a0  mov     r15d, r8d
0x1800091a3  mov     rbp, rcx
0x1800091a6  mov     [rax+20h], r12
0x1800091aa  mov     [r14], r12d
0x1800091ad  mov     [rax+8], r12
0x1800091b1  movups  xmmword ptr [rax-38h], xmm0
0x1800091b5  mov     [r9], r12
0x1800091b8  cmp     [rcx+14h], r12d
0x1800091bc  ja      loc_1800092F6
0x1800091c2  lea     r8, [rax+20h]
0x1800091c6  mov     [rax+10h], rbx
0x1800091ca  call    I_CryptXmlGetCryptoInterface
0x1800091cf  mov     ebx, eax
0x1800091d1  test    eax, eax
0x1800091d3  jns     short loc_1800091FD
0x1800091d5  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800091dc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800091e1  mov     r8, rax
0x1800091e4  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800091eb  mov     edx, ebx
0x1800091ed  mov     r9d, 725h
0x1800091f3  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800091f8  jmp     loc_1800092CB
0x1800091fd  mov     [rsp+68h+arg_10], rdi
0x180009205  mov     rdi, [rsp+68h+arg_18]
0x18000920d  cmp     [rdi+8], r12
0x180009211  jz      loc_1800092B1
0x180009217  mov     rax, [rdi+40h]
0x18000921b  mov     rcx, rbp; pXmlAlgorithm
0x18000921e  test    rax, rax
0x180009221  jz      short loc_18000922F
0x180009223  lea     rdx, [rsp+68h+ppAlgInfo]
0x180009228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000922d  jmp     short loc_18000923E
0x18000922f  lea     r8, [rsp+68h+ppAlgInfo]; ppAlgInfo
0x180009234  mov     edx, 10000000h; dwFlags
0x180009239  call    CryptXmlGetAlgorithmInfo
0x18000923e  mov     ebx, eax
0x180009240  test    eax, eax
0x180009242  jns     short loc_180009269
0x180009244  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000924b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009250  mov     r8, rax
0x180009253  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000925a  mov     edx, ebx
0x18000925c  mov     r9d, 741h
0x180009262  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180009267  jmp     short loc_1800092C3
0x180009269  mov     rcx, [rsp+68h+ppAlgInfo]
0x18000926e  lea     r9, CRYPT_XML_ENCODE_ALGORITHM_CALLBACK
0x180009275  mov     rax, [rdi+8]
0x180009279  lea     r8, [rsp+68h+var_38]
0x18000927e  mov     edx, r15d
0x180009281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009286  mov     ebx, eax
0x180009288  test    eax, eax
0x18000928a  jns     short loc_1800092B1
0x18000928c  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180009293  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180009298  mov     r8, rax
0x18000929b  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800092a2  mov     edx, ebx
0x1800092a4  mov     r9d, 74Dh
0x1800092aa  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800092af  jmp     short loc_1800092C3
0x1800092b1  mov     rax, [rsp+68h+var_38]
0x1800092b6  mov     ebx, r12d
0x1800092b9  mov     [rsi], rax
0x1800092bc  mov     eax, [rsp+68h+var_30]
0x1800092c0  mov     [r14], eax
0x1800092c3  mov     rdi, [rsp+68h+arg_10]
0x1800092cb  mov     rcx, [rsp+68h+ppAlgInfo]; hMem
0x1800092d0  test    rcx, rcx
0x1800092d3  jz      short loc_1800092E1
0x1800092d5  call    cs:__imp_LocalFree
0x1800092dc  nop     dword ptr [rax+rax+00h]
0x1800092e1  mov     eax, ebx
0x1800092e3  mov     rbx, [rsp+68h+arg_8]
0x1800092e8  add     rsp, 40h
0x1800092ec  pop     r15
0x1800092ee  pop     r14
0x1800092f0  pop     r12
0x1800092f2  pop     rsi
0x1800092f3  pop     rbp
0x1800092f4  retn
0x1800092f6  mov     eax, 1
0x1800092fb  add     rsp, 40h
0x1800092ff  pop     r15
0x180009301  pop     r14
0x180009303  pop     r12
0x180009305  pop     rsi
0x180009306  pop     rbp
0x180009307  retn
```
