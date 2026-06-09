# I_CryptXmlDecodeObject

- ea: `0x180016a0c`
- end: `0x180016c2f`
- name: `I_CryptXmlDecodeObject`
- size: `547`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015ea0`

## callees

- `0x180001a40`
- `0x180004f60`
- `0x1800070d0`
- `0x180011040`
- `0x180014ce0`
- `0x1800164cc`
- `0x180016a0c`
- `0x180017224`

## import_xrefs

- `webservices!WsGetReaderProperty` at `0x180016b11`
- `webservices!WsGetReaderProperty` at `0x180016b11`
- `webservices!WsReadElement` at `0x180016b5c`
- `webservices!WsReadElement` at `0x180016b5c`
- `webservices!WsSetInput` at `0x180016ad7`
- `webservices!WsSetInput` at `0x180016ad7`

## string_xrefs

- `0x180016bca`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlDecodeObject(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        struct _CRYPT_XML_OBJECT **a5)
{
  struct _CRYPT_XML_OBJECT **v5; // r14
  WS_ERROR **v6; // rsi
  struct _CRYPT_XML_OBJECT *v10; // rdi
  unsigned int v11; // r12d
  HRESULT ReaderProperty; // ebx
  int v13; // eax
  const char *v14; // rax
  const char *v15; // r10
  int v16; // edx
  struct WS_TYPE_Object *v18; // [rsp+40h] [rbp-20h] BYREF
  WS_XML_READER_INPUT input[4]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v20; // [rsp+58h] [rbp-8h]
  __int64 encoding; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v22; // [rsp+B0h] [rbp+50h] BYREF
  struct _CRYPT_XML_OBJECT *v23; // [rsp+B8h] [rbp+58h] BYREF

  v22 = a3;
  v5 = a5;
  v6 = *(WS_ERROR ***)(a1 + 152);
  v20 = 0;
  encoding = 0;
  v18 = 0;
  v23 = 0;
  v10 = 0;
  v22 = 0;
  *(_OWORD *)&input[0].inputType = 0;
  if ( a5 )
    *a5 = 0;
  I_GetProperty(1, *(_QWORD *)(a1 + 168), *(unsigned int *)(a1 + 176), &v22, 4);
  v11 = v22;
  *(_QWORD *)&input[0].inputType = 1;
  HIDWORD(v20) = 0;
  if ( !v22 )
    v11 = 2147483640;
  LODWORD(encoding) = 1;
  HIDWORD(encoding) = *(_DWORD *)a4;
  *(_QWORD *)&input[2].inputType = *(_QWORD *)(a4 + 8);
  LODWORD(v20) = *(_DWORD *)(a4 + 4);
  ReaderProperty = WsSetInput(v6[1], (const WS_XML_READER_ENCODING *)&encoding, input, 0, 0, *v6);
  if ( ReaderProperty >= 0
    && (HIDWORD(encoding)
     || (ReaderProperty = WsGetReaderProperty(v6[1], WS_XML_READER_PROPERTY_CHARSET, (char *)&encoding + 4, 4u, *v6),
         ReaderProperty >= 0))
    && (ReaderProperty = WsReadElement(
                           v6[1],
                           &Object_ElementDescription,
                           WS_READ_REQUIRED_POINTER,
                           v6[6],
                           &v18,
                           8u,
                           *v6),
        ReaderProperty >= 0)
    && (v13 = I_XmlUnmarshallObject(
                *(HANDLE *)(a2 + 48),
                *(_DWORD *)(a1 + 60),
                SHIDWORD(encoding),
                v11,
                v18,
                (struct _CRYPT_XML_WS_STATE *)v6,
                (const struct _CRYPT_XML_OBJECT **)&v23),
        v10 = v23,
        ReaderProperty = v13,
        v13 >= 0)
    && (ReaderProperty = I_CryptXmlSignatureAddObject(a2, v23), ReaderProperty >= 0) )
  {
    if ( v5 )
      *v5 = v10;
    ReaderProperty = 0;
  }
  else
  {
    v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    WPPTraceLogA(v15, (unsigned int)ReaderProperty, v14);
    if ( *v6 )
      I_TraceWsError(*v6, v16);
  }
  if ( v10 )
    I_CryptXmlRelease(v10->hObject);
  return (unsigned int)ReaderProperty;
}

```

## disassembly

```asm
0x180016a0c  mov     [rsp-38h+arg_8], rbx
0x180016a11  mov     [rsp-38h+arg_10], r8d
0x180016a16  push    rbp
0x180016a17  push    rsi
0x180016a18  push    rdi
0x180016a19  push    r12
0x180016a1b  push    r13
0x180016a1d  push    r14
0x180016a1f  push    r15
0x180016a21  mov     rbp, rsp
0x180016a24  sub     rsp, 60h
0x180016a28  mov     r14, [rbp+arg_20]
0x180016a2c  xor     eax, eax
0x180016a2e  mov     rsi, [rcx+98h]
0x180016a35  xorps   xmm0, xmm0
0x180016a38  mov     [rbp+var_8], rax
0x180016a3c  mov     rbx, r9
0x180016a3f  mov     qword ptr [rbp+encoding.encodingType], rax
0x180016a43  mov     r13, rdx
0x180016a46  mov     [rbp+var_20], rax
0x180016a4a  mov     r15, rcx
0x180016a4d  mov     [rbp+arg_18], rax
0x180016a51  mov     edi, eax
0x180016a53  mov     [rbp+arg_10], eax
0x180016a56  movups  xmmword ptr [rbp+input.inputType], xmm0
0x180016a5a  test    r14, r14
0x180016a5d  jz      short loc_180016A62
0x180016a5f  mov     [r14], rax
0x180016a62  mov     r8d, [rcx+0B0h]
0x180016a69  lea     r9, [rbp+arg_10]
0x180016a6d  mov     rdx, [rcx+0A8h]
0x180016a74  mov     ecx, 1
0x180016a79  mov     [rsp+60h+propertyCount], 4
0x180016a81  call    I_GetProperty
0x180016a86  mov     r12d, [rbp+arg_10]
0x180016a8a  lea     r8, [rbp+input]; input
0x180016a8e  xor     ecx, ecx
0x180016a90  mov     qword ptr [rbp+input.inputType], 1
0x180016a98  mov     eax, 7FFFFFF8h
0x180016a9d  mov     dword ptr [rbp+var_8+4], ecx
0x180016aa0  test    r12d, r12d
0x180016aa3  lea     rdx, [rbp+encoding]; encoding
0x180016aa7  cmovz   r12d, eax
0x180016aab  lea     eax, [rcx+1]
0x180016aae  mov     [rbp+encoding.encodingType], eax
0x180016ab1  xor     r9d, r9d; properties
0x180016ab4  mov     eax, [rbx]
0x180016ab6  mov     dword ptr [rbp+value], eax
0x180016ab9  mov     rax, [rbx+8]
0x180016abd  mov     qword ptr [rbp+input.inputType+8], rax
0x180016ac1  mov     eax, [rbx+4]
0x180016ac4  mov     dword ptr [rbp+var_8], eax
0x180016ac7  mov     rax, [rsi]
0x180016aca  mov     [rsp+60h+error], rax; error
0x180016acf  mov     [rsp+60h+propertyCount], ecx; propertyCount
0x180016ad3  mov     rcx, [rsi+8]; reader
0x180016ad7  call    cs:__imp_WsSetInput
0x180016ade  nop     dword ptr [rax+rax+00h]
0x180016ae3  mov     ebx, eax
0x180016ae5  test    eax, eax
0x180016ae7  jns     short loc_180016AF4
0x180016ae9  mov     r9d, 7E2h
0x180016aef  jmp     loc_180016BCA
0x180016af4  cmp     dword ptr [rbp+value], edi
0x180016af7  jnz     short loc_180016B2E
0x180016af9  mov     rax, [rsi]
0x180016afc  lea     r8, [rbp+value]; value
0x180016b00  mov     rcx, [rsi+8]; reader
0x180016b04  mov     edx, 4; id
0x180016b09  mov     r9d, edx; valueSize
0x180016b0c  mov     qword ptr [rsp+60h+propertyCount], rax; error
0x180016b11  call    cs:__imp_WsGetReaderProperty
0x180016b18  nop     dword ptr [rax+rax+00h]
0x180016b1d  mov     ebx, eax
0x180016b1f  test    eax, eax
0x180016b21  jns     short loc_180016B2E
0x180016b23  mov     r9d, 7F1h
0x180016b29  jmp     loc_180016BCA
0x180016b2e  mov     rax, [rsi]
0x180016b31  lea     rdx, ?Object_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; elementDescription
0x180016b38  mov     r9, [rsi+30h]; heap
0x180016b3c  mov     r8d, 2; readOption
0x180016b42  mov     rcx, [rsi+8]; reader
0x180016b46  mov     [rsp+60h+var_30], rax; error
0x180016b4b  lea     rax, [rbp+var_20]
0x180016b4f  mov     dword ptr [rsp+60h+error], 8; valueSize
0x180016b57  mov     qword ptr [rsp+60h+propertyCount], rax; value
0x180016b5c  call    cs:__imp_WsReadElement
0x180016b63  nop     dword ptr [rax+rax+00h]
0x180016b68  mov     ebx, eax
0x180016b6a  test    eax, eax
0x180016b6c  jns     short loc_180016B76
0x180016b6e  mov     r9d, 801h
0x180016b74  jmp     short loc_180016BCA
0x180016b76  mov     r8d, dword ptr [rbp+value]; enum WS_CHARSET
0x180016b7a  lea     rax, [rbp+arg_18]
0x180016b7e  mov     edx, [r15+3Ch]; unsigned int
0x180016b82  mov     r9d, r12d; unsigned int
0x180016b85  mov     rcx, [r13+30h]; hHeap
0x180016b89  mov     [rsp+60h+var_30], rax; struct _CRYPT_XML_OBJECT **
0x180016b8e  mov     rax, [rbp+var_20]
0x180016b92  mov     [rsp+60h+error], rsi; struct _CRYPT_XML_WS_STATE *
0x180016b97  mov     qword ptr [rsp+60h+propertyCount], rax; struct WS_TYPE_Object *
0x180016b9c  call    ?I_XmlUnmarshallObject@@YAJPEAXKW4WS_CHARSET@@KPEAUWS_TYPE_Object@@PEAU_CRYPT_XML_WS_STATE@@PEAPEBU_CRYPT_XML_OBJECT@@@Z; I_XmlUnmarshallObject(void *,ulong,WS_CHARSET,ulong,WS_TYPE_Object *,_CRYPT_XML_WS_STATE *,_CRYPT_XML_OBJECT const * *)
0x180016ba1  mov     rdi, [rbp+arg_18]
0x180016ba5  mov     ebx, eax
0x180016ba7  test    eax, eax
0x180016ba9  jns     short loc_180016BB3
0x180016bab  mov     r9d, 814h
0x180016bb1  jmp     short loc_180016BCA
0x180016bb3  mov     rdx, rdi
0x180016bb6  mov     rcx, r13
0x180016bb9  call    I_CryptXmlSignatureAddObject
0x180016bbe  mov     ebx, eax
0x180016bc0  test    eax, eax
0x180016bc2  jns     short loc_180016BFC
0x180016bc4  mov     r9d, 81Eh
0x180016bca  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016bd1  mov     r11d, ebx
0x180016bd4  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180016bdb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016be0  mov     r8, rax
0x180016be3  mov     edx, ebx
0x180016be5  mov     rcx, r10; char *
0x180016be8  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180016bed  mov     rcx, [rsi]; error
0x180016bf0  test    rcx, rcx
0x180016bf3  jz      short loc_180016C06
0x180016bf5  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x180016bfa  jmp     short loc_180016C06
0x180016bfc  test    r14, r14
0x180016bff  jz      short loc_180016C04
0x180016c01  mov     [r14], rdi
0x180016c04  xor     ebx, ebx
0x180016c06  test    rdi, rdi
0x180016c09  jz      short loc_180016C14
0x180016c0b  mov     rcx, [rdi+8]
0x180016c0f  call    I_CryptXmlRelease
0x180016c14  mov     eax, ebx
0x180016c16  mov     rbx, [rsp+60h+arg_8]
0x180016c1e  add     rsp, 60h
0x180016c22  pop     r15
0x180016c24  pop     r14
0x180016c26  pop     r13
0x180016c28  pop     r12
0x180016c2a  pop     rdi
0x180016c2b  pop     rsi
0x180016c2c  pop     rbp
0x180016c2d  retn
```
