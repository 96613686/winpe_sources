# RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)

- ea: `0x180011ef0`
- end: `0x180011f9a`
- name: `?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003824`
- `0x180018790`
- `0x18003bbdc`
- `0x18003e3e8`
- `0x180046c18`
- `0x180056788`
- `0x18005b3a8`

## callees

- `0x180011cb8`
- `0x180011e60`
- `0x180011ef0`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011f4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f7d`

## pseudocode

```c
__int64 __fastcall RegQueryDwordValueWithDefaultAndRangeCheck(
        __int64 a1,
        const WCHAR *a2,
        const wchar_t *a3,
        REGSAM a4)
{
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  REGSAM samDesired; // [rsp+38h] [rbp-30h] BYREF

  samDesired = 1;
  if ( (int)SetRegistryType(a1, &samDesired) >= 0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey) )
    {
      samDesired = a4;
      if ( hKey && RegQueryDwordValue(hKey, a3, &samDesired) >= 0 )
        a4 = samDesired;
      RegCloseKey(hKey);
    }
  }
  return a4;
}

```

## disassembly

```asm
0x180011ef0  push    rbx
0x180011ef2  push    rsi
0x180011ef3  push    rdi
0x180011ef4  sub     rsp, 50h
0x180011ef8  mov     rax, cs:__security_cookie
0x180011eff  xor     rax, rsp
0x180011f02  mov     [rsp+68h+var_28], rax
0x180011f07  mov     rsi, rdx
0x180011f0a  mov     [rsp+68h+samDesired], 1
0x180011f12  lea     rdx, [rsp+68h+samDesired]
0x180011f17  mov     ebx, r9d
0x180011f1a  mov     rdi, r8
0x180011f1d  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180011f22  test    eax, eax
0x180011f24  js      short loc_180011F83
0x180011f26  mov     r9d, [rsp+68h+samDesired]; samDesired
0x180011f2b  lea     rax, [rsp+68h+hKey]
0x180011f30  xor     r8d, r8d; ulOptions
0x180011f33  mov     [rsp+68h+phkResult], rax; phkResult
0x180011f38  mov     rdx, rsi; lpSubKey
0x180011f3b  mov     [rsp+68h+hKey], 0
0x180011f44  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011f4b  call    cs:__imp_RegOpenKeyExW
0x180011f51  test    eax, eax
0x180011f53  jnz     short loc_180011F83
0x180011f55  mov     rcx, [rsp+68h+hKey]; HKEY
0x180011f5a  mov     [rsp+68h+samDesired], ebx
0x180011f5e  test    rcx, rcx
0x180011f61  jz      short loc_180011F78
0x180011f63  lea     r8, [rsp+68h+samDesired]; unsigned int *
0x180011f68  mov     rdx, rdi; wchar_t *
0x180011f6b  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x180011f70  test    eax, eax
0x180011f72  js      short loc_180011F78
0x180011f74  mov     ebx, [rsp+68h+samDesired]
0x180011f78  mov     rcx, [rsp+68h+hKey]; hKey
0x180011f7d  call    cs:__imp_RegCloseKey
0x180011f83  mov     eax, ebx
0x180011f85  mov     rcx, [rsp+68h+var_28]
0x180011f8a  xor     rcx, rsp; StackCookie
0x180011f8d  call    __security_check_cookie
0x180011f92  add     rsp, 50h
0x180011f96  pop     rdi
0x180011f97  pop     rsi
0x180011f98  pop     rbx
0x180011f99  retn
```
