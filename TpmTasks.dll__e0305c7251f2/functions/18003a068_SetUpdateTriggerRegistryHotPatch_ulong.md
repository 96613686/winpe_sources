# SetUpdateTriggerRegistryHotPatch(ulong)

- ea: `0x18003a068`
- end: `0x18003a122`
- name: `?SetUpdateTriggerRegistryHotPatch@@YAJK@Z`
- size: `186`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180036318`
- `0x1800393bc`

## callees

- `0x18000e48c`
- `0x180024780`
- `0x18003a068`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a0f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a0f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a0b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a0b8`

## string_xrefs

- `0x18003a0e1`: `AvailableUpdates`

## pseudocode

```c
__int64 __fastcall SetUpdateTriggerRegistryHotPatch(int a1)
{
  HKEY *phkResult; // rax
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  if ( (a1 & 0x19FE7) == 0 && a1 != 0x4000 )
    Data = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing\\Hotpatch",
         0,
         2u,
         phkResult);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    v4 = RegSetValueExW(hKey, L"AvailableUpdates", 0, 4u, (const BYTE *)&Data, 4u);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
      v3 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003a068  mov     [rsp+Data], ecx
0x18003a06c  push    rbx
0x18003a06d  sub     rsp, 30h
0x18003a071  mov     [rsp+38h+hKey], 0
0x18003a07a  test    ecx, 19FE7h
0x18003a080  jnz     short loc_18003A092
0x18003a082  cmp     ecx, 4000h
0x18003a088  jz      short loc_18003A092
0x18003a08a  mov     [rsp+38h+Data], 0
0x18003a092  lea     rcx, [rsp+38h+hKey]
0x18003a097  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18003a09c  mov     r9d, 2; samDesired
0x18003a0a2  mov     [rsp+38h+phkResult], rax; phkResult
0x18003a0a7  xor     r8d, r8d; ulOptions
0x18003a0aa  lea     rdx, aSystemCurrentc_15; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003a0b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a0b8  call    cs:__imp_RegOpenKeyExW
0x18003a0be  mov     ebx, eax
0x18003a0c0  test    eax, eax
0x18003a0c2  jle     short loc_18003A0CD
0x18003a0c4  movzx   ebx, ax
0x18003a0c7  or      ebx, 80070000h
0x18003a0cd  test    ebx, ebx
0x18003a0cf  js      short loc_18003A110
0x18003a0d1  mov     rcx, [rsp+38h+hKey]; hKey
0x18003a0d6  lea     rax, [rsp+38h+Data]
0x18003a0db  mov     r9d, 4; dwType
0x18003a0e1  lea     rdx, aAvailableupdat; "AvailableUpdates"
0x18003a0e8  mov     [rsp+38h+cbData], r9d; cbData
0x18003a0ed  xor     r8d, r8d; Reserved
0x18003a0f0  mov     [rsp+38h+phkResult], rax; lpData
0x18003a0f5  call    cs:__imp_RegSetValueExW
0x18003a0fb  mov     ebx, eax
0x18003a0fd  test    eax, eax
0x18003a0ff  jle     short loc_18003A10A
0x18003a101  movzx   ebx, ax
0x18003a104  or      ebx, 80070000h
0x18003a10a  test    ebx, ebx
0x18003a10c  js      short loc_18003A110
0x18003a10e  xor     ebx, ebx
0x18003a110  lea     rcx, [rsp+38h+hKey]
0x18003a115  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a11a  mov     eax, ebx
0x18003a11c  add     rsp, 30h
0x18003a120  pop     rbx
0x18003a121  retn
```
