# COpenSearchRowset::_GetParentWindowFromSite(void)

- ea: `0x1800442f4`
- end: `0x180044359`
- name: `?_GetParentWindowFromSite@COpenSearchRowset@@AEAAPEAUHWND__@@XZ`
- size: `101`
- prototype: `HWND __fastcall(COpenSearchRowset *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044360`
- `0x180044d50`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x1800442f4`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180044327`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180044327`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18004433b`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18004433b`

## pseudocode

```c
HWND __fastcall COpenSearchRowset::_GetParentWindowFromSite(COpenSearchRowset *this)
{
  __int64 v1; // r10
  HWND v2; // rbx
  void *ppvOut; // [rsp+30h] [rbp+8h] BYREF
  HWND phwnd; // [rsp+38h] [rbp+10h] BYREF

  phwnd = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppvOut);
  if ( IUnknown_QueryService(
         *(IUnknown **)(v1 + 32),
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_00000000_0000_0000_c000_000000000046,
         &ppvOut) >= 0 )
    IUnknown_GetWindow((IUnknown *)ppvOut, &phwnd);
  v2 = phwnd;
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppvOut);
  return v2;
}

```

## disassembly

```asm
0x1800442f4  push    rbx
0x1800442f6  sub     rsp, 20h
0x1800442fa  mov     r10, rcx
0x1800442fd  mov     [rsp+28h+phwnd], 0
0x180044306  lea     rcx, [rsp+28h+ppvOut]; void *
0x18004430b  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180044310  mov     rcx, [r10+20h]; punk
0x180044314  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180044319  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180044320  lea     rdx, SID_STopLevelBrowser; guidService
0x180044327  call    cs:__imp_IUnknown_QueryService
0x18004432d  test    eax, eax
0x18004432f  js      short loc_180044341
0x180044331  mov     rcx, [rsp+28h+ppvOut]; punk
0x180044336  lea     rdx, [rsp+28h+phwnd]; phwnd
0x18004433b  call    cs:__imp_IUnknown_GetWindow
0x180044341  mov     rbx, [rsp+28h+phwnd]
0x180044346  lea     rcx, [rsp+28h+ppvOut]
0x18004434b  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180044350  mov     rax, rbx
0x180044353  add     rsp, 20h
0x180044357  pop     rbx
0x180044358  retn
```
