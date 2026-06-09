# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsGain(ulong)

- ea: `0x180028138`
- end: `0x180028255`
- name: `?UpdateTransferSettingsGain@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x180028138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800281ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800281ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800281d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800281d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028229`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028229`
- `ADVAPI32!RegDeleteTreeW` at `0x18002823e`
- `ADVAPI32!RegDeleteTreeW` at `0x18002823e`

## string_xrefs

- `0x18002821b`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x1800281a0`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

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
0x180028138  push    rbp
0x18002813a  mov     rbp, rsp
0x18002813d  sub     rsp, 50h
0x180028141  mov     [rbp+Data], ecx
0x180028144  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x180028149  test    al, al
0x18002814b  jz      loc_1800281EB
0x180028151  mov     [rbp+hKey], 0
0x180028159  mov     rcx, [rbp+hKey]; hKey
0x18002815d  test    rcx, rcx
0x180028160  jz      short loc_180028167
0x180028162  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x180028167  mov     [rbp+hKey], 0
0x18002816f  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180028178  lea     rax, [rbp+hKey]
0x18002817c  mov     [rsp+50h+phkResult], rax; phkResult
0x180028181  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002818a  mov     [rsp+50h+samDesired], 3; samDesired
0x180028192  mov     [rsp+50h+dwOptions], 1; dwOptions
0x18002819a  xor     r9d, r9d; lpClass
0x18002819d  xor     r8d, r8d; Reserved
0x1800281a0  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800281a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800281ae  call    cs:__imp_RegCreateKeyExW
0x1800281b4  test    eax, eax
0x1800281b6  jnz     short loc_1800281DF
0x1800281b8  lea     r9d, [rax+4]; dwType
0x1800281bc  mov     [rsp+50h+samDesired], r9d; cbData
0x1800281c1  lea     rax, [rbp+Data]
0x1800281c5  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800281ca  xor     r8d, r8d; Reserved
0x1800281cd  lea     rdx, aGain; "Gain"
0x1800281d4  mov     rcx, [rbp+hKey]; hKey
0x1800281d8  call    cs:__imp_RegSetValueExW
0x1800281de  nop
0x1800281df  lea     rcx, [rbp+hKey]
0x1800281e3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800281e8  nop
0x1800281e9  jmp     short loc_18002824F
0x1800281eb  mov     [rbp+hKey], 0
0x1800281f3  mov     rcx, [rbp+hKey]; hKey
0x1800281f7  test    rcx, rcx
0x1800281fa  jz      short loc_180028201
0x1800281fc  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x180028201  mov     [rbp+hKey], 0
0x180028209  lea     rax, [rbp+hKey]
0x18002820d  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x180028212  mov     r9d, 0F003Fh; samDesired
0x180028218  xor     r8d, r8d; ulOptions
0x18002821b  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x180028222  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180028229  call    cs:__imp_RegOpenKeyExW
0x18002822f  test    eax, eax
0x180028231  jnz     short loc_180028245
0x180028233  lea     rdx, aColorfiltering_0; "colorfiltering"
0x18002823a  mov     rcx, [rbp+hKey]; hKey
0x18002823e  call    cs:__imp_RegDeleteTreeW
0x180028244  nop
0x180028245  lea     rcx, [rbp+hKey]
0x180028249  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002824e  nop
0x18002824f  add     rsp, 50h
0x180028253  pop     rbp
0x180028254  retn
```
