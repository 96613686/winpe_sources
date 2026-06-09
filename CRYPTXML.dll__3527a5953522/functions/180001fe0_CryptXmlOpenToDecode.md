# CryptXmlOpenToDecode

- ea: `0x180001fe0`
- end: `0x18000245c`
- name: `CryptXmlOpenToDecode`
- size: `1148`
- prototype: `HRESULT __stdcall(const CRYPT_XML_TRANSFORM_CHAIN_CONFIG *pConfig, DWORD dwFlags, const CRYPT_XML_PROPERTY *rgProperty, ULONG cProperty, const CRYPT_XML_BLOB *pEncoded, HCRYPTXML *phCryptXml)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001fe0`
- `0x180002470`
- `0x180004670`
- `0x180004f60`
- `0x1800070d0`
- `0x180014ce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000220b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000220b`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000224c`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18000224c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180002175`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180002175`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000229f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000229f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000218e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000218e`

## string_xrefs

- `0x1800021b0`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x18000221f`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180002326`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x18000236f`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x1800023b9`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x18000241b`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180002082`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`
- `0x1800020d7`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`
- `0x18000213a`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlOpenToDecode(
        const CRYPT_XML_TRANSFORM_CHAIN_CONFIG *pConfig,
        DWORD dwFlags,
        const CRYPT_XML_PROPERTY *rgProperty,
        ULONG cProperty,
        const CRYPT_XML_BLOB *pEncoded,
        HCRYPTXML *phCryptXml)
{
  ULONG cbData; // eax
  __int64 v12; // rdx
  const CRYPT_XML_PROPERTY *v13; // rax
  const char *v14; // rax
  __int64 i; // rdx
  const CRYPT_XML_PROPERTY *v16; // rax
  const char *v17; // rax
  __int64 j; // rdx
  const char *v19; // rax
  char *v20; // rdi
  HANDLE v21; // rax
  HANDLE v22; // rbp
  signed int LastError; // eax
  HRESULT v24; // ebp
  const char *v25; // r8
  char v26; // cl
  const char *v27; // rdx
  bool v28; // zf
  char *v29; // rax
  char *v30; // rbx
  const char *v31; // rax
  __int64 (__fastcall *v32)(); // rcx
  __int64 (__fastcall *v33)(); // rax
  __int64 v34; // rcx
  const char *v35; // rax
  const char *v36; // rax
  const char *v37; // rax
  const char *v38; // r8
  char v39; // cl
  const char *v40; // rdx
  bool v41; // zf
  unsigned int v42; // [rsp+20h] [rbp-38h]
  HANDLE hHeap; // [rsp+28h] [rbp-30h]
  unsigned int phCryptXmla; // [rsp+88h] [rbp+30h]

  if ( phCryptXml && (!cProperty || rgProperty) )
  {
    if ( pEncoded )
    {
      cbData = pEncoded->cbData;
      if ( cbData )
      {
        v42 = 2147483640;
        if ( cbData > 0x7FFFFFF8 )
          return -2146885375;
        v12 = 0;
        *phCryptXml = 0;
        while ( (unsigned int)v12 < cProperty )
        {
          v13 = &rgProperty[v12];
          if ( v13->dwPropId == CRYPT_XML_PROPERTY_MAX_HEAP_SIZE )
          {
            if ( v13->cbValue == 4 )
            {
              _mm_lfence();
              v42 = *(_DWORD *)v13->pvValue;
            }
            else
            {
              v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v14, 97);
            }
            break;
          }
          v12 = (unsigned int)(v12 + 1);
        }
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= cProperty )
            goto LABEL_21;
          v16 = &rgProperty[i];
          if ( v16->dwPropId == CRYPT_XML_PROPERTY_MAX_SIGNATURES )
            break;
        }
        if ( v16->cbValue != 4 )
        {
          v17 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v17, 97);
LABEL_21:
          phCryptXmla = 16;
          goto LABEL_22;
        }
        _mm_lfence();
        phCryptXmla = *(_DWORD *)v16->pvValue;
LABEL_22:
        for ( j = 0; (unsigned int)j < cProperty; j = (unsigned int)(j + 1) )
        {
          if ( rgProperty[j].dwPropId == CRYPT_XML_PROPERTY_XML_OUTPUT_CHARSET )
          {
            if ( rgProperty[j].cbValue == 4 )
            {
              _mm_lfence();
            }
            else
            {
              v19 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v19, 97);
            }
            break;
          }
        }
        v20 = 0;
        v21 = HeapCreate(0, 0, 0);
        hHeap = v21;
        v22 = v21;
        if ( v21 )
        {
          v29 = (char *)HeapAlloc(v21, (((int)dwFlags >> 31) & 1u) + 8, 8LL * phCryptXmla + 240);
          v30 = v29;
          if ( !v29 )
          {
            v31 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
            v24 = -2147024882;
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v31, 162);
            HeapDestroy(hHeap);
            goto LABEL_50;
          }
          v32 = 0;
          *((_DWORD *)v29 + 14) = 1;
          *(_DWORD *)v29 = 1145324609;
          *((_QWORD *)v29 + 6) = v22;
          *((_DWORD *)v29 + 15) = dwFlags;
          *((_QWORD *)v29 + 14) = I_CRYPT_XML_HANDLE_FREE_DOC;
          *((_QWORD *)v29 + 8) = 12;
          *((_DWORD *)v29 + 18) = 0;
          *((_QWORD *)v29 + 10) = 0;
          *((_QWORD *)v29 + 11) = 0;
          *((_QWORD *)v29 + 12) = 0;
          if ( (dwFlags & 0x80000000) != 0 )
          {
            v33 = 0;
          }
          else
          {
            InitializeCriticalSection((LPCRITICAL_SECTION)(v29 + 8));
            v33 = CRYPT_XML_HANDLE_UNLOCK;
            v32 = CRYPT_XML_HANDLE_LOCK;
          }
          *((_QWORD *)v30 + 15) = v32;
          *((_QWORD *)v30 + 16) = v33;
          *((_QWORD *)v30 + 17) = v30 + 200;
          *((_DWORD *)v30 + 50) = 40;
          *((_QWORD *)v30 + 26) = v30;
          *(_QWORD *)(*((_QWORD *)v30 + 17) + 16LL) = pConfig;
          v34 = *((_QWORD *)v30 + 17);
          *((_DWORD *)v30 + 36) = phCryptXmla;
          *(_QWORD *)(v34 + 32) = v34 + 40;
          *((_QWORD *)v30 + 13) = *((_QWORD *)v30 + 17);
          v24 = I_CryptXmlWsStateInitialize(v42, phCryptXmla, v30);
          if ( v24 >= 0 )
          {
            v20 = v30;
            _InterlockedIncrement((volatile signed __int32 *)v30 + 14);
            v24 = 0;
          }
          else
          {
            v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v24, v35, 196);
          }
          I_CryptXmlRelease(v30);
        }
        else
        {
          LastError = GetLastError();
          v24 = LastError;
          if ( LastError > 0 )
            v24 = (unsigned __int16)LastError | 0x80070000;
          v25 = "";
          while ( 1 )
          {
            v26 = *(v25 - 1);
            v27 = v25--;
            v28 = v26 == 92;
            if ( v26 == 92 )
              break;
            if ( v25 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
            {
              v28 = v26 == 92;
              break;
            }
          }
          if ( v28 )
            v25 = v27;
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v24, v25, 153);
        }
        if ( v24 >= 0 )
        {
          *((_QWORD *)v20 + 21) = rgProperty;
          *((_DWORD *)v20 + 44) = cProperty;
          v24 = I_CryptXmlDecode((struct _HXML_DOC *)v20, dwFlags);
          if ( v24 >= 0 )
          {
            *phCryptXml = v20;
            _InterlockedIncrement((volatile signed __int32 *)v20 + 14);
            v24 = 0;
          }
          else
          {
            v37 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v24, v37, 571);
          }
LABEL_54:
          if ( v20 )
            I_CryptXmlRelease(v20);
          return v24;
        }
LABEL_50:
        v36 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v24, v36, 556);
        goto LABEL_54;
      }
    }
  }
  v38 = "";
  while ( 1 )
  {
    v39 = *(v38 - 1);
    v40 = v38--;
    v41 = v39 == 92;
    if ( v39 == 92 )
      break;
    if ( v38 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
    {
      v41 = v39 == 92;
      break;
    }
  }
  if ( v41 )
    v38 = v40;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v38, 503);
  return -2147024809;
}

```

## disassembly

```asm
0x180001fe0  mov     [rsp+arg_18], rbx
0x180001fe5  mov     [rsp+arg_0], rcx
0x180001fea  push    rsi
0x180001feb  push    r12
0x180001fed  push    r13
0x180001fef  push    r14
0x180001ff1  push    r15
0x180001ff3  sub     rsp, 30h
0x180001ff7  mov     rsi, [rsp+58h+phCryptXml]
0x180001fff  xor     r13d, r13d
0x180002002  mov     r14d, r9d
0x180002005  mov     r15, r8
0x180002008  mov     r12d, edx
0x18000200b  test    rsi, rsi
0x18000200e  jz      loc_180002414
0x180002014  test    r9d, r9d
0x180002017  jz      short loc_180002022
0x180002019  test    r8, r8
0x18000201c  jz      loc_180002414
0x180002022  mov     rbx, [rsp+58h+pEncoded]
0x18000202a  test    rbx, rbx
0x18000202d  jz      loc_180002414
0x180002033  mov     eax, [rbx+4]
0x180002036  test    eax, eax
0x180002038  jz      loc_180002414
0x18000203e  mov     ecx, 7FFFFFF8h
0x180002043  mov     [rsp+58h+var_38], ecx
0x180002047  cmp     eax, ecx
0x180002049  jbe     short loc_180002055
0x18000204b  mov     eax, 80092101h
0x180002050  jmp     loc_180002400
0x180002055  mov     [rsp+58h+arg_8], rbp
0x18000205a  xor     edx, edx
0x18000205c  mov     [rsp+58h+arg_10], rdi
0x180002061  mov     [rsi], r13
0x180002064  cmp     edx, r14d
0x180002067  jnb     short loc_1800020B7
0x180002069  lea     rcx, [rdx+rdx*2]
0x18000206d  cmp     dword ptr [r8+rcx*8], 1
0x180002072  lea     rax, [r8+rcx*8]
0x180002076  jz      short loc_18000207C
0x180002078  inc     edx
0x18000207a  jmp     short loc_180002064
0x18000207c  cmp     dword ptr [rax+10h], 4
0x180002080  jz      short loc_1800020AA
0x180002082  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002089  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000208e  mov     r8, rax
0x180002091  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002098  mov     edx, 80070057h
0x18000209d  mov     r9d, 61h ; 'a'
0x1800020a3  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800020a8  jmp     short loc_1800020B7
0x1800020aa  lfence
0x1800020ad  mov     rax, [rax+8]
0x1800020b1  mov     eax, [rax]
0x1800020b3  mov     [rsp+58h+var_38], eax
0x1800020b7  xor     edx, edx
0x1800020b9  cmp     edx, r14d
0x1800020bc  jnb     short loc_1800020FD
0x1800020be  lea     rcx, [rdx+rdx*2]
0x1800020c2  cmp     dword ptr [r15+rcx*8], 3
0x1800020c7  lea     rax, [r15+rcx*8]
0x1800020cb  jz      short loc_1800020D1
0x1800020cd  inc     edx
0x1800020cf  jmp     short loc_1800020B9
0x1800020d1  cmp     dword ptr [rax+10h], 4
0x1800020d5  jz      short loc_180002122
0x1800020d7  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800020de  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800020e3  mov     r8, rax
0x1800020e6  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800020ed  mov     edx, 80070057h
0x1800020f2  mov     r9d, 61h ; 'a'
0x1800020f8  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800020fd  mov     dword ptr [rsp+58h+phCryptXml], 10h
0x180002108  xor     edx, edx
0x18000210a  cmp     edx, r14d
0x18000210d  jnb     short loc_18000216C
0x18000210f  lea     rcx, [rdx+rdx*2]
0x180002113  cmp     dword ptr [r15+rcx*8], 5
0x180002118  lea     rax, [r15+rcx*8]
0x18000211c  jz      short loc_180002134
0x18000211e  inc     edx
0x180002120  jmp     short loc_18000210A
0x180002122  lfence
0x180002125  mov     rax, [rax+8]
0x180002129  mov     eax, [rax]
0x18000212b  mov     dword ptr [rsp+58h+phCryptXml], eax
0x180002132  jmp     short loc_180002108
0x180002134  cmp     dword ptr [rax+10h], 4
0x180002138  jz      short loc_180002162
0x18000213a  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002141  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180002146  mov     r8, rax
0x180002149  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002150  mov     edx, 80070057h
0x180002155  mov     r9d, 61h ; 'a'
0x18000215b  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002160  jmp     short loc_18000216C
0x180002162  lfence
0x180002165  mov     rax, [rax+8]
0x180002169  mov     r13d, [rax]
0x18000216c  xor     r8d, r8d; dwMaximumSize
0x18000216f  xor     edx, edx; dwInitialSize
0x180002171  xor     ecx, ecx; flOptions
0x180002173  xor     edi, edi
0x180002175  call    cs:__imp_HeapCreate
0x18000217c  nop     dword ptr [rax+rax+00h]
0x180002181  mov     [rsp+58h+hHeap], rax
0x180002186  mov     rbp, rax
0x180002189  test    rax, rax
0x18000218c  jnz     short loc_1800021EC
0x18000218e  call    cs:__imp_GetLastError
0x180002195  nop     dword ptr [rax+rax+00h]
0x18000219a  mov     ebp, eax
0x18000219c  test    eax, eax
0x18000219e  jle     short loc_1800021A9
0x1800021a0  movzx   ebp, ax
0x1800021a3  or      ebp, 80070000h
0x1800021a9  lea     r8, aOnecoreDsSecur_12+2Eh; ""
0x1800021b0  lea     rax, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800021b7  movzx   ecx, byte ptr [r8-1]
0x1800021bc  mov     rdx, r8
0x1800021bf  dec     r8
0x1800021c2  cmp     cl, 5Ch ; '\'
0x1800021c5  jz      short loc_1800021CF
0x1800021c7  cmp     r8, rax
0x1800021ca  ja      short loc_1800021B7
0x1800021cc  cmp     cl, 5Ch ; '\'
0x1800021cf  cmovz   r8, rdx
0x1800021d3  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800021da  mov     edx, ebp
0x1800021dc  mov     r9d, 99h
0x1800021e2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800021e7  jmp     loc_18000236B
0x1800021ec  mov     r8d, dword ptr [rsp+58h+phCryptXml]
0x1800021f4  mov     edx, r12d
0x1800021f7  sar     edx, 1Fh
0x1800021fa  mov     rcx, rbp; hHeap
0x1800021fd  and     edx, 1
0x180002200  add     edx, 8; dwFlags
0x180002203  lea     r8, ds:0F0h[r8*8]; dwBytes
0x18000220b  call    cs:__imp_HeapAlloc
0x180002212  nop     dword ptr [rax+rax+00h]
0x180002217  mov     rbx, rax
0x18000221a  test    rax, rax
0x18000221d  jnz     short loc_18000225D
0x18000221f  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002226  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000222b  mov     ebp, 8007000Eh
0x180002230  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002237  mov     edx, ebp
0x180002239  mov     r8, rax
0x18000223c  mov     r9d, 0A2h
0x180002242  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002247  mov     rcx, [rsp+58h+hHeap]; hHeap
0x18000224c  call    cs:__imp_HeapDestroy
0x180002253  nop     dword ptr [rax+rax+00h]
0x180002258  jmp     loc_18000236F
0x18000225d  xor     ecx, ecx
0x18000225f  mov     dword ptr [rax+38h], 1
0x180002266  mov     dword ptr [rax], 44444441h
0x18000226c  mov     [rax+30h], rbp
0x180002270  mov     [rax+3Ch], r12d
0x180002274  lea     rax, ?I_CRYPT_XML_HANDLE_FREE_DOC@@YAJPEAU_HXML_HANDLE@@@Z; I_CRYPT_XML_HANDLE_FREE_DOC(_HXML_HANDLE *)
0x18000227b  mov     [rbx+70h], rax
0x18000227f  mov     qword ptr [rbx+40h], 0Ch
0x180002287  mov     [rbx+48h], ecx
0x18000228a  mov     [rbx+50h], rcx
0x18000228e  mov     [rbx+58h], rcx
0x180002292  mov     [rbx+60h], rcx
0x180002296  test    r12d, r12d
0x180002299  js      short loc_1800022BB
0x18000229b  lea     rcx, [rbx+8]; lpCriticalSection
0x18000229f  call    cs:__imp_InitializeCriticalSection
0x1800022a6  nop     dword ptr [rax+rax+00h]
0x1800022ab  lea     rax, _CRYPT_XML_HANDLE_UNLOCK
0x1800022b2  lea     rcx, _CRYPT_XML_HANDLE_LOCK
0x1800022b9  jmp     short loc_1800022BE
0x1800022bb  mov     rax, rcx
0x1800022be  mov     edx, dword ptr [rsp+58h+phCryptXml]
0x1800022c5  mov     r8, rbx
0x1800022c8  mov     [rbx+78h], rcx
0x1800022cc  mov     [rbx+80h], rax
0x1800022d3  lea     rax, [rbx+0C8h]
0x1800022da  mov     rcx, [rsp+58h+arg_0]
0x1800022df  mov     [rbx+88h], rax
0x1800022e6  mov     dword ptr [rax], 28h ; '('
0x1800022ec  mov     [rax+8], rbx
0x1800022f0  mov     rax, [rbx+88h]
0x1800022f7  mov     [rax+10h], rcx
0x1800022fb  mov     rcx, [rbx+88h]
0x180002302  mov     [rbx+90h], edx
0x180002308  lea     rax, [rcx+28h]
0x18000230c  mov     [rcx+20h], rax
0x180002310  mov     rax, [rbx+88h]
0x180002317  mov     ecx, [rsp+58h+var_38]
0x18000231b  mov     [rbx+68h], rax
0x18000231f  call    I_CryptXmlWsStateInitialize
0x180002324  mov     ebp, eax
0x180002326  lea     rax, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000232d  test    ebp, ebp
0x18000232f  jns     short loc_180002352
0x180002331  mov     rcx, rax; char *
0x180002334  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180002339  mov     r8, rax
0x18000233c  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002343  mov     edx, ebp
0x180002345  mov     r9d, 0C4h
0x18000234b  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002350  jmp     short loc_18000235B
0x180002352  mov     rdi, rbx
0x180002355  lock inc dword ptr [rbx+38h]
0x180002359  xor     ebp, ebp
0x18000235b  mov     rcx, rbx
0x18000235e  call    I_CryptXmlRelease
0x180002363  mov     rbx, [rsp+58h+pEncoded]
0x18000236b  test    ebp, ebp
0x18000236d  jns     short loc_180002394
0x18000236f  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002376  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000237b  mov     r8, rax
0x18000237e  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002385  mov     edx, ebp
0x180002387  mov     r9d, 22Ch
0x18000238d  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002392  jmp     short loc_1800023E7
0x180002394  mov     r9d, r13d
0x180002397  mov     [rdi+0A8h], r15
0x18000239e  mov     r8, rbx
0x1800023a1  mov     [rdi+0B0h], r14d
0x1800023a8  mov     edx, r12d; dwFlags
0x1800023ab  mov     rcx, rdi; struct _HXML_DOC *
0x1800023ae  call    I_CryptXmlDecode
0x1800023b3  mov     ebp, eax
0x1800023b5  test    eax, eax
0x1800023b7  jns     short loc_1800023DE
0x1800023b9  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800023c0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800023c5  mov     r8, rax
0x1800023c8  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800023cf  mov     edx, ebp
0x1800023d1  mov     r9d, 23Bh
0x1800023d7  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800023dc  jmp     short loc_1800023E7
0x1800023de  mov     [rsi], rdi
0x1800023e1  lock inc dword ptr [rdi+38h]
0x1800023e5  xor     ebp, ebp
0x1800023e7  test    rdi, rdi
0x1800023ea  jz      short loc_1800023F4
0x1800023ec  mov     rcx, rdi
0x1800023ef  call    I_CryptXmlRelease
0x1800023f4  mov     rdi, [rsp+58h+arg_10]
0x1800023f9  mov     eax, ebp
0x1800023fb  mov     rbp, [rsp+58h+arg_8]
0x180002400  mov     rbx, [rsp+58h+arg_18]
0x180002405  add     rsp, 30h
0x180002409  pop     r15
0x18000240b  pop     r14
0x18000240d  pop     r13
0x18000240f  pop     r12
0x180002411  pop     rsi
0x180002412  retn
0x180002414  lea     r8, aOnecoreDsSecur_12+2Eh; ""
0x18000241b  lea     rax, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180002422  movzx   ecx, byte ptr [r8-1]
0x180002427  mov     rdx, r8
0x18000242a  dec     r8
0x18000242d  cmp     cl, 5Ch ; '\'
0x180002430  jz      short loc_18000243A
0x180002432  cmp     r8, rax
0x180002435  ja      short loc_180002422
0x180002437  cmp     cl, 5Ch ; '\'
0x18000243a  cmovz   r8, rdx
0x18000243e  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180002445  mov     edx, 80070057h
0x18000244a  mov     r9d, 1F7h
0x180002450  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180002455  mov     eax, 80070057h
0x18000245a  jmp     short loc_180002400
```
