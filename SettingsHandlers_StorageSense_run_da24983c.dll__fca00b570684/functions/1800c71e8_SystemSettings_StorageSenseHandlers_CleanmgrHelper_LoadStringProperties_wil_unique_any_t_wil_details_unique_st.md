# SystemSettings::StorageSenseHandlers::CleanmgrHelper::_LoadStringProperties(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo &)

- ea: `0x1800c71e8`
- end: `0x1800c738e`
- name: `?_LoadStringProperties@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@AEAAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPluginInfo@123@@Z`
- size: `422`
- prototype: `__int64 __fastcall(__int64, HKEY *, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c4ca0`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x1800c71e8`
- `0x1800c7394`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c726a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c726a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c7297`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c7297`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c724c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c724c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::StorageSenseHandlers::CleanmgrHelper::_LoadStringProperties(
        __int64 a1,
        HKEY *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  LPVOID ppv; // [rsp+40h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-31h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-2Dh] BYREF
  GUID pclsid; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR Data[40]; // [rsp+60h] [rbp-19h] BYREF

  ppv = 0;
  cbData = 78;
  Type = 1;
  if ( !RegQueryValueExW(*a2, L"PropertyBag", 0, &Type, (LPBYTE)Data, &cbData) )
  {
    pclsid = GUID_NULL;
    if ( CLSIDFromString(Data, &pclsid) >= 0 )
    {
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppv);
      CoCreateInstance(&pclsid, 0, 1u, &IID_IPropertyBag, &ppv);
    }
  }
  SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(
    v7,
    a2,
    a3,
    (__int64 *)&ppv,
    L"display",
    256,
    a4 + 32);
  SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(
    v8,
    a2,
    a3,
    (__int64 *)&ppv,
    (LPCWSTR)&stru_180108C08,
    512,
    a4 + 64);
  SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(
    v9,
    a2,
    a3,
    (__int64 *)&ppv,
    L"PreCleanupString",
    512,
    a4 + 128);
  SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(
    v10,
    a2,
    a3,
    (__int64 *)&ppv,
    L"CleanupString",
    512,
    a4 + 160);
  v11 = *(_QWORD *)(a4 + 48) == 0 ? 0x80004005 : 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppv);
  return v11;
}

```

## disassembly

```asm
0x1800c71e8  mov     [rsp-8+arg_0], rbx
0x1800c71ed  push    rbp
0x1800c71ee  push    rsi
0x1800c71ef  push    rdi
0x1800c71f0  lea     rbp, [rsp-47h]
0x1800c71f5  sub     rsp, 0C0h
0x1800c71fc  mov     rax, cs:__security_cookie
0x1800c7203  xor     rax, rsp
0x1800c7206  mov     [rbp+57h+var_20], rax
0x1800c720a  mov     rdi, r9
0x1800c720d  mov     rsi, r8
0x1800c7210  mov     rbx, rdx
0x1800c7213  mov     [rbp+57h+ppv], 0
0x1800c721b  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x1800c7222  mov     [rbp+57h+Type], 1
0x1800c7229  lea     rax, [rbp+57h+cbData]
0x1800c722d  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x1800c7232  lea     rax, [rbp+57h+Data]
0x1800c7236  mov     [rsp+0D0h+lpData], rax; lpData
0x1800c723b  lea     r9, [rbp+57h+Type]; lpType
0x1800c723f  xor     r8d, r8d; lpReserved
0x1800c7242  lea     rdx, aPropertybag; "PropertyBag"
0x1800c7249  mov     rcx, [rbx]; hKey
0x1800c724c  call    cs:__imp_RegQueryValueExW
0x1800c7252  test    eax, eax
0x1800c7254  jnz     short loc_1800C729D
0x1800c7256  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800c725d  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1800c7262  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800c7266  lea     rcx, [rbp+57h+Data]; lpsz
0x1800c726a  call    cs:__imp_CLSIDFromString
0x1800c7270  test    eax, eax
0x1800c7272  js      short loc_1800C729D
0x1800c7274  lea     rcx, [rbp+57h+ppv]
0x1800c7278  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c727d  lea     rax, [rbp+57h+ppv]
0x1800c7281  mov     [rsp+0D0h+lpData], rax; ppv
0x1800c7286  lea     r9, IID_IPropertyBag; riid
0x1800c728d  xor     edx, edx; pUnkOuter
0x1800c728f  lea     r8d, [rdx+1]; dwClsContext
0x1800c7293  lea     rcx, [rbp+57h+pclsid]; rclsid
0x1800c7297  call    cs:__imp_CoCreateInstance
0x1800c729d  lea     rax, [rdi+20h]
0x1800c72a1  mov     [rsp+0D0h+var_A0], rax; __int64
0x1800c72a6  mov     dword ptr [rsp+0D0h+lpcbData], 100h; int
0x1800c72ae  lea     rax, aDisplay; "display"
0x1800c72b5  mov     [rsp+0D0h+lpData], rax; lpValueName
0x1800c72ba  lea     r9, [rbp+57h+ppv]; int
0x1800c72be  mov     r8, rsi; int
0x1800c72c1  mov     rdx, rbx; int
0x1800c72c4  call    ?_ReadProperty@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@PEBGKAEAV67@@Z; SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,Microsoft::WRL::ComPtr<IPropertyBag> const &,ushort const *,ulong,std::wstring &)
0x1800c72c9  lea     rax, [rdi+40h]
0x1800c72cd  mov     [rsp+0D0h+var_A0], rax; __int64
0x1800c72d2  mov     dword ptr [rsp+0D0h+lpcbData], 200h; int
0x1800c72da  lea     rax, stru_180108C08
0x1800c72e1  mov     [rsp+0D0h+lpData], rax; lpValueName
0x1800c72e6  lea     r9, [rbp+57h+ppv]; int
0x1800c72ea  mov     r8, rsi; int
0x1800c72ed  mov     rdx, rbx; int
0x1800c72f0  call    ?_ReadProperty@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@PEBGKAEAV67@@Z; SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,Microsoft::WRL::ComPtr<IPropertyBag> const &,ushort const *,ulong,std::wstring &)
0x1800c72f5  lea     rax, [rdi+80h]
0x1800c72fc  mov     [rsp+0D0h+var_A0], rax; __int64
0x1800c7301  mov     dword ptr [rsp+0D0h+lpcbData], 200h; int
0x1800c7309  lea     rax, aPrecleanupstri; "PreCleanupString"
0x1800c7310  mov     [rsp+0D0h+lpData], rax; lpValueName
0x1800c7315  lea     r9, [rbp+57h+ppv]; int
0x1800c7319  mov     r8, rsi; int
0x1800c731c  mov     rdx, rbx; int
0x1800c731f  call    ?_ReadProperty@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@PEBGKAEAV67@@Z; SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,Microsoft::WRL::ComPtr<IPropertyBag> const &,ushort const *,ulong,std::wstring &)
0x1800c7324  lea     rax, [rdi+0A0h]
0x1800c732b  mov     [rsp+0D0h+var_A0], rax; __int64
0x1800c7330  mov     dword ptr [rsp+0D0h+lpcbData], 200h; int
0x1800c7338  lea     rax, aCleanupstring; "CleanupString"
0x1800c733f  mov     [rsp+0D0h+lpData], rax; lpValueName
0x1800c7344  lea     r9, [rbp+57h+ppv]; int
0x1800c7348  mov     r8, rsi; int
0x1800c734b  mov     rdx, rbx; int
0x1800c734e  call    ?_ReadProperty@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@PEBGKAEAV67@@Z; SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,Microsoft::WRL::ComPtr<IPropertyBag> const &,ushort const *,ulong,std::wstring &)
0x1800c7353  mov     rax, [rdi+30h]
0x1800c7357  neg     rax
0x1800c735a  sbb     ebx, ebx
0x1800c735c  not     ebx
0x1800c735e  and     ebx, 80004005h
0x1800c7364  lea     rcx, [rbp+57h+ppv]
0x1800c7368  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c736d  mov     eax, ebx
0x1800c736f  mov     rcx, [rbp+57h+var_20]
0x1800c7373  xor     rcx, rsp; StackCookie
0x1800c7376  call    __security_check_cookie
0x1800c737b  mov     rbx, [rsp+0D0h+arg_0]
0x1800c7383  add     rsp, 0C0h
0x1800c738a  pop     rdi
0x1800c738b  pop     rsi
0x1800c738c  pop     rbp
0x1800c738d  retn
```
