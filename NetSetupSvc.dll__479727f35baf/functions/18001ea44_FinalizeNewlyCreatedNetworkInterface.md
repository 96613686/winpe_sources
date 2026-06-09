# FinalizeNewlyCreatedNetworkInterface

- ea: `0x18001ea44`
- end: `0x18001eb0c`
- name: `FinalizeNewlyCreatedNetworkInterface`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18001f2e4`
- `0x1800223a4`

## callees

- `0x1800027c0`
- `0x180008d94`
- `0x18000d974`
- `0x18000d9b4`
- `0x18001976c`
- `0x180028334`
- `0x1800283fc`
- `0x18002c3e0`
- `0x18002c728`
- `0x18002ce44`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FinalizeNewlyCreatedNetworkInterface(__int64 a1, HKEY *a2, __int64 a3)
{
  struct Property v4; // rax
  int Uint32; // ebx
  _BYTE v7[24]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v9[8]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v10; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v11[20]; // [rsp+64h] [rbp-44h] BYREF
  _BYTE v12[32]; // [rsp+78h] [rbp-30h] BYREF

  NetSetup2::details::TransactionBase::GetNetworkInterfaceById(a1, v9, a3);
  StringFromGuid(v12, v11);
  RegistryKey::SetValue((__int64)a2, (int)L"NetCfgInstanceId");
  v4.lpVtbl = NetSetup2::ActiveObject::GetProperty(
                (NetSetup2::ActiveObject *)v9,
                (const struct _NETSETUPPROPKEY *)v7,
                (unsigned int)NETSETUPPKEY_Interface_NetLuidIndex).lpVtbl;
  Uint32 = NetSetup2::Property::GetUint32((NetSetup2::Property *)v4.lpVtbl);
  std::vector<unsigned char>::_Tidy((__int64)v8);
  RegistryKey::SetValue(a2, L"NetLuidIndex", Uint32, 0);
  std::wstring::_Tidy_deallocate((__int64)v12);
  return std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(&v10);
}

```

## disassembly

```asm
0x18001ea44  mov     [rsp+arg_18], rbx
0x18001ea49  push    rdi
0x18001ea4a  sub     rsp, 0A0h
0x18001ea51  mov     rax, cs:__security_cookie
0x18001ea58  xor     rax, rsp
0x18001ea5b  mov     [rsp+0A8h+var_10], rax
0x18001ea63  mov     rdi, rdx
0x18001ea66  lea     rdx, [rsp+0A8h+var_58]
0x18001ea6b  call    ?GetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AVNetworkInterface@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetNetworkInterfaceById(_GUID const &)
0x18001ea70  nop
0x18001ea71  lea     rdx, [rsp+0A8h+var_44]
0x18001ea76  lea     rcx, [rsp+0A8h+var_30]
0x18001ea7b  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x18001ea80  nop
0x18001ea81  lea     r8, [rsp+0A8h+var_30]
0x18001ea86  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x18001ea8d  mov     rcx, rdi
0x18001ea90  call    ?SetValue@RegistryKey@@QEBAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RegistryKey::SetValue(wchar_t const *,std::wstring const &)
0x18001ea95  lea     r8, NETSETUPPKEY_Interface_NetLuidIndex
0x18001ea9c  lea     rdx, [rsp+0A8h+var_88]; struct _NETSETUPPROPKEY *
0x18001eaa1  lea     rcx, [rsp+0A8h+var_58]; this
0x18001eaa6  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18001eaab  nop
0x18001eaac  mov     rcx, rax; this
0x18001eaaf  call    ?GetUint32@Property@NetSetup2@@QEBAKXZ; NetSetup2::Property::GetUint32(void)
0x18001eab4  mov     ebx, eax
0x18001eab6  lea     rcx, [rsp+0A8h+var_70]
0x18001eabb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001eac0  xor     r9d, r9d
0x18001eac3  mov     r8d, ebx
0x18001eac6  lea     rdx, aNetluidindex; "NetLuidIndex"
0x18001eacd  mov     rcx, rdi
0x18001ead0  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18001ead5  nop
0x18001ead6  lea     rcx, [rsp+0A8h+var_30]
0x18001eadb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eae0  nop
0x18001eae1  lea     rcx, [rsp+0A8h+var_50]
0x18001eae6  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001eaeb  mov     rcx, [rsp+0A8h+var_10]
0x18001eaf3  xor     rcx, rsp; StackCookie
0x18001eaf6  call    __security_check_cookie
0x18001eafb  mov     rbx, [rsp+0A8h+arg_18]
0x18001eb03  add     rsp, 0A0h
0x18001eb0a  pop     rdi
0x18001eb0b  retn
```
