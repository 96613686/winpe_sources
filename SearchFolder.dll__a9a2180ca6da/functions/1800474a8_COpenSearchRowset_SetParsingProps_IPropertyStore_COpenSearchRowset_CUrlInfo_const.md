# COpenSearchRowset::_SetParsingProps(IPropertyStore *,COpenSearchRowset::CUrlInfo const &)

- ea: `0x1800474a8`
- end: `0x180047834`
- name: `?_SetParsingProps@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBUCUrlInfo@1@@Z`
- size: `908`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, struct IPropertyStore *, const struct COpenSearchRowset::CUrlInfo *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043b28`
- `0x180043dd4`

## callees

- `0x180005460`
- `0x180006900`
- `0x18000ebd0`
- `0x18000ecc4`
- `0x18000eec0`
- `0x180041520`
- `0x180041618`
- `0x180044cec`
- `0x1800474a8`
- `0x18004783c`
- `0x18004ab34`
- `0x18004f6f0`
- `0x18004faa0`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x1800475d8`
- `SHLWAPI!PathFindExtensionW` at `0x1800475d8`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800475e6`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800475e6`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_SetParsingProps(
        COpenSearchRowset *this,
        struct IPropertyStore *a2,
        const wchar_t **a3)
{
  const wchar_t *v4; // r14
  const wchar_t *v6; // r8
  int v7; // ebx
  const wchar_t *v8; // r8
  COpenSearchRowset *v9; // rcx
  const wchar_t *v10; // r8
  COpenSearchRowset *v11; // rcx
  const WCHAR *v12; // rcx
  const WCHAR *ExtensionW; // rax
  unsigned __int16 *v14; // r8
  unsigned int v15; // r11d
  const wchar_t *v16; // r8
  const unsigned __int16 *v17; // r9
  const unsigned __int16 *v18; // r9
  int v19; // eax
  unsigned __int16 **v20; // r14
  const unsigned __int16 *v21; // r9
  unsigned __int16 *v22; // r9
  unsigned __int16 *v23; // r9
  void *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v26; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszStr1; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v28[2088]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = &psz;
  v6 = &psz;
  if ( *a3 )
    v6 = *a3;
  v7 = IPropertyStore_SetString(a2, &PKEY_ItemUrl, v6);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v8 = &psz;
  if ( a3[2] )
    v8 = a3[2];
  v7 = IPropertyStore_SetString(a2, &PKEY_ItemPathDisplay, v8);
  if ( v7 < 0 )
    return (unsigned int)v7;
  if ( *((_DWORD *)a3 + 16) != 9 )
  {
    if ( *a3 )
      v4 = *a3;
    v7 = IPropertyStore_SetString(a2, &PKEY_ParsingPath, v4);
    if ( v7 < 0 )
      return (unsigned int)v7;
    if ( COpenSearchRowset::_IsPropertyPresent(v11, a2, &PKEY_FileName) )
      goto LABEL_35;
    pszStr1 = 0;
    if ( (int)IPropertyStore_GetString(a2, &PKEY_FileExtension, &pszStr1) < 0 )
    {
LABEL_33:
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pszStr1);
LABEL_34:
      if ( v7 < 0 )
        return (unsigned int)v7;
      goto LABEL_35;
    }
    v12 = a3[5];
    if ( v12 )
    {
      ExtensionW = PathFindExtensionW(v12);
      if ( !StrCmpICW(pszStr1, ExtensionW) )
      {
        v7 = StringCchCopyW(v28, 0x104u, a3[5]);
        goto LABEL_28;
      }
    }
    v26 = 0;
    if ( (int)IPropertyStore_GetString(a2, &PKEY_Title, &v26) < 0 || (v14 = v26, !*v26) )
    {
      v7 = TResourceStringAllocCopyEx<unsigned short *>(
             g_hinst,
             38304,
             (__int64)v14,
             (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
             v25,
             (char *)&v26);
      if ( v7 < 0 )
      {
LABEL_27:
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v26);
LABEL_28:
        if ( v7 < 0 )
        {
          if ( v7 == -2147024774 )
            v7 = 0;
        }
        else if ( (unsigned int)PathMakeValidNameW(v28) )
        {
          v7 = IPropertyStore_SetString(a2, &PKEY_FileName, v28);
        }
        goto LABEL_33;
      }
      v14 = v26;
    }
    v7 = StringCchCopyW(v28, 0x104u, v14);
    if ( v7 >= 0 )
      v7 = StringCchCatW(v28, v15, pszStr1);
    goto LABEL_27;
  }
  if ( *a3 )
    v4 = *a3;
  v7 = IPropertyStore_SetString(a2, &PKEY_ParsingPath, v4);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v10 = a3[5];
  if ( v10 )
  {
    v7 = IPropertyStore_SetString(a2, &PKEY_FileName, v10);
    goto LABEL_34;
  }
LABEL_35:
  v16 = a3[5];
  if ( v16 )
  {
    v7 = IPropertyStore_SetString(a2, &PKEY_ParsingName, v16);
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  v17 = a3[6];
  if ( v17 )
  {
    v7 = COpenSearchRowset::_SetPropertyIfEmpty(v9, a2, &PKEY_ItemFolderPathDisplay, v17);
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  v18 = a3[3];
  if ( v18 )
  {
    v19 = COpenSearchRowset::_SetPropertyIfEmpty(v9, a2, &PKEY_ItemFolderNameDisplay, v18);
    v20 = (unsigned __int16 **)(a3 + 7);
  }
  else
  {
    v20 = (unsigned __int16 **)(a3 + 7);
    v21 = a3[7];
    if ( !v21 )
      goto LABEL_44;
    v19 = COpenSearchRowset::_SetPropertyIfEmpty(v9, a2, &PKEY_ItemFolderNameDisplay, v21);
  }
  v7 = v19;
LABEL_44:
  if ( v7 < 0 )
    return (unsigned int)v7;
  if ( a3[5] && *v20 )
  {
    v7 = StringCchPrintfW(v28, 0x824u, L"%s (%s)");
    if ( v7 < 0 )
      return (unsigned int)v7;
    v22 = v28;
  }
  else
  {
    v22 = *v20;
    if ( !*v20 )
      goto LABEL_51;
  }
  v7 = COpenSearchRowset::_SetPropertyIfEmpty(v9, a2, &PKEY_ItemPathDisplayNarrow, v22);
LABEL_51:
  if ( v7 >= 0 )
  {
    if ( a3[4] && a3[3] )
    {
      v7 = StringCchPrintfW(v28, 0x824u, L"%s (%s)");
      if ( v7 >= 0 )
      {
        v23 = v28;
        return (unsigned int)COpenSearchRowset::_SetPropertyIfEmpty(v9, a2, &PKEY_ItemFolderPathDisplayNarrow, v23);
      }
    }
    else
    {
      v23 = *v20;
      if ( *v20 )
        return (unsigned int)COpenSearchRowset::_SetPropertyIfEmpty(v9, a2, &PKEY_ItemFolderPathDisplayNarrow, v23);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800474a8  mov     [rsp-8+arg_0], rbx
0x1800474ad  push    rbp
0x1800474ae  push    rsi
0x1800474af  push    rdi
0x1800474b0  push    r14
0x1800474b2  push    r15
0x1800474b4  lea     rbp, [rsp-0FA0h]
0x1800474bc  mov     eax, 10A0h
0x1800474c1  call    _alloca_probe
0x1800474c6  sub     rsp, rax
0x1800474c9  mov     rax, cs:__security_cookie
0x1800474d0  xor     rax, rsp
0x1800474d3  mov     [rbp+0FC0h+var_30], rax
0x1800474da  mov     rdi, r8
0x1800474dd  lea     r14, psz
0x1800474e4  mov     rsi, rdx
0x1800474e7  xor     r15d, r15d
0x1800474ea  mov     r8, r14
0x1800474ed  lea     rdx, PKEY_ItemUrl
0x1800474f4  mov     rcx, rsi
0x1800474f7  cmp     [rdi], r15
0x1800474fa  cmovnz  r8, [rdi]
0x1800474fe  call    IPropertyStore_SetString
0x180047503  mov     ebx, eax
0x180047505  test    eax, eax
0x180047507  js      loc_18004780C
0x18004750d  cmp     [rdi+10h], r15
0x180047511  lea     rdx, PKEY_ItemPathDisplay
0x180047518  mov     r8, r14
0x18004751b  mov     rcx, rsi
0x18004751e  cmovnz  r8, [rdi+10h]
0x180047523  call    IPropertyStore_SetString
0x180047528  mov     ebx, eax
0x18004752a  test    eax, eax
0x18004752c  js      loc_18004780C
0x180047532  cmp     dword ptr [rdi+40h], 9
0x180047536  lea     rdx, PKEY_ParsingPath
0x18004753d  mov     rcx, rsi
0x180047540  jnz     short loc_18004757E
0x180047542  cmp     [rdi], r15
0x180047545  cmovnz  r14, [rdi]
0x180047549  mov     r8, r14
0x18004754c  call    IPropertyStore_SetString
0x180047551  mov     ebx, eax
0x180047553  test    eax, eax
0x180047555  js      loc_18004780C
0x18004755b  mov     r8, [rdi+28h]
0x18004755f  test    r8, r8
0x180047562  jz      loc_1800476DC
0x180047568  lea     rdx, PKEY_FileName
0x18004756f  mov     rcx, rsi
0x180047572  call    IPropertyStore_SetString
0x180047577  mov     ebx, eax
0x180047579  jmp     loc_1800476D4
0x18004757e  cmp     [rdi], r15
0x180047581  cmovnz  r14, [rdi]
0x180047585  mov     r8, r14
0x180047588  call    IPropertyStore_SetString
0x18004758d  mov     ebx, eax
0x18004758f  test    eax, eax
0x180047591  js      loc_18004780C
0x180047597  lea     r8, PKEY_FileName; struct _tagpropertykey *
0x18004759e  mov     rdx, rsi; struct IPropertyStore *
0x1800475a1  call    ?_IsPropertyPresent@COpenSearchRowset@@AEAAHPEAUIPropertyStore@@AEBU_tagpropertykey@@@Z; COpenSearchRowset::_IsPropertyPresent(IPropertyStore *,_tagpropertykey const &)
0x1800475a6  test    eax, eax
0x1800475a8  jnz     loc_1800476DC
0x1800475ae  lea     r8, [rsp+10C0h+pszStr1]
0x1800475b3  mov     [rsp+10C0h+pszStr1], r15
0x1800475b8  lea     rdx, PKEY_FileExtension
0x1800475bf  mov     rcx, rsi
0x1800475c2  call    IPropertyStore_GetString
0x1800475c7  test    eax, eax
0x1800475c9  js      loc_1800476CA
0x1800475cf  mov     rcx, [rdi+28h]; pszPath
0x1800475d3  test    rcx, rcx
0x1800475d6  jz      short loc_18004760A
0x1800475d8  call    cs:__imp_PathFindExtensionW
0x1800475de  mov     rcx, [rsp+10C0h+pszStr1]; pszStr1
0x1800475e3  mov     rdx, rax; pszStr2
0x1800475e6  call    cs:__imp_StrCmpICW
0x1800475ec  test    eax, eax
0x1800475ee  jnz     short loc_18004760A
0x1800475f0  mov     r8, [rdi+28h]; unsigned __int16 *
0x1800475f4  lea     rcx, [rsp+10C0h+var_1080]; unsigned __int16 *
0x1800475f9  mov     edx, 104h; unsigned __int64
0x1800475fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180047603  mov     ebx, eax
0x180047605  jmp     loc_180047696
0x18004760a  lea     r8, [rsp+10C0h+var_1090]
0x18004760f  mov     [rsp+10C0h+var_1090], r15
0x180047614  lea     rdx, PKEY_Title
0x18004761b  mov     rcx, rsi
0x18004761e  call    IPropertyStore_GetString
0x180047623  test    eax, eax
0x180047625  js      short loc_180047632
0x180047627  mov     r8, [rsp+10C0h+var_1090]; int
0x18004762c  cmp     [r8], r15w
0x180047630  jnz     short loc_18004765F
0x180047632  mov     rcx, cs:g_hinst; int
0x180047639  lea     rax, [rsp+10C0h+var_1090]
0x18004763e  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x180047645  mov     [rsp+10C0h+var_1098], rax; void *
0x18004764a  mov     edx, 95A0h; int
0x18004764f  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180047654  mov     ebx, eax
0x180047656  test    eax, eax
0x180047658  js      short loc_18004768C
0x18004765a  mov     r8, [rsp+10C0h+var_1090]; unsigned __int16 *
0x18004765f  mov     r11d, 104h
0x180047665  lea     rcx, [rsp+10C0h+var_1080]; unsigned __int16 *
0x18004766a  mov     edx, r11d; unsigned __int64
0x18004766d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180047672  mov     ebx, eax
0x180047674  test    eax, eax
0x180047676  js      short loc_18004768C
0x180047678  mov     r8, [rsp+10C0h+pszStr1]; unsigned __int16 *
0x18004767d  lea     rcx, [rsp+10C0h+var_1080]; unsigned __int16 *
0x180047682  mov     edx, r11d; unsigned __int64
0x180047685  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004768a  mov     ebx, eax
0x18004768c  lea     rcx, [rsp+10C0h+var_1090]; void *
0x180047691  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180047696  test    ebx, ebx
0x180047698  js      short loc_1800476C0
0x18004769a  lea     rcx, [rsp+10C0h+var_1080]; unsigned __int16 *
0x18004769f  call    PathMakeValidNameW
0x1800476a4  test    eax, eax
0x1800476a6  jz      short loc_1800476CA
0x1800476a8  lea     r8, [rsp+10C0h+var_1080]
0x1800476ad  mov     rcx, rsi
0x1800476b0  lea     rdx, PKEY_FileName
0x1800476b7  call    IPropertyStore_SetString
0x1800476bc  mov     ebx, eax
0x1800476be  jmp     short loc_1800476CA
0x1800476c0  cmp     ebx, 8007007Ah
0x1800476c6  cmovz   ebx, r15d
0x1800476ca  lea     rcx, [rsp+10C0h+pszStr1]; void *
0x1800476cf  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800476d4  test    ebx, ebx
0x1800476d6  js      loc_18004780C
0x1800476dc  mov     r8, [rdi+28h]
0x1800476e0  test    r8, r8
0x1800476e3  jz      short loc_1800476FE
0x1800476e5  lea     rdx, PKEY_ParsingName
0x1800476ec  mov     rcx, rsi
0x1800476ef  call    IPropertyStore_SetString
0x1800476f4  mov     ebx, eax
0x1800476f6  test    eax, eax
0x1800476f8  js      loc_18004780C
0x1800476fe  mov     r9, [rdi+30h]; unsigned __int16 *
0x180047702  test    r9, r9
0x180047705  jz      short loc_180047720
0x180047707  lea     r8, PKEY_ItemFolderPathDisplay; struct _tagpropertykey *
0x18004770e  mov     rdx, rsi; struct IPropertyStore *
0x180047711  call    ?_SetPropertyIfEmpty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; COpenSearchRowset::_SetPropertyIfEmpty(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x180047716  mov     ebx, eax
0x180047718  test    eax, eax
0x18004771a  js      loc_18004780C
0x180047720  mov     r9, [rdi+18h]; unsigned __int16 *
0x180047724  test    r9, r9
0x180047727  jz      short loc_18004773E
0x180047729  lea     r8, PKEY_ItemFolderNameDisplay; struct _tagpropertykey *
0x180047730  mov     rdx, rsi; struct IPropertyStore *
0x180047733  call    ?_SetPropertyIfEmpty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; COpenSearchRowset::_SetPropertyIfEmpty(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x180047738  lea     r14, [rdi+38h]
0x18004773c  jmp     short loc_180047759
0x18004773e  lea     r14, [rdi+38h]
0x180047742  mov     r9, [r14]; unsigned __int16 *
0x180047745  test    r9, r9
0x180047748  jz      short loc_18004775B
0x18004774a  lea     r8, PKEY_ItemFolderNameDisplay; struct _tagpropertykey *
0x180047751  mov     rdx, rsi; struct IPropertyStore *
0x180047754  call    ?_SetPropertyIfEmpty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; COpenSearchRowset::_SetPropertyIfEmpty(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x180047759  mov     ebx, eax
0x18004775b  test    ebx, ebx
0x18004775d  js      loc_18004780C
0x180047763  mov     r9, [rdi+28h]
0x180047767  test    r9, r9
0x18004776a  jz      short loc_18004779C
0x18004776c  mov     rax, [r14]
0x18004776f  test    rax, rax
0x180047772  jz      short loc_18004779C
0x180047774  lea     r8, aSS; "%s (%s)"
0x18004777b  mov     [rsp+10C0h+var_10A0], rax
0x180047780  mov     edx, 824h; unsigned __int64
0x180047785  lea     rcx, [rsp+10C0h+var_1080]; unsigned __int16 *
0x18004778a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004778f  mov     ebx, eax
0x180047791  test    eax, eax
0x180047793  js      short loc_18004780C
0x180047795  lea     r9, [rsp+10C0h+var_1080]
0x18004779a  jmp     short loc_1800477A4
0x18004779c  mov     r9, [r14]; unsigned __int16 *
0x18004779f  test    r9, r9
0x1800477a2  jz      short loc_1800477B5
0x1800477a4  lea     r8, PKEY_ItemPathDisplayNarrow; struct _tagpropertykey *
0x1800477ab  mov     rdx, rsi; struct IPropertyStore *
0x1800477ae  call    ?_SetPropertyIfEmpty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; COpenSearchRowset::_SetPropertyIfEmpty(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x1800477b3  mov     ebx, eax
0x1800477b5  test    ebx, ebx
0x1800477b7  js      short loc_18004780C
0x1800477b9  mov     rax, [rdi+20h]
0x1800477bd  test    rax, rax
0x1800477c0  jz      short loc_1800477F3
0x1800477c2  mov     r9, [rdi+18h]
0x1800477c6  test    r9, r9
0x1800477c9  jz      short loc_1800477F3
0x1800477cb  lea     r8, aSS; "%s (%s)"
0x1800477d2  mov     [rsp+10C0h+var_10A0], rax
0x1800477d7  mov     edx, 824h; unsigned __int64
0x1800477dc  lea     rcx, [rsp+10C0h+var_1080]; unsigned __int16 *
0x1800477e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800477e6  mov     ebx, eax
0x1800477e8  test    eax, eax
0x1800477ea  js      short loc_18004780C
0x1800477ec  lea     r9, [rsp+10C0h+var_1080]
0x1800477f1  jmp     short loc_1800477FB
0x1800477f3  mov     r9, [r14]; unsigned __int16 *
0x1800477f6  test    r9, r9
0x1800477f9  jz      short loc_18004780C
0x1800477fb  lea     r8, PKEY_ItemFolderPathDisplayNarrow; struct _tagpropertykey *
0x180047802  mov     rdx, rsi; struct IPropertyStore *
0x180047805  call    ?_SetPropertyIfEmpty@COpenSearchRowset@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEBG@Z; COpenSearchRowset::_SetPropertyIfEmpty(IPropertyStore *,_tagpropertykey const &,ushort const *)
0x18004780a  mov     ebx, eax
0x18004780c  mov     eax, ebx
0x18004780e  mov     rcx, [rbp+0FC0h+var_30]
0x180047815  xor     rcx, rsp; StackCookie
0x180047818  call    __security_check_cookie
0x18004781d  mov     rbx, [rsp+10C0h+arg_0]
0x180047825  add     rsp, 10A0h
0x18004782c  pop     r15
0x18004782e  pop     r14
0x180047830  pop     rdi
0x180047831  pop     rsi
0x180047832  pop     rbp
0x180047833  retn
```
