# Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(ulong)

- ea: `0x1800422d0`
- end: `0x18004240a`
- name: `?GetPackageFamilyNameFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180064304`
- `0x18007a804`
- `0x18007af9c`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18002576c`
- `0x1800257ec`
- `0x180029408`
- `0x1800299c4`
- `0x180039e9c`
- `0x18003cf4c`
- `0x18003f2d8`
- `0x18003f4a0`
- `0x1800422d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042301`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042301`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x180042340`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800423a6`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x180042340`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800423a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(
        __int64 a1,
        DWORD a2)
{
  HANDLE v3; // rbx
  const char *v4; // r9
  unsigned int PackageFamilyName; // eax
  WCHAR *v6; // rax
  unsigned int v7; // eax
  UINT32 packageFamilyNameLength; // [rsp+20h] [rbp-40h] BYREF
  HANDLE v10[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v3 = OpenProcess(0x1000u, 0, a2);
  v10[0] = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v4);
  packageFamilyNameLength = 0;
  PackageFamilyName = GetPackageFamilyName(v3, &packageFamilyNameLength, 0);
  if ( PackageFamilyName == 15700 )
  {
    std::wstring::wstring(a1);
  }
  else
  {
    if ( PackageFamilyName != 122 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)PackageFamilyName,
        packageFamilyNameLength);
    std::wstring::wstring(v11, packageFamilyNameLength);
    std::wstring::resize(v11, packageFamilyNameLength - 1);
    v6 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
    v7 = GetPackageFamilyName(v3, &packageFamilyNameLength, v6);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v7,
        packageFamilyNameLength);
    std::wstring::wstring(a1, v11);
    std::wstring::_Tidy_deallocate(v11);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v10);
  return a1;
}

```

## disassembly

```asm
0x1800422d0  mov     [rsp-8+arg_10], rbx
0x1800422d5  mov     [rsp-8+arg_18], rdi
0x1800422da  push    rbp
0x1800422db  mov     rbp, rsp
0x1800422de  sub     rsp, 60h
0x1800422e2  mov     rax, cs:__security_cookie
0x1800422e9  xor     rax, rsp
0x1800422ec  mov     [rbp+var_8], rax
0x1800422f0  mov     rdi, rcx
0x1800422f3  mov     [rbp+var_38], rcx
0x1800422f7  mov     r8d, edx; dwProcessId
0x1800422fa  xor     edx, edx; bInheritHandle
0x1800422fc  mov     ecx, 1000h; dwDesiredAccess
0x180042301  call    cs:__imp_OpenProcess
0x180042307  mov     rbx, rax
0x18004230a  mov     [rbp+var_38], rax
0x18004230e  inc     rax
0x180042311  test    rax, 0FFFFFFFFFFFFFFFEh
0x180042317  jnz     short loc_18004232F
0x180042319  mov     rcx, [rbp+8]; this
0x18004231d  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042324  mov     edx, 1D6h; void *
0x180042329  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004232f  mov     [rbp+packageFamilyNameLength], 0
0x180042336  xor     r8d, r8d; packageFamilyName
0x180042339  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x18004233d  mov     rcx, rbx; hProcess
0x180042340  call    cs:__imp_GetPackageFamilyName
0x180042346  cmp     eax, 3D54h
0x18004234b  jnz     short loc_18004235A
0x18004234d  mov     rcx, rdi
0x180042350  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180042355  jmp     loc_1800423E0
0x18004235a  cmp     eax, 7Ah ; 'z'
0x18004235d  jz      short loc_180042378
0x18004235f  mov     rcx, [rbp+8]; this
0x180042363  mov     r9d, eax; char *
0x180042366  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004236d  mov     edx, 1E6h; void *
0x180042372  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180042378  mov     edx, [rbp+packageFamilyNameLength]
0x18004237b  lea     rcx, [rbp+var_28]
0x18004237f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180042384  nop
0x180042385  mov     edx, [rbp+packageFamilyNameLength]
0x180042388  dec     edx
0x18004238a  lea     rcx, [rbp+var_28]
0x18004238e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180042393  lea     rcx, [rbp+var_28]
0x180042397  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004239c  mov     r8, rax; packageFamilyName
0x18004239f  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x1800423a3  mov     rcx, rbx; hProcess
0x1800423a6  call    cs:__imp_GetPackageFamilyName
0x1800423ac  mov     rcx, [rbp+8]; this
0x1800423b0  test    eax, eax
0x1800423b2  jz      short loc_1800423C9
0x1800423b4  mov     r9d, eax; char *
0x1800423b7  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800423be  mov     edx, 1F1h; void *
0x1800423c3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800423c9  lea     rdx, [rbp+var_28]
0x1800423cd  mov     rcx, rdi
0x1800423d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800423d5  nop
0x1800423d6  lea     rcx, [rbp+var_28]
0x1800423da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800423df  nop
0x1800423e0  lea     rcx, [rbp+var_38]
0x1800423e4  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800423e9  mov     rax, rdi
0x1800423ec  mov     rcx, [rbp+var_8]
0x1800423f0  xor     rcx, rsp; StackCookie
0x1800423f3  call    __security_check_cookie
0x1800423f8  lea     r11, [rsp+60h+var_s0]
0x1800423fd  mov     rbx, [r11+20h]
0x180042401  mov     rdi, [r11+28h]
0x180042405  mov     rsp, r11
0x180042408  pop     rbp
0x180042409  retn
```
