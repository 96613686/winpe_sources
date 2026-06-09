# File::SearchForPeFiles(ConfigSettings const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800c815c`
- end: `0x1800c83da`
- name: `?SearchForPeFiles@File@@KAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `638`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c815c`
- `0x1800c83e0`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000faf0`
- `0x18001c5f0`
- `0x1800295dc`
- `0x1800c3188`
- `0x1800c31ac`
- `0x1800c815c`
- `0x1800c9870`
- `0x1800c993c`
- `0x1800c9a04`
- `0x1800ce818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8390`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800c8281`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800c8281`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800c8382`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800c8382`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800c8257`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800c82fe`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800c8257`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800c82fe`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800c81c4`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800c81c4`

## string_xrefs

- `0x1800c81d8`: `Skipping network path: %ws`
- `0x1800c8216`: `Skipping install directory: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall File::SearchForPeFiles(int a1, __int64 *a2, unsigned int a3, __int64 a4, __int64 a5)
{
  __int64 *v6; // rdi
  const WCHAR *v8; // rcx
  const WCHAR *v9; // rcx
  char *FirstFileW; // rbx
  const WCHAR *v11; // rcx
  PWSTR v12; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-C8h] BYREF
  char *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[20]; // [rsp+48h] [rbp-B8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF

  v6 = a2;
  if ( (unsigned __int64)a2[2] < 4 )
    return;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int64)v6[3] <= 7 )
      v8 = (const WCHAR *)v6;
    else
      v8 = (const WCHAR *)*v6;
    if ( PathIsNetworkPathW(v8) )
    {
      if ( (unsigned __int64)v6[3] > 7 )
        v6 = (__int64 *)*v6;
      AslLogCallPrintf(3, "File::SearchForPeFiles", 1117, "Skipping network path: %ws", v6);
      return;
    }
    if ( !(unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(v6) )
    {
      if ( (unsigned __int64)v6[3] > 7 )
        v6 = (__int64 *)*v6;
      AslLogCallPrintf(3, "File::SearchForPeFiles", 1123, "Skipping install directory: %ws", v6);
      return;
    }
  }
  ppszPathOut = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  if ( (unsigned __int64)v6[3] <= 7 )
    v9 = (const WCHAR *)v6;
  else
    v9 = (const WCHAR *)*v6;
  if ( PathAllocCombine(v9, L"*", 1u, &ppszPathOut) < 0 )
    goto LABEL_38;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(ppszPathOut, &FindFileData);
  v14 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_37;
  while ( 1 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2])
      || (FindFileData.dwFileAttributes & 0x1440) != 0 )
    {
      goto LABEL_35;
    }
    v12 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    v11 = (unsigned __int64)v6[3] <= 7 ? (const WCHAR *)v6 : (const WCHAR *)*v6;
    if ( PathAllocCombine(v11, FindFileData.cFileName, 1u, &v12) < 0 )
      break;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      std::wstring::wstring(pszPath, v12);
      std::vector<std::wstring>::push_back(a5, pszPath);
      goto LABEL_33;
    }
    if ( a3 < 7 )
    {
      std::wstring::wstring(pszPath, v12);
      File::SearchForPeFiles(a1, (unsigned int)pszPath, a3 + 1, 7, a5);
LABEL_33:
      std::wstring::_Tidy_deallocate(pszPath);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
LABEL_35:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      GetLastError();
      goto LABEL_37;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
LABEL_37:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v14);
LABEL_38:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
}

```

## disassembly

```asm
0x1800c815c  push    rbp
0x1800c815e  push    rbx
0x1800c815f  push    rsi
0x1800c8160  push    rdi
0x1800c8161  push    r12
0x1800c8163  push    r14
0x1800c8165  push    r15
0x1800c8167  lea     rbp, [rsp-1D0h]
0x1800c816f  sub     rsp, 2D0h
0x1800c8176  mov     rax, cs:__security_cookie
0x1800c817d  xor     rax, rsp
0x1800c8180  mov     [rbp+200h+var_40], rax
0x1800c8187  mov     esi, r8d
0x1800c818a  mov     rdi, rdx
0x1800c818d  mov     r15, rcx
0x1800c8190  mov     r14, [rbp+200h+arg_20]
0x1800c8197  cmp     qword ptr [rdx+10h], 4
0x1800c819c  jb      loc_1800C83AC
0x1800c81a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppInv_InstallDirectory@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_InstallDirectory@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_InstallDirectory> `wil::Feature<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::GetImpl(void)'::`2'::impl
0x1800c81a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_InstallDirectory@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_InstallDirectory>::__private_IsEnabled(void)
0x1800c81ae  xor     r12d, r12d
0x1800c81b1  test    al, al
0x1800c81b3  jz      short loc_1800C8225
0x1800c81b5  cmp     qword ptr [rdi+18h], 7
0x1800c81ba  jbe     short loc_1800C81C1
0x1800c81bc  mov     rcx, [rdi]
0x1800c81bf  jmp     short loc_1800C81C4
0x1800c81c1  mov     rcx, rdi; pszPath
0x1800c81c4  call    cs:__imp_PathIsNetworkPathW
0x1800c81ca  test    eax, eax
0x1800c81cc  jz      short loc_1800C8200
0x1800c81ce  cmp     qword ptr [rdi+18h], 7
0x1800c81d3  jbe     short loc_1800C81D8
0x1800c81d5  mov     rdi, [rdi]
0x1800c81d8  lea     r9, aSkippingNetwor; "Skipping network path: %ws"
0x1800c81df  mov     r8d, 45Dh
0x1800c81e5  mov     [rsp+300h+var_2E0], rdi
0x1800c81ea  lea     rdx, aFileSearchforp; "File::SearchForPeFiles"
0x1800c81f1  mov     ecx, 3
0x1800c81f6  call    AslLogCallPrintf
0x1800c81fb  jmp     loc_1800C83AC
0x1800c8200  mov     rcx, rdi
0x1800c8203  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x1800c8208  test    al, al
0x1800c820a  jnz     short loc_1800C8225
0x1800c820c  cmp     qword ptr [rdi+18h], 7
0x1800c8211  jbe     short loc_1800C8216
0x1800c8213  mov     rdi, [rdi]
0x1800c8216  lea     r9, aSkippingInstal; "Skipping install directory: %ws"
0x1800c821d  mov     r8d, 463h
0x1800c8223  jmp     short loc_1800C81E5
0x1800c8225  mov     [rsp+300h+ppszPathOut], r12
0x1800c822a  xor     edx, edx
0x1800c822c  lea     rcx, [rsp+300h+ppszPathOut]
0x1800c8231  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c8236  cmp     qword ptr [rdi+18h], 7
0x1800c823b  jbe     short loc_1800C8242
0x1800c823d  mov     rcx, [rdi]
0x1800c8240  jmp     short loc_1800C8245
0x1800c8242  mov     rcx, rdi; pszPathIn
0x1800c8245  lea     r9, [rsp+300h+ppszPathOut]; ppszPathOut
0x1800c824a  mov     r8d, 1; dwFlags
0x1800c8250  lea     rdx, pszMore; "*"
0x1800c8257  call    cs:__imp_PathAllocCombine
0x1800c825d  test    eax, eax
0x1800c825f  js      loc_1800C83A2
0x1800c8265  xor     edx, edx; Val
0x1800c8267  mov     r8d, 250h; Size
0x1800c826d  lea     rcx, [rsp+300h+FindFileData]; void *
0x1800c8272  call    memset_0
0x1800c8277  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x1800c827c  mov     rcx, [rsp+300h+ppszPathOut]; lpFileName
0x1800c8281  call    cs:__imp_FindFirstFileW
0x1800c8287  mov     rbx, rax
0x1800c828a  mov     [rsp+300h+var_2C0], rax
0x1800c828f  dec     rax
0x1800c8292  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800c8296  ja      loc_1800C8397
0x1800c829c  cmp     [rbp+200h+FindFileData.cFileName], 2Eh ; '.'
0x1800c82a1  jnz     short loc_1800C82C1
0x1800c82a3  movzx   eax, [rbp+200h+FindFileData.cFileName+2]
0x1800c82a7  test    ax, ax
0x1800c82aa  jz      loc_1800C837A
0x1800c82b0  cmp     ax, 2Eh ; '.'
0x1800c82b4  jnz     short loc_1800C82C1
0x1800c82b6  cmp     [rbp+200h+FindFileData.cFileName+4], r12w
0x1800c82bb  jz      loc_1800C837A
0x1800c82c1  test    [rsp+300h+FindFileData.dwFileAttributes], 1440h
0x1800c82c9  jnz     loc_1800C837A
0x1800c82cf  mov     [rsp+300h+var_2D0], r12
0x1800c82d4  xor     edx, edx
0x1800c82d6  lea     rcx, [rsp+300h+var_2D0]
0x1800c82db  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c82e0  cmp     qword ptr [rdi+18h], 7
0x1800c82e5  jbe     short loc_1800C82EC
0x1800c82e7  mov     rcx, [rdi]
0x1800c82ea  jmp     short loc_1800C82EF
0x1800c82ec  mov     rcx, rdi; pszPathIn
0x1800c82ef  lea     r9, [rsp+300h+var_2D0]; ppszPathOut
0x1800c82f4  mov     r8d, 1; dwFlags
0x1800c82fa  lea     rdx, [rbp+200h+FindFileData.cFileName]; pszMore
0x1800c82fe  call    cs:__imp_PathAllocCombine
0x1800c8304  test    eax, eax
0x1800c8306  js      loc_1800C83CD
0x1800c830c  test    byte ptr [rsp+300h+FindFileData.dwFileAttributes], 10h
0x1800c8311  jz      short loc_1800C8347
0x1800c8313  cmp     esi, 7
0x1800c8316  jnb     short loc_1800C8370
0x1800c8318  mov     rdx, [rsp+300h+var_2D0]
0x1800c831d  lea     rcx, [rsp+300h+pszPath]
0x1800c8322  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c8327  nop
0x1800c8328  lea     r8d, [rsi+1]
0x1800c832c  mov     [rsp+300h+var_2E0], r14
0x1800c8331  mov     r9d, 7
0x1800c8337  lea     rdx, [rsp+300h+pszPath]
0x1800c833c  mov     rcx, r15
0x1800c833f  call    ?SearchForPeFiles@File@@KAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; File::SearchForPeFiles(ConfigSettings const &,std::wstring const &,ulong,ulong,std::vector<std::wstring> &)
0x1800c8344  nop
0x1800c8345  jmp     short loc_1800C8365
0x1800c8347  mov     rdx, [rsp+300h+var_2D0]
0x1800c834c  lea     rcx, [rsp+300h+pszPath]
0x1800c8351  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c8356  nop
0x1800c8357  lea     rdx, [rsp+300h+pszPath]
0x1800c835c  mov     rcx, r14
0x1800c835f  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800c8364  nop
0x1800c8365  lea     rcx, [rsp+300h+pszPath]
0x1800c836a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c836f  nop
0x1800c8370  lea     rcx, [rsp+300h+var_2D0]
0x1800c8375  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c837a  lea     rdx, [rsp+300h+FindFileData]; lpFindFileData
0x1800c837f  mov     rcx, rbx; hFindFile
0x1800c8382  call    cs:__imp_FindNextFileW
0x1800c8388  test    eax, eax
0x1800c838a  jnz     loc_1800C829C
0x1800c8390  call    cs:__imp_GetLastError
0x1800c8396  nop
0x1800c8397  lea     rcx, [rsp+300h+var_2C0]
0x1800c839c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800c83a1  nop
0x1800c83a2  lea     rcx, [rsp+300h+ppszPathOut]
0x1800c83a7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c83ac  mov     rcx, [rbp+200h+var_40]
0x1800c83b3  xor     rcx, rsp; StackCookie
0x1800c83b6  call    __security_check_cookie
0x1800c83bb  add     rsp, 2D0h
0x1800c83c2  pop     r15
0x1800c83c4  pop     r14
0x1800c83c6  pop     r12
0x1800c83c8  pop     rdi
0x1800c83c9  pop     rsi
0x1800c83ca  pop     rbx
0x1800c83cb  pop     rbp
0x1800c83cc  retn
0x1800c83cd  lea     rcx, [rsp+300h+var_2D0]
0x1800c83d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c83d7  jmp     short loc_1800C8397
```
