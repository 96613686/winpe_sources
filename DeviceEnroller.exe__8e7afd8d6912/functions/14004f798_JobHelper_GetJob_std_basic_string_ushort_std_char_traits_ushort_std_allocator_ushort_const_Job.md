# JobHelper::GetJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_Job &)

- ea: `0x14004f798`
- end: `0x14005011f`
- name: `?GetJob@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_Job@@@Z`
- size: `2439`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400501a4`

## callees

- `0x1400042f0`
- `0x1400045a8`
- `0x140005c81`
- `0x1400095b4`
- `0x140009fc4`
- `0x14001e784`
- `0x14001e838`
- `0x14001ed14`
- `0x1400374d8`
- `0x14004904c`
- `0x140049984`
- `0x140049a68`
- `0x14004f4d0`
- `0x14004f798`
- `0x1400591d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004fb12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004fb4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004ff4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004fb12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004fb4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004ff4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050092`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14004fd89`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x14004fd89`

## string_xrefs

- `0x14004f924`: `DestinationFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall JobHelper::GetJob(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rcx
  int CDNRecordString; // ebx
  void **v6; // r8
  void *v7; // rcx
  void *v9; // r9
  void **v10; // rcx
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rdx
  char *v13; // rsi
  __int64 v14; // rbx
  _QWORD *v15; // rcx
  void **v16; // r8
  void *v17; // rcx
  void *v18; // r9
  void **v19; // rcx
  unsigned __int64 v20; // rdx
  char *v21; // rsi
  __int64 v22; // rbx
  _QWORD *v23; // rcx
  void **v24; // r8
  void *v25; // rcx
  void *v26; // r9
  void **v27; // rcx
  unsigned __int64 v28; // rdx
  char *v29; // rsi
  __int64 v30; // rbx
  _QWORD *v31; // rdx
  int CDNDownloadKey; // esi
  int v33; // r14d
  HKEY v34; // rbx
  void *v35; // rcx
  _QWORD *v36; // rcx
  HKEY v37; // rbx
  const wchar_t *v38; // r14
  __int64 v39; // rsi
  bool v40; // zf
  __int64 v41; // rax
  __int64 v42; // rdx
  OLECHAR *v43; // r8
  wchar_t v44; // cx
  signed int v45; // r14d
  OLECHAR *v46; // rcx
  __int64 v47; // rdx
  int v48; // eax
  OLECHAR *v49; // rdx
  OLECHAR *v50; // rcx
  OLECHAR v51; // r8
  OLECHAR *v52; // rcx
  HRESULT v53; // eax
  _QWORD *v54; // rcx
  int v55; // ebx
  void **v56; // r8
  void *v57; // rcx
  void *v58; // r9
  void **v59; // rcx
  void *v60; // rsi
  _QWORD *v61; // rdx
  const wchar_t *v62; // rdx
  HKEY v63; // rbx
  HKEY v64; // rbx
  __int64 v65; // [rsp+20h] [rbp-E0h] BYREF
  void *Block; // [rsp+28h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  void *v69; // [rsp+40h] [rbp-C0h] BYREF
  void **p_Block; // [rsp+48h] [rbp-B8h]
  void *v71; // [rsp+50h] [rbp-B0h] BYREF
  char v72; // [rsp+58h] [rbp-A8h]
  void *v73; // [rsp+60h] [rbp-A0h] BYREF
  GUID v74[2]; // [rsp+68h] [rbp-98h] BYREF
  GUID pclsid; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[56]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  memset(v74, 0, sizeof(v74));
  std::wstring::_Construct<1,unsigned short const *>((char **)v74, &SubKey, 0);
  pclsid = 0;
  std::wstring::operator=(a2, a1);
  Block = 0;
  p_Block = &Block;
  v71 = 0;
  v72 = 1;
  v4 = a1;
  if ( a1[3] > 7u )
    v4 = (_QWORD *)*a1;
  CDNRecordString = GetCDNRecordString(v4, L"SourceUrl", &v71);
  if ( v72 )
  {
    v6 = p_Block;
    v7 = *p_Block;
    *p_Block = v71;
    if ( v7 )
      operator delete(v7);
  }
  if ( CDNRecordString < 0 )
  {
    LogTelemetryError(L"JobHelper::GetJob: Failed to get %1 with error: 0x%2!x!", L"URL", (unsigned int)CDNRecordString);
LABEL_8:
    if ( Block )
      operator delete(Block);
    goto LABEL_10;
  }
  v9 = Block;
  v10 = (void **)(a2 + 136);
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)Block + v12) );
  if ( v12 > *(_QWORD *)(a2 + 160) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v10, v12, v6, Block);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 160) <= 7u )
      v13 = (char *)(a2 + 136);
    else
      v13 = (char *)*v10;
    *(_QWORD *)(a2 + 152) = v12;
    v14 = 2 * v12;
    memmove_0(v13, v9, 2 * v12);
    *(_WORD *)&v13[v14] = 0;
  }
  Src = 0;
  p_Block = &Src;
  v71 = 0;
  v72 = 1;
  v15 = a1;
  if ( a1[3] > 7u )
    v15 = (_QWORD *)*a1;
  CDNRecordString = GetCDNRecordString(v15, L"DestinationFilePath", &v71);
  if ( v72 )
  {
    v16 = p_Block;
    v17 = *p_Block;
    *p_Block = v71;
    if ( v17 )
      operator delete(v17);
  }
  if ( CDNRecordString < 0 )
  {
    LogTelemetryError(
      L"JobHelper::GetJob: Failed to get %1 with error: 0x%2!x!",
      L"DownloadLocation",
      (unsigned int)CDNRecordString);
LABEL_26:
    if ( Src )
      operator delete(Src);
    goto LABEL_8;
  }
  v18 = Src;
  v19 = (void **)(a2 + 168);
  v20 = -1;
  do
    ++v20;
  while ( *((_WORD *)Src + v20) );
  if ( v20 > *(_QWORD *)(a2 + 192) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v19, v20, v16, Src);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 192) <= 7u )
      v21 = (char *)(a2 + 168);
    else
      v21 = (char *)*v19;
    *(_QWORD *)(a2 + 184) = v20;
    v22 = 2 * v20;
    memmove_0(v21, v18, 2 * v20);
    *(_WORD *)&v21[v22] = 0;
  }
  v69 = 0;
  p_Block = &v69;
  v71 = 0;
  v72 = 1;
  v23 = a1;
  if ( a1[3] > 7u )
    v23 = (_QWORD *)*a1;
  CDNRecordString = GetCDNRecordString(v23, L"Originator", &v71);
  if ( v72 )
  {
    v24 = p_Block;
    v25 = *p_Block;
    *p_Block = v71;
    if ( v25 )
      operator delete(v25);
  }
  if ( CDNRecordString < 0 )
  {
    LogTelemetryError(
      L"JobHelper::GetJob: Failed to get %1 with error: 0x%2!x!",
      L"Originator",
      (unsigned int)CDNRecordString);
    if ( v69 )
      operator delete(v69);
    goto LABEL_26;
  }
  v26 = v69;
  v27 = (void **)(a2 + 64);
  v28 = -1;
  do
    ++v28;
  while ( *((_WORD *)v69 + v28) );
  if ( v28 > *(_QWORD *)(a2 + 88) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v27, v28, v24, v69);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 88) <= 7u )
      v29 = (char *)(a2 + 64);
    else
      v29 = (char *)*v27;
    *(_QWORD *)(a2 + 80) = v28;
    v30 = 2 * v28;
    memmove_0(v29, v26, 2 * v28);
    *(_WORD *)&v29[v30] = 0;
  }
  v31 = a1;
  if ( a1[3] > 7u )
    v31 = (_QWORD *)*a1;
  LODWORD(v65) = 0;
  if ( !v31 )
  {
    CDNDownloadKey = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      v65);
    goto LABEL_64;
  }
  hKey = 0;
  CDNDownloadKey = GetCDNDownloadKey(&hKey);
  if ( CDNDownloadKey < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_64;
  }
  v33 = 0;
  v34 = hKey;
  CDNDownloadKey = DCCDNUtil_GetRegistryDWORD(hKey, 0, L"State", (unsigned int *)&v65);
  if ( CDNDownloadKey >= 0 )
    v33 = v65;
  if ( v34 )
    RegCloseKey(v34);
  if ( CDNDownloadKey < 0 )
  {
LABEL_64:
    LogTelemetryError(
      L"JobHelper::GetJob: Failed to get %1 with error: 0x%2!x!",
      L"Status",
      (unsigned int)CDNDownloadKey);
    if ( v69 )
      operator delete(v69);
    if ( Src )
      operator delete(Src);
    v35 = Block;
    if ( !Block )
      goto LABEL_113;
    goto LABEL_112;
  }
  *(_DWORD *)(a2 + 112) = v33;
  *(GUID *)(a2 + 96) = GUID_00000000_0000_0000_0000_000000000000;
  hKey = 0;
  v36 = a1;
  if ( a1[3] > 7u )
    v36 = (_QWORD *)*a1;
  if ( (int)GetCDNRecordString(v36, L"EnrollmentId", &hKey) >= 0 )
  {
    v37 = hKey;
    v38 = L"{";
    v39 = 50;
    v40 = wcsncmp_0((const wchar_t *)hKey, L"{", 1u) == 0;
    v41 = 2147483646;
    if ( v40 )
    {
      v49 = sz;
      v50 = (OLECHAR *)v37;
      do
      {
        if ( !v41 )
          break;
        v51 = *v50;
        if ( !*v50 )
          break;
        ++v50;
        *v49++ = v51;
        --v41;
        --v39;
      }
      while ( v39 );
      v45 = v39 == 0 ? 0x8007007A : 0;
      v52 = v49 - 1;
      if ( v39 )
        v52 = v49;
      *v52 = 0;
      if ( !v39 )
      {
        v47 = 88;
        goto LABEL_82;
      }
    }
    else
    {
      v42 = 50;
      v43 = sz;
      do
      {
        if ( !v41 )
          break;
        v44 = *v38;
        if ( !*v38 )
          break;
        ++v38;
        *v43++ = v44;
        --v41;
        --v42;
      }
      while ( v42 );
      v45 = v42 == 0 ? 0x8007007A : 0;
      v46 = v43 - 1;
      if ( v42 )
        v46 = v43;
      *v46 = 0;
      if ( !v42 )
      {
        v47 = 82;
LABEL_82:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v47,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobhelper.cpp",
          (const char *)(unsigned int)v45,
          v65);
        if ( v37 )
          operator delete(v37);
        if ( v69 )
          operator delete(v69);
        if ( Src )
          operator delete(Src);
        if ( Block )
          operator delete(Block);
        CDNRecordString = v45;
        goto LABEL_10;
      }
      v45 = StringCchCatW(sz, 0x32u, (const unsigned __int16 *)v37);
      if ( v45 < 0 )
      {
        v47 = 83;
        goto LABEL_82;
      }
      v48 = StringCchCatW(sz, 0x32u, L"}");
      CDNDownloadKey = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobhelper.cpp",
          (const char *)(unsigned int)v48,
          v65);
        goto LABEL_105;
      }
    }
    v53 = CLSIDFromString(sz, &pclsid);
    CDNDownloadKey = v53;
    if ( v53 < 0 )
    {
      LogTelemetryError(
        L"JobHelper::GetJob: Failed to convert %1 to GUID with error: 0x%2!x!",
        L"EnrollmentId",
        (unsigned int)v53);
LABEL_105:
      if ( v37 )
        operator delete(v37);
      if ( v69 )
        operator delete(v69);
      if ( Src )
        operator delete(Src);
      v35 = Block;
      if ( !Block )
        goto LABEL_113;
LABEL_112:
      operator delete(v35);
LABEL_113:
      CDNRecordString = CDNDownloadKey;
LABEL_10:
      std::wstring::~wstring((char **)v74);
      return (unsigned int)CDNRecordString;
    }
    *(GUID *)(a2 + 96) = pclsid;
    if ( v37 )
      operator delete(v37);
  }
  v73 = 0;
  p_Block = &v73;
  v71 = 0;
  v72 = 1;
  v54 = a1;
  if ( a1[3] > 7u )
    v54 = (_QWORD *)*a1;
  v55 = GetCDNRecordString(v54, L"BitsJobId", &v71);
  if ( v72 )
  {
    v56 = p_Block;
    v57 = *p_Block;
    *p_Block = v71;
    if ( v57 )
      operator delete(v57);
  }
  if ( v55 < 0 )
  {
    if ( *(_DWORD *)(a2 + 112) >= 2u )
    {
      if ( a1[3] > 7u )
        a1 = (_QWORD *)*a1;
      v62 = L"BITSJobId";
      goto LABEL_145;
    }
  }
  else
  {
    v58 = v73;
    v59 = (void **)(a2 + 32);
    do
      ++v11;
    while ( *((_WORD *)v73 + v11) );
    if ( v11 > *(_QWORD *)(a2 + 56) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v59,
        v11,
        v56,
        v73);
    }
    else
    {
      if ( *(_QWORD *)(a2 + 56) <= 7u )
        v60 = (void *)(a2 + 32);
      else
        v60 = *v59;
      *(_QWORD *)(a2 + 48) = v11;
      memmove_0(v60, v58, 2 * v11);
      *((_WORD *)v60 + v11) = 0;
    }
  }
  LODWORD(v65) = 0;
  v61 = a1;
  if ( a1[3] > 7u )
    v61 = (_QWORD *)*a1;
  if ( v61 )
  {
    hKey = 0;
    if ( (int)GetCDNDownloadKey(&hKey) >= 0 )
    {
      v63 = hKey;
      DCCDNUtil_GetRegistryDWORD(hKey, 0, L"LastError", (unsigned int *)&v65);
      if ( v63 )
        RegCloseKey(v63);
      *(_DWORD *)(a2 + 128) = v65;
      goto LABEL_157;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      v65);
  }
  if ( (unsigned int)(*(_DWORD *)(a2 + 112) - 4) <= 7 )
  {
    if ( a1[3] > 7u )
      a1 = (_QWORD *)*a1;
    v62 = L"LastError";
LABEL_145:
    LogTelemetryError(L"JobHelper::GetJob: Failed to get %1 with error: 0x%2!x! for job %3", v62, 0, a1, v65);
    if ( v73 )
      operator delete(v73);
    if ( v69 )
      operator delete(v69);
    if ( Src )
      operator delete(Src);
    if ( Block )
      operator delete(Block);
    std::wstring::~wstring((char **)v74);
    return 2;
  }
LABEL_157:
  LODWORD(v65) = 0;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  if ( a1 )
  {
    hKey = 0;
    if ( (int)GetCDNDownloadKey(&hKey) >= 0 )
    {
      v64 = hKey;
      DCCDNUtil_GetRegistryDWORD(hKey, 0, L"RetryCount", (unsigned int *)&v65);
      if ( v64 )
        RegCloseKey(v64);
      *(_DWORD *)(a2 + 120) = v65;
    }
    else if ( hKey )
    {
      RegCloseKey(hKey);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      v65);
  }
  if ( v73 )
    operator delete(v73);
  if ( v69 )
    operator delete(v69);
  if ( Src )
    operator delete(Src);
  if ( Block )
    operator delete(Block);
  std::wstring::~wstring((char **)v74);
  return 0;
}

```

## disassembly

```asm
0x14004f798  mov     [rsp-8+arg_10], rbx
0x14004f79d  push    rbp
0x14004f79e  push    rsi
0x14004f79f  push    rdi
0x14004f7a0  push    r12
0x14004f7a2  push    r13
0x14004f7a4  push    r14
0x14004f7a6  push    r15
0x14004f7a8  lea     rbp, [rsp-20h]
0x14004f7ad  sub     rsp, 120h
0x14004f7b4  mov     rax, cs:__security_cookie
0x14004f7bb  xor     rax, rsp
0x14004f7be  mov     [rbp+50h+var_40], rax
0x14004f7c2  mov     r15, rdx
0x14004f7c5  mov     rdi, rcx
0x14004f7c8  xorps   xmm0, xmm0
0x14004f7cb  movups  [rsp+150h+var_E8], xmm0
0x14004f7d0  xorps   xmm1, xmm1
0x14004f7d3  movdqu  [rsp+150h+var_D8], xmm1
0x14004f7d9  xor     r8d, r8d
0x14004f7dc  lea     rdx, SubKey
0x14004f7e3  lea     rcx, [rsp+150h+var_E8]
0x14004f7e8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004f7ed  nop
0x14004f7ee  xorps   xmm0, xmm0
0x14004f7f1  movups  xmmword ptr [rbp+50h+pclsid.Data1], xmm0
0x14004f7f5  mov     rdx, rdi
0x14004f7f8  mov     rcx, r15
0x14004f7fb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14004f800  xor     r13d, r13d
0x14004f803  mov     [rsp+150h+Block], r13
0x14004f808  lea     rax, [rsp+150h+Block]
0x14004f80d  mov     [rsp+150h+var_108], rax
0x14004f812  mov     [rsp+150h+var_100], r13
0x14004f817  mov     [rsp+150h+var_F8], 1
0x14004f81c  mov     rcx, rdi
0x14004f81f  cmp     qword ptr [rdi+18h], 7
0x14004f824  jbe     short loc_14004F829
0x14004f826  mov     rcx, [rdi]
0x14004f829  lea     r8, [rsp+150h+var_100]
0x14004f82e  lea     rdx, aSourceurl; "SourceUrl"
0x14004f835  call    GetCDNRecordString
0x14004f83a  mov     ebx, eax
0x14004f83c  mov     r14d, 2
0x14004f842  cmp     [rsp+150h+var_F8], r13b
0x14004f847  jz      short loc_14004F866
0x14004f849  mov     r8, [rsp+150h+var_108]
0x14004f84e  mov     rcx, [r8]; Block
0x14004f851  mov     rdx, [rsp+150h+var_100]
0x14004f856  mov     [r8], rdx
0x14004f859  test    rcx, rcx
0x14004f85c  jz      short loc_14004F866
0x14004f85e  mov     edx, r14d
0x14004f861  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004f866  test    ebx, ebx
0x14004f868  jns     short loc_14004F8A5
0x14004f86a  mov     r8d, ebx
0x14004f86d  lea     rdx, aUrl; "URL"
0x14004f874  lea     rcx, aJobhelperGetjo_6; "JobHelper::GetJob: Failed to get %1 wit"...
0x14004f87b  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004f880  nop
0x14004f881  mov     rcx, [rsp+150h+Block]; Block
0x14004f886  test    rcx, rcx
0x14004f889  jz      short loc_14004F894
0x14004f88b  mov     rdx, r14
0x14004f88e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004f893  nop
0x14004f894  lea     rcx, [rsp+150h+var_E8]
0x14004f899  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004f89e  mov     eax, ebx
0x14004f8a0  jmp     loc_1400500F8
0x14004f8a5  mov     r9, [rsp+150h+Block]
0x14004f8aa  lea     rcx, [r15+88h]
0x14004f8b1  or      r12, 0FFFFFFFFFFFFFFFFh
0x14004f8b5  mov     rdx, r12
0x14004f8b8  inc     rdx
0x14004f8bb  cmp     [r9+rdx*2], r13w
0x14004f8c0  jnz     short loc_14004F8B8
0x14004f8c2  cmp     rdx, [rcx+18h]
0x14004f8c6  ja      short loc_14004F8F4
0x14004f8c8  cmp     qword ptr [rcx+18h], 7
0x14004f8cd  jbe     short loc_14004F8D4
0x14004f8cf  mov     rsi, [rcx]
0x14004f8d2  jmp     short loc_14004F8D7
0x14004f8d4  mov     rsi, rcx
0x14004f8d7  mov     [rcx+10h], rdx
0x14004f8db  lea     rbx, [rdx+rdx]
0x14004f8df  mov     r8, rbx; Size
0x14004f8e2  mov     rdx, r9; Src
0x14004f8e5  mov     rcx, rsi; void *
0x14004f8e8  call    memmove_0
0x14004f8ed  mov     [rbx+rsi], r13w
0x14004f8f2  jmp     short loc_14004F8F9
0x14004f8f4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14004f8f9  mov     [rsp+150h+Src], r13
0x14004f8fe  lea     rax, [rsp+150h+Src]
0x14004f903  mov     [rsp+150h+var_108], rax
0x14004f908  mov     [rsp+150h+var_100], r13
0x14004f90d  mov     [rsp+150h+var_F8], 1
0x14004f912  mov     rcx, rdi
0x14004f915  cmp     qword ptr [rdi+18h], 7
0x14004f91a  jbe     short loc_14004F91F
0x14004f91c  mov     rcx, [rdi]
0x14004f91f  lea     r8, [rsp+150h+var_100]
0x14004f924  lea     rdx, aDestinationfil; "DestinationFilePath"
0x14004f92b  call    GetCDNRecordString
0x14004f930  mov     ebx, eax
0x14004f932  cmp     [rsp+150h+var_F8], r13b
0x14004f937  jz      short loc_14004F956
0x14004f939  mov     r8, [rsp+150h+var_108]
0x14004f93e  mov     rcx, [r8]; Block
0x14004f941  mov     rdx, [rsp+150h+var_100]
0x14004f946  mov     [r8], rdx
0x14004f949  test    rcx, rcx
0x14004f94c  jz      short loc_14004F956
0x14004f94e  mov     rdx, r14
0x14004f951  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004f956  test    ebx, ebx
0x14004f958  jns     short loc_14004F98C
0x14004f95a  mov     r8d, ebx
0x14004f95d  lea     rdx, aDownloadlocati; "DownloadLocation"
0x14004f964  lea     rcx, aJobhelperGetjo_6; "JobHelper::GetJob: Failed to get %1 wit"...
0x14004f96b  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004f970  nop
0x14004f971  mov     rcx, [rsp+150h+Src]; Block
0x14004f976  test    rcx, rcx
0x14004f979  jz      loc_14004F881
0x14004f97f  mov     rdx, r14
0x14004f982  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004f987  jmp     loc_14004F881
0x14004f98c  mov     r9, [rsp+150h+Src]
0x14004f991  lea     rcx, [r15+0A8h]
0x14004f998  mov     rdx, r12
0x14004f99b  inc     rdx
0x14004f99e  cmp     [r9+rdx*2], r13w
0x14004f9a3  jnz     short loc_14004F99B
0x14004f9a5  cmp     rdx, [rcx+18h]
0x14004f9a9  ja      short loc_14004F9D7
0x14004f9ab  cmp     qword ptr [rcx+18h], 7
0x14004f9b0  jbe     short loc_14004F9B7
0x14004f9b2  mov     rsi, [rcx]
0x14004f9b5  jmp     short loc_14004F9BA
0x14004f9b7  mov     rsi, rcx
0x14004f9ba  mov     [rcx+10h], rdx
0x14004f9be  lea     rbx, [rdx+rdx]
0x14004f9c2  mov     r8, rbx; Size
0x14004f9c5  mov     rdx, r9; Src
0x14004f9c8  mov     rcx, rsi; void *
0x14004f9cb  call    memmove_0
0x14004f9d0  mov     [rsi+rbx], r13w
0x14004f9d5  jmp     short loc_14004F9DC
0x14004f9d7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14004f9dc  mov     [rsp+150h+var_110], r13
0x14004f9e1  lea     rax, [rsp+150h+var_110]
0x14004f9e6  mov     [rsp+150h+var_108], rax
0x14004f9eb  mov     [rsp+150h+var_100], r13
0x14004f9f0  mov     [rsp+150h+var_F8], 1
0x14004f9f5  mov     rcx, rdi
0x14004f9f8  cmp     qword ptr [rdi+18h], 7
0x14004f9fd  jbe     short loc_14004FA02
0x14004f9ff  mov     rcx, [rdi]
0x14004fa02  lea     r8, [rsp+150h+var_100]
0x14004fa07  lea     rdx, aOriginator; "Originator"
0x14004fa0e  call    GetCDNRecordString
0x14004fa13  mov     ebx, eax
0x14004fa15  cmp     [rsp+150h+var_F8], r13b
0x14004fa1a  jz      short loc_14004FA39
0x14004fa1c  mov     r8, [rsp+150h+var_108]
0x14004fa21  mov     rcx, [r8]; Block
0x14004fa24  mov     rdx, [rsp+150h+var_100]
0x14004fa29  mov     [r8], rdx
0x14004fa2c  test    rcx, rcx
0x14004fa2f  jz      short loc_14004FA39
0x14004fa31  mov     rdx, r14
0x14004fa34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004fa39  test    ebx, ebx
0x14004fa3b  jns     short loc_14004FA6F
0x14004fa3d  mov     r8d, ebx
0x14004fa40  lea     rdx, aOriginator_0; "Originator"
0x14004fa47  lea     rcx, aJobhelperGetjo_6; "JobHelper::GetJob: Failed to get %1 wit"...
0x14004fa4e  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004fa53  nop
0x14004fa54  mov     rcx, [rsp+150h+var_110]; Block
0x14004fa59  test    rcx, rcx
0x14004fa5c  jz      loc_14004F971
0x14004fa62  mov     rdx, r14
0x14004fa65  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004fa6a  jmp     loc_14004F971
0x14004fa6f  mov     r9, [rsp+150h+var_110]
0x14004fa74  lea     rcx, [r15+40h]
0x14004fa78  mov     rdx, r12
0x14004fa7b  inc     rdx
0x14004fa7e  cmp     [r9+rdx*2], r13w
0x14004fa83  jnz     short loc_14004FA7B
0x14004fa85  cmp     rdx, [rcx+18h]
0x14004fa89  ja      short loc_14004FAB7
0x14004fa8b  cmp     qword ptr [rcx+18h], 7
0x14004fa90  jbe     short loc_14004FA97
0x14004fa92  mov     rsi, [rcx]
0x14004fa95  jmp     short loc_14004FA9A
0x14004fa97  mov     rsi, rcx
0x14004fa9a  mov     [rcx+10h], rdx
0x14004fa9e  lea     rbx, [rdx+rdx]
0x14004faa2  mov     r8, rbx; Size
0x14004faa5  mov     rdx, r9; Src
0x14004faa8  mov     rcx, rsi; void *
0x14004faab  call    memmove_0
0x14004fab0  mov     [rsi+rbx], r13w
0x14004fab5  jmp     short loc_14004FABC
0x14004fab7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14004fabc  mov     rdx, rdi
0x14004fabf  cmp     qword ptr [rdi+18h], 7
0x14004fac4  jbe     short loc_14004FAC9
0x14004fac6  mov     rdx, [rdi]
0x14004fac9  mov     dword ptr [rsp+150h+var_130], r13d; int
0x14004face  test    rdx, rdx
0x14004fad1  jnz     short loc_14004FAF3
0x14004fad3  mov     rcx, [rbp+58h]; this
0x14004fad7  mov     esi, 80070057h
0x14004fadc  mov     r9d, esi; char *
0x14004fadf  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004fae6  mov     edx, 48Bh; void *
0x14004faeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004faf0  nop
0x14004faf1  jmp     short loc_14004FB5A
0x14004faf3  mov     [rsp+150h+hKey], r13
0x14004faf8  lea     rcx, [rsp+150h+hKey]
0x14004fafd  call    GetCDNDownloadKey
0x14004fb02  mov     esi, eax
0x14004fb04  test    eax, eax
0x14004fb06  jns     short loc_14004FB1A
0x14004fb08  mov     rcx, [rsp+150h+hKey]; hKey
0x14004fb0d  test    rcx, rcx
0x14004fb10  jz      short loc_14004FB5A
0x14004fb12  call    cs:__imp_RegCloseKey
0x14004fb18  jmp     short loc_14004FB5A
0x14004fb1a  mov     r14d, r13d
0x14004fb1d  lea     r9, [rsp+150h+var_130]; unsigned int *
0x14004fb22  lea     r8, aState; "State"
0x14004fb29  xor     edx, edx; unsigned __int16 *
0x14004fb2b  mov     rbx, [rsp+150h+hKey]
0x14004fb30  mov     rcx, rbx; HKEY
0x14004fb33  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14004fb38  mov     esi, eax
0x14004fb3a  test    eax, eax
0x14004fb3c  cmovns  r14d, dword ptr [rsp+150h+var_130]
0x14004fb42  test    rbx, rbx
0x14004fb45  jz      short loc_14004FB50
0x14004fb47  mov     rcx, rbx; hKey
0x14004fb4a  call    cs:__imp_RegCloseKey
0x14004fb50  test    esi, esi
0x14004fb52  jns     short loc_14004FBAD
0x14004fb54  mov     r14d, 2
0x14004fb5a  mov     r8d, esi
0x14004fb5d  lea     rdx, aStatus_0; "Status"
0x14004fb64  lea     rcx, aJobhelperGetjo_6; "JobHelper::GetJob: Failed to get %1 wit"...
0x14004fb6b  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14004fb70  nop
0x14004fb71  mov     rcx, [rsp+150h+var_110]; Block
0x14004fb76  test    rcx, rcx
0x14004fb79  jz      short loc_14004FB84
0x14004fb7b  mov     rdx, r14
0x14004fb7e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004fb83  nop
0x14004fb84  mov     rcx, [rsp+150h+Src]; Block
0x14004fb89  test    rcx, rcx
0x14004fb8c  jz      short loc_14004FB97
0x14004fb8e  mov     rdx, r14
0x14004fb91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14004fb96  nop
0x14004fb97  mov     rcx, [rsp+150h+Block]
0x14004fb9c  test    rcx, rcx
0x14004fb9f  jz      loc_14004FDF8
0x14004fba5  mov     rdx, r14
0x14004fba8  jmp     loc_14004FDF3
0x14004fbad  mov     [r15+70h], r14d
0x14004fbb1  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x14004fbb8  movdqu  xmmword ptr [r15+60h], xmm0
0x14004fbbe  mov     [rsp+150h+hKey], r13
0x14004fbc3  mov     rcx, rdi
0x14004fbc6  cmp     qword ptr [rdi+18h], 7
0x14004fbcb  jbe     short loc_14004FBD0
0x14004fbcd  mov     rcx, [rdi]
0x14004fbd0  lea     r8, [rsp+150h+hKey]
0x14004fbd5  lea     rdx, aEnrollmentid; "EnrollmentId"
0x14004fbdc  call    GetCDNRecordString
0x14004fbe1  test    eax, eax
0x14004fbe3  js      loc_14004FE21
0x14004fbe9  mov     rbx, [rsp+150h+hKey]
0x14004fbee  mov     r8d, 1; MaxCount
0x14004fbf4  lea     r14, asc_14006B080; "{"
0x14004fbfb  mov     rdx, r14; String2
0x14004fbfe  mov     rcx, rbx; String1
0x14004fc01  call    wcsncmp_0
0x14004fc06  mov     esi, 32h ; '2'
0x14004fc0b  test    eax, eax
0x14004fc0d  mov     eax, 7FFFFFFEh
0x14004fc12  jz      loc_14004FD28
0x14004fc18  mov     edx, esi
0x14004fc1a  lea     r8, [rbp+50h+sz]
  ... truncated ...
```
