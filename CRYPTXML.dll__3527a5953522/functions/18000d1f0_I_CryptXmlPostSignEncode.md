# I_CryptXmlPostSignEncode

- ea: `0x18000d1f0`
- end: `0x18000d4f2`
- name: `I_CryptXmlPostSignEncode`
- size: `770`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x18000d1f0`
- `0x180014ce0`
- `0x1800164cc`

## import_xrefs

- `webservices!WsSetOutputToBuffer` at `0x18000d3b5`
- `webservices!WsSetOutputToBuffer` at `0x18000d3b5`
- `webservices!WsWriteBytes` at `0x18000d447`
- `webservices!WsWriteBytes` at `0x18000d447`
- `webservices!WsReadNode` at `0x18000d2dd`
- `webservices!WsReadNode` at `0x18000d2dd`
- `webservices!WsReadToStartElement` at `0x18000d2b9`
- `webservices!WsReadToStartElement` at `0x18000d2b9`
- `webservices!WsMoveReader` at `0x18000d25c`
- `webservices!WsMoveReader` at `0x18000d25c`
- `webservices!WsSetWriterPosition` at `0x18000d3f4`
- `webservices!WsSetWriterPosition` at `0x18000d3f4`
- `webservices!WsGetReaderPosition` at `0x18000d36f`
- `webservices!WsGetReaderPosition` at `0x18000d36f`
- `webservices!WsSetReaderPosition` at `0x18000d225`
- `webservices!WsSetReaderPosition` at `0x18000d225`
- `webservices!WsReadStartElement` at `0x18000d330`
- `webservices!WsReadStartElement` at `0x18000d330`
- `webservices!WsWriteEndElement` at `0x18000d47b`
- `webservices!WsWriteEndElement` at `0x18000d47b`

## string_xrefs

- `0x18000d237`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d26e`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d2fc`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d342`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d381`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d3c7`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d406`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d459`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d48d`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000d4a8`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlPostSignEncode(__int64 a1)
{
  __int64 v1; // rbx
  const WS_XML_NODE_POSITION *v3; // rdx
  WS_XML_READER *v4; // rcx
  HRESULT started; // edi
  const char *v6; // rax
  const char *v7; // r10
  __int64 v8; // r9
  BOOL v9; // eax
  WS_ERROR *v10; // rdx
  WS_XML_READER *v11; // rcx
  char v12; // dl
  const char *v13; // r8
  __int64 v14; // rdx
  int v15; // edx
  BOOL found; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 152);
  found = 0;
  v3 = *(const WS_XML_NODE_POSITION **)(v1 + 72);
  v4 = *(WS_XML_READER **)(v1 + 8);
  if ( v3->buffer )
  {
    started = WsSetReaderPosition(v4, v3, *(WS_ERROR **)v1);
    if ( started < 0 )
    {
      v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v8 = 970;
      goto LABEL_31;
    }
  }
  else
  {
    started = WsMoveReader(v4, WS_MOVE_TO_ROOT_ELEMENT, &found, *(WS_ERROR **)v1);
    if ( started < 0 )
    {
      v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v8 = 984;
      goto LABEL_31;
    }
  }
  v9 = 0;
  for ( found = 0; ; v9 = found )
  {
    if ( v9 )
      return 0;
    started = WsReadToStartElement(
                *(WS_XML_READER **)(v1 + 8),
                &WS_XML_DIGSIG_SignatureValue,
                &WS_XML_DIGSIG_NS,
                &found,
                *(WS_ERROR **)v1);
    if ( started < 0 )
    {
      v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v8 = 1001;
      goto LABEL_31;
    }
    v10 = *(WS_ERROR **)v1;
    v11 = *(WS_XML_READER **)(v1 + 8);
    if ( found )
    {
      started = WsReadStartElement(v11, v10);
      if ( started < 0 )
      {
        v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 1013;
        goto LABEL_31;
      }
      started = WsGetReaderPosition(
                  *(WS_XML_READER **)(v1 + 8),
                  (WS_XML_NODE_POSITION *)(*(_QWORD *)(v1 + 72) + 16LL),
                  *(WS_ERROR **)v1);
      if ( started < 0 )
      {
        v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 1024;
        goto LABEL_31;
      }
      started = WsSetOutputToBuffer(*(WS_XML_WRITER **)(v1 + 16), *(WS_XML_BUFFER **)(v1 + 40), 0, 0, *(WS_ERROR **)v1);
      if ( started < 0 )
      {
        v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 1037;
        goto LABEL_31;
      }
      started = WsSetWriterPosition(
                  *(WS_XML_WRITER **)(v1 + 16),
                  (const WS_XML_NODE_POSITION *)(*(_QWORD *)(v1 + 72) + 16LL),
                  *(WS_ERROR **)v1);
      if ( started < 0 )
      {
        v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 1048;
        goto LABEL_31;
      }
      v14 = **(_QWORD **)(*(_QWORD *)(a1 + 136) + 32LL);
      started = WsWriteBytes(
                  *(WS_XML_WRITER **)(v1 + 16),
                  *(const void **)(v14 + 144),
                  *(_DWORD *)(v14 + 136),
                  *(WS_ERROR **)v1);
      if ( started < 0 )
      {
        v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 1060;
        goto LABEL_31;
      }
      started = WsWriteEndElement(*(WS_XML_WRITER **)(v1 + 16), *(WS_ERROR **)v1);
      if ( started < 0 )
      {
        v6 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v8 = 1070;
        goto LABEL_31;
      }
      return 0;
    }
    started = WsReadNode(v11, v10);
    if ( started < 0 )
      break;
  }
  v6 = "";
  do
  {
    v12 = *(v6 - 1);
    v13 = v6--;
  }
  while ( v12 != 92 && v6 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" );
  v7 = "ERROR  : (0x%08x) %s:%u";
  v8 = 1084;
  if ( v12 == 92 )
    v6 = v13;
LABEL_31:
  WPPTraceLogA(v7, (unsigned int)started, v6, v8);
  if ( *(_QWORD *)v1 )
    I_TraceWsError(*(struct _WS_ERROR **)v1, v15);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000d1f0  mov     [rsp+arg_8], rbx
0x18000d1f5  mov     [rsp+arg_10], rsi
0x18000d1fa  push    rdi
0x18000d1fb  sub     rsp, 30h
0x18000d1ff  mov     rbx, [rcx+98h]
0x18000d206  mov     rsi, rcx
0x18000d209  mov     [rsp+38h+found], 0
0x18000d211  mov     rdx, [rbx+48h]; nodePosition
0x18000d215  mov     r9, [rbx]; error
0x18000d218  mov     rcx, [rbx+8]; reader
0x18000d21c  cmp     qword ptr [rdx], 0
0x18000d220  jz      short loc_18000D255
0x18000d222  mov     r8, r9; error
0x18000d225  call    cs:__imp_WsSetReaderPosition
0x18000d22c  nop     dword ptr [rax+rax+00h]
0x18000d231  mov     edi, eax
0x18000d233  test    eax, eax
0x18000d235  jns     short loc_18000D28C
0x18000d237  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d23e  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d245  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d24a  mov     r9d, 3CAh
0x18000d250  jmp     loc_18000D4C1
0x18000d255  lea     r8, [rsp+38h+found]; found
0x18000d25a  xor     edx, edx; moveTo
0x18000d25c  call    cs:__imp_WsMoveReader
0x18000d263  nop     dword ptr [rax+rax+00h]
0x18000d268  mov     edi, eax
0x18000d26a  test    eax, eax
0x18000d26c  jns     short loc_18000D28C
0x18000d26e  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d275  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d27c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d281  mov     r9d, 3D8h
0x18000d287  jmp     loc_18000D4C1
0x18000d28c  xor     eax, eax
0x18000d28e  mov     [rsp+38h+found], eax
0x18000d292  test    eax, eax
0x18000d294  jnz     loc_18000D4DF
0x18000d29a  mov     rax, [rbx]
0x18000d29d  lea     r9, [rsp+38h+found]; found
0x18000d2a2  mov     rcx, [rbx+8]; reader
0x18000d2a6  lea     r8, ?WS_XML_DIGSIG_NS@@3U_WS_XML_STRING@@B; ns
0x18000d2ad  lea     rdx, ?WS_XML_DIGSIG_SignatureValue@@3U_WS_XML_STRING@@B; localName
0x18000d2b4  mov     [rsp+38h+error], rax; error
0x18000d2b9  call    cs:__imp_WsReadToStartElement
0x18000d2c0  nop     dword ptr [rax+rax+00h]
0x18000d2c5  mov     edi, eax
0x18000d2c7  test    eax, eax
0x18000d2c9  js      loc_18000D4A8
0x18000d2cf  cmp     [rsp+38h+found], 0
0x18000d2d4  mov     rdx, [rbx]; error
0x18000d2d7  mov     rcx, [rbx+8]; reader
0x18000d2db  jnz     short loc_18000D330
0x18000d2dd  call    cs:__imp_WsReadNode
0x18000d2e4  nop     dword ptr [rax+rax+00h]
0x18000d2e9  mov     edi, eax
0x18000d2eb  test    eax, eax
0x18000d2ed  js      short loc_18000D2F5
0x18000d2ef  mov     eax, [rsp+38h+found]
0x18000d2f3  jmp     short loc_18000D292
0x18000d2f5  lea     rax, aOnecoreDsSecur_5+30h; ""
0x18000d2fc  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d303  movzx   edx, byte ptr [rax-1]
0x18000d307  mov     r8, rax
0x18000d30a  dec     rax
0x18000d30d  cmp     dl, 5Ch ; '\'
0x18000d310  jz      short loc_18000D317
0x18000d312  cmp     rax, rcx
0x18000d315  ja      short loc_18000D303
0x18000d317  cmp     dl, 5Ch ; '\'
0x18000d31a  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d321  mov     r9d, 43Ch
0x18000d327  cmovz   rax, r8
0x18000d32b  jmp     loc_18000D4C1
0x18000d330  call    cs:__imp_WsReadStartElement
0x18000d337  nop     dword ptr [rax+rax+00h]
0x18000d33c  mov     edi, eax
0x18000d33e  test    eax, eax
0x18000d340  jns     short loc_18000D360
0x18000d342  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d349  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d350  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d355  mov     r9d, 3F5h
0x18000d35b  jmp     loc_18000D4C1
0x18000d360  mov     rdx, [rbx+48h]
0x18000d364  mov     r8, [rbx]; error
0x18000d367  add     rdx, 10h; nodePosition
0x18000d36b  mov     rcx, [rbx+8]; reader
0x18000d36f  call    cs:__imp_WsGetReaderPosition
0x18000d376  nop     dword ptr [rax+rax+00h]
0x18000d37b  mov     edi, eax
0x18000d37d  test    eax, eax
0x18000d37f  jns     short loc_18000D39F
0x18000d381  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d388  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d38f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d394  mov     r9d, 400h
0x18000d39a  jmp     loc_18000D4C1
0x18000d39f  mov     rax, [rbx]
0x18000d3a2  xor     r9d, r9d; propertyCount
0x18000d3a5  mov     rdx, [rbx+28h]; buffer
0x18000d3a9  xor     r8d, r8d; properties
0x18000d3ac  mov     rcx, [rbx+10h]; writer
0x18000d3b0  mov     [rsp+38h+error], rax; error
0x18000d3b5  call    cs:__imp_WsSetOutputToBuffer
0x18000d3bc  nop     dword ptr [rax+rax+00h]
0x18000d3c1  mov     edi, eax
0x18000d3c3  test    eax, eax
0x18000d3c5  jns     short loc_18000D3E5
0x18000d3c7  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d3ce  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d3d5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d3da  mov     r9d, 40Dh
0x18000d3e0  jmp     loc_18000D4C1
0x18000d3e5  mov     rdx, [rbx+48h]
0x18000d3e9  mov     r8, [rbx]; error
0x18000d3ec  add     rdx, 10h; nodePosition
0x18000d3f0  mov     rcx, [rbx+10h]; writer
0x18000d3f4  call    cs:__imp_WsSetWriterPosition
0x18000d3fb  nop     dword ptr [rax+rax+00h]
0x18000d400  mov     edi, eax
0x18000d402  test    eax, eax
0x18000d404  jns     short loc_18000D424
0x18000d406  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d40d  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d414  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d419  mov     r9d, 418h
0x18000d41f  jmp     loc_18000D4C1
0x18000d424  mov     rax, [rsi+88h]
0x18000d42b  mov     r9, [rbx]; error
0x18000d42e  mov     rcx, [rax+20h]
0x18000d432  mov     rdx, [rcx]
0x18000d435  mov     rcx, [rbx+10h]; writer
0x18000d439  mov     r8d, [rdx+88h]; byteCount
0x18000d440  mov     rdx, [rdx+90h]; bytes
0x18000d447  call    cs:__imp_WsWriteBytes
0x18000d44e  nop     dword ptr [rax+rax+00h]
0x18000d453  mov     edi, eax
0x18000d455  test    eax, eax
0x18000d457  jns     short loc_18000D474
0x18000d459  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d460  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d467  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d46c  mov     r9d, 424h
0x18000d472  jmp     short loc_18000D4C1
0x18000d474  mov     rdx, [rbx]; error
0x18000d477  mov     rcx, [rbx+10h]; writer
0x18000d47b  call    cs:__imp_WsWriteEndElement
0x18000d482  nop     dword ptr [rax+rax+00h]
0x18000d487  mov     edi, eax
0x18000d489  test    eax, eax
0x18000d48b  jns     short loc_18000D4DF
0x18000d48d  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d494  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d49b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d4a0  mov     r9d, 42Eh
0x18000d4a6  jmp     short loc_18000D4C1
0x18000d4a8  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000d4af  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000d4b6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000d4bb  mov     r9d, 3E9h
0x18000d4c1  mov     r8, rax
0x18000d4c4  mov     edx, edi
0x18000d4c6  mov     rcx, r10; char *
0x18000d4c9  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000d4ce  mov     rcx, [rbx]; error
0x18000d4d1  test    rcx, rcx
0x18000d4d4  jz      short loc_18000D4DB
0x18000d4d6  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x18000d4db  mov     eax, edi
0x18000d4dd  jmp     short loc_18000D4E1
0x18000d4df  xor     eax, eax
0x18000d4e1  mov     rbx, [rsp+38h+arg_8]
0x18000d4e6  mov     rsi, [rsp+38h+arg_10]
0x18000d4eb  add     rsp, 30h
0x18000d4ef  pop     rdi
0x18000d4f0  retn
```
