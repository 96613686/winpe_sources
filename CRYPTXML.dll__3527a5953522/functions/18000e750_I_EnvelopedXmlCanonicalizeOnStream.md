# I_EnvelopedXmlCanonicalizeOnStream

- ea: `0x18000e750`
- end: `0x18000eb01`
- name: `I_EnvelopedXmlCanonicalizeOnStream`
- size: `945`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e290`

## callees

- `0x1800070d0`
- `0x18000e750`
- `0x180014ce0`
- `0x1800164cc`

## import_xrefs

- `webservices!WsFillReader` at `0x18000e8dd`
- `webservices!WsFillReader` at `0x18000e92f`
- `webservices!WsFillReader` at `0x18000e8dd`
- `webservices!WsFillReader` at `0x18000e92f`
- `webservices!WsCreateReader` at `0x18000e80d`
- `webservices!WsCreateReader` at `0x18000e80d`
- `webservices!WsFreeError` at `0x18000e9a8`
- `webservices!WsFreeError` at `0x18000e9a8`
- `webservices!WsReadNode` at `0x18000e94d`
- `webservices!WsReadNode` at `0x18000e94d`
- `webservices!WsEndReaderCanonicalization` at `0x18000e97e`
- `webservices!WsEndReaderCanonicalization` at `0x18000e97e`
- `webservices!WsGetReaderNode` at `0x18000e903`
- `webservices!WsGetReaderNode` at `0x18000e903`
- `webservices!WsFreeReader` at `0x18000ea0a`
- `webservices!WsFreeReader` at `0x18000ea0a`
- `webservices!WsSetInput` at `0x18000e85f`
- `webservices!WsSetInput` at `0x18000e85f`
- `webservices!WsStartReaderCanonicalization` at `0x18000e8a8`
- `webservices!WsStartReaderCanonicalization` at `0x18000e8a8`
- `webservices!WsCreateError` at `0x18000e7eb`
- `webservices!WsCreateError` at `0x18000e7eb`

## string_xrefs

- `0x18000e963`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e9de`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000ea1f`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000ea52`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000ea7b`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000ea8f`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000eaa3`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000eab7`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000eacb`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e77e`: `http://www.w3.org/2000/09/xmldsig#`

## pseudocode

```c
__int64 I_EnvelopedXmlCanonicalizeOnStream(__int64 a1, __int64 a2, __int64 a3, ...)
{
  ULONG v3; // edi
  HRESULT started; // ebx
  const char *v7; // rax
  int v8; // r9d
  int v9; // edx
  WS_ERROR *v10; // rcx
  const char *v12; // r8
  char v13; // al
  const char *v14; // rdx
  bool v15; // zf
  char v16; // al
  const char *v17; // rdx
  bool v18; // zf
  char v19; // al
  const char *v20; // rdx
  bool v21; // zf
  WS_XML_READER_ENCODING encoding[2]; // [rsp+30h] [rbp-79h] BYREF
  WS_XML_NODE *node; // [rsp+38h] [rbp-71h] BYREF
  WS_XML_READER_INPUT input[2]; // [rsp+40h] [rbp-69h] BYREF
  __int64 (__fastcall *v25)(); // [rsp+48h] [rbp-61h]
  __int64 v26; // [rsp+50h] [rbp-59h]
  _QWORD v27[8]; // [rsp+60h] [rbp-49h] BYREF
  _QWORD writeCallbackState[2]; // [rsp+A0h] [rbp-9h] BYREF
  WS_XML_CANONICALIZATION_PROPERTY properties; // [rsp+B0h] [rbp+7h] BYREF
  int v30; // [rsp+C8h] [rbp+1Fh]
  _QWORD *v31; // [rsp+D0h] [rbp+27h]
  int v32; // [rsp+D8h] [rbp+2Fh]
  WS_XML_READER *reader; // [rsp+118h] [rbp+6Fh] BYREF
  WS_ERROR *error; // [rsp+128h] [rbp+7Fh] BYREF
  va_list errora; // [rsp+128h] [rbp+7Fh]
  va_list va1; // [rsp+130h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(errora, a3);
  error = va_arg(va1, WS_ERROR *);
  v3 = *(_DWORD *)(a2 + 8);
  v27[1] = "Signature";
  reader = 0;
  v27[5] = "http://www.w3.org/2000/09/xmldsig#";
  error = 0;
  properties.value = &dword_1800229B4;
  v27[0] = 9;
  v31 = v27;
  v27[2] = 0;
  v27[3] = 0;
  v27[4] = 34;
  v27[6] = 0;
  v27[7] = 0;
  properties.id = WS_XML_CANONICALIZATION_PROPERTY_ALGORITHM;
  properties.valueSize = 4;
  v30 = 2;
  v32 = 64;
  started = WsCreateError(0, 0, (WS_ERROR **)errora);
  if ( started < 0 )
  {
    v12 = "";
    while ( 1 )
    {
      v16 = *(v12 - 1);
      v17 = v12--;
      v18 = v16 == 92;
      if ( v16 == 92 )
        break;
      if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp" )
      {
        v18 = v16 == 92;
        break;
      }
    }
    if ( v18 )
      v12 = v17;
    v8 = 536;
  }
  else
  {
    started = WsCreateReader(0, 0, &reader, error);
    if ( started < 0 )
    {
      v12 = "";
      while ( 1 )
      {
        v19 = *(v12 - 1);
        v20 = v12--;
        v21 = v19 == 92;
        if ( v19 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp" )
        {
          v21 = v19 == 92;
          break;
        }
      }
      if ( v21 )
        v12 = v20;
      v8 = 552;
    }
    else
    {
      v25 = I_WS_READ_CALLBACK;
      *(_QWORD *)&encoding[0].encodingType = 1;
      *(_QWORD *)&input[0].inputType = 2;
      v26 = a2;
      started = WsSetInput(reader, encoding, input, 0, 0, error);
      if ( started < 0 )
      {
        v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
        v8 = 582;
      }
      else
      {
        writeCallbackState[1] = CRYPT_XML_TRANSFORM_C14_WRITE_CALLBACK;
        writeCallbackState[0] = a3;
        started = WsStartReaderCanonicalization(
                    reader,
                    WS_TO_CRYPTXML_WRITE_CALLBACK,
                    writeCallbackState,
                    &properties,
                    2u,
                    error);
        if ( started < 0 )
        {
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
          v8 = 600;
        }
        else
        {
          if ( v3 < 0x400 )
            v3 = 1024;
          while ( 1 )
          {
            started = WsFillReader(reader, v3, 0, error);
            if ( started < 0 )
            {
              v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
              v8 = 624;
              goto LABEL_48;
            }
            node = 0;
            started = WsGetReaderNode(reader, (const WS_XML_NODE **)&node, error);
            if ( started < 0 )
            {
              v12 = "";
              while ( 1 )
              {
                v13 = *(v12 - 1);
                v14 = v12--;
                v15 = v13 == 92;
                if ( v13 == 92 )
                  break;
                if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp" )
                {
                  v15 = v13 == 92;
                  break;
                }
              }
              if ( v15 )
                v12 = v14;
              v8 = 636;
              goto LABEL_49;
            }
            if ( node->nodeType == WS_XML_NODE_TYPE_EOF )
              break;
            started = WsFillReader(reader, v3, 0, error);
            if ( started < 0 )
            {
              v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
              v8 = 654;
              goto LABEL_48;
            }
            started = WsReadNode(reader, error);
            if ( started < 0 )
            {
              v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
              v8 = 668;
              goto LABEL_48;
            }
          }
          started = WsEndReaderCanonicalization(reader, error);
          if ( started >= 0 )
          {
            started = 0;
            goto LABEL_15;
          }
          v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
          v8 = 676;
        }
      }
LABEL_48:
      v12 = v7;
    }
  }
LABEL_49:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v12, v8);
LABEL_15:
  v10 = error;
  if ( error )
  {
    if ( started < 0 )
    {
      I_TraceWsError(error, v9);
      v10 = error;
    }
    WsFreeError(v10);
  }
  if ( reader )
    WsFreeReader(reader);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000e750  mov     [rsp-8+arg_0], rbx
0x18000e755  mov     [rsp-8+error], r9
0x18000e75a  push    rbp
0x18000e75b  push    rsi
0x18000e75c  push    rdi
0x18000e75d  push    r14
0x18000e75f  push    r15
0x18000e761  lea     rbp, [rsp-37h]
0x18000e766  sub     rsp, 0E0h
0x18000e76d  mov     edi, [rdx+8]
0x18000e770  lea     rax, aSignature; "Signature"
0x18000e777  xor     r15d, r15d
0x18000e77a  mov     [rbp+57h+var_98], rax
0x18000e77e  lea     rax, aHttpWwwW3Org20_8; "http://www.w3.org/2000/09/xmldsig#"
0x18000e785  mov     [rbp+57h+reader], r15
0x18000e789  mov     [rbp+57h+var_78], rax
0x18000e78d  mov     r14, r8
0x18000e790  lea     rax, dword_1800229B4
0x18000e797  mov     [rbp+57h+error], r15
0x18000e79b  mov     [rbp+57h+properties.value], rax
0x18000e79f  lea     r8, [rbp+57h+error]; error
0x18000e7a3  lea     rax, [rbp+57h+var_A0]
0x18000e7a7  mov     [rbp+57h+var_A0], 9
0x18000e7af  mov     rsi, rdx
0x18000e7b2  mov     [rbp+57h+var_30], rax
0x18000e7b6  xor     edx, edx; propertyCount
0x18000e7b8  mov     [rbp+57h+var_90], r15
0x18000e7bc  xor     ecx, ecx; properties
0x18000e7be  mov     [rbp+57h+var_88], r15
0x18000e7c2  mov     [rbp+57h+var_80], 22h ; '"'
0x18000e7ca  mov     [rbp+57h+var_70], r15
0x18000e7ce  mov     [rbp+57h+var_68], r15
0x18000e7d2  mov     [rbp+57h+properties.id], r15d
0x18000e7d6  mov     [rbp+57h+properties.valueSize], 4
0x18000e7dd  mov     [rbp+57h+var_38], 2
0x18000e7e4  mov     [rbp+57h+var_28], 40h ; '@'
0x18000e7eb  call    cs:__imp_WsCreateError
0x18000e7f2  nop     dword ptr [rax+rax+00h]
0x18000e7f7  mov     ebx, eax
0x18000e7f9  test    eax, eax
0x18000e7fb  js      loc_18000EA18
0x18000e801  mov     r9, [rbp+57h+error]; error
0x18000e805  lea     r8, [rbp+57h+reader]; reader
0x18000e809  xor     edx, edx; propertyCount
0x18000e80b  xor     ecx, ecx; properties
0x18000e80d  call    cs:__imp_WsCreateReader
0x18000e814  nop     dword ptr [rax+rax+00h]
0x18000e819  mov     ebx, eax
0x18000e81b  test    eax, eax
0x18000e81d  js      loc_18000EA4B
0x18000e823  mov     rcx, [rbp+57h+reader]; reader
0x18000e827  lea     rax, I_WS_READ_CALLBACK
0x18000e82e  mov     [rbp+57h+var_B8], rax
0x18000e832  lea     r8, [rbp+57h+input]; input
0x18000e836  mov     rax, [rbp+57h+error]
0x18000e83a  lea     rdx, [rbp+57h+encoding]; encoding
0x18000e83e  mov     [rsp+100h+var_D8], rax; error
0x18000e843  xor     r9d, r9d; properties
0x18000e846  mov     [rsp+100h+propertyCount], r15d; propertyCount
0x18000e84b  mov     qword ptr [rbp+57h+encoding.encodingType], 1
0x18000e853  mov     qword ptr [rbp+57h+input.inputType], 2
0x18000e85b  mov     [rbp+57h+var_B0], rsi
0x18000e85f  call    cs:__imp_WsSetInput
0x18000e866  nop     dword ptr [rax+rax+00h]
0x18000e86b  mov     ebx, eax
0x18000e86d  test    eax, eax
0x18000e86f  js      loc_18000EA7B
0x18000e875  mov     rcx, [rbp+57h+reader]; reader
0x18000e879  lea     rax, CRYPT_XML_TRANSFORM_C14_WRITE_CALLBACK
0x18000e880  mov     [rbp+57h+var_58], rax
0x18000e884  lea     r9, [rbp+57h+properties]; properties
0x18000e888  mov     rax, [rbp+57h+error]
0x18000e88c  lea     r8, [rbp+57h+writeCallbackState]; writeCallbackState
0x18000e890  mov     [rsp+100h+var_D8], rax; error
0x18000e895  lea     rdx, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; writeCallback
0x18000e89c  mov     [rsp+100h+propertyCount], 2; propertyCount
0x18000e8a4  mov     [rbp+57h+writeCallbackState], r14
0x18000e8a8  call    cs:__imp_WsStartReaderCanonicalization
0x18000e8af  nop     dword ptr [rax+rax+00h]
0x18000e8b4  mov     ebx, eax
0x18000e8b6  test    eax, eax
0x18000e8b8  js      loc_18000EA8F
0x18000e8be  mov     eax, 400h
0x18000e8c3  cmp     edi, eax
0x18000e8c5  cmovb   edi, eax
0x18000e8c8  nop     dword ptr [rax+rax+00000000h]
0x18000e8d0  mov     r9, [rbp+57h+error]; error
0x18000e8d4  xor     r8d, r8d; asyncContext
0x18000e8d7  mov     rcx, [rbp+57h+reader]; reader
0x18000e8db  mov     edx, edi; minSize
0x18000e8dd  call    cs:__imp_WsFillReader
0x18000e8e4  nop     dword ptr [rax+rax+00h]
0x18000e8e9  mov     ebx, eax
0x18000e8eb  test    eax, eax
0x18000e8ed  js      loc_18000EACB
0x18000e8f3  mov     r8, [rbp+57h+error]; error
0x18000e8f7  lea     rdx, [rbp+57h+node]; node
0x18000e8fb  mov     rcx, [rbp+57h+reader]; xmlReader
0x18000e8ff  mov     [rbp+57h+node], r15
0x18000e903  call    cs:__imp_WsGetReaderNode
0x18000e90a  nop     dword ptr [rax+rax+00h]
0x18000e90f  mov     ebx, eax
0x18000e911  test    eax, eax
0x18000e913  js      loc_18000E9D7
0x18000e919  mov     rax, [rbp+57h+node]
0x18000e91d  mov     rcx, [rbp+57h+reader]; reader
0x18000e921  cmp     dword ptr [rax], 8
0x18000e924  jz      short loc_18000E97A
0x18000e926  mov     r9, [rbp+57h+error]; error
0x18000e92a  xor     r8d, r8d; asyncContext
0x18000e92d  mov     edx, edi; minSize
0x18000e92f  call    cs:__imp_WsFillReader
0x18000e936  nop     dword ptr [rax+rax+00h]
0x18000e93b  mov     ebx, eax
0x18000e93d  test    eax, eax
0x18000e93f  js      loc_18000EAA3
0x18000e945  mov     rdx, [rbp+57h+error]; error
0x18000e949  mov     rcx, [rbp+57h+reader]; reader
0x18000e94d  call    cs:__imp_WsReadNode
0x18000e954  nop     dword ptr [rax+rax+00h]
0x18000e959  mov     ebx, eax
0x18000e95b  test    eax, eax
0x18000e95d  jns     loc_18000E8D0
0x18000e963  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e96a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e96f  mov     r9d, 29Ch
0x18000e975  jmp     loc_18000EADD
0x18000e97a  mov     rdx, [rbp+57h+error]; error
0x18000e97e  call    cs:__imp_WsEndReaderCanonicalization
0x18000e985  nop     dword ptr [rax+rax+00h]
0x18000e98a  mov     ebx, eax
0x18000e98c  test    eax, eax
0x18000e98e  js      loc_18000EAB7
0x18000e994  mov     ebx, r15d
0x18000e997  mov     rcx, [rbp+57h+error]; error
0x18000e99b  test    rcx, rcx
0x18000e99e  jz      short loc_18000E9B4
0x18000e9a0  test    ebx, ebx
0x18000e9a2  js      loc_18000EAF3
0x18000e9a8  call    cs:__imp_WsFreeError
0x18000e9af  nop     dword ptr [rax+rax+00h]
0x18000e9b4  mov     rcx, [rbp+57h+reader]; reader
0x18000e9b8  test    rcx, rcx
0x18000e9bb  jnz     short loc_18000EA0A
0x18000e9bd  mov     eax, ebx
0x18000e9bf  mov     rbx, [rsp+100h+arg_0]
0x18000e9c7  add     rsp, 0E0h
0x18000e9ce  pop     r15
0x18000e9d0  pop     r14
0x18000e9d2  pop     rdi
0x18000e9d3  pop     rsi
0x18000e9d4  pop     rbp
0x18000e9d5  retn
0x18000e9d7  lea     r8, aOnecoreDsSecur+32h; ""
0x18000e9de  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e9e5  movzx   eax, byte ptr [r8-1]
0x18000e9ea  mov     rdx, r8
0x18000e9ed  dec     r8
0x18000e9f0  cmp     al, 5Ch ; '\'
0x18000e9f2  jz      short loc_18000E9FB
0x18000e9f4  cmp     r8, rcx
0x18000e9f7  ja      short loc_18000E9E5
0x18000e9f9  cmp     al, 5Ch ; '\'
0x18000e9fb  cmovz   r8, rdx
0x18000e9ff  mov     r9d, 27Ch
0x18000ea05  jmp     loc_18000EAE0
0x18000ea0a  call    cs:__imp_WsFreeReader
0x18000ea11  nop     dword ptr [rax+rax+00h]
0x18000ea16  jmp     short loc_18000E9BD
0x18000ea18  lea     r8, aOnecoreDsSecur+32h; ""
0x18000ea1f  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ea26  movzx   eax, byte ptr [r8-1]
0x18000ea2b  mov     rdx, r8
0x18000ea2e  dec     r8
0x18000ea31  cmp     al, 5Ch ; '\'
0x18000ea33  jz      short loc_18000EA3C
0x18000ea35  cmp     r8, rcx
0x18000ea38  ja      short loc_18000EA26
0x18000ea3a  cmp     al, 5Ch ; '\'
0x18000ea3c  cmovz   r8, rdx
0x18000ea40  mov     r9d, 218h
0x18000ea46  jmp     loc_18000EAE0
0x18000ea4b  lea     r8, aOnecoreDsSecur+32h; ""
0x18000ea52  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ea59  movzx   eax, byte ptr [r8-1]
0x18000ea5e  mov     rdx, r8
0x18000ea61  dec     r8
0x18000ea64  cmp     al, 5Ch ; '\'
0x18000ea66  jz      short loc_18000EA6F
0x18000ea68  cmp     r8, rcx
0x18000ea6b  ja      short loc_18000EA59
0x18000ea6d  cmp     al, 5Ch ; '\'
0x18000ea6f  cmovz   r8, rdx
0x18000ea73  mov     r9d, 228h
0x18000ea79  jmp     short loc_18000EAE0
0x18000ea7b  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ea82  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ea87  mov     r9d, 246h
0x18000ea8d  jmp     short loc_18000EADD
0x18000ea8f  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ea96  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ea9b  mov     r9d, 258h
0x18000eaa1  jmp     short loc_18000EADD
0x18000eaa3  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000eaaa  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000eaaf  mov     r9d, 28Eh
0x18000eab5  jmp     short loc_18000EADD
0x18000eab7  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000eabe  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000eac3  mov     r9d, 2A4h
0x18000eac9  jmp     short loc_18000EADD
0x18000eacb  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ead2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ead7  mov     r9d, 270h
0x18000eadd  mov     r8, rax
0x18000eae0  mov     edx, ebx
0x18000eae2  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000eae9  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000eaee  jmp     loc_18000E997
0x18000eaf3  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x18000eaf8  mov     rcx, [rbp+57h+error]
0x18000eafc  jmp     loc_18000E9A8
```
