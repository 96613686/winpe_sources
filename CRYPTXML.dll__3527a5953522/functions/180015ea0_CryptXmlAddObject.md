# CryptXmlAddObject

- ea: `0x180015ea0`
- end: `0x1800160dc`
- name: `CryptXmlAddObject`
- size: `572`
- prototype: `HRESULT __stdcall(HCRYPTXML hSignatureOrObject, DWORD dwFlags, const CRYPT_XML_PROPERTY *rgProperty, ULONG cProperty, const CRYPT_XML_BLOB *pEncoded, const CRYPT_XML_OBJECT **ppObject)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180009478`
- `0x180012b24`
- `0x180014ce0`
- `0x180015ea0`
- `0x180016a0c`
- `0x18001860d`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015ff0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015ff0`

## string_xrefs

- `0x180015efc`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x180015f35`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x180015f74`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x180015fb3`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x18001600b`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x18001608b`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`
- `0x1800160a8`: `onecore\ds\security\cryptoapi\xml\lib\object.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlAddObject(
        HCRYPTXML hSignatureOrObject,
        DWORD dwFlags,
        const CRYPT_XML_PROPERTY *rgProperty,
        ULONG cProperty,
        const CRYPT_XML_BLOB *pEncoded,
        const CRYPT_XML_OBJECT **ppObject)
{
  HRESULT v7; // ebx
  const char *v8; // rax
  int v9; // r9d
  HRESULT v10; // edx
  __int64 DocCtxt; // rax
  __int64 v12; // rdi
  HRESULT v13; // r10d
  unsigned int v14; // r8d
  const char *v15; // rax
  _QWORD *v16; // rax
  void (__fastcall *v17)(__int64); // rax

  if ( ppObject )
    *ppObject = 0;
  if ( !hSignatureOrObject || cProperty && !rgProperty || !pEncoded || !pEncoded->cbData )
  {
    v7 = -2147024809;
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
    v9 = 389;
    goto LABEL_29;
  }
  if ( pEncoded->cbData > 0x7FFFFFF8 )
  {
    v7 = -2146885375;
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
    v9 = 396;
LABEL_10:
    v10 = v7;
LABEL_30:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v10, v8, v9);
    return v7;
  }
  if ( *(_DWORD *)hSignatureOrObject != 1145324610 )
  {
    if ( *(_DWORD *)hSignatureOrObject != 1145324612 )
    {
      v7 = -2146885370;
      v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
      v9 = 470;
      goto LABEL_29;
    }
    if ( ppObject )
    {
      v7 = -2147024809;
      v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
      v9 = 433;
      goto LABEL_29;
    }
    v12 = 0;
    if ( (dwFlags & 1) != 0 )
    {
      *((_DWORD *)hSignatureOrObject + 40) = 1;
      v16 = HeapAlloc(*((HANDLE *)hSignatureOrObject + 6), 0, pEncoded->cbData + 16LL);
      *((_QWORD *)hSignatureOrObject + 19) = v16;
      if ( !v16 )
      {
        v7 = -2147024882;
        v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
        v9 = 450;
        goto LABEL_10;
      }
      v16[1] = v16 + 2;
      **((_DWORD **)hSignatureOrObject + 19) = pEncoded->dwCharset;
      *(_DWORD *)(*((_QWORD *)hSignatureOrObject + 19) + 4LL) = pEncoded->cbData;
      memcpy_0(*(void **)(*((_QWORD *)hSignatureOrObject + 19) + 8LL), pEncoded->pbData, pEncoded->cbData);
    }
    else
    {
      *((_QWORD *)hSignatureOrObject + 19) = pEncoded;
    }
LABEL_24:
    v7 = 0;
    if ( !v12 )
      return v7;
    goto LABEL_25;
  }
  DocCtxt = I_CryptXmlGetDocCtxt(hSignatureOrObject, (_BYTE)dwFlags, rgProperty);
  v12 = DocCtxt;
  if ( !DocCtxt )
  {
    v7 = -2146885370;
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
    v9 = 408;
LABEL_29:
    v10 = v13;
    goto LABEL_30;
  }
  I_CryptXmlLock(DocCtxt);
  v7 = I_CryptXmlDecodeObject(
         v12,
         (__int64)hSignatureOrObject,
         v14,
         (__int64)pEncoded,
         (struct _CRYPT_XML_OBJECT **)ppObject);
  if ( v7 >= 0 )
    goto LABEL_24;
  v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\object.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v7, v15, 423);
LABEL_25:
  v17 = *(void (__fastcall **)(__int64))(v12 + 128);
  if ( v17 )
    v17(v12);
  return v7;
}

```

## disassembly

```asm
0x180015ea0  push    rbx
0x180015ea2  push    rsi
0x180015ea3  push    rdi
0x180015ea4  push    r14
0x180015ea6  sub     rsp, 38h
0x180015eaa  mov     r14, [rsp+58h+ppObject]
0x180015eb2  mov     rbx, rcx
0x180015eb5  test    r14, r14
0x180015eb8  jz      short loc_180015EC1
0x180015eba  mov     qword ptr [r14], 0
0x180015ec1  test    rbx, rbx
0x180015ec4  jz      loc_1800160A2
0x180015eca  test    r9d, r9d
0x180015ecd  jz      short loc_180015ED8
0x180015ecf  test    r8, r8
0x180015ed2  jz      loc_1800160A2
0x180015ed8  mov     rsi, [rsp+58h+pEncoded]
0x180015ee0  test    rsi, rsi
0x180015ee3  jz      loc_1800160A2
0x180015ee9  cmp     dword ptr [rsi+4], 0
0x180015eed  jz      loc_1800160A2
0x180015ef3  cmp     dword ptr [rsi+4], 7FFFFFF8h
0x180015efa  jbe     short loc_180015F1A
0x180015efc  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180015f03  mov     ebx, 80092101h
0x180015f08  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180015f0d  mov     r9d, 18Ch
0x180015f13  mov     edx, ebx
0x180015f15  jmp     loc_1800160C0
0x180015f1a  cmp     dword ptr [rcx], 44444442h
0x180015f20  jnz     short loc_180015F9C
0x180015f22  call    I_CryptXmlGetDocCtxt
0x180015f27  mov     rdi, rax
0x180015f2a  test    rax, rax
0x180015f2d  jnz     short loc_180015F4F
0x180015f2f  mov     r10d, 80092106h
0x180015f35  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180015f3c  mov     ebx, r10d
0x180015f3f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180015f44  mov     r9d, 198h
0x180015f4a  jmp     loc_1800160BD
0x180015f4f  mov     rcx, rdi
0x180015f52  call    I_CryptXmlLock
0x180015f57  mov     r9, rsi
0x180015f5a  mov     [rsp+58h+var_38], r14
0x180015f5f  mov     rdx, rbx
0x180015f62  mov     rcx, rdi
0x180015f65  call    I_CryptXmlDecodeObject
0x180015f6a  mov     ebx, eax
0x180015f6c  test    eax, eax
0x180015f6e  jns     loc_180016068
0x180015f74  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180015f7b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180015f80  mov     r8, rax
0x180015f83  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180015f8a  mov     edx, ebx
0x180015f8c  mov     r9d, 1A7h
0x180015f92  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180015f97  jmp     loc_18001606F
0x180015f9c  cmp     dword ptr [rcx], 44444444h
0x180015fa2  jnz     loc_180016085
0x180015fa8  test    r14, r14
0x180015fab  jz      short loc_180015FCD
0x180015fad  mov     r10d, 80070057h
0x180015fb3  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180015fba  mov     ebx, r10d
0x180015fbd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180015fc2  mov     r9d, 1B1h
0x180015fc8  jmp     loc_1800160BD
0x180015fcd  xor     edi, edi
0x180015fcf  test    dl, 1
0x180015fd2  jz      loc_180016061
0x180015fd8  mov     dword ptr [rcx+0A0h], 1
0x180015fe2  xor     edx, edx; dwFlags
0x180015fe4  mov     r8d, [rsi+4]
0x180015fe8  mov     rcx, [rcx+30h]; hHeap
0x180015fec  add     r8, 10h; dwBytes
0x180015ff0  call    cs:__imp_HeapAlloc
0x180015ff7  nop     dword ptr [rax+rax+00h]
0x180015ffc  mov     [rbx+98h], rax
0x180016003  mov     rcx, rax
0x180016006  test    rax, rax
0x180016009  jnz     short loc_180016027
0x18001600b  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016012  mov     ebx, 8007000Eh
0x180016017  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001601c  mov     r9d, 1C2h
0x180016022  jmp     loc_180015F13
0x180016027  add     rax, 10h
0x18001602b  mov     [rcx+8], rax
0x18001602f  mov     rcx, [rbx+98h]
0x180016036  mov     eax, [rsi]
0x180016038  mov     [rcx], eax
0x18001603a  mov     rcx, [rbx+98h]
0x180016041  mov     eax, [rsi+4]
0x180016044  mov     [rcx+4], eax
0x180016047  mov     rcx, [rbx+98h]
0x18001604e  mov     r8d, [rsi+4]; Size
0x180016052  mov     rdx, [rsi+8]; Src
0x180016056  mov     rcx, [rcx+8]; void *
0x18001605a  call    memcpy_0
0x18001605f  jmp     short loc_180016068
0x180016061  mov     [rcx+98h], rsi
0x180016068  xor     ebx, ebx
0x18001606a  test    rdi, rdi
0x18001606d  jz      short loc_1800160CF
0x18001606f  mov     rax, [rdi+80h]
0x180016076  test    rax, rax
0x180016079  jz      short loc_1800160CF
0x18001607b  mov     rcx, rdi
0x18001607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016083  jmp     short loc_1800160CF
0x180016085  mov     r10d, 80092106h
0x18001608b  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016092  mov     ebx, r10d
0x180016095  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001609a  mov     r9d, 1D6h
0x1800160a0  jmp     short loc_1800160BD
0x1800160a2  mov     r10d, 80070057h
0x1800160a8  lea     rcx, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800160af  mov     ebx, r10d
0x1800160b2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800160b7  mov     r9d, 185h
0x1800160bd  mov     edx, r10d
0x1800160c0  mov     r8, rax
0x1800160c3  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800160ca  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800160cf  mov     eax, ebx
0x1800160d1  add     rsp, 38h
0x1800160d5  pop     r14
0x1800160d7  pop     rdi
0x1800160d8  pop     rsi
0x1800160d9  pop     rbx
0x1800160da  retn
```
