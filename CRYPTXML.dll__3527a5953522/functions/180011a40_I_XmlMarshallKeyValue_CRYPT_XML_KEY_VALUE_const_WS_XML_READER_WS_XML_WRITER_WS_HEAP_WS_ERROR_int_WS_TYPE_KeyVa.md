# I_XmlMarshallKeyValue(_CRYPT_XML_KEY_VALUE const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,int,WS_TYPE_KeyValue *)

- ea: `0x180011a40`
- end: `0x180011ee4`
- name: `?I_XmlMarshallKeyValue@@YAJPEBU_CRYPT_XML_KEY_VALUE@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@HPEAUWS_TYPE_KeyValue@@@Z`
- size: `1188`
- prototype: `int(const struct _CRYPT_XML_KEY_VALUE *, struct _WS_XML_READER *, struct _WS_XML_WRITER *, struct _WS_HEAP *, struct _WS_ERROR *, int, struct WS_TYPE_KeyValue *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800115a8`
- `0x180016564`

## callees

- `0x1800070d0`
- `0x180011a40`
- `0x180011eec`
- `0x180014ce0`
- `0x180017998`
- `0x18001860d`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011d7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011ebe`
- `webservices!WsAlloc` at `0x180011c4c`
- `webservices!WsAlloc` at `0x180011d26`
- `webservices!WsAlloc` at `0x180011de2`
- `webservices!WsAlloc` at `0x180011c4c`
- `webservices!WsAlloc` at `0x180011d26`
- `webservices!WsAlloc` at `0x180011de2`

## string_xrefs

- `0x180011acf`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011be5`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011c5e`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011ce1`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011d38`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011daa`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011df4`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011e64`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlMarshallKeyValue(
        const struct _CRYPT_XML_KEY_VALUE *a1,
        struct _WS_XML_READER *a2,
        struct _WS_XML_WRITER *a3,
        struct _WS_HEAP *a4,
        struct _WS_ERROR *error,
        int a6,
        struct WS_TYPE_KeyValue *a7)
{
  struct WS_TYPE_KeyValue *v7; // rdi
  int v12; // ebx
  const char *v13; // rax
  struct _WS_ERROR *v14; // rbp
  const char *v15; // rax
  __int64 v16; // rax
  ULONG v17; // eax
  const char *v18; // rax
  const char *v19; // rax
  WS_ERROR *v20; // r14
  const char *v21; // rax
  __int64 cbData; // rdx
  BYTE *pbData; // rcx
  const char *v24; // rax
  const char *v25; // rax
  const char *v26; // rax
  __int64 v27; // rax
  void *Src; // [rsp+60h] [rbp+8h] BYREF

  v7 = a7;
  Src = 0;
  memset_0(a7, 0, 0x88u);
  switch ( a1->dwType )
  {
    case 3u:
      if ( a6 )
      {
        v14 = error;
        *(_DWORD *)v7 = 5;
        if ( a1->ECDSAKeyValue.ExplicitPara.cbData )
        {
          *((_DWORD *)v7 + 2) = 1;
          v12 = I_XmlSetEncodedEx(&a1->ECDSAKeyValue.ExplicitPara, a2, a3, a4, v14, (struct _WS_XML_BUFFER **)v7 + 2);
          if ( v12 < 0 )
          {
            v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v15, 2956);
            return (unsigned int)v12;
          }
        }
        else
        {
          *((_DWORD *)v7 + 2) = 2;
          *((_QWORD *)v7 + 3) = a1->ECDSAKeyValue.wszNamedCurve;
          v16 = -1;
          do
            ++v16;
          while ( a1->ECDSAKeyValue.wszNamedCurve[v16] );
          *((_DWORD *)v7 + 4) = v16;
        }
        v17 = 2 * a1->ECDSAKeyValue.Y.cbData + 1;
        *((_DWORD *)v7 + 12) = v17;
        v12 = WsAlloc(a4, v17, (void **)v7 + 7, v14);
        if ( v12 >= 0 )
        {
          **((_BYTE **)v7 + 7) = 4;
          memcpy_0((void *)(*((_QWORD *)v7 + 7) + 1LL), a1->ECDSAKeyValue.X.pbData, a1->ECDSAKeyValue.X.cbData);
          memcpy_0(
            (void *)(*((_QWORD *)v7 + 7) + 1LL + a1->ECDSAKeyValue.X.cbData),
            a1->ECDSAKeyValue.Y.pbData,
            a1->ECDSAKeyValue.Y.cbData);
        }
        else
        {
          v18 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v18, 2977);
        }
      }
      else
      {
        *(_DWORD *)v7 = 3;
        v12 = I_BigEndianBytesToDecString(a1->ECDSAKeyValue.X.pbData, a1->ECDSAKeyValue.X.cbData, &Src, (char *)v7 + 48);
        if ( v12 >= 0 )
        {
          v20 = error;
          v12 = WsAlloc(a4, 2LL * *((unsigned int *)v7 + 12), (void **)v7 + 7, error);
          if ( v12 >= 0 )
          {
            memcpy_0(*((void **)v7 + 7), Src, 2LL * *((unsigned int *)v7 + 12));
            LocalFree(Src);
            cbData = a1->ECDSAKeyValue.Y.cbData;
            pbData = a1->ECDSAKeyValue.Y.pbData;
            Src = 0;
            v12 = I_BigEndianBytesToDecString(pbData, cbData, &Src, (char *)v7 + 64);
            if ( v12 >= 0 )
            {
              v12 = WsAlloc(a4, 2LL * *((unsigned int *)v7 + 16), (void **)v7 + 9, v20);
              if ( v12 >= 0 )
              {
                memcpy_0(*((void **)v7 + 9), Src, 2LL * *((unsigned int *)v7 + 16));
                if ( a1->ECDSAKeyValue.ExplicitPara.cbData )
                {
                  *((_DWORD *)v7 + 2) = 1;
                  v12 = I_XmlSetEncodedEx(
                          &a1->ECDSAKeyValue.ExplicitPara,
                          a2,
                          a3,
                          a4,
                          v20,
                          (struct _WS_XML_BUFFER **)v7 + 2);
                  if ( v12 < 0 )
                  {
                    v26 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
                    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v26, 2927);
                  }
                }
                else
                {
                  *((_DWORD *)v7 + 2) = 2;
                  *((_QWORD *)v7 + 3) = a1->ECDSAKeyValue.wszNamedCurve;
                  v27 = -1;
                  do
                    ++v27;
                  while ( a1->ECDSAKeyValue.wszNamedCurve[v27] );
                  *((_DWORD *)v7 + 4) = v27;
                }
              }
              else
              {
                v25 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
                WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v25, 2904);
              }
            }
            else
            {
              v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v24, 2892);
            }
          }
          else
          {
            v21 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v21, 2868);
          }
        }
        else
        {
          v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v19, 2856);
        }
        if ( Src )
          LocalFree(Src);
      }
      break;
    case 1u:
      v12 = 1;
      *(_DWORD *)v7 = 1;
      *((_QWORD *)v7 + 6) = a1->DSAKeyValue.G.pbData;
      *((_DWORD *)v7 + 10) = a1->DSAKeyValue.G.cbData;
      *((_QWORD *)v7 + 10) = a1->DSAKeyValue.J.pbData;
      *((_DWORD *)v7 + 18) = a1->DSAKeyValue.J.cbData;
      *((_QWORD *)v7 + 2) = a1->DSAKeyValue.P.pbData;
      *((_DWORD *)v7 + 2) = a1->DSAKeyValue.P.cbData;
      *((_QWORD *)v7 + 4) = a1->DSAKeyValue.Q.pbData;
      *((_DWORD *)v7 + 6) = a1->DSAKeyValue.Q.cbData;
      *((_QWORD *)v7 + 8) = a1->DSAKeyValue.Y.pbData;
      *((_DWORD *)v7 + 14) = a1->DSAKeyValue.Y.cbData;
      *((_QWORD *)v7 + 12) = a1->DSAKeyValue.Seed.pbData;
      *((_DWORD *)v7 + 22) = a1->DSAKeyValue.Seed.cbData;
      *((_QWORD *)v7 + 14) = a1->DSAKeyValue.Counter.pbData;
      *((_DWORD *)v7 + 26) = a1->DSAKeyValue.Counter.cbData;
      break;
    case 2u:
      *(_DWORD *)v7 = 2;
      v12 = 1;
      *((_QWORD *)v7 + 2) = a1->DSAKeyValue.P.pbData;
      *((_DWORD *)v7 + 2) = a1->DSAKeyValue.P.cbData;
      *((_QWORD *)v7 + 4) = a1->DSAKeyValue.Q.pbData;
      *((_DWORD *)v7 + 6) = a1->DSAKeyValue.Q.cbData;
      break;
    default:
      *(_DWORD *)v7 = 4;
      v12 = I_XmlSetEncodedEx(&a1->Custom, a2, a3, a4, error, (struct _WS_XML_BUFFER **)v7 + 1);
      if ( v12 < 0 )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v12, v13, 3001);
      }
      break;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180011a40  mov     [rsp+arg_18], rbx
0x180011a45  push    rsi
0x180011a46  push    rdi
0x180011a47  push    r12
0x180011a49  push    r13
0x180011a4b  push    r15
0x180011a4d  sub     rsp, 30h
0x180011a51  mov     rdi, [rsp+58h+arg_30]
0x180011a59  mov     r12, r8
0x180011a5c  mov     r13, rdx
0x180011a5f  mov     [rsp+58h+Src], 0
0x180011a68  mov     rsi, rcx
0x180011a6b  xor     edx, edx; Val
0x180011a6d  mov     rcx, rdi; void *
0x180011a70  mov     r8d, 88h; Size
0x180011a76  mov     r15, r9
0x180011a79  call    memset_0
0x180011a7e  mov     eax, [rsi]
0x180011a80  cmp     eax, 3
0x180011a83  jz      loc_180011B91
0x180011a89  sub     eax, 1
0x180011a8c  jz      loc_180011B23
0x180011a92  cmp     eax, 1
0x180011a95  jz      short loc_180011AF7
0x180011a97  lea     rax, [rdi+8]
0x180011a9b  mov     dword ptr [rdi], 4
0x180011aa1  mov     [rsp+58h+var_30], rax; struct _WS_XML_BUFFER **
0x180011aa6  lea     rcx, [rsi+8]; struct _CRYPT_XML_BLOB *
0x180011aaa  mov     rax, [rsp+58h+error]
0x180011ab2  mov     r9, r15; struct _WS_HEAP *
0x180011ab5  mov     r8, r12; struct _WS_XML_WRITER *
0x180011ab8  mov     [rsp+58h+var_38], rax; struct _WS_ERROR *
0x180011abd  mov     rdx, r13; struct _WS_XML_READER *
0x180011ac0  call    ?I_XmlSetEncodedEx@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncodedEx(_CRYPT_XML_BLOB const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,_WS_XML_BUFFER * *)
0x180011ac5  mov     ebx, eax
0x180011ac7  test    eax, eax
0x180011ac9  jns     loc_180011ECF
0x180011acf  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011ad6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011adb  mov     r8, rax
0x180011ade  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011ae5  mov     edx, ebx
0x180011ae7  mov     r9d, 0BB9h
0x180011aed  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011af2  jmp     loc_180011ECF
0x180011af7  mov     dword ptr [rdi], 2
0x180011afd  mov     ebx, 1
0x180011b02  mov     rax, [rsi+10h]
0x180011b06  mov     [rdi+10h], rax
0x180011b0a  mov     eax, [rsi+8]
0x180011b0d  mov     [rdi+8], eax
0x180011b10  mov     rax, [rsi+20h]
0x180011b14  mov     [rdi+20h], rax
0x180011b18  mov     eax, [rsi+18h]
0x180011b1b  mov     [rdi+18h], eax
0x180011b1e  jmp     loc_180011ECF
0x180011b23  mov     ebx, 1
0x180011b28  mov     [rdi], ebx
0x180011b2a  mov     rax, [rsi+30h]
0x180011b2e  mov     [rdi+30h], rax
0x180011b32  mov     eax, [rsi+28h]
0x180011b35  mov     [rdi+28h], eax
0x180011b38  mov     rax, [rsi+50h]
0x180011b3c  mov     [rdi+50h], rax
0x180011b40  mov     eax, [rsi+48h]
0x180011b43  mov     [rdi+48h], eax
0x180011b46  mov     rax, [rsi+10h]
0x180011b4a  mov     [rdi+10h], rax
0x180011b4e  mov     eax, [rsi+8]
0x180011b51  mov     [rdi+8], eax
0x180011b54  mov     rax, [rsi+20h]
0x180011b58  mov     [rdi+20h], rax
0x180011b5c  mov     eax, [rsi+18h]
0x180011b5f  mov     [rdi+18h], eax
0x180011b62  mov     rax, [rsi+40h]
0x180011b66  mov     [rdi+40h], rax
0x180011b6a  mov     eax, [rsi+38h]
0x180011b6d  mov     [rdi+38h], eax
0x180011b70  mov     rax, [rsi+60h]
0x180011b74  mov     [rdi+60h], rax
0x180011b78  mov     eax, [rsi+58h]
0x180011b7b  mov     [rdi+58h], eax
0x180011b7e  mov     rax, [rsi+70h]
0x180011b82  mov     [rdi+70h], rax
0x180011b86  mov     eax, [rsi+68h]
0x180011b89  mov     [rdi+68h], eax
0x180011b8c  jmp     loc_180011ECF
0x180011b91  cmp     [rsp+58h+arg_28], 0
0x180011b99  mov     [rsp+58h+arg_8], rbp
0x180011b9e  jz      loc_180011CC0
0x180011ba4  mov     rbp, [rsp+58h+error]
0x180011bac  lea     rdx, [rdi+10h]
0x180011bb0  mov     dword ptr [rdi], 5
0x180011bb6  cmp     dword ptr [rsi+34h], 0
0x180011bba  jbe     short loc_180011C0D
0x180011bbc  mov     [rsp+58h+var_30], rdx; struct _WS_XML_BUFFER **
0x180011bc1  lea     rcx, [rsi+30h]; struct _CRYPT_XML_BLOB *
0x180011bc5  mov     rdx, r13; struct _WS_XML_READER *
0x180011bc8  mov     dword ptr [rdi+8], 1
0x180011bcf  mov     r9, r15; struct _WS_HEAP *
0x180011bd2  mov     [rsp+58h+var_38], rbp; struct _WS_ERROR *
0x180011bd7  mov     r8, r12; struct _WS_XML_WRITER *
0x180011bda  call    ?I_XmlSetEncodedEx@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncodedEx(_CRYPT_XML_BLOB const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,_WS_XML_BUFFER * *)
0x180011bdf  mov     ebx, eax
0x180011be1  test    eax, eax
0x180011be3  jns     short loc_180011C33
0x180011be5  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011bec  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011bf1  mov     r8, rax
0x180011bf4  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011bfb  mov     edx, ebx
0x180011bfd  mov     r9d, 0B8Ch
0x180011c03  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011c08  jmp     loc_180011ECA
0x180011c0d  mov     dword ptr [rdi+8], 2
0x180011c14  mov     rax, [rsi+8]
0x180011c18  mov     [rdi+18h], rax
0x180011c1c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011c23  mov     rcx, [rsi+8]
0x180011c27  inc     rax
0x180011c2a  cmp     word ptr [rcx+rax*2], 0
0x180011c2f  jnz     short loc_180011C27
0x180011c31  mov     [rdx], eax
0x180011c33  mov     eax, [rsi+20h]
0x180011c36  lea     r8, [rdi+38h]; ptr
0x180011c3a  mov     r9, rbp; error
0x180011c3d  mov     rcx, r15; heap
0x180011c40  lea     eax, ds:1[rax*2]
0x180011c47  mov     edx, eax; size
0x180011c49  mov     [rdi+30h], eax
0x180011c4c  call    cs:__imp_WsAlloc
0x180011c53  nop     dword ptr [rax+rax+00h]
0x180011c58  mov     ebx, eax
0x180011c5a  test    eax, eax
0x180011c5c  jns     short loc_180011C86
0x180011c5e  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011c65  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011c6a  mov     r8, rax
0x180011c6d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011c74  mov     edx, ebx
0x180011c76  mov     r9d, 0BA1h
0x180011c7c  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011c81  jmp     loc_180011ECA
0x180011c86  mov     rax, [rdi+38h]
0x180011c8a  mov     byte ptr [rax], 4
0x180011c8d  mov     rcx, [rdi+38h]
0x180011c91  mov     r8d, [rsi+10h]; Size
0x180011c95  inc     rcx; void *
0x180011c98  mov     rdx, [rsi+18h]; Src
0x180011c9c  call    memcpy_0
0x180011ca1  mov     rax, [rdi+38h]
0x180011ca5  mov     ecx, [rsi+10h]
0x180011ca8  inc     rax
0x180011cab  mov     r8d, [rsi+20h]; Size
0x180011caf  add     rcx, rax; void *
0x180011cb2  mov     rdx, [rsi+28h]; Src
0x180011cb6  call    memcpy_0
0x180011cbb  jmp     loc_180011ECA
0x180011cc0  mov     dword ptr [rdi], 3
0x180011cc6  lea     r9, [rdi+30h]
0x180011cca  mov     edx, [rsi+10h]
0x180011ccd  lea     r8, [rsp+58h+Src]
0x180011cd2  mov     rcx, [rsi+18h]
0x180011cd6  call    I_BigEndianBytesToDecString
0x180011cdb  mov     ebx, eax
0x180011cdd  test    eax, eax
0x180011cdf  jns     short loc_180011D09
0x180011ce1  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011ce8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011ced  mov     r8, rax
0x180011cf0  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011cf7  mov     edx, ebx
0x180011cf9  mov     r9d, 0B28h
0x180011cff  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011d04  jmp     loc_180011EB4
0x180011d09  mov     edx, [rdi+30h]
0x180011d0c  lea     r8, [rdi+38h]; ptr
0x180011d10  mov     [rsp+58h+arg_10], r14
0x180011d15  add     rdx, rdx; size
0x180011d18  mov     r14, [rsp+58h+error]
0x180011d20  mov     rcx, r15; heap
0x180011d23  mov     r9, r14; error
0x180011d26  call    cs:__imp_WsAlloc
0x180011d2d  nop     dword ptr [rax+rax+00h]
0x180011d32  mov     ebx, eax
0x180011d34  test    eax, eax
0x180011d36  jns     short loc_180011D60
0x180011d38  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011d3f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011d44  mov     r8, rax
0x180011d47  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011d4e  mov     edx, ebx
0x180011d50  mov     r9d, 0B34h
0x180011d56  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011d5b  jmp     loc_180011EAF
0x180011d60  mov     r8d, [rdi+30h]
0x180011d64  mov     rdx, [rsp+58h+Src]; Src
0x180011d69  add     r8, r8; Size
0x180011d6c  mov     rcx, [rdi+38h]; void *
0x180011d70  call    memcpy_0
0x180011d75  mov     rcx, [rsp+58h+Src]; hMem
0x180011d7a  call    cs:__imp_LocalFree
0x180011d81  nop     dword ptr [rax+rax+00h]
0x180011d86  mov     edx, [rsi+20h]
0x180011d89  lea     r9, [rdi+40h]
0x180011d8d  mov     rcx, [rsi+28h]
0x180011d91  lea     r8, [rsp+58h+Src]
0x180011d96  mov     [rsp+58h+Src], 0
0x180011d9f  call    I_BigEndianBytesToDecString
0x180011da4  mov     ebx, eax
0x180011da6  test    eax, eax
0x180011da8  jns     short loc_180011DD2
0x180011daa  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011db1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011db6  mov     r8, rax
0x180011db9  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011dc0  mov     edx, ebx
0x180011dc2  mov     r9d, 0B4Ch
0x180011dc8  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011dcd  jmp     loc_180011EAF
0x180011dd2  mov     edx, [rdi+40h]
0x180011dd5  lea     r8, [rdi+48h]; ptr
0x180011dd9  add     rdx, rdx; size
0x180011ddc  mov     r9, r14; error
0x180011ddf  mov     rcx, r15; heap
0x180011de2  call    cs:__imp_WsAlloc
0x180011de9  nop     dword ptr [rax+rax+00h]
0x180011dee  mov     ebx, eax
0x180011df0  test    eax, eax
0x180011df2  jns     short loc_180011E1C
0x180011df4  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011dfb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011e00  mov     r8, rax
0x180011e03  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011e0a  mov     edx, ebx
0x180011e0c  mov     r9d, 0B58h
0x180011e12  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011e17  jmp     loc_180011EAF
0x180011e1c  mov     r8d, [rdi+40h]
0x180011e20  mov     rdx, [rsp+58h+Src]; Src
0x180011e25  add     r8, r8; Size
0x180011e28  mov     rcx, [rdi+48h]; void *
0x180011e2c  call    memcpy_0
0x180011e31  cmp     dword ptr [rsi+34h], 0
0x180011e35  lea     rdx, [rdi+10h]
0x180011e39  jbe     short loc_180011E89
0x180011e3b  mov     [rsp+58h+var_30], rdx; struct _WS_XML_BUFFER **
0x180011e40  lea     rcx, [rsi+30h]; struct _CRYPT_XML_BLOB *
0x180011e44  mov     rdx, r13; struct _WS_XML_READER *
0x180011e47  mov     dword ptr [rdi+8], 1
0x180011e4e  mov     r9, r15; struct _WS_HEAP *
0x180011e51  mov     [rsp+58h+var_38], r14; struct _WS_ERROR *
0x180011e56  mov     r8, r12; struct _WS_XML_WRITER *
0x180011e59  call    ?I_XmlSetEncodedEx@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncodedEx(_CRYPT_XML_BLOB const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,_WS_XML_BUFFER * *)
0x180011e5e  mov     ebx, eax
0x180011e60  test    eax, eax
0x180011e62  jns     short loc_180011EAF
0x180011e64  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011e6b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011e70  mov     r8, rax
0x180011e73  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011e7a  mov     edx, ebx
0x180011e7c  mov     r9d, 0B6Fh
0x180011e82  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011e87  jmp     short loc_180011EAF
0x180011e89  mov     dword ptr [rdi+8], 2
0x180011e90  mov     rax, [rsi+8]
0x180011e94  mov     [rdi+18h], rax
0x180011e98  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011e9f  mov     rcx, [rsi+8]
0x180011ea3  inc     rax
0x180011ea6  cmp     word ptr [rcx+rax*2], 0
0x180011eab  jnz     short loc_180011EA3
0x180011ead  mov     [rdx], eax
0x180011eaf  mov     r14, [rsp+58h+arg_10]
0x180011eb4  mov     rcx, [rsp+58h+Src]; hMem
0x180011eb9  test    rcx, rcx
0x180011ebc  jz      short loc_180011ECA
0x180011ebe  call    cs:__imp_LocalFree
0x180011ec5  nop     dword ptr [rax+rax+00h]
0x180011eca  mov     rbp, [rsp+58h+arg_8]
0x180011ecf  mov     eax, ebx
0x180011ed1  mov     rbx, [rsp+58h+arg_18]
0x180011ed6  add     rsp, 30h
0x180011eda  pop     r15
0x180011edc  pop     r13
0x180011ede  pop     r12
0x180011ee0  pop     rdi
0x180011ee1  pop     rsi
0x180011ee2  retn
```
