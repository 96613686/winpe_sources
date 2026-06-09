# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x18001d5f0`
- end: `0x18001d7ea`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `506`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d0f8`
- `0x18001fba8`

## callees

- `0x1800054dc`
- `0x180012634`
- `0x18001d5f0`
- `0x180021730`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18001d655`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18001d765`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18001d655`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18001d765`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d672`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001d672`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d68b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d68b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d707`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d78c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d707`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d78c`

## string_xrefs

- `0x18001d66b`: `urlmon.dll`
- `0x18001d681`: `CoInternetCreateSecurityManager`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  void *v8; // rcx
  void *v9; // rcx
  HRESULT v10; // ebx
  void *v11; // rcx
  HMODULE v13; // [rsp+50h] [rbp+20h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+28h] BYREF

  ppvOut = a2;
  if ( a1 && a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl) )
    {
      v13 = 0;
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0 )
        goto LABEL_13;
      Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
      v13 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "CoInternetCreateSecurityManager");
        if ( ProcAddress )
        {
          v8 = ppvOut;
          ppvOut = 0;
          if ( v8 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
          if ( ((int (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(0, &ppvOut, 0) >= 0 )
            goto LABEL_13;
        }
      }
      v9 = ppvOut;
      ppvOut = 0;
      if ( v9 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      v10 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut);
      if ( v10 >= 0 )
LABEL_13:
        v10 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1);
      ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&ppvOut);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v13);
    }
    else
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0
        || (v10 = CoCreateInstance(
                    &CLSID_InternetSecurityManager,
                    0,
                    1u,
                    &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                    &ppvOut),
            v10 >= 0) )
      {
        v10 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                1);
        v11 = ppvOut;
        ppvOut = 0;
        if ( v11 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001d5f0  mov     [rsp-18h+arg_10], rbx
0x18001d5f5  mov     [rsp-18h+ppvOut], rdx
0x18001d5fa  push    rbp
0x18001d5fb  push    rsi
0x18001d5fc  push    r14
0x18001d5fe  mov     rbp, rsp
0x18001d601  sub     rsp, 30h
0x18001d605  mov     rsi, r9
0x18001d608  mov     r14, rcx
0x18001d60b  test    rcx, rcx
0x18001d60e  jz      loc_18001D7D5
0x18001d614  test    r9, r9
0x18001d617  jz      loc_18001D7D5
0x18001d61d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x18001d624  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x18001d629  test    al, al
0x18001d62b  jz      loc_18001D749
0x18001d631  mov     [rbp+arg_0], 0
0x18001d639  mov     [rbp+ppvOut], 0
0x18001d641  lea     r9, [rbp+ppvOut]; ppvOut
0x18001d645  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001d64c  lea     rdx, IID_IInternetSecurityManager; guidService
0x18001d653  xor     ecx, ecx; punk
0x18001d655  call    cs:__imp_IUnknown_QueryService
0x18001d65b  test    eax, eax
0x18001d65d  jns     loc_18001D713
0x18001d663  xor     edx, edx; hFile
0x18001d665  mov     r8d, 800h; dwFlags
0x18001d66b  lea     rcx, aUrlmonDll_0; "urlmon.dll"
0x18001d672  call    cs:__imp_LoadLibraryExW
0x18001d678  mov     [rbp+arg_0], rax
0x18001d67c  test    rax, rax
0x18001d67f  jz      short loc_18001D6CC
0x18001d681  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x18001d688  mov     rcx, rax; hModule
0x18001d68b  call    cs:__imp_GetProcAddress
0x18001d691  mov     rbx, rax
0x18001d694  test    rax, rax
0x18001d697  jz      short loc_18001D6CC
0x18001d699  mov     rcx, [rbp+ppvOut]
0x18001d69d  mov     [rbp+ppvOut], 0
0x18001d6a5  test    rcx, rcx
0x18001d6a8  jz      short loc_18001D6B7
0x18001d6aa  mov     rdx, [rcx]
0x18001d6ad  mov     rax, [rdx+10h]
0x18001d6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6b6  nop
0x18001d6b7  xor     r8d, r8d
0x18001d6ba  lea     rdx, [rbp+ppvOut]
0x18001d6be  xor     ecx, ecx
0x18001d6c0  mov     rax, rbx
0x18001d6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6c8  test    eax, eax
0x18001d6ca  jns     short loc_18001D713
0x18001d6cc  mov     rcx, [rbp+ppvOut]
0x18001d6d0  mov     [rbp+ppvOut], 0
0x18001d6d8  test    rcx, rcx
0x18001d6db  jz      short loc_18001D6EA
0x18001d6dd  mov     rax, [rcx]
0x18001d6e0  mov     rax, [rax+10h]
0x18001d6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6e9  nop
0x18001d6ea  lea     rax, [rbp+ppvOut]
0x18001d6ee  mov     [rsp+30h+ppv], rax; ppv
0x18001d6f3  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001d6fa  xor     edx, edx; pUnkOuter
0x18001d6fc  lea     r8d, [rdx+1]; dwClsContext
0x18001d700  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18001d707  call    cs:__imp_CoCreateInstance
0x18001d70d  mov     ebx, eax
0x18001d70f  test    eax, eax
0x18001d711  js      short loc_18001D731
0x18001d713  mov     rcx, [rbp+ppvOut]
0x18001d717  mov     rax, [rcx]
0x18001d71a  mov     r9d, 1
0x18001d720  mov     r8, rsi
0x18001d723  mov     rdx, r14
0x18001d726  mov     rax, [rax+28h]
0x18001d72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d72f  mov     ebx, eax
0x18001d731  lea     rcx, [rbp+ppvOut]
0x18001d735  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x18001d73a  nop
0x18001d73b  lea     rcx, [rbp+arg_0]
0x18001d73f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001d744  jmp     loc_18001D7DA
0x18001d749  mov     [rbp+ppvOut], 0
0x18001d751  lea     r9, [rbp+ppvOut]; ppvOut
0x18001d755  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001d75c  lea     rdx, IID_IInternetSecurityManager; guidService
0x18001d763  xor     ecx, ecx; punk
0x18001d765  call    cs:__imp_IUnknown_QueryService
0x18001d76b  test    eax, eax
0x18001d76d  jns     short loc_18001D798
0x18001d76f  lea     rax, [rbp+ppvOut]
0x18001d773  mov     [rsp+30h+ppv], rax; ppv
0x18001d778  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18001d77f  xor     edx, edx; pUnkOuter
0x18001d781  lea     r8d, [rdx+1]; dwClsContext
0x18001d785  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18001d78c  call    cs:__imp_CoCreateInstance
0x18001d792  mov     ebx, eax
0x18001d794  test    eax, eax
0x18001d796  js      short loc_18001D7DA
0x18001d798  mov     rcx, [rbp+ppvOut]
0x18001d79c  mov     rax, [rcx]
0x18001d79f  mov     r9d, 1
0x18001d7a5  mov     r8, rsi
0x18001d7a8  mov     rdx, r14
0x18001d7ab  mov     rax, [rax+28h]
0x18001d7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b4  mov     ebx, eax
0x18001d7b6  mov     rcx, [rbp+ppvOut]
0x18001d7ba  mov     [rbp+ppvOut], 0
0x18001d7c2  test    rcx, rcx
0x18001d7c5  jz      short loc_18001D7DA
0x18001d7c7  mov     rax, [rcx]
0x18001d7ca  mov     rax, [rax+10h]
0x18001d7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d3  jmp     short loc_18001D7DA
0x18001d7d5  mov     ebx, 80070057h
0x18001d7da  mov     eax, ebx
0x18001d7dc  mov     rbx, [rsp+30h+arg_10]
0x18001d7e1  add     rsp, 30h
0x18001d7e5  pop     r14
0x18001d7e7  pop     rsi
0x18001d7e8  pop     rbp
0x18001d7e9  retn
```
