# GetNetworkQualificationFromRegistry(ushort const *,int *,int *)

- ea: `0x18000e5c0`
- end: `0x18000e753`
- name: `?GetNetworkQualificationFromRegistry@@YAJPEBGPEAH1@Z`
- size: `403`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180010120`

## callees

- `0x18000a644`
- `0x18000e5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e683`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e6d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e683`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e6d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e642`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e73a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e6f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e73a`

## pseudocode

```c
__int64 __fastcall GetNetworkQualificationFromRegistry(LPCWSTR lpSubKey, int *a2, int *a3)
{
  LSTATUS v6; // ebx
  HKEY v7; // rdi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  Data = 0;
  *a2 = 0;
  *a3 = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( !v6 )
  {
    v7 = hKey;
    Type = 0;
    cbData = 4;
    v6 = RegQueryValueExW(hKey, L"AutoSetup", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v6 )
    {
      if ( Type == 4 )
      {
        Type = 0;
        cbData = 4;
        *a2 = Data != 0;
        if ( !RegQueryValueExW(v7, L"NetworkSizeEverDisqualified", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
          *a3 = 1;
        v6 = 0;
      }
      else
      {
        v6 = 13;
      }
    }
    if ( v7 )
      RegCloseKey(v7);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e5c0  mov     [rsp-28h+arg_0], rbx
0x18000e5c5  push    rbp
0x18000e5c6  push    rsi
0x18000e5c7  push    rdi
0x18000e5c8  push    r13
0x18000e5ca  push    r14
0x18000e5cc  mov     rbp, rsp
0x18000e5cf  sub     rsp, 40h
0x18000e5d3  mov     rsi, r8
0x18000e5d6  mov     r14, rdx
0x18000e5d9  mov     rbx, rcx
0x18000e5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5e3  lea     r13, WPP_GLOBAL_Control
0x18000e5ea  cmp     rcx, r13
0x18000e5ed  jz      short loc_18000E60A
0x18000e5ef  test    byte ptr [rcx+1Ch], 20h
0x18000e5f3  jz      short loc_18000E60A
0x18000e5f5  mov     rcx, [rcx+10h]
0x18000e5f9  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000e600  mov     edx, 17h
0x18000e605  call    WPP_SF_
0x18000e60a  lea     rax, [rbp+hKey]
0x18000e60e  mov     [rbp+Data], 0
0x18000e615  mov     r9d, 20019h; samDesired
0x18000e61b  mov     [rsp+40h+phkResult], rax; phkResult
0x18000e620  xor     r8d, r8d; ulOptions
0x18000e623  mov     dword ptr [r14], 0
0x18000e62a  mov     rdx, rbx; lpSubKey
0x18000e62d  mov     dword ptr [rsi], 0
0x18000e633  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e63a  mov     [rbp+hKey], 0
0x18000e642  call    cs:__imp_RegOpenKeyExW
0x18000e648  mov     ebx, eax
0x18000e64a  test    eax, eax
0x18000e64c  jnz     loc_18000E6FC
0x18000e652  mov     rdi, [rbp+hKey]
0x18000e656  lea     r9, [rbp+Type]; lpType
0x18000e65a  mov     [rbp+Type], eax
0x18000e65d  lea     rdx, ValueName; "AutoSetup"
0x18000e664  lea     rax, [rbp+cbData]
0x18000e668  mov     [rbp+cbData], 4
0x18000e66f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000e674  xor     r8d, r8d; lpReserved
0x18000e677  lea     rax, [rbp+Data]
0x18000e67b  mov     rcx, rdi; hKey
0x18000e67e  mov     [rsp+40h+phkResult], rax; lpData
0x18000e683  call    cs:__imp_RegQueryValueExW
0x18000e689  mov     ebx, eax
0x18000e68b  test    eax, eax
0x18000e68d  jnz     short loc_18000E6EE
0x18000e68f  cmp     [rbp+Type], 4
0x18000e693  jz      short loc_18000E69A
0x18000e695  lea     ebx, [rax+0Dh]
0x18000e698  jmp     short loc_18000E6EE
0x18000e69a  xor     eax, eax
0x18000e69c  mov     [rbp+Type], 0
0x18000e6a3  cmp     [rbp+Data], eax
0x18000e6a6  lea     r9, [rbp+Type]; lpType
0x18000e6aa  lea     rdx, aNetworksizeeve; "NetworkSizeEverDisqualified"
0x18000e6b1  mov     [rbp+cbData], 4
0x18000e6b8  setnz   al
0x18000e6bb  mov     rcx, rdi; hKey
0x18000e6be  mov     [r14], eax
0x18000e6c1  xor     r8d, r8d; lpReserved
0x18000e6c4  lea     rax, [rbp+cbData]
0x18000e6c8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000e6cd  lea     rax, [rbp+Data]
0x18000e6d1  mov     [rsp+40h+phkResult], rax; lpData
0x18000e6d6  call    cs:__imp_RegQueryValueExW
0x18000e6dc  test    eax, eax
0x18000e6de  jnz     short loc_18000E6EC
0x18000e6e0  cmp     [rbp+Type], 4
0x18000e6e4  jnz     short loc_18000E6EC
0x18000e6e6  mov     dword ptr [rsi], 1
0x18000e6ec  xor     ebx, ebx
0x18000e6ee  test    rdi, rdi
0x18000e6f1  jz      short loc_18000E6FE
0x18000e6f3  mov     rcx, rdi; hKey
0x18000e6f6  call    cs:__imp_RegCloseKey
0x18000e6fc  xor     edi, edi
0x18000e6fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e705  cmp     rcx, r13
0x18000e708  jz      short loc_18000E725
0x18000e70a  test    byte ptr [rcx+1Ch], 20h
0x18000e70e  jz      short loc_18000E725
0x18000e710  mov     rcx, [rcx+10h]
0x18000e714  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000e71b  mov     edx, 18h
0x18000e720  call    WPP_SF_
0x18000e725  test    ebx, ebx
0x18000e727  jle     short loc_18000E732
0x18000e729  movzx   ebx, bx
0x18000e72c  or      ebx, 80070000h
0x18000e732  test    rdi, rdi
0x18000e735  jz      short loc_18000E740
0x18000e737  mov     rcx, rdi; hKey
0x18000e73a  call    cs:__imp_RegCloseKey
0x18000e740  mov     eax, ebx
0x18000e742  mov     rbx, [rsp+40h+arg_0]
0x18000e747  add     rsp, 40h
0x18000e74b  pop     r14
0x18000e74d  pop     r13
0x18000e74f  pop     rdi
0x18000e750  pop     rsi
0x18000e751  pop     rbp
0x18000e752  retn
```
