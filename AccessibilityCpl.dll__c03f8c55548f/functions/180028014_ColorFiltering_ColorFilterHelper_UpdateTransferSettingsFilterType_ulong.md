# ColorFiltering::ColorFilterHelper::UpdateTransferSettingsFilterType(ulong)

- ea: `0x180028014`
- end: `0x180028131`
- name: `?UpdateTransferSettingsFilterType@ColorFilterHelper@ColorFiltering@@SAXK@Z`
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
- `0x180028014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002808a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002808a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800280b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800280b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028105`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028105`
- `ADVAPI32!RegDeleteTreeW` at `0x18002811a`
- `ADVAPI32!RegDeleteTreeW` at `0x18002811a`

## string_xrefs

- `0x1800280f7`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\`
- `0x18002807c`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\colorfiltering`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180028014  push    rbp
0x180028016  mov     rbp, rsp
0x180028019  sub     rsp, 50h
0x18002801d  mov     [rbp+Data], ecx
0x180028020  call    ?IsActive@ColorFilterHelper@ColorFiltering@@SA_NXZ; ColorFiltering::ColorFilterHelper::IsActive(void)
0x180028025  test    al, al
0x180028027  jz      loc_1800280C7
0x18002802d  mov     [rbp+hKey], 0
0x180028035  mov     rcx, [rbp+hKey]; hKey
0x180028039  test    rcx, rcx
0x18002803c  jz      short loc_180028043
0x18002803e  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x180028043  mov     [rbp+hKey], 0
0x18002804b  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180028054  lea     rax, [rbp+hKey]
0x180028058  mov     [rsp+50h+phkResult], rax; phkResult
0x18002805d  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180028066  mov     [rsp+50h+samDesired], 3; samDesired
0x18002806e  mov     [rsp+50h+dwOptions], 1; dwOptions
0x180028076  xor     r9d, r9d; lpClass
0x180028079  xor     r8d, r8d; Reserved
0x18002807c  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x180028083  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002808a  call    cs:__imp_RegCreateKeyExW
0x180028090  test    eax, eax
0x180028092  jnz     short loc_1800280BB
0x180028094  lea     r9d, [rax+4]; dwType
0x180028098  mov     [rsp+50h+samDesired], r9d; cbData
0x18002809d  lea     rax, [rbp+Data]
0x1800280a1  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1800280a6  xor     r8d, r8d; Reserved
0x1800280a9  lea     rdx, aFiltertype; "FilterType"
0x1800280b0  mov     rcx, [rbp+hKey]; hKey
0x1800280b4  call    cs:__imp_RegSetValueExW
0x1800280ba  nop
0x1800280bb  lea     rcx, [rbp+hKey]
0x1800280bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800280c4  nop
0x1800280c5  jmp     short loc_18002812B
0x1800280c7  mov     [rbp+hKey], 0
0x1800280cf  mov     rcx, [rbp+hKey]; hKey
0x1800280d3  test    rcx, rcx
0x1800280d6  jz      short loc_1800280DD
0x1800280d8  call    ?close_reset@?$close_invoke_helper@$00P6AJPEAUHKEY__@@@Z$1?RegCloseKey@@YAJ0@ZPEAU1@@details@wil@@SAXPEAUHKEY__@@@Z; wil::details::close_invoke_helper<1,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),HKEY__ *>::close_reset(HKEY__ *)
0x1800280dd  mov     [rbp+hKey], 0
0x1800280e5  lea     rax, [rbp+hKey]
0x1800280e9  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x1800280ee  mov     r9d, 0F003Fh; samDesired
0x1800280f4  xor     r8d, r8d; ulOptions
0x1800280f7  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800280fe  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180028105  call    cs:__imp_RegOpenKeyExW
0x18002810b  test    eax, eax
0x18002810d  jnz     short loc_180028121
0x18002810f  lea     rdx, aColorfiltering_0; "colorfiltering"
0x180028116  mov     rcx, [rbp+hKey]; hKey
0x18002811a  call    cs:__imp_RegDeleteTreeW
0x180028120  nop
0x180028121  lea     rcx, [rbp+hKey]
0x180028125  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002812a  nop
0x18002812b  add     rsp, 50h
0x18002812f  pop     rbp
0x180028130  retn
```
