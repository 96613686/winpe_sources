# I_XmlMarshallReference(_HXML_REFERENCE const *,_CRYPT_XML_WS_STATE *,WS_TYPE_Reference *)

- ea: `0x180010730`
- end: `0x1800109ad`
- name: `?I_XmlMarshallReference@@YAJPEBU_HXML_REFERENCE@@PEAU_CRYPT_XML_WS_STATE@@PEAUWS_TYPE_Reference@@@Z`
- size: `637`
- prototype: `int(const struct _HXML_REFERENCE *, struct _CRYPT_XML_WS_STATE *, struct WS_TYPE_Reference *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010520`
- `0x1800176d0`

## callees

- `0x1800070d0`
- `0x180010730`
- `0x180014ce0`
- `0x180015178`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010767`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010786`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800107a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800108fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010971`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010767`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010786`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800107a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800108fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010971`
- `webservices!WsAlloc` at `0x1800107ed`
- `webservices!WsAlloc` at `0x1800107ed`

## string_xrefs

- `0x180010806`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800108c4`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18001094f`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlMarshallReference(const struct _HXML_REFERENCE *a1, WS_HEAP **a2, void **a3)
{
  __int64 v3; // rbx
  __int64 v6; // r9
  void *v7; // rax
  void *v8; // rax
  void *v9; // rax
  __int64 v10; // rax
  int v11; // edi
  const char *v12; // r8
  char v13; // al
  const char *v14; // rdx
  bool v15; // zf
  int v16; // r9d
  void *v18; // rcx
  __int64 i; // rdi
  __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // r8
  int v23; // ebp
  const char *v24; // rax
  void *v25; // rax

  v3 = *((_QWORD *)a1 + 17);
  memset_0(a3, 0, 0x68u);
  v7 = *(void **)(v3 + 16);
  if ( v7 )
  {
    a3[1] = v7;
    *(_DWORD *)a3 = lstrlenW(*(LPCWSTR *)(v3 + 16));
  }
  v8 = *(void **)(v3 + 32);
  if ( v8 )
  {
    a3[5] = v8;
    *((_DWORD *)a3 + 8) = lstrlenW(*(LPCWSTR *)(v3 + 32));
  }
  v9 = *(void **)(v3 + 24);
  if ( v9 )
  {
    a3[3] = v9;
    *((_DWORD *)a3 + 4) = lstrlenW(*(LPCWSTR *)(v3 + 24));
  }
  *((_DWORD *)a3 + 12) = *(_DWORD *)(v3 + 88);
  v10 = *(unsigned int *)(v3 + 88);
  if ( (_DWORD)v10 )
  {
    v11 = WsAlloc(a2[6], 24 * v10, a3 + 7, *a2);
    if ( v11 < 0 )
    {
      v12 = "";
      while ( 1 )
      {
        v13 = *(v12 - 1);
        v14 = v12--;
        v15 = v13 == 92;
        if ( v13 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
        {
          v15 = v13 == 92;
          break;
        }
      }
      if ( v15 )
        v12 = v14;
      v16 = 2472;
      goto LABEL_16;
    }
    v18 = a3[7];
    *((_DWORD *)a3 + 12) = *(_DWORD *)(v3 + 88);
    memset_0(v18, 0, 24LL * *(unsigned int *)(v3 + 88));
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v3 + 88); i = (unsigned int)(i + 1) )
    {
      v20 = *(_QWORD *)(v3 + 96);
      v21 = 32LL * (unsigned int)i;
      v6 = *(_QWORD *)(v20 + v21 + 8);
      if ( v6 )
      {
        v22 = (char *)a3[7] + 24 * i;
        if ( *(_DWORD *)(v20 + v21 + 20) )
        {
          v23 = I_XmlSetFromEncoded(a2, (int *)(v20 + 16 + v21), &Transform_ElementDescription, v6, v22, 0x18u);
          if ( v23 < 0 )
          {
            v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v23, v24, 2496);
            return (unsigned int)v23;
          }
        }
        else
        {
          v22[1] = v6;
          *((_DWORD *)a3[7] + 6 * i) = lstrlenW(*(LPCWSTR *)(v21 + *(_QWORD *)(v3 + 96) + 8));
        }
      }
    }
  }
  v25 = *(void **)(v3 + 48);
  if ( v25 )
  {
    if ( *(_DWORD *)(v3 + 60) )
    {
      v11 = I_XmlSetFromEncoded(a2, (int *)(v3 + 56), &DigestMethod_ElementDescription, v6, a3 + 8, 0x18u);
      if ( v11 < 0 )
      {
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        v16 = 2523;
LABEL_16:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v11, v12, v16);
        return (unsigned int)v11;
      }
    }
    else
    {
      a3[9] = v25;
      *((_DWORD *)a3 + 16) = lstrlenW(*(LPCWSTR *)(v3 + 48));
    }
  }
  a3[12] = *(void **)(v3 + 80);
  *((_DWORD *)a3 + 22) = *(_DWORD *)(v3 + 72);
  return 0;
}

```

## disassembly

```asm
0x180010730  push    rbx
0x180010732  push    rsi
0x180010733  push    r15
0x180010735  sub     rsp, 30h
0x180010739  mov     rbx, [rcx+88h]
0x180010740  mov     rsi, r8
0x180010743  mov     r15, rdx
0x180010746  mov     rcx, rsi; void *
0x180010749  xor     edx, edx; Val
0x18001074b  mov     r8d, 68h ; 'h'; Size
0x180010751  call    memset_0
0x180010756  mov     rax, [rbx+10h]
0x18001075a  test    rax, rax
0x18001075d  jz      short loc_180010775
0x18001075f  mov     [rsi+8], rax
0x180010763  mov     rcx, [rbx+10h]; lpString
0x180010767  call    cs:__imp_lstrlenW
0x18001076e  nop     dword ptr [rax+rax+00h]
0x180010773  mov     [rsi], eax
0x180010775  mov     rax, [rbx+20h]
0x180010779  test    rax, rax
0x18001077c  jz      short loc_180010795
0x18001077e  mov     [rsi+28h], rax
0x180010782  mov     rcx, [rbx+20h]; lpString
0x180010786  call    cs:__imp_lstrlenW
0x18001078d  nop     dword ptr [rax+rax+00h]
0x180010792  mov     [rsi+20h], eax
0x180010795  mov     rax, [rbx+18h]
0x180010799  test    rax, rax
0x18001079c  jz      short loc_1800107B5
0x18001079e  mov     [rsi+18h], rax
0x1800107a2  mov     rcx, [rbx+18h]; lpString
0x1800107a6  call    cs:__imp_lstrlenW
0x1800107ad  nop     dword ptr [rax+rax+00h]
0x1800107b2  mov     [rsi+10h], eax
0x1800107b5  mov     eax, [rbx+58h]
0x1800107b8  mov     [rsp+48h+arg_0], rbp
0x1800107bd  mov     [rsp+48h+arg_8], rdi
0x1800107c2  mov     [rsi+30h], eax
0x1800107c5  mov     eax, [rbx+58h]
0x1800107c8  mov     [rsp+48h+arg_10], r12
0x1800107cd  mov     [rsp+48h+arg_18], r14
0x1800107d2  test    eax, eax
0x1800107d4  jz      loc_180010916
0x1800107da  mov     r9, [r15]; error
0x1800107dd  lea     rdx, [rax+rax*2]
0x1800107e1  mov     rcx, [r15+30h]; heap
0x1800107e5  lea     r8, [rsi+38h]; ptr
0x1800107e9  shl     rdx, 3; size
0x1800107ed  call    cs:__imp_WsAlloc
0x1800107f4  nop     dword ptr [rax+rax+00h]
0x1800107f9  mov     edi, eax
0x1800107fb  test    eax, eax
0x1800107fd  jns     short loc_180010842
0x1800107ff  lea     r8, aOnecoreDsSecur_1+35h; ""
0x180010806  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001080d  movzx   eax, byte ptr [r8-1]
0x180010812  mov     rdx, r8
0x180010815  dec     r8
0x180010818  cmp     al, 5Ch ; '\'
0x18001081a  jz      short loc_180010823
0x18001081c  cmp     r8, rcx
0x18001081f  ja      short loc_18001080D
0x180010821  cmp     al, 5Ch ; '\'
0x180010823  cmovz   r8, rdx
0x180010827  mov     r9d, 9A8h
0x18001082d  mov     edx, edi
0x18001082f  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180010836  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18001083b  mov     eax, edi
0x18001083d  jmp     loc_18001098F
0x180010842  mov     eax, [rbx+58h]
0x180010845  xor     edx, edx; Val
0x180010847  mov     rcx, [rsi+38h]; void *
0x18001084b  mov     [rsi+30h], eax
0x18001084e  mov     eax, [rbx+58h]
0x180010851  lea     r8, [rax+rax*2]
0x180010855  shl     r8, 3; Size
0x180010859  call    memset_0
0x18001085e  xor     edi, edi
0x180010860  cmp     edi, [rbx+58h]
0x180010863  jnb     loc_180010916
0x180010869  mov     rcx, [rbx+60h]
0x18001086d  mov     edx, edi
0x18001086f  shl     rdx, 5
0x180010873  mov     r9, [rcx+rdx+8]
0x180010878  test    r9, r9
0x18001087b  jz      loc_18001090F
0x180010881  mov     r8, [rsi+38h]
0x180010885  lea     rax, [rdi+rdi*2]
0x180010889  lea     r14, ds:0[rax*8]
0x180010891  add     r8, r14
0x180010894  cmp     dword ptr [rcx+rdx+14h], 0
0x180010899  jbe     short loc_1800108EE
0x18001089b  add     rcx, 10h
0x18001089f  mov     [rsp+48h+var_20], 18h
0x1800108a7  add     rdx, rcx
0x1800108aa  mov     [rsp+48h+var_28], r8
0x1800108af  mov     rcx, r15
0x1800108b2  lea     r8, ?Transform_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; _WS_ELEMENT_DESCRIPTION const Transform_ElementDescription
0x1800108b9  call    I_XmlSetFromEncoded
0x1800108be  mov     ebp, eax
0x1800108c0  test    eax, eax
0x1800108c2  jns     short loc_18001090F
0x1800108c4  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800108cb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800108d0  mov     r8, rax
0x1800108d3  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800108da  mov     edx, ebp
0x1800108dc  mov     r9d, 9C0h
0x1800108e2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800108e7  mov     eax, ebp
0x1800108e9  jmp     loc_18001098F
0x1800108ee  mov     [r8+8], r9
0x1800108f2  mov     rcx, [rbx+60h]
0x1800108f6  mov     rcx, [rdx+rcx+8]; lpString
0x1800108fb  call    cs:__imp_lstrlenW
0x180010902  nop     dword ptr [rax+rax+00h]
0x180010907  mov     rcx, [rsi+38h]
0x18001090b  mov     [r14+rcx], eax
0x18001090f  inc     edi
0x180010911  jmp     loc_180010860
0x180010916  mov     rax, [rbx+30h]
0x18001091a  test    rax, rax
0x18001091d  jz      short loc_18001097F
0x18001091f  cmp     dword ptr [rbx+3Ch], 0
0x180010923  lea     rdx, [rbx+38h]
0x180010927  lea     rdi, [rsi+40h]
0x18001092b  jbe     short loc_180010969
0x18001092d  mov     [rsp+48h+var_20], 18h
0x180010935  lea     r8, ?DigestMethod_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; _WS_ELEMENT_DESCRIPTION const DigestMethod_ElementDescription
0x18001093c  mov     rcx, r15
0x18001093f  mov     [rsp+48h+var_28], rdi
0x180010944  call    I_XmlSetFromEncoded
0x180010949  mov     edi, eax
0x18001094b  test    eax, eax
0x18001094d  jns     short loc_18001097F
0x18001094f  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010956  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001095b  mov     r8, rax
0x18001095e  mov     r9d, 9DBh
0x180010964  jmp     loc_18001082D
0x180010969  mov     [rdi+8], rax
0x18001096d  mov     rcx, [rbx+30h]; lpString
0x180010971  call    cs:__imp_lstrlenW
0x180010978  nop     dword ptr [rax+rax+00h]
0x18001097d  mov     [rdi], eax
0x18001097f  mov     rax, [rbx+50h]
0x180010983  mov     [rsi+60h], rax
0x180010987  mov     eax, [rbx+48h]
0x18001098a  mov     [rsi+58h], eax
0x18001098d  xor     eax, eax
0x18001098f  mov     r14, [rsp+48h+arg_18]
0x180010994  mov     r12, [rsp+48h+arg_10]
0x180010999  mov     rdi, [rsp+48h+arg_8]
0x18001099e  mov     rbp, [rsp+48h+arg_0]
0x1800109a3  add     rsp, 30h
0x1800109a7  pop     r15
0x1800109a9  pop     rsi
0x1800109aa  pop     rbx
0x1800109ab  retn
```
