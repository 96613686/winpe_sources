# WritePreinstallInformation

- ea: `0x18005e3d8`
- end: `0x18005e5b6`
- name: `WritePreinstallInformation`
- size: `478`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180062610`
- `0x18007cbe0`

## callees

- `0x180005c94`
- `0x180006eb0`
- `0x18000a430`
- `0x180010200`
- `0x180012108`
- `0x180016a20`
- `0x180028db4`
- `0x18004f104`
- `0x180052d50`
- `0x18005e1a8`
- `0x18005e3d8`
- `0x18005e5bc`
- `0x18005e670`
- `0x180062a20`
- `0x18007fc44`
- `0x1800810d0`

## import_xrefs

- `msvcrt!_wcsupr_s` at `0x18005e48e`
- `msvcrt!_wcsupr_s` at `0x18005e48e`

## string_xrefs

- `0x18005e50f`: `ClassConfigured`
- `0x18005e54d`: `ClassConfigured`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LSTATUS __fastcall WritePreinstallInformation(__int64 a1, NetSetup2::ActiveObject *a2)
{
  bool Boolean; // bl
  const wchar_t *v5; // rdx
  HKEY v7; // [rsp+50h] [rbp-61h] BYREF
  HKEY v8; // [rsp+58h] [rbp-59h] BYREF
  HKEY v9; // [rsp+60h] [rbp-51h] BYREF
  _BYTE v10[20]; // [rsp+68h] [rbp-49h] BYREF
  int v11; // [rsp+7Ch] [rbp-35h]
  _BYTE v12[24]; // [rsp+80h] [rbp-31h] BYREF
  wchar_t String[40]; // [rsp+98h] [rbp-19h] BYREF

  CreateDeviceLocationConfigurationKey(&v8, a1, a2);
  RegistryKey::CreateSubKey(&v8, (HKEY)&v9, L"Driver", 2u, 0, 0);
  NetSetup2::ActiveObject::GetProperty(a2, (const struct _NETSETUPPROPKEY *)v10);
  if ( v11 )
    Boolean = NetSetup2::Property::GetBoolean((NetSetup2::Property *)v10);
  else
    Boolean = 0;
  std::vector<_NETSETUPPROPKEY>::_Tidy(v12);
  StringFromGuid<40>((char *)a2 + 20, String);
  _wcsupr_s(String, 0x28u);
  v5 = L"NetCfgInstanceId";
  if ( !Boolean )
    v5 = L"NetSetupAnticipatedInstanceId";
  RegistryKey::SetValue(&v9, v5, (const BYTE *)String);
  if ( Boolean )
  {
    RegistryKey::SetValue((RegistryKey *)&v9, L"AlwaysStartDevice", 1, 0);
    SetBootFlags(a1, a2);
    RegistryKey::CreateSubKey(&v8, (HKEY)&v7, L"Status", 2u, 0, 0);
    RegistryKey::SetValue((RegistryKey *)&v7, L"ClassConfigured", 1, 0);
  }
  else
  {
    RegistryKey::TryOpenSubKey(&v8, (HKEY)&v7, L"Status", 2u, 0);
    if ( v7 )
    {
      RegistryKey::DeleteValue(&v7, L"ClassConfigured");
      GarbageCollectRegistryPath((const struct RegistryKey *)&v8, L"Status");
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v7);
  WriteCustomPropertyRegValues(a2);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v9);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v8);
}

```

## disassembly

```asm
0x18005e3d8  mov     rax, rsp
0x18005e3db  push    rbp
0x18005e3dc  push    rsi
0x18005e3dd  push    rdi
0x18005e3de  lea     rbp, [rax-5Fh]
0x18005e3e2  sub     rsp, 0F0h
0x18005e3e9  mov     [rbp+57h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18005e3f1  mov     [rax+18h], rbx
0x18005e3f5  mov     rax, cs:__security_cookie
0x18005e3fc  xor     rax, rsp
0x18005e3ff  mov     [rbp+57h+var_20], rax
0x18005e403  mov     rdi, rdx
0x18005e406  mov     rsi, rcx
0x18005e409  mov     r8, rdx
0x18005e40c  mov     rdx, rcx
0x18005e40f  lea     rcx, [rbp+57h+var_B0]
0x18005e413  call    CreateDeviceLocationConfigurationKey
0x18005e418  nop
0x18005e419  mov     qword ptr [rsp+28h], 0
0x18005e422  mov     [rsp+100h+var_E0], 0
0x18005e42b  mov     r9d, 2
0x18005e431  lea     r8, aDriver; "Driver"
0x18005e438  lea     rdx, [rbp+57h+var_A8]
0x18005e43c  lea     rcx, [rbp+57h+var_B0]
0x18005e440  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x18005e445  nop
0x18005e446  lea     r8, NETSETUPPKEY_Interface_StartDatapathImmediatelyAfterPnpEnumeration
0x18005e44d  lea     rdx, [rbp+57h+var_A0]; struct _NETSETUPPROPKEY *
0x18005e451  mov     rcx, rdi; this
0x18005e454  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18005e459  nop
0x18005e45a  cmp     [rbp+57h+var_8C], 0
0x18005e45e  jnz     short loc_18005E464
0x18005e460  xor     bl, bl
0x18005e462  jmp     short loc_18005E46F
0x18005e464  lea     rcx, [rbp+57h+var_A0]; this
0x18005e468  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x18005e46d  mov     bl, al
0x18005e46f  lea     rcx, [rbp+57h+var_88]
0x18005e473  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18005e478  lea     rcx, [rdi+14h]
0x18005e47c  lea     rdx, [rbp+57h+String]
0x18005e480  call    ??$StringFromGuid@$0CI@@@YAXAEBU_GUID@@AEAY0CI@_WW4GuidConvertOptions@@@Z; StringFromGuid<40>(_GUID const &,wchar_t (&)[40],GuidConvertOptions)
0x18005e485  mov     edx, 28h ; '('; Size
0x18005e48a  lea     rcx, [rbp+57h+String]; String
0x18005e48e  call    cs:__imp__wcsupr_s
0x18005e494  lea     rax, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18005e49b  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x18005e4a2  test    bl, bl
0x18005e4a4  cmovz   rdx, rax; wchar_t *
0x18005e4a8  lea     r8, [rbp+57h+String]; wchar_t *
0x18005e4ac  lea     rcx, [rbp+57h+var_A8]; this
0x18005e4b0  call    ?SetValue@RegistryKey@@QEBAXPEB_W0@Z; RegistryKey::SetValue(wchar_t const *,wchar_t const *)
0x18005e4b5  test    bl, bl
0x18005e4b7  jz      short loc_18005E522
0x18005e4b9  xor     r9d, r9d
0x18005e4bc  lea     ebx, [r9+1]
0x18005e4c0  mov     r8d, ebx
0x18005e4c3  lea     rdx, aAlwaysstartdev; "AlwaysStartDevice"
0x18005e4ca  lea     rcx, [rbp+57h+var_A8]
0x18005e4ce  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18005e4d3  mov     rdx, rdi
0x18005e4d6  mov     rcx, rsi
0x18005e4d9  call    SetBootFlags
0x18005e4de  mov     qword ptr [rsp+28h], 0
0x18005e4e7  mov     [rsp+100h+var_E0], 0
0x18005e4f0  lea     r9d, [rbx+1]
0x18005e4f4  lea     r8, aStatus; "Status"
0x18005e4fb  lea     rdx, [rbp+57h+var_B8]
0x18005e4ff  lea     rcx, [rbp+57h+var_B0]
0x18005e503  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x18005e508  nop
0x18005e509  xor     r9d, r9d
0x18005e50c  mov     r8d, ebx
0x18005e50f  lea     rdx, aClassconfigure; "ClassConfigured"
0x18005e516  lea     rcx, [rbp+57h+var_B8]
0x18005e51a  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18005e51f  nop
0x18005e520  jmp     short loc_18005E56E
0x18005e522  mov     [rsp+100h+var_E0], 0
0x18005e52b  mov     r9d, 2
0x18005e531  lea     r8, aStatus; "Status"
0x18005e538  lea     rdx, [rbp+57h+var_B8]
0x18005e53c  lea     rcx, [rbp+57h+var_B0]
0x18005e540  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18005e545  nop
0x18005e546  cmp     [rbp+57h+var_B8], 0
0x18005e54b  jz      short loc_18005E56E
0x18005e54d  lea     rdx, aClassconfigure; "ClassConfigured"
0x18005e554  lea     rcx, [rbp+57h+var_B8]; this
0x18005e558  call    ?DeleteValue@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteValue(wchar_t const *)
0x18005e55d  lea     rdx, aStatus; "Status"
0x18005e564  lea     rcx, [rbp+57h+var_B0]; struct RegistryKey *
0x18005e568  call    ?GarbageCollectRegistryPath@@YAXAEBVRegistryKey@@PEB_W@Z; GarbageCollectRegistryPath(RegistryKey const &,wchar_t const *)
0x18005e56d  nop
0x18005e56e  lea     rcx, [rbp+57h+var_B8]
0x18005e572  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005e577  lea     rdx, [rbp+57h+var_A8]
0x18005e57b  mov     rcx, rdi; this
0x18005e57e  call    WriteCustomPropertyRegValues
0x18005e583  nop
0x18005e584  lea     rcx, [rbp+57h+var_A8]
0x18005e588  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005e58d  nop
0x18005e58e  lea     rcx, [rbp+57h+var_B0]
0x18005e592  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005e597  mov     rcx, [rbp+57h+var_20]
0x18005e59b  xor     rcx, rsp; StackCookie
0x18005e59e  call    __security_check_cookie
0x18005e5a3  mov     rbx, [rsp+100h+arg_10]
0x18005e5ab  add     rsp, 0F0h
0x18005e5b2  pop     rdi
0x18005e5b3  pop     rsi
0x18005e5b4  pop     rbp
0x18005e5b5  retn
```
