# DsmRpcSetCostedNetworkPolicy

- ea: `0x18002e3d0`
- end: `0x18002e484`
- name: `DsmRpcSetCostedNetworkPolicy`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x18000b9dc`
- `0x18000bfc0`
- `0x180021790`
- `0x18002e3d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e44b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e44b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e471`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e471`

## pseudocode

```c
__int64 __fastcall DsmRpcSetCostedNetworkPolicy(__int64 a1, int a2)
{
  signed int DeviceSetupKey; // ebx
  LSTATUS v4; // eax
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids);
  hKey = 0;
  DeviceSetupKey = GetDeviceSetupKey(&hKey);
  if ( DeviceSetupKey >= 0 )
  {
    Data = a2;
    v4 = RegSetValueExW(hKey, L"CostedNetworkPolicy", 0, 4u, (const BYTE *)&Data, 4u);
    DeviceSetupKey = v4;
    if ( v4 > 0 )
      DeviceSetupKey = (unsigned __int16)v4 | 0x80070000;
    CDsmCore::OnConnectionAvailabilityParamChanged((CDsmCore *)&g_DsmCore);
    RegCloseKey(hKey);
  }
  return (unsigned int)DeviceSetupKey;
}

```

## disassembly

```asm
0x18002e3d0  mov     [rsp+arg_0], rbx
0x18002e3d5  push    rdi
0x18002e3d6  sub     rsp, 30h
0x18002e3da  mov     edi, edx
0x18002e3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3e3  lea     rax, WPP_GLOBAL_Control
0x18002e3ea  cmp     rcx, rax
0x18002e3ed  jz      short loc_18002E40A
0x18002e3ef  test    byte ptr [rcx+1Ch], 1
0x18002e3f3  jz      short loc_18002E40A
0x18002e3f5  mov     rcx, [rcx+10h]
0x18002e3f9  lea     r8, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids
0x18002e400  mov     edx, 1Fh
0x18002e405  call    WPP_SF_
0x18002e40a  lea     rcx, [rsp+38h+hKey]; phkResult
0x18002e40f  mov     [rsp+38h+hKey], 0
0x18002e418  call    ?GetDeviceSetupKey@@YAJPEAPEAUHKEY__@@@Z; GetDeviceSetupKey(HKEY__ * *)
0x18002e41d  mov     ebx, eax
0x18002e41f  test    eax, eax
0x18002e421  js      short loc_18002E477
0x18002e423  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e428  lea     rax, [rsp+38h+Data]
0x18002e42d  mov     r9d, 4; dwType
0x18002e433  mov     [rsp+38h+Data], edi
0x18002e437  mov     [rsp+38h+cbData], r9d; cbData
0x18002e43c  lea     rdx, Value; "CostedNetworkPolicy"
0x18002e443  xor     r8d, r8d; Reserved
0x18002e446  mov     [rsp+38h+lpData], rax; lpData
0x18002e44b  call    cs:__imp_RegSetValueExW
0x18002e451  mov     ebx, eax
0x18002e453  test    eax, eax
0x18002e455  jle     short loc_18002E460
0x18002e457  movzx   ebx, ax
0x18002e45a  or      ebx, 80070000h
0x18002e460  lea     rcx, ?g_DsmCore@@3VCDsmCore@@A; this
0x18002e467  call    ?OnConnectionAvailabilityParamChanged@CDsmCore@@QEAAXXZ; CDsmCore::OnConnectionAvailabilityParamChanged(void)
0x18002e46c  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e471  call    cs:__imp_RegCloseKey
0x18002e477  mov     eax, ebx
0x18002e479  mov     rbx, [rsp+38h+arg_0]
0x18002e47e  add     rsp, 30h
0x18002e482  pop     rdi
0x18002e483  retn
```
