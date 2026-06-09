# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsActive(bool)

- ea: `0x140014cbc`
- end: `0x140014de1`
- name: `?UpdateTransferSettingsActive@ColorFilterHelper@ColorFiltering@@SAX_N@Z`
- size: `293`
- prototype: `void __fastcall(bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000b250`
- `0x1400133cc`

## callees

- `0x140011000`
- `0x140011018`
- `0x140014cbc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140014db0`
- `ADVAPI32!RegOpenKeyExW` at `0x140014db0`
- `KERNEL32!RegDeleteTreeW` at `0x140014dc5`
- `KERNEL32!RegDeleteTreeW` at `0x140014dc5`
- `KERNEL32!RegCreateKeyExW` at `0x140014d30`
- `KERNEL32!RegCreateKeyExW` at `0x140014d30`
- `KERNEL32!RegSetValueExW` at `0x140014d5a`
- `KERNEL32!RegSetValueExW` at `0x140014d5a`

## string_xrefs

- `0x140014da2`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x140014d22`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

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
0x140014cbc  push    rbp
0x140014cbe  mov     rbp, rsp
0x140014cc1  sub     rsp, 50h
0x140014cc5  movzx   eax, cl
0x140014cc8  mov     [rbp+Data], eax
0x140014ccb  test    cl, cl
0x140014ccd  jz      loc_140014D72
0x140014cd3  mov     [rbp+hKey], 0
0x140014cdb  mov     rcx, [rbp+hKey]; hKey
0x140014cdf  test    rcx, rcx
0x140014ce2  jz      short loc_140014CE9
0x140014ce4  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140014ce9  mov     [rbp+hKey], 0
0x140014cf1  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x140014cfa  lea     rax, [rbp+hKey]
0x140014cfe  mov     [rsp+50h+phkResult], rax; phkResult
0x140014d03  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140014d0c  mov     [rsp+50h+samDesired], 3; samDesired
0x140014d14  mov     [rsp+50h+dwOptions], 1; dwOptions
0x140014d1c  xor     r9d, r9d; lpClass
0x140014d1f  xor     r8d, r8d; Reserved
0x140014d22  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x140014d29  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014d30  call    cs:__imp_RegCreateKeyExW
0x140014d36  test    eax, eax
0x140014d38  jnz     short loc_140014D61
0x140014d3a  lea     r9d, [rax+4]; dwType
0x140014d3e  mov     [rsp+50h+samDesired], r9d; cbData
0x140014d43  lea     rax, [rbp+Data]
0x140014d47  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140014d4c  xor     r8d, r8d; Reserved
0x140014d4f  lea     rdx, aActive; "Active"
0x140014d56  mov     rcx, [rbp+hKey]; hKey
0x140014d5a  call    cs:__imp_RegSetValueExW
0x140014d60  nop
0x140014d61  mov     rcx, [rbp+hKey]
0x140014d65  test    rcx, rcx
0x140014d68  jz      short loc_140014D70
0x140014d6a  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x140014d6f  nop
0x140014d70  jmp     short loc_140014DDB
0x140014d72  mov     [rbp+hKey], 0
0x140014d7a  mov     rcx, [rbp+hKey]; hKey
0x140014d7e  test    rcx, rcx
0x140014d81  jz      short loc_140014D88
0x140014d83  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140014d88  mov     [rbp+hKey], 0
0x140014d90  lea     rax, [rbp+hKey]
0x140014d94  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140014d99  mov     r9d, 0F003Fh; samDesired
0x140014d9f  xor     r8d, r8d; ulOptions
0x140014da2  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x140014da9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140014db0  call    cs:__imp_RegOpenKeyExW
0x140014db6  test    eax, eax
0x140014db8  jnz     short loc_140014DCC
0x140014dba  lea     rdx, aColorfiltering_1; "colorfiltering"
0x140014dc1  mov     rcx, [rbp+hKey]; hKey
0x140014dc5  call    cs:__imp_RegDeleteTreeW
0x140014dcb  nop
0x140014dcc  mov     rcx, [rbp+hKey]
0x140014dd0  test    rcx, rcx
0x140014dd3  jz      short loc_140014DDB
0x140014dd5  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x140014dda  nop
0x140014ddb  add     rsp, 50h
0x140014ddf  pop     rbp
0x140014de0  retn
```
