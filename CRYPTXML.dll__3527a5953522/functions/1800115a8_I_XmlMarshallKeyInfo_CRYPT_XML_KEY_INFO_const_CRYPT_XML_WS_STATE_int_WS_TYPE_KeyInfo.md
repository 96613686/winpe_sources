# I_XmlMarshallKeyInfo(_CRYPT_XML_KEY_INFO const *,_CRYPT_XML_WS_STATE *,int,WS_TYPE_KeyInfo *)

- ea: `0x1800115a8`
- end: `0x180011a31`
- name: `?I_XmlMarshallKeyInfo@@YAJPEBU_CRYPT_XML_KEY_INFO@@PEAU_CRYPT_XML_WS_STATE@@HPEAUWS_TYPE_KeyInfo@@@Z`
- size: `1161`
- prototype: `int(const struct _CRYPT_XML_KEY_INFO *, struct _CRYPT_XML_WS_STATE *, int, struct WS_TYPE_KeyInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c75c`

## callees

- `0x1800070d0`
- `0x1800115a8`
- `0x180011a40`
- `0x180014ce0`
- `0x180017938`
- `0x180018625`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800115ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001182b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180011898`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800118da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800119ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800115ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001182b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180011898`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800118da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800119ea`
- `webservices!WsAlloc` at `0x180011611`
- `webservices!WsAlloc` at `0x180011712`
- `webservices!WsAlloc` at `0x180011611`
- `webservices!WsAlloc` at `0x180011712`

## string_xrefs

- `0x180011623`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800116de`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800117f1`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011924`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011980`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180011a17`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlMarshallKeyInfo(
        const struct _CRYPT_XML_KEY_INFO *a1,
        WS_HEAP **a2,
        int a3,
        struct WS_TYPE_KeyInfo *a4)
{
  int v5; // r13d
  LPCWSTR wszId; // rax
  void **v9; // rdi
  int v10; // ebx
  const char *v11; // r8
  int v12; // r9d
  void *v13; // rcx
  __int64 i; // r12
  __int64 v15; // rsi
  unsigned __int64 v16; // r14
  CRYPT_XML_KEY_INFO_ITEM *rgKeyInfo; // r9
  __int64 v18; // rax
  CRYPT_XML_KEY_INFO_ITEM *v19; // rdx
  __int64 v20; // r12
  __int64 v21; // r13
  __int64 v22; // rdx
  const char *v23; // rax
  bool v24; // zf
  __int64 v26; // rcx
  int v27; // [rsp+80h] [rbp+8h]
  int v28; // [rsp+88h] [rbp+10h]

  *(_OWORD *)a4 = 0;
  v5 = a3;
  *((_OWORD *)a4 + 1) = 0;
  wszId = a1->wszId;
  if ( wszId )
  {
    *((_QWORD *)a4 + 1) = wszId;
    *(_DWORD *)a4 = lstrlenW(a1->wszId);
  }
  v9 = (void **)((char *)a4 + 24);
  v10 = WsAlloc(a2[6], 160LL * a1->cKeyInfo, (void **)a4 + 3, *a2);
  if ( v10 >= 0 )
  {
    v13 = *v9;
    *((_DWORD *)a4 + 4) = a1->cKeyInfo;
    memset_0(v13, 0, 160LL * a1->cKeyInfo);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v28 = i;
      if ( (unsigned int)i >= a1->cKeyInfo )
        return (unsigned int)v10;
      v15 = 160 * i;
      v16 = (unsigned __int64)(unsigned int)i << 7;
      *((_DWORD *)*v9 + 40 * i) = *(DWORD *)((char *)&a1->rgKeyInfo->dwType + v16);
      rgKeyInfo = a1->rgKeyInfo;
      switch ( *(DWORD *)((char *)&rgKeyInfo->dwType + v16) )
      {
        case 1u:
          v26 = *(__int64 *)((char *)&rgKeyInfo->wszKeyName + v16);
          if ( v26 )
          {
            *(_QWORD *)((char *)*v9 + v15 + 16) = v26;
            *(_DWORD *)((char *)*v9 + v15 + 8) = lstrlenW(*(LPCWSTR *)((char *)&a1->rgKeyInfo->wszKeyName + v16));
          }
          break;
        case 2u:
          v10 = I_XmlMarshallKeyValue(
                  (const struct _CRYPT_XML_KEY_VALUE *)((char *)&rgKeyInfo->wszKeyName + v16),
                  a2[1],
                  a2[2],
                  a2[6],
                  *a2,
                  v5,
                  (struct WS_TYPE_KeyValue *)((char *)*v9 + v15 + 8));
          if ( v10 >= 0 )
            continue;
          v11 = "";
          while ( 1 )
          {
            v23 = v11--;
            v24 = *v11 == 92;
            if ( *v11 == 92 )
              break;
            if ( v11 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
            {
              v24 = *v11 == 92;
              break;
            }
          }
          if ( v24 )
            v11 = v23;
          v12 = 3082;
          goto LABEL_39;
        case 3u:
          v10 = I_XmlSetEncoded(
                  (const struct _CRYPT_XML_BLOB *)((char *)&rgKeyInfo->wszKeyName + v16),
                  (struct _CRYPT_XML_WS_STATE *)a2,
                  (struct _WS_XML_BUFFER **)((char *)*v9 + v15 + 8));
          if ( v10 >= 0 )
            continue;
          v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
          v12 = 3095;
          goto LABEL_39;
        case 4u:
          v10 = WsAlloc(
                  a2[6],
                  56LL * *(unsigned int *)((char *)&rgKeyInfo->KeyValue.dwType + v16),
                  (void **)((char *)*v9 + v15 + 16),
                  *a2);
          if ( v10 < 0 )
          {
            v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
            v12 = 3110;
            goto LABEL_39;
          }
          *(_DWORD *)((char *)*v9 + v15 + 8) = *(DWORD *)((char *)&a1->rgKeyInfo->KeyValue.dwType + v16);
          memset_0(
            *(void **)((char *)*v9 + v15 + 16),
            0,
            56LL * *(unsigned int *)((char *)&a1->rgKeyInfo->KeyValue.dwType + v16));
          v18 = 0;
LABEL_16:
          v19 = a1->rgKeyInfo;
          v27 = v18;
          if ( (unsigned int)v18 >= *(DWORD *)((char *)&v19->KeyValue.dwType + v16) )
          {
            LODWORD(i) = v28;
            v5 = a3;
            continue;
          }
          v20 = 3 * v18;
          v21 = 56 * v18;
          *(_DWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + 56 * v18) = *(_DWORD *)&(*(LPCWSTR *)((char *)&v19->KeyValue.ECDSAKeyValue.wszNamedCurve
                                                                                                + v16))[12 * v18];
          v22 = *(__int64 *)((char *)&a1->rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v16);
          if ( *(_DWORD *)(v22 + 24 * v18) == 1 )
          {
            *(_QWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 16) = *(_QWORD *)(v22 + 24 * v18 + 8);
            *(_DWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 8) = lstrlenW(*(LPCWSTR *)&(*(LPCWSTR *)((char *)&a1->rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v16))[12 * v18 + 4]);
            *(_QWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 32) = *(_QWORD *)&(*(LPCWSTR *)((char *)&a1->rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve
                                                                                                  + v16))[4 * v20 + 8];
            *(_DWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 24) = lstrlenW(*(LPCWSTR *)&(*(LPCWSTR *)((char *)&a1->rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v16))[4 * v20 + 8]);
          }
          else
          {
            if ( *(_DWORD *)(v22 + 24 * v18) == 2 )
              goto LABEL_26;
            if ( *(_DWORD *)(v22 + 24 * v18) == 3 )
            {
              *(_QWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 16) = *(_QWORD *)(v22 + 24 * v18 + 8);
              *(_DWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 8) = lstrlenW(*(LPCWSTR *)&(*(LPCWSTR *)((char *)&a1->rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v16))[12 * v18 + 4]);
            }
            else
            {
              if ( *(_DWORD *)(v22 + 24 * v18) != 4 && *(_DWORD *)(v22 + 24 * v18) != 5 )
              {
                if ( *(_DWORD *)(v22 + 24 * v18) == 6 )
                {
                  v10 = I_XmlSetEncoded(
                          (const struct _CRYPT_XML_BLOB *)(v22 + 8 + 24 * v18),
                          (struct _CRYPT_XML_WS_STATE *)a2,
                          (struct _WS_XML_BUFFER **)(v21 + *(_QWORD *)((char *)*v9 + v15 + 16) + 8LL));
                  if ( v10 < 0 )
                  {
                    v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
                    v12 = 3167;
                    goto LABEL_39;
                  }
                }
                goto LABEL_28;
              }
LABEL_26:
              *(_QWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 16) = *(_QWORD *)(v22 + 24 * v18 + 16);
              *(_DWORD *)(*(_QWORD *)((char *)*v9 + v15 + 16) + v21 + 8) = *(_DWORD *)&(*(LPCWSTR *)((char *)&a1->rgKeyInfo->KeyValue.ECDSAKeyValue.wszNamedCurve + v16))[12 * v18 + 4];
            }
          }
LABEL_28:
          v18 = (unsigned int)(v27 + 1);
          goto LABEL_16;
        case 5u:
          v10 = I_XmlSetEncoded(
                  (const struct _CRYPT_XML_BLOB *)((char *)&rgKeyInfo->wszKeyName + v16),
                  (struct _CRYPT_XML_WS_STATE *)a2,
                  (struct _WS_XML_BUFFER **)((char *)*v9 + v15 + 8));
          if ( v10 < 0 )
          {
            v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
            v12 = 3183;
            goto LABEL_39;
          }
          break;
      }
    }
  }
  v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
  v12 = 3048;
LABEL_39:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v10, v11, v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800115a8  mov     [rsp+arg_18], rbx
0x1800115ad  mov     [rsp+arg_10], r8d
0x1800115b2  push    rbp
0x1800115b3  push    rsi
0x1800115b4  push    rdi
0x1800115b5  push    r12
0x1800115b7  push    r13
0x1800115b9  push    r14
0x1800115bb  push    r15
0x1800115bd  sub     rsp, 40h
0x1800115c1  xorps   xmm0, xmm0
0x1800115c4  mov     rsi, r9
0x1800115c7  movups  xmmword ptr [r9], xmm0
0x1800115cb  mov     r13d, r8d
0x1800115ce  mov     r15, rdx
0x1800115d1  movups  xmmword ptr [r9+10h], xmm0
0x1800115d6  mov     rax, [rcx+8]
0x1800115da  mov     rbp, rcx
0x1800115dd  test    rax, rax
0x1800115e0  jz      short loc_1800115F8
0x1800115e2  mov     [r9+8], rax
0x1800115e6  mov     rcx, [rcx+8]; lpString
0x1800115ea  call    cs:__imp_lstrlenW
0x1800115f1  nop     dword ptr [rax+rax+00h]
0x1800115f6  mov     [rsi], eax
0x1800115f8  mov     eax, [rbp+10h]
0x1800115fb  lea     rdi, [rsi+18h]
0x1800115ff  mov     r9, [r15]; error
0x180011602  mov     r8, rdi; ptr
0x180011605  mov     rcx, [r15+30h]; heap
0x180011609  lea     rdx, [rax+rax*4]
0x18001160d  shl     rdx, 5; size
0x180011611  call    cs:__imp_WsAlloc
0x180011618  nop     dword ptr [rax+rax+00h]
0x18001161d  mov     ebx, eax
0x18001161f  test    eax, eax
0x180011621  jns     short loc_18001163D
0x180011623  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001162a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001162f  mov     r8, rax
0x180011632  mov     r9d, 0BE8h
0x180011638  jmp     loc_1800119A6
0x18001163d  mov     eax, [rbp+10h]
0x180011640  xor     edx, edx; Val
0x180011642  mov     rcx, [rdi]; void *
0x180011645  mov     [rsi+10h], eax
0x180011648  mov     eax, [rbp+10h]
0x18001164b  lea     r8, [rax+rax*4]
0x18001164f  shl     r8, 5; Size
0x180011653  call    memset_0
0x180011658  xor     r12d, r12d
0x18001165b  mov     [rsp+78h+arg_8], r12d
0x180011663  cmp     r12d, [rbp+10h]
0x180011667  jnb     loc_1800119B4
0x18001166d  mov     rax, [rbp+18h]
0x180011671  lea     rsi, [r12+r12*4]
0x180011675  mov     rcx, [rdi]
0x180011678  shl     rsi, 5
0x18001167c  mov     r14d, r12d
0x18001167f  shl     r14, 7
0x180011683  mov     eax, [r14+rax]
0x180011687  mov     [rsi+rcx], eax
0x18001168a  mov     r9, [rbp+18h]
0x18001168e  mov     ecx, [r14+r9]
0x180011692  sub     ecx, 1
0x180011695  jz      loc_1800119CF
0x18001169b  sub     ecx, 1
0x18001169e  jz      loc_18001193B
0x1800116a4  sub     ecx, 1
0x1800116a7  jz      loc_180011901
0x1800116ad  sub     ecx, 1
0x1800116b0  jz      short loc_1800116F8
0x1800116b2  cmp     ecx, 1
0x1800116b5  jnz     loc_180011A0F
0x1800116bb  mov     r8, [rdi]
0x1800116be  lea     rcx, [r9+8]
0x1800116c2  add     r8, 8
0x1800116c6  add     rcx, r14; struct _CRYPT_XML_BLOB *
0x1800116c9  add     r8, rsi; struct _WS_XML_BUFFER **
0x1800116cc  mov     rdx, r15; struct _CRYPT_XML_WS_STATE *
0x1800116cf  call    ?I_XmlSetEncoded@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncoded(_CRYPT_XML_BLOB const *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER * *)
0x1800116d4  mov     ebx, eax
0x1800116d6  test    eax, eax
0x1800116d8  jns     loc_180011A0F
0x1800116de  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800116e5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800116ea  mov     r8, rax
0x1800116ed  mov     r9d, 0C6Fh
0x1800116f3  jmp     loc_1800119A6
0x1800116f8  mov     eax, [r14+r9+8]
0x1800116fd  mov     r8, [rdi]
0x180011700  mov     r9, [r15]; error
0x180011703  add     r8, 10h
0x180011707  mov     rcx, [r15+30h]; heap
0x18001170b  add     r8, rsi; ptr
0x18001170e  imul    rdx, rax, 38h ; '8'; size
0x180011712  call    cs:__imp_WsAlloc
0x180011719  nop     dword ptr [rax+rax+00h]
0x18001171e  mov     ebx, eax
0x180011720  test    eax, eax
0x180011722  js      loc_180011A17
0x180011728  mov     rax, [rbp+18h]
0x18001172c  xor     edx, edx; Val
0x18001172e  mov     rcx, [rdi]
0x180011731  mov     eax, [r14+rax+8]
0x180011736  mov     [rcx+rsi+8], eax
0x18001173a  mov     rax, [rbp+18h]
0x18001173e  mov     ecx, [r14+rax+8]
0x180011743  imul    r8, rcx, 38h ; '8'; Size
0x180011747  mov     rcx, [rdi]
0x18001174a  mov     rcx, [rcx+rsi+10h]; void *
0x18001174f  call    memset_0
0x180011754  xor     eax, eax
0x180011756  mov     rdx, [rbp+18h]
0x18001175a  mov     [rsp+78h+arg_0], eax
0x180011761  cmp     eax, [r14+rdx+8]
0x180011766  jnb     loc_1800119FF
0x18001176c  mov     rdx, [r14+rdx+10h]
0x180011771  lea     r12, [rax+rax*2]
0x180011775  imul    r13, rax, 38h ; '8'
0x180011779  mov     rax, [rdi]
0x18001177c  mov     rcx, [rax+rsi+10h]
0x180011781  mov     eax, [rdx+r12*8]
0x180011785  mov     [rcx+r13], eax
0x180011789  mov     rax, [rbp+18h]
0x18001178d  mov     rdx, [r14+rax+10h]
0x180011792  mov     ecx, [rdx+r12*8]
0x180011796  sub     ecx, 1
0x180011799  jz      loc_180011878
0x18001179f  sub     ecx, 1
0x1800117a2  jz      loc_180011849
0x1800117a8  sub     ecx, 1
0x1800117ab  jz      short loc_18001180B
0x1800117ad  sub     ecx, 1
0x1800117b0  jz      loc_180011849
0x1800117b6  sub     ecx, 1
0x1800117b9  jz      loc_180011849
0x1800117bf  cmp     ecx, 1
0x1800117c2  jnz     loc_1800118F3
0x1800117c8  mov     rax, [rdi]
0x1800117cb  lea     rcx, [rdx+8]
0x1800117cf  lea     rcx, [rcx+r12*8]; struct _CRYPT_XML_BLOB *
0x1800117d3  mov     rdx, r15; struct _CRYPT_XML_WS_STATE *
0x1800117d6  mov     r8, [rax+rsi+10h]
0x1800117db  add     r8, 8
0x1800117df  add     r8, r13; struct _WS_XML_BUFFER **
0x1800117e2  call    ?I_XmlSetEncoded@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncoded(_CRYPT_XML_BLOB const *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER * *)
0x1800117e7  mov     ebx, eax
0x1800117e9  test    eax, eax
0x1800117eb  jns     loc_1800118F3
0x1800117f1  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800117f8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800117fd  mov     r8, rax
0x180011800  mov     r9d, 0C5Fh
0x180011806  jmp     loc_1800119A6
0x18001180b  mov     rax, [rdi]
0x18001180e  mov     rcx, [rax+rsi+10h]
0x180011813  mov     rax, [rdx+r12*8+8]
0x180011818  mov     [rcx+r13+10h], rax
0x18001181d  mov     rax, [rbp+18h]
0x180011821  mov     rcx, [r14+rax+10h]
0x180011826  mov     rcx, [rcx+r12*8+8]; lpString
0x18001182b  call    cs:__imp_lstrlenW
0x180011832  nop     dword ptr [rax+rax+00h]
0x180011837  mov     rcx, [rdi]
0x18001183a  mov     rdx, [rcx+rsi+10h]
0x18001183f  mov     [rdx+r13+8], eax
0x180011844  jmp     loc_1800118F3
0x180011849  mov     rax, [rdi]
0x18001184c  mov     rcx, [rax+rsi+10h]
0x180011851  mov     rax, [rdx+r12*8+10h]
0x180011856  mov     [rcx+r13+10h], rax
0x18001185b  mov     rax, [rbp+18h]
0x18001185f  mov     rdx, [r14+rax+10h]
0x180011864  mov     rax, [rdi]
0x180011867  mov     rcx, [rax+rsi+10h]
0x18001186c  mov     eax, [rdx+r12*8+8]
0x180011871  mov     [rcx+r13+8], eax
0x180011876  jmp     short loc_1800118F3
0x180011878  mov     rax, [rdi]
0x18001187b  mov     rcx, [rax+rsi+10h]
0x180011880  mov     rax, [rdx+r12*8+8]
0x180011885  mov     [rcx+r13+10h], rax
0x18001188a  mov     rax, [rbp+18h]
0x18001188e  mov     rcx, [r14+rax+10h]
0x180011893  mov     rcx, [rcx+r12*8+8]; lpString
0x180011898  call    cs:__imp_lstrlenW
0x18001189f  nop     dword ptr [rax+rax+00h]
0x1800118a4  mov     rcx, [rdi]
0x1800118a7  mov     rdx, [rcx+rsi+10h]
0x1800118ac  mov     [rdx+r13+8], eax
0x1800118b1  mov     rax, [rbp+18h]
0x1800118b5  mov     rdx, [r14+rax+10h]
0x1800118ba  mov     rax, [rdi]
0x1800118bd  mov     rcx, [rax+rsi+10h]
0x1800118c2  mov     rax, [rdx+r12*8+10h]
0x1800118c7  mov     [rcx+r13+20h], rax
0x1800118cc  mov     rax, [rbp+18h]
0x1800118d0  mov     rcx, [r14+rax+10h]
0x1800118d5  mov     rcx, [rcx+r12*8+10h]; lpString
0x1800118da  call    cs:__imp_lstrlenW
0x1800118e1  nop     dword ptr [rax+rax+00h]
0x1800118e6  mov     rcx, [rdi]
0x1800118e9  mov     rdx, [rcx+rsi+10h]
0x1800118ee  mov     [rdx+r13+18h], eax
0x1800118f3  mov     eax, [rsp+78h+arg_0]
0x1800118fa  inc     eax
0x1800118fc  jmp     loc_180011756
0x180011901  mov     r8, [rdi]
0x180011904  lea     rcx, [r9+8]
0x180011908  add     r8, 8
0x18001190c  add     rcx, r14; struct _CRYPT_XML_BLOB *
0x18001190f  add     r8, rsi; struct _WS_XML_BUFFER **
0x180011912  mov     rdx, r15; struct _CRYPT_XML_WS_STATE *
0x180011915  call    ?I_XmlSetEncoded@@YAJPEBU_CRYPT_XML_BLOB@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_WS_XML_BUFFER@@@Z; I_XmlSetEncoded(_CRYPT_XML_BLOB const *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER * *)
0x18001191a  mov     ebx, eax
0x18001191c  test    eax, eax
0x18001191e  jns     loc_180011A0F
0x180011924  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001192b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011930  mov     r8, rax
0x180011933  mov     r9d, 0C17h
0x180011939  jmp     short loc_1800119A6
0x18001193b  mov     rdx, [rdi]
0x18001193e  lea     rcx, [r9+8]
0x180011942  mov     rax, [r15]
0x180011945  add     rdx, 8
0x180011949  mov     r9, [r15+30h]; struct _WS_HEAP *
0x18001194d  add     rdx, rsi
0x180011950  mov     r8, [r15+10h]; struct _WS_XML_WRITER *
0x180011954  add     rcx, r14; struct _CRYPT_XML_KEY_VALUE *
0x180011957  mov     [rsp+78h+var_48], rdx; struct WS_TYPE_KeyValue *
0x18001195c  mov     rdx, [r15+8]; struct _WS_XML_READER *
0x180011960  mov     [rsp+78h+var_50], r13d; int
0x180011965  mov     [rsp+78h+var_58], rax; struct _WS_ERROR *
0x18001196a  call    ?I_XmlMarshallKeyValue@@YAJPEBU_CRYPT_XML_KEY_VALUE@@PEAU_WS_XML_READER@@PEAU_WS_XML_WRITER@@PEAU_WS_HEAP@@PEAU_WS_ERROR@@HPEAUWS_TYPE_KeyValue@@@Z; I_XmlMarshallKeyValue(_CRYPT_XML_KEY_VALUE const *,_WS_XML_READER *,_WS_XML_WRITER *,_WS_HEAP *,_WS_ERROR *,int,WS_TYPE_KeyValue *)
0x18001196f  mov     ebx, eax
0x180011971  test    eax, eax
0x180011973  jns     loc_180011A0F
0x180011979  lea     r8, aOnecoreDsSecur_1+35h; ""
0x180011980  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011987  mov     rax, r8
0x18001198a  dec     r8
0x18001198d  cmp     byte ptr [r8], 5Ch ; '\'
0x180011991  jz      short loc_18001199C
0x180011993  cmp     r8, rcx
0x180011996  ja      short loc_180011987
0x180011998  cmp     byte ptr [r8], 5Ch ; '\'
0x18001199c  cmovz   r8, rax
0x1800119a0  mov     r9d, 0C0Ah
0x1800119a6  mov     edx, ebx
0x1800119a8  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800119af  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800119b4  mov     eax, ebx
0x1800119b6  mov     rbx, [rsp+78h+arg_18]
0x1800119be  add     rsp, 40h
0x1800119c2  pop     r15
0x1800119c4  pop     r14
0x1800119c6  pop     r13
0x1800119c8  pop     r12
0x1800119ca  pop     rdi
0x1800119cb  pop     rsi
0x1800119cc  pop     rbp
0x1800119cd  retn
0x1800119cf  mov     rcx, [r14+r9+8]
0x1800119d4  test    rcx, rcx
0x1800119d7  jz      short loc_180011A0F
0x1800119d9  mov     rax, [rdi]
0x1800119dc  mov     [rax+rsi+10h], rcx
0x1800119e1  mov     rcx, [rbp+18h]
0x1800119e5  mov     rcx, [r14+rcx+8]; lpString
0x1800119ea  call    cs:__imp_lstrlenW
0x1800119f1  nop     dword ptr [rax+rax+00h]
0x1800119f6  mov     rcx, [rdi]
0x1800119f9  mov     [rcx+rsi+8], eax
0x1800119fd  jmp     short loc_180011A0F
0x1800119ff  mov     r12d, [rsp+78h+arg_8]
0x180011a07  mov     r13d, [rsp+78h+arg_10]
0x180011a0f  inc     r12d
0x180011a12  jmp     loc_18001165B
0x180011a17  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011a1e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180011a23  mov     r8, rax
0x180011a26  mov     r9d, 0C26h
0x180011a2c  jmp     loc_1800119A6
```
