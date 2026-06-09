# CConfigSource::ProcessElement(__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0001,IXmlReader *,IMVKey * *,ulong,__MIDL___MIDL_itf_mvdatastore_0000_0000_0001,std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>> &)

- ea: `0x18000e184`
- end: `0x18000f2aa`
- name: `?ProcessElement@CConfigSource@@AEAAJW4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0001@@PEAUIXmlReader@@PEAPEAUIMVKey@@KW4__MIDL___MIDL_itf_mvdatastore_0000_0000_0001@@AEAV?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@@Z`
- size: `4390`
- prototype: `__int64 __fastcall(int *, int, int *, unsigned __int16 *, unsigned int, int, int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000dd4c`

## callees

- `0x1800011c4`
- `0x180001264`
- `0x18000135c`
- `0x180001478`
- `0x1800015e4`
- `0x1800018f4`
- `0x180001e08`
- `0x180005644`
- `0x180006d94`
- `0x180009068`
- `0x18000a65c`
- `0x18000bf1c`
- `0x18000c26c`
- `0x18000c540`
- `0x18000c7e4`
- `0x18000d424`
- `0x18000d610`
- `0x18000db4c`
- `0x18000e184`
- `0x18000f704`
- `0x18000f790`
- `0x18000fadc`
- `0x180010d44`
- `0x180010f4e`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e259`
- `msvcrt!_wcsicmp` at `0x18000e2ac`
- `msvcrt!_wcsicmp` at `0x18000e259`
- `msvcrt!_wcsicmp` at `0x18000e2ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e5ca`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e642`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e5ca`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000e642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e607`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e67c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e607`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e67c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000e29c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000e29c`
- `DMCmnUtils!SafeStringToDword` at `0x18000e8aa`
- `DMCmnUtils!SafeStringToDword` at `0x18000e8aa`

## string_xrefs

- `0x18000e2a5`: `.provxml`
- `0x18000e491`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000e625`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000e7b1`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000e814`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000e8ee`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000eb9b`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000ecf6`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000edc9`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000ee87`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000ef1f`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000efa0`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000f040`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000f0c8`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000f150`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`
- `0x18000f275`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`

## pseudocode

```c
__int64 __fastcall CConfigSource::ProcessElement(
        int *a1,
        int a2,
        int *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        int *a7)
{
  int *v9; // r15
  unsigned int XmlAttribute; // ebx
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // edi
  const wchar_t *ExtensionW; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r9
  void *v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // ebx
  int ConfigSetColumns; // eax
  int IsDuplicateUIMatch; // r14d
  _QWORD *v26; // rdi
  unsigned int v27; // r15d
  __int64 v28; // rcx
  unsigned int v30; // r14d
  _QWORD *v31; // rbx
  void *v32; // rdi
  unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  unsigned int j; // edi
  __int64 v37; // rcx
  unsigned int i; // edi
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 *v41; // r12
  __int64 v42; // rdx
  char v43; // r14
  wchar_t *v44; // rax
  int *v45; // rdx
  __int64 v46; // rcx
  unsigned int v47; // ecx
  __int64 v48; // rax
  int v49; // eax
  int v50; // ecx
  int v51; // ebx
  __int64 *v52; // r10
  __int64 *v53; // r13
  __int64 *k; // r14
  __int64 v55; // rax
  __int64 *v56; // r12
  __int64 v57; // rax
  __int64 *v58; // rcx
  __int64 *v59; // r9
  void (__fastcall **v60)(void *, __int64); // rax
  void *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r9
  _QWORD *v65; // rax
  _QWORD *v66; // rbx
  int v67; // r13d
  unsigned int v68; // r12d
  int v69; // esi
  int v70; // r14d
  unsigned __int16 *v71; // r15
  int v72; // ebx
  int v73; // edi
  _QWORD **v74; // rax
  int v75; // r12d
  unsigned __int16 **v76; // r14
  int inited; // eax
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  unsigned int v81; // edi
  volatile signed __int32 *v82; // rbx
  void (__fastcall ***v83)(_QWORD, __int64); // rcx
  int v84; // eax
  unsigned int v85; // r12d
  volatile signed __int32 *v86; // rbx
  int *v87; // rbx
  int v88; // eax
  volatile signed __int32 *v89; // rbx
  int v90; // eax
  __int64 v91; // rcx
  volatile signed __int32 *v92; // rbx
  unsigned __int16 *v93; // rbx
  bool v94; // zf
  volatile signed __int32 *v95; // rdi
  int v96; // eax
  volatile signed __int32 *v97; // rbx
  unsigned __int16 *v98; // rbx
  int v99; // eax
  volatile signed __int32 *v100; // rbx
  unsigned __int16 *v101; // rbx
  int v102; // eax
  volatile signed __int32 *v103; // rbx
  int *v104; // rdx
  volatile signed __int32 *v105; // rbx
  __int64 v106; // [rsp+20h] [rbp-E0h]
  int v107; // [rsp+20h] [rbp-E0h]
  int v108; // [rsp+38h] [rbp-C8h]
  unsigned int v109; // [rsp+48h] [rbp-B8h]
  char v110; // [rsp+70h] [rbp-90h] BYREF
  char v111; // [rsp+71h] [rbp-8Fh]
  int v112[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v113; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  void *v115; // [rsp+90h] [rbp-70h]
  int v116; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v117; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID pv[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v119; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v120; // [rsp+C0h] [rbp-40h] BYREF
  __int64 **v121; // [rsp+C8h] [rbp-38h] BYREF
  int v122[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v123; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v124; // [rsp+E8h] [rbp-18h]
  wchar_t *v125; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v126; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v127; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v128; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v129[32]; // [rsp+110h] [rbp+10h] BYREF
  void *v130; // [rsp+130h] [rbp+30h]
  int v131; // [rsp+138h] [rbp+38h]
  int v132; // [rsp+13Ch] [rbp+3Ch]
  int *v133; // [rsp+140h] [rbp+40h]
  __int64 v134; // [rsp+148h] [rbp+48h]
  unsigned __int16 **v135; // [rsp+150h] [rbp+50h]
  __int64 v136; // [rsp+158h] [rbp+58h]
  unsigned __int16 **v137; // [rsp+160h] [rbp+60h]
  __int64 v138; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v113 = a4;
  v126 = (unsigned __int16 *)a3;
  v116 = a2;
  v9 = a1;
  v125 = (wchar_t *)a1;
  v121 = (__int64 **)a7;
  v110 = 0;
  if ( !a2 )
  {
    v13 = 0;
    goto LABEL_9;
  }
  if ( a2 == 1 )
  {
    v13 = 1;
LABEL_9:
    v12 = 1;
    goto LABEL_10;
  }
  if ( a2 != 2 )
  {
    XmlAttribute = -2147024809;
    v11 = 1237;
LABEL_226:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
      (const char *)XmlAttribute,
      v106);
    return XmlAttribute;
  }
  if ( a6 == 2 )
    return 0;
  v110 = 1;
  v12 = 0;
  v13 = 1;
LABEL_10:
  String1 = 0;
  XmlAttribute = GetXmlAttribute((__int64)a3, (__int64)L"Type", v12, &String1);
  if ( (XmlAttribute & 0x80000000) != 0 )
  {
    if ( XmlAttribute != -2147023728 )
    {
      v11 = 1267;
      goto LABEL_226;
    }
    v119 = 1;
  }
  else
  {
    if ( _wcsicmp(String1, L"provxml") )
    {
      XmlAttribute = -2147024809;
      v11 = 1247;
      goto LABEL_226;
    }
    XmlAttribute = GetXmlAttribute((__int64)a3, (__int64)L"Data", 1, &String1);
    if ( (XmlAttribute & 0x80000000) != 0 )
    {
      v11 = 1251;
      goto LABEL_226;
    }
    ExtensionW = PathFindExtensionW(String1);
    if ( _wcsicmp(L".provxml", ExtensionW) )
    {
      if ( (unsigned int)dword_180019000 > 2 )
      {
        v116 = 2;
        *(_QWORD *)v122 = String1;
        v121 = (__int64 **)(v9 + 131);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v15,
          (__int64)byte_180015861,
          v16,
          v17,
          (int **)&v121,
          (int **)v122,
          (__int64)&v116);
      }
      return 0;
    }
    v119 = 2;
  }
  v117 = 0;
  XmlAttribute = GetXmlAttribute((__int64)a3, (__int64)L"ProfileID", v13, &v117);
  if ( (int)(XmlAttribute + 0x80000000) >= 0 && XmlAttribute != -2147023728 )
  {
    v11 = 1274;
    goto LABEL_226;
  }
  if ( v117 )
  {
    if ( a2 == 1 )
    {
      if ( v9[262] != 1 )
      {
        v106 = std::_Tree_buy<std::wstring>::_Buynode<unsigned short const * &>(v9 + 264, &v117);
        std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring &,std::_Tree_node<std::wstring,void *> *>(
          v9 + 264,
          pv,
          v22,
          v106 + 32);
        v23 = 0;
        if ( LOBYTE(pv[1]) )
        {
          *(_OWORD *)pv = 0;
          ConfigSetColumns = GetConfigSetColumns(a3, pv, &pv[1]);
          IsDuplicateUIMatch = ConfigSetColumns;
          if ( ConfigSetColumns < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x507,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
              (const char *)(unsigned int)ConfigSetColumns,
              v106);
            v26 = pv[0];
            if ( pv[0] )
            {
              v27 = (unsigned int)pv[1];
              if ( LODWORD(pv[1]) )
              {
                do
                {
                  v28 = v26[v23];
                  if ( v28 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                    v26[v23] = 0;
                  }
                  ++v23;
                }
                while ( v23 < v27 );
              }
              CoTaskMemFree(v26);
            }
            return (unsigned int)IsDuplicateUIMatch;
          }
          v123 = 0;
          v124 = 0;
          v30 = (unsigned int)pv[1];
          v31 = pv[0];
          MvPackKeys((__int64)&v123, (__int64)pv[0], (unsigned int)pv[1]);
          v32 = (void *)v123;
          if ( *((_QWORD *)&v123 + 1) - (_QWORD)v123 > 0xFFFFFFFF )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x50B,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
              (const char *)0x80070216LL,
              v106);
            if ( v32 )
              operator delete(v32);
            if ( v31 )
            {
              for ( i = 0; i < v30; ++i )
              {
                v39 = v31[i];
                if ( v39 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                  v31[i] = 0;
                }
              }
              CoTaskMemFree(v31);
            }
            return 2147942934LL;
          }
          if ( (unsigned int)dword_180019000 > 4 )
          {
            v112[0] = v9[262];
            v33 = v117;
            v135 = (unsigned __int16 **)v123;
            v136 = (unsigned int)(DWORD2(v123) - v123);
            v133 = v112;
            v134 = 4;
            if ( v117 )
            {
              v34 = -1;
              do
                ++v34;
              while ( v117[v34] );
              v35 = 2 * v34 + 2;
            }
            else
            {
              v33 = (unsigned __int16 *)&dword_18001490C;
              v35 = 2;
            }
            v130 = v33;
            v131 = v35;
            v132 = 0;
            tlgWriteTransfer_EventWriteTransfer(&dword_180019000, byte_180015621, 0, 0, 5, v129);
          }
          if ( v32 )
            operator delete(v32);
          if ( v31 )
          {
            for ( j = 0; j < v30; ++j )
            {
              v37 = v31[j];
              if ( v37 )
              {
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 16LL))(v37, 0);
                v31[j] = 0;
              }
            }
            CoTaskMemFree(v31);
          }
        }
      }
    }
    else if ( a2 == 2 )
    {
      v106 = std::_Tree_buy<std::wstring>::_Buynode<unsigned short const * &>(v9 + 268, &v117);
      std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring &,std::_Tree_node<std::wstring,void *> *>(
        v9 + 268,
        pv,
        v18,
        v106 + 32);
      if ( LOBYTE(pv[1]) )
      {
        if ( (unsigned int)dword_180019000 > 4 )
        {
          v112[0] = v9[262];
          *(_QWORD *)v122 = v117;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&dword_180019000,
            (__int64)&word_1800158A6,
            0,
            v19,
            (int **)v122,
            (__int64)v112);
        }
      }
    }
  }
  v20 = 0;
  v115 = 0;
  *(_QWORD *)v122 = 0;
  v111 = 0;
  if ( !v110 )
  {
    if ( a6 == 1 )
    {
      v20 = operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
      v115 = v20;
      pv[0] = v20;
      if ( v20 )
      {
        *(_QWORD *)v20 = &CXMLComparison::`vftable';
        *((_QWORD *)v20 + 5) = 7;
        *((_QWORD *)v20 + 4) = 0;
        *((_WORD *)v20 + 8) = 0;
        *((_QWORD *)v20 + 9) = 7;
        *((_QWORD *)v20 + 8) = 0;
        *((_WORD *)v20 + 24) = 0;
        *((_QWORD *)v20 + 10) = 0;
        *((_QWORD *)v20 + 11) = 0;
        *((_QWORD *)v20 + 12) = 0;
        *((_QWORD *)v20 + 13) = 0;
        goto LABEL_74;
      }
    }
    else
    {
      if ( a6 != 2 )
      {
        XmlAttribute = -2147024809;
        v21 = 1327;
LABEL_137:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
          (const char *)XmlAttribute,
          v106);
        return XmlAttribute;
      }
      v40 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v40;
      v115 = v40;
      if ( v40 )
      {
        v40[5] = 7;
        v40[4] = 0;
        *((_WORD *)v40 + 8) = 0;
        v40[9] = 7;
        v40[8] = 0;
        *((_WORD *)v40 + 24) = 0;
        v40[10] = 0;
        v40[11] = 0;
        v40[12] = 0;
        v40[13] = 0;
        *v40 = &CXMLComparisonUI::`vftable';
        *((_DWORD *)v40 + 28) = 0;
LABEL_74:
        *(_QWORD *)v122 = v20;
        (*(void (__fastcall **)(void *, int *))(*(_QWORD *)v20 + 80LL))(v20, a3);
        IsDuplicateUIMatch = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, _QWORD, char *))(*(_QWORD *)v20 + 8LL))(
                               v20,
                               v113,
                               a5,
                               &v110);
        if ( IsDuplicateUIMatch < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x534,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
            (const char *)(unsigned int)IsDuplicateUIMatch,
            v106);
          if ( v20 )
            goto LABEL_93;
          return (unsigned int)IsDuplicateUIMatch;
        }
        if ( v110 )
        {
          if ( a6 == 2 )
          {
            v41 = (__int64 *)v121;
            IsDuplicateUIMatch = CConfigSource::IsDuplicateUIMatch((__int64)v20, v121, &v110);
            if ( IsDuplicateUIMatch < 0 )
            {
              v42 = 1341;
              goto LABEL_81;
            }
            if ( !v110 )
            {
LABEL_128:
              if ( v20 )
              {
                v60 = *(void (__fastcall ***)(void *, __int64))v20;
                v61 = v20;
LABEL_130:
                (*v60)(v61, 1);
              }
              return 0;
            }
            IsDuplicateUIMatch = CConfigSource::FilterForPreferredUIMatches((__int64)v20, v41, &v110);
            if ( IsDuplicateUIMatch < 0 )
            {
              v42 = 1350;
LABEL_81:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v42,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
                (const char *)(unsigned int)IsDuplicateUIMatch,
                v106);
              if ( v20 )
                goto LABEL_93;
              return (unsigned int)IsDuplicateUIMatch;
            }
          }
          else
          {
            v112[0] = 0;
            v113 = 0;
            IsDuplicateUIMatch = GetXmlAttribute((__int64)a3, (__int64)L"Altitude", 0, &v113);
            if ( IsDuplicateUIMatch >= 0 )
            {
              IsDuplicateUIMatch = SafeStringToDword(v113, 10, 1, (unsigned int *)v112);
              if ( IsDuplicateUIMatch >= 0 )
                IsDuplicateUIMatch = 0;
            }
            if ( IsDuplicateUIMatch == -2147023728 )
            {
              v112[0] = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 48LL))(v20);
              v43 = 1;
              v111 = 1;
            }
            else
            {
              if ( IsDuplicateUIMatch < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x555,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
                  (const char *)(unsigned int)IsDuplicateUIMatch,
                  v106);
                if ( v20 )
LABEL_93:
                  (**(void (__fastcall ***)(void *, __int64))v20)(v20, 1);
                return (unsigned int)IsDuplicateUIMatch;
              }
              v43 = v111;
            }
            if ( (unsigned int)dword_180019000 > 5 )
            {
              LODWORD(v120) = v9[261];
              LODWORD(v113) = v112[0];
              v44 = String1;
              v45 = v9 + 131;
              v137 = &v120;
              v138 = 4;
              v135 = &v113;
              v136 = 4;
              if ( String1 )
              {
                v46 = -1;
                do
                  ++v46;
                while ( String1[v46] );
                v47 = 2 * v46 + 2;
              }
              else
              {
                v44 = (wchar_t *)&dword_18001490C;
                v47 = 2;
              }
              v133 = (int *)v44;
              v134 = v47;
              if ( v9 == (int *)-524LL )
              {
                v45 = &dword_18001490C;
                v49 = 2;
              }
              else
              {
                v48 = -1;
                do
                  ++v48;
                while ( *((_WORD *)v45 + v48) );
                v49 = 2 * v48 + 2;
              }
              v130 = v45;
              v131 = v49;
              v132 = 0;
              tlgWriteTransfer_EventWriteTransfer(&dword_180019000, &unk_1800157E8, 0, 0, 6, v129);
            }
            if ( !v43 || ((*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 32LL))(v20) & 3) == 3 )
            {
              v50 = v112[0];
              if ( (unsigned int)v9[261] >= v112[0] )
              {
                if ( (unsigned int)v9[261] > v112[0] )
                  v110 = 0;
              }
              else
              {
                v51 = *v9;
                v52 = (__int64 *)v121;
                v53 = v121[1];
                for ( k = *v121; k != v53; k += 2 )
                {
                  v55 = *k;
                  if ( v51 == *(_DWORD *)(*k + 116) && (!*(_BYTE *)(v55 + 120) || (*(_BYTE *)(v55 + 104) & 3) == 3) )
                    break;
                }
                if ( k != v53 )
                {
                  v56 = k + 2;
                  if ( k + 2 != v53 )
                  {
                    do
                    {
                      v57 = *v56;
                      if ( v51 != *(_DWORD *)(*v56 + 116) || *(_BYTE *)(v57 + 120) && (*(_BYTE *)(v57 + 104) & 3) != 3 )
                      {
                        v58 = k;
                        k += 2;
                        std::shared_ptr<CConfigSet>::operator=(v58, v56);
                      }
                      v56 += 2;
                    }
                    while ( v56 != v53 );
                    v50 = v112[0];
                    v20 = v115;
                    v52 = (__int64 *)v121;
                  }
                }
                v59 = (__int64 *)v52[1];
                if ( v59 != k )
                {
                  std::vector<std::shared_ptr<CConfigSet>>::erase(v52, (__int64 **)pv, k, v59);
                  v50 = v112[0];
                }
                v9[261] = v50;
              }
            }
          }
        }
        else
        {
          v120 = 0;
          v113 = 0;
          (*(void (__fastcall **)(void *, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v20 + 40LL))(
            v20,
            &v120,
            &v113);
          if ( (unsigned int)dword_180019000 > 5 )
          {
            *(_QWORD *)v112 = v117;
            v127 = v113;
            v128 = v120;
            *(_QWORD *)&v123 = String1;
            pv[0] = v9 + 131;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v62,
              (__int64)byte_1800156DB,
              v63,
              v64,
              (int **)pv,
              (int **)&v123,
              (int **)&v128,
              (int **)&v127,
              (int **)v112);
          }
        }
        if ( !v110 )
          goto LABEL_128;
        goto LABEL_138;
      }
    }
    XmlAttribute = -2147024882;
    v21 = 1329;
    goto LABEL_137;
  }
LABEL_138:
  v65 = operator new(0x80u);
  v66 = v65;
  if ( v65 )
  {
    memset_0(v65, 0, 0x68u);
    v66[13] = 0;
    v66[14] = 0;
    *((_BYTE *)v66 + 120) = 0;
  }
  else
  {
    v66 = 0;
  }
  v123 = 0;
  std::shared_ptr<CConfigSet>::_Resetp<CConfigSet>((CConfigSet **)&v123, (CConfigSet *)v66);
  if ( v116 != 2 )
  {
    v112[0] = 0;
    (*(void (__fastcall **)(void *, int *))(*(_QWORD *)v20 + 24LL))(v20, v112);
    v67 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 64LL))(v20);
    LODWORD(v113) = *v9;
    v68 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 72LL))(v20);
    v69 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 56LL))(v20);
    v70 = v9[262];
    v71 = String1;
    v72 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v20 + 32LL))(v20);
    v73 = v112[0];
    v74 = (_QWORD **)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v115 + 16LL))(v115);
    v109 = v68;
    v108 = v70;
    v75 = v116;
    v76 = (unsigned __int16 **)v123;
    inited = CConfigSet::InitConfigSet(v123, v116, v119, v74, v73, v72, v71, v108, v69, v109, (int)v113, v67, v111);
    v81 = inited;
    if ( inited < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A1,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
        (const char *)(unsigned int)inited,
        v107);
      v82 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
      if ( *((_QWORD *)&v123 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
          if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
        }
      }
      v83 = (void (__fastcall ***)(_QWORD, __int64))v115;
      if ( !v115 )
        return v81;
LABEL_148:
      (**v83)(v83, 1);
      return v81;
    }
    v9 = (int *)v125;
    goto LABEL_160;
  }
  v76 = (unsigned __int16 **)v123;
  v84 = CConfigSet::InitConfigSet(v123, 2, v119, 0, 0, 0, String1, v9[262], 0, 0, *v9, 1, 0);
  v85 = v84;
  if ( v84 >= 0 )
  {
    v75 = v116;
LABEL_160:
    if ( String1 )
    {
      v120 = 0;
      v87 = (int *)v126;
      v88 = GetXmlAttribute((__int64)v126, (__int64)L"SettingsGroup", 0, &v120);
      v81 = v88;
      if ( v88 < 0 && v88 != -2147023728 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B2,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
          (const char *)(unsigned int)v88,
          v107);
        v89 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
        if ( *((_QWORD *)&v123 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
            if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
          }
        }
        goto LABEL_167;
      }
      v113 = 0;
      v90 = GetXmlAttribute((__int64)v87, (__int64)L"ProductID", 0, &v113);
      v81 = v90;
      if ( v90 < 0 && v90 != -2147023728 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B9,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
          (const char *)(unsigned int)v90,
          v107);
        v92 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
        if ( *((_QWORD *)&v123 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v92)(v92);
            if ( _InterlockedExchangeAdd(v92 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v92 + 8LL))(v92);
          }
        }
        goto LABEL_167;
      }
      v93 = v113;
      v94 = v120 == 0;
      if ( !v120 )
      {
        if ( !v113 )
        {
          XmlAttribute = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5BD,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
            (const char *)0x80070057LL,
            v107);
          v95 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
          if ( *((_QWORD *)&v123 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v95)(v95);
              if ( _InterlockedExchangeAdd(v95 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v95 + 8LL))(v95);
            }
          }
          if ( v115 )
            (**(void (__fastcall ***)(void *, __int64))v115)(v115, 1);
          return XmlAttribute;
        }
        v94 = v120 == 0;
      }
      if ( !v94 )
        v93 = v120;
      if ( v76[5] )
        MicrosoftTelemetryAssertTriggeredNoArgs(v91);
      v96 = CoAllocString(v93, v76 + 5);
      v81 = v96;
      if ( v96 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C3,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
          (const char *)(unsigned int)v96,
          v107);
        v97 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
        if ( *((_QWORD *)&v123 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
            if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
          }
        }
        goto LABEL_167;
      }
      v98 = v113;
      if ( v113 )
      {
        if ( v76[7] )
          MicrosoftTelemetryAssertTriggeredNoArgs(v78);
        v99 = CoAllocString(v98, v76 + 7);
        v81 = v99;
        if ( v99 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5C7,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
            (const char *)(unsigned int)v99,
            v107);
          v100 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
          if ( *((_QWORD *)&v123 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v100)(v100);
              if ( _InterlockedExchangeAdd(v100 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v100 + 8LL))(v100);
            }
          }
          goto LABEL_167;
        }
      }
    }
    v101 = v117;
    if ( v117 )
    {
      if ( v76[8] )
        MicrosoftTelemetryAssertTriggeredNoArgs(v78);
      v102 = CoAllocString(v101, v76 + 8);
      v81 = v102;
      if ( v102 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5CD,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
          (const char *)(unsigned int)v102,
          v107);
        v103 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
        if ( *((_QWORD *)&v123 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v103)(v103);
            if ( _InterlockedExchangeAdd(v103 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v103 + 8LL))(v103);
          }
        }
LABEL_167:
        v83 = (void (__fastcall ***)(_QWORD, __int64))v115;
        if ( !v115 )
          return v81;
        goto LABEL_148;
      }
    }
    if ( v75 == 2 )
    {
      if ( (unsigned int)dword_180019000 <= 4 )
        goto LABEL_219;
      v104 = &dword_18001566C;
    }
    else
    {
      if ( (unsigned int)dword_180019000 <= 4 )
        goto LABEL_219;
      v104 = &dword_1800157AC;
    }
    v126 = v117;
    v125 = String1;
    pv[0] = v9 + 131;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v78,
      (__int64)v104,
      v79,
      v80,
      (int **)pv,
      (int **)&v125,
      (int **)&v126);
LABEL_219:
    std::vector<std::shared_ptr<CConfigSet>>::push_back(v121, &v123);
    v105 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
    if ( *((_QWORD *)&v123 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v105)(v105);
        if ( _InterlockedExchangeAdd(v105 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v105 + 8LL))(v105);
      }
    }
    v61 = v115;
    if ( !v115 )
      return 0;
    v60 = *(void (__fastcall ***)(void *, __int64))v115;
    goto LABEL_130;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5A9,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
    (const char *)(unsigned int)v84,
    v107);
  v86 = (volatile signed __int32 *)*((_QWORD *)&v123 + 1);
  if ( *((_QWORD *)&v123 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v123 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
      if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
    }
  }
  if ( v20 )
    (**(void (__fastcall ***)(void *, __int64))v20)(v20, 1);
  return v85;
}

```

## disassembly

```asm
0x18000e184  push    rbp
0x18000e186  push    rbx
0x18000e187  push    rsi
0x18000e188  push    rdi
0x18000e189  push    r12
0x18000e18b  push    r13
0x18000e18d  push    r14
0x18000e18f  push    r15
0x18000e191  lea     rbp, [rsp-88h]
0x18000e199  sub     rsp, 188h
0x18000e1a0  mov     rax, cs:__security_cookie
0x18000e1a7  xor     rax, rsp
0x18000e1aa  mov     [rbp+0C0h+var_50], rax
0x18000e1ae  mov     [rbp+0C0h+var_140], r9
0x18000e1b2  mov     r13, r8
0x18000e1b5  mov     [rbp+0C0h+var_C8], r8
0x18000e1b9  mov     r14d, edx
0x18000e1bc  mov     [rbp+0C0h+var_128], edx
0x18000e1bf  mov     r15, rcx
0x18000e1c2  mov     [rbp+0C0h+var_D0], rcx
0x18000e1c6  mov     rax, [rbp+0C0h+arg_30]
0x18000e1cd  mov     [rbp+0C0h+var_F8], rax
0x18000e1d1  xor     edx, edx
0x18000e1d3  mov     [rsp+1C0h+var_150], dl
0x18000e1d7  mov     ecx, r14d
0x18000e1da  mov     r12d, [rbp+0C0h+arg_28]
0x18000e1e1  test    r14d, r14d
0x18000e1e4  jz      short loc_18000E223
0x18000e1e6  sub     ecx, 1
0x18000e1e9  jz      short loc_18000E21A
0x18000e1eb  cmp     ecx, 1
0x18000e1ee  jz      short loc_18000E1FF
0x18000e1f0  mov     ebx, 80070057h
0x18000e1f5  mov     edx, 4D5h
0x18000e1fa  jmp     loc_18000F272
0x18000e1ff  cmp     r12d, 2
0x18000e203  jz      loc_18000EAE6
0x18000e209  mov     esi, 1
0x18000e20e  mov     [rsp+1C0h+var_150], sil
0x18000e213  mov     r8d, edx
0x18000e216  mov     edi, esi
0x18000e218  jmp     short loc_18000E22D
0x18000e21a  mov     esi, 1
0x18000e21f  mov     edi, esi
0x18000e221  jmp     short loc_18000E22A
0x18000e223  mov     esi, 1
0x18000e228  mov     edi, edx
0x18000e22a  mov     r8d, esi
0x18000e22d  mov     [rbp+0C0h+String1], rdx
0x18000e231  lea     r9, [rbp+0C0h+String1]
0x18000e235  lea     rdx, aType; "Type"
0x18000e23c  mov     rcx, r13
0x18000e23f  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000e244  mov     ebx, eax
0x18000e246  test    eax, eax
0x18000e248  js      loc_18000E314
0x18000e24e  lea     rdx, ?gc_szProvxmlExtension@@3QBGB+2; String2
0x18000e255  mov     rcx, [rbp+0C0h+String1]; String1
0x18000e259  call    cs:__imp__wcsicmp
0x18000e25f  test    eax, eax
0x18000e261  jz      short loc_18000E272
0x18000e263  mov     ebx, 80070057h
0x18000e268  mov     edx, 4DFh
0x18000e26d  jmp     loc_18000F272
0x18000e272  lea     r9, [rbp+0C0h+String1]
0x18000e276  mov     r8d, esi
0x18000e279  lea     rdx, aData; "Data"
0x18000e280  mov     rcx, r13
0x18000e283  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000e288  mov     ebx, eax
0x18000e28a  test    eax, eax
0x18000e28c  jns     short loc_18000E298
0x18000e28e  mov     edx, 4E3h
0x18000e293  jmp     loc_18000F272
0x18000e298  mov     rcx, [rbp+0C0h+String1]; pszPath
0x18000e29c  call    cs:__imp_PathFindExtensionW
0x18000e2a2  mov     rdx, rax; String2
0x18000e2a5  lea     rcx, ?gc_szProvxmlExtension@@3QBGB; ".provxml"
0x18000e2ac  call    cs:__imp__wcsicmp
0x18000e2b2  test    eax, eax
0x18000e2b4  jz      short loc_18000E30B
0x18000e2b6  mov     eax, cs:dword_180019000
0x18000e2bc  cmp     eax, 2
0x18000e2bf  jbe     loc_18000EAE6
0x18000e2c5  mov     [rbp+0C0h+var_128], 2
0x18000e2cc  mov     rax, [rbp+0C0h+String1]
0x18000e2d0  mov     qword ptr [rbp+0C0h+var_F0], rax
0x18000e2d4  lea     rax, [r15+20Ch]
0x18000e2db  mov     [rbp+0C0h+var_F8], rax
0x18000e2df  lea     rax, [rbp+0C0h+var_128]
0x18000e2e3  mov     [rsp+1C0h+var_190], rax
0x18000e2e8  lea     rax, [rbp+0C0h+var_F0]
0x18000e2ec  mov     [rsp+1C0h+var_198], rax
0x18000e2f1  lea     rax, [rbp+0C0h+var_F8]
0x18000e2f5  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18000e2fa  lea     rdx, byte_180015861
0x18000e301  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e306  jmp     loc_18000EAE6
0x18000e30b  mov     [rbp+0C0h+var_108], 2
0x18000e312  jmp     short loc_18000E323
0x18000e314  cmp     ebx, 80070490h
0x18000e31a  jnz     loc_18000F26D
0x18000e320  mov     [rbp+0C0h+var_108], esi
0x18000e323  mov     [rbp+0C0h+var_120], 0
0x18000e32b  lea     r9, [rbp+0C0h+var_120]
0x18000e32f  mov     r8d, edi
0x18000e332  lea     rdx, aProfileid; "ProfileID"
0x18000e339  mov     rcx, r13
0x18000e33c  call    ?GetXmlAttribute@@YAJPEAUIXmlReader@@PEBGW4AttributePresence@@PEAPEBG@Z; GetXmlAttribute(IXmlReader *,ushort const *,AttributePresence,ushort const * *)
0x18000e341  mov     ebx, eax
0x18000e343  mov     eax, 80000000h
0x18000e348  lea     ecx, [rbx+rax]
0x18000e34b  test    eax, ecx
0x18000e34d  jnz     short loc_18000E361
0x18000e34f  cmp     ebx, 80070490h
0x18000e355  jz      short loc_18000E361
0x18000e357  mov     edx, 4FAh
0x18000e35c  jmp     loc_18000F272
0x18000e361  xor     ebx, ebx
0x18000e363  cmp     [rbp+0C0h+var_120], rbx
0x18000e367  jz      loc_18000E3F4
0x18000e36d  mov     ecx, r14d
0x18000e370  sub     ecx, 1
0x18000e373  jz      loc_18000E431
0x18000e379  cmp     ecx, 1
0x18000e37c  jnz     short loc_18000E3F4
0x18000e37e  lea     rbx, [r15+430h]
0x18000e385  lea     rdx, [rbp+0C0h+var_120]
0x18000e389  mov     rcx, rbx
0x18000e38c  call    ??$_Buynode@AEAPEBG@?$_Tree_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEAPEBG@Z; std::_Tree_buy<std::wstring>::_Buynode<ushort const * &>(ushort const * &)
0x18000e391  lea     r9, [rax+20h]
0x18000e395  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18000e39a  lea     rdx, [rbp+0C0h+pv]
0x18000e39e  mov     rcx, rbx
0x18000e3a1  call    ??$_Insert_nohint@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_less_no_case@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring &,std::_Tree_node<std::wstring,void *> *>(bool,std::wstring &,std::_Tree_node<std::wstring,void *> *)
0x18000e3a6  xor     ebx, ebx
0x18000e3a8  cmp     byte ptr [rbp+0C0h+pv+8], bl
0x18000e3ab  jz      short loc_18000E3F4
0x18000e3ad  mov     eax, cs:dword_180019000
0x18000e3b3  cmp     eax, 4
0x18000e3b6  jbe     short loc_18000E3F4
0x18000e3b8  mov     eax, [r15+418h]
0x18000e3bf  mov     [rsp+1C0h+var_148], eax
0x18000e3c3  mov     rax, [rbp+0C0h+var_120]
0x18000e3c7  mov     qword ptr [rbp+0C0h+var_F0], rax
0x18000e3cb  lea     rax, [rsp+1C0h+var_148]
0x18000e3d0  mov     [rsp+1C0h+var_198], rax
0x18000e3d5  lea     rax, [rbp+0C0h+var_F0]
0x18000e3d9  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18000e3de  xor     r8d, r8d
0x18000e3e1  lea     rdx, word_1800158A6
0x18000e3e8  lea     rcx, dword_180019000
0x18000e3ef  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000e3f4  mov     rdi, rbx
0x18000e3f7  mov     [rbp+0C0h+var_130], rbx
0x18000e3fb  mov     qword ptr [rbp+0C0h+var_F0], rbx
0x18000e3ff  mov     [rsp+1C0h+var_14F], bl
0x18000e403  cmp     [rsp+1C0h+var_150], bl
0x18000e407  jnz     loc_18000EBB4
0x18000e40d  mov     ecx, r12d
0x18000e410  sub     ecx, 1
0x18000e413  jz      loc_18000E6F4
0x18000e419  cmp     ecx, 1
0x18000e41c  jz      loc_18000E68B
0x18000e422  mov     ebx, 80070057h
0x18000e427  mov     edx, 52Fh
0x18000e42c  jmp     loc_18000EB98
0x18000e431  cmp     [r15+418h], esi
0x18000e438  jz      short loc_18000E3F4
0x18000e43a  lea     rbx, [r15+420h]
0x18000e441  lea     rdx, [rbp+0C0h+var_120]
0x18000e445  mov     rcx, rbx
0x18000e448  call    ??$_Buynode@AEAPEBG@?$_Tree_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEAPEBG@Z; std::_Tree_buy<std::wstring>::_Buynode<ushort const * &>(ushort const * &)
0x18000e44d  lea     r9, [rax+20h]
0x18000e451  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18000e456  lea     rdx, [rbp+0C0h+pv]
0x18000e45a  mov     rcx, rbx
0x18000e45d  call    ??$_Insert_nohint@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_less_no_case@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring &,std::_Tree_node<std::wstring,void *> *>(bool,std::wstring &,std::_Tree_node<std::wstring,void *> *)
0x18000e462  xor     ebx, ebx
0x18000e464  cmp     byte ptr [rbp+0C0h+pv+8], bl
0x18000e467  jz      short loc_18000E3F4
0x18000e469  xorps   xmm0, xmm0
0x18000e46c  movups  xmmword ptr [rbp+0C0h+pv], xmm0
0x18000e470  lea     r8, [rbp+0C0h+pv+8]
0x18000e474  lea     rdx, [rbp+0C0h+pv]
0x18000e478  mov     rcx, r13
0x18000e47b  call    GetConfigSetColumns
0x18000e480  mov     r14d, eax
0x18000e483  test    eax, eax
0x18000e485  jns     short loc_18000E4ED
0x18000e487  mov     rcx, [rbp+0C8h]; this
0x18000e48e  mov     r9d, eax; char *
0x18000e491  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000e498  mov     edx, 507h; void *
0x18000e49d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4a2  nop
0x18000e4a3  mov     rdi, [rbp+0C0h+pv]
0x18000e4a7  test    rdi, rdi
0x18000e4aa  jz      short loc_18000E4E5
0x18000e4ac  mov     r15d, dword ptr [rbp+0C0h+pv+8]
0x18000e4b0  xor     r13d, r13d
0x18000e4b3  test    r15d, r15d
0x18000e4b6  jz      short loc_18000E4DB
0x18000e4b8  mov     r12d, ebx
0x18000e4bb  mov     rcx, [rdi+r12*8]
0x18000e4bf  test    rcx, rcx
0x18000e4c2  jz      short loc_18000E4D4
0x18000e4c4  mov     rax, [rcx]
0x18000e4c7  mov     rax, [rax+10h]
0x18000e4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d0  mov     [rdi+r12*8], r13
0x18000e4d4  add     ebx, esi
0x18000e4d6  cmp     ebx, r15d
0x18000e4d9  jb      short loc_18000E4B8
0x18000e4db  mov     rcx, rdi; pv
0x18000e4de  call    cs:__imp_CoTaskMemFree
0x18000e4e4  nop
0x18000e4e5  mov     eax, r14d
0x18000e4e8  jmp     loc_18000F28A
0x18000e4ed  xorps   xmm0, xmm0
0x18000e4f0  movdqu  [rbp+0C0h+var_E8], xmm0
0x18000e4f5  mov     [rbp+0C0h+var_D8], rbx
0x18000e4f9  mov     r14, [rbp+0C0h+pv+8]
0x18000e4fd  mov     r8d, r14d
0x18000e500  mov     rbx, [rbp+0C0h+pv]
0x18000e504  mov     rdx, rbx
0x18000e507  lea     rcx, [rbp+0C0h+var_E8]
0x18000e50b  call    ?MvPackKeys@@YAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEAPEAUIMVKey@@K@Z; MvPackKeys(std::vector<uchar> &,IMVKey * *,ulong)
0x18000e510  mov     rdx, qword ptr [rbp+0C0h+var_E8+8]
0x18000e514  mov     rdi, qword ptr [rbp+0C0h+var_E8]
0x18000e518  sub     rdx, rdi
0x18000e51b  mov     eax, 0FFFFFFFFh
0x18000e520  cmp     rdx, rax
0x18000e523  ja      loc_18000E615
0x18000e529  mov     eax, cs:dword_180019000
0x18000e52f  cmp     eax, 4
0x18000e532  jbe     loc_18000E5C0
0x18000e538  mov     eax, [r15+418h]
0x18000e53f  mov     [rsp+1C0h+var_148], eax
0x18000e543  mov     rcx, [rbp+0C0h+var_120]
0x18000e547  mov     [rbp+0C0h+var_70], rdi
0x18000e54b  mov     dword ptr [rbp+0C0h+var_68], edx
0x18000e54e  xor     edx, edx
0x18000e550  mov     dword ptr [rbp+0C0h+var_68+4], edx
0x18000e553  lea     rax, [rsp+1C0h+var_148]
0x18000e558  mov     [rbp+0C0h+var_80], rax
0x18000e55c  mov     [rbp+0C0h+var_78], 4
0x18000e564  test    rcx, rcx
0x18000e567  jz      short loc_18000E57F
0x18000e569  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e56d  inc     rax
0x18000e570  cmp     [rcx+rax*2], dx
0x18000e574  jnz     short loc_18000E56D
0x18000e576  lea     eax, ds:2[rax*2]
0x18000e57d  jmp     short loc_18000E58B
0x18000e57f  lea     rcx, dword_18001490C
0x18000e586  mov     eax, 2
0x18000e58b  mov     [rbp+0C0h+var_90], rcx
0x18000e58f  mov     [rbp+0C0h+var_88], eax
0x18000e592  mov     [rbp+0C0h+var_84], edx
0x18000e595  lea     rax, [rbp+0C0h+var_B0]
0x18000e599  mov     [rsp+1C0h+var_198], rax
0x18000e59e  mov     [rsp+1C0h+var_1A0], 5
0x18000e5a6  xor     r9d, r9d
0x18000e5a9  xor     r8d, r8d
0x18000e5ac  lea     rdx, byte_180015621
0x18000e5b3  lea     rcx, dword_180019000
0x18000e5ba  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e5bf  nop
0x18000e5c0  xor     edx, edx
0x18000e5c2  test    rdi, rdi
0x18000e5c5  jz      short loc_18000E5D2
0x18000e5c7  mov     rcx, rdi
0x18000e5ca  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000e5d0  xor     edx, edx
0x18000e5d2  test    rbx, rbx
0x18000e5d5  jz      short loc_18000E60E
0x18000e5d7  mov     edi, edx
0x18000e5d9  test    r14d, r14d
0x18000e5dc  jz      short loc_18000E604
0x18000e5de  mov     eax, edi
0x18000e5e0  mov     rcx, [rbx+rax*8]
0x18000e5e4  test    rcx, rcx
0x18000e5e7  jz      short loc_18000E5FD
0x18000e5e9  mov     rax, [rcx]
0x18000e5ec  mov     rax, [rax+10h]
0x18000e5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f5  mov     eax, edi
0x18000e5f7  xor     edx, edx
0x18000e5f9  mov     [rbx+rax*8], rdx
0x18000e5fd  add     edi, esi
0x18000e5ff  cmp     edi, r14d
0x18000e602  jb      short loc_18000E5DE
0x18000e604  mov     rcx, rbx; pv
0x18000e607  call    cs:__imp_CoTaskMemFree
0x18000e60d  nop
0x18000e60e  xor     ebx, ebx
0x18000e610  jmp     loc_18000E3F4
0x18000e615  mov     rcx, [rbp+0C8h]; this
0x18000e61c  mov     r13d, 80070216h
  ... truncated ...
```
