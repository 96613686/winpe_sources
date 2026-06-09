# I_CryptXmlResolveEmptyReference

- ea: `0x180009f80`
- end: `0x18000a304`
- name: `I_CryptXmlResolveEmptyReference`
- size: `900`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800094a0`
- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x180009f80`
- `0x18000b1a0`
- `0x18000cfb0`
- `0x180011410`
- `0x180014ce0`
- `0x1800164cc`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2e6`
- `webservices!WsReadNode` at `0x18000a0fa`
- `webservices!WsReadNode` at `0x18000a0fa`
- `webservices!WsEndReaderCanonicalization` at `0x18000a18d`
- `webservices!WsEndReaderCanonicalization` at `0x18000a18d`
- `webservices!WsGetReaderNode` at `0x18000a0cc`
- `webservices!WsGetReaderNode` at `0x18000a0cc`
- `webservices!WsSetInputToBuffer` at `0x18000a03c`
- `webservices!WsSetInputToBuffer` at `0x18000a03c`
- `webservices!WsStartReaderCanonicalization` at `0x18000a09f`
- `webservices!WsStartReaderCanonicalization` at `0x18000a09f`

## string_xrefs

- `0x18000a116`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000a156`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000a21a`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000a238`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000a256`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000a274`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000a292`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x180009fa2`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`

## pseudocode

```c
__int64 __fastcall I_CryptXmlResolveEmptyReference(__int64 a1, __int64 a2)
{
  WS_ERROR **v2; // rdi
  _DWORD *v4; // rax
  _DWORD *v5; // rsi
  const struct _CRYPT_XML_PROPERTY *v6; // rdx
  HRESULT CanonPropertiesForWsReader; // ebx
  unsigned int v8; // r8d
  WS_ERROR *v9; // rdx
  WS_XML_READER *v10; // rcx
  unsigned int v11; // r10d
  const char *v12; // rax
  char v13; // dl
  const char *v14; // r8
  const char *v15; // r11
  __int64 v16; // r9
  char v17; // dl
  const char *v18; // r8
  int v19; // eax
  int v21; // edx
  ULONG propertyCount; // [rsp+30h] [rbp-C8h] BYREF
  WS_XML_NODE *node; // [rsp+38h] [rbp-C0h] BYREF
  _CRYPT_XML_ALGORITHM v24; // [rsp+40h] [rbp-B8h] BYREF
  _QWORD writeCallbackState[2]; // [rsp+60h] [rbp-98h] BYREF
  WS_XML_CANONICALIZATION_PROPERTY properties; // [rsp+70h] [rbp-88h] BYREF

  v2 = *(WS_ERROR ***)(a1 + 152);
  *(_OWORD *)a2 = 0;
  node = 0;
  *(_QWORD *)&v24.cbSize = 32;
  *(_OWORD *)(a2 + 16) = 0;
  v24.wszAlgorithm = L"http://www.w3.org/TR/2001/REC-xml-c14n-20010315";
  propertyCount = 3;
  *(_QWORD *)&v24.Encoded.dwCharset = 0;
  v24.Encoded.pbData = 0;
  v4 = (_DWORD *)CryptXmlAlloc(a1, 32);
  v5 = v4;
  if ( v4 )
  {
    *v4 = 32;
    writeCallbackState[0] = v4;
    writeCallbackState[1] = &CRYPT_XML_ENCODE_REFERENCE_WRITE_CALLBACK;
    CanonPropertiesForWsReader = WsSetInputToBuffer(v2[1], v2[5], 0, 0, *v2);
    if ( CanonPropertiesForWsReader < 0 )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
      v16 = 618;
    }
    else
    {
      CanonPropertiesForWsReader = I_CryptXmlGetCanonPropertiesForWsReader(&v24, v6, v8, &properties, &propertyCount, 0);
      if ( CanonPropertiesForWsReader < 0 )
      {
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
        v16 = 632;
      }
      else
      {
        CanonPropertiesForWsReader = WsStartReaderCanonicalization(
                                       v2[1],
                                       WS_TO_CRYPTXML_WRITE_CALLBACK,
                                       writeCallbackState,
                                       &properties,
                                       propertyCount,
                                       *v2);
        if ( CanonPropertiesForWsReader < 0 )
        {
          v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
          v16 = 646;
        }
        else
        {
          while ( 1 )
          {
            CanonPropertiesForWsReader = WsGetReaderNode(v2[1], (const WS_XML_NODE **)&node, *v2);
            if ( CanonPropertiesForWsReader < 0 )
            {
              v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
              v16 = 662;
              goto LABEL_30;
            }
            v9 = *v2;
            v10 = v2[1];
            if ( node->nodeType == WS_XML_NODE_TYPE_EOF )
              break;
            CanonPropertiesForWsReader = WsReadNode(v10, v9);
            v11 = CanonPropertiesForWsReader;
            if ( CanonPropertiesForWsReader < 0 )
            {
              v12 = "";
              do
              {
                v13 = *(v12 - 1);
                v14 = v12--;
              }
              while ( v13 != 92 && v12 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp" );
              v15 = "ERROR  : (0x%08x) %s:%u";
              v16 = 686;
              if ( v13 == 92 )
                v12 = v14;
              goto LABEL_30;
            }
          }
          CanonPropertiesForWsReader = WsEndReaderCanonicalization(v10, v9);
          if ( CanonPropertiesForWsReader >= 0 )
          {
            *(_QWORD *)a2 = v5;
            *(_QWORD *)(a2 + 16) = &CRYPT_XML_REFERENCE_DATA_PROVIDER_READ;
            *(_QWORD *)(a2 + 24) = CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE;
            v19 = v5[3];
            v5 = 0;
            *(_DWORD *)(a2 + 8) = v19;
            goto LABEL_22;
          }
          v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
          v16 = 697;
        }
      }
    }
  }
  else
  {
    CanonPropertiesForWsReader = -2147024882;
    v12 = "";
    do
    {
      v17 = *(v12 - 1);
      v18 = v12--;
    }
    while ( v17 != 92 && v12 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp" );
    v15 = "ERROR  : (0x%08x) %s:%u";
    v11 = -2147024882;
    v16 = 594;
    if ( v17 == 92 )
      v12 = v18;
  }
LABEL_30:
  WPPTraceLogA(v15, v11, v12, v16);
  if ( *v2 )
    I_TraceWsError(*v2, v21);
LABEL_22:
  if ( v5 )
    CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE(v5);
  return (unsigned int)CanonPropertiesForWsReader;
}

```

## disassembly

```asm
0x180009f80  mov     r11, rsp
0x180009f83  push    rbx
0x180009f84  push    rsi
0x180009f85  sub     rsp, 0E8h
0x180009f8c  mov     rax, cs:__security_cookie
0x180009f93  xor     rax, rsp
0x180009f96  mov     [rsp+0F8h+var_38], rax
0x180009f9e  mov     [r11+18h], rbp
0x180009fa2  lea     rax, aHttpWwwW3OrgTr_0; "http://www.w3.org/TR/2001/REC-xml-c14n-"...
0x180009fa9  mov     [r11+20h], rdi
0x180009fad  xorps   xmm0, xmm0
0x180009fb0  mov     rdi, [rcx+98h]
0x180009fb7  xor     ebp, ebp
0x180009fb9  mov     [r11-18h], r14
0x180009fbd  mov     r14, rdx
0x180009fc0  movups  xmmword ptr [rdx], xmm0
0x180009fc3  mov     [rsp+0F8h+node], rbp
0x180009fc8  movaps  xmmword ptr [r11-28h], xmm6
0x180009fcd  xorps   xmm6, xmm6
0x180009fd0  movups  xmmword ptr [rsp+0F8h+var_B8.cbSize], xmm6
0x180009fd5  mov     qword ptr [rsp+0F8h+var_B8.cbSize], 20h ; ' '
0x180009fde  movups  xmmword ptr [rdx+10h], xmm0
0x180009fe2  mov     edx, 20h ; ' '
0x180009fe7  mov     [rsp+0F8h+var_B8.wszAlgorithm], rax
0x180009fec  mov     [rsp+0F8h+propertyCount], 3
0x180009ff4  mov     qword ptr [rsp+0F8h+var_B8.Encoded.dwCharset], rbp
0x180009ff9  mov     [rsp+0F8h+var_B8.Encoded.pbData], rbp
0x180009ffe  call    CryptXmlAlloc
0x18000a003  mov     rsi, rax
0x18000a006  test    rax, rax
0x18000a009  jz      loc_18000A14A
0x18000a00f  mov     dword ptr [rax], 20h ; ' '
0x18000a015  xor     r9d, r9d; propertyCount
0x18000a018  mov     [rsp+0F8h+writeCallbackState], rsi
0x18000a01d  lea     rax, CRYPT_XML_ENCODE_REFERENCE_WRITE_CALLBACK
0x18000a024  mov     [rsp+0F8h+var_90], rax
0x18000a029  xor     r8d, r8d; properties
0x18000a02c  mov     rax, [rdi]
0x18000a02f  mov     rdx, [rdi+28h]; buffer
0x18000a033  mov     rcx, [rdi+8]; reader
0x18000a037  mov     [rsp+0F8h+error], rax; error
0x18000a03c  call    cs:__imp_WsSetInputToBuffer
0x18000a043  nop     dword ptr [rax+rax+00h]
0x18000a048  mov     ebx, eax
0x18000a04a  test    eax, eax
0x18000a04c  js      loc_18000A21A
0x18000a052  lea     rax, [rsp+0F8h+propertyCount]
0x18000a057  mov     [rsp+0F8h+var_D0], rbp; int *
0x18000a05c  lea     r9, [rsp+0F8h+properties]; struct _WS_XML_CANONICALIZATION_PROPERTY *
0x18000a061  mov     [rsp+0F8h+error], rax; unsigned int *
0x18000a066  lea     rcx, [rsp+0F8h+var_B8]; struct _CRYPT_XML_ALGORITHM *
0x18000a06b  call    ?I_CryptXmlGetCanonPropertiesForWsReader@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEBU_CRYPT_XML_PROPERTY@@KPEAU_WS_XML_CANONICALIZATION_PROPERTY@@PEAKPEAH@Z; I_CryptXmlGetCanonPropertiesForWsReader(_CRYPT_XML_ALGORITHM const *,_CRYPT_XML_PROPERTY const *,ulong,_WS_XML_CANONICALIZATION_PROPERTY *,ulong *,int *)
0x18000a070  mov     ebx, eax
0x18000a072  test    eax, eax
0x18000a074  js      loc_18000A238
0x18000a07a  mov     rax, [rdi]
0x18000a07d  lea     r9, [rsp+0F8h+properties]; properties
0x18000a082  mov     rcx, [rdi+8]; reader
0x18000a086  lea     r8, [rsp+0F8h+writeCallbackState]; writeCallbackState
0x18000a08b  mov     [rsp+0F8h+var_D0], rax; error
0x18000a090  lea     rdx, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; writeCallback
0x18000a097  mov     eax, [rsp+0F8h+propertyCount]
0x18000a09b  mov     dword ptr [rsp+0F8h+error], eax; propertyCount
0x18000a09f  call    cs:__imp_WsStartReaderCanonicalization
0x18000a0a6  nop     dword ptr [rax+rax+00h]
0x18000a0ab  mov     ebx, eax
0x18000a0ad  test    eax, eax
0x18000a0af  js      loc_18000A256
0x18000a0b5  nop     word ptr [rax+rax+00000000h]
0x18000a0c0  mov     r8, [rdi]; error
0x18000a0c3  lea     rdx, [rsp+0F8h+node]; node
0x18000a0c8  mov     rcx, [rdi+8]; xmlReader
0x18000a0cc  call    cs:__imp_WsGetReaderNode
0x18000a0d3  nop     dword ptr [rax+rax+00h]
0x18000a0d8  mov     ebx, eax
0x18000a0da  mov     r10d, eax
0x18000a0dd  test    eax, eax
0x18000a0df  js      loc_18000A292
0x18000a0e5  mov     rax, [rsp+0F8h+node]
0x18000a0ea  mov     rdx, [rdi]; error
0x18000a0ed  mov     rcx, [rdi+8]; reader
0x18000a0f1  cmp     dword ptr [rax], 8
0x18000a0f4  jz      loc_18000A18D
0x18000a0fa  call    cs:__imp_WsReadNode
0x18000a101  nop     dword ptr [rax+rax+00h]
0x18000a106  mov     ebx, eax
0x18000a108  mov     r10d, eax
0x18000a10b  test    eax, eax
0x18000a10d  jns     short loc_18000A0C0
0x18000a10f  lea     rax, aOnecoreDsSecur_0+30h; ""
0x18000a116  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000a11d  movzx   edx, byte ptr [rax-1]
0x18000a121  mov     r8, rax
0x18000a124  dec     rax
0x18000a127  cmp     dl, 5Ch ; '\'
0x18000a12a  jz      short loc_18000A131
0x18000a12c  cmp     rax, rcx
0x18000a12f  ja      short loc_18000A11D
0x18000a131  cmp     dl, 5Ch ; '\'
0x18000a134  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000a13b  mov     r9d, 2AEh
0x18000a141  cmovz   rax, r8
0x18000a145  jmp     loc_18000A2AB
0x18000a14a  mov     ebx, 8007000Eh
0x18000a14f  lea     rax, aOnecoreDsSecur_0+30h; ""
0x18000a156  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000a15d  movzx   edx, byte ptr [rax-1]
0x18000a161  mov     r8, rax
0x18000a164  dec     rax
0x18000a167  cmp     dl, 5Ch ; '\'
0x18000a16a  jz      short loc_18000A171
0x18000a16c  cmp     rax, rcx
0x18000a16f  ja      short loc_18000A15D
0x18000a171  cmp     dl, 5Ch ; '\'
0x18000a174  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000a17b  mov     r10d, ebx
0x18000a17e  mov     r9d, 252h
0x18000a184  cmovz   rax, r8
0x18000a188  jmp     loc_18000A2AB
0x18000a18d  call    cs:__imp_WsEndReaderCanonicalization
0x18000a194  nop     dword ptr [rax+rax+00h]
0x18000a199  mov     ebx, eax
0x18000a19b  test    eax, eax
0x18000a19d  js      loc_18000A274
0x18000a1a3  lea     rax, CRYPT_XML_REFERENCE_DATA_PROVIDER_READ
0x18000a1aa  mov     [r14], rsi
0x18000a1ad  mov     [r14+10h], rax
0x18000a1b1  lea     rax, CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE
0x18000a1b8  mov     [r14+18h], rax
0x18000a1bc  mov     eax, [rsi+0Ch]
0x18000a1bf  mov     rsi, rbp
0x18000a1c2  mov     [r14+8], eax
0x18000a1c6  mov     r14, [rsp+0F8h+var_18]
0x18000a1ce  movq    rdi, xmm6
0x18000a1d3  movaps  xmm6, [rsp+0F8h+var_28]
0x18000a1db  mov     rbp, [rsp+0F8h+arg_10]
0x18000a1e3  test    rdi, rdi
0x18000a1e6  jnz     loc_18000A2CF
0x18000a1ec  mov     rdi, [rsp+0F8h+arg_18]
0x18000a1f4  test    rsi, rsi
0x18000a1f7  jnz     loc_18000A2F7
0x18000a1fd  mov     eax, ebx
0x18000a1ff  mov     rcx, [rsp+0F8h+var_38]
0x18000a207  xor     rcx, rsp; StackCookie
0x18000a20a  call    __security_check_cookie
0x18000a20f  add     rsp, 0E8h
0x18000a216  pop     rsi
0x18000a217  pop     rbx
0x18000a218  retn
0x18000a21a  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000a221  mov     r10d, eax
0x18000a224  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000a22b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a230  mov     r9d, 26Ah
0x18000a236  jmp     short loc_18000A2AB
0x18000a238  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000a23f  mov     r10d, eax
0x18000a242  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000a249  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a24e  mov     r9d, 278h
0x18000a254  jmp     short loc_18000A2AB
0x18000a256  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000a25d  mov     r10d, eax
0x18000a260  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000a267  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a26c  mov     r9d, 286h
0x18000a272  jmp     short loc_18000A2AB
0x18000a274  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000a27b  mov     r10d, eax
0x18000a27e  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000a285  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a28a  mov     r9d, 2B9h
0x18000a290  jmp     short loc_18000A2AB
0x18000a292  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000a299  lea     r11, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000a2a0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000a2a5  mov     r9d, 296h
0x18000a2ab  mov     r8, rax
0x18000a2ae  mov     edx, r10d
0x18000a2b1  mov     rcx, r11; char *
0x18000a2b4  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000a2b9  mov     rcx, [rdi]; error
0x18000a2bc  test    rcx, rcx
0x18000a2bf  jz      loc_18000A1C6
0x18000a2c5  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x18000a2ca  jmp     loc_18000A1C6
0x18000a2cf  call    cs:__imp_GetProcessHeap
0x18000a2d6  nop     dword ptr [rax+rax+00h]
0x18000a2db  mov     r8, rdi; lpMem
0x18000a2de  mov     edx, 8; dwFlags
0x18000a2e3  mov     rcx, rax; hHeap
0x18000a2e6  call    cs:__imp_HeapFree
0x18000a2ed  nop     dword ptr [rax+rax+00h]
0x18000a2f2  jmp     loc_18000A1EC
0x18000a2f7  mov     rcx, rsi; lpMem
0x18000a2fa  call    CRYPT_XML_REFERENCE_DATA_PROVIDER_CLOSE
0x18000a2ff  jmp     loc_18000A1FD
```
