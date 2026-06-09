# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)

- ea: `0x18002825c`
- end: `0x180028379`
- name: `?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z`
- size: `285`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180027808`

## callees

- `0x18002154c`
- `0x180024a10`
- `0x180026810`
- `0x18002825c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800282d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800282d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800282fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800282fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002834d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002834d`
- `ADVAPI32!RegDeleteTreeW` at `0x180028362`
- `ADVAPI32!RegDeleteTreeW` at `0x180028362`

## string_xrefs

- `0x18002833f`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1800282c4`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(int a1)
{
  int Data; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  Data = a1;
  if ( ColorFiltering::ColorFilterHelper::IsActive() )
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
      RegSetValueExW(hKey, L"Intensity", 0, 4u, (const BYTE *)&Data, 4u);
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
0x18002825c  push    rbp
0x18002825e  mov     rbp, rsp
0x180028261  sub     rsp, 50h
0x180028265  mov     [rbp+Data], ecx
0x180028268  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x18002826d  test    al, al
0x18002826f  jz      loc_18002830F
0x180028275  mov     [rbp+hKey], 0
0x18002827d  mov     rcx, [rbp+hKey]; hKey
0x180028281  test    rcx, rcx
0x180028284  jz      short loc_18002828B
0x180028286  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x18002828b  mov     [rbp+hKey], 0
0x180028293  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x18002829c  lea     rax, [rbp+hKey]
0x1800282a0  mov     [rsp+50h+phkResult], rax; phkResult
0x1800282a5  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800282ae  mov     [rsp+50h+samDesired], 3; samDesired
0x1800282b6  mov     [rsp+50h+dwOptions], 1; dwOptions
0x1800282be  xor     r9d, r9d; lpClass
0x1800282c1  xor     r8d, r8d; Reserved
0x1800282c4  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800282cb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800282d2  call    cs:__imp_RegCreateKeyExW
0x1800282d8  test    eax, eax
0x1800282da  jnz     short loc_180028303
0x1800282dc  lea     r9d, [rax+4]; dwType
0x1800282e0  mov     [rsp+50h+samDesired], r9d; cbData
0x1800282e5  lea     rax, [rbp+Data]
0x1800282e9  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800282ee  xor     r8d, r8d; Reserved
0x1800282f1  lea     rdx, aIntensity; "Intensity"
0x1800282f8  mov     rcx, [rbp+hKey]; hKey
0x1800282fc  call    cs:__imp_RegSetValueExW
0x180028302  nop
0x180028303  lea     rcx, [rbp+hKey]
0x180028307  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002830c  nop
0x18002830d  jmp     short loc_180028373
0x18002830f  mov     [rbp+hKey], 0
0x180028317  mov     rcx, [rbp+hKey]; hKey
0x18002831b  test    rcx, rcx
0x18002831e  jz      short loc_180028325
0x180028320  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x180028325  mov     [rbp+hKey], 0
0x18002832d  lea     rax, [rbp+hKey]
0x180028331  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x180028336  mov     r9d, 0F003Fh; samDesired
0x18002833c  xor     r8d, r8d; ulOptions
0x18002833f  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x180028346  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002834d  call    cs:__imp_RegOpenKeyExW
0x180028353  test    eax, eax
0x180028355  jnz     short loc_180028369
0x180028357  lea     rdx, aColorfiltering_0; "colorfiltering"
0x18002835e  mov     rcx, [rbp+hKey]; hKey
0x180028362  call    cs:__imp_RegDeleteTreeW
0x180028368  nop
0x180028369  lea     rcx, [rbp+hKey]
0x18002836d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028372  nop
0x180028373  add     rsp, 50h
0x180028377  pop     rbp
0x180028378  retn
```
