# CoreShellUtils::OpenComposerClassRegistrationBaseKeyWithoutChecks(void)

- ea: `0x1800774f8`
- end: `0x18007757b`
- name: `?OpenComposerClassRegistrationBaseKeyWithoutChecks@CoreShellUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800756a0`
- `0x180075a9c`
- `0x1800763c4`

## callees

- `0x18001475c`
- `0x180017b88`
- `0x1800774f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007756c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007756c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007751b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007751b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007753e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007753e`

## pseudocode

```c
HKEY *__fastcall CoreShellUtils::OpenComposerClassRegistrationBaseKeyWithoutChecks(HKEY *a1)
{
  const WCHAR *StringRawBuffer; // rax
  HKEY v3; // rax
  HKEY phkResult; // [rsp+58h] [rbp+10h] BYREF
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  CoreShellUtils::GetComposerRegistryRootPathWithoutChecks(&string);
  phkResult = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, StringRawBuffer, 0, 0xF003Fu, &phkResult) )
  {
    v3 = 0;
  }
  else
  {
    v3 = phkResult;
    phkResult = 0;
  }
  *a1 = v3;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x1800774f8  push    rbx
0x1800774fa  sub     rsp, 40h
0x1800774fe  mov     rbx, rcx
0x180077501  lea     rcx, [rsp+48h+string]
0x180077506  call    ?GetComposerRegistryRootPathWithoutChecks@CoreShellUtils@@YA?AVHString@Wrappers@WRL@Microsoft@@XZ; CoreShellUtils::GetComposerRegistryRootPathWithoutChecks(void)
0x18007750b  mov     rcx, [rsp+48h+string]; string
0x180077510  xor     edx, edx; length
0x180077512  mov     [rsp+48h+arg_8], 0
0x18007751b  call    cs:__imp_WindowsGetStringRawBuffer
0x180077521  lea     rcx, [rsp+48h+arg_8]
0x180077526  mov     r9d, 0F003Fh; samDesired
0x18007752c  mov     [rsp+48h+phkResult], rcx; phkResult
0x180077531  xor     r8d, r8d; ulOptions
0x180077534  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007753b  mov     rdx, rax; lpSubKey
0x18007753e  call    cs:__imp_RegOpenKeyExW
0x180077544  lea     rcx, [rsp+48h+arg_8]
0x180077549  test    eax, eax
0x18007754b  jz      short loc_180077551
0x18007754d  xor     eax, eax
0x18007754f  jmp     short loc_18007755F
0x180077551  mov     rax, [rsp+48h+arg_8]
0x180077556  mov     [rsp+48h+arg_8], 0
0x18007755f  mov     [rbx], rax
0x180077562  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180077567  mov     rcx, [rsp+48h+string]; string
0x18007756c  call    cs:__imp_WindowsDeleteString
0x180077572  mov     rax, rbx
0x180077575  add     rsp, 40h
0x180077579  pop     rbx
0x18007757a  retn
```
