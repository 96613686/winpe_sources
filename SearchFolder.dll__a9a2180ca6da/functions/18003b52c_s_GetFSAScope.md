# s_GetFSAScope

- ea: `0x18003b52c`
- end: `0x18003bc0b`
- name: `s_GetFSAScope`
- size: `1759`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002cc10`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c74`
- `0x180005c88`
- `0x180006900`
- `0x180006948`
- `0x1800070ec`
- `0x1800129ec`
- `0x1800129f8`
- `0x18002e8e4`
- `0x18003a30c`
- `0x18003b52c`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetKnownFolderItem` at `0x18003b8eb`
- `SHELL32!SHGetKnownFolderItem` at `0x18003b8eb`
- `SHELL32!SHGetKnownFolderPath` at `0x18003b661`
- `SHELL32!SHGetKnownFolderPath` at `0x18003b661`
- `SHELL32!__imp_PathComparePaths` at `0x18003b7ab`
- `SHELL32!__imp_PathComparePaths` at `0x18003b7ab`
- `SHLWAPI!UrlGetPartW` at `0x18003b80b`
- `SHLWAPI!UrlGetPartW` at `0x18003b80b`
- `SHLWAPI!PathIsUNCW` at `0x18003bace`
- `SHLWAPI!PathIsUNCW` at `0x18003bace`
- `SHLWAPI!__imp_StrCmpICW` at `0x18003b822`
- `SHLWAPI!__imp_StrCmpICW` at `0x18003b822`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003b588`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScope` at `0x18003b588`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromShellItem` at `0x18003bb2a`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeItemFromShellItem` at `0x18003bb2a`
- `api-ms-win-winrt-search-folder-l1-1-0!SEARCH_RemoteLocationsCscStateCache_IsRemoteLocationInCsc` at `0x18003baea`
- `api-ms-win-winrt-search-folder-l1-1-0!SEARCH_RemoteLocationsCscStateCache_IsRemoteLocationInCsc` at `0x18003baea`

## pseudocode

```c
__int64 __fastcall s_GetFSAScope(_QWORD *a1)
{
  __int64 v2; // rax
  HRESULT PartW; // ebx
  struct IScope **v4; // rax
  int v5; // edi
  HRESULT v6; // eax
  int v7; // r14d
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned int i; // edi
  PWSTR v12; // rcx
  bool v13; // di
  void **v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  void **v17; // rax
  DWORD v18; // edi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchOut; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+3Ch] [rbp-C4h] BYREF
  LPCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  void *v26; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR pszIn; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  struct IEnumIDList *v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  PWSTR v34[7]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v35[7]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszOut[264]; // [rsp+130h] [rbp+30h] BYREF

  *a1 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v30);
  v2 = ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v30);
  PartW = SHCreateScope(0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v2);
  if ( PartW >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v29);
    v4 = (struct IScope **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v29);
    if ( (int)CStartMenuFilesResultSetManager::s_GetAllIndexFilesScope(v4) < 0 )
    {
      PartW = 0;
      v7 = 1;
    }
    else
    {
      v35[0] = FOLDERID_Windows;
      v35[1] = FOLDERID_LocalAppData;
      v35[2] = FOLDERID_LocalAppDataLow;
      v35[3] = FOLDERID_RoamingAppData;
      v35[4] = FOLDERID_CommonStartMenu;
      v35[5] = FOLDERID_ProgramFilesX86;
      v35[6] = FOLDERID_ProgramFilesX64;
      `eh vector constructor iterator'(
        v34,
        8u,
        7u,
        (void (*)(void *))ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>,
        (void (*)(void *))CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>);
      v5 = 0;
      while ( (unsigned __int64)v5 < 7 )
      {
        v6 = SHGetKnownFolderPath((const KNOWNFOLDERID *const)&v35[v5], 0x5000u, 0, &v34[v5]);
        PartW = 0;
        if ( v6 != -2147024894 )
          PartW = v6;
        ++v5;
        if ( PartW < 0 )
        {
          v7 = 1;
          goto LABEL_29;
        }
      }
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v28);
      v8 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v29);
      PartW = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v8 + 64LL))(
                v8,
                0,
                &GUID_2c1c7e2e_2d0e_4059_831e_1e6f82335c2e,
                &v28);
      if ( !PartW )
      {
        while ( 1 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v22);
          v9 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v28);
          PartW = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *, _QWORD))(*(_QWORD *)v9 + 24LL))(
                    v9,
                    1,
                    &GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0,
                    &v22,
                    0);
          if ( PartW )
            goto LABEL_27;
          v24 = 0;
          PartW = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 32LL))(v22, &v24);
          if ( PartW < 0 )
            goto LABEL_27;
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&pszPath);
          v10 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v22);
          PartW = (*(__int64 (__fastcall **)(__int64, GUID *, LPCWSTR *))(*(_QWORD *)v10 + 120LL))(
                    v10,
                    &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                    &pszPath);
          if ( PartW >= 0 )
            break;
LABEL_26:
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&pszPath);
LABEL_27:
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v22);
          if ( PartW )
            goto LABEL_28;
        }
        v26 = 0;
        PartW = (*(__int64 (__fastcall **)(LPCWSTR, __int64, void **))(*(_QWORD *)pszPath + 40LL))(
                  pszPath,
                  2147844096LL,
                  &v26);
        if ( PartW < 0 )
        {
          pszIn = 0;
          v13 = 0;
          PartW = (*(__int64 (__fastcall **)(LPCWSTR, __int64, PCWSTR *))(*(_QWORD *)pszPath + 40LL))(
                    pszPath,
                    2147909632LL,
                    &pszIn);
          if ( PartW >= 0 )
          {
            pcchOut = 260;
            PartW = UrlGetPartW(pszIn, pszOut, &pcchOut, 1u, 0);
            if ( PartW >= 0 )
              v13 = StrCmpICW(L"csc", pszOut) == 0;
          }
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pszIn);
          if ( PartW < 0 || !v13 )
            goto LABEL_25;
        }
        else
        {
          for ( i = 0; i < 7; ++i )
          {
            v12 = v34[i];
            if ( v12 && (unsigned int)PathComparePaths(v12, v26) != 1 )
              goto LABEL_25;
          }
        }
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 24LL))(v30, v22);
LABEL_25:
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v26);
        goto LABEL_26;
      }
LABEL_28:
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v28);
      v7 = 0;
LABEL_29:
      `eh vector destructor iterator'(
        v34,
        8u,
        7u,
        (void (*)(void *))CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>);
    }
    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v29);
    if ( PartW >= 0 )
    {
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v33);
      v14 = (void **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v33);
      PartW = SHGetKnownFolderItem(
                &FOLDERID_UsersLibraries,
                KF_FLAG_DEFAULT,
                0,
                &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                v14);
      if ( PartW >= 0 )
      {
        ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&pszIn);
        v15 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v33);
        PartW = (*(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *, PCWSTR *))(*(_QWORD *)v15 + 24LL))(
                  v15,
                  0,
                  &BHID_SFObject,
                  &GUID_000214e6_0000_0000_c000_000000000046,
                  &pszIn);
        if ( PartW >= 0 )
        {
          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v32);
          v16 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&pszIn);
          PartW = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, struct IEnumIDList **))(*(_QWORD *)v16 + 32LL))(
                    v16,
                    0,
                    32,
                    &v32);
          while ( !PartW )
          {
            ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v31);
            v17 = (void **)ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v31);
            PartW = NextItem(v32, (struct IShellFolder *)pszIn, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v17);
            if ( !PartW )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v26);
              if ( (*(int (__fastcall **)(__int64, _QWORD, const GUID *, GUID *, void **))(*(_QWORD *)v31 + 24LL))(
                     v31,
                     0,
                     &BHID_SFObject,
                     &GUID_86187c37_e662_4d1e_a122_7478676d7e6e,
                     &v26) >= 0 )
              {
                pcchOut = PartW;
                v18 = 0;
                for ( PartW = (*(__int64 (__fastcall **)(void *, DWORD *))(*(_QWORD *)v26 + 104LL))(v26, &pcchOut);
                      PartW >= 0;
                      ++v18 )
                {
                  if ( v18 >= pcchOut )
                    break;
                  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v28);
                  v19 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v26);
                  PartW = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 112LL))(
                            v19,
                            v18,
                            &v28);
                  if ( PartW >= 0 )
                  {
                    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v22);
                    v20 = ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->((__int64)&v28);
                    PartW = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v20 + 112LL))(
                              v20,
                              &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                              &v22);
                    if ( PartW >= 0 )
                    {
                      pszPath = 0;
                      if ( (*(int (__fastcall **)(__int64, __int64, LPCWSTR *))(*(_QWORD *)v22 + 40LL))(
                             v22,
                             2147844096LL,
                             &pszPath) >= 0 )
                      {
                        if ( !PathIsUNCW(pszPath)
                          || (v24 = 0, (int)SEARCH_RemoteLocationsCscStateCache_IsRemoteLocationInCsc(pszPath, &v24) >= 0)
                          && !v24 )
                        {
                          ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v29);
                          ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v29);
                          PartW = SHCreateScopeItemFromShellItem(v22, 1, 2);
                          if ( PartW >= 0 )
                          {
                            PartW = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 24LL))(v30, v29);
                            if ( PartW >= 0 )
                              PartW = 0;
                          }
                          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v29);
                        }
                      }
                      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pszPath);
                    }
                    ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v22);
                  }
                  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v28);
                }
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v26);
            }
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v31);
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v32);
        }
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&pszIn);
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v33);
      if ( PartW >= 0 )
      {
        *a1 = ATL::CComPtrBase<IScope>::Detach(&v30);
        PartW = v7;
      }
    }
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v30);
  return (unsigned int)PartW;
}

```

## disassembly

```asm
0x18003b52c  mov     [rsp-8+arg_8], rbx
0x18003b531  mov     [rsp-8+arg_10], rsi
0x18003b536  push    rbp
0x18003b537  push    rdi
0x18003b538  push    r13
0x18003b53a  push    r14
0x18003b53c  push    r15
0x18003b53e  lea     rbp, [rsp-250h]
0x18003b546  sub     rsp, 350h
0x18003b54d  mov     rax, cs:__security_cookie
0x18003b554  xor     rax, rsp
0x18003b557  mov     [rbp+270h+var_30], rax
0x18003b55e  mov     r15, rcx
0x18003b561  mov     qword ptr [rcx], 0
0x18003b568  lea     rcx, [rsp+370h+var_308]; void *
0x18003b56d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b572  lea     rcx, [rsp+370h+var_308]
0x18003b577  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003b57c  mov     r8, rax
0x18003b57f  lea     rdx, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x18003b586  xor     ecx, ecx
0x18003b588  call    cs:__imp_SHCreateScope
0x18003b58e  mov     ebx, eax
0x18003b590  test    eax, eax
0x18003b592  js      loc_18003BBD4
0x18003b598  lea     rcx, [rsp+370h+var_310]; void *
0x18003b59d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b5a2  lea     rcx, [rsp+370h+var_310]
0x18003b5a7  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003b5ac  mov     rcx, rax; struct IScope **
0x18003b5af  call    ?s_GetAllIndexFilesScope@CStartMenuFilesResultSetManager@@SAJPEAPEAUIScope@@@Z; CStartMenuFilesResultSetManager::s_GetAllIndexFilesScope(IScope * *)
0x18003b5b4  test    eax, eax
0x18003b5b6  js      loc_18003B8A7
0x18003b5bc  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x18003b5c3  mov     r13d, 7
0x18003b5c9  lea     rax, ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003b5d0  movups  xmm1, xmmword ptr cs:FOLDERID_LocalAppData.Data1
0x18003b5d7  lea     r9, ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; void (*)(void *)
0x18003b5de  mov     r8d, r13d; unsigned __int64
0x18003b5e1  movdqu  [rbp+270h+var_2B0], xmm0
0x18003b5e6  lea     edx, [r13+1]; unsigned __int64
0x18003b5ea  mov     qword ptr [rsp+370h+dwFlags], rax; void (*)(void *)
0x18003b5ef  movups  xmm0, xmmword ptr cs:FOLDERID_LocalAppDataLow.Data1
0x18003b5f6  lea     rcx, [rbp+270h+var_2E8]; void *
0x18003b5fa  movdqu  [rbp+270h+var_2A0], xmm1
0x18003b5ff  movups  xmm1, xmmword ptr cs:FOLDERID_RoamingAppData.Data1
0x18003b606  movdqu  [rbp+270h+var_290], xmm0
0x18003b60b  movups  xmm0, xmmword ptr cs:FOLDERID_CommonStartMenu.Data1
0x18003b612  movdqu  [rbp+270h+var_280], xmm1
0x18003b617  movups  xmm1, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x18003b61e  movdqu  [rbp+270h+var_270], xmm0
0x18003b623  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x18003b62a  movdqu  [rbp+270h+var_260], xmm1
0x18003b62f  movdqu  [rbp+270h+var_250], xmm0
0x18003b634  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003b639  xor     edi, edi
0x18003b63b  lea     esi, [rdi+1]
0x18003b63e  movsxd  rax, edi
0x18003b641  cmp     rax, r13
0x18003b644  jnb     short loc_18003B67F
0x18003b646  lea     r9, [rbp+270h+var_2E8]
0x18003b64a  xor     r8d, r8d; hToken
0x18003b64d  lea     r9, [r9+rax*8]; ppszPath
0x18003b651  mov     edx, 5000h; dwFlags
0x18003b656  shl     rax, 4
0x18003b65a  lea     rcx, [rbp+270h+var_2B0]
0x18003b65e  add     rcx, rax; rfid
0x18003b661  call    cs:__imp_SHGetKnownFolderPath
0x18003b667  xor     ebx, ebx
0x18003b669  cmp     eax, 80070002h
0x18003b66e  cmovnz  ebx, eax
0x18003b671  add     edi, esi
0x18003b673  test    ebx, ebx
0x18003b675  jns     short loc_18003B63E
0x18003b677  mov     r14d, esi
0x18003b67a  jmp     loc_18003B88D
0x18003b67f  lea     rcx, [rsp+370h+var_318]; void *
0x18003b684  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b689  lea     rcx, [rsp+370h+var_310]
0x18003b68e  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18003b693  mov     r10, rax
0x18003b696  lea     r9, [rsp+370h+var_318]
0x18003b69b  lea     r8, _GUID_2c1c7e2e_2d0e_4059_831e_1e6f82335c2e
0x18003b6a2  xor     edx, edx
0x18003b6a4  mov     rcx, [rax]
0x18003b6a7  mov     rax, [rcx+40h]
0x18003b6ab  mov     rcx, r10
0x18003b6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6b3  mov     ebx, eax
0x18003b6b5  test    eax, eax
0x18003b6b7  jnz     loc_18003B880
0x18003b6bd  lea     rcx, [rsp+370h+var_340]; void *
0x18003b6c2  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b6c7  lea     rcx, [rsp+370h+var_318]
0x18003b6cc  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18003b6d1  mov     r10, rax
0x18003b6d4  mov     qword ptr [rsp+370h+dwFlags], 0
0x18003b6dd  lea     r9, [rsp+370h+var_340]
0x18003b6e2  mov     edx, esi
0x18003b6e4  lea     r8, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18003b6eb  mov     rcx, [rax]
0x18003b6ee  mov     rax, [rcx+18h]
0x18003b6f2  mov     rcx, r10
0x18003b6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6fa  mov     ebx, eax
0x18003b6fc  test    eax, eax
0x18003b6fe  jnz     loc_18003B86E
0x18003b704  mov     rcx, [rsp+370h+var_340]
0x18003b709  lea     rdx, [rsp+370h+var_334]
0x18003b70e  mov     [rsp+370h+var_334], eax
0x18003b712  mov     rax, [rcx]
0x18003b715  mov     rax, [rax+20h]
0x18003b719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b71e  mov     ebx, eax
0x18003b720  test    eax, eax
0x18003b722  js      loc_18003B86E
0x18003b728  lea     rcx, [rsp+370h+pszPath]; void *
0x18003b72d  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b732  lea     rcx, [rsp+370h+var_340]
0x18003b737  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18003b73c  mov     r9, rax
0x18003b73f  lea     r8, [rsp+370h+pszPath]
0x18003b744  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18003b74b  mov     rcx, [rax]
0x18003b74e  mov     rax, [rcx+78h]
0x18003b752  mov     rcx, r9
0x18003b755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b75a  mov     ebx, eax
0x18003b75c  test    eax, eax
0x18003b75e  js      loc_18003B864
0x18003b764  mov     rcx, [rsp+370h+pszPath]
0x18003b769  lea     r8, [rsp+370h+var_328]
0x18003b76e  mov     [rsp+370h+var_328], 0
0x18003b777  mov     edx, 80058000h
0x18003b77c  mov     rax, [rcx]
0x18003b77f  mov     rax, [rax+28h]
0x18003b783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b788  mov     ebx, eax
0x18003b78a  test    eax, eax
0x18003b78c  js      short loc_18003B7BD
0x18003b78e  xor     edi, edi
0x18003b790  cmp     edi, r13d
0x18003b793  jnb     loc_18003B844
0x18003b799  movsxd  rax, edi
0x18003b79c  mov     rcx, [rbp+rax*8+270h+var_2E8]
0x18003b7a1  test    rcx, rcx
0x18003b7a4  jz      short loc_18003B7B9
0x18003b7a6  mov     rdx, [rsp+370h+var_328]
0x18003b7ab  call    cs:__imp_PathComparePaths
0x18003b7b1  cmp     eax, esi
0x18003b7b3  jnz     loc_18003B85A
0x18003b7b9  add     edi, esi
0x18003b7bb  jmp     short loc_18003B790
0x18003b7bd  mov     rcx, [rsp+370h+pszPath]
0x18003b7c2  lea     r8, [rsp+370h+pszIn]
0x18003b7c7  mov     [rsp+370h+pszIn], 0
0x18003b7d0  mov     edx, 80068000h
0x18003b7d5  xor     dil, dil
0x18003b7d8  mov     rax, [rcx]
0x18003b7db  mov     rax, [rax+28h]
0x18003b7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7e4  mov     ebx, eax
0x18003b7e6  test    eax, eax
0x18003b7e8  js      short loc_18003B831
0x18003b7ea  mov     rcx, [rsp+370h+pszIn]; pszIn
0x18003b7ef  lea     r8, [rsp+370h+pcchOut]; pcchOut
0x18003b7f4  mov     r9d, esi; dwPart
0x18003b7f7  mov     [rsp+370h+pcchOut], 104h
0x18003b7ff  lea     rdx, [rbp+270h+pszOut]; pszOut
0x18003b803  mov     [rsp+370h+dwFlags], 0; dwFlags
0x18003b80b  call    cs:__imp_UrlGetPartW
0x18003b811  mov     ebx, eax
0x18003b813  test    eax, eax
0x18003b815  js      short loc_18003B831
0x18003b817  lea     rdx, [rbp+270h+pszOut]; pszStr2
0x18003b81b  lea     rcx, aCsc; "csc"
0x18003b822  call    cs:__imp_StrCmpICW
0x18003b828  test    eax, eax
0x18003b82a  movzx   edi, dil
0x18003b82e  cmovz   edi, esi
0x18003b831  lea     rcx, [rsp+370h+pszIn]; void *
0x18003b836  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003b83b  test    ebx, ebx
0x18003b83d  js      short loc_18003B85A
0x18003b83f  test    dil, dil
0x18003b842  jz      short loc_18003B85A
0x18003b844  mov     rcx, [rsp+370h+var_308]
0x18003b849  mov     rdx, [rsp+370h+var_340]
0x18003b84e  mov     rax, [rcx]
0x18003b851  mov     rax, [rax+18h]
0x18003b855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b85a  lea     rcx, [rsp+370h+var_328]; void *
0x18003b85f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18003b864  lea     rcx, [rsp+370h+pszPath]
0x18003b869  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003b86e  lea     rcx, [rsp+370h+var_340]
0x18003b873  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003b878  test    ebx, ebx
0x18003b87a  jz      loc_18003B6BD
0x18003b880  lea     rcx, [rsp+370h+var_318]
0x18003b885  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003b88a  xor     r14d, r14d
0x18003b88d  lea     r9, ??1?$CCoTaskMemPtr@G@@QEAA@XZ; void (*)(void *)
0x18003b894  mov     r8, r13; unsigned __int64
0x18003b897  mov     edx, 8; unsigned __int64
0x18003b89c  lea     rcx, [rbp+270h+var_2E8]; void *
0x18003b8a0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003b8a5  jmp     short loc_18003B8AF
0x18003b8a7  xor     ebx, ebx
0x18003b8a9  lea     esi, [rbx+1]
0x18003b8ac  mov     r14d, esi
0x18003b8af  lea     rcx, [rsp+370h+var_310]
0x18003b8b4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003b8b9  test    ebx, ebx
0x18003b8bb  js      loc_18003BBD4
0x18003b8c1  lea     rcx, [rbp+270h+var_2F0]; void *
0x18003b8c5  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b8ca  lea     rcx, [rbp+270h+var_2F0]
0x18003b8ce  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003b8d3  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003b8da  mov     qword ptr [rsp+370h+dwFlags], rax; ppv
0x18003b8df  xor     r8d, r8d; hToken
0x18003b8e2  lea     rcx, FOLDERID_UsersLibraries; rfid
0x18003b8e9  xor     edx, edx; flags
0x18003b8eb  call    cs:__imp_SHGetKnownFolderItem
0x18003b8f1  mov     ebx, eax
0x18003b8f3  test    eax, eax
0x18003b8f5  js      loc_18003BBB7
0x18003b8fb  lea     rcx, [rsp+370h+pszIn]; void *
0x18003b900  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b905  lea     rcx, [rbp+270h+var_2F0]
0x18003b909  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18003b90e  mov     r10, rax
0x18003b911  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x18003b918  lea     r8, BHID_SFObject
0x18003b91f  xor     edx, edx
0x18003b921  mov     rcx, [rax]
0x18003b924  mov     rax, [rcx+18h]
0x18003b928  lea     rcx, [rsp+370h+pszIn]
0x18003b92d  mov     qword ptr [rsp+370h+dwFlags], rcx
0x18003b932  mov     rcx, r10
0x18003b935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b93a  mov     ebx, eax
0x18003b93c  test    eax, eax
0x18003b93e  js      loc_18003BBAD
0x18003b944  lea     rcx, [rsp+370h+var_2F8]; void *
0x18003b949  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b94e  lea     rcx, [rsp+370h+pszIn]
0x18003b953  call    ??C?$CComPtrBase@UIStartMenuResultSetInternal@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIStartMenuResultSetInternal@@@1@XZ; ATL::CComPtrBase<IStartMenuResultSetInternal>::operator->(void)
0x18003b958  mov     r10, rax
0x18003b95b  lea     r9, [rsp+370h+var_2F8]
0x18003b960  xor     edx, edx
0x18003b962  mov     rcx, [rax]
0x18003b965  lea     r8d, [rdx+20h]
0x18003b969  mov     rax, [rcx+20h]
0x18003b96d  mov     rcx, r10
0x18003b970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b975  mov     ebx, eax
0x18003b977  test    eax, eax
0x18003b979  jnz     loc_18003BBA3
0x18003b97f  lea     r13, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x18003b986  lea     rcx, [rsp+370h+var_300]; void *
0x18003b98b  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b990  lea     rcx, [rsp+370h+var_300]
0x18003b995  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x18003b99a  mov     rdx, [rsp+370h+pszIn]; struct IShellFolder *
0x18003b99f  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x18003b9a6  mov     rcx, [rsp+370h+var_2F8]; struct IEnumIDList *
0x18003b9ab  mov     r9, rax; void **
0x18003b9ae  call    ?NextItem@@YAJPEAUIEnumIDList@@PEAUIShellFolder@@AEBU_GUID@@PEAPEAX@Z; NextItem(IEnumIDList *,IShellFolder *,_GUID const &,void * *)
0x18003b9b3  mov     ebx, eax
0x18003b9b5  test    eax, eax
0x18003b9b7  jnz     loc_18003BB91
0x18003b9bd  lea     rcx, [rsp+370h+var_328]; void *
0x18003b9c2  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003b9c7  mov     rcx, [rsp+370h+var_300]
0x18003b9cc  lea     rdx, [rsp+370h+var_328]
0x18003b9d1  mov     qword ptr [rsp+370h+dwFlags], rdx
0x18003b9d6  lea     r9, _GUID_86187c37_e662_4d1e_a122_7478676d7e6e
0x18003b9dd  lea     r8, BHID_SFObject
0x18003b9e4  xor     edx, edx
0x18003b9e6  mov     rax, [rcx]
0x18003b9e9  mov     rax, [rax+18h]
0x18003b9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9f2  test    eax, eax
0x18003b9f4  js      loc_18003BB87
0x18003b9fa  mov     rcx, [rsp+370h+var_328]
0x18003b9ff  lea     rdx, [rsp+370h+pcchOut]
0x18003ba04  mov     [rsp+370h+pcchOut], ebx
0x18003ba08  mov     rax, [rcx]
0x18003ba0b  mov     rax, [rax+68h]
0x18003ba0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba14  xor     edi, edi
0x18003ba16  mov     ebx, eax
0x18003ba18  test    eax, eax
0x18003ba1a  js      loc_18003BB87
0x18003ba20  cmp     edi, [rsp+370h+pcchOut]
0x18003ba24  jnb     loc_18003BB87
0x18003ba2a  lea     rcx, [rsp+370h+var_318]; void *
0x18003ba2f  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
  ... truncated ...
```
