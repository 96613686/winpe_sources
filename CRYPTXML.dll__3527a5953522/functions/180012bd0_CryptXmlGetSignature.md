# CryptXmlGetSignature

- ea: `0x180012bd0`
- end: `0x180012c5e`
- name: `CryptXmlGetSignature`
- size: `142`
- prototype: `HRESULT __stdcall(HCRYPTXML hCryptXml, const CRYPT_XML_SIGNATURE **ppStruct)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180012bd0`
- `0x180014ce0`

## string_xrefs

- `0x180012bed`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`
- `0x180012c21`: `onecore\ds\security\cryptoapi\xml\lib\handle.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlGetSignature(HCRYPTXML hCryptXml, const CRYPT_XML_SIGNATURE **ppStruct)
{
  HRESULT v2; // ebx
  const char *v3; // r8
  int v4; // r9d
  const char *v5; // rax
  bool v6; // zf

  v2 = 0;
  if ( !hCryptXml || !ppStruct )
  {
    v2 = -2147024809;
    v3 = "";
    while ( 1 )
    {
      v5 = v3--;
      v6 = *v3 == 92;
      if ( *v3 == 92 )
        break;
      if ( v3 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp" )
      {
        v6 = *v3 == 92;
        break;
      }
    }
    if ( v6 )
      v3 = v5;
    v4 = 261;
    goto LABEL_13;
  }
  *ppStruct = 0;
  if ( *(_DWORD *)hCryptXml != 1145324610 )
  {
    v2 = -2146885370;
    v3 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\handle.cpp");
    v4 = 270;
LABEL_13:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v2, v3, v4);
    return v2;
  }
  *ppStruct = (const CRYPT_XML_SIGNATURE *)*((_QWORD *)hCryptXml + 18);
  return v2;
}

```

## disassembly

```asm
0x180012bd0  push    rbx
0x180012bd2  sub     rsp, 20h
0x180012bd6  xor     ebx, ebx
0x180012bd8  test    rcx, rcx
0x180012bdb  jz      short loc_180012C15
0x180012bdd  test    rdx, rdx
0x180012be0  jz      short loc_180012C15
0x180012be2  mov     [rdx], rbx
0x180012be5  cmp     dword ptr [rcx], 44444442h
0x180012beb  jz      short loc_180012C09
0x180012bed  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012bf4  mov     ebx, 80092106h
0x180012bf9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180012bfe  mov     r8, rax
0x180012c01  mov     r9d, 10Eh
0x180012c07  jmp     short loc_180012C47
0x180012c09  mov     rax, [rcx+90h]
0x180012c10  mov     [rdx], rax
0x180012c13  jmp     short loc_180012C55
0x180012c15  mov     ebx, 80070057h
0x180012c1a  lea     r8, aOnecoreDsSecur_7+30h; ""
0x180012c21  lea     rcx, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012c28  mov     rax, r8
0x180012c2b  dec     r8
0x180012c2e  cmp     byte ptr [r8], 5Ch ; '\'
0x180012c32  jz      short loc_180012C3D
0x180012c34  cmp     r8, rcx
0x180012c37  ja      short loc_180012C28
0x180012c39  cmp     byte ptr [r8], 5Ch ; '\'
0x180012c3d  cmovz   r8, rax
0x180012c41  mov     r9d, 105h
0x180012c47  mov     edx, ebx
0x180012c49  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180012c50  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180012c55  mov     eax, ebx
0x180012c57  add     rsp, 20h
0x180012c5b  pop     rbx
0x180012c5c  retn
```
