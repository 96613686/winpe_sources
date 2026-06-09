# CMigrationPlugin::raw_Discover(IMigrationContext *,wchar_t * *)

- ea: `0x1800144e0`
- end: `0x18001498e`
- name: `?raw_Discover@CMigrationPlugin@@UEAAJPEAUIMigrationContext@@PEAPEA_W@Z`
- size: `1198`
- prototype: `__int64 __fastcall(CMigrationPlugin *this, struct IUnknown *, wchar_t **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800026f0`
- `0x180002c0c`
- `0x18000cb14`
- `0x18000cba4`
- `0x18000cc90`
- `0x1800105b4`
- `0x180010f84`
- `0x180011a18`
- `0x180012390`
- `0x1800144e0`
- `0x180015340`
- `0x180015358`
- `0x180018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001490d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001490d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800145e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800145e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014943`

## string_xrefs

- `0x180014603`: `DataDirectory`
- `0x18001464c`: `<migXml>\n  <rules context="System">\n    <detects>\n      <detect>\n        <condition negation="Yes">MigXmlHelper.IsUpgrade()</condition>\n      </detect>\n    </detects>\n    <include>\n      <objectSet>\n        <pattern type="File">`
- `0x180014705`: `  <rules context="System">\n    <detects>\n      <detect>\n        <condition>MigXmlHelper.IsUpgrade()</condition>\n      </detect>\n    </detects>\n    <include>\n      <objectSet>\n        <pattern type="File">`
- `0x180014778`: `</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search [IndexerCatalogVersion]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search\Applications\* [*]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search\CatalogList\* [*]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search\CatalogNames\* [*]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search`
- `0x180014830`: `</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search [IndexerCatalogVersion]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search\Applications\* [*]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search\CatalogList\* [*]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search\CatalogNames\* [*]</pattern>\n        <pattern type="Registry">HKLM\Software\Microsoft\Windows Search`
- `0x1800148bd`: `</migXml>\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMigrationPlugin::raw_Discover(CMigrationPlugin *this, struct IUnknown *a2, wchar_t **a3)
{
  struct IUnknown v4; // rax
  int v6; // eax
  const struct _GUID *v7; // r8
  HKEY v8; // rbx
  HKEY v9; // rax
  int v10; // ecx
  struct IUnknown v11; // rax
  int v12; // eax
  const struct _GUID *v13; // r8
  HKEY v14; // rbx
  char v15; // bl
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  __int64 v20; // rax
  _QWORD *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rdx
  _QWORD *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  _QWORD *v31; // rdx
  _QWORD *v32; // rdx
  _QWORD *v33; // rdx
  __int64 v34; // rax
  _QWORD *v35; // rdx
  OLECHAR *v36; // rbx
  OLECHAR *psz; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v43[3]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v44[264]; // [rsp+70h] [rbp-90h] BYREF

  *a3 = 0;
  v4.lpVtbl = a2->lpVtbl;
  hKey = 0;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, HKEY *))v4.lpVtbl[2].Release)(a2, &hKey);
  if ( v6 < 0 )
    _com_issue_errorex(v6, a2, v7);
  v8 = hKey;
  v9 = (HKEY)operator new(0x18u);
  if ( !v9 )
    _com_issue_error(v10);
  *((_QWORD *)v9 + 1) = 0;
  *((_DWORD *)v9 + 4) = 1;
  *(_QWORD *)v9 = v8;
  hKey = v9;
  _bstr_t::~_bstr_t((_bstr_t *)&hKey);
  if ( !v8 )
  {
    v11.lpVtbl = a2->lpVtbl;
    LOWORD(psz) = 0;
    v12 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR **))v11.lpVtbl[6].AddRef)(a2, &psz);
    if ( v12 < 0 )
      _com_issue_errorex(v12, a2, v13);
    if ( !(_WORD)psz )
    {
      v43[1] = 0;
      v43[2] = 0;
      LODWORD(psz) = 260;
      hKey = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", 0, 0x20019u, &hKey) )
      {
        v14 = hKey;
        v43[0] = hKey;
        if ( !(unsigned int)ATL::CRegKey::QueryStringValue(
                              (ATL::CRegKey *)v43,
                              L"DataDirectory",
                              v44,
                              (unsigned int *)&psz)
          && (_DWORD)psz )
        {
          v15 = IsDataMigrationEligible(a2);
          psz = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
          if ( (unsigned __int64)L"<migXml>\r\n"
                                  "  <rules context=\"System\">\r\n"
                                  "    <detects>\r\n"
                                  "      <detect>\r\n"
                                  "        <condition negation=\"Yes\">MigXmlHelper.IsUpgrade()</condition>\r\n"
                                  "      </detect>\r\n"
                                  "    </detects>\r\n"
                                  "    <include>\r\n"
                                  "      <objectSet>\r\n"
                                  "        <pattern type=\"File\">" >= 0x10000 )
            ATL::CSimpleStringT<wchar_t,0>::SetString(
              &psz,
              L"<migXml>\r\n"
               "  <rules context=\"System\">\r\n"
               "    <detects>\r\n"
               "      <detect>\r\n"
               "        <condition negation=\"Yes\">MigXmlHelper.IsUpgrade()</condition>\r\n"
               "      </detect>\r\n"
               "    </detects>\r\n"
               "    <include>\r\n"
               "      <objectSet>\r\n"
               "        <pattern type=\"File\">",
              237);
          else
            ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
              &psz,
              (unsigned __int16)L"<migXml>\r\n"
                                 "  <rules context=\"System\">\r\n"
                                 "    <detects>\r\n"
                                 "      <detect>\r\n"
                                 "        <condition negation=\"Yes\">MigXmlHelper.IsUpgrade()</condition>\r\n"
                                 "      </detect>\r\n"
                                 "    </detects>\r\n"
                                 "    <include>\r\n"
                                 "      <objectSet>\r\n"
                                 "        <pattern type=\"File\">");
          v16 = ATL::operator+(&v40, &psz, v44);
          v17 = ATL::operator+(&v41, v16, L"</pattern>\r\n      </objectSet>\r\n    </include>\r\n  </rules>\r\n");
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(&psz, v17);
          v18 = (_QWORD *)(v41 - 24);
          if ( _InterlockedDecrement((volatile signed __int32 *)(v41 - 24 + 16)) <= 0 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
          v19 = (_QWORD *)(v40 - 24);
          if ( _InterlockedDecrement((volatile signed __int32 *)(v40 - 24 + 16)) <= 0 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
          if ( v15 )
          {
            v20 = ATL::operator+(
                    &v40,
                    &psz,
                    L"  <rules context=\"System\">\r\n"
                     "    <detects>\r\n"
                     "      <detect>\r\n"
                     "        <condition>MigXmlHelper.IsUpgrade()</condition>\r\n"
                     "      </detect>\r\n"
                     "    </detects>\r\n"
                     "    <include>\r\n"
                     "      <objectSet>\r\n"
                     "        <pattern type=\"File\">");
            ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(&psz, v20);
            v21 = (_QWORD *)(v40 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v40 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
            v22 = ATL::operator+(&v42, &psz, v44);
            v23 = ATL::operator+(&v41, v22, L"* [*]");
            v24 = ATL::operator+(
                    &v40,
                    v23,
                    L"</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search [IndexerCatalogVersion"
                     "]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Applications\\* [*]</"
                     "pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\CatalogList\\* [*]</p"
                     "attern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\CatalogNames\\* [*]</"
                     "pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Databases\\* [*]</pat"
                     "tern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gather\\Windows\\* [*"
                     "]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gathering Manager [Te"
                     "mpPath]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gathering Manager [De"
                     "faultApplicationsPath]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gathering Manager\\Ap"
                     "plications\\* [*]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\ProtocolHandlers\\* ["
                     "*]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\ScopeChangeNotificati"
                     "on\\* [*]</pattern>\r\n"
                     "      </objectSet>\r\n"
                     "    </include>\r\n"
                     "    <merge script = \"MigXmlHelper.SourcePriority()\">\r\n"
                     "      <objectSet>\r\n"
                     "        <pattern type=\"File\">");
            ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(&psz, v24);
            v25 = (_QWORD *)(v40 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v40 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
            v26 = (_QWORD *)(v41 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v41 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 8LL))(*v26);
            v27 = (_QWORD *)(v42 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v42 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 8LL))(*v27);
            v28 = ATL::operator+(&v41, &psz, v44);
            v29 = ATL::operator+(&v40, v28, L"* [*]");
            v30 = ATL::operator+(
                    &v42,
                    v29,
                    L"</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search [IndexerCatalogVersion"
                     "]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Applications\\* [*]</"
                     "pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\CatalogList\\* [*]</p"
                     "attern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\CatalogNames\\* [*]</"
                     "pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Databases\\* [*]</pat"
                     "tern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gather\\Windows\\* [*"
                     "]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gathering Manager [Te"
                     "mpPath]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gathering Manager [De"
                     "faultApplicationsPath]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\Gathering Manager\\Ap"
                     "plications\\* [*]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\ProtocolHandlers\\* ["
                     "*]</pattern>\r\n"
                     "        <pattern type=\"Registry\">HKLM\\Software\\Microsoft\\Windows Search\\ScopeChangeNotificati"
                     "on\\* [*]</pattern>\r\n"
                     "      </objectSet>\r\n"
                     "    </merge>\r\n"
                     "  </rules>\r\n");
            ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(&psz, v30);
            v31 = (_QWORD *)(v42 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v42 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 8LL))(*v31);
            v32 = (_QWORD *)(v40 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v40 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 8LL))(*v32);
            v33 = (_QWORD *)(v41 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v41 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v33 + 8LL))(*v33);
          }
          v34 = ATL::operator+(&v42, &psz, L"</migXml>\r\n");
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(&psz, v34);
          v35 = (_QWORD *)(v42 - 24);
          if ( _InterlockedDecrement((volatile signed __int32 *)(v42 - 24 + 16)) <= 0 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v35 + 8LL))(*v35);
          v36 = psz;
          *a3 = SysAllocString(psz);
          if ( _InterlockedDecrement((volatile signed __int32 *)v36 - 2) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v36 - 3) + 8LL))(*((_QWORD *)v36 - 3));
          v14 = hKey;
        }
        if ( v14 )
          RegCloseKey(v14);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800144e0  mov     [rsp-8+arg_0], rbx
0x1800144e5  mov     [rsp-8+arg_18], rsi
0x1800144ea  push    rbp
0x1800144eb  push    rdi
0x1800144ec  push    r14
0x1800144ee  lea     rbp, [rsp-190h]
0x1800144f6  sub     rsp, 290h
0x1800144fd  mov     rax, cs:__security_cookie
0x180014504  xor     rax, rsp
0x180014507  mov     [rbp+1A0h+var_20], rax
0x18001450e  mov     rdi, rdx
0x180014511  xor     r14d, r14d
0x180014514  mov     [r8], r14
0x180014517  mov     rcx, rdi
0x18001451a  mov     rax, [rdx]
0x18001451d  mov     rsi, r8
0x180014520  lea     rdx, [rsp+2A0h+hKey]
0x180014525  mov     [rsp+2A0h+hKey], r14
0x18001452a  mov     rax, [rax+40h]
0x18001452e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014533  test    eax, eax
0x180014535  js      loc_180014983
0x18001453b  mov     rbx, [rsp+2A0h+hKey]
0x180014540  lea     ecx, [r14+18h]; Size
0x180014544  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014549  test    rax, rax
0x18001454c  jz      loc_18001497D
0x180014552  mov     [rax+8], r14
0x180014556  lea     rcx, [rsp+2A0h+hKey]; this
0x18001455b  mov     dword ptr [rax+10h], 1
0x180014562  mov     [rax], rbx
0x180014565  mov     [rsp+2A0h+hKey], rax
0x18001456a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001456f  test    rbx, rbx
0x180014572  jnz     loc_180014949
0x180014578  mov     rax, [rdi]
0x18001457b  lea     rdx, [rsp+2A0h+psz]
0x180014580  mov     rcx, rdi
0x180014583  mov     word ptr [rsp+2A0h+psz], r14w
0x180014589  mov     rax, [rax+98h]
0x180014590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014595  test    eax, eax
0x180014597  js      loc_180014972
0x18001459d  cmp     word ptr [rsp+2A0h+psz], r14w
0x1800145a3  jnz     loc_180014949
0x1800145a9  lea     rax, [rsp+2A0h+hKey]
0x1800145ae  mov     [rsp+2A0h+var_240], r14
0x1800145b3  mov     r9d, 20019h; samDesired
0x1800145b9  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800145be  xor     r8d, r8d; ulOptions
0x1800145c1  mov     [rsp+2A0h+var_238], r14
0x1800145c6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Search"
0x1800145cd  mov     dword ptr [rsp+2A0h+psz], 104h
0x1800145d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800145dc  mov     [rsp+2A0h+hKey], r14
0x1800145e1  call    cs:__imp_RegOpenKeyExW
0x1800145e7  test    eax, eax
0x1800145e9  jnz     loc_180014949
0x1800145ef  mov     rbx, [rsp+2A0h+hKey]
0x1800145f4  lea     r9, [rsp+2A0h+psz]; unsigned int *
0x1800145f9  lea     r8, [rsp+2A0h+var_230]; wchar_t *
0x1800145fe  mov     [rsp+2A0h+var_248], rbx
0x180014603  lea     rdx, aDatadirectory; "DataDirectory"
0x18001460a  lea     rcx, [rsp+2A0h+var_248]; this
0x18001460f  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEB_WPEA_WPEAK@Z; ATL::CRegKey::QueryStringValue(wchar_t const *,wchar_t *,ulong *)
0x180014614  test    eax, eax
0x180014616  jnz     loc_18001493B
0x18001461c  cmp     dword ptr [rsp+2A0h+psz], r14d
0x180014621  jbe     loc_18001493B
0x180014627  mov     rcx, rdi
0x18001462a  call    IsDataMigrationEligible
0x18001462f  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014636  mov     bl, al
0x180014638  mov     rax, [rcx+18h]
0x18001463c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014648  add     rax, 18h
0x18001464c  lea     rdx, aMigxmlRulesCon; "<migXml>\r\n  <rules context=\"System\""...
0x180014653  mov     [rsp+2A0h+psz], rax
0x180014658  lea     rcx, [rsp+2A0h+psz]
0x18001465d  cmp     rdx, 10000h
0x180014664  jnb     short loc_180014670
0x180014666  movzx   edx, dx
0x180014669  call    ?LoadStringW@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(uint)
0x18001466e  jmp     short loc_18001467B
0x180014670  mov     r8d, 0EDh
0x180014676  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18001467b  lea     r8, [rsp+2A0h+var_230]
0x180014680  lea     rdx, [rsp+2A0h+psz]
0x180014685  lea     rcx, [rsp+2A0h+var_260]
0x18001468a  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18001468f  mov     rdx, rax
0x180014692  lea     r8, aPatternObjects; "</pattern>\r\n      </objectSet>\r\n   "...
0x180014699  lea     rcx, [rsp+2A0h+var_258]
0x18001469e  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x1800146a3  mov     rdx, rax
0x1800146a6  lea     rcx, [rsp+2A0h+psz]
0x1800146ab  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800146b0  mov     rdx, [rsp+2A0h+var_258]
0x1800146b5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800146b9  or      edi, 0FFFFFFFFh
0x1800146bc  mov     eax, edi
0x1800146be  lock xadd [rdx+10h], eax
0x1800146c3  add     eax, edi
0x1800146c5  test    eax, eax
0x1800146c7  jg      short loc_1800146D8
0x1800146c9  mov     rcx, [rdx]
0x1800146cc  mov     rax, [rcx]
0x1800146cf  mov     rax, [rax+8]
0x1800146d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146d8  mov     rdx, [rsp+2A0h+var_260]
0x1800146dd  mov     eax, edi
0x1800146df  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800146e3  lock xadd [rdx+10h], eax
0x1800146e8  add     eax, edi
0x1800146ea  test    eax, eax
0x1800146ec  jg      short loc_1800146FD
0x1800146ee  mov     rcx, [rdx]
0x1800146f1  mov     rax, [rcx]
0x1800146f4  mov     rax, [rax+8]
0x1800146f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146fd  test    bl, bl
0x1800146ff  jz      loc_1800148BD
0x180014705  lea     r8, aRulesContextSy; "  <rules context=\"System\">\r\n    <de"...
0x18001470c  lea     rdx, [rsp+2A0h+psz]
0x180014711  lea     rcx, [rsp+2A0h+var_260]
0x180014716  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18001471b  mov     rdx, rax
0x18001471e  lea     rcx, [rsp+2A0h+psz]
0x180014723  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180014728  mov     rdx, [rsp+2A0h+var_260]
0x18001472d  mov     eax, edi
0x18001472f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014733  lock xadd [rdx+10h], eax
0x180014738  add     eax, edi
0x18001473a  test    eax, eax
0x18001473c  jg      short loc_18001474D
0x18001473e  mov     rcx, [rdx]
0x180014741  mov     rax, [rcx]
0x180014744  mov     rax, [rax+8]
0x180014748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001474d  lea     r8, [rsp+2A0h+var_230]
0x180014752  lea     rdx, [rsp+2A0h+psz]
0x180014757  lea     rcx, [rsp+2A0h+var_250]
0x18001475c  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x180014761  mov     rdx, rax
0x180014764  lea     r8, asc_18001C680; "* [*]"
0x18001476b  lea     rcx, [rsp+2A0h+var_258]
0x180014770  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x180014775  mov     rdx, rax
0x180014778  lea     r8, aPatternPattern_0; "</pattern>\r\n        <pattern type=\"R"...
0x18001477f  lea     rcx, [rsp+2A0h+var_260]
0x180014784  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x180014789  mov     rdx, rax
0x18001478c  lea     rcx, [rsp+2A0h+psz]
0x180014791  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180014796  mov     rdx, [rsp+2A0h+var_260]
0x18001479b  mov     eax, edi
0x18001479d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800147a1  lock xadd [rdx+10h], eax
0x1800147a6  add     eax, edi
0x1800147a8  test    eax, eax
0x1800147aa  jg      short loc_1800147BB
0x1800147ac  mov     rcx, [rdx]
0x1800147af  mov     rax, [rcx]
0x1800147b2  mov     rax, [rax+8]
0x1800147b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147bb  mov     rdx, [rsp+2A0h+var_258]
0x1800147c0  mov     eax, edi
0x1800147c2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800147c6  lock xadd [rdx+10h], eax
0x1800147cb  add     eax, edi
0x1800147cd  test    eax, eax
0x1800147cf  jg      short loc_1800147E0
0x1800147d1  mov     rcx, [rdx]
0x1800147d4  mov     rax, [rcx]
0x1800147d7  mov     rax, [rax+8]
0x1800147db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147e0  mov     rdx, [rsp+2A0h+var_250]
0x1800147e5  mov     eax, edi
0x1800147e7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800147eb  lock xadd [rdx+10h], eax
0x1800147f0  add     eax, edi
0x1800147f2  test    eax, eax
0x1800147f4  jg      short loc_180014805
0x1800147f6  mov     rcx, [rdx]
0x1800147f9  mov     rax, [rcx]
0x1800147fc  mov     rax, [rax+8]
0x180014800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014805  lea     r8, [rsp+2A0h+var_230]
0x18001480a  lea     rdx, [rsp+2A0h+psz]
0x18001480f  lea     rcx, [rsp+2A0h+var_258]
0x180014814  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x180014819  mov     rdx, rax
0x18001481c  lea     r8, asc_18001C680; "* [*]"
0x180014823  lea     rcx, [rsp+2A0h+var_260]
0x180014828  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x18001482d  mov     rdx, rax
0x180014830  lea     r8, aPatternPattern; "</pattern>\r\n        <pattern type=\"R"...
0x180014837  lea     rcx, [rsp+2A0h+var_250]
0x18001483c  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x180014841  mov     rdx, rax
0x180014844  lea     rcx, [rsp+2A0h+psz]
0x180014849  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18001484e  mov     rdx, [rsp+2A0h+var_250]
0x180014853  mov     eax, edi
0x180014855  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014859  lock xadd [rdx+10h], eax
0x18001485e  add     eax, edi
0x180014860  test    eax, eax
0x180014862  jg      short loc_180014873
0x180014864  mov     rcx, [rdx]
0x180014867  mov     rax, [rcx]
0x18001486a  mov     rax, [rax+8]
0x18001486e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014873  mov     rdx, [rsp+2A0h+var_260]
0x180014878  mov     eax, edi
0x18001487a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001487e  lock xadd [rdx+10h], eax
0x180014883  add     eax, edi
0x180014885  test    eax, eax
0x180014887  jg      short loc_180014898
0x180014889  mov     rcx, [rdx]
0x18001488c  mov     rax, [rcx]
0x18001488f  mov     rax, [rax+8]
0x180014893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014898  mov     rdx, [rsp+2A0h+var_258]
0x18001489d  mov     eax, edi
0x18001489f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800148a3  lock xadd [rdx+10h], eax
0x1800148a8  add     eax, edi
0x1800148aa  test    eax, eax
0x1800148ac  jg      short loc_1800148BD
0x1800148ae  mov     rcx, [rdx]
0x1800148b1  mov     rax, [rcx]
0x1800148b4  mov     rax, [rax+8]
0x1800148b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148bd  lea     r8, aMigxml; "</migXml>\r\n"
0x1800148c4  lea     rdx, [rsp+2A0h+psz]
0x1800148c9  lea     rcx, [rsp+2A0h+var_250]
0x1800148ce  call    ??HATL@@YA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@0@AEBV10@PEB_W@Z; ATL::operator+(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &,wchar_t const *)
0x1800148d3  mov     rdx, rax
0x1800148d6  lea     rcx, [rsp+2A0h+psz]
0x1800148db  call    ??4?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator=(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800148e0  mov     rdx, [rsp+2A0h+var_250]
0x1800148e5  mov     eax, edi
0x1800148e7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800148eb  lock xadd [rdx+10h], eax
0x1800148f0  add     eax, edi
0x1800148f2  test    eax, eax
0x1800148f4  jg      short loc_180014905
0x1800148f6  mov     rcx, [rdx]
0x1800148f9  mov     rax, [rcx]
0x1800148fc  mov     rax, [rax+8]
0x180014900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014905  mov     rbx, [rsp+2A0h+psz]
0x18001490a  mov     rcx, rbx; psz
0x18001490d  call    cs:__imp_SysAllocString
0x180014913  mov     [rsi], rax
0x180014916  lea     rdx, [rbx-18h]
0x18001491a  mov     eax, edi
0x18001491c  lock xadd [rdx+10h], eax
0x180014921  add     eax, edi
0x180014923  test    eax, eax
0x180014925  jg      short loc_180014936
0x180014927  mov     rcx, [rdx]
0x18001492a  mov     rax, [rcx]
0x18001492d  mov     rax, [rax+8]
0x180014931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014936  mov     rbx, [rsp+2A0h+hKey]
0x18001493b  test    rbx, rbx
0x18001493e  jz      short loc_180014949
0x180014940  mov     rcx, rbx; hKey
0x180014943  call    cs:__imp_RegCloseKey
0x180014949  xor     eax, eax
0x18001494b  mov     rcx, [rbp+1A0h+var_20]
0x180014952  xor     rcx, rsp; StackCookie
0x180014955  call    __security_check_cookie
0x18001495a  lea     r11, [rsp+2A0h+var_10]
0x180014962  mov     rbx, [r11+20h]
0x180014966  mov     rsi, [r11+38h]
0x18001496a  mov     rsp, r11
0x18001496d  pop     r14
0x18001496f  pop     rdi
0x180014970  pop     rbp
0x180014971  retn
0x180014972  mov     rdx, rdi; struct IUnknown *
0x180014975  mov     ecx, eax; int
0x180014977  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18001497d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180014983  mov     rdx, rdi; struct IUnknown *
0x180014986  mov     ecx, eax; int
0x180014988  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
