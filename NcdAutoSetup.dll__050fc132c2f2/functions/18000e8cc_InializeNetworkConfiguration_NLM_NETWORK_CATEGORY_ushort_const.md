# InializeNetworkConfiguration(NLM_NETWORK_CATEGORY,ushort const *)

- ea: `0x18000e8cc`
- end: `0x18000ead4`
- name: `?InializeNetworkConfiguration@@YAXW4NLM_NETWORK_CATEGORY@@PEBG@Z`
- size: `520`
- prototype: `void __fastcall(enum NLM_NETWORK_CATEGORY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1800107f0`

## callees

- `0x18000a644`
- `0x18000e8cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e97a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e9cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea67`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e97a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e9cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ea67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e93c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e93c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ea86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eabd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ea86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eabd`

## pseudocode

```c
void __fastcall InializeNetworkConfiguration(enum NLM_NETWORK_CATEGORY a1, const unsigned __int16 *a2)
{
  __int64 v3; // rbx
  HKEY v4; // rdi
  __int64 v5; // rbx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  v3 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  Data = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey) )
  {
    v4 = hKey;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"AutoSetup", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)&g_NetworkConfiguration + 4 * v3) = Data != 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(v4, L"MaxNetworkSize", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *((_DWORD *)&g_NetworkConfiguration + 4 * v3 + 1) = Data;
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(v4, L"MaxNetworkSizeAge", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    {
      v5 = 16 * v3;
    }
    else
    {
      v5 = 16 * v3;
      *(_DWORD *)((char *)&g_NetworkConfiguration + v5 + 8) = Data;
    }
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(v4, L"IgnorePrivateToDomainMapping", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      *(_DWORD *)((char *)&g_NetworkConfiguration + v5 + 12) = Data;
    if ( v4 )
      RegCloseKey(v4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
}

```

## disassembly

```asm
0x18000e8cc  mov     [rsp-28h+arg_0], rbx
0x18000e8d1  push    rbp
0x18000e8d2  push    rsi
0x18000e8d3  push    rdi
0x18000e8d4  push    r12
0x18000e8d6  push    r15
0x18000e8d8  mov     rbp, rsp
0x18000e8db  sub     rsp, 40h
0x18000e8df  mov     rsi, rdx
0x18000e8e2  movsxd  rbx, ecx
0x18000e8e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8ec  lea     r12, WPP_GLOBAL_Control
0x18000e8f3  cmp     rcx, r12
0x18000e8f6  jz      short loc_18000E913
0x18000e8f8  test    byte ptr [rcx+1Ch], 20h
0x18000e8fc  jz      short loc_18000E913
0x18000e8fe  mov     rcx, [rcx+10h]
0x18000e902  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000e909  mov     edx, 0Ah
0x18000e90e  call    WPP_SF_
0x18000e913  lea     rax, [rbp+hKey]
0x18000e917  mov     [rbp+Data], 0
0x18000e91e  xor     edi, edi
0x18000e920  mov     [rsp+40h+phkResult], rax; phkResult
0x18000e925  mov     r9d, 20019h; samDesired
0x18000e92b  mov     [rbp+hKey], rdi
0x18000e92f  xor     r8d, r8d; ulOptions
0x18000e932  mov     rdx, rsi; lpSubKey
0x18000e935  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e93c  call    cs:__imp_RegOpenKeyExW
0x18000e942  test    eax, eax
0x18000e944  jnz     loc_18000EA8E
0x18000e94a  mov     rdi, [rbp+hKey]
0x18000e94e  lea     esi, [rax+4]
0x18000e951  mov     [rbp+Type], eax
0x18000e954  lea     r9, [rbp+Type]; lpType
0x18000e958  lea     rax, [rbp+cbData]
0x18000e95c  mov     [rbp+cbData], esi
0x18000e95f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000e964  lea     rdx, ValueName; "AutoSetup"
0x18000e96b  lea     rax, [rbp+Data]
0x18000e96f  xor     r8d, r8d; lpReserved
0x18000e972  mov     rcx, rdi; hKey
0x18000e975  mov     [rsp+40h+phkResult], rax; lpData
0x18000e97a  call    cs:__imp_RegQueryValueExW
0x18000e980  lea     r15, ?g_NetworkConfiguration@@3PAUNETWORK_CONFIGURATION@@A; NETWORK_CONFIGURATION near * g_NetworkConfiguration
0x18000e987  test    eax, eax
0x18000e989  jnz     short loc_18000E9A2
0x18000e98b  cmp     [rbp+Type], esi
0x18000e98e  jnz     short loc_18000E9A2
0x18000e990  xor     ecx, ecx
0x18000e992  mov     rax, rbx
0x18000e995  cmp     [rbp+Data], ecx
0x18000e998  setnz   cl
0x18000e99b  add     rax, rax
0x18000e99e  mov     [r15+rax*8], ecx
0x18000e9a2  lea     rax, [rbp+cbData]
0x18000e9a6  mov     [rbp+Type], 0
0x18000e9ad  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000e9b2  lea     r9, [rbp+Type]; lpType
0x18000e9b6  lea     rax, [rbp+Data]
0x18000e9ba  mov     [rbp+cbData], esi
0x18000e9bd  xor     r8d, r8d; lpReserved
0x18000e9c0  mov     [rsp+40h+phkResult], rax; lpData
0x18000e9c5  lea     rdx, aMaxnetworksize_0; "MaxNetworkSize"
0x18000e9cc  mov     rcx, rdi; hKey
0x18000e9cf  call    cs:__imp_RegQueryValueExW
0x18000e9d5  test    eax, eax
0x18000e9d7  jnz     short loc_18000E9EC
0x18000e9d9  cmp     [rbp+Type], esi
0x18000e9dc  jnz     short loc_18000E9EC
0x18000e9de  mov     eax, [rbp+Data]
0x18000e9e1  mov     rcx, rbx
0x18000e9e4  add     rcx, rcx
0x18000e9e7  mov     [r15+rcx*8+4], eax
0x18000e9ec  lea     rax, [rbp+cbData]
0x18000e9f0  mov     [rbp+Type], 0
0x18000e9f7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000e9fc  lea     r9, [rbp+Type]; lpType
0x18000ea00  lea     rax, [rbp+Data]
0x18000ea04  mov     [rbp+cbData], esi
0x18000ea07  xor     r8d, r8d; lpReserved
0x18000ea0a  mov     [rsp+40h+phkResult], rax; lpData
0x18000ea0f  lea     rdx, aMaxnetworksize; "MaxNetworkSizeAge"
0x18000ea16  mov     rcx, rdi; hKey
0x18000ea19  call    cs:__imp_RegQueryValueExW
0x18000ea1f  test    eax, eax
0x18000ea21  jnz     short loc_18000EA36
0x18000ea23  cmp     [rbp+Type], esi
0x18000ea26  jnz     short loc_18000EA36
0x18000ea28  mov     eax, [rbp+Data]
0x18000ea2b  shl     rbx, 4
0x18000ea2f  mov     [rbx+r15+8], eax
0x18000ea34  jmp     short loc_18000EA3A
0x18000ea36  shl     rbx, 4
0x18000ea3a  lea     rax, [rbp+cbData]
0x18000ea3e  mov     [rbp+Type], 0
0x18000ea45  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000ea4a  lea     r9, [rbp+Type]; lpType
0x18000ea4e  lea     rax, [rbp+Data]
0x18000ea52  mov     [rbp+cbData], esi
0x18000ea55  xor     r8d, r8d; lpReserved
0x18000ea58  mov     [rsp+40h+phkResult], rax; lpData
0x18000ea5d  lea     rdx, aIgnoreprivatet; "IgnorePrivateToDomainMapping"
0x18000ea64  mov     rcx, rdi; hKey
0x18000ea67  call    cs:__imp_RegQueryValueExW
0x18000ea6d  test    eax, eax
0x18000ea6f  jnz     short loc_18000EA7E
0x18000ea71  cmp     [rbp+Type], esi
0x18000ea74  jnz     short loc_18000EA7E
0x18000ea76  mov     eax, [rbp+Data]
0x18000ea79  mov     [rbx+r15+0Ch], eax
0x18000ea7e  test    rdi, rdi
0x18000ea81  jz      short loc_18000EA8E
0x18000ea83  mov     rcx, rdi; hKey
0x18000ea86  call    cs:__imp_RegCloseKey
0x18000ea8c  xor     edi, edi
0x18000ea8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea95  cmp     rcx, r12
0x18000ea98  jz      short loc_18000EAB5
0x18000ea9a  test    byte ptr [rcx+1Ch], 20h
0x18000ea9e  jz      short loc_18000EAB5
0x18000eaa0  mov     rcx, [rcx+10h]
0x18000eaa4  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000eaab  mov     edx, 0Bh
0x18000eab0  call    WPP_SF_
0x18000eab5  test    rdi, rdi
0x18000eab8  jz      short loc_18000EAC3
0x18000eaba  mov     rcx, rdi; hKey
0x18000eabd  call    cs:__imp_RegCloseKey
0x18000eac3  mov     rbx, [rsp+40h+arg_0]
0x18000eac8  add     rsp, 40h
0x18000eacc  pop     r15
0x18000eace  pop     r12
0x18000ead0  pop     rdi
0x18000ead1  pop     rsi
0x18000ead2  pop     rbp
0x18000ead3  retn
```
