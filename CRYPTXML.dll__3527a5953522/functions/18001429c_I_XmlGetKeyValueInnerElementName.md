# I_XmlGetKeyValueInnerElementName

- ea: `0x18001429c`
- end: `0x180014589`
- name: `I_XmlGetKeyValueInnerElementName`
- size: `749`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012838`

## callees

- `0x1800070d0`
- `0x18001429c`
- `0x180014ce0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001450f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001450f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001451f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001451f`
- `webservices!WsCreateReader` at `0x1800142cd`
- `webservices!WsCreateReader` at `0x1800142cd`
- `webservices!WsReadNode` at `0x1800143f1`
- `webservices!WsReadNode` at `0x1800143f1`
- `webservices!WsReadToStartElement` at `0x1800143a7`
- `webservices!WsReadToStartElement` at `0x180014470`
- `webservices!WsReadToStartElement` at `0x1800143a7`
- `webservices!WsReadToStartElement` at `0x180014470`
- `webservices!WsGetReaderNode` at `0x1800143cc`
- `webservices!WsGetReaderNode` at `0x180014431`
- `webservices!WsGetReaderNode` at `0x1800144a4`
- `webservices!WsGetReaderNode` at `0x1800143cc`
- `webservices!WsGetReaderNode` at `0x180014431`
- `webservices!WsGetReaderNode` at `0x1800144a4`
- `webservices!WsFreeReader` at `0x180014565`
- `webservices!WsFreeReader` at `0x180014565`
- `webservices!WsSetInput` at `0x180014350`
- `webservices!WsSetInput` at `0x180014350`

## string_xrefs

- `0x1800142df`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180014362`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180014403`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18001441a`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180014443`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180014482`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800144b6`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800144dc`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18001453a`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlGetKeyValueInnerElementName(int *a1, WCHAR *a2, int *a3)
{
  int ReaderNode; // ebx
  const char *v7; // rax
  int v8; // r9d
  __int64 v9; // r8
  int v10; // eax
  signed int LastError; // eax
  WS_XML_READER *reader; // [rsp+30h] [rbp-30h] BYREF
  WS_XML_NODE *node; // [rsp+38h] [rbp-28h] BYREF
  WS_XML_READER_ENCODING encoding; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+44h] [rbp-1Ch]
  WS_XML_READER_INPUT input[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]
  int v19; // [rsp+58h] [rbp-8h]
  int v20; // [rsp+5Ch] [rbp-4h]
  BOOL found; // [rsp+98h] [rbp+38h] BYREF

  reader = 0;
  ReaderNode = WsCreateReader(0, 0, &reader, 0);
  if ( ReaderNode >= 0 )
  {
    v18 = *((_QWORD *)a1 + 1);
    v19 = a1[1];
    v16 = *a1;
    *(_QWORD *)&input[0].inputType = 1;
    v20 = 0;
    encoding.encodingType = WS_XML_READER_ENCODING_TYPE_TEXT;
    ReaderNode = WsSetInput(reader, &encoding, input, 0, 0, 0);
    if ( ReaderNode >= 0 )
    {
      found = 0;
      node = 0;
      while ( 1 )
      {
        if ( WsReadToStartElement(reader, &WS_XML_DIGSIG_KeyValue, &WS_XML_DIGSIG_NS, &found, 0) < 0 )
        {
LABEL_27:
          ReaderNode = 1;
          goto LABEL_28;
        }
        if ( found )
          break;
        ReaderNode = WsGetReaderNode(reader, (const WS_XML_NODE **)&node, 0);
        if ( ReaderNode < 0 )
        {
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
          v8 = 3135;
          goto LABEL_3;
        }
        if ( node->nodeType == WS_XML_NODE_TYPE_EOF )
          goto LABEL_27;
        ReaderNode = WsReadNode(reader, 0);
        if ( ReaderNode < 0 )
        {
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
          v8 = 3148;
          goto LABEL_3;
        }
      }
      ReaderNode = WsGetReaderNode(reader, (const WS_XML_NODE **)&node, 0);
      if ( ReaderNode < 0 )
      {
        v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 3062;
        goto LABEL_3;
      }
      ReaderNode = WsReadToStartElement(reader, 0, 0, &found, 0);
      if ( ReaderNode < 0 )
      {
        v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 3079;
        goto LABEL_3;
      }
      ReaderNode = WsGetReaderNode(reader, (const WS_XML_NODE **)&node, 0);
      if ( ReaderNode < 0 )
      {
        v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 3090;
        goto LABEL_3;
      }
      v9 = *(_QWORD *)&node[4].nodeType;
      if ( (unsigned int)*a3 < *(_DWORD *)v9 )
      {
        ReaderNode = -2147024662;
        v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 3098;
        goto LABEL_3;
      }
      v10 = MultiByteToWideChar(0xFDE9u, 0, *(LPCCH *)(v9 + 8), *(_DWORD *)v9, a2, *a3);
      if ( v10 )
      {
        *a3 = v10;
        ReaderNode = 0;
        goto LABEL_28;
      }
      LastError = GetLastError();
      ReaderNode = LastError;
      if ( LastError > 0 )
        ReaderNode = (unsigned __int16)LastError | 0x80070000;
      v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v8 = 3114;
    }
    else
    {
      v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v8 = 3030;
    }
  }
  else
  {
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v8 = 3006;
  }
LABEL_3:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", ReaderNode, v7, v8);
LABEL_28:
  if ( reader )
    WsFreeReader(reader);
  return (unsigned int)ReaderNode;
}

```

## disassembly

```asm
0x18001429c  mov     [rsp-18h+arg_0], rbx
0x1800142a1  mov     [rsp-18h+arg_8], rsi
0x1800142a6  push    rbp
0x1800142a7  push    rdi
0x1800142a8  push    r14
0x1800142aa  mov     rbp, rsp
0x1800142ad  sub     rsp, 60h
0x1800142b1  mov     rdi, r8
0x1800142b4  mov     [rbp+reader], 0
0x1800142bc  mov     r14, rdx
0x1800142bf  lea     r8, [rbp+reader]; reader
0x1800142c3  mov     rsi, rcx
0x1800142c6  xor     edx, edx; propertyCount
0x1800142c8  xor     ecx, ecx; properties
0x1800142ca  xor     r9d, r9d; error
0x1800142cd  call    cs:__imp_WsCreateReader
0x1800142d4  nop     dword ptr [rax+rax+00h]
0x1800142d9  mov     ebx, eax
0x1800142db  test    eax, eax
0x1800142dd  jns     short loc_180014307
0x1800142df  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800142e6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800142eb  mov     r9d, 0BBEh
0x1800142f1  mov     r8, rax
0x1800142f4  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800142fb  mov     edx, ebx
0x1800142fd  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180014302  jmp     loc_18001455C
0x180014307  mov     rax, [rsi+8]
0x18001430b  lea     r8, [rbp+input]; input
0x18001430f  mov     rcx, [rbp+reader]; reader
0x180014313  lea     rdx, [rbp+encoding]; encoding
0x180014317  mov     [rbp+var_10], rax
0x18001431b  xor     r9d, r9d; properties
0x18001431e  mov     eax, [rsi+4]
0x180014321  mov     [rbp+var_8], eax
0x180014324  mov     eax, [rsi]
0x180014326  mov     [rsp+60h+error], 0; error
0x18001432f  mov     [rbp+var_1C], eax
0x180014332  mov     qword ptr [rbp+input.inputType], 1
0x18001433a  mov     [rbp+var_4], 0
0x180014341  mov     [rbp+encoding.encodingType], 1
0x180014348  mov     [rsp+60h+propertyCount], 0; propertyCount
0x180014350  call    cs:__imp_WsSetInput
0x180014357  nop     dword ptr [rax+rax+00h]
0x18001435c  mov     ebx, eax
0x18001435e  test    eax, eax
0x180014360  jns     short loc_180014379
0x180014362  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014369  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001436e  mov     r9d, 0BD6h
0x180014374  jmp     loc_1800142F1
0x180014379  mov     [rbp+found], 0
0x180014380  mov     [rbp+node], 0
0x180014388  mov     rcx, [rbp+reader]; reader
0x18001438c  lea     r9, [rbp+found]; found
0x180014390  lea     r8, ?WS_XML_DIGSIG_NS@@3U_WS_XML_STRING@@B; ns
0x180014397  mov     qword ptr [rsp+60h+propertyCount], 0; error
0x1800143a0  lea     rdx, ?WS_XML_DIGSIG_KeyValue@@3U_WS_XML_STRING@@B; localName
0x1800143a7  call    cs:__imp_WsReadToStartElement
0x1800143ae  nop     dword ptr [rax+rax+00h]
0x1800143b3  test    eax, eax
0x1800143b5  js      loc_180014557
0x1800143bb  mov     rcx, [rbp+reader]; xmlReader
0x1800143bf  lea     rdx, [rbp+node]; node
0x1800143c3  xor     r8d, r8d; error
0x1800143c6  cmp     [rbp+found], r8d
0x1800143ca  jnz     short loc_180014431
0x1800143cc  call    cs:__imp_WsGetReaderNode
0x1800143d3  nop     dword ptr [rax+rax+00h]
0x1800143d8  mov     ebx, eax
0x1800143da  test    eax, eax
0x1800143dc  js      short loc_18001441A
0x1800143de  mov     rax, [rbp+node]
0x1800143e2  cmp     dword ptr [rax], 8
0x1800143e5  jz      loc_180014557
0x1800143eb  mov     rcx, [rbp+reader]; reader
0x1800143ef  xor     edx, edx; error
0x1800143f1  call    cs:__imp_WsReadNode
0x1800143f8  nop     dword ptr [rax+rax+00h]
0x1800143fd  mov     ebx, eax
0x1800143ff  test    eax, eax
0x180014401  jns     short loc_180014388
0x180014403  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001440a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001440f  mov     r9d, 0C4Ch
0x180014415  jmp     loc_1800142F1
0x18001441a  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014421  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014426  mov     r9d, 0C3Fh
0x18001442c  jmp     loc_1800142F1
0x180014431  call    cs:__imp_WsGetReaderNode
0x180014438  nop     dword ptr [rax+rax+00h]
0x18001443d  mov     ebx, eax
0x18001443f  test    eax, eax
0x180014441  jns     short loc_18001445A
0x180014443  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001444a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001444f  mov     r9d, 0BF6h
0x180014455  jmp     loc_1800142F1
0x18001445a  mov     rcx, [rbp+reader]; reader
0x18001445e  lea     r9, [rbp+found]; found
0x180014462  xor     r8d, r8d; ns
0x180014465  mov     qword ptr [rsp+60h+propertyCount], 0; error
0x18001446e  xor     edx, edx; localName
0x180014470  call    cs:__imp_WsReadToStartElement
0x180014477  nop     dword ptr [rax+rax+00h]
0x18001447c  mov     ebx, eax
0x18001447e  test    eax, eax
0x180014480  jns     short loc_180014499
0x180014482  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014489  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001448e  mov     r9d, 0C07h
0x180014494  jmp     loc_1800142F1
0x180014499  mov     rcx, [rbp+reader]; xmlReader
0x18001449d  lea     rdx, [rbp+node]; node
0x1800144a1  xor     r8d, r8d; error
0x1800144a4  call    cs:__imp_WsGetReaderNode
0x1800144ab  nop     dword ptr [rax+rax+00h]
0x1800144b0  mov     ebx, eax
0x1800144b2  test    eax, eax
0x1800144b4  jns     short loc_1800144CD
0x1800144b6  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800144bd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800144c2  mov     r9d, 0C12h
0x1800144c8  jmp     loc_1800142F1
0x1800144cd  mov     rax, [rbp+node]
0x1800144d1  mov     r8, [rax+10h]
0x1800144d5  mov     eax, [rdi]
0x1800144d7  cmp     eax, [r8]
0x1800144da  jnb     short loc_1800144F8
0x1800144dc  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800144e3  mov     ebx, 800700EAh
0x1800144e8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800144ed  mov     r9d, 0C1Ah
0x1800144f3  jmp     loc_1800142F1
0x1800144f8  mov     r9d, [r8]; cbMultiByte
0x1800144fb  xor     edx, edx; dwFlags
0x1800144fd  mov     r8, [r8+8]; lpMultiByteStr
0x180014501  mov     ecx, 0FDE9h; CodePage
0x180014506  mov     dword ptr [rsp+60h+error], eax; cchWideChar
0x18001450a  mov     qword ptr [rsp+60h+propertyCount], r14; lpWideCharStr
0x18001450f  call    cs:__imp_MultiByteToWideChar
0x180014516  nop     dword ptr [rax+rax+00h]
0x18001451b  test    eax, eax
0x18001451d  jnz     short loc_180014551
0x18001451f  call    cs:__imp_GetLastError
0x180014526  nop     dword ptr [rax+rax+00h]
0x18001452b  mov     ebx, eax
0x18001452d  test    eax, eax
0x18001452f  jle     short loc_18001453A
0x180014531  movzx   ebx, ax
0x180014534  or      ebx, 80070000h
0x18001453a  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180014541  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180014546  mov     r9d, 0C2Ah
0x18001454c  jmp     loc_1800142F1
0x180014551  mov     [rdi], eax
0x180014553  xor     ebx, ebx
0x180014555  jmp     short loc_18001455C
0x180014557  mov     ebx, 1
0x18001455c  mov     rcx, [rbp+reader]; reader
0x180014560  test    rcx, rcx
0x180014563  jz      short loc_180014571
0x180014565  call    cs:__imp_WsFreeReader
0x18001456c  nop     dword ptr [rax+rax+00h]
0x180014571  lea     r11, [rsp+60h+var_s0]
0x180014576  mov     eax, ebx
0x180014578  mov     rbx, [r11+20h]
0x18001457c  mov     rsi, [r11+28h]
0x180014580  mov     rsp, r11
0x180014583  pop     r14
0x180014585  pop     rdi
0x180014586  pop     rbp
0x180014587  retn
```
