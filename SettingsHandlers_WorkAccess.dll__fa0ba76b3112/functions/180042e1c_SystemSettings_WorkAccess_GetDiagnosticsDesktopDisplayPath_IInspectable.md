# SystemSettings::WorkAccess::GetDiagnosticsDesktopDisplayPath(IInspectable * *)

- ea: `0x180042e1c`
- end: `0x180043028`
- name: `?GetDiagnosticsDesktopDisplayPath@WorkAccess@SystemSettings@@YAJPEAPEAUIInspectable@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct IInspectable **this, struct IInspectable **)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025e30`
- `0x180033d00`

## callees

- `0x180002a60`
- `0x180003534`
- `0x1800096cc`
- `0x1800096ec`
- `0x180011a14`
- `0x180020dd4`
- `0x180023164`
- `0x1800236d8`
- `0x1800291ec`
- `0x180029234`
- `0x180029708`
- `0x180042e1c`
- `0x1800433e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f47`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180042e7d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180042e7d`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180042f07`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180042f37`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180042f07`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180042f37`

## string_xrefs

- `0x180042e94`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x180042ec9`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x180042faf`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::GetDiagnosticsDesktopDisplayPath(
        struct IInspectable **this,
        struct IInspectable **a2)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v8; // rax
  int String; // eax
  PWSTR ppszPath; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v11[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v12[40]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Dst; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[526]; // [rsp+72h] [rbp-8Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( !SystemSettings::WorkAccess::IsDesktopSKU((SystemSettings::WorkAccess *)this) )
  {
    ppszPath = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPath,
      0);
    if ( SHGetKnownFolderPath(&FOLDERID_Documents, 0, 0, &ppszPath) >= 0
      || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &ppszPath,
            0),
          SHGetKnownFolderPath(&FOLDERID_Documents, 0x4400u, 0, &ppszPath) >= 0) )
    {
      std::wstring::wstring(v12, ppszPath);
      std::operator+<unsigned short>(v11, v12, L"\\MDMDiagnostics");
      v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
      String = SystemSettings::DataModel::PropValueHelper::CreateString(v8, this);
      v6 = String;
      if ( String >= 0 )
      {
        std::wstring::_Tidy_deallocate(v11);
        std::wstring::_Tidy_deallocate(v12);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
        (const char *)(unsigned int)String,
        (int)ppszPath);
      std::wstring::_Tidy_deallocate(v11);
      std::wstring::_Tidy_deallocate(v12);
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    return v6;
  }
  Dst = 0;
  memset_0(v14, 0, 0x206u);
  if ( !ExpandEnvironmentStringsW(L"%PUBLIC%\\Documents\\MDMDiagnostics", &Dst, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x43,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
             v3);
  v5 = SystemSettings::DataModel::PropValueHelper::CreateString(&Dst, this);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
      (const char *)(unsigned int)v5,
      (int)ppszPath);
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180042e1c  mov     [rsp-8+arg_8], rbx
0x180042e21  push    rbp
0x180042e22  lea     rbp, [rsp-190h]
0x180042e2a  sub     rsp, 290h
0x180042e31  mov     rax, cs:__security_cookie
0x180042e38  xor     rax, rsp
0x180042e3b  mov     [rbp+190h+var_10], rax
0x180042e42  mov     rbx, rcx
0x180042e45  call    ?IsDesktopSKU@WorkAccess@SystemSettings@@YA_NXZ; SystemSettings::WorkAccess::IsDesktopSKU(void)
0x180042e4a  test    al, al
0x180042e4c  jz      loc_180042EE1
0x180042e52  xor     eax, eax
0x180042e54  mov     [rsp+290h+Dst], ax
0x180042e59  xor     edx, edx; Val
0x180042e5b  mov     r8d, 206h; Size
0x180042e61  lea     rcx, [rsp+290h+var_21E]; void *
0x180042e66  call    memset_0
0x180042e6b  mov     r8d, 104h; nSize
0x180042e71  lea     rdx, [rsp+290h+Dst]; lpDst
0x180042e76  lea     rcx, Src; "%PUBLIC%\\Documents\\MDMDiagnostics"
0x180042e7d  call    cs:__imp_ExpandEnvironmentStringsW
0x180042e84  nop     dword ptr [rax+rax+00h]
0x180042e89  test    eax, eax
0x180042e8b  jnz     short loc_180042EA8
0x180042e8d  mov     rcx, [rbp+198h]; this
0x180042e94  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180042e9b  lea     edx, [rax+43h]; void *
0x180042e9e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042ea3  jmp     loc_180043007
0x180042ea8  mov     rdx, rbx; struct IInspectable **
0x180042eab  lea     rcx, [rsp+290h+Dst]; unsigned __int16 *
0x180042eb0  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180042eb5  mov     ebx, eax
0x180042eb7  test    eax, eax
0x180042eb9  jns     loc_180043005
0x180042ebf  mov     rcx, [rbp+198h]; this
0x180042ec6  mov     r9d, eax; char *
0x180042ec9  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180042ed0  mov     edx, 44h ; 'D'; void *
0x180042ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042eda  mov     eax, ebx
0x180042edc  jmp     loc_180043007
0x180042ee1  mov     [rsp+290h+ppszPath], 0; int
0x180042eea  xor     edx, edx
0x180042eec  lea     rcx, [rsp+290h+ppszPath]
0x180042ef1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180042ef6  lea     r9, [rsp+290h+ppszPath]; ppszPath
0x180042efb  xor     r8d, r8d; hToken
0x180042efe  xor     edx, edx; dwFlags
0x180042f00  lea     rcx, FOLDERID_Documents; rfid
0x180042f07  call    cs:__imp_SHGetKnownFolderPath
0x180042f0e  nop     dword ptr [rax+rax+00h]
0x180042f13  test    eax, eax
0x180042f15  jns     short loc_180042F64
0x180042f17  xor     edx, edx
0x180042f19  lea     rcx, [rsp+290h+ppszPath]
0x180042f1e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180042f23  lea     r9, [rsp+290h+ppszPath]; ppszPath
0x180042f28  xor     r8d, r8d; hToken
0x180042f2b  mov     edx, 4400h; dwFlags
0x180042f30  lea     rcx, FOLDERID_Documents; rfid
0x180042f37  call    cs:__imp_SHGetKnownFolderPath
0x180042f3e  nop     dword ptr [rax+rax+00h]
0x180042f43  test    eax, eax
0x180042f45  jns     short loc_180042F64
0x180042f47  call    cs:__imp_GetLastError
0x180042f4e  nop     dword ptr [rax+rax+00h]
0x180042f53  mov     ebx, eax
0x180042f55  test    eax, eax
0x180042f57  jle     short loc_180042FD6
0x180042f59  movzx   ebx, ax
0x180042f5c  or      ebx, 80070000h
0x180042f62  jmp     short loc_180042FD6
0x180042f64  mov     rdx, [rsp+290h+ppszPath]
0x180042f69  lea     rcx, [rsp+290h+var_248]
0x180042f6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042f73  nop
0x180042f74  lea     r8, aMdmdiagnostics_0; "\\MDMDiagnostics"
0x180042f7b  lea     rdx, [rsp+290h+var_248]
0x180042f80  lea     rcx, [rsp+290h+var_268]
0x180042f85  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180042f8a  lea     rcx, [rsp+290h+var_268]
0x180042f8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042f94  mov     rcx, rax; unsigned __int16 *
0x180042f97  mov     rdx, rbx; struct IInspectable **
0x180042f9a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180042f9f  mov     ebx, eax
0x180042fa1  test    eax, eax
0x180042fa3  jns     short loc_180042FE5
0x180042fa5  mov     rcx, [rbp+198h]; this
0x180042fac  mov     r9d, eax; char *
0x180042faf  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180042fb6  mov     edx, 57h ; 'W'; void *
0x180042fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042fc0  lea     rcx, [rsp+290h+var_268]
0x180042fc5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042fca  nop
0x180042fcb  lea     rcx, [rsp+290h+var_248]
0x180042fd0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042fd5  nop
0x180042fd6  lea     rcx, [rsp+290h+ppszPath]
0x180042fdb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180042fe0  jmp     loc_180042EDA
0x180042fe5  lea     rcx, [rsp+290h+var_268]
0x180042fea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042fef  nop
0x180042ff0  lea     rcx, [rsp+290h+var_248]
0x180042ff5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042ffa  nop
0x180042ffb  lea     rcx, [rsp+290h+ppszPath]
0x180043000  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043005  xor     eax, eax
0x180043007  mov     rcx, [rbp+190h+var_10]
0x18004300e  xor     rcx, rsp; StackCookie
0x180043011  call    __security_check_cookie
0x180043016  mov     rbx, [rsp+290h+arg_8]
0x18004301e  add     rsp, 290h
0x180043025  pop     rbp
0x180043026  retn
```
