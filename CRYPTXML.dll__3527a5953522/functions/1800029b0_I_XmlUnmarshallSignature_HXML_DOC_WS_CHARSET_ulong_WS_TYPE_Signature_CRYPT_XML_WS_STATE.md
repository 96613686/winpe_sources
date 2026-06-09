# I_XmlUnmarshallSignature(_HXML_DOC *,WS_CHARSET,ulong,WS_TYPE_Signature *,_CRYPT_XML_WS_STATE *)

- ea: `0x1800029b0`
- end: `0x1800031a2`
- name: `?I_XmlUnmarshallSignature@@YAJPEAU_HXML_DOC@@W4WS_CHARSET@@KPEAUWS_TYPE_Signature@@PEAU_CRYPT_XML_WS_STATE@@@Z`
- size: `2034`
- prototype: `__int64 __fastcall(struct _HXML_DOC *, enum WS_CHARSET, unsigned int, struct WS_TYPE_Signature *, struct _CRYPT_XML_WS_STATE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002470`

## callees

- `0x180001010`
- `0x180001d00`
- `0x1800029b0`
- `0x1800031b0`
- `0x180004f60`
- `0x1800070d0`
- `0x1800110e0`
- `0x180014ce0`
- `0x180018625`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000311d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000311d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003147`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003171`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003005`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003135`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000315f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003005`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003135`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000315f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003189`

## string_xrefs

- `0x180002c2f`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180002ad3`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002b40`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002bc5`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002ccc`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002d40`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002e75`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002ecb`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002f80`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002fad`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180002fe0`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180003084`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800030ac`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlUnmarshallSignature(
        struct _HXML_DOC *a1,
        enum WS_CHARSET a2,
        unsigned int a3,
        struct WS_TYPE_Signature *a4,
        struct _CRYPT_XML_WS_STATE *a5)
{
  unsigned int v5; // edi
  int v9; // r9d
  unsigned int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // edx
  struct _CRYPT_XML_WS_STATE *v14; // r13
  int EncodedElement; // edi
  const char *v16; // r8
  int v17; // r9d
  const char *v18; // r12
  char v19; // cl
  const char *v20; // rdx
  bool v21; // zf
  void *v22; // rcx
  int v23; // eax
  __int64 v24; // rsi
  const char *v25; // r12
  char v26; // cl
  const char *v27; // rdx
  bool v28; // zf
  int v29; // r9d
  __int64 v30; // r15
  void (__fastcall *v31)(struct _HXML_DOC *); // rax
  __int64 v32; // r12
  const char *v33; // r8
  char v34; // al
  const char *v35; // rcx
  bool v36; // zf
  __int64 v37; // rdx
  int v38; // eax
  void (__fastcall *v39)(struct _HXML_DOC *); // rax
  const char *v40; // r8
  __int64 i; // r15
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  _DWORD *v45; // r15
  unsigned int v46; // edx
  unsigned int v47; // ecx
  __int64 v48; // rax
  const char *v49; // r8
  const char *v50; // rax
  const char *v51; // rax
  __int64 v52; // r8
  unsigned int v53; // eax
  const char *v54; // rax
  const char *v55; // r8
  const char *v56; // rax
  HANDLE ProcessHeap; // rax
  char v58; // al
  const char *v59; // rcx
  bool v60; // zf
  char v61; // cl
  const char *v62; // r8
  bool v63; // zf
  HANDLE v64; // rax
  HANDLE v65; // rax
  HANDLE v66; // rax
  int v68; // [rsp+40h] [rbp-C0h]
  __int64 v69; // [rsp+48h] [rbp-B8h]
  __int64 v70; // [rsp+48h] [rbp-B8h]
  HANDLE hHeap; // [rsp+50h] [rbp-B0h]
  __int64 v72; // [rsp+58h] [rbp-A8h]
  __int64 v73; // [rsp+60h] [rbp-A0h] BYREF
  int v74; // [rsp+68h] [rbp-98h]
  __int64 v75; // [rsp+70h] [rbp-90h]
  unsigned int v76; // [rsp+78h] [rbp-88h]
  __int64 v77; // [rsp+80h] [rbp-80h]
  unsigned int v78; // [rsp+88h] [rbp-78h]
  struct _CRYPT_XML_BLOB v79; // [rsp+90h] [rbp-70h] BYREF
  int v80; // [rsp+A0h] [rbp-60h]
  _DWORD *v81; // [rsp+A8h] [rbp-58h]
  __int64 v82; // [rsp+B0h] [rbp-50h] BYREF
  int v83; // [rsp+B8h] [rbp-48h]
  __int64 v84; // [rsp+D0h] [rbp-30h]
  unsigned int v85; // [rsp+D8h] [rbp-28h]
  struct _CRYPT_XML_BLOB v86; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v87; // [rsp+F0h] [rbp-10h]
  int v88; // [rsp+F8h] [rbp-8h]
  struct _CRYPT_XML_BLOB v89; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v90; // [rsp+110h] [rbp+10h]
  __int64 v91; // [rsp+118h] [rbp+18h]
  int v92; // [rsp+120h] [rbp+20h]
  int v93; // [rsp+12Ch] [rbp+2Ch]
  LPVOID v94; // [rsp+130h] [rbp+30h]
  int v95; // [rsp+138h] [rbp+38h]
  struct WS_TYPE_Signature *v96; // [rsp+140h] [rbp+40h]
  __int64 v99; // [rsp+1A8h] [rbp+A8h] BYREF

  v5 = a3;
  v99 = 0;
  memset_0(&v82, 0, 0x98u);
  v9 = *(_DWORD *)a4;
  if ( *(_DWORD *)a4 > 0x100u
    || (v10 = *((_DWORD *)a4 + 8), v10 > 0x2000)
    || (v11 = *((_DWORD *)a4 + 14), v11 > 0x2000)
    || (v12 = *((_DWORD *)a4 + 22), v12 > 0x7FF8)
    || (v13 = *((_DWORD *)a4 + 26), v13 > 0x800)
    || *((_DWORD *)a4 + 32) > 0x100u )
  {
    EncodedElement = -2146885375;
    v18 = "";
    while ( 1 )
    {
      v61 = *(v18 - 1);
      v62 = v18--;
      v63 = v61 == 92;
      if ( v61 == 92 )
        break;
      if ( v18 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
      {
        v63 = v61 == 92;
        break;
      }
    }
    if ( v63 )
      v18 = v62;
    v17 = 2174;
    goto LABEL_100;
  }
  if ( !v11 || !v13 )
  {
    EncodedElement = -2146885360;
    v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v17 = 2183;
    goto LABEL_101;
  }
  v21 = *((_QWORD *)a4 + 6) == 0;
  v14 = a5;
  v82 = *((_QWORD *)a4 + 1);
  v84 = *((_QWORD *)a4 + 5);
  v96 = a4;
  v83 = v9;
  v90 = v12;
  v85 = v10;
  if ( !v21 )
  {
    EncodedElement = I_XmlGetEncodedElement(
                       a2,
                       a5,
                       &CanonicalizationMethod_ElementDescription,
                       (char *)a4 + 32,
                       0x18u,
                       v5,
                       &v86);
    if ( EncodedElement < 0 )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v17 = 2213;
LABEL_101:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", EncodedElement, v16, v17);
      goto LABEL_102;
    }
    v5 = a3;
  }
  v21 = *((_QWORD *)a4 + 10) == 0;
  v87 = *((_QWORD *)a4 + 8);
  v88 = *((_DWORD *)a4 + 14);
  if ( !v21 )
  {
    EncodedElement = I_XmlGetEncodedElement(
                       a2,
                       v14,
                       &SignatureMethod_ElementDescription,
                       (char *)a4 + 56,
                       0x20u,
                       v5,
                       &v89);
    if ( EncodedElement < 0 )
    {
      v18 = "";
      while ( 1 )
      {
        v19 = *(v18 - 1);
        v20 = v18--;
        v21 = v19 == 92;
        if ( v19 == 92 )
          break;
        if ( v18 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
        {
          v21 = v19 == 92;
          break;
        }
      }
      if ( v21 )
        v18 = v20;
      v17 = 2235;
LABEL_100:
      v16 = v18;
      goto LABEL_101;
    }
  }
  v22 = (void *)*((_QWORD *)a1 + 6);
  v91 = *((_QWORD *)a4 + 14);
  v92 = *((_DWORD *)a4 + 26);
  v95 = *((_DWORD *)a4 + 32);
  v23 = I_CryptXmlHandleAllocSignature(v22, (__int64)&v99);
  v24 = v99;
  EncodedElement = v23;
  if ( v23 >= 0 )
  {
    v30 = *(_QWORD *)(v99 + 144);
    v31 = (void (__fastcall *)(struct _HXML_DOC *))*((_QWORD *)a1 + 15);
    v32 = *(_QWORD *)(v30 + 8);
    if ( v31 )
      v31(a1);
    if ( *(_DWORD *)(*((_QWORD *)a1 + 17) + 24LL) < *((_DWORD *)a1 + 36) )
    {
      EncodedElement = 0;
      *(_QWORD *)(v32 + 80) = a1;
      _InterlockedIncrement((volatile signed __int32 *)(v32 + 56));
      v37 = *((_QWORD *)a1 + 17);
      v38 = *(_DWORD *)(v37 + 24);
      if ( v38 )
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v37 + 32) + 8LL * (unsigned int)(v38 - 1)) + 8LL) + 96LL) = *(_QWORD *)(v30 + 8);
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 17) + 32LL)
                + 8LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)a1 + 17) + 24LL))++) = v30;
    }
    else
    {
      EncodedElement = -2146885375;
      v33 = "";
      while ( 1 )
      {
        v34 = *(v33 - 1);
        v35 = v33--;
        v36 = v34 == 92;
        if ( v34 == 92 )
          break;
        if ( v33 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
        {
          v36 = v34 == 92;
          break;
        }
      }
      if ( v36 )
        v33 = v35;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v33, 255);
    }
    v39 = (void (__fastcall *)(struct _HXML_DOC *))*((_QWORD *)a1 + 16);
    if ( v39 )
      v39(a1);
    if ( EncodedElement >= 0 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)a4 + 22); i = (unsigned int)(i + 1) )
      {
        EncodedElement = I_XmlUnmarshallReference(
                           *((HANDLE *)a1 + 6),
                           a2,
                           a3,
                           (struct WS_TYPE_Reference *)(*((_QWORD *)a4 + 12) + 104LL * (unsigned int)i),
                           v14,
                           *(struct _HXML_HANDLE **)(*(_QWORD *)(v24 + 144) + 8LL),
                           (const struct _CRYPT_XML_REFERENCE **)(*(_QWORD *)(*(_QWORD *)(v24 + 144) + 112LL) + 8 * i));
        if ( EncodedElement < 0 )
        {
          v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
          v29 = 2295;
          goto LABEL_89;
        }
      }
      v42 = 0;
      v25 = "";
      while ( 1 )
      {
        v68 = v42;
        if ( (unsigned int)v42 >= *((_DWORD *)a4 + 32) )
          goto LABEL_90;
        v43 = 9 * v42;
        v72 = v42;
        v44 = *((_QWORD *)a4 + 17);
        v99 = 0;
        v45 = (_DWORD *)(v44 + 8 * v43);
        memset_0(&v73, 0, 0x50u);
        if ( *v45 > 0x100u || (v46 = v45[4], v46 > 0x2000) || (v47 = v45[8], v47 > 0x2000) || v45[12] > 0x7FF8u )
        {
          EncodedElement = -2146885375;
          v55 = "";
          do
          {
            v56 = v55 - 1;
            if ( *(v55 - 1) == 92 )
              break;
            --v55;
          }
          while ( v56 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v55, 810);
        }
        else
        {
          v21 = *((_QWORD *)v45 + 8) == 0;
          v48 = *(_QWORD *)(v24 + 144);
          v74 = *v45;
          v76 = v46;
          v78 = v47;
          v69 = *(_QWORD *)(v48 + 168);
          hHeap = (HANDLE)*((_QWORD *)a1 + 6);
          v73 = *((_QWORD *)v45 + 1);
          v75 = *((_QWORD *)v45 + 3);
          v77 = *((_QWORD *)v45 + 5);
          v81 = v45;
          if ( v21 && (*((_DWORD *)a1 + 15) & 0x40000000) == 0
            || (EncodedElement = I_XmlGetEncodedElement(a2, v14, &Object_ElementDescription, v45, 0x48u, a3, &v79),
                EncodedElement >= 0) )
          {
            v80 = v45[12];
            EncodedElement = I_CryptXmlHandleAllocObject(hHeap);
            if ( EncodedElement >= 0 )
            {
              v52 = v69 + 8 * v72;
              v70 = v52;
              v53 = 0;
              *(_QWORD *)v52 = *(_QWORD *)(v99 + 136);
              while ( 1 )
              {
                LODWORD(v99) = v53;
                if ( v53 >= v45[12] )
                  break;
                EncodedElement = I_XmlUnmarshallReference(
                                   hHeap,
                                   a2,
                                   a3,
                                   (struct WS_TYPE_Reference *)(*((_QWORD *)v45 + 7) + 104LL * v53),
                                   v14,
                                   *(struct _HXML_HANDLE **)(*(_QWORD *)v52 + 8LL),
                                   (const struct _CRYPT_XML_REFERENCE **)(*(_QWORD *)(*(_QWORD *)v52 + 48LL) + 8LL * v53));
                if ( EncodedElement < 0 )
                {
                  v54 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
                  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", EncodedElement, v54, 874);
                  break;
                }
                v52 = v70;
                v53 = v99 + 1;
              }
            }
            else
            {
              v51 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u", EncodedElement, v51, 853);
            }
          }
          else
          {
            v49 = "";
            do
            {
              v50 = v49 - 1;
              if ( *(v49 - 1) == 92 )
                break;
              --v49;
            }
            while ( v50 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", EncodedElement, v49, 837);
          }
        }
        if ( v79.cbData )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 8u, v79.pbData);
        }
        if ( EncodedElement < 0 )
        {
          while ( 1 )
          {
            v58 = *(v25 - 1);
            v59 = v25--;
            v60 = v58 == 92;
            if ( v58 == 92 )
              break;
            if ( v25 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
            {
              v60 = v58 == 92;
              break;
            }
          }
          if ( v60 )
            v25 = v59;
          v29 = 2319;
          goto LABEL_88;
        }
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v24 + 144) + 168LL) + 8 * v72) + 8LL) + 80LL) = *(_QWORD *)(*(_QWORD *)(v24 + 144) + 8LL);
        v42 = (unsigned int)(v68 + 1);
      }
    }
    v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v29 = 2272;
  }
  else
  {
    if ( v99 )
      I_CryptXmlRelease(v99);
    v25 = "";
    while ( 1 )
    {
      v26 = *(v25 - 1);
      v27 = v25--;
      v28 = v26 == 92;
      if ( v26 == 92 )
        break;
      if ( v25 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
      {
        v28 = v26 == 92;
        break;
      }
    }
    if ( v28 )
      v25 = v27;
    v29 = 2258;
LABEL_88:
    v40 = v25;
  }
LABEL_89:
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", EncodedElement, v40, v29);
LABEL_90:
  if ( v24 )
    I_CryptXmlRelease(v24);
LABEL_102:
  if ( v93 )
  {
    v64 = GetProcessHeap();
    HeapFree(v64, 8u, v94);
  }
  if ( v86.cbData )
  {
    v65 = GetProcessHeap();
    HeapFree(v65, 8u, v86.pbData);
  }
  if ( v89.cbData )
  {
    v66 = GetProcessHeap();
    HeapFree(v66, 8u, v89.pbData);
  }
  return (unsigned int)EncodedElement;
}

```

## disassembly

```asm
0x1800029b0  mov     rax, rsp
0x1800029b3  mov     [rax+18h], r8d
0x1800029b7  mov     [rax+10h], edx
0x1800029ba  push    rbp
0x1800029bb  push    rdi
0x1800029bc  lea     rbp, [rsp-78h]
0x1800029c1  sub     rsp, 178h
0x1800029c8  mov     [rax+8], rbx
0x1800029cc  mov     edi, r8d
0x1800029cf  mov     [rax-18h], rsi
0x1800029d3  mov     r8d, 98h; Size
0x1800029d9  mov     [rax-20h], r12
0x1800029dd  mov     rbx, r9
0x1800029e0  mov     [rax-28h], r13
0x1800029e4  mov     [rax-30h], r14
0x1800029e8  mov     r14, rcx
0x1800029eb  mov     [rax-38h], r15
0x1800029ef  lea     rcx, [rbp+80h+var_D0]; void *
0x1800029f3  mov     r15d, edx
0x1800029f6  mov     [rbp+80h+arg_18], 0
0x180002a01  xor     edx, edx; Val
0x180002a03  call    memset_0
0x180002a08  mov     r9d, [rbx]
0x180002a0b  cmp     r9d, 100h
0x180002a12  ja      loc_1800030A0
0x180002a18  mov     ecx, [rbx+20h]
0x180002a1b  cmp     ecx, 2000h
0x180002a21  ja      loc_1800030A0
0x180002a27  mov     eax, [rbx+38h]
0x180002a2a  cmp     eax, 2000h
0x180002a2f  ja      loc_1800030A0
0x180002a35  mov     r8d, [rbx+58h]
0x180002a39  cmp     r8d, 7FF8h
0x180002a40  ja      loc_1800030A0
0x180002a46  mov     edx, [rbx+68h]
0x180002a49  cmp     edx, 800h
0x180002a4f  ja      loc_1800030A0
0x180002a55  cmp     dword ptr [rbx+80h], 100h
0x180002a5f  ja      loc_1800030A0
0x180002a65  test    eax, eax
0x180002a67  jz      loc_180003084
0x180002a6d  test    edx, edx
0x180002a6f  jz      loc_180003084
0x180002a75  cmp     qword ptr [rbx+30h], 0
0x180002a7a  mov     rax, [rbx+8]
0x180002a7e  mov     r13, [rbp+80h+arg_20]
0x180002a85  mov     [rbp+80h+var_D0], rax
0x180002a89  mov     rax, [rbx+28h]
0x180002a8d  mov     [rbp+80h+var_B0], rax
0x180002a91  mov     [rbp+80h+var_40], rbx
0x180002a95  mov     [rbp+80h+var_C8], r9d
0x180002a99  mov     [rbp+80h+var_70], r8d
0x180002a9d  mov     [rbp+80h+var_A8], ecx
0x180002aa0  jz      short loc_180002AF3
0x180002aa2  lea     rax, [rbp+80h+var_A0]
0x180002aa6  mov     rdx, r13; struct _CRYPT_XML_WS_STATE *
0x180002aa9  mov     [rsp+180h+var_150], rax; struct _CRYPT_XML_BLOB *
0x180002aae  lea     r9, [rbx+20h]; void *
0x180002ab2  mov     dword ptr [rsp+180h+var_158], edi; unsigned int
0x180002ab6  lea     r8, ?CanonicalizationMethod_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; struct _WS_ELEMENT_DESCRIPTION *
0x180002abd  mov     ecx, r15d; enum WS_CHARSET
0x180002ac0  mov     dword ptr [rsp+180h+var_160], 18h; unsigned int
0x180002ac8  call    ?I_XmlGetEncodedElement@@YAJW4WS_CHARSET@@PEAU_CRYPT_XML_WS_STATE@@PEBU_WS_ELEMENT_DESCRIPTION@@PEBXKKPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncodedElement(WS_CHARSET,_CRYPT_XML_WS_STATE *,_WS_ELEMENT_DESCRIPTION const *,void const *,ulong,ulong,_CRYPT_XML_BLOB *)
0x180002acd  mov     edi, eax
0x180002acf  test    eax, eax
0x180002ad1  jns     short loc_180002AED
0x180002ad3  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002ada  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180002adf  mov     r8, rax
0x180002ae2  mov     r9d, 8A5h
0x180002ae8  jmp     loc_1800030D9
0x180002aed  mov     edi, [rbp+80h+arg_10]
0x180002af3  cmp     qword ptr [rbx+50h], 0
0x180002af8  mov     rax, [rbx+40h]
0x180002afc  mov     [rbp+80h+var_90], rax
0x180002b00  mov     eax, [rbx+38h]
0x180002b03  mov     [rbp+80h+var_88], eax
0x180002b06  jz      short loc_180002B6F
0x180002b08  lea     rax, [rbp+80h+var_80]
0x180002b0c  mov     rdx, r13; struct _CRYPT_XML_WS_STATE *
0x180002b0f  mov     [rsp+180h+var_150], rax; struct _CRYPT_XML_BLOB *
0x180002b14  lea     r9, [rbx+38h]; void *
0x180002b18  mov     dword ptr [rsp+180h+var_158], edi; unsigned int
0x180002b1c  lea     r8, ?SignatureMethod_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; struct _WS_ELEMENT_DESCRIPTION *
0x180002b23  mov     ecx, r15d; enum WS_CHARSET
0x180002b26  mov     dword ptr [rsp+180h+var_160], 20h ; ' '; unsigned int
0x180002b2e  call    ?I_XmlGetEncodedElement@@YAJW4WS_CHARSET@@PEAU_CRYPT_XML_WS_STATE@@PEBU_WS_ELEMENT_DESCRIPTION@@PEBXKKPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncodedElement(WS_CHARSET,_CRYPT_XML_WS_STATE *,_WS_ELEMENT_DESCRIPTION const *,void const *,ulong,ulong,_CRYPT_XML_BLOB *)
0x180002b33  mov     edi, eax
0x180002b35  test    eax, eax
0x180002b37  jns     short loc_180002B6F
0x180002b39  lea     r12, aOnecoreDsSecur_1+35h; ""
0x180002b40  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002b47  movzx   ecx, byte ptr [r12-1]
0x180002b4d  mov     rdx, r12
0x180002b50  dec     r12
0x180002b53  cmp     cl, 5Ch ; '\'
0x180002b56  jz      short loc_180002B60
0x180002b58  cmp     r12, rax
0x180002b5b  ja      short loc_180002B47
0x180002b5d  cmp     cl, 5Ch ; '\'
0x180002b60  cmovz   r12, rdx
0x180002b64  mov     r9d, 8BBh
0x180002b6a  jmp     loc_1800030D6
0x180002b6f  mov     rax, [rbx+70h]
0x180002b73  lea     r9, [rbp+80h+var_D0]
0x180002b77  mov     rcx, [r14+30h]; hHeap
0x180002b7b  xor     r8d, r8d
0x180002b7e  mov     [rbp+80h+var_68], rax
0x180002b82  xor     edx, edx
0x180002b84  mov     eax, [rbx+68h]
0x180002b87  mov     [rbp+80h+var_60], eax
0x180002b8a  mov     eax, [rbx+80h]
0x180002b90  mov     [rbp+80h+var_48], eax
0x180002b93  lea     rax, [rbp+80h+arg_18]
0x180002b9a  mov     [rsp+180h+var_160], rax; __int64
0x180002b9f  call    I_CryptXmlHandleAllocSignature
0x180002ba4  mov     rsi, [rbp+80h+arg_18]
0x180002bab  mov     edi, eax
0x180002bad  test    eax, eax
0x180002baf  jns     short loc_180002BF4
0x180002bb1  test    rsi, rsi
0x180002bb4  jz      short loc_180002BBE
0x180002bb6  mov     rcx, rsi
0x180002bb9  call    I_CryptXmlRelease
0x180002bbe  lea     r12, aOnecoreDsSecur_1+35h; ""
0x180002bc5  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002bcc  movzx   ecx, byte ptr [r12-1]
0x180002bd2  mov     rdx, r12
0x180002bd5  dec     r12
0x180002bd8  cmp     cl, 5Ch ; '\'
0x180002bdb  jz      short loc_180002BE5
0x180002bdd  cmp     r12, rax
0x180002be0  ja      short loc_180002BCC
0x180002be2  cmp     cl, 5Ch ; '\'
0x180002be5  cmovz   r12, rdx
0x180002be9  mov     r9d, 8D2h
0x180002bef  jmp     loc_180003064
0x180002bf4  mov     r15, [rsi+90h]
0x180002bfb  mov     rax, [r14+78h]
0x180002bff  mov     r12, [r15+8]
0x180002c03  test    rax, rax
0x180002c06  jz      short loc_180002C10
0x180002c08  mov     rcx, r14
0x180002c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c10  mov     rcx, [r14+88h]
0x180002c17  mov     eax, [r14+90h]
0x180002c1e  cmp     [rcx+18h], eax
0x180002c21  jb      short loc_180002C66
0x180002c23  mov     edi, 80092101h
0x180002c28  lea     r8, aOnecoreDsSecur_12+2Eh; ""
0x180002c2f  lea     rdx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002c36  movzx   eax, byte ptr [r8-1]
0x180002c3b  mov     rcx, r8
0x180002c3e  dec     r8
0x180002c41  cmp     al, 5Ch ; '\'
0x180002c43  jz      short loc_180002C4C
0x180002c45  cmp     r8, rdx
0x180002c48  ja      short loc_180002C36
0x180002c4a  cmp     al, 5Ch ; '\'
0x180002c4c  cmovz   r8, rcx
0x180002c50  mov     edx, edi
0x180002c52  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002c59  mov     r9d, 0FFh
0x180002c5f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002c64  jmp     short loc_180002CB4
0x180002c66  xor     edi, edi
0x180002c68  mov     [r12+50h], r14
0x180002c6d  lock inc dword ptr [r12+38h]
0x180002c73  mov     rdx, [r14+88h]
0x180002c7a  mov     eax, [rdx+18h]
0x180002c7d  test    eax, eax
0x180002c7f  jz      short loc_180002C98
0x180002c81  lea     ecx, [rax-1]
0x180002c84  mov     rax, [rdx+20h]
0x180002c88  mov     rcx, [rax+rcx*8]
0x180002c8c  mov     rax, [r15+8]
0x180002c90  mov     rdx, [rcx+8]
0x180002c94  mov     [rdx+60h], rax
0x180002c98  mov     rax, [r14+88h]
0x180002c9f  mov     ecx, [rax+18h]
0x180002ca2  mov     rax, [rax+20h]
0x180002ca6  mov     [rax+rcx*8], r15
0x180002caa  mov     rax, [r14+88h]
0x180002cb1  inc     dword ptr [rax+18h]
0x180002cb4  mov     rax, [r14+80h]
0x180002cbb  test    rax, rax
0x180002cbe  jz      short loc_180002CC8
0x180002cc0  mov     rcx, r14
0x180002cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc8  test    edi, edi
0x180002cca  jns     short loc_180002CE6
0x180002ccc  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002cd3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180002cd8  mov     r8, rax
0x180002cdb  mov     r9d, 8E0h
0x180002ce1  jmp     loc_180003067
0x180002ce6  mov     r12d, [rbp+80h+arg_10]
0x180002ced  xor     r15d, r15d
0x180002cf0  cmp     r15d, [rbx+58h]
0x180002cf4  jnb     short loc_180002D5A
0x180002cf6  mov     r8, [rsi+90h]
0x180002cfd  mov     edx, r15d
0x180002d00  imul    r9, rdx, 68h ; 'h'
0x180002d04  mov     rax, [r8+70h]
0x180002d08  add     r9, [rbx+60h]; struct WS_TYPE_Reference *
0x180002d0c  mov     edx, [rbp+80h+arg_8]; enum WS_CHARSET
0x180002d12  lea     rcx, [rax+r15*8]
0x180002d16  mov     rax, [r8+8]
0x180002d1a  mov     [rsp+180h+var_150], rcx; struct _CRYPT_XML_REFERENCE **
0x180002d1f  mov     r8d, r12d; unsigned int
0x180002d22  mov     rcx, [r14+30h]; hHeap
0x180002d26  mov     [rsp+180h+var_158], rax; struct _HXML_HANDLE *
0x180002d2b  mov     [rsp+180h+var_160], r13; struct _CRYPT_XML_WS_STATE *
0x180002d30  call    ?I_XmlUnmarshallReference@@YAJPEAXW4WS_CHARSET@@KPEAUWS_TYPE_Reference@@PEAU_CRYPT_XML_WS_STATE@@PEAU_HXML_HANDLE@@PEAPEBU_CRYPT_XML_REFERENCE@@@Z; I_XmlUnmarshallReference(void *,WS_CHARSET,ulong,WS_TYPE_Reference *,_CRYPT_XML_WS_STATE *,_HXML_HANDLE *,_CRYPT_XML_REFERENCE const * *)
0x180002d35  mov     edi, eax
0x180002d37  test    eax, eax
0x180002d39  js      short loc_180002D40
0x180002d3b  inc     r15d
0x180002d3e  jmp     short loc_180002CF0
0x180002d40  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002d47  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180002d4c  mov     r8, rax
0x180002d4f  mov     r9d, 8F7h
0x180002d55  jmp     loc_180003067
0x180002d5a  xor     eax, eax
0x180002d5c  lea     r12, aOnecoreDsSecur_1+35h; ""
0x180002d63  mov     [rsp+180h+var_140], eax
0x180002d67  cmp     eax, [rbx+80h]
0x180002d6d  jnb     loc_180003075
0x180002d73  lea     rcx, [rax+rax*8]
0x180002d77  mov     [rsp+180h+var_128], rax
0x180002d7c  mov     rax, [rbx+88h]
0x180002d83  xor     edx, edx; Val
0x180002d85  mov     r8d, 50h ; 'P'; Size
0x180002d8b  mov     [rbp+80h+arg_18], 0
0x180002d96  lea     r15, [rax+rcx*8]
0x180002d9a  lea     rcx, [rsp+180h+var_120]; void *
0x180002d9f  call    memset_0
0x180002da4  mov     r8d, [r15]
0x180002da7  cmp     r8d, 100h
0x180002dae  ja      loc_180002FA8
0x180002db4  mov     edx, [r15+10h]
0x180002db8  cmp     edx, 2000h
0x180002dbe  ja      loc_180002FA8
0x180002dc4  mov     ecx, [r15+20h]
0x180002dc8  cmp     ecx, 2000h
0x180002dce  ja      loc_180002FA8
0x180002dd4  cmp     dword ptr [r15+30h], 7FF8h
0x180002ddc  ja      loc_180002FA8
0x180002de2  cmp     qword ptr [r15+40h], 0
0x180002de7  mov     rax, [rsi+90h]
0x180002dee  mov     [rsp+180h+var_118], r8d
0x180002df3  mov     [rsp+180h+var_108], edx
0x180002df7  mov     [rbp+80h+var_F8], ecx
0x180002dfa  mov     rax, [rax+0A8h]
0x180002e01  mov     [rsp+180h+var_138], rax
0x180002e06  mov     rax, [r14+30h]
0x180002e0a  mov     [rsp+180h+hHeap], rax
0x180002e0f  mov     rax, [r15+8]
0x180002e13  mov     [rsp+180h+var_120], rax
0x180002e18  mov     rax, [r15+18h]
0x180002e1c  mov     [rsp+180h+var_110], rax
0x180002e21  mov     rax, [r15+28h]
0x180002e25  mov     [rbp+80h+var_100], rax
0x180002e29  mov     [rbp+80h+var_D8], r15
0x180002e2d  jnz     short loc_180002E39
0x180002e2f  test    dword ptr [r14+3Ch], 40000000h
0x180002e37  jz      short loc_180002EA8
0x180002e39  mov     ecx, [rbp+80h+arg_8]; enum WS_CHARSET
0x180002e3f  lea     rax, [rbp+80h+var_F0]
0x180002e43  mov     [rsp+180h+var_150], rax; struct _CRYPT_XML_BLOB *
0x180002e48  lea     r8, ?Object_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; struct _WS_ELEMENT_DESCRIPTION *
0x180002e4f  mov     eax, [rbp+80h+arg_10]
0x180002e55  mov     r9, r15; void *
0x180002e58  mov     dword ptr [rsp+180h+var_158], eax; unsigned int
0x180002e5c  mov     rdx, r13; struct _CRYPT_XML_WS_STATE *
0x180002e5f  mov     dword ptr [rsp+180h+var_160], 48h ; 'H'; unsigned int
0x180002e67  call    ?I_XmlGetEncodedElement@@YAJW4WS_CHARSET@@PEAU_CRYPT_XML_WS_STATE@@PEBU_WS_ELEMENT_DESCRIPTION@@PEBXKKPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncodedElement(WS_CHARSET,_CRYPT_XML_WS_STATE *,_WS_ELEMENT_DESCRIPTION const *,void const *,ulong,ulong,_CRYPT_XML_BLOB *)
0x180002e6c  mov     edi, eax
0x180002e6e  test    eax, eax
0x180002e70  jns     short loc_180002EA8
0x180002e72  mov     r8, r12
0x180002e75  lea     r15, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002e7c  cmp     byte ptr [r8-1], 5Ch ; '\'
0x180002e81  lea     rax, [r8-1]
0x180002e85  jz      short loc_180002E8F
0x180002e87  mov     r8, rax
0x180002e8a  cmp     rax, r15
0x180002e8d  ja      short loc_180002E7C
0x180002e8f  mov     r9d, 345h
0x180002e95  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002e9c  mov     edx, edi
0x180002e9e  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002ea3  jmp     loc_180002FE7
0x180002ea8  mov     eax, [r15+30h]
0x180002eac  lea     r9, [rbp+80h+arg_18]
0x180002eb3  mov     rcx, [rsp+180h+hHeap]; hHeap
0x180002eb8  lea     r8, [rsp+180h+var_120]
0x180002ebd  mov     [rbp+80h+var_E0], eax
0x180002ec0  call    I_CryptXmlHandleAllocObject
  ... truncated ...
```
