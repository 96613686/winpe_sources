# TcpipPlugin::SetInterfaceDHCPConfigurationV1

- ea: `0x18007c6b4`
- end: `0x18007c716`
- name: `TcpipPlugin::SetInterfaceDHCPConfigurationV1`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180018570`
- `0x180051cf0`
- `0x18007c588`

## callees

- `0x18005a5e8`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c6fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c6fd`

## pseudocode

```c
LSTATUS __fastcall TcpipPlugin::SetInterfaceDHCPConfigurationV1(NetSetup2::NetworkInterface *a1, HKEY a2)
{
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)Data = !NetSetup2::NetworkInterface::getordefault_DisableDhcp(a1);
  return RegSetValueExW(a2, L"EnableDHCP", 0, 4u, Data, 4u);
}

```

## disassembly

```asm
0x18007c6b4  push    rbx
0x18007c6b6  sub     rsp, 40h
0x18007c6ba  mov     rax, cs:__security_cookie
0x18007c6c1  xor     rax, rsp
0x18007c6c4  mov     [rsp+48h+var_10], rax
0x18007c6c9  mov     rbx, rdx
0x18007c6cc  call    ?getordefault_DisableDhcp@NetworkInterface@NetSetup2@@QEBA_NXZ; NetSetup2::NetworkInterface::getordefault_DisableDhcp(void)
0x18007c6d1  movzx   eax, al
0x18007c6d4  lea     rdx, aEnabledhcp; "EnableDHCP"
0x18007c6db  xor     eax, 1
0x18007c6de  mov     r9d, 4; dwType
0x18007c6e4  mov     dword ptr [rsp+48h+Data], eax
0x18007c6e8  xor     r8d, r8d; Reserved
0x18007c6eb  lea     rax, [rsp+48h+Data]
0x18007c6f0  mov     [rsp+48h+cbData], r9d; cbData
0x18007c6f5  mov     rcx, rbx; hKey
0x18007c6f8  mov     [rsp+48h+lpData], rax; lpData
0x18007c6fd  call    cs:__imp_RegSetValueExW
0x18007c703  mov     rcx, [rsp+48h+var_10]
0x18007c708  xor     rcx, rsp; StackCookie
0x18007c70b  call    __security_check_cookie
0x18007c710  add     rsp, 40h
0x18007c714  pop     rbx
0x18007c715  retn
```
