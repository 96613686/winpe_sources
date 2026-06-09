# Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(ulong)

- ea: `0x180022460`
- end: `0x18002259a`
- name: `?GetPackageFamilyNameFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024440`

## callees

- `0x180003c80`
- `0x18000f9e4`
- `0x180013b8c`
- `0x1800142d4`
- `0x18001b444`
- `0x1800212c8`
- `0x180021348`
- `0x180022460`
- `0x180023690`
- `0x1800236ac`
- `0x180023bc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022491`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022491`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800224d0`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x180022536`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800224d0`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x180022536`

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
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  WCHAR *v9; // rax
  unsigned int v10; // eax
  UINT32 packageFamilyNameLength; // [rsp+20h] [rbp-40h] BYREF
  HANDLE v13[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v14[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v3 = OpenProcess(0x1000u, 0, a2);
  v13[0] = v3;
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
    std::wstring::wstring(v14, packageFamilyNameLength);
    std::wstring::resize(v14, packageFamilyNameLength - 1);
    v9 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14, v6, v7, v8);
    v10 = GetPackageFamilyName(v3, &packageFamilyNameLength, v9);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v10,
        packageFamilyNameLength);
    std::wstring::wstring(a1, v14);
    std::wstring::_Tidy_deallocate(v14);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v13);
  return a1;
}

```

## disassembly

```asm
0x180022460  mov     [rsp-8+arg_10], rbx
0x180022465  mov     [rsp-8+arg_18], rdi
0x18002246a  push    rbp
0x18002246b  mov     rbp, rsp
0x18002246e  sub     rsp, 60h
0x180022472  mov     rax, cs:__security_cookie
0x180022479  xor     rax, rsp
0x18002247c  mov     [rbp+var_8], rax
0x180022480  mov     rdi, rcx
0x180022483  mov     [rbp+var_38], rcx
0x180022487  mov     r8d, edx; dwProcessId
0x18002248a  xor     edx, edx; bInheritHandle
0x18002248c  mov     ecx, 1000h; dwDesiredAccess
0x180022491  call    cs:__imp_OpenProcess
0x180022497  mov     rbx, rax
0x18002249a  mov     [rbp+var_38], rax
0x18002249e  inc     rax
0x1800224a1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800224a7  jnz     short loc_1800224BF
0x1800224a9  mov     rcx, [rbp+8]; this
0x1800224ad  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800224b4  mov     edx, 1D6h; void *
0x1800224b9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800224bf  mov     [rbp+packageFamilyNameLength], 0
0x1800224c6  xor     r8d, r8d; packageFamilyName
0x1800224c9  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x1800224cd  mov     rcx, rbx; hProcess
0x1800224d0  call    cs:__imp_GetPackageFamilyName
0x1800224d6  cmp     eax, 3D54h
0x1800224db  jnz     short loc_1800224EA
0x1800224dd  mov     rcx, rdi
0x1800224e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800224e5  jmp     loc_180022570
0x1800224ea  cmp     eax, 7Ah ; 'z'
0x1800224ed  jz      short loc_180022508
0x1800224ef  mov     rcx, [rbp+8]; this
0x1800224f3  mov     r9d, eax; char *
0x1800224f6  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800224fd  mov     edx, 1E6h; void *
0x180022502  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180022508  mov     edx, [rbp+packageFamilyNameLength]
0x18002250b  lea     rcx, [rbp+var_28]
0x18002250f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180022514  nop
0x180022515  mov     edx, [rbp+packageFamilyNameLength]
0x180022518  dec     edx
0x18002251a  lea     rcx, [rbp+var_28]
0x18002251e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180022523  lea     rcx, [rbp+var_28]
0x180022527  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002252c  mov     r8, rax; packageFamilyName
0x18002252f  lea     rdx, [rbp+packageFamilyNameLength]; packageFamilyNameLength
0x180022533  mov     rcx, rbx; hProcess
0x180022536  call    cs:__imp_GetPackageFamilyName
0x18002253c  mov     rcx, [rbp+8]; this
0x180022540  test    eax, eax
0x180022542  jz      short loc_180022559
0x180022544  mov     r9d, eax; char *
0x180022547  lea     r8, aOnecoreBaseDev_8; "onecore\\base\\devices\\cam\\core\\clie"...
0x18002254e  mov     edx, 1F1h; void *
0x180022553  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180022559  lea     rdx, [rbp+var_28]
0x18002255d  mov     rcx, rdi
0x180022560  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180022565  nop
0x180022566  lea     rcx, [rbp+var_28]
0x18002256a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002256f  nop
0x180022570  lea     rcx, [rbp+var_38]
0x180022574  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180022579  mov     rax, rdi
0x18002257c  mov     rcx, [rbp+var_8]
0x180022580  xor     rcx, rsp; StackCookie
0x180022583  call    __security_check_cookie
0x180022588  lea     r11, [rsp+60h+var_s0]
0x18002258d  mov     rbx, [r11+20h]
0x180022591  mov     rdi, [r11+28h]
0x180022595  mov     rsp, r11
0x180022598  pop     rbp
0x180022599  retn
```
