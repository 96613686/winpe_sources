# Microsoft::Resources::Runtime::CMrtUriParser::Normalize(ushort const *)

- ea: `0x18002eef0`
- end: `0x18002fdfc`
- name: `?Normalize@CMrtUriParser@Runtime@Resources@Microsoft@@QEAAJPEBG@Z`
- size: `3852`
- prototype: `int(Microsoft::Resources::Runtime::CMrtUriParser *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18002d0c0`
- `0x180030168`
- `0x1800a8178`

## callees

- `0x18002c8d0`
- `0x18002eef0`
- `0x18003490c`
- `0x18004c960`
- `0x18004dbb8`
- `0x18006b618`
- `0x18008454c`
- `0x18008679c`
- `0x18008680c`
- `0x180086f7c`
- `0x180088810`
- `0x180088878`
- `0x180088d45`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002f7bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002f7bd`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002f83a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002f83a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f1f1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f401`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f49d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f6b1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f73f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f1f1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f401`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f49d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f6b1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002f73f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f23c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f455`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f4ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f6fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f786`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f960`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f9f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fa10`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f23c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f455`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f4ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f6fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f786`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f960`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f9f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fa10`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f1d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f253`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f3e7`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f487`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f697`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f72b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f952`
- `OLEAUT32!__imp_SysStringLen` at `0x18002fbd5`
- `OLEAUT32!__imp_SysStringLen` at `0x18002fbe0`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f1d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f253`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f3e7`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f487`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f697`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f72b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002f952`
- `OLEAUT32!__imp_SysStringLen` at `0x18002fbd5`
- `OLEAUT32!__imp_SysStringLen` at `0x18002fbe0`
- `iertutil!CreateUri` at `0x18002f60d`
- `iertutil!CreateUri` at `0x18002f8ef`
- `iertutil!CreateUri` at `0x18002f60d`
- `iertutil!CreateUri` at `0x18002f8ef`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18002fb15`
- `iertutil!PrivateCoInternetCombineIUri` at `0x18002fb15`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CMrtUriParser::Normalize(
        Microsoft::Resources::Runtime::CMrtUriParser *this,
        const unsigned __int16 *a2)
{
  Microsoft::Resources::Runtime::CMrtUriParser *v2; // r13
  __int64 v4; // rcx
  char v5; // r8
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  int v8; // esi
  __int64 v9; // r10
  int v10; // r15d
  char v11; // r12
  int v12; // edi
  __int64 v13; // rdx
  unsigned __int16 v14; // cx
  __int64 v15; // r14
  __int64 *v16; // rax
  const unsigned __int16 *v17; // r15
  __int64 v18; // rcx
  __int64 v19; // rbx
  _WORD *v20; // rbx
  __int64 v21; // rsi
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // r12
  IUri *v24; // rax
  IUri *v25; // rdi
  const struct std::nothrow_t *v26; // rdx
  __int64 v27; // rax
  char *v28; // r13
  IUri *v29; // rcx
  unsigned int v30; // ebx
  const struct std::nothrow_t *v31; // rdx
  unsigned __int16 **v32; // r9
  BSTR *v33; // r12
  signed int v34; // ebx
  signed int v35; // esi
  BSTR v36; // rax
  OLECHAR *v37; // rdi
  Microsoft::Resources::Runtime::CMrtUriParser *v38; // r14
  OLECHAR *v39; // rcx
  UINT v40; // eax
  unsigned __int16 *v41; // rdi
  Microsoft::Resources::Runtime::CMrtUriParser *v42; // rbx
  __int64 v43; // rax
  const unsigned __int16 *v45; // rbx
  __int64 v46; // rsi
  unsigned __int64 v47; // rsi
  unsigned __int64 v48; // r15
  IUri *v49; // rax
  IUri *v50; // rdi
  const struct std::nothrow_t *v51; // rdx
  __int64 v52; // rax
  _WORD *v53; // r15
  IUri *v54; // rcx
  int v55; // ebx
  unsigned int v56; // edi
  const struct std::nothrow_t *v57; // rdx
  __int64 k; // rcx
  const unsigned __int16 *v59; // rdi
  unsigned __int16 v60; // ax
  Microsoft::Resources::Runtime::CMrtUriParser *v61; // rsi
  __int64 v62; // rbx
  OLECHAR *v63; // rcx
  signed int v64; // esi
  signed int v65; // r13d
  BSTR v66; // r12
  const void *v67; // rdx
  BSTR *v68; // rsi
  __int64 v69; // rbx
  signed int v70; // edi
  signed int v71; // r12d
  BSTR v72; // rsi
  BSTR *v73; // rbx
  int v74; // eax
  unsigned __int64 v75; // rax
  int i; // eax
  struct IUri *BaseIUri; // rdi
  HRESULT v78; // eax
  __int64 j; // rcx
  __int16 v80; // ax
  const unsigned __int16 *v81; // rbx
  __int64 v82; // rdi
  OLECHAR *v83; // rcx
  signed int v84; // esi
  signed int v85; // r12d
  BSTR v86; // rax
  BSTR v87; // r15
  const void *v88; // rdx
  const void **v89; // r13
  signed int v90; // ebx
  signed int v91; // esi
  BSTR v92; // rax
  BSTR v93; // rdi
  int v94; // ecx
  unsigned __int16 v95; // ax
  wchar_t *v96; // rax
  wchar_t v97; // cx
  HRESULT Uri; // eax
  unsigned int v99; // ebx
  int v100; // ebx
  OLECHAR *v101; // rcx
  __int64 v102; // rcx
  const struct std::nothrow_t *v103; // rdx
  __int64 v104; // rdx
  void *v105; // rdi
  const struct std::nothrow_t *v106; // rdx
  int v107; // eax
  unsigned int v108; // ebx
  OLECHAR *v109; // rbx
  UINT v110; // eax
  BSTR v111; // rbx
  UINT v112; // eax
  int v113; // eax
  unsigned __int16 v114; // r9
  __int64 v115; // rdx
  int v116; // eax
  int v117; // eax
  Microsoft::Resources::Runtime::CMrtUriParser *v118; // rsi
  struct IUri *v119; // rax
  struct IUri *v120; // rdi
  int v121; // eax
  int v122; // eax
  unsigned __int64 *v123; // [rsp+20h] [rbp-60h]
  int v124; // [rsp+20h] [rbp-60h]
  int v125; // [rsp+20h] [rbp-60h]
  char v126; // [rsp+28h] [rbp-58h]
  BSTR bstrString; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v128[4]; // [rsp+48h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  Microsoft::Resources::Runtime::CMrtUriParser *v130; // [rsp+B0h] [rbp+30h] BYREF
  void *Src; // [rsp+B8h] [rbp+38h] BYREF
  BSTR pbstr; // [rsp+C0h] [rbp+40h] BYREF
  IUri *ppURI; // [rsp+C8h] [rbp+48h] BYREF

  v130 = this;
  v2 = this;
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)v2 + 5) = 0;
  }
  v5 = 0;
  v6 = -1;
  v7 = 0;
  do
    ++v6;
  while ( a2[v6] );
  v8 = 1;
  v9 = 0x200000000801LL;
  do
  {
    if ( a2[v7] == 46 )
    {
      if ( !v7 || (v75 = a2[v7 - 1], LOWORD(v75) = v75 - 47, (unsigned __int16)v75 <= 0x2Du) && _bittest64(&v9, v75) )
      {
        for ( i = 1; ; ++i )
        {
          if ( ++v7 >= v6 )
            goto LABEL_122;
          v114 = a2[v7];
          if ( v114 != 46 )
            break;
        }
        if ( v114 != 47 && v114 != 92 )
        {
LABEL_122:
          if ( i < 3 && v7 == v6 )
            v5 = 1;
          goto LABEL_7;
        }
        if ( i < 3 )
          v5 = 1;
      }
    }
LABEL_7:
    ++v7;
  }
  while ( v7 < v6 );
  if ( v5 )
  {
    pbstr = 0;
    BaseIUri = Microsoft::Resources::Runtime::CMrtUriParser::GetBaseIUri(v2);
    if ( BaseIUri )
    {
      ppURI = 0;
      v78 = CreateUri(a2, 0x4B85u, 0, &ppURI);
      v30 = v78;
      if ( v78 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA5,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)(unsigned int)v78,
          (int)v123);
        if ( ppURI )
          ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
        return v30;
      }
      v126 = 0;
      v123 = 0;
      v107 = PrivateCoInternetCombineIUri(BaseIUri, ppURI, 0, (char *)v2 + 40);
      v108 = v107;
      if ( v107 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA7,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)(unsigned int)v107,
          0);
        ATL::CComPtr<IUri>::~CComPtr<IUri>(&ppURI);
        return v108;
      }
      if ( ppURI )
        ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    }
LABEL_178:
    v100 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 5) + 120LL))(*((_QWORD *)v2 + 5), &pbstr);
    if ( v100 < 0 )
    {
      v104 = 187;
    }
    else
    {
      *((_QWORD *)v2 + 1) = pbstr;
      v100 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 5) + 104LL))(*((_QWORD *)v2 + 5), &pbstr);
      if ( v100 < 0 )
      {
        v104 = 191;
      }
      else
      {
        v101 = pbstr;
        *(_QWORD *)v2 = pbstr;
        if ( v101 && SysStringLen(v101) )
          goto LABEL_186;
        SysFreeString(*(BSTR *)v2);
        *(_QWORD *)v2 = 0;
        if ( !BaseIUri )
        {
          BaseIUri = Microsoft::Resources::Runtime::CMrtUriParser::GetBaseIUri(v2);
          if ( !BaseIUri )
            goto LABEL_186;
        }
        v100 = ((__int64 (__fastcall *)(struct IUri *, BSTR *))BaseIUri->lpVtbl->GetHost)(BaseIUri, &pbstr);
        if ( v100 >= 0 )
        {
          *(_QWORD *)v2 = pbstr;
LABEL_186:
          v102 = *((_QWORD *)v2 + 5);
          LODWORD(Src) = 0;
          bstrString = 0;
          if ( !(*(unsigned int (__fastcall **)(__int64, void **))(*(_QWORD *)v102 + 184LL))(v102, &Src)
            || !(*(unsigned int (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)v2 + 5) + 160LL))(
                  *((_QWORD *)v2 + 5),
                  &bstrString) )
          {
            SysFreeString(bstrString);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 5) + 16LL))(*((_QWORD *)v2 + 5));
            return 2147957520LL;
          }
          SysFreeString(bstrString);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 5) + 16LL))(*((_QWORD *)v2 + 5));
          goto LABEL_65;
        }
        v104 = 206;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v104,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)(unsigned int)v100,
      (int)v123);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 5) + 16LL))(*((_QWORD *)v2 + 5));
    return (unsigned int)v100;
  }
  v10 = 0;
  v11 = 0;
  v12 = 0;
  do
  {
    v13 = v12;
    v14 = a2[v12];
    if ( (unsigned __int16)(v14 - 97) <= 0x19u )
      goto LABEL_27;
    if ( v14 >= 0x41u )
    {
      if ( v14 <= 0x5Au )
        goto LABEL_27;
    }
    else
    {
      if ( v14 >= 0x30u )
      {
        if ( v14 <= 0x39u )
          goto LABEL_27;
LABEL_156:
        if ( v12 != 11 || v14 != 58 || (unsigned int)_o__wcsnicmp(a2, L"ms-resource", 11, 1229) )
          goto LABEL_26;
        v94 = a2[12];
        v11 = 1;
        if ( (unsigned __int16)(v94 - 97) <= 0x19u
          || (unsigned __int16)(v94 - 45) <= 0x32u
          && (v115 = 0x43FFFFFF01FFBLL, _bittest64(&v115, (unsigned int)(v94 - 45)))
          || (unsigned __int16)(v94 - 161) <= 0xD75Du
          || (unsigned __int16)(v94 + 1791) <= 0x4CDu
          || (unsigned __int16)(v94 + 527) <= 0x1FDu
          || (_WORD)v94 == 126 )
        {
          v8 = 2;
        }
        goto LABEL_27;
      }
      if ( v14 == 45 )
        goto LABEL_27;
    }
    if ( (unsigned __int16)(v14 - 161) <= 0xD75Du
      || v14 == 126
      || v14 == 95
      || v14 == 46
      || (unsigned __int16)(v14 + 1791) <= 0x4CDu )
    {
      goto LABEL_27;
    }
    if ( v14 > 0xFDF0u )
    {
      if ( v14 < 0xFFEFu )
        goto LABEL_27;
LABEL_26:
      v8 = 4;
      goto LABEL_27;
    }
    if ( v14 != 47 )
      goto LABEL_156;
    if ( !v12 )
      goto LABEL_26;
    if ( v12 != 12 || !v11 )
    {
      if ( a2[v12 + 1] != 47 )
        goto LABEL_27;
      goto LABEL_26;
    }
    v8 = 4;
    v12 = 13;
    if ( a2[v13 + 1] == 47 )
    {
      v95 = a2[v13 + 2];
      if ( v95 )
      {
        if ( v95 != 47 )
        {
          v96 = wcschr(&a2[v13 + 2], 0x2Fu);
          if ( v96 )
          {
            v97 = v96[1];
            if ( v97 )
            {
              if ( v97 != 47 || v96[2] )
                v8 = 3;
            }
          }
        }
      }
      else
      {
        v10 = -2147009776;
      }
    }
LABEL_27:
    ++v12;
  }
  while ( a2[v12] );
  v2 = v130;
  v15 = -1;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)(unsigned int)v10,
      (int)v123);
    return (unsigned int)v10;
  }
  pbstr = 0;
  if ( v8 == 4 )
  {
    Uri = CreateUri(a2, 0x4B85u, 0, (IUri **)v130 + 5);
    v99 = Uri;
    if ( Uri < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
        (const char *)(unsigned int)Uri,
        (int)v123);
      return v99;
    }
    BaseIUri = 0;
    goto LABEL_178;
  }
  if ( v8 == 3 )
  {
    v45 = a2 + 14;
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v47 = v46 + 1;
    v48 = 2 * v47;
    if ( !is_mul_ok(v47, 2u) )
      v48 = -1;
    v49 = (IUri *)operator new[](v48, (const struct std::nothrow_t *)&std::nothrow);
    v50 = v49;
    if ( !v49 )
    {
      v56 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B3,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
        (const char *)0x8007000ELL,
        (int)v123);
      goto LABEL_192;
    }
    memset_0(v49, 0, v48);
    ppURI = v50;
    if ( v47 )
    {
      if ( v47 <= 0x7FFFFFFF )
      {
        v52 = 2147483646;
        Src = v50;
        v53 = v50;
        do
        {
          if ( !v52 )
            break;
          if ( !*v45 )
            break;
          LOWORD(v50->lpVtbl) = *v45++;
          v50 = (IUri *)((char *)v50 + 2);
          --v52;
          --v47;
        }
        while ( v47 );
        v54 = (IUri *)((char *)v50 - 2);
        v55 = -2147024774;
        if ( v47 )
        {
          v54 = v50;
          v55 = 0;
        }
        LOWORD(v54->lpVtbl) = 0;
        if ( v47 )
        {
          for ( j = 0; ; ++j )
          {
            v80 = v53[j];
            v81 = &v53[j];
            if ( !v80 )
              goto LABEL_155;
            if ( v80 == 47 )
              break;
            if ( v80 == 92 )
            {
              v116 = ATL::CComBSTR::Append((Microsoft::Resources::Runtime::CMrtUriParser *)((char *)v2 + 8), L"/");
              v56 = v116;
              if ( v116 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2C2,
                  (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
                  (const char *)(unsigned int)v116,
                  (int)v123);
                wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&ppURI);
                goto LABEL_192;
              }
              ATL::CComBSTR::Append((Microsoft::Resources::Runtime::CMrtUriParser *)((char *)v2 + 8), v81 + 1);
LABEL_146:
              *v81 = 0;
              do
                ++v15;
              while ( v53[v15] );
              v89 = (const void **)v130;
              if ( *(_QWORD *)v130 )
                v90 = SysStringLen(*(BSTR *)v130);
              else
                v90 = 0;
              v91 = v90 + v15;
              if ( v90 + (int)v15 >= v90 )
              {
                v92 = SysAllocStringLen(0, v91);
                v93 = v92;
                if ( v92 )
                {
                  if ( *v89 )
                    memcpy_0(v92, *v89, 2LL * v90);
                  memcpy_0(&v93[v90], v53, 2LL * (int)v15);
                  v93[v91] = 0;
                  SysFreeString((BSTR)*v89);
                  *v89 = v93;
                }
              }
LABEL_155:
              operator delete(v53, v51);
              goto LABEL_65;
            }
          }
          v82 = -1;
          do
            ++v82;
          while ( v81[v82] );
          v83 = (OLECHAR *)*((_QWORD *)v2 + 1);
          if ( v83 )
            v84 = SysStringLen(v83);
          else
            v84 = 0;
          v85 = v84 + v82;
          if ( v84 + (int)v82 >= v84 )
          {
            v86 = SysAllocStringLen(0, v85);
            v87 = v86;
            if ( v86 )
            {
              v88 = (const void *)*((_QWORD *)v2 + 1);
              if ( v88 )
                memcpy_0(v86, v88, 2LL * v84);
              memcpy_0(&v87[v84], v81, 2LL * (int)v82);
              v87[v85] = 0;
              SysFreeString(*((BSTR *)v2 + 1));
              *((_QWORD *)v2 + 1) = v87;
              v53 = Src;
              goto LABEL_146;
            }
            v53 = Src;
          }
          v56 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2BE,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
            (const char *)0x8007000ELL,
            (int)v123);
          operator delete(v53, v103);
          goto LABEL_192;
        }
LABEL_86:
        v56 = v55;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B5,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)(unsigned int)v55,
          (int)v123);
        operator delete(v53, v57);
        if ( v55 >= 0 )
        {
LABEL_65:
          v38 = v130;
          v39 = (OLECHAR *)*((_QWORD *)v130 + 1);
          if ( v39 )
            v40 = SysStringLen(v39);
          else
            v40 = 0;
          v41 = (unsigned __int16 *)*((_QWORD *)v38 + 1);
          v42 = (Microsoft::Resources::Runtime::CMrtUriParser *)v40;
          v43 = 0;
          v130 = v42;
          while ( v41[v43] != 37 )
          {
            if ( ++v43 >= (unsigned __int64)v42 )
              return 0;
          }
          if ( __TSS0__4___DecodePathInPlace_CMrtUriParser_Runtime_Resources_Microsoft__AEAAJPEAGPEA_K_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 8LL) )
          {
            Init_thread_header(&__TSS0__4___DecodePathInPlace_CMrtUriParser_Runtime_Resources_Microsoft__AEAAJPEAGPEA_K_Z_4HA);
            if ( __TSS0__4___DecodePathInPlace_CMrtUriParser_Runtime_Resources_Microsoft__AEAAJPEAGPEA_K_Z_4HA == -1 )
            {
              `Microsoft::Resources::Runtime::CMrtUriParser::_DecodePathInPlace'::`5'::DecodingFlags = 2;
              Init_thread_footer(&__TSS0__4___DecodePathInPlace_CMrtUriParser_Runtime_Resources_Microsoft__AEAAJPEAGPEA_K_Z_4HA);
            }
          }
          v128[1] = v41;
          v128[0] = &`Microsoft::Resources::Runtime::CMrtUriParser::_DecodePathInPlace'::`5'::CPercentEncodingForMrtReference::`vftable';
          v128[2] = v42;
          v74 = CPercentDecodeString::Decode(
                  (CPercentDecodeString *)v128,
                  v41,
                  (unsigned __int64 *)&v130,
                  v32,
                  v123,
                  v126);
          v30 = v74;
          if ( v74 >= 0 )
            return 0;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x302,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
            (const char *)(unsigned int)v74,
            v124);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x111,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
            (const char *)v30,
            v125);
          return v30;
        }
LABEL_192:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)v56,
          (int)v123);
        return v56;
      }
      v55 = -2147024809;
      LOWORD(v50->lpVtbl) = 0;
    }
    else
    {
      v55 = -2147024809;
    }
    v53 = v50;
    goto LABEL_86;
  }
  v16 = (__int64 *)*((_QWORD *)v130 + 3);
  v17 = a2 + 12;
  if ( v8 != 2 )
    v17 = a2;
  v18 = *v16;
  if ( !*v16
    || !*(_QWORD *)v18 && *(_DWORD *)(v18 + 8)
    || !*(_DWORD *)(v18 + 8) && *(_QWORD *)v18
    || (v19 = *(_QWORD *)(v18 + 16)) == 0 )
  {
    v30 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x8007139FLL,
      (int)v123);
    goto LABEL_250;
  }
  v20 = (_WORD *)(v19 + 28);
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  v22 = v21 + 1;
  v23 = 2 * v22;
  if ( !is_mul_ok(v22, 2u) )
    v23 = -1;
  v24 = (IUri *)operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
  v25 = v24;
  if ( !v24 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B3,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x8007000ELL,
      (int)v123);
    v30 = -2147024882;
    goto LABEL_54;
  }
  memset_0(v24, 0, v23);
  ppURI = v25;
  if ( !v22 )
  {
    v30 = -2147024809;
    goto LABEL_249;
  }
  if ( v22 > 0x7FFFFFFF )
  {
    v30 = -2147024809;
    LOWORD(v25->lpVtbl) = 0;
LABEL_249:
    v28 = (char *)v25;
    goto LABEL_53;
  }
  v27 = 2147483646;
  Src = v25;
  v28 = (char *)v25;
  do
  {
    if ( !v27 )
      break;
    if ( !*v20 )
      break;
    LOWORD(v25->lpVtbl) = *v20++;
    v25 = (IUri *)((char *)v25 + 2);
    --v27;
    --v22;
  }
  while ( v22 );
  v29 = (IUri *)((char *)v25 - 2);
  v30 = -2147024774;
  if ( v22 )
  {
    v29 = v25;
    v30 = 0;
  }
  LOWORD(v29->lpVtbl) = 0;
  if ( !v22 )
  {
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)v30,
      (int)v123);
    operator delete(v28, v31);
    goto LABEL_54;
  }
  for ( k = 0; ; ++k )
  {
    v59 = (const unsigned __int16 *)&v28[2 * k];
    v60 = *v59;
    if ( !*v59 )
      goto LABEL_113;
    if ( v60 == 47 || v60 == 92 )
      break;
  }
  v61 = v130;
  if ( v60 == 47 )
  {
    v62 = -1;
    do
      ++v62;
    while ( v59[v62] );
    v63 = (OLECHAR *)*((_QWORD *)v130 + 1);
    if ( v63 )
      v64 = SysStringLen(v63);
    else
      v64 = 0;
    v65 = v64 + v62;
    if ( v64 + (int)v62 >= v64 )
    {
      v66 = SysAllocStringLen(0, v65);
      if ( v66 )
      {
        v67 = (const void *)*((_QWORD *)v130 + 1);
        if ( v67 )
          memcpy_0(v66, v67, 2LL * v64);
        memcpy_0(&v66[v64], v59, 2LL * (int)v62);
        v68 = (BSTR *)v130;
        v66[v65] = 0;
        SysFreeString(v68[1]);
        v28 = (char *)Src;
        v68[1] = v66;
        goto LABEL_104;
      }
    }
    v105 = Src;
    v30 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BE,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x8007000ELL,
      (int)v123);
    operator delete(v105, v106);
  }
  else
  {
    v117 = ATL::CComBSTR::Append((Microsoft::Resources::Runtime::CMrtUriParser *)((char *)v130 + 8), L"/");
    v30 = v117;
    if ( v117 >= 0 )
    {
      ATL::CComBSTR::Append((Microsoft::Resources::Runtime::CMrtUriParser *)((char *)v61 + 8), v59 + 1);
      v68 = (BSTR *)v130;
LABEL_104:
      v69 = -1;
      *v59 = 0;
      do
        ++v69;
      while ( *(_WORD *)&v28[2 * v69] );
      if ( *v68 )
        v70 = SysStringLen(*v68);
      else
        v70 = 0;
      v71 = v70 + v69;
      if ( v70 + (int)v69 >= v70 )
      {
        v72 = SysAllocStringLen(0, v71);
        if ( v72 )
        {
          if ( *(_QWORD *)v130 )
            memcpy_0(v72, *(const void **)v130, 2LL * v70);
          memcpy_0(&v72[v70], v28, 2LL * (int)v69);
          v73 = (BSTR *)v130;
          v72[v71] = 0;
          SysFreeString(*v73);
          *v73 = v72;
        }
      }
LABEL_113:
      operator delete(v28, v26);
      v30 = 0;
      goto LABEL_54;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C2,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)(unsigned int)v117,
      (int)v123);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&ppURI);
  }
LABEL_54:
  if ( (v30 & 0x80000000) == 0 )
  {
    v33 = (BSTR *)((char *)v130 + 8);
    goto LABEL_56;
  }
LABEL_250:
  v118 = v130;
  v119 = Microsoft::Resources::Runtime::CMrtUriParser::GetBaseIUri(v130);
  v120 = v119;
  if ( !v119 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)v30,
      (int)v123);
    return v30;
  }
  v121 = ((__int64 (__fastcall *)(struct IUri *, BSTR *))v119->lpVtbl->GetHost)(v119, &pbstr);
  v30 = v121;
  if ( v121 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)(unsigned int)v121,
      (int)v123);
    return v30;
  }
  *(_QWORD *)v118 = pbstr;
  v122 = ((__int64 (__fastcall *)(struct IUri *, BSTR *))v120->lpVtbl->GetPath)(v120, &pbstr);
  v30 = v122;
  if ( v122 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)(unsigned int)v122,
      (int)v123);
    return v30;
  }
  v109 = pbstr;
  v33 = (BSTR *)((char *)v118 + 8);
  *((_QWORD *)v118 + 1) = pbstr;
  if ( v109 )
    v110 = SysStringLen(v109);
  else
    v110 = 0;
  if ( v109[v110 - 1] != 47 )
  {
    v111 = *v33;
    v112 = *v33 ? SysStringLen(*v33) : 0;
    if ( v111[v112 - 1] != 92 )
    {
      v113 = ATL::CComBSTR::Append((Microsoft::Resources::Runtime::CMrtUriParser *)((char *)v118 + 8), L"/");
      v30 = v113;
      if ( v113 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)(unsigned int)v113,
          (int)v123);
        return v30;
      }
    }
  }
LABEL_56:
  if ( !v17 )
    goto LABEL_65;
  do
    ++v15;
  while ( v17[v15] );
  if ( *v33 )
    v34 = SysStringLen(*v33);
  else
    v34 = 0;
  v35 = v34 + v15;
  if ( v34 + (int)v15 >= v34 )
  {
    v36 = SysAllocStringLen(0, v35);
    v37 = v36;
    if ( v36 )
    {
      if ( *v33 )
        memcpy_0(v36, *v33, 2LL * v34);
      memcpy_0(&v37[v34], v17, 2LL * (int)v15);
      v37[v35] = 0;
      SysFreeString(*v33);
      *v33 = v37;
      goto LABEL_65;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10C,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
    (const char *)0x8007000ELL,
    (int)v123);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002eef0  mov     [rsp-28h+arg_0], rcx
0x18002eef5  push    rbp
0x18002eef6  push    rbx
0x18002eef7  push    rsi
0x18002eef8  push    r13
0x18002eefa  push    r14
0x18002eefc  mov     rbp, rsp
0x18002eeff  sub     rsp, 80h
0x18002ef06  mov     r13, rcx
0x18002ef09  mov     rbx, rdx
0x18002ef0c  mov     rcx, [rcx+28h]
0x18002ef10  test    rcx, rcx
0x18002ef13  jnz     loc_18002FBE8
0x18002ef19  xor     r8b, r8b
0x18002ef1c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ef23  xor     edx, edx
0x18002ef25  inc     rcx
0x18002ef28  cmp     [rbx+rcx*2], dx
0x18002ef2c  jnz     short loc_18002EF25
0x18002ef2e  mov     esi, 1
0x18002ef33  mov     r10, 200000000801h
0x18002ef3d  nop     dword ptr [rax]
0x18002ef40  cmp     word ptr [rbx+rdx*2], 2Eh ; '.'
0x18002ef45  jz      loc_18002F591
0x18002ef4b  inc     rdx
0x18002ef4e  cmp     rdx, rcx
0x18002ef51  jb      short loc_18002EF40
0x18002ef53  mov     [rsp+80h+var_8], rdi
0x18002ef58  mov     [rsp+80h+var_10], r12
0x18002ef5d  mov     [rsp+80h+var_18], r15
0x18002ef62  test    r8b, r8b
0x18002ef65  jnz     loc_18002F5DA
0x18002ef6b  xor     r15d, r15d
0x18002ef6e  xor     r12b, r12b
0x18002ef71  xor     edi, edi
0x18002ef73  mov     r13d, 0A1h
0x18002ef79  mov     r14d, 0D75Dh
0x18002ef7f  mov     r8d, 6FFh
0x18002ef85  mov     r9d, 4CDh
0x18002ef8b  mov     r11d, 0FDF0h
0x18002ef91  mov     r10d, 0FFEFh
0x18002ef97  nop     word ptr [rax+rax+00000000h]
0x18002efa0  movsxd  rdx, edi
0x18002efa3  movzx   ecx, word ptr [rbx+rdx*2]
0x18002efa7  lea     eax, [rcx-61h]
0x18002efaa  cmp     ax, 19h
0x18002efae  jbe     short loc_18002F025
0x18002efb0  cmp     cx, 41h ; 'A'
0x18002efb4  jnb     loc_18002FC18
0x18002efba  cmp     cx, 30h ; '0'
0x18002efbe  jnb     loc_18002FC27
0x18002efc4  cmp     cx, 2Dh ; '-'
0x18002efc8  jz      short loc_18002F025
0x18002efca  movzx   eax, cx
0x18002efcd  sub     ax, r13w
0x18002efd1  cmp     ax, r14w
0x18002efd5  jbe     short loc_18002F025
0x18002efd7  cmp     cx, 7Eh ; '~'
0x18002efdb  jz      short loc_18002F025
0x18002efdd  cmp     cx, 5Fh ; '_'
0x18002efe1  jz      short loc_18002F025
0x18002efe3  cmp     cx, 2Eh ; '.'
0x18002efe7  jz      short loc_18002F025
0x18002efe9  lea     eax, [r8+rcx]
0x18002efed  cmp     ax, r9w
0x18002eff1  jbe     short loc_18002F025
0x18002eff3  cmp     cx, r11w
0x18002eff7  jbe     short loc_18002F001
0x18002eff9  cmp     cx, r10w
0x18002effd  jb      short loc_18002F025
0x18002efff  jmp     short loc_18002F020
0x18002f001  cmp     cx, 2Fh ; '/'
0x18002f005  jnz     loc_18002F79D
0x18002f00b  test    edi, edi
0x18002f00d  jz      short loc_18002F020
0x18002f00f  cmp     edi, 0Ch
0x18002f012  jz      loc_18002F7F7
0x18002f018  cmp     word ptr [rbx+rdx*2+2], 2Fh ; '/'
0x18002f01e  jnz     short loc_18002F025
0x18002f020  mov     esi, 4
0x18002f025  inc     edi
0x18002f027  mov     r8d, 6FFh
0x18002f02d  movsxd  rcx, edi
0x18002f030  mov     r9d, 4CDh
0x18002f036  mov     r10d, 0FFEFh
0x18002f03c  mov     r11d, 0FDF0h
0x18002f042  cmp     word ptr [rbx+rcx*2], 0
0x18002f047  jnz     loc_18002EFA0
0x18002f04d  mov     r13, [rbp+arg_0]
0x18002f051  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002f058  test    r15d, r15d
0x18002f05b  js      loc_18002F8C0
0x18002f061  mov     [rbp+pbstr], 0
0x18002f069  cmp     esi, 5
0x18002f06c  jz      loc_18002FD71
0x18002f072  cmp     esi, 4
0x18002f075  jz      loc_18002F8E0
0x18002f07b  cmp     esi, 3
0x18002f07e  jz      loc_18002F29C
0x18002f084  mov     rax, [r13+18h]
0x18002f088  lea     r15, [rbx+18h]
0x18002f08c  cmp     esi, 2
0x18002f08f  cmovnz  r15, rbx
0x18002f093  mov     rcx, [rax]
0x18002f096  test    rcx, rcx
0x18002f099  jz      loc_18002F86A
0x18002f09f  mov     rdx, [rcx]
0x18002f0a2  test    rdx, rdx
0x18002f0a5  jnz     short loc_18002F0B0
0x18002f0a7  cmp     [rcx+8], edx
0x18002f0aa  ja      loc_18002F86A
0x18002f0b0  cmp     dword ptr [rcx+8], 0
0x18002f0b4  jnz     short loc_18002F0BF
0x18002f0b6  test    rdx, rdx
0x18002f0b9  jnz     loc_18002F86A
0x18002f0bf  mov     rbx, [rcx+10h]
0x18002f0c3  test    rbx, rbx
0x18002f0c6  jz      loc_18002F86A
0x18002f0cc  add     rbx, 1Ch
0x18002f0d0  mov     rsi, r14
0x18002f0d3  inc     rsi
0x18002f0d6  cmp     word ptr [rbx+rsi*2], 0
0x18002f0db  jnz     short loc_18002F0D3
0x18002f0dd  inc     rsi
0x18002f0e0  mov     eax, 2
0x18002f0e5  mul     rsi
0x18002f0e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f0ef  mov     r12, rax
0x18002f0f2  cmovb   r12, r14
0x18002f0f6  mov     rcx, r12; unsigned __int64
0x18002f0f9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002f0fe  mov     rdi, rax
0x18002f101  test    rax, rax
0x18002f104  jz      loc_18002FD49
0x18002f10a  mov     r8, r12; Size
0x18002f10d  xor     edx, edx; Val
0x18002f10f  mov     rcx, rax; void *
0x18002f112  call    memset_0
0x18002f117  mov     [rbp+ppURI], rdi
0x18002f11b  test    rsi, rsi
0x18002f11e  jz      loc_18002FD36
0x18002f124  cmp     rsi, 7FFFFFFFh
0x18002f12b  ja      loc_18002FCE6
0x18002f131  mov     eax, 7FFFFFFEh
0x18002f136  mov     [rbp+Src], rdi
0x18002f13a  mov     r13, rdi
0x18002f13d  nop     dword ptr [rax]
0x18002f140  test    rax, rax
0x18002f143  jz      short loc_18002F161
0x18002f145  movzx   ecx, word ptr [rbx]
0x18002f148  test    cx, cx
0x18002f14b  jz      short loc_18002F161
0x18002f14d  mov     [rdi], cx
0x18002f150  add     rbx, 2
0x18002f154  add     rdi, 2
0x18002f158  dec     rax
0x18002f15b  sub     rsi, 1
0x18002f15f  jnz     short loc_18002F140
0x18002f161  test    rsi, rsi
0x18002f164  lea     rcx, [rdi-2]
0x18002f168  mov     ebx, 8007007Ah
0x18002f16d  cmovnz  rcx, rdi
0x18002f171  xor     eax, eax
0x18002f173  test    rsi, rsi
0x18002f176  cmovnz  ebx, eax
0x18002f179  mov     [rcx], ax
0x18002f17c  jnz     loc_18002F388
0x18002f182  mov     rcx, [rbp+28h]; this
0x18002f186  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18002f18d  mov     r9d, ebx; char *
0x18002f190  mov     edx, 2B5h; void *
0x18002f195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f19a  mov     rcx, r13; void *
0x18002f19d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f1a2  mov     r13d, 8007000Eh
0x18002f1a8  test    ebx, ebx
0x18002f1aa  js      loc_1800C1923
0x18002f1b0  mov     r12, [rbp+arg_0]
0x18002f1b4  add     r12, 8
0x18002f1b8  test    r15, r15
0x18002f1bb  jz      loc_18002F246
0x18002f1c1  inc     r14
0x18002f1c4  cmp     word ptr [r15+r14*2], 0
0x18002f1ca  jnz     short loc_18002F1C1
0x18002f1cc  mov     rcx, [r12]; pbstr
0x18002f1d0  test    rcx, rcx
0x18002f1d3  jz      loc_18002F381
0x18002f1d9  call    cs:__imp_SysStringLen
0x18002f1df  mov     ebx, eax
0x18002f1e1  lea     esi, [rbx+r14]
0x18002f1e5  cmp     esi, ebx
0x18002f1e7  jl      loc_18002F892
0x18002f1ed  mov     edx, esi; ui
0x18002f1ef  xor     ecx, ecx; strIn
0x18002f1f1  call    cs:__imp_SysAllocStringLen
0x18002f1f7  mov     rdi, rax
0x18002f1fa  test    rax, rax
0x18002f1fd  jz      loc_18002F892
0x18002f203  mov     rdx, [r12]; Src
0x18002f207  test    rdx, rdx
0x18002f20a  jz      short loc_18002F21A
0x18002f20c  movsxd  r8, ebx
0x18002f20f  mov     rcx, rax; void *
0x18002f212  add     r8, r8; Size
0x18002f215  call    memcpy_0
0x18002f21a  movsxd  rax, ebx
0x18002f21d  mov     rdx, r15; Src
0x18002f220  movsxd  r8, r14d
0x18002f223  add     r8, r8; Size
0x18002f226  lea     rcx, [rdi+rax*2]; void *
0x18002f22a  call    memcpy_0
0x18002f22f  movsxd  rcx, esi
0x18002f232  xor     eax, eax
0x18002f234  mov     [rdi+rcx*2], ax
0x18002f238  mov     rcx, [r12]; bstrString
0x18002f23c  call    cs:__imp_SysFreeString
0x18002f242  mov     [r12], rdi
0x18002f246  mov     r14, [rbp+arg_0]
0x18002f24a  mov     rcx, [r14+8]; pbstr
0x18002f24e  test    rcx, rcx
0x18002f251  jz      short loc_18002F298
0x18002f253  call    cs:__imp_SysStringLen
0x18002f259  mov     rdi, [r14+8]
0x18002f25d  mov     ebx, eax
0x18002f25f  xor     eax, eax
0x18002f261  mov     [rbp+arg_0], rbx
0x18002f265  cmp     word ptr [rdi+rax*2], 25h ; '%'
0x18002f26a  jz      loc_18002F508
0x18002f270  inc     rax
0x18002f273  cmp     rax, rbx
0x18002f276  jb      short loc_18002F265
0x18002f278  xor     eax, eax
0x18002f27a  mov     r15, [rsp+80h+var_18]
0x18002f27f  mov     r12, [rsp+80h+var_10]
0x18002f284  mov     rdi, [rsp+80h+var_8]
0x18002f289  add     rsp, 80h
0x18002f290  pop     r14
0x18002f292  pop     r13
0x18002f294  pop     rsi
0x18002f295  pop     rbx
0x18002f296  pop     rbp
0x18002f297  retn
0x18002f298  xor     eax, eax
0x18002f29a  jmp     short loc_18002F259
0x18002f29c  add     rbx, 1Ch
0x18002f2a0  mov     rsi, r14
0x18002f2a3  inc     rsi
0x18002f2a6  cmp     word ptr [rbx+rsi*2], 0
0x18002f2ab  jnz     short loc_18002F2A3
0x18002f2ad  inc     rsi
0x18002f2b0  mov     eax, 2
0x18002f2b5  mul     rsi
0x18002f2b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f2bf  mov     r15, rax
0x18002f2c2  cmovb   r15, r14
0x18002f2c6  mov     rcx, r15; unsigned __int64
0x18002f2c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002f2ce  mov     rdi, rax
0x18002f2d1  test    rax, rax
0x18002f2d4  jz      loc_18002FCC4
0x18002f2da  mov     r8, r15; Size
0x18002f2dd  xor     edx, edx; Val
0x18002f2df  mov     rcx, rax; void *
0x18002f2e2  call    memset_0
0x18002f2e7  mov     [rbp+ppURI], rdi
0x18002f2eb  test    rsi, rsi
0x18002f2ee  jz      loc_18002FCB1
0x18002f2f4  cmp     rsi, 7FFFFFFFh
0x18002f2fb  ja      loc_18002FC67
0x18002f301  mov     eax, 7FFFFFFEh
0x18002f306  mov     [rbp+Src], rdi
0x18002f30a  mov     r15, rdi
0x18002f30d  nop     dword ptr [rax]
0x18002f310  test    rax, rax
0x18002f313  jz      short loc_18002F331
0x18002f315  movzx   ecx, word ptr [rbx]
0x18002f318  test    cx, cx
0x18002f31b  jz      short loc_18002F331
0x18002f31d  mov     [rdi], cx
0x18002f320  add     rbx, 2
0x18002f324  add     rdi, 2
0x18002f328  dec     rax
0x18002f32b  sub     rsi, 1
0x18002f32f  jnz     short loc_18002F310
0x18002f331  test    rsi, rsi
0x18002f334  lea     rcx, [rdi-2]
0x18002f338  mov     ebx, 8007007Ah
0x18002f33d  cmovnz  rcx, rdi
0x18002f341  xor     eax, eax
0x18002f343  test    rsi, rsi
0x18002f346  cmovnz  ebx, eax
0x18002f349  mov     [rcx], ax
0x18002f34c  jnz     loc_18002F649
0x18002f352  mov     rcx, [rbp+28h]; this
0x18002f356  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x18002f35d  mov     r9d, ebx; char *
0x18002f360  mov     edx, 2B5h; void *
0x18002f365  mov     edi, ebx
0x18002f367  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f36c  mov     rcx, r15; void *
  ... truncated ...
```
