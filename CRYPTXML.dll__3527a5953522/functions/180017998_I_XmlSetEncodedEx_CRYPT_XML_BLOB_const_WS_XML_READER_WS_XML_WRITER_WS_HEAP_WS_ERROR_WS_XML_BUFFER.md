# I_XmlSetEncodedEx(_CRYPT_XML_BLOB const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,_WS_XML_BUFFER * *)

- ea: `0x180017998`
- end: `0x180017b2a`
- name: `?I_XmlSetEncodedEx@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@PEAPEAU_WS_XML_BUFFER@@@Z`
- size: `402`
- prototype: `int(const struct _CRYPT_XML_BLOB *, struct _WS_XML_READER *, struct _WS_XML_WRITER *, struct _WS_HEAP *, struct _WS_ERROR *, struct _WS_XML_BUFFER **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011a40`
- `0x180017938`

## callees

- `0x1800070d0`
- `0x180014ce0`
- `0x180017998`

## import_xrefs

- `webservices!WsCopyNode` at `0x180017abb`
- `webservices!WsCopyNode` at `0x180017abb`
- `webservices!WsSetOutputToBuffer` at `0x180017a89`
- `webservices!WsSetOutputToBuffer` at `0x180017a89`
- `webservices!WsFlushWriter` at `0x180017aef`
- `webservices!WsFlushWriter` at `0x180017aef`
- `webservices!WsCreateXmlBuffer` at `0x180017a52`
- `webservices!WsCreateXmlBuffer` at `0x180017a52`
- `webservices!WsSetInput` at `0x180017a00`
- `webservices!WsSetInput` at `0x180017a00`

## string_xrefs

- `0x180017a12`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017a64`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017a9b`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017acd`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017b01`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlSetEncodedEx(
        const struct _CRYPT_XML_BLOB *a1,
        struct _WS_XML_READER *a2,
        struct _WS_XML_WRITER *a3,
        struct _WS_HEAP *a4,
        struct _WS_ERROR *error,
        struct _WS_XML_BUFFER **buffer)
{
  BYTE *pbData; // rax
  WS_ERROR *v8; // rdi
  HRESULT XmlBuffer; // ebx
  const char *v12; // rax
  int v13; // r9d
  WS_XML_BUFFER **v14; // r14
  _QWORD v16[2]; // [rsp+30h] [rbp-58h] BYREF
  ULONG cbData; // [rsp+40h] [rbp-48h]
  int v18; // [rsp+44h] [rbp-44h]
  WS_XML_READER_ENCODING v19; // [rsp+90h] [rbp+8h] BYREF
  int v20; // [rsp+94h] [rbp+Ch]

  pbData = a1->pbData;
  v8 = error;
  v16[0] = 1;
  v18 = 0;
  v16[1] = pbData;
  cbData = a1->cbData;
  LODWORD(pbData) = a1->dwCharset;
  v19.encodingType = WS_XML_READER_ENCODING_TYPE_TEXT;
  v20 = (int)pbData;
  XmlBuffer = WsSetInput(a2, &v19, (const WS_XML_READER_INPUT *)v16, 0, 0, error);
  if ( XmlBuffer >= 0 )
  {
    v14 = buffer;
    XmlBuffer = WsCreateXmlBuffer(a4, 0, 0, buffer, v8);
    if ( XmlBuffer >= 0 )
    {
      XmlBuffer = WsSetOutputToBuffer(a3, *v14, 0, 0, v8);
      if ( XmlBuffer >= 0 )
      {
        XmlBuffer = WsCopyNode(a3, a2, v8);
        if ( XmlBuffer >= 0 )
        {
          XmlBuffer = WsFlushWriter(a3, 0, 0, v8);
          if ( XmlBuffer >= 0 )
            return 0;
          v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
          v13 = 628;
        }
        else
        {
          v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
          v13 = 612;
        }
      }
      else
      {
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
        v13 = 597;
      }
    }
    else
    {
      v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v13 = 584;
    }
  }
  else
  {
    v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v13 = 567;
  }
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", XmlBuffer, v12, v13);
  return (unsigned int)XmlBuffer;
}

```

## disassembly

```asm
0x180017998  mov     r11, rsp
0x18001799b  push    rbx
0x18001799c  push    rbp
0x18001799d  push    rsi
0x18001799e  push    rdi
0x18001799f  push    r14
0x1800179a1  push    r15
0x1800179a3  sub     rsp, 58h
0x1800179a7  mov     rax, [rcx+8]
0x1800179ab  mov     rbp, rdx
0x1800179ae  mov     rdi, [rsp+88h+error]
0x1800179b6  mov     edx, 1
0x1800179bb  mov     qword ptr [r11-58h], 1
0x1800179c3  mov     r15, r9
0x1800179c6  mov     [rsp+88h+var_44], 0
0x1800179ce  mov     rsi, r8
0x1800179d1  mov     [r11-50h], rax
0x1800179d5  lea     r8, [r11-58h]; input
0x1800179d9  mov     eax, [rcx+4]
0x1800179dc  xor     r9d, r9d; properties
0x1800179df  mov     [rsp+88h+var_48], eax
0x1800179e3  mov     eax, [rcx]
0x1800179e5  mov     rcx, rbp; reader
0x1800179e8  mov     [r11+8], edx
0x1800179ec  lea     rdx, [r11+8]; encoding
0x1800179f0  mov     [r11-60h], rdi
0x1800179f4  mov     [r11+0Ch], eax
0x1800179f8  mov     [rsp+88h+propertyCount], 0; propertyCount
0x180017a00  call    cs:__imp_WsSetInput
0x180017a07  nop     dword ptr [rax+rax+00h]
0x180017a0c  mov     ebx, eax
0x180017a0e  test    eax, eax
0x180017a10  jns     short loc_180017A3A
0x180017a12  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017a19  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017a1e  mov     r9d, 237h
0x180017a24  mov     r8, rax
0x180017a27  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180017a2e  mov     edx, ebx
0x180017a30  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180017a35  jmp     loc_180017B1A
0x180017a3a  mov     r14, [rsp+88h+buffer]
0x180017a42  xor     r8d, r8d; propertyCount
0x180017a45  mov     r9, r14; buffer
0x180017a48  mov     qword ptr [rsp+88h+propertyCount], rdi; error
0x180017a4d  xor     edx, edx; properties
0x180017a4f  mov     rcx, r15; heap
0x180017a52  call    cs:__imp_WsCreateXmlBuffer
0x180017a59  nop     dword ptr [rax+rax+00h]
0x180017a5e  mov     ebx, eax
0x180017a60  test    eax, eax
0x180017a62  jns     short loc_180017A78
0x180017a64  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017a6b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017a70  mov     r9d, 248h
0x180017a76  jmp     short loc_180017A24
0x180017a78  mov     rdx, [r14]; buffer
0x180017a7b  xor     r9d, r9d; propertyCount
0x180017a7e  xor     r8d, r8d; properties
0x180017a81  mov     qword ptr [rsp+88h+propertyCount], rdi; error
0x180017a86  mov     rcx, rsi; writer
0x180017a89  call    cs:__imp_WsSetOutputToBuffer
0x180017a90  nop     dword ptr [rax+rax+00h]
0x180017a95  mov     ebx, eax
0x180017a97  test    eax, eax
0x180017a99  jns     short loc_180017AB2
0x180017a9b  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017aa2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017aa7  mov     r9d, 255h
0x180017aad  jmp     loc_180017A24
0x180017ab2  mov     r8, rdi; error
0x180017ab5  mov     rdx, rbp; reader
0x180017ab8  mov     rcx, rsi; writer
0x180017abb  call    cs:__imp_WsCopyNode
0x180017ac2  nop     dword ptr [rax+rax+00h]
0x180017ac7  mov     ebx, eax
0x180017ac9  test    eax, eax
0x180017acb  jns     short loc_180017AE4
0x180017acd  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017ad4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017ad9  mov     r9d, 264h
0x180017adf  jmp     loc_180017A24
0x180017ae4  mov     r9, rdi; error
0x180017ae7  xor     r8d, r8d; asyncContext
0x180017aea  xor     edx, edx; minSize
0x180017aec  mov     rcx, rsi; writer
0x180017aef  call    cs:__imp_WsFlushWriter
0x180017af6  nop     dword ptr [rax+rax+00h]
0x180017afb  mov     ebx, eax
0x180017afd  test    eax, eax
0x180017aff  jns     short loc_180017B18
0x180017b01  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017b08  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017b0d  mov     r9d, 274h
0x180017b13  jmp     loc_180017A24
0x180017b18  xor     ebx, ebx
0x180017b1a  mov     eax, ebx
0x180017b1c  add     rsp, 58h
0x180017b20  pop     r15
0x180017b22  pop     r14
0x180017b24  pop     rdi
0x180017b25  pop     rsi
0x180017b26  pop     rbp
0x180017b27  pop     rbx
0x180017b28  retn
```
