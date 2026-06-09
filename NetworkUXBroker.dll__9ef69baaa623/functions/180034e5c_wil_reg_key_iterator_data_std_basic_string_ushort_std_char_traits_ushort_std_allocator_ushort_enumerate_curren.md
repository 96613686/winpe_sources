# wil::reg::key_iterator_data<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::enumerate_current_index(void)

- ea: `0x180034e5c`
- end: `0x180035005`
- name: `?enumerate_current_index@?$key_iterator_data@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@AEAAJXZ`
- size: `425`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180027078`
- `0x1800299ec`

## callees

- `0x18000e768`
- `0x18000f054`
- `0x18001fcb4`
- `0x180030678`
- `0x1800345fc`
- `0x180034e5c`
- `0x1800369d0`
- `0x180037540`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180034f29`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180034f29`

## string_xrefs

- `0x180034ea8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180034f6f`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180034fb8`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`
- `0x180034ff3`: `onecore\internal\sdk\inc\wil\opensource\wil\registry_helpers.h`

## pseudocode

```c
int __fastcall wil::reg::key_iterator_data<std::wstring>::enumerate_current_index(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  DWORD v5; // eax
  __int64 v6; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  WCHAR *v10; // rax
  unsigned int v11; // eax
  int v12; // eax
  int v13; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD cchName; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 40) == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      a4);
  v5 = 32;
  if ( *(_DWORD *)(a1 + 48) )
    v5 = *(_DWORD *)(a1 + 48);
  while ( 1 )
  {
    v6 = v5;
    cchName = v5;
    if ( (unsigned __int64)v5 <= *(_QWORD *)(a1 + 48) )
    {
      v6 = *(_QWORD *)(a1 + 48);
    }
    else if ( (int)wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * v5) < 0 )
    {
      *(_QWORD *)(a1 + 48) = 0;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
        (const char *)0x8007000ELL,
        lpReserved);
      return -2147024882;
    }
    wil::reg::reg_iterator_details::clear_name(a1);
    *(_QWORD *)(a1 + 48) = v6;
    if ( !v6 )
      goto LABEL_7;
    v10 = cchName ? (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1, v8, v9) : 0LL;
    v11 = RegEnumKeyExW(*(HKEY *)(a1 + 32), *(_DWORD *)(a1 + 40), v10, &cchName, 0, 0, 0, 0);
    if ( !v11 )
      break;
    if ( v11 == 259 )
    {
      wil::reg::reg_iterator_details::clear_name(a1);
      *(_DWORD *)(a1 + 40) = -1;
      return 0;
    }
    if ( v11 != 234 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x646,
               (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
               (const char *)v11,
               lpReserved);
    if ( cchName >= 0x7F )
    {
      if ( cchName >= 0x100 )
        return 0;
      v5 = 256;
    }
    else
    {
      v5 = 127;
    }
  }
  ++cchName;
  v12 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(a1, 2 * cchName);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x625,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry_helpers.h",
      (const char *)(unsigned int)v12,
      lpReserved);
    return v13;
  }
  *(_QWORD *)(a1 + 48) = cchName;
  *(_QWORD *)(a1 + 48) = wil::reg::reg_view_details::reg_value_type_info::trim_buffer(a1);
  return 0;
}

```

## disassembly

```asm
0x180034e5c  mov     [rsp+arg_8], rbx
0x180034e61  push    rdi
0x180034e62  sub     rsp, 40h
0x180034e66  cmp     dword ptr [rcx+28h], 0FFFFFFFFh
0x180034e6a  mov     rbx, rcx
0x180034e6d  jz      loc_180034FEE
0x180034e73  cmp     dword ptr [rcx+30h], 0
0x180034e77  mov     eax, 20h ; ' '
0x180034e7c  cmova   eax, [rcx+30h]
0x180034e80  mov     edi, eax
0x180034e82  mov     [rsp+48h+cchName], eax
0x180034e86  cmp     rdi, [rbx+30h]
0x180034e8a  jbe     short loc_180034ECE
0x180034e8c  lea     edx, [rax+rax]
0x180034e8f  mov     rcx, rbx
0x180034e92  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x180034e97  test    eax, eax
0x180034e99  jns     short loc_180034ED2
0x180034e9b  mov     qword ptr [rbx+30h], 0
0x180034ea3  mov     rcx, [rsp+48h]; this
0x180034ea8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034eaf  mov     ebx, 8007000Eh
0x180034eb4  mov     edx, 60Fh; void *
0x180034eb9  mov     r9d, ebx; char *
0x180034ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034ec1  mov     eax, ebx
0x180034ec3  mov     rbx, [rsp+48h+arg_8]
0x180034ec8  add     rsp, 40h
0x180034ecc  pop     rdi
0x180034ecd  retn
0x180034ece  mov     rdi, [rbx+30h]
0x180034ed2  mov     rcx, rbx
0x180034ed5  call    ?clear_name@reg_iterator_details@reg@wil@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; wil::reg::reg_iterator_details::clear_name(std::wstring &,unsigned __int64)
0x180034eda  mov     [rbx+30h], rdi
0x180034ede  test    rdi, rdi
0x180034ee1  jz      short loc_180034EA3
0x180034ee3  cmp     [rsp+48h+cchName], 0
0x180034ee8  jnz     short loc_180034EEE
0x180034eea  xor     eax, eax
0x180034eec  jmp     short loc_180034EF6
0x180034eee  mov     rcx, rbx
0x180034ef1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034ef6  mov     edx, [rbx+28h]; dwIndex
0x180034ef9  lea     r9, [rsp+48h+cchName]; lpcchName
0x180034efe  mov     rcx, [rbx+20h]; hKey
0x180034f02  mov     r8, rax; lpName
0x180034f05  mov     [rsp+48h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180034f0e  mov     [rsp+48h+lpcchClass], 0; lpcchClass
0x180034f17  mov     [rsp+48h+lpClass], 0; lpClass
0x180034f20  mov     [rsp+48h+lpReserved], 0; int
0x180034f29  call    cs:__imp_RegEnumKeyExW
0x180034f2f  test    eax, eax
0x180034f31  jz      short loc_180034F99
0x180034f33  cmp     eax, 103h
0x180034f38  jz      short loc_180034F88
0x180034f3a  cmp     eax, 0EAh
0x180034f3f  jnz     short loc_180034F6A
0x180034f41  cmp     [rsp+48h+cchName], 7Fh
0x180034f46  jnb     short loc_180034F52
0x180034f48  mov     eax, 7Fh
0x180034f4d  jmp     loc_180034E80
0x180034f52  cmp     [rsp+48h+cchName], 100h
0x180034f5a  jnb     loc_180034FE7
0x180034f60  mov     eax, 100h
0x180034f65  jmp     loc_180034E80
0x180034f6a  mov     rcx, [rsp+48h]; this
0x180034f6f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034f76  mov     r9d, eax; char *
0x180034f79  mov     edx, 646h; void *
0x180034f7e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034f83  jmp     loc_180034EC3
0x180034f88  mov     rcx, rbx
0x180034f8b  call    ?clear_name@reg_iterator_details@reg@wil@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; wil::reg::reg_iterator_details::clear_name(std::wstring &,unsigned __int64)
0x180034f90  mov     dword ptr [rbx+28h], 0FFFFFFFFh
0x180034f97  jmp     short loc_180034FE7
0x180034f99  mov     edx, [rsp+48h+cchName]
0x180034f9d  mov     rcx, rbx
0x180034fa0  inc     edx
0x180034fa2  mov     [rsp+48h+cchName], edx
0x180034fa6  add     edx, edx
0x180034fa8  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x180034fad  mov     edi, eax
0x180034faf  test    eax, eax
0x180034fb1  jns     short loc_180034FD3
0x180034fb3  mov     rcx, [rsp+48h]; this
0x180034fb8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034fbf  mov     r9d, eax; char *
0x180034fc2  mov     edx, 625h; void *
0x180034fc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034fcc  mov     eax, edi
0x180034fce  jmp     loc_180034EC3
0x180034fd3  mov     eax, [rsp+48h+cchName]
0x180034fd7  mov     rcx, rbx
0x180034fda  mov     [rbx+30h], rax
0x180034fde  call    ?trim_buffer@reg_value_type_info@reg_view_details@reg@wil@@YA_KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wil::reg::reg_view_details::reg_value_type_info::trim_buffer(std::wstring &)
0x180034fe3  mov     [rbx+30h], rax
0x180034fe7  xor     eax, eax
0x180034fe9  jmp     loc_180034EC3
0x180034fee  mov     rcx, [rsp+48h]; this
0x180034ff3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034ffa  mov     edx, 606h; void *
0x180034fff  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
