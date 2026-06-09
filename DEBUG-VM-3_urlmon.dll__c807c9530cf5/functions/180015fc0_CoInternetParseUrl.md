# CoInternetParseUrl

- ea: `0x180015fc0`
- end: `0x180016634`
- name: `CoInternetParseUrl`
- size: `1652`
- prototype: `HRESULT __stdcall(LPCWSTR pwzUrl, PARSEACTION ParseAction, DWORD dwFlags, LPWSTR pszResult, DWORD cchResult, DWORD *pcchResult, DWORD dwReserved)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013c30`
- `0x180016640`
- `0x180017620`
- `0x1800f0674`

## callees

- `0x180015fc0`
- `0x180017590`
- `0x18001e340`
- `0x18006a260`
- `0x18011ba3e`
- `0x18011ba6e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180016438`
- `msvcrt!memcpy_s` at `0x18001645e`
- `msvcrt!memcpy_s` at `0x180016438`
- `msvcrt!memcpy_s` at `0x18001645e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016056`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016056`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800160ce`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800160f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001613f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800160ce`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800160f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001613f`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x18001625c`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x18001625c`
- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x18001654c`
- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x18001654c`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18001650a`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18001650a`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x18001628c`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x1800163f8`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x18001628c`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x1800163f8`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180016530`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x180016530`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x1800164b8`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x1800164b8`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x1800163a5`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x1800163a5`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x1800164e1`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x1800164e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016071`

## pseudocode

```c
HRESULT __stdcall CoInternetParseUrl(
        LPCWSTR pwzUrl,
        PARSEACTION ParseAction,
        DWORD dwFlags,
        LPWSTR pszResult,
        DWORD cchResult,
        DWORD *pcchResult,
        DWORD dwReserved)
{
  unsigned int v10; // eax
  bool v11; // zf
  int v12; // eax
  unsigned int *v13; // rdi
  __int64 v14; // rbp
  unsigned __int64 v15; // r12
  COInetSession *v16; // rsi
  unsigned int v17; // ecx
  __int64 v18; // rax
  HRESULT v19; // ebx
  COInetSession *v20; // rsi
  HRESULT v21; // eax
  HRESULT result; // eax
  DWORD v23; // r9d
  DWORD *v24; // r8
  WCHAR *v25; // rdx
  unsigned __int64 v26; // rdx
  int v27; // ebx
  __int64 v28; // rax
  const wchar_t *v29; // rcx
  LPWSTR v30; // r8
  LPWSTR v31; // rcx
  UINT cchProtocol; // ecx
  UINT v33; // eax
  LPCWSTR pszProtocol; // r8
  WCHAR *v35; // rbx
  const unsigned __int16 *LocationW; // rax
  int v37; // [rsp+40h] [rbp-68h] BYREF
  PARSEDURLW ppu; // [rsp+48h] [rbp-60h] BYREF
  DWORD pcchOut; // [rsp+B0h] [rbp+8h] BYREF
  _tagPARSEACTION v40; // [rsp+B8h] [rbp+10h]

  v40 = ParseAction;
  v10 = IsKnownProtocol(pwzUrl);
  if ( !v10 || (v11 = v10 == 7, v12 = 1, v11) )
    v12 = 0;
  if ( !pwzUrl )
    return -2147024809;
  if ( !pszResult )
    return -2147024809;
  v13 = pcchResult;
  if ( !pcchResult )
    return -2147024809;
  v14 = -1;
  v15 = cchResult;
  if ( !g_bShortcircuitKnownProtocols || !v12 )
  {
    EnterCriticalSection(&g_mxsOInet);
    v16 = g_pCOInetSession;
    if ( g_pCOInetSession )
    {
      v19 = 0;
    }
    else
    {
      v16 = (COInetSession *)CoTaskMemAlloc(0x180u);
      if ( v16 )
      {
        *((_DWORD *)v16 + 5) = 0;
        memset_0((char *)v16 + 40, 0, 0x158u);
        *(_QWORD *)v16 = &COInetSession::`vftable'{for `IInternetSession'};
        *((_DWORD *)v16 + 4) = 1;
        *((_QWORD *)v16 + 1) = &COInetSession::`vftable'{for `IInternetProtocolInfo'};
        *((_QWORD *)v16 + 3) = &CProtMgr::`vftable';
        *((_DWORD *)v16 + 8) = 1;
        *((_DWORD *)v16 + 9) = -1;
        InitializeCriticalSection((LPCRITICAL_SECTION)v16 + 1);
        *((_QWORD *)v16 + 11) = 0;
        *((_QWORD *)v16 + 10) = 0;
        *((_QWORD *)v16 + 12) = &CProtMgr::`vftable';
        *((_DWORD *)v16 + 26) = 1;
        *((_DWORD *)v16 + 27) = -1;
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v16 + 112));
        *((_QWORD *)v16 + 20) = 0;
        *((_QWORD *)v16 + 19) = 0;
        *((_QWORD *)v16 + 21) = 0;
        *((_DWORD *)v16 + 27) = 0;
        *((_QWORD *)v16 + 12) = &CProtMgrNameSpace::`vftable';
        *((_QWORD *)v16 + 22) = &CProtMgr::`vftable';
        *((_DWORD *)v16 + 46) = 1;
        *((_DWORD *)v16 + 47) = -1;
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v16 + 192));
        *((_QWORD *)v16 + 30) = 0;
        v17 = 0;
        *((_QWORD *)v16 + 29) = 0;
        *((_QWORD *)v16 + 22) = &CProtMgrMimeHandler::`vftable';
        *((_DWORD *)v16 + 62) = 8;
        do
        {
          v18 = v17++;
          *((_QWORD *)v16 + 2 * v18 + 33) = 0;
        }
        while ( v17 < *((_DWORD *)v16 + 62) );
        _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
        v19 = 0;
        g_pCOInetSession = v16;
      }
      else
      {
        v16 = g_pCOInetSession;
        v19 = -2147024882;
      }
      if ( !v16 )
      {
        v19 = -2147024882;
        LeaveCriticalSection(&g_mxsOInet);
        goto LABEL_20;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)v16 + 4);
    v20 = g_pCOInetSession;
    LeaveCriticalSection(&g_mxsOInet);
    if ( !v19 )
    {
      v21 = COInetSession::ParseUrl(
              (COInetSession *)((char *)v20 + 8),
              pwzUrl,
              v40,
              dwFlags,
              pszResult,
              v15,
              v13,
              dwReserved);
      _InterlockedDecrement((volatile signed __int32 *)v20 + 4);
      v19 = v21;
    }
LABEL_20:
    if ( v19 != -2146697199 )
      return v19;
  }
  v19 = -2147467259;
  switch ( v40 )
  {
    case PARSE_CANONICALIZE:
      *v13 = v15;
      return UrlCanonicalizeW(pwzUrl, pszResult, v13, dwFlags);
    case PARSE_ROOTDOCUMENT:
      memset(&ppu, 0, sizeof(ppu));
      ppu.cbSize = 40;
      if ( ParseURLW(pwzUrl, &ppu) < 0 )
        return v19;
      switch ( ppu.nScheme )
      {
        case 1u:
        case 2u:
        case 5u:
        case 6u:
        case 7u:
        case 0xBu:
        case 0xDu:
          pcchOut = 1;
          if ( UrlGetPartW(pwzUrl, pszResult, &pcchOut, 2u, 0) != -2147467261 )
            return v19;
          cchProtocol = ppu.cchProtocol;
          v33 = ppu.cchProtocol + 3;
          if ( ppu.cchProtocol + 3 < ppu.cchProtocol )
          {
            v33 = -1;
          }
          else
          {
            pcchOut = ppu.cchProtocol + 3;
            if ( (unsigned int)v15 >= v33 )
            {
              pszProtocol = ppu.pszProtocol;
              *v13 = ppu.cchProtocol + 2;
              memcpy_s(pszResult, 2 * v15, pszProtocol, 2LL * cchProtocol);
              v35 = &pszResult[ppu.cchProtocol];
              memcpy_s(v35, 2LL * (unsigned int)(v15 - ppu.cchProtocol), L"://", 6u);
              v25 = v35 + 3;
              v23 = 2;
              v24 = (DWORD *)&v37;
              v37 = v15 - (v35 + 3 - pszResult);
              goto LABEL_25;
            }
          }
          *v13 = v33;
          result = -2147024882;
          break;
        default:
          return v19;
      }
      return result;
    case PARSE_ENCODE_IS_UNESCAPE:
    case PARSE_UNESCAPE:
      *v13 = v15;
      return UrlUnescapeW((PWSTR)pwzUrl, pszResult, v13, dwFlags);
    case PARSE_DECODE_IS_ESCAPE:
    case PARSE_ESCAPE:
      *v13 = v15;
      return UrlEscapeW(pwzUrl, pszResult, v13, dwFlags);
    case PARSE_PATH_FROM_URL:
      *v13 = v15;
      return PathCreateFromUrlW(pwzUrl, pszResult, v13, dwFlags);
    case PARSE_URL_FROM_PATH:
      *v13 = v15;
      return UrlCreateFromPathW(pwzUrl, pszResult, v13, dwFlags);
    case PARSE_SCHEMA:
      v23 = 1;
      goto LABEL_24;
    case PARSE_DOMAIN:
      if ( !wcsncmp_0(pwzUrl, L"blob:", 5u) )
      {
        v26 = v15;
        if ( v15 <= 0x7FFFFFFF )
        {
          if ( !(_DWORD)v15 )
          {
            *v13 = 11;
            return 1;
          }
          v28 = 11;
          v29 = L"about:blob";
          v30 = pszResult;
          do
          {
            if ( !v28 )
              break;
            if ( !*v29 )
              break;
            *v30++ = *v29++;
            --v28;
            --v26;
          }
          while ( v26 );
          v31 = v30 - 1;
          v27 = -2147024774;
          if ( v26 )
          {
            v31 = v30;
            v27 = 0;
          }
          *v31 = 0;
          if ( v26 )
            goto LABEL_39;
        }
        else
        {
          v27 = -2147024809;
        }
        *pszResult = 0;
LABEL_39:
        *v13 = (v27 >> 31) + 12;
        return (unsigned int)v27 >> 31;
      }
      v23 = 2;
LABEL_24:
      *v13 = v15;
      v24 = v13;
      v25 = pszResult;
LABEL_25:
      result = UrlGetPartW(pwzUrl, v25, v24, v23, 0);
      break;
    case PARSE_LOCATION:
      *v13 = 0;
      LocationW = UrlGetLocationW(pwzUrl);
      if ( LocationW )
      {
        do
          ++v14;
        while ( LocationW[v14] );
        if ( (unsigned int)v14 < (unsigned int)v15 )
        {
          StringCchCopyW(pszResult, v15, LocationW);
          *v13 = v14;
          return 0;
        }
      }
      return v19;
    default:
      return v19;
  }
  return result;
}

```

## disassembly

```asm
0x180015fc0  mov     [rsp+arg_8], edx
0x180015fc4  push    rsi
0x180015fc5  push    r13
0x180015fc7  push    r14
0x180015fc9  push    r15
0x180015fcb  sub     rsp, 88h
0x180015fd2  mov     r14, r9
0x180015fd5  mov     r13d, r8d
0x180015fd8  mov     r15, rcx
0x180015fdb  call    ?IsKnownProtocol@@YAKPEBG@Z; IsKnownProtocol(ushort const *)
0x180015fe0  xor     esi, esi
0x180015fe2  test    eax, eax
0x180015fe4  jz      short loc_180015FF0
0x180015fe6  cmp     eax, 7
0x180015fe9  mov     eax, 1
0x180015fee  jnz     short loc_180015FF2
0x180015ff0  mov     eax, esi
0x180015ff2  mov     [rsp+0A8h+arg_10], rbx
0x180015ffa  mov     [rsp+0A8h+var_30], rdi
0x180015fff  test    r15, r15
0x180016002  jz      loc_180016592
0x180016008  test    r14, r14
0x18001600b  jz      loc_180016592
0x180016011  mov     rdi, [rsp+0A8h+pcchResult]
0x180016019  test    rdi, rdi
0x18001601c  jz      loc_180016592
0x180016022  cmp     cs:?g_bShortcircuitKnownProtocols@@3EA, sil; uchar g_bShortcircuitKnownProtocols
0x180016029  mov     [rsp+0A8h+var_28], rbp
0x180016031  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180016038  mov     [rsp+0A8h+var_38], r12
0x18001603d  mov     r12d, [rsp+0A8h+cchResult]
0x180016045  jz      short loc_18001604F
0x180016047  test    eax, eax
0x180016049  jnz     loc_180016221
0x18001604f  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180016056  call    cs:__imp_EnterCriticalSection
0x18001605c  mov     rsi, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180016063  test    rsi, rsi
0x180016066  jnz     loc_1800161BE
0x18001606c  mov     ecx, 180h; cb
0x180016071  call    cs:__imp_CoTaskMemAlloc
0x180016077  mov     rsi, rax
0x18001607a  test    rax, rax
0x18001607d  jz      loc_180016199
0x180016083  xor     eax, eax
0x180016085  lea     rcx, [rsi+28h]; void *
0x180016089  xor     edx, edx; Val
0x18001608b  mov     [rsi+14h], eax
0x18001608e  mov     r8d, 158h; Size
0x180016094  call    memset_0
0x180016099  lea     rax, ??_7COInetSession@@6BIInternetSession@@@; const COInetSession::`vftable'{for `IInternetSession'}
0x1800160a0  mov     [rsi], rax
0x1800160a3  lea     rbx, ??_7CProtMgr@@6B@; const CProtMgr::`vftable'
0x1800160aa  lea     rax, ??_7COInetSession@@6BIInternetProtocolInfo@@@; const COInetSession::`vftable'{for `IInternetProtocolInfo'}
0x1800160b1  mov     dword ptr [rsi+10h], 1
0x1800160b8  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800160bc  mov     [rsi+8], rax
0x1800160c0  mov     [rsi+18h], rbx
0x1800160c4  mov     dword ptr [rsi+20h], 1
0x1800160cb  mov     [rsi+24h], ebp
0x1800160ce  call    cs:__imp_InitializeCriticalSection
0x1800160d4  mov     qword ptr [rsi+58h], 0
0x1800160dc  lea     rcx, [rsi+70h]; lpCriticalSection
0x1800160e0  mov     qword ptr [rsi+50h], 0
0x1800160e8  mov     [rsi+60h], rbx
0x1800160ec  mov     dword ptr [rsi+68h], 1
0x1800160f3  mov     [rsi+6Ch], ebp
0x1800160f6  call    cs:__imp_InitializeCriticalSection
0x1800160fc  xor     ecx, ecx
0x1800160fe  lea     rax, ??_7CProtMgrNameSpace@@6B@; const CProtMgrNameSpace::`vftable'
0x180016105  mov     [rsi+0A0h], rcx
0x18001610c  mov     [rsi+98h], rcx
0x180016113  mov     [rsi+0A8h], rcx
0x18001611a  mov     [rsi+6Ch], ecx
0x18001611d  lea     rcx, [rsi+0C0h]; lpCriticalSection
0x180016124  mov     [rsi+60h], rax
0x180016128  mov     [rsi+0B0h], rbx
0x18001612f  mov     dword ptr [rsi+0B8h], 1
0x180016139  mov     [rsi+0BCh], ebp
0x18001613f  call    cs:__imp_InitializeCriticalSection
0x180016145  xor     edx, edx
0x180016147  lea     rax, ??_7CProtMgrMimeHandler@@6B@; const CProtMgrMimeHandler::`vftable'
0x18001614e  mov     [rsi+0F0h], rdx
0x180016155  mov     ecx, edx
0x180016157  mov     [rsi+0E8h], rdx
0x18001615e  mov     [rsi+0B0h], rax
0x180016165  mov     dword ptr [rsi+0F8h], 8
0x18001616f  nop
0x180016170  mov     eax, ecx
0x180016172  inc     ecx
0x180016174  add     rax, rax
0x180016177  mov     [rsi+rax*8+108h], rdx
0x18001617f  cmp     ecx, [rsi+0F8h]
0x180016185  jb      short loc_180016170
0x180016187  lock inc cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x18001618e  mov     ebx, edx
0x180016190  mov     cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA, rsi; COInetSession * g_pCOInetSession
0x180016197  jmp     short loc_1800161A5
0x180016199  mov     rsi, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x1800161a0  mov     ebx, 8007000Eh
0x1800161a5  test    rsi, rsi
0x1800161a8  jnz     short loc_1800161C0
0x1800161aa  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x1800161b1  mov     ebx, 8007000Eh
0x1800161b6  call    cs:__imp_LeaveCriticalSection
0x1800161bc  jmp     short loc_180016213
0x1800161be  xor     ebx, ebx
0x1800161c0  lock inc dword ptr [rsi+10h]
0x1800161c4  mov     rsi, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x1800161cb  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x1800161d2  call    cs:__imp_LeaveCriticalSection
0x1800161d8  test    ebx, ebx
0x1800161da  jnz     short loc_180016213
0x1800161dc  mov     eax, [rsp+0A8h+dwReserved]
0x1800161e3  lea     rcx, [rsi+8]; this
0x1800161e7  mov     r8d, [rsp+0A8h+arg_8]; enum _tagPARSEACTION
0x1800161ef  mov     r9d, r13d; unsigned int
0x1800161f2  mov     [rsp+0A8h+var_70], eax; unsigned int
0x1800161f6  mov     rdx, r15; unsigned __int16 *
0x1800161f9  mov     [rsp+0A8h+var_78], rdi; unsigned int *
0x1800161fe  mov     [rsp+0A8h+var_80], r12d; unsigned int
0x180016203  mov     qword ptr [rsp+0A8h+dwFlags], r14; unsigned __int16 *
0x180016208  call    ?ParseUrl@COInetSession@@UEAAJPEBGW4_tagPARSEACTION@@KPEAGKPEAKK@Z; COInetSession::ParseUrl(ushort const *,_tagPARSEACTION,ulong,ushort *,ulong,ulong *,ulong)
0x18001620d  lock dec dword ptr [rsi+10h]
0x180016211  mov     ebx, eax
0x180016213  cmp     ebx, 800C0011h
0x180016219  jnz     def_18001624B; jumptable 000000018001624B default case, cases 2,3,5,6,11,12,14,17
0x18001621f  xor     esi, esi
0x180016221  mov     eax, [rsp+0A8h+arg_8]
0x180016228  mov     ebx, 80004005h
0x18001622d  dec     eax; switch 19 cases
0x18001622f  cmp     eax, 12h
0x180016232  ja      def_18001624B; jumptable 000000018001624B default case, cases 2,3,5,6,11,12,14,17
0x180016238  cdqe
0x18001623a  lea     rcx, __ImageBase
0x180016241  mov     eax, ds:(jpt_18001624B - 180000000h)[rcx+rax*4]
0x180016248  add     rax, rcx
0x18001624b  jmp     rax; switch jump
0x18001624d  mov     r9d, r13d; jumptable 000000018001624B case 1
0x180016250  mov     [rdi], r12d
0x180016253  mov     r8, rdi; pcchCanonicalized
0x180016256  mov     rdx, r14; pszCanonicalized
0x180016259  mov     rcx, r15; pszUrl
0x18001625c  call    cs:__imp_UrlCanonicalizeW
0x180016262  mov     r12, [rsp+0A8h+var_38]
0x180016267  mov     ebx, eax
0x180016269  mov     rbp, [rsp+0A8h+var_28]
0x180016271  jmp     loc_180016597
0x180016276  mov     r9d, 1; jumptable 000000018001624B case 13
0x18001627c  mov     [rdi], r12d
0x18001627f  mov     r8, rdi; pcchOut
0x180016282  mov     rdx, r14; pszOut
0x180016285  mov     rcx, r15; pszIn
0x180016288  mov     [rsp+0A8h+dwFlags], esi; dwFlags
0x18001628c  call    cs:__imp_UrlGetPartW
0x180016292  mov     r12, [rsp+0A8h+var_38]
0x180016297  mov     ebx, eax
0x180016299  mov     rbp, [rsp+0A8h+var_28]
0x1800162a1  jmp     loc_180016597
0x1800162a6  mov     r8d, 5; jumptable 000000018001624B case 15
0x1800162ac  lea     rdx, aBlob_0; "blob:"
0x1800162b3  mov     rcx, r15; String1
0x1800162b6  call    wcsncmp_0
0x1800162bb  test    eax, eax
0x1800162bd  jnz     loc_180016376
0x1800162c3  mov     rdx, r12
0x1800162c6  cmp     r12, 7FFFFFFFh
0x1800162cd  jbe     short loc_1800162D6
0x1800162cf  mov     ebx, 80070057h
0x1800162d4  jmp     short loc_180016351
0x1800162d6  test    r12d, r12d
0x1800162d9  jnz     short loc_180016301
0x1800162db  mov     ebx, 8007007Ah
0x1800162e0  mov     eax, ebx
0x1800162e2  sar     eax, 1Fh
0x1800162e5  add     eax, 0Ch
0x1800162e8  mov     [rdi], eax
0x1800162ea  mov     r12, [rsp+0A8h+var_38]
0x1800162ef  mov     rbp, [rsp+0A8h+var_28]
0x1800162f7  shr     ebx, 1Fh
0x1800162fa  mov     eax, ebx
0x1800162fc  jmp     loc_180016597
0x180016301  mov     eax, 0Bh
0x180016306  lea     rcx, aAboutBlob; "about:blob"
0x18001630d  mov     r8, r14
0x180016310  test    rax, rax
0x180016313  jz      short loc_180016334
0x180016315  movzx   r9d, word ptr [rcx]
0x180016319  test    r9w, r9w
0x18001631d  jz      short loc_180016334
0x18001631f  mov     [r8], r9w
0x180016323  add     rcx, 2
0x180016327  add     r8, 2
0x18001632b  dec     rax
0x18001632e  sub     rdx, 1
0x180016332  jnz     short loc_180016310
0x180016334  test    rdx, rdx
0x180016337  lea     rcx, [r8-2]
0x18001633b  mov     ebx, 8007007Ah
0x180016340  cmovnz  rcx, r8
0x180016344  cmovnz  ebx, esi
0x180016347  mov     [rcx], si
0x18001634a  jnz     short loc_180016355
0x18001634c  test    r12d, r12d
0x18001634f  jz      short loc_180016355
0x180016351  mov     [r14], si
0x180016355  mov     eax, ebx
0x180016357  sar     eax, 1Fh
0x18001635a  add     eax, 0Ch
0x18001635d  mov     [rdi], eax
0x18001635f  mov     r12, [rsp+0A8h+var_38]
0x180016364  mov     rbp, [rsp+0A8h+var_28]
0x18001636c  shr     ebx, 1Fh
0x18001636f  mov     eax, ebx
0x180016371  jmp     loc_180016597
0x180016376  mov     r9d, 2
0x18001637c  jmp     loc_18001627C
0x180016381  xorps   xmm0, xmm0; jumptable 000000018001624B case 4
0x180016384  lea     rdx, [rsp+0A8h+ppu]; ppu
0x180016389  xor     eax, eax
0x18001638b  mov     rcx, r15; pcszURL
0x18001638e  movups  xmmword ptr [rsp+0A8h+ppu.cbSize], xmm0
0x180016393  mov     [rsp+0A8h+ppu.cbSize], 28h ; '('
0x18001639b  movups  xmmword ptr [rsp+0A8h+ppu.cchProtocol], xmm0
0x1800163a0  mov     qword ptr [rsp+0A8h+ppu.cchSuffix], rax
0x1800163a5  call    cs:__imp_ParseURLW
0x1800163ab  test    eax, eax
0x1800163ad  js      def_18001624B; jumptable 000000018001624B default case, cases 2,3,5,6,11,12,14,17
0x1800163b3  mov     eax, [rsp+0A8h+ppu.nScheme]
0x1800163b7  dec     eax; switch 13 cases
0x1800163b9  cmp     eax, 0Ch
0x1800163bc  ja      def_18001624B; jumptable 000000018001624B default case, cases 2,3,5,6,11,12,14,17
0x1800163c2  lea     rcx, __ImageBase
0x1800163c9  mov     eax, ds:(jpt_1800163D3 - 180000000h)[rcx+rax*4]
0x1800163d0  add     rax, rcx
0x1800163d3  jmp     rax; switch jump
0x1800163d5  mov     r9d, 2; jumptable 00000001800163D3 cases 1,2,5-7,11,13
0x1800163db  mov     [rsp+0A8h+pcchOut], 1
0x1800163e6  lea     r8, [rsp+0A8h+pcchOut]; pcchOut
0x1800163ee  mov     [rsp+0A8h+dwFlags], esi; dwFlags
0x1800163f2  mov     rdx, r14; pszOut
0x1800163f5  mov     rcx, r15; pszIn
0x1800163f8  call    cs:__imp_UrlGetPartW
0x1800163fe  cmp     eax, 80004003h
0x180016403  jnz     def_18001624B; jumptable 000000018001624B default case, cases 2,3,5,6,11,12,14,17
0x180016409  mov     ecx, [rsp+0A8h+ppu.cchProtocol]
0x18001640d  lea     eax, [rcx+3]
0x180016410  cmp     eax, ecx
0x180016412  jb      short loc_180016489
0x180016414  mov     [rsp+0A8h+pcchOut], eax
0x18001641b  cmp     r12d, eax
0x18001641e  jb      short loc_18001648E
0x180016420  mov     r8, [rsp+0A8h+ppu.pszProtocol]; Source
0x180016425  mov     r9d, ecx
0x180016428  dec     eax
0x18001642a  mov     rdx, r12
0x18001642d  add     r9, r9; SourceSize
0x180016430  mov     [rdi], eax
0x180016432  add     rdx, rdx; DestinationSize
0x180016435  mov     rcx, r14; Destination
0x180016438  call    cs:__imp_memcpy_s
0x18001643e  mov     ecx, [rsp+0A8h+ppu.cchProtocol]
0x180016442  lea     r8, asc_18012D998; "://"
0x180016449  mov     edx, r12d
0x18001644c  mov     r9d, 6; SourceSize
0x180016452  sub     edx, ecx
0x180016454  add     rdx, rdx; DestinationSize
0x180016457  lea     rbx, [r14+rcx*2]
0x18001645b  mov     rcx, rbx; Destination
0x18001645e  call    cs:__imp_memcpy_s
0x180016464  lea     rdx, [rbx+6]
0x180016468  mov     r9d, 2
0x18001646e  mov     rax, rdx
0x180016471  lea     r8, [rsp+0A8h+var_68]
0x180016476  sub     rax, r14
0x180016479  sar     rax, 1
0x18001647c  sub     r12d, eax
0x18001647f  mov     [rsp+0A8h+var_68], r12d
0x180016484  jmp     loc_180016285
0x180016489  mov     eax, 0FFFFFFFFh
0x18001648e  mov     r12, [rsp+0A8h+var_38]
0x180016493  mov     ebx, 8007000Eh
0x180016498  mov     rbp, [rsp+0A8h+var_28]
0x1800164a0  mov     [rdi], eax
0x1800164a2  mov     eax, ebx
0x1800164a4  jmp     loc_180016597
0x1800164a9  mov     r9d, r13d; jumptable 000000018001624B cases 7,19
0x1800164ac  mov     [rdi], r12d
0x1800164af  mov     r8, rdi; pcchUnescaped
0x1800164b2  mov     rdx, r14; pszUnescaped
0x1800164b5  mov     rcx, r15; pszUrl
0x1800164b8  call    cs:__imp_UrlUnescapeW
0x1800164be  mov     r12, [rsp+0A8h+var_38]
0x1800164c3  mov     ebx, eax
0x1800164c5  mov     rbp, [rsp+0A8h+var_28]
0x1800164cd  jmp     loc_180016597
0x1800164d2  mov     r9d, r13d; jumptable 000000018001624B cases 8,18
0x1800164d5  mov     [rdi], r12d
0x1800164d8  mov     r8, rdi; pcchEscaped
0x1800164db  mov     rdx, r14; pszEscaped
  ... truncated ...
```
