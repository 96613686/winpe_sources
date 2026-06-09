# ModernDeployment::Autopilot::Core::TryCollectAadJoinType

- ea: `0x1800e7f1c`
- end: `0x1800e80a8`
- name: `ModernDeployment::Autopilot::Core::TryCollectAadJoinType`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e79e8`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x18008019c`
- `0x180084208`
- `0x180089614`
- `0x18008c244`
- `0x1800e7f1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800e7fd8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800e7fd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e7f83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e7f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800e802e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800e802e`

## string_xrefs

- `0x1800e805b`: `AzureADJoined`
- `0x1800e8052`: `HybridAzureADJoined`

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
0x1800e7f1c  push    rbx
0x1800e7f1e  push    rsi
0x1800e7f1f  push    rdi
0x1800e7f20  push    r14
0x1800e7f22  sub     rsp, 298h
0x1800e7f29  mov     rax, cs:__security_cookie
0x1800e7f30  xor     rax, rsp
0x1800e7f33  mov     [rsp+2B8h+var_38], rax
0x1800e7f3b  mov     rdi, rcx
0x1800e7f3e  xor     r14d, r14d
0x1800e7f41  mov     [rcx+10h], r14
0x1800e7f45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e7f4a  mov     [rax], r14w
0x1800e7f4e  mov     sil, r14b
0x1800e7f51  mov     [rsp+2B8h+hKey], r14
0x1800e7f56  xor     edx, edx
0x1800e7f58  lea     rcx, [rsp+2B8h+hKey]
0x1800e7f5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800e7f62  lea     rax, [rsp+2B8h+hKey]
0x1800e7f67  mov     [rsp+2B8h+phkResult], rax; phkResult
0x1800e7f6c  mov     r9d, 20019h; samDesired
0x1800e7f72  xor     r8d, r8d; ulOptions
0x1800e7f75  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x1800e7f7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e7f83  call    cs:__imp_RegOpenKeyExW
0x1800e7f89  test    eax, eax
0x1800e7f8b  jle     short loc_1800E7F97
0x1800e7f8d  movzx   eax, ax
0x1800e7f90  or      eax, 80070000h
0x1800e7f95  test    eax, eax
0x1800e7f97  js      short loc_1800E7FF7
0x1800e7f99  mov     [rsp+2B8h+cSubKeys], r14d
0x1800e7f9e  mov     [rsp+2B8h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800e7fa3  mov     [rsp+2B8h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800e7fa8  mov     [rsp+2B8h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800e7fad  mov     [rsp+2B8h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800e7fb2  mov     [rsp+2B8h+lpcValues], r14; lpcValues
0x1800e7fb7  mov     [rsp+2B8h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800e7fbc  mov     [rsp+2B8h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800e7fc1  lea     rax, [rsp+2B8h+cSubKeys]
0x1800e7fc6  mov     [rsp+2B8h+phkResult], rax; lpcSubKeys
0x1800e7fcb  xor     r9d, r9d; lpReserved
0x1800e7fce  xor     r8d, r8d; lpcchClass
0x1800e7fd1  xor     edx, edx; lpClass
0x1800e7fd3  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1800e7fd8  call    cs:__imp_RegQueryInfoKeyW
0x1800e7fde  test    eax, eax
0x1800e7fe0  jle     short loc_1800E7FEC
0x1800e7fe2  movzx   eax, ax
0x1800e7fe5  or      eax, 80070000h
0x1800e7fea  test    eax, eax
0x1800e7fec  js      short loc_1800E7FF7
0x1800e7fee  cmp     [rsp+2B8h+cSubKeys], r14d
0x1800e7ff3  setnbe  sil
0x1800e7ff7  lea     rcx, [rsp+2B8h+hKey]
0x1800e7ffc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e8001  movzx   ebx, r14b
0x1800e8005  xor     edx, edx; Val
0x1800e8007  mov     r8d, 208h; Size
0x1800e800d  lea     rcx, [rsp+2B8h+Buffer]; void *
0x1800e8012  call    memset_0
0x1800e8017  mov     [rsp+2B8h+cSubKeys], 104h
0x1800e801f  lea     r8, [rsp+2B8h+cSubKeys]; nSize
0x1800e8024  lea     rdx, [rsp+2B8h+Buffer]; lpBuffer
0x1800e8029  mov     ecx, 2; NameType
0x1800e802e  call    cs:__imp_GetComputerNameExW
0x1800e8034  test    eax, eax
0x1800e8036  jz      short loc_1800E8046
0x1800e8038  mov     eax, 1
0x1800e803d  cmp     [rsp+2B8h+Buffer], r14w
0x1800e8043  cmovnz  ebx, eax
0x1800e8046  mov     rcx, rdi
0x1800e8049  test    sil, sil
0x1800e804c  jz      short loc_1800E8064
0x1800e804e  test    bl, bl
0x1800e8050  jz      short loc_1800E805B
0x1800e8052  lea     rdx, ?AadJoinTypeHybrid@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "HybridAzureADJoined"
0x1800e8059  jmp     short loc_1800E806F
0x1800e805b  lea     rdx, ?AadJoinTypeAzureAD@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "AzureADJoined"
0x1800e8062  jmp     short loc_1800E806F
0x1800e8064  test    bl, bl
0x1800e8066  jz      short loc_1800E8076
0x1800e8068  lea     rdx, ?AadJoinTypeDomainOnly@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "DomainJoined"
0x1800e806f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800e8074  jmp     short loc_1800E8082
0x1800e8076  lea     rdx, ?AadJoinTypeNotJoined@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "NotJoined"
0x1800e807d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800e8082  xor     eax, eax
0x1800e8084  jmp     short loc_1800E808A
0x1800e8086  mov     eax, [rsp+2B8h+cSubKeys]
0x1800e808a  mov     rcx, [rsp+2B8h+var_38]
0x1800e8092  xor     rcx, rsp; StackCookie
0x1800e8095  call    __security_check_cookie
0x1800e809a  add     rsp, 298h
0x1800e80a1  pop     r14
0x1800e80a3  pop     rdi
0x1800e80a4  pop     rsi
0x1800e80a5  pop     rbx
0x1800e80a6  retn
```
