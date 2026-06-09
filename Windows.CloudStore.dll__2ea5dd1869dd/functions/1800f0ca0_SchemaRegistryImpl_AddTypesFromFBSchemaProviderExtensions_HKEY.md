# SchemaRegistryImpl::AddTypesFromFBSchemaProviderExtensions(HKEY__ *)

- ea: `0x1800f0ca0`
- end: `0x1800f0f12`
- name: `?AddTypesFromFBSchemaProviderExtensions@SchemaRegistryImpl@@AEAAXPEAUHKEY__@@@Z`
- size: `626`
- prototype: `void __fastcall(SchemaRegistryImpl *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f11b0`

## callees

- `0x18000f4b4`
- `0x180016cf4`
- `0x18003e670`
- `0x18003f6c4`
- `0x180091858`
- `0x1800a60f0`
- `0x1800f0ca0`
- `0x1800f14dc`
- `0x1801201a0`
- `0x1801a6bf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f0d04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f0d04`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800f0e94`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800f0e94`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f0dae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800f0dae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f0e28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800f0e28`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800f0dcf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800f0dcf`

## string_xrefs

- `0x1800f0d21`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800f0ed6`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800f0eeb`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800f0f00`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800f0cf6`: `Software\Microsoft\Windows\CurrentVersion\CloudStore\SchemaExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SchemaRegistryImpl::AddTypesFromFBSchemaProviderExtensions(SchemaRegistryImpl *this, HKEY a2)
{
  unsigned int v3; // eax
  DWORD v4; // ebx
  DWORD i; // edx
  HRESULT v6; // eax
  __int64 v7; // rdx
  HRESULT v8; // eax
  unsigned int v9; // eax
  int v10; // r9d
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String1[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\SchemaExtensions",
         0,
         0x20019u,
         &hKey);
  if ( v3 != 2 )
  {
    if ( v3 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2FB,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
        (const char *)v3,
        phkResult);
    v4 = 0;
    for ( i = 0; ; i = v4 )
    {
      cchName = 260;
      v9 = RegEnumKeyExW(hKey, i, sz, &cchName, 0, 0, 0, 0);
      if ( v9 == 259 )
        break;
      if ( v9 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x309,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)v9,
          phkResultc);
      if ( (int)SHRegGetStringEx(hKey, sz, L"SchemaType", v10, String1, 0x104u) >= 0
        && CompareStringOrdinal(String1, -1, L"FlatBuffers", -1, 1) == 2 )
      {
        pclsid = 0;
        v6 = CLSIDFromString(sz, &pclsid);
        if ( v6 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x314,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
            (const char *)(unsigned int)v6,
            phkResulta);
        if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
          McTemplateU0j_EventWriteTransfer(retaddr, v7, &pclsid);
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        v8 = CoCreateInstance(&pclsid, 0, 0x401u, &GUID_efe84c27_afa6_485d_a70a_aa2ab5cb6c67, &ppv);
        if ( v8 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x318,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
            (const char *)(unsigned int)v8,
            phkResultb);
        SchemaRegistryImpl::AddTypesFromFBProvider(this, (struct ICloudStoreSchemaProvider *)ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      }
      ++v4;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800f0ca0  mov     [rsp-8+arg_8], rbx
0x1800f0ca5  mov     [rsp-8+arg_10], rdi
0x1800f0caa  push    rbp
0x1800f0cab  lea     rbp, [rsp-3A0h]
0x1800f0cb3  sub     rsp, 4A0h
0x1800f0cba  mov     rax, cs:__security_cookie
0x1800f0cc1  xor     rax, rsp
0x1800f0cc4  mov     [rbp+3A0h+var_10], rax
0x1800f0ccb  mov     rdi, rcx
0x1800f0cce  mov     [rsp+4A0h+hKey], 0
0x1800f0cd7  xor     edx, edx
0x1800f0cd9  lea     rcx, [rsp+4A0h+hKey]
0x1800f0cde  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800f0ce3  lea     rax, [rsp+4A0h+hKey]
0x1800f0ce8  mov     [rsp+4A0h+phkResult], rax; unsigned int
0x1800f0ced  mov     r9d, 20019h; samDesired
0x1800f0cf3  xor     r8d, r8d; ulOptions
0x1800f0cf6  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800f0cfd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f0d04  call    cs:__imp_RegOpenKeyExW
0x1800f0d0a  cmp     eax, 2
0x1800f0d0d  jz      loc_1800F0EA5
0x1800f0d13  mov     rcx, [rbp+3A8h]; this
0x1800f0d1a  test    eax, eax
0x1800f0d1c  jz      short loc_1800F0D33
0x1800f0d1e  mov     r9d, eax; char *
0x1800f0d21  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800f0d28  mov     edx, 2FBh; void *
0x1800f0d2d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800f0d33  xor     ebx, ebx
0x1800f0d35  mov     [rsp+4A0h+lpftLastWriteTime], rbx
0x1800f0d3a  mov     [rsp+4A0h+lpcchClass], rbx
0x1800f0d3f  mov     [rsp+4A0h+lpClass], rbx
0x1800f0d44  mov     [rsp+4A0h+phkResult], rbx
0x1800f0d49  xor     edx, edx
0x1800f0d4b  jmp     loc_1800F0E7D
0x1800f0d50  mov     rcx, [rbp+3A8h]; this
0x1800f0d57  test    eax, eax
0x1800f0d59  jnz     loc_1800F0EFD
0x1800f0d5f  mov     dword ptr [rsp+4A0h+lpClass], 104h; unsigned int
0x1800f0d67  lea     rax, [rbp+3A0h+String1]
0x1800f0d6e  mov     [rsp+4A0h+phkResult], rax; unsigned __int16 *
0x1800f0d73  lea     r8, aSchematype; "SchemaType"
0x1800f0d7a  lea     rdx, [rsp+4A0h+sz]; unsigned __int16 *
0x1800f0d7f  mov     rcx, [rsp+4A0h+hKey]; HKEY
0x1800f0d84  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1800f0d89  test    eax, eax
0x1800f0d8b  js      loc_1800F0E55
0x1800f0d91  mov     dword ptr [rsp+4A0h+phkResult], 1; int
0x1800f0d99  or      r9d, 0FFFFFFFFh; cchCount2
0x1800f0d9d  lea     r8, aFlatbuffers_0; "FlatBuffers"
0x1800f0da4  or      edx, r9d; cchCount1
0x1800f0da7  lea     rcx, [rbp+3A0h+String1]; lpString1
0x1800f0dae  call    cs:__imp_CompareStringOrdinal
0x1800f0db4  cmp     eax, 2
0x1800f0db7  jnz     loc_1800F0E55
0x1800f0dbd  xorps   xmm0, xmm0
0x1800f0dc0  movups  xmmword ptr [rsp+4A0h+pclsid.Data1], xmm0
0x1800f0dc5  lea     rdx, [rsp+4A0h+pclsid]; pclsid
0x1800f0dca  lea     rcx, [rsp+4A0h+sz]; lpsz
0x1800f0dcf  call    cs:__imp_CLSIDFromString
0x1800f0dd5  mov     rcx, [rbp+3A8h]; this
0x1800f0ddc  test    eax, eax
0x1800f0dde  js      loc_1800F0EE8
0x1800f0de4  test    cs:Microsoft_Windows_CloudStoreEnableBits, 2
0x1800f0deb  jz      short loc_1800F0DF7
0x1800f0ded  lea     r8, [rsp+4A0h+pclsid]
0x1800f0df2  call    McTemplateU0j_EventWriteTransfer
0x1800f0df7  mov     [rsp+4A0h+ppv], 0
0x1800f0e00  lea     rcx, [rsp+4A0h+ppv]
0x1800f0e05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0e0a  lea     rax, [rsp+4A0h+ppv]
0x1800f0e0f  mov     [rsp+4A0h+phkResult], rax; int
0x1800f0e14  lea     r9, _GUID_efe84c27_afa6_485d_a70a_aa2ab5cb6c67; riid
0x1800f0e1b  xor     edx, edx; pUnkOuter
0x1800f0e1d  mov     r8d, 401h; dwClsContext
0x1800f0e23  lea     rcx, [rsp+4A0h+pclsid]; rclsid
0x1800f0e28  call    cs:__imp_CoCreateInstance
0x1800f0e2e  mov     rcx, [rbp+3A8h]; this
0x1800f0e35  test    eax, eax
0x1800f0e37  js      loc_1800F0ED3
0x1800f0e3d  mov     rdx, [rsp+4A0h+ppv]; struct ICloudStoreSchemaProvider *
0x1800f0e42  mov     rcx, rdi; this
0x1800f0e45  call    ?AddTypesFromFBProvider@SchemaRegistryImpl@@AEAAXPEAUICloudStoreSchemaProvider@@@Z; SchemaRegistryImpl::AddTypesFromFBProvider(ICloudStoreSchemaProvider *)
0x1800f0e4a  nop
0x1800f0e4b  lea     rcx, [rsp+4A0h+ppv]
0x1800f0e50  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f0e55  inc     ebx
0x1800f0e57  mov     [rsp+4A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800f0e60  mov     [rsp+4A0h+lpcchClass], 0; lpcchClass
0x1800f0e69  mov     [rsp+4A0h+lpClass], 0; lpClass
0x1800f0e72  mov     [rsp+4A0h+phkResult], 0; unsigned int
0x1800f0e7b  mov     edx, ebx; dwIndex
0x1800f0e7d  mov     [rsp+4A0h+cchName], 104h
0x1800f0e85  lea     r9, [rsp+4A0h+cchName]; lpcchName
0x1800f0e8a  lea     r8, [rsp+4A0h+sz]; lpName
0x1800f0e8f  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800f0e94  call    cs:__imp_RegEnumKeyExW
0x1800f0e9a  cmp     eax, 103h
0x1800f0e9f  jnz     loc_1800F0D50
0x1800f0ea5  lea     rcx, [rsp+4A0h+hKey]
0x1800f0eaa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f0eaf  mov     rcx, [rbp+3A0h+var_10]
0x1800f0eb6  xor     rcx, rsp; StackCookie
0x1800f0eb9  call    __security_check_cookie
0x1800f0ebe  lea     r11, [rsp+4A0h+var_s0]
0x1800f0ec6  mov     rbx, [r11+18h]
0x1800f0eca  mov     rdi, [r11+20h]
0x1800f0ece  mov     rsp, r11
0x1800f0ed1  pop     rbp
0x1800f0ed2  retn
0x1800f0ed3  mov     r9d, eax; char *
0x1800f0ed6  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800f0edd  mov     edx, 318h; void *
0x1800f0ee2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f0ee8  mov     r9d, eax; char *
0x1800f0eeb  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800f0ef2  mov     edx, 314h; void *
0x1800f0ef7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f0efd  mov     r9d, eax; char *
0x1800f0f00  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800f0f07  mov     edx, 309h; void *
0x1800f0f0c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
