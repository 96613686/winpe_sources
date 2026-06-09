# I_CryptXmlResolveByIdOrElementName

- ea: `0x18000fe50`
- end: `0x180010510`
- name: `I_CryptXmlResolveByIdOrElementName`
- size: `1728`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, ULONG, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800094a0`
- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x18000b1a0`
- `0x18000cfb0`
- `0x18000fe50`
- `0x180011410`
- `0x180014ce0`
- `0x1800164cc`
- `0x180018625`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800104ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800104ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104d1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001014b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001014b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800100c8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001017f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800100c8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001017f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800100a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001015c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800100a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001015c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180010058`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180010058`
- `webservices!WsSkipNode` at `0x1800102d7`
- `webservices!WsSkipNode` at `0x1800102d7`
- `webservices!WsCopyNode` at `0x1800103ba`
- `webservices!WsCopyNode` at `0x1800103ba`
- `webservices!WsFlushWriter` at `0x1800103ef`
- `webservices!WsFlushWriter` at `0x1800103ef`
- `webservices!WsReadNode` at `0x1800101ab`
- `webservices!WsReadNode` at `0x1800101ab`
- `webservices!WsEndReaderCanonicalization` at `0x180010307`
- `webservices!WsEndReaderCanonicalization` at `0x180010307`
- `webservices!WsGetReaderNode` at `0x18000ffec`
- `webservices!WsGetReaderNode` at `0x18000ffec`
- `webservices!WsSetOutput` at `0x180010386`
- `webservices!WsSetOutput` at `0x180010386`
- `webservices!WsSetInputToBuffer` at `0x18000ff94`
- `webservices!WsSetInputToBuffer` at `0x18000ff94`
- `webservices!WsStartReaderCanonicalization` at `0x1800102a7`
- `webservices!WsStartReaderCanonicalization` at `0x1800102a7`

## string_xrefs

- `0x18000ffad`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x1800100ff`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x1800101c8`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18001026c`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x1800102b9`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x1800102e9`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18001031d`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x180010398`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x1800103cc`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x180010401`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18001043f`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x180010458`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x180010216`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`
- `0x18000ff1f`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlResolveByIdOrElementName(__int64 a1, const WCHAR *a2, __int64 a3, ULONG a4, __int64 a5)
{
  const WCHAR *v6; // rsi
  _DWORD *v7; // r13
  WS_ERROR **v8; // r15
  unsigned int v9; // r8d
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rax
  const char *v13; // rax
  ULONG v14; // eax
  HRESULT ReaderNode; // ebx
  const char *v16; // r8
  char v17; // al
  const char *v18; // rdx
  bool v19; // zf
  int v20; // r9d
  WS_XML_NODE *v21; // r14
  __int64 i; // rbx
  __int64 v23; // rdi
  __int64 v24; // rdi
  unsigned int v25; // esi
  const WCHAR *v26; // rdi
  int v27; // eax
  __int64 v28; // rcx
  _DWORD *v29; // rax
  const struct _CRYPT_XML_PROPERTY *v30; // rdx
  unsigned int v31; // r8d
  char v32; // al
  const char *v33; // rdx
  bool v34; // zf
  int v35; // edi
  int v36; // eax
  char v37; // al
  const char *v38; // rdx
  bool v39; // zf
  const char *v40; // rax
  WS_XML_WRITER *v41; // rcx
  int v42; // eax
  int v43; // edx
  int cchCount2; // [rsp+30h] [rbp-D8h]
  WS_ERROR *cchCount2a; // [rsp+30h] [rbp-D8h]
  ULONG propertyCount[2]; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpString; // [rsp+40h] [rbp-C8h] BYREF
  WS_XML_NODE *node; // [rsp+48h] [rbp-C0h] BYREF
  struct _CRYPT_XML_ALGORITHM output; // [rsp+50h] [rbp-B8h] BYREF
  _DWORD *writeCallbackState; // [rsp+70h] [rbp-98h] BYREF
  WS_XML_WRITER_PROPERTY v52; // [rsp+78h] [rbp-90h] BYREF
  int v53; // [rsp+90h] [rbp-78h]
  WS_XML_CANONICALIZATION_PROPERTY properties; // [rsp+A8h] [rbp-60h] BYREF
  WCHAR WideCharStr[256]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v56[256]; // [rsp+2F8h] [rbp+1F0h] BYREF

  v6 = a2;
  v7 = 0;
  v8 = *(WS_ERROR ***)(a1 + 152);
  lpString = a2;
  *(_OWORD *)&v52.value = 0;
  propertyCount[1] = a4;
  node = 0;
  memset_0(v56, 0, sizeof(v56));
  v9 = *(_DWORD *)(a1 + 176);
  v10 = *(_QWORD *)(a1 + 168);
  v11 = 0;
  *(_QWORD *)&v52.valueSize = propertyCount;
  propertyCount[0] = 2147483640;
  LODWORD(v52.value) = 8;
  v53 = 4;
  while ( 1 )
  {
    if ( (unsigned int)v11 >= v9 )
    {
      v14 = 0;
      goto LABEL_9;
    }
    v12 = v10 + 24 * v11;
    if ( *(_DWORD *)v12 == 1 )
      break;
    v11 = (unsigned int)(v11 + 1);
  }
  if ( *(_DWORD *)(v12 + 16) != 4 )
  {
    v13 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v13, 97);
    v14 = propertyCount[0];
    goto LABEL_10;
  }
  _mm_lfence();
  v14 = **(_DWORD **)(v12 + 8);
LABEL_9:
  propertyCount[0] = v14;
LABEL_10:
  if ( !v14 )
    propertyCount[0] = 2147483640;
  *(_OWORD *)a5 = 0;
  *(_OWORD *)(a5 + 16) = 0;
  ReaderNode = WsSetInputToBuffer(v8[1], v8[5], 0, 0, *v8);
  if ( ReaderNode >= 0 )
  {
    while ( 1 )
    {
      ReaderNode = WsGetReaderNode(v8[1], (const WS_XML_NODE **)&node, *v8);
      if ( ReaderNode < 0 )
        break;
      v21 = node;
      if ( node->nodeType == WS_XML_NODE_TYPE_ELEMENT )
      {
        for ( i = 0; (unsigned int)i < v21[8].nodeType; i = (unsigned int)(i + 1) )
        {
          v23 = *(_QWORD *)(*(_QWORD *)&v21[10].nodeType + 8 * i);
          if ( !*(_BYTE *)(v23 + 1)
            && CompareStringA(0, 1u, "Id", 2, *(PCNZCH *)(*(_QWORD *)(v23 + 16) + 8LL), **(_DWORD **)(v23 + 16)) == 2 )
          {
            v24 = *(_QWORD *)(v23 + 32);
            memset_0(WideCharStr, 0, sizeof(WideCharStr));
            if ( *(_DWORD *)v24 == 1 )
            {
              v35 = MultiByteToWideChar(0xFDE9u, 0, *(LPCCH *)(v24 + 16), *(_DWORD *)(v24 + 8), WideCharStr, 256);
              v36 = lstrlenW(v6);
              if ( CompareStringW(0, 0, v6, v36, WideCharStr, v35) == 2 )
                goto LABEL_29;
            }
            else if ( *(_DWORD *)v24 == 2 )
            {
              v25 = *(_DWORD *)(v24 + 16);
              v26 = *(const WCHAR **)(v24 + 8);
              v27 = lstrlenW(lpString);
              cchCount2 = v25 >> 1;
              v6 = lpString;
              if ( CompareStringW(0, 0, lpString, v27, v26, cchCount2) == 2 )
              {
LABEL_29:
                v29 = (_DWORD *)CryptXmlAlloc(v28, 32);
                v7 = v29;
                if ( !v29 )
                {
                  ReaderNode = -2147024882;
                  v16 = "";
                  while ( 1 )
                  {
                    v32 = *(v16 - 1);
                    v33 = v16--;
                    v34 = v32 == 92;
                    if ( v32 == 92 )
                      break;
                    if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp" )
                    {
                      v34 = v32 == 92;
                      break;
                    }
                  }
                  if ( v34 )
                    v16 = v33;
                  v20 = 344;
                  goto LABEL_67;
                }
                v19 = propertyCount[1] == 0;
                *v29 = 32;
                *(_QWORD *)&v52.id = &CRYPT_XML_ENCODE_REFERENCE_WRITE_CALLBACK;
                writeCallbackState = v29;
                if ( v19 )
                {
                  v41 = v8[2];
                  output.wszAlgorithm = (LPCWSTR)WS_TO_CRYPTXML_WRITE_CALLBACK;
                  lpString = (LPCWSTR)0x100000001LL;
                  *(_QWORD *)&output.Encoded.dwCharset = &writeCallbackState;
                  cchCount2a = *v8;
                  *(_QWORD *)&output.cbSize = 2;
                  ReaderNode = WsSetOutput(
                                 v41,
                                 (const WS_XML_WRITER_ENCODING *)&lpString,
                                 (const WS_XML_WRITER_OUTPUT *)&output,
                                 (const WS_XML_WRITER_PROPERTY *)&v52.value,
                                 1u,
                                 cchCount2a);
                  if ( ReaderNode < 0 )
                  {
                    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
                    v20 = 441;
                    goto LABEL_66;
                  }
                  ReaderNode = WsCopyNode(v8[2], v8[1], *v8);
                  if ( ReaderNode < 0 )
                  {
                    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
                    v20 = 452;
                    goto LABEL_66;
                  }
                  ReaderNode = WsFlushWriter(v8[2], 0, 0, *v8);
                  if ( ReaderNode < 0 )
                  {
                    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
                    v20 = 464;
                    goto LABEL_66;
                  }
                }
                else
                {
                  output.wszAlgorithm = L"http://www.w3.org/TR/2001/REC-xml-c14n-20010315";
                  propertyCount[1] = 3;
                  *(_QWORD *)&output.cbSize = 32;
                  *(_QWORD *)&output.Encoded.dwCharset = 0;
                  output.Encoded.pbData = 0;
                  ReaderNode = I_CryptXmlGetCanonPropertiesForWsReader(
                                 &output,
                                 v30,
                                 v31,
                                 &properties,
                                 &propertyCount[1],
                                 0);
                  if ( ReaderNode < 0 )
                  {
                    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
                    v20 = 376;
                    goto LABEL_66;
                  }
                  ReaderNode = WsStartReaderCanonicalization(
                                 v8[1],
                                 WS_TO_CRYPTXML_WRITE_CALLBACK,
                                 &writeCallbackState,
                                 &properties,
                                 propertyCount[1],
                                 *v8);
                  if ( ReaderNode < 0 )
                  {
                    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
                    v20 = 390;
                    goto LABEL_66;
                  }
                  ReaderNode = WsSkipNode(v8[1], *v8);
                  if ( ReaderNode < 0 )
                  {
                    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
                    v20 = 401;
                    goto LABEL_66;
                  }
                  ReaderNode = WsEndReaderCanonicalization(v8[1], *v8);
                  if ( ReaderNode < 0 )
                  {
                    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
                    v20 = 411;
                    goto LABEL_66;
                  }
                }
                *(_QWORD *)a5 = v7;
                *(_QWORD *)(a5 + 16) = &CRYPT_XML_REFERENCE_DATA_PROVIDER_READ;
                *(_QWORD *)(a5 + 24) = CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE;
                v42 = v7[3];
                v7 = 0;
                *(_DWORD *)(a5 + 8) = v42;
                goto LABEL_69;
              }
            }
          }
        }
      }
      else if ( node->nodeType == WS_XML_NODE_TYPE_EOF )
      {
        ReaderNode = -2146885368;
        v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
        v20 = 501;
LABEL_66:
        v16 = v40;
        goto LABEL_67;
      }
      ReaderNode = WsReadNode(v8[1], *v8);
      if ( ReaderNode < 0 )
      {
        v16 = "";
        while ( 1 )
        {
          v37 = *(v16 - 1);
          v38 = v16--;
          v39 = v37 == 92;
          if ( v37 == 92 )
            break;
          if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp" )
          {
            v39 = v37 == 92;
            break;
          }
        }
        if ( v39 )
          v16 = v38;
        v20 = 493;
        goto LABEL_67;
      }
    }
    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
    v20 = 261;
    goto LABEL_66;
  }
  v16 = "";
  while ( 1 )
  {
    v17 = *(v16 - 1);
    v18 = v16--;
    v19 = v17 == 92;
    if ( v17 == 92 )
      break;
    if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp" )
    {
      v19 = v17 == 92;
      break;
    }
  }
  if ( v19 )
    v16 = v18;
  v20 = 227;
LABEL_67:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", ReaderNode, v16, v20);
  if ( *v8 )
    I_TraceWsError(*v8, v43);
LABEL_69:
  if ( v7 )
    CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE(v7);
  return (unsigned int)ReaderNode;
}

```

## disassembly

```asm
0x18000fe50  mov     r11, rsp
0x18000fe53  push    rbp
0x18000fe54  push    rbx
0x18000fe55  push    r13
0x18000fe57  lea     rbp, [r11-348h]
0x18000fe5e  sub     rsp, 430h
0x18000fe65  mov     rax, cs:__security_cookie
0x18000fe6c  xor     rax, rsp
0x18000fe6f  mov     [rbp+340h+var_50], rax
0x18000fe76  mov     [r11+18h], rsi
0x18000fe7a  mov     rbx, rcx
0x18000fe7d  mov     [r11-20h], rdi
0x18000fe81  mov     rsi, rdx
0x18000fe84  mov     [r11-28h], r12
0x18000fe88  mov     r8d, 100h; Size
0x18000fe8e  mov     r12, [rbp+340h+arg_20]
0x18000fe95  xor     r13d, r13d
0x18000fe98  mov     [r11-38h], r15
0x18000fe9c  mov     r15, [rcx+98h]
0x18000fea3  lea     rcx, [rbp+340h+var_150]; void *
0x18000feaa  movaps  xmmword ptr [r11-48h], xmm6
0x18000feaf  xorps   xmm6, xmm6
0x18000feb2  mov     [rsp+440h+lpString], rdx
0x18000feb7  xor     edx, edx; Val
0x18000feb9  movups  xmmword ptr [rsp+440h+var_3D0.value], xmm6
0x18000febe  mov     [rsp+440h+propertyCount+4], r9d
0x18000fec3  mov     [rsp+440h+node], 0
0x18000fecc  call    memset_0
0x18000fed1  mov     r8d, [rbx+0B0h]
0x18000fed8  lea     rax, [rsp+440h+propertyCount]
0x18000fedd  mov     r9, [rbx+0A8h]
0x18000fee4  xor     edx, edx
0x18000fee6  mov     qword ptr [rbp+340h+var_3D0.valueSize], rax
0x18000feea  mov     [rsp+440h+propertyCount], 7FFFFFF8h
0x18000fef2  mov     dword ptr [rsp+440h+var_3D0.value], 8
0x18000fefa  mov     [rbp+340h+var_3B8], 4
0x18000ff01  cmp     edx, r8d
0x18000ff04  jnb     short loc_18000FF56
0x18000ff06  lea     rcx, [rdx+rdx*2]
0x18000ff0a  cmp     dword ptr [r9+rcx*8], 1
0x18000ff0f  lea     rax, [r9+rcx*8]
0x18000ff13  jz      short loc_18000FF19
0x18000ff15  inc     edx
0x18000ff17  jmp     short loc_18000FF01
0x18000ff19  cmp     dword ptr [rax+10h], 4
0x18000ff1d  jz      short loc_18000FF4B
0x18000ff1f  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ff26  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ff2b  mov     r8, rax
0x18000ff2e  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ff35  mov     edx, 80070057h
0x18000ff3a  mov     r9d, 61h ; 'a'
0x18000ff40  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ff45  mov     eax, [rsp+440h+propertyCount]
0x18000ff49  jmp     short loc_18000FF5C
0x18000ff4b  lfence
0x18000ff4e  mov     rax, [rax+8]
0x18000ff52  mov     eax, [rax]
0x18000ff54  jmp     short loc_18000FF58
0x18000ff56  xor     eax, eax
0x18000ff58  mov     [rsp+440h+propertyCount], eax
0x18000ff5c  test    eax, eax
0x18000ff5e  jnz     short loc_18000FF68
0x18000ff60  mov     [rsp+440h+propertyCount], 7FFFFFF8h
0x18000ff68  xorps   xmm0, xmm0
0x18000ff6b  mov     [rsp+440h+var_28], r14
0x18000ff73  movups  xmmword ptr [r12], xmm0
0x18000ff78  xor     r9d, r9d; propertyCount
0x18000ff7b  xor     r8d, r8d; properties
0x18000ff7e  movups  xmmword ptr [r12+10h], xmm0
0x18000ff84  mov     rax, [r15]
0x18000ff87  mov     rdx, [r15+28h]; buffer
0x18000ff8b  mov     rcx, [r15+8]; reader
0x18000ff8f  mov     [rsp+440h+error], rax; error
0x18000ff94  call    cs:__imp_WsSetInputToBuffer
0x18000ff9b  nop     dword ptr [rax+rax+00h]
0x18000ffa0  mov     ebx, eax
0x18000ffa2  test    eax, eax
0x18000ffa4  jns     short loc_18000FFE0
0x18000ffa6  lea     r8, aOnecoreDsSecur_0+30h; ""
0x18000ffad  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ffb4  movzx   eax, byte ptr [r8-1]
0x18000ffb9  mov     rdx, r8
0x18000ffbc  dec     r8
0x18000ffbf  cmp     al, 5Ch ; '\'
0x18000ffc1  jz      short loc_18000FFCA
0x18000ffc3  cmp     r8, rcx
0x18000ffc6  ja      short loc_18000FFB4
0x18000ffc8  cmp     al, 5Ch ; '\'
0x18000ffca  cmovz   r8, rdx
0x18000ffce  mov     r9d, 0E3h
0x18000ffd4  jmp     loc_18001046D
0x18000ffe0  mov     r8, [r15]; error
0x18000ffe3  lea     rdx, [rsp+440h+node]; node
0x18000ffe8  mov     rcx, [r15+8]; xmlReader
0x18000ffec  call    cs:__imp_WsGetReaderNode
0x18000fff3  nop     dword ptr [rax+rax+00h]
0x18000fff8  mov     ebx, eax
0x18000fffa  test    eax, eax
0x18000fffc  js      loc_180010458
0x180010002  mov     r14, [rsp+440h+node]
0x180010007  mov     eax, [r14]
0x18001000a  cmp     eax, 1
0x18001000d  jnz     loc_18001019B
0x180010013  xor     ebx, ebx
0x180010015  cmp     ebx, [r14+20h]
0x180010019  jnb     loc_1800101A4
0x18001001f  mov     rax, [r14+28h]
0x180010023  mov     rdi, [rax+rbx*8]
0x180010027  cmp     [rdi+1], r13b
0x18001002b  jnz     loc_180010194
0x180010031  mov     rcx, [rdi+10h]
0x180010035  lea     r8, String1; "Id"
0x18001003c  mov     r9d, 2; cchCount1
0x180010042  mov     edx, 1; dwCmpFlags
0x180010047  mov     eax, [rcx]
0x180010049  mov     [rsp+440h+cchCount2], eax; cchCount2
0x18001004d  mov     rax, [rcx+8]
0x180010051  xor     ecx, ecx; Locale
0x180010053  mov     [rsp+440h+error], rax; lpString2
0x180010058  call    cs:__imp_CompareStringA
0x18001005f  nop     dword ptr [rax+rax+00h]
0x180010064  cmp     eax, 2
0x180010067  jnz     loc_180010194
0x18001006d  mov     rdi, [rdi+20h]
0x180010071  lea     rcx, [rbp+340h+WideCharStr]; void *
0x180010075  xor     edx, edx; Val
0x180010077  mov     r8d, 200h; Size
0x18001007d  call    memset_0
0x180010082  mov     ecx, [rdi]
0x180010084  sub     ecx, 1
0x180010087  jz      loc_18001012B
0x18001008d  cmp     ecx, 1
0x180010090  jnz     loc_180010194
0x180010096  mov     esi, [rdi+10h]
0x180010099  mov     rcx, [rsp+440h+lpString]; lpString
0x18001009e  mov     rdi, [rdi+8]
0x1800100a2  shr     esi, 1
0x1800100a4  call    cs:__imp_lstrlenW
0x1800100ab  nop     dword ptr [rax+rax+00h]
0x1800100b0  mov     [rsp+440h+cchCount2], esi; cchCount2
0x1800100b4  xor     edx, edx; dwCmpFlags
0x1800100b6  mov     rsi, [rsp+440h+lpString]
0x1800100bb  mov     r9d, eax; cchCount1
0x1800100be  mov     r8, rsi; lpString1
0x1800100c1  mov     [rsp+440h+error], rdi; lpString2
0x1800100c6  xor     ecx, ecx; Locale
0x1800100c8  call    cs:__imp_CompareStringW
0x1800100cf  nop     dword ptr [rax+rax+00h]
0x1800100d4  cmp     eax, 2
0x1800100d7  jnz     loc_180010194
0x1800100dd  mov     edx, 20h ; ' '
0x1800100e2  call    CryptXmlAlloc
0x1800100e7  mov     r13, rax
0x1800100ea  test    rax, rax
0x1800100ed  jnz     loc_1800101F4
0x1800100f3  mov     ebx, 8007000Eh
0x1800100f8  lea     r8, aOnecoreDsSecur_0+30h; ""
0x1800100ff  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010106  movzx   eax, byte ptr [r8-1]
0x18001010b  mov     rdx, r8
0x18001010e  dec     r8
0x180010111  cmp     al, 5Ch ; '\'
0x180010113  jz      short loc_18001011C
0x180010115  cmp     r8, rcx
0x180010118  ja      short loc_180010106
0x18001011a  cmp     al, 5Ch ; '\'
0x18001011c  cmovz   r8, rdx
0x180010120  mov     r9d, 158h
0x180010126  jmp     loc_18001046D
0x18001012b  mov     r9d, [rdi+8]; cbMultiByte
0x18001012f  lea     rax, [rbp+340h+WideCharStr]
0x180010133  mov     r8, [rdi+10h]; lpMultiByteStr
0x180010137  xor     edx, edx; dwFlags
0x180010139  mov     [rsp+440h+cchCount2], 100h; cchWideChar
0x180010141  mov     ecx, 0FDE9h; CodePage
0x180010146  mov     [rsp+440h+error], rax; lpWideCharStr
0x18001014b  call    cs:__imp_MultiByteToWideChar
0x180010152  nop     dword ptr [rax+rax+00h]
0x180010157  mov     rcx, rsi; lpString
0x18001015a  mov     edi, eax
0x18001015c  call    cs:__imp_lstrlenW
0x180010163  nop     dword ptr [rax+rax+00h]
0x180010168  mov     [rsp+440h+cchCount2], edi; cchCount2
0x18001016c  mov     r8, rsi; lpString1
0x18001016f  mov     r9d, eax; cchCount1
0x180010172  xor     edx, edx; dwCmpFlags
0x180010174  lea     rax, [rbp+340h+WideCharStr]
0x180010178  xor     ecx, ecx; Locale
0x18001017a  mov     [rsp+440h+error], rax; lpString2
0x18001017f  call    cs:__imp_CompareStringW
0x180010186  nop     dword ptr [rax+rax+00h]
0x18001018b  cmp     eax, 2
0x18001018e  jz      loc_1800100DD
0x180010194  inc     ebx
0x180010196  jmp     loc_180010015
0x18001019b  cmp     eax, 8
0x18001019e  jz      loc_18001043F
0x1800101a4  mov     rdx, [r15]; error
0x1800101a7  mov     rcx, [r15+8]; reader
0x1800101ab  call    cs:__imp_WsReadNode
0x1800101b2  nop     dword ptr [rax+rax+00h]
0x1800101b7  mov     ebx, eax
0x1800101b9  test    eax, eax
0x1800101bb  jns     loc_18000FFE0
0x1800101c1  lea     r8, aOnecoreDsSecur_0+30h; ""
0x1800101c8  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800101cf  movzx   eax, byte ptr [r8-1]
0x1800101d4  mov     rdx, r8
0x1800101d7  dec     r8
0x1800101da  cmp     al, 5Ch ; '\'
0x1800101dc  jz      short loc_1800101E5
0x1800101de  cmp     r8, rcx
0x1800101e1  ja      short loc_1800101CF
0x1800101e3  cmp     al, 5Ch ; '\'
0x1800101e5  cmovz   r8, rdx
0x1800101e9  mov     r9d, 1EDh
0x1800101ef  jmp     loc_18001046D
0x1800101f4  cmp     [rsp+440h+propertyCount+4], 0
0x1800101f9  mov     dword ptr [rax], 20h ; ' '
0x1800101ff  lea     rax, CRYPT_XML_ENCODE_REFERENCE_WRITE_CALLBACK
0x180010206  mov     qword ptr [rsp+440h+var_3D0.id], rax
0x18001020b  mov     [rsp+440h+writeCallbackState], r13
0x180010210  jz      loc_180010334
0x180010216  lea     rax, aHttpWwwW3OrgTr_0; "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x18001021d  mov     qword ptr [rsp+440h+cchCount2], 0; int *
0x180010226  mov     [rsp+440h+var_3F0], rax
0x18001022b  lea     r9, [rbp+340h+properties]; struct _WS_XML_CANONICALIZATION_PROPERTY *
0x18001022f  lea     rax, [rsp+440h+propertyCount+4]
0x180010234  mov     [rsp+440h+propertyCount+4], 3
0x18001023c  lea     rcx, [rsp+440h+output]; struct _CRYPT_XML_ALGORITHM *
0x180010241  mov     [rsp+440h+error], rax; unsigned int *
0x180010246  mov     qword ptr [rsp+440h+output.outputType], 20h ; ' '
0x18001024f  mov     [rsp+440h+var_3E8], 0
0x180010258  mov     [rsp+440h+var_3E0], 0
0x180010261  call    ?I_CryptXmlGetCanonPropertiesForWsReader@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEBU_CRYPT_XML_PROPERTY@@KPEAU_WS_XML_CANONICALIZATION_PROPERTY@@PEAKPEAH@Z; I_CryptXmlGetCanonPropertiesForWsReader(_CRYPT_XML_ALGORITHM const *,_CRYPT_XML_PROPERTY const *,ulong,_WS_XML_CANONICALIZATION_PROPERTY *,ulong *,int *)
0x180010266  mov     ebx, eax
0x180010268  test    eax, eax
0x18001026a  jns     short loc_180010283
0x18001026c  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010273  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010278  mov     r9d, 178h
0x18001027e  jmp     loc_18001046A
0x180010283  mov     rax, [r15]
0x180010286  lea     r9, [rbp+340h+properties]; properties
0x18001028a  mov     rcx, [r15+8]; reader
0x18001028e  lea     r8, [rsp+440h+writeCallbackState]; writeCallbackState
0x180010293  mov     qword ptr [rsp+440h+cchCount2], rax; error
0x180010298  lea     rdx, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; writeCallback
0x18001029f  mov     eax, [rsp+440h+propertyCount+4]
0x1800102a3  mov     dword ptr [rsp+440h+error], eax; propertyCount
0x1800102a7  call    cs:__imp_WsStartReaderCanonicalization
0x1800102ae  nop     dword ptr [rax+rax+00h]
0x1800102b3  mov     ebx, eax
0x1800102b5  test    eax, eax
0x1800102b7  jns     short loc_1800102D0
0x1800102b9  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800102c0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800102c5  mov     r9d, 186h
0x1800102cb  jmp     loc_18001046A
0x1800102d0  mov     rdx, [r15]; error
0x1800102d3  mov     rcx, [r15+8]; reader
0x1800102d7  call    cs:__imp_WsSkipNode
0x1800102de  nop     dword ptr [rax+rax+00h]
0x1800102e3  mov     ebx, eax
0x1800102e5  test    eax, eax
0x1800102e7  jns     short loc_180010300
0x1800102e9  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800102f0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800102f5  mov     r9d, 191h
0x1800102fb  jmp     loc_18001046A
0x180010300  mov     rdx, [r15]; error
0x180010303  mov     rcx, [r15+8]; reader
0x180010307  call    cs:__imp_WsEndReaderCanonicalization
0x18001030e  nop     dword ptr [rax+rax+00h]
0x180010313  mov     ebx, eax
0x180010315  test    eax, eax
0x180010317  jns     loc_180010415
0x18001031d  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010324  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010329  mov     r9d, 19Bh
0x18001032f  jmp     loc_18001046A
0x180010334  mov     rcx, [r15+10h]; writer
0x180010338  lea     rax, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; WS_TO_CRYPTXML_WRITE_CALLBACK(void *,_WS_BYTES const *,ulong,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)
0x18001033f  mov     [rsp+440h+var_3F0], rax
0x180010344  lea     r9, [rsp+440h+var_3D0.value]; properties
0x180010349  lea     rax, [rsp+440h+writeCallbackState]
0x18001034e  mov     dword ptr [rsp+440h+lpString], 1
0x180010356  mov     [rsp+440h+var_3E8], rax
0x18001035b  lea     r8, [rsp+440h+output]; output
0x180010360  mov     rax, [r15]
0x180010363  lea     rdx, [rsp+440h+lpString]; encoding
0x180010368  mov     qword ptr [rsp+440h+cchCount2], rax; error
0x18001036d  mov     dword ptr [rsp+440h+error], 1; propertyCount
0x180010375  mov     dword ptr [rsp+440h+lpString+4], 1
0x18001037d  mov     qword ptr [rsp+440h+output.outputType], 2
0x180010386  call    cs:__imp_WsSetOutput
0x18001038d  nop     dword ptr [rax+rax+00h]
0x180010392  mov     ebx, eax
0x180010394  test    eax, eax
  ... truncated ...
```
