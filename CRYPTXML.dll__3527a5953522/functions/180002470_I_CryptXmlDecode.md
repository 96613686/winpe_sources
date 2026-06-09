# I_CryptXmlDecode

- ea: `0x180002470`
- end: `0x18000299d`
- name: `I_CryptXmlDecode`
- size: `1325`
- prototype: `__int64 __fastcall(struct _HXML_DOC *, DWORD dwFlags, __int64, enum WS_CHARSET)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001fe0`

## callees

- `0x1800013a0`
- `0x180002470`
- `0x1800029b0`
- `0x180006150`
- `0x1800070d0`
- `0x18000c990`
- `0x180012d90`
- `0x180014ce0`
- `0x1800164cc`

## import_xrefs

- `webservices!WsReadNode` at `0x18000258c`
- `webservices!WsReadNode` at `0x18000258c`
- `webservices!WsReadToStartElement` at `0x180002532`
- `webservices!WsReadToStartElement` at `0x180002532`
- `webservices!WsGetReaderNode` at `0x18000255e`
- `webservices!WsGetReaderNode` at `0x18000255e`
- `webservices!WsReadElement` at `0x18000263d`
- `webservices!WsReadElement` at `0x18000263d`
- `webservices!WsSetInputToBuffer` at `0x1800024f9`
- `webservices!WsSetInputToBuffer` at `0x1800024f9`
- `webservices!WsGetReaderPosition` at `0x1800025e3`
- `webservices!WsGetReaderPosition` at `0x1800025e3`

## string_xrefs

- `0x1800025a2`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000268e`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000281c`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180002850`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180002889`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800028bd`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180002929`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000293d`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180002968`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180002902`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlDecode(struct _HXML_DOC *a1, DWORD dwFlags, __int64 a3, enum WS_CHARSET a4)
{
  __int64 v4; // rbx
  unsigned int v5; // esi
  __int64 v7; // r8
  unsigned int v8; // r10d
  unsigned int v12; // r15d
  HRESULT ReaderNode; // edi
  const char *v14; // rax
  int v15; // r9d
  __int64 v16; // rcx
  __int64 v17; // rcx
  enum WS_CHARSET v18; // ecx
  __int64 v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // rsi
  struct WS_TYPE_KeyInfo *v22; // r9
  __int64 v23; // rcx
  enum WS_CHARSET v24; // edx
  int v25; // eax
  __int64 v26; // rdx
  unsigned int i; // ebp
  __int64 v28; // r8
  __int64 v29; // rax
  unsigned __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // rax
  char v34; // dl
  const char *v35; // r8
  bool v36; // zf
  char v37; // dl
  const char *v38; // r8
  bool v39; // zf
  char v40; // dl
  const char *v41; // r8
  bool v42; // zf
  char v43; // dl
  const char *v44; // r8
  bool v45; // zf
  __int64 v46; // rax
  const char *v47; // rax
  int v48; // edx
  WS_XML_NODE *node; // [rsp+80h] [rbp+8h] BYREF
  BOOL found; // [rsp+98h] [rbp+20h] BYREF

  v4 = *((_QWORD *)a1 + 19);
  v5 = 0;
  found = 0;
  v7 = *((_QWORD *)a1 + 21);
  v8 = 0;
  node = 0;
  v12 = 2147483640;
  while ( 1 )
  {
    if ( v8 >= *((_DWORD *)a1 + 44) )
      goto LABEL_3;
    v33 = v7 + 24LL * v8;
    if ( *(_DWORD *)v33 == 1 )
      break;
    ++v8;
  }
  if ( *(_DWORD *)(v33 + 16) == 4 )
  {
    _mm_lfence();
    v12 = **(_DWORD **)(v33 + 8);
    if ( !v12 )
LABEL_3:
      v12 = 2147483640;
  }
  else
  {
    v47 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v47, 97);
  }
  ReaderNode = I_CryptXmlSetEncodedCtxt(a1, 0, a3);
  if ( ReaderNode < 0 )
  {
    v14 = "";
    while ( 1 )
    {
      v34 = *(v14 - 1);
      v35 = v14--;
      v36 = v34 == 92;
      if ( v34 == 92 )
        break;
      if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
      {
        v36 = v34 == 92;
        break;
      }
    }
    if ( v36 )
      v14 = v35;
    v15 = 1737;
  }
  else
  {
    ReaderNode = WsSetInputToBuffer(*(WS_XML_READER **)(v4 + 8), *(WS_XML_BUFFER **)(v4 + 40), 0, 0, *(WS_ERROR **)v4);
    if ( ReaderNode < 0 )
    {
      v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v15 = 1754;
    }
    else
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( WsReadToStartElement(
                 *(WS_XML_READER **)(v4 + 8),
                 &WS_XML_DIGSIG_Signature,
                 &WS_XML_DIGSIG_NS,
                 &found,
                 *(WS_ERROR **)v4) < 0 )
            goto LABEL_20;
          if ( found )
            break;
          ReaderNode = WsGetReaderNode(*(WS_XML_READER **)(v4 + 8), (const WS_XML_NODE **)&node, *(WS_ERROR **)v4);
          if ( ReaderNode < 0 )
          {
            v14 = "";
            while ( 1 )
            {
              v43 = *(v14 - 1);
              v44 = v14--;
              v45 = v43 == 92;
              if ( v43 == 92 )
                break;
              if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
              {
                v45 = v43 == 92;
                break;
              }
            }
            if ( v45 )
              v14 = v44;
            v15 = 1843;
            goto LABEL_76;
          }
          if ( node->nodeType == WS_XML_NODE_TYPE_EOF )
          {
LABEL_20:
            while ( 1 )
            {
              v19 = *((_QWORD *)a1 + 17);
              v20 = *(_DWORD *)(v19 + 24);
              if ( v5 >= v20 )
                break;
              ReaderNode = I_CryptXmlCanonicalizeSignedInfo(a1, v5);
              if ( ReaderNode < 0 )
              {
                v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
                v15 = 1875;
                goto LABEL_76;
              }
              ++v5;
            }
            if ( v20 )
            {
              v21 = 0;
              do
              {
                v22 = *(struct WS_TYPE_KeyInfo **)(*(_QWORD *)(*(_QWORD *)(v4 + 72) + 40 * v21 + 32) + 120LL);
                if ( v22 )
                {
                  v23 = *(_QWORD *)(*(_QWORD *)(v19 + 32) + 8 * v21);
                  if ( a4 )
                    v24 = a4;
                  else
                    v24 = *(_DWORD *)(v4 + 24);
                  v25 = I_XmlUnmarshallKeyInfo(
                          *(HANDLE *)(*(_QWORD *)(v23 + 8) + 48LL),
                          v24,
                          v12,
                          v22,
                          (struct _CRYPT_XML_WS_STATE *)v4,
                          (struct _CRYPT_XML_KEY_INFO **)(v23 + 152));
                  v26 = *((_QWORD *)a1 + 17);
                  if ( v25 >= 0 && *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v26 + 32) + 8 * v21) + 152LL) )
                  {
                    for ( i = 0; ; ++i )
                    {
                      v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 17) + 32LL) + 8 * v21) + 152LL);
                      if ( i >= *(_DWORD *)(v28 + 16) )
                        break;
                      v29 = *(_QWORD *)(v28 + 24);
                      v30 = (unsigned __int64)i << 7;
                      if ( *(_DWORD *)(v30 + v29) == 2
                        && CryptXmlImportPublicKey(
                             dwFlags,
                             (const CRYPT_XML_KEY_VALUE *)(v30 + v29 + 8),
                             (BCRYPT_KEY_HANDLE *)(v28 + 32)) >= 0 )
                      {
                        v31 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 17) + 32LL) + 8 * v21) + 8LL);
                        *(_DWORD *)(v31 + 72) |= 2u;
                        break;
                      }
                    }
                  }
                  else
                  {
                    v46 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v26 + 32) + 8 * v21) + 8LL);
                    *(_DWORD *)(v46 + 68) |= 0x20000u;
                  }
                }
                v19 = *((_QWORD *)a1 + 17);
                v21 = (unsigned int)(v21 + 1);
              }
              while ( (unsigned int)v21 < *(_DWORD *)(v19 + 24) );
            }
            return 0;
          }
          ReaderNode = WsReadNode(*(WS_XML_READER **)(v4 + 8), *(WS_ERROR **)v4);
          if ( ReaderNode < 0 )
          {
            v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
            v15 = 1856;
            goto LABEL_76;
          }
        }
        v16 = *(unsigned int *)(*((_QWORD *)a1 + 17) + 24LL);
        if ( (unsigned int)v16 >= *((_DWORD *)a1 + 36) )
          break;
        ReaderNode = WsGetReaderPosition(
                       *(WS_XML_READER **)(v4 + 8),
                       (WS_XML_NODE_POSITION *)(*(_QWORD *)(v4 + 72) + 40 * v16),
                       *(WS_ERROR **)v4);
        if ( ReaderNode < 0 )
        {
          v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
          v15 = 1789;
          goto LABEL_76;
        }
        v17 = *(unsigned int *)(*((_QWORD *)a1 + 17) + 24LL);
        ReaderNode = WsReadElement(
                       *(WS_XML_READER **)(v4 + 8),
                       &Signature_ElementDescription,
                       WS_READ_REQUIRED_POINTER,
                       *(WS_HEAP **)(v4 + 48),
                       (void *)(*(_QWORD *)(v4 + 72) + 8 * (v17 + 4 * (v17 + 1))),
                       8u,
                       *(WS_ERROR **)v4);
        if ( ReaderNode < 0 )
        {
          v14 = "";
          while ( 1 )
          {
            v37 = *(v14 - 1);
            v38 = v14--;
            v39 = v37 == 92;
            if ( v37 == 92 )
              break;
            if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
            {
              v39 = v37 == 92;
              break;
            }
          }
          if ( v39 )
            v14 = v38;
          v15 = 1808;
          goto LABEL_76;
        }
        if ( a4 )
          v18 = a4;
        else
          v18 = *(_DWORD *)(v4 + 24);
        ReaderNode = I_XmlUnmarshallSignature(
                       a1,
                       v18,
                       v12,
                       *(struct WS_TYPE_Signature **)(*(_QWORD *)(v4 + 72)
                                                    + 40LL * *(unsigned int *)(*((_QWORD *)a1 + 17) + 24LL)
                                                    + 32),
                       (struct _CRYPT_XML_WS_STATE *)v4);
        if ( ReaderNode < 0 )
        {
          v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
          v15 = 1825;
          goto LABEL_76;
        }
      }
      ReaderNode = -2146885362;
      v14 = "";
      while ( 1 )
      {
        v40 = *(v14 - 1);
        v41 = v14--;
        v42 = v40 == 92;
        if ( v40 == 92 )
          break;
        if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
        {
          v42 = v40 == 92;
          break;
        }
      }
      if ( v42 )
        v14 = v41;
      v15 = 1774;
    }
  }
LABEL_76:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", ReaderNode, v14, v15);
  I_TraceWsError(*(struct _WS_ERROR **)v4, v48);
  return (unsigned int)ReaderNode;
}

```

## disassembly

```asm
0x180002470  mov     rax, rsp
0x180002473  mov     [rax+10h], rbx
0x180002477  push    rbp
0x180002478  push    rsi
0x180002479  push    rdi
0x18000247a  push    r12
0x18000247c  push    r13
0x18000247e  push    r14
0x180002480  push    r15
0x180002482  sub     rsp, 40h
0x180002486  mov     rbx, [rcx+98h]
0x18000248d  xor     esi, esi
0x18000248f  mov     rdi, r8
0x180002492  mov     [rax+20h], esi
0x180002495  mov     r8, [rcx+0A8h]
0x18000249c  mov     r10d, esi
0x18000249f  mov     [rax+8], rsi
0x1800024a3  mov     r12d, r9d
0x1800024a6  mov     r13d, edx
0x1800024a9  mov     r14, rcx
0x1800024ac  mov     r15d, 7FFFFFF8h
0x1800024b2  lea     rbp, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800024b9  cmp     r10d, [r14+0B0h]
0x1800024c0  jb      loc_1800027D1
0x1800024c6  mov     r15d, 7FFFFFF8h
0x1800024cc  mov     r8, rdi
0x1800024cf  xor     edx, edx
0x1800024d1  mov     rcx, r14
0x1800024d4  call    I_CryptXmlSetEncodedCtxt
0x1800024d9  mov     edi, eax
0x1800024db  test    eax, eax
0x1800024dd  js      loc_180002815
0x1800024e3  mov     rax, [rbx]
0x1800024e6  xor     r9d, r9d; propertyCount
0x1800024e9  mov     rdx, [rbx+28h]; buffer
0x1800024ed  xor     r8d, r8d; properties
0x1800024f0  mov     rcx, [rbx+8]; reader
0x1800024f4  mov     [rsp+78h+error], rax; error
0x1800024f9  call    cs:__imp_WsSetInputToBuffer
0x180002500  nop     dword ptr [rax+rax+00h]
0x180002505  mov     edi, eax
0x180002507  test    eax, eax
0x180002509  js      loc_180002929
0x18000250f  nop
0x180002510  mov     rax, [rbx]
0x180002513  lea     r9, [rsp+78h+found]; found
0x18000251b  mov     rcx, [rbx+8]; reader
0x18000251f  lea     r8, ?WS_XML_DIGSIG_NS@@3U_WS_XML_STRING@@B; ns
0x180002526  lea     rdx, ?WS_XML_DIGSIG_Signature@@3U_WS_XML_STRING@@B; localName
0x18000252d  mov     [rsp+78h+error], rax; error
0x180002532  call    cs:__imp_WsReadToStartElement
0x180002539  nop     dword ptr [rax+rax+00h]
0x18000253e  test    eax, eax
0x180002540  js      loc_1800026B0
0x180002546  cmp     [rsp+78h+found], esi
0x18000254d  jnz     short loc_1800025B9
0x18000254f  mov     r8, [rbx]; error
0x180002552  lea     rdx, [rsp+78h+node]; node
0x18000255a  mov     rcx, [rbx+8]; xmlReader
0x18000255e  call    cs:__imp_WsGetReaderNode
0x180002565  nop     dword ptr [rax+rax+00h]
0x18000256a  mov     edi, eax
0x18000256c  test    eax, eax
0x18000256e  js      loc_1800028B6
0x180002574  mov     rax, [rsp+78h+node]
0x18000257c  cmp     dword ptr [rax], 8
0x18000257f  jz      loc_1800026B0
0x180002585  mov     rdx, [rbx]; error
0x180002588  mov     rcx, [rbx+8]; reader
0x18000258c  call    cs:__imp_WsReadNode
0x180002593  nop     dword ptr [rax+rax+00h]
0x180002598  mov     edi, eax
0x18000259a  test    eax, eax
0x18000259c  jns     loc_180002510
0x1800025a2  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800025a9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800025ae  mov     r9d, 740h
0x1800025b4  jmp     loc_18000297A
0x1800025b9  mov     rax, [r14+88h]
0x1800025c0  mov     ecx, [rax+18h]
0x1800025c3  cmp     ecx, [r14+90h]
0x1800025ca  jnb     loc_18000287D
0x1800025d0  mov     rax, [rbx+48h]
0x1800025d4  lea     rcx, [rcx+rcx*4]
0x1800025d8  mov     r8, [rbx]; error
0x1800025db  lea     rdx, [rax+rcx*8]; nodePosition
0x1800025df  mov     rcx, [rbx+8]; reader
0x1800025e3  call    cs:__imp_WsGetReaderPosition
0x1800025ea  nop     dword ptr [rax+rax+00h]
0x1800025ef  mov     edi, eax
0x1800025f1  test    eax, eax
0x1800025f3  js      loc_18000293D
0x1800025f9  mov     rax, [r14+88h]
0x180002600  mov     r8d, 2; readOption
0x180002606  mov     r9, [rbx+30h]; heap
0x18000260a  mov     ecx, [rax+18h]
0x18000260d  mov     rax, [rbx+48h]
0x180002611  lea     rdx, [rcx+1]
0x180002615  lea     rdx, [rcx+rdx*4]
0x180002619  lea     rcx, [rax+rdx*8]
0x18000261d  mov     rax, [rbx]
0x180002620  mov     [rsp+78h+var_48], rax; error
0x180002625  lea     rdx, ?Signature_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; elementDescription
0x18000262c  mov     [rsp+78h+valueSize], 8; valueSize
0x180002634  mov     [rsp+78h+error], rcx; value
0x180002639  mov     rcx, [rbx+8]; reader
0x18000263d  call    cs:__imp_WsReadElement
0x180002644  nop     dword ptr [rax+rax+00h]
0x180002649  mov     edi, eax
0x18000264b  test    eax, eax
0x18000264d  js      loc_180002849
0x180002653  mov     rax, [r14+88h]
0x18000265a  mov     ecx, [rax+18h]
0x18000265d  mov     rax, [rbx+48h]
0x180002661  lea     rdx, [rcx+rcx*4]
0x180002665  test    r12d, r12d
0x180002668  jnz     short loc_1800026A5
0x18000266a  mov     ecx, [rbx+18h]
0x18000266d  mov     r9, [rax+rdx*8+20h]; struct WS_TYPE_Signature *
0x180002672  mov     r8d, r15d; unsigned int
0x180002675  mov     edx, ecx; enum WS_CHARSET
0x180002677  mov     [rsp+78h+error], rbx; struct _CRYPT_XML_WS_STATE *
0x18000267c  mov     rcx, r14; struct _HXML_DOC *
0x18000267f  call    ?I_XmlUnmarshallSignature@@YAJPEAU_HXML_DOC@@W4WS_CHARSET@@KPEAUWS_TYPE_Signature@@PEAU_CRYPT_XML_WS_STATE@@@Z; I_XmlUnmarshallSignature(_HXML_DOC *,WS_CHARSET,ulong,WS_TYPE_Signature *,_CRYPT_XML_WS_STATE *)
0x180002684  mov     edi, eax
0x180002686  test    eax, eax
0x180002688  jns     loc_180002510
0x18000268e  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002695  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000269a  mov     r9d, 721h
0x1800026a0  jmp     loc_18000297A
0x1800026a5  mov     ecx, r12d
0x1800026a8  jmp     short loc_18000266D
0x1800026b0  mov     rdx, [r14+88h]
0x1800026b7  mov     eax, [rdx+18h]
0x1800026ba  cmp     esi, eax
0x1800026bc  jb      loc_180002951
0x1800026c2  test    eax, eax
0x1800026c4  jz      loc_1800027B6
0x1800026ca  xor     esi, esi
0x1800026cc  mov     rax, [rbx+48h]
0x1800026d0  lea     rcx, [rsi+rsi*4]
0x1800026d4  mov     rcx, [rax+rcx*8+20h]
0x1800026d9  mov     r9, [rcx+78h]; struct WS_TYPE_KeyInfo *
0x1800026dd  test    r9, r9
0x1800026e0  jz      loc_1800027A4
0x1800026e6  mov     rax, [rdx+20h]
0x1800026ea  mov     rcx, [rax+rsi*8]
0x1800026ee  lea     rax, [rcx+98h]
0x1800026f5  test    r12d, r12d
0x1800026f8  jnz     loc_180002805
0x1800026fe  mov     edx, [rbx+18h]; enum WS_CHARSET
0x180002701  mov     rcx, [rcx+8]
0x180002705  mov     r8d, r15d; unsigned int
0x180002708  mov     qword ptr [rsp+78h+valueSize], rax; struct _CRYPT_XML_KEY_INFO **
0x18000270d  mov     [rsp+78h+error], rbx; struct _CRYPT_XML_WS_STATE *
0x180002712  mov     rcx, [rcx+30h]; hHeap
0x180002716  call    ?I_XmlUnmarshallKeyInfo@@YAJPEAXW4WS_CHARSET@@KPEAUWS_TYPE_KeyInfo@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_CRYPT_XML_KEY_INFO@@@Z; I_XmlUnmarshallKeyInfo(void *,WS_CHARSET,ulong,WS_TYPE_KeyInfo *,_CRYPT_XML_WS_STATE *,_CRYPT_XML_KEY_INFO * *)
0x18000271b  mov     rdx, [r14+88h]
0x180002722  test    eax, eax
0x180002724  js      loc_1800028EA
0x18000272a  mov     rax, [rdx+20h]
0x18000272e  mov     rcx, [rax+rsi*8]
0x180002732  cmp     qword ptr [rcx+98h], 0
0x18000273a  jz      loc_1800028EA
0x180002740  xor     ebp, ebp
0x180002742  mov     rax, [r14+88h]
0x180002749  mov     rcx, [rax+20h]
0x18000274d  mov     rax, [rcx+rsi*8]
0x180002751  mov     r8, [rax+98h]
0x180002758  cmp     ebp, [r8+10h]
0x18000275c  jnb     short loc_1800027A4
0x18000275e  mov     rax, [r8+18h]
0x180002762  mov     ecx, ebp
0x180002764  shl     rcx, 7
0x180002768  cmp     dword ptr [rcx+rax], 2
0x18000276c  jnz     loc_180002996
0x180002772  lea     rdx, [rax+8]
0x180002776  add     r8, 20h ; ' '; phKey
0x18000277a  add     rdx, rcx; pKeyValue
0x18000277d  mov     ecx, r13d; dwFlags
0x180002780  call    CryptXmlImportPublicKey
0x180002785  test    eax, eax
0x180002787  js      loc_180002996
0x18000278d  mov     rax, [r14+88h]
0x180002794  mov     rcx, [rax+20h]
0x180002798  mov     rax, [rcx+rsi*8]
0x18000279c  mov     rcx, [rax+8]
0x1800027a0  or      dword ptr [rcx+48h], 2
0x1800027a4  mov     rdx, [r14+88h]
0x1800027ab  inc     esi
0x1800027ad  cmp     esi, [rdx+18h]
0x1800027b0  jb      loc_1800026CC
0x1800027b6  xor     eax, eax
0x1800027b8  mov     rbx, [rsp+78h+arg_8]
0x1800027c0  add     rsp, 40h
0x1800027c4  pop     r15
0x1800027c6  pop     r14
0x1800027c8  pop     r13
0x1800027ca  pop     r12
0x1800027cc  pop     rdi
0x1800027cd  pop     rsi
0x1800027ce  pop     rbp
0x1800027cf  retn
0x1800027d1  mov     eax, r10d
0x1800027d4  lea     rcx, [rax+rax*2]
0x1800027d8  cmp     dword ptr [r8+rcx*8], 1
0x1800027dd  lea     rax, [r8+rcx*8]
0x1800027e1  jnz     short loc_18000280D
0x1800027e3  cmp     dword ptr [rax+10h], 4
0x1800027e7  jnz     loc_180002902
0x1800027ed  lfence
0x1800027f0  mov     rax, [rax+8]
0x1800027f4  mov     r15d, [rax]
0x1800027f7  test    r15d, r15d
0x1800027fa  jnz     loc_1800024CC
0x180002800  jmp     loc_1800024C6
0x180002805  mov     edx, r12d
0x180002808  jmp     loc_180002701
0x18000280d  inc     r10d
0x180002810  jmp     loc_1800024B2
0x180002815  lea     rax, aOnecoreDsSecur_5+30h; ""
0x18000281c  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002823  movzx   edx, byte ptr [rax-1]
0x180002827  mov     r8, rax
0x18000282a  dec     rax
0x18000282d  cmp     dl, 5Ch ; '\'
0x180002830  jz      short loc_18000283A
0x180002832  cmp     rax, rcx
0x180002835  ja      short loc_180002823
0x180002837  cmp     dl, 5Ch ; '\'
0x18000283a  cmovz   rax, r8
0x18000283e  mov     r9d, 6C9h
0x180002844  jmp     loc_18000297A
0x180002849  lea     rax, aOnecoreDsSecur_5+30h; ""
0x180002850  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002857  movzx   edx, byte ptr [rax-1]
0x18000285b  mov     r8, rax
0x18000285e  dec     rax
0x180002861  cmp     dl, 5Ch ; '\'
0x180002864  jz      short loc_18000286E
0x180002866  cmp     rax, rcx
0x180002869  ja      short loc_180002857
0x18000286b  cmp     dl, 5Ch ; '\'
0x18000286e  cmovz   rax, r8
0x180002872  mov     r9d, 710h
0x180002878  jmp     loc_18000297A
0x18000287d  mov     edi, 8009210Eh
0x180002882  lea     rax, aOnecoreDsSecur_5+30h; ""
0x180002889  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002890  movzx   edx, byte ptr [rax-1]
0x180002894  mov     r8, rax
0x180002897  dec     rax
0x18000289a  cmp     dl, 5Ch ; '\'
0x18000289d  jz      short loc_1800028A7
0x18000289f  cmp     rax, rcx
0x1800028a2  ja      short loc_180002890
0x1800028a4  cmp     dl, 5Ch ; '\'
0x1800028a7  cmovz   rax, r8
0x1800028ab  mov     r9d, 6EEh
0x1800028b1  jmp     loc_18000297A
0x1800028b6  lea     rax, aOnecoreDsSecur_5+30h; ""
0x1800028bd  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800028c4  movzx   edx, byte ptr [rax-1]
0x1800028c8  mov     r8, rax
0x1800028cb  dec     rax
0x1800028ce  cmp     dl, 5Ch ; '\'
0x1800028d1  jz      short loc_1800028DB
0x1800028d3  cmp     rax, rcx
0x1800028d6  ja      short loc_1800028C4
0x1800028d8  cmp     dl, 5Ch ; '\'
0x1800028db  cmovz   rax, r8
0x1800028df  mov     r9d, 733h
0x1800028e5  jmp     loc_18000297A
0x1800028ea  mov     rax, [rdx+20h]
0x1800028ee  mov     rcx, [rax+rsi*8]
0x1800028f2  mov     rax, [rcx+8]
0x1800028f6  or      dword ptr [rax+44h], 20000h
0x1800028fd  jmp     loc_1800027A4
0x180002902  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002909  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000290e  mov     r8, rax
0x180002911  mov     edx, 80070057h
0x180002916  mov     r9d, 61h ; 'a'
0x18000291c  mov     rcx, rbp; char *
0x18000291f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002924  jmp     loc_1800024CC
0x180002929  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002930  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180002935  mov     r9d, 6DAh
0x18000293b  jmp     short loc_18000297A
0x18000293d  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002944  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180002949  mov     r9d, 6FDh
0x18000294f  jmp     short loc_18000297A
0x180002951  mov     edx, esi
0x180002953  mov     rcx, r14
0x180002956  call    I_CryptXmlCanonicalizeSignedInfo
0x18000295b  mov     edi, eax
0x18000295d  test    eax, eax
  ... truncated ...
```
