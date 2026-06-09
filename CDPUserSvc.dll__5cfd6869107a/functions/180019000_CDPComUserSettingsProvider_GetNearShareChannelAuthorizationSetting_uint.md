# CDPComUserSettingsProvider::GetNearShareChannelAuthorizationSetting(uint *)

- ea: `0x180019000`
- end: `0x18001914d`
- name: `?GetNearShareChannelAuthorizationSetting@CDPComUserSettingsProvider@@UEAAJPEAI@Z`
- size: `333`
- prototype: `__int64 __fastcall(CDPComUserSettingsProvider *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000db78`
- `0x180019000`
- `0x180020cc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800190ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800190ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800190f2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800190f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001906c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001906c`

## string_xrefs

- `0x18001902c`: `..\cdpcomusersettingsprovider.cpp`
- `0x180019095`: `..\cdpcomusersettingsprovider.cpp`
- `0x18001911b`: `..\cdpcomusersettingsprovider.cpp`

## pseudocode

```c
__int64 __fastcall CDPComUserSettingsProvider::GetNearShareChannelAuthorizationSetting(
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
  unsigned int v12; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v15; // [rsp+68h] [rbp+18h] BYREF
  unsigned int pvData; // [rsp+70h] [rbp+20h] BYREF
  int v17; // [rsp+78h] [rbp+28h] BYREF

  if ( !a2 )
  {
    v15 = -2147024809;
    v17 = 47;
    Log<long &,char const (&)[40],int>((__int64)this, 0, &v15, "..\\cdpcomusersettingsprovider.cpp", &v17);
    return v15;
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
    v15 = v4;
    v17 = 51;
    Log<long &,char const (&)[40],int>(v6, v5, &v15, "..\\cdpcomusersettingsprovider.cpp", &v17);
    if ( hKey )
      RegCloseKey(hKey);
    return v15;
  }
  pvData = 0;
  pcbData = 4;
  ValueA = RegGetValueA(hKey, 0, "NearShareChannelUserAuthzPolicy", 0x10u, 0, &pvData, &pcbData);
  v11 = ValueA < 0;
  if ( ValueA > 0 )
  {
    ValueA = (unsigned __int16)ValueA | 0x80070000;
    v11 = ValueA < 0;
  }
  if ( v11 )
  {
    v15 = ValueA;
    v17 = 56;
    Log<long &,char const (&)[40],int>(v10, v9, &v15, "..\\cdpcomusersettingsprovider.cpp", &v17);
    v12 = v15;
  }
  else
  {
    *a2 = pvData;
    v12 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v12;
}

```

## disassembly

```asm
0x180019000  mov     [rsp-8+arg_0], rbx
0x180019005  push    rbp
0x180019006  mov     rbp, rsp
0x180019009  sub     rsp, 50h
0x18001900d  mov     rbx, rdx
0x180019010  test    rdx, rdx
0x180019013  jnz     short loc_180019044
0x180019015  mov     [rbp+arg_8], 80070057h
0x18001901c  mov     [rbp+arg_18], 2Fh ; '/'
0x180019023  lea     rax, [rbp+arg_18]
0x180019027  mov     [rsp+50h+phkResult], rax
0x18001902c  lea     r9, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x180019033  lea     r8, [rbp+arg_8]
0x180019037  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18001903c  mov     eax, [rbp+arg_8]
0x18001903f  jmp     loc_180019142
0x180019044  mov     [rbp+hKey], 0
0x18001904c  lea     rax, [rbp+hKey]
0x180019050  mov     [rsp+50h+phkResult], rax; phkResult
0x180019055  mov     r9d, 20019h; samDesired
0x18001905b  xor     r8d, r8d; ulOptions
0x18001905e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180019065  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001906c  call    cs:__imp_RegOpenKeyExA
0x180019072  test    eax, eax
0x180019074  jle     short loc_180019080
0x180019076  movzx   eax, ax
0x180019079  or      eax, 80070000h
0x18001907e  test    eax, eax
0x180019080  jns     short loc_1800190B6
0x180019082  mov     [rbp+arg_8], eax
0x180019085  mov     [rbp+arg_18], 33h ; '3'
0x18001908c  lea     rax, [rbp+arg_18]
0x180019090  mov     [rsp+50h+phkResult], rax
0x180019095  lea     r9, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x18001909c  lea     r8, [rbp+arg_8]
0x1800190a0  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x1800190a5  mov     rcx, [rbp+hKey]; hKey
0x1800190a9  test    rcx, rcx
0x1800190ac  jz      short loc_18001903C
0x1800190ae  call    cs:__imp_RegCloseKey
0x1800190b4  jmp     short loc_18001903C
0x1800190b6  mov     [rbp+arg_10], 0
0x1800190bd  mov     [rbp+var_10], 4
0x1800190c4  lea     rax, [rbp+var_10]
0x1800190c8  mov     [rsp+50h+pcbData], rax; pcbData
0x1800190cd  lea     rax, [rbp+arg_10]
0x1800190d1  mov     [rsp+50h+pvData], rax; pvData
0x1800190d6  mov     [rsp+50h+phkResult], 0; pdwType
0x1800190df  mov     r9d, 10h; dwFlags
0x1800190e5  lea     r8, aNearsharechann; "NearShareChannelUserAuthzPolicy"
0x1800190ec  xor     edx, edx; lpSubKey
0x1800190ee  mov     rcx, [rbp+hKey]; hkey
0x1800190f2  call    cs:__imp_RegGetValueA
0x1800190f8  test    eax, eax
0x1800190fa  jle     short loc_180019106
0x1800190fc  movzx   eax, ax
0x1800190ff  or      eax, 80070000h
0x180019104  test    eax, eax
0x180019106  jns     short loc_180019130
0x180019108  mov     [rbp+arg_8], eax
0x18001910b  mov     [rbp+arg_18], 38h ; '8'
0x180019112  lea     rax, [rbp+arg_18]
0x180019116  mov     [rsp+50h+phkResult], rax
0x18001911b  lea     r9, aCdpcomusersett; "..\\cdpcomusersettingsprovider.cpp"
0x180019122  lea     r8, [rbp+arg_8]
0x180019126  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18001912b  mov     ebx, [rbp+arg_8]
0x18001912e  jmp     short loc_180019137
0x180019130  mov     eax, [rbp+arg_10]
0x180019133  mov     [rbx], eax
0x180019135  xor     ebx, ebx
0x180019137  lea     rcx, [rbp+hKey]
0x18001913b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180019140  mov     eax, ebx
0x180019142  mov     rbx, [rsp+50h+arg_0]
0x180019147  add     rsp, 50h
0x18001914b  pop     rbp
0x18001914c  retn
```
