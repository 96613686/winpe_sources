# PrintCore::RegHelpers::CreateOrOpenKey(HKEY__ * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x1800132e8`
- end: `0x180013398`
- name: `?CreateOrOpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `176`
- prototype: `HKEY __fastcall(HKEY *, __int64, REGSAM)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001a404`

## callees

- `0x180007468`
- `0x18000e164`
- `0x18000e1ac`
- `0x18000e790`
- `0x1800132e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013350`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013350`

## pseudocode

```c
HKEY __fastcall PrintCore::RegHelpers::CreateOrOpenKey(HKEY *a1, __int64 a2, REGSAM a3)
{
  const WCHAR *v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  HKEY v9; // rbx
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY phkResult; // [rsp+60h] [rbp+8h] BYREF

  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v7 = RegCreateKeyExW(*a1, v6, 0, 0, 0, a3, 0, &phkResult, 0);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x15, v8, (const char *)v7, dwOptions);
  v9 = phkResult;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v9;
}

```

## disassembly

```asm
0x1800132e8  mov     rax, rsp
0x1800132eb  mov     [rax+10h], rbx
0x1800132ef  mov     [rax+18h], rsi
0x1800132f3  push    rdi
0x1800132f4  sub     rsp, 50h
0x1800132f8  mov     edi, r8d
0x1800132fb  mov     rbx, rdx
0x1800132fe  mov     rsi, rcx
0x180013301  mov     qword ptr [rax+8], 0
0x180013309  xor     edx, edx
0x18001330b  lea     rcx, [rax+8]
0x18001330f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013314  mov     rcx, rbx
0x180013317  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001331c  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180013325  lea     rcx, [rsp+58h+arg_0]
0x18001332a  mov     [rsp+58h+phkResult], rcx; phkResult
0x18001332f  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180013338  mov     [rsp+58h+samDesired], edi; samDesired
0x18001333c  mov     [rsp+58h+dwOptions], 0; unsigned int
0x180013344  xor     r9d, r9d; lpClass
0x180013347  xor     r8d, r8d; Reserved
0x18001334a  mov     rdx, rax; lpSubKey
0x18001334d  mov     rcx, [rsi]; hKey
0x180013350  call    cs:__imp_RegCreateKeyExW
0x180013356  mov     rcx, [rsp+58h]; this
0x18001335b  test    eax, eax
0x18001335d  jz      short loc_18001336D
0x18001335f  mov     r9d, eax; char *
0x180013362  mov     edx, 15h; void *
0x180013367  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001336d  mov     rbx, [rsp+58h+arg_0]
0x180013372  mov     [rsp+58h+arg_0], 0
0x18001337b  lea     rcx, [rsp+58h+arg_0]
0x180013380  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013385  mov     rax, rbx
0x180013388  mov     rbx, [rsp+58h+arg_8]
0x18001338d  mov     rsi, [rsp+58h+arg_10]
0x180013392  add     rsp, 50h
0x180013396  pop     rdi
0x180013397  retn
```
