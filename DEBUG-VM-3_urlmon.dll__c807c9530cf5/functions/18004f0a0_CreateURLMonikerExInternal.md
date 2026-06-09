# CreateURLMonikerExInternal

- ea: `0x18004f0a0`
- end: `0x18004f649`
- name: `CreateURLMonikerExInternal`
- size: `1449`
- prototype: ``
- caller_count: `12`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004dd30`
- `0x18004e390`
- `0x18004eeb0`
- `0x18004eed0`
- `0x1800ba8f4`
- `0x1800bfe60`
- `0x1800ce0ac`
- `0x1800ceec0`
- `0x1800e7e70`
- `0x1800e97e0`
- `0x1800ea520`
- `0x1800efda0`

## callees

- `0x1800150e0`
- `0x1800214d0`
- `0x1800215c0`
- `0x18002d5dc`
- `0x18003b010`
- `0x1800478b0`
- `0x18004d4b4`
- `0x18004f0a0`
- `0x18004f650`
- `0x18004fb24`
- `0x180050370`
- `0x18008df68`
- `0x1800a856c`
- `0x1800e96f8`
- `0x1800f4d20`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x18004f1eb`
- `iertutil!CreateUri` at `0x18004f1eb`
- `iertutil!__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z` at `0x18004f35f`
- `iertutil!__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z` at `0x18004f35f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18004f13c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18004f13c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004f14e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18004f14e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18004f4b8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18004f4b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f265`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f265`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f63e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f514`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f63e`

## string_xrefs

- `0x18004f4d8`: `OldUri`
- `0x18004f4c2`: `NewUri`
- `0x18004f4d1`: `CreateURLMonikerDifference`

## pseudocode

```c
__int64 __fastcall CreateURLMonikerExInternal(
        struct IMoniker *a1,
        const WCHAR *a2,
        CUrlMon **a3,
        int a4,
        unsigned int a5)
{
  int v7; // esi
  unsigned int v8; // r14d
  int v9; // r12d
  __int64 v10; // rbx
  unsigned int v11; // r13d
  const WCHAR *v12; // rcx
  unsigned int v13; // ebx
  DWORD v14; // edx
  HRESULT v15; // r13d
  struct IUri *v16; // r9
  int v17; // ebx
  CUrlMon *v18; // rax
  CUrlMon *v19; // rax
  const unsigned __int16 *v21; // rdi
  int v22; // eax
  const WCHAR *v23; // rbx
  int v24; // eax
  HRESULT IsFeatureEnabledInternal; // eax
  unsigned __int16 **v26; // r9
  unsigned __int16 *v27; // r13
  unsigned int v28; // eax
  CUrlMon *v29; // r9
  CUrlMon *v30; // rax
  unsigned __int64 *v31; // [rsp+20h] [rbp-81h]
  int v32; // [rsp+20h] [rbp-81h]
  const WCHAR *psz2; // [rsp+40h] [rbp-61h]
  int v34; // [rsp+4Ch] [rbp-55h] BYREF
  int v35; // [rsp+50h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-49h]
  IUri *ppURI; // [rsp+60h] [rbp-41h] BYREF
  unsigned __int64 v38[2]; // [rsp+68h] [rbp-39h] BYREF
  unsigned int v39; // [rsp+78h] [rbp-29h]
  void **v40; // [rsp+80h] [rbp-21h] BYREF
  LPVOID v41; // [rsp+88h] [rbp-19h]
  __int64 v42; // [rsp+90h] [rbp-11h]
  void *v43; // [rsp+98h] [rbp-9h]
  __int64 v44; // [rsp+A0h] [rbp-1h]
  _QWORD v45[9]; // [rsp+A8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]
  struct IUri *nChar; // [rsp+110h] [rbp+6Fh] BYREF
  int v49; // [rsp+118h] [rbp+77h]

  v49 = a4;
  ppURI = 0;
  _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
  if ( !a3 )
  {
    v17 = -2147024809;
    goto LABEL_39;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v17 = -2147024809;
    goto LABEL_39;
  }
  v7 = a4 & 1;
  v8 = 50342549;
  v9 = a4 & 2;
  if ( (a4 & 2) != 0 )
  {
    a5 = 50342549;
  }
  else
  {
    a5 = 50342789;
    if ( (a4 & 1) == 0 )
    {
      v10 = -1;
      a5 = 50375589;
      do
        ++v10;
      while ( a2[v10] );
      pv = 0;
      v11 = v10;
      LODWORD(nChar) = v10;
      psz2 = a2;
      goto LABEL_8;
    }
  }
  v12 = a2;
  pv = 0;
  psz2 = a2;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  LODWORD(nChar) = v10;
  v11 = v10;
  if ( (a4 & 1) != 0 )
    goto LABEL_16;
LABEL_8:
  if ( PathGetDriveNumberW(a2) == -1 && !PathIsUNCW(a2) && !IsLegacyFileURI(a2) )
    goto LABEL_11;
  v39 = v10;
  IsFeatureEnabledInternal = CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_CREATE_URL_MONIKER_DISABLE_LEGACY_COMPAT);
  v12 = a2;
  if ( IsFeatureEnabledInternal == 1 )
  {
    pv = OLESTRDuplicate(a2);
    if ( pv )
    {
      v42 = v11;
      v38[0] = v11 + 1;
      v40 = &CPercentDecodeList::`vftable';
      v35 = -1;
      v43 = &unk_18012FF00;
      v34 = -1;
      v41 = pv;
      v44 = 1;
      CPercentDecodeString::Decode(
        (CPercentDecodeString *)&v40,
        (unsigned __int16 *)pv,
        v38,
        (unsigned __int16 **)pv,
        v31,
        7u);
      v22 = LongLongToULong(v38[0], (unsigned int *)&nChar);
      if ( v22 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x114,
          (unsigned int)"onecoreuap\\inetcore\\urlmon\\utils\\urlfile.cxx",
          (const char *)(unsigned int)v22,
          (int)v31);
      if ( (int)EnsureSecurityManager() < 0
        || ((int (__fastcall *)(IInternetSecurityManager *, const WCHAR *, int *, _QWORD))g_pInternetSecurityManager->lpVtbl->MapUrlToZone)(
             g_pInternetSecurityManager,
             a2,
             &v35,
             0) < 0
        || (v23 = (const WCHAR *)pv,
            ((int (__fastcall *)(IInternetSecurityManager *, LPVOID, int *, _QWORD))g_pInternetSecurityManager->lpVtbl->MapUrlToZone)(
              g_pInternetSecurityManager,
              pv,
              &v34,
              0) < 0) )
      {
        LODWORD(v10) = (_DWORD)nChar;
        v12 = a2;
        v15 = 1;
      }
      else
      {
        v12 = a2;
        v15 = 1;
        if ( v35 == v34 )
          v12 = v23;
        LODWORD(v10) = (_DWORD)nChar;
        psz2 = v12;
      }
    }
    else
    {
      v15 = -2147024882;
      v12 = a2;
    }
  }
  else
  {
    v15 = IsFeatureEnabledInternal;
  }
  if ( g_cmptlgs == 1 )
  {
LABEL_48:
    if ( v15 >= 0 )
      goto LABEL_16;
LABEL_49:
    v13 = a5;
    goto LABEL_50;
  }
  if ( !(unsigned int)IECompatLoggingEnabled() )
  {
    v12 = psz2;
    goto LABEL_48;
  }
  if ( v15 < 0 )
    goto LABEL_49;
  v27 = OLESTRDuplicate(a2);
  if ( !v27 )
  {
LABEL_11:
    v12 = psz2;
    goto LABEL_16;
  }
  v40 = &CPercentDecodeList::`vftable';
  v42 = v39;
  v41 = v27;
  v43 = &unk_180130094;
  v38[0] = v39 + 1;
  v44 = 0;
  CPercentDecodeString::Decode((CPercentDecodeString *)&v40, v27, v38, v26, v31, 7u);
  v24 = LongLongToULong(v38[0], (unsigned int *)&nChar);
  if ( v24 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\utils\\urlfile.cxx",
      (const char *)(unsigned int)v24,
      v32);
  if ( StrCmpNW(v27, psz2, v10) )
  {
    v38[0] = (unsigned __int64)psz2;
    v45[0] = L"NewUri";
    v38[1] = (unsigned __int64)v27;
    v45[1] = L"OldUri";
    IECompatLogEventWithUrl(
      -1073740785,
      (unsigned int)L"CreateURLMonikerDifference",
      (_DWORD)a2,
      0,
      2,
      (__int64)v45,
      (__int64)v38);
  }
  CoTaskMemFree(v27);
  v12 = psz2;
LABEL_16:
  v13 = a5;
  v14 = a5;
  if ( (a5 & 0x110) == 0 )
    v14 = a5 | 0x100;
  if ( (v14 & 0x1800) == 0 )
    v14 |= 0x800u;
  if ( (v14 & 0x6000) == 0 )
    v14 |= 0x2000u;
  if ( (v14 & 0x2000000) == 0 )
    v14 |= 0x2000000u;
  if ( (v14 & 0x1000000) == 0 )
    v14 |= 0x1000000u;
  v15 = CreateUri(v12, v14, 0, &ppURI);
  if ( v15 >= 0 && ppURI )
  {
    nChar = 0;
    if ( (v49 & 0xFFFFFFFC) == 0 )
    {
      if ( !v9 )
      {
        v8 = 50342789;
        if ( !v7 )
          v8 = 50375589;
      }
      v16 = ppURI;
      *a3 = 0;
      v17 = CombineIMonikerAndIUri(0, a1, 0, v16, &nChar, v8, 0);
      if ( v17 < 0 )
        goto LABEL_35;
      v18 = (CUrlMon *)CoTaskMemAlloc(0x70u);
      if ( v18 )
      {
        *(_OWORD *)v18 = 0;
        *((_OWORD *)v18 + 1) = 0;
        *((_OWORD *)v18 + 2) = 0;
        *((_OWORD *)v18 + 3) = 0;
        *((_OWORD *)v18 + 4) = 0;
        *((_OWORD *)v18 + 5) = 0;
        *((_OWORD *)v18 + 6) = 0;
        v19 = CUrlMon::CUrlMon(v18, nChar, v8);
        *a3 = v19;
        if ( v19 )
          goto LABEL_35;
      }
      else
      {
        *a3 = 0;
      }
      v17 = -2147024882;
LABEL_35:
      if ( nChar )
        ((void (__fastcall *)(struct IUri *))nChar->lpVtbl->Release)(nChar);
      goto LABEL_37;
    }
    v17 = -2147024809;
    goto LABEL_37;
  }
LABEL_50:
  if ( g_cmptlgs == 1 )
  {
    v21 = psz2;
  }
  else
  {
    v21 = psz2;
    if ( (unsigned int)IECompatLoggingEnabled() )
      IECompatLogURICreationFailure(psz2, v15);
  }
  if ( operator new(0x70u) )
  {
    v28 = HelperAddUriDefaultFlags(0x3002B80u, v13);
    v30 = CUrlMon::CUrlMon(v29, v21, v28);
    *a3 = v30;
    if ( v30 )
    {
      v17 = 0;
      goto LABEL_37;
    }
  }
  else
  {
    *a3 = 0;
  }
  v17 = -2147024882;
LABEL_37:
  if ( pv )
    CoTaskMemFree(pv);
LABEL_39:
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( g_cRef > 0 )
    _InterlockedDecrement((volatile signed __int32 *)&g_cRef);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18004f0a0  mov     [rsp-8+arg_8], rbx
0x18004f0a5  mov     [rsp-8+arg_18], r9d
0x18004f0aa  mov     [rsp-8+arg_0], rcx
0x18004f0af  push    rbp
0x18004f0b0  push    rsi
0x18004f0b1  push    rdi
0x18004f0b2  push    r12
0x18004f0b4  push    r13
0x18004f0b6  push    r14
0x18004f0b8  push    r15
0x18004f0ba  lea     rbp, [rsp-1Fh]
0x18004f0bf  sub     rsp, 0C0h
0x18004f0c6  xor     r13d, r13d
0x18004f0c9  mov     eax, r9d
0x18004f0cc  mov     [rbp+4Fh+ppURI], r13
0x18004f0d0  mov     r15, r8
0x18004f0d3  mov     rdi, rdx
0x18004f0d6  lock inc cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x18004f0dd  test    r8, r8
0x18004f0e0  jz      loc_18004F314
0x18004f0e6  mov     [r8], r13
0x18004f0e9  test    rdx, rdx
0x18004f0ec  jz      loc_18004F31B
0x18004f0f2  mov     esi, eax
0x18004f0f4  mov     r12d, eax
0x18004f0f7  and     esi, 1
0x18004f0fa  mov     r14d, 3002A95h
0x18004f100  and     r12d, 2
0x18004f104  jnz     short loc_18004F172
0x18004f106  mov     eax, 3002B85h
0x18004f10b  mov     [rbp+4Fh+arg_20], eax
0x18004f10e  test    esi, esi
0x18004f110  jnz     short loc_18004F176
0x18004f112  mov     eax, 300ABA5h
0x18004f117  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18004f11e  mov     [rbp+4Fh+arg_20], eax
0x18004f121  inc     rbx
0x18004f124  cmp     [rdx+rbx*2], r13w
0x18004f129  jnz     short loc_18004F121
0x18004f12b  mov     [rbp+4Fh+pv], r13
0x18004f12f  mov     r13d, ebx
0x18004f132  mov     dword ptr [rbp+4Fh+nChar], ebx
0x18004f135  mov     [rbp+4Fh+psz2], rdi
0x18004f139  mov     rcx, rdi; pszPath
0x18004f13c  call    cs:__imp_PathGetDriveNumberW
0x18004f142  cmp     eax, 0FFFFFFFFh
0x18004f145  jnz     loc_18004F522
0x18004f14b  mov     rcx, rdi; pszPath
0x18004f14e  call    cs:__imp_PathIsUNCW
0x18004f154  test    eax, eax
0x18004f156  jnz     loc_18004F522
0x18004f15c  mov     rcx, rdi; unsigned __int16 *
0x18004f15f  call    ?IsLegacyFileURI@@YA_NPEBG@Z; IsLegacyFileURI(ushort const *)
0x18004f164  test    al, al
0x18004f166  jnz     loc_18004F522
0x18004f16c  mov     rcx, [rbp+4Fh+psz2]
0x18004f170  jmp     short loc_18004F1A4
0x18004f172  mov     [rbp+4Fh+arg_20], r14d
0x18004f176  mov     rcx, rdi; pwzURI
0x18004f179  mov     [rbp+4Fh+pv], r13
0x18004f17d  mov     [rbp+4Fh+psz2], rcx
0x18004f181  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18004f188  nop     dword ptr [rax+rax+00000000h]
0x18004f190  inc     rbx
0x18004f193  cmp     [rdx+rbx*2], r13w
0x18004f198  jnz     short loc_18004F190
0x18004f19a  mov     dword ptr [rbp+4Fh+nChar], ebx
0x18004f19d  mov     r13, rbx
0x18004f1a0  test    esi, esi
0x18004f1a2  jz      short loc_18004F139
0x18004f1a4  mov     ebx, [rbp+4Fh+arg_20]
0x18004f1a7  mov     eax, ebx
0x18004f1a9  bts     eax, 8
0x18004f1ad  mov     edx, ebx
0x18004f1af  test    ebx, 110h
0x18004f1b5  cmovz   edx, eax
0x18004f1b8  test    edx, 1800h
0x18004f1be  jnz     short loc_18004F1C4
0x18004f1c0  bts     edx, 0Bh
0x18004f1c4  test    edx, 6000h
0x18004f1ca  jnz     short loc_18004F1D0
0x18004f1cc  bts     edx, 0Dh
0x18004f1d0  bt      edx, 19h
0x18004f1d4  jb      short loc_18004F1DA
0x18004f1d6  bts     edx, 19h
0x18004f1da  bt      edx, 18h
0x18004f1de  jb      short loc_18004F1E4
0x18004f1e0  bts     edx, 18h; dwFlags
0x18004f1e4  lea     r9, [rbp+4Fh+ppURI]; ppURI
0x18004f1e8  xor     r8d, r8d; dwReserved
0x18004f1eb  call    cs:__imp_CreateUri
0x18004f1f1  mov     r13d, eax
0x18004f1f4  test    eax, eax
0x18004f1f6  js      loc_18004F33B
0x18004f1fc  mov     rdx, [rbp+4Fh+ppURI]
0x18004f200  test    rdx, rdx
0x18004f203  jz      loc_18004F33B
0x18004f209  xor     r13d, r13d
0x18004f20c  test    [rbp+4Fh+arg_18], 0FFFFFFFCh
0x18004f213  mov     [rbp+4Fh+nChar], r13
0x18004f217  jnz     loc_18004F5DE
0x18004f21d  test    r12d, r12d
0x18004f220  jnz     short loc_18004F233
0x18004f222  test    esi, esi
0x18004f224  mov     r14d, 3002B85h
0x18004f22a  mov     eax, 300ABA5h
0x18004f22f  cmovz   r14d, eax
0x18004f233  mov     [rsp+0F0h+var_C0], r13d; unsigned int
0x18004f238  lea     rax, [rbp+4Fh+nChar]
0x18004f23c  mov     r9, rdx; struct IUri *
0x18004f23f  mov     [rsp+0F0h+var_C8], r14d; unsigned int
0x18004f244  mov     rdx, [rbp+4Fh+arg_0]; struct IMoniker *
0x18004f248  xor     r8d, r8d; struct IMoniker *
0x18004f24b  xor     ecx, ecx; struct IBindCtx *
0x18004f24d  mov     [rsp+0F0h+var_D0], rax; struct IUri **
0x18004f252  mov     [r15], r13
0x18004f255  call    ?CombineIMonikerAndIUri@@YAJPEAUIBindCtx@@PEAUIMoniker@@1PEAUIUri@@PEAPEAU3@KK@Z; CombineIMonikerAndIUri(IBindCtx *,IMoniker *,IMoniker *,IUri *,IUri * *,ulong,ulong)
0x18004f25a  mov     ebx, eax
0x18004f25c  test    eax, eax
0x18004f25e  js      short loc_18004F2A9
0x18004f260  mov     ecx, 70h ; 'p'; cb
0x18004f265  call    cs:__imp_CoTaskMemAlloc
0x18004f26b  test    rax, rax
0x18004f26e  jz      loc_18004F322
0x18004f274  xorps   xmm0, xmm0
0x18004f277  mov     r8d, r14d; unsigned int
0x18004f27a  movups  xmmword ptr [rax], xmm0
0x18004f27d  mov     rcx, rax; this
0x18004f280  movups  xmmword ptr [rax+10h], xmm0
0x18004f284  movups  xmmword ptr [rax+20h], xmm0
0x18004f288  movups  xmmword ptr [rax+30h], xmm0
0x18004f28c  movups  xmmword ptr [rax+40h], xmm0
0x18004f290  movups  xmmword ptr [rax+50h], xmm0
0x18004f294  movups  xmmword ptr [rax+60h], xmm0
0x18004f298  mov     rdx, [rbp+4Fh+nChar]; struct IUri *
0x18004f29c  call    ??0CUrlMon@@QEAA@PEAUIUri@@K@Z; CUrlMon::CUrlMon(IUri *,ulong)
0x18004f2a1  mov     [r15], rax
0x18004f2a4  test    rax, rax
0x18004f2a7  jz      short loc_18004F325
0x18004f2a9  mov     rcx, [rbp+4Fh+nChar]
0x18004f2ad  test    rcx, rcx
0x18004f2b0  jz      short loc_18004F2BE
0x18004f2b2  mov     rax, [rcx]
0x18004f2b5  mov     rax, [rax+10h]
0x18004f2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2be  mov     rax, [rbp+4Fh+pv]
0x18004f2c2  test    rax, rax
0x18004f2c5  jnz     loc_18004F63B
0x18004f2cb  mov     rdx, [rbp+4Fh+ppURI]
0x18004f2cf  test    rdx, rdx
0x18004f2d2  jz      short loc_18004F2E7
0x18004f2d4  mov     rcx, [rdx]
0x18004f2d7  mov     rax, [rcx+10h]
0x18004f2db  mov     rcx, rdx
0x18004f2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2e3  mov     [rbp+4Fh+ppURI], r13
0x18004f2e7  cmp     cs:?g_cRef@@3VCRefCount@@A, 0; CRefCount g_cRef
0x18004f2ee  jle     short loc_18004F2F7
0x18004f2f0  lock dec cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x18004f2f7  mov     eax, ebx
0x18004f2f9  mov     rbx, [rsp+0F0h+arg_8]
0x18004f301  add     rsp, 0C0h
0x18004f308  pop     r15
0x18004f30a  pop     r14
0x18004f30c  pop     r13
0x18004f30e  pop     r12
0x18004f310  pop     rdi
0x18004f311  pop     rsi
0x18004f312  pop     rbp
0x18004f313  retn
0x18004f314  mov     ebx, 80070057h
0x18004f319  jmp     short loc_18004F2CB
0x18004f31b  mov     ebx, 80070057h
0x18004f320  jmp     short loc_18004F2CB
0x18004f322  mov     [r15], r13
0x18004f325  mov     ebx, 8007000Eh
0x18004f32a  jmp     loc_18004F2A9
0x18004f32f  test    r13d, r13d
0x18004f332  jns     loc_18004F1A4
0x18004f338  mov     ebx, [rbp+4Fh+arg_20]
0x18004f33b  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x18004f342  jz      loc_18004F5E8
0x18004f348  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x18004f34d  mov     rdi, [rbp+4Fh+psz2]
0x18004f351  test    eax, eax
0x18004f353  jz      loc_18004F5EC
0x18004f359  mov     edx, r13d
0x18004f35c  mov     rcx, rdi
0x18004f35f  call    cs:__imp_?IECompatLogURICreationFailure@@YAXPEBGJ@Z; IECompatLogURICreationFailure(ushort const *,long)
0x18004f365  jmp     loc_18004F5EC
0x18004f36a  mov     eax, r13d
0x18004f36d  lea     ecx, [r13+1]
0x18004f371  mov     [rbp+4Fh+var_60], rax
0x18004f375  lea     r8, [rbp+4Fh+var_88]; unsigned __int64 *
0x18004f379  lea     rax, ??_7CPercentDecodeList@@6B@; const CPercentDecodeList::`vftable'
0x18004f380  mov     [rbp+4Fh+var_88], rcx
0x18004f384  mov     [rbp+4Fh+var_70], rax
0x18004f388  lea     rcx, [rbp+4Fh+var_70]; this
0x18004f38c  lea     rax, unk_18012FF00
0x18004f393  mov     [rbp+4Fh+var_A0], 0FFFFFFFFh
0x18004f39a  mov     rdx, r9; unsigned __int16 *
0x18004f39d  mov     [rbp+4Fh+var_58], rax
0x18004f3a1  mov     [rbp+4Fh+var_A4], 0FFFFFFFFh
0x18004f3a8  mov     [rbp+4Fh+var_68], r9
0x18004f3ac  mov     [rbp+4Fh+var_50], 1
0x18004f3b4  mov     [rsp+0F0h+var_C8], 7; unsigned int
0x18004f3bc  call    ?Decode@CPercentDecodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentDecodeString::Decode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x18004f3c1  mov     rcx, [rbp+4Fh+var_88]; __int64
0x18004f3c5  lea     rdx, [rbp+4Fh+nChar]; unsigned int *
0x18004f3c9  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18004f3ce  test    eax, eax
0x18004f3d0  js      loc_18004F55C
0x18004f3d6  call    ?EnsureSecurityManager@@YAJXZ; EnsureSecurityManager(void)
0x18004f3db  test    eax, eax
0x18004f3dd  js      loc_18004F575
0x18004f3e3  mov     rcx, cs:?g_pInternetSecurityManager@@3PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * g_pInternetSecurityManager
0x18004f3ea  lea     r8, [rbp+4Fh+var_A0]
0x18004f3ee  xor     r9d, r9d
0x18004f3f1  mov     rdx, rdi
0x18004f3f4  mov     rax, [rcx]
0x18004f3f7  mov     rax, [rax+28h]
0x18004f3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f400  test    eax, eax
0x18004f402  js      loc_18004F575
0x18004f408  mov     rcx, cs:?g_pInternetSecurityManager@@3PEAUIInternetSecurityManager@@EA; IInternetSecurityManager * g_pInternetSecurityManager
0x18004f40f  lea     r8, [rbp+4Fh+var_A4]
0x18004f413  mov     rbx, [rbp+4Fh+pv]
0x18004f417  xor     r9d, r9d
0x18004f41a  mov     rdx, rbx
0x18004f41d  mov     rax, [rcx]
0x18004f420  mov     rax, [rax+28h]
0x18004f424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f429  test    eax, eax
0x18004f42b  js      loc_18004F575
0x18004f431  mov     eax, [rbp+4Fh+var_A4]
0x18004f434  mov     rcx, rdi
0x18004f437  cmp     [rbp+4Fh+var_A0], eax
0x18004f43a  mov     r13d, [rbp+4Fh+var_A8]
0x18004f43e  cmovz   rcx, rbx
0x18004f442  mov     ebx, dword ptr [rbp+4Fh+nChar]
0x18004f445  mov     [rbp+4Fh+psz2], rcx
0x18004f449  jmp     loc_18004F584
0x18004f44e  mov     edx, [rbp+4Fh+var_78]
0x18004f451  lea     rax, ??_7CPercentDecodeList@@6B@; const CPercentDecodeList::`vftable'
0x18004f458  mov     [rbp+4Fh+var_70], rax
0x18004f45c  lea     r8, [rbp+4Fh+var_88]; unsigned __int64 *
0x18004f460  mov     [rbp+4Fh+var_60], rdx
0x18004f464  lea     rax, unk_180130094
0x18004f46b  mov     [rbp+4Fh+var_68], r13
0x18004f46f  lea     ecx, [rdx+1]
0x18004f472  mov     [rbp+4Fh+var_58], rax
0x18004f476  mov     [rbp+4Fh+var_88], rcx
0x18004f47a  mov     rdx, r13; unsigned __int16 *
0x18004f47d  lea     rcx, [rbp+4Fh+var_70]; this
0x18004f481  mov     [rbp+4Fh+var_50], 0
0x18004f489  mov     [rsp+0F0h+var_C8], 7; unsigned int
0x18004f491  call    ?Decode@CPercentDecodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentDecodeString::Decode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x18004f496  mov     rcx, [rbp+4Fh+var_88]; __int64
0x18004f49a  lea     rdx, [rbp+4Fh+nChar]; unsigned int *
0x18004f49e  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x18004f4a3  test    eax, eax
0x18004f4a5  js      loc_18004F5BC
0x18004f4ab  mov     r8d, ebx; nChar
0x18004f4ae  mov     rcx, r13; psz1
0x18004f4b1  mov     rbx, [rbp+4Fh+psz2]
0x18004f4b5  mov     rdx, rbx; psz2
0x18004f4b8  call    cs:__imp_StrCmpNW
0x18004f4be  test    eax, eax
0x18004f4c0  jz      short loc_18004F511
0x18004f4c2  lea     rax, aNewuri; "NewUri"
0x18004f4c9  mov     [rbp+4Fh+var_88], rbx
0x18004f4cd  mov     [rbp+4Fh+var_48], rax
0x18004f4d1  lea     rdx, aCreateurlmonik_2; "CreateURLMonikerDifference"
0x18004f4d8  lea     rax, aOlduri; "OldUri"
0x18004f4df  mov     [rbp+4Fh+var_80], r13
0x18004f4e3  mov     [rbp+4Fh+var_40], rax
0x18004f4e7  xor     r9d, r9d
0x18004f4ea  lea     rax, [rbp+4Fh+var_88]
0x18004f4ee  mov     r8, rdi
0x18004f4f1  mov     qword ptr [rsp+0F0h+var_C0], rax
0x18004f4f6  mov     ecx, 0C000040Fh
0x18004f4fb  lea     rax, [rbp+4Fh+var_48]
0x18004f4ff  mov     qword ptr [rsp+0F0h+var_C8], rax
0x18004f504  mov     dword ptr [rsp+0F0h+var_D0], 2
0x18004f50c  call    IECompatLogEventWithUrl
0x18004f511  mov     rcx, r13; pv
0x18004f514  call    cs:__imp_CoTaskMemFree
0x18004f51a  mov     rcx, rbx
0x18004f51d  jmp     loc_18004F1A4
0x18004f522  lea     rcx, ?FEATURE_CREATE_URL_MONIKER_DISABLE_LEGACY_COMPAT@FCK@@3VCFeatureControlKey@@A; this
0x18004f529  mov     [rbp+4Fh+var_78], ebx
0x18004f52c  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x18004f531  mov     [rbp+4Fh+var_A8], eax
0x18004f534  mov     rcx, rdi; unsigned __int16 *
0x18004f537  cmp     eax, 1
0x18004f53a  jnz     short loc_18004F581
0x18004f53c  call    ?OLESTRDuplicate@@YAPEAGPEBG@Z; OLESTRDuplicate(ushort const *)
0x18004f541  mov     [rbp+4Fh+pv], rax
0x18004f545  mov     r9, rax; unsigned __int16 **
0x18004f548  test    rax, rax
  ... truncated ...
```
