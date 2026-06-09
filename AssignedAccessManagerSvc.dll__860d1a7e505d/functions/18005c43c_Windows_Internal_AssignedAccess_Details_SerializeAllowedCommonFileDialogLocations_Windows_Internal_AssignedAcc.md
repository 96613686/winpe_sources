# Windows::Internal::AssignedAccess::Details::SerializeAllowedCommonFileDialogLocations<Windows::Internal::AssignedAccess::RegistryKeyBroker>(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation> *)

- ea: `0x18005c43c`
- end: `0x18005c4dc`
- name: `??$SerializeAllowedCommonFileDialogLocations@VRegistryKeyBroker@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAXAEAVRegistryKeyBroker@123@PEAU?$IVectorView@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@Collections@Foundation@3@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d4e8`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x18002b190`
- `0x18005c43c`
- `0x18005f868`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c49b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c49b`

## string_xrefs

- `0x18005c4ad`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005c460`: `AllowedCommonFileDialogLocations`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::SerializeAllowedCommonFileDialogLocations<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
        __int64 a1,
        __int64 a2)
{
  const WCHAR *v3; // rax
  unsigned int v4; // eax
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  BYTE Data[8]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_DWORD *)Data = Windows::Internal::AssignedAccess::Details::CommonFileDialogLocationsConverter::ConvertFromLocationsToBitset(a2);
  std::wstring::wstring(v8, L"AllowedCommonFileDialogLocations");
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
  v4 = RegSetValueExW(*(HKEY *)(a1 + 16), v3, 0, 4u, Data, 4u);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v4,
      lpData);
  return std::wstring::_Tidy_deallocate(v8);
}

```

## disassembly

```asm
0x18005c43c  push    rbx
0x18005c43e  sub     rsp, 60h
0x18005c442  mov     rax, cs:__security_cookie
0x18005c449  xor     rax, rsp
0x18005c44c  mov     [rsp+68h+var_10], rax
0x18005c451  mov     rbx, rcx
0x18005c454  mov     rcx, rdx
0x18005c457  call    ?ConvertFromLocationsToBitset@CommonFileDialogLocationsConverter@Details@AssignedAccess@Internal@Windows@@SAKPEAU?$IVectorView@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@Collections@Foundation@5@@Z; Windows::Internal::AssignedAccess::Details::CommonFileDialogLocationsConverter::ConvertFromLocationsToBitset(Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation> *)
0x18005c45c  mov     dword ptr [rsp+68h+Data], eax
0x18005c460  lea     rdx, aAllowedcommonf; "AllowedCommonFileDialogLocations"
0x18005c467  lea     rcx, [rsp+68h+var_30]
0x18005c46c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c471  nop
0x18005c472  lea     rcx, [rsp+68h+var_30]
0x18005c477  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c47c  mov     rdx, rax; lpValueName
0x18005c47f  mov     r9d, 4; dwType
0x18005c485  mov     [rsp+68h+cbData], r9d; cbData
0x18005c48a  lea     rax, [rsp+68h+Data]
0x18005c48f  mov     [rsp+68h+lpData], rax; unsigned int
0x18005c494  xor     r8d, r8d; Reserved
0x18005c497  mov     rcx, [rbx+10h]; hKey
0x18005c49b  call    cs:__imp_RegSetValueExW
0x18005c4a1  mov     rcx, [rsp+68h]; this
0x18005c4a6  test    eax, eax
0x18005c4a8  jz      short loc_18005C4BF
0x18005c4aa  mov     r9d, eax; char *
0x18005c4ad  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005c4b4  mov     edx, 0CDh; void *
0x18005c4b9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005c4bf  lea     rcx, [rsp+68h+var_30]
0x18005c4c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c4c9  mov     rcx, [rsp+68h+var_10]
0x18005c4ce  xor     rcx, rsp; StackCookie
0x18005c4d1  call    __security_check_cookie
0x18005c4d6  add     rsp, 60h
0x18005c4da  pop     rbx
0x18005c4db  retn
```
