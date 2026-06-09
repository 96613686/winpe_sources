# CDPComUserSettingsProvider::GetRomeSdkChannelAuthorizationSetting(uint *)

- ea: `0x1800181b0`
- end: `0x18001830a`
- name: `?GetRomeSdkChannelAuthorizationSetting@CDPComUserSettingsProvider@@UEAAJPEAI@Z`
- size: `346`
- prototype: `__int64 __fastcall(CDPComUserSettingsProvider *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000db78`
- `0x1800181b0`
- `0x180020cc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001825e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800182f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001825e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800182f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800182a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800182a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001821c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001821c`

## string_xrefs

- `0x1800181dc`: `..\cdpcomusersettingsprovider.cpp`
- `0x180018245`: `..\cdpcomusersettingsprovider.cpp`
- `0x1800182cb`: `..\cdpcomusersettingsprovider.cpp`

## pseudocode

```c
__int64 __fastcall CDPComUserSettingsProvider::GetRomeSdkChannelAuthorizationSetting(
        CDPComUserSettingsProvider *this,
        unsigned int *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  bool v7; // sf
  int ValueA; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  bool v11; // sf
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v14; // [rsp+68h] [rbp+18h] BYREF
  unsigned int pvData; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+78h] [rbp+28h] BYREF

  if ( !a2 )
  {
    v14 = -2147024809;
    v16 = 29;
    Log<long &,char const (&)[40],int>((__int64)this, 0, &v14, "..\\cdpcomusersettingsprovider.cpp", &v16);
    return v14;
  }
  hKey = 0;
  v4 = RegOpenKeyExA(HKEY_CURRENT_USER, "Software\\Microsoft\\Windows\\CurrentVersion\\CDP", 0, 0x20019u, &hKey);
  v7 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
    v7 = v4 < 0;
  }
  if ( v7 )
  {
    v14 = v4;
    v16 = 33;
    Log<long &,char const (&)[40],int>(v6, v5, &v14, "..\\cdpcomusersettingsprovider.cpp", &v16);
    if ( hKey )
      RegCloseKey(hKey);
    return v14;
  }
  pvData = 0;
  pcbData = 4;
  ValueA = RegGetValueA(hKey, 0, "RomeSdkChannelUserAuthzPolicy", 0x10u, 0, &pvData, &pcbData);
  v11 = ValueA < 0;
  if ( ValueA > 0 )
  {
    ValueA = (unsigned __int16)ValueA | 0x80070000;
    v11 = ValueA < 0;
  }
  if ( v11 )
  {
    v14 = ValueA;
    v16 = 38;
    Log<long &,char const (&)[40],int>(v10, v9, &v14, "..\\cdpcomusersettingsprovider.cpp", &v16);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v14;
  }
  *a2 = pvData;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800181b0  mov     [rsp-8+arg_0], rbx
0x1800181b5  push    rbp
0x1800181b6  mov     rbp, rsp
0x1800181b9  sub     rsp, 50h
0x1800181bd  mov     rbx, rdx
0x1800181c0  test    rdx, rdx
0x1800181c3  jnz     short loc_1800181F4
0x1800181c5  mov     [rbp+arg_8], 80070057h
0x1800181cc  mov     [rbp+arg_18], 1Dh
0x1800181d3  lea     rax, [rbp+arg_18]
0x1800181d7  mov     [rsp+50h+phkResult], rax
0x1800181dc  lea     r9, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x1800181e3  lea     r8, [rbp+arg_8]
0x1800181e7  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800181ec  mov     eax, [rbp+arg_8]
0x1800181ef  jmp     loc_1800182FF
0x1800181f4  mov     [rbp+hKey], 0
0x1800181fc  lea     rax, [rbp+hKey]
0x180018200  mov     [rsp+50h+phkResult], rax; phkResult
0x180018205  mov     r9d, 20019h; samDesired
0x18001820b  xor     r8d, r8d; ulOptions
0x18001820e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018215  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001821c  call    cs:__imp_RegOpenKeyExA
0x180018222  test    eax, eax
0x180018224  jle     short loc_180018230
0x180018226  movzx   eax, ax
0x180018229  or      eax, 80070000h
0x18001822e  test    eax, eax
0x180018230  jns     short loc_180018266
0x180018232  mov     [rbp+arg_8], eax
0x180018235  mov     [rbp+arg_18], 21h ; '!'
0x18001823c  lea     rax, [rbp+arg_18]
0x180018240  mov     [rsp+50h+phkResult], rax
0x180018245  lea     r9, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x18001824c  lea     r8, [rbp+arg_8]
0x180018250  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x180018255  mov     rcx, [rbp+hKey]; hKey
0x180018259  test    rcx, rcx
0x18001825c  jz      short loc_1800181EC
0x18001825e  call    cs:__imp_RegCloseKey
0x180018264  jmp     short loc_1800181EC
0x180018266  mov     [rbp+arg_10], 0
0x18001826d  mov     [rbp+var_10], 4
0x180018274  lea     rax, [rbp+var_10]
0x180018278  mov     [rsp+50h+pcbData], rax; pcbData
0x18001827d  lea     rax, [rbp+arg_10]
0x180018281  mov     [rsp+50h+pvData], rax; pvData
0x180018286  mov     [rsp+50h+phkResult], 0; pdwType
0x18001828f  mov     r9d, 10h; dwFlags
0x180018295  lea     r8, aRomesdkchannel; "RomeSdkChannelUserAuthzPolicy"
0x18001829c  xor     edx, edx; lpSubKey
0x18001829e  mov     rcx, [rbp+hKey]; hkey
0x1800182a2  call    cs:__imp_RegGetValueA
0x1800182a8  test    eax, eax
0x1800182aa  jle     short loc_1800182B6
0x1800182ac  movzx   eax, ax
0x1800182af  or      eax, 80070000h
0x1800182b4  test    eax, eax
0x1800182b6  jns     short loc_1800182E9
0x1800182b8  mov     [rbp+arg_8], eax
0x1800182bb  mov     [rbp+arg_18], 26h ; '&'
0x1800182c2  lea     rax, [rbp+arg_18]
0x1800182c6  mov     [rsp+50h+phkResult], rax
0x1800182cb  lea     r9, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x1800182d2  lea     r8, [rbp+arg_8]
0x1800182d6  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800182db  lea     rcx, [rbp+hKey]
0x1800182df  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800182e4  jmp     loc_1800181EC
0x1800182e9  mov     eax, [rbp+arg_10]
0x1800182ec  mov     [rbx], eax
0x1800182ee  mov     rcx, [rbp+hKey]; hKey
0x1800182f2  test    rcx, rcx
0x1800182f5  jz      short loc_1800182FD
0x1800182f7  call    cs:__imp_RegCloseKey
0x1800182fd  xor     eax, eax
0x1800182ff  mov     rbx, [rsp+50h+arg_0]
0x180018304  add     rsp, 50h
0x180018308  pop     rbp
0x180018309  retn
```
