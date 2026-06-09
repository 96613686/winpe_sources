# NgcFirst::SetSwitchCounts

- ea: `0x180044714`
- end: `0x18004489a`
- name: `NgcFirst::SetSwitchCounts`
- size: `390`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, BYTE *lpData, BYTE *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042a1c`
- `0x180042e40`

## callees

- `0x18000782c`
- `0x180032b6c`
- `0x180032c20`
- `0x180044714`
- `0x180048304`
- `0x180085ba0`
- `0x180085e40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800447ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800447ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044824`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004486b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044824`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004486b`

## string_xrefs

- `0x180044773`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044838`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`

## pseudocode

```c
__int64 __fastcall NgcFirst::SetSwitchCounts(LPCWSTR lpSubKey, BYTE *lpData, BYTE *a3)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
    return NgcFirst::SetSwitchCountsHelper(
             lpSubKey,
             L"ConsecutiveSwitchCount",
             (unsigned int)lpData,
             L"MaxSwitchCount",
             a3);
  if ( lpSubKey )
  {
    if ( !lpData && !a3 )
    {
      v7 = -2147024809;
      v8 = 501;
      goto LABEL_5;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v9 )
    {
      v10 = 514;
    }
    else if ( lpData && (v9 = RegSetValueExW(hKey, L"ConsecutiveSwitchCount", 0, 4u, lpData, 4u)) != 0 )
    {
      v10 = 525;
    }
    else
    {
      if ( !a3 || (v9 = RegSetValueExW(hKey, L"MaxSwitchCount", 0, 4u, a3, 4u)) == 0 )
      {
        v7 = 0;
        goto LABEL_19;
      }
      v10 = 537;
    }
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
           (const char *)v9,
           dwOptionsa);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v7;
  }
  v7 = -2147467261;
  v8 = 500;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
    (const char *)v7,
    dwOptions);
  return v7;
}

```

## disassembly

```asm
0x180044714  mov     [rsp+arg_0], rbx
0x180044719  mov     [rsp+arg_8], rsi
0x18004471e  push    rdi
0x18004471f  sub     rsp, 50h
0x180044723  mov     rdi, r8
0x180044726  mov     rbx, rdx
0x180044729  mov     rsi, rcx
0x18004472c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst> `wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl(void)'::`2'::impl
0x180044733  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(void)
0x180044738  test    al, al
0x18004473a  jz      short loc_18004475F
0x18004473c  lea     r9, aMaxswitchcount; "MaxSwitchCount"
0x180044743  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x180044748  mov     r8, rbx; unsigned int
0x18004474b  lea     rdx, aConsecutiveswi; "ConsecutiveSwitchCount"
0x180044752  mov     rcx, rsi; lpSubKey
0x180044755  call    NgcFirst__SetSwitchCountsHelper
0x18004475a  jmp     loc_18004488A
0x18004475f  test    rsi, rsi
0x180044762  jnz     short loc_180044787
0x180044764  mov     ebx, 80004003h
0x180044769  mov     edx, 1F4h; void *
0x18004476e  mov     rcx, [rsp+58h]; this
0x180044773  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x18004477a  mov     r9d, ebx; char *
0x18004477d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044782  jmp     loc_180044888
0x180044787  test    rbx, rbx
0x18004478a  jnz     short loc_18004479D
0x18004478c  test    rdi, rdi
0x18004478f  jnz     short loc_18004479D
0x180044791  mov     ebx, 80070057h
0x180044796  mov     edx, 1F5h
0x18004479b  jmp     short loc_18004476E
0x18004479d  xor     edx, edx
0x18004479f  mov     [rsp+58h+hKey], 0
0x1800447a8  lea     rcx, [rsp+58h+hKey]
0x1800447ad  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800447b2  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800447bb  lea     rax, [rsp+58h+hKey]
0x1800447c0  mov     [rsp+58h+phkResult], rax; phkResult
0x1800447c5  xor     r9d, r9d; lpClass
0x1800447c8  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800447d1  xor     r8d, r8d; Reserved
0x1800447d4  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800447dc  mov     rdx, rsi; lpSubKey
0x1800447df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800447e6  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800447ee  call    cs:__imp_RegCreateKeyExW
0x1800447f4  test    eax, eax
0x1800447f6  jz      short loc_1800447FF
0x1800447f8  mov     edx, 202h
0x1800447fd  jmp     short loc_180044833
0x1800447ff  mov     esi, 4
0x180044804  test    rbx, rbx
0x180044807  jz      short loc_18004484B
0x180044809  mov     rcx, [rsp+58h+hKey]; hKey
0x18004480e  lea     rdx, aConsecutiveswi; "ConsecutiveSwitchCount"
0x180044815  mov     [rsp+58h+samDesired], esi; cbData
0x180044819  mov     r9d, esi; dwType
0x18004481c  xor     r8d, r8d; Reserved
0x18004481f  mov     qword ptr [rsp+58h+dwOptions], rbx; unsigned int
0x180044824  call    cs:__imp_RegSetValueExW
0x18004482a  test    eax, eax
0x18004482c  jz      short loc_18004484B
0x18004482e  mov     edx, 20Dh; void *
0x180044833  mov     rcx, [rsp+58h]; this
0x180044838  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x18004483f  mov     r9d, eax; char *
0x180044842  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044847  mov     ebx, eax
0x180044849  jmp     short loc_18004487E
0x18004484b  test    rdi, rdi
0x18004484e  jz      short loc_18004487C
0x180044850  mov     rcx, [rsp+58h+hKey]; hKey
0x180044855  lea     rdx, aMaxswitchcount; "MaxSwitchCount"
0x18004485c  mov     [rsp+58h+samDesired], esi; cbData
0x180044860  mov     r9d, esi; dwType
0x180044863  xor     r8d, r8d; Reserved
0x180044866  mov     qword ptr [rsp+58h+dwOptions], rdi; lpData
0x18004486b  call    cs:__imp_RegSetValueExW
0x180044871  test    eax, eax
0x180044873  jz      short loc_18004487C
0x180044875  mov     edx, 219h
0x18004487a  jmp     short loc_180044833
0x18004487c  xor     ebx, ebx
0x18004487e  lea     rcx, [rsp+58h+hKey]
0x180044883  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044888  mov     eax, ebx
0x18004488a  mov     rbx, [rsp+58h+arg_0]
0x18004488f  mov     rsi, [rsp+58h+arg_8]
0x180044894  add     rsp, 50h
0x180044898  pop     rdi
0x180044899  retn
```
