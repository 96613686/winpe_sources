# File::SearchForPeFiles(ConfigSettings const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180037a78`
- end: `0x180037cf5`
- name: `?SearchForPeFiles@File@@KAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `637`
- prototype: `_UNKNOWN **__fastcall(int, const WCHAR *, unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000dfc4`
- `0x180037a78`

## callees

- `0x1800056f0`
- `0x18000c220`
- `0x18000c24c`
- `0x180018a60`
- `0x1800197d4`
- `0x180022340`
- `0x18002261c`
- `0x1800260f4`
- `0x180037a78`
- `0x1800404c4`
- `0x1800493b8`
- `0x180059920`
- `0x18005a8bc`
- `0x18010066c`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x180037ba8`
- `KERNEL32!FindFirstFileW` at `0x180037ba8`
- `KERNEL32!FindNextFileW` at `0x180037c98`
- `KERNEL32!FindNextFileW` at `0x180037c98`
- `KERNEL32!GetLastError` at `0x180037ca6`
- `KERNEL32!GetLastError` at `0x180037ca6`
- `SHLWAPI!PathIsNetworkPathW` at `0x180037ae8`
- `SHLWAPI!PathIsNetworkPathW` at `0x180037ae8`

## string_xrefs

- `0x180037afc`: `Skipping network path: %ws`
- `0x180037b3a`: `Skipping install directory: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_UNKNOWN **__fastcall File::SearchForPeFiles(int a1, const WCHAR *a2, unsigned int a3, __int64 a4, __int64 a5)
{
  _UNKNOWN **result; // rax
  const WCHAR *v9; // rcx
  const char *v10; // r9
  int v11; // r8d
  const WCHAR *v12; // rcx
  char *FirstFileW; // rbx
  const WCHAR *v14; // rcx
  unsigned __int16 *v15; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v17[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR pszPath[12]; // [rsp+58h] [rbp-B0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+78h] [rbp-90h] BYREF
  _UNKNOWN *retaddr; // [rsp+300h] [rbp+1F8h] BYREF

  result = &retaddr;
  v17[1] = -2;
  if ( *((_QWORD *)a2 + 2) < 4u )
    return result;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::GetImpl'::`2'::impl) )
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v9 = a2;
    else
      v9 = *(const WCHAR **)a2;
    if ( PathIsNetworkPathW(v9) )
    {
      v10 = "Skipping network path: %ws";
      v11 = 1117;
      return (_UNKNOWN **)AslLogCallPrintf(3, (unsigned int)"File::SearchForPeFiles", v11, (_DWORD)v10);
    }
    if ( !Utility::ShouldScanInstallDirectoryForFiles((__int64)a2) )
    {
      v10 = "Skipping install directory: %ws";
      v11 = 1123;
      return (_UNKNOWN **)AslLogCallPrintf(3, (unsigned int)"File::SearchForPeFiles", v11, (_DWORD)v10);
    }
  }
  lpFileName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpFileName,
    0);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v12 = a2;
  else
    v12 = *(const WCHAR **)a2;
  if ( (int)PathAllocCombine(v12, L"*", 1u, (unsigned __int16 **)&lpFileName) < 0 )
    return (_UNKNOWN **)wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpFileName);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
  v17[0] = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_30;
  while ( 1 )
  {
    if ( Utility::PathIsDotOrDotDot(FindFileData.cFileName) || (FindFileData.dwFileAttributes & 0x1440) != 0 )
      goto LABEL_28;
    v15 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v15,
      0);
    v14 = *((_QWORD *)a2 + 3) <= 7u ? a2 : *(const WCHAR **)a2;
    if ( (int)PathAllocCombine(v14, FindFileData.cFileName, 1u, &v15) < 0 )
      break;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      std::wstring::wstring(pszPath, v15);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a5, pszPath);
      goto LABEL_26;
    }
    if ( a3 < 7 )
    {
      std::wstring::wstring(pszPath, v15);
      File::SearchForPeFiles(a1, (unsigned int)pszPath, a3 + 1, 7, a5);
LABEL_26:
      std::wstring::~wstring(pszPath);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
LABEL_28:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      GetLastError();
      goto LABEL_30;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
LABEL_30:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v17);
  return (_UNKNOWN **)wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpFileName);
}

```

## disassembly

```asm
0x180037a78  mov     rax, rsp
0x180037a7b  push    rbp
0x180037a7c  push    rsi
0x180037a7d  push    rdi
0x180037a7e  push    r14
0x180037a80  push    r15
0x180037a82  lea     rbp, [rax-1F8h]
0x180037a89  sub     rsp, 2D0h
0x180037a90  mov     qword ptr [rsp+2F0h+var_2A8], 0FFFFFFFFFFFFFFFEh
0x180037a99  mov     [rax+20h], rbx
0x180037a9d  mov     rax, cs:__security_cookie
0x180037aa4  xor     rax, rsp
0x180037aa7  mov     [rbp+1F0h+var_30], rax
0x180037aae  mov     esi, r8d
0x180037ab1  mov     rdi, rdx
0x180037ab4  mov     r15, rcx
0x180037ab7  mov     r14, [rbp+1F0h+arg_20]
0x180037abe  cmp     qword ptr [rdx+10h], 4
0x180037ac3  jb      loc_180037CC2
0x180037ac9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppInv_InstallDirectory@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_InstallDirectory@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_InstallDirectory> `wil::Feature<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::GetImpl(void)'::`2'::impl
0x180037ad0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_InstallDirectory@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::__private_IsEnabled(void)
0x180037ad5  test    al, al
0x180037ad7  jz      short loc_180037B49
0x180037ad9  cmp     qword ptr [rdi+18h], 7
0x180037ade  jbe     short loc_180037AE5
0x180037ae0  mov     rcx, [rdi]
0x180037ae3  jmp     short loc_180037AE8
0x180037ae5  mov     rcx, rdi; pszPath
0x180037ae8  call    cs:__imp_PathIsNetworkPathW
0x180037aee  test    eax, eax
0x180037af0  jz      short loc_180037B24
0x180037af2  cmp     qword ptr [rdi+18h], 7
0x180037af7  jbe     short loc_180037AFC
0x180037af9  mov     rdi, [rdi]
0x180037afc  lea     r9, aSkippingNetwor; "Skipping network path: %ws"
0x180037b03  mov     r8d, 45Dh
0x180037b09  mov     [rsp+20h], rdi
0x180037b0e  lea     rdx, aFileSearchforp; "File::SearchForPeFiles"
0x180037b15  mov     ecx, 3
0x180037b1a  call    AslLogCallPrintf
0x180037b1f  jmp     loc_180037CC2
0x180037b24  mov     rcx, rdi
0x180037b27  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x180037b2c  test    al, al
0x180037b2e  jnz     short loc_180037B49
0x180037b30  cmp     qword ptr [rdi+18h], 7
0x180037b35  jbe     short loc_180037B3A
0x180037b37  mov     rdi, [rdi]
0x180037b3a  lea     r9, aSkippingInstal; "Skipping install directory: %ws"
0x180037b41  mov     r8d, 463h
0x180037b47  jmp     short loc_180037B09
0x180037b49  mov     [rsp+2F0h+lpFileName], 0
0x180037b52  xor     edx, edx
0x180037b54  lea     rcx, [rsp+2F0h+lpFileName]
0x180037b59  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180037b5e  cmp     qword ptr [rdi+18h], 7
0x180037b63  jbe     short loc_180037B6A
0x180037b65  mov     rcx, [rdi]
0x180037b68  jmp     short loc_180037B6D
0x180037b6a  mov     rcx, rdi; pszPathIn
0x180037b6d  lea     r9, [rsp+2F0h+lpFileName]; unsigned __int16 **
0x180037b72  mov     r8d, 1; dwFlags
0x180037b78  lea     rdx, asc_18015249C; "*"
0x180037b7f  call    ?PathAllocCombine@@YAJPEBG0W4PATHCCH_OPTIONS@@PEAPEAG@Z; PathAllocCombine(ushort const *,ushort const *,PATHCCH_OPTIONS,ushort * *)
0x180037b84  test    eax, eax
0x180037b86  js      loc_180037CB8
0x180037b8c  xor     edx, edx; Val
0x180037b8e  mov     r8d, 250h; Size
0x180037b94  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x180037b99  call    memset_0
0x180037b9e  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180037ba3  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x180037ba8  call    cs:__imp_FindFirstFileW
0x180037bae  mov     rbx, rax
0x180037bb1  mov     [rsp+2F0h+var_2B0], rax
0x180037bb6  dec     rax
0x180037bb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037bbd  ja      loc_180037CAD
0x180037bc3  lea     rcx, [rbp+1F0h+FindFileData.cFileName]; unsigned __int16 *
0x180037bc7  call    ?PathIsDotOrDotDot@Utility@@SA_NPEBG@Z; Utility::PathIsDotOrDotDot(ushort const *)
0x180037bcc  test    al, al
0x180037bce  jnz     loc_180037C90
0x180037bd4  test    [rsp+2F0h+FindFileData.dwFileAttributes], 1440h
0x180037bdc  jnz     loc_180037C90
0x180037be2  mov     [rsp+2F0h+var_2C0], 0
0x180037beb  xor     edx, edx
0x180037bed  lea     rcx, [rsp+2F0h+var_2C0]
0x180037bf2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180037bf7  cmp     qword ptr [rdi+18h], 7
0x180037bfc  jbe     short loc_180037C03
0x180037bfe  mov     rcx, [rdi]
0x180037c01  jmp     short loc_180037C06
0x180037c03  mov     rcx, rdi; pszPathIn
0x180037c06  lea     r9, [rsp+2F0h+var_2C0]; unsigned __int16 **
0x180037c0b  mov     r8d, 1; dwFlags
0x180037c11  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; pszMore
0x180037c15  call    ?PathAllocCombine@@YAJPEBG0W4PATHCCH_OPTIONS@@PEAPEAG@Z; PathAllocCombine(ushort const *,ushort const *,PATHCCH_OPTIONS,ushort * *)
0x180037c1a  test    eax, eax
0x180037c1c  js      loc_180037CE8
0x180037c22  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x180037c27  jz      short loc_180037C5D
0x180037c29  cmp     esi, 7
0x180037c2c  jnb     short loc_180037C86
0x180037c2e  mov     rdx, [rsp+2F0h+var_2C0]
0x180037c33  lea     rcx, [rsp+2F0h+pszPath]
0x180037c38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037c3d  nop
0x180037c3e  lea     r8d, [rsi+1]
0x180037c42  mov     [rsp+20h], r14
0x180037c47  mov     r9d, 7
0x180037c4d  lea     rdx, [rsp+2F0h+pszPath]
0x180037c52  mov     rcx, r15
0x180037c55  call    ?SearchForPeFiles@File@@KAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; File::SearchForPeFiles(ConfigSettings const &,std::wstring const &,ulong,ulong,std::vector<std::wstring> &)
0x180037c5a  nop
0x180037c5b  jmp     short loc_180037C7B
0x180037c5d  mov     rdx, [rsp+2F0h+var_2C0]
0x180037c62  lea     rcx, [rsp+2F0h+pszPath]
0x180037c67  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037c6c  nop
0x180037c6d  lea     rdx, [rsp+2F0h+pszPath]
0x180037c72  mov     rcx, r14
0x180037c75  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180037c7a  nop
0x180037c7b  lea     rcx, [rsp+2F0h+pszPath]
0x180037c80  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037c85  nop
0x180037c86  lea     rcx, [rsp+2F0h+var_2C0]
0x180037c8b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037c90  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x180037c95  mov     rcx, rbx; hFindFile
0x180037c98  call    cs:__imp_FindNextFileW
0x180037c9e  test    eax, eax
0x180037ca0  jnz     loc_180037BC3
0x180037ca6  call    cs:__imp_GetLastError
0x180037cac  nop
0x180037cad  lea     rcx, [rsp+2F0h+var_2B0]
0x180037cb2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180037cb7  nop
0x180037cb8  lea     rcx, [rsp+2F0h+lpFileName]
0x180037cbd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037cc2  mov     rcx, [rbp+1F0h+var_30]
0x180037cc9  xor     rcx, rsp; StackCookie
0x180037ccc  call    __security_check_cookie
0x180037cd1  mov     rbx, [rsp+2F0h+arg_18]
0x180037cd9  add     rsp, 2D0h
0x180037ce0  pop     r15
0x180037ce2  pop     r14
0x180037ce4  pop     rdi
0x180037ce5  pop     rsi
0x180037ce6  pop     rbp
0x180037ce7  retn
0x180037ce8  lea     rcx, [rsp+2F0h+var_2C0]
0x180037ced  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037cf2  jmp     short loc_180037CAD
```
