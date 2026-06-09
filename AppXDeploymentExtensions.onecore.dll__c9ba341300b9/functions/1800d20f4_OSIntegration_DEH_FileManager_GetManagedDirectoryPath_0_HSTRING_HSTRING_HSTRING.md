# OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800d20f4`
- end: `0x1800d24d2`
- name: `??$GetManagedDirectoryPath@$0A@@FileManager@DEH@OSIntegration@@CAJPEAUHSTRING__@@PEAPEAU3@1@Z`
- size: `990`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING *newString, HSTRING *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800d1c90`
- `0x1800d1f4c`
- `0x1801d6740`

## callees

- `0x1800649b4`
- `0x1800754b8`
- `0x18007b440`
- `0x18009aff4`
- `0x1800a67d0`
- `0x1800b10c0`
- `0x1800bf99c`
- `0x1800cc418`
- `0x1800d20f4`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f0a7c`
- `0x1801d4be4`
- `0x1801d74a4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d22b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d23e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d2461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d22b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d23e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800d2461`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d21c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2352`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d21c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d2283`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d22f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d2312`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d2283`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d22f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d2312`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d2242`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d2242`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x1800d2155`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x1800d21da`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x1800d2155`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetSystemMetadataPathForPackage` at `0x1800d21da`

## string_xrefs

- `0x1800d22cc`: `HStringReference(managedDirectoryPath).CopyTo(pDirectoryPath)`
- `0x1800d225a`: `PathAllocCombine( systemMetadataPath, L"PackagedCom", PATHCCH_ALLOW_LONG_PATHS, &managedDirectoryPath)`
- `0x1800d21f0`: `::GetSystemMetadataPathForPackage( WindowsGetStringRawBuffer(packageMoniker, nullptr), &systemMetadataPathLength, systemMetadataPath)`
- `0x1800d217c`: `OSIntegration::DEH::FileManager::GetManagedDirectoryPath`
- `0x1800d21fc`: `OSIntegration::DEH::FileManager::GetManagedDirectoryPath`
- `0x1800d2266`: `OSIntegration::DEH::FileManager::GetManagedDirectoryPath`
- `0x1800d22d8`: `OSIntegration::DEH::FileManager::GetManagedDirectoryPath`
- `0x1800d2404`: `OSIntegration::DEH::FileManager::GetManagedDirectoryPath`
- `0x1800d2485`: `OSIntegration::DEH::FileManager::GetManagedDirectoryPath`
- `0x1800d23f8`: `HStringReference(managedDirectoryPath.c_str()).CopyTo(pDirectoryPath)`
- `0x1800d2238`: `PackagedCom`
- `0x1800d2328`: `PackagedCom`
- `0x1800d2479`: `securityDescriptor.CopyTo(pDirectorySecurityDescriptor)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::FileManager::GetManagedDirectoryPath<0>(
        HSTRING string,
        HSTRING *newString,
        HSTRING *a3)
{
  PCWSTR v6; // rax
  int v7; // eax
  void *v9; // rdi
  PCWSTR v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  HSTRING_HEADER *v15; // rax
  HRESULT v16; // eax
  unsigned int v17; // ebx
  WCHAR *StringRawBuffer; // rax
  __int64 v19; // rdx
  struct std::filesystem::path *SystemMetadataPathForPackage; // rax
  WCHAR *v21; // rax
  __int64 v22; // rax
  HRESULT v23; // eax
  unsigned int v24; // ebx
  HRESULT v25; // eax
  unsigned int v26; // ebx
  char *v27; // [rsp+28h] [rbp-C0h]
  unsigned int v28[4]; // [rsp+30h] [rbp-B8h] BYREF
  PWSTR ppszPathOut; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-A0h]
  HSTRING_HEADER v31; // [rsp+50h] [rbp-98h] BYREF
  HSTRING stringa; // [rsp+68h] [rbp-80h]
  _QWORD v33[4]; // [rsp+70h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    ppszPathOut = (PWSTR)L"PackagedCom";
    v30 = 11;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&v31, &ppszPathOut);
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
    v19 = -1;
    do
      ++v19;
    while ( StringRawBuffer[v19] );
    ppszPathOut = StringRawBuffer;
    v30 = v19;
    SystemMetadataPathForPackage = (struct std::filesystem::path *)OSIntegration::DEH::GetSystemMetadataPathForPackage(
                                                                     &hstringHeader,
                                                                     &ppszPathOut);
    std::filesystem::operator/((std::filesystem::path *)v33, SystemMetadataPathForPackage);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    std::wstring::_Tidy_deallocate(&v31);
    v21 = (WCHAR *)v33;
    if ( v33[3] > 7u )
      v21 = (WCHAR *)v33[0];
    ppszPathOut = v21;
    v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &ppszPathOut);
    v23 = WindowsDuplicateString(*(HSTRING *)(v22 + 24), newString);
    v24 = v23;
    if ( v23 < 0 )
    {
      LODWORD(v27) = v23;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x2EE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
        "OSIntegration::DEH::FileManager::GetManagedDirectoryPath",
        "HStringReference(managedDirectoryPath.c_str()).CopyTo(pDirectoryPath)",
        v27,
        v28[0]);
      std::wstring::_Tidy_deallocate(v33);
      return v24;
    }
    std::wstring::_Tidy_deallocate(v33);
  }
  else
  {
    v28[0] = 0;
    v6 = WindowsGetStringRawBuffer(string, 0);
    v7 = GetSystemMetadataPathForPackage(v6, v28, 0);
    if ( v7 != 122 )
    {
      if ( !v7 )
        return 0;
      LODWORD(v27) = v7;
      return wil::details::in1diag5::Return_Win32(
               retaddr,
               (void *)0x2FD,
               (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
               "OSIntegration::DEH::FileManager::GetManagedDirectoryPath",
               "error",
               v27,
               v28[0]);
    }
    v9 = operator new[](saturated_mul(v28[0], 2u));
    v10 = WindowsGetStringRawBuffer(string, 0);
    v11 = GetSystemMetadataPathForPackage(v10, v28, v9);
    if ( v11 )
    {
      LODWORD(v27) = v11;
      v12 = wil::details::in1diag5::Return_Win32(
              retaddr,
              (void *)0x304,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
              "OSIntegration::DEH::FileManager::GetManagedDirectoryPath",
              "::GetSystemMetadataPathForPackage( WindowsGetStringRawBuffer(packageMoniker, nullptr), &systemMetadataPath"
              "Length, systemMetadataPath)",
              v27,
              v28[0]);
      operator delete(v9, 2u);
      return v12;
    }
    ppszPathOut = 0;
    v13 = PathAllocCombine((PCWSTR)v9, L"PackagedCom", 1u, &ppszPathOut);
    v14 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v27) = v13;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x309,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
        "OSIntegration::DEH::FileManager::GetManagedDirectoryPath",
        "PathAllocCombine( systemMetadataPath, L\"PackagedCom\", PATHCCH_ALLOW_LONG_PATHS, &managedDirectoryPath)",
        v27,
        v28[0]);
      LocalFree(ppszPathOut);
      operator delete(v9, 2u);
      return v14;
    }
    v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&ppszPathOut);
    v16 = WindowsDuplicateString((HSTRING)v15[1].Reserved.Reserved1, newString);
    v17 = v16;
    if ( v16 < 0 )
    {
      LODWORD(v27) = v16;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x30B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
        "OSIntegration::DEH::FileManager::GetManagedDirectoryPath",
        "HStringReference(managedDirectoryPath).CopyTo(pDirectoryPath)",
        v27,
        v28[0]);
      LocalFree(ppszPathOut);
      operator delete(v9, 2u);
      return v17;
    }
    LocalFree(ppszPathOut);
    operator delete(v9, 2u);
  }
  if ( !a3 )
    return 0;
  stringa = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v31,
    L"D:(A;CIOI;GRGX;;;BU)(A;CIOI;GRGX;;;AC)(A;CIOI;GRGX;;;S-1-15-3-1024-2405443489-874036122-4286035555-1823921565-174654"
     "7431-2453885448-3625952902-991631256)(A;CIOI;GRGWSD;;;SY)",
    0xAEu,
    0xADu);
  v25 = WindowsDuplicateString(stringa, a3);
  v26 = v25;
  if ( v25 >= 0 )
    return 0;
  LODWORD(v27) = v25;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x318,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\filemanager.cpp",
    "OSIntegration::DEH::FileManager::GetManagedDirectoryPath",
    "securityDescriptor.CopyTo(pDirectorySecurityDescriptor)",
    v27,
    v28[0]);
  return v26;
}

```

## disassembly

```asm
0x1800d20f4  mov     [rsp+arg_18], rbx
0x1800d20f9  push    rsi
0x1800d20fa  push    rdi
0x1800d20fb  push    r12
0x1800d20fd  push    r14
0x1800d20ff  push    r15
0x1800d2101  sub     rsp, 0C0h
0x1800d2108  mov     rax, cs:__security_cookie
0x1800d210f  xor     rax, rsp
0x1800d2112  mov     [rsp+0E8h+var_38], rax
0x1800d211a  mov     rsi, r8
0x1800d211d  mov     r14, rdx
0x1800d2120  mov     rbx, rcx
0x1800d2123  xor     r15d, r15d
0x1800d2126  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800d212d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800d2132  test    al, al
0x1800d2134  jnz     loc_1800D2328
0x1800d213a  mov     [rsp+0E8h+var_B8], r15d; int
0x1800d213f  xor     edx, edx; length
0x1800d2141  mov     rcx, rbx; string
0x1800d2144  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d214a  mov     rcx, rax
0x1800d214d  xor     r8d, r8d
0x1800d2150  lea     rdx, [rsp+0E8h+var_B8]
0x1800d2155  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800d215b  cmp     eax, 7Ah ; 'z'
0x1800d215e  jz      short loc_1800D21A0
0x1800d2160  test    eax, eax
0x1800d2162  jz      short loc_1800D2199
0x1800d2164  mov     rcx, [rsp+0E8h]; this
0x1800d216c  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x1800d2170  lea     rax, aError_1; "error"
0x1800d2177  mov     [rsp+0E8h+var_C8], rax; char *
0x1800d217c  lea     r9, aOsintegrationD_516; "OSIntegration::DEH::FileManager::GetMan"...
0x1800d2183  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d218a  mov     edx, 2FDh; void *
0x1800d218f  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x1800d2194  jmp     loc_1800D24A9
0x1800d2199  xor     eax, eax
0x1800d219b  jmp     loc_1800D24A9
0x1800d21a0  mov     edx, [rsp+0E8h+var_B8]
0x1800d21a4  mov     r12d, 2
0x1800d21aa  mov     eax, r12d
0x1800d21ad  mul     rdx
0x1800d21b0  lea     rdx, [r12-3]
0x1800d21b5  cmovb   rax, rdx
0x1800d21b9  mov     rcx, rax; unsigned __int64
0x1800d21bc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800d21c1  mov     rdi, rax
0x1800d21c4  xor     edx, edx; length
0x1800d21c6  mov     rcx, rbx; string
0x1800d21c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d21cf  mov     r8, rdi
0x1800d21d2  lea     rdx, [rsp+0E8h+var_B8]
0x1800d21d7  mov     rcx, rax
0x1800d21da  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800d21e0  test    eax, eax
0x1800d21e2  jz      short loc_1800D2228
0x1800d21e4  mov     rcx, [rsp+0E8h]; this
0x1800d21ec  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x1800d21f0  lea     rax, aGetsystemmetad_1; "::GetSystemMetadataPathForPackage( Wind"...
0x1800d21f7  mov     [rsp+0E8h+var_C8], rax; char *
0x1800d21fc  lea     r9, aOsintegrationD_516; "OSIntegration::DEH::FileManager::GetMan"...
0x1800d2203  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d220a  mov     edx, 304h; void *
0x1800d220f  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x1800d2214  mov     ebx, eax
0x1800d2216  mov     edx, r12d; unsigned __int64
0x1800d2219  mov     rcx, rdi; void *
0x1800d221c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d2221  mov     eax, ebx
0x1800d2223  jmp     loc_1800D24A9
0x1800d2228  mov     [rsp+0E8h+ppszPathOut], r15
0x1800d222d  lea     r9, [rsp+0E8h+ppszPathOut]; ppszPathOut
0x1800d2232  mov     r8d, 1; dwFlags
0x1800d2238  lea     rdx, pszMore; "PackagedCom"
0x1800d223f  mov     rcx, rdi; pszPathIn
0x1800d2242  call    cs:__imp_PathAllocCombine
0x1800d2248  mov     ebx, eax
0x1800d224a  test    eax, eax
0x1800d224c  jns     short loc_1800D229B
0x1800d224e  mov     rcx, [rsp+0E8h]; this
0x1800d2256  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x1800d225a  lea     rax, aPathalloccombi_4; "PathAllocCombine( systemMetadataPath, L"...
0x1800d2261  mov     [rsp+0E8h+var_C8], rax; char *
0x1800d2266  lea     r9, aOsintegrationD_516; "OSIntegration::DEH::FileManager::GetMan"...
0x1800d226d  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d2274  mov     edx, 309h; void *
0x1800d2279  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d227e  mov     rcx, [rsp+0E8h+ppszPathOut]; hMem
0x1800d2283  call    cs:__imp_LocalFree
0x1800d2289  mov     rdx, r12; unsigned __int64
0x1800d228c  mov     rcx, rdi; void *
0x1800d228f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d2294  mov     eax, ebx
0x1800d2296  jmp     loc_1800D24A9
0x1800d229b  lea     rdx, [rsp+0E8h+ppszPathOut]
0x1800d22a0  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x1800d22a8  call    ??$?0V?$AutoPtrLocal@G@Common@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$AutoPtrLocal@G@Common@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Common::AutoPtrLocal<ushort> const &,Microsoft::WRL::Details::Dummy)
0x1800d22ad  mov     rdx, r14; newString
0x1800d22b0  mov     rcx, [rax+18h]; string
0x1800d22b4  call    cs:__imp_WindowsDuplicateString
0x1800d22ba  mov     ebx, eax
0x1800d22bc  test    eax, eax
0x1800d22be  jns     short loc_1800D230D
0x1800d22c0  mov     rcx, [rsp+0E8h]; this
0x1800d22c8  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x1800d22cc  lea     rax, aHstringreferen_0; "HStringReference(managedDirectoryPath)."...
0x1800d22d3  mov     [rsp+0E8h+var_C8], rax; char *
0x1800d22d8  lea     r9, aOsintegrationD_516; "OSIntegration::DEH::FileManager::GetMan"...
0x1800d22df  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d22e6  mov     edx, 30Bh; void *
0x1800d22eb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d22f0  mov     rcx, [rsp+0E8h+ppszPathOut]; hMem
0x1800d22f5  call    cs:__imp_LocalFree
0x1800d22fb  mov     rdx, r12; unsigned __int64
0x1800d22fe  mov     rcx, rdi; void *
0x1800d2301  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d2306  mov     eax, ebx
0x1800d2308  jmp     loc_1800D24A9
0x1800d230d  mov     rcx, [rsp+0E8h+ppszPathOut]; hMem
0x1800d2312  call    cs:__imp_LocalFree
0x1800d2318  mov     rdx, r12; unsigned __int64
0x1800d231b  mov     rcx, rdi; void *
0x1800d231e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d2323  jmp     loc_1800D2434
0x1800d2328  lea     rax, pszMore; "PackagedCom"
0x1800d232f  mov     [rsp+0E8h+ppszPathOut], rax
0x1800d2334  mov     [rsp+0E8h+var_A0], 0Bh
0x1800d233d  lea     rdx, [rsp+0E8h+ppszPathOut]
0x1800d2342  lea     rcx, [rsp+0E8h+var_98]
0x1800d2347  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1800d234c  nop
0x1800d234d  xor     edx, edx; length
0x1800d234f  mov     rcx, rbx; string
0x1800d2352  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2358  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800d235c  inc     rdx
0x1800d235f  cmp     [rax+rdx*2], r15w
0x1800d2364  jnz     short loc_1800D235C
0x1800d2366  mov     [rsp+0E8h+ppszPathOut], rax
0x1800d236b  mov     [rsp+0E8h+var_A0], rdx
0x1800d2370  lea     rdx, [rsp+0E8h+ppszPathOut]
0x1800d2375  lea     rcx, [rsp+0E8h+hstringHeader]
0x1800d237d  call    ?GetSystemMetadataPathForPackage@DEH@OSIntegration@@YA?AVpath@filesystem@std@@V?$basic_string_view@GU?$char_traits@G@std@@@5@@Z; OSIntegration::DEH::GetSystemMetadataPathForPackage(std::basic_string_view<ushort>)
0x1800d2382  nop
0x1800d2383  lea     r8, [rsp+0E8h+var_98]
0x1800d2388  mov     rdx, rax; struct std::filesystem::path *
0x1800d238b  lea     rcx, [rsp+0E8h+var_78]; this
0x1800d2390  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800d2395  nop
0x1800d2396  lea     rcx, [rsp+0E8h+hstringHeader]
0x1800d239e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d23a3  nop
0x1800d23a4  lea     rcx, [rsp+0E8h+var_98]
0x1800d23a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d23ae  lea     rax, [rsp+0E8h+var_78]
0x1800d23b3  cmp     [rsp+0E8h+var_60], 7
0x1800d23bc  cmova   rax, [rsp+0E8h+var_78]
0x1800d23c2  mov     [rsp+0E8h+ppszPathOut], rax
0x1800d23c7  lea     rdx, [rsp+0E8h+ppszPathOut]
0x1800d23cc  lea     rcx, [rsp+0E8h+hstringHeader]
0x1800d23d4  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d23d9  mov     rdx, r14; newString
0x1800d23dc  mov     rcx, [rax+18h]; string
0x1800d23e0  call    cs:__imp_WindowsDuplicateString
0x1800d23e6  mov     ebx, eax
0x1800d23e8  test    eax, eax
0x1800d23ea  jns     short loc_1800D242A
0x1800d23ec  mov     rcx, [rsp+0E8h]; this
0x1800d23f4  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x1800d23f8  lea     rax, aHstringreferen; "HStringReference(managedDirectoryPath.c"...
0x1800d23ff  mov     [rsp+0E8h+var_C8], rax; char *
0x1800d2404  lea     r9, aOsintegrationD_516; "OSIntegration::DEH::FileManager::GetMan"...
0x1800d240b  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d2412  mov     edx, 2EEh; void *
0x1800d2417  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d241c  lea     rcx, [rsp+0E8h+var_78]
0x1800d2421  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d2426  mov     eax, ebx
0x1800d2428  jmp     short loc_1800D24A9
0x1800d242a  lea     rcx, [rsp+0E8h+var_78]
0x1800d242f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d2434  test    rsi, rsi
0x1800d2437  jz      short loc_1800D24A1
0x1800d2439  mov     [rsp+0E8h+string], r15
0x1800d243e  mov     r9d, 0ADh; unsigned int
0x1800d2444  lea     r8d, [r9+1]; unsigned int
0x1800d2448  lea     rdx, aDACioiGrgxBuAC; "D:(A;CIOI;GRGX;;;BU)(A;CIOI;GRGX;;;AC)("...
0x1800d244f  lea     rcx, [rsp+0E8h+var_98]; hstringHeader
0x1800d2454  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d2459  mov     rdx, rsi; newString
0x1800d245c  mov     rcx, [rsp+0E8h+string]; string
0x1800d2461  call    cs:__imp_WindowsDuplicateString
0x1800d2467  mov     ebx, eax
0x1800d2469  test    eax, eax
0x1800d246b  jns     short loc_1800D24A1
0x1800d246d  mov     rcx, [rsp+0E8h]; this
0x1800d2475  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x1800d2479  lea     rax, aSecuritydescri; "securityDescriptor.CopyTo(pDirectorySec"...
0x1800d2480  mov     [rsp+0E8h+var_C8], rax; char *
0x1800d2485  lea     r9, aOsintegrationD_516; "OSIntegration::DEH::FileManager::GetMan"...
0x1800d248c  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800d2493  mov     edx, 318h; void *
0x1800d2498  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800d249d  mov     eax, ebx
0x1800d249f  jmp     short loc_1800D24A9
0x1800d24a1  xor     eax, eax
0x1800d24a3  jmp     short loc_1800D24A9
0x1800d24a5  mov     eax, [rsp+0E8h+var_B8]
0x1800d24a9  mov     rcx, [rsp+0E8h+var_38]
0x1800d24b1  xor     rcx, rsp; StackCookie
0x1800d24b4  call    __security_check_cookie
0x1800d24b9  mov     rbx, [rsp+0E8h+arg_18]
0x1800d24c1  add     rsp, 0C0h
0x1800d24c8  pop     r15
0x1800d24ca  pop     r14
0x1800d24cc  pop     r12
0x1800d24ce  pop     rdi
0x1800d24cf  pop     rsi
0x1800d24d0  retn
```
