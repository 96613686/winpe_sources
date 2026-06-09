# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetCurrentlyAppliedResolution(bool *)

- ea: `0x18001e5d4`
- end: `0x18001e6b8`
- name: `?GetCurrentlyAppliedResolution@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@AEAAPEBUSUPPORTED_RESOLUTION@23@PEA_N@Z`
- size: `228`
- prototype: `const struct SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION *__fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016368`
- `0x1800286d0`

## callees

- `0x18001e5d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e651`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e651`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e60c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e60c`

## pseudocode

```c
const struct SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION *__fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::GetCurrentlyAppliedResolution(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *this,
        bool *a2)
{
  char *v3; // rdi
  bool v4; // bl
  unsigned int i; // ecx
  __int64 v6; // rax
  SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution *pvData; // [rsp+60h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+18h] BYREF

  pvData = this;
  v3 = 0;
  hkey = 0;
  v4 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ResolutionOverride",
          0,
          0x20019u,
          &hkey) )
  {
    LODWORD(pvData) = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"Resolution", 0x10u, 0, &pvData, &pcbData) )
    {
      if ( (_DWORD)pvData )
      {
        if ( (_DWORD)pvData != 1 )
        {
          for ( i = 0; i < 2; ++i )
          {
            v6 = 16LL * i;
            if ( *(_DWORD *)((char *)&SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTIONS
                           + v6) == (_DWORD)pvData )
            {
              v3 = (char *)&SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTIONS
                 + v6;
              goto LABEL_11;
            }
          }
        }
      }
      else
      {
        v3 = (char *)&SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTION_1440;
LABEL_11:
        v4 = 1;
      }
    }
    RegCloseKey(hkey);
  }
  if ( a2 )
    *a2 = v4;
  return (const struct SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION *)v3;
}

```

## disassembly

```asm
0x18001e5d4  mov     r11, rsp
0x18001e5d7  mov     [r11+8], rcx
0x18001e5db  push    rbx
0x18001e5dc  push    rsi
0x18001e5dd  push    rdi
0x18001e5de  sub     rsp, 40h
0x18001e5e2  mov     rsi, rdx
0x18001e5e5  lea     rax, [r11+18h]
0x18001e5e9  xor     edi, edi
0x18001e5eb  mov     [r11-38h], rax
0x18001e5ef  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001e5f6  mov     [r11+18h], rdi
0x18001e5fa  mov     r9d, 20019h; samDesired
0x18001e600  xor     r8d, r8d; ulOptions
0x18001e603  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e60a  xor     bl, bl
0x18001e60c  call    cs:__imp_RegOpenKeyExW
0x18001e612  test    eax, eax
0x18001e614  jnz     loc_18001E6A6
0x18001e61a  mov     rcx, [rsp+58h+hkey]; hkey
0x18001e61f  lea     rax, [rsp+58h+arg_8]
0x18001e624  mov     [rsp+58h+pcbData], rax; pcbData
0x18001e629  lea     r9d, [rdi+10h]; dwFlags
0x18001e62d  lea     rax, [rsp+58h+arg_0]
0x18001e632  mov     dword ptr [rsp+58h+arg_0], edi
0x18001e636  mov     [rsp+58h+pvData], rax; pvData
0x18001e63b  lea     r8, ValueName; "Resolution"
0x18001e642  xor     edx, edx; lpSubKey
0x18001e644  mov     [rsp+58h+pdwType], rdi; pdwType
0x18001e649  mov     [rsp+58h+arg_8], 4
0x18001e651  call    cs:__imp_RegGetValueW
0x18001e657  test    eax, eax
0x18001e659  jnz     short loc_18001E69B
0x18001e65b  mov     r8d, dword ptr [rsp+58h+arg_0]
0x18001e660  mov     eax, r8d
0x18001e663  test    r8d, r8d
0x18001e666  jz      short loc_18001E692
0x18001e668  cmp     eax, 1
0x18001e66b  jz      short loc_18001E69B
0x18001e66d  xor     ecx, ecx
0x18001e66f  cmp     ecx, 2
0x18001e672  jnb     short loc_18001E69B
0x18001e674  mov     eax, ecx
0x18001e676  lea     rdx, ?s_SUPPORTED_RESOLUTIONS@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@0QBUSUPPORTED_RESOLUTION@23@B; SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION const near * const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTIONS
0x18001e67d  shl     rax, 4
0x18001e681  add     rdx, rax
0x18001e684  cmp     [rdx], r8d
0x18001e687  jz      short loc_18001E68D
0x18001e689  inc     ecx
0x18001e68b  jmp     short loc_18001E66F
0x18001e68d  mov     rdi, rdx
0x18001e690  jmp     short loc_18001E699
0x18001e692  lea     rdi, ?s_SUPPORTED_RESOLUTION_1440@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@0USUPPORTED_RESOLUTION@23@B; SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTION_1440
0x18001e699  mov     bl, 1
0x18001e69b  mov     rcx, [rsp+58h+hkey]; hKey
0x18001e6a0  call    cs:__imp_RegCloseKey
0x18001e6a6  test    rsi, rsi
0x18001e6a9  jz      short loc_18001E6AD
0x18001e6ab  mov     [rsi], bl
0x18001e6ad  mov     rax, rdi
0x18001e6b0  add     rsp, 40h
0x18001e6b4  pop     rdi
0x18001e6b5  pop     rsi
0x18001e6b6  pop     rbx
0x18001e6b7  retn
```
