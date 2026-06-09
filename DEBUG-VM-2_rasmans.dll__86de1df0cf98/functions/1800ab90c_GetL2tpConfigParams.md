# GetL2tpConfigParams

- ea: `0x1800ab90c`
- end: `0x1800abb07`
- name: `GetL2tpConfigParams`
- size: `507`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009bdb4`

## callees

- `0x1800a5770`
- `0x1800ab81c`
- `0x1800ab90c`
- `0x1800abb10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab9ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab9ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800abacb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab9ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab9ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800abacb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aba5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aba5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aba85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aba85`

## pseudocode

```c
__int64 __fastcall GetL2tpConfigParams(HKEY hKey, char a2, __int64 a3, DWORD a4)
{
  unsigned int i; // edi
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  __int64 v9; // xmm1_8
  void *v10; // rdi
  HKEY v11; // rcx
  LSTATUS v12; // eax
  void *v13; // rax
  BYTE *lpData; // r14
  HKEY phkResult; // [rsp+30h] [rbp-50h] BYREF
  __int128 v17; // [rsp+38h] [rbp-48h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h]
  LPCWSTR lpValueName; // [rsp+50h] [rbp-30h]
  LPBYTE v20[5]; // [rsp+58h] [rbp-28h]
  DWORD cbData; // [rsp+B8h] [rbp+38h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+48h] BYREF

  Type = a4;
  LOBYTE(cbData) = a2;
  lpValueName = L"idleTimeout";
  v20[0] = (LPBYTE)&v17;
  v20[1] = (LPBYTE)L"saLifeTime";
  v20[2] = (LPBYTE)&v17 + 8;
  v20[3] = (LPBYTE)L"saDataSize";
  v20[4] = (LPBYTE)&v17 + 12;
  v17 = 0;
  v18 = 0;
  for ( i = 0; i < 3; ++i )
  {
    cbData = 4;
    Type = 4;
    v7 = RegQueryValueExW(hKey, (LPCWSTR)v20[2 * i - 1], 0, &Type, v20[2 * i], &cbData);
    if ( v7 )
      return v7;
  }
  cbData = 4;
  Type = 4;
  v8 = RegQueryValueExW(hKey, L"mmSaLifeTime", 0, &Type, (LPBYTE)(a3 + 24), &cbData);
  v7 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
      return v7;
    *(_DWORD *)(a3 + 24) = 28800;
  }
  v9 = v18;
  *(_OWORD *)a3 = v17;
  *(_QWORD *)(a3 + 16) = v9;
  v10 = (void *)MprCommonAlloc(24);
  if ( !v10 )
    return 8;
  v11 = 0;
  phkResult = 0;
  if ( hKey )
  {
    v12 = RegOpenKeyExW(hKey, L"L2TPCustomPolicy", 0, 0x20019u, &phkResult);
    v11 = phkResult;
    v7 = v12;
    if ( !v12 )
    {
      GetCustomPolicyRegParams(phkResult, v10);
      v11 = phkResult;
    }
  }
  else
  {
    v7 = 87;
  }
  if ( v11 )
    RegCloseKey(v11);
  if ( v7 )
  {
    if ( v7 != 2 )
    {
LABEL_22:
      MprCommonFree(v10);
      return v7;
    }
    v13 = 0;
  }
  else
  {
    v13 = v10;
    v10 = 0;
  }
  *(_QWORD *)(a3 + 16) = v13;
  cbData = 4;
  lpData = (BYTE *)(a3 + 4);
  Type = 4;
  v7 = RegQueryValueExW(hKey, L"EncryptionType", 0, &Type, lpData, &cbData);
  if ( v7 == 2 )
  {
    v7 = 0;
    *(_DWORD *)lpData = 1;
  }
  if ( v10 )
    goto LABEL_22;
  return v7;
}

```

## disassembly

```asm
0x1800ab90c  mov     [rsp-28h+arg_0], rbx
0x1800ab911  mov     [rsp-28h+Type], r9d
0x1800ab916  mov     byte ptr [rsp-28h+cbData], dl
0x1800ab91a  push    rbp
0x1800ab91b  push    rsi
0x1800ab91c  push    rdi
0x1800ab91d  push    r14
0x1800ab91f  push    r15
0x1800ab921  mov     rbp, rsp
0x1800ab924  sub     rsp, 80h
0x1800ab92b  lea     rax, aIdletimeout; "idleTimeout"
0x1800ab932  xorps   xmm0, xmm0
0x1800ab935  mov     [rbp+lpValueName], rax
0x1800ab939  mov     r14, r8
0x1800ab93c  lea     rax, [rbp+var_48]
0x1800ab940  mov     rsi, rcx
0x1800ab943  mov     [rbp+var_28], rax
0x1800ab947  lea     rax, aSalifetime; "saLifeTime"
0x1800ab94e  mov     [rbp+var_20], rax
0x1800ab952  lea     rax, [rbp+var_48+8]
0x1800ab956  mov     [rbp+var_18], rax
0x1800ab95a  lea     rax, aSadatasize; "saDataSize"
0x1800ab961  mov     [rbp+var_10], rax
0x1800ab965  lea     rax, [rbp+var_48+0Ch]
0x1800ab969  mov     [rbp+var_8], rax
0x1800ab96d  xor     eax, eax
0x1800ab96f  movups  [rbp+var_48], xmm0
0x1800ab973  mov     [rbp+var_38], rax
0x1800ab977  xor     edi, edi
0x1800ab979  lea     r15d, [rax+4]
0x1800ab97d  lea     rax, [rbp+cbData]
0x1800ab981  mov     edx, edi
0x1800ab983  add     rdx, rdx
0x1800ab986  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800ab98b  lea     r9, [rbp+Type]; lpType
0x1800ab98f  mov     [rbp+cbData], r15d
0x1800ab993  xor     r8d, r8d; lpReserved
0x1800ab996  mov     [rbp+Type], r15d
0x1800ab99a  mov     rcx, rsi; hKey
0x1800ab99d  mov     rax, [rbp+rdx*8+var_28]
0x1800ab9a2  mov     rdx, [rbp+rdx*8+lpValueName]; lpValueName
0x1800ab9a7  mov     [rsp+80h+lpData], rax; lpData
0x1800ab9ac  call    cs:__imp_RegQueryValueExW
0x1800ab9b2  mov     ebx, eax
0x1800ab9b4  test    eax, eax
0x1800ab9b6  jnz     loc_1800ABAEE
0x1800ab9bc  inc     edi
0x1800ab9be  cmp     edi, 3
0x1800ab9c1  jb      short loc_1800AB97D
0x1800ab9c3  lea     rax, [rbp+cbData]
0x1800ab9c7  mov     [rbp+cbData], r15d
0x1800ab9cb  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800ab9d0  lea     rdi, [r14+18h]
0x1800ab9d4  lea     r9, [rbp+Type]; lpType
0x1800ab9d8  mov     [rsp+80h+lpData], rdi; lpData
0x1800ab9dd  xor     r8d, r8d; lpReserved
0x1800ab9e0  mov     [rbp+Type], r15d
0x1800ab9e4  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x1800ab9eb  mov     rcx, rsi; hKey
0x1800ab9ee  call    cs:__imp_RegQueryValueExW
0x1800ab9f4  mov     ebx, eax
0x1800ab9f6  test    eax, eax
0x1800ab9f8  jz      short loc_1800ABA09
0x1800ab9fa  cmp     eax, 2
0x1800ab9fd  jnz     loc_1800ABAEE
0x1800aba03  mov     dword ptr [rdi], 7080h
0x1800aba09  movups  xmm0, [rbp+var_48]
0x1800aba0d  mov     ecx, 18h
0x1800aba12  movsd   xmm1, [rbp+var_38]
0x1800aba17  movups  xmmword ptr [r14], xmm0
0x1800aba1b  movsd   qword ptr [r14+10h], xmm1
0x1800aba21  call    MprCommonAlloc
0x1800aba26  mov     rdi, rax
0x1800aba29  test    rax, rax
0x1800aba2c  jnz     short loc_1800ABA36
0x1800aba2e  lea     ebx, [rax+8]
0x1800aba31  jmp     loc_1800ABAEE
0x1800aba36  xor     ecx, ecx; hKey
0x1800aba38  mov     [rbp+phkResult], rcx
0x1800aba3c  test    rsi, rsi
0x1800aba3f  jz      short loc_1800ABA7B
0x1800aba41  lea     rax, [rbp+phkResult]
0x1800aba45  mov     r9d, 20019h; samDesired
0x1800aba4b  xor     r8d, r8d; ulOptions
0x1800aba4e  mov     [rsp+80h+lpData], rax; phkResult
0x1800aba53  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x1800aba5a  mov     rcx, rsi; hKey
0x1800aba5d  call    cs:__imp_RegOpenKeyExW
0x1800aba63  mov     rcx, [rbp+phkResult]
0x1800aba67  mov     ebx, eax
0x1800aba69  test    eax, eax
0x1800aba6b  jnz     short loc_1800ABA80
0x1800aba6d  mov     rdx, rdi
0x1800aba70  call    GetCustomPolicyRegParams
0x1800aba75  mov     rcx, [rbp+phkResult]
0x1800aba79  jmp     short loc_1800ABA80
0x1800aba7b  mov     ebx, 57h ; 'W'
0x1800aba80  test    rcx, rcx
0x1800aba83  jz      short loc_1800ABA8B
0x1800aba85  call    cs:__imp_RegCloseKey
0x1800aba8b  test    ebx, ebx
0x1800aba8d  jz      short loc_1800ABA98
0x1800aba8f  cmp     ebx, 2
0x1800aba92  jnz     short loc_1800ABAE6
0x1800aba94  xor     eax, eax
0x1800aba96  jmp     short loc_1800ABA9D
0x1800aba98  mov     rax, rdi
0x1800aba9b  xor     edi, edi
0x1800aba9d  mov     [r14+10h], rax
0x1800abaa1  lea     r9, [rbp+Type]; lpType
0x1800abaa5  lea     rax, [rbp+cbData]
0x1800abaa9  mov     [rbp+cbData], r15d
0x1800abaad  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800abab2  lea     rdx, aEncryptiontype; "EncryptionType"
0x1800abab9  add     r14, r15
0x1800ababc  mov     [rbp+Type], r15d
0x1800abac0  xor     r8d, r8d; lpReserved
0x1800abac3  mov     [rsp+80h+lpData], r14; lpData
0x1800abac8  mov     rcx, rsi; hKey
0x1800abacb  call    cs:__imp_RegQueryValueExW
0x1800abad1  mov     ebx, eax
0x1800abad3  cmp     eax, 2
0x1800abad6  jnz     short loc_1800ABAE1
0x1800abad8  xor     ebx, ebx
0x1800abada  mov     dword ptr [r14], 1
0x1800abae1  test    rdi, rdi
0x1800abae4  jz      short loc_1800ABAEE
0x1800abae6  mov     rcx, rdi; lpMem
0x1800abae9  call    MprCommonFree
0x1800abaee  mov     eax, ebx
0x1800abaf0  mov     rbx, [rsp+80h+arg_0]
0x1800abaf8  add     rsp, 80h
0x1800abaff  pop     r15
0x1800abb01  pop     r14
0x1800abb03  pop     rdi
0x1800abb04  pop     rsi
0x1800abb05  pop     rbp
0x1800abb06  retn
```
