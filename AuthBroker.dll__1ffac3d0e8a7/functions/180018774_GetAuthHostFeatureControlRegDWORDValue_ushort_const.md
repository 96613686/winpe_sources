# GetAuthHostFeatureControlRegDWORDValue(ushort const *)

- ea: `0x180018774`
- end: `0x180018821`
- name: `?GetAuthHostFeatureControlRegDWORDValue@@YAKPEBG@Z`
- size: `173`
- prototype: `__int64 __fastcall(const wchar_t *valueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017770`

## callees

- `0x180018774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018812`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018812`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800187be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800187be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800187ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800187ec`

## pseudocode

```c
__int64 __fastcall GetAuthHostFeatureControlRegDWORDValue(const wchar_t *valueName)
{
  __int64 value; // [rsp+40h] [rbp+10h] BYREF
  unsigned int type; // [rsp+48h] [rbp+18h] BYREF
  unsigned int valueSize; // [rsp+50h] [rbp+20h] BYREF
  HKEY__ *key; // [rsp+58h] [rbp+28h] BYREF

  HIDWORD(value) = HIDWORD(valueName);
  LODWORD(value) = 0;
  valueSize = 4;
  type = 0;
  key = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\AuthHost", 0, 0x20019u, &key)
    && (RegQueryValueExW(key, L"RequireHttps", 0, &type, (LPBYTE)&value, &valueSize) || type != 4 || valueSize != 4) )
  {
    LODWORD(value) = 0;
  }
  if ( key )
    RegCloseKey(key);
  return (unsigned int)value;
}

```

## disassembly

```asm
0x180018774  mov     [rsp-8+value], rcx
0x180018779  push    rbp
0x18001877a  mov     rbp, rsp
0x18001877d  sub     rsp, 30h
0x180018781  lea     rax, [rbp+key]
0x180018785  mov     dword ptr [rbp+value], 0
0x18001878c  mov     r9d, 20019h; samDesired
0x180018792  mov     [rsp+30h+phkResult], rax; phkResult
0x180018797  xor     r8d, r8d; ulOptions
0x18001879a  mov     [rbp+valueSize], 4
0x1800187a1  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\AuthHost"
0x1800187a8  mov     [rbp+type], 0
0x1800187af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800187b6  mov     [rbp+key], 0
0x1800187be  call    cs:__imp_RegOpenKeyExW
0x1800187c4  test    eax, eax
0x1800187c6  jnz     short $Exit_18
0x1800187c8  mov     rcx, [rbp+key]; hKey
0x1800187cc  lea     rax, [rbp+valueSize]
0x1800187d0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800187d5  lea     r9, [rbp+type]; lpType
0x1800187d9  lea     rax, [rbp+value]
0x1800187dd  xor     r8d, r8d; lpReserved
0x1800187e0  lea     rdx, aRequirehttps; "RequireHttps"
0x1800187e7  mov     [rsp+30h+phkResult], rax; lpData
0x1800187ec  call    cs:__imp_RegQueryValueExW
0x1800187f2  test    eax, eax
0x1800187f4  jnz     short loc_180018802
0x1800187f6  cmp     [rbp+type], 4
0x1800187fa  jnz     short loc_180018802
0x1800187fc  cmp     [rbp+valueSize], 4
0x180018800  jz      short $Exit_18
0x180018802  mov     dword ptr [rbp+value], 0
0x180018809  mov     rcx, [rbp+key]; hKey
0x18001880d  test    rcx, rcx
0x180018810  jz      short loc_180018818
0x180018812  call    cs:__imp_RegCloseKey
0x180018818  mov     eax, dword ptr [rbp+value]
0x18001881b  add     rsp, 30h
0x18001881f  pop     rbp
0x180018820  retn
```
