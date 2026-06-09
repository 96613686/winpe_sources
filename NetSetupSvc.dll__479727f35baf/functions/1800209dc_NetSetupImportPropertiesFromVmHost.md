# NetSetupImportPropertiesFromVmHost

- ea: `0x1800209dc`
- end: `0x180020bc4`
- name: `NetSetupImportPropertiesFromVmHost`
- size: `488`
- prototype: `__int64 __fastcall(NetSetup2::NetworkInterfaceTemplate *this, RegistryKey *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800207bc`

## callees

- `0x1800027c0`
- `0x18000d9b4`
- `0x18001b168`
- `0x18001b1e8`
- `0x18001b2d0`
- `0x18001b414`
- `0x18001f1cc`
- `0x1800209dc`
- `0x180024638`
- `0x1800275e4`
- `0x180027be0`
- `0x180027d2c`
- `0x1800286d8`

## string_xrefs

- `0x180020a14`: `Compartment`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NetSetupImportPropertiesFromVmHost(NetSetup2::NetworkInterfaceTemplate *this, HKEY *a2)
{
  unsigned __int64 ValueQword; // rax
  char v6[8]; // [rsp+20h] [rbp-69h] BYREF
  int ValueDword; // [rsp+28h] [rbp-61h] BYREF
  __int128 v8; // [rsp+30h] [rbp-59h] BYREF
  __int128 v9; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v10[16]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v11; // [rsp+60h] [rbp-29h]
  _BYTE v12[16]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v13; // [rsp+80h] [rbp-9h]
  _BYTE v14[32]; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v15[32]; // [rsp+B0h] [rbp+27h] BYREF

  v8 = 0;
  RegistryKey::GetValueString(a2, (__int64)v15, L"Compartment", 1);
  if ( (unsigned __int8)GuidFromString(v15, &v8) )
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(
      (__int64)this,
      (__int128 *)NETSETUPPKEY_Interface_IsolationCompartmentId,
      (__int64)&v8);
  v9 = 0;
  RegistryKey::GetValueString(a2, (__int64)v14, L"Guid", 1);
  if ( (unsigned __int8)GuidFromString(v14, &v9) )
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(
      (__int64)this,
      &NETSETUPPKEY_Object_Id,
      (__int64)&v9);
  if ( RegistryKey::ValueExists((RegistryKey *)a2, L"Luid") )
  {
    ValueQword = RegistryKey::GetValueQword(a2, L"Luid");
    NetSetup2::NetworkInterfaceTemplate::set_NetLuid(this, (union _NET_LUID_LH)ValueQword);
  }
  if ( RegistryKey::ValueExists((RegistryKey *)a2, L"Index") )
  {
    ValueDword = RegistryKey::GetValueDword(a2, L"Index", 0, 0);
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      (__int64)this,
      (__int128 *)NETSETUPPKEY_Interface_SuggestedIfIndex,
      (__int64)&ValueDword);
  }
  RegistryKey::GetValueString(a2, (__int64)v12, L"Alias", 1);
  if ( v13 )
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(
      (__int64)this,
      &NETSETUPPKEY_Interface_IfAlias,
      (__int64)v12);
  RegistryKey::GetValueString(a2, (__int64)v10, L"Description", 1);
  if ( v11 )
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(
      (__int64)this,
      &NETSETUPPKEY_Interface_IfDescr,
      (__int64)v10);
  v6[0] = 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    (__int64)this,
    (__int128 *)NETSETUPPKEY_Interface_IsMirroredFromHost,
    (__int64)v6);
  std::wstring::_Tidy_deallocate((__int64)v10);
  std::wstring::_Tidy_deallocate((__int64)v12);
  std::wstring::_Tidy_deallocate((__int64)v14);
  return std::wstring::_Tidy_deallocate((__int64)v15);
}

```

## disassembly

```asm
0x1800209dc  mov     [rsp-8+arg_10], rbx
0x1800209e1  mov     [rsp-8+arg_18], rdi
0x1800209e6  push    rbp
0x1800209e7  lea     rbp, [rsp-57h]
0x1800209ec  sub     rsp, 0E0h
0x1800209f3  mov     rax, cs:__security_cookie
0x1800209fa  xor     rax, rsp
0x1800209fd  mov     [rbp+57h+var_10], rax
0x180020a01  mov     rdi, rdx
0x180020a04  mov     rbx, rcx
0x180020a07  xorps   xmm0, xmm0
0x180020a0a  movups  [rbp+57h+var_B0], xmm0
0x180020a0e  mov     r9d, 1
0x180020a14  lea     r8, aCompartment; "Compartment"
0x180020a1b  lea     rdx, [rbp+57h+var_30]
0x180020a1f  mov     rcx, rdi
0x180020a22  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180020a27  nop
0x180020a28  lea     rdx, [rbp+57h+var_B0]
0x180020a2c  lea     rcx, [rbp+57h+var_30]
0x180020a30  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x180020a35  test    al, al
0x180020a37  jz      short loc_180020A4C
0x180020a39  lea     r8, [rbp+57h+var_B0]
0x180020a3d  lea     rdx, NETSETUPPKEY_Interface_IsolationCompartmentId
0x180020a44  mov     rcx, rbx
0x180020a47  call    ??$SetPropertyToValue@$0N@U_GUID@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBU_GUID@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(_NETSETUPPROPKEY const &,_GUID const &)
0x180020a4c  xorps   xmm0, xmm0
0x180020a4f  movups  [rbp+57h+var_A0], xmm0
0x180020a53  mov     r9d, 1
0x180020a59  lea     r8, aGuid; "Guid"
0x180020a60  lea     rdx, [rbp+57h+var_50]
0x180020a64  mov     rcx, rdi
0x180020a67  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180020a6c  nop
0x180020a6d  lea     rdx, [rbp+57h+var_A0]
0x180020a71  lea     rcx, [rbp+57h+var_50]
0x180020a75  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x180020a7a  test    al, al
0x180020a7c  jz      short loc_180020A91
0x180020a7e  lea     r8, [rbp+57h+var_A0]
0x180020a82  lea     rdx, NETSETUPPKEY_Object_Id
0x180020a89  mov     rcx, rbx
0x180020a8c  call    ??$SetPropertyToValue@$0N@U_GUID@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBU_GUID@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(_NETSETUPPROPKEY const &,_GUID const &)
0x180020a91  lea     rdx, aLuid; "Luid"
0x180020a98  mov     rcx, rdi; this
0x180020a9b  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180020aa0  test    al, al
0x180020aa2  jz      short loc_180020ABE
0x180020aa4  lea     rdx, aLuid; "Luid"
0x180020aab  mov     rcx, rdi; this
0x180020aae  call    ?GetValueQword@RegistryKey@@QEBA_KPEB_W@Z; RegistryKey::GetValueQword(wchar_t const *)
0x180020ab3  mov     rdx, rax; union _NET_LUID_LH
0x180020ab6  mov     rcx, rbx; this
0x180020ab9  call    ?set_NetLuid@NetworkInterfaceTemplate@NetSetup2@@QEAAXT_NET_LUID_LH@@@Z; NetSetup2::NetworkInterfaceTemplate::set_NetLuid(_NET_LUID_LH)
0x180020abe  lea     rdx, aIndex; "Index"
0x180020ac5  mov     rcx, rdi; this
0x180020ac8  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180020acd  test    al, al
0x180020acf  jz      short loc_180020AFC
0x180020ad1  xor     r9d, r9d
0x180020ad4  xor     r8d, r8d
0x180020ad7  lea     rdx, aIndex; "Index"
0x180020ade  mov     rcx, rdi
0x180020ae1  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180020ae6  mov     [rbp+57h+var_B8], eax
0x180020ae9  lea     r8, [rbp+57h+var_B8]
0x180020aed  lea     rdx, NETSETUPPKEY_Interface_SuggestedIfIndex
0x180020af4  mov     rcx, rbx
0x180020af7  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x180020afc  mov     r9d, 1
0x180020b02  lea     r8, aAlias; "Alias"
0x180020b09  lea     rdx, [rbp+57h+var_70]
0x180020b0d  mov     rcx, rdi
0x180020b10  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180020b15  nop
0x180020b16  cmp     [rbp+57h+var_60], 0
0x180020b1b  jz      short loc_180020B30
0x180020b1d  lea     r8, [rbp+57h+var_70]
0x180020b21  lea     rdx, NETSETUPPKEY_Interface_IfAlias
0x180020b28  mov     rcx, rbx
0x180020b2b  call    ??$SetPropertyToValue@$0BC@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(_NETSETUPPROPKEY const &,std::wstring const &)
0x180020b30  mov     r9d, 1
0x180020b36  lea     r8, aDescription; "Description"
0x180020b3d  lea     rdx, [rbp+57h+var_90]
0x180020b41  mov     rcx, rdi
0x180020b44  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180020b49  nop
0x180020b4a  cmp     [rbp+57h+var_80], 0
0x180020b4f  jz      short loc_180020B64
0x180020b51  lea     r8, [rbp+57h+var_90]
0x180020b55  lea     rdx, NETSETUPPKEY_Interface_IfDescr
0x180020b5c  mov     rcx, rbx
0x180020b5f  call    ??$SetPropertyToValue@$0BC@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(_NETSETUPPROPKEY const &,std::wstring const &)
0x180020b64  mov     [rbp+57h+var_C0], 1
0x180020b68  lea     r8, [rbp+57h+var_C0]
0x180020b6c  lea     rdx, NETSETUPPKEY_Interface_IsMirroredFromHost
0x180020b73  mov     rcx, rbx
0x180020b76  call    ??$SetPropertyToValue@$0BB@_N@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x180020b7b  nop
0x180020b7c  lea     rcx, [rbp+57h+var_90]
0x180020b80  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020b85  nop
0x180020b86  lea     rcx, [rbp+57h+var_70]
0x180020b8a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020b8f  nop
0x180020b90  lea     rcx, [rbp+57h+var_50]
0x180020b94  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020b99  nop
0x180020b9a  lea     rcx, [rbp+57h+var_30]
0x180020b9e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020ba3  mov     rcx, [rbp+57h+var_10]
0x180020ba7  xor     rcx, rsp; StackCookie
0x180020baa  call    __security_check_cookie
0x180020baf  lea     r11, [rsp+0E0h+var_s0]
0x180020bb7  mov     rbx, [r11+20h]
0x180020bbb  mov     rdi, [r11+28h]
0x180020bbf  mov     rsp, r11
0x180020bc2  pop     rbp
0x180020bc3  retn
```
