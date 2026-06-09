# Windows::Internal::Storage::Cloud::FileStorage::CleanupIdsNotInWhiteList(IEnumString *,int)

- ea: `0x1801a8a40`
- end: `0x1801a8e58`
- name: `?CleanupIdsNotInWhiteList@FileStorage@Cloud@Storage@Internal@Windows@@UEAAJPEAUIEnumString@@H@Z`
- size: `1048`
- prototype: `__int64 __fastcall(PCWSTR *this, struct IEnumString *, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x1800238d0`
- `0x180024fd0`
- `0x180047904`
- `0x18005274c`
- `0x180062040`
- `0x1800c8458`
- `0x1800fc644`
- `0x1800ff298`
- `0x18010987c`
- `0x1801201a0`
- `0x180120c94`
- `0x1801a8710`
- `0x1801a88e0`
- `0x1801a8948`
- `0x1801a8a40`
- `0x1801a8e60`
- `0x1801a8f00`
- `0x1801a91c8`
- `0x1801a9350`
- `0x180208010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1801a8b40`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1801a8ca8`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1801a8b40`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1801a8ca8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801a8c46`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1801a8c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a8db2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a8d39`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801a8d39`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a8c15`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a8c15`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a8d56`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a8d56`

## string_xrefs

- `0x1801a8b0a`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1801a8bc2`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1801a8c5d`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1801a8d7b`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`
- `0x1801a8dcf`: `onecoreuap\shell\cloudstore\store\cache\src\filestorage.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Storage::Cloud::FileStorage::CleanupIdsNotInWhiteList(
        PCWSTR *this,
        struct IEnumString *a2,
        unsigned int a3)
{
  int v6; // edi
  struct IEnumStringVtbl *lpVtbl; // rax
  int v8; // ebx
  unsigned __int64 v9; // r9
  int v10; // eax
  char v11; // dl
  __int16 v12; // r8
  int v13; // r9d
  unsigned int v14; // ebx
  _QWORD *v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  HANDLE FirstFileW; // rbx
  HRESULT v20; // eax
  char v21; // dl
  __int16 v22; // r8
  int v23; // r9d
  unsigned int v24; // esi
  _QWORD *v25; // rax
  int v26; // r8d
  bool v27; // si
  void *v28; // rdx
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  unsigned int v32; // ebx
  DWORD LastError; // eax
  unsigned int v34; // ebx
  unsigned int v35; // [rsp+20h] [rbp-738h]
  long double v36; // [rsp+28h] [rbp-730h]
  int v37; // [rsp+30h] [rbp-728h] BYREF
  unsigned __int16 *v38; // [rsp+38h] [rbp-720h] BYREF
  _QWORD v39[2]; // [rsp+40h] [rbp-718h] BYREF
  _BYTE v40[8]; // [rsp+50h] [rbp-708h] BYREF
  __int64 v41; // [rsp+58h] [rbp-700h]
  _BYTE v42[16]; // [rsp+90h] [rbp-6C8h] BYREF
  unsigned __int16 **v43; // [rsp+A0h] [rbp-6B8h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-6B0h] BYREF
  char v45; // [rsp+B0h] [rbp-6A8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-698h] BYREF
  WCHAR pszPathOut[264]; // [rsp+310h] [rbp-448h] BYREF
  WCHAR FileName[264]; // [rsp+520h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+758h] [rbp+0h]

  v6 = 0;
  std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(v40);
  v37 = 0;
  v38 = 0;
  while ( 1 )
  {
    lpVtbl = a2->lpVtbl;
    v43 = &v38;
    v44 = 0;
    v45 = 1;
    v8 = ((__int64 (__fastcall *)(struct IEnumString *, __int64, __int64 *, int *))lpVtbl->Next)(a2, 1, &v44, &v37);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v43);
    if ( v8 )
      break;
    v10 = Windows::Internal::Storage::Cloud::FileStorage::GetFileName(
            (Windows::Internal::Storage::Cloud::FileStorage *)this,
            v38,
            pszPathOut,
            v9);
    v14 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
        (const char *)(unsigned int)v10,
        v35);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v40);
      return v14;
    }
    o((wchar_t)pszPathOut, v11, v12, v13, v35, v36);
    std::wstring::wstring(&v43);
    v16 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(
                      v40,
                      v42,
                      &v43);
    std::wstring::assign(*v16 + 48LL, pszPathOut);
    std::wstring::~wstring(&v43);
  }
  v17 = Windows::Internal::Storage::Cloud::FileStorage::GetFileName(
          (Windows::Internal::Storage::Cloud::FileStorage *)this,
          L"*",
          FileName,
          v9);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
      (const char *)(unsigned int)v17,
      v35);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v40);
    return v18;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v39[0] = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError - 2 > 1 && LastError )
    {
      v34 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
              (const char *)LastError,
              v35);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v39);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v40);
      return v34;
    }
  }
  else
  {
    do
    {
      v20 = PathCchCombine(pszPathOut, 0x104u, this[2], FindFileData.cFileName);
      v24 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
          (const char *)(unsigned int)v20,
          v35);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v39);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v40);
        return v24;
      }
      v27 = 0;
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        o((wchar_t)pszPathOut, v21, v22, v23, v35, v36);
        std::wstring::wstring(&v43);
        v6 |= 1u;
        v25 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                          v40,
                          v42,
                          &v43);
        if ( *v25 == v41
          && Windows::Internal::Storage::Cloud::IsVersionOlderThanNDays(
               (Windows::Internal::Storage::Cloud *)(FindFileData.ftCreationTime.dwLowDateTime
                                                   + ((unsigned __int64)FindFileData.ftCreationTime.dwHighDateTime << 32)),
               a3,
               v26) )
        {
          v27 = 1;
        }
      }
      if ( (v6 & 1) != 0 )
      {
        v6 &= ~1u;
        std::wstring::~wstring(&v43);
      }
      if ( v27 && !DeleteFileW(pszPathOut) )
        wil::details::in1diag3::_Log_GetLastError(retaddr, v28, v29, v30);
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( GetLastError() != 18 )
    {
      v32 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xB3,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\filestorage.cpp",
              v31);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v39);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v40);
      return v32;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(v39);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v40);
  return 0;
}

```

## disassembly

```asm
0x1801a8a40  mov     [rsp+arg_10], rbx
0x1801a8a45  mov     [rsp+arg_18], rsi
0x1801a8a4a  push    rdi
0x1801a8a4b  push    r14
0x1801a8a4d  push    r15
0x1801a8a4f  sub     rsp, 740h
0x1801a8a56  mov     rax, cs:__security_cookie
0x1801a8a5d  xor     rax, rsp
0x1801a8a60  mov     [rsp+758h+var_28], rax
0x1801a8a68  mov     r15d, r8d
0x1801a8a6b  mov     rsi, rdx
0x1801a8a6e  mov     r14, rcx
0x1801a8a71  xor     edi, edi
0x1801a8a73  mov     [rsp+758h+var_728], edi
0x1801a8a77  lea     rcx, [rsp+758h+var_708]
0x1801a8a7c  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::unordered_map<std::wstring,std::wstring>(void)
0x1801a8a81  nop
0x1801a8a82  mov     [rsp+758h+var_728], edi
0x1801a8a86  mov     [rsp+758h+var_720], rdi
0x1801a8a8b  mov     rax, [rsi]
0x1801a8a8e  lea     rcx, [rsp+758h+var_720]
0x1801a8a93  mov     [rsp+758h+var_6B8], rcx
0x1801a8a9b  mov     [rsp+758h+var_6B0], 0
0x1801a8aa7  mov     [rsp+758h+var_6A8], 1
0x1801a8aaf  lea     r9, [rsp+758h+var_728]
0x1801a8ab4  lea     r8, [rsp+758h+var_6B0]
0x1801a8abc  mov     edx, 1
0x1801a8ac1  mov     rcx, rsi
0x1801a8ac4  mov     rax, [rax+18h]
0x1801a8ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8acd  mov     ebx, eax
0x1801a8acf  lea     rcx, [rsp+758h+var_6B8]
0x1801a8ad7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1801a8adc  mov     rcx, r14; this
0x1801a8adf  test    ebx, ebx
0x1801a8ae1  jnz     loc_1801A8B9D
0x1801a8ae7  lea     r8, [rsp+758h+pszPathOut]; unsigned __int16 *
0x1801a8aef  mov     rdx, [rsp+758h+var_720]; unsigned __int16 *
0x1801a8af4  call    ?GetFileName@FileStorage@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAG_K@Z; Windows::Internal::Storage::Cloud::FileStorage::GetFileName(ushort const *,ushort *,unsigned __int64)
0x1801a8af9  mov     ebx, eax
0x1801a8afb  test    eax, eax
0x1801a8afd  jns     short loc_1801A8B38
0x1801a8aff  mov     rcx, [rsp+758h]; this
0x1801a8b07  mov     r9d, eax; char *
0x1801a8b0a  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a8b11  mov     edx, 97h; void *
0x1801a8b16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8b1b  nop
0x1801a8b1c  lea     rcx, [rsp+758h+var_720]
0x1801a8b21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a8b26  nop
0x1801a8b27  lea     rcx, [rsp+758h+var_708]
0x1801a8b2c  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801a8b31  mov     eax, ebx
0x1801a8b33  jmp     loc_1801A8E2E
0x1801a8b38  lea     rcx, [rsp+758h+pszPathOut]
0x1801a8b40  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1801a8b46  lea     rdx, [rsp+758h+pszPathOut]
0x1801a8b4e  lea     rcx, [rsp+758h+var_6B8]
0x1801a8b56  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a8b5b  nop
0x1801a8b5c  lea     r8, [rsp+758h+var_6B8]
0x1801a8b64  lea     rdx, [rsp+758h+var_6C8]
0x1801a8b6c  lea     rcx, [rsp+758h+var_708]
0x1801a8b71  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1801a8b76  mov     rcx, [rax]
0x1801a8b79  add     rcx, 30h ; '0'
0x1801a8b7d  lea     rdx, [rsp+758h+pszPathOut]
0x1801a8b85  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801a8b8a  nop
0x1801a8b8b  lea     rcx, [rsp+758h+var_6B8]
0x1801a8b93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a8b98  jmp     loc_1801A8A8B
0x1801a8b9d  lea     r8, [rsp+758h+FileName]; unsigned __int16 *
0x1801a8ba5  lea     rdx, asc_180228F28; "*"
0x1801a8bac  call    ?GetFileName@FileStorage@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAG_K@Z; Windows::Internal::Storage::Cloud::FileStorage::GetFileName(ushort const *,ushort *,unsigned __int64)
0x1801a8bb1  mov     ebx, eax
0x1801a8bb3  test    eax, eax
0x1801a8bb5  jns     short loc_1801A8BF0
0x1801a8bb7  mov     rcx, [rsp+758h]; this
0x1801a8bbf  mov     r9d, eax; char *
0x1801a8bc2  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a8bc9  mov     edx, 9Fh; void *
0x1801a8bce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8bd3  nop
0x1801a8bd4  lea     rcx, [rsp+758h+var_720]
0x1801a8bd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a8bde  nop
0x1801a8bdf  lea     rcx, [rsp+758h+var_708]
0x1801a8be4  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801a8be9  mov     eax, ebx
0x1801a8beb  jmp     loc_1801A8E2E
0x1801a8bf0  xor     edx, edx; Val
0x1801a8bf2  mov     r8d, 250h; Size
0x1801a8bf8  lea     rcx, [rsp+758h+FindFileData]; void *
0x1801a8c00  call    memset_0
0x1801a8c05  lea     rdx, [rsp+758h+FindFileData]; lpFindFileData
0x1801a8c0d  lea     rcx, [rsp+758h+FileName]; lpFileName
0x1801a8c15  call    cs:__imp_FindFirstFileW
0x1801a8c1b  mov     rbx, rax
0x1801a8c1e  mov     [rsp+758h+var_718], rax
0x1801a8c23  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a8c27  jz      loc_1801A8DB2
0x1801a8c2d  lea     r9, [rsp+758h+FindFileData.cFileName]; pszMore
0x1801a8c35  mov     r8, [r14+10h]; pszPathIn
0x1801a8c39  mov     edx, 104h; cchPathOut
0x1801a8c3e  lea     rcx, [rsp+758h+pszPathOut]; pszPathOut
0x1801a8c46  call    cs:__imp_PathCchCombine
0x1801a8c4c  mov     esi, eax
0x1801a8c4e  test    eax, eax
0x1801a8c50  jns     short loc_1801A8C96
0x1801a8c52  mov     rcx, [rsp+758h]; this
0x1801a8c5a  mov     r9d, eax; char *
0x1801a8c5d  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a8c64  mov     edx, 0AAh; void *
0x1801a8c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a8c6e  nop
0x1801a8c6f  lea     rcx, [rsp+758h+var_718]
0x1801a8c74  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801a8c79  nop
0x1801a8c7a  lea     rcx, [rsp+758h+var_720]
0x1801a8c7f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a8c84  nop
0x1801a8c85  lea     rcx, [rsp+758h+var_708]
0x1801a8c8a  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801a8c8f  mov     eax, esi
0x1801a8c91  jmp     loc_1801A8E2E
0x1801a8c96  test    byte ptr [rsp+758h+FindFileData.dwFileAttributes], 10h
0x1801a8c9e  jnz     short loc_1801A8D0B
0x1801a8ca0  lea     rcx, [rsp+758h+pszPathOut]
0x1801a8ca8  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1801a8cae  mov     rdx, rax
0x1801a8cb1  lea     rcx, [rsp+758h+var_6B8]
0x1801a8cb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801a8cbe  or      edi, 1
0x1801a8cc1  lea     r8, [rsp+758h+var_6B8]
0x1801a8cc9  lea     rdx, [rsp+758h+var_6C8]
0x1801a8cd1  lea     rcx, [rsp+758h+var_708]
0x1801a8cd6  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1801a8cdb  mov     rcx, [rsp+758h+var_700]
0x1801a8ce0  cmp     [rax], rcx
0x1801a8ce3  jnz     short loc_1801A8D0B
0x1801a8ce5  mov     ecx, [rsp+758h+FindFileData.ftCreationTime.dwHighDateTime]
0x1801a8cec  shl     rcx, 20h
0x1801a8cf0  mov     eax, [rsp+758h+FindFileData.ftCreationTime.dwLowDateTime]
0x1801a8cf7  add     rcx, rax; this
0x1801a8cfa  mov     edx, r15d; unsigned __int64
0x1801a8cfd  call    ?IsVersionOlderThanNDays@Cloud@Storage@Internal@Windows@@YA_N_KH@Z; Windows::Internal::Storage::Cloud::IsVersionOlderThanNDays(unsigned __int64,int)
0x1801a8d02  test    al, al
0x1801a8d04  jz      short loc_1801A8D0B
0x1801a8d06  mov     sil, 1
0x1801a8d09  jmp     short loc_1801A8D0E
0x1801a8d0b  xor     sil, sil
0x1801a8d0e  test    dil, 1
0x1801a8d12  jz      short loc_1801A8D24
0x1801a8d14  and     edi, 0FFFFFFFEh
0x1801a8d17  lea     rcx, [rsp+758h+var_6B8]
0x1801a8d1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a8d24  test    sil, sil
0x1801a8d27  jz      short loc_1801A8D4B
0x1801a8d29  mov     rsi, [rsp+758h]
0x1801a8d31  lea     rcx, [rsp+758h+pszPathOut]; lpFileName
0x1801a8d39  call    cs:__imp_DeleteFileW
0x1801a8d3f  test    eax, eax
0x1801a8d41  jnz     short loc_1801A8D4B
0x1801a8d43  mov     rcx, rsi; this
0x1801a8d46  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801a8d4b  lea     rdx, [rsp+758h+FindFileData]; lpFindFileData
0x1801a8d53  mov     rcx, rbx; hFindFile
0x1801a8d56  call    cs:__imp_FindNextFileW
0x1801a8d5c  test    eax, eax
0x1801a8d5e  jnz     loc_1801A8C2D
0x1801a8d64  call    cs:__imp_GetLastError
0x1801a8d6a  cmp     eax, 12h
0x1801a8d6d  jz      loc_1801A8E06
0x1801a8d73  mov     rcx, [rsp+758h]; this
0x1801a8d7b  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a8d82  mov     edx, 0B3h; void *
0x1801a8d87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801a8d8c  mov     ebx, eax
0x1801a8d8e  lea     rcx, [rsp+758h+var_718]
0x1801a8d93  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801a8d98  nop
0x1801a8d99  lea     rcx, [rsp+758h+var_720]
0x1801a8d9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a8da3  nop
0x1801a8da4  lea     rcx, [rsp+758h+var_708]
0x1801a8da9  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801a8dae  mov     eax, ebx
0x1801a8db0  jmp     short loc_1801A8E2E
0x1801a8db2  call    cs:__imp_GetLastError
0x1801a8db8  lea     ecx, [rax-2]
0x1801a8dbb  cmp     ecx, 1
0x1801a8dbe  jbe     short loc_1801A8E06
0x1801a8dc0  test    eax, eax
0x1801a8dc2  jz      short loc_1801A8E06
0x1801a8dc4  mov     rcx, [rsp+758h]; this
0x1801a8dcc  mov     r9d, eax; char *
0x1801a8dcf  lea     r8, aOnecoreuapShel_103; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1801a8dd6  mov     edx, 0BAh; void *
0x1801a8ddb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801a8de0  mov     ebx, eax
0x1801a8de2  lea     rcx, [rsp+758h+var_718]
0x1801a8de7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801a8dec  nop
0x1801a8ded  lea     rcx, [rsp+758h+var_720]
0x1801a8df2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a8df7  nop
0x1801a8df8  lea     rcx, [rsp+758h+var_708]
0x1801a8dfd  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801a8e02  mov     eax, ebx
0x1801a8e04  jmp     short loc_1801A8E2E
0x1801a8e06  lea     rcx, [rsp+758h+var_718]
0x1801a8e0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1801a8e10  nop
0x1801a8e11  lea     rcx, [rsp+758h+var_720]
0x1801a8e16  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801a8e1b  nop
0x1801a8e1c  lea     rcx, [rsp+758h+var_708]
0x1801a8e21  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1801a8e26  xor     eax, eax
0x1801a8e28  jmp     short loc_1801A8E2E
0x1801a8e2a  mov     eax, [rsp+758h+var_728]
0x1801a8e2e  mov     rcx, [rsp+758h+var_28]
0x1801a8e36  xor     rcx, rsp; StackCookie
0x1801a8e39  call    __security_check_cookie
0x1801a8e3e  lea     r11, [rsp+758h+var_18]
0x1801a8e46  mov     rbx, [r11+30h]
0x1801a8e4a  mov     rsi, [r11+38h]
0x1801a8e4e  mov     rsp, r11
0x1801a8e51  pop     r15
0x1801a8e53  pop     r14
0x1801a8e55  pop     rdi
0x1801a8e56  retn
```
