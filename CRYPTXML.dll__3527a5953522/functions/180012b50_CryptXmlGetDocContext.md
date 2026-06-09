# CryptXmlGetDocContext

- ea: `0x180012b50`
- end: `0x180012bc3`
- name: `CryptXmlGetDocContext`
- size: `115`
- prototype: `HRESULT __stdcall(HCRYPTXML hCryptXml, const CRYPT_XML_DOC_CTXT **ppStruct)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180012b50`
- `0x180014ce0`

## string_xrefs

- `0x180012b6d`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`
- `0x180012b92`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlGetDocContext(HCRYPTXML hCryptXml, const CRYPT_XML_DOC_CTXT **ppStruct)
{
  HRESULT v2; // ebx
  const char *v3; // rax
  int v4; // r9d

  v2 = 0;
  if ( !hCryptXml || !ppStruct )
  {
    v2 = -2147024809;
    v3 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp");
    v4 = 218;
    goto LABEL_7;
  }
  *ppStruct = 0;
  if ( *(_DWORD *)hCryptXml != 1145324609 )
  {
    v2 = -2146885370;
    v3 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp");
    v4 = 227;
LABEL_7:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v2, v3, v4);
    return v2;
  }
  *ppStruct = (const CRYPT_XML_DOC_CTXT *)*((_QWORD *)hCryptXml + 17);
  return v2;
}

```

## disassembly

```asm
0x180012b50  push    rbx
0x180012b52  sub     rsp, 20h
0x180012b56  xor     ebx, ebx
0x180012b58  test    rcx, rcx
0x180012b5b  jz      short loc_180012B92
0x180012b5d  test    rdx, rdx
0x180012b60  jz      short loc_180012B92
0x180012b62  mov     [rdx], rbx
0x180012b65  cmp     dword ptr [rcx], 44444441h
0x180012b6b  jz      short loc_180012B86
0x180012b6d  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012b74  mov     ebx, 80092106h
0x180012b79  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012b7e  mov     r9d, 0E3h
0x180012b84  jmp     short loc_180012BA9
0x180012b86  mov     rax, [rcx+88h]
0x180012b8d  mov     [rdx], rax
0x180012b90  jmp     short loc_180012BBA
0x180012b92  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012b99  mov     ebx, 80070057h
0x180012b9e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012ba3  mov     r9d, 0DAh
0x180012ba9  mov     r8, rax
0x180012bac  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180012bb3  mov     edx, ebx
0x180012bb5  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180012bba  mov     eax, ebx
0x180012bbc  add     rsp, 20h
0x180012bc0  pop     rbx
0x180012bc1  retn
```
