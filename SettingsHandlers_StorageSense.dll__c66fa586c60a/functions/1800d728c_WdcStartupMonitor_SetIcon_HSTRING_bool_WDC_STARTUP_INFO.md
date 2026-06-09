# WdcStartupMonitor::_SetIcon(HSTRING__ *,bool,_WDC_STARTUP_INFO *)

- ea: `0x1800d728c`
- end: `0x1800d7552`
- name: `?_SetIcon@WdcStartupMonitor@@AEAAJPEAUHSTRING__@@_NPEAU_WDC_STARTUP_INFO@@@Z`
- size: `710`
- prototype: `int(WdcStartupMonitor *__hidden this, HSTRING, bool, struct _WDC_STARTUP_INFO *)`
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d4d24`
- `0x1800d5540`
- `0x1800d5988`

## callees

- `0x180006e50`
- `0x180008cdc`
- `0x18000e6cc`
- `0x180012a70`
- `0x180016ef4`
- `0x180023578`
- `0x180023928`
- `0x1800292c8`
- `0x180044d90`
- `0x1800d728c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d72be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d72be`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800d72e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x1800d72e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800d735c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800d735c`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800d7341`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800d7341`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800d730a`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800d730a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800d731c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800d731c`
- `ext-ms-win-shell-shell32-l1-2-1!SHDefExtractIconW` at `0x1800d73a0`
- `ext-ms-win-shell-shell32-l1-2-1!SHDefExtractIconW` at `0x1800d73a0`

## pseudocode

```c
__int64 __fastcall WdcStartupMonitor::_SetIcon(WdcStartupMonitor *this, HSTRING a2, __int64 a3, HSTRING *a4)
{
  PCWSTR StringRawBuffer; // rax
  WCHAR *v6; // rax
  int v7; // r14d
  const WCHAR *v8; // rax
  size_t v9; // rdx
  int v10; // esi
  char v11; // di
  const WCHAR *v12; // rax
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  __int64 result; // rax
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  unsigned int v24; // ebx
  int phiconSmall; // [rsp+20h] [rbp-88h]
  int phiconSmalla; // [rsp+20h] [rbp-88h]
  HICON phiconLarge; // [rsp+30h] [rbp-78h] BYREF
  HSTRING v28; // [rsp+38h] [rbp-70h] BYREF
  PCWSTR ppszExt; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v30[16]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v31[32]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v28 = a2;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  try
  {
    std::wstring::wstring(v30, StringRawBuffer);
    ppszExt = 0;
    v6 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    v7 = PathParseIconLocationW(v6);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    PathCchFindExtension(v8, v9, &ppszExt);
    v10 = lstrcmpW(ppszExt, L".exe");
    if ( (unsigned __int8)IsDestroyIconPresent() )
    {
      v11 = 1;
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
      if ( !PathIsNetworkPathW(v12) )
      {
        v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
        if ( PathFileExistsW(v13) )
        {
          if ( !v10 )
          {
            phiconLarge = 0;
            v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
            SHDefExtractIconW(v14, v7, 0, &phiconLarge, 0, 0);
            if ( phiconLarge )
            {
              v15 = Microsoft::WRL::Wrappers::HString::Set(a4 + 60, &v28);
              v16 = v15;
              if ( v15 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2C2,
                  (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
                  (const char *)(unsigned int)v15,
                  phiconSmalla);
                wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&phiconLarge);
                std::wstring::_Tidy_deallocate(v30);
                return v16;
              }
            }
            else
            {
              v28 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &off_1800FFC58) + 24);
              v19 = Microsoft::WRL::Wrappers::HString::Set(a4 + 60, &v28);
              v20 = v19;
              if ( v19 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2C6,
                  (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
                  (const char *)(unsigned int)v19,
                  phiconSmalla);
                wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&phiconLarge);
                std::wstring::_Tidy_deallocate(v30);
                return v20;
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&int DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(&phiconLarge);
LABEL_18:
            std::wstring::_Tidy_deallocate(v30);
            return 0;
          }
        }
      }
    }
    else
    {
      v11 = 0;
    }
    if ( v11 )
    {
      v28 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, off_1800FFC50) + 24);
      v21 = Microsoft::WRL::Wrappers::HString::Set(a4 + 60, &v28);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2CB,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
          (const char *)(unsigned int)v21,
          phiconSmall);
        std::wstring::_Tidy_deallocate(v30);
        return v22;
      }
    }
    else
    {
      v23 = Microsoft::WRL::Wrappers::HString::Set(a4 + 60, &v28);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D0,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
          (const char *)(unsigned int)v23,
          phiconSmall);
        std::wstring::_Tidy_deallocate(v30);
        return v24;
      }
    }
    goto LABEL_18;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D5,
                           (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800d728c  mov     [rsp+arg_0], rbx
0x1800d7291  push    rsi
0x1800d7292  push    rdi
0x1800d7293  push    r14
0x1800d7295  sub     rsp, 90h
0x1800d729c  mov     rax, cs:__security_cookie
0x1800d72a3  xor     rax, rsp
0x1800d72a6  mov     [rsp+0A8h+var_20], rax
0x1800d72ae  mov     rbx, r9
0x1800d72b1  mov     rax, rdx
0x1800d72b4  mov     [rsp+0A8h+var_70], rdx
0x1800d72b9  xor     edx, edx; length
0x1800d72bb  mov     rcx, rax; string
0x1800d72be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d72c4  mov     rdx, rax
0x1800d72c7  lea     rcx, [rsp+0A8h+var_60]
0x1800d72cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d72d1  mov     [rsp+0A8h+ppszExt], 0
0x1800d72da  lea     rcx, [rsp+0A8h+var_60]
0x1800d72df  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d72e4  mov     rcx, rax; pszIconFile
0x1800d72e7  call    cs:__imp_PathParseIconLocationW
0x1800d72ed  mov     r14d, eax
0x1800d72f0  mov     rdx, [rsp+0A8h+var_50]
0x1800d72f5  inc     rdx
0x1800d72f8  lea     rcx, [rsp+0A8h+var_60]
0x1800d72fd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d7302  mov     rcx, rax; pszPath
0x1800d7305  lea     r8, [rsp+0A8h+ppszExt]; ppszExt
0x1800d730a  call    cs:__imp_PathCchFindExtension
0x1800d7310  lea     rdx, pszSrch; ".exe"
0x1800d7317  mov     rcx, [rsp+0A8h+ppszExt]; lpString1
0x1800d731c  call    cs:__imp_lstrcmpW
0x1800d7322  mov     esi, eax
0x1800d7324  call    IsDestroyIconPresent
0x1800d7329  test    al, al
0x1800d732b  jz      loc_1800D7477
0x1800d7331  mov     dil, 1
0x1800d7334  lea     rcx, [rsp+0A8h+var_60]
0x1800d7339  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d733e  mov     rcx, rax; pszPath
0x1800d7341  call    cs:__imp_PathIsNetworkPathW
0x1800d7347  test    eax, eax
0x1800d7349  jnz     loc_1800D747A
0x1800d734f  lea     rcx, [rsp+0A8h+var_60]
0x1800d7354  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d7359  mov     rcx, rax; pszPath
0x1800d735c  call    cs:__imp_PathFileExistsW
0x1800d7362  test    eax, eax
0x1800d7364  jz      loc_1800D747A
0x1800d736a  test    esi, esi
0x1800d736c  jnz     loc_1800D747A
0x1800d7372  mov     [rsp+0A8h+phiconLarge], 0
0x1800d737b  lea     rcx, [rsp+0A8h+var_60]
0x1800d7380  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d7385  mov     rcx, rax; pszIconFile
0x1800d7388  mov     [rsp+0A8h+nIconSize], esi; nIconSize
0x1800d738c  mov     [rsp+0A8h+phiconSmall], 0; int
0x1800d7395  lea     r9, [rsp+0A8h+phiconLarge]; phiconLarge
0x1800d739a  xor     r8d, r8d; uFlags
0x1800d739d  mov     edx, r14d; iIndex
0x1800d73a0  call    cs:__imp_SHDefExtractIconW
0x1800d73a6  cmp     [rsp+0A8h+phiconLarge], 0
0x1800d73ac  jz      short loc_1800D7400
0x1800d73ae  lea     rcx, [rbx+1E0h]; newString
0x1800d73b5  lea     rdx, [rsp+0A8h+var_70]; HSTRING *
0x1800d73ba  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d73bf  mov     ebx, eax
0x1800d73c1  test    eax, eax
0x1800d73c3  jns     loc_1800D7468
0x1800d73c9  mov     rcx, [rsp+0A8h]; this
0x1800d73d1  mov     r9d, eax; char *
0x1800d73d4  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d73db  mov     edx, 2C2h; void *
0x1800d73e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d73e5  lea     rcx, [rsp+0A8h+phiconLarge]
0x1800d73ea  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x1800d73ef  lea     rcx, [rsp+0A8h+var_60]
0x1800d73f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d73f9  mov     eax, ebx
0x1800d73fb  jmp     loc_1800D752D
0x1800d7400  lea     rdx, off_1800FFC58; "%SystemRoot%\\system32\\imageres.dll,-1"...
0x1800d7407  lea     rcx, [rsp+0A8h+var_40]
0x1800d740c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d7411  mov     rdx, [rax+18h]
0x1800d7415  mov     [rsp+0A8h+var_70], rdx
0x1800d741a  lea     rdx, [rsp+0A8h+var_70]; HSTRING *
0x1800d741f  lea     rcx, [rbx+1E0h]; newString
0x1800d7426  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d742b  mov     ebx, eax
0x1800d742d  test    eax, eax
0x1800d742f  jns     short loc_1800D7468
0x1800d7431  mov     rcx, [rsp+0A8h]; this
0x1800d7439  mov     r9d, eax; char *
0x1800d743c  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d7443  mov     edx, 2C6h; void *
0x1800d7448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d744d  lea     rcx, [rsp+0A8h+phiconLarge]
0x1800d7452  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x1800d7457  lea     rcx, [rsp+0A8h+var_60]
0x1800d745c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d7461  mov     eax, ebx
0x1800d7463  jmp     loc_1800D752D
0x1800d7468  lea     rcx, [rsp+0A8h+phiconLarge]
0x1800d746d  call    ??1?$unique_storage@U?$resource_policy@PEAUHICON__@@P6AHPEAU1@@Z$1?DestroyIcon@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HICON__ *,int (*)(HICON__ *),&DestroyIcon(HICON__ *),wistd::integral_constant<unsigned __int64,0>,HICON__ *,HICON__ *,0,std::nullptr_t>>(void)
0x1800d7472  jmp     loc_1800D751B
0x1800d7477  xor     dil, dil
0x1800d747a  test    dil, dil
0x1800d747d  jz      short loc_1800D74DA
0x1800d747f  lea     rdx, off_1800FFC50; "%SystemRoot%\\system32\\imageres.dll,-2"
0x1800d7486  lea     rcx, [rsp+0A8h+var_40]
0x1800d748b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d7490  mov     rdx, [rax+18h]
0x1800d7494  mov     [rsp+0A8h+var_70], rdx
0x1800d7499  lea     rdx, [rsp+0A8h+var_70]; HSTRING *
0x1800d749e  lea     rcx, [rbx+1E0h]; newString
0x1800d74a5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d74aa  mov     ebx, eax
0x1800d74ac  test    eax, eax
0x1800d74ae  jns     short loc_1800D751B
0x1800d74b0  mov     rcx, [rsp+0A8h]; this
0x1800d74b8  mov     r9d, eax; char *
0x1800d74bb  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d74c2  mov     edx, 2CBh; void *
0x1800d74c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d74cc  lea     rcx, [rsp+0A8h+var_60]
0x1800d74d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d74d6  mov     eax, ebx
0x1800d74d8  jmp     short loc_1800D752D
0x1800d74da  lea     rdx, [rsp+0A8h+var_70]; HSTRING *
0x1800d74df  lea     rcx, [rbx+1E0h]; newString
0x1800d74e6  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d74eb  mov     ebx, eax
0x1800d74ed  test    eax, eax
0x1800d74ef  jns     short loc_1800D751B
0x1800d74f1  mov     rcx, [rsp+0A8h]; this
0x1800d74f9  mov     r9d, eax; char *
0x1800d74fc  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d7503  mov     edx, 2D0h; void *
0x1800d7508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d750d  lea     rcx, [rsp+0A8h+var_60]
0x1800d7512  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d7517  mov     eax, ebx
0x1800d7519  jmp     short loc_1800D752D
0x1800d751b  lea     rcx, [rsp+0A8h+var_60]
0x1800d7520  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d7525  xor     eax, eax
0x1800d7527  jmp     short loc_1800D752D
0x1800d7529  mov     eax, dword ptr [rsp+0A8h+phiconLarge]
0x1800d752d  mov     rcx, [rsp+0A8h+var_20]
0x1800d7535  xor     rcx, rsp; StackCookie
0x1800d7538  call    __security_check_cookie
0x1800d753d  mov     rbx, [rsp+0A8h+arg_0]
0x1800d7545  add     rsp, 90h
0x1800d754c  pop     r14
0x1800d754e  pop     rdi
0x1800d754f  pop     rsi
0x1800d7550  retn
```
