# ReadNetworkInterfaceCompartmentGuid

- ea: `0x180021580`
- end: `0x180021648`
- name: `ReadNetworkInterfaceCompartmentGuid`
- size: `200`
- prototype: `__int64 __fastcall(RegistryKey *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180021650`

## callees

- `0x1800027c0`
- `0x18000d9b4`
- `0x180018490`
- `0x18001b414`
- `0x18001d89c`
- `0x18001f1cc`
- `0x180021580`
- `0x180027d2c`
- `0x1800286d8`

## string_xrefs

- `0x1800215aa`: `*CompartmentGuid`
- `0x1800215c0`: `*CompartmentGuid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadNetworkInterfaceCompartmentGuid(HKEY *this, __int64 a2)
{
  __int64 ValueString; // rax
  _OWORD v6[2]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v7[16]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v8; // [rsp+50h] [rbp-28h]

  std::wstring::wstring((__int64)v7);
  if ( RegistryKey::ValueExists((RegistryKey *)this, L"*CompartmentGuid") )
  {
    ValueString = RegistryKey::GetValueString(this, (__int64)v6, L"*CompartmentGuid", 0);
    std::wstring::operator=(v7, ValueString);
    std::wstring::_Tidy_deallocate((__int64)v6);
  }
  if ( v8 )
  {
    v6[0] = 0;
    if ( (unsigned __int8)GuidFromString(v7, v6) )
      NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(
        a2,
        (__int128 *)NETSETUPPKEY_Interface_IsolationCompartmentId,
        (__int64)v6);
  }
  return std::wstring::_Tidy_deallocate((__int64)v7);
}

```

## disassembly

```asm
0x180021580  mov     [rsp+arg_10], rbx
0x180021585  push    rdi
0x180021586  sub     rsp, 70h
0x18002158a  mov     rax, cs:__security_cookie
0x180021591  xor     rax, rsp
0x180021594  mov     [rsp+78h+var_18], rax
0x180021599  mov     rbx, rdx
0x18002159c  mov     rdi, rcx
0x18002159f  lea     rcx, [rsp+78h+var_38]
0x1800215a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800215a9  nop
0x1800215aa  lea     rdx, aCompartmentgui; "*CompartmentGuid"
0x1800215b1  mov     rcx, rdi; this
0x1800215b4  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x1800215b9  test    al, al
0x1800215bb  jz      short loc_1800215EB
0x1800215bd  xor     r9d, r9d
0x1800215c0  lea     r8, aCompartmentgui; "*CompartmentGuid"
0x1800215c7  lea     rdx, [rsp+78h+var_58]
0x1800215cc  mov     rcx, rdi
0x1800215cf  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x1800215d4  mov     rdx, rax
0x1800215d7  lea     rcx, [rsp+78h+var_38]
0x1800215dc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800215e1  lea     rcx, [rsp+78h+var_58]
0x1800215e6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800215eb  cmp     [rsp+78h+var_28], 0
0x1800215f1  jz      short loc_180021623
0x1800215f3  xorps   xmm0, xmm0
0x1800215f6  movups  [rsp+78h+var_58], xmm0
0x1800215fb  lea     rdx, [rsp+78h+var_58]
0x180021600  lea     rcx, [rsp+78h+var_38]
0x180021605  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x18002160a  test    al, al
0x18002160c  jz      short loc_180021623
0x18002160e  lea     r8, [rsp+78h+var_58]
0x180021613  lea     rdx, NETSETUPPKEY_Interface_IsolationCompartmentId
0x18002161a  mov     rcx, rbx
0x18002161d  call    ??$SetPropertyToValue@$0N@U_GUID@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBU_GUID@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(_NETSETUPPROPKEY const &,_GUID const &)
0x180021622  nop
0x180021623  lea     rcx, [rsp+78h+var_38]
0x180021628  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002162d  mov     rcx, [rsp+78h+var_18]
0x180021632  xor     rcx, rsp; StackCookie
0x180021635  call    __security_check_cookie
0x18002163a  mov     rbx, [rsp+78h+arg_10]
0x180021642  add     rsp, 70h
0x180021646  pop     rdi
0x180021647  retn
```
