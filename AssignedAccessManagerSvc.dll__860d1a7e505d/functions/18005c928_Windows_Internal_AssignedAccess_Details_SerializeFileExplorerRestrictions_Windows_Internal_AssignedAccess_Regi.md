# Windows::Internal::AssignedAccess::Details::SerializeFileExplorerRestrictions<Windows::Internal::AssignedAccess::RegistryKeyBroker>(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessFileExplorerRestrictions *)

- ea: `0x18005c928`
- end: `0x18005cab8`
- name: `??$SerializeFileExplorerRestrictions@VRegistryKeyBroker@AssignedAccess@Internal@Windows@@@Details@AssignedAccess@Internal@Windows@@YAXAEAVRegistryKeyBroker@123@PEAUIAssignedAccessFileExplorerRestrictions@123@@Z`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d4e8`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180020050`
- `0x18002b190`
- `0x18005c928`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c9c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ca6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c9c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005ca6e`

## string_xrefs

- `0x18005c9d9`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005ca7f`: `onecoreuap\internal\base\inc\embedded\registrykey.h`
- `0x18005c970`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`
- `0x18005ca16`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registryserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::Details::SerializeFileExplorerRestrictions<Windows::Internal::AssignedAccess::RegistryKeyBroker>(
        __int64 a1,
        __int64 a2)
{
  int v4; // eax
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  int v7; // eax
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  int lpData; // [rsp+20h] [rbp-40h]
  unsigned int lpDataa; // [rsp+20h] [rbp-40h]
  unsigned int lpDatab; // [rsp+20h] [rbp-40h]
  char v14; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v15[3]; // [rsp+31h] [rbp-2Fh] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-2Ch] BYREF
  _BYTE v17[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v14 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a2 + 48LL))(a2, &v14);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26A,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v4,
      lpData);
  *(_DWORD *)Data = v14 != 0;
  std::wstring::wstring(v17, L"AllowRemovableDrives");
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  v6 = RegSetValueExW(*(HKEY *)(a1 + 16), v5, 0, 4u, Data, 4u);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v6,
      lpDataa);
  std::wstring::_Tidy_deallocate(v17);
  v15[0] = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 64LL))(a2, v15);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registryserializer.cpp",
      (const char *)(unsigned int)v7,
      lpDataa);
  *(_DWORD *)Data = v15[0] != 0;
  std::wstring::wstring(v17, L"NoRestriction");
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  v9 = RegSetValueExW(*(HKEY *)(a1 + 16), v8, 0, 4u, Data, 4u);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\internal\\base\\inc\\embedded\\registrykey.h",
      (const char *)v9,
      lpDatab);
  return std::wstring::_Tidy_deallocate(v17);
}

```

## disassembly

```asm
0x18005c928  mov     [rsp-8+arg_10], rbx
0x18005c92d  mov     [rsp-8+arg_18], rdi
0x18005c932  push    rbp
0x18005c933  mov     rbp, rsp
0x18005c936  sub     rsp, 60h
0x18005c93a  mov     rax, cs:__security_cookie
0x18005c941  xor     rax, rsp
0x18005c944  mov     [rbp+var_8], rax
0x18005c948  mov     rbx, rdx
0x18005c94b  mov     rdi, rcx
0x18005c94e  mov     [rbp+var_30], 0
0x18005c952  mov     rax, [rdx]
0x18005c955  lea     rdx, [rbp+var_30]
0x18005c959  mov     rcx, rbx
0x18005c95c  mov     rax, [rax+30h]
0x18005c960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c965  mov     rcx, [rbp+8]; this
0x18005c969  test    eax, eax
0x18005c96b  jns     short loc_18005C982
0x18005c96d  mov     r9d, eax; char *
0x18005c970  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005c977  mov     edx, 26Ah; void *
0x18005c97c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005c982  xor     eax, eax
0x18005c984  cmp     [rbp+var_30], al
0x18005c987  setnz   al
0x18005c98a  mov     dword ptr [rbp+Data], eax
0x18005c98d  lea     rdx, aAllowremovable; "AllowRemovableDrives"
0x18005c994  lea     rcx, [rbp+var_28]
0x18005c998  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005c99d  nop
0x18005c99e  lea     rcx, [rbp+var_28]
0x18005c9a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c9a7  mov     rdx, rax; lpValueName
0x18005c9aa  mov     [rsp+60h+cbData], 4; cbData
0x18005c9b2  lea     rax, [rbp+Data]
0x18005c9b6  mov     [rsp+60h+lpData], rax; int
0x18005c9bb  mov     r9d, 4; dwType
0x18005c9c1  xor     r8d, r8d; Reserved
0x18005c9c4  mov     rcx, [rdi+10h]; hKey
0x18005c9c8  call    cs:__imp_RegSetValueExW
0x18005c9ce  mov     rcx, [rbp+8]; this
0x18005c9d2  test    eax, eax
0x18005c9d4  jz      short loc_18005C9EB
0x18005c9d6  mov     r9d, eax; char *
0x18005c9d9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005c9e0  mov     edx, 0CDh; void *
0x18005c9e5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005c9eb  lea     rcx, [rbp+var_28]
0x18005c9ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c9f4  mov     [rbp+var_2F], 0
0x18005c9f8  mov     rax, [rbx]
0x18005c9fb  lea     rdx, [rbp+var_2F]
0x18005c9ff  mov     rcx, rbx
0x18005ca02  mov     rax, [rax+40h]
0x18005ca06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca0b  mov     rcx, [rbp+8]; this
0x18005ca0f  test    eax, eax
0x18005ca11  jns     short loc_18005CA28
0x18005ca13  mov     r9d, eax; char *
0x18005ca16  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005ca1d  mov     edx, 26Eh; void *
0x18005ca22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ca28  xor     eax, eax
0x18005ca2a  cmp     [rbp+var_2F], al
0x18005ca2d  setnz   al
0x18005ca30  mov     dword ptr [rbp+Data], eax
0x18005ca33  lea     rdx, aNorestriction; "NoRestriction"
0x18005ca3a  lea     rcx, [rbp+var_28]
0x18005ca3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ca43  nop
0x18005ca44  lea     rcx, [rbp+var_28]
0x18005ca48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005ca4d  mov     rdx, rax; lpValueName
0x18005ca50  mov     [rsp+60h+cbData], 4; cbData
0x18005ca58  lea     rax, [rbp+Data]
0x18005ca5c  mov     [rsp+60h+lpData], rax; unsigned int
0x18005ca61  mov     r9d, 4; dwType
0x18005ca67  xor     r8d, r8d; Reserved
0x18005ca6a  mov     rcx, [rdi+10h]; hKey
0x18005ca6e  call    cs:__imp_RegSetValueExW
0x18005ca74  mov     rcx, [rbp+8]; this
0x18005ca78  test    eax, eax
0x18005ca7a  jz      short loc_18005CA91
0x18005ca7c  mov     r9d, eax; char *
0x18005ca7f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\embedd"...
0x18005ca86  mov     edx, 0CDh; void *
0x18005ca8b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18005ca91  lea     rcx, [rbp+var_28]
0x18005ca95  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ca9a  mov     rcx, [rbp+var_8]
0x18005ca9e  xor     rcx, rsp; StackCookie
0x18005caa1  call    __security_check_cookie
0x18005caa6  lea     r11, [rsp+60h+var_s0]
0x18005caab  mov     rbx, [r11+20h]
0x18005caaf  mov     rdi, [r11+28h]
0x18005cab3  mov     rsp, r11
0x18005cab6  pop     rbp
0x18005cab7  retn
```
