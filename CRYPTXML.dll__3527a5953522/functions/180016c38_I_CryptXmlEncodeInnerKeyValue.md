# I_CryptXmlEncodeInnerKeyValue

- ea: `0x180016c38`
- end: `0x180016e36`
- name: `I_CryptXmlEncodeInnerKeyValue`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012838`

## callees

- `0x1800070d0`
- `0x180014ce0`
- `0x1800164cc`
- `0x180016564`
- `0x180016c38`

## import_xrefs

- `webservices!WsFreeWriter` at `0x180016e12`
- `webservices!WsFreeWriter` at `0x180016e12`
- `webservices!WsCreateReader` at `0x180016cc9`
- `webservices!WsCreateReader` at `0x180016cc9`
- `webservices!WsCreateHeap` at `0x180016d43`
- `webservices!WsCreateHeap` at `0x180016d43`
- `webservices!WsFreeError` at `0x180016de8`
- `webservices!WsFreeError` at `0x180016de8`
- `webservices!WsCreateWriter` at `0x180016cfb`
- `webservices!WsCreateWriter` at `0x180016cfb`
- `webservices!WsFreeReader` at `0x180016dc6`
- `webservices!WsFreeReader` at `0x180016dc6`
- `webservices!WsFreeHeap` at `0x180016dfd`
- `webservices!WsFreeHeap` at `0x180016dfd`
- `webservices!WsCreateError` at `0x180016c83`
- `webservices!WsCreateError` at `0x180016c83`

## string_xrefs

- `0x180016c95`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180016cdb`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180016d0d`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180016d55`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180016da4`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlEncodeInnerKeyValue(unsigned int a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // ebx
  const char *v7; // rax
  int v8; // r9d
  int v9; // edx
  WS_ERROR *v10; // rcx
  WS_XML_READER *reader; // [rsp+40h] [rbp-20h] BYREF
  WS_HEAP *heap; // [rsp+48h] [rbp-18h] BYREF
  WS_XML_WRITER *writer; // [rsp+50h] [rbp-10h] BYREF
  WS_ERROR *error; // [rsp+98h] [rbp+38h] BYREF

  reader = 0;
  writer = 0;
  heap = 0;
  error = 0;
  v6 = WsCreateError(0, 0, &error);
  if ( v6 < 0 )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v8 = 2740;
LABEL_3:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v6, v7, v8);
    goto LABEL_13;
  }
  v6 = WsCreateReader(0, 0, &reader, error);
  if ( v6 < 0 )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v8 = 2756;
    goto LABEL_3;
  }
  v6 = WsCreateWriter(0, 0, &writer, error);
  if ( v6 < 0 )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v8 = 2772;
    goto LABEL_3;
  }
  v6 = WsCreateHeap(0x10000u, 0x1000u, 0, 0, &heap, error);
  if ( v6 < 0 )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v8 = 2790;
    goto LABEL_3;
  }
  v6 = I_XmlEncodeInnerKeyValue(a1, a2, a3);
  if ( v6 < 0 )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v8 = 2806;
    goto LABEL_3;
  }
  v6 = 0;
LABEL_13:
  if ( reader )
    WsFreeReader(reader);
  v10 = error;
  if ( error )
  {
    if ( v6 < 0 )
    {
      I_TraceWsError(error, v9);
      v10 = error;
    }
    WsFreeError(v10);
  }
  if ( heap )
    WsFreeHeap(heap);
  if ( writer )
    WsFreeWriter(writer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016c38  mov     [rsp-18h+arg_0], rbx
0x180016c3d  mov     [rsp-18h+arg_8], rsi
0x180016c42  mov     [rsp-18h+error], r9
0x180016c47  push    rbp
0x180016c48  push    rdi
0x180016c49  push    r14
0x180016c4b  mov     rbp, rsp
0x180016c4e  sub     rsp, 60h
0x180016c52  mov     rdi, r8
0x180016c55  mov     [rbp+reader], 0
0x180016c5d  mov     rsi, rdx
0x180016c60  mov     [rbp+writer], 0
0x180016c68  mov     r14d, ecx
0x180016c6b  mov     [rbp+var_18], 0
0x180016c73  lea     r8, [rbp+error]; error
0x180016c77  mov     [rbp+error], 0
0x180016c7f  xor     edx, edx; propertyCount
0x180016c81  xor     ecx, ecx; properties
0x180016c83  call    cs:__imp_WsCreateError
0x180016c8a  nop     dword ptr [rax+rax+00h]
0x180016c8f  mov     ebx, eax
0x180016c91  test    eax, eax
0x180016c93  jns     short loc_180016CBD
0x180016c95  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016c9c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016ca1  mov     r9d, 0AB4h
0x180016ca7  mov     r8, rax
0x180016caa  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180016cb1  mov     edx, ebx
0x180016cb3  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180016cb8  jmp     loc_180016DBD
0x180016cbd  mov     r9, [rbp+error]; error
0x180016cc1  lea     r8, [rbp+reader]; reader
0x180016cc5  xor     edx, edx; propertyCount
0x180016cc7  xor     ecx, ecx; properties
0x180016cc9  call    cs:__imp_WsCreateReader
0x180016cd0  nop     dword ptr [rax+rax+00h]
0x180016cd5  mov     ebx, eax
0x180016cd7  test    eax, eax
0x180016cd9  jns     short loc_180016CEF
0x180016cdb  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016ce2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016ce7  mov     r9d, 0AC4h
0x180016ced  jmp     short loc_180016CA7
0x180016cef  mov     r9, [rbp+error]; error
0x180016cf3  lea     r8, [rbp+writer]; writer
0x180016cf7  xor     edx, edx; propertyCount
0x180016cf9  xor     ecx, ecx; properties
0x180016cfb  call    cs:__imp_WsCreateWriter
0x180016d02  nop     dword ptr [rax+rax+00h]
0x180016d07  mov     ebx, eax
0x180016d09  test    eax, eax
0x180016d0b  jns     short loc_180016D21
0x180016d0d  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016d14  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016d19  mov     r9d, 0AD4h
0x180016d1f  jmp     short loc_180016CA7
0x180016d21  mov     rax, [rbp+error]
0x180016d25  xor     r9d, r9d; propertyCount
0x180016d28  mov     [rsp+60h+var_38], rax; error
0x180016d2d  xor     r8d, r8d; properties
0x180016d30  lea     rax, [rbp+var_18]
0x180016d34  mov     edx, 1000h; trimSize
0x180016d39  mov     ecx, 10000h; maxSize
0x180016d3e  mov     [rsp+60h+heap], rax; heap
0x180016d43  call    cs:__imp_WsCreateHeap
0x180016d4a  nop     dword ptr [rax+rax+00h]
0x180016d4f  mov     ebx, eax
0x180016d51  test    eax, eax
0x180016d53  jns     short loc_180016D6C
0x180016d55  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016d5c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016d61  mov     r9d, 0AE6h
0x180016d67  jmp     loc_180016CA7
0x180016d6c  mov     rax, [rbp+error]
0x180016d70  mov     r8, rdi
0x180016d73  mov     [rsp+60h+var_28], rax
0x180016d78  mov     rdx, rsi
0x180016d7b  mov     rax, [rbp+var_18]
0x180016d7f  mov     ecx, r14d
0x180016d82  mov     [rsp+60h+var_30], rax
0x180016d87  mov     rax, [rbp+writer]
0x180016d8b  mov     [rsp+60h+var_38], rax
0x180016d90  mov     rax, [rbp+reader]
0x180016d94  mov     [rsp+60h+heap], rax
0x180016d99  call    I_XmlEncodeInnerKeyValue
0x180016d9e  mov     ebx, eax
0x180016da0  test    eax, eax
0x180016da2  jns     short loc_180016DBB
0x180016da4  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180016dab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180016db0  mov     r9d, 0AF6h
0x180016db6  jmp     loc_180016CA7
0x180016dbb  xor     ebx, ebx
0x180016dbd  mov     rcx, [rbp+reader]; reader
0x180016dc1  test    rcx, rcx
0x180016dc4  jz      short loc_180016DD2
0x180016dc6  call    cs:__imp_WsFreeReader
0x180016dcd  nop     dword ptr [rax+rax+00h]
0x180016dd2  mov     rcx, [rbp+error]; error
0x180016dd6  test    rcx, rcx
0x180016dd9  jz      short loc_180016DF4
0x180016ddb  test    ebx, ebx
0x180016ddd  jns     short loc_180016DE8
0x180016ddf  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x180016de4  mov     rcx, [rbp+error]; error
0x180016de8  call    cs:__imp_WsFreeError
0x180016def  nop     dword ptr [rax+rax+00h]
0x180016df4  mov     rcx, [rbp+var_18]; heap
0x180016df8  test    rcx, rcx
0x180016dfb  jz      short loc_180016E09
0x180016dfd  call    cs:__imp_WsFreeHeap
0x180016e04  nop     dword ptr [rax+rax+00h]
0x180016e09  mov     rcx, [rbp+writer]; writer
0x180016e0d  test    rcx, rcx
0x180016e10  jz      short loc_180016E1E
0x180016e12  call    cs:__imp_WsFreeWriter
0x180016e19  nop     dword ptr [rax+rax+00h]
0x180016e1e  lea     r11, [rsp+60h+var_s0]
0x180016e23  mov     eax, ebx
0x180016e25  mov     rbx, [r11+20h]
0x180016e29  mov     rsi, [r11+28h]
0x180016e2d  mov     rsp, r11
0x180016e30  pop     r14
0x180016e32  pop     rdi
0x180016e33  pop     rbp
0x180016e34  retn
```
