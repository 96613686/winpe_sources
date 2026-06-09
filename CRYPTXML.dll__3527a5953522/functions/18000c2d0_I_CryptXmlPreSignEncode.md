# I_CryptXmlPreSignEncode

- ea: `0x18000c2d0`
- end: `0x18000c754`
- name: `I_CryptXmlPreSignEncode`
- size: `1156`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x18000c2d0`
- `0x18000c75c`
- `0x180014ce0`
- `0x1800164cc`
- `0x180018625`

## import_xrefs

- `webservices!WsMoveWriter` at `0x18000c4b3`
- `webservices!WsMoveWriter` at `0x18000c52d`
- `webservices!WsMoveWriter` at `0x18000c6c1`
- `webservices!WsMoveWriter` at `0x18000c4b3`
- `webservices!WsMoveWriter` at `0x18000c52d`
- `webservices!WsMoveWriter` at `0x18000c6c1`
- `webservices!WsSetOutputToBuffer` at `0x18000c390`
- `webservices!WsSetOutputToBuffer` at `0x18000c435`
- `webservices!WsSetOutputToBuffer` at `0x18000c5f0`
- `webservices!WsSetOutputToBuffer` at `0x18000c390`
- `webservices!WsSetOutputToBuffer` at `0x18000c435`
- `webservices!WsSetOutputToBuffer` at `0x18000c5f0`
- `webservices!WsWriteElement` at `0x18000c646`
- `webservices!WsWriteElement` at `0x18000c646`
- `webservices!WsResetHeap` at `0x18000c565`
- `webservices!WsResetHeap` at `0x18000c565`
- `webservices!WsCreateXmlBuffer` at `0x18000c5aa`
- `webservices!WsCreateXmlBuffer` at `0x18000c5aa`
- `webservices!WsRemoveNode` at `0x18000c4e9`
- `webservices!WsRemoveNode` at `0x18000c4e9`
- `webservices!WsSetWriterPosition` at `0x18000c3d9`
- `webservices!WsSetWriterPosition` at `0x18000c46f`
- `webservices!WsSetWriterPosition` at `0x18000c3d9`
- `webservices!WsSetWriterPosition` at `0x18000c46f`
- `webservices!WsGetWriterPosition` at `0x18000c6f8`
- `webservices!WsGetWriterPosition` at `0x18000c6f8`

## string_xrefs

- `0x18000c33e`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c3a2`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c3ef`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c447`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c481`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c4c5`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c4fb`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c543`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c577`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c5bc`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c602`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c65f`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c6d3`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000c70a`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlPreSignEncode(__int64 a1, int a2, int a3, int a4)
{
  __int64 v4; // rbx
  HRESULT XmlBuffer; // edi
  const char *v10; // rax
  char v11; // dl
  const char *v12; // r8
  const char *v13; // r10
  __int64 v14; // r9
  const WS_XML_NODE_POSITION *v15; // rdx
  const WS_XML_NODE_POSITION **v16; // rsi
  char v17; // dl
  const char *v18; // r8
  int v19; // edx
  _BYTE value[200]; // [rsp+30h] [rbp-C8h] BYREF
  BOOL found; // [rsp+100h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 152);
  found = 0;
  memset_0(value, 0, 0x90u);
  XmlBuffer = I_XmlMarshallSignature(
                *(const struct _HXML_SIGNATURE **)(**(_QWORD **)(*(_QWORD *)(a1 + 136) + 32LL) + 8LL),
                (struct _CRYPT_XML_WS_STATE *)v4,
                a4,
                (struct WS_TYPE_Signature *)value);
  if ( XmlBuffer < 0 )
  {
    v10 = "";
    do
    {
      v11 = *(v10 - 1);
      v12 = v10--;
    }
    while ( v11 != 92 && v10 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" );
    v13 = "ERROR  : (0x%08x) %s:%u";
    v14 = 402;
    if ( v11 == 92 )
      v10 = v12;
    goto LABEL_45;
  }
  if ( a2 )
  {
    v16 = (const WS_XML_NODE_POSITION **)(v4 + 72);
    if ( **(_QWORD **)(v4 + 72) )
    {
      XmlBuffer = WsSetOutputToBuffer(
                    *(WS_XML_WRITER **)(v4 + 16),
                    *(WS_XML_BUFFER **)(v4 + 40),
                    0,
                    0,
                    *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 455;
        goto LABEL_45;
      }
      XmlBuffer = WsSetWriterPosition(*(WS_XML_WRITER **)(v4 + 16), *v16, *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 470;
        goto LABEL_45;
      }
      XmlBuffer = WsMoveWriter(*(WS_XML_WRITER **)(v4 + 16), WS_MOVE_TO_PARENT_ELEMENT, &found, *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 482;
        goto LABEL_45;
      }
      XmlBuffer = WsRemoveNode(*v16, *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 498;
        goto LABEL_45;
      }
      XmlBuffer = WsMoveWriter(*(WS_XML_WRITER **)(v4 + 16), WS_MOVE_TO_END_ELEMENT, &found, *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 510;
        goto LABEL_45;
      }
    }
    else
    {
      XmlBuffer = WsResetHeap(*(WS_HEAP **)(v4 + 32), *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 524;
        goto LABEL_45;
      }
      XmlBuffer = WsCreateXmlBuffer(*(WS_HEAP **)(v4 + 32), 0, 0, (WS_XML_BUFFER **)(v4 + 40), *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 541;
        goto LABEL_45;
      }
      XmlBuffer = WsSetOutputToBuffer(
                    *(WS_XML_WRITER **)(v4 + 16),
                    *(WS_XML_BUFFER **)(v4 + 40),
                    0,
                    0,
                    *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 554;
        goto LABEL_45;
      }
    }
    goto LABEL_31;
  }
  XmlBuffer = WsSetOutputToBuffer(*(WS_XML_WRITER **)(v4 + 16), *(WS_XML_BUFFER **)(v4 + 40), 0, 0, *(WS_ERROR **)v4);
  if ( XmlBuffer >= 0 )
  {
    v15 = *(const WS_XML_NODE_POSITION **)(v4 + 72);
    v16 = (const WS_XML_NODE_POSITION **)(v4 + 72);
    if ( v15->buffer )
    {
      XmlBuffer = WsSetWriterPosition(*(WS_XML_WRITER **)(v4 + 16), v15, *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 437;
        goto LABEL_45;
      }
    }
LABEL_31:
    XmlBuffer = WsWriteElement(
                  *(WS_XML_WRITER **)(v4 + 16),
                  &Signature_ElementDescription,
                  WS_WRITE_REQUIRED_VALUE,
                  value,
                  0x90u,
                  *(WS_ERROR **)v4);
    if ( XmlBuffer < 0 )
    {
      v10 = "";
      do
      {
        v17 = *(v10 - 1);
        v18 = v10--;
      }
      while ( v17 != 92 && v10 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" );
      v13 = "ERROR  : (0x%08x) %s:%u";
      v14 = 570;
      if ( v17 == 92 )
        v10 = v18;
      goto LABEL_45;
    }
    if ( a2 || a3 && (*v16)->buffer )
    {
      XmlBuffer = WsMoveWriter(*(WS_XML_WRITER **)(v4 + 16), WS_MOVE_TO_PREVIOUS_NODE, &found, *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 589;
        goto LABEL_45;
      }
      XmlBuffer = WsGetWriterPosition(*(WS_XML_WRITER **)(v4 + 16), (WS_XML_NODE_POSITION *)*v16, *(WS_ERROR **)v4);
      if ( XmlBuffer < 0 )
      {
        v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v14 = 602;
        goto LABEL_45;
      }
    }
    return 0;
  }
  v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
  v14 = 421;
LABEL_45:
  WPPTraceLogA(v13, (unsigned int)XmlBuffer, v10, v14);
  if ( *(_QWORD *)v4 )
    I_TraceWsError(*(struct _WS_ERROR **)v4, v19);
  return (unsigned int)XmlBuffer;
}

```

## disassembly

```asm
0x18000c2d0  push    rbx
0x18000c2d2  push    rbp
0x18000c2d3  push    rsi
0x18000c2d4  push    rdi
0x18000c2d5  push    r14
0x18000c2d7  push    r15
0x18000c2d9  sub     rsp, 0C8h
0x18000c2e0  mov     rbx, [rcx+98h]
0x18000c2e7  mov     r14d, r8d
0x18000c2ea  mov     ebp, edx
0x18000c2ec  mov     [rsp+0F8h+found], 0
0x18000c2f7  mov     rdi, rcx
0x18000c2fa  xor     edx, edx; Val
0x18000c2fc  mov     r8d, 90h; Size
0x18000c302  lea     rcx, [rsp+0F8h+value]; void *
0x18000c307  mov     esi, r9d
0x18000c30a  call    memset_0
0x18000c30f  mov     rax, [rdi+88h]
0x18000c316  lea     r9, [rsp+0F8h+value]; struct WS_TYPE_Signature *
0x18000c31b  mov     r8d, esi; int
0x18000c31e  mov     rdx, rbx; struct _CRYPT_XML_WS_STATE *
0x18000c321  mov     rcx, [rax+20h]
0x18000c325  mov     rcx, [rcx]
0x18000c328  mov     rcx, [rcx+8]; struct _HXML_SIGNATURE *
0x18000c32c  call    ?I_XmlMarshallSignature@@YAJPEBU_HXML_SIGNATURE@@PEAU_CRYPT_XML_WS_STATE@@HPEAUWS_TYPE_Signature@@@Z; I_XmlMarshallSignature(_HXML_SIGNATURE const *,_CRYPT_XML_WS_STATE *,int,WS_TYPE_Signature *)
0x18000c331  mov     edi, eax
0x18000c333  test    eax, eax
0x18000c335  jns     short loc_18000C372
0x18000c337  lea     rax, aOnecoreDsSecur_5+30h; ""
0x18000c33e  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c345  movzx   edx, byte ptr [rax-1]
0x18000c349  mov     r8, rax
0x18000c34c  dec     rax
0x18000c34f  cmp     dl, 5Ch ; '\'
0x18000c352  jz      short loc_18000C359
0x18000c354  cmp     rax, rcx
0x18000c357  ja      short loc_18000C345
0x18000c359  cmp     dl, 5Ch ; '\'
0x18000c35c  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c363  mov     r9d, 192h
0x18000c369  cmovz   rax, r8
0x18000c36d  jmp     loc_18000C723
0x18000c372  test    ebp, ebp
0x18000c374  jnz     loc_18000C40D
0x18000c37a  mov     rax, [rbx]
0x18000c37d  xor     r9d, r9d; propertyCount
0x18000c380  mov     rdx, [rbx+28h]; buffer
0x18000c384  xor     r8d, r8d; properties
0x18000c387  mov     rcx, [rbx+10h]; writer
0x18000c38b  mov     [rsp+0F8h+error], rax; error
0x18000c390  call    cs:__imp_WsSetOutputToBuffer
0x18000c397  nop     dword ptr [rax+rax+00h]
0x18000c39c  mov     edi, eax
0x18000c39e  test    eax, eax
0x18000c3a0  jns     short loc_18000C3C0
0x18000c3a2  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c3a9  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c3b0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c3b5  mov     r9d, 1A5h
0x18000c3bb  jmp     loc_18000C723
0x18000c3c0  mov     rdx, [rbx+48h]; nodePosition
0x18000c3c4  lea     rsi, [rbx+48h]
0x18000c3c8  cmp     qword ptr [rdx], 0
0x18000c3cc  jz      loc_18000C620
0x18000c3d2  mov     r8, [rbx]; error
0x18000c3d5  mov     rcx, [rbx+10h]; writer
0x18000c3d9  call    cs:__imp_WsSetWriterPosition
0x18000c3e0  nop     dword ptr [rax+rax+00h]
0x18000c3e5  mov     edi, eax
0x18000c3e7  test    eax, eax
0x18000c3e9  jns     loc_18000C620
0x18000c3ef  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c3f6  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c3fd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c402  mov     r9d, 1B5h
0x18000c408  jmp     loc_18000C723
0x18000c40d  mov     rax, [rbx+48h]
0x18000c411  lea     rsi, [rbx+48h]
0x18000c415  mov     rdx, [rbx]; error
0x18000c418  cmp     qword ptr [rax], 0
0x18000c41c  jz      loc_18000C561
0x18000c422  mov     rcx, [rbx+10h]; writer
0x18000c426  xor     r9d, r9d; propertyCount
0x18000c429  mov     [rsp+0F8h+error], rdx; error
0x18000c42e  xor     r8d, r8d; properties
0x18000c431  mov     rdx, [rbx+28h]; buffer
0x18000c435  call    cs:__imp_WsSetOutputToBuffer
0x18000c43c  nop     dword ptr [rax+rax+00h]
0x18000c441  mov     edi, eax
0x18000c443  test    eax, eax
0x18000c445  jns     short loc_18000C465
0x18000c447  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c44e  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c455  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c45a  mov     r9d, 1C7h
0x18000c460  jmp     loc_18000C723
0x18000c465  mov     r8, [rbx]; error
0x18000c468  mov     rdx, [rsi]; nodePosition
0x18000c46b  mov     rcx, [rbx+10h]; writer
0x18000c46f  call    cs:__imp_WsSetWriterPosition
0x18000c476  nop     dword ptr [rax+rax+00h]
0x18000c47b  mov     edi, eax
0x18000c47d  test    eax, eax
0x18000c47f  jns     short loc_18000C49F
0x18000c481  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c488  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c48f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c494  mov     r9d, 1D6h
0x18000c49a  jmp     loc_18000C723
0x18000c49f  mov     r9, [rbx]; error
0x18000c4a2  lea     r8, [rsp+0F8h+found]; found
0x18000c4aa  mov     rcx, [rbx+10h]; writer
0x18000c4ae  mov     edx, 5; moveTo
0x18000c4b3  call    cs:__imp_WsMoveWriter
0x18000c4ba  nop     dword ptr [rax+rax+00h]
0x18000c4bf  mov     edi, eax
0x18000c4c1  test    eax, eax
0x18000c4c3  jns     short loc_18000C4E3
0x18000c4c5  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c4cc  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c4d3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c4d8  mov     r9d, 1E2h
0x18000c4de  jmp     loc_18000C723
0x18000c4e3  mov     rdx, [rbx]; error
0x18000c4e6  mov     rcx, [rsi]; nodePosition
0x18000c4e9  call    cs:__imp_WsRemoveNode
0x18000c4f0  nop     dword ptr [rax+rax+00h]
0x18000c4f5  mov     edi, eax
0x18000c4f7  test    eax, eax
0x18000c4f9  jns     short loc_18000C519
0x18000c4fb  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c502  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c509  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c50e  mov     r9d, 1F2h
0x18000c514  jmp     loc_18000C723
0x18000c519  mov     r9, [rbx]; error
0x18000c51c  lea     r8, [rsp+0F8h+found]; found
0x18000c524  mov     rcx, [rbx+10h]; writer
0x18000c528  mov     edx, 4; moveTo
0x18000c52d  call    cs:__imp_WsMoveWriter
0x18000c534  nop     dword ptr [rax+rax+00h]
0x18000c539  mov     edi, eax
0x18000c53b  test    eax, eax
0x18000c53d  jns     loc_18000C620
0x18000c543  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c54a  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c551  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c556  mov     r9d, 1FEh
0x18000c55c  jmp     loc_18000C723
0x18000c561  mov     rcx, [rbx+20h]; heap
0x18000c565  call    cs:__imp_WsResetHeap
0x18000c56c  nop     dword ptr [rax+rax+00h]
0x18000c571  mov     edi, eax
0x18000c573  test    eax, eax
0x18000c575  jns     short loc_18000C595
0x18000c577  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c57e  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c585  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c58a  mov     r9d, 20Ch
0x18000c590  jmp     loc_18000C723
0x18000c595  mov     rax, [rbx]
0x18000c598  lea     r9, [rbx+28h]; buffer
0x18000c59c  mov     rcx, [rbx+20h]; heap
0x18000c5a0  xor     r8d, r8d; propertyCount
0x18000c5a3  xor     edx, edx; properties
0x18000c5a5  mov     [rsp+0F8h+error], rax; error
0x18000c5aa  call    cs:__imp_WsCreateXmlBuffer
0x18000c5b1  nop     dword ptr [rax+rax+00h]
0x18000c5b6  mov     edi, eax
0x18000c5b8  test    eax, eax
0x18000c5ba  jns     short loc_18000C5DA
0x18000c5bc  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c5c3  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c5ca  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c5cf  mov     r9d, 21Dh
0x18000c5d5  jmp     loc_18000C723
0x18000c5da  mov     rax, [rbx]
0x18000c5dd  xor     r9d, r9d; propertyCount
0x18000c5e0  mov     rdx, [rbx+28h]; buffer
0x18000c5e4  xor     r8d, r8d; properties
0x18000c5e7  mov     rcx, [rbx+10h]; writer
0x18000c5eb  mov     [rsp+0F8h+error], rax; error
0x18000c5f0  call    cs:__imp_WsSetOutputToBuffer
0x18000c5f7  nop     dword ptr [rax+rax+00h]
0x18000c5fc  mov     edi, eax
0x18000c5fe  test    eax, eax
0x18000c600  jns     short loc_18000C620
0x18000c602  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c609  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c610  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c615  mov     r9d, 22Ah
0x18000c61b  jmp     loc_18000C723
0x18000c620  mov     rax, [rbx]
0x18000c623  lea     r9, [rsp+0F8h+value]; value
0x18000c628  mov     rcx, [rbx+10h]; writer
0x18000c62c  lea     rdx, ?Signature_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; elementDescription
0x18000c633  mov     [rsp+0F8h+var_D0], rax; error
0x18000c638  mov     r8d, 1; writeOption
0x18000c63e  mov     dword ptr [rsp+0F8h+error], 90h; valueSize
0x18000c646  call    cs:__imp_WsWriteElement
0x18000c64d  nop     dword ptr [rax+rax+00h]
0x18000c652  mov     edi, eax
0x18000c654  test    eax, eax
0x18000c656  jns     short loc_18000C693
0x18000c658  lea     rax, aOnecoreDsSecur_5+30h; ""
0x18000c65f  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c666  movzx   edx, byte ptr [rax-1]
0x18000c66a  mov     r8, rax
0x18000c66d  dec     rax
0x18000c670  cmp     dl, 5Ch ; '\'
0x18000c673  jz      short loc_18000C67A
0x18000c675  cmp     rax, rcx
0x18000c678  ja      short loc_18000C666
0x18000c67a  cmp     dl, 5Ch ; '\'
0x18000c67d  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c684  mov     r9d, 23Ah
0x18000c68a  cmovz   rax, r8
0x18000c68e  jmp     loc_18000C723
0x18000c693  test    ebp, ebp
0x18000c695  jnz     short loc_18000C6AD
0x18000c697  test    r14d, r14d
0x18000c69a  jz      loc_18000C741
0x18000c6a0  mov     rax, [rsi]
0x18000c6a3  cmp     qword ptr [rax], 0
0x18000c6a7  jz      loc_18000C741
0x18000c6ad  mov     r9, [rbx]; error
0x18000c6b0  lea     r8, [rsp+0F8h+found]; found
0x18000c6b8  mov     rcx, [rbx+10h]; writer
0x18000c6bc  mov     edx, 7; moveTo
0x18000c6c1  call    cs:__imp_WsMoveWriter
0x18000c6c8  nop     dword ptr [rax+rax+00h]
0x18000c6cd  mov     edi, eax
0x18000c6cf  test    eax, eax
0x18000c6d1  jns     short loc_18000C6EE
0x18000c6d3  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c6da  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c6e1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c6e6  mov     r9d, 24Dh
0x18000c6ec  jmp     short loc_18000C723
0x18000c6ee  mov     r8, [rbx]; error
0x18000c6f1  mov     rdx, [rsi]; nodePosition
0x18000c6f4  mov     rcx, [rbx+10h]; writer
0x18000c6f8  call    cs:__imp_WsGetWriterPosition
0x18000c6ff  nop     dword ptr [rax+rax+00h]
0x18000c704  mov     edi, eax
0x18000c706  test    eax, eax
0x18000c708  jns     short loc_18000C741
0x18000c70a  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000c711  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000c718  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000c71d  mov     r9d, 25Ah
0x18000c723  mov     r8, rax
0x18000c726  mov     edx, edi
0x18000c728  mov     rcx, r10; char *
0x18000c72b  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000c730  mov     rcx, [rbx]; error
0x18000c733  test    rcx, rcx
0x18000c736  jz      short loc_18000C73D
0x18000c738  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x18000c73d  mov     eax, edi
0x18000c73f  jmp     short loc_18000C743
0x18000c741  xor     eax, eax
0x18000c743  add     rsp, 0C8h
0x18000c74a  pop     r15
0x18000c74c  pop     r14
0x18000c74e  pop     rdi
0x18000c74f  pop     rsi
0x18000c750  pop     rbp
0x18000c751  pop     rbx
0x18000c752  retn
```
