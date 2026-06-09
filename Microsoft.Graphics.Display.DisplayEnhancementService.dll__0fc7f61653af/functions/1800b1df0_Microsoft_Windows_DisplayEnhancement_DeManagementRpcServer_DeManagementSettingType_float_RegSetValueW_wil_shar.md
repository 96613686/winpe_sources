# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<float>::RegSetValueW(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800b1df0`
- end: `0x1800b1efb`
- name: `?RegSetValueW@?$DeManagementSettingType@M@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@QEAAXV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `267`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800ba2d0`
- `0x1800ba484`
- `0x1800bc00c`
- `0x1800bc1c0`
- `0x1800e784e`
- `0x1800e78ee`
- `0x1800e83a5`
- `0x1800e8445`

## callees

- `0x180006440`
- `0x180009984`
- `0x18000fa0c`
- `0x180011814`
- `0x180013578`
- `0x1800a1998`
- `0x1800a1c6c`
- `0x1800b1df0`
- `0x1800bda54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1eb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1eb2`

## string_xrefs

- `0x1800b1ec3`: `onecore\private\drivers\inc\bluetooth\foundation\RegistryHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementSettingType<float>::RegSetValueW(
        __int64 a1,
        HKEY *a2,
        __int64 a3)
{
  char *v6; // rdi
  __int64 v7; // r8
  char *v8; // rax
  __int64 v9; // rbx
  const WCHAR *v10; // rax
  int v11; // edx
  const BYTE *v12; // r8
  HKEY v13; // rcx
  unsigned int v14; // eax
  unsigned int lpData; // [rsp+20h] [rbp-30h]
  char *v17; // [rsp+30h] [rbp-20h] BYREF
  void *v18; // [rsp+38h] [rbp-18h]
  __int64 v19; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 v21; // [rsp+80h] [rbp+30h] BYREF
  HKEY *v22; // [rsp+88h] [rbp+38h]

  v22 = a2;
  std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>(&v17);
  v6 = (char *)v18;
  v7 = (_BYTE *)v18 - v17;
  if ( (unsigned __int64)((_BYTE *)v18 - v17) <= 4 )
  {
    if ( (unsigned __int64)((_BYTE *)v18 - v17) >= 4 )
      goto LABEL_8;
    if ( (unsigned __int64)(v19 - (_QWORD)v17) < 4 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v17);
      goto LABEL_8;
    }
    v9 = 4 - v7;
    memset_0(v18, 0, 4 - v7);
    v8 = &v6[v9];
  }
  else
  {
    v8 = v17 + 4;
  }
  v18 = v8;
LABEL_8:
  std::copy<unsigned char *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>>(
    &v21,
    (const void *)(a1 + 8),
    a1 + 12,
    v17);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v18, v17);
  v13 = *a2;
  if ( *a2 )
    v13 = *(HKEY *)v13;
  v14 = RegSetValueExW(v13, v10, 0, 3u, v12, v11 - (_DWORD)v12);
  if ( v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\RegistryHelpers.h",
      (const char *)v14,
      lpData);
  std::vector<unsigned char>::_Tidy(&v17);
  return std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<unsigned int,unsigned int>>>>(a2);
}

```

## disassembly

```asm
0x1800b1df0  mov     [rsp-28h+arg_10], rbx
0x1800b1df5  mov     [rsp-28h+arg_8], rdx
0x1800b1dfa  push    rbp
0x1800b1dfb  push    rsi
0x1800b1dfc  push    rdi
0x1800b1dfd  push    r14
0x1800b1dff  push    r15
0x1800b1e01  mov     rbp, rsp
0x1800b1e04  sub     rsp, 50h
0x1800b1e08  mov     r15, r8
0x1800b1e0b  mov     rsi, rdx
0x1800b1e0e  mov     r14, rcx
0x1800b1e11  lea     rcx, [rbp+var_20]
0x1800b1e15  call    ??0?$vector@UMilliLuxToPercentageMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@V?$allocator@UMilliLuxToPercentageMapping@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>::vector<Microsoft::Windows::DisplayEnhancement::Foundation::MilliLuxToPercentageMapping>(void)
0x1800b1e1a  nop
0x1800b1e1b  mov     r9, [rbp+var_20]
0x1800b1e1f  mov     rdi, [rbp+var_18]
0x1800b1e23  mov     r8, rdi
0x1800b1e26  sub     r8, r9
0x1800b1e29  mov     ebx, 4
0x1800b1e2e  cmp     r8, rbx
0x1800b1e31  jbe     short loc_1800B1E39
0x1800b1e33  lea     rax, [r9+4]
0x1800b1e37  jmp     short loc_1800B1E66
0x1800b1e39  jnb     short loc_1800B1E6A
0x1800b1e3b  mov     rax, [rbp+var_10]
0x1800b1e3f  sub     rax, r9
0x1800b1e42  cmp     rax, rbx
0x1800b1e45  jnb     short loc_1800B1E52
0x1800b1e47  lea     rcx, [rbp+var_20]
0x1800b1e4b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800b1e50  jmp     short loc_1800B1E6A
0x1800b1e52  sub     rbx, r8
0x1800b1e55  mov     r8, rbx; Size
0x1800b1e58  xor     edx, edx; Val
0x1800b1e5a  mov     rcx, rdi; void *
0x1800b1e5d  call    memset_0
0x1800b1e62  lea     rax, [rbx+rdi]
0x1800b1e66  mov     [rbp+var_18], rax
0x1800b1e6a  lea     r8, [r14+0Ch]
0x1800b1e6e  lea     rdx, [r14+8]
0x1800b1e72  mov     r9, [rbp+var_20]
0x1800b1e76  lea     rcx, [rbp+arg_0]
0x1800b1e7a  call    ??$copy@PEAEV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@PEAE0V10@@Z; std::copy<uchar *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>>(uchar *,uchar *,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>)
0x1800b1e7f  mov     r8, [rbp+var_20]
0x1800b1e83  mov     rdx, [rbp+var_18]
0x1800b1e87  mov     rcx, r15
0x1800b1e8a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b1e8f  mov     rcx, [rsi]
0x1800b1e92  test    rcx, rcx
0x1800b1e95  jz      short loc_1800B1E9A
0x1800b1e97  mov     rcx, [rcx]; hKey
0x1800b1e9a  sub     edx, r8d
0x1800b1e9d  mov     [rsp+50h+cbData], edx; cbData
0x1800b1ea1  mov     [rsp+50h+lpData], r8; unsigned int
0x1800b1ea6  mov     r9d, 3; dwType
0x1800b1eac  xor     r8d, r8d; Reserved
0x1800b1eaf  mov     rdx, rax; lpValueName
0x1800b1eb2  call    cs:__imp_RegSetValueExW
0x1800b1eb8  mov     rcx, [rbp+28h]; this
0x1800b1ebc  test    eax, eax
0x1800b1ebe  jz      short loc_1800B1ED5
0x1800b1ec0  mov     r9d, eax; char *
0x1800b1ec3  lea     r8, aOnecorePrivate; "onecore\\private\\drivers\\inc\\bluetoo"...
0x1800b1eca  mov     edx, 53h ; 'S'; void *
0x1800b1ecf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b1ed5  lea     rcx, [rbp+var_20]
0x1800b1ed9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800b1ede  nop
0x1800b1edf  mov     rcx, rsi
0x1800b1ee2  call    ??1?$shared_ptr@V?$OEMSetting@V?$vector@V?$tuple@II@std@@V?$allocator@V?$tuple@II@std@@@2@@std@@@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<uint,uint>>>>::~shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<std::vector<std::tuple<uint,uint>>>>(void)
0x1800b1ee7  mov     rbx, [rsp+50h+arg_10]
0x1800b1eef  add     rsp, 50h
0x1800b1ef3  pop     r15
0x1800b1ef5  pop     r14
0x1800b1ef7  pop     rdi
0x1800b1ef8  pop     rsi
0x1800b1ef9  pop     rbp
0x1800b1efa  retn
```
