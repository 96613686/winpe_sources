# RestoreTaskbarTask::Execute(void)

- ea: `0x18002b150`
- end: `0x18002b6d9`
- name: `?Execute@RestoreTaskbarTask@@MEAAXXZ`
- size: `1417`
- prototype: `void __fastcall(RestoreTaskbarTask *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180003e00`
- `0x180006450`
- `0x180008bbc`
- `0x18000e0f0`
- `0x18000e3bc`
- `0x18001092c`
- `0x18001094c`
- `0x180010a60`
- `0x180015e6c`
- `0x18001e55c`
- `0x18001ff9c`
- `0x180028e14`
- `0x18002941c`
- `0x18002a8a4`
- `0x18002af1c`
- `0x18002b0a0`
- `0x18002b150`
- `0x18002e5b8`
- `0x18002e6e8`
- `0x18002fa88`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002b422`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002b460`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002b49e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002b422`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002b460`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002b49e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002b52f`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18002b52f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002b57c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002b57c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002b4ea`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002b4ea`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002b3e2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002b3e2`

## string_xrefs

- `0x18002b354`: `ServiceReadWrite\PinnedToTaskbarDefaultApplist`
- `0x18002b448`: `Taskbar`
- `0x18002b1ba`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b204`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b24a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b2fe`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b372`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b3f6`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b436`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b474`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b4b2`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b5eb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`
- `0x18002b600`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\restoretaskbartask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall RestoreTaskbarTask::Execute(RestoreTaskbarTask *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int i; // r14d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, GUID *, RetailDemoUtil **); // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  int v21; // eax
  int v22; // ebx
  __int64 j; // rbx
  __int64 v24; // rdi
  HRESULT v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // eax
  HRESULT v28; // eax
  __int64 v29; // rdi
  char *FirstFileW; // rbx
  __int64 v31; // r9
  HRESULT v32; // eax
  const unsigned __int16 *v33; // rdx
  _QWORD *UserAgent; // rax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  int v42; // [rsp+20h] [rbp-E0h]
  RetailDemoUtil *v43; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v44; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  char v46; // [rsp+48h] [rbp-B8h]
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h]
  PWSTR ppszPath; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  RetailDemoUtil **v52; // [rsp+80h] [rbp-80h] BYREF
  PWSTR ppszPathOut; // [rsp+88h] [rbp-78h] BYREF
  char v54; // [rsp+90h] [rbp-70h]
  __int128 v55; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+A8h] [rbp-58h]
  char *v57; // [rsp+B0h] [rbp-50h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPathIn[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR pszPathOut[264]; // [rsp+520h] [rbp+420h] BYREF
  WCHAR FileName[264]; // [rsp+730h] [rbp+630h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+968h] [rbp+868h]

  v51 = 0;
  v3 = *((_QWORD *)this + 8);
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51, a2, a3);
  v5 = v4(v3, &v51);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v5,
      v42);
  v47 = 0;
  v8 = v51;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47, v6, v7);
  v10 = v9(v8, &v47);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v10,
      v42);
  std::vector<std::wstring>::vector<std::wstring>(&v48);
  v44 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v47 + 24LL))(v47, &v44);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v11,
      v42);
  for ( i = 0; i < v44; ++i )
  {
    v43 = 0;
    v15 = v47;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, RetailDemoUtil **))(*(_QWORD *)v47 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v12, v13);
    v17 = v16(v15, i, &GUID_368af30e_7a5f_4cca_a390_c844bb9ade09, &v43);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
        (const char *)(unsigned int)v17,
        v42);
    if ( !(*(unsigned int (__fastcall **)(RetailDemoUtil *))(*(_QWORD *)v43 + 80LL))(v43) )
    {
      v45 = 0;
      v20 = *(_QWORD *)v43;
      v52 = (RetailDemoUtil **)&v45;
      ppszPathOut = 0;
      v54 = 1;
      v21 = (*(__int64 (__fastcall **)(RetailDemoUtil *, PWSTR *))(v20 + 48))(v43, &ppszPathOut);
      v22 = v21;
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x32,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
          (const char *)(unsigned int)v21,
          v42);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v52);
      if ( v22 >= 0 )
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (__int64 *)&v48,
          &v45);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v45);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v18, v19);
  }
  RetailDemoUtil::EnumWin32AppListFromRegistry(&v55, L"ServiceReadWrite\\PinnedToTaskbarDefaultApplist");
  v24 = *((_QWORD *)&v55 + 1);
  for ( j = v55; j != v24; j += 32 )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j);
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v45);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      (__int64 *)&v48,
      &v45);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v45);
  }
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v25 = SHGetKnownFolderPath(&FOLDERID_RetailDemo, 0x5000u, 0, &ppszPath);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v25,
      v42);
  v26 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"Theme");
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v26,
      v42);
  v27 = PathCchCombine(pszPathIn, 0x104u, pszPathOut, L"Taskbar");
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v27,
      v42);
  v28 = PathCchCombine(FileName, 0x104u, pszPathIn, L"*.lnk");
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v28,
      v42);
  v29 = *((_QWORD *)&v48 + 1) - v48;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
  v57 = FirstFileW;
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      v43 = 0;
      v52 = &v43;
      ppszPathOut = 0;
      v54 = 1;
      v32 = PathAllocCombine(pszPathIn, FindFileData.cFileName, 1u, &ppszPathOut);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
          (const char *)(unsigned int)v32,
          v42);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v52);
      if ( RetailDemoUtil::IsShortcutTargetValid(v43, v33) )
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          (__int64 *)&v48,
          (__int64 *)&v43);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v43);
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  LOBYTE(v31) = v46;
  std::_Sort_unchecked_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_unsigned_short___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std::nullptr_t_________lambda_4097d04b249869b737647acae0d30411___(
    v48 + 8 * (v29 >> 3),
    *((_QWORD *)&v48 + 1),
    (*((_QWORD *)&v48 + 1) - ((__int64)v48 + 8 * (v29 >> 3))) >> 3,
    v31);
  UserAgent = (_QWORD *)RetailDemoUtil::GetUserAgent(&v45, 0);
  v35 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*UserAgent + 88LL))(
          *UserAgent,
          (__int64)(*((_QWORD *)&v48 + 1) - v48) >> 3);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\restoretaskbartask.cpp",
      (const char *)(unsigned int)v35,
      v42);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45, v36, v37);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v57);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  if ( (_QWORD)v55 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v55, *((_QWORD *)&v55 + 1));
    std::_Deallocate<16>((void *)v55, (v56 - v55) & 0xFFFFFFFFFFFFFFE0uLL);
    v55 = 0;
    v56 = 0;
  }
  if ( (_QWORD)v48 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
      v48,
      *((__int64 *)&v48 + 1));
    std::_Deallocate<16>((void *)v48, (v49 - v48) & 0xFFFFFFFFFFFFFFF8uLL);
    v48 = 0;
    v49 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47, v38, v39);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51, v40, v41);
}

```

## disassembly

```asm
0x18002b150  mov     [rsp-8+arg_8], rbx
0x18002b155  mov     [rsp-8+arg_10], rdi
0x18002b15a  push    rbp
0x18002b15b  push    r14
0x18002b15d  push    r15
0x18002b15f  lea     rbp, [rsp-850h]
0x18002b167  sub     rsp, 950h
0x18002b16e  mov     rax, cs:__security_cookie
0x18002b175  xor     rax, rsp
0x18002b178  mov     [rbp+860h+var_20], rax
0x18002b17f  xor     r15d, r15d
0x18002b182  mov     [rsp+960h+var_8E8], r15
0x18002b187  mov     rdi, [rcx+40h]
0x18002b18b  mov     rax, [rdi]
0x18002b18e  mov     rbx, [rax+60h]
0x18002b192  lea     rcx, [rsp+960h+var_8E8]
0x18002b197  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b19c  lea     rdx, [rsp+960h+var_8E8]
0x18002b1a1  mov     rcx, rdi
0x18002b1a4  mov     rax, rbx
0x18002b1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1ac  mov     rcx, [rbp+868h]; this
0x18002b1b3  test    eax, eax
0x18002b1b5  jns     short loc_18002B1CB
0x18002b1b7  mov     r9d, eax; char *
0x18002b1ba  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b1c1  lea     edx, [r15+22h]; void *
0x18002b1c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b1cb  mov     [rsp+960h+var_910], r15
0x18002b1d0  mov     rdi, [rsp+960h+var_8E8]
0x18002b1d5  mov     rax, [rdi]
0x18002b1d8  mov     rbx, [rax+58h]
0x18002b1dc  lea     rcx, [rsp+960h+var_910]
0x18002b1e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b1e6  lea     rdx, [rsp+960h+var_910]
0x18002b1eb  mov     rcx, rdi
0x18002b1ee  mov     rax, rbx
0x18002b1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b1f6  mov     rcx, [rbp+868h]; this
0x18002b1fd  test    eax, eax
0x18002b1ff  jns     short loc_18002B216
0x18002b201  mov     r9d, eax; char *
0x18002b204  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b20b  mov     edx, 24h ; '$'; void *
0x18002b210  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b216  lea     rcx, [rsp+960h+var_908]
0x18002b21b  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18002b220  nop
0x18002b221  mov     [rsp+960h+var_928], r15d
0x18002b226  mov     rcx, [rsp+960h+var_910]
0x18002b22b  mov     rax, [rcx]
0x18002b22e  lea     rdx, [rsp+960h+var_928]
0x18002b233  mov     rax, [rax+18h]
0x18002b237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b23c  mov     rcx, [rbp+868h]; this
0x18002b243  test    eax, eax
0x18002b245  jns     short loc_18002B25C
0x18002b247  mov     r9d, eax; char *
0x18002b24a  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b251  mov     edx, 28h ; '('; void *
0x18002b256  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b25c  mov     r14d, r15d
0x18002b25f  cmp     [rsp+960h+var_928], r15d
0x18002b264  jbe     loc_18002B354
0x18002b26a  mov     [rsp+960h+var_930], r15
0x18002b26f  mov     rdi, [rsp+960h+var_910]
0x18002b274  mov     rax, [rdi]
0x18002b277  mov     rbx, [rax+20h]
0x18002b27b  lea     rcx, [rsp+960h+var_930]
0x18002b280  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b285  lea     r9, [rsp+960h+var_930]
0x18002b28a  lea     r8, _GUID_368af30e_7a5f_4cca_a390_c844bb9ade09
0x18002b291  mov     edx, r14d
0x18002b294  mov     rcx, rdi
0x18002b297  mov     rax, rbx
0x18002b29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b29f  mov     rcx, [rbp+868h]; this
0x18002b2a6  test    eax, eax
0x18002b2a8  js      loc_18002B36F
0x18002b2ae  mov     rcx, [rsp+960h+var_930]
0x18002b2b3  mov     rax, [rcx]
0x18002b2b6  mov     rax, [rax+50h]
0x18002b2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2bf  test    eax, eax
0x18002b2c1  jnz     short loc_18002B33C
0x18002b2c3  mov     [rsp+960h+var_920], r15
0x18002b2c8  mov     rcx, [rsp+960h+var_930]
0x18002b2cd  mov     rax, [rcx]
0x18002b2d0  lea     rdx, [rsp+960h+var_920]
0x18002b2d5  mov     [rbp+860h+var_8E0], rdx
0x18002b2d9  mov     [rbp+860h+ppszPathOut], r15
0x18002b2dd  mov     [rbp+860h+var_8D0], 1
0x18002b2e1  lea     rdx, [rbp+860h+ppszPathOut]
0x18002b2e5  mov     rax, [rax+30h]
0x18002b2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2ee  mov     ebx, eax
0x18002b2f0  mov     rcx, [rbp+868h]; this
0x18002b2f7  test    eax, eax
0x18002b2f9  jns     short loc_18002B310
0x18002b2fb  mov     r9d, eax; char *
0x18002b2fe  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b305  mov     edx, 32h ; '2'; void *
0x18002b30a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b30f  nop
0x18002b310  lea     rcx, [rbp+860h+var_8E0]
0x18002b314  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002b319  shr     ebx, 1Fh
0x18002b31c  xor     bl, 1
0x18002b31f  jz      short loc_18002B331
0x18002b321  lea     rdx, [rsp+960h+var_920]
0x18002b326  lea     rcx, [rsp+960h+var_908]
0x18002b32b  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002b330  nop
0x18002b331  lea     rcx, [rsp+960h+var_920]
0x18002b336  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b33b  nop
0x18002b33c  lea     rcx, [rsp+960h+var_930]
0x18002b341  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b346  inc     r14d
0x18002b349  cmp     r14d, [rsp+960h+var_928]
0x18002b34e  jb      loc_18002B26A
0x18002b354  lea     rdx, ?c_retailDemoKeyPinnedToTaskbarDefaultApplistSubKey@@3QBGB; "ServiceReadWrite\\PinnedToTaskbarDefaul"...
0x18002b35b  lea     rcx, [rbp+860h+var_8C8]
0x18002b35f  call    ?EnumWin32AppListFromRegistry@RetailDemoUtil@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; RetailDemoUtil::EnumWin32AppListFromRegistry(ushort const *)
0x18002b364  nop
0x18002b365  mov     rbx, qword ptr [rbp+860h+var_8C8]
0x18002b369  mov     rdi, qword ptr [rbp+860h+var_8C8+8]
0x18002b36d  jmp     short loc_18002B3B8
0x18002b36f  mov     r9d, eax; char *
0x18002b372  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b379  mov     edx, 2Ch ; ','; void *
0x18002b37e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b384  mov     rcx, rbx
0x18002b387  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b38c  mov     rdx, rax
0x18002b38f  lea     rcx, [rsp+960h+var_920]
0x18002b394  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002b399  nop
0x18002b39a  lea     rdx, [rsp+960h+var_920]
0x18002b39f  lea     rcx, [rsp+960h+var_908]
0x18002b3a4  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002b3a9  nop
0x18002b3aa  lea     rcx, [rsp+960h+var_920]
0x18002b3af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b3b4  add     rbx, 20h ; ' '
0x18002b3b8  cmp     rbx, rdi
0x18002b3bb  jnz     short loc_18002B384
0x18002b3bd  mov     [rsp+960h+ppszPath], r15
0x18002b3c2  xor     edx, edx
0x18002b3c4  lea     rcx, [rsp+960h+ppszPath]
0x18002b3c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002b3ce  lea     r9, [rsp+960h+ppszPath]; ppszPath
0x18002b3d3  xor     r8d, r8d; hToken
0x18002b3d6  mov     edx, 5000h; dwFlags
0x18002b3db  lea     rcx, FOLDERID_RetailDemo; rfid
0x18002b3e2  call    cs:__imp_SHGetKnownFolderPath
0x18002b3e8  mov     rcx, [rbp+868h]; this
0x18002b3ef  test    eax, eax
0x18002b3f1  jns     short loc_18002B408
0x18002b3f3  mov     r9d, eax; char *
0x18002b3f6  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b3fd  mov     edx, 41h ; 'A'; void *
0x18002b402  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b408  lea     r9, aTheme; "Theme"
0x18002b40f  mov     r8, [rsp+960h+ppszPath]; pszPathIn
0x18002b414  mov     ebx, 104h
0x18002b419  mov     edx, ebx; cchPathOut
0x18002b41b  lea     rcx, [rbp+860h+pszPathOut]; pszPathOut
0x18002b422  call    cs:__imp_PathCchCombine
0x18002b428  mov     rcx, [rbp+868h]; this
0x18002b42f  test    eax, eax
0x18002b431  jns     short loc_18002B448
0x18002b433  mov     r9d, eax; char *
0x18002b436  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b43d  mov     edx, 43h ; 'C'; void *
0x18002b442  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b448  lea     r9, aTaskbar; "Taskbar"
0x18002b44f  lea     r8, [rbp+860h+pszPathOut]; pszPathIn
0x18002b456  mov     rdx, rbx; cchPathOut
0x18002b459  lea     rcx, [rbp+860h+pszPathIn]; pszPathOut
0x18002b460  call    cs:__imp_PathCchCombine
0x18002b466  mov     rcx, [rbp+868h]; this
0x18002b46d  test    eax, eax
0x18002b46f  jns     short loc_18002B486
0x18002b471  mov     r9d, eax; char *
0x18002b474  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b47b  mov     edx, 45h ; 'E'; void *
0x18002b480  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b486  lea     r9, aLnk; "*.lnk"
0x18002b48d  lea     r8, [rbp+860h+pszPathIn]; pszPathIn
0x18002b494  mov     rdx, rbx; cchPathOut
0x18002b497  lea     rcx, [rbp+860h+FileName]; pszPathOut
0x18002b49e  call    cs:__imp_PathCchCombine
0x18002b4a4  mov     rcx, [rbp+868h]; this
0x18002b4ab  test    eax, eax
0x18002b4ad  jns     short loc_18002B4C4
0x18002b4af  mov     r9d, eax; char *
0x18002b4b2  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b4b9  mov     edx, 47h ; 'G'; void *
0x18002b4be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b4c4  mov     rdi, qword ptr [rsp+960h+var_908+8]
0x18002b4c9  sub     rdi, qword ptr [rsp+960h+var_908]
0x18002b4ce  xor     edx, edx; Val
0x18002b4d0  mov     r8d, 250h; Size
0x18002b4d6  lea     rcx, [rbp+860h+FindFileData]; void *
0x18002b4da  call    memset_0
0x18002b4df  lea     rdx, [rbp+860h+FindFileData]; lpFindFileData
0x18002b4e3  lea     rcx, [rbp+860h+FileName]; lpFileName
0x18002b4ea  call    cs:__imp_FindFirstFileW
0x18002b4f0  mov     rbx, rax
0x18002b4f3  mov     [rbp+860h+var_8B0], rax
0x18002b4f7  dec     rax
0x18002b4fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002b4fe  ja      loc_18002B58A
0x18002b504  mov     [rsp+960h+var_930], r15
0x18002b509  lea     rax, [rsp+960h+var_930]
0x18002b50e  mov     [rbp+860h+var_8E0], rax
0x18002b512  mov     [rbp+860h+ppszPathOut], r15
0x18002b516  mov     [rbp+860h+var_8D0], 1
0x18002b51a  lea     r9, [rbp+860h+ppszPathOut]; ppszPathOut
0x18002b51e  mov     r8d, 1; dwFlags
0x18002b524  lea     rdx, [rbp+860h+FindFileData.cFileName]; pszMore
0x18002b528  lea     rcx, [rbp+860h+pszPathIn]; pszPathIn
0x18002b52f  call    cs:__imp_PathAllocCombine
0x18002b535  mov     rcx, [rbp+868h]; this
0x18002b53c  test    eax, eax
0x18002b53e  js      loc_18002B5FD
0x18002b544  lea     rcx, [rbp+860h+var_8E0]
0x18002b548  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002b54d  mov     rcx, [rsp+960h+var_930]; this
0x18002b552  call    ?IsShortcutTargetValid@RetailDemoUtil@@YA_NPEBG@Z; RetailDemoUtil::IsShortcutTargetValid(ushort const *)
0x18002b557  test    al, al
0x18002b559  jz      short loc_18002B56B
0x18002b55b  lea     rdx, [rsp+960h+var_930]
0x18002b560  lea     rcx, [rsp+960h+var_908]
0x18002b565  call    ??$emplace_back@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::emplace_back<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002b56a  nop
0x18002b56b  lea     rcx, [rsp+960h+var_930]
0x18002b570  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b575  lea     rdx, [rbp+860h+FindFileData]; lpFindFileData
0x18002b579  mov     rcx, rbx; hFindFile
0x18002b57c  call    cs:__imp_FindNextFileW
0x18002b582  test    eax, eax
0x18002b584  jnz     loc_18002B504
0x18002b58a  mov     rdx, qword ptr [rsp+960h+var_908+8]
0x18002b58f  sar     rdi, 3
0x18002b593  mov     rax, qword ptr [rsp+960h+var_908]
0x18002b598  lea     rcx, [rax+rdi*8]
0x18002b59c  mov     r8, rdx
0x18002b59f  sub     r8, rcx
0x18002b5a2  sar     r8, 3
0x18002b5a6  mov     r9b, [rsp+960h+var_918]
0x18002b5ab  call    std___Sort_unchecked_wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_unsigned_short___void____cdecl___void_____CoTaskMemFree_wistd__integral_constant_unsigned___int64_0__unsigned_short___unsigned_short___0_std__nullptr_t_________lambda_4097d04b249869b737647acae0d30411___
0x18002b5b0  xor     edx, edx
0x18002b5b2  lea     rcx, [rsp+960h+var_920]
0x18002b5b7  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x18002b5bc  nop
0x18002b5bd  mov     rcx, [rax]
0x18002b5c0  mov     r8, qword ptr [rsp+960h+var_908]
0x18002b5c5  mov     rax, [rcx]
0x18002b5c8  mov     rdx, qword ptr [rsp+960h+var_908+8]
0x18002b5cd  sub     rdx, r8
0x18002b5d0  sar     rdx, 3
0x18002b5d4  mov     rax, [rax+58h]
0x18002b5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5dd  mov     rcx, [rbp+868h]; this
0x18002b5e4  test    eax, eax
0x18002b5e6  jns     short loc_18002B612
0x18002b5e8  mov     r9d, eax; char *
0x18002b5eb  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b5f2  mov     edx, 63h ; 'c'; void *
0x18002b5f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b5fd  mov     r9d, eax; char *
0x18002b600  lea     r8, aPcshellShellRe_20; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002b607  mov     edx, 53h ; 'S'; void *
0x18002b60c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b612  lea     rcx, [rsp+960h+var_920]
0x18002b617  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b61c  nop
0x18002b61d  lea     rcx, [rbp+860h+var_8B0]
0x18002b621  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18002b626  nop
0x18002b627  lea     rcx, [rsp+960h+ppszPath]
0x18002b62c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002b631  nop
0x18002b632  mov     rcx, qword ptr [rbp+860h+var_8C8]
0x18002b636  test    rcx, rcx
0x18002b639  jz      short loc_18002B664
0x18002b63b  mov     rdx, qword ptr [rbp+860h+var_8C8+8]
0x18002b63f  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002b644  mov     rcx, qword ptr [rbp+860h+var_8C8]
0x18002b648  mov     rdx, [rbp+860h+var_8B8]
0x18002b64c  sub     rdx, rcx
0x18002b64f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002b653  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002b658  xorps   xmm0, xmm0
0x18002b65b  movdqu  [rbp+860h+var_8C8], xmm0
0x18002b660  mov     [rbp+860h+var_8B8], r15
0x18002b664  mov     rcx, qword ptr [rsp+960h+var_908]
0x18002b669  test    rcx, rcx
  ... truncated ...
```
