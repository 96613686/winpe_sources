# CDPAdminHandler::DispatchToggleCDPBluetooth(bool)

- ea: `0x140066b38`
- end: `0x140066bd2`
- name: `?DispatchToggleCDPBluetooth@CDPAdminHandler@@CAJ_N@Z`
- size: `154`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140020120`

## callees

- `0x14000ed38`
- `0x14002c070`
- `0x140066b38`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140066b74`
- `KERNEL32!RegOpenKeyExW` at `0x140066b74`
- `KERNEL32!RegSetValueExW` at `0x140066ba6`
- `KERNEL32!RegSetValueExW` at `0x140066ba6`

## pseudocode

```c
__int64 __fastcall CDPAdminHandler::DispatchToggleCDPBluetooth(unsigned __int8 a1)
{
  int v1; // edi
  HKEY *phkResult; // rax
  int v3; // ebx
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v1 = a1;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\SmartGlass",
         0,
         0x20106u,
         phkResult);
  if ( !v3 )
  {
    Data = v1;
    v3 = RegSetValueExW(hKey, L"BluetoothPolicy", 0, 4u, (const BYTE *)&Data, 4u);
  }
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140066b38  mov     [rsp+arg_0], rbx
0x140066b3d  push    rdi
0x140066b3e  sub     rsp, 30h
0x140066b42  movzx   edi, cl
0x140066b45  lea     rcx, [rsp+38h+hKey]
0x140066b4a  mov     [rsp+38h+hKey], 0
0x140066b53  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140066b58  mov     r9d, 20106h; samDesired
0x140066b5e  mov     [rsp+38h+phkResult], rax; phkResult
0x140066b63  xor     r8d, r8d; ulOptions
0x140066b66  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140066b6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140066b74  call    cs:__imp_RegOpenKeyExW
0x140066b7a  mov     ebx, eax
0x140066b7c  test    eax, eax
0x140066b7e  jnz     short loc_140066BAE
0x140066b80  mov     rcx, [rsp+38h+hKey]; hKey
0x140066b85  lea     r9d, [rax+4]; dwType
0x140066b89  lea     rax, [rsp+38h+Data]
0x140066b8e  mov     [rsp+38h+cbData], r9d; cbData
0x140066b93  xor     r8d, r8d; Reserved
0x140066b96  mov     [rsp+38h+phkResult], rax; lpData
0x140066b9b  lea     rdx, aBluetoothpolic; "BluetoothPolicy"
0x140066ba2  mov     [rsp+38h+Data], edi
0x140066ba6  call    cs:__imp_RegSetValueExW
0x140066bac  mov     ebx, eax
0x140066bae  test    ebx, ebx
0x140066bb0  jle     short loc_140066BBB
0x140066bb2  movzx   ebx, bx
0x140066bb5  or      ebx, 80070000h
0x140066bbb  lea     rcx, [rsp+38h+hKey]
0x140066bc0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140066bc5  mov     eax, ebx
0x140066bc7  mov     rbx, [rsp+38h+arg_0]
0x140066bcc  add     rsp, 30h
0x140066bd0  pop     rdi
0x140066bd1  retn
```
