# I_XmlEncodeFromBuffer

- ea: `0x1800109c0`
- end: `0x180010bbf`
- name: `I_XmlEncodeFromBuffer`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012600`

## callees

- `0x1800070d0`
- `0x1800109c0`
- `0x180014ce0`

## import_xrefs

- `webservices!WsCopyNode` at `0x180010aec`
- `webservices!WsCopyNode` at `0x180010aec`
- `webservices!WsFlushWriter` at `0x180010b24`
- `webservices!WsFlushWriter` at `0x180010b24`
- `webservices!WsGetReaderNode` at `0x180010ab7`
- `webservices!WsGetReaderNode` at `0x180010ab7`
- `webservices!WsSetOutput` at `0x180010a2f`
- `webservices!WsSetOutput` at `0x180010a2f`
- `webservices!WsSetInputToBuffer` at `0x180010a71`
- `webservices!WsSetInputToBuffer` at `0x180010a71`

## string_xrefs

- `0x180010a41`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180010a83`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180010afe`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180010b36`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180010b77`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlEncodeFromBuffer(
        int a1,
        const WS_XML_WRITER_PROPERTY *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        WS_XML_NODE *node)
{
  WS_ERROR **v6; // rbx
  WS_ERROR *v7; // rax
  WS_XML_WRITER *v8; // rcx
  HRESULT ReaderNode; // edi
  const char *v10; // r8
  int v11; // r9d
  WS_ERROR *v12; // r8
  WS_XML_READER *v13; // rcx
  HRESULT v14; // ebx
  const char *v15; // rax
  char v17; // al
  const char *v18; // rdx
  bool v19; // zf
  _QWORD v20[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v21[5]; // [rsp+40h] [rbp-28h] BYREF

  v6 = (WS_ERROR **)node;
  v20[1] = a5;
  v21[1] = WS_TO_CRYPTXML_WRITE_CALLBACK;
  v21[2] = v20;
  v7 = *(WS_ERROR **)&node->nodeType;
  v20[0] = a4;
  HIDWORD(a5) = a1;
  v8 = *(WS_XML_WRITER **)&node[4].nodeType;
  v21[0] = 2;
  LODWORD(a5) = 1;
  ReaderNode = WsSetOutput(v8, (const WS_XML_WRITER_ENCODING *)&a5, (const WS_XML_WRITER_OUTPUT *)v21, a2, 2u, v7);
  if ( ReaderNode >= 0 )
  {
    ReaderNode = WsSetInputToBuffer(v6[1], v6[5], 0, 0, *v6);
    if ( ReaderNode >= 0 )
    {
      while ( 1 )
      {
        v12 = *v6;
        v13 = v6[1];
        node = 0;
        ReaderNode = WsGetReaderNode(v13, (const WS_XML_NODE **)&node, v12);
        if ( ReaderNode < 0 )
          break;
        if ( node->nodeType == WS_XML_NODE_TYPE_END_ELEMENT || node->nodeType == WS_XML_NODE_TYPE_EOF )
        {
          v14 = WsFlushWriter(v6[2], 0, 0, *v6);
          if ( v14 >= 0 )
            return 0;
          v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v14, v15, 2516);
          return (unsigned int)v14;
        }
        ReaderNode = WsCopyNode(v6[2], v6[1], *v6);
        if ( ReaderNode < 0 )
        {
          v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
          v11 = 2499;
          goto LABEL_20;
        }
      }
      v10 = "";
      while ( 1 )
      {
        v17 = *(v10 - 1);
        v18 = v10--;
        v19 = v17 == 92;
        if ( v17 == 92 )
          break;
        if ( v10 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
        {
          v19 = v17 == 92;
          break;
        }
      }
      if ( v19 )
        v10 = v18;
      v11 = 2482;
    }
    else
    {
      v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v11 = 2464;
    }
  }
  else
  {
    v10 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v11 = 2446;
  }
LABEL_20:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", ReaderNode, v10, v11);
  return (unsigned int)ReaderNode;
}

```

## disassembly

```asm
0x1800109c0  mov     r11, rsp
0x1800109c3  mov     [r11+8], rbx
0x1800109c7  mov     [r11+10h], rsi
0x1800109cb  push    rdi
0x1800109cc  sub     rsp, 60h
0x1800109d0  mov     rax, [rsp+68h+arg_20]
0x1800109d8  lea     r8, [r11-28h]; output
0x1800109dc  mov     rbx, [rsp+68h+node]
0x1800109e4  xor     esi, esi
0x1800109e6  mov     [r11-30h], rax
0x1800109ea  lea     rax, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; WS_TO_CRYPTXML_WRITE_CALLBACK(void *,_WS_BYTES const *,ulong,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)
0x1800109f1  mov     [r11-20h], rax
0x1800109f5  lea     rax, [r11-38h]
0x1800109f9  mov     [r11-18h], rax
0x1800109fd  mov     rax, [rbx]
0x180010a00  mov     [r11-38h], r9
0x180010a04  mov     r9, rdx; properties
0x180010a07  mov     [r11+2Ch], ecx
0x180010a0b  lea     rdx, [r11+28h]; encoding
0x180010a0f  mov     rcx, [rbx+10h]; writer
0x180010a13  mov     [r11-40h], rax
0x180010a17  mov     [rsp+68h+propertyCount], 2; propertyCount
0x180010a1f  mov     qword ptr [r11-28h], 2
0x180010a27  mov     dword ptr [r11+28h], 1
0x180010a2f  call    cs:__imp_WsSetOutput
0x180010a36  nop     dword ptr [rax+rax+00h]
0x180010a3b  mov     edi, eax
0x180010a3d  test    eax, eax
0x180010a3f  jns     short loc_180010A5B
0x180010a41  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010a48  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010a4d  mov     r8, rax
0x180010a50  mov     r9d, 98Eh
0x180010a56  jmp     loc_180010B9E
0x180010a5b  mov     rax, [rbx]
0x180010a5e  xor     r9d, r9d; propertyCount
0x180010a61  mov     rdx, [rbx+28h]; buffer
0x180010a65  xor     r8d, r8d; properties
0x180010a68  mov     rcx, [rbx+8]; reader
0x180010a6c  mov     qword ptr [rsp+68h+propertyCount], rax; error
0x180010a71  call    cs:__imp_WsSetInputToBuffer
0x180010a78  nop     dword ptr [rax+rax+00h]
0x180010a7d  mov     edi, eax
0x180010a7f  test    eax, eax
0x180010a81  jns     short loc_180010AA0
0x180010a83  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010a8a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010a8f  mov     r8, rax
0x180010a92  mov     r9d, 9A0h
0x180010a98  jmp     loc_180010B9E
0x180010aa0  mov     r8, [rbx]; error
0x180010aa3  lea     rdx, [rsp+68h+node]; node
0x180010aab  mov     rcx, [rbx+8]; xmlReader
0x180010aaf  mov     [rsp+68h+node], rsi
0x180010ab7  call    cs:__imp_WsGetReaderNode
0x180010abe  nop     dword ptr [rax+rax+00h]
0x180010ac3  mov     edi, eax
0x180010ac5  test    eax, eax
0x180010ac7  js      loc_180010B70
0x180010acd  mov     rax, [rsp+68h+node]
0x180010ad5  mov     ecx, [rax]
0x180010ad7  cmp     ecx, 3
0x180010ada  jz      short loc_180010B18
0x180010adc  cmp     ecx, 8
0x180010adf  jz      short loc_180010B18
0x180010ae1  mov     r8, [rbx]; error
0x180010ae4  mov     rdx, [rbx+8]; reader
0x180010ae8  mov     rcx, [rbx+10h]; writer
0x180010aec  call    cs:__imp_WsCopyNode
0x180010af3  nop     dword ptr [rax+rax+00h]
0x180010af8  mov     edi, eax
0x180010afa  test    eax, eax
0x180010afc  jns     short loc_180010AA0
0x180010afe  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010b05  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010b0a  mov     r8, rax
0x180010b0d  mov     r9d, 9C3h
0x180010b13  jmp     loc_180010B9E
0x180010b18  mov     r9, [rbx]; error
0x180010b1b  xor     r8d, r8d; asyncContext
0x180010b1e  mov     rcx, [rbx+10h]; writer
0x180010b22  xor     edx, edx; minSize
0x180010b24  call    cs:__imp_WsFlushWriter
0x180010b2b  nop     dword ptr [rax+rax+00h]
0x180010b30  mov     ebx, eax
0x180010b32  test    eax, eax
0x180010b34  jns     short loc_180010B5D
0x180010b36  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010b3d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180010b42  mov     r8, rax
0x180010b45  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180010b4c  mov     edx, ebx
0x180010b4e  mov     r9d, 9D4h
0x180010b54  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180010b59  mov     eax, ebx
0x180010b5b  jmp     short loc_180010BAE
0x180010b5d  mov     eax, esi
0x180010b5f  mov     rbx, [rsp+68h+arg_0]
0x180010b64  mov     rsi, [rsp+68h+arg_8]
0x180010b69  add     rsp, 60h
0x180010b6d  pop     rdi
0x180010b6e  retn
0x180010b70  lea     r8, aOnecoreDsSecur_5+30h; ""
0x180010b77  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180010b7e  movzx   eax, byte ptr [r8-1]
0x180010b83  mov     rdx, r8
0x180010b86  dec     r8
0x180010b89  cmp     al, 5Ch ; '\'
0x180010b8b  jz      short loc_180010B94
0x180010b8d  cmp     r8, rcx
0x180010b90  ja      short loc_180010B7E
0x180010b92  cmp     al, 5Ch ; '\'
0x180010b94  cmovz   r8, rdx
0x180010b98  mov     r9d, 9B2h
0x180010b9e  mov     edx, edi
0x180010ba0  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180010ba7  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180010bac  mov     eax, edi
0x180010bae  mov     rbx, [rsp+68h+arg_0]
0x180010bb3  mov     rsi, [rsp+68h+arg_8]
0x180010bb8  add     rsp, 60h
0x180010bbc  pop     rdi
0x180010bbd  retn
```
