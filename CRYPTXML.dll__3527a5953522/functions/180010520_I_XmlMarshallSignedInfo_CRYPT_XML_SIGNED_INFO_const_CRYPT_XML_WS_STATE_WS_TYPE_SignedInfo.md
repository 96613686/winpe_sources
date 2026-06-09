# I_XmlMarshallSignedInfo(_CRYPT_XML_SIGNED_INFO const *,_CRYPT_XML_WS_STATE *,WS_TYPE_SignedInfo *)

- ea: `0x180010520`
- end: `0x180010728`
- name: `?I_XmlMarshallSignedInfo@@YAJPEBU_CRYPT_XML_SIGNED_INFO@@PEAU_CRYPT_XML_WS_STATE@@PEAUWS_TYPE_SignedInfo@@@Z`
- size: `520`
- prototype: `int(const struct _CRYPT_XML_SIGNED_INFO *, struct _CRYPT_XML_WS_STATE *, struct WS_TYPE_SignedInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c75c`

## callees

- `0x1800070d0`
- `0x180010520`
- `0x180010730`
- `0x180014ce0`
- `0x180015178`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010557`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800105ee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001064f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010557`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800105ee`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001064f`
- `webservices!WsAlloc` at `0x18001067f`
- `webservices!WsAlloc` at `0x18001067f`

## string_xrefs

- `0x1800105a1`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18001062c`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180010691`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800106ea`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlMarshallSignedInfo(const struct _CRYPT_XML_SIGNED_INFO *a1, WS_ERROR **a2, void **a3)
{
  __int64 v6; // r9
  LPCWSTR wszId; // rax
  int v8; // ebp
  __int64 v9; // r9
  const char *v10; // r8
  char v11; // al
  const char *v12; // rdx
  bool v13; // zf
  int v14; // r9d
  __int64 cReference; // rax
  void **v17; // r14
  HRESULT v18; // esi
  const char *v19; // rax
  int v20; // r9d
  void *v21; // rcx
  __int64 i; // rdi

  memset_0(a3, 0, 0x58u);
  wszId = a1->wszId;
  if ( wszId )
  {
    a3[1] = (void *)wszId;
    *(_DWORD *)a3 = lstrlenW(a1->wszId);
  }
  if ( a1->Canonicalization.Encoded.cbData )
  {
    v8 = I_XmlSetFromEncoded(
           a2,
           (int *)&a1->Canonicalization.Encoded,
           &CanonicalizationMethod_ElementDescription,
           v6,
           a3 + 2,
           0x18u);
    if ( v8 < 0 )
    {
      v10 = "";
      while ( 1 )
      {
        v11 = *(v10 - 1);
        v12 = v10--;
        v13 = v11 == 92;
        if ( v11 == 92 )
          break;
        if ( v10 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
        {
          v13 = v11 == 92;
          break;
        }
      }
      if ( v13 )
        v10 = v12;
      v14 = 2699;
      goto LABEL_12;
    }
  }
  else
  {
    v8 = 1;
    a3[3] = (void *)a1->Canonicalization.wszAlgorithm;
    *((_DWORD *)a3 + 4) = lstrlenW(a1->Canonicalization.wszAlgorithm);
  }
  if ( a1->SignatureMethod.Encoded.cbData )
  {
    v8 = I_XmlSetFromEncoded(
           a2,
           (int *)&a1->SignatureMethod.Encoded,
           &SignatureMethod_ElementDescription,
           v9,
           a3 + 5,
           0x20u);
    if ( v8 < 0 )
    {
      v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v14 = 2723;
LABEL_12:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v8, v10, v14);
      return (unsigned int)v8;
    }
  }
  else
  {
    a3[6] = (void *)a1->SignatureMethod.wszAlgorithm;
    *((_DWORD *)a3 + 10) = lstrlenW(a1->SignatureMethod.wszAlgorithm);
  }
  cReference = a1->cReference;
  if ( !(_DWORD)cReference )
    return (unsigned int)v8;
  v17 = a3 + 10;
  v18 = WsAlloc(a2[6], 104 * cReference, a3 + 10, *a2);
  if ( v18 >= 0 )
  {
    v21 = *v17;
    *((_DWORD *)a3 + 18) = a1->cReference;
    memset_0(v21, 0, 104LL * a1->cReference);
    for ( i = 0; (unsigned int)i < a1->cReference; i = (unsigned int)(i + 1) )
    {
      v18 = I_XmlMarshallReference(
              (const struct _HXML_REFERENCE *)a1->rgpReference[i]->hReference,
              (struct _CRYPT_XML_WS_STATE *)a2,
              (struct WS_TYPE_Reference *)((char *)*v17 + 104 * (unsigned int)i));
      if ( v18 < 0 )
      {
        v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        v20 = 2763;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v20 = 2745;
LABEL_27:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v18, v19, v20);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180010520  mov     [rsp+arg_10], rbx
0x180010525  push    rsi
0x180010526  push    rdi
0x180010527  push    r15
0x180010529  sub     rsp, 30h
0x18001052d  mov     rdi, r8
0x180010530  mov     r15, rdx
0x180010533  mov     rbx, rcx
0x180010536  xor     edx, edx; Val
0x180010538  mov     rcx, rdi; void *
0x18001053b  mov     r8d, 58h ; 'X'; Size
0x180010541  call    memset_0
0x180010546  mov     rax, [rbx+8]
0x18001054a  test    rax, rax
0x18001054d  jz      short loc_180010565
0x18001054f  mov     [rdi+8], rax
0x180010553  mov     rcx, [rbx+8]; lpString
0x180010557  call    cs:__imp_lstrlenW
0x18001055e  nop     dword ptr [rax+rax+00h]
0x180010563  mov     [rdi], eax
0x180010565  cmp     dword ptr [rbx+24h], 0
0x180010569  lea     rdx, [rbx+20h]
0x18001056d  mov     [rsp+48h+arg_0], rbp
0x180010572  lea     rsi, [rdi+10h]
0x180010576  jbe     short loc_1800105DD
0x180010578  mov     [rsp+48h+var_20], 18h
0x180010580  lea     r8, ?CanonicalizationMethod_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; _WS_ELEMENT_DESCRIPTION const CanonicalizationMethod_ElementDescription
0x180010587  mov     rcx, r15
0x18001058a  mov     [rsp+48h+var_28], rsi
0x18001058f  call    I_XmlSetFromEncoded
0x180010594  mov     ebp, eax
0x180010596  test    eax, eax
0x180010598  jns     short loc_1800105FC
0x18001059a  lea     r8, aOnecoreDsSecur_1+35h; ""
0x1800105a1  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800105a8  movzx   eax, byte ptr [r8-1]
0x1800105ad  mov     rdx, r8
0x1800105b0  dec     r8
0x1800105b3  cmp     al, 5Ch ; '\'
0x1800105b5  jz      short loc_1800105BE
0x1800105b7  cmp     r8, rcx
0x1800105ba  ja      short loc_1800105A8
0x1800105bc  cmp     al, 5Ch ; '\'
0x1800105be  cmovz   r8, rdx
0x1800105c2  mov     r9d, 0A8Bh
0x1800105c8  mov     edx, ebp
0x1800105ca  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800105d1  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800105d6  mov     eax, ebp
0x1800105d8  jmp     loc_180010714
0x1800105dd  mov     rax, [rbx+18h]
0x1800105e1  mov     ebp, 1
0x1800105e6  mov     [rsi+8], rax
0x1800105ea  mov     rcx, [rbx+18h]; lpString
0x1800105ee  call    cs:__imp_lstrlenW
0x1800105f5  nop     dword ptr [rax+rax+00h]
0x1800105fa  mov     [rsi], eax
0x1800105fc  cmp     dword ptr [rbx+44h], 0
0x180010600  lea     rdx, [rbx+40h]
0x180010604  lea     rsi, [rdi+28h]
0x180010608  jbe     short loc_180010643
0x18001060a  mov     [rsp+48h+var_20], 20h ; ' '
0x180010612  lea     r8, ?SignatureMethod_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; _WS_ELEMENT_DESCRIPTION const SignatureMethod_ElementDescription
0x180010619  mov     rcx, r15
0x18001061c  mov     [rsp+48h+var_28], rsi
0x180010621  call    I_XmlSetFromEncoded
0x180010626  mov     ebp, eax
0x180010628  test    eax, eax
0x18001062a  jns     short loc_18001065D
0x18001062c  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010633  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010638  mov     r8, rax
0x18001063b  mov     r9d, 0AA3h
0x180010641  jmp     short loc_1800105C8
0x180010643  mov     rax, [rbx+38h]
0x180010647  mov     [rsi+8], rax
0x18001064b  mov     rcx, [rbx+38h]; lpString
0x18001064f  call    cs:__imp_lstrlenW
0x180010656  nop     dword ptr [rax+rax+00h]
0x18001065b  mov     [rsi], eax
0x18001065d  mov     eax, [rbx+50h]
0x180010660  test    eax, eax
0x180010662  jz      loc_1800105D6
0x180010668  mov     r9, [r15]; error
0x18001066b  mov     rcx, [r15+30h]; heap
0x18001066f  imul    rdx, rax, 68h ; 'h'; size
0x180010673  mov     [rsp+48h+arg_8], r14
0x180010678  lea     r14, [rdi+50h]
0x18001067c  mov     r8, r14; ptr
0x18001067f  call    cs:__imp_WsAlloc
0x180010686  nop     dword ptr [rax+rax+00h]
0x18001068b  mov     esi, eax
0x18001068d  test    eax, eax
0x18001068f  jns     short loc_1800106A5
0x180010691  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010698  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001069d  mov     r9d, 0AB9h
0x1800106a3  jmp     short loc_1800106FC
0x1800106a5  mov     eax, [rbx+50h]
0x1800106a8  xor     edx, edx; Val
0x1800106aa  mov     rcx, [r14]; void *
0x1800106ad  mov     [rdi+48h], eax
0x1800106b0  mov     eax, [rbx+50h]
0x1800106b3  imul    r8, rax, 68h ; 'h'; Size
0x1800106b7  call    memset_0
0x1800106bc  xor     edi, edi
0x1800106be  cmp     edi, [rbx+50h]
0x1800106c1  jnb     short loc_18001070D
0x1800106c3  mov     rax, [rbx+58h]
0x1800106c7  mov     rdx, r15; struct _CRYPT_XML_WS_STATE *
0x1800106ca  mov     ecx, edi
0x1800106cc  imul    r8, rcx, 68h ; 'h'
0x1800106d0  mov     rcx, [rax+rdi*8]
0x1800106d4  add     r8, [r14]; struct WS_TYPE_Reference *
0x1800106d7  mov     rcx, [rcx+8]; struct _HXML_REFERENCE *
0x1800106db  call    ?I_XmlMarshallReference@@YAJPEBU_HXML_REFERENCE@@PEAU_CRYPT_XML_WS_STATE@@PEAUWS_TYPE_Reference@@@Z; I_XmlMarshallReference(_HXML_REFERENCE const *,_CRYPT_XML_WS_STATE *,WS_TYPE_Reference *)
0x1800106e0  mov     esi, eax
0x1800106e2  test    eax, eax
0x1800106e4  js      short loc_1800106EA
0x1800106e6  inc     edi
0x1800106e8  jmp     short loc_1800106BE
0x1800106ea  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800106f1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800106f6  mov     r9d, 0ACBh
0x1800106fc  mov     r8, rax
0x1800106ff  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180010706  mov     edx, esi
0x180010708  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001070d  mov     r14, [rsp+48h+arg_8]
0x180010712  mov     eax, esi
0x180010714  mov     rbp, [rsp+48h+arg_0]
0x180010719  mov     rbx, [rsp+48h+arg_10]
0x18001071e  add     rsp, 30h
0x180010722  pop     r15
0x180010724  pop     rdi
0x180010725  pop     rsi
0x180010726  retn
```
