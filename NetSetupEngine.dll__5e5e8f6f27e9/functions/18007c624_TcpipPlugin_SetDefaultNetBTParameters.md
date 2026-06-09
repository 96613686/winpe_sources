# TcpipPlugin::SetDefaultNetBTParameters

- ea: `0x18007c624`
- end: `0x18007c6ae`
- name: `TcpipPlugin::SetDefaultNetBTParameters`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180018570`

## callees

- `0x18007c624`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c66b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c695`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c66b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c695`

## pseudocode

```c
LSTATUS __fastcall TcpipPlugin::SetDefaultNetBTParameters(__int64 a1, HKEY a2)
{
  LSTATUS result; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)Data = 0;
  result = RegSetValueExW(a2, L"NameServerList", 0, 7u, (const BYTE *)&::Data, 2u);
  if ( !result )
    return RegSetValueExW(a2, L"NetbiosOptions", 0, 4u, Data, 4u);
  return result;
}

```

## disassembly

```asm
0x18007c624  push    rbx
0x18007c626  sub     rsp, 40h
0x18007c62a  mov     rax, cs:__security_cookie
0x18007c631  xor     rax, rsp
0x18007c634  mov     [rsp+48h+var_10], rax
0x18007c639  mov     rbx, rdx
0x18007c63c  mov     [rsp+48h+cbData], 2; cbData
0x18007c644  lea     rax, Data
0x18007c64b  mov     dword ptr [rsp+48h+Data], 0
0x18007c653  mov     rcx, rbx; hKey
0x18007c656  mov     [rsp+48h+lpData], rax; lpData
0x18007c65b  mov     r9d, 7; dwType
0x18007c661  lea     rdx, aNameserverlist; "NameServerList"
0x18007c668  xor     r8d, r8d; Reserved
0x18007c66b  call    cs:__imp_RegSetValueExW
0x18007c671  test    eax, eax
0x18007c673  jnz     short loc_18007C69B
0x18007c675  lea     r9d, [rax+4]; dwType
0x18007c679  xor     r8d, r8d; Reserved
0x18007c67c  lea     rax, [rsp+48h+Data]
0x18007c681  mov     [rsp+48h+cbData], r9d; cbData
0x18007c686  lea     rdx, aNetbiosoptions; "NetbiosOptions"
0x18007c68d  mov     [rsp+48h+lpData], rax; lpData
0x18007c692  mov     rcx, rbx; hKey
0x18007c695  call    cs:__imp_RegSetValueExW
0x18007c69b  mov     rcx, [rsp+48h+var_10]
0x18007c6a0  xor     rcx, rsp; StackCookie
0x18007c6a3  call    __security_check_cookie
0x18007c6a8  add     rsp, 40h
0x18007c6ac  pop     rbx
0x18007c6ad  retn
```
