# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)

- ea: `0x18002a020`
- end: `0x18002a15d`
- name: `?ReadActivePolicyCode@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `317`
- prototype: `HKEY __fastcall(__int64, HKEY)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800296d8`
- `0x18002a164`

## callees

- `0x180003c80`
- `0x18000f9e4`
- `0x180013b8c`
- `0x180014754`
- `0x18001b444`
- `0x180021550`
- `0x180029d34`
- `0x18002a020`
- `0x18002f690`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a130`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a130`

## string_xrefs

- `0x18002a0b3`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HKEY __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadActivePolicyCode(
        __int64 a1,
        HKEY a2)
{
  _QWORD *v3; // r10
  __int64 StringValue; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const BYTE *lpData; // rax
  HKEY v10; // r10
  _BYTE v12[4]; // [rsp+30h] [rbp-40h] BYREF
  int v13; // [rsp+34h] [rbp-3Ch]
  HKEY phkResult[2]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-28h] BYREF

  phkResult[1] = a2;
  v12[0] = 0;
  std::wstring::wstring(a2);
  v13 = 1;
  StringValue = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(v15, *v3, 0, L"ActivePolicyCode", v12);
  std::wstring::operator=(a2, StringValue);
  std::wstring::_Tidy_deallocate(v15);
  if ( !v12[0] || !*((_QWORD *)a2 + 2) )
  {
    v5 = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(
           v15,
           -2147483646,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
           L"ActivePolicyCode",
           v12);
    std::wstring::operator=(a2, v5);
    std::wstring::_Tidy_deallocate(v15);
    if ( v12[0] )
    {
      if ( *((_QWORD *)a2 + 2) )
      {
        Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(phkResult, 983103);
        if ( phkResult[0] )
        {
          lpData = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v6, v7, v8);
          RegSetValueExW(v10, L"ActivePolicyCode", 0, 1u, lpData, 2 * *((_DWORD *)a2 + 4) + 2);
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18002a020  mov     [rsp-8+arg_0], rbx
0x18002a025  push    rbp
0x18002a026  mov     rbp, rsp
0x18002a029  sub     rsp, 70h
0x18002a02d  mov     rax, cs:__security_cookie
0x18002a034  xor     rax, rsp
0x18002a037  mov     [rbp+var_8], rax
0x18002a03b  mov     r10, r8
0x18002a03e  mov     rbx, rdx
0x18002a041  mov     [rbp+var_30], rdx
0x18002a045  mov     [rbp+var_3C], 0
0x18002a04c  mov     [rbp+var_40], 0
0x18002a050  mov     rcx, rdx
0x18002a053  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002a058  mov     [rbp+var_3C], 1
0x18002a05f  lea     rax, [rbp+var_40]
0x18002a063  mov     [rsp+70h+lpData], rax
0x18002a068  lea     r9, ValueName; "ActivePolicyCode"
0x18002a06f  xor     r8d, r8d
0x18002a072  mov     rdx, [r10]
0x18002a075  lea     rcx, [rbp+var_28]
0x18002a079  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a07e  mov     rdx, rax
0x18002a081  mov     rcx, rbx
0x18002a084  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a089  lea     rcx, [rbp+var_28]
0x18002a08d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a092  cmp     [rbp+var_40], 0
0x18002a096  jz      short loc_18002A0A3
0x18002a098  cmp     qword ptr [rbx+10h], 0
0x18002a09d  jnz     loc_18002A13F
0x18002a0a3  lea     rax, [rbp+var_40]
0x18002a0a7  mov     [rsp+70h+lpData], rax
0x18002a0ac  lea     r9, ValueName; "ActivePolicyCode"
0x18002a0b3  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002a0ba  mov     rdx, 0FFFFFFFF80000002h
0x18002a0c1  lea     rcx, [rbp+var_28]
0x18002a0c5  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x18002a0ca  mov     rdx, rax
0x18002a0cd  mov     rcx, rbx
0x18002a0d0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a0d5  lea     rcx, [rbp+var_28]
0x18002a0d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a0de  cmp     [rbp+var_40], 0
0x18002a0e2  jz      short loc_18002A13F
0x18002a0e4  cmp     qword ptr [rbx+10h], 0
0x18002a0e9  jz      short loc_18002A13F
0x18002a0eb  mov     edx, 0F003Fh
0x18002a0f0  lea     rcx, [rbp+phkResult]; phkResult
0x18002a0f4  call    ?GetCapabilitiesKey@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetCapabilitiesKey(ulong)
0x18002a0f9  mov     r10, [rbp+phkResult]
0x18002a0fd  test    r10, r10
0x18002a100  jz      short loc_18002A136
0x18002a102  mov     rcx, rbx
0x18002a105  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a10a  mov     ecx, [rbx+10h]
0x18002a10d  lea     ecx, ds:2[rcx*2]
0x18002a114  mov     [rsp+70h+cbData], ecx; cbData
0x18002a118  mov     [rsp+70h+lpData], rax; lpData
0x18002a11d  mov     r9d, 1; dwType
0x18002a123  xor     r8d, r8d; Reserved
0x18002a126  lea     rdx, ValueName; "ActivePolicyCode"
0x18002a12d  mov     rcx, r10; hKey
0x18002a130  call    cs:__imp_RegSetValueExW
0x18002a136  lea     rcx, [rbp+phkResult]
0x18002a13a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a13f  mov     rax, rbx
0x18002a142  mov     rcx, [rbp+var_8]
0x18002a146  xor     rcx, rsp; StackCookie
0x18002a149  call    __security_check_cookie
0x18002a14e  mov     rbx, [rsp+70h+arg_0]
0x18002a156  add     rsp, 70h
0x18002a15a  pop     rbp
0x18002a15b  retn
```
