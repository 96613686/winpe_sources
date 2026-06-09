# I_XmlEncodeInnerKeyValue

- ea: `0x180016564`
- end: `0x180016817`
- name: `I_XmlEncodeInnerKeyValue`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016c38`

## callees

- `0x1800070d0`
- `0x180011a40`
- `0x180014ce0`
- `0x180016564`
- `0x180018625`

## import_xrefs

- `webservices!WsCopyNode` at `0x18001677c`
- `webservices!WsCopyNode` at `0x18001677c`
- `webservices!WsFlushWriter` at `0x1800167ae`
- `webservices!WsFlushWriter` at `0x1800167ae`
- `webservices!WsWriteElement` at `0x1800166d2`
- `webservices!WsWriteElement` at `0x1800166d2`
- `webservices!WsGetReaderNode` at `0x180016750`
- `webservices!WsGetReaderNode` at `0x180016750`
- `webservices!WsSetOutput` at `0x180016640`
- `webservices!WsSetOutput` at `0x180016640`
- `webservices!WsSetInputToBuffer` at `0x180016712`
- `webservices!WsSetInputToBuffer` at `0x180016712`

## string_xrefs

- `0x1800165d1`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180016652`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800166e8`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180016724`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18001678e`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800167c0`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800167d8`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 I_XmlEncodeInnerKeyValue(int a1, const struct _CRYPT_XML_KEY_VALUE *a2, __int64 a3, ...)
{
  WS_ERROR *error; // rdi
  HRESULT ReaderNode; // ebx
  const char *v8; // rax
  int v9; // r9d
  const WS_ELEMENT_DESCRIPTION *v10; // rdx
  ULONG v11; // eax
  WS_XML_BUFFER **v12; // r9
  WS_XML_NODE *node; // [rsp+48h] [rbp-99h] BYREF
  WS_XML_WRITER_OUTPUT output[2]; // [rsp+50h] [rbp-91h] BYREF
  HRESULT (__stdcall *v16)(void *, const WS_BYTES *, ULONG, const WS_ASYNC_CONTEXT *, WS_ERROR *); // [rsp+58h] [rbp-89h]
  _QWORD *v17; // [rsp+60h] [rbp-81h]
  _QWORD v18[2]; // [rsp+68h] [rbp-79h] BYREF
  int v19; // [rsp+78h] [rbp-69h] BYREF
  WS_XML_BUFFER *value[17]; // [rsp+80h] [rbp-61h] BYREF
  __int64 encoding; // [rsp+140h] [rbp+5Fh] BYREF
  va_list encodinga; // [rsp+140h] [rbp+5Fh]
  WS_XML_READER *reader; // [rsp+148h] [rbp+67h]
  WS_XML_WRITER *writer; // [rsp+150h] [rbp+6Fh]
  struct _WS_HEAP *v25; // [rsp+158h] [rbp+77h]
  WS_ERROR *v26; // [rsp+160h] [rbp+7Fh]
  va_list va1; // [rsp+168h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(encodinga, a3);
  encoding = va_arg(va1, _QWORD);
  reader = va_arg(va1, WS_XML_READER *);
  writer = va_arg(va1, WS_XML_WRITER *);
  v25 = va_arg(va1, struct _WS_HEAP *);
  v26 = va_arg(va1, WS_ERROR *);
  memset_0(&v19, 0, 0x88u);
  error = v26;
  ReaderNode = I_XmlMarshallKeyValue(a2, reader, writer, v25, v26, 0, (struct WS_TYPE_KeyValue *)&v19);
  if ( ReaderNode < 0 )
  {
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v9 = 2565;
LABEL_26:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", ReaderNode, v8, v9);
    return (unsigned int)ReaderNode;
  }
  v18[1] = &CRYPT_XML_ENCODE_ALGORITHM_CALLBACK;
  v18[0] = a3;
  v16 = WS_TO_CRYPTXML_WRITE_CALLBACK;
  v17 = v18;
  *(_QWORD *)&output[0].outputType = 2;
  LODWORD(encoding) = 1;
  HIDWORD(encoding) = a1;
  ReaderNode = WsSetOutput(writer, (const WS_XML_WRITER_ENCODING *)encodinga, output, 0, 0, error);
  if ( ReaderNode < 0 )
  {
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v9 = 2593;
    goto LABEL_26;
  }
  switch ( v19 )
  {
    case 1:
      v10 = &DSAKeyValue_ElementDescription;
      v11 = 112;
      v12 = value;
      break;
    case 2:
      v10 = &RSAKeyValue_ElementDescription;
      v11 = 32;
      v12 = value;
      break;
    case 3:
      v10 = &ECDSAKeyValue_ElementDescription;
      v11 = 72;
      v12 = value;
      break;
    case 4:
      ReaderNode = WsSetInputToBuffer(reader, value[0], 0, 0, error);
      if ( ReaderNode >= 0 )
      {
        while ( 1 )
        {
          node = 0;
          ReaderNode = WsGetReaderNode(reader, (const WS_XML_NODE **)&node, error);
          if ( ReaderNode < 0 )
            break;
          if ( node->nodeType == WS_XML_NODE_TYPE_END_ELEMENT || node->nodeType == WS_XML_NODE_TYPE_EOF )
            goto LABEL_22;
          ReaderNode = WsCopyNode(writer, reader, error);
          if ( ReaderNode < 0 )
          {
            v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
            v9 = 2680;
            goto LABEL_26;
          }
        }
        v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v9 = 2663;
      }
      else
      {
        v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
        v9 = 2649;
      }
      goto LABEL_26;
    default:
      v10 = 0;
      v11 = 0;
      v12 = 0;
      break;
  }
  ReaderNode = WsWriteElement(writer, v10, WS_WRITE_REQUIRED_VALUE, v12, v11, error);
  if ( ReaderNode < 0 )
  {
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v9 = 2634;
    goto LABEL_26;
  }
LABEL_22:
  ReaderNode = WsFlushWriter(writer, 0, 0, error);
  if ( ReaderNode < 0 )
  {
    v8 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v9 = 2698;
    goto LABEL_26;
  }
  return 0;
}

```

## disassembly

```asm
0x180016564  mov     rax, rsp
0x180016567  mov     [rax+8], rbx
0x18001656b  mov     [rax+10h], rdi
0x18001656f  mov     [rax+20h], r9
0x180016573  push    rbp
0x180016574  push    r12
0x180016576  push    r15
0x180016578  lea     rbp, [rax-3Fh]
0x18001657c  sub     rsp, 100h
0x180016583  mov     r15, r8
0x180016586  mov     rbx, rdx
0x180016589  mov     r12d, ecx
0x18001658c  xor     edx, edx; Val
0x18001658e  mov     r8d, 88h; Size
0x180016594  lea     rcx, [rbp+37h+var_A0]; void *
0x180016598  call    memset_0
0x18001659d  mov     rdi, [rbp+37h+arg_38]
0x1800165a1  lea     rax, [rbp+37h+var_A0]
0x1800165a5  mov     r9, [rbp+37h+arg_30]; struct _WS_HEAP *
0x1800165a9  mov     rcx, rbx; struct _CRYPT_XML_KEY_VALUE *
0x1800165ac  mov     r8, [rbp+37h+writer]; struct _WS_XML_WRITER *
0x1800165b0  mov     rdx, [rbp+37h+reader]; struct _WS_XML_READER *
0x1800165b4  mov     [rsp+110h+var_E0], rax; struct WS_TYPE_KeyValue *
0x1800165b9  mov     dword ptr [rsp+110h+error], 0; int
0x1800165c1  mov     qword ptr [rsp+110h+propertyCount], rdi; struct _WS_ERROR *
0x1800165c6  call    ?I_XmlMarshallKeyValue@@YAJPEBU_CRYPT_XML_KEY_VALUE@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@HPEAUWS_TYPE_KeyValue@@@Z; I_XmlMarshallKeyValue(_CRYPT_XML_KEY_VALUE const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,int,WS_TYPE_KeyValue *)
0x1800165cb  mov     ebx, eax
0x1800165cd  test    eax, eax
0x1800165cf  jns     short loc_1800165E8
0x1800165d1  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800165d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800165dd  mov     r9d, 0A05h
0x1800165e3  jmp     loc_1800167EA
0x1800165e8  mov     rcx, [rbp+37h+writer]; writer
0x1800165ec  lea     rax, CRYPT_XML_ENCODE_ALGORITHM_CALLBACK
0x1800165f3  mov     [rbp+37h+var_A8], rax
0x1800165f7  lea     r8, [rsp+110h+output]; output
0x1800165fc  lea     rax, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; WS_TO_CRYPTXML_WRITE_CALLBACK(void *,_WS_BYTES const *,ulong,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)
0x180016603  mov     [rbp+37h+var_B0], r15
0x180016607  mov     [rsp+110h+var_C0], rax
0x18001660c  lea     rdx, [rbp+37h+encoding]; encoding
0x180016610  lea     rax, [rbp+37h+var_B0]
0x180016614  mov     [rsp+110h+error], rdi; error
0x180016619  mov     r15d, 1
0x18001661f  mov     [rsp+110h+var_B8], rax
0x180016624  xor     r9d, r9d; properties
0x180016627  mov     qword ptr [rsp+110h+output.outputType], 2
0x180016630  mov     dword ptr [rbp+37h+encoding], r15d
0x180016634  mov     dword ptr [rbp+37h+encoding+4], r12d
0x180016638  mov     [rsp+110h+propertyCount], 0; propertyCount
0x180016640  call    cs:__imp_WsSetOutput
0x180016647  nop     dword ptr [rax+rax+00h]
0x18001664c  mov     ebx, eax
0x18001664e  test    eax, eax
0x180016650  jns     short loc_180016669
0x180016652  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016659  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001665e  mov     r9d, 0A21h
0x180016664  jmp     loc_1800167EA
0x180016669  mov     r8d, [rbp+37h+var_A0]
0x18001666d  mov     ecx, r8d
0x180016670  sub     ecx, r15d
0x180016673  jz      short loc_1800166AC
0x180016675  sub     ecx, r15d
0x180016678  jz      short loc_18001669A
0x18001667a  cmp     ecx, r15d
0x18001667d  jz      short loc_180016688
0x18001667f  xor     edx, edx
0x180016681  xor     eax, eax
0x180016683  xor     r9d, r9d
0x180016686  jmp     short loc_1800166BC
0x180016688  lea     rdx, ?ECDSAKeyValue_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; _WS_ELEMENT_DESCRIPTION const ECDSAKeyValue_ElementDescription
0x18001668f  mov     eax, 48h ; 'H'
0x180016694  lea     r9, [rbp+37h+value]
0x180016698  jmp     short loc_1800166C2
0x18001669a  lea     rdx, ?RSAKeyValue_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; _WS_ELEMENT_DESCRIPTION const RSAKeyValue_ElementDescription
0x1800166a1  mov     eax, 20h ; ' '
0x1800166a6  lea     r9, [rbp+37h+value]
0x1800166aa  jmp     short loc_1800166C2
0x1800166ac  lea     rdx, ?DSAKeyValue_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; elementDescription
0x1800166b3  mov     eax, 70h ; 'p'
0x1800166b8  lea     r9, [rbp+37h+value]; value
0x1800166bc  cmp     r8d, 4
0x1800166c0  jz      short loc_1800166FF
0x1800166c2  mov     rcx, [rbp+37h+writer]; writer
0x1800166c6  mov     r8d, r15d; writeOption
0x1800166c9  mov     [rsp+110h+error], rdi; error
0x1800166ce  mov     [rsp+110h+propertyCount], eax; valueSize
0x1800166d2  call    cs:__imp_WsWriteElement
0x1800166d9  nop     dword ptr [rax+rax+00h]
0x1800166de  mov     ebx, eax
0x1800166e0  test    eax, eax
0x1800166e2  jns     loc_1800167A2
0x1800166e8  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800166ef  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800166f4  mov     r9d, 0A4Ah
0x1800166fa  jmp     loc_1800167EA
0x1800166ff  mov     rdx, [rbp+37h+value]; buffer
0x180016703  xor     r9d, r9d; propertyCount
0x180016706  mov     rcx, [rbp+37h+reader]; reader
0x18001670a  xor     r8d, r8d; properties
0x18001670d  mov     qword ptr [rsp+110h+propertyCount], rdi; error
0x180016712  call    cs:__imp_WsSetInputToBuffer
0x180016719  nop     dword ptr [rax+rax+00h]
0x18001671e  mov     ebx, eax
0x180016720  test    eax, eax
0x180016722  jns     short loc_18001673B
0x180016724  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001672b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016730  mov     r9d, 0A59h
0x180016736  jmp     loc_1800167EA
0x18001673b  mov     rcx, [rbp+37h+reader]; xmlReader
0x18001673f  lea     rdx, [rsp+110h+node]; node
0x180016744  mov     r8, rdi; error
0x180016747  mov     [rsp+110h+node], 0
0x180016750  call    cs:__imp_WsGetReaderNode
0x180016757  nop     dword ptr [rax+rax+00h]
0x18001675c  mov     ebx, eax
0x18001675e  test    eax, eax
0x180016760  js      short loc_1800167D8
0x180016762  mov     rax, [rsp+110h+node]
0x180016767  cmp     dword ptr [rax], 3
0x18001676a  jz      short loc_1800167A2
0x18001676c  cmp     dword ptr [rax], 8
0x18001676f  jz      short loc_1800167A2
0x180016771  mov     rdx, [rbp+37h+reader]; reader
0x180016775  mov     r8, rdi; error
0x180016778  mov     rcx, [rbp+37h+writer]; writer
0x18001677c  call    cs:__imp_WsCopyNode
0x180016783  nop     dword ptr [rax+rax+00h]
0x180016788  mov     ebx, eax
0x18001678a  test    eax, eax
0x18001678c  jns     short loc_18001673B
0x18001678e  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016795  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001679a  mov     r9d, 0A78h
0x1800167a0  jmp     short loc_1800167EA
0x1800167a2  mov     rcx, [rbp+37h+writer]; writer
0x1800167a6  mov     r9, rdi; error
0x1800167a9  xor     r8d, r8d; asyncContext
0x1800167ac  xor     edx, edx; minSize
0x1800167ae  call    cs:__imp_WsFlushWriter
0x1800167b5  nop     dword ptr [rax+rax+00h]
0x1800167ba  mov     ebx, eax
0x1800167bc  test    eax, eax
0x1800167be  jns     short loc_1800167D4
0x1800167c0  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800167c7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800167cc  mov     r9d, 0A8Ah
0x1800167d2  jmp     short loc_1800167EA
0x1800167d4  xor     ebx, ebx
0x1800167d6  jmp     short loc_1800167FB
0x1800167d8  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800167df  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800167e4  mov     r9d, 0A67h
0x1800167ea  mov     r8, rax
0x1800167ed  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800167f4  mov     edx, ebx
0x1800167f6  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800167fb  lea     r11, [rsp+110h+var_10]
0x180016803  mov     eax, ebx
0x180016805  mov     rbx, [r11+20h]
0x180016809  mov     rdi, [r11+28h]
0x18001680d  mov     rsp, r11
0x180016810  pop     r15
0x180016812  pop     r12
0x180016814  pop     rbp
0x180016815  retn
```
