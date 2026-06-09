# Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x1800428a8`
- end: `0x1800429a6`
- name: `?GetPackageFullNameFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `254`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004f7d4`
- `0x18005ef00`
- `0x18006ae88`
- `0x1800901e0`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18002576c`
- `0x1800257ec`
- `0x180029408`
- `0x1800299c4`
- `0x18003cf4c`
- `0x18003f2d8`
- `0x1800428a8`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800428df`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18004294c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x1800428df`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18004294c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromToken(__int64 a1, HANDLE *a2)
{
  unsigned int PackageFullNameFromToken; // eax
  WCHAR *v5; // rax
  unsigned int v6; // eax
  UINT32 packageFullNameLength[4]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v9[32]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  packageFullNameLength[1] = HIDWORD(a1);
  packageFullNameLength[0] = 0;
  PackageFullNameFromToken = GetPackageFullNameFromToken(*a2, packageFullNameLength, 0);
  if ( PackageFullNameFromToken == 15700 )
  {
    std::wstring::wstring(a1);
  }
  else
  {
    if ( PackageFullNameFromToken != 122 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x247,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)PackageFullNameFromToken,
        packageFullNameLength[0]);
    std::wstring::wstring(v9, packageFullNameLength[0]);
    std::wstring::resize(v9, packageFullNameLength[0] - 1);
    v5 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
    v6 = GetPackageFullNameFromToken(*a2, packageFullNameLength, v5);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x250,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v6,
        packageFullNameLength[0]);
    std::wstring::wstring(a1, v9);
    std::wstring::_Tidy_deallocate(v9);
  }
  return a1;
}

```

## disassembly

```asm
0x1800428a8  mov     [rsp+arg_10], rbx
0x1800428ad  push    rdi
0x1800428ae  sub     rsp, 60h
0x1800428b2  mov     rax, cs:__security_cookie
0x1800428b9  xor     rax, rsp
0x1800428bc  mov     [rsp+68h+var_18], rax
0x1800428c1  mov     rdi, rdx
0x1800428c4  mov     rbx, rcx
0x1800428c7  mov     qword ptr [rsp+68h+packageFullNameLength], rcx
0x1800428cc  mov     [rsp+68h+packageFullNameLength], 0; unsigned int
0x1800428d4  xor     r8d, r8d; packageFullName
0x1800428d7  lea     rdx, [rsp+68h+packageFullNameLength]; packageFullNameLength
0x1800428dc  mov     rcx, [rdi]; token
0x1800428df  call    cs:__imp_GetPackageFullNameFromToken
0x1800428e5  cmp     eax, 3D54h
0x1800428ea  jnz     short loc_1800428F9
0x1800428ec  mov     rcx, rbx
0x1800428ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800428f4  jmp     loc_180042988
0x1800428f9  cmp     eax, 7Ah ; 'z'
0x1800428fc  jz      short loc_180042918
0x1800428fe  mov     rcx, [rsp+68h]; this
0x180042903  mov     r9d, eax; char *
0x180042906  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004290d  mov     edx, 247h; void *
0x180042912  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180042918  mov     edx, [rsp+68h+packageFullNameLength]
0x18004291c  lea     rcx, [rsp+68h+var_38]
0x180042921  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180042926  nop
0x180042927  mov     edx, [rsp+68h+packageFullNameLength]
0x18004292b  dec     edx
0x18004292d  lea     rcx, [rsp+68h+var_38]
0x180042932  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180042937  lea     rcx, [rsp+68h+var_38]
0x18004293c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042941  mov     r8, rax; packageFullName
0x180042944  lea     rdx, [rsp+68h+packageFullNameLength]; packageFullNameLength
0x180042949  mov     rcx, [rdi]; token
0x18004294c  call    cs:__imp_GetPackageFullNameFromToken
0x180042952  mov     rcx, [rsp+68h]; this
0x180042957  test    eax, eax
0x180042959  jz      short loc_180042970
0x18004295b  mov     r9d, eax; char *
0x18004295e  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042965  mov     edx, 250h; void *
0x18004296a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180042970  lea     rdx, [rsp+68h+var_38]
0x180042975  mov     rcx, rbx
0x180042978  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18004297d  nop
0x18004297e  lea     rcx, [rsp+68h+var_38]
0x180042983  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042988  mov     rax, rbx
0x18004298b  mov     rcx, [rsp+68h+var_18]
0x180042990  xor     rcx, rsp; StackCookie
0x180042993  call    __security_check_cookie
0x180042998  mov     rbx, [rsp+68h+arg_10]
0x1800429a0  add     rsp, 60h
0x1800429a4  pop     rdi
0x1800429a5  retn
```
