# I_XmlSetEncoded(_CRYPT_XML_BLOB const *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER * *)

- ea: `0x180017938`
- end: `0x180017992`
- name: `?I_XmlSetEncoded@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_WS_XML_BUFFER@@@Z`
- size: `90`
- prototype: `int(const struct _CRYPT_XML_BLOB *, struct _CRYPT_XML_WS_STATE *, struct _WS_XML_BUFFER **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800115a8`
- `0x1800176d0`

## callees

- `0x1800070d0`
- `0x180014ce0`
- `0x180017938`
- `0x180017998`

## string_xrefs

- `0x180017962`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlSetEncoded(
        const struct _CRYPT_XML_BLOB *a1,
        struct _WS_XML_READER **a2,
        struct _WS_XML_BUFFER **a3)
{
  int v3; // ebx
  const char *v4; // rax

  v3 = I_XmlSetEncodedEx(a1, a2[1], a2[2], a2[6], *a2, a3);
  if ( v3 >= 0 )
  {
    return 0;
  }
  else
  {
    v4 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v3, v4, 517);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017938  push    rbx
0x18001793a  sub     rsp, 30h
0x18001793e  mov     rax, [rdx]
0x180017941  mov     r9, [rdx+30h]; struct _WS_HEAP *
0x180017945  mov     [rsp+38h+var_10], r8; struct _WS_XML_BUFFER **
0x18001794a  mov     r8, [rdx+10h]; struct _WS_XML_WRITER *
0x18001794e  mov     rdx, [rdx+8]; struct _WS_XML_READER *
0x180017952  mov     [rsp+38h+var_18], rax; struct _WS_ERROR *
0x180017957  call    ?I_XmlSetEncodedEx@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncodedEx(_CRYPT_XML_BLOB const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,_WS_XML_BUFFER * *)
0x18001795c  mov     ebx, eax
0x18001795e  test    eax, eax
0x180017960  jns     short loc_180017987
0x180017962  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017969  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001796e  mov     r8, rax
0x180017971  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180017978  mov     edx, ebx
0x18001797a  mov     r9d, 205h
0x180017980  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180017985  jmp     short loc_180017989
0x180017987  xor     ebx, ebx
0x180017989  mov     eax, ebx
0x18001798b  add     rsp, 30h
0x18001798f  pop     rbx
0x180017990  retn
```
