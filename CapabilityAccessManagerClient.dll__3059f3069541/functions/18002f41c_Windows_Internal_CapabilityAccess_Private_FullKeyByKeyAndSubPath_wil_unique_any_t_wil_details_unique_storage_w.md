# Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18002f41c`
- end: `0x18002f4c2`
- name: `?FullKeyByKeyAndSubPath@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV56@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `166`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002a438`

## callees

- `0x18001b444`
- `0x1800236ac`
- `0x180023b38`
- `0x18002f41c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f48d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f48d`

## string_xrefs

- `0x18002f4a2`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHKEY __fastcall Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(
        PHKEY phkResult,
        HKEY *a2,
        __int64 a3,
        int a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  const WCHAR *v11; // rax
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v8, v9, v10);
  Key = RegCreateKeyExW(*a2, v11, 0, 0, 0, a4 | 0x100, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
      (const char *)Key,
      dwOptions);
  return phkResult;
}

```

## disassembly

```asm
0x18002f41c  mov     [rsp+arg_0], rcx
0x18002f421  push    rbx
0x18002f422  push    rsi
0x18002f423  push    rdi
0x18002f424  push    r14
0x18002f426  sub     rsp, 68h
0x18002f42a  mov     edi, r9d
0x18002f42d  mov     rbx, r8
0x18002f430  mov     rsi, rdx
0x18002f433  mov     r14, rcx
0x18002f436  mov     [rsp+88h+var_38], 0
0x18002f43e  xor     eax, eax
0x18002f440  mov     [rcx], rax
0x18002f443  mov     [rsp+88h+var_38], 1
0x18002f44b  xor     edx, edx
0x18002f44d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002f452  mov     rcx, rbx
0x18002f455  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f45a  bts     edi, 8
0x18002f45e  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x18002f467  mov     [rsp+88h+phkResult], r14; phkResult
0x18002f46c  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002f475  mov     [rsp+88h+samDesired], edi; samDesired
0x18002f479  mov     [rsp+88h+dwOptions], 0; unsigned int
0x18002f481  xor     r9d, r9d; lpClass
0x18002f484  xor     r8d, r8d; Reserved
0x18002f487  mov     rdx, rax; lpSubKey
0x18002f48a  mov     rcx, [rsi]; hKey
0x18002f48d  call    cs:__imp_RegCreateKeyExW
0x18002f493  test    eax, eax
0x18002f495  jz      short loc_18002F4B4
0x18002f497  mov     rcx, [rsp+88h]; this
0x18002f49f  mov     r9d, eax; char *
0x18002f4a2  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f4a9  mov     edx, 18h; void *
0x18002f4ae  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f4b4  mov     rax, r14
0x18002f4b7  add     rsp, 68h
0x18002f4bb  pop     r14
0x18002f4bd  pop     rdi
0x18002f4be  pop     rsi
0x18002f4bf  pop     rbx
0x18002f4c0  retn
```
