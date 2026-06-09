# GetNetworkSizeFromRegistry(ushort const *,ulong &,_ULARGE_INTEGER *)

- ea: `0x18000e75c`
- end: `0x18000e8c6`
- name: `?GetNetworkSizeFromRegistry@@YAJPEBGAEAKPEAT_ULARGE_INTEGER@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPBYTE lpData, LPBYTE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010120`

## callees

- `0x18000a644`
- `0x18000e75c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e80b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e848`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e80b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000e848`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e7ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e86d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e86d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8b1`

## pseudocode

```c
__int64 __fastcall GetNetworkSizeFromRegistry(LPCWSTR lpSubKey, LPBYTE lpData, LPBYTE a3)
{
  LSTATUS v6; // ebx
  HKEY v7; // rdi
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD Type; // [rsp+98h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  lpcbData = 8;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( !v6 )
  {
    v7 = hKey;
    Type = 0;
    cbData = 4;
    v6 = RegQueryValueExW(hKey, L"NetworkSize", 0, &Type, lpData, &cbData);
    if ( !v6 )
    {
      if ( Type == 4 )
      {
        Type = 0;
        v6 = RegQueryValueExW(v7, L"NetworkSizeTimestamp", 0, &Type, a3, &lpcbData);
        if ( !v6 )
          v6 = Type != 3 ? 0xD : 0;
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e75c  push    rbp
0x18000e75e  push    rbx
0x18000e75f  push    rsi
0x18000e760  push    rdi
0x18000e761  push    r12
0x18000e763  push    r14
0x18000e765  mov     rbp, rsp
0x18000e768  sub     rsp, 48h
0x18000e76c  mov     r14, r8
0x18000e76f  mov     rsi, rdx
0x18000e772  mov     rbx, rcx
0x18000e775  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e77c  lea     r12, WPP_GLOBAL_Control
0x18000e783  cmp     rcx, r12
0x18000e786  jz      short loc_18000E7A3
0x18000e788  test    byte ptr [rcx+1Ch], 20h
0x18000e78c  jz      short loc_18000E7A3
0x18000e78e  mov     rcx, [rcx+10h]
0x18000e792  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000e799  mov     edx, 1Bh
0x18000e79e  call    WPP_SF_
0x18000e7a3  lea     rax, [rbp+hKey]
0x18000e7a7  mov     [rbp+var_14], 8
0x18000e7ae  mov     r9d, 20019h; samDesired
0x18000e7b4  mov     [rsp+48h+phkResult], rax; phkResult
0x18000e7b9  xor     r8d, r8d; ulOptions
0x18000e7bc  mov     [rbp+hKey], 0
0x18000e7c4  mov     rdx, rbx; lpSubKey
0x18000e7c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e7ce  call    cs:__imp_RegOpenKeyExW
0x18000e7d4  mov     ebx, eax
0x18000e7d6  test    eax, eax
0x18000e7d8  jnz     loc_18000E873
0x18000e7de  mov     rdi, [rbp+hKey]
0x18000e7e2  lea     r9, [rbp+Type]; lpType
0x18000e7e6  mov     [rbp+Type], eax
0x18000e7e9  lea     rdx, aNetworksize; "NetworkSize"
0x18000e7f0  lea     rax, [rbp+cbData]
0x18000e7f4  mov     [rbp+cbData], 4
0x18000e7fb  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000e800  xor     r8d, r8d; lpReserved
0x18000e803  mov     rcx, rdi; hKey
0x18000e806  mov     [rsp+48h+phkResult], rsi; lpData
0x18000e80b  call    cs:__imp_RegQueryValueExW
0x18000e811  mov     ebx, eax
0x18000e813  test    eax, eax
0x18000e815  jnz     short loc_18000E865
0x18000e817  cmp     [rbp+Type], 4
0x18000e81b  jz      short loc_18000E822
0x18000e81d  lea     ebx, [rax+0Dh]
0x18000e820  jmp     short loc_18000E865
0x18000e822  lea     rax, [rbp+var_14]
0x18000e826  mov     [rbp+Type], 0
0x18000e82d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000e832  lea     r9, [rbp+Type]; lpType
0x18000e836  xor     r8d, r8d; lpReserved
0x18000e839  mov     [rsp+48h+phkResult], r14; lpData
0x18000e83e  lea     rdx, aNetworksizetim; "NetworkSizeTimestamp"
0x18000e845  mov     rcx, rdi; hKey
0x18000e848  call    cs:__imp_RegQueryValueExW
0x18000e84e  mov     ebx, eax
0x18000e850  test    eax, eax
0x18000e852  jnz     short loc_18000E865
0x18000e854  mov     eax, [rbp+Type]
0x18000e857  mov     ebx, 0Dh
0x18000e85c  sub     eax, 3
0x18000e85f  neg     eax
0x18000e861  sbb     eax, eax
0x18000e863  and     ebx, eax
0x18000e865  test    rdi, rdi
0x18000e868  jz      short loc_18000E875
0x18000e86a  mov     rcx, rdi; hKey
0x18000e86d  call    cs:__imp_RegCloseKey
0x18000e873  xor     edi, edi
0x18000e875  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e87c  cmp     rcx, r12
0x18000e87f  jz      short loc_18000E89C
0x18000e881  test    byte ptr [rcx+1Ch], 20h
0x18000e885  jz      short loc_18000E89C
0x18000e887  mov     rcx, [rcx+10h]
0x18000e88b  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000e892  mov     edx, 1Ch
0x18000e897  call    WPP_SF_
0x18000e89c  test    ebx, ebx
0x18000e89e  jle     short loc_18000E8A9
0x18000e8a0  movzx   ebx, bx
0x18000e8a3  or      ebx, 80070000h
0x18000e8a9  test    rdi, rdi
0x18000e8ac  jz      short loc_18000E8B7
0x18000e8ae  mov     rcx, rdi; hKey
0x18000e8b1  call    cs:__imp_RegCloseKey
0x18000e8b7  mov     eax, ebx
0x18000e8b9  add     rsp, 48h
0x18000e8bd  pop     r14
0x18000e8bf  pop     r12
0x18000e8c1  pop     rdi
0x18000e8c2  pop     rsi
0x18000e8c3  pop     rbx
0x18000e8c4  pop     rbp
0x18000e8c5  retn
```
