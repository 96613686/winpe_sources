# SetWallpaperTask::Execute(void)

- ea: `0x18002c2f0`
- end: `0x18002c5e2`
- name: `?Execute@SetWallpaperTask@@MEAAXXZ`
- size: `754`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x180024a48`
- `0x18002c020`
- `0x18002c2f0`
- `0x18002c610`
- `0x18002fc68`
- `0x180050010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x18002c474`
- `SHLWAPI!PathFileExistsW` at `0x18002c4bd`
- `SHLWAPI!PathFileExistsW` at `0x18002c474`
- `SHLWAPI!PathFileExistsW` at `0x18002c4bd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c40f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002c40f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c3d8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c44a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c493`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c3d8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c44a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002c493`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002c39b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002c39b`

## string_xrefs

- `0x18002c349`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c3af`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c3ec`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c423`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c45e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c4a7`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c55b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`
- `0x18002c597`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\setwallpapertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SetWallpaperTask::Execute(HSTRING *this)
{
  int v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  HRESULT v6; // eax
  HRESULT v7; // eax
  __int64 (__fastcall ***v8)(); // rdx
  int v9; // eax
  int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+24h] [rbp-DCh] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v15[16]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall **v16)(); // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+48h] [rbp-B8h]
  __int64 (__fastcall ***v18)(); // [rsp+78h] [rbp-88h]
  HSTRING pszPath[66]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszPathOut[264]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v13 = 0;
  v2 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)this[8] + 40LL))(this[8], &v13);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
      (const char *)(unsigned int)v2,
      v12);
  if ( (v13 & 2) == 0 || (unsigned __int8)TaskBase<void,0,0,12>::IsContentTypeAvailable(this) )
  {
    ppszPath = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &ppszPath,
      0);
    v3 = SHGetKnownFolderPath(&FOLDERID_RetailDemo, 0x5000u, 0, &ppszPath);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
        (const char *)(unsigned int)v3,
        v12);
    v4 = PathCchCombine(pszPathOut, 0x104u, ppszPath, (PCWSTR)this[10]);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
        (const char *)(unsigned int)v4,
        v12);
    v5 = PathCchAppend(pszPathOut, 0x104u, L"Wallpaper");
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
        (const char *)(unsigned int)v5,
        v12);
    v6 = PathCchCombine((PWSTR)pszPath, 0x104u, pszPathOut, L"wallpaper.jpg");
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
        (const char *)(unsigned int)v6,
        v12);
    if ( !PathFileExistsW((LPCWSTR)pszPath) )
    {
      v7 = PathCchCombine((PWSTR)pszPath, 0x104u, pszPathOut, L"wallpaper_old.jpg");
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
          (const char *)(unsigned int)v7,
          v12);
    }
    if ( PathFileExistsW((LPCWSTR)pszPath) )
    {
      *((_BYTE *)this + 88) = 1;
      v18 = 0;
      v16 = off_180052FE0;
      v17 = *(_OWORD *)_lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(
                         (_lambda_6d98a26ab645bb601d6c6842c9556ef9_ *)v15,
                         this,
                         pszPath);
      v18 = &v16;
      RetailDemoUtil::ExecuteAsDemoUser(&v16);
      if ( v18 )
      {
        v8 = &v16;
        LOBYTE(v8) = v18 != &v16;
        ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v18)[4])(v18, v8);
      }
    }
    v12 = 0;
    v9 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)this[8] + 64LL))(this[8], &v12);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
        (const char *)(unsigned int)v9,
        v12);
    v12 &= ~0x4000u;
    v10 = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)this[8] + 72LL))(this[8]);
    v11 = retaddr;
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\setwallpapertask.cpp",
        (const char *)(unsigned int)v10,
        v12);
    LOBYTE(v11) = *((_BYTE *)this + 88);
    RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<13,bool,long>(v11, 0);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  }
}

```

## disassembly

```asm
0x18002c2f0  mov     [rsp-8+arg_8], rbx
0x18002c2f5  mov     [rsp-8+arg_10], rsi
0x18002c2fa  push    rbp
0x18002c2fb  lea     rbp, [rsp-3B0h]
0x18002c303  sub     rsp, 4B0h
0x18002c30a  mov     rax, cs:__security_cookie
0x18002c311  xor     rax, rsp
0x18002c314  mov     [rbp+3B0h+var_10], rax
0x18002c31b  mov     rbx, rcx
0x18002c31e  mov     [rsp+4B0h+var_48C], 0
0x18002c326  mov     rcx, [rcx+40h]
0x18002c32a  mov     rax, [rcx]
0x18002c32d  lea     rdx, [rsp+4B0h+var_48C]
0x18002c332  mov     rax, [rax+28h]
0x18002c336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c33b  mov     rcx, [rbp+3B8h]; this
0x18002c342  test    eax, eax
0x18002c344  jns     short loc_18002C35B
0x18002c346  mov     r9d, eax; char *
0x18002c349  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c350  mov     edx, 2Dh ; '-'; void *
0x18002c355  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c35b  test    byte ptr [rsp+4B0h+var_48C], 2
0x18002c360  jz      short loc_18002C372
0x18002c362  mov     rcx, rbx
0x18002c365  call    ?IsContentTypeAvailable@?$TaskBase@X$0A@$0A@$0M@@@IEAA_NW4ProvisioningContentType@@@Z; TaskBase<void,0,0,12>::IsContentTypeAvailable(ProvisioningContentType)
0x18002c36a  test    al, al
0x18002c36c  jz      loc_18002C5BE
0x18002c372  mov     [rsp+4B0h+ppszPath], 0
0x18002c37b  xor     edx, edx
0x18002c37d  lea     rcx, [rsp+4B0h+ppszPath]
0x18002c382  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18002c387  lea     r9, [rsp+4B0h+ppszPath]; ppszPath
0x18002c38c  xor     r8d, r8d; hToken
0x18002c38f  mov     edx, 5000h; dwFlags
0x18002c394  lea     rcx, FOLDERID_RetailDemo; rfid
0x18002c39b  call    cs:__imp_SHGetKnownFolderPath
0x18002c3a1  mov     rcx, [rbp+3B8h]; this
0x18002c3a8  test    eax, eax
0x18002c3aa  jns     short loc_18002C3C1
0x18002c3ac  mov     r9d, eax; char *
0x18002c3af  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c3b6  mov     edx, 34h ; '4'; void *
0x18002c3bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c3c1  mov     r9, [rbx+50h]; pszMore
0x18002c3c5  mov     r8, [rsp+4B0h+ppszPath]; pszPathIn
0x18002c3ca  mov     esi, 104h
0x18002c3cf  mov     edx, esi; cchPathOut
0x18002c3d1  lea     rcx, [rbp+3B0h+pszPathOut]; pszPathOut
0x18002c3d8  call    cs:__imp_PathCchCombine
0x18002c3de  mov     rcx, [rbp+3B8h]; this
0x18002c3e5  test    eax, eax
0x18002c3e7  jns     short loc_18002C3FE
0x18002c3e9  mov     r9d, eax; char *
0x18002c3ec  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c3f3  mov     edx, 36h ; '6'; void *
0x18002c3f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c3fe  lea     r8, aWallpaper; "Wallpaper"
0x18002c405  mov     rdx, rsi; cchPath
0x18002c408  lea     rcx, [rbp+3B0h+pszPathOut]; pszPath
0x18002c40f  call    cs:__imp_PathCchAppend
0x18002c415  mov     rcx, [rbp+3B8h]; this
0x18002c41c  test    eax, eax
0x18002c41e  jns     short loc_18002C435
0x18002c420  mov     r9d, eax; char *
0x18002c423  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c42a  mov     edx, 37h ; '7'; void *
0x18002c42f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c435  lea     r9, aWallpaperJpg; "wallpaper.jpg"
0x18002c43c  lea     r8, [rbp+3B0h+pszPathOut]; pszPathIn
0x18002c443  mov     rdx, rsi; cchPathOut
0x18002c446  lea     rcx, [rbp+3B0h+pszPath]; pszPathOut
0x18002c44a  call    cs:__imp_PathCchCombine
0x18002c450  mov     rcx, [rbp+3B8h]; this
0x18002c457  test    eax, eax
0x18002c459  jns     short loc_18002C470
0x18002c45b  mov     r9d, eax; char *
0x18002c45e  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c465  mov     edx, 39h ; '9'; void *
0x18002c46a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c470  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x18002c474  call    cs:__imp_PathFileExistsW
0x18002c47a  test    eax, eax
0x18002c47c  jnz     short loc_18002C4B9
0x18002c47e  lea     r9, aWallpaperOldJp; "wallpaper_old.jpg"
0x18002c485  lea     r8, [rbp+3B0h+pszPathOut]; pszPathIn
0x18002c48c  mov     rdx, rsi; cchPathOut
0x18002c48f  lea     rcx, [rbp+3B0h+pszPath]; pszPathOut
0x18002c493  call    cs:__imp_PathCchCombine
0x18002c499  mov     rcx, [rbp+3B8h]; this
0x18002c4a0  test    eax, eax
0x18002c4a2  jns     short loc_18002C4B9
0x18002c4a4  mov     r9d, eax; char *
0x18002c4a7  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c4ae  mov     edx, 3Eh ; '>'; void *
0x18002c4b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c4b9  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x18002c4bd  call    cs:__imp_PathFileExistsW
0x18002c4c3  test    eax, eax
0x18002c4c5  jz      short loc_18002C530
0x18002c4c7  mov     byte ptr [rbx+58h], 1
0x18002c4cb  mov     [rsp+4B0h+var_438], 0
0x18002c4d4  lea     rax, off_180052FE0
0x18002c4db  mov     [rsp+4B0h+var_470], rax
0x18002c4e0  lea     r8, [rbp+3B0h+pszPath]; HSTRING *
0x18002c4e4  mov     rdx, rbx; HSTRING *
0x18002c4e7  lea     rcx, [rsp+4B0h+var_480]; this
0x18002c4ec  call    ??0_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@QEAA@AEAPEAUHSTRING__@@0@Z; _lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(HSTRING__ * &,HSTRING__ * &)
0x18002c4f1  movups  xmm0, xmmword ptr [rax]
0x18002c4f4  movdqu  [rsp+4B0h+var_468], xmm0
0x18002c4fa  lea     rax, [rsp+4B0h+var_470]
0x18002c4ff  mov     [rsp+4B0h+var_438], rax
0x18002c504  lea     rcx, [rsp+4B0h+var_470]
0x18002c509  call    ?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z; RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)
0x18002c50e  nop
0x18002c50f  mov     rcx, [rsp+4B0h+var_438]
0x18002c514  test    rcx, rcx
0x18002c517  jz      short loc_18002C530
0x18002c519  mov     rax, [rcx]
0x18002c51c  lea     rdx, [rsp+4B0h+var_470]
0x18002c521  cmp     rcx, rdx
0x18002c524  setnz   dl
0x18002c527  mov     rax, [rax+20h]
0x18002c52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c530  mov     [rsp+4B0h+var_490], 0; int
0x18002c538  mov     rcx, [rbx+40h]
0x18002c53c  mov     rax, [rcx]
0x18002c53f  lea     rdx, [rsp+4B0h+var_490]
0x18002c544  mov     rax, [rax+40h]
0x18002c548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c54d  mov     rcx, [rbp+3B8h]; this
0x18002c554  test    eax, eax
0x18002c556  jns     short loc_18002C56D
0x18002c558  mov     r9d, eax; char *
0x18002c55b  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c562  mov     edx, 56h ; 'V'; void *
0x18002c567  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c56d  mov     edx, [rsp+4B0h+var_490]
0x18002c571  btr     edx, 0Eh
0x18002c575  mov     [rsp+4B0h+var_490], edx; int
0x18002c579  mov     rcx, [rbx+40h]
0x18002c57d  mov     rax, [rcx]
0x18002c580  mov     rax, [rax+48h]
0x18002c584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c589  mov     rcx, [rbp+3B8h]; this
0x18002c590  test    eax, eax
0x18002c592  jns     short loc_18002C5A9
0x18002c594  mov     r9d, eax; char *
0x18002c597  lea     r8, aPcshellShellRe_36; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002c59e  mov     edx, 58h ; 'X'; void *
0x18002c5a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c5a9  xor     edx, edx
0x18002c5ab  mov     cl, [rbx+58h]
0x18002c5ae  call    ??$HandleEvent@$0N@_NJ@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@SAX_NJ@Z; RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<13,bool,long>(bool,long)
0x18002c5b3  nop
0x18002c5b4  lea     rcx, [rsp+4B0h+ppszPath]
0x18002c5b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002c5be  mov     rcx, [rbp+3B0h+var_10]
0x18002c5c5  xor     rcx, rsp; StackCookie
0x18002c5c8  call    __security_check_cookie
0x18002c5cd  lea     r11, [rsp+4B0h+var_s0]
0x18002c5d5  mov     rbx, [r11+18h]
0x18002c5d9  mov     rsi, [r11+20h]
0x18002c5dd  mov     rsp, r11
0x18002c5e0  pop     rbp
0x18002c5e1  retn
```
