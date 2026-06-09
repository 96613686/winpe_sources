# OneDriveUtils::CopyToPictures(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800aa010`
- end: `0x1800aa3e1`
- name: `?CopyToPictures@OneDriveUtils@@YA?AV?$com_ptr_t@UIShellItem2@@Uerr_exception_policy@wil@@@wil@@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `977`
- prototype: `void **__fastcall(void **ppv, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a96f0`
- `0x1800bca00`

## callees

- `0x18000c6e0`
- `0x180015668`
- `0x18001666c`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001da4c`
- `0x18001faa8`
- `0x180036b18`
- `0x180066ce8`
- `0x18008d374`
- `0x18009cbec`
- `0x18009defc`
- `0x1800a235c`
- `0x1800a23c8`
- `0x1800a3dc8`
- `0x1800a4074`
- `0x1800a442c`
- `0x1800a5f44`
- `0x1800aa010`
- `0x1800aca2c`
- `0x1800ad734`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800aa2c5`
- `KERNEL32!CompareStringOrdinal` at `0x1800aa2c5`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800aa180`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800aa281`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800aa180`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800aa281`
- `SHELL32!SHGetKnownFolderPath` at `0x1800aa077`
- `SHELL32!SHGetKnownFolderPath` at `0x1800aa077`

## string_xrefs

- `0x1800aa302`: `BackedUpLockscreenPath`
- `0x1800aa2de`: `BackedUpWallpaperPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void **__fastcall OneDriveUtils::CopyToPictures(void **ppv, const WCHAR *a2, __int64 a3)
{
  HRESULT v6; // eax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  const struct std::filesystem::path *v10; // rdx
  bool v11; // bl
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // r8
  void *v14; // rcx
  const WCHAR *v15; // rax
  HRESULT v16; // eax
  __int64 v17; // rax
  __int64 NewFileName; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  void *v21; // rcx
  const WCHAR *v22; // rax
  HRESULT v23; // eax
  const WCHAR *v24; // rax
  HKEY v25; // rcx
  const unsigned __int16 *v26; // r9
  int v27; // edx
  int v28; // eax
  int v29; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  void **v34; // [rsp+38h] [rbp-C8h] BYREF
  int v35; // [rsp+40h] [rbp-C0h]
  void **v36; // [rsp+48h] [rbp-B8h]
  __int64 v37; // [rsp+58h] [rbp-A8h]
  _BYTE v38[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v40[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v41[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v43[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v44[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v45[32]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v36 = ppv;
  v34 = (void **)a2;
  v37 = a3;
  v35 = 1;
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v6 = SHGetKnownFolderPath(&FOLDERID_Pictures, 0, 0, &ppszPath);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  std::filesystem::path::path(v42, &v34, v7);
  std::wstring::wstring(v41, ppszPath);
  *ppv = 0;
  v35 = 1;
  v8 = std::filesystem::path::filename(v42, v38);
  std::filesystem::path::wstring(v8, v40);
  std::wstring::_Tidy_deallocate(v38);
  v9 = std::operator+<unsigned short>(v45, v41);
  std::operator+<unsigned short>(v39, v9, v40);
  std::wstring::_Tidy_deallocate(v45);
  std::filesystem::path::path(v38, v39);
  v11 = std::filesystem::exists((std::filesystem *)v38, v10);
  std::wstring::_Tidy_deallocate(v38);
  if ( v11 )
  {
    v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
    if ( OneDriveUtils::IsFileIdentical(a2, v12, v13) )
    {
      v14 = *ppv;
      *ppv = 0;
      if ( v14 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
      v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
      v16 = SHCreateItemFromParsingName(v15, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, ppv);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x113,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
          (const char *)(unsigned int)v16,
          bIgnoreCase);
      goto LABEL_16;
    }
    v34 = (void **)v38;
    std::wstring::wstring(v38, v42);
    v17 = std::wstring::wstring(v43, v41);
    NewFileName = OneDriveUtils::GetNewFileName(v44, v17, v38);
    std::wstring::operator=(v40, NewFileName);
    std::wstring::_Tidy_deallocate(v44);
    v19 = std::operator+<unsigned short>(v43, v41);
    v20 = std::operator+<unsigned short>(v44, v19, v40);
    std::wstring::operator=(v39, v20);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v43);
  }
  std::filesystem::path::path(v38, v39);
  std::filesystem::copy_file(v42, v38);
  std::wstring::_Tidy_deallocate(v38);
  v21 = *ppv;
  *ppv = 0;
  if ( v21 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
  v23 = SHCreateItemFromParsingName(v22, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, ppv);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
      (const char *)(unsigned int)v23,
      bIgnoreCase);
  v34 = ppv;
  OneDriveUtils::RetryUntilTimeout<_lambda_12430c30872bdfb0bc16aa7ecb3cd60e_>(retaddr, &v34);
  v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  CompareStringOrdinal(v24, -1, L"Background", -1, 1);
  v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
  if ( v27 == 2 )
  {
    v28 = SHRegSetString(
            v25,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
            L"BackedUpWallpaperPath",
            v26);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
        (const char *)(unsigned int)v28,
        bIgnoreCasea);
  }
  else
  {
    v29 = SHRegSetString(
            v25,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
            L"BackedUpLockscreenPath",
            v26);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
        (const char *)(unsigned int)v29,
        bIgnoreCasea);
  }
LABEL_16:
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(v40);
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v42);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  std::wstring::_Tidy_deallocate(a3);
  return ppv;
}

```

## disassembly

```asm
0x1800aa010  push    rbp
0x1800aa012  push    rbx
0x1800aa013  push    rsi
0x1800aa014  push    rdi
0x1800aa015  push    r14
0x1800aa017  lea     rbp, [rsp-70h]
0x1800aa01c  sub     rsp, 170h
0x1800aa023  mov     rax, cs:__security_cookie
0x1800aa02a  xor     rax, rsp
0x1800aa02d  mov     [rbp+90h+var_30], rax
0x1800aa031  mov     rsi, r8
0x1800aa034  mov     r14, rdx
0x1800aa037  mov     rdi, rcx
0x1800aa03a  mov     [rsp+190h+var_148], rcx
0x1800aa03f  mov     [rsp+190h+var_158], rdx
0x1800aa044  mov     [rsp+190h+var_138], r8
0x1800aa049  mov     [rsp+190h+var_150], 1
0x1800aa051  mov     [rsp+190h+ppszPath], 0
0x1800aa05a  xor     edx, edx
0x1800aa05c  lea     rcx, [rsp+190h+ppszPath]
0x1800aa061  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800aa066  lea     r9, [rsp+190h+ppszPath]; ppszPath
0x1800aa06b  xor     r8d, r8d; hToken
0x1800aa06e  xor     edx, edx; dwFlags
0x1800aa070  lea     rcx, FOLDERID_Pictures; rfid
0x1800aa077  call    cs:__imp_SHGetKnownFolderPath
0x1800aa07d  mov     rcx, [rbp+98h]; this
0x1800aa084  test    eax, eax
0x1800aa086  js      loc_1800AA3B7
0x1800aa08c  lea     rdx, [rsp+190h+var_158]
0x1800aa091  lea     rcx, [rbp+90h+var_B0]
0x1800aa095  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x1800aa09a  nop
0x1800aa09b  mov     rdx, [rsp+190h+ppszPath]
0x1800aa0a0  lea     rcx, [rbp+90h+var_D0]
0x1800aa0a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aa0a9  nop
0x1800aa0aa  mov     qword ptr [rdi], 0
0x1800aa0b1  mov     [rsp+190h+var_150], 1
0x1800aa0b9  lea     rdx, [rsp+190h+var_130]
0x1800aa0be  lea     rcx, [rbp+90h+var_B0]
0x1800aa0c2  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1800aa0c7  nop
0x1800aa0c8  lea     rdx, [rbp+90h+var_F0]
0x1800aa0cc  mov     rcx, rax
0x1800aa0cf  call    ?wstring@path@filesystem@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@XZ; std::filesystem::path::wstring(void)
0x1800aa0d4  nop
0x1800aa0d5  lea     rcx, [rsp+190h+var_130]
0x1800aa0da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa0df  lea     rdx, [rbp+90h+var_D0]
0x1800aa0e3  lea     rcx, [rbp+90h+var_50]
0x1800aa0e7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800aa0ec  nop
0x1800aa0ed  lea     r8, [rbp+90h+var_F0]
0x1800aa0f1  mov     rdx, rax
0x1800aa0f4  lea     rcx, [rbp+90h+var_110]
0x1800aa0f8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800aa0fd  nop
0x1800aa0fe  lea     rcx, [rbp+90h+var_50]
0x1800aa102  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa107  lea     rdx, [rbp+90h+var_110]
0x1800aa10b  lea     rcx, [rsp+190h+var_130]
0x1800aa110  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1800aa115  nop
0x1800aa116  lea     rcx, [rsp+190h+var_130]; this
0x1800aa11b  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800aa120  mov     bl, al
0x1800aa122  lea     rcx, [rsp+190h+var_130]
0x1800aa127  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa12c  test    bl, bl
0x1800aa12e  jz      loc_1800AA224
0x1800aa134  lea     rcx, [rbp+90h+var_110]
0x1800aa138  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa13d  mov     rdx, rax; unsigned __int16 *
0x1800aa140  mov     rcx, r14; this
0x1800aa143  call    ?IsFileIdentical@OneDriveUtils@@YA_NPEBG0@Z; OneDriveUtils::IsFileIdentical(ushort const *,ushort const *)
0x1800aa148  test    al, al
0x1800aa14a  jz      short loc_1800AA19A
0x1800aa14c  mov     rcx, [rdi]
0x1800aa14f  mov     qword ptr [rdi], 0
0x1800aa156  test    rcx, rcx
0x1800aa159  jz      short loc_1800AA168
0x1800aa15b  mov     rax, [rcx]
0x1800aa15e  mov     rax, [rax+10h]
0x1800aa162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa167  nop
0x1800aa168  lea     rcx, [rbp+90h+var_110]
0x1800aa16c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa171  mov     rcx, rax; pszPath
0x1800aa174  mov     r9, rdi; ppv
0x1800aa177  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800aa17e  xor     edx, edx; pbc
0x1800aa180  call    cs:__imp_SHCreateItemFromParsingName
0x1800aa186  mov     rcx, [rbp+98h]; this
0x1800aa18d  test    eax, eax
0x1800aa18f  js      loc_1800AA38D
0x1800aa195  jmp     loc_1800AA320
0x1800aa19a  lea     rax, [rsp+190h+var_130]
0x1800aa19f  mov     [rsp+190h+var_158], rax
0x1800aa1a4  lea     rdx, [rbp+90h+var_B0]
0x1800aa1a8  lea     rcx, [rsp+190h+var_130]
0x1800aa1ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800aa1b2  nop
0x1800aa1b3  lea     rdx, [rbp+90h+var_D0]
0x1800aa1b7  lea     rcx, [rbp+90h+var_90]
0x1800aa1bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800aa1c0  nop
0x1800aa1c1  lea     r8, [rsp+190h+var_130]
0x1800aa1c6  mov     rdx, rax
0x1800aa1c9  lea     rcx, [rbp+90h+var_70]
0x1800aa1cd  call    ?GetNewFileName@OneDriveUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@Vpath@filesystem@3@@Z; OneDriveUtils::GetNewFileName(std::wstring,std::filesystem::path)
0x1800aa1d2  mov     rdx, rax
0x1800aa1d5  lea     rcx, [rbp+90h+var_F0]
0x1800aa1d9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800aa1de  lea     rcx, [rbp+90h+var_70]
0x1800aa1e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa1e7  lea     rdx, [rbp+90h+var_D0]
0x1800aa1eb  lea     rcx, [rbp+90h+var_90]
0x1800aa1ef  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800aa1f4  nop
0x1800aa1f5  lea     r8, [rbp+90h+var_F0]
0x1800aa1f9  mov     rdx, rax
0x1800aa1fc  lea     rcx, [rbp+90h+var_70]
0x1800aa200  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800aa205  mov     rdx, rax
0x1800aa208  lea     rcx, [rbp+90h+var_110]
0x1800aa20c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800aa211  lea     rcx, [rbp+90h+var_70]
0x1800aa215  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa21a  nop
0x1800aa21b  lea     rcx, [rbp+90h+var_90]
0x1800aa21f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa224  lea     rdx, [rbp+90h+var_110]
0x1800aa228  lea     rcx, [rsp+190h+var_130]
0x1800aa22d  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1800aa232  nop
0x1800aa233  lea     rdx, [rsp+190h+var_130]
0x1800aa238  lea     rcx, [rbp+90h+var_B0]
0x1800aa23c  call    ?copy_file@filesystem@std@@YA_NAEBVpath@12@0W4copy_options@12@@Z; std::filesystem::copy_file(std::filesystem::path const &,std::filesystem::path const &,std::filesystem::copy_options)
0x1800aa241  nop
0x1800aa242  lea     rcx, [rsp+190h+var_130]
0x1800aa247  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa24c  nop
0x1800aa24d  mov     rcx, [rdi]
0x1800aa250  mov     qword ptr [rdi], 0
0x1800aa257  test    rcx, rcx
0x1800aa25a  jz      short loc_1800AA269
0x1800aa25c  mov     rax, [rcx]
0x1800aa25f  mov     rax, [rax+10h]
0x1800aa263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa268  nop
0x1800aa269  lea     rcx, [rbp+90h+var_110]
0x1800aa26d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa272  mov     rcx, rax; pszPath
0x1800aa275  mov     r9, rdi; ppv
0x1800aa278  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800aa27f  xor     edx, edx; pbc
0x1800aa281  call    cs:__imp_SHCreateItemFromParsingName
0x1800aa287  mov     rcx, [rbp+98h]; this
0x1800aa28e  test    eax, eax
0x1800aa290  js      loc_1800AA3CC
0x1800aa296  mov     [rsp+190h+var_158], rdi
0x1800aa29b  lea     rdx, [rsp+190h+var_158]
0x1800aa2a0  call    ??$RetryUntilTimeout@V_lambda_12430c30872bdfb0bc16aa7ecb3cd60e_@@@OneDriveUtils@@YAXKAEBV_lambda_12430c30872bdfb0bc16aa7ecb3cd60e_@@@Z; OneDriveUtils::RetryUntilTimeout<_lambda_12430c30872bdfb0bc16aa7ecb3cd60e_>(ulong,_lambda_12430c30872bdfb0bc16aa7ecb3cd60e_ const &)
0x1800aa2a5  mov     rcx, rsi
0x1800aa2a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa2ad  mov     [rsp+190h+bIgnoreCase], 1; int
0x1800aa2b5  or      edx, 0FFFFFFFFh; cchCount1
0x1800aa2b8  mov     r9d, edx; cchCount2
0x1800aa2bb  lea     r8, aBackground; "Background"
0x1800aa2c2  mov     rcx, rax; lpString1
0x1800aa2c5  call    cs:__imp_CompareStringOrdinal
0x1800aa2cb  mov     edx, eax
0x1800aa2cd  lea     rcx, [rbp+90h+var_110]
0x1800aa2d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800aa2d6  mov     r9, rax; unsigned __int16 *
0x1800aa2d9  cmp     edx, 2
0x1800aa2dc  jnz     short loc_1800AA302
0x1800aa2de  lea     r8, aBackedupwallpa; "BackedUpWallpaperPath"
0x1800aa2e5  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800aa2ec  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800aa2f1  mov     rcx, [rbp+98h]; this
0x1800aa2f8  test    eax, eax
0x1800aa2fa  js      loc_1800AA3A2
0x1800aa300  jmp     short loc_1800AA320
0x1800aa302  lea     r8, aBackeduplocksc; "BackedUpLockscreenPath"
0x1800aa309  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800aa310  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800aa315  mov     rcx, [rbp+98h]; this
0x1800aa31c  test    eax, eax
0x1800aa31e  js      short loc_1800AA378
0x1800aa320  lea     rcx, [rbp+90h+var_110]
0x1800aa324  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa329  nop
0x1800aa32a  lea     rcx, [rbp+90h+var_F0]
0x1800aa32e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa333  nop
0x1800aa334  lea     rcx, [rbp+90h+var_D0]
0x1800aa338  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa33d  nop
0x1800aa33e  lea     rcx, [rbp+90h+var_B0]
0x1800aa342  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa347  nop
0x1800aa348  lea     rcx, [rsp+190h+ppszPath]
0x1800aa34d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800aa352  nop
0x1800aa353  mov     rcx, rsi
0x1800aa356  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aa35b  mov     rax, rdi
0x1800aa35e  mov     rcx, [rbp+90h+var_30]
0x1800aa362  xor     rcx, rsp; StackCookie
0x1800aa365  call    __security_check_cookie
0x1800aa36a  add     rsp, 170h
0x1800aa371  pop     r14
0x1800aa373  pop     rdi
0x1800aa374  pop     rsi
0x1800aa375  pop     rbx
0x1800aa376  pop     rbp
0x1800aa377  retn
0x1800aa378  mov     r9d, eax; char *
0x1800aa37b  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aa382  mov     edx, 129h; void *
0x1800aa387  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800aa38d  mov     r9d, eax; char *
0x1800aa390  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aa397  mov     edx, 113h; void *
0x1800aa39c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800aa3a2  mov     r9d, eax; char *
0x1800aa3a5  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aa3ac  mov     edx, 125h; void *
0x1800aa3b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800aa3b7  mov     r9d, eax; char *
0x1800aa3ba  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aa3c1  mov     edx, 108h; void *
0x1800aa3c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800aa3cc  mov     r9d, eax; char *
0x1800aa3cf  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800aa3d6  mov     edx, 11Bh; void *
0x1800aa3db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
