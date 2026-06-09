# TcpipPlugin::SetDefaultInterfaceParameters

- ea: `0x18007c588`
- end: `0x18007c61b`
- name: `TcpipPlugin::SetDefaultInterfaceParameters`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180018570`

## callees

- `0x18007c588`
- `0x18007c6b4`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c5d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c602`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c5d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c602`

## pseudocode

```c
LSTATUS __fastcall TcpipPlugin::SetDefaultInterfaceParameters(__int64 a1, HKEY a2)
{
  LSTATUS result; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF

  result = TcpipPlugin::SetInterfaceDHCPConfigurationV1(a1, a2);
  if ( !result )
  {
    *(_WORD *)Data = 0;
    result = RegSetValueExW(a2, L"Domain", 0, 1u, Data, 2u);
    if ( !result )
      return RegSetValueExW(a2, L"NameServer", 0, 1u, Data, 2u);
  }
  return result;
}

```

## disassembly

```asm
0x18007c588  push    rbx
0x18007c58a  sub     rsp, 40h
0x18007c58e  mov     rax, cs:__security_cookie
0x18007c595  xor     rax, rsp
0x18007c598  mov     [rsp+48h+var_10], rax
0x18007c59d  mov     rbx, rdx
0x18007c5a0  call    TcpipPlugin__SetInterfaceDHCPConfigurationV1
0x18007c5a5  test    eax, eax
0x18007c5a7  jnz     short loc_18007C608
0x18007c5a9  mov     word ptr [rsp+48h+Data], ax
0x18007c5ae  lea     rdx, aDomain; "Domain"
0x18007c5b5  lea     rax, [rsp+48h+Data]
0x18007c5ba  mov     [rsp+48h+cbData], 2; cbData
0x18007c5c2  mov     r9d, 1; dwType
0x18007c5c8  mov     [rsp+48h+lpData], rax; lpData
0x18007c5cd  xor     r8d, r8d; Reserved
0x18007c5d0  mov     rcx, rbx; hKey
0x18007c5d3  call    cs:__imp_RegSetValueExW
0x18007c5d9  test    eax, eax
0x18007c5db  jnz     short loc_18007C608
0x18007c5dd  lea     rax, [rsp+48h+Data]
0x18007c5e2  mov     [rsp+48h+cbData], 2; cbData
0x18007c5ea  mov     r9d, 1; dwType
0x18007c5f0  mov     [rsp+48h+lpData], rax; lpData
0x18007c5f5  xor     r8d, r8d; Reserved
0x18007c5f8  lea     rdx, aNameserver; "NameServer"
0x18007c5ff  mov     rcx, rbx; hKey
0x18007c602  call    cs:__imp_RegSetValueExW
0x18007c608  mov     rcx, [rsp+48h+var_10]
0x18007c60d  xor     rcx, rsp; StackCookie
0x18007c610  call    __security_check_cookie
0x18007c615  add     rsp, 40h
0x18007c619  pop     rbx
0x18007c61a  retn
```
