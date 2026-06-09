# WindowsStorage::Utilities::registry_create_key(HKEY__ *,ushort const *,ulong)

- ea: `0x180010dc8`
- end: `0x180010e6e`
- name: `?registry_create_key@Utilities@WindowsStorage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBGK@Z`
- size: `166`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ca78`

## callees

- `0x1800106d4`
- `0x180010dc8`
- `0x180011344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010e34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010e34`

## string_xrefs

- `0x180010e46`: `onecore\base\windows.storage\src\Registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHKEY __fastcall WindowsStorage::Utilities::registry_create_key(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x20019u, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
      (const char *)Key,
      dwOptions);
  return phkResult;
}

```

## disassembly

```asm
0x180010dc8  mov     rax, rsp
0x180010dcb  mov     [rax+10h], rbx
0x180010dcf  mov     [rax+18h], rsi
0x180010dd3  mov     [rax+8], rcx
0x180010dd7  push    rdi
0x180010dd8  sub     rsp, 60h
0x180010ddc  mov     rbx, r8
0x180010ddf  mov     rdi, rdx
0x180010de2  mov     rsi, rcx
0x180010de5  mov     dword ptr [rax-18h], 0
0x180010dec  mov     qword ptr [rcx], 0
0x180010df3  mov     dword ptr [rax-18h], 1
0x180010dfa  xor     edx, edx
0x180010dfc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010e01  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180010e0a  mov     [rsp+68h+phkResult], rsi; phkResult
0x180010e0f  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010e18  mov     [rsp+68h+samDesired], 20019h; samDesired
0x180010e20  mov     [rsp+68h+dwOptions], 0; unsigned int
0x180010e28  xor     r9d, r9d; lpClass
0x180010e2b  xor     r8d, r8d; Reserved
0x180010e2e  mov     rdx, rbx; lpSubKey
0x180010e31  mov     rcx, rdi; hKey
0x180010e34  call    cs:__imp_RegCreateKeyExW
0x180010e3a  test    eax, eax
0x180010e3c  jz      short loc_180010E58
0x180010e3e  mov     rcx, [rsp+68h]; this
0x180010e43  mov     r9d, eax; char *
0x180010e46  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x180010e4d  mov     edx, 5Ah ; 'Z'; void *
0x180010e52  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180010e58  mov     rax, rsi
0x180010e5b  lea     r11, [rsp+68h+var_8]
0x180010e60  mov     rbx, [r11+18h]
0x180010e64  mov     rsi, [r11+20h]
0x180010e68  mov     rsp, r11
0x180010e6b  pop     rdi
0x180010e6c  retn
```
