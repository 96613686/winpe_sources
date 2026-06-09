# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)

- ea: `0x140014de8`
- end: `0x140014f0f`
- name: `?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z`
- size: `295`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400143ac`

## callees

- `0x140011000`
- `0x140011018`
- `0x1400133cc`
- `0x140014de8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140014ede`
- `ADVAPI32!RegOpenKeyExW` at `0x140014ede`
- `KERNEL32!RegDeleteTreeW` at `0x140014ef3`
- `KERNEL32!RegDeleteTreeW` at `0x140014ef3`
- `KERNEL32!RegCreateKeyExW` at `0x140014e5e`
- `KERNEL32!RegCreateKeyExW` at `0x140014e5e`
- `KERNEL32!RegSetValueExW` at `0x140014e88`
- `KERNEL32!RegSetValueExW` at `0x140014e88`

## string_xrefs

- `0x140014ed0`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x140014e50`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(int a1)
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
      RegSetValueExW(hKey, L"FilterType", 0, 4u, (const BYTE *)&Data, 4u);
    if ( hKey )
      wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ *>::close();
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
    if ( hKey )
      wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),HKEY__ *>::close();
  }
}

```

## disassembly

```asm
0x140014de8  push    rbp
0x140014dea  mov     rbp, rsp
0x140014ded  sub     rsp, 50h
0x140014df1  mov     [rbp+Data], ecx
0x140014df4  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x140014df9  test    al, al
0x140014dfb  jz      loc_140014EA0
0x140014e01  mov     [rbp+hKey], 0
0x140014e09  mov     rcx, [rbp+hKey]; hKey
0x140014e0d  test    rcx, rcx
0x140014e10  jz      short loc_140014E17
0x140014e12  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140014e17  mov     [rbp+hKey], 0
0x140014e1f  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x140014e28  lea     rax, [rbp+hKey]
0x140014e2c  mov     [rsp+50h+phkResult], rax; phkResult
0x140014e31  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140014e3a  mov     [rsp+50h+samDesired], 3; samDesired
0x140014e42  mov     [rsp+50h+dwOptions], 1; dwOptions
0x140014e4a  xor     r9d, r9d; lpClass
0x140014e4d  xor     r8d, r8d; Reserved
0x140014e50  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x140014e57  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014e5e  call    cs:__imp_RegCreateKeyExW
0x140014e64  test    eax, eax
0x140014e66  jnz     short loc_140014E8F
0x140014e68  lea     r9d, [rax+4]; dwType
0x140014e6c  mov     [rsp+50h+samDesired], r9d; cbData
0x140014e71  lea     rax, [rbp+Data]
0x140014e75  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140014e7a  xor     r8d, r8d; Reserved
0x140014e7d  lea     rdx, aFiltertype; "FilterType"
0x140014e84  mov     rcx, [rbp+hKey]; hKey
0x140014e88  call    cs:__imp_RegSetValueExW
0x140014e8e  nop
0x140014e8f  mov     rcx, [rbp+hKey]
0x140014e93  test    rcx, rcx
0x140014e96  jz      short loc_140014E9E
0x140014e98  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x140014e9d  nop
0x140014e9e  jmp     short loc_140014F09
0x140014ea0  mov     [rbp+hKey], 0
0x140014ea8  mov     rcx, [rbp+hKey]; hKey
0x140014eac  test    rcx, rcx
0x140014eaf  jz      short loc_140014EB6
0x140014eb1  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140014eb6  mov     [rbp+hKey], 0
0x140014ebe  lea     rax, [rbp+hKey]
0x140014ec2  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140014ec7  mov     r9d, 0F003Fh; samDesired
0x140014ecd  xor     r8d, r8d; ulOptions
0x140014ed0  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x140014ed7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014ede  call    cs:__imp_RegOpenKeyExW
0x140014ee4  test    eax, eax
0x140014ee6  jnz     short loc_140014EFA
0x140014ee8  lea     rdx, aColorfiltering_1; "colorfiltering"
0x140014eef  mov     rcx, [rbp+hKey]; hKey
0x140014ef3  call    cs:__imp_RegDeleteTreeW
0x140014ef9  nop
0x140014efa  mov     rcx, [rbp+hKey]
0x140014efe  test    rcx, rcx
0x140014f01  jz      short loc_140014F09
0x140014f03  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x140014f08  nop
0x140014f09  add     rsp, 50h
0x140014f0d  pop     rbp
0x140014f0e  retn
```
