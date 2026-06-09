# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)

- ea: `0x140014f18`
- end: `0x14001503f`
- name: `?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z`
- size: `295`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400143ac`

## callees

- `0x140011000`
- `0x140011018`
- `0x1400133cc`
- `0x140014f18`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001500e`
- `ADVAPI32!RegOpenKeyExW` at `0x14001500e`
- `KERNEL32!RegDeleteTreeW` at `0x140015023`
- `KERNEL32!RegDeleteTreeW` at `0x140015023`
- `KERNEL32!RegCreateKeyExW` at `0x140014f8e`
- `KERNEL32!RegCreateKeyExW` at `0x140014f8e`
- `KERNEL32!RegSetValueExW` at `0x140014fb8`
- `KERNEL32!RegSetValueExW` at `0x140014fb8`

## string_xrefs

- `0x140015000`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x140014f80`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
void __fastcall ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(int a1)
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
      RegSetValueExW(hKey, L"Gain", 0, 4u, (const BYTE *)&Data, 4u);
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
0x140014f18  push    rbp
0x140014f1a  mov     rbp, rsp
0x140014f1d  sub     rsp, 50h
0x140014f21  mov     [rbp+Data], ecx
0x140014f24  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x140014f29  test    al, al
0x140014f2b  jz      loc_140014FD0
0x140014f31  mov     [rbp+hKey], 0
0x140014f39  mov     rcx, [rbp+hKey]; hKey
0x140014f3d  test    rcx, rcx
0x140014f40  jz      short loc_140014F47
0x140014f42  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140014f47  mov     [rbp+hKey], 0
0x140014f4f  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x140014f58  lea     rax, [rbp+hKey]
0x140014f5c  mov     [rsp+50h+phkResult], rax; phkResult
0x140014f61  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140014f6a  mov     [rsp+50h+samDesired], 3; samDesired
0x140014f72  mov     [rsp+50h+dwOptions], 1; dwOptions
0x140014f7a  xor     r9d, r9d; lpClass
0x140014f7d  xor     r8d, r8d; Reserved
0x140014f80  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x140014f87  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014f8e  call    cs:__imp_RegCreateKeyExW
0x140014f94  test    eax, eax
0x140014f96  jnz     short loc_140014FBF
0x140014f98  lea     r9d, [rax+4]; dwType
0x140014f9c  mov     [rsp+50h+samDesired], r9d; cbData
0x140014fa1  lea     rax, [rbp+Data]
0x140014fa5  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140014faa  xor     r8d, r8d; Reserved
0x140014fad  lea     rdx, aGain; "Gain"
0x140014fb4  mov     rcx, [rbp+hKey]; hKey
0x140014fb8  call    cs:__imp_RegSetValueExW
0x140014fbe  nop
0x140014fbf  mov     rcx, [rbp+hKey]
0x140014fc3  test    rcx, rcx
0x140014fc6  jz      short loc_140014FCE
0x140014fc8  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x140014fcd  nop
0x140014fce  jmp     short loc_140015039
0x140014fd0  mov     [rbp+hKey], 0
0x140014fd8  mov     rcx, [rbp+hKey]; hKey
0x140014fdc  test    rcx, rcx
0x140014fdf  jz      short loc_140014FE6
0x140014fe1  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140014fe6  mov     [rbp+hKey], 0
0x140014fee  lea     rax, [rbp+hKey]
0x140014ff2  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140014ff7  mov     r9d, 0F003Fh; samDesired
0x140014ffd  xor     r8d, r8d; ulOptions
0x140015000  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x140015007  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001500e  call    cs:__imp_RegOpenKeyExW
0x140015014  test    eax, eax
0x140015016  jnz     short loc_14001502A
0x140015018  lea     rdx, aColorfiltering_1; "colorfiltering"
0x14001501f  mov     rcx, [rbp+hKey]; hKey
0x140015023  call    cs:__imp_RegDeleteTreeW
0x140015029  nop
0x14001502a  mov     rcx, [rbp+hKey]
0x14001502e  test    rcx, rcx
0x140015031  jz      short loc_140015039
0x140015033  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x140015038  nop
0x140015039  add     rsp, 50h
0x14001503d  pop     rbp
0x14001503e  retn
```
