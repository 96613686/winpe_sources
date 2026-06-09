# GetAuthHostRegDWORDValue(ushort const *)

- ea: `0x180004940`
- end: `0x1800049f6`
- name: `?GetAuthHostRegDWORDValue@@YAKPEBG@Z`
- size: `182`
- prototype: `__int64 __fastcall(const wchar_t *valueName)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002b20`
- `0x18000ed84`
- `0x18000f568`
- `0x180010494`
- `0x180011034`
- `0x180011474`
- `0x180017770`

## callees

- `0x180004940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800049e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800049e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004985`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004985`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800049b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800049b3`

## pseudocode

```c
__int64 __fastcall GetAuthHostRegDWORDValue(const wchar_t *valueName)
{
  __int64 result; // rax
  HKEY__ *key; // [rsp+30h] [rbp-18h] BYREF
  unsigned int value; // [rsp+58h] [rbp+10h] BYREF
  unsigned int type; // [rsp+60h] [rbp+18h] BYREF
  unsigned int valueSize; // [rsp+68h] [rbp+20h] BYREF

  valueSize = 4;
  value = 0;
  type = 0;
  key = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\authhost.exe",
         0,
         0x20019u,
         &key)
    || !RegQueryValueExW(key, valueName, 0, &type, (LPBYTE)&value, &valueSize) && type == 4 && valueSize == 4 )
  {
    result = value;
  }
  else
  {
    result = 0;
    value = 0;
  }
  if ( key )
  {
    RegCloseKey(key);
    return value;
  }
  return result;
}

```

## disassembly

```asm
0x180004940  mov     [rsp+arg_0], rbx
0x180004945  push    rdi
0x180004946  sub     rsp, 40h
0x18000494a  xor     edi, edi
0x18000494c  mov     [rsp+48h+valueSize], 4
0x180004954  mov     rbx, valueName
0x180004957  mov     [rsp+48h+value], edi
0x18000495b  lea     rax, [rsp+48h+key]
0x180004960  mov     [rsp+48h+type], edi
0x180004964  mov     valueName, 0FFFFFFFF80000002h; hKey
0x18000496b  mov     [rsp+48h+key], rdi
0x180004970  mov     r9d, 20019h; samDesired
0x180004976  mov     [rsp+48h+phkResult], rax; phkResult
0x18000497b  xor     r8d, r8d; ulOptions
0x18000497e  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180004985  call    cs:__imp_RegOpenKeyExW
0x18000498b  test    eax, eax
0x18000498d  jnz     short loc_1800049D3
0x18000498f  mov     valueName, [rsp+48h+key]; hKey
0x180004994  lea     rax, [rsp+48h+valueSize]
0x180004999  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000499e  lea     r9, [rsp+48h+type]; lpType
0x1800049a3  lea     rax, [rsp+48h+value]
0x1800049a8  xor     r8d, r8d; lpReserved
0x1800049ab  mov     rdx, rbx; lpValueName
0x1800049ae  mov     [rsp+48h+phkResult], rax; lpData
0x1800049b3  call    cs:__imp_RegQueryValueExW
0x1800049b9  test    eax, eax
0x1800049bb  jnz     short loc_1800049CB
0x1800049bd  cmp     [rsp+48h+type], 4
0x1800049c2  jnz     short loc_1800049CB
0x1800049c4  cmp     [rsp+48h+valueSize], 4
0x1800049c9  jz      short loc_1800049D3
0x1800049cb  mov     eax, edi
0x1800049cd  mov     [rsp+48h+value], eax
0x1800049d1  jmp     short $Exit_3
0x1800049d3  mov     eax, [rsp+48h+value]
0x1800049d7  mov     valueName, [rsp+48h+key]; hKey
0x1800049dc  test    valueName, valueName
0x1800049df  jz      short loc_1800049EB
0x1800049e1  call    cs:__imp_RegCloseKey
0x1800049e7  mov     eax, [rsp+48h+value]
0x1800049eb  mov     rbx, [rsp+48h+arg_0]
0x1800049f0  add     rsp, 40h
0x1800049f4  pop     rdi
0x1800049f5  retn
```
