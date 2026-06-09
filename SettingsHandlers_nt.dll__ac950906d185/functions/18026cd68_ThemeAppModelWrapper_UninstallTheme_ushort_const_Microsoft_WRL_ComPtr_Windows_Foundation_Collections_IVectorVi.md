# ThemeAppModelWrapper::UninstallTheme(ushort const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppExtension *>>,ushort const *)

- ea: `0x18026cd68`
- end: `0x18026cf7f`
- name: `?UninstallTheme@ThemeAppModelWrapper@@AEAAJPEBGV?$ComPtr@U?$IVectorView@PEAVAppExtension@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@0@Z`
- size: `535`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18026cf88`
- `0x18026d0b4`

## callees

- `0x180011bb0`
- `0x180019a20`
- `0x180269d68`
- `0x18026aa40`
- `0x18026c9d0`
- `0x18026cd68`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026ce5e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026ce5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ce10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ce73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ce8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cf50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ce10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ce73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026ce8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026cf50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026ce40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026ce40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ThemeAppModelWrapper::UninstallTheme(HSTRING a1, const WCHAR *a2, _QWORD *a3, __int64 a4)
{
  int v6; // eax
  ThemeAppModelWrapper *v7; // rcx
  unsigned int v8; // ebx
  unsigned int i; // edi
  int v10; // eax
  __int64 (__fastcall *v11)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *); // rbx
  int ExtensionPackageFullName; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  HSTRING string; // [rsp+30h] [rbp-10h] BYREF
  struct Windows::Internal::StateRepository::IAppExtension *v20; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING v22; // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v23; // [rsp+80h] [rbp+40h]
  unsigned int v24; // [rsp+88h] [rbp+48h] BYREF
  int v25; // [rsp+8Ch] [rbp+4Ch]

  v25 = HIDWORD(a4);
  v23 = a3;
  v22 = a1;
  v24 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*a3 + 56LL))(*a3, &v24);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v22 = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= v24 )
        goto LABEL_14;
      v20 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct Windows::Internal::StateRepository::IAppExtension **))(*(_QWORD *)*a3 + 48LL))(
              *a3,
              i,
              &v20);
      v8 = v10;
      if ( v10 < 0 )
      {
        v16 = 327;
        goto LABEL_18;
      }
      string = 0;
      v11 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IAppExtension *, HSTRING *))(*(_QWORD *)v20 + 104LL);
      WindowsDeleteString(0);
      string = 0;
      ExtensionPackageFullName = v11(v20, &string);
      v8 = ExtensionPackageFullName;
      if ( ExtensionPackageFullName < 0 )
      {
        v14 = 329;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)ExtensionPackageFullName,
          bIgnoreCase);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_12;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, a2, -1, 0) == 2 )
        break;
      WindowsDeleteString(string);
      string = 0;
    }
    WindowsDeleteString(v22);
    v22 = 0;
    ExtensionPackageFullName = ThemeAppModelWrapper::GetExtensionPackageFullName(v20, &v22);
    v8 = ExtensionPackageFullName;
    if ( ExtensionPackageFullName < 0 )
    {
      v14 = 332;
      goto LABEL_11;
    }
    WindowsDeleteString(string);
LABEL_14:
    v10 = ThemeAppModelWrapper::RequestRemovePackage(v7, v22);
    v8 = v10;
    if ( v10 < 0 )
    {
      v16 = 337;
      goto LABEL_18;
    }
    v10 = ThemeAppModelWrapper::CleanupOnAppPackageUninstall(a2, v15);
    v8 = v10;
    if ( v10 < 0 )
    {
      v16 = 338;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
LABEL_12:
      WindowsDeleteString(v22);
      goto LABEL_22;
    }
    WindowsDeleteString(v22);
    v8 = 0;
LABEL_22:
    v22 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
  return v8;
}

```

## disassembly

```asm
0x18026cd68  mov     rax, rsp
0x18026cd6b  mov     [rax+10h], rbx
0x18026cd6f  mov     [rax+20h], r9
0x18026cd73  mov     [rax+18h], r8
0x18026cd77  mov     [rax+8], rcx
0x18026cd7b  push    rbp
0x18026cd7c  push    rsi
0x18026cd7d  push    rdi
0x18026cd7e  push    r14
0x18026cd80  push    r15
0x18026cd82  mov     rbp, rsp
0x18026cd85  sub     rsp, 40h
0x18026cd89  mov     rsi, r8
0x18026cd8c  mov     r14, rdx
0x18026cd8f  xor     r15d, r15d
0x18026cd92  mov     [rbp+arg_18], r15d
0x18026cd96  mov     rcx, [r8]
0x18026cd99  mov     rax, [rcx]
0x18026cd9c  lea     rdx, [rbp+arg_18]
0x18026cda0  mov     rax, [rax+38h]
0x18026cda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cda9  mov     ebx, eax
0x18026cdab  test    eax, eax
0x18026cdad  jns     short loc_18026CDCC
0x18026cdaf  mov     rcx, [rbp+28h]; this
0x18026cdb3  mov     r9d, eax; char *
0x18026cdb6  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026cdbd  mov     edx, 142h; void *
0x18026cdc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cdc7  jmp     loc_18026CF63
0x18026cdcc  mov     [rbp+arg_0], r15
0x18026cdd0  mov     edi, r15d
0x18026cdd3  cmp     edi, [rbp+arg_18]
0x18026cdd6  jnb     loc_18026CF00
0x18026cddc  mov     [rbp+var_8], r15
0x18026cde0  mov     rcx, [rsi]
0x18026cde3  mov     rax, [rcx]
0x18026cde6  lea     r8, [rbp+var_8]
0x18026cdea  mov     edx, edi
0x18026cdec  mov     rax, [rax+30h]
0x18026cdf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026cdf5  mov     ebx, eax
0x18026cdf7  test    eax, eax
0x18026cdf9  js      loc_18026CF1D
0x18026cdff  mov     [rbp+string], r15
0x18026ce03  mov     rax, [rbp+var_8]
0x18026ce07  mov     rcx, [rax]
0x18026ce0a  mov     rbx, [rcx+68h]
0x18026ce0e  xor     ecx, ecx; string
0x18026ce10  call    cs:__imp_WindowsDeleteString
0x18026ce17  nop     dword ptr [rax+rax+00h]
0x18026ce1c  mov     [rbp+string], r15
0x18026ce20  lea     rdx, [rbp+string]
0x18026ce24  mov     rcx, [rbp+var_8]
0x18026ce28  mov     rax, rbx
0x18026ce2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026ce30  mov     ebx, eax
0x18026ce32  test    eax, eax
0x18026ce34  js      loc_18026CF16
0x18026ce3a  xor     edx, edx; length
0x18026ce3c  mov     rcx, [rbp+string]; string
0x18026ce40  call    cs:__imp_WindowsGetStringRawBuffer
0x18026ce47  nop     dword ptr [rax+rax+00h]
0x18026ce4c  mov     [rsp+40h+bIgnoreCase], r15d; int
0x18026ce51  or      r9d, 0FFFFFFFFh; cchCount2
0x18026ce55  mov     r8, r14; lpString2
0x18026ce58  or      edx, r9d; cchCount1
0x18026ce5b  mov     rcx, rax; lpString1
0x18026ce5e  call    cs:__imp_CompareStringOrdinal
0x18026ce65  nop     dword ptr [rax+rax+00h]
0x18026ce6a  cmp     eax, 2
0x18026ce6d  jz      short loc_18026CE8A
0x18026ce6f  mov     rcx, [rbp+string]; string
0x18026ce73  call    cs:__imp_WindowsDeleteString
0x18026ce7a  nop     dword ptr [rax+rax+00h]
0x18026ce7f  mov     [rbp+string], r15
0x18026ce83  inc     edi
0x18026ce85  jmp     loc_18026CDD3
0x18026ce8a  mov     rcx, [rbp+arg_0]; string
0x18026ce8e  call    cs:__imp_WindowsDeleteString
0x18026ce95  nop     dword ptr [rax+rax+00h]
0x18026ce9a  mov     [rbp+arg_0], r15
0x18026ce9e  lea     rdx, [rbp+arg_0]; HSTRING *
0x18026cea2  mov     rcx, [rbp+var_8]; struct Windows::Internal::StateRepository::IAppExtension *
0x18026cea6  call    ?GetExtensionPackageFullName@ThemeAppModelWrapper@@SAJPEAUIAppExtension@StateRepository@Internal@Windows@@PEAPEAUHSTRING__@@@Z; ThemeAppModelWrapper::GetExtensionPackageFullName(Windows::Internal::StateRepository::IAppExtension *,HSTRING__ * *)
0x18026ceab  mov     ebx, eax
0x18026cead  test    eax, eax
0x18026ceaf  jns     short loc_18026CEF0
0x18026ceb1  mov     edx, 14Ch; void *
0x18026ceb6  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026cebd  mov     r9d, eax; char *
0x18026cec0  mov     rcx, [rbp+28h]; this
0x18026cec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cec9  nop
0x18026ceca  mov     rcx, [rbp+string]; string
0x18026cece  call    cs:__imp_WindowsDeleteString
0x18026ced5  nop     dword ptr [rax+rax+00h]
0x18026ceda  mov     [rbp+string], r15
0x18026cede  mov     rcx, [rbp+arg_0]; string
0x18026cee2  call    cs:__imp_WindowsDeleteString
0x18026cee9  nop     dword ptr [rax+rax+00h]
0x18026ceee  jmp     short loc_18026CF5F
0x18026cef0  mov     rcx, [rbp+string]; string
0x18026cef4  call    cs:__imp_WindowsDeleteString
0x18026cefb  nop     dword ptr [rax+rax+00h]
0x18026cf00  mov     rdx, [rbp+arg_0]; HSTRING
0x18026cf04  call    ?RequestRemovePackage@ThemeAppModelWrapper@@AEAAJPEAUHSTRING__@@@Z; ThemeAppModelWrapper::RequestRemovePackage(HSTRING__ *)
0x18026cf09  mov     ebx, eax
0x18026cf0b  test    eax, eax
0x18026cf0d  jns     short loc_18026CF37
0x18026cf0f  mov     edx, 151h
0x18026cf14  jmp     short loc_18026CF22
0x18026cf16  mov     edx, 149h
0x18026cf1b  jmp     short loc_18026CEB6
0x18026cf1d  mov     edx, 147h; void *
0x18026cf22  mov     rcx, [rbp+28h]; this
0x18026cf26  mov     r9d, eax; char *
0x18026cf29  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026cf30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026cf35  jmp     short loc_18026CEDE
0x18026cf37  mov     rcx, r14; lpValueName
0x18026cf3a  call    ?CleanupOnAppPackageUninstall@ThemeAppModelWrapper@@SAJPEBG0@Z; ThemeAppModelWrapper::CleanupOnAppPackageUninstall(ushort const *,ushort const *)
0x18026cf3f  mov     ebx, eax
0x18026cf41  test    eax, eax
0x18026cf43  jns     short loc_18026CF4C
0x18026cf45  mov     edx, 152h
0x18026cf4a  jmp     short loc_18026CF22
0x18026cf4c  mov     rcx, [rbp+arg_0]; string
0x18026cf50  call    cs:__imp_WindowsDeleteString
0x18026cf57  nop     dword ptr [rax+rax+00h]
0x18026cf5c  mov     ebx, r15d
0x18026cf5f  mov     [rbp+arg_0], r15
0x18026cf63  mov     rcx, rsi
0x18026cf66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026cf6b  mov     eax, ebx
0x18026cf6d  mov     rbx, [rsp+40h+arg_8]
0x18026cf72  add     rsp, 40h
0x18026cf76  pop     r15
0x18026cf78  pop     r14
0x18026cf7a  pop     rdi
0x18026cf7b  pop     rsi
0x18026cf7c  pop     rbp
0x18026cf7d  retn
```
