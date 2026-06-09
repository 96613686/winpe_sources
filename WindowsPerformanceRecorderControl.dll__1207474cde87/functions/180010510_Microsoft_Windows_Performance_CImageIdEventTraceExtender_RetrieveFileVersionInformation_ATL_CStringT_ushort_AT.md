# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x180010510`
- end: `0x180011277`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `3431`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *, const unsigned __int16 *, struct XPerfCore::CFileMapping *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014e58`

## callees

- `0x18000829c`
- `0x180010208`
- `0x1800102d8`
- `0x180010510`
- `0x180011280`
- `0x1800128f8`
- `0x180021130`
- `0x180044210`
- `0x18004b39c`
- `0x18004ece0`
- `0x18004f1d0`
- `0x18004f8ce`
- `0x18004f964`
- `0x1800781ec`
- `0x180079c40`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010706`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800108ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010c1b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010dfb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010fe8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010706`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800108ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010c1b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010dfb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010fe8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010609`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010806`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800109b5`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010b32`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010d12`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010eec`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010609`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010806`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800109b5`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010b32`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010d12`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180010eec`

## string_xrefs

- `0x180010cb2`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        _QWORD *a1,
        __int64 *a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  void *v7; // rcx
  unsigned int v8; // edi
  int VersionInfo; // eax
  __int64 result; // rax
  void *v11; // rdi
  unsigned __int16 v12; // r13
  int v13; // eax
  __int64 v14; // rcx
  unsigned __int64 v15; // rax
  __int16 *v16; // r8
  __int64 v17; // rdx
  _WORD *v18; // rax
  __int16 v19; // r9
  _WORD *v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // r15
  unsigned __int64 v23; // r12
  int v24; // esi
  unsigned __int64 v25; // rax
  _WORD *v26; // rdx
  size_t v27; // r8
  void *v28; // rcx
  __int64 v29; // rsi
  int v30; // edi
  void *v31; // rsi
  __int64 v32; // rcx
  __int16 *v33; // r8
  __int64 v34; // rdx
  _WORD *v35; // rax
  __int16 v36; // r9
  _WORD *v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // r15
  unsigned __int64 v40; // r12
  int v41; // esi
  unsigned __int64 v42; // rax
  _WORD *v43; // rdx
  size_t v44; // r8
  void *v45; // rcx
  __int64 v46; // rsi
  int v47; // edi
  void *v48; // r15
  int Error; // ebx
  __int64 v50; // rsi
  int v51; // edi
  __int64 v52; // rsi
  int v53; // edi
  __int64 v54; // rcx
  __int16 *v55; // r8
  __int64 v56; // rdx
  _WORD *v57; // rax
  __int16 v58; // r9
  _WORD *v59; // rcx
  __int64 v60; // rdi
  __int64 v61; // r15
  unsigned __int64 v62; // r12
  int v63; // esi
  unsigned __int64 v64; // rax
  _WORD *v65; // rdx
  size_t v66; // r8
  void *v67; // rcx
  __int64 v68; // rsi
  int v69; // edi
  int v70; // r13d
  __int64 v71; // rcx
  __int16 *v72; // r8
  __int64 v73; // rdx
  _WORD *v74; // rax
  __int16 v75; // r9
  _WORD *v76; // rcx
  __int64 v77; // rdi
  __int64 v78; // r15
  unsigned __int64 v79; // r12
  int v80; // esi
  unsigned __int64 v81; // rax
  _WORD *v82; // rdx
  size_t v83; // r8
  void *v84; // rcx
  __int64 v85; // rsi
  int v86; // edi
  __int64 v87; // rdi
  __int64 v88; // rcx
  __int16 *v89; // rdx
  _WORD *v90; // rax
  __int16 v91; // r8
  _WORD *v92; // rcx
  __int64 v93; // r8
  __int64 v94; // rsi
  unsigned __int64 v95; // r15
  int v96; // edi
  unsigned __int64 v97; // rax
  _WORD *v98; // rdx
  size_t v99; // r8
  void *v100; // rcx
  __int64 v101; // rsi
  int v102; // edi
  _QWORD *v103; // rsi
  __int64 (__fastcall *v104)(const unsigned __int16 *, __int64, LPVOID *); // rax
  int v105; // eax
  __int64 *v106; // rdx
  __int64 v107; // rdx
  __int64 v108; // r15
  int v109; // edi
  __int64 v110; // rdx
  __int64 v111; // r15
  int v112; // edi
  __int64 v113; // [rsp+20h] [rbp-4C8h]
  __int64 v114; // [rsp+20h] [rbp-4C8h]
  __int64 v115; // [rsp+20h] [rbp-4C8h]
  __int64 v116; // [rsp+20h] [rbp-4C8h]
  __int64 v117; // [rsp+28h] [rbp-4C0h]
  unsigned int puLen; // [rsp+30h] [rbp-4B8h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-4B0h] BYREF
  LPVOID v120; // [rsp+40h] [rbp-4A8h] BYREF
  void *Block; // [rsp+48h] [rbp-4A0h] BYREF
  unsigned __int16 v122; // [rsp+50h] [rbp-498h]
  unsigned __int16 v123; // [rsp+52h] [rbp-496h]
  _QWORD *v124; // [rsp+58h] [rbp-490h]
  const unsigned __int16 *v125; // [rsp+60h] [rbp-488h]
  _QWORD *v126; // [rsp+68h] [rbp-480h]
  __int64 v127; // [rsp+70h] [rbp-478h]
  ATL::CAtlException *v128; // [rsp+78h] [rbp-470h] BYREF
  _WORD Src[264]; // [rsp+80h] [rbp-468h] BYREF
  WCHAR SubBlock[264]; // [rsp+290h] [rbp-258h] BYREF

  v127 = -2;
  v125 = a3;
  v124 = a1;
  v126 = a1;
  operator delete(0);
  v7 = 0;
  Block = 0;
  if ( !a4 )
  {
    v8 = -2147467261;
LABEL_5:
    operator delete(v7);
    return v8;
  }
  VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&Block, a3, a4);
  v8 = VersionInfo;
  if ( VersionInfo < 0 )
  {
    v7 = Block;
    goto LABEL_5;
  }
  v11 = Block;
  if ( !Block )
  {
    v12 = v122;
    goto LABEL_20;
  }
  v12 = v122;
  v13 = StringCchPrintfW(SubBlock, 0x104u, L"\\StringFileInfo\\%04X%04X\\%ws", v122, v123, L"FileDescription");
  if ( v13 < 0 )
    goto LABEL_18;
  lpBuffer = 0;
  puLen = 0;
  if ( !VerQueryValueW(v11, SubBlock, &lpBuffer, &puLen) )
  {
    Src[0] = 0;
    ATL::AtlHresultFromLastError();
    goto LABEL_20;
  }
  v14 = puLen;
  v15 = puLen - 1LL;
  if ( v15 > 0x7FFFFFFD )
  {
LABEL_18:
    Src[0] = 0;
    goto LABEL_20;
  }
  v16 = (__int16 *)lpBuffer;
  v17 = 260;
  v18 = Src;
  do
  {
    if ( !v14 )
      break;
    v19 = *v16;
    if ( !*v16 )
      break;
    ++v16;
    *v18++ = v19;
    --v14;
    --v17;
  }
  while ( v17 );
  v20 = v18 - 1;
  if ( v17 )
    v20 = v18;
  *v20 = 0;
LABEL_20:
  v21 = -1;
  do
    ++v21;
  while ( Src[v21] );
  try
  {
    v22 = *a2;
    v23 = *(unsigned int *)(*a2 - 16);
    v24 = v23 + v21;
    if ( (((*(_DWORD *)(*a2 - 12) - (v23 + v21)) | (1 - *(_DWORD *)(*a2 - 8))) & 0x80000000) != 0LL )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v24);
    v25 = ((__int64)Src - v22) >> 1;
    v26 = (_WORD *)(*a2 + 2 * v25);
    if ( v25 > v23 )
      v26 = Src;
    v27 = 2LL * (int)v21;
    if ( v27 )
    {
      v28 = (void *)(*a2 + 2 * v23);
      if ( v28 )
      {
        if ( v26 )
        {
          memcpy_0(v28, v26, v27);
          goto LABEL_33;
        }
        memset_0(v28, 0, v27);
      }
      *(_DWORD *)_o__errno(v28, v26) = 22;
      invalid_parameter_noinfo();
    }
LABEL_33:
    if ( v24 < 0 || v24 > *(_DWORD *)(*a2 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a2 - 16) = v24;
    *(_WORD *)(*a2 + 2LL * v24) = 0;
    v29 = *(unsigned int *)(*a2 - 16);
    v30 = v29 + 1;
    if ( (int)((*(_DWORD *)(*a2 - 12) - (v29 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v30);
    *(_WORD *)(*a2 + 2 * v29) = 0;
    if ( v30 < 0 || v30 > *(_DWORD *)(*a2 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a2 - 16) = v30;
    *(_WORD *)(*a2 + 2LL * v30) = 0;
    v31 = Block;
    if ( Block )
    {
      LODWORD(v113) = v123;
      if ( (int)StringCchPrintfW(SubBlock, 0x104u, L"\\StringFileInfo\\%04X%04X\\%ws", v12, v113, L"FileVersion") < 0 )
        goto LABEL_51;
      lpBuffer = 0;
      puLen = 0;
      if ( !VerQueryValueW(v31, SubBlock, &lpBuffer, &puLen) )
      {
        Src[0] = 0;
        ATL::AtlHresultFromLastError();
        goto LABEL_52;
      }
      v32 = puLen;
      if ( (unsigned __int64)puLen - 1 > 0x7FFFFFFD )
      {
LABEL_51:
        Src[0] = 0;
        goto LABEL_52;
      }
      v33 = (__int16 *)lpBuffer;
      v34 = 260;
      v35 = Src;
      do
      {
        if ( !v32 )
          break;
        v36 = *v33;
        if ( !*v33 )
          break;
        ++v33;
        *v35++ = v36;
        --v32;
        --v34;
      }
      while ( v34 );
      v37 = v35 - 1;
      if ( v34 )
        v37 = v35;
      *v37 = 0;
    }
LABEL_52:
    v38 = -1;
    do
      ++v38;
    while ( Src[v38] );
    v39 = *a2;
    v40 = *(unsigned int *)(*a2 - 16);
    v41 = v40 + v38;
    if ( (((*(_DWORD *)(*a2 - 12) - (v40 + v38)) | (1 - *(_DWORD *)(*a2 - 8))) & 0x80000000) != 0LL )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v41);
    v42 = ((__int64)Src - v39) >> 1;
    v43 = (_WORD *)(*a2 + 2 * v42);
    if ( v42 > v40 )
      v43 = Src;
    v44 = 2LL * (int)v38;
    if ( v44 )
    {
      v45 = (void *)(*a2 + 2 * v40);
      if ( v45 )
      {
        if ( v43 )
        {
          memcpy_0(v45, v43, v44);
          goto LABEL_64;
        }
        memset_0(v45, 0, v44);
      }
      *(_DWORD *)_o__errno(v45, v43) = 22;
      invalid_parameter_noinfo();
    }
LABEL_64:
    if ( v41 < 0 || v41 > *(_DWORD *)(*a2 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a2 - 16) = v41;
    *(_WORD *)(*a2 + 2LL * v41) = 0;
    v46 = *(unsigned int *)(*a2 - 16);
    v47 = v46 + 1;
    if ( (int)((*(_DWORD *)(*a2 - 12) - (v46 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v47);
    *(_WORD *)(*a2 + 2 * v46) = 0;
    if ( v47 < 0 || v47 > *(_DWORD *)(*a2 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a2 - 16) = v47;
    *(_WORD *)(*a2 + 2LL * v47) = 0;
    lpBuffer = 0;
    v48 = Block;
    if ( !Block )
    {
      Error = -2147418113;
LABEL_74:
      operator delete(v48);
      return (unsigned int)Error;
    }
    puLen = 0;
    if ( !VerQueryValueW(Block, L"\\", &lpBuffer, &puLen) )
    {
      lpBuffer = 0;
      Error = ATL::AtlHresultFromLastError();
      if ( Error < 0 )
        goto LABEL_74;
      goto LABEL_76;
    }
    if ( puLen < 0xC )
    {
LABEL_76:
      operator delete(v48);
      return 2147549183LL;
    }
    LODWORD(v117) = *((unsigned __int16 *)lpBuffer + 6);
    LODWORD(v113) = *((unsigned __int16 *)lpBuffer + 7);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      a2,
      L"%u.%u.%u.%u",
      *((unsigned __int16 *)lpBuffer + 5),
      *((unsigned __int16 *)lpBuffer + 4),
      v113,
      v117);
    v50 = *(unsigned int *)(*a2 - 16);
    v51 = v50 + 1;
    if ( (int)((*(_DWORD *)(*a2 - 12) - (v50 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v51);
    *(_WORD *)(*a2 + 2 * v50) = 0;
    if ( v51 < 0 || v51 > *(_DWORD *)(*a2 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a2 - 16) = v51;
    *(_WORD *)(*a2 + 2LL * v51) = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      a2,
      L"%u",
      v12);
    v52 = *(unsigned int *)(*a2 - 16);
    v53 = v52 + 1;
    if ( (int)((*(_DWORD *)(*a2 - 12) - (v52 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v53);
    *(_WORD *)(*a2 + 2 * v52) = 0;
    if ( v53 < 0 || v53 > *(_DWORD *)(*a2 - 12) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*a2 - 16) = v53;
    *(_WORD *)(*a2 + 2LL * v53) = 0;
    LODWORD(lpBuffer) = v12;
    LODWORD(v114) = v123;
    if ( (int)StringCchPrintfW(SubBlock, 0x104u, L"\\StringFileInfo\\%04X%04X\\%ws", v12, v114, L"ProductName") >= 0 )
    {
      v120 = 0;
      puLen = 0;
      if ( !VerQueryValueW(v48, SubBlock, &v120, &puLen) )
      {
        Src[0] = 0;
        ATL::AtlHresultFromLastError();
        goto LABEL_97;
      }
      v54 = puLen;
      if ( (unsigned __int64)puLen - 1 <= 0x7FFFFFFD )
      {
        v55 = (__int16 *)v120;
        v56 = 260;
        v57 = Src;
        do
        {
          if ( !v54 )
            break;
          v58 = *v55;
          if ( !*v55 )
            break;
          ++v55;
          *v57++ = v58;
          --v54;
          --v56;
        }
        while ( v56 );
        v59 = v57 - 1;
        if ( v56 )
          v59 = v57;
        *v59 = 0;
LABEL_97:
        v60 = -1;
        do
          ++v60;
        while ( Src[v60] );
        v61 = *a2;
        v62 = *(unsigned int *)(*a2 - 16);
        v63 = v62 + v60;
        if ( (((*(_DWORD *)(*a2 - 12) - (v62 + v60)) | (1 - *(_DWORD *)(*a2 - 8))) & 0x80000000) != 0LL )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v63);
        v64 = ((__int64)Src - v61) >> 1;
        v65 = (_WORD *)(*a2 + 2 * v64);
        if ( v64 > v62 )
          v65 = Src;
        v66 = 2LL * (int)v60;
        if ( v66 )
        {
          v67 = (void *)(*a2 + 2 * v62);
          if ( v67 )
          {
            if ( v65 )
            {
              memcpy_0(v67, v65, v66);
              goto LABEL_109;
            }
            memset_0(v67, 0, v66);
          }
          *(_DWORD *)_o__errno(v67, v65) = 22;
          invalid_parameter_noinfo();
        }
LABEL_109:
        if ( v63 < 0 || v63 > *(_DWORD *)(*a2 - 12) )
          ATL::AtlThrowImpl(-2147024809);
        *(_DWORD *)(*a2 - 16) = v63;
        *(_WORD *)(*a2 + 2LL * v63) = 0;
        v68 = *(unsigned int *)(*a2 - 16);
        v69 = v68 + 1;
        if ( (int)((*(_DWORD *)(*a2 - 12) - (v68 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v69);
        *(_WORD *)(*a2 + 2 * v68) = 0;
        if ( v69 < 0 || v69 > *(_DWORD *)(*a2 - 12) )
          ATL::AtlThrowImpl(-2147024809);
        *(_DWORD *)(*a2 - 16) = v69;
        *(_WORD *)(*a2 + 2LL * v69) = 0;
        v70 = v123;
        LODWORD(v115) = v123;
        if ( (int)StringCchPrintfW(
                    SubBlock,
                    0x104u,
                    L"\\StringFileInfo\\%04X%04X\\%ws",
                    (unsigned int)lpBuffer,
                    v115,
                    L"CompanyName") >= 0 )
        {
          v120 = 0;
          puLen = 0;
          if ( !VerQueryValueW(Block, SubBlock, &v120, &puLen) )
          {
            Src[0] = 0;
            ATL::AtlHresultFromLastError();
            goto LABEL_127;
          }
          v71 = puLen;
          if ( (unsigned __int64)puLen - 1 <= 0x7FFFFFFD )
          {
            v72 = (__int16 *)v120;
            v73 = 260;
            v74 = Src;
            do
            {
              if ( !v71 )
                break;
              v75 = *v72;
              if ( !*v72 )
                break;
              ++v72;
              *v74++ = v75;
              --v71;
              --v73;
            }
            while ( v73 );
            v76 = v74 - 1;
            if ( v73 )
              v76 = v74;
            *v76 = 0;
LABEL_127:
            v77 = -1;
            do
              ++v77;
            while ( Src[v77] );
            v78 = *a2;
            v79 = *(unsigned int *)(*a2 - 16);
            v80 = v79 + v77;
            if ( (((*(_DWORD *)(*a2 - 12) - (v79 + v77)) | (1 - *(_DWORD *)(*a2 - 8))) & 0x80000000) != 0LL )
              ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v80);
            v81 = ((__int64)Src - v78) >> 1;
            v82 = (_WORD *)(*a2 + 2 * v81);
            if ( v81 > v79 )
              v82 = Src;
            v83 = 2LL * (int)v77;
            if ( v83 )
            {
              v84 = (void *)(*a2 + 2 * v79);
              if ( v84 )
              {
                if ( v82 )
                {
                  memcpy_0(v84, v82, v83);
                  goto LABEL_139;
                }
                memset_0(v84, 0, v83);
              }
              *(_DWORD *)_o__errno(v84, v82) = 22;
              invalid_parameter_noinfo();
            }
LABEL_139:
            if ( v80 < 0 || v80 > *(_DWORD *)(*a2 - 12) )
              ATL::AtlThrowImpl(-2147024809);
            *(_DWORD *)(*a2 - 16) = v80;
            *(_WORD *)(*a2 + 2LL * v80) = 0;
            v85 = *(unsigned int *)(*a2 - 16);
            v86 = v85 + 1;
            if ( (int)((*(_DWORD *)(*a2 - 12) - (v85 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
              ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v86);
            *(_WORD *)(*a2 + 2 * v85) = 0;
            if ( v86 < 0 || v86 > *(_DWORD *)(*a2 - 12) )
              ATL::AtlThrowImpl(-2147024809);
            *(_DWORD *)(*a2 - 16) = v86;
            *(_WORD *)(*a2 + 2LL * v86) = 0;
            LODWORD(v116) = v70;
            v87 = 260;
            if ( (int)StringCchPrintfW(
                        SubBlock,
                        0x104u,
                        L"\\StringFileInfo\\%04X%04X\\%ws",
                        (unsigned int)lpBuffer,
                        v116,
                        L"ProductVersion") >= 0 )
            {
              v120 = 0;
              LODWORD(lpBuffer) = 0;
              if ( !VerQueryValueW(Block, SubBlock, &v120, (PUINT)&lpBuffer) )
              {
                Src[0] = 0;
                ATL::AtlHresultFromLastError();
                goto LABEL_157;
              }
              v88 = (unsigned int)lpBuffer;
              if ( (unsigned __int64)(unsigned int)lpBuffer - 1 <= 0x7FFFFFFD )
              {
                v89 = (__int16 *)v120;
                v90 = Src;
                do
                {
                  if ( !v88 )
                    break;
                  v91 = *v89;
                  if ( !*v89 )
                    break;
                  ++v89;
                  *v90++ = v91;
                  --v88;
                  --v87;
                }
                while ( v87 );
                v92 = v90 - 1;
                if ( v87 )
                  v92 = v90;
                *v92 = 0;
LABEL_157:
                v93 = -1;
                do
                  v120 = (LPVOID)++v93;
                while ( Src[v93] );
                v94 = *a2;
                v95 = *(unsigned int *)(*a2 - 16);
                v96 = v95 + v93;
                if ( (((*(_DWORD *)(*a2 - 12) - (v95 + v93)) | (1 - *(_DWORD *)(*a2 - 8))) & 0x80000000) != 0LL )
                {
                  ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v96);
                  LODWORD(v93) = (_DWORD)v120;
                }
                v97 = ((__int64)Src - v94) >> 1;
                v98 = (_WORD *)(*a2 + 2 * v97);
                if ( v97 > v95 )
                  v98 = Src;
                v99 = 2LL * (int)v93;
                if ( !v99 )
                  goto LABEL_169;
                v100 = (void *)(*a2 + 2 * v95);
                if ( v100 )
                {
                  if ( v98 )
                  {
                    memcpy_0(v100, v98, v99);
                    goto LABEL_169;
                  }
                  memset_0(v100, 0, v99);
                }
                *(_DWORD *)_o__errno(v100, v98) = 22;
                invalid_parameter_noinfo();
LABEL_169:
                if ( v96 < 0 || v96 > *(_DWORD *)(*a2 - 12) )
                  ATL::AtlThrowImpl(-2147024809);
                *(_DWORD *)(*a2 - 16) = v96;
                *(_WORD *)(*a2 + 2LL * v96) = 0;
                v101 = *(unsigned int *)(*a2 - 16);
                v102 = v101 + 1;
                if ( (int)((*(_DWORD *)(*a2 - 12) - (v101 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
                  ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v102);
                *(_WORD *)(*a2 + 2 * v101) = 0;
                if ( v102 < 0 || v102 > *(_DWORD *)(*a2 - 12) )
                  ATL::AtlThrowImpl(-2147024809);
                *(_DWORD *)(*a2 - 16) = v102;
                *(_WORD *)(*a2 + 2LL * v102) = 0;
                lpBuffer = 0;
                try
                {
                  v103 = v124;
                  if ( !*((_BYTE *)v124 + 296) )
                    Microsoft::Windows::Performance::CAeDelayLoad::LoadAeModule((Microsoft::Windows::Performance::CAeDelayLoad *)(v124 + 37));
                  v104 = (__int64 (__fastcall *)(const unsigned __int16 *, __int64, LPVOID *))v103[39];
                  if ( v104 && v103[40] )
                  {
                    v105 = v104(v125, 1, &lpBuffer);
                    v106 = (__int64 *)lpBuffer;
                  }
                  else
                  {
                    v105 = ATL::AtlHresultFromWin32(0x7Fu);
                  }
                  if ( v105 < 0 )
                  {
                    v106 = 0;
                    lpBuffer = 0;
                  }
                  if ( v106 )
                  {
                    v107 = *v106;
                    if ( v107 )
                      ATL::CSimpleStringT<unsigned short,0>::Append(a2, v107);
                  }
                  v108 = *(unsigned int *)(*a2 - 16);
                  v109 = v108 + 1;
                  if ( (int)((*(_DWORD *)(*a2 - 12) - (v108 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
                    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v109);
                  *(_WORD *)(*a2 + 2 * v108) = 0;
                  if ( v109 < 0 || v109 > *(_DWORD *)(*a2 - 12) )
                    ATL::AtlThrowImpl(-2147024809);
                  *(_DWORD *)(*a2 - 16) = v109;
                  *(_WORD *)(*a2 + 2LL * v109) = 0;
                  if ( lpBuffer )
                  {
                    v110 = *((_QWORD *)lpBuffer + 1);
                    if ( v110 )
                      ATL::CSimpleStringT<unsigned short,0>::Append(a2, v110);
                  }
                  v111 = *(unsigned int *)(*a2 - 16);
                  v112 = v111 + 1;
                  if ( (int)((*(_DWORD *)(*a2 - 12) - (v111 + 1)) | (1 - *(_DWORD *)(*a2 - 8))) < 0 )
                    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v112);
                  *(_WORD *)(*a2 + 2 * v111) = 0;
                  if ( v112 < 0 || v112 > *(_DWORD *)(*a2 - 12) )
                    ATL::AtlThrowImpl(-2147024809);
                  *(_DWORD *)(*a2 - 16) = v112;
                  *(_WORD *)(*a2 + 2LL * v112) = 0;
                  if ( lpBuffer )
                  {
                    Microsoft::Windows::Performance::CAeDelayLoad::PicFreeFileInfo(
                      (Microsoft::Windows::Performance::CAeDelayLoad *)(v103 + 37),
                      (struct _FILE_INFO *)lpBuffer);
                    lpBuffer = 0;
                  }
                }
                catch ( ... )
                {
                  throw;
                }
                operator delete(Block);
                return 0;
              }
            }
            Src[0] = 0;
            goto LABEL_157;
          }
        }
        Src[0] = 0;
        goto LABEL_127;
      }
    }
    Src[0] = 0;
    goto LABEL_97;
  }
  catch ( ATL::CAtlException *v128 )
  {
    return *(unsigned int *)v128;
  }
  v22 = *a2;
}

```

## disassembly

```asm
0x180010510  push    rbx
0x180010512  push    rsi
0x180010513  push    rdi
0x180010514  push    r12
0x180010516  push    r13
0x180010518  push    r14
0x18001051a  push    r15
0x18001051c  sub     rsp, 4B0h
0x180010523  mov     [rsp+4E8h+var_478], 0FFFFFFFFFFFFFFFEh
0x18001052c  mov     rax, cs:__security_cookie
0x180010533  xor     rax, rsp
0x180010536  mov     [rsp+4E8h+var_48], rax
0x18001053e  mov     rdi, r9
0x180010541  mov     rsi, r8
0x180010544  mov     [rsp+4E8h+var_488], r8
0x180010549  mov     rbx, rdx
0x18001054c  mov     [rsp+4E8h+var_490], rcx
0x180010551  mov     [rsp+4E8h+var_480], rcx
0x180010556  xor     ecx, ecx; Block
0x180010558  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001055d  xor     r15d, r15d
0x180010560  mov     ecx, r15d
0x180010563  mov     [rsp+4E8h+Block], rcx
0x180010568  test    rdi, rdi
0x18001056b  jnz     short loc_180010574
0x18001056d  mov     edi, 80004003h
0x180010572  jmp     short loc_18001058F
0x180010574  mov     r8, rdi; struct XPerfCore::CFileMapping *
0x180010577  mov     rdx, rsi; unsigned __int16 *
0x18001057a  lea     rcx, [rsp+4E8h+Block]; this
0x18001057f  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x180010584  mov     edi, eax
0x180010586  test    eax, eax
0x180010588  jns     short loc_18001059B
0x18001058a  mov     rcx, [rsp+4E8h+Block]; Block
0x18001058f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010594  mov     eax, edi
0x180010596  jmp     loc_180011253
0x18001059b  mov     rdi, [rsp+4E8h+Block]
0x1800105a0  test    rdi, rdi
0x1800105a3  jz      loc_180010688
0x1800105a9  movzx   eax, [rsp+4E8h+var_496]
0x1800105ae  movzx   r13d, [rsp+4E8h+var_498]
0x1800105b4  mov     r9d, r13d
0x1800105b7  lea     rcx, aFiledescriptio; "FileDescription"
0x1800105be  mov     [rsp+4E8h+var_4C0], rcx
0x1800105c3  mov     dword ptr [rsp+4E8h+var_4C8], eax
0x1800105c7  lea     r8, aStringfileinfo_0; "\\StringFileInfo\\%04X%04X\\%ws"
0x1800105ce  mov     esi, 104h
0x1800105d3  mov     edx, esi; unsigned __int64
0x1800105d5  lea     rcx, [rsp+4E8h+SubBlock]; unsigned __int16 *
0x1800105dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800105e2  test    eax, eax
0x1800105e4  js      loc_18001067D
0x1800105ea  mov     [rsp+4E8h+lpBuffer], r15
0x1800105ef  mov     [rsp+4E8h+puLen], r15d
0x1800105f4  lea     r9, [rsp+4E8h+puLen]; puLen
0x1800105f9  lea     r8, [rsp+4E8h+lpBuffer]; lplpBuffer
0x1800105fe  lea     rdx, [rsp+4E8h+SubBlock]; lpSubBlock
0x180010606  mov     rcx, rdi; pBlock
0x180010609  call    cs:__imp_VerQueryValueW
0x18001060f  test    eax, eax
0x180010611  jnz     short loc_180010623
0x180010613  mov     [rsp+4E8h+Src], r15w
0x18001061c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010621  jmp     short loc_18001068E
0x180010623  mov     ecx, [rsp+4E8h+puLen]
0x180010627  lea     rax, [rcx-1]
0x18001062b  cmp     rax, 7FFFFFFDh
0x180010631  ja      short loc_18001067D
0x180010633  mov     r8, [rsp+4E8h+lpBuffer]
0x180010638  mov     rdx, rsi
0x18001063b  lea     rax, [rsp+4E8h+Src]
0x180010643  mov     r14d, 1
0x180010649  test    rcx, rcx
0x18001064c  jz      short loc_18001066C
0x18001064e  movzx   r9d, word ptr [r8]
0x180010652  test    r9w, r9w
0x180010656  jz      short loc_18001066C
0x180010658  add     r8, 2
0x18001065c  mov     [rax], r9w
0x180010660  add     rax, 2
0x180010664  sub     rcx, r14
0x180010667  sub     rdx, r14
0x18001066a  jnz     short loc_180010649
0x18001066c  lea     rcx, [rax-2]
0x180010670  test    rdx, rdx
0x180010673  cmovnz  rcx, rax
0x180010677  mov     [rcx], r15w
0x18001067b  jmp     short loc_180010694
0x18001067d  mov     [rsp+4E8h+Src], r15w
0x180010686  jmp     short loc_18001068E
0x180010688  movzx   r13d, [rsp+4E8h+var_498]
0x18001068e  mov     r14d, 1
0x180010694  lea     rax, [rsp+4E8h+Src]
0x18001069c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800106a0  inc     rdi
0x1800106a3  cmp     [rax+rdi*2], r15w
0x1800106a8  jnz     short loc_1800106A0
0x1800106aa  mov     r15, [rbx]
0x1800106ad  mov     r12d, [r15-10h]
0x1800106b1  lea     esi, [r12+rdi]
0x1800106b5  mov     ecx, r14d
0x1800106b8  sub     ecx, [r15-8]
0x1800106bc  mov     eax, [r15-0Ch]
0x1800106c0  sub     eax, esi
0x1800106c2  or      ecx, eax
0x1800106c4  jge     short loc_1800106D0
0x1800106c6  mov     edx, esi
0x1800106c8  mov     rcx, rbx
0x1800106cb  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800106d0  lea     rax, [rsp+4E8h+Src]
0x1800106d8  sub     rax, r15
0x1800106db  sar     rax, 1
0x1800106de  mov     rcx, [rbx]
0x1800106e1  cmp     rax, r12
0x1800106e4  lea     rdx, [rcx+rax*2]
0x1800106e8  jbe     short loc_1800106F2
0x1800106ea  lea     rdx, [rsp+4E8h+Src]; Src
0x1800106f2  movsxd  r8, edi
0x1800106f5  add     r8, r8; Size
0x1800106f8  jz      short loc_18001072C
0x1800106fa  lea     rcx, [rcx+r12*2]; void *
0x1800106fe  xor     r15d, r15d
0x180010701  test    rcx, rcx
0x180010704  jnz     short loc_180010719
0x180010706  call    cs:__imp__o__errno
0x18001070c  mov     dword ptr [rax], 16h
0x180010712  call    _invalid_parameter_noinfo
0x180010717  jmp     short loc_18001072F
0x180010719  test    rdx, rdx
0x18001071c  jz      short loc_180010725
0x18001071e  call    memcpy_0
0x180010723  jmp     short loc_18001072F
0x180010725  call    memset_0
0x18001072a  jmp     short loc_180010706
0x18001072c  xor     r15d, r15d
0x18001072f  test    esi, esi
0x180010731  js      loc_180011244
0x180010737  mov     rax, [rbx]
0x18001073a  cmp     esi, [rax-0Ch]
0x18001073d  jg      loc_180011244
0x180010743  mov     [rax-10h], esi
0x180010746  movsxd  rdx, esi
0x180010749  mov     rcx, [rbx]
0x18001074c  mov     [rcx+rdx*2], r15w
0x180010751  mov     rax, [rbx]
0x180010754  mov     esi, [rax-10h]
0x180010757  lea     edi, [rsi+1]
0x18001075a  mov     ecx, r14d
0x18001075d  sub     ecx, [rax-8]
0x180010760  mov     eax, [rax-0Ch]
0x180010763  sub     eax, edi
0x180010765  or      ecx, eax
0x180010767  jge     short loc_180010773
0x180010769  mov     edx, edi
0x18001076b  mov     rcx, rbx
0x18001076e  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180010773  mov     rcx, [rbx]
0x180010776  mov     [rcx+rsi*2], r15w
0x18001077b  test    edi, edi
0x18001077d  js      loc_18001123A
0x180010783  mov     rax, [rbx]
0x180010786  cmp     edi, [rax-0Ch]
0x180010789  jg      loc_18001123A
0x18001078f  mov     [rax-10h], edi
0x180010792  movsxd  rdx, edi
0x180010795  mov     rcx, [rbx]
0x180010798  mov     [rcx+rdx*2], r15w
0x18001079d  mov     rsi, [rsp+4E8h+Block]
0x1800107a2  test    rsi, rsi
0x1800107a5  jz      loc_18001087D
0x1800107ab  movzx   eax, [rsp+4E8h+var_496]
0x1800107b0  movzx   r9d, r13w
0x1800107b4  lea     rcx, aFileversion; "FileVersion"
0x1800107bb  mov     [rsp+4E8h+var_4C0], rcx
0x1800107c0  mov     dword ptr [rsp+4E8h+var_4C8], eax
0x1800107c4  lea     r8, aStringfileinfo_0; "\\StringFileInfo\\%04X%04X\\%ws"
0x1800107cb  mov     edi, 104h
0x1800107d0  mov     edx, edi; unsigned __int64
0x1800107d2  lea     rcx, [rsp+4E8h+SubBlock]; unsigned __int16 *
0x1800107da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800107df  test    eax, eax
0x1800107e1  js      loc_180010874
0x1800107e7  mov     [rsp+4E8h+lpBuffer], r15
0x1800107ec  mov     [rsp+4E8h+puLen], r15d
0x1800107f1  lea     r9, [rsp+4E8h+puLen]; puLen
0x1800107f6  lea     r8, [rsp+4E8h+lpBuffer]; lplpBuffer
0x1800107fb  lea     rdx, [rsp+4E8h+SubBlock]; lpSubBlock
0x180010803  mov     rcx, rsi; pBlock
0x180010806  call    cs:__imp_VerQueryValueW
0x18001080c  test    eax, eax
0x18001080e  jnz     short loc_180010820
0x180010810  mov     [rsp+4E8h+Src], r15w
0x180010819  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001081e  jmp     short loc_18001087D
0x180010820  mov     ecx, [rsp+4E8h+puLen]
0x180010824  lea     rax, [rcx-1]
0x180010828  cmp     rax, 7FFFFFFDh
0x18001082e  ja      short loc_180010874
0x180010830  mov     r8, [rsp+4E8h+lpBuffer]
0x180010835  mov     rdx, rdi
0x180010838  lea     rax, [rsp+4E8h+Src]
0x180010840  test    rcx, rcx
0x180010843  jz      short loc_180010863
0x180010845  movzx   r9d, word ptr [r8]
0x180010849  test    r9w, r9w
0x18001084d  jz      short loc_180010863
0x18001084f  add     r8, 2
0x180010853  mov     [rax], r9w
0x180010857  add     rax, 2
0x18001085b  sub     rcx, r14
0x18001085e  sub     rdx, r14
0x180010861  jnz     short loc_180010840
0x180010863  lea     rcx, [rax-2]
0x180010867  test    rdx, rdx
0x18001086a  cmovnz  rcx, rax
0x18001086e  mov     [rcx], r15w
0x180010872  jmp     short loc_18001087D
0x180010874  mov     [rsp+4E8h+Src], r15w
0x18001087d  lea     rax, [rsp+4E8h+Src]
0x180010885  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010889  inc     rdi
0x18001088c  cmp     [rax+rdi*2], r15w
0x180010891  jnz     short loc_180010889
0x180010893  mov     r15, [rbx]
0x180010896  mov     r12d, [r15-10h]
0x18001089a  lea     esi, [r12+rdi]
0x18001089e  mov     ecx, r14d
0x1800108a1  sub     ecx, [r15-8]
0x1800108a5  mov     eax, [r15-0Ch]
0x1800108a9  sub     eax, esi
0x1800108ab  or      ecx, eax
0x1800108ad  jge     short loc_1800108B9
0x1800108af  mov     edx, esi
0x1800108b1  mov     rcx, rbx
0x1800108b4  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800108b9  lea     rax, [rsp+4E8h+Src]
0x1800108c1  sub     rax, r15
0x1800108c4  sar     rax, 1
0x1800108c7  mov     rcx, [rbx]
0x1800108ca  cmp     rax, r12
0x1800108cd  lea     rdx, [rcx+rax*2]
0x1800108d1  jbe     short loc_1800108DB
0x1800108d3  lea     rdx, [rsp+4E8h+Src]; Src
0x1800108db  movsxd  r8, edi
0x1800108de  add     r8, r8; Size
0x1800108e1  jz      short loc_180010915
0x1800108e3  lea     rcx, [rcx+r12*2]; void *
0x1800108e7  xor     r12d, r12d
0x1800108ea  test    rcx, rcx
0x1800108ed  jnz     short loc_180010902
0x1800108ef  call    cs:__imp__o__errno
0x1800108f5  mov     dword ptr [rax], 16h
0x1800108fb  call    _invalid_parameter_noinfo
0x180010900  jmp     short loc_180010918
0x180010902  test    rdx, rdx
0x180010905  jz      short loc_18001090E
0x180010907  call    memcpy_0
0x18001090c  jmp     short loc_180010918
0x18001090e  call    memset_0
0x180010913  jmp     short loc_1800108EF
0x180010915  xor     r12d, r12d
0x180010918  test    esi, esi
0x18001091a  js      loc_180011230
0x180010920  mov     rax, [rbx]
0x180010923  cmp     esi, [rax-0Ch]
0x180010926  jg      loc_180011230
0x18001092c  mov     [rax-10h], esi
0x18001092f  movsxd  rdx, esi
0x180010932  mov     rcx, [rbx]
0x180010935  mov     [rcx+rdx*2], r12w
0x18001093a  mov     rax, [rbx]
0x18001093d  mov     esi, [rax-10h]
0x180010940  lea     edi, [rsi+1]
0x180010943  mov     ecx, r14d
0x180010946  sub     ecx, [rax-8]
0x180010949  mov     eax, [rax-0Ch]
0x18001094c  sub     eax, edi
0x18001094e  or      ecx, eax
0x180010950  jge     short loc_18001095C
0x180010952  mov     edx, edi
0x180010954  mov     rcx, rbx
0x180010957  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001095c  mov     rcx, [rbx]
0x18001095f  mov     [rcx+rsi*2], r12w
0x180010964  test    edi, edi
0x180010966  js      loc_180011226
0x18001096c  mov     rax, [rbx]
0x18001096f  cmp     edi, [rax-0Ch]
0x180010972  jg      loc_180011226
0x180010978  mov     [rax-10h], edi
0x18001097b  movsxd  rdx, edi
0x18001097e  mov     rcx, [rbx]
0x180010981  mov     [rcx+rdx*2], r12w
0x180010986  mov     [rsp+4E8h+lpBuffer], r12
0x18001098b  mov     r15, [rsp+4E8h+Block]
0x180010990  test    r15, r15
0x180010993  jnz     short loc_18001099C
0x180010995  mov     ebx, 8000FFFFh
  ... truncated ...
```
