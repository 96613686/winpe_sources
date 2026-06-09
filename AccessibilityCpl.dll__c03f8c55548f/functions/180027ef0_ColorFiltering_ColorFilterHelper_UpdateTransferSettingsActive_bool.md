# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)

- ea: `0x180027ef0`
- end: `0x18002800b`
- name: `?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z`
- size: `283`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180026810`

## callees

- `0x18002154c`
- `0x180024a10`
- `0x180027ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027f64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027f64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027f8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027f8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027fdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027fdf`
- `ADVAPI32!RegDeleteTreeW` at `0x180027ff4`
- `ADVAPI32!RegDeleteTreeW` at `0x180027ff4`

## string_xrefs

- `0x180027fd1`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x180027f56`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(unsigned __int8 a1)
{
  int Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  Data = a1;
  if ( a1 )
  {
    hKey = 0;
    if ( !RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\colorfiltering",
            0,
            0,
            1u,
            3u,
            0,
            &hKey,
            0) )
      RegSetValueExW(hKey, L"Active", 0, 4u, (const BYTE *)&Data, 4u);
  }
  else
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\",
            0,
            0xF003Fu,
            &hKey) )
      RegDeleteTreeW(hKey, L"colorfiltering");
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180027ef0  push    rbp
0x180027ef2  mov     rbp, rsp
0x180027ef5  sub     rsp, 50h
0x180027ef9  movzx   eax, cl
0x180027efc  mov     [rbp+Data], eax
0x180027eff  test    cl, cl
0x180027f01  jz      loc_180027FA1
0x180027f07  mov     [rbp+hKey], 0
0x180027f0f  mov     rcx, [rbp+hKey]; hKey
0x180027f13  test    rcx, rcx
0x180027f16  jz      short loc_180027F1D
0x180027f18  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x180027f1d  mov     [rbp+hKey], 0
0x180027f25  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180027f2e  lea     rax, [rbp+hKey]
0x180027f32  mov     [rsp+50h+phkResult], rax; phkResult
0x180027f37  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180027f40  mov     [rsp+50h+samDesired], 3; samDesired
0x180027f48  mov     [rsp+50h+dwOptions], 1; dwOptions
0x180027f50  xor     r9d, r9d; lpClass
0x180027f53  xor     r8d, r8d; Reserved
0x180027f56  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x180027f5d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180027f64  call    cs:__imp_RegCreateKeyExW
0x180027f6a  test    eax, eax
0x180027f6c  jnz     short loc_180027F95
0x180027f6e  lea     r9d, [rax+4]; dwType
0x180027f72  mov     [rsp+50h+samDesired], r9d; cbData
0x180027f77  lea     rax, [rbp+Data]
0x180027f7b  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180027f80  xor     r8d, r8d; Reserved
0x180027f83  lea     rdx, aActive; "Active"
0x180027f8a  mov     rcx, [rbp+hKey]; hKey
0x180027f8e  call    cs:__imp_RegSetValueExW
0x180027f94  nop
0x180027f95  lea     rcx, [rbp+hKey]
0x180027f99  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027f9e  nop
0x180027f9f  jmp     short loc_180028005
0x180027fa1  mov     [rbp+hKey], 0
0x180027fa9  mov     rcx, [rbp+hKey]; hKey
0x180027fad  test    rcx, rcx
0x180027fb0  jz      short loc_180027FB7
0x180027fb2  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x180027fb7  mov     [rbp+hKey], 0
0x180027fbf  lea     rax, [rbp+hKey]
0x180027fc3  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x180027fc8  mov     r9d, 0F003Fh; samDesired
0x180027fce  xor     r8d, r8d; ulOptions
0x180027fd1  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x180027fd8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180027fdf  call    cs:__imp_RegOpenKeyExW
0x180027fe5  test    eax, eax
0x180027fe7  jnz     short loc_180027FFB
0x180027fe9  lea     rdx, aColorfiltering_0; "colorfiltering"
0x180027ff0  mov     rcx, [rbp+hKey]; hKey
0x180027ff4  call    cs:__imp_RegDeleteTreeW
0x180027ffa  nop
0x180027ffb  lea     rcx, [rbp+hKey]
0x180027fff  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028004  nop
0x180028005  add     rsp, 50h
0x180028009  pop     rbp
0x18002800a  retn
```
