# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::DoesGroupConfigExistInStore(void)

- ea: `0x18000c020`
- end: `0x18000c1a3`
- name: `?DoesGroupConfigExistInStore@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@EEAA_NXZ`
- size: `387`
- prototype: `bool __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008ec8`
- `0x18000c020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c16c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c073`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c16c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c0b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c0b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c09d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c0da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c0da`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c122`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c0a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c17b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c0a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c17b`

## string_xrefs

- `0x18000c04b`: `GroupConfigs`

## pseudocode

```c
bool __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::DoesGroupConfigExistInStore(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this)
{
  bool v1; // si
  HKEY v2; // rdi
  DWORD LastError; // ebx
  void *v4; // rdi
  LSTATUS v5; // eax
  signed int v6; // ebx
  bool v7; // cc
  bool result; // al
  LPVOID pv[4]; // [rsp+60h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+28h] BYREF

  hKey = 0;
  memset(pv, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              pv,
              L"%s\\%s",
              *((_QWORD *)this + 1),
              L"GroupConfigs") >= 0 )
  {
    v1 = 0;
    v2 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v2);
      SetLastError(LastError);
    }
    hKey = 0;
    v4 = pv[0];
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)pv[0], 0, 0x20019u, &hKey);
    v6 = v5;
    v7 = v5 <= 0;
    if ( v5
      || (cSubKeys = 0, v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0), v6 = v5, v7 = v5 <= 0, v5) )
    {
      if ( !v7 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( v4 )
        CoTaskMemFree(v4);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v6 < 0 )
        return 0;
    }
    else
    {
      v1 = cSubKeys != 0;
      if ( v4 )
        CoTaskMemFree(v4);
      if ( hKey )
        RegCloseKey(hKey);
    }
    result = 1;
    if ( v1 )
      return result;
    return 0;
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18000c020  mov     [rsp-18h+arg_10], rbx
0x18000c025  mov     [rsp-18h+arg_18], rsi
0x18000c02a  push    rbp
0x18000c02b  push    rdi
0x18000c02c  push    r14
0x18000c02e  mov     rbp, rsp
0x18000c031  sub     rsp, 80h
0x18000c038  xor     r14d, r14d
0x18000c03b  mov     [rbp+hKey], r14
0x18000c03f  mov     [rbp+pv], r14
0x18000c043  mov     [rbp+var_18], r14
0x18000c047  mov     [rbp+var_10], r14
0x18000c04b  lea     r9, aGroupconfigs; "GroupConfigs"
0x18000c052  mov     r8, [rcx+8]
0x18000c056  lea     rdx, aSS; "%s\\%s"
0x18000c05d  lea     rcx, [rbp+pv]
0x18000c061  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000c066  test    eax, eax
0x18000c068  jns     short loc_18000C091
0x18000c06a  mov     rcx, [rbp+pv]; pv
0x18000c06e  test    rcx, rcx
0x18000c071  jz      short loc_18000C079
0x18000c073  call    cs:__imp_CoTaskMemFree
0x18000c079  mov     rcx, [rbp+hKey]; hKey
0x18000c07d  test    rcx, rcx
0x18000c080  jz      loc_18000C188
0x18000c086  call    cs:__imp_RegCloseKey
0x18000c08c  jmp     loc_18000C188
0x18000c091  mov     sil, r14b
0x18000c094  mov     rdi, [rbp+hKey]
0x18000c098  test    rdi, rdi
0x18000c09b  jz      short loc_18000C0B6
0x18000c09d  call    cs:__imp_GetLastError
0x18000c0a3  mov     ebx, eax
0x18000c0a5  mov     rcx, rdi; hKey
0x18000c0a8  call    cs:__imp_RegCloseKey
0x18000c0ae  mov     ecx, ebx; dwErrCode
0x18000c0b0  call    cs:__imp_SetLastError
0x18000c0b6  mov     [rbp+hKey], r14
0x18000c0ba  lea     rax, [rbp+hKey]
0x18000c0be  mov     [rsp+80h+phkResult], rax; phkResult
0x18000c0c3  mov     r9d, 20019h; samDesired
0x18000c0c9  xor     r8d, r8d; ulOptions
0x18000c0cc  mov     rdi, [rbp+pv]
0x18000c0d0  mov     rdx, rdi; lpSubKey
0x18000c0d3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c0da  call    cs:__imp_RegOpenKeyExW
0x18000c0e0  mov     ebx, eax
0x18000c0e2  test    eax, eax
0x18000c0e4  jnz     short loc_18000C12E
0x18000c0e6  mov     [rbp+cSubKeys], r14d
0x18000c0ea  mov     [rsp+80h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000c0ef  mov     [rsp+80h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000c0f4  mov     [rsp+80h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18000c0f9  mov     [rsp+80h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18000c0fe  mov     [rsp+80h+lpcValues], r14; lpcValues
0x18000c103  mov     [rsp+80h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18000c108  mov     [rsp+80h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18000c10d  lea     rax, [rbp+cSubKeys]
0x18000c111  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18000c116  xor     r9d, r9d; lpReserved
0x18000c119  xor     r8d, r8d; lpcchClass
0x18000c11c  xor     edx, edx; lpClass
0x18000c11e  mov     rcx, [rbp+hKey]; hKey
0x18000c122  call    cs:__imp_RegQueryInfoKeyW
0x18000c128  mov     ebx, eax
0x18000c12a  test    eax, eax
0x18000c12c  jz      short loc_18000C15C
0x18000c12e  jle     short loc_18000C139
0x18000c130  movzx   ebx, ax
0x18000c133  or      ebx, 80070000h
0x18000c139  test    rdi, rdi
0x18000c13c  jz      short loc_18000C147
0x18000c13e  mov     rcx, rdi; pv
0x18000c141  call    cs:__imp_CoTaskMemFree
0x18000c147  mov     rcx, [rbp+hKey]; hKey
0x18000c14b  test    rcx, rcx
0x18000c14e  jz      short loc_18000C156
0x18000c150  call    cs:__imp_RegCloseKey
0x18000c156  test    ebx, ebx
0x18000c158  js      short loc_18000C188
0x18000c15a  jmp     short loc_18000C181
0x18000c15c  cmp     [rbp+cSubKeys], r14d
0x18000c160  setnz   sil
0x18000c164  test    rdi, rdi
0x18000c167  jz      short loc_18000C172
0x18000c169  mov     rcx, rdi; pv
0x18000c16c  call    cs:__imp_CoTaskMemFree
0x18000c172  mov     rcx, [rbp+hKey]; hKey
0x18000c176  test    rcx, rcx
0x18000c179  jz      short loc_18000C181
0x18000c17b  call    cs:__imp_RegCloseKey
0x18000c181  test    sil, sil
0x18000c184  mov     al, 1
0x18000c186  jnz     short loc_18000C18B
0x18000c188  mov     al, r14b
0x18000c18b  lea     r11, [rsp+80h+var_s0]
0x18000c193  mov     rbx, [r11+30h]
0x18000c197  mov     rsi, [r11+38h]
0x18000c19b  mov     rsp, r11
0x18000c19e  pop     r14
0x18000c1a0  pop     rdi
0x18000c1a1  pop     rbp
0x18000c1a2  retn
```
