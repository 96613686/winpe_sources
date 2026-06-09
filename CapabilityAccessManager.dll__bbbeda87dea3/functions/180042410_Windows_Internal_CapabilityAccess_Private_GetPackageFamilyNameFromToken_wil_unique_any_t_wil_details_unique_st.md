# Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x180042410`
- end: `0x18004250e`
- name: `?GetPackageFamilyNameFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `254`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180040788`
- `0x180043b0c`
- `0x18006ae88`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18002576c`
- `0x1800257ec`
- `0x180029408`
- `0x1800299c4`
- `0x18003cf4c`
- `0x18003f2d8`
- `0x180042410`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180042447`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800424b4`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180042447`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x1800424b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromToken(__int64 a1, HANDLE *a2)
{
  unsigned int PackageFamilyNameFromToken; // eax
  WCHAR *v5; // rax
  unsigned int v6; // eax
  UINT32 packageFamilyNameLength[4]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v9[32]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  packageFamilyNameLength[1] = HIDWORD(a1);
  packageFamilyNameLength[0] = 0;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(*a2, packageFamilyNameLength, 0);
  if ( PackageFamilyNameFromToken == 15700 )
  {
    std::wstring::wstring(a1);
  }
  else
  {
    if ( PackageFamilyNameFromToken != 122 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x21F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)PackageFamilyNameFromToken,
        packageFamilyNameLength[0]);
    std::wstring::wstring(v9, packageFamilyNameLength[0]);
    std::wstring::resize(v9, packageFamilyNameLength[0] - 1);
    v5 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
    v6 = GetPackageFamilyNameFromToken(*a2, packageFamilyNameLength, v5);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v6,
        packageFamilyNameLength[0]);
    std::wstring::wstring(a1, v9);
    std::wstring::_Tidy_deallocate(v9);
  }
  return a1;
}

```

## disassembly

```asm
0x180042410  mov     [rsp+arg_10], rbx
0x180042415  push    rdi
0x180042416  sub     rsp, 60h
0x18004241a  mov     rax, cs:__security_cookie
0x180042421  xor     rax, rsp
0x180042424  mov     [rsp+68h+var_18], rax
0x180042429  mov     rdi, rdx
0x18004242c  mov     rbx, rcx
0x18004242f  mov     qword ptr [rsp+68h+packageFamilyNameLength], rcx
0x180042434  mov     [rsp+68h+packageFamilyNameLength], 0; unsigned int
0x18004243c  xor     r8d, r8d; packageFamilyName
0x18004243f  lea     rdx, [rsp+68h+packageFamilyNameLength]; packageFamilyNameLength
0x180042444  mov     rcx, [rdi]; token
0x180042447  call    cs:__imp_GetPackageFamilyNameFromToken
0x18004244d  cmp     eax, 3D54h
0x180042452  jnz     short loc_180042461
0x180042454  mov     rcx, rbx
0x180042457  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004245c  jmp     loc_1800424F0
0x180042461  cmp     eax, 7Ah ; 'z'
0x180042464  jz      short loc_180042480
0x180042466  mov     rcx, [rsp+68h]; this
0x18004246b  mov     r9d, eax; char *
0x18004246e  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042475  mov     edx, 21Fh; void *
0x18004247a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180042480  mov     edx, [rsp+68h+packageFamilyNameLength]
0x180042484  lea     rcx, [rsp+68h+var_38]
0x180042489  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18004248e  nop
0x18004248f  mov     edx, [rsp+68h+packageFamilyNameLength]
0x180042493  dec     edx
0x180042495  lea     rcx, [rsp+68h+var_38]
0x18004249a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004249f  lea     rcx, [rsp+68h+var_38]
0x1800424a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800424a9  mov     r8, rax; packageFamilyName
0x1800424ac  lea     rdx, [rsp+68h+packageFamilyNameLength]; packageFamilyNameLength
0x1800424b1  mov     rcx, [rdi]; token
0x1800424b4  call    cs:__imp_GetPackageFamilyNameFromToken
0x1800424ba  mov     rcx, [rsp+68h]; this
0x1800424bf  test    eax, eax
0x1800424c1  jz      short loc_1800424D8
0x1800424c3  mov     r9d, eax; char *
0x1800424c6  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800424cd  mov     edx, 228h; void *
0x1800424d2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800424d8  lea     rdx, [rsp+68h+var_38]
0x1800424dd  mov     rcx, rbx
0x1800424e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800424e5  nop
0x1800424e6  lea     rcx, [rsp+68h+var_38]
0x1800424eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800424f0  mov     rax, rbx
0x1800424f3  mov     rcx, [rsp+68h+var_18]
0x1800424f8  xor     rcx, rsp; StackCookie
0x1800424fb  call    __security_check_cookie
0x180042500  mov     rbx, [rsp+68h+arg_10]
0x180042508  add     rsp, 60h
0x18004250c  pop     rdi
0x18004250d  retn
```
