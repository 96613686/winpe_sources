# RegReadDefValue(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180099a20`
- end: `0x180099af9`
- name: `?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `217`
- prototype: `int __fastcall(HKEY__ *hKey, const wchar_t *pszKey, wchar_t **ppszValue)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180099274`

## callees

- `0x180099a20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099ade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099ade`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099a56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099a56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099a7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099abd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099a7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180099abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099a8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099acc`

## pseudocode

```c
__int64 __fastcall RegReadDefValue(HKEY hKey, const wchar_t *pszKey, wchar_t **ppszValue)
{
  unsigned __int8 *v4; // rbx
  unsigned int v5; // edi
  unsigned int dw; // [rsp+50h] [rbp+18h] BYREF
  HKEY__ *hSubKey; // [rsp+58h] [rbp+20h] BYREF

  hSubKey = 0;
  dw = 0;
  v4 = 0;
  v5 = RegOpenKeyExW(hKey, pszKey, 0, 0x20019u, &hSubKey);
  if ( !v5 )
  {
    v5 = RegQueryValueExW(hSubKey, 0, 0, 0, 0, &dw);
    if ( !v5 )
    {
      v4 = (unsigned __int8 *)CoTaskMemAlloc(dw);
      if ( v4 )
      {
        v5 = RegQueryValueExW(hSubKey, 0, 0, 0, v4, &dw);
        if ( v5 )
        {
          CoTaskMemFree(v4);
          v4 = 0;
        }
      }
      else
      {
        v5 = 14;
      }
    }
  }
  if ( hSubKey )
    RegCloseKey(hSubKey);
  *ppszValue = (wchar_t *)v4;
  return v5;
}

```

## disassembly

```asm
0x180099a20  mov     rax, rsp
0x180099a23  mov     [rax+8], rbx
0x180099a27  mov     [rax+10h], rsi
0x180099a2b  push    rdi
0x180099a2c  sub     rsp, 30h
0x180099a30  mov     qword ptr [rax+20h], 0
0x180099a38  mov     rsi, ppszValue
0x180099a3b  mov     dword ptr [rax+18h], 0
0x180099a42  lea     rax, [rax+20h]
0x180099a46  mov     r9d, 20019h; samDesired
0x180099a4c  mov     [rsp+38h+phkResult], rax; phkResult
0x180099a51  xor     r8d, r8d; ulOptions
0x180099a54  xor     ebx, ebx
0x180099a56  call    cs:__imp_RegOpenKeyExW
0x180099a5c  mov     edi, eax
0x180099a5e  test    eax, eax
0x180099a60  jnz     short loc_180099AD4
0x180099a62  mov     hKey, [rsp+38h+hSubKey]; hKey
0x180099a67  lea     rax, [rsp+38h+dw]
0x180099a6c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180099a71  xor     r9d, r9d; lpType
0x180099a74  xor     r8d, r8d; lpReserved
0x180099a77  mov     [rsp+38h+phkResult], rbx; lpData
0x180099a7c  xor     edx, edx; lpValueName
0x180099a7e  call    cs:__imp_RegQueryValueExW
0x180099a84  mov     edi, eax
0x180099a86  test    eax, eax
0x180099a88  jnz     short loc_180099AD4
0x180099a8a  mov     ecx, [rsp+38h+dw]; cb
0x180099a8e  call    cs:__imp_CoTaskMemAlloc
0x180099a94  mov     rbx, rax
0x180099a97  test    rax, rax
0x180099a9a  jnz     short loc_180099AA1
0x180099a9c  lea     edi, [rax+0Eh]
0x180099a9f  jmp     short loc_180099AD4
0x180099aa1  mov     hKey, [rsp+38h+hSubKey]; hKey
0x180099aa6  lea     rax, [rsp+38h+dw]
0x180099aab  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180099ab0  xor     r9d, r9d; lpType
0x180099ab3  xor     r8d, r8d; lpReserved
0x180099ab6  mov     [rsp+38h+phkResult], rbx; lpData
0x180099abb  xor     edx, edx; lpValueName
0x180099abd  call    cs:__imp_RegQueryValueExW
0x180099ac3  mov     edi, eax
0x180099ac5  test    eax, eax
0x180099ac7  jz      short loc_180099AD4
0x180099ac9  mov     hKey, rbx; pv
0x180099acc  call    cs:__imp_CoTaskMemFree
0x180099ad2  xor     ebx, ebx
0x180099ad4  mov     hKey, [rsp+38h+hSubKey]; hKey
0x180099ad9  test    hKey, hKey
0x180099adc  jz      short loc_180099AE4
0x180099ade  call    cs:__imp_RegCloseKey
0x180099ae4  mov     [rsi], rbx
0x180099ae7  mov     eax, edi
0x180099ae9  mov     rbx, [rsp+38h+arg_0]
0x180099aee  mov     rsi, [rsp+38h+arg_8]
0x180099af3  add     rsp, 30h
0x180099af7  pop     rdi
0x180099af8  retn
```
