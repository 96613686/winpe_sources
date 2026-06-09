# SaveTopView(IUnknown *,IShellItem *,ushort const *)

- ea: `0x180091ea8`
- end: `0x1800922b2`
- name: `?SaveTopView@@YAJPEAUIUnknown@@PEAUIShellItem@@PEBG@Z`
- size: `1034`
- prototype: `int(struct IUnknown *, struct IShellItem *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180091aa8`

## callees

- `0x180091ea8`
- `0x1800922b8`
- `0x18013f7d0`
- `0x1801912c8`
- `0x180210010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x180092051`
- `SHELL32!SHGetIDListFromObject` at `0x180092051`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1800921ff`
- `SHELL32!__imp_SHCLSIDFromString` at `0x180092212`
- `SHELL32!__imp_SHCLSIDFromString` at `0x1800921ff`
- `SHELL32!__imp_SHCLSIDFromString` at `0x180092212`
- `SHELL32!__imp_ILFree` at `0x180092260`
- `SHELL32!__imp_ILFree` at `0x180092260`
- `SHELL32!__imp_SHGetFolderTypeDescription` at `0x180091f82`
- `SHELL32!__imp_SHGetFolderTypeDescription` at `0x180091f82`
- `SHELL32!__imp_SHGetTopViewDescription` at `0x18009214d`
- `SHELL32!__imp_SHGetTopViewDescription` at `0x18009214d`
- `SHELL32!__imp_SaveTopViewSettings` at `0x180091fd3`
- `SHELL32!__imp_SaveTopViewSettings` at `0x180091fd3`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800920e1`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800920f2`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800920e1`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800920f2`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800921ce`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800921e1`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800921ce`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800921e1`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x180092089`
- `SHLWAPI!__imp_SHGetViewStatePropertyBag` at `0x180092089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092244`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800920b4`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800920cb`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800920b4`
- `PROPSYS!PSPropertyBag_ReadStrAlloc` at `0x1800920cb`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180092191`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180092191`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180092108`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180092128`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180092108`
- `PROPSYS!PSPropertyBag_WriteStr` at `0x180092128`

## pseudocode

```c
__int64 __fastcall SaveTopView(struct IUnknown *a1, struct IShellItem *a2, const unsigned __int16 *a3)
{
  HRESULT v5; // ebx
  PWSTR v7; // rcx
  const unsigned __int16 *v8; // rdx
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh] BYREF
  IPropertyBag *propBag; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v13; // [rsp+44h] [rbp-BCh] BYREF
  PWSTR value; // [rsp+48h] [rbp-B8h] BYREF
  PWSTR v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  struct ITopViewAwareItem *v17; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  LPITEMIDLIST ppidl; // [rsp+70h] [rbp-90h] BYREF
  IUnknown *punk; // [rsp+78h] [rbp-88h] BYREF
  CLSID v21; // [rsp+80h] [rbp-80h] BYREF
  CLSID v22; // [rsp+90h] [rbp-70h] BYREF
  CLSID pclsid; // [rsp+A0h] [rbp-60h] BYREF
  CLSID v24; // [rsp+B0h] [rbp-50h] BYREF
  CLSID v25; // [rsp+C0h] [rbp-40h] BYREF
  CLSID v26; // [rsp+D0h] [rbp-30h]
  WCHAR pszStr2[40]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v28[40]; // [rsp+130h] [rbp+30h] BYREF

  v17 = 0;
  if ( (unsigned int)IsFilteredSet(a2) )
    return (unsigned int)-2147467259;
  v5 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, struct ITopViewAwareItem **))a2->lpVtbl->BindToHandler)(
         a2,
         0,
         &BHID_SFViewObject,
         &GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb,
         &v17);
  if ( v5 >= 0 )
  {
    v21 = 0;
    v22 = 0;
    v5 = (*(__int64 (__fastcall **)(struct ITopViewAwareItem *, CLSID *))(*(_QWORD *)v17 + 24LL))(v17, &v21);
    if ( v5 < 0
      || (v16 = 0, v5 = SHGetFolderTypeDescription(&v21, &GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80, &v16), v5 < 0) )
    {
LABEL_36:
      (*(void (__fastcall **)(struct ITopViewAwareItem *))(*(_QWORD *)v17 + 16LL))(v17);
      return (unsigned int)v5;
    }
    v10 = 0;
    v25 = v21;
    v9 = 0;
    v26 = v22;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 104LL))(v16, &v9) >= 0 && v9 == 1 )
      SaveTopViewSettings(a1, &v10);
    v12 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 96LL))(v16, &v12) >= 0 && v12 == 1 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, CLSID *))(*(_QWORD *)v16 + 168LL))(v16, &v22);
      goto LABEL_34;
    }
    punk = 0;
    v5 = (*(__int64 (__fastcall **)(struct ITopViewAwareItem *, IUnknown **))(*(_QWORD *)v17 + 48LL))(v17, &punk);
    if ( v5 < 0 )
    {
LABEL_34:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v10 )
        ClearViewSettingsForTopView(v17, v8, (const struct TOPVIEWKEY *)&v25);
      goto LABEL_36;
    }
    ppidl = 0;
    v5 = SHGetIDListFromObject(punk, &ppidl);
    if ( v5 < 0 )
    {
LABEL_33:
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      goto LABEL_34;
    }
    propBag = 0;
    v5 = SHGetViewStatePropertyBag(ppidl, L"Shell", 5u, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, (void **)&propBag);
    if ( v5 < 0 )
    {
LABEL_32:
      ILFree(ppidl);
      goto LABEL_33;
    }
    value = 0;
    v15 = 0;
    PSPropertyBag_ReadStrAlloc(propBag, L"TV_FolderType", &value);
    PSPropertyBag_ReadStrAlloc(propBag, L"TV_TopViewID", &v15);
    SHStringFromGUIDW(&v21, pszStr2, 39);
    SHStringFromGUIDW(&v22, v28, 39);
    v5 = PSPropertyBag_WriteStr(propBag, L"TV_FolderType", pszStr2);
    if ( v5 >= 0 )
    {
      v5 = PSPropertyBag_WriteStr(propBag, L"TV_TopViewID", v28);
      if ( v5 >= 0 )
      {
        v18 = 0;
        v5 = SHGetTopViewDescription(&v21, &GUID_fe812157_522c_46cb_8d53_6efe3dce2c46, &v18);
        if ( v5 >= 0 )
        {
          v13 = 0;
          v5 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v18 + 176LL))(v18, &v13);
          if ( v5 >= 0 )
            v5 = PSPropertyBag_WriteDWORD(propBag, L"TV_TopViewVersion", v13);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          if ( v5 >= 0 && v9 == 1 )
          {
            v7 = value;
            if ( !value || !v15 )
              goto LABEL_31;
            if ( StrCmpICW(value, pszStr2) || StrCmpICW(v15, v28) )
            {
              pclsid = 0;
              v24 = 0;
              if ( SHCLSIDFromString(value, &pclsid) >= 0 && SHCLSIDFromString(v15, &v24) >= 0 )
              {
                v10 = 1;
                v25 = pclsid;
                v26 = v24;
              }
            }
          }
        }
      }
    }
    v7 = value;
LABEL_31:
    CoTaskMemFree(v7);
    CoTaskMemFree(v15);
    ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
    goto LABEL_32;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180091ea8  mov     [rsp-8+arg_10], rbx
0x180091ead  push    rbp
0x180091eae  push    rsi
0x180091eaf  push    rdi
0x180091eb0  lea     rbp, [rsp-90h]
0x180091eb8  sub     rsp, 190h
0x180091ebf  mov     rax, cs:__security_cookie
0x180091ec6  xor     rax, rsp
0x180091ec9  mov     [rbp+0A0h+var_20], rax
0x180091ed0  mov     rdi, rcx
0x180091ed3  xor     esi, esi
0x180091ed5  mov     rcx, rdx; struct IShellItem *
0x180091ed8  mov     [rsp+1A0h+var_140], rsi
0x180091edd  mov     rbx, rdx
0x180091ee0  call    ?IsFilteredSet@@YAHPEAUIShellItem@@@Z; IsFilteredSet(IShellItem *)
0x180091ee5  test    eax, eax
0x180091ee7  jnz     short loc_180091F3C
0x180091ee9  mov     rax, [rbx]
0x180091eec  lea     rcx, [rsp+1A0h+var_140]
0x180091ef1  mov     [rsp+1A0h+ppv], rcx
0x180091ef6  lea     r9, _GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb
0x180091efd  lea     r8, BHID_SFViewObject
0x180091f04  xor     edx, edx
0x180091f06  mov     rcx, rbx
0x180091f09  mov     rax, [rax+18h]
0x180091f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091f12  mov     ebx, eax
0x180091f14  test    eax, eax
0x180091f16  jns     short loc_180091F43
0x180091f18  mov     eax, ebx
0x180091f1a  mov     rcx, [rbp+0A0h+var_20]
0x180091f21  xor     rcx, rsp; StackCookie
0x180091f24  call    __security_check_cookie
0x180091f29  mov     rbx, [rsp+1A0h+arg_10]
0x180091f31  add     rsp, 190h
0x180091f38  pop     rdi
0x180091f39  pop     rsi
0x180091f3a  pop     rbp
0x180091f3b  retn
0x180091f3c  mov     ebx, 80004005h
0x180091f41  jmp     short loc_180091F18
0x180091f43  mov     rcx, [rsp+1A0h+var_140]
0x180091f48  lea     rdx, [rbp+0A0h+var_120]
0x180091f4c  xorps   xmm0, xmm0
0x180091f4f  movups  [rbp+0A0h+var_120], xmm0
0x180091f53  movups  [rbp+0A0h+var_110], xmm0
0x180091f57  mov     rax, [rcx]
0x180091f5a  mov     rax, [rax+18h]
0x180091f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091f63  mov     ebx, eax
0x180091f65  test    eax, eax
0x180091f67  js      loc_18009229C
0x180091f6d  lea     r8, [rsp+1A0h+var_148]
0x180091f72  mov     [rsp+1A0h+var_148], rsi
0x180091f77  lea     rdx, _GUID_e2ba9629_b18f_4e3a_aba5_42d879e79c80
0x180091f7e  lea     rcx, [rbp+0A0h+var_120]
0x180091f82  call    cs:__imp_SHGetFolderTypeDescription
0x180091f88  mov     ebx, eax
0x180091f8a  test    eax, eax
0x180091f8c  js      loc_18009229C
0x180091f92  movups  xmm0, [rbp+0A0h+var_120]
0x180091f96  mov     rcx, [rsp+1A0h+var_148]
0x180091f9b  lea     rdx, [rsp+1A0h+var_170]
0x180091fa0  movups  xmm1, [rbp+0A0h+var_110]
0x180091fa4  mov     [rsp+1A0h+var_16C], esi
0x180091fa8  movups  [rbp+0A0h+var_E0], xmm0
0x180091fac  mov     [rsp+1A0h+var_170], esi
0x180091fb0  movups  [rbp+0A0h+var_D0], xmm1
0x180091fb4  mov     rax, [rcx]
0x180091fb7  mov     rax, [rax+68h]
0x180091fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091fc0  test    eax, eax
0x180091fc2  js      short loc_180091FD9
0x180091fc4  cmp     [rsp+1A0h+var_170], 1
0x180091fc9  jnz     short loc_180091FD9
0x180091fcb  lea     rdx, [rsp+1A0h+var_16C]
0x180091fd0  mov     rcx, rdi
0x180091fd3  call    cs:__imp_SaveTopViewSettings
0x180091fd9  mov     rcx, [rsp+1A0h+var_148]
0x180091fde  lea     rdx, [rsp+1A0h+var_160]
0x180091fe3  mov     [rsp+1A0h+var_160], esi
0x180091fe7  mov     rax, [rcx]
0x180091fea  mov     rax, [rax+60h]
0x180091fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ff3  test    eax, eax
0x180091ff5  js      short loc_18009201D
0x180091ff7  cmp     [rsp+1A0h+var_160], 1
0x180091ffc  jnz     short loc_18009201D
0x180091ffe  mov     rcx, [rsp+1A0h+var_148]
0x180092003  lea     rdx, [rbp+0A0h+var_110]
0x180092007  mov     rax, [rcx]
0x18009200a  mov     rax, [rax+0A8h]
0x180092011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092016  mov     ebx, eax
0x180092018  jmp     loc_180092277
0x18009201d  mov     rcx, [rsp+1A0h+var_140]
0x180092022  lea     rdx, [rsp+1A0h+punk]
0x180092027  mov     [rsp+1A0h+punk], rsi
0x18009202c  mov     rax, [rcx]
0x18009202f  mov     rax, [rax+30h]
0x180092033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092038  mov     ebx, eax
0x18009203a  test    eax, eax
0x18009203c  js      loc_180092277
0x180092042  mov     rcx, [rsp+1A0h+punk]; punk
0x180092047  lea     rdx, [rsp+1A0h+ppidl]; ppidl
0x18009204c  mov     [rsp+1A0h+ppidl], rsi
0x180092051  call    cs:__imp_SHGetIDListFromObject
0x180092057  mov     ebx, eax
0x180092059  test    eax, eax
0x18009205b  js      loc_180092266
0x180092061  mov     rcx, [rsp+1A0h+ppidl]; pidl
0x180092066  lea     rax, [rsp+1A0h+propBag]
0x18009206b  lea     r9, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180092072  mov     [rsp+1A0h+ppv], rax; ppv
0x180092077  mov     r8d, 5; dwFlags
0x18009207d  mov     [rsp+1A0h+propBag], rsi
0x180092082  lea     rdx, pszBagName; "Shell"
0x180092089  call    cs:__imp_SHGetViewStatePropertyBag
0x18009208f  mov     ebx, eax
0x180092091  test    eax, eax
0x180092093  js      loc_18009225B
0x180092099  mov     rcx, [rsp+1A0h+propBag]; propBag
0x18009209e  lea     r8, [rsp+1A0h+value]; value
0x1800920a3  lea     rdx, aTvFoldertype; "TV_FolderType"
0x1800920aa  mov     [rsp+1A0h+value], rsi
0x1800920af  mov     [rsp+1A0h+var_150], rsi
0x1800920b4  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1800920ba  mov     rcx, [rsp+1A0h+propBag]; propBag
0x1800920bf  lea     r8, [rsp+1A0h+var_150]; value
0x1800920c4  lea     rdx, aTvTopviewid; "TV_TopViewID"
0x1800920cb  call    cs:__imp_PSPropertyBag_ReadStrAlloc
0x1800920d1  mov     ebx, 27h ; '''
0x1800920d6  lea     rdx, [rbp+0A0h+pszStr2]
0x1800920da  mov     r8d, ebx
0x1800920dd  lea     rcx, [rbp+0A0h+var_120]
0x1800920e1  call    cs:__imp_SHStringFromGUIDW
0x1800920e7  mov     r8d, ebx
0x1800920ea  lea     rdx, [rbp+0A0h+var_70]
0x1800920ee  lea     rcx, [rbp+0A0h+var_110]
0x1800920f2  call    cs:__imp_SHStringFromGUIDW
0x1800920f8  mov     rcx, [rsp+1A0h+propBag]; propBag
0x1800920fd  lea     r8, [rbp+0A0h+pszStr2]; value
0x180092101  lea     rdx, aTvFoldertype; "TV_FolderType"
0x180092108  call    cs:__imp_PSPropertyBag_WriteStr
0x18009210e  mov     ebx, eax
0x180092110  test    eax, eax
0x180092112  js      loc_180092234
0x180092118  mov     rcx, [rsp+1A0h+propBag]; propBag
0x18009211d  lea     r8, [rbp+0A0h+var_70]; value
0x180092121  lea     rdx, aTvTopviewid; "TV_TopViewID"
0x180092128  call    cs:__imp_PSPropertyBag_WriteStr
0x18009212e  mov     ebx, eax
0x180092130  test    eax, eax
0x180092132  js      loc_180092234
0x180092138  lea     r8, [rsp+1A0h+var_138]
0x18009213d  mov     [rsp+1A0h+var_138], rsi
0x180092142  lea     rdx, _GUID_fe812157_522c_46cb_8d53_6efe3dce2c46
0x180092149  lea     rcx, [rbp+0A0h+var_120]
0x18009214d  call    cs:__imp_SHGetTopViewDescription
0x180092153  mov     ebx, eax
0x180092155  test    eax, eax
0x180092157  js      loc_180092234
0x18009215d  mov     rcx, [rsp+1A0h+var_138]
0x180092162  lea     rdx, [rsp+1A0h+var_15C]
0x180092167  mov     [rsp+1A0h+var_15C], esi
0x18009216b  mov     rax, [rcx]
0x18009216e  mov     rax, [rax+0B0h]
0x180092175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009217a  mov     ebx, eax
0x18009217c  test    eax, eax
0x18009217e  js      short loc_180092199
0x180092180  mov     r8d, [rsp+1A0h+var_15C]; value
0x180092185  lea     rdx, aTvTopviewversi; "TV_TopViewVersion"
0x18009218c  mov     rcx, [rsp+1A0h+propBag]; propBag
0x180092191  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180092197  mov     ebx, eax
0x180092199  mov     rcx, [rsp+1A0h+var_138]
0x18009219e  mov     rax, [rcx]
0x1800921a1  mov     rax, [rax+10h]
0x1800921a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800921aa  test    ebx, ebx
0x1800921ac  js      loc_180092234
0x1800921b2  cmp     [rsp+1A0h+var_170], 1
0x1800921b7  jnz     short loc_180092234
0x1800921b9  mov     rcx, [rsp+1A0h+value]; pszStr1
0x1800921be  test    rcx, rcx
0x1800921c1  jz      short loc_180092239
0x1800921c3  cmp     [rsp+1A0h+var_150], rsi
0x1800921c8  jz      short loc_180092239
0x1800921ca  lea     rdx, [rbp+0A0h+pszStr2]; pszStr2
0x1800921ce  call    cs:__imp_StrCmpICW
0x1800921d4  test    eax, eax
0x1800921d6  jnz     short loc_1800921EB
0x1800921d8  mov     rcx, [rsp+1A0h+var_150]; pszStr1
0x1800921dd  lea     rdx, [rbp+0A0h+var_70]; pszStr2
0x1800921e1  call    cs:__imp_StrCmpICW
0x1800921e7  test    eax, eax
0x1800921e9  jz      short loc_180092234
0x1800921eb  mov     rcx, [rsp+1A0h+value]; psz
0x1800921f0  lea     rdx, [rbp+0A0h+pclsid]; pclsid
0x1800921f4  xorps   xmm0, xmm0
0x1800921f7  movups  xmmword ptr [rbp+0A0h+pclsid.Data1], xmm0
0x1800921fb  movups  xmmword ptr [rbp+0A0h+var_F0.Data1], xmm0
0x1800921ff  call    cs:__imp_SHCLSIDFromString
0x180092205  test    eax, eax
0x180092207  js      short loc_180092234
0x180092209  mov     rcx, [rsp+1A0h+var_150]; psz
0x18009220e  lea     rdx, [rbp+0A0h+var_F0]; pclsid
0x180092212  call    cs:__imp_SHCLSIDFromString
0x180092218  test    eax, eax
0x18009221a  js      short loc_180092234
0x18009221c  movups  xmm0, xmmword ptr [rbp+0A0h+pclsid.Data1]
0x180092220  mov     [rsp+1A0h+var_16C], 1
0x180092228  movups  xmm1, xmmword ptr [rbp+0A0h+var_F0.Data1]
0x18009222c  movups  [rbp+0A0h+var_E0], xmm0
0x180092230  movups  [rbp+0A0h+var_D0], xmm1
0x180092234  mov     rcx, [rsp+1A0h+value]; pv
0x180092239  call    cs:__imp_CoTaskMemFree
0x18009223f  mov     rcx, [rsp+1A0h+var_150]; pv
0x180092244  call    cs:__imp_CoTaskMemFree
0x18009224a  mov     rcx, [rsp+1A0h+propBag]
0x18009224f  mov     rax, [rcx]
0x180092252  mov     rax, [rax+10h]
0x180092256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009225b  mov     rcx, [rsp+1A0h+ppidl]; pidl
0x180092260  call    cs:__imp_ILFree
0x180092266  mov     rcx, [rsp+1A0h+punk]
0x18009226b  mov     rax, [rcx]
0x18009226e  mov     rax, [rax+10h]
0x180092272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092277  mov     rcx, [rsp+1A0h+var_148]
0x18009227c  mov     rax, [rcx]
0x18009227f  mov     rax, [rax+10h]
0x180092283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092288  cmp     [rsp+1A0h+var_16C], esi
0x18009228c  jz      short loc_18009229C
0x18009228e  mov     rcx, [rsp+1A0h+var_140]; struct ITopViewAwareItem *
0x180092293  lea     r8, [rbp+0A0h+var_E0]; struct TOPVIEWKEY *
0x180092297  call    ?ClearViewSettingsForTopView@@YAXPEAUITopViewAwareItem@@PEBGAEBUTOPVIEWKEY@@@Z; ClearViewSettingsForTopView(ITopViewAwareItem *,ushort const *,TOPVIEWKEY const &)
0x18009229c  mov     rcx, [rsp+1A0h+var_140]
0x1800922a1  mov     rax, [rcx]
0x1800922a4  mov     rax, [rax+10h]
0x1800922a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800922ad  jmp     loc_180091F18
```
