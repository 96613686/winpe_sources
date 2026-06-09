# MdmRegistry::GetByteValue(ushort const *,ushort const *,uchar * const,ulong &)

- ea: `0x18001d21c`
- end: `0x18001d3db`
- name: `?GetByteValue@MdmRegistry@@SAJPEBG0QEAEAEAK@Z`
- size: `447`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, unsigned __int8 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012f70`

## callees

- `0x1800065c0`
- `0x18001d21c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d2d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d367`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d2d0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d367`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d3bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d3bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d268`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d268`

## string_xrefs

- `0x18001d3a3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::GetByteValue(
        LPCWSTR lpSubKey,
        const unsigned __int16 *a2,
        unsigned __int8 *const a3,
        unsigned int *a4)
{
  LSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // ebx
  LSTATUS v10; // eax
  int v11; // edx
  int v12; // ecx
  LSTATUS Value; // eax
  int v14; // edx
  int v15; // ecx
  __int64 Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  int v20; // [rsp+5Ch] [rbp+14h]

  v20 = HIDWORD(a2);
  cbData = 0;
  LODWORD(Type) = 3;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v9 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v9 = (unsigned __int16)v6 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        v9,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
        42,
        "CBR(0L == dwResult)",
        Type);
  }
  else
  {
    v10 = RegQueryValueExW(hKey, L"ProtectionSessionLastSent", 0, 0, 0, &cbData);
    v9 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
          52,
          "CBR(0L == dwResult)",
          Type);
    }
    else
    {
      v9 = 0;
      if ( cbData )
      {
        if ( *a4 >= cbData )
        {
          Value = RegQueryValueExW(hKey, L"ProtectionSessionLastSent", 0, (LPDWORD)&Type, a3, a4);
          if ( Value )
          {
            v9 = Value > 0 ? (unsigned __int16)Value | 0x80070000 : Value;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v15,
                v14,
                v9,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
                70,
                "CBR(0L == dwResult)",
                Type);
          }
        }
        else
        {
          v9 = -2147024774;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v12,
              v11,
              -2147024774,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
              60,
              "CBR(cbValue >= cbSize)",
              Type);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18001d21c  mov     rax, rsp
0x18001d21f  mov     [rax+8], rbx
0x18001d223  mov     [rax+18h], rsi
0x18001d227  mov     [rax+10h], rdx
0x18001d22b  push    rdi
0x18001d22c  sub     rsp, 40h
0x18001d230  mov     dword ptr [rax+10h], 0
0x18001d237  mov     rdi, r9
0x18001d23a  mov     dword ptr [rax-18h], 3
0x18001d241  mov     rsi, r8
0x18001d244  mov     qword ptr [rax-10h], 0
0x18001d24c  lea     rax, [rax-10h]
0x18001d250  mov     rdx, rcx; lpSubKey
0x18001d253  mov     [rsp+48h+phkResult], rax; phkResult
0x18001d258  mov     r9d, 20019h; samDesired
0x18001d25e  xor     r8d, r8d; ulOptions
0x18001d261  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d268  call    cs:__imp_RegOpenKeyExW
0x18001d26f  nop     dword ptr [rax+rax+00h]
0x18001d274  mov     ebx, eax
0x18001d276  test    eax, eax
0x18001d278  jz      short loc_18001D2AB
0x18001d27a  jle     short loc_18001D285
0x18001d27c  movzx   ebx, ax
0x18001d27f  or      ebx, 80070000h
0x18001d285  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d28c  jz      loc_18001D3B2
0x18001d292  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d299  mov     [rsp+48h+lpcbData], rax
0x18001d29e  mov     dword ptr [rsp+48h+phkResult], 2Ah ; '*'
0x18001d2a6  jmp     loc_18001D3A3
0x18001d2ab  mov     rcx, [rsp+48h+hKey]; hKey
0x18001d2b0  lea     rax, [rsp+48h+cbData]
0x18001d2b5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001d2ba  lea     rdx, ValueName; "ProtectionSessionLastSent"
0x18001d2c1  xor     r9d, r9d; lpType
0x18001d2c4  mov     [rsp+48h+phkResult], 0; lpData
0x18001d2cd  xor     r8d, r8d; lpReserved
0x18001d2d0  call    cs:__imp_RegQueryValueExW
0x18001d2d7  nop     dword ptr [rax+rax+00h]
0x18001d2dc  mov     ebx, eax
0x18001d2de  test    eax, eax
0x18001d2e0  jz      short loc_18001D313
0x18001d2e2  jle     short loc_18001D2ED
0x18001d2e4  movzx   ebx, ax
0x18001d2e7  or      ebx, 80070000h
0x18001d2ed  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d2f4  jz      loc_18001D3B2
0x18001d2fa  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d301  mov     [rsp+48h+lpcbData], rax
0x18001d306  mov     dword ptr [rsp+48h+phkResult], 34h ; '4'
0x18001d30e  jmp     loc_18001D3A3
0x18001d313  mov     eax, [rsp+48h+cbData]
0x18001d317  xor     ebx, ebx
0x18001d319  test    eax, eax
0x18001d31b  jz      loc_18001D3B2
0x18001d321  cmp     [rdi], eax
0x18001d323  jnb     short loc_18001D349
0x18001d325  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d32c  mov     ebx, 8007007Ah
0x18001d331  jz      short loc_18001D3B2
0x18001d333  lea     rax, aCbrCbvalueCbsi; "CBR(cbValue >= cbSize)"
0x18001d33a  mov     [rsp+48h+lpcbData], rax
0x18001d33f  mov     dword ptr [rsp+48h+phkResult], 3Ch ; '<'
0x18001d347  jmp     short loc_18001D3A3
0x18001d349  mov     rcx, [rsp+48h+hKey]; hKey
0x18001d34e  lea     r9, [rsp+48h+Type]; lpType
0x18001d353  mov     [rsp+48h+lpcbData], rdi; lpcbData
0x18001d358  lea     rdx, ValueName; "ProtectionSessionLastSent"
0x18001d35f  xor     r8d, r8d; lpReserved
0x18001d362  mov     [rsp+48h+phkResult], rsi; lpData
0x18001d367  call    cs:__imp_RegQueryValueExW
0x18001d36e  nop     dword ptr [rax+rax+00h]
0x18001d373  test    eax, eax
0x18001d375  jz      short loc_18001D3B2
0x18001d377  jg      short loc_18001D37D
0x18001d379  mov     ebx, eax
0x18001d37b  jmp     short loc_18001D386
0x18001d37d  movzx   ebx, ax
0x18001d380  or      ebx, 80070000h
0x18001d386  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d38d  jz      short loc_18001D3B2
0x18001d38f  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d396  mov     [rsp+48h+lpcbData], rax
0x18001d39b  mov     dword ptr [rsp+48h+phkResult], 46h ; 'F'
0x18001d3a3  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d3aa  mov     r8d, ebx
0x18001d3ad  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d3b2  mov     rcx, [rsp+48h+hKey]; hKey
0x18001d3b7  test    rcx, rcx
0x18001d3ba  jz      short loc_18001D3C8
0x18001d3bc  call    cs:__imp_RegCloseKey
0x18001d3c3  nop     dword ptr [rax+rax+00h]
0x18001d3c8  mov     rsi, [rsp+48h+arg_10]
0x18001d3cd  mov     eax, ebx
0x18001d3cf  mov     rbx, [rsp+48h+arg_0]
0x18001d3d4  add     rsp, 40h
0x18001d3d8  pop     rdi
0x18001d3d9  retn
```
