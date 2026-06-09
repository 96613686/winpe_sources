# DeviceConfiguration::StringifyDeviceType(DeviceConfiguration::DeviceType)

- ea: `0x18000f9b4`
- end: `0x18000f9e3`
- name: `?StringifyDeviceType@DeviceConfiguration@@YAPEBGW4DeviceType@1@@Z`
- size: `47`
- prototype: `const wchar_t *__fastcall(int)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ed18`
- `0x18000fad4`
- `0x18000fbe0`
- `0x180010ca4`

## callees

- `0x18000f9b4`

## pseudocode

```c
const wchar_t *__fastcall DeviceConfiguration::StringifyDeviceType(int a1)
{
  int v1; // ecx
  int v2; // ecx

  v1 = a1 - 1;
  if ( !v1 )
    return L"IPP";
  v2 = v1 - 1;
  if ( !v2 )
    return L"IPPUSB";
  if ( v2 == 1 )
    return L"UP";
  return L"Unknown";
}

```

## disassembly

```asm
0x18000f9b4  sub     ecx, 1
0x18000f9b7  jz      short loc_18000F9DB
0x18000f9b9  sub     ecx, 1
0x18000f9bc  jz      short loc_18000F9D3
0x18000f9be  cmp     ecx, 1
0x18000f9c1  jz      short loc_18000F9CB
0x18000f9c3  lea     rax, aUnknown_0; "Unknown"
0x18000f9ca  retn
0x18000f9cb  lea     rax, aUp; "UP"
0x18000f9d2  retn
0x18000f9d3  lea     rax, aIppusb; "IPPUSB"
0x18000f9da  retn
0x18000f9db  lea     rax, aIpp_0; "IPP"
0x18000f9e2  retn
```
