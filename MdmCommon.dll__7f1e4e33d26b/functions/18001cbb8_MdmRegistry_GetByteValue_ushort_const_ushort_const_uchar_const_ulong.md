# MdmRegistry::GetByteValue(ushort const *,ushort const *,uchar * const,ulong &)

- ea: `0x18001cbb8`
- end: `0x18001cd5e`
- name: `?GetByteValue@MdmRegistry@@SAJPEBG0QEAEAEAK@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, unsigned __int8 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012b8c`

## callees

- `0x180006548`
- `0x18001cbb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cc66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ccf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cc66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ccf7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cc04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cc04`

## string_xrefs

- `0x18001cd2d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

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
0x18001cbb8  mov     rax, rsp
0x18001cbbb  mov     [rax+8], rbx
0x18001cbbf  mov     [rax+18h], rsi
0x18001cbc3  mov     [rax+10h], rdx
0x18001cbc7  push    rdi
0x18001cbc8  sub     rsp, 40h
0x18001cbcc  mov     dword ptr [rax+10h], 0
0x18001cbd3  mov     rdi, r9
0x18001cbd6  mov     dword ptr [rax-18h], 3
0x18001cbdd  mov     rsi, r8
0x18001cbe0  mov     qword ptr [rax-10h], 0
0x18001cbe8  lea     rax, [rax-10h]
0x18001cbec  mov     rdx, rcx; lpSubKey
0x18001cbef  mov     [rsp+48h+phkResult], rax; phkResult
0x18001cbf4  mov     r9d, 20019h; samDesired
0x18001cbfa  xor     r8d, r8d; ulOptions
0x18001cbfd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cc04  call    cs:__imp_RegOpenKeyExW
0x18001cc0a  mov     ebx, eax
0x18001cc0c  test    eax, eax
0x18001cc0e  jz      short loc_18001CC41
0x18001cc10  jle     short loc_18001CC1B
0x18001cc12  movzx   ebx, ax
0x18001cc15  or      ebx, 80070000h
0x18001cc1b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cc22  jz      loc_18001CD3C
0x18001cc28  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001cc2f  mov     [rsp+48h+lpcbData], rax
0x18001cc34  mov     dword ptr [rsp+48h+phkResult], 2Ah ; '*'
0x18001cc3c  jmp     loc_18001CD2D
0x18001cc41  mov     rcx, [rsp+48h+hKey]; hKey
0x18001cc46  lea     rax, [rsp+48h+cbData]
0x18001cc4b  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001cc50  lea     rdx, ValueName; "ProtectionSessionLastSent"
0x18001cc57  xor     r9d, r9d; lpType
0x18001cc5a  mov     [rsp+48h+phkResult], 0; lpData
0x18001cc63  xor     r8d, r8d; lpReserved
0x18001cc66  call    cs:__imp_RegQueryValueExW
0x18001cc6c  mov     ebx, eax
0x18001cc6e  test    eax, eax
0x18001cc70  jz      short loc_18001CCA3
0x18001cc72  jle     short loc_18001CC7D
0x18001cc74  movzx   ebx, ax
0x18001cc77  or      ebx, 80070000h
0x18001cc7d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cc84  jz      loc_18001CD3C
0x18001cc8a  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001cc91  mov     [rsp+48h+lpcbData], rax
0x18001cc96  mov     dword ptr [rsp+48h+phkResult], 34h ; '4'
0x18001cc9e  jmp     loc_18001CD2D
0x18001cca3  mov     eax, [rsp+48h+cbData]
0x18001cca7  xor     ebx, ebx
0x18001cca9  test    eax, eax
0x18001ccab  jz      loc_18001CD3C
0x18001ccb1  cmp     [rdi], eax
0x18001ccb3  jnb     short loc_18001CCD9
0x18001ccb5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ccbc  mov     ebx, 8007007Ah
0x18001ccc1  jz      short loc_18001CD3C
0x18001ccc3  lea     rax, aCbrCbvalueCbsi; "CBR(cbValue >= cbSize)"
0x18001ccca  mov     [rsp+48h+lpcbData], rax
0x18001cccf  mov     dword ptr [rsp+48h+phkResult], 3Ch ; '<'
0x18001ccd7  jmp     short loc_18001CD2D
0x18001ccd9  mov     rcx, [rsp+48h+hKey]; hKey
0x18001ccde  lea     r9, [rsp+48h+Type]; lpType
0x18001cce3  mov     [rsp+48h+lpcbData], rdi; lpcbData
0x18001cce8  lea     rdx, ValueName; "ProtectionSessionLastSent"
0x18001ccef  xor     r8d, r8d; lpReserved
0x18001ccf2  mov     [rsp+48h+phkResult], rsi; lpData
0x18001ccf7  call    cs:__imp_RegQueryValueExW
0x18001ccfd  test    eax, eax
0x18001ccff  jz      short loc_18001CD3C
0x18001cd01  jg      short loc_18001CD07
0x18001cd03  mov     ebx, eax
0x18001cd05  jmp     short loc_18001CD10
0x18001cd07  movzx   ebx, ax
0x18001cd0a  or      ebx, 80070000h
0x18001cd10  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cd17  jz      short loc_18001CD3C
0x18001cd19  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001cd20  mov     [rsp+48h+lpcbData], rax
0x18001cd25  mov     dword ptr [rsp+48h+phkResult], 46h ; 'F'
0x18001cd2d  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001cd34  mov     r8d, ebx
0x18001cd37  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cd3c  mov     rcx, [rsp+48h+hKey]; hKey
0x18001cd41  test    rcx, rcx
0x18001cd44  jz      short loc_18001CD4C
0x18001cd46  call    cs:__imp_RegCloseKey
0x18001cd4c  mov     rsi, [rsp+48h+arg_10]
0x18001cd51  mov     eax, ebx
0x18001cd53  mov     rbx, [rsp+48h+arg_0]
0x18001cd58  add     rsp, 40h
0x18001cd5c  pop     rdi
0x18001cd5d  retn
```
