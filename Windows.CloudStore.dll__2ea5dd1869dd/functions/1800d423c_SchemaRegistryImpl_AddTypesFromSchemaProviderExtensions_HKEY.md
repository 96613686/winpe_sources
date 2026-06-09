# SchemaRegistryImpl::AddTypesFromSchemaProviderExtensions(HKEY__ *)

- ea: `0x1800d423c`
- end: `0x1800d452e`
- name: `?AddTypesFromSchemaProviderExtensions@SchemaRegistryImpl@@AEAAXPEAUHKEY__@@@Z`
- size: `754`
- prototype: `void(SchemaRegistryImpl *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d4534`

## callees

- `0x18000f4b4`
- `0x180016cf4`
- `0x18003e670`
- `0x18003f6c4`
- `0x180053a60`
- `0x18007afd0`
- `0x180091858`
- `0x1800a60f0`
- `0x1800d423c`
- `0x1800d5234`
- `0x1800d5484`
- `0x1801201a0`
- `0x1801a6bf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d429d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d429d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d4310`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d4310`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d43ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d43ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d4468`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d4468`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d440f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d440f`

## string_xrefs

- `0x1800d42ba`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800d449b`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800d44b0`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800d44c5`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800d44da`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800d44ef`: `onecoreuap\shell\cloudstore\metadata\schemaprovider\typeservices.cpp`
- `0x1800d435a`: `Software\Microsoft\Windows\CurrentVersion\CloudStore\SchemaExtensions\`
- `0x1800d4293`: `Software\Microsoft\Windows\CurrentVersion\CloudStore\SchemaExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SchemaRegistryImpl::AddTypesFromSchemaProviderExtensions(SchemaRegistryImpl *this, HKEY a2)
{
  unsigned int v4; // eax
  DWORD i; // ebx
  int v6; // eax
  int v7; // r9d
  WCHAR *v8; // rdx
  HKEY v9; // rcx
  int v10; // eax
  int v11; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  HRESULT v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR String1[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v25[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5C8h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v4 = RegOpenKeyExW(
         a2,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\SchemaExtensions",
         0,
         0x20019u,
         &hKey);
  if ( v4 != 2 )
  {
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x217,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
        (const char *)v4,
        phkResult);
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      v6 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 == -2147024637 )
        break;
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x224,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
          (const char *)(unsigned int)v6,
          phkResulta);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetImpl'::`2'::impl) )
      {
        v8 = Name;
        v9 = hKey;
      }
      else
      {
        v10 = StringCchCopyW(
                v25,
                0x104u,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\SchemaExtensions\\");
        if ( v10 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x238,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
            (const char *)(unsigned int)v10,
            phkResulta);
        v11 = StringCchCatW(v25, 0x104u, Name);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x239,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
            (const char *)(unsigned int)v11,
            phkResulta);
        v8 = v25;
        v9 = HKEY_LOCAL_MACHINE;
      }
      if ( (int)SHRegGetStringEx(v9, v8, L"SchemaType", v7, String1, 0x104u) < 0
        || CompareStringOrdinal(String1, -1, L"FlatBuffers", -1, 1) != 2 )
      {
        pclsid = 0;
        v12 = CLSIDFromString(Name, &pclsid);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x245,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
            (const char *)(unsigned int)v12,
            phkResultb);
        if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
          McTemplateU0j_EventWriteTransfer(retaddr, v13, &pclsid);
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        v14 = CoCreateInstance(&pclsid, 0, 0x401u, &GUID_efe84c27_afa6_485d_a70a_aa2ab5cb6c67, &ppv);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x249,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\metadata\\schemaprovider\\typeservices.cpp",
            (const char *)(unsigned int)v14,
            phkResultc);
        SchemaRegistryImpl::AddTypesFromProvider(this, (struct ICloudStoreSchemaProvider *)ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800d423c  mov     [rsp-8+arg_10], rbx
0x1800d4241  push    rbp
0x1800d4242  push    rdi
0x1800d4243  push    r14
0x1800d4245  lea     rbp, [rsp-5B0h]
0x1800d424d  sub     rsp, 6B0h
0x1800d4254  mov     rax, cs:__security_cookie
0x1800d425b  xor     rax, rsp
0x1800d425e  mov     [rbp+5C0h+var_20], rax
0x1800d4265  mov     rbx, rdx
0x1800d4268  mov     rdi, rcx
0x1800d426b  mov     [rsp+6C0h+hKey], 0
0x1800d4274  xor     edx, edx
0x1800d4276  lea     rcx, [rsp+6C0h+hKey]
0x1800d427b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d4280  lea     rax, [rsp+6C0h+hKey]
0x1800d4285  mov     [rsp+6C0h+phkResult], rax; unsigned int
0x1800d428a  mov     r9d, 20019h; samDesired
0x1800d4290  xor     r8d, r8d; ulOptions
0x1800d4293  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d429a  mov     rcx, rbx; hKey
0x1800d429d  call    cs:__imp_RegOpenKeyExW
0x1800d42a3  cmp     eax, 2
0x1800d42a6  jz      loc_1800D4501
0x1800d42ac  mov     rcx, [rbp+5C8h]; this
0x1800d42b3  test    eax, eax
0x1800d42b5  jz      short loc_1800D42CC
0x1800d42b7  mov     r9d, eax; char *
0x1800d42ba  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800d42c1  mov     edx, 217h; void *
0x1800d42c6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800d42cc  xor     ebx, ebx
0x1800d42ce  mov     r14d, 104h
0x1800d42d4  mov     [rsp+6C0h+cchName], r14d
0x1800d42d9  mov     [rsp+6C0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800d42e2  mov     [rsp+6C0h+lpcchClass], 0; lpcchClass
0x1800d42eb  mov     [rsp+6C0h+lpClass], 0; lpClass
0x1800d42f4  mov     [rsp+6C0h+phkResult], 0; int
0x1800d42fd  lea     r9, [rsp+6C0h+cchName]; lpcchName
0x1800d4302  lea     r8, [rbp+5C0h+Name]; lpName
0x1800d4309  mov     edx, ebx; dwIndex
0x1800d430b  mov     rcx, [rsp+6C0h+hKey]; hKey
0x1800d4310  call    cs:__imp_RegEnumKeyExW
0x1800d4316  test    eax, eax
0x1800d4318  jle     short loc_1800D4322
0x1800d431a  movzx   eax, ax
0x1800d431d  or      eax, 80070000h
0x1800d4322  cmp     eax, 80070103h
0x1800d4327  jz      loc_1800D4501
0x1800d432d  mov     rcx, [rbp+5C8h]; this
0x1800d4334  test    eax, eax
0x1800d4336  js      loc_1800D44EC
0x1800d433c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers> `wil::Feature<__WilFeatureTraits_Feature_CDSFlatBuffers>::GetImpl(void)'::`2'::impl
0x1800d4343  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CDSFlatBuffers@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDSFlatBuffers>::__private_IsEnabled(void)
0x1800d4348  test    al, al
0x1800d434a  jz      short loc_1800D435A
0x1800d434c  lea     rdx, [rbp+5C0h+Name]
0x1800d4353  mov     rcx, [rsp+6C0h+hKey]
0x1800d4358  jmp     short loc_1800D43B2
0x1800d435a  lea     r8, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d4361  mov     rdx, r14; unsigned __int64
0x1800d4364  lea     rcx, [rbp+5C0h+var_230]; unsigned __int16 *
0x1800d436b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d4370  mov     rcx, [rbp+5C8h]; this
0x1800d4377  test    eax, eax
0x1800d4379  js      loc_1800D44D7
0x1800d437f  lea     r8, [rbp+5C0h+Name]; unsigned __int16 *
0x1800d4386  mov     rdx, r14; unsigned __int64
0x1800d4389  lea     rcx, [rbp+5C0h+var_230]; unsigned __int16 *
0x1800d4390  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800d4395  mov     rcx, [rbp+5C8h]; this
0x1800d439c  test    eax, eax
0x1800d439e  js      loc_1800D44C2
0x1800d43a4  lea     rdx, [rbp+5C0h+var_230]; unsigned __int16 *
0x1800d43ab  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800d43b2  mov     dword ptr [rsp+6C0h+lpClass], r14d; unsigned int
0x1800d43b7  lea     rax, [rsp+6C0h+String1]
0x1800d43bc  mov     [rsp+6C0h+phkResult], rax; unsigned __int16 *
0x1800d43c1  lea     r8, aSchematype; "SchemaType"
0x1800d43c8  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1800d43cd  test    eax, eax
0x1800d43cf  js      short loc_1800D43FB
0x1800d43d1  mov     dword ptr [rsp+6C0h+phkResult], 1; int
0x1800d43d9  or      r9d, 0FFFFFFFFh; cchCount2
0x1800d43dd  lea     r8, aFlatbuffers_0; "FlatBuffers"
0x1800d43e4  or      edx, r9d; cchCount1
0x1800d43e7  lea     rcx, [rsp+6C0h+String1]; lpString1
0x1800d43ec  call    cs:__imp_CompareStringOrdinal
0x1800d43f2  cmp     eax, 2
0x1800d43f5  jz      loc_1800D4491
0x1800d43fb  xorps   xmm0, xmm0
0x1800d43fe  movups  xmmword ptr [rsp+6C0h+pclsid.Data1], xmm0
0x1800d4403  lea     rdx, [rsp+6C0h+pclsid]; pclsid
0x1800d4408  lea     rcx, [rbp+5C0h+Name]; lpsz
0x1800d440f  call    cs:__imp_CLSIDFromString
0x1800d4415  mov     rcx, [rbp+5C8h]; this
0x1800d441c  test    eax, eax
0x1800d441e  js      loc_1800D44AD
0x1800d4424  test    cs:Microsoft_Windows_CloudStoreEnableBits, 2
0x1800d442b  jz      short loc_1800D4437
0x1800d442d  lea     r8, [rsp+6C0h+pclsid]
0x1800d4432  call    McTemplateU0j_EventWriteTransfer
0x1800d4437  mov     [rsp+6C0h+ppv], 0
0x1800d4440  lea     rcx, [rsp+6C0h+ppv]
0x1800d4445  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d444a  lea     rax, [rsp+6C0h+ppv]
0x1800d444f  mov     [rsp+6C0h+phkResult], rax; int
0x1800d4454  lea     r9, _GUID_efe84c27_afa6_485d_a70a_aa2ab5cb6c67; riid
0x1800d445b  xor     edx, edx; pUnkOuter
0x1800d445d  mov     r8d, 401h; dwClsContext
0x1800d4463  lea     rcx, [rsp+6C0h+pclsid]; rclsid
0x1800d4468  call    cs:__imp_CoCreateInstance
0x1800d446e  mov     rcx, [rbp+5C8h]; this
0x1800d4475  test    eax, eax
0x1800d4477  js      short loc_1800D4498
0x1800d4479  mov     rdx, [rsp+6C0h+ppv]; struct ICloudStoreSchemaProvider *
0x1800d447e  mov     rcx, rdi; this
0x1800d4481  call    ?AddTypesFromProvider@SchemaRegistryImpl@@AEAAXPEAUICloudStoreSchemaProvider@@@Z; SchemaRegistryImpl::AddTypesFromProvider(ICloudStoreSchemaProvider *)
0x1800d4486  nop
0x1800d4487  lea     rcx, [rsp+6C0h+ppv]
0x1800d448c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d4491  inc     ebx
0x1800d4493  jmp     loc_1800D42D4
0x1800d4498  mov     r9d, eax; char *
0x1800d449b  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800d44a2  mov     edx, 249h; void *
0x1800d44a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d44ad  mov     r9d, eax; char *
0x1800d44b0  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800d44b7  mov     edx, 245h; void *
0x1800d44bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d44c2  mov     r9d, eax; char *
0x1800d44c5  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800d44cc  mov     edx, 239h; void *
0x1800d44d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d44d7  mov     r9d, eax; char *
0x1800d44da  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800d44e1  mov     edx, 238h; void *
0x1800d44e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d44ec  mov     r9d, eax; char *
0x1800d44ef  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\cloudstore\\metadata"...
0x1800d44f6  mov     edx, 224h; void *
0x1800d44fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d4501  lea     rcx, [rsp+6C0h+hKey]
0x1800d4506  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d450b  mov     rcx, [rbp+5C0h+var_20]
0x1800d4512  xor     rcx, rsp; StackCookie
0x1800d4515  call    __security_check_cookie
0x1800d451a  mov     rbx, [rsp+6C0h+arg_10]
0x1800d4522  add     rsp, 6B0h
0x1800d4529  pop     r14
0x1800d452b  pop     rdi
0x1800d452c  pop     rbp
0x1800d452d  retn
```
