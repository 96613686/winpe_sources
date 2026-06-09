# I_CryptXmlCanonicalizeSignedInfo

- ea: `0x18000c990`
- end: `0x18000cf9b`
- name: `I_CryptXmlCanonicalizeSignedInfo`
- size: `1547`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002470`
- `0x18000b3b0`

## callees

- `0x1800070d0`
- `0x18000c990`
- `0x18000cfb0`
- `0x180010da0`
- `0x180014ce0`
- `0x1800164cc`
- `0x180018640`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000cd22`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000cd22`
- `webservices!WsSkipNode` at `0x18000cbca`
- `webservices!WsSkipNode` at `0x18000cbca`
- `webservices!WsReadNode` at `0x18000cd55`
- `webservices!WsReadNode` at `0x18000cd55`
- `webservices!WsEndReaderCanonicalization` at `0x18000cbe7`
- `webservices!WsEndReaderCanonicalization` at `0x18000cbe7`
- `webservices!WsReadToStartElement` at `0x18000cb0a`
- `webservices!WsReadToStartElement` at `0x18000cb0a`
- `webservices!WsSetInputToBuffer` at `0x18000ca1c`
- `webservices!WsSetInputToBuffer` at `0x18000ca1c`
- `webservices!WsSetReaderPosition` at `0x18000ca92`
- `webservices!WsSetReaderPosition` at `0x18000ca92`
- `webservices!WsStartReaderCanonicalization` at `0x18000cbad`
- `webservices!WsStartReaderCanonicalization` at `0x18000cbad`

## string_xrefs

- `0x18000ca35`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000caa4`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000cd72`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000cdac`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000cdd9`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000ce01`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000ce29`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000ce58`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000ce99`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000ced7`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18000cf0e`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlCanonicalizeSignedInfo(__int64 a1, unsigned int a2)
{
  __int64 v2; // rdi
  WS_ERROR *error; // rax
  WS_XML_READER *v5; // rcx
  __int64 v6; // rsi
  WS_XML_BUFFER *v7; // rdx
  HRESULT started; // ebx
  const char *v9; // r8
  char v10; // al
  const char *v11; // rdx
  bool v12; // zf
  const WS_XML_NODE_POSITION *v13; // rdx
  __int64 v14; // r14
  const char *v15; // rax
  unsigned int v16; // r8d
  const struct _CRYPT_XML_PROPERTY *v17; // rdx
  _QWORD *pvValue; // rax
  __int64 v19; // r10
  unsigned int v20; // esi
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r8
  unsigned int v25; // eax
  LPVOID v26; // rax
  const char *v27; // r8
  char v28; // al
  const char *v29; // rdx
  bool v30; // zf
  const char *v31; // rax
  const char *v32; // rax
  const char *v33; // rax
  const char *v34; // rax
  const char *v35; // r8
  char v36; // al
  const char *v37; // rdx
  bool v38; // zf
  const char *v39; // r8
  char v40; // al
  const char *v41; // rdx
  bool v42; // zf
  const char *v43; // r8
  char v44; // al
  const char *v45; // rdx
  bool v46; // zf
  const char *v47; // rax
  BOOL found; // [rsp+38h] [rbp-D0h] BYREF
  ULONG propertyCount; // [rsp+3Ch] [rbp-CCh] BYREF
  int v51[2]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD writeCallbackState[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v53; // [rsp+58h] [rbp-B0h] BYREF
  __int128 *v54; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+70h] [rbp-98h]
  void *v56; // [rsp+78h] [rbp-90h]
  __int64 (__fastcall *v57)(); // [rsp+80h] [rbp-88h]
  __int128 v58; // [rsp+88h] [rbp-80h] BYREF
  __int128 v59; // [rsp+98h] [rbp-70h]
  WS_XML_CANONICALIZATION_PROPERTY properties; // [rsp+A8h] [rbp-60h] BYREF

  v2 = *(_QWORD *)(a1 + 152);
  v54 = &v53;
  v58 = 0;
  v56 = &I_CRYPT_XML_C14N_DATA_PROVIDER_READ_0;
  v59 = 0;
  found = 0;
  v53 = 0;
  v57 = I_CRYPT_XML_TRANSFORM_C14N_PROVIDER_CLOSE_0;
  error = *(WS_ERROR **)v2;
  v5 = *(WS_XML_READER **)(v2 + 8);
  v6 = a2;
  v7 = *(WS_XML_BUFFER **)(v2 + 40);
  v55 = 0;
  started = WsSetInputToBuffer(v5, v7, 0, 0, error);
  if ( started >= 0 )
  {
    v13 = (const WS_XML_NODE_POSITION *)(*(_QWORD *)(v2 + 72) + 40 * v6);
    v14 = v6;
    if ( v13->buffer && (started = WsSetReaderPosition(*(WS_XML_READER **)(v2 + 8), v13, *(WS_ERROR **)v2), started < 0) )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v15, 752);
    }
    else
    {
      found = 0;
      do
      {
        while ( 1 )
        {
LABEL_13:
          if ( found )
          {
            started = 0;
            goto LABEL_63;
          }
          started = WsReadToStartElement(
                      *(WS_XML_READER **)(v2 + 8),
                      &WS_XML_DIGSIG_SignedInfo,
                      &WS_XML_DIGSIG_NS,
                      &found,
                      *(WS_ERROR **)v2);
          if ( started < 0 )
          {
            v47 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v47, 769);
            goto LABEL_63;
          }
          if ( !found )
            break;
          v17 = *(const struct _CRYPT_XML_PROPERTY **)(a1 + 136);
          writeCallbackState[0] = 0;
          writeCallbackState[1] = &CRYPT_XML_SIGNEDINFO_CANONICAL_CALLBACK;
          v51[0] = 0;
          pvValue = v17[1].pvValue;
          propertyCount = 3;
          writeCallbackState[0] = pvValue[v14];
          started = I_CryptXmlGetCanonPropertiesForWsReader(
                      (const struct _CRYPT_XML_ALGORITHM *)(*((_QWORD *)v17[1].pvValue + v14) + 40LL),
                      v17,
                      v16,
                      &properties,
                      &propertyCount,
                      v51);
          if ( started < 0 )
          {
            v43 = "";
            while ( 1 )
            {
              v44 = *(v43 - 1);
              v45 = v43--;
              v46 = v44 == 92;
              if ( v44 == 92 )
                break;
              if ( v43 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
              {
                v46 = v44 == 92;
                break;
              }
            }
            if ( v46 )
              v43 = v45;
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v43, 794);
            goto LABEL_63;
          }
          started = WsStartReaderCanonicalization(
                      *(WS_XML_READER **)(v2 + 8),
                      WS_TO_CRYPTXML_WRITE_CALLBACK,
                      writeCallbackState,
                      &properties,
                      propertyCount,
                      *(WS_ERROR **)v2);
          if ( started < 0 )
          {
            v39 = "";
            while ( 1 )
            {
              v40 = *(v39 - 1);
              v41 = v39--;
              v42 = v40 == 92;
              if ( v40 == 92 )
                break;
              if ( v39 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
              {
                v42 = v40 == 92;
                break;
              }
            }
            if ( v42 )
              v39 = v41;
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v39, 808);
            goto LABEL_63;
          }
          started = WsSkipNode(*(WS_XML_READER **)(v2 + 8), *(WS_ERROR **)v2);
          if ( started < 0 )
          {
            v35 = "";
            while ( 1 )
            {
              v36 = *(v35 - 1);
              v37 = v35--;
              v38 = v36 == 92;
              if ( v36 == 92 )
                break;
              if ( v35 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
              {
                v38 = v36 == 92;
                break;
              }
            }
            if ( v38 )
              v35 = v37;
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v35, 819);
            goto LABEL_63;
          }
          started = WsEndReaderCanonicalization(*(WS_XML_READER **)(v2 + 8), *(WS_ERROR **)v2);
          if ( started < 0 )
          {
            v34 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v34, 829);
            goto LABEL_63;
          }
          if ( v51[0] )
          {
            v19 = *(_QWORD *)(a1 + 136);
            v20 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 32) + 8 * v14) + 124LL);
            v51[1] = 0;
            v21 = *(_QWORD *)(v19 + 32);
            LODWORD(v55) = v20;
            *((_QWORD *)&v53 + 1) = *(_QWORD *)(*(_QWORD *)(v21 + 8 * v14) + 128LL);
            LODWORD(v53) = v20;
            started = I_CreateTransformChainEngine(
                        *(_QWORD *)(v19 + 16),
                        1,
                        (unsigned int)*(_QWORD *)(*(_QWORD *)(v19 + 32) + 8 * v14) + 40,
                        (unsigned int)&v54,
                        (__int64)&v58);
            if ( started < 0 )
            {
              v33 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v33, 855);
            }
            else
            {
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 32LL) + 8 * v14) + 120LL) = 0;
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 32LL) + 8 * v14) + 124LL) = 0;
              while ( 1 )
              {
                v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 32LL) + 8 * v14);
                started = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, int *))v59)(
                            v58,
                            *(_QWORD *)(v22 + 128) + *(unsigned int *)(v22 + 124),
                            v20 - *(_DWORD *)(v22 + 124),
                            &v51[1]);
                if ( started < 0 )
                  break;
                LODWORD(v13) = v51[1];
                if ( !v51[1] )
                  goto LABEL_13;
                v23 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 32LL) + 8 * v14);
                *(_DWORD *)(v23 + 124) += v51[1];
                v24 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 32LL) + 8 * v14);
                v25 = *(_DWORD *)(v24 + 124);
                if ( v25 > v20 )
                {
                  v20 = (v25 & 0xFFFFFC00) + 1024;
                  v26 = HeapReAlloc(*(HANDLE *)(*(_QWORD *)(v24 + 8) + 48LL), 0, *(LPVOID *)(v24 + 128), v20);
                  if ( !v26 )
                  {
                    started = -2147024882;
                    v31 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
                    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v31, 900);
                    goto LABEL_63;
                  }
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 32LL) + 8 * v14) + 128LL) = v26;
                }
              }
              v32 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v32, 875);
            }
            goto LABEL_63;
          }
        }
        started = WsReadNode(*(WS_XML_READER **)(v2 + 8), *(WS_ERROR **)v2);
      }
      while ( started >= 0 );
      v27 = "";
      while ( 1 )
      {
        v28 = *(v27 - 1);
        v29 = v27--;
        v30 = v28 == 92;
        if ( v28 == 92 )
          break;
        if ( v27 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
        {
          v30 = v28 == 92;
          break;
        }
      }
      if ( v30 )
        v27 = v29;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v27, 916);
    }
  }
  else
  {
    v9 = "";
    while ( 1 )
    {
      v10 = *(v9 - 1);
      v11 = v9--;
      v12 = v10 == 92;
      if ( v10 == 92 )
        break;
      if ( v9 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
      {
        v12 = v10 == 92;
        break;
      }
    }
    if ( v12 )
      v9 = v11;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", started, v9, 734);
  }
LABEL_63:
  if ( *((_QWORD *)&v59 + 1) )
    (*((void (__fastcall **)(_QWORD))&v59 + 1))(v58);
  if ( started < 0 && *(_QWORD *)v2 )
    I_TraceWsError(*(struct _WS_ERROR **)v2, (int)v13);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000c990  mov     r11, rsp
0x18000c993  push    rbp
0x18000c994  push    rbx
0x18000c995  push    rdi
0x18000c996  lea     rbp, [r11-38h]
0x18000c99a  sub     rsp, 120h
0x18000c9a1  mov     rax, cs:__security_cookie
0x18000c9a8  xor     rax, rsp
0x18000c9ab  mov     [rbp+30h+var_40], rax
0x18000c9af  mov     rdi, [rcx+98h]
0x18000c9b6  lea     rax, [rsp+130h+var_E8+8]
0x18000c9bb  mov     [rsp+130h+var_D0], rax
0x18000c9c0  xorps   xmm0, xmm0
0x18000c9c3  mov     [r11+18h], rsi
0x18000c9c7  lea     rax, I_CRYPT_XML_C14N_DATA_PROVIDER_READ_0
0x18000c9ce  movups  [rbp+30h+var_B0], xmm0
0x18000c9d2  mov     [rsp+130h+var_C0], rax
0x18000c9d7  lea     rax, I_CRYPT_XML_TRANSFORM_C14N_PROVIDER_CLOSE_0
0x18000c9de  movups  [rbp+30h+var_A0], xmm0
0x18000c9e2  mov     [r11-20h], r12
0x18000c9e6  xor     r12d, r12d
0x18000c9e9  mov     [rsp+130h+found], r12d
0x18000c9ee  xor     r9d, r9d; propertyCount
0x18000c9f1  movups  [rsp+130h+var_E8+8], xmm0
0x18000c9f6  mov     [rsp+130h+var_B8], rax
0x18000c9fb  xor     r8d, r8d; properties
0x18000c9fe  mov     rax, [rdi]
0x18000ca01  mov     [r11-38h], r15
0x18000ca05  mov     r15, rcx
0x18000ca08  mov     rcx, [rdi+8]; reader
0x18000ca0c  mov     esi, edx
0x18000ca0e  mov     rdx, [rdi+28h]; buffer
0x18000ca12  mov     [rsp+130h+error], rax; error
0x18000ca17  mov     [rsp+130h+var_C8], r12
0x18000ca1c  call    cs:__imp_WsSetInputToBuffer
0x18000ca23  nop     dword ptr [rax+rax+00h]
0x18000ca28  mov     ebx, eax
0x18000ca2a  test    eax, eax
0x18000ca2c  jns     short loc_18000CA6F
0x18000ca2e  lea     r8, aOnecoreDsSecur_5+30h; ""
0x18000ca35  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ca3c  movzx   eax, byte ptr [r8-1]
0x18000ca41  mov     rdx, r8
0x18000ca44  dec     r8
0x18000ca47  cmp     al, 5Ch ; '\'
0x18000ca49  jz      short loc_18000CA52
0x18000ca4b  cmp     r8, rcx
0x18000ca4e  ja      short loc_18000CA3C
0x18000ca50  cmp     al, 5Ch ; '\'
0x18000ca52  cmovz   r8, rdx
0x18000ca56  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ca5d  mov     edx, ebx
0x18000ca5f  mov     r9d, 2DEh
0x18000ca65  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ca6a  jmp     loc_18000CF46
0x18000ca6f  mov     rax, [rdi+48h]
0x18000ca73  lea     rcx, [rsi+rsi*4]
0x18000ca77  lea     rdx, [rax+rcx*8]; nodePosition
0x18000ca7b  mov     [rsp+130h+var_28], r14
0x18000ca83  mov     r14, rsi
0x18000ca86  cmp     [rdx], r12
0x18000ca89  jz      short loc_18000CACC
0x18000ca8b  mov     r8, [rdi]; error
0x18000ca8e  mov     rcx, [rdi+8]; reader
0x18000ca92  call    cs:__imp_WsSetReaderPosition
0x18000ca99  nop     dword ptr [rax+rax+00h]
0x18000ca9e  mov     ebx, eax
0x18000caa0  test    eax, eax
0x18000caa2  jns     short loc_18000CACC
0x18000caa4  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000caab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000cab0  mov     r8, rax
0x18000cab3  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000caba  mov     edx, ebx
0x18000cabc  mov     r9d, 2F0h
0x18000cac2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000cac7  jmp     loc_18000CF3E
0x18000cacc  mov     [rsp+130h+var_20], r13
0x18000cad4  lea     r13, CRYPT_XML_SIGNEDINFO_CANONICAL_CALLBACK
0x18000cadb  mov     [rsp+130h+found], r12d
0x18000cae0  cmp     [rsp+130h+found], r12d
0x18000cae5  jnz     loc_18000CF33
0x18000caeb  mov     rax, [rdi]
0x18000caee  lea     r9, [rsp+130h+found]; found
0x18000caf3  mov     rcx, [rdi+8]; reader
0x18000caf7  lea     r8, ?WS_XML_DIGSIG_NS@@3U_WS_XML_STRING@@B; ns
0x18000cafe  lea     rdx, ?WS_XML_DIGSIG_SignedInfo@@3U_WS_XML_STRING@@B; localName
0x18000cb05  mov     [rsp+130h+error], rax; error
0x18000cb0a  call    cs:__imp_WsReadToStartElement
0x18000cb11  nop     dword ptr [rax+rax+00h]
0x18000cb16  mov     ebx, eax
0x18000cb18  test    eax, eax
0x18000cb1a  js      loc_18000CF0E
0x18000cb20  cmp     [rsp+130h+found], r12d
0x18000cb25  jz      loc_18000CD4E
0x18000cb2b  mov     rdx, [r15+88h]; struct _CRYPT_XML_PROPERTY *
0x18000cb32  lea     r9, [rbp+30h+properties]; struct _WS_XML_CANONICALIZATION_PROPERTY *
0x18000cb36  mov     [rsp+130h+writeCallbackState], r12
0x18000cb3b  mov     qword ptr [rsp+130h+var_E8], r13
0x18000cb40  mov     [rsp+130h+var_F8], r12d
0x18000cb45  mov     rax, [rdx+20h]
0x18000cb49  mov     [rsp+130h+propertyCount], 3
0x18000cb51  mov     rcx, [rax+r14*8]
0x18000cb55  mov     [rsp+130h+writeCallbackState], rcx
0x18000cb5a  mov     rax, [rdx+20h]
0x18000cb5e  mov     rcx, [rax+r14*8]
0x18000cb62  lea     rax, [rsp+130h+var_F8]
0x18000cb67  mov     [rsp+130h+var_108], rax; int *
0x18000cb6c  add     rcx, 28h ; '('; struct _CRYPT_XML_ALGORITHM *
0x18000cb70  lea     rax, [rsp+130h+propertyCount]
0x18000cb75  mov     [rsp+130h+error], rax; unsigned int *
0x18000cb7a  call    ?I_CryptXmlGetCanonPropertiesForWsReader@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEBU_CRYPT_XML_PROPERTY@@KPEAU_WS_XML_CANONICALIZATION_PROPERTY@@PEAKPEAH@Z; I_CryptXmlGetCanonPropertiesForWsReader(_CRYPT_XML_ALGORITHM const *,_CRYPT_XML_PROPERTY const *,ulong,_WS_XML_CANONICALIZATION_PROPERTY *,ulong *,int *)
0x18000cb7f  mov     ebx, eax
0x18000cb81  test    eax, eax
0x18000cb83  js      loc_18000CED0
0x18000cb89  mov     rax, [rdi]
0x18000cb8c  lea     r9, [rbp+30h+properties]; properties
0x18000cb90  mov     rcx, [rdi+8]; reader
0x18000cb94  lea     r8, [rsp+130h+writeCallbackState]; writeCallbackState
0x18000cb99  mov     [rsp+130h+var_108], rax; error
0x18000cb9e  lea     rdx, ?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z; writeCallback
0x18000cba5  mov     eax, [rsp+130h+propertyCount]
0x18000cba9  mov     dword ptr [rsp+130h+error], eax; propertyCount
0x18000cbad  call    cs:__imp_WsStartReaderCanonicalization
0x18000cbb4  nop     dword ptr [rax+rax+00h]
0x18000cbb9  mov     ebx, eax
0x18000cbbb  test    eax, eax
0x18000cbbd  js      loc_18000CE92
0x18000cbc3  mov     rdx, [rdi]; error
0x18000cbc6  mov     rcx, [rdi+8]; reader
0x18000cbca  call    cs:__imp_WsSkipNode
0x18000cbd1  nop     dword ptr [rax+rax+00h]
0x18000cbd6  mov     ebx, eax
0x18000cbd8  test    eax, eax
0x18000cbda  js      loc_18000CE51
0x18000cbe0  mov     rdx, [rdi]; error
0x18000cbe3  mov     rcx, [rdi+8]; reader
0x18000cbe7  call    cs:__imp_WsEndReaderCanonicalization
0x18000cbee  nop     dword ptr [rax+rax+00h]
0x18000cbf3  mov     ebx, eax
0x18000cbf5  test    eax, eax
0x18000cbf7  js      loc_18000CE29
0x18000cbfd  cmp     [rsp+130h+var_F8], r12d
0x18000cc02  jz      loc_18000CAE0
0x18000cc08  mov     r10, [r15+88h]
0x18000cc0f  lea     r9, [rsp+130h+var_D0]
0x18000cc14  mov     rax, [r10+20h]
0x18000cc18  mov     rcx, [rax+r14*8]
0x18000cc1c  mov     esi, [rcx+7Ch]
0x18000cc1f  mov     [rsp+130h+var_F8+4], r12d
0x18000cc24  mov     rax, [r10+20h]
0x18000cc28  mov     dword ptr [rsp+130h+var_C8], esi
0x18000cc2c  mov     rdx, [rax+r14*8]
0x18000cc30  mov     rax, [rdx+80h]
0x18000cc37  mov     edx, 1
0x18000cc3c  mov     [rsp+130h+var_D8], rax
0x18000cc41  mov     dword ptr [rsp+130h+var_E8+8], esi
0x18000cc45  mov     rax, [r10+20h]
0x18000cc49  mov     rcx, [r10+10h]
0x18000cc4d  mov     r8, [rax+r14*8]
0x18000cc51  lea     rax, [rbp+30h+var_B0]
0x18000cc55  add     r8, 28h ; '('
0x18000cc59  mov     [rsp+130h+error], rax
0x18000cc5e  call    I_CreateTransformChainEngine
0x18000cc63  mov     ebx, eax
0x18000cc65  test    eax, eax
0x18000cc67  js      loc_18000CE01
0x18000cc6d  mov     rax, [r15+88h]
0x18000cc74  mov     rcx, [rax+20h]
0x18000cc78  mov     rax, [rcx+r14*8]
0x18000cc7c  mov     [rax+78h], r12d
0x18000cc80  mov     rax, [r15+88h]
0x18000cc87  mov     rcx, [rax+20h]
0x18000cc8b  mov     rax, [rcx+r14*8]
0x18000cc8f  mov     [rax+7Ch], r12d
0x18000cc93  mov     rcx, [r15+88h]
0x18000cc9a  lea     r9, [rsp+130h+var_F8+4]
0x18000cc9f  mov     rax, qword ptr [rbp+30h+var_A0]
0x18000cca3  mov     r8d, esi
0x18000cca6  mov     rdx, [rcx+20h]
0x18000ccaa  mov     rcx, [rdx+r14*8]
0x18000ccae  mov     edx, [rcx+7Ch]
0x18000ccb1  sub     r8d, edx
0x18000ccb4  add     rdx, [rcx+80h]
0x18000ccbb  mov     rcx, qword ptr [rbp+30h+var_B0]
0x18000ccbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc4  mov     ebx, eax
0x18000ccc6  test    eax, eax
0x18000ccc8  js      loc_18000CDD9
0x18000ccce  mov     edx, [rsp+130h+var_F8+4]
0x18000ccd2  test    edx, edx
0x18000ccd4  jz      loc_18000CAE0
0x18000ccda  mov     rax, [r15+88h]
0x18000cce1  mov     rcx, [rax+20h]
0x18000cce5  mov     rax, [rcx+r14*8]
0x18000cce9  add     [rax+7Ch], edx
0x18000ccec  mov     rax, [r15+88h]
0x18000ccf3  mov     rcx, [rax+20h]
0x18000ccf7  mov     r8, [rcx+r14*8]
0x18000ccfb  mov     eax, [r8+7Ch]
0x18000ccff  cmp     eax, esi
0x18000cd01  jbe     short loc_18000CC93
0x18000cd03  mov     rcx, [r8+8]
0x18000cd07  and     eax, 0FFFFFC00h
0x18000cd0c  mov     r8, [r8+80h]; lpMem
0x18000cd13  xor     edx, edx; dwFlags
0x18000cd15  mov     rcx, [rcx+30h]; hHeap
0x18000cd19  lea     esi, [rax+400h]
0x18000cd1f  mov     r9d, esi; dwBytes
0x18000cd22  call    cs:__imp_HeapReAlloc
0x18000cd29  nop     dword ptr [rax+rax+00h]
0x18000cd2e  test    rax, rax
0x18000cd31  jz      short loc_18000CDAC
0x18000cd33  mov     rcx, [r15+88h]
0x18000cd3a  mov     rdx, [rcx+20h]
0x18000cd3e  mov     rcx, [rdx+r14*8]
0x18000cd42  mov     [rcx+80h], rax
0x18000cd49  jmp     loc_18000CC93
0x18000cd4e  mov     rdx, [rdi]; error
0x18000cd51  mov     rcx, [rdi+8]; reader
0x18000cd55  call    cs:__imp_WsReadNode
0x18000cd5c  nop     dword ptr [rax+rax+00h]
0x18000cd61  mov     ebx, eax
0x18000cd63  test    eax, eax
0x18000cd65  jns     loc_18000CAE0
0x18000cd6b  lea     r8, aOnecoreDsSecur_5+30h; ""
0x18000cd72  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000cd79  movzx   eax, byte ptr [r8-1]
0x18000cd7e  mov     rdx, r8
0x18000cd81  dec     r8
0x18000cd84  cmp     al, 5Ch ; '\'
0x18000cd86  jz      short loc_18000CD8F
0x18000cd88  cmp     r8, rcx
0x18000cd8b  ja      short loc_18000CD79
0x18000cd8d  cmp     al, 5Ch ; '\'
0x18000cd8f  cmovz   r8, rdx
0x18000cd93  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000cd9a  mov     edx, ebx
0x18000cd9c  mov     r9d, 394h
0x18000cda2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000cda7  jmp     loc_18000CF36
0x18000cdac  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000cdb3  mov     ebx, 8007000Eh
0x18000cdb8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000cdbd  mov     r8, rax
0x18000cdc0  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000cdc7  mov     edx, ebx
0x18000cdc9  mov     r9d, 384h
0x18000cdcf  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000cdd4  jmp     loc_18000CF36
0x18000cdd9  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000cde0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000cde5  mov     r8, rax
0x18000cde8  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000cdef  mov     edx, ebx
0x18000cdf1  mov     r9d, 36Bh
0x18000cdf7  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000cdfc  jmp     loc_18000CF36
0x18000ce01  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ce08  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ce0d  mov     r8, rax
0x18000ce10  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ce17  mov     edx, ebx
0x18000ce19  mov     r9d, 357h
0x18000ce1f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ce24  jmp     loc_18000CF36
0x18000ce29  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ce30  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ce35  mov     r8, rax
0x18000ce38  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ce3f  mov     edx, ebx
0x18000ce41  mov     r9d, 33Dh
0x18000ce47  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ce4c  jmp     loc_18000CF36
0x18000ce51  lea     r8, aOnecoreDsSecur_5+30h; ""
0x18000ce58  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ce5f  movzx   eax, byte ptr [r8-1]
0x18000ce64  mov     rdx, r8
0x18000ce67  dec     r8
0x18000ce6a  cmp     al, 5Ch ; '\'
0x18000ce6c  jz      short loc_18000CE75
0x18000ce6e  cmp     r8, rcx
0x18000ce71  ja      short loc_18000CE5F
0x18000ce73  cmp     al, 5Ch ; '\'
0x18000ce75  cmovz   r8, rdx
0x18000ce79  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ce80  mov     edx, ebx
0x18000ce82  mov     r9d, 333h
0x18000ce88  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ce8d  jmp     loc_18000CF36
0x18000ce92  lea     r8, aOnecoreDsSecur_5+30h; ""
0x18000ce99  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000cea0  movzx   eax, byte ptr [r8-1]
0x18000cea5  mov     rdx, r8
0x18000cea8  dec     r8
0x18000ceab  cmp     al, 5Ch ; '\'
0x18000cead  jz      short loc_18000CEB6
0x18000ceaf  cmp     r8, rcx
0x18000ceb2  ja      short loc_18000CEA0
0x18000ceb4  cmp     al, 5Ch ; '\'
  ... truncated ...
```
