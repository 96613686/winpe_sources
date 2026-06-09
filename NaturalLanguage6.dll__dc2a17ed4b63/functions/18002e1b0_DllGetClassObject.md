# DllGetClassObject

- ea: `0x18002e1b0`
- end: `0x18002ed78`
- name: `DllGetClassObject`
- size: `3016`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003894`
- `0x180005160`
- `0x180005190`
- `0x180016a1c`
- `0x18001a07c`
- `0x18001a0d8`
- `0x18002cb78`
- `0x18002e0d0`
- `0x18002e1b0`
- `0x18002ee48`
- `0x18002ef84`
- `0x180030198`
- `0x180030bd0`
- `0x180030c5c`
- `0x180034078`
- `0x180035640`
- `0x180037018`
- `0x180038a4c`
- `0x18003dfcc`
- `0x18003ed6c`
- `0x1800418f4`
- `0x180041b1c`
- `0x180049618`
- `0x18004997c`
- `0x180049e8c`
- `0x18004af2c`
- `0x18005d5d8`
- `0x18009e2b6`
- `0x18009e300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e3f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e50f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ed0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ed68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e3f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e50f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ed0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ed68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e217`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e217`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e4ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eaab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eae4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e4ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ea64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eaab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eae4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e4a8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e4a8`

## string_xrefs

- `0x18002e739`: `HKEY_CLASSES_ROOT\CLSID\`
- `0x18002e91a`: `HKEY_CLASSES_ROOT\CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  LPVOID *v3; // r13
  const IID *v5; // r12
  char *v6; // rbx
  bool v8; // r15
  int v9; // ecx
  char v10; // r14
  __int64 v11; // rdx
  _QWORD *v12; // r8
  __int64 v13; // rax
  char *v14; // rax
  char *v15; // rdi
  IID *v16; // rdx
  void *v17; // rax
  HRESULT v18; // ebx
  int v19; // eax
  HKEY v20; // rdi
  _WORD *v21; // rdi
  int v22; // eax
  bool v23; // zf
  char v24; // al
  struct _variant_t *Value; // rax
  HINSTANCE v26; // r8
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 v31; // rax
  const unsigned __int16 *v32; // rax
  HKEY v33; // rax
  __int64 DefaultValue; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdi
  __int64 v38; // rax
  const unsigned __int16 *v39; // rax
  HKEY v40; // rax
  __int64 v41; // rax
  DualModeClassFactory *v42; // rcx
  DualModeClassFactory *v43; // rax
  void *v44; // rax
  _com_error *v45; // rbx
  const unsigned __int16 *v46; // [rsp+28h] [rbp-610h]
  bool v47; // [rsp+60h] [rbp-5D8h]
  void *v48; // [rsp+68h] [rbp-5D0h] BYREF
  char v49; // [rsp+70h] [rbp-5C8h]
  __int64 v50; // [rsp+78h] [rbp-5C0h] BYREF
  __int64 v51; // [rsp+80h] [rbp-5B8h] BYREF
  __int64 v52; // [rsp+88h] [rbp-5B0h] BYREF
  __int64 v53; // [rsp+90h] [rbp-5A8h] BYREF
  __int64 v54; // [rsp+98h] [rbp-5A0h] BYREF
  LPVOID *v55; // [rsp+A0h] [rbp-598h]
  unsigned int v56; // [rsp+A8h] [rbp-590h]
  char *v57; // [rsp+B0h] [rbp-588h]
  void *v58; // [rsp+B8h] [rbp-580h] BYREF
  _QWORD v59[2]; // [rsp+C0h] [rbp-578h] BYREF
  DualModeClassFactory *v60; // [rsp+D0h] [rbp-568h] BYREF
  HKEY hKey[2]; // [rsp+D8h] [rbp-560h] BYREF
  _QWORD v62[2]; // [rsp+E8h] [rbp-550h] BYREF
  int v63; // [rsp+F8h] [rbp-540h]
  const IID *v64; // [rsp+100h] [rbp-538h]
  HKEY v65[2]; // [rsp+108h] [rbp-530h] BYREF
  char v66[8]; // [rsp+118h] [rbp-520h] BYREF
  char v67[8]; // [rsp+120h] [rbp-518h] BYREF
  char v68[8]; // [rsp+128h] [rbp-510h] BYREF
  char v69[8]; // [rsp+130h] [rbp-508h] BYREF
  char v70[8]; // [rsp+138h] [rbp-500h] BYREF
  _com_error *v71; // [rsp+140h] [rbp-4F8h] BYREF
  _com_error *v72; // [rsp+148h] [rbp-4F0h] BYREF
  _com_error *v73[5]; // [rsp+150h] [rbp-4E8h] BYREF
  _com_error *v74; // [rsp+178h] [rbp-4C0h] BYREF
  VARIANTARG v75; // [rsp+180h] [rbp-4B8h] BYREF
  VARIANTARG v76; // [rsp+198h] [rbp-4A0h] BYREF
  VARIANTARG v77; // [rsp+1B0h] [rbp-488h] BYREF
  VARIANTARG v78; // [rsp+1C8h] [rbp-470h] BYREF
  VARIANTARG v79; // [rsp+1E0h] [rbp-458h] BYREF
  VARIANTARG v80; // [rsp+1F8h] [rbp-440h] BYREF
  VARIANTARG v81; // [rsp+210h] [rbp-428h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+228h] [rbp-410h] BYREF
  OLECHAR sz[192]; // [rsp+270h] [rbp-3C8h] BYREF
  unsigned __int16 v84[264]; // [rsp+3F0h] [rbp-248h] BYREF
  const void *retaddr; // [rsp+638h] [rbp+0h]

  v73[4] = (_com_error *)-2LL;
  v3 = ppv;
  v5 = rclsid;
  v64 = rclsid;
  v55 = ppv;
  v6 = &byte_1800FB900;
  v57 = &byte_1800FB900;
  EnterCriticalSection(&stru_1800FB908);
  if ( v3 )
  {
    *v3 = 0;
    if ( !qword_1800FB400[0] )
    {
      try
      {
        BuildGlobalObjects();
      }
      catch ( _com_error *v74 )
      {
        v45 = v74;
        ImxTraceCatch(1, *((unsigned int *)v74 + 2), retaddr);
        FreeGlobalObjects();
        v18 = *((_DWORD *)v45 + 2);
        goto LABEL_19;
      }
      catch ( exception )
      {
        ImxTraceCatch(2, 2147500037LL, retaddr);
        FreeGlobalObjects();
        v18 = -2147467259;
        goto LABEL_19;
      }
    }
    if ( !memcmp_0(riid, &IID_IClassFactory, 0x10u) || !memcmp_0(riid, &IID_IUnknown, 0x10u) )
    {
      v8 = 0;
      v49 = 0;
      v56 = -1;
      v54 = 0;
      v51 = 0;
      v53 = 0;
      v50 = 0;
      v52 = 0;
      v9 = 0;
      v10 = 1;
      while ( 1 )
      {
        v63 = v9;
        v59[0] = v9;
        if ( (unsigned __int64)v9 >= 0x60 )
          break;
        v11 = qword_1800FB400[v9];
        if ( v11 )
        {
          v12 = *(_QWORD **)(v11 + 8);
          v13 = *(_QWORD *)&v5->Data1 - *v12;
          if ( *(_QWORD *)&v5->Data1 == *v12 )
            v13 = *(_QWORD *)v5->Data4 - v12[1];
          if ( !v13 )
          {
            v14 = (char *)operator new(0x68u);
            v15 = v14;
            v60 = (DualModeClassFactory *)v14;
            if ( v14 )
            {
              CClassFactory::CClassFactory(
                (CClassFactory *)v14,
                (const struct _GUID *)(v14 + 24),
                *(int (**)(struct IUnknown *, const struct _GUID *, void **))(qword_1800FB400[v59[0]] + 16));
              *(_QWORD *)v15 = &DualModeClassFactory::`vftable';
              *v16 = *v5;
              v15[40] = 0;
              *((_DWORD *)v15 + 11) = 0;
              *((_DWORD *)v15 + 12) = v56;
              ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)(
                (_bstr_t *)(v15 + 56),
                L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\ContentIndex\\Language");
              *((_QWORD *)v15 + 8) = 0;
              *((_QWORD *)v15 + 9) = 0;
              *((_QWORD *)v15 + 10) = 0;
              *((_QWORD *)v15 + 11) = 0;
              *((_QWORD *)v15 + 12) = 0;
            }
            else
            {
              v15 = 0;
            }
            v59[0] = v15;
            v17 = 0;
            v48 = 0;
            if ( v15 )
            {
              v19 = _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::_QueryInterface<DualModeClassFactory *>(
                      (__int64 *)&v48,
                      (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v59);
              if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147467262 )
                _com_issue_error(v19);
              v17 = v48;
            }
            v48 = 0;
            *v3 = v17;
            LeaveCriticalSection(&stru_1800FB908);
            return 0;
          }
        }
        ++v9;
      }
      v20 = ((HKEY (__stdcall *)(const unsigned __int16 *, HKEY))NLG::RegistryKey::OpenKey)(
              L"HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\ContentIndex\\Language",
              0);
      v65[0] = v20;
      if ( v20 )
      {
        if ( !StringFromGUID2(v5, sz, 192) )
        {
          RegCloseKey(v20);
          v65[0] = 0;
          ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v52);
          ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v50);
          ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v53);
          ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v51);
          ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v54);
          LeaveCriticalSection(&stru_1800FB908);
          return -2147467259;
        }
        _variant_t::_variant_t((_variant_t *)&v75, sz);
        v58 = 0;
        NLG::RegistryKey::FindSubKeyWithValue(v65, hKey, &v75);
        v21 = (_WORD *)_bstr_t::operator unsigned short const *(&v58);
        if ( hKey[0] && v21 && *v21 )
        {
          v22 = CMN_CompareStringNoCaseNumW(v21, L"WBreakerClass", 13);
          v8 = v22 == 0;
          v47 = v22 == 0;
          if ( !v22 || (v23 = (unsigned int)CMN_CompareStringNoCaseNumW(v21, L"StemmerClass", 12) == 0, v24 = 1, !v23) )
            v24 = 0;
          v49 = v24;
          Value = (struct _variant_t *)NLG::RegistryKey::GetValue(hKey, &v76, L"Locale");
          v56 = _variant_t::operator long(Value);
          _variant_t::~_variant_t(&v76);
          if ( !(unsigned int)GetModuleFilePath(v84, 260, v26) )
          {
            CNLException::CNLException((CNLException *)pExceptionObject, -2147467259, retaddr);
            throw (CNLException *)pExceptionObject;
          }
          try
          {
            if ( NLG::RegistryKey::ContainsValueName((NLG::RegistryKey *)hKey, L"CustomDict") )
            {
              v27 = NLG::RegistryKey::GetValue(hKey, &v77, L"CustomDict");
              _bstr_t::operator=(&v54, v27);
              _variant_t::~_variant_t(&v77);
            }
          }
          catch ( _com_error *v71 )
          {
            ImxTraceCatch(1, *((unsigned int *)v71 + 2), retaddr);
            v10 = 1;
            v6 = v57;
            v8 = v47;
            v5 = v64;
            v3 = v55;
          }
          try
          {
            if ( NLG::RegistryKey::ContainsValueName((NLG::RegistryKey *)hKey, L"LegacyWBreakerClass") )
            {
              v28 = NLG::RegistryKey::GetValue(hKey, &v78, L"LegacyWBreakerClass");
              _bstr_t::operator=(&v51, v28);
              _variant_t::~_variant_t(&v78);
              ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)(
                (_bstr_t *)&v48,
                L"HKEY_CLASSES_ROOT\\CLSID\\");
              ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)((_bstr_t *)v59, L"\\");
              v29 = _bstr_t::operator+(&v48, v70, v59);
              v30 = _bstr_t::operator+(v29, v69, &v51);
              ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)(
                (_bstr_t *)v62,
                L"\\InprocServer32");
              v31 = _bstr_t::operator+(v30, v68, v62);
              _bstr_t::operator=(&v48, v31);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v68);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v62);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v69);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v70);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v59);
              v32 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(&v48);
              v33 = ((HKEY (__stdcall *)(const unsigned __int16 *, HKEY))NLG::RegistryKey::OpenKey)(v32, 0);
              v59[0] = v33;
              if ( v33 )
              {
                DefaultValue = NLG::RegistryKey::GetDefaultValue(v59, &v79);
                _bstr_t::operator=(&v53, DefaultValue);
                _variant_t::~_variant_t(&v79);
                v33 = (HKEY)v59[0];
              }
              if ( v33 )
              {
                RegCloseKey(v33);
                v59[0] = 0;
              }
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v48);
            }
          }
          catch ( _com_error *v72 )
          {
            ImxTraceCatch(1, *((unsigned int *)v72 + 2), retaddr);
            v10 = 1;
            v6 = v57;
            v8 = v47;
            v5 = v64;
            v3 = v55;
          }
          try
          {
            if ( NLG::RegistryKey::ContainsValueName((NLG::RegistryKey *)hKey, L"LegacyStemmerClass") )
            {
              v35 = NLG::RegistryKey::GetValue(hKey, &v80, L"LegacyStemmerClass");
              _bstr_t::operator=(&v50, v35);
              _variant_t::~_variant_t(&v80);
              ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)(
                (_bstr_t *)&v48,
                L"HKEY_CLASSES_ROOT\\CLSID\\");
              ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)((_bstr_t *)v62, L"\\");
              v36 = _bstr_t::operator+(&v48, &v60, v62);
              v37 = _bstr_t::operator+(v36, v67, &v50);
              ((void (__stdcall *)(_bstr_t *, const unsigned __int16 *))_bstr_t::_bstr_t)(
                (_bstr_t *)v59,
                L"\\InprocServer32");
              v38 = _bstr_t::operator+(v37, v66, v59);
              _bstr_t::operator=(&v48, v38);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v66);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v59);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v67);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v60);
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)v62);
              v39 = (const unsigned __int16 *)_bstr_t::operator unsigned short const *(&v48);
              v40 = ((HKEY (__stdcall *)(const unsigned __int16 *, HKEY))NLG::RegistryKey::OpenKey)(v39, 0);
              v62[0] = v40;
              if ( !v40 )
                v10 = 0;
              if ( v10 )
              {
                v41 = NLG::RegistryKey::GetDefaultValue(v62, &v81);
                _bstr_t::operator=(&v52, v41);
                _variant_t::~_variant_t(&v81);
                v40 = (HKEY)v62[0];
              }
              if ( v40 )
              {
                RegCloseKey(v40);
                v62[0] = 0;
              }
              ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v48);
            }
          }
          catch ( _com_error *v73 )
          {
            ImxTraceCatch(1, *((unsigned int *)v73[0] + 2), retaddr);
            v6 = v57;
            v8 = v47;
            v5 = v64;
            v3 = v55;
          }
        }
        if ( hKey[0] )
        {
          RegCloseKey(hKey[0]);
          hKey[0] = 0;
        }
        ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v58);
        _variant_t::~_variant_t(&v75);
        v20 = v65[0];
      }
      if ( v20 )
      {
        RegCloseKey(v20);
        v65[0] = 0;
      }
      if ( !v8 && !v49 )
      {
        ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v52);
        ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v50);
        ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v53);
        ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v51);
        ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v54);
        goto LABEL_5;
      }
      v42 = (DualModeClassFactory *)operator new(0x68u);
      v60 = v42;
      if ( v42 )
        v43 = DualModeClassFactory::DualModeClassFactory(
                v42,
                v5,
                0,
                v8,
                v56,
                v46,
                (struct _bstr_t *)&v54,
                (struct _bstr_t *)&v51,
                (struct _bstr_t *)&v53,
                (struct _bstr_t *)&v50,
                (struct _bstr_t *)&v52);
      else
        v43 = 0;
      v60 = v43;
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(
        &v58,
        &v60);
      v44 = v58;
      v58 = 0;
      *v3 = v44;
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>((__int64 *)&v58);
      ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v52);
      ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v50);
      ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v53);
      ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v51);
      ((void (__fastcall *)(_bstr_t *))_bstr_t::_Free)((_bstr_t *)&v54);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
      return 0;
    }
    else
    {
LABEL_5:
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
      return -2147221231;
    }
  }
  else
  {
    v18 = -2147024809;
LABEL_19:
    LeaveCriticalSection(&stru_1800FB908);
    return v18;
  }
}

```

## disassembly

```asm
0x18002e1b0  mov     rax, rsp
0x18002e1b3  push    rdi
0x18002e1b4  push    r12
0x18002e1b6  push    r13
0x18002e1b8  push    r14
0x18002e1ba  push    r15
0x18002e1bc  sub     rsp, 610h
0x18002e1c3  mov     qword ptr [rax-4C8h], 0FFFFFFFFFFFFFFFEh
0x18002e1ce  mov     [rax+10h], rbx
0x18002e1d2  mov     [rax+20h], rsi
0x18002e1d6  mov     rax, cs:__security_cookie
0x18002e1dd  xor     rax, rsp
0x18002e1e0  mov     [rsp+638h+var_38], rax
0x18002e1e8  mov     r13, r8
0x18002e1eb  mov     rdi, rdx
0x18002e1ee  mov     r12, rcx
0x18002e1f1  mov     [rsp+638h+var_538], rcx
0x18002e1f9  mov     [rsp+638h+var_598], r8
0x18002e201  lea     rbx, byte_1800FB900
0x18002e208  mov     [rsp+638h+var_588], rbx
0x18002e210  lea     rcx, stru_1800FB908; lpCriticalSection
0x18002e217  call    cs:__imp_EnterCriticalSection
0x18002e21d  nop
0x18002e21e  xor     esi, esi
0x18002e220  test    r13, r13
0x18002e223  jz      loc_18002E403
0x18002e229  mov     [r13+0], rsi
0x18002e22d  cmp     cs:qword_1800FB400, rsi
0x18002e234  jz      loc_18002E40A
0x18002e23a  mov     r14d, 10h
0x18002e240  mov     r8d, r14d; Size
0x18002e243  lea     rdx, IID_IClassFactory; Buf2
0x18002e24a  mov     rcx, rdi; Buf1
0x18002e24d  call    memcmp_0
0x18002e252  test    eax, eax
0x18002e254  jz      short loc_18002E2A8
0x18002e256  mov     r8d, r14d; Size
0x18002e259  lea     rdx, IID_IUnknown; Buf2
0x18002e260  mov     rcx, rdi; Buf1
0x18002e263  call    memcmp_0
0x18002e268  test    eax, eax
0x18002e26a  jz      short loc_18002E2A8
0x18002e26c  lea     rcx, [rbx+8]; lpCriticalSection
0x18002e270  call    cs:__imp_LeaveCriticalSection
0x18002e276  mov     eax, 80040111h
0x18002e27b  mov     rcx, [rsp+638h+var_38]
0x18002e283  xor     rcx, rsp; StackCookie
0x18002e286  call    __security_check_cookie
0x18002e28b  lea     r11, [rsp+638h+var_28]
0x18002e293  mov     rbx, [r11+38h]
0x18002e297  mov     rsi, [r11+48h]
0x18002e29b  mov     rsp, r11
0x18002e29e  pop     r15
0x18002e2a0  pop     r14
0x18002e2a2  pop     r13
0x18002e2a4  pop     r12
0x18002e2a6  pop     rdi
0x18002e2a7  retn
0x18002e2a8  mov     r15b, sil
0x18002e2ab  mov     [rsp+638h+var_5D8], sil
0x18002e2b0  mov     [rsp+638h+var_5C8], sil
0x18002e2b5  mov     [rsp+638h+var_590], 0FFFFFFFFh
0x18002e2c0  mov     [rsp+638h+var_5A0], rsi
0x18002e2c8  mov     [rsp+638h+var_5B8], rsi
0x18002e2d0  mov     [rsp+638h+var_5A8], rsi
0x18002e2d8  mov     [rsp+638h+var_5C0], rsi
0x18002e2dd  mov     [rsp+638h+var_5B0], rsi
0x18002e2e5  mov     ecx, esi
0x18002e2e7  mov     r14d, 1
0x18002e2ed  mov     [rsp+638h+var_540], ecx
0x18002e2f4  movsxd  rax, ecx
0x18002e2f7  mov     [rsp+638h+var_578], rax
0x18002e2ff  cmp     rax, 60h ; '`'
0x18002e303  jnb     loc_18002E469
0x18002e309  lea     rdx, qword_1800FB400
0x18002e310  mov     rdx, [rdx+rax*8]
0x18002e314  test    rdx, rdx
0x18002e317  jz      short loc_18002E33B
0x18002e319  mov     r8, [rdx+8]
0x18002e31d  mov     rax, [r12]
0x18002e321  sub     rax, [r8]
0x18002e324  jnz     short loc_18002E32F
0x18002e326  mov     rax, [r12+8]
0x18002e32b  sub     rax, [r8+8]
0x18002e32f  test    rax, rax
0x18002e332  jnz     short loc_18002E340
0x18002e334  mov     eax, r14d
0x18002e337  test    eax, eax
0x18002e339  jnz     short loc_18002E344
0x18002e33b  add     ecx, r14d
0x18002e33e  jmp     short loc_18002E2ED
0x18002e340  mov     eax, esi
0x18002e342  jmp     short loc_18002E337
0x18002e344  mov     ecx, 68h ; 'h'; Size
0x18002e349  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e34e  mov     rdi, rax
0x18002e351  mov     [rsp+638h+var_568], rax
0x18002e359  test    rax, rax
0x18002e35c  jz      loc_18002E3FE
0x18002e362  lea     rdx, [rax+18h]; struct _GUID *
0x18002e366  mov     r8, [rsp+638h+var_578]
0x18002e36e  lea     rax, qword_1800FB400
0x18002e375  mov     r8, [rax+r8*8]
0x18002e379  mov     r8, [r8+10h]; int (*)(struct IUnknown *, const struct _GUID *, void **)
0x18002e37d  mov     rcx, rdi; this
0x18002e380  call    ??0CClassFactory@@QEAA@AEBU_GUID@@P6AJPEAUIUnknown@@0PEAPEAX@Z@Z; CClassFactory::CClassFactory(_GUID const &,long (*)(IUnknown *,_GUID const &,void * *))
0x18002e385  nop
0x18002e386  lea     rax, ??_7DualModeClassFactory@@6B@; const DualModeClassFactory::`vftable'
0x18002e38d  mov     [rdi], rax
0x18002e390  movups  xmm0, xmmword ptr [r12]
0x18002e395  movdqu  xmmword ptr [rdx], xmm0
0x18002e399  mov     [rdi+28h], sil
0x18002e39d  mov     [rdi+2Ch], esi
0x18002e3a0  mov     eax, [rsp+638h+var_590]
0x18002e3a7  mov     [rdi+30h], eax
0x18002e3aa  lea     rcx, [rdi+38h]; this
0x18002e3ae  lea     rdx, psz; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18002e3b5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002e3ba  nop
0x18002e3bb  mov     [rdi+40h], rsi
0x18002e3bf  mov     [rdi+48h], rsi
0x18002e3c3  mov     [rdi+50h], rsi
0x18002e3c7  mov     [rdi+58h], rsi
0x18002e3cb  mov     [rdi+60h], rsi
0x18002e3cf  mov     [rsp+638h+var_578], rdi
0x18002e3d7  mov     rax, rsi
0x18002e3da  mov     [rsp+638h+var_5D0], rax
0x18002e3df  test    rdi, rdi
0x18002e3e2  jnz     short loc_18002E433
0x18002e3e4  mov     [rsp+638h+var_5D0], rsi
0x18002e3e9  mov     [r13+0], rax
0x18002e3ed  lea     rcx, [rbx+8]; lpCriticalSection
0x18002e3f1  call    cs:__imp_LeaveCriticalSection
0x18002e3f7  xor     eax, eax
0x18002e3f9  jmp     loc_18002E27B
0x18002e3fe  mov     rdi, rsi
0x18002e401  jmp     short loc_18002E3CF
0x18002e403  mov     ebx, 80070057h
0x18002e408  jmp     short loc_18002E41F
0x18002e40a  call    BuildGlobalObjects
0x18002e40f  jmp     loc_18002E23A
0x18002e414  mov     ebx, dword ptr [rsp+638h+var_5D0]
0x18002e418  jmp     short loc_18002E41F
0x18002e41a  mov     ebx, 80004005h
0x18002e41f  lea     rcx, stru_1800FB908; lpCriticalSection
0x18002e426  call    cs:__imp_LeaveCriticalSection
0x18002e42c  mov     eax, ebx
0x18002e42e  jmp     loc_18002E27B
0x18002e433  lea     rdx, [rsp+638h+var_578]
0x18002e43b  lea     rcx, [rsp+638h+var_5D0]
0x18002e440  call    ??$_QueryInterface@PEAVDualModeClassFactory@@@?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAJAEBQEAVDualModeClassFactory@@@Z; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::_QueryInterface<DualModeClassFactory *>(DualModeClassFactory * const &)
0x18002e445  mov     edx, 80000000h
0x18002e44a  lea     ecx, [rax+rdx]
0x18002e44d  test    edx, ecx
0x18002e44f  jnz     short loc_18002E45F
0x18002e451  cmp     eax, 80004002h
0x18002e456  jz      short loc_18002E45F
0x18002e458  mov     ecx, eax; int
0x18002e45a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002e45f  mov     rax, [rsp+638h+var_5D0]
0x18002e464  jmp     loc_18002E3E4
0x18002e469  xor     edx, edx; HKEY
0x18002e46b  lea     rcx, psz; "HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCont"...
0x18002e472  call    ?OpenKey@RegistryKey@NLG@@KAPEAUHKEY__@@PEBGPEAU3@@Z; NLG::RegistryKey::OpenKey(ushort const *,HKEY__ *)
0x18002e477  mov     rdi, rax
0x18002e47a  mov     [rsp+638h+var_530], rax
0x18002e482  test    rax, rax
0x18002e485  jz      short loc_18002E48C
0x18002e487  mov     al, r14b
0x18002e48a  jmp     short loc_18002E48F
0x18002e48c  mov     al, sil
0x18002e48f  test    al, al
0x18002e491  jz      loc_18002EADC
0x18002e497  mov     r8d, 0C0h; cchMax
0x18002e49d  lea     rdx, [rsp+638h+sz]; lpsz
0x18002e4a5  mov     rcx, r12; rguid
0x18002e4a8  call    cs:__imp_StringFromGUID2
0x18002e4ae  test    eax, eax
0x18002e4b0  jnz     short loc_18002E51F
0x18002e4b2  test    rdi, rdi
0x18002e4b5  jz      short loc_18002E4C8
0x18002e4b7  mov     rcx, rdi; hKey
0x18002e4ba  call    cs:__imp_RegCloseKey
0x18002e4c0  mov     [rsp+638h+var_530], rsi
0x18002e4c8  lea     rcx, [rsp+638h+var_5B0]; this
0x18002e4d0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002e4d5  nop
0x18002e4d6  lea     rcx, [rsp+638h+var_5C0]; this
0x18002e4db  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002e4e0  nop
0x18002e4e1  lea     rcx, [rsp+638h+var_5A8]; this
0x18002e4e9  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002e4ee  nop
0x18002e4ef  lea     rcx, [rsp+638h+var_5B8]; this
0x18002e4f7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002e4fc  nop
0x18002e4fd  lea     rcx, [rsp+638h+var_5A0]; this
0x18002e505  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002e50a  nop
0x18002e50b  lea     rcx, [rbx+8]; lpCriticalSection
0x18002e50f  call    cs:__imp_LeaveCriticalSection
0x18002e515  mov     eax, 80004005h
0x18002e51a  jmp     loc_18002E27B
0x18002e51f  lea     rdx, [rsp+638h+sz]; unsigned __int16 *
0x18002e527  lea     rcx, [rsp+638h+var_4B8]; this
0x18002e52f  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18002e534  nop
0x18002e535  mov     [rsp+638h+var_580], rsi
0x18002e53d  lea     rax, [rsp+638h+var_580]
0x18002e545  mov     qword ptr [rsp+638h+var_618], rax
0x18002e54a  lea     r8, [rsp+638h+var_4B8]
0x18002e552  lea     rdx, [rsp+638h+hKey]
0x18002e55a  lea     rcx, [rsp+638h+var_530]
0x18002e562  call    ?FindSubKeyWithValue@RegistryKey@NLG@@QEBA?AV12@AEAV_variant_t@@PEAV12@PEAV_bstr_t@@@Z; NLG::RegistryKey::FindSubKeyWithValue(_variant_t &,NLG::RegistryKey *,_bstr_t *)
0x18002e567  nop
0x18002e568  lea     rcx, [rsp+638h+var_580]
0x18002e570  call    ??B_bstr_t@@QEBAPEBGXZ; _bstr_t::operator ushort const *(void)
0x18002e575  mov     rdi, rax
0x18002e578  cmp     [rsp+638h+hKey], rsi
0x18002e580  jz      short loc_18002E587
0x18002e582  mov     al, r14b
0x18002e585  jmp     short loc_18002E58A
0x18002e587  mov     al, sil
0x18002e58a  test    al, al
0x18002e58c  jz      loc_18002EA9E
0x18002e592  test    rdi, rdi
0x18002e595  jz      loc_18002EA9E
0x18002e59b  cmp     [rdi], si
0x18002e59e  jz      loc_18002EA9E
0x18002e5a4  mov     r8d, 0Dh
0x18002e5aa  lea     rdx, aWbreakerclass; "WBreakerClass"
0x18002e5b1  mov     rcx, rdi
0x18002e5b4  call    CMN_CompareStringNoCaseNumW
0x18002e5b9  test    eax, eax
0x18002e5bb  setz    r15b
0x18002e5bf  mov     [rsp+638h+var_5D8], r15b
0x18002e5c4  test    eax, eax
0x18002e5c6  jz      short loc_18002E5E4
0x18002e5c8  mov     r8d, 0Ch
0x18002e5ce  lea     rdx, aStemmerclass; "StemmerClass"
0x18002e5d5  mov     rcx, rdi
0x18002e5d8  call    CMN_CompareStringNoCaseNumW
0x18002e5dd  test    eax, eax
0x18002e5df  mov     al, r14b
0x18002e5e2  jz      short loc_18002E5E7
0x18002e5e4  mov     al, sil
0x18002e5e7  mov     [rsp+638h+var_5C8], al
0x18002e5eb  lea     r8, aLocale; "Locale"
0x18002e5f2  lea     rdx, [rsp+638h+var_4A0]
0x18002e5fa  lea     rcx, [rsp+638h+hKey]
0x18002e602  call    ?GetValue@RegistryKey@NLG@@QEBA?AV_variant_t@@PEBG@Z; NLG::RegistryKey::GetValue(ushort const *)
0x18002e607  nop
0x18002e608  mov     rcx, rax; struct _variant_t *
0x18002e60b  call    ??B_variant_t@@QEBAJXZ; _variant_t::operator long(void)
0x18002e610  mov     [rsp+638h+var_590], eax
0x18002e617  lea     rcx, [rsp+638h+var_4A0]; this
0x18002e61f  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18002e624  mov     edx, 104h; int
0x18002e629  lea     rcx, [rsp+638h+var_248]; unsigned __int16 *
0x18002e631  call    ?GetModuleFilePath@@YAHPEAGHPEAUHINSTANCE__@@@Z; GetModuleFilePath(ushort *,int,HINSTANCE__ *)
0x18002e636  test    eax, eax
0x18002e638  jnz     short loc_18002E669
0x18002e63a  mov     r8, [rsp+638h]; void *
0x18002e642  mov     edx, 80004005h; int
0x18002e647  lea     rcx, [rsp+638h+pExceptionObject]; this
0x18002e64f  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18002e654  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18002e65b  lea     rcx, [rsp+638h+pExceptionObject]; pExceptionObject
0x18002e663  call    _CxxThrowException_0
0x18002e669  lea     rdx, aCustomdict; "CustomDict"
0x18002e670  lea     rcx, [rsp+638h+hKey]; this
0x18002e678  call    ?ContainsValueName@RegistryKey@NLG@@QEBA_NPEBG@Z; NLG::RegistryKey::ContainsValueName(ushort const *)
0x18002e67d  test    al, al
0x18002e67f  jz      short loc_18002E6BD
0x18002e681  lea     r8, aCustomdict; "CustomDict"
0x18002e688  lea     rdx, [rsp+638h+var_488]
0x18002e690  lea     rcx, [rsp+638h+hKey]
0x18002e698  call    ?GetValue@RegistryKey@NLG@@QEBA?AV_variant_t@@PEBG@Z; NLG::RegistryKey::GetValue(ushort const *)
0x18002e69d  nop
0x18002e69e  mov     rdx, rax
0x18002e6a1  lea     rcx, [rsp+638h+var_5A0]
0x18002e6a9  call    ??4_bstr_t@@QEAAAEAV0@AEBV_variant_t@@@Z; _bstr_t::operator=(_variant_t const &)
0x18002e6ae  nop
0x18002e6af  lea     rcx, [rsp+638h+var_488]; this
0x18002e6b7  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18002e6bc  nop
0x18002e6bd  jmp     short loc_18002E6E2
0x18002e6bf  xor     esi, esi
0x18002e6c1  lea     r14d, [rsi+1]
0x18002e6c5  mov     rbx, [rsp+638h+var_588]
0x18002e6cd  mov     r15b, [rsp+638h+var_5D8]
0x18002e6d2  mov     r12, [rsp+638h+var_538]
0x18002e6da  mov     r13, [rsp+638h+var_598]
0x18002e6e2  lea     rdx, aLegacywbreaker; "LegacyWBreakerClass"
0x18002e6e9  lea     rcx, [rsp+638h+hKey]; this
0x18002e6f1  call    ?ContainsValueName@RegistryKey@NLG@@QEBA_NPEBG@Z; NLG::RegistryKey::ContainsValueName(ushort const *)
0x18002e6f6  test    al, al
0x18002e6f8  jz      loc_18002E8A1
0x18002e6fe  lea     r8, aLegacywbreaker; "LegacyWBreakerClass"
0x18002e705  lea     rdx, [rsp+638h+var_470]
  ... truncated ...
```
