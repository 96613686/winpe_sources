# CryptXmlGetReference

- ea: `0x1800162b0`
- end: `0x180016323`
- name: `CryptXmlGetReference`
- size: `115`
- prototype: `HRESULT __stdcall(HCRYPTXML hCryptXml, const CRYPT_XML_REFERENCE **ppStruct)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180014ce0`
- `0x1800162b0`

## string_xrefs

- `0x1800162cd`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`
- `0x1800162f2`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlGetReference(HCRYPTXML hCryptXml, const CRYPT_XML_REFERENCE **ppStruct)
{
  HRESULT v2; // ebx
  const char *v3; // rax
  int v4; // r9d

  v2 = 0;
  if ( !hCryptXml || !ppStruct )
  {
    v2 = -2147024809;
    v3 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp");
    v4 = 304;
    goto LABEL_7;
  }
  *ppStruct = 0;
  if ( *(_DWORD *)hCryptXml != 1145324611 )
  {
    v2 = -2146885370;
    v3 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp");
    v4 = 313;
LABEL_7:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v2, v3, v4);
    return v2;
  }
  *ppStruct = (const CRYPT_XML_REFERENCE *)*((_QWORD *)hCryptXml + 17);
  return v2;
}

```

## disassembly

```asm
0x1800162b0  push    rbx
0x1800162b2  sub     rsp, 20h
0x1800162b6  xor     ebx, ebx
0x1800162b8  test    rcx, rcx
0x1800162bb  jz      short loc_1800162F2
0x1800162bd  test    rdx, rdx
0x1800162c0  jz      short loc_1800162F2
0x1800162c2  mov     [rdx], rbx
0x1800162c5  cmp     dword ptr [rcx], 44444443h
0x1800162cb  jz      short loc_1800162E6
0x1800162cd  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800162d4  mov     ebx, 80092106h
0x1800162d9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800162de  mov     r9d, 139h
0x1800162e4  jmp     short loc_180016309
0x1800162e6  mov     rax, [rcx+88h]
0x1800162ed  mov     [rdx], rax
0x1800162f0  jmp     short loc_18001631A
0x1800162f2  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800162f9  mov     ebx, 80070057h
0x1800162fe  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016303  mov     r9d, 130h
0x180016309  mov     r8, rax
0x18001630c  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180016313  mov     edx, ebx
0x180016315  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001631a  mov     eax, ebx
0x18001631c  add     rsp, 20h
0x180016320  pop     rbx
0x180016321  retn
```
