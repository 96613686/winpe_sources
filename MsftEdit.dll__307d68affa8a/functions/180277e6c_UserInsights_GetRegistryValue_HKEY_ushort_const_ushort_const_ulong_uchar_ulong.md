# UserInsights::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x180277e6c`
- end: `0x180277f54`
- name: `?GetRegistryValue@UserInsights@@AEAA_NPEAUHKEY__@@PEBG1KPEAEK@Z`
- size: `232`
- prototype: `bool(UserInsights *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180277ce4`
- `0x18027807c`
- `0x18027816c`

## callees

- `0x1800775e8`
- `0x1800ce2c4`
- `0x1800ce404`
- `0x18013bad0`
- `0x180277e6c`
- `0x180277f5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180277ef2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180277ef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180277f27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180277f27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180277f18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180277f18`

## pseudocode

```c
bool __fastcall UserInsights::GetRegistryValue(
        UserInsights *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD Type,
        LPBYTE lpData,
        DWORD cbData)
{
  BYTE *v8; // rsi
  bool v9; // bl
  __int64 v10; // r8
  int v11; // r10d
  int v12; // r11d
  const WCHAR *v13; // rax
  HKEY phkResult; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v17[32]; // [rsp+40h] [rbp-30h] BYREF

  v8 = lpData;
  v9 = 0;
  phkResult = 0;
  hKey = 0;
  std::wstring::wstring(v17, a2, this, a4);
  InsightsRegistryPath(v11, v12, *(_QWORD *)(v10 + 48), (unsigned int)&hKey, (__int64)v17);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  if ( !RegOpenKeyExW(hKey, v13, 0, 0x20019u, &phkResult) )
  {
    v9 = RegQueryValueExW(phkResult, a4, 0, &Type, v8, &cbData) == 0;
    RegCloseKey(phkResult);
  }
  std::wstring::_Tidy_deallocate(v17);
  return v9;
}

```

## disassembly

```asm
0x180277e6c  mov     [rsp-18h+arg_8], rbx
0x180277e71  push    rbp
0x180277e72  push    rsi
0x180277e73  push    rdi
0x180277e74  mov     rbp, rsp
0x180277e77  sub     rsp, 70h
0x180277e7b  mov     rax, cs:__security_cookie
0x180277e82  xor     rax, rsp
0x180277e85  mov     [rbp+var_10], rax
0x180277e89  mov     rdi, r9
0x180277e8c  mov     r11, r8
0x180277e8f  mov     r10, rdx
0x180277e92  mov     r8, rcx
0x180277e95  mov     rsi, [rbp+lpData]
0x180277e99  xor     bl, bl
0x180277e9b  mov     [rbp+var_40], 0
0x180277ea3  mov     [rbp+hKey], 0
0x180277eab  lea     rcx, [rbp+var_30]
0x180277eaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180277eb4  lea     rcx, [rbp+var_30]
0x180277eb8  mov     [rsp+70h+phkResult], rcx
0x180277ebd  lea     r9, [rbp+hKey]
0x180277ec1  mov     r8, [r8+30h]
0x180277ec5  mov     rdx, r11
0x180277ec8  mov     rcx, r10
0x180277ecb  call    InsightsRegistryPath
0x180277ed0  lea     rcx, [rbp+var_30]
0x180277ed4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180277ed9  mov     rdx, rax; lpSubKey
0x180277edc  lea     rax, [rbp+var_40]
0x180277ee0  mov     [rsp+70h+phkResult], rax; phkResult
0x180277ee5  mov     r9d, 20019h; samDesired
0x180277eeb  xor     r8d, r8d; ulOptions
0x180277eee  mov     rcx, [rbp+hKey]; hKey
0x180277ef2  call    cs:__imp_RegOpenKeyExW
0x180277ef8  test    eax, eax
0x180277efa  jnz     short loc_180277F2D
0x180277efc  lea     rax, [rbp+cbData]
0x180277f00  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180277f05  mov     [rsp+70h+phkResult], rsi; lpData
0x180277f0a  lea     r9, [rbp+Type]; lpType
0x180277f0e  xor     r8d, r8d; lpReserved
0x180277f11  mov     rdx, rdi; lpValueName
0x180277f14  mov     rcx, [rbp+var_40]; hKey
0x180277f18  call    cs:__imp_RegQueryValueExW
0x180277f1e  test    eax, eax
0x180277f20  setz    bl
0x180277f23  mov     rcx, [rbp+var_40]; hKey
0x180277f27  call    cs:__imp_RegCloseKey
0x180277f2d  lea     rcx, [rbp+var_30]
0x180277f31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180277f36  mov     al, bl
0x180277f38  mov     rcx, [rbp+var_10]
0x180277f3c  xor     rcx, rsp; StackCookie
0x180277f3f  call    __security_check_cookie
0x180277f44  mov     rbx, [rsp+70h+arg_8]
0x180277f4c  add     rsp, 70h
0x180277f50  pop     rdi
0x180277f51  pop     rsi
0x180277f52  pop     rbp
0x180277f53  retn
```
