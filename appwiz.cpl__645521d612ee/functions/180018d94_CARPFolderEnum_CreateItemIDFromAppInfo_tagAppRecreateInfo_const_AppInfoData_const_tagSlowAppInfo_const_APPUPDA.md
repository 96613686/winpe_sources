# CARPFolderEnum::_CreateItemIDFromAppInfo(tagAppRecreateInfo const *,_AppInfoData const *,_tagSlowAppInfo const *,APPUPDATEINFO const *,ulong,ulong,_ITEMID_CHILD * *)

- ea: `0x180018d94`
- end: `0x18001933a`
- name: `?_CreateItemIDFromAppInfo@CARPFolderEnum@@AEAAJPEBUtagAppRecreateInfo@@PEBU_AppInfoData@@PEBU_tagSlowAppInfo@@PEBUAPPUPDATEINFO@@KKPEAPEAU_ITEMID_CHILD@@@Z`
- size: `1446`
- prototype: `__int64 __fastcall(CARPFolderEnum *__hidden this, const struct tagAppRecreateInfo *, const struct _AppInfoData *, const struct _tagSlowAppInfo *, const struct APPUPDATEINFO *, unsigned int, unsigned int, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800198bc`

## callees

- `0x180007960`
- `0x180008cf8`
- `0x180018d94`
- `0x18001b000`
- `0x180045080`
- `0x18005165c`
- `0x18005169c`
- `0x1800516dc`
- `0x180051724`
- `0x1800517c0`
- `0x1800582a2`
- `0x1800582e0`
- `0x1800583a0`
- `0x180059010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180018dfb`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180018dfb`
- `SHLWAPI!PathParseIconLocationW` at `0x180018e49`
- `SHLWAPI!PathParseIconLocationW` at `0x180018e66`
- `SHLWAPI!PathParseIconLocationW` at `0x180018e49`
- `SHLWAPI!PathParseIconLocationW` at `0x180018e66`
- `SHLWAPI!StrToIntW` at `0x180018f7a`
- `SHLWAPI!StrToIntW` at `0x180018f7a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019008`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180019008`

## string_xrefs

- `0x1800190dd`: `launchreadmeurl`
- `0x180019141`: `launchupdateurl`

## pseudocode

```c
__int64 __fastcall CARPFolderEnum::_CreateItemIDFromAppInfo(
        CARPFolderEnum *this,
        const struct tagAppRecreateInfo *a2,
        const struct _AppInfoData *a3,
        const struct _tagSlowAppInfo *a4,
        const struct APPUPDATEINFO *a5,
        unsigned int a6,
        unsigned int a7,
        struct _ITEMID_CHILD **a8)
{
  __int64 v12; // rdx
  HRESULT ItemID; // edi
  WCHAR *pszImage; // rcx
  int v15; // eax
  LPWSTR v16; // r8
  WCHAR *v17; // rcx
  unsigned int v18; // edi
  const WCHAR *pszInstallDate; // rcx
  unsigned int v20; // eax
  int v21; // r9d
  void *v22; // rdi
  LPWSTR pszSupportUrl; // rax
  void *ullSize; // rax
  __int64 v25; // rax
  _OWORD *v26; // rcx
  __int64 v27; // rax
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int64 v35; // rax
  __int64 v36; // r9
  void *v37; // rdx
  __int64 v38; // r9
  void *ppv[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _SYSTEMTIME v41; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  _DWORD v44[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v45[1060]; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 v46[8]; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int128 v47; // [rsp+4B0h] [rbp+3B0h]
  __int64 v48; // [rsp+4C0h] [rbp+3C0h]
  unsigned __int16 v49[2088]; // [rsp+4D0h] [rbp+3D0h] BYREF

  ppv[0] = 0;
  *a8 = 0;
  ItemID = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, ppv);
  if ( ItemID < 0 )
    goto LABEL_61;
  ItemID = a3->pszDisplayName ? IPropertyStore_SetString(ppv[0], &PKEY_ItemNameDisplay) : -2147467259;
  if ( ItemID < 0 )
    goto LABEL_61;
  pszImage = a3->pszImage;
  if ( pszImage && *pszImage )
  {
    v15 = PathParseIconLocationW(pszImage);
    v16 = a3->pszImage;
LABEL_12:
    v18 = v15;
    if ( v16 && (int)IPropertyStore_SetString(ppv[0], PKEY_IconPath) >= 0 )
      IPropertyStore_SetInt(ppv[0], v12, v18);
    goto LABEL_15;
  }
  v17 = a4->pszImage;
  if ( v17 && *v17 )
  {
    v15 = PathParseIconLocationW(v17);
    v16 = a4->pszImage;
    goto LABEL_12;
  }
LABEL_15:
  if ( a3->pszVersion )
    IPropertyStore_SetString(ppv[0], PKEY_Software_ProductVersion);
  if ( a3->pszPublisher )
    IPropertyStore_SetString(ppv[0], PKEY_Software_Publisher);
  if ( a3->pszProductID )
    IPropertyStore_SetString(ppv[0], PKEY_Software_ProductID);
  if ( a3->pszRegisteredOwner )
    IPropertyStore_SetString(ppv[0], PKEY_Software_RegisteredOwner);
  if ( a3->pszRegisteredCompany )
    IPropertyStore_SetString(ppv[0], PKEY_Software_RegisteredCompany);
  if ( a3->pszSupportTelephone )
    IPropertyStore_SetString(ppv[0], PKEY_Software_SupportTelephone);
  if ( a3->pszInstallLocation )
    IPropertyStore_SetString(ppv[0], PKEY_Software_InstallLocation);
  if ( a3->pszInstallSource )
    IPropertyStore_SetString(ppv[0], PKEY_Software_InstallSource);
  pszInstallDate = a3->pszInstallDate;
  if ( pszInstallDate )
  {
    v41 = 0;
    v20 = StrToIntW(pszInstallDate);
    if ( (unsigned int)InstallDateToSystemTime(v20, &v41) )
      IPropertyStore_SetSystemTime(ppv[0], v12, (unsigned int)&v41, v21, 259);
  }
  v22 = ppv[0];
  *(FILETIME *)&v41.wYear = a4->ftLastUsed;
  v43 = 0;
  *(_OWORD *)pvar = 0;
  if ( (int)InitPropVariantFromFileTimeEx(&v41, v12, 257, pvar) >= 0 )
  {
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v22 + 48LL))(
      v22,
      &PKEY_Software_DateLastUsed,
      pvar);
    PropVariantClear(pvar);
  }
  if ( a3->pszContact )
    IPropertyStore_SetString(ppv[0], PKEY_Software_SupportContactName);
  if ( a3->pszComments )
    IPropertyStore_SetString(ppv[0], PKEY_Software_Comments);
  pszSupportUrl = a3->pszSupportUrl;
  *(_OWORD *)v46 = *(_OWORD *)L"<a id=\"%ws\">%ws</a>";
  v48 = *(_QWORD *)L"/a>";
  v47 = *(_OWORD *)L"ws\">%ws</a>";
  if ( pszSupportUrl && StringCchPrintfW(v49, 0x824u, v46, L"launchsupporturl", pszSupportUrl) >= 0 )
  {
    IPropertyStore_SetString(ppv[0], PKEY_Software_HelpLink);
    IPropertyStore_SetString(ppv[0], PKEY_Software_SupportUrl);
  }
  if ( a3->pszReadmeUrl && StringCchPrintfW(v49, 0x824u, v46, L"launchreadmeurl", a3->pszReadmeUrl) >= 0 )
  {
    IPropertyStore_SetString(ppv[0], PKEY_Software_HelpLink);
    IPropertyStore_SetString(ppv[0], PKEY_Software_ReadMeUrl);
  }
  if ( a3->pszUpdateInfoUrl && StringCchPrintfW(v49, 0x824u, v46, L"launchupdateurl", a3->pszUpdateInfoUrl) >= 0 )
  {
    IPropertyStore_SetString(ppv[0], PKEY_Software_HelpLink);
    IPropertyStore_SetString(ppv[0], PKEY_Software_UpdateInfoUrl);
  }
  if ( a3->pszHelpLink && StringCchPrintfW(v49, 0x824u, v46, L"launchhelpurl", a3->pszHelpLink) >= 0 )
    IPropertyStore_SetString(ppv[0], PKEY_Software_HelpLink);
  ullSize = (void *)a4->ullSize;
  if ( a4->ullSize )
  {
    pvar[0] = 0;
    pvar[1] = ullSize;
    v25 = *(_QWORD *)ppv[0];
    v43 = 0;
    LOWORD(pvar[0]) = 21;
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(v25 + 48))(ppv[0], &PKEY_Size, pvar);
  }
  if ( a4->iTimesUsed >= 0 )
    IPropertyStore_SetUInt32(ppv[0], PKEY_Software_TimesUsed);
  if ( *((_QWORD *)a5 + 3) )
    IPropertyStore_SetString(ppv[0], &PKEY_Software_ParentName);
  memset_0(v45, 0, 0x418u);
  v26 = v45;
  v44[0] = a6;
  v27 = 8;
  do
  {
    v28 = *((_OWORD *)a2 + 1);
    *v26 = *(_OWORD *)a2;
    v29 = *((_OWORD *)a2 + 2);
    v26[1] = v28;
    v30 = *((_OWORD *)a2 + 3);
    v26[2] = v29;
    v31 = *((_OWORD *)a2 + 4);
    v26[3] = v30;
    v32 = *((_OWORD *)a2 + 5);
    v26[4] = v31;
    v33 = *((_OWORD *)a2 + 6);
    v26[5] = v32;
    v34 = *((_OWORD *)a2 + 7);
    a2 = (const struct tagAppRecreateInfo *)((char *)a2 + 128);
    v26[6] = v33;
    v26[7] = v34;
    v26 += 8;
    --v27;
  }
  while ( v27 );
  v35 = *((_QWORD *)a2 + 2);
  v36 = *((_QWORD *)this + 4);
  v37 = ppv[0];
  *v26 = *(_OWORD *)a2;
  *((_QWORD *)v26 + 2) = v35;
  v38 = *(_QWORD *)(v36 + 104);
  v44[2] = a7;
  v44[1] = 0;
  ItemID = CItemIDFactory<tagARPITEM,1230000705>::s_CreateItemID(v44, v37, a8, v38);
LABEL_61:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
  return (unsigned int)ItemID;
}

```

## disassembly

```asm
0x180018d94  mov     [rsp-8+arg_8], rbx
0x180018d99  push    rbp
0x180018d9a  push    rsi
0x180018d9b  push    rdi
0x180018d9c  push    r12
0x180018d9e  push    r13
0x180018da0  push    r14
0x180018da2  push    r15
0x180018da4  lea     rbp, [rsp-1430h]
0x180018dac  mov     eax, 1530h
0x180018db1  call    _alloca_probe
0x180018db6  sub     rsp, rax
0x180018db9  mov     rax, cs:__security_cookie
0x180018dc0  xor     rax, rsp
0x180018dc3  mov     [rbp+1460h+var_40], rax
0x180018dca  mov     r12, [rbp+1460h+arg_38]
0x180018dd1  xor     eax, eax
0x180018dd3  mov     r15, [rbp+1460h+arg_20]
0x180018dda  mov     rsi, rdx
0x180018ddd  mov     r13, rcx
0x180018de0  mov     [rsp+1560h+ppv], rax
0x180018de5  lea     rdx, [rsp+1560h+ppv]; ppv
0x180018dea  mov     r14, r9
0x180018ded  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180018df4  mov     [r12], rax
0x180018df8  mov     rbx, r8
0x180018dfb  call    cs:__imp_PSCreateMemoryPropertyStore
0x180018e01  mov     edi, eax
0x180018e03  test    eax, eax
0x180018e05  js      loc_180019304
0x180018e0b  mov     r8, [rbx+8]
0x180018e0f  test    r8, r8
0x180018e12  jz      short loc_180018E29
0x180018e14  mov     rcx, [rsp+1560h+ppv]
0x180018e19  lea     rdx, PKEY_ItemNameDisplay
0x180018e20  call    IPropertyStore_SetString
0x180018e25  mov     edi, eax
0x180018e27  jmp     short loc_180018E2E
0x180018e29  mov     edi, 80004005h
0x180018e2e  test    edi, edi
0x180018e30  js      loc_180019304
0x180018e36  mov     rcx, [rbx+80h]; pszIconFile
0x180018e3d  xor     edi, edi
0x180018e3f  test    rcx, rcx
0x180018e42  jz      short loc_180018E58
0x180018e44  cmp     [rcx], di
0x180018e47  jz      short loc_180018E58
0x180018e49  call    cs:__imp_PathParseIconLocationW
0x180018e4f  mov     r8, [rbx+80h]
0x180018e56  jmp     short loc_180018E70
0x180018e58  mov     rcx, [r14+18h]; pszIconFile
0x180018e5c  test    rcx, rcx
0x180018e5f  jz      short loc_180018E99
0x180018e61  cmp     [rcx], di
0x180018e64  jz      short loc_180018E99
0x180018e66  call    cs:__imp_PathParseIconLocationW
0x180018e6c  mov     r8, [r14+18h]
0x180018e70  mov     edi, eax
0x180018e72  test    r8, r8
0x180018e75  jz      short loc_180018E99
0x180018e77  mov     rcx, [rsp+1560h+ppv]
0x180018e7c  lea     rdx, PKEY_IconPath
0x180018e83  call    IPropertyStore_SetString
0x180018e88  test    eax, eax
0x180018e8a  js      short loc_180018E99
0x180018e8c  mov     rcx, [rsp+1560h+ppv]
0x180018e91  mov     r8d, edi
0x180018e94  call    IPropertyStore_SetInt
0x180018e99  mov     r8, [rbx+10h]
0x180018e9d  test    r8, r8
0x180018ea0  jz      short loc_180018EB3
0x180018ea2  mov     rcx, [rsp+1560h+ppv]
0x180018ea7  lea     rdx, PKEY_Software_ProductVersion
0x180018eae  call    IPropertyStore_SetString
0x180018eb3  mov     r8, [rbx+18h]
0x180018eb7  test    r8, r8
0x180018eba  jz      short loc_180018ECD
0x180018ebc  mov     rcx, [rsp+1560h+ppv]
0x180018ec1  lea     rdx, PKEY_Software_Publisher
0x180018ec8  call    IPropertyStore_SetString
0x180018ecd  mov     r8, [rbx+20h]
0x180018ed1  test    r8, r8
0x180018ed4  jz      short loc_180018EE7
0x180018ed6  mov     rcx, [rsp+1560h+ppv]
0x180018edb  lea     rdx, PKEY_Software_ProductID
0x180018ee2  call    IPropertyStore_SetString
0x180018ee7  mov     r8, [rbx+28h]
0x180018eeb  test    r8, r8
0x180018eee  jz      short loc_180018F01
0x180018ef0  mov     rcx, [rsp+1560h+ppv]
0x180018ef5  lea     rdx, PKEY_Software_RegisteredOwner
0x180018efc  call    IPropertyStore_SetString
0x180018f01  mov     r8, [rbx+30h]
0x180018f05  test    r8, r8
0x180018f08  jz      short loc_180018F1B
0x180018f0a  mov     rcx, [rsp+1560h+ppv]
0x180018f0f  lea     rdx, PKEY_Software_RegisteredCompany
0x180018f16  call    IPropertyStore_SetString
0x180018f1b  mov     r8, [rbx+48h]
0x180018f1f  test    r8, r8
0x180018f22  jz      short loc_180018F35
0x180018f24  mov     rcx, [rsp+1560h+ppv]
0x180018f29  lea     rdx, PKEY_Software_SupportTelephone
0x180018f30  call    IPropertyStore_SetString
0x180018f35  mov     r8, [rbx+58h]
0x180018f39  test    r8, r8
0x180018f3c  jz      short loc_180018F4F
0x180018f3e  mov     rcx, [rsp+1560h+ppv]
0x180018f43  lea     rdx, PKEY_Software_InstallLocation
0x180018f4a  call    IPropertyStore_SetString
0x180018f4f  mov     r8, [rbx+60h]
0x180018f53  test    r8, r8
0x180018f56  jz      short loc_180018F69
0x180018f58  mov     rcx, [rsp+1560h+ppv]
0x180018f5d  lea     rdx, PKEY_Software_InstallSource
0x180018f64  call    IPropertyStore_SetString
0x180018f69  mov     rcx, [rbx+68h]; pszSrc
0x180018f6d  test    rcx, rcx
0x180018f70  jz      short loc_180018FB2
0x180018f72  xorps   xmm0, xmm0
0x180018f75  movups  xmmword ptr [rsp+1560h+var_1520.wYear], xmm0
0x180018f7a  call    cs:__imp_StrToIntW
0x180018f80  mov     ecx, eax; unsigned int
0x180018f82  lea     rdx, [rsp+1560h+var_1520]; struct _SYSTEMTIME *
0x180018f87  call    ?InstallDateToSystemTime@@YAHKPEAU_SYSTEMTIME@@@Z; InstallDateToSystemTime(ulong,_SYSTEMTIME *)
0x180018f8c  test    eax, eax
0x180018f8e  jz      short loc_180018FB2
0x180018f90  movaps  xmm0, xmmword ptr [rsp+1560h+var_1520.wYear]
0x180018f95  lea     r8, [rsp+1560h+var_1520]
0x180018f9a  mov     rcx, [rsp+1560h+ppv]
0x180018f9f  movdqa  xmmword ptr [rsp+1560h+var_1520.wYear], xmm0
0x180018fa5  mov     dword ptr [rsp+1560h+var_1540], 103h
0x180018fad  call    IPropertyStore_SetSystemTime
0x180018fb2  mov     rax, [r14+8]
0x180018fb6  lea     r9, [rsp+1560h+pvar]
0x180018fbb  mov     rdi, [rsp+1560h+ppv]
0x180018fc0  lea     rcx, [rsp+1560h+var_1520]
0x180018fc5  mov     qword ptr [rsp+1560h+var_1520.wYear], rax
0x180018fca  xorps   xmm0, xmm0
0x180018fcd  xor     eax, eax
0x180018fcf  mov     r8d, 101h
0x180018fd5  mov     [rsp+1560h+var_1500], rax
0x180018fda  movups  xmmword ptr [rsp+1560h+pvar], xmm0
0x180018fdf  call    InitPropVariantFromFileTimeEx
0x180018fe4  test    eax, eax
0x180018fe6  js      short loc_18001900E
0x180018fe8  mov     rax, [rdi]
0x180018feb  lea     r8, [rsp+1560h+pvar]
0x180018ff0  lea     rdx, PKEY_Software_DateLastUsed
0x180018ff7  mov     rcx, rdi
0x180018ffa  mov     rax, [rax+30h]
0x180018ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019003  lea     rcx, [rsp+1560h+pvar]; pvar
0x180019008  call    cs:__imp_PropVariantClear
0x18001900e  mov     r8, [rbx+70h]
0x180019012  xor     edi, edi
0x180019014  test    r8, r8
0x180019017  jz      short loc_18001902A
0x180019019  mov     rcx, [rsp+1560h+ppv]
0x18001901e  lea     rdx, PKEY_Software_SupportContactName
0x180019025  call    IPropertyStore_SetString
0x18001902a  mov     r8, [rbx+78h]
0x18001902e  test    r8, r8
0x180019031  jz      short loc_180019044
0x180019033  mov     rcx, [rsp+1560h+ppv]
0x180019038  lea     rdx, PKEY_Software_Comments
0x18001903f  call    IPropertyStore_SetString
0x180019044  movups  xmm0, xmmword ptr cs:aAIdWsWsA; "<a id=\"%ws\">%ws</a>"
0x18001904b  mov     rax, [rbx+40h]
0x18001904f  movups  xmm1, xmmword ptr cs:aAIdWsWsA+10h; "ws\">%ws</a>"
0x180019056  movups  xmmword ptr [rbp+1460h+var_10C0], xmm0
0x18001905d  movsd   xmm0, qword ptr cs:aAIdWsWsA+20h; "/a>"
0x180019065  movsd   [rbp+1460h+var_10A0], xmm0
0x18001906d  movups  [rbp+1460h+var_10B0], xmm1
0x180019074  test    rax, rax
0x180019077  jz      short loc_1800190D1
0x180019079  lea     r9, aLaunchsupportu; "launchsupporturl"
0x180019080  mov     [rsp+1560h+var_1540], rax
0x180019085  lea     r8, [rbp+1460h+var_10C0]; unsigned __int16 *
0x18001908c  mov     edx, 824h; unsigned __int64
0x180019091  lea     rcx, [rbp+1460h+var_1090]; unsigned __int16 *
0x180019098  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001909d  test    eax, eax
0x18001909f  js      short loc_1800190D1
0x1800190a1  mov     rcx, [rsp+1560h+ppv]
0x1800190a6  lea     r8, [rbp+1460h+var_1090]
0x1800190ad  lea     rdx, PKEY_Software_HelpLink
0x1800190b4  call    IPropertyStore_SetString
0x1800190b9  mov     rcx, [rsp+1560h+ppv]
0x1800190be  lea     r8, [rbp+1460h+var_1090]
0x1800190c5  lea     rdx, PKEY_Software_SupportUrl
0x1800190cc  call    IPropertyStore_SetString
0x1800190d1  mov     rax, [rbx+88h]
0x1800190d8  test    rax, rax
0x1800190db  jz      short loc_180019135
0x1800190dd  lea     r9, aLaunchreadmeur; "launchreadmeurl"
0x1800190e4  mov     [rsp+1560h+var_1540], rax
0x1800190e9  lea     r8, [rbp+1460h+var_10C0]; unsigned __int16 *
0x1800190f0  mov     edx, 824h; unsigned __int64
0x1800190f5  lea     rcx, [rbp+1460h+var_1090]; unsigned __int16 *
0x1800190fc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019101  test    eax, eax
0x180019103  js      short loc_180019135
0x180019105  mov     rcx, [rsp+1560h+ppv]
0x18001910a  lea     r8, [rbp+1460h+var_1090]
0x180019111  lea     rdx, PKEY_Software_HelpLink
0x180019118  call    IPropertyStore_SetString
0x18001911d  mov     rcx, [rsp+1560h+ppv]
0x180019122  lea     r8, [rbp+1460h+var_1090]
0x180019129  lea     rdx, PKEY_Software_ReadMeUrl
0x180019130  call    IPropertyStore_SetString
0x180019135  mov     rax, [rbx+90h]
0x18001913c  test    rax, rax
0x18001913f  jz      short loc_180019199
0x180019141  lea     r9, aLaunchupdateur; "launchupdateurl"
0x180019148  mov     [rsp+1560h+var_1540], rax
0x18001914d  lea     r8, [rbp+1460h+var_10C0]; unsigned __int16 *
0x180019154  mov     edx, 824h; unsigned __int64
0x180019159  lea     rcx, [rbp+1460h+var_1090]; unsigned __int16 *
0x180019160  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019165  test    eax, eax
0x180019167  js      short loc_180019199
0x180019169  mov     rcx, [rsp+1560h+ppv]
0x18001916e  lea     r8, [rbp+1460h+var_1090]
0x180019175  lea     rdx, PKEY_Software_HelpLink
0x18001917c  call    IPropertyStore_SetString
0x180019181  mov     rcx, [rsp+1560h+ppv]
0x180019186  lea     r8, [rbp+1460h+var_1090]
0x18001918d  lea     rdx, PKEY_Software_UpdateInfoUrl
0x180019194  call    IPropertyStore_SetString
0x180019199  mov     rax, [rbx+50h]
0x18001919d  test    rax, rax
0x1800191a0  jz      short loc_1800191E2
0x1800191a2  lea     r9, aLaunchhelpurl; "launchhelpurl"
0x1800191a9  mov     [rsp+1560h+var_1540], rax
0x1800191ae  lea     r8, [rbp+1460h+var_10C0]; unsigned __int16 *
0x1800191b5  mov     edx, 824h; unsigned __int64
0x1800191ba  lea     rcx, [rbp+1460h+var_1090]; unsigned __int16 *
0x1800191c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800191c6  test    eax, eax
0x1800191c8  js      short loc_1800191E2
0x1800191ca  mov     rcx, [rsp+1560h+ppv]
0x1800191cf  lea     r8, [rbp+1460h+var_1090]
0x1800191d6  lea     rdx, PKEY_Software_HelpLink
0x1800191dd  call    IPropertyStore_SetString
0x1800191e2  mov     rax, [r14]
0x1800191e5  test    rax, rax
0x1800191e8  jz      short loc_180019225
0x1800191ea  mov     rcx, [rsp+1560h+ppv]
0x1800191ef  lea     r8, [rsp+1560h+pvar]
0x1800191f4  xor     edx, edx
0x1800191f6  xorps   xmm0, xmm0
0x1800191f9  movups  xmmword ptr [rsp+1560h+pvar], xmm0
0x1800191fe  mov     [rsp+1560h+pvar+8], rax
0x180019203  mov     rax, [rcx]
0x180019206  mov     [rsp+1560h+var_1500], rdx
0x18001920b  mov     edx, 15h
0x180019210  mov     word ptr [rsp+1560h+pvar], dx
0x180019215  lea     rdx, PKEY_Size
0x18001921c  mov     rax, [rax+30h]
0x180019220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019225  mov     r8d, [r14+10h]
0x180019229  test    r8d, r8d
0x18001922c  js      short loc_18001923F
0x18001922e  mov     rcx, [rsp+1560h+ppv]
0x180019233  lea     rdx, PKEY_Software_TimesUsed
0x18001923a  call    IPropertyStore_SetUInt32
0x18001923f  mov     r8, [r15+18h]
0x180019243  test    r8, r8
0x180019246  jz      short loc_180019259
0x180019248  mov     rcx, [rsp+1560h+ppv]
0x18001924d  lea     rdx, PKEY_Software_ParentName
0x180019254  call    IPropertyStore_SetString
0x180019259  xor     edx, edx; Val
0x18001925b  lea     rcx, [rsp+1560h+var_14E4]; void *
0x180019260  mov     r8d, 418h; Size
0x180019266  call    memset_0
0x18001926b  mov     eax, [rbp+1460h+arg_28]
0x180019271  lea     rcx, [rsp+1560h+var_14E4]
0x180019276  mov     [rsp+1560h+var_14F0], eax
0x18001927a  mov     eax, 8
0x18001927f  lea     edx, [rax+78h]
0x180019282  movups  xmm0, xmmword ptr [rsi]
0x180019285  movups  xmm1, xmmword ptr [rsi+10h]
0x180019289  movups  xmmword ptr [rcx], xmm0
0x18001928c  movups  xmm0, xmmword ptr [rsi+20h]
0x180019290  movups  xmmword ptr [rcx+10h], xmm1
0x180019294  movups  xmm1, xmmword ptr [rsi+30h]
0x180019298  movups  xmmword ptr [rcx+20h], xmm0
0x18001929c  movups  xmm0, xmmword ptr [rsi+40h]
0x1800192a0  movups  xmmword ptr [rcx+30h], xmm1
0x1800192a4  movups  xmm1, xmmword ptr [rsi+50h]
0x1800192a8  movups  xmmword ptr [rcx+40h], xmm0
0x1800192ac  movups  xmm0, xmmword ptr [rsi+60h]
0x1800192b0  movups  xmmword ptr [rcx+50h], xmm1
0x1800192b4  movups  xmm1, xmmword ptr [rsi+70h]
0x1800192b8  add     rsi, rdx
0x1800192bb  movups  xmmword ptr [rcx+60h], xmm0
0x1800192bf  movups  xmmword ptr [rcx+70h], xmm1
0x1800192c3  add     rcx, rdx
  ... truncated ...
```
