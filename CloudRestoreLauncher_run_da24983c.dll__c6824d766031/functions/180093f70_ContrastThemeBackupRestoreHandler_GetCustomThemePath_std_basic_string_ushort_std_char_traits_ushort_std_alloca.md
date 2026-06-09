# ContrastThemeBackupRestoreHandler::GetCustomThemePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180093f70`
- end: `0x180094116`
- name: `?GetCustomThemePath@ContrastThemeBackupRestoreHandler@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z`
- size: `422`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180093624`

## callees

- `0x18000c6e0`
- `0x18000fda0`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001faa8`
- `0x180091ae8`
- `0x18009256c`
- `0x180092700`
- `0x180093f70`
- `0x1800972b4`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180094000`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180094000`
- `SHELL32!SHGetKnownFolderPath` at `0x180093fd1`
- `SHELL32!SHGetKnownFolderPath` at `0x180093fd1`
- `SHELL32!__imp_SHCreateDirectory` at `0x180094018`
- `SHELL32!__imp_SHCreateDirectory` at `0x180094018`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ContrastThemeBackupRestoreHandler::GetCustomThemePath(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT v5; // eax
  HRESULT v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned int v12; // eax
  PWSTR ppszPathOut; // [rsp+20h] [rbp-40h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-38h] BYREF
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v16[3]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v16[0] = a2;
  v16[2] = a3;
  ppszPath = 0;
  ppszPathOut = 0;
  v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v5 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
      (const char *)(unsigned int)v5,
      (int)ppszPathOut);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v6 = PathAllocCombine(ppszPath, L"Microsoft\\Windows\\Themes", 0, &ppszPathOut);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
      (const char *)(unsigned int)v6,
      (int)ppszPathOut);
  v7 = SHCreateDirectory(0, ppszPathOut);
  v8 = (unsigned int)v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( (int)(v8 + 0x80000000) >= 0 && (_DWORD)v8 != -2147024713 )
  {
    v12 = wil::verify_hresult<long>(v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x219,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\contrastthemebackuprestorehandler.cpp",
      (const char *)v12,
      (int)ppszPathOut);
  }
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v10 = wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          v16,
          L"%s\\%s.theme",
          ppszPathOut,
          v9);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v15,
    v10);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v16);
  std::wstring::wstring(a2, v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
  std::wstring::_Tidy_deallocate(a3);
  return a2;
}

```

## disassembly

```asm
0x180093f70  mov     [rsp-8+arg_0], rbx
0x180093f75  mov     [rsp-8+arg_18], rdi
0x180093f7a  push    rbp
0x180093f7b  mov     rbp, rsp
0x180093f7e  sub     rsp, 60h
0x180093f82  mov     rax, cs:__security_cookie
0x180093f89  xor     rax, rsp
0x180093f8c  mov     [rbp+var_10], rax
0x180093f90  mov     rdi, r8
0x180093f93  mov     rbx, rdx
0x180093f96  mov     [rbp+var_28], rdx
0x180093f9a  mov     [rbp+var_18], r8
0x180093f9e  mov     [rbp+ppszPath], 0
0x180093fa6  mov     [rbp+ppszPathOut], 0
0x180093fae  mov     [rbp+var_30], 0
0x180093fb6  xor     edx, edx
0x180093fb8  lea     rcx, [rbp+ppszPath]
0x180093fbc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180093fc1  lea     r9, [rbp+ppszPath]; ppszPath
0x180093fc5  xor     r8d, r8d; hToken
0x180093fc8  xor     edx, edx; dwFlags
0x180093fca  lea     rcx, FOLDERID_LocalAppData; rfid
0x180093fd1  call    cs:__imp_SHGetKnownFolderPath
0x180093fd7  mov     rcx, [rbp+8]; this
0x180093fdb  test    eax, eax
0x180093fdd  js      loc_1800940EC
0x180093fe3  xor     edx, edx
0x180093fe5  lea     rcx, [rbp+ppszPathOut]
0x180093fe9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180093fee  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180093ff2  xor     r8d, r8d; dwFlags
0x180093ff5  lea     rdx, pszMore; "Microsoft\\Windows\\Themes"
0x180093ffc  mov     rcx, [rbp+ppszPath]; pszPathIn
0x180094000  call    cs:__imp_PathAllocCombine
0x180094006  mov     rcx, [rbp+8]; this
0x18009400a  test    eax, eax
0x18009400c  js      loc_180094101
0x180094012  mov     rdx, [rbp+ppszPathOut]; pszPath
0x180094016  xor     ecx, ecx; hwnd
0x180094018  call    cs:__imp_SHCreateDirectory
0x18009401e  mov     ecx, eax
0x180094020  test    eax, eax
0x180094022  jle     short loc_18009402D
0x180094024  movzx   ecx, ax
0x180094027  or      ecx, 80070000h
0x18009402d  mov     edx, 80000000h
0x180094032  lea     eax, [rcx+rdx]
0x180094035  test    edx, eax
0x180094037  jnz     short loc_180094045
0x180094039  cmp     ecx, 800700B7h
0x18009403f  jnz     loc_1800940CD
0x180094045  mov     rcx, rdi
0x180094048  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009404d  mov     r9, rax
0x180094050  mov     r8, [rbp+ppszPathOut]
0x180094054  lea     rdx, aSSTheme; "%s\\%s.theme"
0x18009405b  lea     rcx, [rbp+var_28]
0x18009405f  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180094064  mov     rdx, rax
0x180094067  lea     rcx, [rbp+var_30]
0x18009406b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180094070  lea     rcx, [rbp+var_28]
0x180094074  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180094079  mov     rdx, [rbp+var_30]
0x18009407d  mov     rcx, rbx
0x180094080  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180094085  nop
0x180094086  lea     rcx, [rbp+var_30]
0x18009408a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009408f  nop
0x180094090  lea     rcx, [rbp+ppszPathOut]
0x180094094  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180094099  nop
0x18009409a  lea     rcx, [rbp+ppszPath]
0x18009409e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800940a3  nop
0x1800940a4  mov     rcx, rdi
0x1800940a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800940ac  mov     rax, rbx
0x1800940af  mov     rcx, [rbp+var_10]
0x1800940b3  xor     rcx, rsp; StackCookie
0x1800940b6  call    __security_check_cookie
0x1800940bb  lea     r11, [rsp+60h+var_s0]
0x1800940c0  mov     rbx, [r11+10h]
0x1800940c4  mov     rdi, [r11+28h]
0x1800940c8  mov     rsp, r11
0x1800940cb  pop     rbp
0x1800940cc  retn
0x1800940cd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800940d2  nop
0x1800940d3  mov     r9d, eax; char *
0x1800940d6  mov     rcx, [rbp+8]; this
0x1800940da  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800940e1  mov     edx, 219h; void *
0x1800940e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800940ec  mov     r9d, eax; char *
0x1800940ef  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800940f6  mov     edx, 20Ch; void *
0x1800940fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094101  mov     r9d, eax; char *
0x180094104  lea     r8, aPcshellShellCl_28; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x18009410b  mov     edx, 20Eh; void *
0x180094110  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
