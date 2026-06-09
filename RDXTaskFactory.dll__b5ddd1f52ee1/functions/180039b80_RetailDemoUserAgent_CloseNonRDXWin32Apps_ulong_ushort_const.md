# RetailDemoUserAgent::CloseNonRDXWin32Apps(ulong,ushort const * *)

- ea: `0x180039b80`
- end: `0x180039e09`
- name: `?CloseNonRDXWin32Apps@RetailDemoUserAgent@@UEAAJKPEAPEBG@Z`
- size: `649`
- prototype: `__int64 __fastcall(RetailDemoUserAgent *__hidden this, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180039e50`

## callees

- `0x180003390`
- `0x180006450`
- `0x18000649c`
- `0x18000c168`
- `0x1800181b0`
- `0x180022ad8`
- `0x18002a8a4`
- `0x18002fa88`
- `0x18003262c`
- `0x1800351ac`
- `0x18003548c`
- `0x180039b80`
- `0x18003afa0`
- `0x1800412d0`
- `0x1800415c8`
- `0x1800420dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039d22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039d22`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180039d31`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180039d31`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039c54`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039c54`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180039c6f`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180039c6f`
- `USER32!GetWindowThreadProcessId` at `0x180039c42`
- `USER32!GetWindowThreadProcessId` at `0x180039c42`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180039cc3`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180039cc3`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x180039d0b`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x180039d0b`

## string_xrefs

- `0x180039bbc`: `ServiceReadWrite\ProcessCloseExclusionList`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RetailDemoUserAgent::CloseNonRDXWin32Apps(
        RetailDemoUserAgent *this,
        unsigned int a2,
        const unsigned __int16 **a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int128 i; // rdi
  HANDLE v9; // rbx
  RetailDemoUserAgent *v10; // rcx
  HANDLE *v11; // rbx
  HANDLE *v12; // rdi
  RetailDemoUserAgent *v13; // rcx
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE *pHandles[2]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE *v17; // [rsp+48h] [rbp-B8h]
  HANDLE v18; // [rsp+50h] [rbp-B0h] BYREF
  void *v19; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+80h] [rbp-80h]
  _BYTE v23[40]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ImageFileName[264]; // [rsp+B0h] [rbp-50h] BYREF

  *(_OWORD *)pHandles = 0;
  v17 = 0;
  RetailDemoUtil::EnumWin32AppListFromRegistry(&v19, L"ServiceReadWrite\\ProcessCloseExclusionList");
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
    v5);
  if ( a2 && a3 )
  {
    v7 = 0;
    do
    {
      std::wstring::wstring((__int64)v23, (__int64)a3[v7]);
      std::vector<std::wstring>::push_back(&v19, v23);
      std::wstring::_Tidy_deallocate(v23);
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < a2 );
  }
  RetailDemoUserAgent::EnumWin32AppWindows(v6, &v21, &v19);
  for ( i = v21; (_QWORD)i != *((_QWORD *)&i + 1); *(_QWORD *)&i = i + 16 )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId(*(HWND *)i, &dwProcessId);
    v9 = OpenProcess(0x401u, 0, dwProcessId);
    v18 = v9;
    if ( !K32GetProcessImageFileNameW(v9, ImageFileName, 0x104u) )
      goto LABEL_13;
    if ( *(_DWORD *)(i + 8) )
    {
      if ( *(_DWORD *)(i + 8) != 1 )
        goto LABEL_13;
    }
    else if ( pHandles[1] == v17 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
        pHandles,
        pHandles[1],
        &v18);
    }
    else
    {
      *pHandles[1] = v9;
      v18 = 0;
      ++pHandles[1];
    }
    PostMessageW(*(HWND *)i, 0x10u, 0, 0);
LABEL_13:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
  }
  v10 = (RetailDemoUserAgent *)pHandles[1];
  if ( pHandles[0] != pHandles[1] )
  {
    MsgWaitForMultipleObjects(pHandles[1] - pHandles[0], pHandles[0], 1, 0x3E8u, 0x1CFFu);
    v11 = pHandles[0];
    v12 = pHandles[1];
    while ( v11 != v12 )
    {
      if ( WaitForSingleObject(*v11, 0) )
        TerminateProcess(*v11, 0);
      ++v11;
    }
  }
  RetailDemoUserAgent::TerminateAppsInInclusionList(v10);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_3PPAppsM>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RDX_3PPAppsM>::GetImpl'::`2'::impl) )
    RetailDemoUserAgent::TerminateAppsInDMSInclusionList(v13);
  if ( (_QWORD)v21 )
  {
    std::_Deallocate<16>((void *)v21, (v22 - v21) & 0xFFFFFFFFFFFFFFF0uLL);
    v21 = 0;
    v22 = 0;
  }
  if ( v19 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v19, v20);
    std::_Deallocate<16>(v19, (*((_QWORD *)&v20 + 1) - (_QWORD)v19) & 0xFFFFFFFFFFFFFFE0uLL);
    v19 = 0;
    v20 = 0;
  }
  if ( pHandles[0] )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
      pHandles[0],
      pHandles[1]);
    std::_Deallocate<16>(pHandles[0], ((char *)v17 - (char *)pHandles[0]) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x180039b80  push    rbp
0x180039b82  push    rbx
0x180039b83  push    rsi
0x180039b84  push    rdi
0x180039b85  lea     rbp, [rsp-1D8h]
0x180039b8d  sub     rsp, 2D8h
0x180039b94  mov     rax, cs:__security_cookie
0x180039b9b  xor     rax, rsp
0x180039b9e  mov     [rbp+1F0h+var_30], rax
0x180039ba5  mov     rdi, r8
0x180039ba8  mov     esi, edx
0x180039baa  xorps   xmm0, xmm0
0x180039bad  movdqu  xmmword ptr [rsp+2F0h+pHandles], xmm0
0x180039bb3  mov     [rsp+2F0h+var_2A8], 0
0x180039bbc  lea     rdx, c_retailDemoKeyProcessCloseExclusionListSubKey; "ServiceReadWrite\\ProcessCloseExclusion"...
0x180039bc3  lea     rcx, [rsp+2F0h+var_298]
0x180039bc8  call    ?EnumWin32AppListFromRegistry@RetailDemoUtil@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; RetailDemoUtil::EnumWin32AppListFromRegistry(ushort const *)
0x180039bcd  nop
0x180039bce  mov     dl, 1
0x180039bd0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x180039bd7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180039bdc  test    esi, esi
0x180039bde  jz      short loc_180039C13
0x180039be0  test    rdi, rdi
0x180039be3  jz      short loc_180039C13
0x180039be5  xor     ebx, ebx
0x180039be7  mov     rdx, [rdi+rbx*8]
0x180039beb  lea     rcx, [rbp+1F0h+var_268]
0x180039bef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180039bf4  nop
0x180039bf5  lea     rdx, [rbp+1F0h+var_268]
0x180039bf9  lea     rcx, [rsp+2F0h+var_298]
0x180039bfe  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180039c03  nop
0x180039c04  lea     rcx, [rbp+1F0h+var_268]
0x180039c08  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039c0d  inc     ebx
0x180039c0f  cmp     ebx, esi
0x180039c11  jb      short loc_180039BE7
0x180039c13  lea     r8, [rsp+2F0h+var_298]
0x180039c18  lea     rdx, [rsp+2F0h+var_280]
0x180039c1d  call    ?EnumWin32AppWindows@RetailDemoUserAgent@@AEAA?AV?$vector@UTopLevelWindowInfo@@V?$allocator@UTopLevelWindowInfo@@@std@@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z; RetailDemoUserAgent::EnumWin32AppWindows(std::vector<std::wstring> const &)
0x180039c22  nop
0x180039c23  mov     rdi, qword ptr [rsp+2F0h+var_280]
0x180039c28  mov     rsi, qword ptr [rsp+2F0h+var_280+8]
0x180039c2d  jmp     loc_180039CD8
0x180039c32  mov     [rsp+2F0h+dwProcessId], 0
0x180039c3a  lea     rdx, [rsp+2F0h+dwProcessId]; lpdwProcessId
0x180039c3f  mov     rcx, [rdi]; hWnd
0x180039c42  call    cs:__imp_GetWindowThreadProcessId
0x180039c48  mov     r8d, [rsp+2F0h+dwProcessId]; dwProcessId
0x180039c4d  xor     edx, edx; bInheritHandle
0x180039c4f  mov     ecx, 401h; dwDesiredAccess
0x180039c54  call    cs:__imp_OpenProcess
0x180039c5a  mov     rbx, rax
0x180039c5d  mov     [rsp+2F0h+var_2A0], rax
0x180039c62  mov     r8d, 104h; nSize
0x180039c68  lea     rdx, [rbp+1F0h+ImageFileName]; lpImageFileName
0x180039c6c  mov     rcx, rax; hProcess
0x180039c6f  call    cs:__imp_K32GetProcessImageFileNameW
0x180039c75  test    eax, eax
0x180039c77  jz      short loc_180039CCA
0x180039c79  cmp     dword ptr [rdi+8], 0
0x180039c7d  jnz     short loc_180039CB0
0x180039c7f  mov     rdx, [rsp+2F0h+pHandles+8]
0x180039c84  cmp     rdx, [rsp+2F0h+var_2A8]
0x180039c89  jz      short loc_180039C9F
0x180039c8b  mov     [rdx], rbx
0x180039c8e  mov     [rsp+2F0h+var_2A0], 0
0x180039c97  add     [rsp+2F0h+pHandles+8], 8
0x180039c9d  jmp     short loc_180039CB6
0x180039c9f  lea     r8, [rsp+2F0h+var_2A0]
0x180039ca4  lea     rcx, [rsp+2F0h+pHandles]
0x180039ca9  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180039cae  jmp     short loc_180039CB6
0x180039cb0  cmp     dword ptr [rdi+8], 1
0x180039cb4  jnz     short loc_180039CCA
0x180039cb6  xor     r9d, r9d; lParam
0x180039cb9  xor     r8d, r8d; wParam
0x180039cbc  lea     edx, [r9+10h]; Msg
0x180039cc0  mov     rcx, [rdi]; hWnd
0x180039cc3  call    cs:__imp_PostMessageW
0x180039cc9  nop
0x180039cca  lea     rcx, [rsp+2F0h+var_2A0]
0x180039ccf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180039cd4  add     rdi, 10h
0x180039cd8  cmp     rdi, rsi
0x180039cdb  jnz     loc_180039C32
0x180039ce1  mov     rcx, [rsp+2F0h+pHandles+8]
0x180039ce6  mov     rdx, [rsp+2F0h+pHandles]; pHandles
0x180039ceb  cmp     rdx, rcx
0x180039cee  jz      short loc_180039D40
0x180039cf0  sub     rcx, rdx
0x180039cf3  sar     rcx, 3; nCount
0x180039cf7  mov     [rsp+2F0h+dwWakeMask], 1CFFh; dwWakeMask
0x180039cff  mov     r9d, 3E8h; dwMilliseconds
0x180039d05  mov     r8d, 1; fWaitAll
0x180039d0b  call    cs:__imp_MsgWaitForMultipleObjects
0x180039d11  mov     rbx, [rsp+2F0h+pHandles]
0x180039d16  mov     rdi, [rsp+2F0h+pHandles+8]
0x180039d1b  jmp     short loc_180039D3B
0x180039d1d  xor     edx, edx; dwMilliseconds
0x180039d1f  mov     rcx, [rbx]; hHandle
0x180039d22  call    cs:__imp_WaitForSingleObject
0x180039d28  test    eax, eax
0x180039d2a  jz      short loc_180039D37
0x180039d2c  xor     edx, edx; uExitCode
0x180039d2e  mov     rcx, [rbx]; hProcess
0x180039d31  call    cs:__imp_TerminateProcess
0x180039d37  add     rbx, 8
0x180039d3b  cmp     rbx, rdi
0x180039d3e  jnz     short loc_180039D1D
0x180039d40  call    ?TerminateAppsInInclusionList@RetailDemoUserAgent@@AEAAXXZ; RetailDemoUserAgent::TerminateAppsInInclusionList(void)
0x180039d45  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_3PPAppsM@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_3PPAppsM@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_3PPAppsM> `wil::Feature<__WilFeatureTraits_Feature_RDX_3PPAppsM>::GetImpl(void)'::`2'::impl
0x180039d4c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_3PPAppsM@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_3PPAppsM>::__private_IsEnabled(void)
0x180039d51  test    al, al
0x180039d53  jz      short loc_180039D5B
0x180039d55  call    ?TerminateAppsInDMSInclusionList@RetailDemoUserAgent@@AEAAXXZ; RetailDemoUserAgent::TerminateAppsInDMSInclusionList(void)
0x180039d5a  nop
0x180039d5b  mov     rcx, qword ptr [rsp+2F0h+var_280]
0x180039d60  test    rcx, rcx
0x180039d63  jz      short loc_180039D86
0x180039d65  mov     rdx, [rbp+1F0h+var_270]
0x180039d69  sub     rdx, rcx
0x180039d6c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180039d70  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180039d75  xorps   xmm0, xmm0
0x180039d78  movdqu  [rsp+2F0h+var_280], xmm0
0x180039d7e  mov     [rbp+1F0h+var_270], 0
0x180039d86  mov     rcx, [rsp+2F0h+var_298]
0x180039d8b  test    rcx, rcx
0x180039d8e  jz      short loc_180039DC2
0x180039d90  mov     rdx, qword ptr [rsp+2F0h+var_290]
0x180039d95  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180039d9a  mov     rcx, [rsp+2F0h+var_298]
0x180039d9f  mov     rdx, qword ptr [rsp+2F0h+var_290+8]
0x180039da4  sub     rdx, rcx
0x180039da7  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180039dab  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180039db0  mov     [rsp+2F0h+var_298], 0
0x180039db9  xorps   xmm0, xmm0
0x180039dbc  movdqu  [rsp+2F0h+var_290], xmm0
0x180039dc2  mov     rcx, [rsp+2F0h+pHandles]
0x180039dc7  test    rcx, rcx
0x180039dca  jz      short loc_180039DEC
0x180039dcc  mov     rdx, [rsp+2F0h+pHandles+8]
0x180039dd1  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &)
0x180039dd6  mov     rcx, [rsp+2F0h+pHandles]
0x180039ddb  mov     rdx, [rsp+2F0h+var_2A8]
0x180039de0  sub     rdx, rcx
0x180039de3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180039de7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180039dec  xor     eax, eax
0x180039dee  mov     rcx, [rbp+1F0h+var_30]
0x180039df5  xor     rcx, rsp; StackCookie
0x180039df8  call    __security_check_cookie
0x180039dfd  add     rsp, 2D8h
0x180039e04  pop     rdi
0x180039e05  pop     rsi
0x180039e06  pop     rbx
0x180039e07  pop     rbp
0x180039e08  retn
```
