# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x180079be4`
- end: `0x180079dde`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `506`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, __int64, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ab0c`
- `0x18007ae34`
- `0x18008c438`
- `0x18008c760`

## callees

- `0x180063f24`
- `0x180078224`
- `0x180079be4`
- `0x18007d688`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180079c49`
- `SHCORE!IUnknown_QueryService` at `0x180079d59`
- `SHCORE!IUnknown_QueryService` at `0x180079c49`
- `SHCORE!IUnknown_QueryService` at `0x180079d59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079c7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079c7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079c66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079c66`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079cfb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079d80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079cfb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180079d80`

## string_xrefs

- `0x180079c5f`: `urlmon.dll`
- `0x180079c75`: `CoInternetCreateSecurityManager`

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
      wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&ppvOut);
      SearchFolderInstance::~SearchFolderInstance((SearchFolderInstance *)&v13);
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
0x180079be4  mov     [rsp-18h+arg_10], rbx
0x180079be9  mov     [rsp-18h+ppvOut], rdx
0x180079bee  push    rbp
0x180079bef  push    rsi
0x180079bf0  push    r14
0x180079bf2  mov     rbp, rsp
0x180079bf5  sub     rsp, 30h
0x180079bf9  mov     rsi, r9
0x180079bfc  mov     r14, rcx
0x180079bff  test    rcx, rcx
0x180079c02  jz      loc_180079DC9
0x180079c08  test    r9, r9
0x180079c0b  jz      loc_180079DC9
0x180079c11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x180079c18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x180079c1d  test    al, al
0x180079c1f  jz      loc_180079D3D
0x180079c25  mov     [rbp+arg_0], 0
0x180079c2d  mov     [rbp+ppvOut], 0
0x180079c35  lea     r9, [rbp+ppvOut]; ppvOut
0x180079c39  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180079c40  lea     rdx, IID_IInternetSecurityManager; guidService
0x180079c47  xor     ecx, ecx; punk
0x180079c49  call    cs:__imp_IUnknown_QueryService
0x180079c4f  test    eax, eax
0x180079c51  jns     loc_180079D07
0x180079c57  xor     edx, edx; hFile
0x180079c59  mov     r8d, 800h; dwFlags
0x180079c5f  lea     rcx, aUrlmonDll_0; "urlmon.dll"
0x180079c66  call    cs:__imp_LoadLibraryExW
0x180079c6c  mov     [rbp+arg_0], rax
0x180079c70  test    rax, rax
0x180079c73  jz      short loc_180079CC0
0x180079c75  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x180079c7c  mov     rcx, rax; hModule
0x180079c7f  call    cs:__imp_GetProcAddress
0x180079c85  mov     rbx, rax
0x180079c88  test    rax, rax
0x180079c8b  jz      short loc_180079CC0
0x180079c8d  mov     rcx, [rbp+ppvOut]
0x180079c91  mov     [rbp+ppvOut], 0
0x180079c99  test    rcx, rcx
0x180079c9c  jz      short loc_180079CAB
0x180079c9e  mov     rdx, [rcx]
0x180079ca1  mov     rax, [rdx+10h]
0x180079ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079caa  nop
0x180079cab  xor     r8d, r8d
0x180079cae  lea     rdx, [rbp+ppvOut]
0x180079cb2  xor     ecx, ecx
0x180079cb4  mov     rax, rbx
0x180079cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079cbc  test    eax, eax
0x180079cbe  jns     short loc_180079D07
0x180079cc0  mov     rcx, [rbp+ppvOut]
0x180079cc4  mov     [rbp+ppvOut], 0
0x180079ccc  test    rcx, rcx
0x180079ccf  jz      short loc_180079CDE
0x180079cd1  mov     rax, [rcx]
0x180079cd4  mov     rax, [rax+10h]
0x180079cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079cdd  nop
0x180079cde  lea     rax, [rbp+ppvOut]
0x180079ce2  mov     [rsp+30h+ppv], rax; ppv
0x180079ce7  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180079cee  xor     edx, edx; pUnkOuter
0x180079cf0  lea     r8d, [rdx+1]; dwClsContext
0x180079cf4  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180079cfb  call    cs:__imp_CoCreateInstance
0x180079d01  mov     ebx, eax
0x180079d03  test    eax, eax
0x180079d05  js      short loc_180079D25
0x180079d07  mov     rcx, [rbp+ppvOut]
0x180079d0b  mov     rax, [rcx]
0x180079d0e  mov     r9d, 1
0x180079d14  mov     r8, rsi
0x180079d17  mov     rdx, r14
0x180079d1a  mov     rax, [rax+28h]
0x180079d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d23  mov     ebx, eax
0x180079d25  lea     rcx, [rbp+ppvOut]
0x180079d29  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180079d2e  nop
0x180079d2f  lea     rcx, [rbp+arg_0]; this
0x180079d33  call    ??1SearchFolderInstance@@QEAA@XZ; SearchFolderInstance::~SearchFolderInstance(void)
0x180079d38  jmp     loc_180079DCE
0x180079d3d  mov     [rbp+ppvOut], 0
0x180079d45  lea     r9, [rbp+ppvOut]; ppvOut
0x180079d49  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180079d50  lea     rdx, IID_IInternetSecurityManager; guidService
0x180079d57  xor     ecx, ecx; punk
0x180079d59  call    cs:__imp_IUnknown_QueryService
0x180079d5f  test    eax, eax
0x180079d61  jns     short loc_180079D8C
0x180079d63  lea     rax, [rbp+ppvOut]
0x180079d67  mov     [rsp+30h+ppv], rax; ppv
0x180079d6c  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180079d73  xor     edx, edx; pUnkOuter
0x180079d75  lea     r8d, [rdx+1]; dwClsContext
0x180079d79  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180079d80  call    cs:__imp_CoCreateInstance
0x180079d86  mov     ebx, eax
0x180079d88  test    eax, eax
0x180079d8a  js      short loc_180079DCE
0x180079d8c  mov     rcx, [rbp+ppvOut]
0x180079d90  mov     rax, [rcx]
0x180079d93  mov     r9d, 1
0x180079d99  mov     r8, rsi
0x180079d9c  mov     rdx, r14
0x180079d9f  mov     rax, [rax+28h]
0x180079da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079da8  mov     ebx, eax
0x180079daa  mov     rcx, [rbp+ppvOut]
0x180079dae  mov     [rbp+ppvOut], 0
0x180079db6  test    rcx, rcx
0x180079db9  jz      short loc_180079DCE
0x180079dbb  mov     rax, [rcx]
0x180079dbe  mov     rax, [rax+10h]
0x180079dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079dc7  jmp     short loc_180079DCE
0x180079dc9  mov     ebx, 80070057h
0x180079dce  mov     eax, ebx
0x180079dd0  mov     rbx, [rsp+30h+arg_10]
0x180079dd5  add     rsp, 30h
0x180079dd9  pop     r14
0x180079ddb  pop     rsi
0x180079ddc  pop     rbp
0x180079ddd  retn
```
