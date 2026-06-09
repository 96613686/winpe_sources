# I_XmlCanonicalizeOnStream

- ea: `0x18000e290`
- end: `0x18000e747`
- name: `I_XmlCanonicalizeOnStream`
- size: `1207`
- prototype: `__int64 __fastcall(struct _CRYPT_XML_ALGORITHM *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e220`

## callees

- `0x1800070d0`
- `0x18000cfb0`
- `0x18000e290`
- `0x18000e750`
- `0x180014ce0`
- `0x1800164cc`
- `0x180018625`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e30d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e30d`
- `webservices!WsFillReader` at `0x18000e51e`
- `webservices!WsFillReader` at `0x18000e572`
- `webservices!WsFillReader` at `0x18000e51e`
- `webservices!WsFillReader` at `0x18000e572`
- `webservices!WsCreateReader` at `0x18000e447`
- `webservices!WsCreateReader` at `0x18000e447`
- `webservices!WsFreeError` at `0x18000e3d5`
- `webservices!WsFreeError` at `0x18000e3d5`
- `webservices!WsReadNode` at `0x18000e591`
- `webservices!WsReadNode` at `0x18000e591`
- `webservices!WsEndReaderCanonicalization` at `0x18000e5c6`
- `webservices!WsEndReaderCanonicalization` at `0x18000e5c6`
- `webservices!WsGetReaderNode` at `0x18000e545`
- `webservices!WsGetReaderNode` at `0x18000e545`
- `webservices!WsFreeReader` at `0x18000e610`
- `webservices!WsFreeReader` at `0x18000e610`
- `webservices!WsSetInput` at `0x18000e49a`
- `webservices!WsSetInput` at `0x18000e49a`
- `webservices!WsStartReaderCanonicalization` at `0x18000e4e3`
- `webservices!WsStartReaderCanonicalization` at `0x18000e4e3`
- `webservices!WsCreateError` at `0x18000e424`
- `webservices!WsCreateError` at `0x18000e424`

## string_xrefs

- `0x18000e393`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e5a7`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e5eb`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e628`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e654`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e68e`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e6a5`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e6bc`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e6d3`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e6ea`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e704`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e71e`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`
- `0x18000e2e4`: `http://www.w3.org/2000/09/xmldsig#enveloped-signature`

## pseudocode

```c
__int64 __fastcall I_XmlCanonicalizeOnStream(struct _CRYPT_XML_ALGORITHM *a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG v7; // edi
  __int64 v8; // rcx
  int v9; // edx
  HRESULT CanonPropertiesForWsReader; // ebx
  WS_ERROR *v11; // rcx
  const char *v13; // r8
  char v14; // al
  const char *v15; // rdx
  bool v16; // zf
  const struct _CRYPT_XML_PROPERTY *v17; // rdx
  unsigned int v18; // r8d
  const char *v19; // r8
  int v20; // r9d
  char v21; // al
  const char *v22; // rdx
  bool v23; // zf
  char v24; // al
  char v25; // al
  WS_ERROR *error; // [rsp+38h] [rbp-81h] BYREF
  WS_XML_READER *reader; // [rsp+40h] [rbp-79h] BYREF
  ULONG propertyCount[2]; // [rsp+48h] [rbp-71h] BYREF
  WS_XML_READER_ENCODING encoding[2]; // [rsp+50h] [rbp-69h] BYREF
  WS_XML_READER_INPUT input[2]; // [rsp+58h] [rbp-61h] BYREF
  __int64 (__fastcall *v31)(); // [rsp+60h] [rbp-59h]
  __int64 v32; // [rsp+68h] [rbp-51h]
  _QWORD writeCallbackState[3]; // [rsp+70h] [rbp-49h] BYREF
  WS_XML_CANONICALIZATION_PROPERTY properties; // [rsp+88h] [rbp-31h] BYREF

  propertyCount[0] = 3;
  reader = 0;
  error = 0;
  if ( a1->Encoded.cbData )
  {
    CanonPropertiesForWsReader = -2146885371;
    v13 = "";
    while ( 1 )
    {
      v14 = *(v13 - 1);
      v15 = v13--;
      v16 = v14 == 92;
      if ( v14 == 92 )
        break;
      if ( v13 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp" )
      {
        v16 = v14 == 92;
        break;
      }
    }
    if ( v16 )
      v13 = v15;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885371, v13, 731);
  }
  else
  {
    v7 = *(_DWORD *)(a3 + 8);
    if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, L"http://www.w3.org/2000/09/xmldsig#enveloped-signature", -1) == 2 )
    {
      CanonPropertiesForWsReader = I_EnvelopedXmlCanonicalizeOnStream(v8, a3, a4);
      if ( CanonPropertiesForWsReader >= 0 )
        goto LABEL_4;
      v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
      v20 = 756;
    }
    else
    {
      memset_0(&properties, 0, 0x48u);
      CanonPropertiesForWsReader = I_CryptXmlGetCanonPropertiesForWsReader(a1, v17, v18, &properties, propertyCount, 0);
      if ( CanonPropertiesForWsReader < 0 )
      {
        v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
        v20 = 774;
      }
      else
      {
        CanonPropertiesForWsReader = WsCreateError(0, 0, &error);
        if ( CanonPropertiesForWsReader < 0 )
        {
          v19 = "";
          while ( 1 )
          {
            v21 = *(v19 - 1);
            v22 = v19--;
            v23 = v21 == 92;
            if ( v21 == 92 )
              break;
            if ( v19 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp" )
            {
              v23 = v21 == 92;
              break;
            }
          }
          v20 = 785;
LABEL_48:
          if ( v23 )
            v19 = v22;
        }
        else
        {
          CanonPropertiesForWsReader = WsCreateReader(0, 0, &reader, error);
          if ( CanonPropertiesForWsReader < 0 )
          {
            v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
            v20 = 801;
          }
          else
          {
            v31 = I_WS_READ_CALLBACK;
            *(_QWORD *)&encoding[0].encodingType = 1;
            *(_QWORD *)&input[0].inputType = 2;
            v32 = a3;
            CanonPropertiesForWsReader = WsSetInput(reader, encoding, input, 0, 0, error);
            if ( CanonPropertiesForWsReader < 0 )
            {
              v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
              v20 = 831;
            }
            else
            {
              writeCallbackState[1] = CRYPT_XML_TRANSFORM_C14_WRITE_CALLBACK;
              writeCallbackState[0] = a4;
              CanonPropertiesForWsReader = WsStartReaderCanonicalization(
                                             reader,
                                             WS_TO_CRYPTXML_WRITE_CALLBACK,
                                             writeCallbackState,
                                             &properties,
                                             propertyCount[0],
                                             error);
              if ( CanonPropertiesForWsReader < 0 )
              {
                v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
                v20 = 849;
              }
              else
              {
                if ( v7 < 0x400 )
                  v7 = 1024;
                while ( 1 )
                {
                  CanonPropertiesForWsReader = WsFillReader(reader, v7, 0, error);
                  if ( CanonPropertiesForWsReader < 0 )
                  {
                    v19 = "";
                    while ( 1 )
                    {
                      v25 = *(v19 - 1);
                      v22 = v19--;
                      v23 = v25 == 92;
                      if ( v25 == 92 )
                        break;
                      if ( v19 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp" )
                      {
                        v23 = v25 == 92;
                        break;
                      }
                    }
                    v20 = 873;
                    goto LABEL_48;
                  }
                  *(_QWORD *)propertyCount = 0;
                  CanonPropertiesForWsReader = WsGetReaderNode(reader, (const WS_XML_NODE **)propertyCount, error);
                  if ( CanonPropertiesForWsReader < 0 )
                  {
                    v19 = "";
                    while ( 1 )
                    {
                      v24 = *(v19 - 1);
                      v22 = v19--;
                      v23 = v24 == 92;
                      if ( v24 == 92 )
                        break;
                      if ( v19 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp" )
                      {
                        v23 = v24 == 92;
                        break;
                      }
                    }
                    v20 = 885;
                    goto LABEL_48;
                  }
                  if ( **(_DWORD **)propertyCount == 8 )
                    break;
                  CanonPropertiesForWsReader = WsFillReader(reader, v7, 0, error);
                  if ( CanonPropertiesForWsReader < 0 )
                  {
                    v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
                    v20 = 903;
                    goto LABEL_50;
                  }
                  CanonPropertiesForWsReader = WsReadNode(reader, error);
                  if ( CanonPropertiesForWsReader < 0 )
                  {
                    v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
                    v20 = 917;
                    goto LABEL_50;
                  }
                }
                CanonPropertiesForWsReader = WsEndReaderCanonicalization(reader, error);
                if ( CanonPropertiesForWsReader >= 0 )
                {
                  CanonPropertiesForWsReader = 0;
                  goto LABEL_4;
                }
                v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
                v20 = 926;
              }
            }
          }
        }
      }
    }
LABEL_50:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CanonPropertiesForWsReader, v19, v20);
  }
LABEL_4:
  v11 = error;
  if ( error )
  {
    if ( CanonPropertiesForWsReader < 0 )
    {
      I_TraceWsError(error, v9);
      v11 = error;
    }
    WsFreeError(v11);
  }
  if ( reader )
    WsFreeReader(reader);
  return (unsigned int)CanonPropertiesForWsReader;
}

```

## disassembly

```asm
0x18000e290  mov     r11, rsp
0x18000e293  push    rbp
0x18000e294  push    rbx
0x18000e295  lea     rbp, [r11-57h]
0x18000e299  sub     rsp, 0F8h
0x18000e2a0  mov     rax, cs:__security_cookie
0x18000e2a7  xor     rax, rsp
0x18000e2aa  mov     [rbp+4Fh+var_30], rax
0x18000e2ae  mov     [r11+10h], rsi
0x18000e2b2  mov     rbx, rcx
0x18000e2b5  mov     [r11-20h], r14
0x18000e2b9  mov     rsi, r8
0x18000e2bc  mov     [r11-28h], r15
0x18000e2c0  mov     r14, r9
0x18000e2c3  xor     r15d, r15d
0x18000e2c6  mov     [rbp+4Fh+propertyCount], 3
0x18000e2cd  mov     [rbp+4Fh+reader], r15
0x18000e2d1  mov     [rsp+100h+error], r15
0x18000e2d6  cmp     [rcx+14h], r15d
0x18000e2da  ja      loc_18000E387
0x18000e2e0  mov     [r11-18h], rdi
0x18000e2e4  lea     rax, aHttpWwwW3Org20_13; "http://www.w3.org/2000/09/xmldsig#envel"...
0x18000e2eb  mov     edi, [r8+8]
0x18000e2ef  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000e2f5  mov     r8, [rcx+8]; lpString1
0x18000e2f9  mov     edx, 1; dwCmpFlags
0x18000e2fe  xor     ecx, ecx; Locale
0x18000e300  mov     [rsp+100h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000e308  mov     [rsp+100h+lpString2], rax; lpString2
0x18000e30d  call    cs:__imp_CompareStringW
0x18000e314  nop     dword ptr [rax+rax+00h]
0x18000e319  cmp     eax, 2
0x18000e31c  jnz     loc_18000E3E6
0x18000e322  mov     r8, r14
0x18000e325  mov     rdx, rsi
0x18000e328  call    I_EnvelopedXmlCanonicalizeOnStream
0x18000e32d  mov     ebx, eax
0x18000e32f  test    eax, eax
0x18000e331  js      loc_18000E68E
0x18000e337  mov     rdi, [rsp+0F0h]
0x18000e33f  mov     rcx, [rsp+100h+error]; error
0x18000e344  mov     r15, [rsp+100h+var_20]
0x18000e34c  mov     r14, [rsp+100h+var_18]
0x18000e354  mov     rsi, [rsp+100h+arg_8]
0x18000e35c  test    rcx, rcx
0x18000e35f  jnz     short loc_18000E3CD
0x18000e361  mov     rcx, [rbp+4Fh+reader]; reader
0x18000e365  test    rcx, rcx
0x18000e368  jnz     loc_18000E610
0x18000e36e  mov     eax, ebx
0x18000e370  mov     rcx, [rbp+4Fh+var_30]
0x18000e374  xor     rcx, rsp; StackCookie
0x18000e377  call    __security_check_cookie
0x18000e37c  add     rsp, 0F8h
0x18000e383  pop     rbx
0x18000e384  pop     rbp
0x18000e385  retn
0x18000e387  mov     ebx, 80092105h
0x18000e38c  lea     r8, aOnecoreDsSecur+32h; ""
0x18000e393  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e39a  movzx   eax, byte ptr [r8-1]
0x18000e39f  mov     rdx, r8
0x18000e3a2  dec     r8
0x18000e3a5  cmp     al, 5Ch ; '\'
0x18000e3a7  jz      short loc_18000E3B0
0x18000e3a9  cmp     r8, rcx
0x18000e3ac  ja      short loc_18000E39A
0x18000e3ae  cmp     al, 5Ch ; '\'
0x18000e3b0  cmovz   r8, rdx
0x18000e3b4  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000e3bb  mov     edx, ebx
0x18000e3bd  mov     r9d, 2DBh
0x18000e3c3  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000e3c8  jmp     loc_18000E33F
0x18000e3cd  test    ebx, ebx
0x18000e3cf  js      loc_18000E738
0x18000e3d5  call    cs:__imp_WsFreeError
0x18000e3dc  nop     dword ptr [rax+rax+00h]
0x18000e3e1  jmp     loc_18000E361
0x18000e3e6  xor     edx, edx; Val
0x18000e3e8  lea     rcx, [rbp+4Fh+properties]; void *
0x18000e3ec  mov     r8d, 48h ; 'H'; Size
0x18000e3f2  call    memset_0
0x18000e3f7  lea     rax, [rbp+4Fh+propertyCount]
0x18000e3fb  mov     qword ptr [rsp+100h+cchCount2], r15; int *
0x18000e400  lea     r9, [rbp+4Fh+properties]; struct _WS_XML_CANONICALIZATION_PROPERTY *
0x18000e404  mov     [rsp+100h+lpString2], rax; unsigned int *
0x18000e409  mov     rcx, rbx; struct _CRYPT_XML_ALGORITHM *
0x18000e40c  call    ?I_CryptXmlGetCanonPropertiesForWsReader@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEBU_CRYPT_XML_PROPERTY@@KPEAU_WS_XML_CANONICALIZATION_PROPERTY@@PEAKPEAH@Z; I_CryptXmlGetCanonPropertiesForWsReader(_CRYPT_XML_ALGORITHM const *,_CRYPT_XML_PROPERTY const *,ulong,_WS_XML_CANONICALIZATION_PROPERTY *,ulong *,int *)
0x18000e411  mov     ebx, eax
0x18000e413  test    eax, eax
0x18000e415  js      loc_18000E6A5
0x18000e41b  lea     r8, [rsp+100h+error]; error
0x18000e420  xor     edx, edx; propertyCount
0x18000e422  xor     ecx, ecx; properties
0x18000e424  call    cs:__imp_WsCreateError
0x18000e42b  nop     dword ptr [rax+rax+00h]
0x18000e430  mov     ebx, eax
0x18000e432  test    eax, eax
0x18000e434  js      loc_18000E5E4
0x18000e43a  mov     r9, [rsp+100h+error]; error
0x18000e43f  lea     r8, [rbp+4Fh+reader]; reader
0x18000e443  xor     edx, edx; propertyCount
0x18000e445  xor     ecx, ecx; properties
0x18000e447  call    cs:__imp_WsCreateReader
0x18000e44e  nop     dword ptr [rax+rax+00h]
0x18000e453  mov     ebx, eax
0x18000e455  test    eax, eax
0x18000e457  js      loc_18000E6BC
0x18000e45d  mov     rcx, [rbp+4Fh+reader]; reader
0x18000e461  lea     rax, I_WS_READ_CALLBACK
0x18000e468  mov     [rbp+4Fh+var_A8], rax
0x18000e46c  lea     r8, [rbp+4Fh+input]; input
0x18000e470  mov     rax, [rsp+100h+error]
0x18000e475  lea     rdx, [rbp+4Fh+encoding]; encoding
0x18000e479  mov     qword ptr [rsp+100h+cchCount2], rax; error
0x18000e47e  xor     r9d, r9d; properties
0x18000e481  mov     dword ptr [rsp+100h+lpString2], r15d; propertyCount
0x18000e486  mov     qword ptr [rbp+4Fh+encoding.encodingType], 1
0x18000e48e  mov     qword ptr [rbp+4Fh+input.inputType], 2
0x18000e496  mov     [rbp+4Fh+var_A0], rsi
0x18000e49a  call    cs:__imp_WsSetInput
0x18000e4a1  nop     dword ptr [rax+rax+00h]
0x18000e4a6  mov     ebx, eax
0x18000e4a8  test    eax, eax
0x18000e4aa  js      loc_18000E6D3
0x18000e4b0  mov     rcx, [rbp+4Fh+reader]; reader
0x18000e4b4  lea     rax, CRYPT_XML_TRANSFORM_C14_WRITE_CALLBACK
0x18000e4bb  mov     [rbp+4Fh+var_90], rax
0x18000e4bf  lea     r9, [rbp+4Fh+properties]; properties
0x18000e4c3  mov     rax, [rsp+100h+error]
0x18000e4c8  lea     r8, [rbp+4Fh+writeCallbackState]; writeCallbackState
0x18000e4cc  mov     qword ptr [rsp+100h+cchCount2], rax; error
0x18000e4d1  lea     rdx, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; writeCallback
0x18000e4d8  mov     eax, [rbp+4Fh+propertyCount]
0x18000e4db  mov     dword ptr [rsp+100h+lpString2], eax; propertyCount
0x18000e4df  mov     [rbp+4Fh+writeCallbackState], r14
0x18000e4e3  call    cs:__imp_WsStartReaderCanonicalization
0x18000e4ea  nop     dword ptr [rax+rax+00h]
0x18000e4ef  mov     ebx, eax
0x18000e4f1  test    eax, eax
0x18000e4f3  js      loc_18000E6EA
0x18000e4f9  mov     eax, 400h
0x18000e4fe  cmp     edi, eax
0x18000e500  cmovb   edi, eax
0x18000e503  nop     dword ptr [rax+00h]
0x18000e507  nop     word ptr [rax+rax+00000000h]
0x18000e510  mov     r9, [rsp+100h+error]; error
0x18000e515  xor     r8d, r8d; asyncContext
0x18000e518  mov     rcx, [rbp+4Fh+reader]; reader
0x18000e51c  mov     edx, edi; minSize
0x18000e51e  call    cs:__imp_WsFillReader
0x18000e525  nop     dword ptr [rax+rax+00h]
0x18000e52a  mov     ebx, eax
0x18000e52c  test    eax, eax
0x18000e52e  js      loc_18000E64D
0x18000e534  mov     r8, [rsp+100h+error]; error
0x18000e539  lea     rdx, [rbp+4Fh+propertyCount]; node
0x18000e53d  mov     rcx, [rbp+4Fh+reader]; xmlReader
0x18000e541  mov     qword ptr [rbp+4Fh+propertyCount], r15
0x18000e545  call    cs:__imp_WsGetReaderNode
0x18000e54c  nop     dword ptr [rax+rax+00h]
0x18000e551  mov     ebx, eax
0x18000e553  test    eax, eax
0x18000e555  js      loc_18000E621
0x18000e55b  mov     rax, qword ptr [rbp+4Fh+propertyCount]
0x18000e55f  mov     rcx, [rbp+4Fh+reader]; reader
0x18000e563  cmp     dword ptr [rax], 8
0x18000e566  jz      short loc_18000E5C1
0x18000e568  mov     r9, [rsp+100h+error]; error
0x18000e56d  xor     r8d, r8d; asyncContext
0x18000e570  mov     edx, edi; minSize
0x18000e572  call    cs:__imp_WsFillReader
0x18000e579  nop     dword ptr [rax+rax+00h]
0x18000e57e  mov     ebx, eax
0x18000e580  test    eax, eax
0x18000e582  js      loc_18000E704
0x18000e588  mov     rdx, [rsp+100h+error]; error
0x18000e58d  mov     rcx, [rbp+4Fh+reader]; reader
0x18000e591  call    cs:__imp_WsReadNode
0x18000e598  nop     dword ptr [rax+rax+00h]
0x18000e59d  mov     ebx, eax
0x18000e59f  test    eax, eax
0x18000e5a1  jns     loc_18000E510
0x18000e5a7  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e5ae  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e5b3  mov     r8, rax
0x18000e5b6  mov     r9d, 395h
0x18000e5bc  jmp     loc_18000E67B
0x18000e5c1  mov     rdx, [rsp+100h+error]; error
0x18000e5c6  call    cs:__imp_WsEndReaderCanonicalization
0x18000e5cd  nop     dword ptr [rax+rax+00h]
0x18000e5d2  mov     ebx, eax
0x18000e5d4  test    eax, eax
0x18000e5d6  js      loc_18000E71E
0x18000e5dc  mov     ebx, r15d
0x18000e5df  jmp     loc_18000E337
0x18000e5e4  lea     r8, aOnecoreDsSecur+32h; ""
0x18000e5eb  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e5f2  movzx   eax, byte ptr [r8-1]
0x18000e5f7  mov     rdx, r8
0x18000e5fa  dec     r8
0x18000e5fd  cmp     al, 5Ch ; '\'
0x18000e5ff  jz      short loc_18000E608
0x18000e601  cmp     r8, rcx
0x18000e604  ja      short loc_18000E5F2
0x18000e606  cmp     al, 5Ch ; '\'
0x18000e608  mov     r9d, 311h
0x18000e60e  jmp     short loc_18000E677
0x18000e610  call    cs:__imp_WsFreeReader
0x18000e617  nop     dword ptr [rax+rax+00h]
0x18000e61c  jmp     loc_18000E36E
0x18000e621  lea     r8, aOnecoreDsSecur+32h; ""
0x18000e628  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e62f  movzx   eax, byte ptr [r8-1]
0x18000e634  mov     rdx, r8
0x18000e637  dec     r8
0x18000e63a  cmp     al, 5Ch ; '\'
0x18000e63c  jz      short loc_18000E645
0x18000e63e  cmp     r8, rcx
0x18000e641  ja      short loc_18000E62F
0x18000e643  cmp     al, 5Ch ; '\'
0x18000e645  mov     r9d, 375h
0x18000e64b  jmp     short loc_18000E677
0x18000e64d  lea     r8, aOnecoreDsSecur+32h; ""
0x18000e654  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e65b  movzx   eax, byte ptr [r8-1]
0x18000e660  mov     rdx, r8
0x18000e663  dec     r8
0x18000e666  cmp     al, 5Ch ; '\'
0x18000e668  jz      short loc_18000E671
0x18000e66a  cmp     r8, rcx
0x18000e66d  ja      short loc_18000E65B
0x18000e66f  cmp     al, 5Ch ; '\'
0x18000e671  mov     r9d, 369h
0x18000e677  cmovz   r8, rdx
0x18000e67b  mov     edx, ebx
0x18000e67d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000e684  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000e689  jmp     loc_18000E337
0x18000e68e  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e695  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e69a  mov     r8, rax
0x18000e69d  mov     r9d, 2F4h
0x18000e6a3  jmp     short loc_18000E67B
0x18000e6a5  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e6ac  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e6b1  mov     r8, rax
0x18000e6b4  mov     r9d, 306h
0x18000e6ba  jmp     short loc_18000E67B
0x18000e6bc  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e6c3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e6c8  mov     r8, rax
0x18000e6cb  mov     r9d, 321h
0x18000e6d1  jmp     short loc_18000E67B
0x18000e6d3  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e6da  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e6df  mov     r8, rax
0x18000e6e2  mov     r9d, 33Fh
0x18000e6e8  jmp     short loc_18000E67B
0x18000e6ea  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e6f1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e6f6  mov     r8, rax
0x18000e6f9  mov     r9d, 351h
0x18000e6ff  jmp     loc_18000E67B
0x18000e704  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e70b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e710  mov     r8, rax
0x18000e713  mov     r9d, 387h
0x18000e719  jmp     loc_18000E67B
0x18000e71e  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000e725  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e72a  mov     r8, rax
0x18000e72d  mov     r9d, 39Eh
0x18000e733  jmp     loc_18000E67B
0x18000e738  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x18000e73d  mov     rcx, [rsp+100h+error]
0x18000e742  jmp     loc_18000E3D5
```
