# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x180009f04`
- end: `0x18000a0dd`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `473`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a0e4`

## callees

- `0x180009f04`
- `0x18000a368`
- `0x180017010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000a054`
- `KERNEL32!FreeLibrary` at `0x18000a054`
- `KERNEL32!LoadLibraryExW` at `0x180009f7e`
- `KERNEL32!LoadLibraryExW` at `0x180009f7e`
- `KERNEL32!GetProcAddress` at `0x180009f96`
- `KERNEL32!GetProcAddress` at `0x180009f96`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180009f61`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a064`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180009f61`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a064`
- `ole32!CoCreateInstance` at `0x18000a010`
- `ole32!CoCreateInstance` at `0x18000a08b`
- `ole32!CoCreateInstance` at `0x18000a010`
- `ole32!CoCreateInstance` at `0x18000a08b`

## string_xrefs

- `0x180009f71`: `urlmon.dll`
- `0x180009f8c`: `CoInternetCreateSecurityManager`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, unsigned int a3, unsigned int *a4)
{
  HMODULE v7; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  void *v10; // rcx
  void *v11; // rcx
  HRESULT v12; // edi
  void *ppvOut; // [rsp+78h] [rbp+40h] BYREF

  ppvOut = a2;
  if ( a1 && a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl) )
    {
      v7 = 0;
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0 )
        goto LABEL_13;
      Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
      v7 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "CoInternetCreateSecurityManager");
        if ( ProcAddress )
        {
          v10 = ppvOut;
          ppvOut = 0;
          if ( v10 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
          if ( ((int (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(0, &ppvOut, 0) >= 0 )
            goto LABEL_13;
        }
      }
      v11 = ppvOut;
      ppvOut = 0;
      if ( v11 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      v12 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut);
      if ( v12 >= 0 )
LABEL_13:
        v12 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)ppvOut
                                                                                                  + 40LL))(
                ppvOut,
                a1,
                a4,
                a3);
      if ( ppvOut )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      if ( v7 )
        FreeLibrary(v7);
    }
    else
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0
        || (v12 = CoCreateInstance(
                    &CLSID_InternetSecurityManager,
                    0,
                    1u,
                    &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                    &ppvOut),
            v12 >= 0) )
      {
        v12 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)ppvOut
                                                                                                  + 40LL))(
                ppvOut,
                a1,
                a4,
                a3);
        if ( ppvOut )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180009f04  mov     [rsp-30h+ppvOut], rdx
0x180009f09  push    rbp
0x180009f0a  push    rbx
0x180009f0b  push    rsi
0x180009f0c  push    rdi
0x180009f0d  push    r14
0x180009f0f  push    r15
0x180009f11  mov     rbp, rsp
0x180009f14  sub     rsp, 38h
0x180009f18  mov     rsi, r9
0x180009f1b  mov     r15d, r8d
0x180009f1e  mov     r14, rcx
0x180009f21  test    rcx, rcx
0x180009f24  jz      loc_18000A0C9
0x180009f2a  test    r9, r9
0x180009f2d  jz      loc_18000A0C9
0x180009f33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x180009f3a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x180009f3f  xor     ecx, ecx; punk
0x180009f41  lea     r9, [rbp+ppvOut]; ppvOut
0x180009f45  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180009f4c  lea     rdx, IID_IInternetSecurityManager; guidService
0x180009f53  test    al, al
0x180009f55  jz      loc_18000A05C
0x180009f5b  xor     ebx, ebx
0x180009f5d  mov     [rbp+ppvOut], rbx
0x180009f61  call    cs:__imp_IUnknown_QueryService
0x180009f67  test    eax, eax
0x180009f69  jns     loc_18000A01C
0x180009f6f  xor     edx, edx; hFile
0x180009f71  lea     rcx, LibFileName; "urlmon.dll"
0x180009f78  mov     r8d, 800h; dwFlags
0x180009f7e  call    cs:__imp_LoadLibraryExW
0x180009f84  mov     rbx, rax
0x180009f87  test    rax, rax
0x180009f8a  jz      short loc_180009FD6
0x180009f8c  lea     rdx, aCointernetcrea; "CoInternetCreateSecurityManager"
0x180009f93  mov     rcx, rax; hModule
0x180009f96  call    cs:__imp_GetProcAddress
0x180009f9c  mov     rdi, rax
0x180009f9f  test    rax, rax
0x180009fa2  jz      short loc_180009FD6
0x180009fa4  mov     rcx, [rbp+ppvOut]
0x180009fa8  mov     [rbp+ppvOut], 0
0x180009fb0  test    rcx, rcx
0x180009fb3  jz      short loc_180009FC1
0x180009fb5  mov     rdx, [rcx]
0x180009fb8  mov     rax, [rdx+10h]
0x180009fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc1  xor     r8d, r8d
0x180009fc4  lea     rdx, [rbp+ppvOut]
0x180009fc8  xor     ecx, ecx
0x180009fca  mov     rax, rdi
0x180009fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd2  test    eax, eax
0x180009fd4  jns     short loc_18000A01C
0x180009fd6  mov     rcx, [rbp+ppvOut]
0x180009fda  mov     [rbp+ppvOut], 0
0x180009fe2  test    rcx, rcx
0x180009fe5  jz      short loc_180009FF3
0x180009fe7  mov     rax, [rcx]
0x180009fea  mov     rax, [rax+10h]
0x180009fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff3  xor     edx, edx; pUnkOuter
0x180009ff5  lea     rax, [rbp+ppvOut]
0x180009ff9  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18000a000  mov     [rsp+38h+ppv], rax; ppv
0x18000a005  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18000a00c  lea     r8d, [rdx+1]; dwClsContext
0x18000a010  call    cs:__imp_CoCreateInstance
0x18000a016  mov     edi, eax
0x18000a018  test    eax, eax
0x18000a01a  js      short loc_18000A037
0x18000a01c  mov     rcx, [rbp+ppvOut]
0x18000a020  mov     r9d, r15d
0x18000a023  mov     r8, rsi
0x18000a026  mov     rdx, r14
0x18000a029  mov     rax, [rcx]
0x18000a02c  mov     rax, [rax+28h]
0x18000a030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a035  mov     edi, eax
0x18000a037  mov     rcx, [rbp+ppvOut]
0x18000a03b  test    rcx, rcx
0x18000a03e  jz      short loc_18000A04C
0x18000a040  mov     rax, [rcx]
0x18000a043  mov     rax, [rax+10h]
0x18000a047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a04c  test    rbx, rbx
0x18000a04f  jz      short loc_18000A0CE
0x18000a051  mov     rcx, rbx; hLibModule
0x18000a054  call    cs:__imp_FreeLibrary
0x18000a05a  jmp     short loc_18000A0CE
0x18000a05c  mov     [rbp+ppvOut], 0
0x18000a064  call    cs:__imp_IUnknown_QueryService
0x18000a06a  test    eax, eax
0x18000a06c  jns     short loc_18000A097
0x18000a06e  xor     edx, edx; pUnkOuter
0x18000a070  lea     rax, [rbp+ppvOut]
0x18000a074  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18000a07b  mov     [rsp+38h+ppv], rax; ppv
0x18000a080  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18000a087  lea     r8d, [rdx+1]; dwClsContext
0x18000a08b  call    cs:__imp_CoCreateInstance
0x18000a091  mov     edi, eax
0x18000a093  test    eax, eax
0x18000a095  js      short loc_18000A0CE
0x18000a097  mov     rcx, [rbp+ppvOut]
0x18000a09b  mov     r9d, r15d
0x18000a09e  mov     r8, rsi
0x18000a0a1  mov     rdx, r14
0x18000a0a4  mov     rax, [rcx]
0x18000a0a7  mov     rax, [rax+28h]
0x18000a0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0b0  mov     rcx, [rbp+ppvOut]
0x18000a0b4  mov     edi, eax
0x18000a0b6  test    rcx, rcx
0x18000a0b9  jz      short loc_18000A0CE
0x18000a0bb  mov     rax, [rcx]
0x18000a0be  mov     rax, [rax+10h]
0x18000a0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c7  jmp     short loc_18000A0CE
0x18000a0c9  mov     edi, 80070057h
0x18000a0ce  mov     eax, edi
0x18000a0d0  add     rsp, 38h
0x18000a0d4  pop     r15
0x18000a0d6  pop     r14
0x18000a0d8  pop     rdi
0x18000a0d9  pop     rsi
0x18000a0da  pop     rbx
0x18000a0db  pop     rbp
0x18000a0dc  retn
```
