# ModernDeployment::Autopilot::Core::TryCollectAadJoinType

- ea: `0x1800ea99c`
- end: `0x1800eab3a`
- name: `ModernDeployment::Autopilot::Core::TryCollectAadJoinType`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ea464`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180080bac`
- `0x180084d80`
- `0x18008a454`
- `0x18008d290`
- `0x1800ea99c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800eaa5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800eaa5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eaa03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eaa03`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800eaaba`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800eaaba`

## string_xrefs

- `0x1800eaaed`: `AzureADJoined`
- `0x1800eaae4`: `HybridAzureADJoined`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::TryCollectAadJoinType(__int64 a1)
{
  bool v2; // si
  LSTATUS v3; // eax
  bool v4; // sf
  LSTATUS v5; // eax
  bool v6; // sf
  bool v7; // bl
  const unsigned __int16 *v8; // rdx
  DWORD cSubKeys; // [rsp+60h] [rbp-258h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-250h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-248h] BYREF

  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1) = 0;
  v2 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin\\JoinInfo",
         0,
         0x20019u,
         &hKey);
  v4 = v3 < 0;
  if ( v3 > 0 )
    v4 = 1;
  if ( !v4 )
  {
    cSubKeys = 0;
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v6 = v5 < 0;
    if ( v5 > 0 )
      v6 = 1;
    if ( !v6 )
      v2 = cSubKeys != 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  v7 = 0;
  memset_0(Buffer, 0, 0x208u);
  cSubKeys = 260;
  if ( GetComputerNameExW(ComputerNameDnsDomain, Buffer, &cSubKeys) )
    v7 = Buffer[0] != 0;
  if ( v2 )
  {
    if ( v7 )
      v8 = L"HybridAzureADJoined";
    else
      v8 = L"AzureADJoined";
  }
  else
  {
    if ( !v7 )
    {
      std::wstring::assign(a1, L"NotJoined");
      return 0;
    }
    v8 = L"DomainJoined";
  }
  std::wstring::assign(a1, v8);
  return 0;
}

```

## disassembly

```asm
0x1800ea99c  push    rbx
0x1800ea99e  push    rsi
0x1800ea99f  push    rdi
0x1800ea9a0  push    r14
0x1800ea9a2  sub     rsp, 298h
0x1800ea9a9  mov     rax, cs:__security_cookie
0x1800ea9b0  xor     rax, rsp
0x1800ea9b3  mov     [rsp+2B8h+var_38], rax
0x1800ea9bb  mov     rdi, rcx
0x1800ea9be  xor     r14d, r14d
0x1800ea9c1  mov     [rcx+10h], r14
0x1800ea9c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ea9ca  mov     [rax], r14w
0x1800ea9ce  mov     sil, r14b
0x1800ea9d1  mov     [rsp+2B8h+hKey], r14
0x1800ea9d6  xor     edx, edx
0x1800ea9d8  lea     rcx, [rsp+2B8h+hKey]
0x1800ea9dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ea9e2  lea     rax, [rsp+2B8h+hKey]
0x1800ea9e7  mov     [rsp+2B8h+phkResult], rax; phkResult
0x1800ea9ec  mov     r9d, 20019h; samDesired
0x1800ea9f2  xor     r8d, r8d; ulOptions
0x1800ea9f5  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x1800ea9fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800eaa03  call    cs:__imp_RegOpenKeyExW
0x1800eaa0a  nop     dword ptr [rax+rax+00h]
0x1800eaa0f  test    eax, eax
0x1800eaa11  jle     short loc_1800EAA1D
0x1800eaa13  movzx   eax, ax
0x1800eaa16  or      eax, 80070000h
0x1800eaa1b  test    eax, eax
0x1800eaa1d  js      short loc_1800EAA83
0x1800eaa1f  mov     [rsp+2B8h+cSubKeys], r14d
0x1800eaa24  mov     [rsp+2B8h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800eaa29  mov     [rsp+2B8h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800eaa2e  mov     [rsp+2B8h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800eaa33  mov     [rsp+2B8h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800eaa38  mov     [rsp+2B8h+lpcValues], r14; lpcValues
0x1800eaa3d  mov     [rsp+2B8h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800eaa42  mov     [rsp+2B8h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800eaa47  lea     rax, [rsp+2B8h+cSubKeys]
0x1800eaa4c  mov     [rsp+2B8h+phkResult], rax; lpcSubKeys
0x1800eaa51  xor     r9d, r9d; lpReserved
0x1800eaa54  xor     r8d, r8d; lpcchClass
0x1800eaa57  xor     edx, edx; lpClass
0x1800eaa59  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1800eaa5e  call    cs:__imp_RegQueryInfoKeyW
0x1800eaa65  nop     dword ptr [rax+rax+00h]
0x1800eaa6a  test    eax, eax
0x1800eaa6c  jle     short loc_1800EAA78
0x1800eaa6e  movzx   eax, ax
0x1800eaa71  or      eax, 80070000h
0x1800eaa76  test    eax, eax
0x1800eaa78  js      short loc_1800EAA83
0x1800eaa7a  cmp     [rsp+2B8h+cSubKeys], r14d
0x1800eaa7f  setnbe  sil
0x1800eaa83  lea     rcx, [rsp+2B8h+hKey]
0x1800eaa88  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800eaa8d  movzx   ebx, r14b
0x1800eaa91  xor     edx, edx; Val
0x1800eaa93  mov     r8d, 208h; Size
0x1800eaa99  lea     rcx, [rsp+2B8h+Buffer]; void *
0x1800eaa9e  call    memset_0
0x1800eaaa3  mov     [rsp+2B8h+cSubKeys], 104h
0x1800eaaab  lea     r8, [rsp+2B8h+cSubKeys]; nSize
0x1800eaab0  lea     rdx, [rsp+2B8h+Buffer]; lpBuffer
0x1800eaab5  mov     ecx, 2; NameType
0x1800eaaba  call    cs:__imp_GetComputerNameExW
0x1800eaac1  nop     dword ptr [rax+rax+00h]
0x1800eaac6  test    eax, eax
0x1800eaac8  jz      short loc_1800EAAD8
0x1800eaaca  mov     eax, 1
0x1800eaacf  cmp     [rsp+2B8h+Buffer], r14w
0x1800eaad5  cmovnz  ebx, eax
0x1800eaad8  mov     rcx, rdi
0x1800eaadb  test    sil, sil
0x1800eaade  jz      short loc_1800EAAF6
0x1800eaae0  test    bl, bl
0x1800eaae2  jz      short loc_1800EAAED
0x1800eaae4  lea     rdx, ?AadJoinTypeHybrid@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "HybridAzureADJoined"
0x1800eaaeb  jmp     short loc_1800EAB01
0x1800eaaed  lea     rdx, ?AadJoinTypeAzureAD@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "AzureADJoined"
0x1800eaaf4  jmp     short loc_1800EAB01
0x1800eaaf6  test    bl, bl
0x1800eaaf8  jz      short loc_1800EAB08
0x1800eaafa  lea     rdx, ?AadJoinTypeDomainOnly@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "DomainJoined"
0x1800eab01  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800eab06  jmp     short loc_1800EAB14
0x1800eab08  lea     rdx, ?AadJoinTypeNotJoined@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "NotJoined"
0x1800eab0f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800eab14  xor     eax, eax
0x1800eab16  jmp     short loc_1800EAB1C
0x1800eab18  mov     eax, [rsp+2B8h+cSubKeys]
0x1800eab1c  mov     rcx, [rsp+2B8h+var_38]
0x1800eab24  xor     rcx, rsp; StackCookie
0x1800eab27  call    __security_check_cookie
0x1800eab2c  add     rsp, 298h
0x1800eab33  pop     r14
0x1800eab35  pop     rdi
0x1800eab36  pop     rsi
0x1800eab37  pop     rbx
0x1800eab38  retn
```
