# CDBFolder::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x180086c40`
- end: `0x180086fef`
- name: `?GetDisplayNameOf@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `943`
- prototype: `__int64 __fastcall(CDBFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007a00`
- `0x18000baa0`
- `0x180015f78`
- `0x180019000`
- `0x180028a68`
- `0x18003d2a4`
- `0x18003d55c`
- `0x180042530`
- `0x18004fdf8`
- `0x1800520f0`
- `0x180055f2c`
- `0x1800566bc`
- `0x18005c2b0`
- `0x18005e73c`
- `0x180063a68`
- `0x180064790`
- `0x180082f40`
- `0x180083138`
- `0x1800848f4`
- `0x180084ff4`
- `0x180086c40`
- `0x1800ea010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x180086d79`
- `SHCORE!SHStrDupW` at `0x180086e54`
- `SHCORE!SHStrDupW` at `0x180086fca`
- `SHCORE!SHStrDupW` at `0x180086d79`
- `SHCORE!SHStrDupW` at `0x180086e54`
- `SHCORE!SHStrDupW` at `0x180086fca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086edf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086edf`
- `OLEAUT32!__imp_SysFreeString` at `0x180086f75`
- `OLEAUT32!__imp_SysFreeString` at `0x180086fd6`
- `OLEAUT32!__imp_SysFreeString` at `0x180086f75`
- `OLEAUT32!__imp_SysFreeString` at `0x180086fd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDBFolder::GetDisplayNameOf(
        const struct _ITEMIDLIST_RELATIVE **this,
        const struct _ITEMID_CHILD *a2,
        struct IBindCtx *a3,
        struct _STRRET *a4)
{
  unsigned int v5; // esi
  unsigned int v8; // edx
  int DataFromIDList; // ebx
  HRESULT v10; // eax
  __int64 v11; // rdx
  const struct _ITEMIDLIST_RELATIVE *v12; // rdx
  CDBFolder *v13; // rcx
  const struct _ITEMIDLIST_RELATIVE *v14; // rcx
  __int64 v15; // r8
  int QueryAbsoluteParsingName; // eax
  CDBFolder *v17; // rcx
  _DWORD *v18; // r13
  int ParsingName; // eax
  int pbstr; // [rsp+20h] [rbp-58h]
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  struct DBITEM *v23; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-38h] BYREF
  LPVOID *p_pv; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 *v26; // [rsp+60h] [rbp-18h] BYREF
  char v27; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  LPCWSTR psz; // [rsp+C8h] [rbp+50h] BYREF

  v5 = (unsigned int)a3;
  if ( a2 )
  {
    if ( (unsigned int)ILIsEmpty(a2) )
      goto LABEL_18;
    pv = 0;
    DataFromIDList = CDBFolder::_GetDataFromIDList(v13, v12, (const struct DBITEM **)&pv);
    if ( DataFromIDList < 0 )
      return (unsigned int)DataFromIDList;
    psz = 0;
    v17 = (CDBFolder *)((unsigned __int16)v5 & 0xC000);
    if ( (_DWORD)v17 == 0x8000 )
    {
      ParsingName = CDBFolder::_GetParsingName(
                      (CDBFolder *)this,
                      a2,
                      v5,
                      *((_DWORD *)pv + 7) & 1,
                      (unsigned __int16 **)&psz);
    }
    else
    {
      v18 = pv;
      if ( (_DWORD)v17 == 49152 && (unsigned int)CDBFolder::_IsFilterOrStack(v17, (const struct DBITEM *)pv) )
      {
        pv = 0;
        DataFromIDList = CDBFolder::_GetQueryAbsoluteParsingName((CDBFolder *)this, a2, (unsigned __int16 **)&pv);
        if ( DataFromIDList >= 0 )
        {
          DataFromIDList = SHSysAllocString((const unsigned __int16 *)pv, (unsigned __int16 **)&psz);
          CoTaskMemFree(pv);
          goto LABEL_40;
        }
LABEL_42:
        SysFreeString((BSTR)psz);
        return (unsigned int)DataFromIDList;
      }
      if ( v5 && (v5 & 1) == 0 )
      {
        v23 = 0;
        DataFromIDList = CDBFolder::_GetDataFromIDList(v17, this[28], &v23);
        if ( DataFromIDList >= 0 )
        {
          pv = 0;
          DataFromIDList = DisplayNameOfFolderAsBSTR(this[28], v5, (BSTR)&pv);
          if ( DataFromIDList >= 0 )
            DataFromIDList = CDBFolder::_AppendInFolderDisplayName(
                               (CDBFolder *)this,
                               a2,
                               (unsigned __int16 *)pv,
                               v18[7] & 1,
                               (unsigned __int16 **)&psz);
          SysFreeString((BSTR)pv);
          goto LABEL_40;
        }
        goto LABEL_42;
      }
      ParsingName = CDBFolder::_GetInFolderDisplayName((CDBFolder *)this, a2, v18[7] & 1, (unsigned __int16 **)&psz);
    }
    DataFromIDList = ParsingName;
LABEL_40:
    if ( DataFromIDList >= 0 )
    {
      a4->uType = 0;
      DataFromIDList = SHStrDupW(psz, &a4->pOleStr);
    }
    goto LABEL_42;
  }
  if ( (_DWORD)a3 == 1 || !CDBFolder::ShouldFormatSearchResultsFolderDisplayName((CDBFolder *)this) )
  {
LABEL_18:
    DataFromIDList = -2147467259;
    if ( SHGetAttributesWithBindCtx(0, this[28], a3, 0x40000000u) )
      return (unsigned int)DataFromIDList;
    psz = 0;
    v14 = this[33];
    v15 = *(_QWORD *)v14;
    if ( (v5 & 0xC000) == 0xC000 )
    {
      if ( (*(int (__fastcall **)(const struct _ITEMIDLIST_RELATIVE *, LPCWSTR *))(v15 + 32))(v14, &psz) >= 0 )
        goto LABEL_24;
      QueryAbsoluteParsingName = CDBFolder::_GetQueryAbsoluteParsingName(
                                   (CDBFolder *)this,
                                   0,
                                   (unsigned __int16 **)&psz);
    }
    else
    {
      QueryAbsoluteParsingName = (*(__int64 (__fastcall **)(const struct _ITEMIDLIST_RELATIVE *, LPCWSTR *))(v15 + 24))(
                                   v14,
                                   &psz);
    }
    DataFromIDList = QueryAbsoluteParsingName;
    if ( QueryAbsoluteParsingName < 0 )
      return (unsigned int)DataFromIDList;
LABEL_24:
    a4->uType = 0;
    DataFromIDList = SHStrDupW(psz, &a4->pOleStr);
    CoTaskMemFree((LPVOID)psz);
    return (unsigned int)DataFromIDList;
  }
  memset(v24, 0, sizeof(v24));
  DataFromIDList = -2147467259;
  v23 = 0;
  LOWORD(psz) = 0;
  if ( !Windows::Internal::ResourceString::FindAndSize(
          g_hinst,
          v8,
          (unsigned __int16)a3,
          (const unsigned __int16 **)&v23,
          (unsigned __int16 *)&psz)
    || (DataFromIDList = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                           (__int64)v24,
                           (const unsigned __int16 *)v23,
                           (unsigned __int16)psz),
        DataFromIDList < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1727,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)DataFromIDList,
      pbstr);
    goto LABEL_16;
  }
  pv = 0;
  p_pv = &pv;
  v26 = 0;
  v27 = 1;
  DataFromIDList = CDBFolder::GetAutoListDisplayName((CDBFolder *)this, &v26);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_pv);
  if ( DataFromIDList >= 0 )
  {
    psz = 0;
    v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &psz,
            v24[0],
            pv);
    DataFromIDList = v10;
    if ( v10 >= 0 )
    {
      a4->uType = 0;
      v10 = SHStrDupW(psz, &a4->pOleStr);
      DataFromIDList = v10;
      if ( v10 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pv);
        DataFromIDList = 0;
        goto LABEL_16;
      }
      v11 = 5935;
    }
    else
    {
      v11 = 5933;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)v10,
      pbstr);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x172A,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\dbfolder.cpp",
      (const char *)(unsigned int)DataFromIDList,
      pbstr);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pv);
LABEL_16:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v24);
  return (unsigned int)DataFromIDList;
}

```

## disassembly

```asm
0x180086c40  push    rbp
0x180086c42  push    rbx
0x180086c43  push    rsi
0x180086c44  push    rdi
0x180086c45  push    r12
0x180086c47  push    r13
0x180086c49  push    r14
0x180086c4b  push    r15
0x180086c4d  mov     rbp, rsp
0x180086c50  sub     rsp, 78h
0x180086c54  mov     r15, r9
0x180086c57  mov     esi, r8d
0x180086c5a  mov     r14, rdx
0x180086c5d  mov     rdi, rcx
0x180086c60  xor     r12d, r12d
0x180086c63  test    rdx, rdx
0x180086c66  jnz     loc_180086DCB
0x180086c6c  cmp     r8d, 1
0x180086c70  jz      loc_180086DDB
0x180086c76  call    ?ShouldFormatSearchResultsFolderDisplayName@CDBFolder@@AEAA_NXZ; CDBFolder::ShouldFormatSearchResultsFolderDisplayName(void)
0x180086c7b  test    al, al
0x180086c7d  jz      loc_180086DDB
0x180086c83  mov     [rbp+var_38], r12
0x180086c87  mov     [rbp+var_30], r12
0x180086c8b  mov     [rbp+var_28], r12
0x180086c8f  mov     ebx, 80004005h
0x180086c94  mov     [rbp+var_40], r12
0x180086c98  mov     word ptr [rbp+psz], r12w
0x180086c9d  lea     rax, [rbp+psz]
0x180086ca1  mov     qword ptr [rsp+78h+pbstr], rax; int
0x180086ca6  lea     r9, [rbp+var_40]; unsigned __int16 **
0x180086caa  mov     rcx, cs:g_hinst; hModule
0x180086cb1  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x180086cb6  test    al, al
0x180086cb8  jz      loc_180086DA4
0x180086cbe  movzx   r8d, word ptr [rbp+psz]
0x180086cc3  mov     rdx, [rbp+var_40]
0x180086cc7  lea     rcx, [rbp+var_38]
0x180086ccb  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180086cd0  mov     ebx, eax
0x180086cd2  test    eax, eax
0x180086cd4  js      loc_180086DA4
0x180086cda  mov     [rbp+pv], r12
0x180086cde  lea     rax, [rbp+pv]
0x180086ce2  mov     [rbp+var_20], rax
0x180086ce6  mov     [rbp+var_18], r12
0x180086cea  mov     [rbp+var_10], 1
0x180086cee  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180086cf2  mov     rcx, rdi; this
0x180086cf5  call    ?GetAutoListDisplayName@CDBFolder@@AEAAJPEAPEAG@Z; CDBFolder::GetAutoListDisplayName(ushort * *)
0x180086cfa  mov     ebx, eax
0x180086cfc  lea     rcx, [rbp+var_20]
0x180086d00  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180086d05  test    ebx, ebx
0x180086d07  jns     short loc_180086D30
0x180086d09  mov     rcx, [rbp+40h]; this
0x180086d0d  mov     r9d, ebx; char *
0x180086d10  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180086d17  mov     edx, 172Ah; void *
0x180086d1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086d21  nop
0x180086d22  lea     rcx, [rbp+pv]
0x180086d26  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180086d2b  jmp     loc_180086DBD
0x180086d30  mov     [rbp+psz], r12
0x180086d34  mov     r8, [rbp+pv]
0x180086d38  mov     rdx, [rbp+var_38]
0x180086d3c  lea     rcx, [rbp+psz]
0x180086d40  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180086d45  mov     ebx, eax
0x180086d47  test    eax, eax
0x180086d49  jns     short loc_180086D6E
0x180086d4b  mov     edx, 172Dh; void *
0x180086d50  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180086d57  mov     r9d, eax; char *
0x180086d5a  mov     rcx, [rbp+40h]; this
0x180086d5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086d63  lea     rcx, [rbp+psz]
0x180086d67  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180086d6c  jmp     short loc_180086D22
0x180086d6e  mov     [r15], r12d
0x180086d71  lea     rdx, [r15+8]; ppwsz
0x180086d75  mov     rcx, [rbp+psz]; psz
0x180086d79  call    cs:__imp_SHStrDupW
0x180086d7f  mov     ebx, eax
0x180086d81  test    eax, eax
0x180086d83  jns     short loc_180086D8C
0x180086d85  mov     edx, 172Fh
0x180086d8a  jmp     short loc_180086D50
0x180086d8c  lea     rcx, [rbp+psz]
0x180086d90  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180086d95  nop
0x180086d96  lea     rcx, [rbp+pv]
0x180086d9a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180086d9f  mov     ebx, r12d
0x180086da2  jmp     short loc_180086DBD
0x180086da4  mov     rcx, [rbp+40h]; this
0x180086da8  mov     r9d, ebx; char *
0x180086dab  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\windows.storage.sear"...
0x180086db2  mov     edx, 1727h; void *
0x180086db7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086dbc  nop
0x180086dbd  lea     rcx, [rbp+var_38]
0x180086dc1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180086dc6  jmp     loc_180086FDC
0x180086dcb  mov     rcx, r14; struct _ITEMIDLIST_RELATIVE *
0x180086dce  call    ?ILIsEmpty@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsEmpty(_ITEMIDLIST_RELATIVE const *)
0x180086dd3  test    eax, eax
0x180086dd5  jz      loc_180086E6B
0x180086ddb  mov     ebx, 80004005h
0x180086de0  mov     r9d, 40000000h; unsigned int
0x180086de6  mov     rdx, [rdi+0E0h]; struct _ITEMIDLIST_RELATIVE *
0x180086ded  xor     ecx, ecx; struct IShellFolder *
0x180086def  call    ?SHGetAttributesWithBindCtx@@YAKPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@K@Z; SHGetAttributesWithBindCtx(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong)
0x180086df4  test    eax, eax
0x180086df6  jnz     loc_180086FDC
0x180086dfc  mov     [rbp+psz], r12
0x180086e00  mov     rcx, [rdi+108h]
0x180086e07  mov     r8, [rcx]
0x180086e0a  mov     eax, 0C000h
0x180086e0f  and     esi, eax
0x180086e11  lea     rdx, [rbp+psz]
0x180086e15  cmp     esi, eax
0x180086e17  jnz     short loc_180086E36
0x180086e19  mov     rax, [r8+20h]
0x180086e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086e22  test    eax, eax
0x180086e24  jns     short loc_180086E49
0x180086e26  lea     r8, [rbp+psz]; unsigned __int16 **
0x180086e2a  xor     edx, edx; struct _ITEMID_CHILD *
0x180086e2c  mov     rcx, rdi; this
0x180086e2f  call    ?_GetQueryAbsoluteParsingName@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAG@Z; CDBFolder::_GetQueryAbsoluteParsingName(_ITEMID_CHILD const *,ushort * *)
0x180086e34  jmp     short loc_180086E3F
0x180086e36  mov     rax, [r8+18h]
0x180086e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086e3f  mov     ebx, eax
0x180086e41  test    eax, eax
0x180086e43  js      loc_180086FDC
0x180086e49  mov     [r15], r12d
0x180086e4c  lea     rdx, [r15+8]; ppwsz
0x180086e50  mov     rcx, [rbp+psz]; psz
0x180086e54  call    cs:__imp_SHStrDupW
0x180086e5a  mov     ebx, eax
0x180086e5c  mov     rcx, [rbp+psz]; pv
0x180086e60  call    cs:__imp_CoTaskMemFree
0x180086e66  jmp     loc_180086FDC
0x180086e6b  mov     [rbp+pv], r12
0x180086e6f  lea     r8, [rbp+pv]; struct DBITEM **
0x180086e73  call    ?_GetDataFromIDList@CDBFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEFBUDBITEM@@@Z; CDBFolder::_GetDataFromIDList(_ITEMIDLIST_RELATIVE const *,DBITEM const * *)
0x180086e78  mov     ebx, eax
0x180086e7a  test    eax, eax
0x180086e7c  js      loc_180086FDC
0x180086e82  mov     [rbp+psz], r12
0x180086e86  mov     ecx, esi
0x180086e88  mov     eax, 0C000h
0x180086e8d  and     ecx, eax; this
0x180086e8f  cmp     ecx, 8000h
0x180086e95  jz      loc_180086F96
0x180086e9b  mov     r13, [rbp+pv]
0x180086e9f  cmp     ecx, eax
0x180086ea1  jnz     short loc_180086EEA
0x180086ea3  mov     rdx, r13; struct DBITEM *
0x180086ea6  call    ?_IsFilterOrStack@CDBFolder@@AEAAHPEFBUDBITEM@@@Z; CDBFolder::_IsFilterOrStack(DBITEM const *)
0x180086eab  test    eax, eax
0x180086ead  jz      short loc_180086EEA
0x180086eaf  mov     [rbp+pv], r12
0x180086eb3  lea     r8, [rbp+pv]; unsigned __int16 **
0x180086eb7  mov     rdx, r14; struct _ITEMID_CHILD *
0x180086eba  mov     rcx, rdi; this
0x180086ebd  call    ?_GetQueryAbsoluteParsingName@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAPEAG@Z; CDBFolder::_GetQueryAbsoluteParsingName(_ITEMID_CHILD const *,ushort * *)
0x180086ec2  mov     ebx, eax
0x180086ec4  test    eax, eax
0x180086ec6  js      loc_180086FD2
0x180086ecc  lea     rdx, [rbp+psz]; unsigned __int16 **
0x180086ed0  mov     rcx, [rbp+pv]; unsigned __int16 *
0x180086ed4  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180086ed9  mov     ebx, eax
0x180086edb  mov     rcx, [rbp+pv]; pv
0x180086edf  call    cs:__imp_CoTaskMemFree
0x180086ee5  jmp     loc_180086FBB
0x180086eea  test    esi, esi
0x180086eec  jz      loc_180086F7D
0x180086ef2  test    sil, 1
0x180086ef6  jnz     loc_180086F7D
0x180086efc  mov     [rbp+var_40], r12
0x180086f00  lea     r8, [rbp+var_40]; struct DBITEM **
0x180086f04  mov     rdx, [rdi+0E0h]; struct _ITEMIDLIST_RELATIVE *
0x180086f0b  call    ?_GetDataFromIDList@CDBFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEFBUDBITEM@@@Z; CDBFolder::_GetDataFromIDList(_ITEMIDLIST_RELATIVE const *,DBITEM const * *)
0x180086f10  mov     ebx, eax
0x180086f12  test    eax, eax
0x180086f14  js      loc_180086FD2
0x180086f1a  mov     [rbp+pv], r12
0x180086f1e  mov     r9d, [r13+1Ch]
0x180086f22  and     r9d, 1
0x180086f26  mov     rax, [rbp+var_40]
0x180086f2a  mov     r8d, [rax+1Ch]
0x180086f2e  and     r8d, 1
0x180086f32  lea     rax, [rbp+pv]
0x180086f36  mov     qword ptr [rsp+78h+pbstr], rax; pbstr
0x180086f3b  mov     edx, esi; unsigned int
0x180086f3d  mov     rcx, [rdi+0E0h]; struct _ITEMIDLIST_RELATIVE *
0x180086f44  call    DisplayNameOfFolderAsBSTR
0x180086f49  mov     ebx, eax
0x180086f4b  test    eax, eax
0x180086f4d  js      short loc_180086F71
0x180086f4f  mov     r9d, [r13+1Ch]
0x180086f53  and     r9d, 1; int
0x180086f57  lea     rax, [rbp+psz]
0x180086f5b  mov     qword ptr [rsp+78h+pbstr], rax; unsigned __int16 **
0x180086f60  mov     r8, [rbp+pv]; unsigned __int16 *
0x180086f64  mov     rdx, r14; struct _ITEMID_CHILD *
0x180086f67  mov     rcx, rdi; this
0x180086f6a  call    ?_AppendInFolderDisplayName@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAGHPEAPEAG@Z; CDBFolder::_AppendInFolderDisplayName(_ITEMID_CHILD const *,ushort *,int,ushort * *)
0x180086f6f  mov     ebx, eax
0x180086f71  mov     rcx, [rbp+pv]; bstrString
0x180086f75  call    cs:__imp_SysFreeString
0x180086f7b  jmp     short loc_180086FBB
0x180086f7d  mov     r8d, [r13+1Ch]
0x180086f81  and     r8d, 1; int
0x180086f85  lea     r9, [rbp+psz]; unsigned __int16 **
0x180086f89  mov     rdx, r14; struct _ITEMID_CHILD *
0x180086f8c  mov     rcx, rdi; this
0x180086f8f  call    ?_GetInFolderDisplayName@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@HPEAPEAG@Z; CDBFolder::_GetInFolderDisplayName(_ITEMID_CHILD const *,int,ushort * *)
0x180086f94  jmp     short loc_180086FB9
0x180086f96  mov     rax, [rbp+pv]
0x180086f9a  mov     r9d, [rax+1Ch]
0x180086f9e  and     r9d, 1; int
0x180086fa2  lea     rax, [rbp+psz]
0x180086fa6  mov     qword ptr [rsp+78h+pbstr], rax; unsigned __int16 **
0x180086fab  mov     r8d, esi; unsigned int
0x180086fae  mov     rdx, r14; struct _ITEMID_CHILD *
0x180086fb1  mov     rcx, rdi; this
0x180086fb4  call    ?_GetParsingName@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@KHPEAPEAG@Z; CDBFolder::_GetParsingName(_ITEMID_CHILD const *,ulong,int,ushort * *)
0x180086fb9  mov     ebx, eax
0x180086fbb  test    ebx, ebx
0x180086fbd  js      short loc_180086FD2
0x180086fbf  mov     [r15], r12d
0x180086fc2  lea     rdx, [r15+8]; ppwsz
0x180086fc6  mov     rcx, [rbp+psz]; psz
0x180086fca  call    cs:__imp_SHStrDupW
0x180086fd0  mov     ebx, eax
0x180086fd2  mov     rcx, [rbp+psz]; bstrString
0x180086fd6  call    cs:__imp_SysFreeString
0x180086fdc  mov     eax, ebx
0x180086fde  add     rsp, 78h
0x180086fe2  pop     r15
0x180086fe4  pop     r14
0x180086fe6  pop     r13
0x180086fe8  pop     r12
0x180086fea  pop     rdi
0x180086feb  pop     rsi
0x180086fec  pop     rbx
0x180086fed  pop     rbp
0x180086fee  retn
```
