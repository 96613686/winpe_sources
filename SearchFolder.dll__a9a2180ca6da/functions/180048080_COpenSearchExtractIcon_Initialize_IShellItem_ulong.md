# COpenSearchExtractIcon::Initialize(IShellItem *,ulong)

- ea: `0x180048080`
- end: `0x1800482ef`
- name: `?Initialize@COpenSearchExtractIcon@@UEAAJPEAUIShellItem@@K@Z`
- size: `623`
- prototype: `__int64 __fastcall(COpenSearchExtractIcon *__hidden this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x1800129f8`
- `0x18002850c`
- `0x1800418bc`
- `0x180048080`
- `0x180051010`

## import_xrefs

- `SHELL32!AssocCreateForClasses` at `0x180048145`
- `SHELL32!AssocCreateForClasses` at `0x180048244`
- `SHELL32!AssocCreateForClasses` at `0x180048145`
- `SHELL32!AssocCreateForClasses` at `0x180048244`
- `SHLWAPI!PathParseIconLocationW` at `0x18004828b`
- `SHLWAPI!PathParseIconLocationW` at `0x18004828b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18004810d`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800481c8`
- `SHLWAPI!__imp_StrCmpICW` at `0x18004810d`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800481c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800481e0`

## string_xrefs

- `0x180048106`: `opensearchresult`

## pseudocode

```c
__int64 __fastcall COpenSearchExtractIcon::Initialize(COpenSearchExtractIcon *this, struct IShellItem *a2)
{
  __int64 v3; // rax
  __int64 (__fastcall **v4)(__int64, GUID *, __int64); // r9
  __int64 v5; // r10
  HRESULT v6; // ebx
  LPCWSTR *v7; // rdi
  WCHAR *v8; // rcx
  void *v9; // rcx
  void *v11; // [rsp+30h] [rbp-30h] BYREF
  const WCHAR *v12; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR pszStr1; // [rsp+40h] [rbp-20h] BYREF
  ASSOCIATIONELEMENT rgClasses; // [rsp+48h] [rbp-18h] BYREF
  void *ppv; // [rsp+88h] [rbp+28h] BYREF
  __int64 v16; // [rsp+98h] [rbp+38h] BYREF

  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v16);
  v3 = ATL::CComPtrBase<IXMLDOMDocument>::operator&((__int64)&v16);
  v6 = (*v4)(v5, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, v3);
  if ( v6 >= 0 )
  {
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
    pszStr1 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, LPCWSTR *))(*(_QWORD *)v16 + 136LL))(
           v16,
           &PKEY_ItemType,
           &pszStr1);
    if ( v6 >= 0 )
    {
      if ( StrCmpICW(pszStr1, L"opensearchresult")
        || (rgClasses.ac = ASSOCCLASS_PROGID_STR,
            rgClasses.pszClass = L"http",
            rgClasses.hkClass = 0,
            v6 = AssocCreateForClasses(&rgClasses, 1u, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f, &ppv),
            v6 >= 0) )
      {
        if ( !ATL::CComPtrBase<IResultSetManager>::operator!(&ppv)
          || (v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *, void **))(*(_QWORD *)v16 + 24LL))(
                     v16,
                     0,
                     &BHID_SFUIObject,
                     &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f,
                     &ppv),
              v6 >= 0) )
        {
          v7 = (LPCWSTR *)((char *)this + 16);
          v6 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, char *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 458753,
                 0,
                 (char *)this + 16);
          if ( v6 < 0 )
            goto LABEL_17;
          if ( !StrCmpICW(*v7, L"\"%1\"") )
          {
            v8 = (WCHAR *)*v7;
            *v7 = 0;
            CoTaskMemFree(v8);
            v12 = 0;
            v6 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, const WCHAR **))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   4653059,
                   0,
                   &v12);
            if ( v6 >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v11);
              rgClasses.pszClass = v12;
              rgClasses.ac = ASSOCCLASS_CLSID_STR;
              rgClasses.hkClass = 0;
              v6 = AssocCreateForClasses(&rgClasses, 1u, &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f, &v11);
              if ( v6 >= 0 )
                v6 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, char *))(*(_QWORD *)v11 + 24LL))(
                       v11,
                       458753,
                       0,
                       (char *)this + 16);
              ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>();
            }
            CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v12);
            if ( v6 < 0 )
              goto LABEL_17;
          }
          if ( *v7 )
            *((_DWORD *)this + 3) = PathParseIconLocationW((LPWSTR)*v7);
          if ( !*v7 )
          {
LABEL_17:
            v9 = ppv;
            *((_DWORD *)this + 2) |= 1u;
            *((_DWORD *)this + 3) = 0;
            v6 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, char *))(*(_QWORD *)v9 + 24LL))(
                   v9,
                   33619975,
                   0,
                   (char *)this + 16);
          }
        }
      }
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pszStr1);
    ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>();
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180048080  mov     [rsp-18h+arg_0], rbx
0x180048085  push    rbp
0x180048086  push    rsi
0x180048087  push    rdi
0x180048088  mov     rbp, rsp
0x18004808b  sub     rsp, 60h
0x18004808f  mov     rsi, rcx
0x180048092  mov     r10, rdx
0x180048095  lea     rcx, [rbp+arg_18]; void *
0x180048099  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18004809e  mov     r9, [rdx]
0x1800480a1  lea     rcx, [rbp+arg_18]
0x1800480a5  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x1800480aa  mov     r8, rax
0x1800480ad  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1800480b4  mov     rax, [r9]
0x1800480b7  mov     rcx, r10
0x1800480ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480bf  mov     ebx, eax
0x1800480c1  test    eax, eax
0x1800480c3  js      loc_1800482D4
0x1800480c9  lea     rcx, [rbp+ppv]; void *
0x1800480cd  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800480d2  mov     rcx, [rbp+arg_18]
0x1800480d6  lea     r8, [rbp+pszStr1]
0x1800480da  mov     [rbp+pszStr1], 0
0x1800480e2  lea     rdx, PKEY_ItemType
0x1800480e9  mov     rax, [rcx]
0x1800480ec  mov     rax, [rax+88h]
0x1800480f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480f8  mov     ebx, eax
0x1800480fa  test    eax, eax
0x1800480fc  js      loc_1800482C2
0x180048102  mov     rcx, [rbp+pszStr1]; pszStr1
0x180048106  lea     rdx, aOpensearchresu; "opensearchresult"
0x18004810d  call    cs:__imp_StrCmpICW
0x180048113  test    eax, eax
0x180048115  jnz     short loc_180048155
0x180048117  lea     rax, aHttp; "http"
0x18004811e  mov     [rbp+rgClasses.ac], 2
0x180048125  lea     r9, [rbp+ppv]; ppv
0x180048129  mov     [rbp+rgClasses.pszClass], rax
0x18004812d  lea     r8, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f; riid
0x180048134  mov     [rbp+rgClasses.hkClass], 0
0x18004813c  mov     edx, 1; cClasses
0x180048141  lea     rcx, [rbp+rgClasses]; rgClasses
0x180048145  call    cs:__imp_AssocCreateForClasses
0x18004814b  mov     ebx, eax
0x18004814d  test    eax, eax
0x18004814f  js      loc_1800482C2
0x180048155  lea     rcx, [rbp+ppv]
0x180048159  call    ??7?$CComPtrBase@UIResultSetManager@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IResultSetManager>::operator!(void)
0x18004815e  test    al, al
0x180048160  jz      short loc_180048195
0x180048162  mov     rcx, [rbp+arg_18]
0x180048166  lea     rdx, [rbp+ppv]
0x18004816a  mov     [rsp+60h+var_40], rdx
0x18004816f  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x180048176  lea     r8, BHID_SFUIObject
0x18004817d  xor     edx, edx
0x18004817f  mov     rax, [rcx]
0x180048182  mov     rax, [rax+18h]
0x180048186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004818b  mov     ebx, eax
0x18004818d  test    eax, eax
0x18004818f  js      loc_1800482C2
0x180048195  mov     rcx, [rbp+ppv]
0x180048199  lea     rdi, [rsi+10h]
0x18004819d  mov     r9, rdi
0x1800481a0  xor     r8d, r8d
0x1800481a3  mov     edx, 70001h
0x1800481a8  mov     rax, [rcx]
0x1800481ab  mov     rax, [rax+18h]
0x1800481af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481b4  mov     ebx, eax
0x1800481b6  test    eax, eax
0x1800481b8  js      loc_18004829A
0x1800481be  mov     rcx, [rdi]; pszStr1
0x1800481c1  lea     rdx, a1; "\"%1\""
0x1800481c8  call    cs:__imp_StrCmpICW
0x1800481ce  test    eax, eax
0x1800481d0  jnz     loc_180048283
0x1800481d6  mov     rcx, [rdi]; pv
0x1800481d9  mov     qword ptr [rdi], 0
0x1800481e0  call    cs:__imp_CoTaskMemFree
0x1800481e6  mov     rcx, [rbp+ppv]
0x1800481ea  lea     r9, [rbp+var_28]
0x1800481ee  mov     [rbp+var_28], 0
0x1800481f6  xor     r8d, r8d
0x1800481f9  mov     edx, 470003h
0x1800481fe  mov     rax, [rcx]
0x180048201  mov     rax, [rax+18h]
0x180048205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004820a  mov     ebx, eax
0x18004820c  test    eax, eax
0x18004820e  js      short loc_180048276
0x180048210  lea     rcx, [rbp+var_30]; void *
0x180048214  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180048219  mov     rax, [rbp+var_28]
0x18004821d  lea     r9, [rbp+var_30]; ppv
0x180048221  lea     r8, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f; riid
0x180048228  mov     [rbp+rgClasses.pszClass], rax
0x18004822c  mov     edx, 1; cClasses
0x180048231  mov     [rbp+rgClasses.ac], 4
0x180048238  lea     rcx, [rbp+rgClasses]; rgClasses
0x18004823c  mov     [rbp+rgClasses.hkClass], 0
0x180048244  call    cs:__imp_AssocCreateForClasses
0x18004824a  mov     ebx, eax
0x18004824c  test    eax, eax
0x18004824e  js      short loc_18004826D
0x180048250  mov     rcx, [rbp+var_30]
0x180048254  mov     r9, rdi
0x180048257  xor     r8d, r8d
0x18004825a  mov     edx, 70001h
0x18004825f  mov     rax, [rcx]
0x180048262  mov     rax, [rax+18h]
0x180048266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004826b  mov     ebx, eax
0x18004826d  lea     rcx, [rbp+var_30]
0x180048271  call    ??1?$CComPtr@VCPropertyMapTable@@@ATL@@QEAA@XZ; ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>(void)
0x180048276  lea     rcx, [rbp+var_28]; void *
0x18004827a  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18004827f  test    ebx, ebx
0x180048281  js      short loc_18004829A
0x180048283  mov     rcx, [rdi]; pszIconFile
0x180048286  test    rcx, rcx
0x180048289  jz      short loc_180048294
0x18004828b  call    cs:__imp_PathParseIconLocationW
0x180048291  mov     [rsi+0Ch], eax
0x180048294  cmp     qword ptr [rdi], 0
0x180048298  jnz     short loc_1800482C2
0x18004829a  mov     rcx, [rbp+ppv]
0x18004829e  mov     r9, rdi
0x1800482a1  or      dword ptr [rsi+8], 1
0x1800482a5  xor     r8d, r8d
0x1800482a8  mov     dword ptr [rsi+0Ch], 0
0x1800482af  mov     edx, 2010007h
0x1800482b4  mov     rax, [rcx]
0x1800482b7  mov     rax, [rax+18h]
0x1800482bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482c0  mov     ebx, eax
0x1800482c2  lea     rcx, [rbp+pszStr1]; void *
0x1800482c6  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800482cb  lea     rcx, [rbp+ppv]
0x1800482cf  call    ??1?$CComPtr@VCPropertyMapTable@@@ATL@@QEAA@XZ; ATL::CComPtr<CPropertyMapTable>::~CComPtr<CPropertyMapTable>(void)
0x1800482d4  lea     rcx, [rbp+arg_18]
0x1800482d8  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800482dd  mov     eax, ebx
0x1800482df  mov     rbx, [rsp+60h+arg_0]
0x1800482e7  add     rsp, 60h
0x1800482eb  pop     rdi
0x1800482ec  pop     rsi
0x1800482ed  pop     rbp
0x1800482ee  retn
```
