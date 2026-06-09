# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsIntensity(ulong)

- ea: `0x140015048`
- end: `0x14001516f`
- name: `?UpdateTransferSettingsIntensity@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x140015048`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001513e`
- `ADVAPI32!RegOpenKeyExW` at `0x14001513e`
- `KERNEL32!RegDeleteTreeW` at `0x140015153`
- `KERNEL32!RegDeleteTreeW` at `0x140015153`
- `KERNEL32!RegCreateKeyExW` at `0x1400150be`
- `KERNEL32!RegCreateKeyExW` at `0x1400150be`
- `KERNEL32!RegSetValueExW` at `0x1400150e8`
- `KERNEL32!RegSetValueExW` at `0x1400150e8`

## string_xrefs

- `0x140015130`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1400150b0`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

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
0x140015048  push    rbp
0x14001504a  mov     rbp, rsp
0x14001504d  sub     rsp, 50h
0x140015051  mov     [rbp+Data], ecx
0x140015054  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x140015059  test    al, al
0x14001505b  jz      loc_140015100
0x140015061  mov     [rbp+hKey], 0
0x140015069  mov     rcx, [rbp+hKey]; hKey
0x14001506d  test    rcx, rcx
0x140015070  jz      short loc_140015077
0x140015072  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140015077  mov     [rbp+hKey], 0
0x14001507f  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x140015088  lea     rax, [rbp+hKey]
0x14001508c  mov     [rsp+50h+phkResult], rax; phkResult
0x140015091  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001509a  mov     [rsp+50h+samDesired], 3; samDesired
0x1400150a2  mov     [rsp+50h+dwOptions], 1; dwOptions
0x1400150aa  xor     r9d, r9d; lpClass
0x1400150ad  xor     r8d, r8d; Reserved
0x1400150b0  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400150b7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400150be  call    cs:__imp_RegCreateKeyExW
0x1400150c4  test    eax, eax
0x1400150c6  jnz     short loc_1400150EF
0x1400150c8  lea     r9d, [rax+4]; dwType
0x1400150cc  mov     [rsp+50h+samDesired], r9d; cbData
0x1400150d1  lea     rax, [rbp+Data]
0x1400150d5  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400150da  xor     r8d, r8d; Reserved
0x1400150dd  lea     rdx, aIntensity; "Intensity"
0x1400150e4  mov     rcx, [rbp+hKey]; hKey
0x1400150e8  call    cs:__imp_RegSetValueExW
0x1400150ee  nop
0x1400150ef  mov     rcx, [rbp+hKey]
0x1400150f3  test    rcx, rcx
0x1400150f6  jz      short loc_1400150FE
0x1400150f8  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x1400150fd  nop
0x1400150fe  jmp     short loc_140015169
0x140015100  mov     [rbp+hKey], 0
0x140015108  mov     rcx, [rbp+hKey]; hKey
0x14001510c  test    rcx, rcx
0x14001510f  jz      short loc_140015116
0x140015111  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x140015116  mov     [rbp+hKey], 0
0x14001511e  lea     rax, [rbp+hKey]
0x140015122  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140015127  mov     r9d, 0F003Fh; samDesired
0x14001512d  xor     r8d, r8d; ulOptions
0x140015130  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x140015137  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14001513e  call    cs:__imp_RegOpenKeyExW
0x140015144  test    eax, eax
0x140015146  jnz     short loc_14001515A
0x140015148  lea     rdx, aColorfiltering_1; "colorfiltering"
0x14001514f  mov     rcx, [rbp+hKey]; hKey
0x140015153  call    cs:__imp_RegDeleteTreeW
0x140015159  nop
0x14001515a  mov     rcx, [rbp+hKey]
0x14001515e  test    rcx, rcx
0x140015161  jz      short loc_140015169
0x140015163  call    ?close@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close(HKEY__ *)
0x140015168  nop
0x140015169  add     rsp, 50h
0x14001516d  pop     rbp
0x14001516e  retn
```
