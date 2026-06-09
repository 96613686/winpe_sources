# CabUtils::GetWinTrustDataForFileInCatalog(void *,ushort const *,_WINTRUST_DATA *,_GUID *)

- ea: `0x18003e190`
- end: `0x18003e49a`
- name: `?GetWinTrustDataForFileInCatalog@CabUtils@@CAJPEAXPEBGPEAU_WINTRUST_DATA@@PEAU_GUID@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(HANDLE hFile, const unsigned __int16 *, struct _WINTRUST_DATA *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003e60c`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18001206c`
- `0x18001208c`
- `0x18003e190`
- `0x18003e5d4`

## import_xrefs

- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18003e2d2`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x18003e2d2`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18003e26e`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x18003e26e`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18003e1f9`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18003e1f9`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e229`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e2b4`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e409`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e473`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e229`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e2b4`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e409`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18003e473`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18003e2a2`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18003e3f7`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18003e461`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18003e2a2`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18003e3f7`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x18003e461`
- `WINTRUST!WinVerifyTrust` at `0x18003e3c6`
- `WINTRUST!WinVerifyTrust` at `0x18003e3c6`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18003e240`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x18003e240`

## string_xrefs

- `0x18003e20f`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e284`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e2e3`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003e3d3`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c
__int64 __fastcall CabUtils::GetWinTrustDataForFileInCatalog(
        HANDLE hFile,
        const unsigned __int16 *a2,
        struct _WINTRUST_DATA *a3,
        struct _GUID *a4)
{
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int LastError; // ebx
  HCATINFO v12; // rax
  const char *v13; // r9
  void *v14; // rbx
  unsigned int v15; // edi
  const char *v16; // r9
  HWND v17; // rcx
  int v18; // esi
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  int phPrevCatInfo; // [rsp+20h] [rbp-E0h]
  HCATADMIN hCatAdmin; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbHash; // [rsp+38h] [rbp-C8h] BYREF
  struct _WINTRUST_DATA pWVTData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+90h] [rbp-70h]
  _QWORD v28[6]; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+D4h] [rbp-2Ch]
  __int64 v31; // [rsp+DCh] [rbp-24h]
  int v32; // [rsp+E4h] [rbp-1Ch]
  GUID pgActionID; // [rsp+F0h] [rbp-10h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+100h] [rbp+0h] BYREF
  BYTE pbHash[64]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+298h]

  hCatAdmin = 0;
  memset_0(&psCatInfo, 0, sizeof(psCatInfo));
  pcbHash = 64;
  if ( !CryptCATAdminCalcHashFromFileHandle(hFile, &pcbHash, pbHash, 0) )
  {
    v9 = 579;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
                  v8);
    if ( hCatAdmin )
      CryptCATAdminReleaseContext(hCatAdmin, 0);
    return LastError;
  }
  if ( !CryptCATAdminAcquireContext(&hCatAdmin, 0, 0) )
  {
    v9 = 582;
    goto LABEL_3;
  }
  v12 = CryptCATAdminEnumCatalogFromHash(hCatAdmin, pbHash, pcbHash, 0, 0);
  v14 = v12;
  if ( v12 == (HCATINFO)-1LL )
  {
    v15 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x249,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
            v13);
LABEL_10:
    CryptCATAdminReleaseCatalogContext(hCatAdmin, v14, 0);
LABEL_11:
    if ( hCatAdmin )
      CryptCATAdminReleaseContext(hCatAdmin, 0);
    return v15;
  }
  psCatInfo.cbStruct = 524;
  if ( !CryptCATCatalogInfoFromContext(v12, &psCatInfo, 0) )
  {
    v15 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x24C,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
            v16);
    if ( !v14 )
      goto LABEL_11;
    goto LABEL_10;
  }
  v28[4] = hFile;
  v28[1] = psCatInfo.wszCatalogFile;
  v28[0] = 72;
  v28[5] = pbHash;
  v29 = pcbHash;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v28[3] = a2;
  v28[2] = 0;
  memset_0(&pWVTData, 0, 0x58u);
  pWVTData.cbStruct = 88;
  pWVTData.pFile = (struct WINTRUST_FILE_INFO_ *)v28;
  pWVTData.dwUnionChoice = 2;
  *(_QWORD *)&pWVTData.dwUIChoice = 2;
  pWVTData.dwProvFlags = 4224;
  pWVTData.dwStateAction = 1;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  v18 = CabUtils::HrWinVerifyTrust(v17, &pgActionID, &pWVTData);
  if ( v18 >= 0 )
  {
    v19 = *(_OWORD *)&pWVTData.pSIPClientData;
    *(_OWORD *)&a3->cbStruct = *(_OWORD *)&pWVTData.cbStruct;
    v20 = *(_OWORD *)&pWVTData.dwUnionChoice;
    *(_OWORD *)&a3->pSIPClientData = v19;
    v21 = *(_OWORD *)&pWVTData.dwStateAction;
    *(_OWORD *)&a3->dwUnionChoice = v20;
    v22 = *(_OWORD *)&pWVTData.pwszURLReference;
    *(_OWORD *)&a3->dwStateAction = v21;
    *(_QWORD *)&v21 = v27;
    *(_OWORD *)&a3->pwszURLReference = v22;
    *(_QWORD *)&a3[1].cbStruct = v21;
    *a4 = pgActionID;
    if ( v14 )
      CryptCATAdminReleaseCatalogContext(hCatAdmin, v14, 0);
    if ( hCatAdmin )
      CryptCATAdminReleaseContext(hCatAdmin, 0);
    return 0;
  }
  else
  {
    pWVTData.dwStateAction = 2;
    WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, &pWVTData);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26A,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
      (const char *)(unsigned int)v18,
      phPrevCatInfo);
    if ( v14 )
      CryptCATAdminReleaseCatalogContext(hCatAdmin, v14, 0);
    if ( hCatAdmin )
      CryptCATAdminReleaseContext(hCatAdmin, 0);
    return (unsigned int)v18;
  }
}

```

## disassembly

```asm
0x18003e190  push    rbp
0x18003e192  push    rbx
0x18003e193  push    rsi
0x18003e194  push    rdi
0x18003e195  push    r14
0x18003e197  push    r15
0x18003e199  lea     rbp, [rsp-268h]
0x18003e1a1  sub     rsp, 368h
0x18003e1a8  mov     rax, cs:__security_cookie
0x18003e1af  xor     rax, rsp
0x18003e1b2  mov     [rbp+290h+var_40], rax
0x18003e1b9  mov     rdi, r8
0x18003e1bc  mov     [rsp+390h+hCatAdmin], 0
0x18003e1c5  mov     r15, rdx
0x18003e1c8  mov     rsi, rcx
0x18003e1cb  xor     edx, edx; Val
0x18003e1cd  lea     rcx, [rbp+290h+psCatInfo]; void *
0x18003e1d1  mov     r8d, 20Ch; Size
0x18003e1d7  mov     r14, r9
0x18003e1da  call    memset_0
0x18003e1df  xor     r9d, r9d; dwFlags
0x18003e1e2  mov     [rsp+390h+pcbHash], 40h ; '@'
0x18003e1ea  lea     r8, [rbp+290h+pbHash]; pbHash
0x18003e1f1  mov     rcx, rsi; hFile
0x18003e1f4  lea     rdx, [rsp+390h+pcbHash]; pcbHash
0x18003e1f9  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18003e1ff  test    eax, eax
0x18003e201  jnz     short loc_18003E236
0x18003e203  mov     edx, 243h; void *
0x18003e208  mov     rcx, [rbp+298h]; this
0x18003e20f  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e216  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e21b  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e220  mov     ebx, eax
0x18003e222  test    rcx, rcx
0x18003e225  jz      short loc_18003E22F
0x18003e227  xor     edx, edx; dwFlags
0x18003e229  call    cs:__imp_CryptCATAdminReleaseContext
0x18003e22f  mov     eax, ebx
0x18003e231  jmp     loc_18003E47B
0x18003e236  xor     r8d, r8d; dwFlags
0x18003e239  lea     rcx, [rsp+390h+hCatAdmin]; phCatAdmin
0x18003e23e  xor     edx, edx; pgSubsystem
0x18003e240  call    cs:__imp_CryptCATAdminAcquireContext
0x18003e246  test    eax, eax
0x18003e248  jnz     short loc_18003E251
0x18003e24a  mov     edx, 246h
0x18003e24f  jmp     short loc_18003E208
0x18003e251  mov     r8d, [rsp+390h+pcbHash]; cbHash
0x18003e256  lea     rdx, [rbp+290h+pbHash]; pbHash
0x18003e25d  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e262  xor     r9d, r9d; dwFlags
0x18003e265  mov     qword ptr [rsp+390h+phPrevCatInfo], 0; int
0x18003e26e  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x18003e274  mov     rbx, rax
0x18003e277  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e27b  jnz     short loc_18003E2C1
0x18003e27d  mov     rcx, [rbp+298h]; this
0x18003e284  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e28b  mov     edx, 249h; void *
0x18003e290  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e295  mov     edi, eax
0x18003e297  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e29c  xor     r8d, r8d; dwFlags
0x18003e29f  mov     rdx, rbx; hCatInfo
0x18003e2a2  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x18003e2a8  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e2ad  test    rcx, rcx
0x18003e2b0  jz      short loc_18003E2BA
0x18003e2b2  xor     edx, edx; dwFlags
0x18003e2b4  call    cs:__imp_CryptCATAdminReleaseContext
0x18003e2ba  mov     eax, edi
0x18003e2bc  jmp     loc_18003E47B
0x18003e2c1  xor     r8d, r8d; dwFlags
0x18003e2c4  mov     [rbp+290h+psCatInfo.cbStruct], 20Ch
0x18003e2cb  lea     rdx, [rbp+290h+psCatInfo]; psCatInfo
0x18003e2cf  mov     rcx, rbx; hCatInfo
0x18003e2d2  call    cs:__imp_CryptCATCatalogInfoFromContext
0x18003e2d8  test    eax, eax
0x18003e2da  jnz     short loc_18003E2FD
0x18003e2dc  mov     rcx, [rbp+298h]; this
0x18003e2e3  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e2ea  mov     edx, 24Ch; void *
0x18003e2ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e2f4  mov     edi, eax
0x18003e2f6  test    rbx, rbx
0x18003e2f9  jz      short loc_18003E2A8
0x18003e2fb  jmp     short loc_18003E297
0x18003e2fd  lea     rax, [rbp+290h+psCatInfo.wszCatalogFile]
0x18003e301  mov     [rbp+290h+var_2D0], rsi
0x18003e305  mov     [rbp+290h+var_2E8], rax
0x18003e309  lea     rcx, [rsp+390h+pWVTData]; void *
0x18003e30e  lea     rax, [rbp+290h+pbHash]
0x18003e315  mov     [rbp+290h+var_2F0], 48h ; 'H'
0x18003e31d  mov     [rbp+290h+var_2C8], rax
0x18003e321  mov     esi, 58h ; 'X'
0x18003e326  mov     eax, [rsp+390h+pcbHash]
0x18003e32a  mov     r8d, esi; Size
0x18003e32d  xor     edx, edx; Val
0x18003e32f  mov     [rbp+290h+var_2C0], eax
0x18003e332  mov     [rbp+290h+var_2BC], 0
0x18003e33a  mov     [rbp+290h+var_2B4], 0
0x18003e342  mov     [rbp+290h+var_2AC], 0
0x18003e349  mov     [rbp+290h+var_2D8], r15
0x18003e34d  mov     [rbp+290h+var_2E0], 0
0x18003e355  call    memset_0
0x18003e35a  lea     rax, [rbp+290h+var_2F0]
0x18003e35e  mov     dword ptr [rsp+390h+pWVTData], esi
0x18003e362  lea     r15d, [rsi-56h]
0x18003e366  mov     qword ptr [rsp+390h+var_330+8], rax
0x18003e36b  lea     r8, [rsp+390h+pWVTData]; struct _WINTRUST_DATA *
0x18003e370  mov     dword ptr [rsp+390h+var_330], r15d
0x18003e375  lea     rdx, [rbp+290h+pgActionID]; struct _GUID *
0x18003e379  mov     [rsp+390h+var_338], r15
0x18003e37e  mov     [rbp+290h+var_308], 1080h
0x18003e385  mov     dword ptr [rsp+390h+var_320], 1
0x18003e38d  mov     [rbp+290h+pgActionID.Data1], 0AAC56Bh
0x18003e394  mov     dword ptr [rbp+290h+pgActionID.Data2], 11D0CD44h
0x18003e39b  mov     dword ptr [rbp+290h+pgActionID.Data4], 0C000C28Ch
0x18003e3a2  mov     dword ptr [rbp+290h+pgActionID.Data4+4], 0EE95C24Fh
0x18003e3a9  call    ?HrWinVerifyTrust@CabUtils@@CAJQEAUHWND__@@AEAU_GUID@@AEAU_WINTRUST_DATA@@@Z; CabUtils::HrWinVerifyTrust(HWND__ * const,_GUID &,_WINTRUST_DATA &)
0x18003e3ae  mov     esi, eax
0x18003e3b0  test    eax, eax
0x18003e3b2  jns     short loc_18003E413
0x18003e3b4  lea     r8, [rsp+390h+pWVTData]; pWVTData
0x18003e3b9  mov     dword ptr [rsp+390h+var_320], r15d
0x18003e3be  lea     rdx, [rbp+290h+pgActionID]; pgActionID
0x18003e3c2  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x18003e3c6  call    cs:__imp_WinVerifyTrust
0x18003e3cc  mov     rcx, [rbp+298h]; this
0x18003e3d3  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003e3da  mov     r9d, esi; char *
0x18003e3dd  mov     edx, 26Ah; void *
0x18003e3e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e3e7  test    rbx, rbx
0x18003e3ea  jz      short loc_18003E3FD
0x18003e3ec  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e3f1  xor     r8d, r8d; dwFlags
0x18003e3f4  mov     rdx, rbx; hCatInfo
0x18003e3f7  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x18003e3fd  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e402  test    rcx, rcx
0x18003e405  jz      short loc_18003E40F
0x18003e407  xor     edx, edx; dwFlags
0x18003e409  call    cs:__imp_CryptCATAdminReleaseContext
0x18003e40f  mov     eax, esi
0x18003e411  jmp     short loc_18003E47B
0x18003e413  movaps  xmm0, [rsp+390h+pWVTData]
0x18003e418  movaps  xmm1, xmmword ptr [rsp+50h]
0x18003e41d  movaps  xmmword ptr [rdi], xmm0
0x18003e420  movaps  xmm0, [rsp+390h+var_330]
0x18003e425  movaps  xmmword ptr [rdi+10h], xmm1
0x18003e429  movaps  xmm1, [rsp+390h+var_320]
0x18003e42e  movaps  xmmword ptr [rdi+20h], xmm0
0x18003e432  movaps  xmm0, xmmword ptr [rbp-80h]
0x18003e436  movaps  xmmword ptr [rdi+30h], xmm1
0x18003e43a  movsd   xmm1, [rbp+290h+var_300]
0x18003e43f  movaps  xmmword ptr [rdi+40h], xmm0
0x18003e443  movsd   qword ptr [rdi+50h], xmm1
0x18003e448  movups  xmm0, xmmword ptr [rbp+290h+pgActionID.Data1]
0x18003e44c  movdqu  xmmword ptr [r14], xmm0
0x18003e451  test    rbx, rbx
0x18003e454  jz      short loc_18003E467
0x18003e456  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e45b  xor     r8d, r8d; dwFlags
0x18003e45e  mov     rdx, rbx; hCatInfo
0x18003e461  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x18003e467  mov     rcx, [rsp+390h+hCatAdmin]; hCatAdmin
0x18003e46c  test    rcx, rcx
0x18003e46f  jz      short loc_18003E479
0x18003e471  xor     edx, edx; dwFlags
0x18003e473  call    cs:__imp_CryptCATAdminReleaseContext
0x18003e479  xor     eax, eax
0x18003e47b  mov     rcx, [rbp+290h+var_40]
0x18003e482  xor     rcx, rsp; StackCookie
0x18003e485  call    __security_check_cookie
0x18003e48a  add     rsp, 368h
0x18003e491  pop     r15
0x18003e493  pop     r14
0x18003e495  pop     rdi
0x18003e496  pop     rsi
0x18003e497  pop     rbx
0x18003e498  pop     rbp
0x18003e499  retn
```
