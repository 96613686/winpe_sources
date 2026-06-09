# I_XmlMarshallSignature(_HXML_SIGNATURE const *,_CRYPT_XML_WS_STATE *,int,WS_TYPE_Signature *)

- ea: `0x18000c75c`
- end: `0x18000c987`
- name: `?I_XmlMarshallSignature@@YAJPEBU_HXML_SIGNATURE@@PEAU_CRYPT_XML_WS_STATE@@HPEAUWS_TYPE_Signature@@@Z`
- size: `555`
- prototype: `int(const struct _HXML_SIGNATURE *, struct _CRYPT_XML_WS_STATE *, int, struct WS_TYPE_Signature *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c2d0`

## callees

- `0x1800070d0`
- `0x18000c75c`
- `0x180010520`
- `0x1800115a8`
- `0x180014ce0`
- `0x1800176d0`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c79f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000c79f`
- `webservices!WsAlloc` at `0x18000c831`
- `webservices!WsAlloc` at `0x18000c8c7`
- `webservices!WsAlloc` at `0x18000c831`
- `webservices!WsAlloc` at `0x18000c8c7`

## string_xrefs

- `0x18000c7ca`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000c843`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000c889`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000c8d9`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18000c952`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlMarshallSignature(
        const struct _HXML_SIGNATURE *a1,
        struct _CRYPT_XML_WS_STATE *a2,
        int a3,
        struct WS_TYPE_Signature *a4)
{
  __int64 v4; // rdi
  __int64 v9; // rax
  int v10; // ebx
  const char *v11; // r8
  const char *v12; // rax
  bool v13; // zf
  int v14; // r9d
  struct WS_TYPE_KeyInfo **v15; // r15
  const char *v16; // rax
  struct WS_TYPE_KeyInfo *v17; // rax
  __int64 v18; // rax
  void *v19; // rcx
  __int64 i; // rbp

  v4 = *((_QWORD *)a1 + 18);
  memset_0(a4, 0, 0x90u);
  v9 = *(_QWORD *)(v4 + 16);
  if ( v9 )
  {
    *((_QWORD *)a4 + 1) = v9;
    *(_DWORD *)a4 = lstrlenW(*(LPCWSTR *)(v4 + 16));
  }
  v10 = I_XmlMarshallSignedInfo(
          (const struct _CRYPT_XML_SIGNED_INFO *)(v4 + 24),
          a2,
          (struct WS_TYPE_Signature *)((char *)a4 + 16));
  if ( v10 < 0 )
  {
    v11 = "";
    while ( 1 )
    {
      v12 = v11--;
      v13 = *v11 == 92;
      if ( *v11 == 92 )
        break;
      if ( v11 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
      {
        v13 = *v11 == 92;
        break;
      }
    }
    if ( v13 )
      v11 = v12;
    v14 = 3227;
    goto LABEL_25;
  }
  *((_QWORD *)a4 + 14) = *(_QWORD *)(v4 + 144);
  *((_DWORD *)a4 + 26) = *(_DWORD *)(v4 + 136);
  if ( *(_QWORD *)(*((_QWORD *)a1 + 18) + 152LL) )
  {
    v15 = (struct WS_TYPE_KeyInfo **)((char *)a4 + 120);
    v10 = WsAlloc(*((WS_HEAP **)a2 + 6), 0x20u, (void **)a4 + 15, *(WS_ERROR **)a2);
    if ( v10 < 0 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v14 = 3244;
LABEL_24:
      v11 = v16;
LABEL_25:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v10, v11, v14);
      return (unsigned int)v10;
    }
    v17 = *v15;
    *(_OWORD *)v17 = 0;
    *((_OWORD *)v17 + 1) = 0;
    v10 = I_XmlMarshallKeyInfo(
            *(const struct _CRYPT_XML_KEY_INFO **)(*((_QWORD *)a1 + 18) + 152LL),
            (WS_HEAP **)a2,
            a3,
            *v15);
    if ( v10 < 0 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v14 = 3258;
      goto LABEL_24;
    }
  }
  v18 = *(unsigned int *)(v4 + 160);
  if ( (_DWORD)v18 )
  {
    v10 = WsAlloc(*((WS_HEAP **)a2 + 6), 72 * v18, (void **)a4 + 17, *(WS_ERROR **)a2);
    if ( v10 < 0 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v14 = 3273;
      goto LABEL_24;
    }
    v19 = (void *)*((_QWORD *)a4 + 17);
    *((_DWORD *)a4 + 32) = *(_DWORD *)(v4 + 160);
    memset_0(v19, 0, 72LL * *(unsigned int *)(v4 + 160));
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v4 + 160); i = (unsigned int)(i + 1) )
    {
      v10 = I_XmlMarshallObject(
              a2,
              *(struct _HXML_OBJECT **)(*(_QWORD *)(*(_QWORD *)(v4 + 168) + 8 * i) + 8LL),
              (struct WS_TYPE_Object *)(*((_QWORD *)a4 + 17) + 72 * i));
      if ( v10 < 0 )
      {
        v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        v14 = 3290;
        goto LABEL_24;
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c75c  push    rbx
0x18000c75e  push    rbp
0x18000c75f  push    rsi
0x18000c760  push    rdi
0x18000c761  push    r12
0x18000c763  push    r14
0x18000c765  push    r15
0x18000c767  sub     rsp, 20h
0x18000c76b  mov     rdi, [rcx+90h]
0x18000c772  mov     r12d, r8d
0x18000c775  mov     r14, rdx
0x18000c778  mov     rbp, rcx
0x18000c77b  xor     edx, edx; Val
0x18000c77d  mov     r8d, 90h; Size
0x18000c783  mov     rcx, r9; void *
0x18000c786  mov     rsi, r9
0x18000c789  call    memset_0
0x18000c78e  mov     rax, [rdi+10h]
0x18000c792  test    rax, rax
0x18000c795  jz      short loc_18000C7AD
0x18000c797  mov     [rsi+8], rax
0x18000c79b  mov     rcx, [rdi+10h]; lpString
0x18000c79f  call    cs:__imp_lstrlenW
0x18000c7a6  nop     dword ptr [rax+rax+00h]
0x18000c7ab  mov     [rsi], eax
0x18000c7ad  lea     r8, [rsi+10h]; struct WS_TYPE_SignedInfo *
0x18000c7b1  mov     rdx, r14; struct _CRYPT_XML_WS_STATE *
0x18000c7b4  lea     rcx, [rdi+18h]; struct _CRYPT_XML_SIGNED_INFO *
0x18000c7b8  call    ?I_XmlMarshallSignedInfo@@YAJPEBU_CRYPT_XML_SIGNED_INFO@@PEAU_CRYPT_XML_WS_STATE@@PEAUWS_TYPE_SignedInfo@@@Z; I_XmlMarshallSignedInfo(_CRYPT_XML_SIGNED_INFO const *,_CRYPT_XML_WS_STATE *,WS_TYPE_SignedInfo *)
0x18000c7bd  mov     ebx, eax
0x18000c7bf  test    eax, eax
0x18000c7c1  jns     short loc_18000C7F5
0x18000c7c3  lea     r8, aOnecoreDsSecur_1+35h; ""
0x18000c7ca  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c7d1  mov     rax, r8
0x18000c7d4  dec     r8
0x18000c7d7  cmp     byte ptr [r8], 5Ch ; '\'
0x18000c7db  jz      short loc_18000C7E6
0x18000c7dd  cmp     r8, rcx
0x18000c7e0  ja      short loc_18000C7D1
0x18000c7e2  cmp     byte ptr [r8], 5Ch ; '\'
0x18000c7e6  cmovz   r8, rax
0x18000c7ea  mov     r9d, 0C9Bh
0x18000c7f0  jmp     loc_18000C967
0x18000c7f5  mov     rax, [rdi+90h]
0x18000c7fc  mov     [rsi+70h], rax
0x18000c800  mov     eax, [rdi+88h]
0x18000c806  mov     [rsi+68h], eax
0x18000c809  mov     rax, [rbp+90h]
0x18000c810  cmp     qword ptr [rax+98h], 0
0x18000c818  jz      loc_18000C8A0
0x18000c81e  mov     r9, [r14]; error
0x18000c821  lea     r15, [rsi+78h]
0x18000c825  mov     rcx, [r14+30h]; heap
0x18000c829  mov     r8, r15; ptr
0x18000c82c  mov     edx, 20h ; ' '; size
0x18000c831  call    cs:__imp_WsAlloc
0x18000c838  nop     dword ptr [rax+rax+00h]
0x18000c83d  mov     ebx, eax
0x18000c83f  test    eax, eax
0x18000c841  jns     short loc_18000C85A
0x18000c843  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c84a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c84f  mov     r9d, 0CACh
0x18000c855  jmp     loc_18000C964
0x18000c85a  mov     rax, [r15]
0x18000c85d  xorps   xmm0, xmm0
0x18000c860  mov     r8d, r12d; int
0x18000c863  mov     rdx, r14; struct _CRYPT_XML_WS_STATE *
0x18000c866  movups  xmmword ptr [rax], xmm0
0x18000c869  movups  xmmword ptr [rax+10h], xmm0
0x18000c86d  mov     rcx, [rbp+90h]
0x18000c874  mov     r9, [r15]; struct WS_TYPE_KeyInfo *
0x18000c877  mov     rcx, [rcx+98h]; struct _CRYPT_XML_KEY_INFO *
0x18000c87e  call    ?I_XmlMarshallKeyInfo@@YAJPEBU_CRYPT_XML_KEY_INFO@@PEAU_CRYPT_XML_WS_STATE@@HPEAUWS_TYPE_KeyInfo@@@Z; I_XmlMarshallKeyInfo(_CRYPT_XML_KEY_INFO const *,_CRYPT_XML_WS_STATE *,int,WS_TYPE_KeyInfo *)
0x18000c883  mov     ebx, eax
0x18000c885  test    eax, eax
0x18000c887  jns     short loc_18000C8A0
0x18000c889  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c890  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c895  mov     r9d, 0CBAh
0x18000c89b  jmp     loc_18000C964
0x18000c8a0  mov     eax, [rdi+0A0h]
0x18000c8a6  test    eax, eax
0x18000c8a8  jz      loc_18000C975
0x18000c8ae  mov     r9, [r14]; error
0x18000c8b1  lea     rdx, [rax+rax*8]
0x18000c8b5  mov     rcx, [r14+30h]; heap
0x18000c8b9  lea     r15, [rsi+88h]
0x18000c8c0  shl     rdx, 3; size
0x18000c8c4  mov     r8, r15; ptr
0x18000c8c7  call    cs:__imp_WsAlloc
0x18000c8ce  nop     dword ptr [rax+rax+00h]
0x18000c8d3  mov     ebx, eax
0x18000c8d5  test    eax, eax
0x18000c8d7  jns     short loc_18000C8ED
0x18000c8d9  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c8e0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c8e5  mov     r9d, 0CC9h
0x18000c8eb  jmp     short loc_18000C964
0x18000c8ed  mov     eax, [rdi+0A0h]
0x18000c8f3  xor     edx, edx; Val
0x18000c8f5  mov     rcx, [r15]; void *
0x18000c8f8  mov     [rsi+80h], eax
0x18000c8fe  mov     eax, [rdi+0A0h]
0x18000c904  lea     r8, [rax+rax*8]
0x18000c908  shl     r8, 3; Size
0x18000c90c  call    memset_0
0x18000c911  xor     ebp, ebp
0x18000c913  cmp     ebp, [rdi+0A0h]
0x18000c919  jnb     short loc_18000C975
0x18000c91b  mov     rax, [rsi+88h]
0x18000c922  lea     rcx, ds:0[rbp*8]
0x18000c92a  add     rcx, rbp
0x18000c92d  lea     r8, [rax+rcx*8]; struct WS_TYPE_Object *
0x18000c931  mov     rax, [rdi+0A8h]
0x18000c938  mov     rcx, r14; struct _CRYPT_XML_WS_STATE *
0x18000c93b  mov     rdx, [rax+rbp*8]
0x18000c93f  mov     rdx, [rdx+8]; struct _HXML_OBJECT *
0x18000c943  call    ?I_XmlMarshallObject@@YAJPEAU_CRYPT_XML_WS_STATE@@PEAU_HXML_OBJECT@@PEAUWS_TYPE_Object@@@Z; I_XmlMarshallObject(_CRYPT_XML_WS_STATE *,_HXML_OBJECT *,WS_TYPE_Object *)
0x18000c948  mov     ebx, eax
0x18000c94a  test    eax, eax
0x18000c94c  js      short loc_18000C952
0x18000c94e  inc     ebp
0x18000c950  jmp     short loc_18000C913
0x18000c952  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c959  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c95e  mov     r9d, 0CDAh
0x18000c964  mov     r8, rax
0x18000c967  mov     edx, ebx
0x18000c969  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c970  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000c975  mov     eax, ebx
0x18000c977  add     rsp, 20h
0x18000c97b  pop     r15
0x18000c97d  pop     r14
0x18000c97f  pop     r12
0x18000c981  pop     rdi
0x18000c982  pop     rsi
0x18000c983  pop     rbp
0x18000c984  pop     rbx
0x18000c985  retn
```
