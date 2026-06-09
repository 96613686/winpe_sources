# _Windows::FileSystem::ReFs::JsonFormatting::WriteVolumeId_::_2_::_lambda_1_::operator()

- ea: `0x14005f6b8`
- end: `0x14005f850`
- name: `_Windows::FileSystem::ReFs::JsonFormatting::WriteVolumeId_::_2_::_lambda_1_::operator()`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14005a1e0`

## callees

- `0x140004870`
- `0x14001452c`
- `0x140014ff0`
- `0x140019600`
- `0x14001983c`
- `0x140024354`
- `0x140050094`
- `0x140058cc4`
- `0x14005a484`
- `0x14005e244`
- `0x1400614a4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14005f7de`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14005f7de`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14005f775`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14005f775`

## string_xrefs

- `0x14005f7f4`: `MountPoints`
- `0x14005f6f5`: `VolumeGuidPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::FileSystem::ReFs::JsonFormatting::WriteVolumeId_::_2_::_lambda_1_::operator()(_QWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rdi
  _QWORD *v9; // rax
  const WCHAR *v10; // rsi
  const WCHAR *v12; // [rsp+20h] [rbp-60h] BYREF
  __int64 v13; // [rsp+28h] [rbp-58h]
  _QWORD v14[2]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v15[16]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+50h] [rbp-30h]

  v2 = a1[1];
  v3 = *a1;
  v4 = std::basic_ostream<unsigned short>::operator<<(*a1, 34);
  v12 = L"VolumeGuidPath";
  v13 = 14;
  v5 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v4, &v12);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, (__int64)L"\": ");
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2 + 32);
  v13 = *(_QWORD *)(v2 + 48);
  Windows::FileSystem::ReFs::JsonFormatting::write_jsonString(v3, &v12);
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[1] + 32LL);
  v13 = *(_QWORD *)(v6 + 48);
  Windows::FileSystem::ReFs::GetVolumePathNamesForVolumeNameW((__int64)v15, &v12);
  std::basic_ostream<unsigned short>::operator<<(*a1, Windows::FileSystem::ReFs::JsonFormatting::next_property);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  v8 = v16;
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(0xA0u);
  v10 = (const WCHAR *)(v9 + 4);
  v12 = (const WCHAR *)(v9 + 4);
  v9[17] = v7;
  v9[18] = v8;
  *((_BYTE *)v9 + 153) = 0;
  v9[4] = Microsoft::PathParsing::split_string__ResumeCoro_1_unsigned_short__Microsoft::PathParsing::single_char_tokenizer_unsigned_short_0_::Tokenize_::_2_::_lambda_1___;
  *((_DWORD *)v9 + 10) = 65538;
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  __ExceptionPtrCreate(v9 + 1);
  v12 = v10;
  *((_BYTE *)v10 + 96) = 0;
  v14[0] = L"MountPoints";
  v14[1] = 11;
  Windows::FileSystem::ReFs::JsonFormatting::WriteJsonProperty<std::experimental::generator<wil::basic_zstring_view<unsigned short>,std::allocator<char>>>(
    *a1,
    v14,
    &v12);
  std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::~generator<std::basic_string_view<unsigned short>,std::allocator<char>>(&v12);
  return std::wstring::_Tidy_deallocate(v15);
}

```

## disassembly

```asm
0x14005f6b8  mov     [rsp-18h+arg_8], rbx
0x14005f6bd  mov     [rsp-18h+arg_10], rsi
0x14005f6c2  push    rbp
0x14005f6c3  push    rdi
0x14005f6c4  push    r14
0x14005f6c6  mov     rbp, rsp
0x14005f6c9  sub     rsp, 80h
0x14005f6d0  mov     rax, cs:__security_cookie
0x14005f6d7  xor     rax, rsp
0x14005f6da  mov     [rbp+var_10], rax
0x14005f6de  mov     r14, rcx
0x14005f6e1  mov     rbx, [rcx+8]
0x14005f6e5  mov     rdi, [rcx]
0x14005f6e8  mov     edx, 22h ; '"'
0x14005f6ed  mov     rcx, rdi
0x14005f6f0  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x14005f6f5  lea     rcx, aVolumeguidpath; "VolumeGuidPath"
0x14005f6fc  mov     [rbp+var_60], rcx
0x14005f700  mov     [rbp+var_58], 0Eh
0x14005f708  lea     rdx, [rbp+var_60]
0x14005f70c  mov     rcx, rax
0x14005f70f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@V?$basic_string_view@GU?$char_traits@G@std@@@0@@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,std::basic_string_view<ushort>)
0x14005f714  mov     rcx, rax
0x14005f717  lea     rdx, asc_1401E6AC8; "\": "
0x14005f71e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f723  lea     rcx, [rbx+20h]
0x14005f727  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14005f72c  mov     [rbp+var_60], rax
0x14005f730  mov     rax, [rbx+30h]
0x14005f734  mov     [rbp+var_58], rax
0x14005f738  lea     rdx, [rbp+var_60]
0x14005f73c  mov     rcx, rdi
0x14005f73f  call    ?write_jsonString@JsonFormatting@ReFs@FileSystem@Windows@@YAXAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@6@@Z; Windows::FileSystem::ReFs::JsonFormatting::write_jsonString(std::basic_ostream<ushort> &,std::basic_string_view<ushort>)
0x14005f744  mov     rdx, [r14+8]
0x14005f748  lea     rcx, [rdx+20h]
0x14005f74c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14005f751  mov     [rbp+var_60], rax
0x14005f755  mov     rax, [rdx+30h]
0x14005f759  mov     [rbp+var_58], rax
0x14005f75d  lea     rdx, [rbp+var_60]
0x14005f761  lea     rcx, [rbp+var_40]
0x14005f765  call    ?GetVolumePathNamesForVolumeNameW@ReFs@FileSystem@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@G@wil@@@Z; Windows::FileSystem::ReFs::GetVolumePathNamesForVolumeNameW(wil::basic_zstring_view<ushort>)
0x14005f76a  nop
0x14005f76b  lea     rdx, ?next_property@JsonFormatting@ReFs@FileSystem@Windows@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV56@@Z; Windows::FileSystem::ReFs::JsonFormatting::next_property(std::basic_ostream<ushort> &)
0x14005f772  mov     rcx, [r14]
0x14005f775  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14005f77c  nop     dword ptr [rax+rax+00h]
0x14005f781  lea     rcx, [rbp+var_40]
0x14005f785  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14005f78a  mov     rbx, rax
0x14005f78d  mov     rdi, [rbp+var_30]
0x14005f791  mov     ecx, 0A0h
0x14005f796  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14005f79b  mov     [rbp+var_60], rax
0x14005f79f  lea     rsi, [rax+20h]
0x14005f7a3  mov     [rbp+var_60], rsi
0x14005f7a7  mov     [rsi+68h], rbx
0x14005f7ab  mov     [rsi+70h], rdi
0x14005f7af  mov     byte ptr [rsi+79h], 0
0x14005f7b3  lea     rcx, Microsoft__PathParsing__split_string$_ResumeCoro$1_unsigned_short__Microsoft__PathParsing__single_char_tokenizer_unsigned_short_0___Tokenize____2____lambda_1___
0x14005f7ba  mov     [rsi], rcx
0x14005f7bd  mov     dword ptr [rsi+8], 10002h
0x14005f7c4  mov     qword ptr [rax], 0
0x14005f7cb  lea     rcx, [rsi-18h]
0x14005f7cf  mov     qword ptr [rcx], 0
0x14005f7d6  mov     qword ptr [rcx+8], 0
0x14005f7de  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x14005f7e5  nop     dword ptr [rax+rax+00h]
0x14005f7ea  nop
0x14005f7eb  mov     [rbp+var_60], rsi
0x14005f7ef  xor     eax, eax
0x14005f7f1  mov     [rsi+60h], al
0x14005f7f4  lea     rax, aMountpoints; "MountPoints"
0x14005f7fb  mov     [rbp+var_50], rax
0x14005f7ff  mov     [rbp+var_48], 0Bh
0x14005f807  lea     r8, [rbp+var_60]
0x14005f80b  lea     rdx, [rbp+var_50]
0x14005f80f  mov     rcx, [r14]
0x14005f812  call    ??$WriteJsonProperty@U?$generator@V?$basic_zstring_view@G@wil@@V?$allocator@D@std@@@experimental@std@@@JsonFormatting@ReFs@FileSystem@Windows@@YAXAEAV?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@5@AEBU?$generator@V?$basic_zstring_view@G@wil@@V?$allocator@D@std@@@experimental@5@@Z; Windows::FileSystem::ReFs::JsonFormatting::WriteJsonProperty<std::experimental::generator<wil::basic_zstring_view<ushort>,std::allocator<char>>>(std::basic_ostringstream<ushort> &,std::basic_string_view<ushort>,std::experimental::generator<wil::basic_zstring_view<ushort>,std::allocator<char>> const &)
0x14005f817  nop
0x14005f818  lea     rcx, [rbp+var_60]
0x14005f81c  call    ??1?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAA@XZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::~generator<std::basic_string_view<ushort>,std::allocator<char>>(void)
0x14005f821  nop
0x14005f822  lea     rcx, [rbp+var_40]
0x14005f826  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005f82b  mov     rcx, [rbp+var_10]
0x14005f82f  xor     rcx, rsp; StackCookie
0x14005f832  call    __security_check_cookie
0x14005f837  lea     r11, [rsp+80h+var_s0]
0x14005f83f  mov     rbx, [r11+28h]
0x14005f843  mov     rsi, [r11+30h]
0x14005f847  mov     rsp, r11
0x14005f84a  pop     r14
0x14005f84c  pop     rdi
0x14005f84d  pop     rbp
0x14005f84e  retn
```
