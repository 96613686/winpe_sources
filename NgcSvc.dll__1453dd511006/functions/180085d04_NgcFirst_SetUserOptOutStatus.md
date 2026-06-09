# NgcFirst::SetUserOptOutStatus

- ea: `0x180085d04`
- end: `0x180085e38`
- name: `NgcFirst::SetUserOptOutStatus`
- size: `308`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042e40`

## callees

- `0x18000782c`
- `0x180032b6c`
- `0x180032c20`
- `0x180048304`
- `0x180085d04`
- `0x180085e40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085d96`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085d96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085ddb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085e09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085ddb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085e09`

## string_xrefs

- `0x180085d2f`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180085df2`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFirst::SetUserOptOutStatus(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned __int8 a3)
{
  int v3; // edi
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v3 = a3;
  if ( lpSubKey )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v7 )
    {
      v8 = 400;
LABEL_8:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v8,
             (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
             (const char *)v7,
             dwOptionsa);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v6;
    }
    Data = v3;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
    {
      v7 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
      if ( v7 )
      {
        v8 = 412;
        goto LABEL_8;
      }
    }
    else
    {
      v7 = RegSetValueExW(hKey, L"OptOut", 0, 4u, (const BYTE *)&Data, 4u);
      if ( v7 )
      {
        v8 = 423;
        goto LABEL_8;
      }
    }
    v6 = 0;
    goto LABEL_12;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x183,
    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
    (const char *)0x80004003LL,
    dwOptions);
  return v6;
}

```

## disassembly

```asm
0x180085d04  mov     [rsp+arg_8], rbx
0x180085d09  mov     [rsp+arg_10], rsi
0x180085d0e  push    rdi
0x180085d0f  sub     rsp, 50h
0x180085d13  movzx   edi, r8b
0x180085d17  mov     rsi, rdx
0x180085d1a  mov     rbx, rcx
0x180085d1d  test    rcx, rcx
0x180085d20  jnz     short loc_180085D45
0x180085d22  mov     rcx, [rsp+58h]; this
0x180085d27  mov     ebx, 80004003h
0x180085d2c  mov     r9d, ebx; char *
0x180085d2f  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180085d36  mov     edx, 183h; void *
0x180085d3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085d40  jmp     loc_180085E26
0x180085d45  mov     [rsp+58h+hKey], 0
0x180085d4e  xor     edx, edx
0x180085d50  lea     rcx, [rsp+58h+hKey]
0x180085d55  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180085d5a  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180085d63  lea     rax, [rsp+58h+hKey]
0x180085d68  mov     [rsp+58h+phkResult], rax; phkResult
0x180085d6d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180085d76  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180085d7e  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180085d86  xor     r9d, r9d; lpClass
0x180085d89  xor     r8d, r8d; Reserved
0x180085d8c  mov     rdx, rbx; lpSubKey
0x180085d8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180085d96  call    cs:__imp_RegCreateKeyExW
0x180085d9c  test    eax, eax
0x180085d9e  jz      short loc_180085DA7
0x180085da0  mov     edx, 190h
0x180085da5  jmp     short loc_180085DEA
0x180085da7  mov     [rsp+58h+Data], edi
0x180085dab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst> `wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl(void)'::`2'::impl
0x180085db2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(void)
0x180085db7  mov     r9d, 4; dwType
0x180085dbd  xor     r8d, r8d; Reserved
0x180085dc0  mov     rcx, [rsp+58h+hKey]; hKey
0x180085dc5  mov     [rsp+58h+samDesired], r9d; cbData
0x180085dca  test    al, al
0x180085dcc  lea     rax, [rsp+58h+Data]
0x180085dd1  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x180085dd6  jz      short loc_180085E02
0x180085dd8  mov     rdx, rsi; lpValueName
0x180085ddb  call    cs:__imp_RegSetValueExW
0x180085de1  test    eax, eax
0x180085de3  jz      short loc_180085E1A
0x180085de5  mov     edx, 19Ch; void *
0x180085dea  mov     rcx, [rsp+58h]; this
0x180085def  mov     r9d, eax; char *
0x180085df2  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180085df9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180085dfe  mov     ebx, eax
0x180085e00  jmp     short loc_180085E1C
0x180085e02  lea     rdx, aOptout; "OptOut"
0x180085e09  call    cs:__imp_RegSetValueExW
0x180085e0f  test    eax, eax
0x180085e11  jz      short loc_180085E1A
0x180085e13  mov     edx, 1A7h
0x180085e18  jmp     short loc_180085DEA
0x180085e1a  xor     ebx, ebx
0x180085e1c  lea     rcx, [rsp+58h+hKey]
0x180085e21  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180085e26  mov     eax, ebx
0x180085e28  mov     rbx, [rsp+58h+arg_8]
0x180085e2d  mov     rsi, [rsp+58h+arg_10]
0x180085e32  add     rsp, 50h
0x180085e36  pop     rdi
0x180085e37  retn
```
