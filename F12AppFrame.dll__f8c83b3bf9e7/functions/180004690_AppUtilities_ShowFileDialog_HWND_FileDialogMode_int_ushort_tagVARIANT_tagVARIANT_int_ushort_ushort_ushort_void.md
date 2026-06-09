# AppUtilities::ShowFileDialog(HWND__ *,FileDialogMode,int,ushort *,tagVARIANT *,tagVARIANT *,int *,ushort * *,ushort * *,ushort * *,void * *)

- ea: `0x180004690`
- end: `0x1800055df`
- name: `?ShowFileDialog@AppUtilities@@UEAAJPEAUHWND__@@W4FileDialogMode@@HPEAGPEAUtagVARIANT@@3PEAHPEAPEAG55PEAPEAX@Z`
- size: `3919`
- prototype: `__int64 __fastcall(__int64, HWND, int, int, void *, VARIANTARG *, VARIANTARG *, int *, BSTR *, BSTR *, BSTR *, _QWORD *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001800`
- `0x1800029dc`
- `0x180002b60`
- `0x180002d44`
- `0x18000306c`
- `0x1800030dc`
- `0x1800031a4`
- `0x180003538`
- `0x180003858`
- `0x180003b94`
- `0x180003c38`
- `0x180003db0`
- `0x1800045b4`
- `0x180004690`
- `0x1800055e8`
- `0x18002e670`
- `0x18002f108`
- `0x180032aa4`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180004a9b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180004a9b`
- `KERNEL32!FreeLibrary` at `0x180004bad`
- `KERNEL32!FreeLibrary` at `0x180004c8a`
- `KERNEL32!FreeLibrary` at `0x180004bad`
- `KERNEL32!FreeLibrary` at `0x180004c8a`
- `KERNEL32!GetProcAddress` at `0x180004b60`
- `KERNEL32!GetProcAddress` at `0x180004c69`
- `KERNEL32!GetProcAddress` at `0x180004b60`
- `KERNEL32!GetProcAddress` at `0x180004c69`
- `KERNEL32!LoadLibraryExW` at `0x180004b48`
- `KERNEL32!LoadLibraryExW` at `0x180004c4d`
- `KERNEL32!LoadLibraryExW` at `0x180004b48`
- `KERNEL32!LoadLibraryExW` at `0x180004c4d`
- `ole32!CoCreateInstance` at `0x180004e0e`
- `ole32!CoCreateInstance` at `0x18000517e`
- `ole32!CoCreateInstance` at `0x180004e0e`
- `ole32!CoCreateInstance` at `0x18000517e`
- `ole32!CoTaskMemFree` at `0x180004c37`
- `ole32!CoTaskMemFree` at `0x180004cc2`
- `ole32!CoTaskMemFree` at `0x180004f4e`
- `ole32!CoTaskMemFree` at `0x180005298`
- `ole32!CoTaskMemFree` at `0x180004c37`
- `ole32!CoTaskMemFree` at `0x180004cc2`
- `ole32!CoTaskMemFree` at `0x180004f4e`
- `ole32!CoTaskMemFree` at `0x180005298`
- `OLEAUT32!__imp_SysAllocString` at `0x18000535f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000535f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005372`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000539a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180005372`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000539a`
- `OLEAUT32!__imp_VariantInit` at `0x180004778`
- `OLEAUT32!__imp_VariantInit` at `0x1800047ff`
- `OLEAUT32!__imp_VariantInit` at `0x180004778`
- `OLEAUT32!__imp_VariantInit` at `0x1800047ff`
- `OLEAUT32!__imp_VariantClear` at `0x180004787`
- `OLEAUT32!__imp_VariantClear` at `0x1800047bd`
- `OLEAUT32!__imp_VariantClear` at `0x1800047e9`
- `OLEAUT32!__imp_VariantClear` at `0x18000480e`
- `OLEAUT32!__imp_VariantClear` at `0x180004844`
- `OLEAUT32!__imp_VariantClear` at `0x180004870`
- `OLEAUT32!__imp_VariantClear` at `0x180005578`
- `OLEAUT32!__imp_VariantClear` at `0x180005593`
- `OLEAUT32!__imp_VariantClear` at `0x180004787`
- `OLEAUT32!__imp_VariantClear` at `0x1800047bd`
- `OLEAUT32!__imp_VariantClear` at `0x1800047e9`
- `OLEAUT32!__imp_VariantClear` at `0x18000480e`
- `OLEAUT32!__imp_VariantClear` at `0x180004844`
- `OLEAUT32!__imp_VariantClear` at `0x180004870`
- `OLEAUT32!__imp_VariantClear` at `0x180005578`
- `OLEAUT32!__imp_VariantClear` at `0x180005593`
- `USER32!GetAncestor` at `0x18000475e`
- `USER32!GetAncestor` at `0x18000475e`

## string_xrefs

- `0x180004b41`: `ieframe.dll`
- `0x180004c46`: `ieframe.dll`
- `0x180004c5f`: `IEGetWriteableFolderPath`

## pseudocode

```c
__int64 __fastcall AppUtilities::ShowFileDialog(
        __int64 a1,
        HWND a2,
        int a3,
        int a4,
        void *a5,
        VARIANTARG *a6,
        VARIANTARG *a7,
        int *a8,
        BSTR *a9,
        BSTR *a10,
        BSTR *a11,
        _QWORD *a12)
{
  HRESULT VectorFromScriptArray; // esi
  unsigned __int64 v14; // rcx
  OLECHAR *v15; // r14
  unsigned __int64 v16; // r15
  __int64 v17; // rcx
  const wchar_t *v18; // rbx
  void *v19; // rcx
  OLECHAR *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // r13
  OLECHAR *v23; // rbx
  int v24; // r15d
  OLECHAR *v25; // rdi
  int v26; // r15d
  HMODULE Library; // rax
  HMODULE v28; // r12
  FARPROC ProcAddress; // rax
  __int64 v30; // r8
  OLECHAR *v31; // rdx
  HMODULE v32; // rax
  HMODULE v33; // rbx
  FARPROC v34; // rax
  __int64 v35; // r8
  __int64 v36; // rbx
  _QWORD *v37; // rdx
  volatile signed __int32 *v38; // rdx
  volatile signed __int32 *v39; // rdx
  HRESULT v40; // eax
  __int64 v41; // r8
  OLECHAR *v42; // rdx
  HRESULT v43; // eax
  __int64 v44; // r8
  __int64 v45; // rax
  BSTR v46; // rax
  BSTR v47; // rax
  UINT v48; // edx
  const OLECHAR *v49; // rcx
  BSTR v50; // rax
  OLECHAR *strIn; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v53; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v55; // [rsp+68h] [rbp-98h] BYREF
  __int64 v56; // [rsp+70h] [rbp-90h] BYREF
  int v57; // [rsp+78h] [rbp-88h]
  int v58; // [rsp+7Ch] [rbp-84h] BYREF
  __int128 v59; // [rsp+80h] [rbp-80h] BYREF
  __int64 v60; // [rsp+90h] [rbp-70h]
  __int128 v61; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  LPVOID Ancestor; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v64; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID v67; // [rsp+D8h] [rbp-28h] BYREF
  LPVOID v68; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v69; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v70; // [rsp+F8h] [rbp-8h]
  LPVOID pv[2]; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG v72; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG pvarg; // [rsp+128h] [rbp+28h] BYREF
  int *v74; // [rsp+140h] [rbp+40h]
  BSTR *v75; // [rsp+148h] [rbp+48h]
  BSTR *v76; // [rsp+150h] [rbp+50h]
  BSTR *v77; // [rsp+158h] [rbp+58h]
  char v78[528]; // [rsp+160h] [rbp+60h] BYREF

  v58 = a4;
  v68 = a5;
  v74 = a8;
  v75 = a9;
  v76 = a10;
  v77 = a11;
  v67 = a12;
  if ( !a8 )
    return 2147942487LL;
  *a8 = 0;
  if ( !a9 )
    return 2147942487LL;
  *a9 = 0;
  if ( !a10 )
    return 2147942487LL;
  *a10 = 0;
  if ( !a11 )
    return 2147942487LL;
  *a11 = 0;
  if ( !a12 )
    return 2147942487LL;
  *a12 = 0;
  Ancestor = GetAncestor(a2, 2u);
  v69 = 0;
  v70 = 0;
  VariantInit(&pvarg);
  if ( a6 && VariantClear(&pvarg) >= 0 )
  {
    *(_OWORD *)&pvarg.vt = *(_OWORD *)&a6->vt;
    pvarg.pRecInfo = a6->pRecInfo;
    a6->vt = 0;
  }
  VectorFromScriptArray = ScriptHelpers::GetVectorFromScriptArray(&pvarg, &v69);
  if ( a6 && VariantClear(a6) >= 0 )
  {
    *a6 = pvarg;
    pvarg.vt = 0;
  }
  if ( VectorFromScriptArray )
  {
    if ( VectorFromScriptArray >= 0 )
      VectorFromScriptArray = -2147467259;
    VariantClear(&pvarg);
    goto LABEL_231;
  }
  VariantClear(&pvarg);
  v59 = 0;
  v60 = 0;
  VariantInit(&v72);
  if ( a7 && VariantClear(&v72) >= 0 )
  {
    *(_OWORD *)&v72.vt = *(_OWORD *)&a7->vt;
    v72.pRecInfo = a7->pRecInfo;
    a7->vt = 0;
  }
  VectorFromScriptArray = ScriptHelpers::GetVectorFromScriptArray(&v72, &v59);
  if ( a7 && VariantClear(a7) >= 0 )
  {
    *a7 = v72;
    v72.vt = 0;
  }
  if ( VectorFromScriptArray )
  {
    if ( VectorFromScriptArray >= 0 )
      VectorFromScriptArray = -2147467259;
    VariantClear(&v72);
    goto LABEL_227;
  }
  VariantClear(&v72);
  v14 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v69 + 1) - v69) >> 3);
  if ( v14 != 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) || !v14 )
  {
LABEL_53:
    std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(&v59);
    VectorFromScriptArray = -2147024809;
    goto LABEL_231;
  }
  v61 = 0;
  v62 = 0;
  v64 = 0;
  v65 = 0;
  v15 = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  strIn = v15;
  v16 = 0;
  v17 = v69;
  if ( !(0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v69 + 1) - v69) >> 3)) )
    goto LABEL_38;
  do
  {
    if ( *(_WORD *)(v59 + 24 * v16) != 8
      || *(_WORD *)(v17 + 24 * v16) != 8
      || (v18 = *(const wchar_t **)(v17 + 24 * v16 + 8), wcscmp_0(v18, L"UTF-8"))
      && wcscmp_0(v18, L"UTF-16LE")
      && wcscmp_0(v18, L"BINARY") )
    {
      v31 = strIn - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)strIn - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 8LL))(*(_QWORD *)v31);
      std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v64);
      std::vector<_COMDLG_FILTERSPEC>::~vector<_COMDLG_FILTERSPEC>(&v61);
      goto LABEL_53;
    }
    v53 = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v53,
      L"*.%s",
      *(_QWORD *)(v59 + 24 * v16 + 8));
    if ( *((_QWORD *)&v64 + 1) == v65 )
    {
      std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::_Emplace_reallocate<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const &>(
        &v64,
        *((_QWORD *)&v64 + 1),
        &v53);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        *((_QWORD *)&v64 + 1),
        &v53);
      *((_QWORD *)&v64 + 1) += 8LL;
    }
    v19 = *(void **)(v59 + 24 * v16 + 8);
    pv[0] = v19;
    v20 = v53;
    pv[1] = v53;
    v21 = *((_QWORD *)&v61 + 1);
    if ( *((_QWORD *)&v61 + 1) == v62 )
    {
      std::vector<_COMDLG_FILTERSPEC>::_Emplace_reallocate<_COMDLG_FILTERSPEC const &>(&v61, *((_QWORD *)&v61 + 1), pv);
    }
    else
    {
      **((_QWORD **)&v61 + 1) = v19;
      *(_QWORD *)(v21 + 8) = v20;
      *((_QWORD *)&v61 + 1) += 16LL;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &strIn,
      L"%s (*.%s)|*.%s|",
      *(_QWORD *)(v59 + 24 * v16 + 8),
      *(_QWORD *)(v59 + 24 * v16 + 8),
      *(_QWORD *)(v59 + 24 * v16 + 8));
    if ( _InterlockedDecrement((volatile signed __int32 *)v20 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v20 - 3) + 8LL))(*((_QWORD *)v20 - 3));
    ++v16;
    v17 = v69;
  }
  while ( v16 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v69 + 1) - v69) >> 3) );
  v15 = strIn;
LABEL_38:
  v22 = *(_QWORD *)(v59 + 8);
  _o_wcscpy_s(v78, 260, v68);
  if ( *((int *)v15 - 2) > 1 )
  {
    ATL::CSimpleStringT<unsigned short,0>::Fork(&strIn, *((unsigned int *)v15 - 4));
    v15 = strIn;
  }
  v57 = 0;
  v23 = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  strIn = v23;
  v24 = 0;
  v25 = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v53 = v25;
  if ( !a3 )
  {
    v55 = 0;
    VectorFromScriptArray = CoCreateInstance(
                              &GUID_dc1c5a9c_e88a_4dde_a5a1_60f82a20aef7,
                              0,
                              0x17u,
                              &GUID_d57c7288_d4ad_4768_be02_9d969532d960,
                              &v55);
    if ( VectorFromScriptArray )
    {
      if ( VectorFromScriptArray >= 0 )
        VectorFromScriptArray = -2147467259;
      if ( v55 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
      goto LABEL_217;
    }
    VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v55 + 32LL))(
                              v55,
                              (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 4);
    if ( VectorFromScriptArray )
    {
      if ( VectorFromScriptArray >= 0 )
        VectorFromScriptArray = -2147467259;
      if ( v55 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
      goto LABEL_217;
    }
    VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v55 + 72LL))(v55, 36866);
    if ( VectorFromScriptArray )
    {
      if ( VectorFromScriptArray >= 0 )
        VectorFromScriptArray = -2147467259;
      if ( v55 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
      goto LABEL_217;
    }
    v43 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v55 + 24LL))(v55, Ancestor);
    VectorFromScriptArray = v43;
    if ( !v43
      || v43 != -2147023673
      && (VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v55 + 24LL))(v55, 0)) == 0 )
    {
      v53 = 0;
      VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, OLECHAR **))(*(_QWORD *)v55 + 160LL))(v55, &v53);
      if ( VectorFromScriptArray )
      {
        if ( VectorFromScriptArray >= 0 )
          VectorFromScriptArray = -2147467259;
        if ( v53 )
          (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v55 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
        goto LABEL_217;
      }
      v68 = 0;
      VectorFromScriptArray = (*(__int64 (__fastcall **)(OLECHAR *, __int64, LPVOID *))(*(_QWORD *)v53 + 40LL))(
                                v53,
                                2147844096LL,
                                &v68);
      if ( VectorFromScriptArray )
      {
        if ( VectorFromScriptArray >= 0 )
          VectorFromScriptArray = -2147467259;
        if ( v53 )
          (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v55 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
        goto LABEL_217;
      }
      if ( v68 )
      {
        v44 = -1;
        do
          ++v44;
        while ( *((_WORD *)v68 + v44) );
      }
      else
      {
        v44 = 0;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(&strIn, v68, v44);
      CoTaskMemFree(v68);
      v58 = 0;
      VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v55 + 48LL))(v55, &v58);
      if ( VectorFromScriptArray )
      {
        if ( VectorFromScriptArray >= 0 )
          VectorFromScriptArray = -2147467259;
        if ( v53 )
          (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v55 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
        goto LABEL_109;
      }
      v57 = v58;
      v24 = 1;
      if ( v53 )
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v53 + 16LL))(v53);
      v23 = strIn;
    }
    if ( v55 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 16LL))(v55);
LABEL_166:
    if ( v15 )
    {
      v45 = -1;
      do
        ++v45;
      while ( v15[v45] );
      if ( (int)v45 < 0 )
        goto LABEL_233;
    }
    else
    {
      LODWORD(v45) = 0;
    }
    if ( (int)v45 <= *((_DWORD *)v15 - 3) )
    {
      *((_DWORD *)v15 - 4) = v45;
      v15[(unsigned int)v45] = 0;
      *v74 = v24;
      if ( v24 == 1 )
      {
        v46 = SysAllocString(*(const OLECHAR **)(v69 + 24LL * (unsigned int)(v57 - 1) + 8));
        *v75 = v46;
        v47 = SysAllocStringLen(v23, *((_DWORD *)v23 - 4));
        if ( !v47
          || ((*v76 = v47, (v48 = *((_DWORD *)v25 - 4)) != 0) ? (v49 = v25) : (v48 = *((_DWORD *)v23 - 4), v49 = v23),
              (v50 = SysAllocStringLen(v49, v48)) == 0) )
        {
          ATL::CSimpleStringT<char,0>::ThrowMemoryException();
        }
        *v77 = v50;
      }
      if ( _InterlockedDecrement((volatile signed __int32 *)v25 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 - 3) + 8LL))(*((_QWORD *)v25 - 3));
      v39 = (volatile signed __int32 *)(v23 - 12);
      goto LABEL_76;
    }
LABEL_233:
    ATL::AtlThrowImpl(-2147024809);
  }
  if ( a3 != 1 )
    goto LABEL_166;
  pv[0] = 0;
  if ( !v58 )
  {
    ppv = 0;
    VectorFromScriptArray = CoCreateInstance(
                              &GUID_c0b4e2f3_ba21_4773_8dba_335ec946eb8b,
                              0,
                              0x17u,
                              &GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab,
                              &ppv);
    if ( VectorFromScriptArray )
    {
      if ( VectorFromScriptArray >= 0 )
        VectorFromScriptArray = -2147467259;
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 32LL))(
                                ppv,
                                (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 4);
      if ( VectorFromScriptArray )
      {
        if ( VectorFromScriptArray >= 0 )
          VectorFromScriptArray = -2147467259;
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      else
      {
        VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 72LL))(ppv, 32770);
        if ( VectorFromScriptArray )
        {
          if ( VectorFromScriptArray >= 0 )
            VectorFromScriptArray = -2147467259;
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        else
        {
          VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 176LL))(
                                    ppv,
                                    *(_QWORD *)(v59 + 8));
          if ( VectorFromScriptArray )
          {
            if ( VectorFromScriptArray >= 0 )
              VectorFromScriptArray = -2147467259;
            if ( ppv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          else
          {
            v40 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 24LL))(ppv, Ancestor);
            VectorFromScriptArray = v40;
            if ( v40 )
            {
              if ( v40 == -2147023673
                || (VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0)) != 0 )
              {
LABEL_100:
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                goto LABEL_166;
              }
            }
            v56 = 0;
            VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 160LL))(ppv, &v56);
            if ( VectorFromScriptArray )
            {
              if ( VectorFromScriptArray >= 0 )
                VectorFromScriptArray = -2147467259;
              if ( v56 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
              if ( ppv )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            else
            {
              Ancestor = 0;
              VectorFromScriptArray = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v56 + 40LL))(
                                        v56,
                                        2147844096LL,
                                        &Ancestor);
              if ( !VectorFromScriptArray )
              {
                if ( Ancestor )
                {
                  v41 = -1;
                  do
                    ++v41;
                  while ( *((_WORD *)Ancestor + v41) );
                }
                else
                {
                  v41 = 0;
                }
                ATL::CSimpleStringT<unsigned short,0>::SetString(&strIn, Ancestor, v41);
                CoTaskMemFree(Ancestor);
                v66 = 0;
                VectorFromScriptArray = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 48LL))(ppv, &v66);
                if ( !VectorFromScriptArray )
                {
                  v57 = v66;
                  v24 = 1;
                  if ( v56 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                  v23 = strIn;
                  goto LABEL_100;
                }
                if ( VectorFromScriptArray >= 0 )
                  VectorFromScriptArray = -2147467259;
                if ( v56 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_109:
                if ( _InterlockedDecrement((volatile signed __int32 *)v25 - 2) <= 0 )
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 - 3) + 8LL))(*((_QWORD *)v25 - 3));
                v42 = strIn - 12;
                if ( _InterlockedDecrement((volatile signed __int32 *)strIn - 2) <= 0 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v42 + 8LL))(*(_QWORD *)v42);
                goto LABEL_221;
              }
              if ( VectorFromScriptArray >= 0 )
                VectorFromScriptArray = -2147467259;
              if ( v56 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
              if ( ppv )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
          }
        }
      }
    }
LABEL_217:
    if ( _InterlockedDecrement((volatile signed __int32 *)v25 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v25 - 3) + 8LL))(*((_QWORD *)v25 - 3));
    if ( _InterlockedDecrement((volatile signed __int32 *)v23 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
    goto LABEL_221;
  }
  v57 = 1;
  v26 = -2147467263;
  VectorFromScriptArray = -2147467263;
  Library = LoadLibraryExW(L"ieframe.dll", 0, 0);
  v28 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "IEShowSaveFileDialog");
    if ( ProcAddress )
      VectorFromScriptArray = ((__int64 (__fastcall *)(LPVOID, const OLECHAR *, _QWORD, OLECHAR *, __int64, int, int, LPVOID *, LPVOID))ProcAddress)(
                                Ancestor,
                                &String,
                                0,
                                v15,
                                v22,
                                1,
                                8421378,
                                pv,
                                v67);
    FreeLibrary(v28);
  }
  if ( VectorFromScriptArray )
  {
    v24 = 0;
    goto LABEL_166;
  }
  if ( pv[0] )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)pv[0] + v30) );
  }
  else
  {
    v30 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&strIn, pv[0], v30);
  CoTaskMemFree(pv[0]);
  v67 = 0;
  v32 = LoadLibraryExW(L"ieframe.dll", 0, 0);
  v33 = v32;
  if ( !v32 )
    goto LABEL_80;
  v34 = GetProcAddress(v32, "IEGetWriteableFolderPath");
  if ( v34 )
    v26 = ((__int64 (__fastcall *)(const GUID *, LPVOID *))v34)(&FOLDERID_InternetCache, &v67);
  FreeLibrary(v33);
  if ( v26 )
  {
    VectorFromScriptArray = -2147467259;
    if ( v26 >= 0 )
    {
LABEL_81:
      v38 = (volatile signed __int32 *)(v25 - 12);
      goto LABEL_73;
    }
LABEL_80:
    VectorFromScriptArray = v26;
    goto LABEL_81;
  }
  if ( v67 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_WORD *)v67 + v35) );
  }
  else
  {
    v35 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v53, v67, v35);
  CoTaskMemFree(v67);
  v56 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  VectorFromScriptArray = AppUtilities::GenerateSafeFileName(&v56);
  if ( !VectorFromScriptArray )
  {
    v24 = 1;
    v36 = v56;
    Win32Helpers::OurPathAppend(&v53, v56);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v36 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v36 - 24) + 8LL))(*(_QWORD *)(v36 - 24));
    v23 = strIn;
    v25 = v53;
    goto LABEL_166;
  }
  if ( VectorFromScriptArray >= 0 )
    VectorFromScriptArray = -2147467259;
  v37 = (_QWORD *)(v56 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v56 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v37 + 8LL))(*v37);
  v38 = (volatile signed __int32 *)(v53 - 12);
LABEL_73:
  if ( _InterlockedDecrement(v38 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 8LL))(*(_QWORD *)v38);
  v39 = (volatile signed __int32 *)(strIn - 12);
LABEL_76:
  if ( _InterlockedDecrement(v39 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v39 + 8LL))(*(_QWORD *)v39);
LABEL_221:
  if ( _InterlockedDecrement((volatile signed __int32 *)v15 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v64);
  std::vector<_COMDLG_FILTERSPEC>::~vector<_COMDLG_FILTERSPEC>(&v61);
LABEL_227:
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(&v59);
LABEL_231:
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(&v69);
  return (unsigned int)VectorFromScriptArray;
}

```

## disassembly

```asm
0x180004690  push    rbp
0x180004692  push    rbx
0x180004693  push    rsi
0x180004694  push    rdi
0x180004695  push    r12
0x180004697  push    r13
0x180004699  push    r14
0x18000469b  push    r15
0x18000469d  lea     rbp, [rsp-288h]
0x1800046a5  sub     rsp, 388h
0x1800046ac  mov     rax, cs:__security_cookie
0x1800046b3  xor     rax, rsp
0x1800046b6  mov     [rbp+2C0h+var_50], rax
0x1800046bd  mov     [rsp+3C0h+var_344], r9d
0x1800046c2  mov     r12d, r8d
0x1800046c5  mov     rax, rdx
0x1800046c8  mov     rbx, [rbp+2C0h+arg_30]
0x1800046cf  mov     rdi, [rbp+2C0h+arg_28]
0x1800046d6  mov     rcx, [rbp+2C0h+arg_20]
0x1800046dd  mov     [rbp+2C0h+var_2E0], rcx
0x1800046e1  mov     r10, [rbp+2C0h+arg_38]
0x1800046e8  mov     [rbp+2C0h+var_280], r10
0x1800046ec  mov     r9, [rbp+2C0h+arg_40]
0x1800046f3  mov     [rbp+2C0h+var_278], r9
0x1800046f7  mov     rdx, [rbp+2C0h+arg_48]
0x1800046fe  mov     [rbp+2C0h+var_270], rdx
0x180004702  mov     r8, [rbp+2C0h+arg_50]
0x180004709  mov     [rbp+2C0h+var_268], r8
0x18000470d  mov     rcx, [rbp+2C0h+arg_58]
0x180004714  mov     [rbp+2C0h+var_2E8], rcx
0x180004718  xor     r13d, r13d
0x18000471b  test    r10, r10
0x18000471e  jz      loc_1800055A6
0x180004724  mov     [r10], r13d
0x180004727  test    r9, r9
0x18000472a  jz      loc_1800055A6
0x180004730  mov     [r9], r13
0x180004733  test    rdx, rdx
0x180004736  jz      loc_1800055A6
0x18000473c  mov     [rdx], r13
0x18000473f  test    r8, r8
0x180004742  jz      loc_1800055A6
0x180004748  mov     [r8], r13
0x18000474b  test    rcx, rcx
0x18000474e  jz      loc_1800055A6
0x180004754  mov     [rcx], r13
0x180004757  lea     edx, [r13+2]; gaFlags
0x18000475b  mov     rcx, rax; hwnd
0x18000475e  call    cs:__imp_GetAncestor
0x180004764  mov     [rbp+2C0h+var_310], rax
0x180004768  xorps   xmm0, xmm0
0x18000476b  movdqu  [rbp+2C0h+var_2D8], xmm0
0x180004770  mov     [rbp+2C0h+var_2C8], r13
0x180004774  lea     rcx, [rbp+2C0h+pvarg]; pvarg
0x180004778  call    cs:__imp_VariantInit
0x18000477e  test    rdi, rdi
0x180004781  jz      short loc_1800047A6
0x180004783  lea     rcx, [rbp+2C0h+pvarg]; pvarg
0x180004787  call    cs:__imp_VariantClear
0x18000478d  test    eax, eax
0x18000478f  js      short loc_1800047A6
0x180004791  movups  xmm0, xmmword ptr [rdi]
0x180004794  movups  xmmword ptr [rbp+2C0h+pvarg], xmm0
0x180004798  movsd   xmm1, qword ptr [rdi+10h]
0x18000479d  movsd   qword ptr [rbp+2C0h+pvarg+10h], xmm1
0x1800047a2  mov     [rdi], r13w
0x1800047a6  lea     rdx, [rbp+2C0h+var_2D8]
0x1800047aa  lea     rcx, [rbp+2C0h+pvarg]
0x1800047ae  call    ?GetVectorFromScriptArray@ScriptHelpers@@YAJAEBUtagVARIANT@@AEAV?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@Z; ScriptHelpers::GetVectorFromScriptArray(tagVARIANT const &,std::vector<ATL::CComVariant> &)
0x1800047b3  mov     esi, eax
0x1800047b5  test    rdi, rdi
0x1800047b8  jz      short loc_1800047DD
0x1800047ba  mov     rcx, rdi; pvarg
0x1800047bd  call    cs:__imp_VariantClear
0x1800047c3  test    eax, eax
0x1800047c5  js      short loc_1800047DD
0x1800047c7  movups  xmm0, xmmword ptr [rbp+2C0h+pvarg]
0x1800047cb  movups  xmmword ptr [rdi], xmm0
0x1800047ce  movsd   xmm1, qword ptr [rbp+2C0h+pvarg+10h]
0x1800047d3  movsd   qword ptr [rdi+10h], xmm1
0x1800047d8  mov     word ptr [rbp+2C0h+pvarg], r13w
0x1800047dd  lea     rcx, [rbp+2C0h+pvarg]; pvarg
0x1800047e1  test    esi, esi
0x1800047e3  jnz     loc_180005589
0x1800047e9  call    cs:__imp_VariantClear
0x1800047ef  xorps   xmm0, xmm0
0x1800047f2  movdqu  [rbp+2C0h+var_340], xmm0
0x1800047f7  mov     [rbp+2C0h+var_330], r13
0x1800047fb  lea     rcx, [rbp+2C0h+var_2B0]; pvarg
0x1800047ff  call    cs:__imp_VariantInit
0x180004805  test    rbx, rbx
0x180004808  jz      short loc_18000482D
0x18000480a  lea     rcx, [rbp+2C0h+var_2B0]; pvarg
0x18000480e  call    cs:__imp_VariantClear
0x180004814  test    eax, eax
0x180004816  js      short loc_18000482D
0x180004818  movups  xmm0, xmmword ptr [rbx]
0x18000481b  movups  xmmword ptr [rbp+2C0h+var_2B0], xmm0
0x18000481f  movsd   xmm1, qword ptr [rbx+10h]
0x180004824  movsd   qword ptr [rbp+2C0h+var_2B0+10h], xmm1
0x180004829  mov     [rbx], r13w
0x18000482d  lea     rdx, [rbp+2C0h+var_340]
0x180004831  lea     rcx, [rbp+2C0h+var_2B0]
0x180004835  call    ?GetVectorFromScriptArray@ScriptHelpers@@YAJAEBUtagVARIANT@@AEAV?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@@Z; ScriptHelpers::GetVectorFromScriptArray(tagVARIANT const &,std::vector<ATL::CComVariant> &)
0x18000483a  mov     esi, eax
0x18000483c  test    rbx, rbx
0x18000483f  jz      short loc_180004864
0x180004841  mov     rcx, rbx; pvarg
0x180004844  call    cs:__imp_VariantClear
0x18000484a  test    eax, eax
0x18000484c  js      short loc_180004864
0x18000484e  movups  xmm0, xmmword ptr [rbp+2C0h+var_2B0]
0x180004852  movups  xmmword ptr [rbx], xmm0
0x180004855  movsd   xmm1, qword ptr [rbp+2C0h+var_2B0+10h]
0x18000485a  movsd   qword ptr [rbx+10h], xmm1
0x18000485f  mov     word ptr [rbp+2C0h+var_2B0], r13w
0x180004864  lea     rcx, [rbp+2C0h+var_2B0]; pvarg
0x180004868  test    esi, esi
0x18000486a  jnz     loc_18000556E
0x180004870  call    cs:__imp_VariantClear
0x180004876  mov     rcx, qword ptr [rbp+2C0h+var_2D8+8]
0x18000487a  sub     rcx, qword ptr [rbp+2C0h+var_2D8]
0x18000487e  sar     rcx, 3
0x180004882  mov     rbx, 0AAAAAAAAAAAAAAABh
0x18000488c  imul    rcx, rbx
0x180004890  mov     rax, qword ptr [rbp+2C0h+var_340+8]
0x180004894  sub     rax, qword ptr [rbp+2C0h+var_340]
0x180004898  sar     rax, 3
0x18000489c  imul    rax, rbx
0x1800048a0  cmp     rcx, rax
0x1800048a3  jnz     loc_180004C09
0x1800048a9  test    rcx, rcx
0x1800048ac  jz      loc_180004C09
0x1800048b2  xorps   xmm0, xmm0
0x1800048b5  movdqu  [rbp+2C0h+var_328], xmm0
0x1800048ba  mov     [rbp+2C0h+var_318], r13
0x1800048be  xorps   xmm1, xmm1
0x1800048c1  movdqu  [rbp+2C0h+var_308], xmm1
0x1800048c6  mov     [rbp+2C0h+var_2F8], r13
0x1800048ca  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800048d1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800048d8  mov     rax, [rax+18h]
0x1800048dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e1  lea     r14, [rax+18h]
0x1800048e5  mov     [rsp+3C0h+strIn], r14
0x1800048ea  mov     r15, r13
0x1800048ed  mov     rax, qword ptr [rbp+2C0h+var_2D8+8]
0x1800048f1  mov     rcx, qword ptr [rbp+2C0h+var_2D8]
0x1800048f5  sub     rax, rcx
0x1800048f8  sar     rax, 3
0x1800048fc  imul    rax, rbx
0x180004900  test    rax, rax
0x180004903  jz      loc_180004A86
0x180004909  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000490d  mov     edx, 8
0x180004912  lea     rdi, [r15+r15*2]
0x180004916  mov     rax, qword ptr [rbp+2C0h+var_340]
0x18000491a  cmp     [rax+rdi*8], dx
0x18000491e  jnz     loc_180004BD0
0x180004924  cmp     [rcx+rdi*8], dx
0x180004928  jnz     loc_180004BD0
0x18000492e  mov     rbx, [rcx+rdi*8+8]
0x180004933  lea     rdx, aUtf8; "UTF-8"
0x18000493a  mov     rcx, rbx; String1
0x18000493d  call    wcscmp_0
0x180004942  test    eax, eax
0x180004944  jz      short loc_180004970
0x180004946  lea     rdx, aUtf16le; "UTF-16LE"
0x18000494d  mov     rcx, rbx; String1
0x180004950  call    wcscmp_0
0x180004955  test    eax, eax
0x180004957  jz      short loc_180004970
0x180004959  lea     rdx, aBinary; "BINARY"
0x180004960  mov     rcx, rbx; String1
0x180004963  call    wcscmp_0
0x180004968  test    eax, eax
0x18000496a  jnz     loc_180004BD0
0x180004970  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004977  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000497e  mov     rax, [rax+18h]
0x180004982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004987  add     rax, 18h
0x18000498b  mov     [rsp+3C0h+var_368], rax
0x180004990  mov     r8, qword ptr [rbp+2C0h+var_340]
0x180004994  mov     r8, [r8+rdi*8+8]
0x180004999  lea     rdx, aS_0; "*.%s"
0x1800049a0  lea     rcx, [rsp+3C0h+var_368]
0x1800049a5  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800049aa  mov     rax, qword ptr [rbp+2C0h+var_308+8]
0x1800049ae  cmp     rax, [rbp+2C0h+var_2F8]
0x1800049b2  jz      short loc_1800049C8
0x1800049b4  lea     rdx, [rsp+3C0h+var_368]
0x1800049b9  mov     rcx, rax
0x1800049bc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800049c1  add     qword ptr [rbp+2C0h+var_308+8], 8
0x1800049c6  jmp     short loc_1800049D9
0x1800049c8  lea     r8, [rsp+3C0h+var_368]
0x1800049cd  mov     rdx, rax
0x1800049d0  lea     rcx, [rbp+2C0h+var_308]
0x1800049d4  call    ??$_Emplace_reallocate@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@AEAAPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAV23@AEBV23@@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::_Emplace_reallocate<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800049d9  mov     rax, qword ptr [rbp+2C0h+var_340]
0x1800049dd  mov     rcx, [rax+rdi*8+8]
0x1800049e2  mov     [rbp+2C0h+pv], rcx
0x1800049e6  mov     rbx, [rsp+3C0h+var_368]
0x1800049eb  mov     [rbp+2C0h+var_2B8], rbx
0x1800049ef  mov     rdx, qword ptr [rbp+2C0h+var_328+8]
0x1800049f3  cmp     rdx, [rbp+2C0h+var_318]
0x1800049f7  jz      short loc_180004A07
0x1800049f9  mov     [rdx], rcx
0x1800049fc  mov     [rdx+8], rbx
0x180004a00  add     qword ptr [rbp+2C0h+var_328+8], 10h
0x180004a05  jmp     short loc_180004A14
0x180004a07  lea     r8, [rbp+2C0h+pv]
0x180004a0b  lea     rcx, [rbp+2C0h+var_328]
0x180004a0f  call    ??$_Emplace_reallocate@AEBU_COMDLG_FILTERSPEC@@@?$vector@U_COMDLG_FILTERSPEC@@V?$allocator@U_COMDLG_FILTERSPEC@@@std@@@std@@AEAAPEAU_COMDLG_FILTERSPEC@@QEAU2@AEBU2@@Z; std::vector<_COMDLG_FILTERSPEC>::_Emplace_reallocate<_COMDLG_FILTERSPEC const &>(_COMDLG_FILTERSPEC * const,_COMDLG_FILTERSPEC const &)
0x180004a14  mov     rax, qword ptr [rbp+2C0h+var_340]
0x180004a18  mov     r8, [rax+rdi*8+8]
0x180004a1d  mov     [rsp+3C0h+ppv], r8
0x180004a22  mov     r9, r8
0x180004a25  lea     rdx, aSSS; "%s (*.%s)|*.%s|"
0x180004a2c  lea     rcx, [rsp+3C0h+strIn]
0x180004a31  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180004a36  lea     rdx, [rbx-18h]
0x180004a3a  mov     eax, r14d
0x180004a3d  lock xadd [rdx+10h], eax
0x180004a42  add     eax, r14d
0x180004a45  test    eax, eax
0x180004a47  jg      short loc_180004A58
0x180004a49  mov     rcx, [rdx]
0x180004a4c  mov     rax, [rcx]
0x180004a4f  mov     rax, [rax+8]
0x180004a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a58  inc     r15
0x180004a5b  mov     rax, qword ptr [rbp+2C0h+var_2D8+8]
0x180004a5f  mov     rcx, qword ptr [rbp+2C0h+var_2D8]
0x180004a63  sub     rax, rcx
0x180004a66  sar     rax, 3
0x180004a6a  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180004a74  imul    rax, rdx
0x180004a78  cmp     r15, rax
0x180004a7b  jb      loc_18000490D
0x180004a81  mov     r14, [rsp+3C0h+strIn]
0x180004a86  mov     rax, qword ptr [rbp+2C0h+var_340]
0x180004a8a  mov     r13, [rax+8]
0x180004a8e  mov     r8, [rbp+2C0h+var_2E0]
0x180004a92  mov     edx, 104h
0x180004a97  lea     rcx, [rbp+2C0h+var_260]
0x180004a9b  call    cs:__imp__o_wcscpy_s
0x180004aa1  cmp     dword ptr [r14-8], 1
0x180004aa6  jle     short loc_180004ABB
0x180004aa8  mov     edx, [r14-10h]
0x180004aac  lea     rcx, [rsp+3C0h+strIn]
0x180004ab1  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180004ab6  mov     r14, [rsp+3C0h+strIn]
0x180004abb  mov     [rsp+3C0h+var_348], 0
0x180004ac3  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004aca  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004ad1  mov     rax, [rax+18h]
0x180004ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ada  lea     rbx, [rax+18h]
0x180004ade  mov     [rsp+3C0h+strIn], rbx
0x180004ae3  xor     r15d, r15d
0x180004ae6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004aed  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004af4  mov     rax, [rax+18h]
0x180004af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004afd  lea     rdi, [rax+18h]
0x180004b01  mov     [rsp+3C0h+var_368], rdi
0x180004b06  test    r12d, r12d
0x180004b09  jz      loc_180005157
0x180004b0f  cmp     r12d, 1
0x180004b13  jnz     loc_180005304
0x180004b19  xor     r12d, r12d
0x180004b1c  mov     [rbp+2C0h+pv], r12
0x180004b20  xor     edx, edx; pUnkOuter
0x180004b22  cmp     [rsp+3C0h+var_344], r12d
0x180004b27  jz      loc_180004DEB
0x180004b2d  mov     [rsp+3C0h+var_348], 1
0x180004b35  mov     r15d, 80004001h
0x180004b3b  mov     esi, r15d
0x180004b3e  xor     r8d, r8d; dwFlags
0x180004b41  lea     rcx, LibFileName; "ieframe.dll"
0x180004b48  call    cs:__imp_LoadLibraryExW
0x180004b4e  mov     r12, rax
0x180004b51  test    rax, rax
0x180004b54  jz      short loc_180004BB3
0x180004b56  lea     rdx, aIeshowsavefile; "IEShowSaveFileDialog"
0x180004b5d  mov     rcx, rax; hModule
0x180004b60  call    cs:__imp_GetProcAddress
0x180004b66  test    rax, rax
0x180004b69  jz      short loc_180004BAA
0x180004b6b  mov     rdx, [rbp+2C0h+var_2E8]
0x180004b6f  mov     [rsp+3C0h+var_380], rdx
0x180004b74  lea     rcx, [rbp+2C0h+pv]
0x180004b78  mov     [rsp+3C0h+var_388], rcx
0x180004b7d  mov     [rsp+3C0h+var_390], 808002h
0x180004b85  mov     [rsp+3C0h+var_398], 1
0x180004b8d  mov     [rsp+3C0h+ppv], r13
0x180004b92  mov     r9, r14
0x180004b95  xor     r8d, r8d
  ... truncated ...
```
