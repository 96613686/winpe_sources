# s_GetStartMenuFilesScope

- ea: `0x18003bc20`
- end: `0x18003beba`
- name: `s_GetStartMenuFilesScope`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025da0`

## callees

- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x180010fcc`
- `0x1800129f8`
- `0x180013d94`
- `0x180029e98`
- `0x180039b1c`
- `0x180039b70`
- `0x180039bfc`
- `0x18003a038`
- `0x18003a384`
- `0x18003a3b0`
- `0x18003a420`
- `0x18003a5e0`
- `0x18003a784`
- `0x18003a888`
- `0x18003bc20`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bc8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bc67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bc67`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003bcc1`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003bcec`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003bcc1`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003bcec`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromKnownFolder` at `0x18003bd80`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromKnownFolder` at `0x18003bd80`

## pseudocode

```c
__int64 __fastcall s_GetStartMenuFilesScope(__int64 a1, _QWORD *a2)
{
  unsigned int QueryFilesSetting; // edi
  unsigned int QueryCommSetting; // r14d
  int Scope; // ebx
  __int64 v7; // rax
  __int64 v8; // rsi
  struct IScope **v9; // rax
  __int64 v10; // rsi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  struct _DPA *v13; // [rsp+88h] [rbp+48h] BYREF
  struct IScope *v14; // [rsp+90h] [rbp+50h] BYREF
  __int64 v15; // [rsp+98h] [rbp+58h] BYREF

  *a2 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
         0,
         1u,
         &hKey) )
  {
    QueryFilesSetting = CStartMenuTopRowset::s_GetQueryFilesSetting(0);
    QueryCommSetting = CStartMenuTopRowset::s_GetQueryCommSetting(0);
  }
  else
  {
    QueryFilesSetting = CStartMenuTopRowset::s_GetQueryFilesSetting(hKey);
    QueryCommSetting = CStartMenuTopRowset::s_GetQueryCommSetting(hKey);
    RegCloseKey(hKey);
  }
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v14);
  if ( !QueryFilesSetting )
  {
    Scope = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, &v14);
    goto LABEL_29;
  }
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v15);
  v7 = ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v15);
  Scope = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v7);
  if ( Scope >= 0 )
  {
    v8 = v15;
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v13);
    v9 = (struct IScope **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v13);
    Scope = CStartMenuProgramsResultSetManager::s_GetScope(v9);
    if ( Scope >= 0 )
      Scope = s_IncludeOneScope(v8, v13, 0);
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v13);
    if ( Scope >= 0 )
    {
      if ( QueryFilesSetting == 2 )
        goto LABEL_34;
      v10 = v15;
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v13);
      ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v13);
      Scope = SHCreateScopeItemFromKnownFolder(&FOLDERID_Public, 1, 2);
      if ( Scope >= 0 )
        Scope = (*(__int64 (__fastcall **)(__int64, struct _DPA *))(*(_QWORD *)v10 + 24LL))(v10, v13);
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v13);
      if ( Scope >= 0 )
      {
LABEL_34:
        Scope = CStartMenuFilesResultSetManager::s_GetTopLevelScope(QueryFilesSetting, a1, &v14);
        if ( Scope >= 0 )
        {
          v13 = 0;
          if ( !(unsigned int)CDPA_Base<ICondition,CTContainer_PolicyUnOwned<ICondition>>::Create(&v13) )
            goto LABEL_20;
          Scope = CStartMenuTopRowset::s_FindAndSortLibraryGroups(QueryFilesSetting, &v13, 0);
          if ( Scope >= 0 )
            Scope = s_IncludeExcludeLibraryScopes(&v13, v15, v14);
          CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::DestroyCallback(&v13);
          if ( Scope < 0 )
            goto LABEL_27;
          if ( (unsigned int)CDPA_Base<ICondition,CTContainer_PolicyUnOwned<ICondition>>::Create(&v13) )
          {
            Scope = CStartMenuTopRowset::s_FindAndSortLocationGroups(QueryFilesSetting, QueryCommSetting, &v13, 0);
            if ( Scope >= 0 )
              Scope = s_IncludeExcludeLibraryScopes(&v13, v15, v14);
            CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::DestroyCallback(&v13);
            if ( Scope >= 0 )
            {
              Scope = CStartMenuFilesResultSetManager::s_ExcludeProgramsScopes(v14);
              if ( Scope >= 0 && QueryFilesSetting != 2 )
                Scope = CStartMenuFilesResultSetManager::s_ExcludePublicFolders(v14);
            }
          }
          else
          {
LABEL_20:
            Scope = -2147024882;
          }
LABEL_27:
          CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::~CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>(&v13);
        }
      }
    }
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v15);
LABEL_29:
  if ( Scope >= 0 )
    *a2 = ATL::CComPtrBase<IScope>::Detach(&v14);
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v14);
  return (unsigned int)Scope;
}

```

## disassembly

```asm
0x18003bc20  push    rbp
0x18003bc22  push    rbx
0x18003bc23  push    rsi
0x18003bc24  push    rdi
0x18003bc25  push    r12
0x18003bc27  push    r14
0x18003bc29  push    r15
0x18003bc2b  mov     rbp, rsp
0x18003bc2e  sub     rsp, 40h
0x18003bc32  mov     r12, rdx
0x18003bc35  mov     qword ptr [rdx], 0
0x18003bc3c  mov     r15, rcx
0x18003bc3f  mov     [rbp+hKey], 0
0x18003bc47  lea     rax, [rbp+hKey]
0x18003bc4b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003bc52  lea     rdx, pwszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003bc59  mov     [rsp+40h+phkResult], rax; phkResult
0x18003bc5e  mov     r9d, 1; samDesired
0x18003bc64  xor     r8d, r8d; ulOptions
0x18003bc67  call    cs:__imp_RegOpenKeyExW
0x18003bc6d  test    eax, eax
0x18003bc6f  jnz     short loc_18003BC94
0x18003bc71  mov     rcx, [rbp+hKey]
0x18003bc75  call    ?s_GetQueryFilesSetting@CStartMenuTopRowset@@SA?AW4_QUERY_FILES@@PEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryFilesSetting(HKEY__ *)
0x18003bc7a  mov     rcx, [rbp+hKey]; HKEY
0x18003bc7e  mov     edi, eax
0x18003bc80  call    ?s_GetQueryCommSetting@CStartMenuTopRowset@@SAHPEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryCommSetting(HKEY__ *)
0x18003bc85  mov     rcx, [rbp+hKey]; hKey
0x18003bc89  mov     r14d, eax
0x18003bc8c  call    cs:__imp_RegCloseKey
0x18003bc92  jmp     short loc_18003BCA7
0x18003bc94  xor     ecx, ecx
0x18003bc96  call    ?s_GetQueryFilesSetting@CStartMenuTopRowset@@SA?AW4_QUERY_FILES@@PEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryFilesSetting(HKEY__ *)
0x18003bc9b  xor     ecx, ecx; HKEY
0x18003bc9d  mov     edi, eax
0x18003bc9f  call    ?s_GetQueryCommSetting@CStartMenuTopRowset@@SAHPEAUHKEY__@@@Z; CStartMenuTopRowset::s_GetQueryCommSetting(HKEY__ *)
0x18003bca4  mov     r14d, eax
0x18003bca7  lea     rcx, [rbp+arg_10]; void *
0x18003bcab  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003bcb0  test    edi, edi
0x18003bcb2  jnz     short loc_18003BCCE
0x18003bcb4  lea     r8, [rbp+arg_10]
0x18003bcb8  xor     ecx, ecx
0x18003bcba  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x18003bcc1  call    cs:__imp_SHCreateScope
0x18003bcc7  mov     ebx, eax
0x18003bcc9  jmp     loc_18003BE8F
0x18003bcce  lea     rcx, [rbp+arg_18]; void *
0x18003bcd2  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003bcd7  lea     rcx, [rbp+arg_18]
0x18003bcdb  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003bce0  mov     r8, rax
0x18003bce3  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x18003bcea  xor     ecx, ecx
0x18003bcec  call    cs:__imp_SHCreateScope
0x18003bcf2  mov     ebx, eax
0x18003bcf4  test    eax, eax
0x18003bcf6  js      loc_18003BE86
0x18003bcfc  mov     rsi, [rbp+arg_18]
0x18003bd00  lea     rcx, [rbp+arg_8]; void *
0x18003bd04  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003bd09  lea     rcx, [rbp+arg_8]
0x18003bd0d  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003bd12  mov     rcx, rax; struct IScope **
0x18003bd15  call    ?s_GetScope@CStartMenuProgramsResultSetManager@@SAJPEAPEAUIScope@@@Z; CStartMenuProgramsResultSetManager::s_GetScope(IScope * *)
0x18003bd1a  mov     ebx, eax
0x18003bd1c  test    eax, eax
0x18003bd1e  js      short loc_18003BD31
0x18003bd20  mov     rdx, [rbp+arg_8]
0x18003bd24  xor     r8d, r8d
0x18003bd27  mov     rcx, rsi
0x18003bd2a  call    s_IncludeOneScope
0x18003bd2f  mov     ebx, eax
0x18003bd31  lea     rcx, [rbp+arg_8]
0x18003bd35  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003bd3a  test    ebx, ebx
0x18003bd3c  js      loc_18003BE86
0x18003bd42  cmp     edi, 2
0x18003bd45  jz      short loc_18003BDB2
0x18003bd47  mov     rsi, [rbp+arg_18]
0x18003bd4b  lea     rcx, [rbp+arg_8]; void *
0x18003bd4f  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003bd54  lea     rcx, [rbp+arg_8]
0x18003bd58  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003bd5d  xor     r9d, r9d
0x18003bd60  mov     [rsp+40h+var_18], rax
0x18003bd65  lea     rax, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18003bd6c  lea     rcx, FOLDERID_Public
0x18003bd73  mov     [rsp+40h+phkResult], rax
0x18003bd78  lea     edx, [r9+1]
0x18003bd7c  lea     r8d, [r9+2]
0x18003bd80  call    cs:__imp_SHCreateScopeItemFromKnownFolder
0x18003bd86  mov     ebx, eax
0x18003bd88  test    eax, eax
0x18003bd8a  js      short loc_18003BDA1
0x18003bd8c  mov     rax, [rsi]
0x18003bd8f  mov     rcx, rsi
0x18003bd92  mov     rdx, [rbp+arg_8]
0x18003bd96  mov     rax, [rax+18h]
0x18003bd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd9f  mov     ebx, eax
0x18003bda1  lea     rcx, [rbp+arg_8]
0x18003bda5  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003bdaa  test    ebx, ebx
0x18003bdac  js      loc_18003BE86
0x18003bdb2  lea     r8, [rbp+arg_10]
0x18003bdb6  mov     rdx, r15
0x18003bdb9  mov     ecx, edi
0x18003bdbb  call    ?s_GetTopLevelScope@CStartMenuFilesResultSetManager@@SAJW4_QUERY_FILES@@PEAUINamedPropertyStore@@PEAPEAUIScope@@@Z; CStartMenuFilesResultSetManager::s_GetTopLevelScope(_QUERY_FILES,INamedPropertyStore *,IScope * *)
0x18003bdc0  mov     ebx, eax
0x18003bdc2  test    eax, eax
0x18003bdc4  js      loc_18003BE86
0x18003bdca  lea     rcx, [rbp+arg_8]
0x18003bdce  mov     [rbp+arg_8], 0
0x18003bdd6  call    ?Create@?$CDPA_Base@UICondition@@V?$CTContainer_PolicyUnOwned@UICondition@@@@@@QEAAHH@Z; CDPA_Base<ICondition,CTContainer_PolicyUnOwned<ICondition>>::Create(int)
0x18003bddb  test    eax, eax
0x18003bddd  jz      short loc_18003BE20
0x18003bddf  xor     r8d, r8d
0x18003bde2  lea     rdx, [rbp+arg_8]
0x18003bde6  mov     ecx, edi
0x18003bde8  call    ?s_FindAndSortLibraryGroups@CStartMenuTopRowset@@SAJW4_QUERY_FILES@@PEAV?$CDPA@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@PEAUIUnknown@@@Z; CStartMenuTopRowset::s_FindAndSortLibraryGroups(_QUERY_FILES,CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>> *,IUnknown *)
0x18003bded  mov     ebx, eax
0x18003bdef  test    eax, eax
0x18003bdf1  js      short loc_18003BE06
0x18003bdf3  mov     r8, [rbp+arg_10]
0x18003bdf7  lea     rcx, [rbp+arg_8]
0x18003bdfb  mov     rdx, [rbp+arg_18]
0x18003bdff  call    s_IncludeExcludeLibraryScopes
0x18003be04  mov     ebx, eax
0x18003be06  lea     rcx, [rbp+arg_8]
0x18003be0a  call    ?DestroyCallback@?$CDPA@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@QEAAXP6AHPEAVCLibraryInfo@@PEAX@Z1@Z; CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::DestroyCallback(int (*)(CLibraryInfo *,void *),void *)
0x18003be0f  test    ebx, ebx
0x18003be11  js      short loc_18003BE7D
0x18003be13  lea     rcx, [rbp+arg_8]
0x18003be17  call    ?Create@?$CDPA_Base@UICondition@@V?$CTContainer_PolicyUnOwned@UICondition@@@@@@QEAAHH@Z; CDPA_Base<ICondition,CTContainer_PolicyUnOwned<ICondition>>::Create(int)
0x18003be1c  test    eax, eax
0x18003be1e  jnz     short loc_18003BE27
0x18003be20  mov     ebx, 8007000Eh
0x18003be25  jmp     short loc_18003BE7D
0x18003be27  xor     r9d, r9d
0x18003be2a  lea     r8, [rbp+arg_8]
0x18003be2e  mov     edx, r14d
0x18003be31  mov     ecx, edi
0x18003be33  call    ?s_FindAndSortLocationGroups@CStartMenuTopRowset@@SAJW4_QUERY_FILES@@HPEAV?$CDPA@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@PEAUIUnknown@@@Z; CStartMenuTopRowset::s_FindAndSortLocationGroups(_QUERY_FILES,int,CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>> *,IUnknown *)
0x18003be38  mov     ebx, eax
0x18003be3a  test    eax, eax
0x18003be3c  js      short loc_18003BE51
0x18003be3e  mov     r8, [rbp+arg_10]
0x18003be42  lea     rcx, [rbp+arg_8]
0x18003be46  mov     rdx, [rbp+arg_18]
0x18003be4a  call    s_IncludeExcludeLibraryScopes
0x18003be4f  mov     ebx, eax
0x18003be51  lea     rcx, [rbp+arg_8]
0x18003be55  call    ?DestroyCallback@?$CDPA@VCLibraryInfo@@V?$CTContainer_PolicyUnOwned@VCLibraryInfo@@@@@@QEAAXP6AHPEAVCLibraryInfo@@PEAX@Z1@Z; CDPA<CLibraryInfo,CTContainer_PolicyUnOwned<CLibraryInfo>>::DestroyCallback(int (*)(CLibraryInfo *,void *),void *)
0x18003be5a  test    ebx, ebx
0x18003be5c  js      short loc_18003BE7D
0x18003be5e  mov     rcx, [rbp+arg_10]; struct IScope *
0x18003be62  call    ?s_ExcludeProgramsScopes@CStartMenuFilesResultSetManager@@SAJPEAUIScope@@@Z; CStartMenuFilesResultSetManager::s_ExcludeProgramsScopes(IScope *)
0x18003be67  mov     ebx, eax
0x18003be69  test    eax, eax
0x18003be6b  js      short loc_18003BE7D
0x18003be6d  cmp     edi, 2
0x18003be70  jz      short loc_18003BE7D
0x18003be72  mov     rcx, [rbp+arg_10]; struct IScope *
0x18003be76  call    ?s_ExcludePublicFolders@CStartMenuFilesResultSetManager@@SAJPEAUIScope@@@Z; CStartMenuFilesResultSetManager::s_ExcludePublicFolders(IScope *)
0x18003be7b  mov     ebx, eax
0x18003be7d  lea     rcx, [rbp+arg_8]
0x18003be81  call    ??1?$CDPA_Base@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@QEAA@XZ; CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::~CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>(void)
0x18003be86  lea     rcx, [rbp+arg_18]
0x18003be8a  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003be8f  test    ebx, ebx
0x18003be91  js      short loc_18003BEA0
0x18003be93  lea     rcx, [rbp+arg_10]
0x18003be97  call    ?Detach@?$CComPtrBase@UIScope@@@ATL@@QEAAPEAUIScope@@XZ; ATL::CComPtrBase<IScope>::Detach(void)
0x18003be9c  mov     [r12], rax
0x18003bea0  lea     rcx, [rbp+arg_10]
0x18003bea4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003bea9  mov     eax, ebx
0x18003beab  add     rsp, 40h
0x18003beaf  pop     r15
0x18003beb1  pop     r14
0x18003beb3  pop     r12
0x18003beb5  pop     rdi
0x18003beb6  pop     rsi
0x18003beb7  pop     rbx
0x18003beb8  pop     rbp
0x18003beb9  retn
```
