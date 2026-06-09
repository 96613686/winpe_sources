# GetRegKeyForPackageAndHost(HSTRING__ *,HSTRING__ *)

- ea: `0x14000ced4`
- end: `0x14000cf86`
- name: `?GetRegKeyForPackageAndHost@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@0@Z`
- size: `178`
- prototype: `PHKEY __fastcall(PHKEY phkResult, HSTRING, HSTRING)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000eb7c`
- `0x14000ed9c`

## callees

- `0x14000a13c`
- `0x14000ced4`
- `0x14000cf8c`
- `0x14000fc20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000cf0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000cf0f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000cf4d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000cf4d`

## pseudocode

```c
PHKEY __fastcall GetRegKeyForPackageAndHost(PHKEY phkResult, HSTRING a2, HSTRING a3)
{
  const WCHAR *StringRawBuffer; // rax
  unsigned int Key; // eax
  unsigned int v7; // r8d
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  GetSystemApplicationDataKeyForPackage(&hKey, a2);
  *phkResult = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  Key = RegCreateKeyExW(hKey, StringRawBuffer, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x2B4, v7, (const char *)Key, dwOptions);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return phkResult;
}

```

## disassembly

```asm
0x14000ced4  mov     rax, rsp
0x14000ced7  mov     [rax+10h], rbx
0x14000cedb  mov     [rax+8], rcx
0x14000cedf  push    rdi
0x14000cee0  sub     rsp, 60h
0x14000cee4  mov     rbx, r8
0x14000cee7  mov     rdi, rcx
0x14000ceea  mov     dword ptr [rax-18h], 0
0x14000cef1  lea     rcx, [rax+20h]; phkResult
0x14000cef5  call    ?GetSystemApplicationDataKeyForPackage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHSTRING__@@@Z; GetSystemApplicationDataKeyForPackage(HSTRING__ *)
0x14000cefa  nop
0x14000cefb  mov     qword ptr [rdi], 0
0x14000cf02  mov     [rsp+68h+var_18], 1
0x14000cf0a  xor     edx, edx; length
0x14000cf0c  mov     rcx, rbx; string
0x14000cf0f  call    cs:__imp_WindowsGetStringRawBuffer
0x14000cf15  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x14000cf1e  mov     [rsp+68h+phkResult], rdi; phkResult
0x14000cf23  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14000cf2c  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x14000cf34  mov     [rsp+68h+dwOptions], 0; unsigned int
0x14000cf3c  xor     r9d, r9d; lpClass
0x14000cf3f  xor     r8d, r8d; Reserved
0x14000cf42  mov     rdx, rax; lpSubKey
0x14000cf45  mov     rcx, [rsp+68h+hKey]; hKey
0x14000cf4d  call    cs:__imp_RegCreateKeyExW
0x14000cf53  mov     rcx, [rsp+68h]; this
0x14000cf58  test    eax, eax
0x14000cf5a  jz      short loc_14000CF6A
0x14000cf5c  mov     r9d, eax; char *
0x14000cf5f  mov     edx, 2B4h; void *
0x14000cf64  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x14000cf6a  lea     rcx, [rsp+68h+hKey]
0x14000cf72  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000cf77  mov     rax, rdi
0x14000cf7a  mov     rbx, [rsp+68h+arg_8]
0x14000cf7f  add     rsp, 60h
0x14000cf83  pop     rdi
0x14000cf84  retn
```
