# SetFeatureV3Status(__int64)

- ea: `0x14000ec00`
- end: `0x14000ecea`
- name: `?SetFeatureV3Status@@YAX_J@Z`
- size: `234`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000e590`

## callees

- `0x14000a390`
- `0x14000ec00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000ec43`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ec43`
- `ADVAPI32!RegCloseKey` at `0x14000ecd2`
- `ADVAPI32!RegCloseKey` at `0x14000ecd2`
- `ADVAPI32!RegQueryValueExW` at `0x14000ec83`
- `ADVAPI32!RegQueryValueExW` at `0x14000ec83`
- `ADVAPI32!RegSetValueExW` at `0x14000ecc8`
- `ADVAPI32!RegSetValueExW` at `0x14000ecc8`

## string_xrefs

- `0x14000ec3c`: `SYSTEM\CurrentControlSet\Services\UCPD`

## pseudocode

```c
void __fastcall SetFeatureV3Status(__int64 a1)
{
  LSTATUS v1; // eax
  bool v2; // zf
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  BYTE v4[8]; // [rsp+38h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-18h] BYREF

  *(_QWORD *)v4 = a1;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\UCPD", 0, 0x2001Fu, &hKey) )
  {
    *(_QWORD *)Data = 0;
    cbData = 8;
    v1 = RegQueryValueExW(hKey, L"FeatureV3", 0, 0, Data, &cbData);
    if ( v1 )
    {
      if ( v1 != 2 )
      {
LABEL_8:
        RegCloseKey(hKey);
        return;
      }
      v2 = *(_QWORD *)v4 == 0;
    }
    else
    {
      v2 = *(_QWORD *)Data == *(_QWORD *)v4;
    }
    if ( !v2 )
      RegSetValueExW(hKey, L"FeatureV3", 0, 0xBu, v4, 8u);
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x14000ec00  push    rbp
0x14000ec02  mov     rbp, rsp
0x14000ec05  sub     rsp, 60h
0x14000ec09  mov     rax, cs:__security_cookie
0x14000ec10  xor     rax, rsp
0x14000ec13  mov     [rbp+var_10], rax
0x14000ec17  mov     qword ptr [rbp+var_28], rcx
0x14000ec1b  lea     rax, [rbp+hKey]
0x14000ec1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ec26  mov     [rsp+60h+phkResult], rax; phkResult
0x14000ec2b  mov     r9d, 2001Fh; samDesired
0x14000ec31  mov     [rbp+hKey], 0
0x14000ec39  xor     r8d, r8d; ulOptions
0x14000ec3c  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\UC"...
0x14000ec43  call    cs:__imp_RegOpenKeyExW
0x14000ec49  test    eax, eax
0x14000ec4b  jnz     loc_14000ECD8
0x14000ec51  mov     rcx, [rbp+hKey]; hKey
0x14000ec55  lea     rax, [rbp+cbData]
0x14000ec59  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14000ec5e  lea     rdx, aFeaturev3; "FeatureV3"
0x14000ec65  lea     rax, [rbp+Data]
0x14000ec69  mov     qword ptr [rbp+Data], 0
0x14000ec71  xor     r9d, r9d; lpType
0x14000ec74  mov     [rsp+60h+phkResult], rax; lpData
0x14000ec79  xor     r8d, r8d; lpReserved
0x14000ec7c  mov     [rbp+cbData], 8
0x14000ec83  call    cs:__imp_RegQueryValueExW
0x14000ec89  test    eax, eax
0x14000ec8b  jnz     short loc_14000EC97
0x14000ec8d  mov     rax, qword ptr [rbp+var_28]
0x14000ec91  cmp     qword ptr [rbp+Data], rax
0x14000ec95  jmp     short loc_14000ECA1
0x14000ec97  cmp     eax, 2
0x14000ec9a  jnz     short loc_14000ECCE
0x14000ec9c  cmp     qword ptr [rbp+var_28], 0
0x14000eca1  jz      short loc_14000ECCE
0x14000eca3  mov     rcx, [rbp+hKey]; hKey
0x14000eca7  lea     rax, [rbp+var_28]
0x14000ecab  mov     dword ptr [rsp+60h+lpcbData], 8; cbData
0x14000ecb3  lea     rdx, aFeaturev3; "FeatureV3"
0x14000ecba  mov     r9d, 0Bh; dwType
0x14000ecc0  mov     [rsp+60h+phkResult], rax; lpData
0x14000ecc5  xor     r8d, r8d; Reserved
0x14000ecc8  call    cs:__imp_RegSetValueExW
0x14000ecce  mov     rcx, [rbp+hKey]; hKey
0x14000ecd2  call    cs:__imp_RegCloseKey
0x14000ecd8  mov     rcx, [rbp+var_10]
0x14000ecdc  xor     rcx, rsp; StackCookie
0x14000ecdf  call    __security_check_cookie
0x14000ece4  add     rsp, 60h
0x14000ece8  pop     rbp
0x14000ece9  retn
```
