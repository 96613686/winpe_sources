# CRYPT_XML_ENCODE_ALGORITHM_CALLBACK

- ea: `0x180016e40`
- end: `0x180016eef`
- name: `CRYPT_XML_ENCODE_ALGORITHM_CALLBACK`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x18000b1a0`
- `0x18000fc70`
- `0x180014ce0`
- `0x180016e40`
- `0x18001860d`

## string_xrefs

- `0x180016e62`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180016eaa`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
__int64 __fastcall CRYPT_XML_ENCODE_ALGORITHM_CALLBACK(__int64 a1, const void *a2, unsigned int a3)
{
  unsigned int v3; // eax
  size_t v5; // rdi
  __int64 v7; // rcx
  unsigned int v8; // ebx
  const char *v9; // rax
  int v10; // r9d
  __int64 v11; // rax
  void *v12; // rcx

  v3 = *(_DWORD *)(a1 + 8);
  v5 = a3;
  v7 = v3 + a3;
  if ( (unsigned int)v7 >= v3 )
  {
    if ( v3 )
      v11 = CryptXmlRealloc(*(_QWORD *)a1, a2, (unsigned int)v7);
    else
      v11 = CryptXmlAlloc(v7, (unsigned int)v7);
    if ( v11 )
    {
      v12 = (void *)(v11 + *(unsigned int *)(a1 + 8));
      *(_QWORD *)a1 = v11;
      memcpy_0(v12, a2, v5);
      *(_DWORD *)(a1 + 8) += v5;
      return 0;
    }
    v8 = -2147024882;
    v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
    v10 = 1773;
  }
  else
  {
    v8 = -2147024362;
    v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
    v10 = 1750;
  }
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v8, v9, v10);
  return v8;
}

```

## disassembly

```asm
0x180016e40  mov     [rsp+arg_0], rbx
0x180016e45  mov     [rsp+arg_8], rsi
0x180016e4a  push    rdi
0x180016e4b  sub     rsp, 20h
0x180016e4f  mov     eax, [rcx+8]
0x180016e52  mov     rbx, rcx
0x180016e55  mov     edi, r8d
0x180016e58  mov     rsi, rdx
0x180016e5b  lea     ecx, [rax+rdi]
0x180016e5e  cmp     ecx, eax
0x180016e60  jnb     short loc_180016E8C
0x180016e62  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016e69  mov     ebx, 80070216h
0x180016e6e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016e73  mov     r9d, 6D6h
0x180016e79  mov     r8, rax
0x180016e7c  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180016e83  mov     edx, ebx
0x180016e85  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180016e8a  jmp     short loc_180016EDC
0x180016e8c  mov     r8d, ecx
0x180016e8f  test    eax, eax
0x180016e91  jnz     short loc_180016E9D
0x180016e93  mov     edx, r8d
0x180016e96  call    CryptXmlAlloc
0x180016e9b  jmp     short loc_180016EA5
0x180016e9d  mov     rcx, [rbx]
0x180016ea0  call    CryptXmlRealloc
0x180016ea5  test    rax, rax
0x180016ea8  jnz     short loc_180016EC3
0x180016eaa  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016eb1  mov     ebx, 8007000Eh
0x180016eb6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016ebb  mov     r9d, 6EDh
0x180016ec1  jmp     short loc_180016E79
0x180016ec3  mov     ecx, [rbx+8]
0x180016ec6  mov     r8, rdi; Size
0x180016ec9  add     rcx, rax; void *
0x180016ecc  mov     [rbx], rax
0x180016ecf  mov     rdx, rsi; Src
0x180016ed2  call    memcpy_0
0x180016ed7  add     [rbx+8], edi
0x180016eda  xor     ebx, ebx
0x180016edc  mov     rsi, [rsp+28h+arg_8]
0x180016ee1  mov     eax, ebx
0x180016ee3  mov     rbx, [rsp+28h+arg_0]
0x180016ee8  add     rsp, 20h
0x180016eec  pop     rdi
0x180016eed  retn
```
