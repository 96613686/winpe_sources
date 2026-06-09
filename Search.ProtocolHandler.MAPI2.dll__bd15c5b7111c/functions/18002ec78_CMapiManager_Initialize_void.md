# CMapiManager::Initialize(void)

- ea: `0x18002ec78`
- end: `0x18002ed9f`
- name: `?Initialize@CMapiManager@@AEAAJXZ`
- size: `295`
- prototype: `__int64 __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e57c`

## callees

- `0x18000e658`
- `0x18000e6e0`
- `0x1800113ac`
- `0x1800113ec`
- `0x180011884`
- `0x18002db80`
- `0x18002ec78`
- `0x180030a10`
- `0x180031310`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ecc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ecc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ece0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ecf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ed4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ed64`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ece0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ecf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ed4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ed64`

## string_xrefs

- `0x18002ecd6`: `GetDefCachedMode@4`
- `0x18002ecbf`: `msmapi32.dll`
- `0x18002ed43`: `HrOpenOfflineObj@20`
- `0x18002eced`: `GetDefCachedModeDownloadPubFoldFavs@4`
- `0x18002ed5a`: `WrapCompressedRTFStreamEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiManager::Initialize(HMODULE *this)
{
  DWORD MapiIdleThread; // edi
  HMODULE *v3; // rsi
  _QWORD *v4; // rax
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  CLogger::Info(L"CMapiManager::Initialize() Enter");
  MapiIdleThread = 0;
  if ( *((_DWORD *)this + 38) )
  {
    MapiIdleThread = CMapiManager::CreateMapiIdleThread((CMapiManager *)this);
    *((_DWORD *)this + 40) = (MapiIdleThread & 0x80000000) == 0;
  }
  v3 = this + 28;
  if ( GetModuleHandleExW(0, L"msmapi32.dll", this + 28) )
  {
    this[29] = (HMODULE)GetProcAddress(*v3, "GetDefCachedMode@4");
    this[30] = (HMODULE)GetProcAddress(*v3, "GetDefCachedModeDownloadPubFoldFavs@4");
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v6);
    if ( !(unsigned int)CMapiSupport::GetInstalledOutlookVersion(&v6) )
    {
      v4 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
             &v7,
             &v6);
      if ( CMapiSupport::ConvertToIntVersion(v4) >= 0xB000000000000LL )
      {
        this[31] = (HMODULE)GetProcAddress(*v3, "HrOpenOfflineObj@20");
        this[32] = (HMODULE)GetProcAddress(*v3, "WrapCompressedRTFStreamEx");
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v6 - 24));
  }
  CLogger::Info(MapiIdleThread, L"CMapiManager::Initialize() Exit");
  return MapiIdleThread;
}

```

## disassembly

```asm
0x18002ec78  mov     [rsp+arg_10], rbx
0x18002ec7d  mov     [rsp+arg_18], rsi
0x18002ec82  push    rdi
0x18002ec83  sub     rsp, 20h
0x18002ec87  mov     rbx, rcx
0x18002ec8a  lea     rcx, aCmapimanagerIn_2; "CMapiManager::Initialize() Enter"
0x18002ec91  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x18002ec96  xor     edi, edi
0x18002ec98  cmp     [rbx+98h], edi
0x18002ec9e  jz      short loc_18002ECB5
0x18002eca0  mov     rcx, rbx; this
0x18002eca3  call    ?CreateMapiIdleThread@CMapiManager@@AEAAJXZ; CMapiManager::CreateMapiIdleThread(void)
0x18002eca8  mov     edi, eax
0x18002ecaa  not     eax
0x18002ecac  shr     eax, 1Fh
0x18002ecaf  mov     [rbx+0A0h], eax
0x18002ecb5  lea     rsi, [rbx+0E0h]
0x18002ecbc  mov     r8, rsi; phModule
0x18002ecbf  lea     rdx, aMsmapi32Dll; "msmapi32.dll"
0x18002ecc6  xor     ecx, ecx; dwFlags
0x18002ecc8  call    cs:__imp_GetModuleHandleExW
0x18002ecce  test    eax, eax
0x18002ecd0  jz      loc_18002ED7F
0x18002ecd6  lea     rdx, aGetdefcachedmo; "GetDefCachedMode@4"
0x18002ecdd  mov     rcx, [rsi]; hModule
0x18002ece0  call    cs:__imp_GetProcAddress
0x18002ece6  mov     [rbx+0E8h], rax
0x18002eced  lea     rdx, aGetdefcachedmo_0; "GetDefCachedModeDownloadPubFoldFavs@4"
0x18002ecf4  mov     rcx, [rsi]; hModule
0x18002ecf7  call    cs:__imp_GetProcAddress
0x18002ecfd  mov     [rbx+0F0h], rax
0x18002ed04  lea     rcx, [rsp+28h+arg_0]
0x18002ed09  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002ed0e  nop
0x18002ed0f  lea     rcx, [rsp+28h+arg_0]
0x18002ed14  call    ?GetInstalledOutlookVersion@CMapiSupport@@SAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::GetInstalledOutlookVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002ed19  test    eax, eax
0x18002ed1b  jnz     short loc_18002ED71
0x18002ed1d  lea     rdx, [rsp+28h+arg_0]
0x18002ed22  lea     rcx, [rsp+28h+arg_8]
0x18002ed27  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002ed2c  mov     rcx, rax
0x18002ed2f  call    ?ConvertToIntVersion@CMapiSupport@@SA_JV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSupport::ConvertToIntVersion(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>)
0x18002ed34  mov     rcx, 0B000000000000h
0x18002ed3e  cmp     rax, rcx
0x18002ed41  jl      short loc_18002ED71
0x18002ed43  lea     rdx, aHropenofflineo; "HrOpenOfflineObj@20"
0x18002ed4a  mov     rcx, [rsi]; hModule
0x18002ed4d  call    cs:__imp_GetProcAddress
0x18002ed53  mov     [rbx+0F8h], rax
0x18002ed5a  lea     rdx, aWrapcompressed; "WrapCompressedRTFStreamEx"
0x18002ed61  mov     rcx, [rsi]; hModule
0x18002ed64  call    cs:__imp_GetProcAddress
0x18002ed6a  mov     [rbx+100h], rax
0x18002ed71  mov     rcx, [rsp+28h+arg_0]
0x18002ed76  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002ed7a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002ed7f  lea     rdx, aCmapimanagerIn_1; "CMapiManager::Initialize() Exit"
0x18002ed86  mov     ecx, edi; int
0x18002ed88  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x18002ed8d  mov     eax, edi
0x18002ed8f  mov     rbx, [rsp+28h+arg_10]
0x18002ed94  mov     rsi, [rsp+28h+arg_18]
0x18002ed99  add     rsp, 20h
0x18002ed9d  pop     rdi
0x18002ed9e  retn
```
