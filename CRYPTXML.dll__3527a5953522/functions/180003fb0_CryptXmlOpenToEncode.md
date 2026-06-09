# CryptXmlOpenToEncode

- ea: `0x180003fb0`
- end: `0x180004667`
- name: `CryptXmlOpenToEncode`
- size: `1719`
- prototype: `HRESULT __stdcall(const CRYPT_XML_TRANSFORM_CHAIN_CONFIG *pConfig, DWORD dwFlags, LPCWSTR wszId, const CRYPT_XML_PROPERTY *rgProperty, ULONG cProperty, const CRYPT_XML_BLOB *pEncoded, HCRYPTXML *phSignature)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800031b0`
- `0x180003fb0`
- `0x180004670`
- `0x180004f60`
- `0x180006150`
- `0x180006da0`
- `0x1800070d0`
- `0x180014ce0`
- `0x180018625`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800041e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800041e5`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180004229`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x180004229`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000415e`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000415e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004281`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004174`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800040bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800040bf`

## string_xrefs

- `0x18000403f`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x1800040f2`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180004196`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x1800041f9`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180004313`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180004355`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x1800043af`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x18000444f`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180004498`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x1800044ec`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x18000453e`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x1800045c0`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180004625`: `onecore\ds\security\cryptoapi\xml\lib\ctxt.cpp`
- `0x180004084`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`
- `0x180004424`: `onecore\ds\security\cryptoapi\xml\lib\util.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlOpenToEncode(
        const CRYPT_XML_TRANSFORM_CHAIN_CONFIG *pConfig,
        DWORD dwFlags,
        LPCWSTR wszId,
        const CRYPT_XML_PROPERTY *rgProperty,
        ULONG cProperty,
        const CRYPT_XML_BLOB *pEncoded,
        HCRYPTXML *phSignature)
{
  int *v12; // rdi
  HRESULT v13; // esi
  const char *v14; // r8
  int v15; // r9d
  __int64 i; // rdx
  const CRYPT_XML_PROPERTY *v17; // rax
  const char *v18; // rax
  unsigned int v19; // eax
  LPCWSTR v20; // rcx
  const char *v21; // rdx
  char v22; // al
  const char *v23; // rcx
  bool v24; // zf
  __int64 v26; // rbx
  HANDLE v27; // rax
  signed int LastError; // eax
  const char *v29; // r8
  char v30; // al
  const char *v31; // rcx
  bool v32; // zf
  char *v33; // rax
  __int64 v34; // rdi
  const char *v35; // rax
  __int64 (__fastcall *v36)(); // rcx
  __int64 (__fastcall *v37)(); // rax
  __int64 v38; // rcx
  const char *v39; // rax
  const char *v40; // rax
  const char *v41; // rdx
  char v42; // al
  const char *v43; // rcx
  bool v44; // zf
  int v45; // r9d
  const char *v46; // r8
  __int64 j; // rdx
  const CRYPT_XML_PROPERTY *v48; // rax
  const char *v49; // rax
  char v50; // al
  char v51; // al
  void *v52; // rdi
  void (__fastcall *v53)(__int64); // rax
  __int64 v54; // rbp
  __int64 v55; // r15
  const char *v56; // rdx
  char v57; // al
  const char *v58; // rcx
  bool v59; // zf
  __int64 v60; // rdx
  int v61; // eax
  void (__fastcall *v62)(__int64); // rax
  const char *v63; // r8
  char v64; // al
  const char *v65; // rcx
  bool v66; // zf
  HANDLE hHeap; // [rsp+30h] [rbp-D8h]
  __int64 v68; // [rsp+38h] [rbp-D0h] BYREF
  const WCHAR *v69; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v70; // [rsp+48h] [rbp-C0h]
  unsigned int phSignaturea; // [rsp+140h] [rbp+38h]

  v68 = 0;
  memset_0(&v69, 0, 0x98u);
  if ( phSignature && (!cProperty || rgProperty) )
  {
    v12 = (int *)pEncoded;
    phSignaturea = 2147483640;
    if ( pEncoded && pEncoded->cbData > 0x7FFFFFF8 )
    {
      v13 = -2146885375;
      v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
      v15 = 322;
LABEL_24:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v14, v15);
      return v13;
    }
    *phSignature = 0;
    for ( i = 0; (unsigned int)i < cProperty; i = (unsigned int)(i + 1) )
    {
      v17 = &rgProperty[i];
      if ( v17->dwPropId == CRYPT_XML_PROPERTY_MAX_HEAP_SIZE )
      {
        if ( v17->cbValue == 4 )
        {
          _mm_lfence();
          phSignaturea = *(_DWORD *)v17->pvValue;
        }
        else
        {
          v18 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v18, 97);
        }
        break;
      }
    }
    v19 = lstrlenW(wszId);
    v20 = v69;
    v70 = v19;
    if ( v19 )
      v20 = wszId;
    v69 = v20;
    if ( v19 > 0x100 )
    {
      v13 = -2146885375;
      v21 = "";
      while ( 1 )
      {
        v22 = *(v21 - 1);
        v23 = v21--;
        v24 = v22 == 92;
        if ( v22 == 92 )
          break;
        if ( v21 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
        {
          v24 = v22 == 92;
          break;
        }
      }
      if ( v24 )
        v21 = v23;
      v15 = 357;
      v14 = v21;
      goto LABEL_24;
    }
    v26 = 0;
    v27 = HeapCreate(0, 0, 0);
    hHeap = v27;
    if ( v27 )
    {
      v33 = (char *)HeapAlloc(v27, (((int)dwFlags >> 31) & 1u) + 8, 0xF8u);
      v34 = (__int64)v33;
      if ( !v33 )
      {
        v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
        v13 = -2147024882;
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v35, 162);
        HeapDestroy(hHeap);
LABEL_46:
        v40 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v40, 371);
        goto LABEL_97;
      }
      v36 = 0;
      *((_DWORD *)v33 + 14) = 1;
      *(_DWORD *)v33 = 1145324609;
      *((_QWORD *)v33 + 6) = hHeap;
      *((_QWORD *)v33 + 14) = I_CRYPT_XML_HANDLE_FREE_DOC;
      *((_DWORD *)v33 + 15) = dwFlags;
      *((_QWORD *)v33 + 8) = 12;
      *((_DWORD *)v33 + 18) = 0;
      *((_QWORD *)v33 + 10) = 0;
      *((_QWORD *)v33 + 11) = 0;
      *((_QWORD *)v33 + 12) = 0;
      if ( (dwFlags & 0x80000000) != 0 )
      {
        v37 = 0;
      }
      else
      {
        InitializeCriticalSection((LPCRITICAL_SECTION)(v33 + 8));
        v37 = CRYPT_XML_HANDLE_UNLOCK;
        v36 = CRYPT_XML_HANDLE_LOCK;
      }
      *(_QWORD *)(v34 + 120) = v36;
      *(_QWORD *)(v34 + 128) = v37;
      *(_DWORD *)(v34 + 72) |= 0x80000000;
      *(_QWORD *)(v34 + 136) = v34 + 200;
      *(_DWORD *)(v34 + 200) = 40;
      *(_QWORD *)(v34 + 208) = v34;
      *(_QWORD *)(*(_QWORD *)(v34 + 136) + 16LL) = pConfig;
      v38 = *(_QWORD *)(v34 + 136);
      *(_DWORD *)(v34 + 144) = 1;
      *(_QWORD *)(v38 + 32) = v38 + 40;
      *(_QWORD *)(v34 + 104) = *(_QWORD *)(v34 + 136);
      v13 = I_CryptXmlWsStateInitialize(phSignaturea, 1u, v34);
      if ( v13 >= 0 )
      {
        v26 = v34;
        _InterlockedIncrement((volatile signed __int32 *)(v34 + 56));
        v13 = 0;
      }
      else
      {
        v39 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v39, 196);
      }
      I_CryptXmlRelease(v34);
      v12 = (int *)pEncoded;
    }
    else
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      v29 = "";
      while ( 1 )
      {
        v30 = *(v29 - 1);
        v31 = v29--;
        v32 = v30 == 92;
        if ( v30 == 92 )
          break;
        if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
        {
          v32 = v30 == 92;
          break;
        }
      }
      if ( v32 )
        v29 = v31;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v29, 153);
    }
    if ( v13 < 0 )
      goto LABEL_46;
    *(_QWORD *)(v26 + 168) = rgProperty;
    *(_DWORD *)(v26 + 176) = cProperty;
    if ( wszId && (v13 = I_CryptXmlCheckUniqueId(v26, wszId, 0xFFFFFFFF, 1), v13 < 0) )
    {
      v41 = "";
      while ( 1 )
      {
        v42 = *(v41 - 1);
        v43 = v41--;
        v44 = v42 == 92;
        if ( v42 == 92 )
          break;
        if ( v41 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
        {
          v44 = v42 == 92;
          break;
        }
      }
      v45 = 388;
    }
    else
    {
      if ( !v12 || !v12[1] )
      {
LABEL_77:
        v13 = I_CryptXmlHandleAllocSignature(*(HANDLE *)(v26 + 48), 1, dwFlags, (__int64)&v69, &v68);
        if ( v13 >= 0 )
        {
          v52 = (void *)v68;
          v53 = *(void (__fastcall **)(__int64))(v26 + 120);
          v54 = *(_QWORD *)(v68 + 144);
          v55 = *(_QWORD *)(v54 + 8);
          if ( v53 )
            v53(v26);
          if ( *(_DWORD *)(*(_QWORD *)(v26 + 136) + 24LL) < *(_DWORD *)(v26 + 144) )
          {
            v13 = 0;
            *(_QWORD *)(v55 + 80) = v26;
            _InterlockedIncrement((volatile signed __int32 *)(v55 + 56));
            v60 = *(_QWORD *)(v26 + 136);
            v61 = *(_DWORD *)(v60 + 24);
            if ( v61 )
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + 32) + 8LL * (unsigned int)(v61 - 1)) + 8LL) + 96LL) = *(_QWORD *)(v54 + 8);
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v26 + 136) + 32LL)
                      + 8LL * (unsigned int)(*(_DWORD *)(*(_QWORD *)(v26 + 136) + 24LL))++) = v54;
          }
          else
          {
            v13 = -2146885375;
            v56 = "";
            while ( 1 )
            {
              v57 = *(v56 - 1);
              v58 = v56--;
              v59 = v57 == 92;
              if ( v57 == 92 )
                break;
              if ( v56 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
              {
                v59 = v57 == 92;
                break;
              }
            }
            if ( v59 )
              v56 = v58;
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v56, 255);
          }
          v62 = *(void (__fastcall **)(__int64))(v26 + 128);
          if ( v62 )
            v62(v26);
          if ( v13 >= 0 )
          {
            *phSignature = v52;
            _InterlockedIncrement((volatile signed __int32 *)(v26 + 56));
            v13 = 0;
LABEL_97:
            if ( v26 )
              I_CryptXmlRelease(v26);
            return v13;
          }
          v46 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
          v45 = 444;
        }
        else
        {
          v46 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp");
          v45 = 434;
        }
LABEL_57:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v46, v45);
        goto LABEL_97;
      }
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= cProperty )
          goto LABEL_66;
        v48 = &rgProperty[j];
        if ( v48->dwPropId == CRYPT_XML_PROPERTY_SIGNATURE_LOCATION )
          break;
      }
      if ( v48->cbValue != 8 )
      {
        v49 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\util.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v49, 97);
LABEL_66:
        v13 = -2147024809;
        v41 = "";
        while ( 1 )
        {
          v50 = *(v41 - 1);
          v43 = v41--;
          v44 = v50 == 92;
          if ( v50 == 92 )
            break;
          if ( v41 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
          {
            v44 = v50 == 92;
            break;
          }
        }
        v45 = 405;
        goto LABEL_54;
      }
      _mm_lfence();
      v13 = I_CryptXmlSetEncodedCtxt(v26, *(const WCHAR **)v48->pvValue, v12);
      if ( v13 >= 0 )
        goto LABEL_77;
      v41 = "";
      while ( 1 )
      {
        v51 = *(v41 - 1);
        v43 = v41--;
        v44 = v51 == 92;
        if ( v51 == 92 )
          break;
        if ( v41 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
        {
          v44 = v51 == 92;
          break;
        }
      }
      v45 = 416;
    }
LABEL_54:
    if ( v44 )
      v41 = v43;
    v46 = v41;
    goto LABEL_57;
  }
  v63 = "";
  while ( 1 )
  {
    v64 = *(v63 - 1);
    v65 = v63--;
    v66 = v64 == 92;
    if ( v64 == 92 )
      break;
    if ( v63 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ctxt.cpp" )
    {
      v66 = v64 == 92;
      break;
    }
  }
  if ( v66 )
    v63 = v65;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v63, 315);
  return -2147024809;
}

```

## disassembly

```asm
0x180003fb0  mov     [rsp+arg_10], rbp
0x180003fb5  push    rsi
0x180003fb6  push    r12
0x180003fb8  push    r13
0x180003fba  push    r14
0x180003fbc  push    r15
0x180003fbe  sub     rsp, 0E0h
0x180003fc5  mov     r15, r8
0x180003fc8  mov     [rsp+108h+var_D0], 0
0x180003fd1  mov     r13d, edx
0x180003fd4  mov     rsi, rcx
0x180003fd7  xor     edx, edx; Val
0x180003fd9  lea     rcx, [rsp+108h+var_C8]; void *
0x180003fde  mov     r8d, 98h; Size
0x180003fe4  mov     r12, r9
0x180003fe7  call    memset_0
0x180003fec  mov     r14, [rsp+108h+phSignature]
0x180003ff4  test    r14, r14
0x180003ff7  jz      loc_18000461E
0x180003ffd  mov     ebp, [rsp+108h+cProperty]
0x180004004  test    ebp, ebp
0x180004006  jz      short loc_180004011
0x180004008  test    r12, r12
0x18000400b  jz      loc_18000461E
0x180004011  mov     [rsp+108h+arg_0], rbx
0x180004019  mov     ebx, 7FFFFFF8h
0x18000401e  mov     [rsp+108h+arg_8], rdi
0x180004026  mov     rdi, [rsp+108h+pEncoded]
0x18000402e  mov     dword ptr [rsp+108h+phSignature], ebx
0x180004035  test    rdi, rdi
0x180004038  jz      short loc_18000405E
0x18000403a  cmp     [rdi+4], ebx
0x18000403d  jbe     short loc_18000405E
0x18000403f  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004046  mov     esi, 80092101h
0x18000404b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004050  mov     r8, rax
0x180004053  mov     r9d, 142h
0x180004059  jmp     loc_18000411B
0x18000405e  mov     qword ptr [r14], 0
0x180004065  xor     edx, edx
0x180004067  cmp     edx, ebp
0x180004069  jnb     short loc_1800040BC
0x18000406b  lea     rcx, [rdx+rdx*2]
0x18000406f  cmp     dword ptr [r12+rcx*8], 1
0x180004074  lea     rax, [r12+rcx*8]
0x180004078  jz      short loc_18000407E
0x18000407a  inc     edx
0x18000407c  jmp     short loc_180004067
0x18000407e  cmp     dword ptr [rax+10h], 4
0x180004082  jz      short loc_1800040AC
0x180004084  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000408b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004090  mov     r8, rax
0x180004093  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000409a  mov     edx, 80070057h
0x18000409f  mov     r9d, 61h ; 'a'
0x1800040a5  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800040aa  jmp     short loc_1800040BC
0x1800040ac  lfence
0x1800040af  mov     rax, [rax+8]
0x1800040b3  mov     eax, [rax]
0x1800040b5  mov     dword ptr [rsp+108h+phSignature], eax
0x1800040bc  mov     rcx, r15; lpString
0x1800040bf  call    cs:__imp_lstrlenW
0x1800040c6  nop     dword ptr [rax+rax+00h]
0x1800040cb  mov     rcx, [rsp+108h+var_C8]
0x1800040d0  test    eax, eax
0x1800040d2  mov     [rsp+108h+var_C0], eax
0x1800040d6  cmovnz  rcx, r15
0x1800040da  mov     [rsp+108h+var_C8], rcx
0x1800040df  cmp     eax, 100h
0x1800040e4  jbe     short loc_180004155
0x1800040e6  mov     esi, 80092101h
0x1800040eb  lea     rdx, aOnecoreDsSecur_12+2Eh; ""
0x1800040f2  lea     rbp, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800040f9  movzx   eax, byte ptr [rdx-1]
0x1800040fd  mov     rcx, rdx
0x180004100  dec     rdx
0x180004103  cmp     al, 5Ch ; '\'
0x180004105  jz      short loc_18000410E
0x180004107  cmp     rdx, rbp
0x18000410a  ja      short loc_1800040F9
0x18000410c  cmp     al, 5Ch ; '\'
0x18000410e  cmovz   rdx, rcx
0x180004112  mov     r9d, 165h
0x180004118  mov     r8, rdx
0x18000411b  mov     edx, esi
0x18000411d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180004124  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180004129  mov     rbx, [rsp+108h+arg_0]
0x180004131  mov     eax, esi
0x180004133  mov     rdi, [rsp+108h+arg_8]
0x18000413b  mov     rbp, [rsp+108h+arg_10]
0x180004143  add     rsp, 0E0h
0x18000414a  pop     r15
0x18000414c  pop     r14
0x18000414e  pop     r13
0x180004150  pop     r12
0x180004152  pop     rsi
0x180004153  retn
0x180004155  xor     r8d, r8d; dwMaximumSize
0x180004158  xor     edx, edx; dwInitialSize
0x18000415a  xor     ecx, ecx; flOptions
0x18000415c  xor     ebx, ebx
0x18000415e  call    cs:__imp_HeapCreate
0x180004165  nop     dword ptr [rax+rax+00h]
0x18000416a  mov     [rsp+108h+hHeap], rax
0x18000416f  test    rax, rax
0x180004172  jnz     short loc_1800041D0
0x180004174  call    cs:__imp_GetLastError
0x18000417b  nop     dword ptr [rax+rax+00h]
0x180004180  mov     esi, eax
0x180004182  test    eax, eax
0x180004184  jle     short loc_18000418F
0x180004186  movzx   esi, ax
0x180004189  or      esi, 80070000h
0x18000418f  lea     r8, aOnecoreDsSecur_12+2Eh; ""
0x180004196  lea     rdx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000419d  movzx   eax, byte ptr [r8-1]
0x1800041a2  mov     rcx, r8
0x1800041a5  dec     r8
0x1800041a8  cmp     al, 5Ch ; '\'
0x1800041aa  jz      short loc_1800041B3
0x1800041ac  cmp     r8, rdx
0x1800041af  ja      short loc_18000419D
0x1800041b1  cmp     al, 5Ch ; '\'
0x1800041b3  cmovz   r8, rcx
0x1800041b7  mov     r9d, 99h
0x1800041bd  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800041c4  mov     edx, esi
0x1800041c6  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800041cb  jmp     loc_180004351
0x1800041d0  mov     edx, r13d
0x1800041d3  mov     r8d, 0F8h; dwBytes
0x1800041d9  sar     edx, 1Fh
0x1800041dc  mov     rcx, rax; hHeap
0x1800041df  and     edx, 1
0x1800041e2  add     edx, 8; dwFlags
0x1800041e5  call    cs:__imp_HeapAlloc
0x1800041ec  nop     dword ptr [rax+rax+00h]
0x1800041f1  mov     rdi, rax
0x1800041f4  test    rax, rax
0x1800041f7  jnz     short loc_18000423A
0x1800041f9  lea     rbp, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004200  mov     rcx, rbp; char *
0x180004203  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004208  mov     esi, 8007000Eh
0x18000420d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180004214  mov     edx, esi
0x180004216  mov     r8, rax
0x180004219  mov     r9d, 0A2h
0x18000421f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180004224  mov     rcx, [rsp+108h+hHeap]; hHeap
0x180004229  call    cs:__imp_HeapDestroy
0x180004230  nop     dword ptr [rax+rax+00h]
0x180004235  jmp     loc_18000435C
0x18000423a  xor     ecx, ecx
0x18000423c  mov     dword ptr [rax+38h], 1
0x180004243  mov     dword ptr [rax], 44444441h
0x180004249  mov     rax, [rsp+108h+hHeap]
0x18000424e  mov     [rdi+30h], rax
0x180004252  lea     rax, ?I_CRYPT_XML_HANDLE_FREE_DOC@@YAJPEAU_HXML_HANDLE@@@Z; I_CRYPT_XML_HANDLE_FREE_DOC(_HXML_HANDLE *)
0x180004259  mov     [rdi+70h], rax
0x18000425d  mov     [rdi+3Ch], r13d
0x180004261  mov     qword ptr [rdi+40h], 0Ch
0x180004269  mov     [rdi+48h], ecx
0x18000426c  mov     [rdi+50h], rcx
0x180004270  mov     [rdi+58h], rcx
0x180004274  mov     [rdi+60h], rcx
0x180004278  test    r13d, r13d
0x18000427b  js      short loc_18000429D
0x18000427d  lea     rcx, [rdi+8]; lpCriticalSection
0x180004281  call    cs:__imp_InitializeCriticalSection
0x180004288  nop     dword ptr [rax+rax+00h]
0x18000428d  lea     rax, _CRYPT_XML_HANDLE_UNLOCK
0x180004294  lea     rcx, _CRYPT_XML_HANDLE_LOCK
0x18000429b  jmp     short loc_1800042A0
0x18000429d  mov     rax, rcx
0x1800042a0  mov     [rdi+78h], rcx
0x1800042a4  mov     r8, rdi
0x1800042a7  mov     [rdi+80h], rax
0x1800042ae  mov     edx, 1
0x1800042b3  or      dword ptr [rdi+48h], 80000000h
0x1800042ba  lea     rax, [rdi+0C8h]
0x1800042c1  mov     [rdi+88h], rax
0x1800042c8  mov     dword ptr [rax], 28h ; '('
0x1800042ce  mov     [rax+8], rdi
0x1800042d2  mov     rax, [rdi+88h]
0x1800042d9  mov     [rax+10h], rsi
0x1800042dd  mov     rcx, [rdi+88h]
0x1800042e4  mov     dword ptr [rdi+90h], 1
0x1800042ee  lea     rax, [rcx+28h]
0x1800042f2  mov     [rcx+20h], rax
0x1800042f6  mov     rax, [rdi+88h]
0x1800042fd  mov     ecx, dword ptr [rsp+108h+phSignature]
0x180004304  mov     [rdi+68h], rax
0x180004308  call    I_CryptXmlWsStateInitialize
0x18000430d  mov     esi, eax
0x18000430f  test    eax, eax
0x180004311  jns     short loc_180004338
0x180004313  lea     rcx, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000431a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000431f  mov     r8, rax
0x180004322  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180004329  mov     edx, esi
0x18000432b  mov     r9d, 0C4h
0x180004331  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180004336  jmp     short loc_180004341
0x180004338  mov     rbx, rdi
0x18000433b  lock inc dword ptr [rdi+38h]
0x18000433f  xor     esi, esi
0x180004341  mov     rcx, rdi
0x180004344  call    I_CryptXmlRelease
0x180004349  mov     rdi, [rsp+108h+pEncoded]
0x180004351  test    esi, esi
0x180004353  jns     short loc_180004380
0x180004355  lea     rbp, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000435c  mov     rcx, rbp; char *
0x18000435f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004364  mov     r8, rax
0x180004367  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000436e  mov     edx, esi
0x180004370  mov     r9d, 173h
0x180004376  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000437b  jmp     loc_180004608
0x180004380  mov     [rbx+0A8h], r12
0x180004387  mov     [rbx+0B0h], ebp
0x18000438d  test    r15, r15
0x180004390  jz      short loc_1800043F2
0x180004392  mov     r9d, 1
0x180004398  mov     r8d, 0FFFFFFFFh
0x18000439e  mov     rdx, r15
0x1800043a1  mov     rcx, rbx
0x1800043a4  call    I_CryptXmlCheckUniqueId
0x1800043a9  mov     esi, eax
0x1800043ab  test    eax, eax
0x1800043ad  jns     short loc_1800043F2
0x1800043af  lea     rbp, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800043b6  lea     rdx, aOnecoreDsSecur_12+2Eh; ""
0x1800043bd  movzx   eax, byte ptr [rdx-1]
0x1800043c1  mov     rcx, rdx
0x1800043c4  dec     rdx
0x1800043c7  cmp     al, 5Ch ; '\'
0x1800043c9  jz      short loc_1800043D2
0x1800043cb  cmp     rdx, rbp
0x1800043ce  ja      short loc_1800043BD
0x1800043d0  cmp     al, 5Ch ; '\'
0x1800043d2  mov     r9d, 184h
0x1800043d8  cmovz   rdx, rcx
0x1800043dc  mov     r8, rdx
0x1800043df  mov     edx, esi
0x1800043e1  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800043e8  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800043ed  jmp     loc_180004608
0x1800043f2  test    rdi, rdi
0x1800043f5  jz      loc_1800044C6
0x1800043fb  cmp     dword ptr [rdi+4], 0
0x1800043ff  jbe     loc_1800044C6
0x180004405  xor     edx, edx
0x180004407  cmp     edx, ebp
0x180004409  jnb     short loc_18000444A
0x18000440b  lea     rcx, [rdx+rdx*2]
0x18000440f  cmp     dword ptr [r12+rcx*8], 2
0x180004414  lea     rax, [r12+rcx*8]
0x180004418  jz      short loc_18000441E
0x18000441a  inc     edx
0x18000441c  jmp     short loc_180004407
0x18000441e  cmp     dword ptr [rax+10h], 8
0x180004422  jz      short loc_18000447D
0x180004424  lea     rcx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000442b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180004430  mov     r8, rax
0x180004433  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000443a  mov     edx, 80070057h
0x18000443f  mov     r9d, 61h ; 'a'
0x180004445  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000444a  mov     esi, 80070057h
0x18000444f  lea     rbp, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004456  lea     rdx, aOnecoreDsSecur_12+2Eh; ""
0x18000445d  movzx   eax, byte ptr [rdx-1]
0x180004461  mov     rcx, rdx
0x180004464  dec     rdx
0x180004467  cmp     al, 5Ch ; '\'
0x180004469  jz      short loc_180004472
0x18000446b  cmp     rdx, rbp
0x18000446e  ja      short loc_18000445D
0x180004470  cmp     al, 5Ch ; '\'
0x180004472  mov     r9d, 195h
0x180004478  jmp     loc_1800043D8
0x18000447d  lfence
0x180004480  mov     rdx, [rax+8]
0x180004484  mov     r8, rdi
0x180004487  mov     rcx, rbx
0x18000448a  mov     rdx, [rdx]
0x18000448d  call    I_CryptXmlSetEncodedCtxt
0x180004492  mov     esi, eax
0x180004494  test    eax, eax
0x180004496  jns     short loc_1800044C6
0x180004498  lea     rbp, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\xml\\"...
  ... truncated ...
```
