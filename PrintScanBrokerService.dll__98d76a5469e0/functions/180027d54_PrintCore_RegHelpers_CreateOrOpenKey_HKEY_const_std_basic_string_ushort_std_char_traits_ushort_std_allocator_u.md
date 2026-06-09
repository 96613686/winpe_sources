# PrintCore::RegHelpers::CreateOrOpenKey(HKEY__ * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180027d54`
- end: `0x180027e05`
- name: `?CreateOrOpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800296a0`

## callees

- `0x180027060`
- `0x180027d54`
- `0x18002f1d4`
- `0x18002faf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027dbb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027dbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY __fastcall PrintCore::RegHelpers::CreateOrOpenKey(HKEY *a1, const WCHAR *a2)
{
  unsigned int v4; // eax
  HKEY v5; // rbx
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF

  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v4 = RegCreateKeyExW(*a1, a2, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x15,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\RegHelpers.h",
      (const char *)v4,
      dwOptions);
  v5 = phkResult;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v5;
}

```

## disassembly

```asm
0x180027d54  mov     [rsp+arg_8], rbx
0x180027d59  push    rdi
0x180027d5a  sub     rsp, 50h
0x180027d5e  mov     rbx, rdx
0x180027d61  mov     rdi, rcx
0x180027d64  mov     [rsp+58h+arg_0], 0
0x180027d6d  xor     edx, edx
0x180027d6f  lea     rcx, [rsp+58h+arg_0]
0x180027d74  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180027d79  cmp     qword ptr [rbx+18h], 7
0x180027d7e  jbe     short loc_180027D83
0x180027d80  mov     rbx, [rbx]
0x180027d83  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180027d8c  lea     rax, [rsp+58h+arg_0]
0x180027d91  mov     [rsp+58h+phkResult], rax; phkResult
0x180027d96  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180027d9f  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180027da7  mov     [rsp+58h+dwOptions], 0; unsigned int
0x180027daf  xor     r9d, r9d; lpClass
0x180027db2  xor     r8d, r8d; Reserved
0x180027db5  mov     rdx, rbx; lpSubKey
0x180027db8  mov     rcx, [rdi]; hKey
0x180027dbb  call    cs:__imp_RegCreateKeyExW
0x180027dc1  mov     rcx, [rsp+58h]; this
0x180027dc6  test    eax, eax
0x180027dc8  jnz     short loc_180027DF0
0x180027dca  mov     rbx, [rsp+58h+arg_0]
0x180027dcf  mov     [rsp+58h+arg_0], 0
0x180027dd8  lea     rcx, [rsp+58h+arg_0]
0x180027ddd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027de2  mov     rax, rbx
0x180027de5  mov     rbx, [rsp+58h+arg_8]
0x180027dea  add     rsp, 50h
0x180027dee  pop     rdi
0x180027def  retn
0x180027df0  mov     r9d, eax; char *
0x180027df3  lea     r8, aOnecoreuapInte_3; "OneCoreUap\\Internal\\Printscan\\inc\\R"...
0x180027dfa  mov     edx, 15h; void *
0x180027dff  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
