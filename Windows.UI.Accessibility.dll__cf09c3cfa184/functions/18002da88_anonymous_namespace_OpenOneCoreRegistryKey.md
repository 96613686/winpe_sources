# _anonymous_namespace_::OpenOneCoreRegistryKey

- ea: `0x18002da88`
- end: `0x18002dafc`
- name: `_anonymous_namespace_::OpenOneCoreRegistryKey`
- size: `116`
- prototype: `__int64 __fastcall(PHKEY phkResult, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002d6d8`

## callees

- `0x18002c4f4`
- `0x18002da88`
- `0x18002dbd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dad2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dad2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHKEY __fastcall anonymous_namespace_::OpenOneCoreRegistryKey(PHKEY phkResult, LPCWSTR lpSubKey)
{
  unsigned int v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  v4 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20006u, phkResult);
  if ( (v4 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(retaddr, v5, v6, (const char *)v4, phkResulta);
  return phkResult;
}

```

## disassembly

```asm
0x18002da88  mov     rax, rsp
0x18002da8b  mov     [rax+10h], rbx
0x18002da8f  mov     [rax+8], rcx
0x18002da93  push    rdi
0x18002da94  sub     rsp, 40h
0x18002da98  mov     rbx, rdx
0x18002da9b  mov     rdi, rcx
0x18002da9e  mov     dword ptr [rax-18h], 0
0x18002daa5  mov     qword ptr [rcx], 0
0x18002daac  mov     dword ptr [rax-18h], 1
0x18002dab3  xor     edx, edx
0x18002dab5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002daba  mov     qword ptr [rsp+48h+phkResult], rdi; unsigned int
0x18002dabf  mov     r9d, 20006h; samDesired
0x18002dac5  xor     r8d, r8d; ulOptions
0x18002dac8  mov     rdx, rbx; lpSubKey
0x18002dacb  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002dad2  call    cs:__imp_RegOpenKeyExW
0x18002dad8  test    eax, 0FFFFFFFDh
0x18002dadd  jz      short loc_18002DAED
0x18002dadf  mov     rcx, [rsp+48h]; this
0x18002dae4  mov     r9d, eax; char *
0x18002dae7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002daed  mov     rax, rdi
0x18002daf0  mov     rbx, [rsp+48h+arg_8]
0x18002daf5  add     rsp, 40h
0x18002daf9  pop     rdi
0x18002dafa  retn
```
