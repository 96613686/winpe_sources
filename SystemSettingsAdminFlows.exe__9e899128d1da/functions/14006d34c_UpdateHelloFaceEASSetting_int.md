# UpdateHelloFaceEASSetting(int)

- ea: `0x14006d34c`
- end: `0x14006d428`
- name: `?UpdateHelloFaceEASSetting@@YAJH@Z`
- size: `220`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x14000ed38`
- `0x14002c070`
- `0x14006d34c`

## import_xrefs

- `KERNEL32!RegCreateKeyExW` at `0x14006d3b0`
- `KERNEL32!RegCreateKeyExW` at `0x14006d3b0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14006d3dd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14006d3dd`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14006d402`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14006d402`

## pseudocode

```c
__int64 __fastcall UpdateHelloFaceEASSetting(int a1)
{
  HKEY *phkResult; // rax
  int Key; // ebx
  int v3; // eax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = 1;
  hKey = 0;
  if ( a1 )
  {
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Policies\\Microsoft\\Biometrics\\FacialFeatures",
            0,
            0,
            0,
            2u,
            0,
            phkResult,
            0);
    if ( !Key )
      Key = RegSetKeyValueW(hKey, 0, L"EnhancedAntiSpoofing", 4u, &Data, 4u);
    if ( Key > 0 )
      Key = (unsigned __int16)Key | 0x80070000;
  }
  else
  {
    v3 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Biometrics\\FacialFeatures");
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    Key = v3;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x14006d34c  push    rbx
0x14006d34e  sub     rsp, 50h
0x14006d352  mov     [rsp+58h+Data], 1
0x14006d35a  mov     [rsp+58h+hKey], 0
0x14006d363  test    ecx, ecx
0x14006d365  jz      loc_14006D3F4
0x14006d36b  lea     rcx, [rsp+58h+hKey]
0x14006d370  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x14006d375  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x14006d37e  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Biometri"...
0x14006d385  mov     [rsp+58h+phkResult], rax; phkResult
0x14006d38a  xor     r9d, r9d; lpClass
0x14006d38d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006d396  xor     r8d, r8d; Reserved
0x14006d399  mov     [rsp+58h+samDesired], 2; samDesired
0x14006d3a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006d3a8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14006d3b0  call    cs:__imp_RegCreateKeyExW
0x14006d3b6  mov     ebx, eax
0x14006d3b8  test    eax, eax
0x14006d3ba  jnz     short loc_14006D3E5
0x14006d3bc  mov     rcx, [rsp+58h+hKey]; hKey
0x14006d3c1  lea     r9d, [rax+4]; dwType
0x14006d3c5  lea     rax, [rsp+58h+Data]
0x14006d3ca  mov     [rsp+58h+samDesired], r9d; cbData
0x14006d3cf  lea     r8, aEnhancedantisp; "EnhancedAntiSpoofing"
0x14006d3d6  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x14006d3db  xor     edx, edx; lpSubKey
0x14006d3dd  call    cs:__imp_RegSetKeyValueW
0x14006d3e3  mov     ebx, eax
0x14006d3e5  test    ebx, ebx
0x14006d3e7  jle     short loc_14006D416
0x14006d3e9  movzx   ebx, bx
0x14006d3ec  or      ebx, 80070000h
0x14006d3f2  jmp     short loc_14006D416
0x14006d3f4  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Biometri"...
0x14006d3fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006d402  call    cs:__imp_RegDeleteKeyW
0x14006d408  test    eax, eax
0x14006d40a  jle     short loc_14006D414
0x14006d40c  movzx   eax, ax
0x14006d40f  or      eax, 80070000h
0x14006d414  mov     ebx, eax
0x14006d416  lea     rcx, [rsp+58h+hKey]
0x14006d41b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14006d420  mov     eax, ebx
0x14006d422  add     rsp, 50h
0x14006d426  pop     rbx
0x14006d427  retn
```
