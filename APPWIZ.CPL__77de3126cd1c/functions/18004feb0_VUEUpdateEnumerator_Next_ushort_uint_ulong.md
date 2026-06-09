# VUEUpdateEnumerator::Next(ushort *,uint,ulong *)

- ea: `0x18004feb0`
- end: `0x180050072`
- name: `?Next@VUEUpdateEnumerator@@QEAAJPEAGIPEAK@Z`
- size: `450`
- prototype: `int(VUEUpdateEnumerator *__hidden this, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012910`
- `0x1800185b4`

## callees

- `0x18004feb0`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ff3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004ff3a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ff7d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ffca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ff7d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004ffca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005003a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005003a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fff7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180050027`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004fff7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180050027`
- `ADVAPI32!RegEnumKeyW` at `0x18004fefd`
- `ADVAPI32!RegEnumKeyW` at `0x18004fefd`

## pseudocode

```c
__int64 __fastcall VUEUpdateEnumerator::Next(HKEY *this, unsigned __int16 *a2, __int64 a3, unsigned int *a4)
{
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  HKEY v10; // rcx
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v14; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR String1[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+260h] [rbp+160h] BYREF

  v7 = -2147467259;
  v8 = RegEnumKeyW(this[1], *(_DWORD *)this, Name, 0x104u);
  if ( v8 )
  {
    if ( v8 == 259 )
      return 1;
  }
  else
  {
    v9 = this[1];
    ++*(_DWORD *)this;
    hkey = 0;
    if ( !RegOpenKeyExW(v9, Name, 0, 0x20019u, &hkey) )
    {
      pcbData = 520;
      if ( !RegGetValueW(hkey, 0, L"Identifier", 2u, 0, a2, &pcbData) )
      {
        v7 = 0;
        if ( a4 )
        {
          v10 = hkey;
          *a4 = 0;
          v14 = 520;
          if ( !RegGetValueW(v10, 0, L"Type", 2u, 0, String1, &v14) )
          {
            if ( CompareStringW(0x7Fu, 1u, String1, -1, L"PACKAGE_TYPE_CBS", 17) == 2 )
            {
              *a4 = 1;
            }
            else if ( CompareStringW(0x7Fu, 1u, String1, -1, L"PACKAGE_TYPE_MSP", 17) == 2 )
            {
              *a4 = 2;
            }
          }
        }
      }
      RegCloseKey(hkey);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18004feb0  mov     [rsp-8+arg_10], rbx
0x18004feb5  push    rbp
0x18004feb6  push    rsi
0x18004feb7  push    rdi
0x18004feb8  push    r14
0x18004feba  push    r15
0x18004febc  lea     rbp, [rsp-380h]
0x18004fec4  sub     rsp, 480h
0x18004fecb  mov     rax, cs:__security_cookie
0x18004fed2  xor     rax, rsp
0x18004fed5  mov     [rbp+3A0h+var_30], rax
0x18004fedc  mov     r15, rdx
0x18004fedf  lea     r8, [rbp+3A0h+Name]; lpName
0x18004fee6  mov     edx, [rcx]; dwIndex
0x18004fee8  mov     rsi, r9
0x18004feeb  mov     r14, rcx
0x18004feee  mov     r9d, 104h; cchName
0x18004fef4  mov     rcx, [rcx+8]; hKey
0x18004fef8  mov     ebx, 80004005h
0x18004fefd  call    cs:__imp_RegEnumKeyW
0x18004ff03  mov     edi, 1
0x18004ff08  test    eax, eax
0x18004ff0a  jnz     loc_180050042
0x18004ff10  mov     rcx, [r14+8]; hKey
0x18004ff14  lea     rax, [rsp+4A0h+hkey]
0x18004ff19  add     [r14], edi
0x18004ff1c  lea     rdx, [rbp+3A0h+Name]; lpSubKey
0x18004ff23  mov     r9d, 20019h; samDesired
0x18004ff29  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18004ff2e  xor     r8d, r8d; ulOptions
0x18004ff31  mov     [rsp+4A0h+hkey], 0
0x18004ff3a  call    cs:__imp_RegOpenKeyExW
0x18004ff40  test    eax, eax
0x18004ff42  jnz     loc_18005004A
0x18004ff48  mov     rcx, [rsp+4A0h+hkey]; hkey
0x18004ff4d  lea     rax, [rsp+4A0h+var_458]
0x18004ff52  mov     [rsp+4A0h+pcbData], rax; pcbData
0x18004ff57  lea     r14d, [rdi+1]
0x18004ff5b  mov     [rsp+4A0h+pvData], r15; pvData
0x18004ff60  lea     r8, aIdentifier; "Identifier"
0x18004ff67  mov     r9d, r14d; dwFlags
0x18004ff6a  mov     [rsp+4A0h+phkResult], 0; pdwType
0x18004ff73  xor     edx, edx; lpSubKey
0x18004ff75  mov     [rsp+4A0h+var_458], 208h
0x18004ff7d  call    cs:__imp_RegGetValueW
0x18004ff83  test    eax, eax
0x18004ff85  jnz     loc_180050035
0x18004ff8b  xor     ebx, ebx
0x18004ff8d  test    rsi, rsi
0x18004ff90  jz      loc_180050035
0x18004ff96  mov     rcx, [rsp+4A0h+hkey]; hkey
0x18004ff9b  lea     rax, [rsp+4A0h+var_454]
0x18004ffa0  mov     [rsp+4A0h+pcbData], rax; pcbData
0x18004ffa5  lea     r8, aType; "Type"
0x18004ffac  lea     rax, [rsp+4A0h+String1]
0x18004ffb1  mov     [rsi], ebx
0x18004ffb3  mov     [rsp+4A0h+pvData], rax; pvData
0x18004ffb8  mov     r9d, r14d; dwFlags
0x18004ffbb  xor     edx, edx; lpSubKey
0x18004ffbd  mov     [rsp+4A0h+phkResult], rbx; pdwType
0x18004ffc2  mov     [rsp+4A0h+var_454], 208h
0x18004ffca  call    cs:__imp_RegGetValueW
0x18004ffd0  test    eax, eax
0x18004ffd2  jnz     short loc_180050035
0x18004ffd4  lea     rax, aPackageTypeCbs; "PACKAGE_TYPE_CBS"
0x18004ffdb  or      r9d, 0FFFFFFFFh; cchCount1
0x18004ffdf  lea     r15d, [rdi+10h]
0x18004ffe3  mov     edx, edi; dwCmpFlags
0x18004ffe5  mov     dword ptr [rsp+4A0h+pvData], r15d; cchCount2
0x18004ffea  lea     r8, [rsp+4A0h+String1]; lpString1
0x18004ffef  lea     ecx, [rdi+7Eh]; Locale
0x18004fff2  mov     [rsp+4A0h+phkResult], rax; lpString2
0x18004fff7  call    cs:__imp_CompareStringW
0x18004fffd  cmp     eax, r14d
0x180050000  jnz     short loc_180050006
0x180050002  mov     [rsi], edi
0x180050004  jmp     short loc_180050035
0x180050006  lea     rax, aPackageTypeMsp; "PACKAGE_TYPE_MSP"
0x18005000d  mov     dword ptr [rsp+4A0h+pvData], r15d; cchCount2
0x180050012  or      r9d, 0FFFFFFFFh; cchCount1
0x180050016  mov     [rsp+4A0h+phkResult], rax; lpString2
0x18005001b  lea     r8, [rsp+4A0h+String1]; lpString1
0x180050020  mov     edx, edi; dwCmpFlags
0x180050022  mov     ecx, 7Fh; Locale
0x180050027  call    cs:__imp_CompareStringW
0x18005002d  cmp     eax, r14d
0x180050030  jnz     short loc_180050035
0x180050032  mov     [rsi], r14d
0x180050035  mov     rcx, [rsp+4A0h+hkey]; hKey
0x18005003a  call    cs:__imp_RegCloseKey
0x180050040  jmp     short loc_18005004A
0x180050042  cmp     eax, 103h
0x180050047  cmovz   ebx, edi
0x18005004a  mov     eax, ebx
0x18005004c  mov     rcx, [rbp+3A0h+var_30]
0x180050053  xor     rcx, rsp; StackCookie
0x180050056  call    __security_check_cookie
0x18005005b  mov     rbx, [rsp+4A0h+arg_10]
0x180050063  add     rsp, 480h
0x18005006a  pop     r15
0x18005006c  pop     r14
0x18005006e  pop     rdi
0x18005006f  pop     rsi
0x180050070  pop     rbp
0x180050071  retn
```
