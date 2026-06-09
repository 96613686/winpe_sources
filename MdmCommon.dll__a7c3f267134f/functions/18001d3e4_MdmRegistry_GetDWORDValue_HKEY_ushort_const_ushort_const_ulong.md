# MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)

- ea: `0x18001d3e4`
- end: `0x18001d4ee`
- name: `?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z`
- size: `266`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6e8`
- `0x1800133e8`
- `0x1800136b8`
- `0x18001d19c`

## callees

- `0x1800065c0`
- `0x18001d3e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d487`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d487`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d4cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d4cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d41b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d41b`

## string_xrefs

- `0x18001d459`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::GetDWORDValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4)
{
  LSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // ebx
  LSTATUS Value; // eax
  int v11; // edx
  int v12; // ecx
  __int64 cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF

  LODWORD(cbData) = 4;
  hKey = 0;
  v6 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
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
        215,
        "CBR(0L == dwResult)",
        cbData);
  }
  else
  {
    Value = RegQueryValueExW(hKey, a3, 0, 0, a4, (LPDWORD)&cbData);
    v9 = Value;
    if ( Value )
    {
      if ( Value > 0 )
        v9 = (unsigned __int16)Value | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v12,
          v11,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
          224,
          "CBR(0L == dwResult)",
          cbData);
    }
    else
    {
      v9 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18001d3e4  mov     rax, rsp
0x18001d3e7  mov     [rax+8], rbx
0x18001d3eb  mov     [rax+10h], rsi
0x18001d3ef  push    rdi
0x18001d3f0  sub     rsp, 40h
0x18001d3f4  mov     dword ptr [rax-18h], 4
0x18001d3fb  mov     rdi, r9
0x18001d3fe  mov     qword ptr [rax-10h], 0
0x18001d406  lea     rax, [rax-10h]
0x18001d40a  mov     rsi, r8
0x18001d40d  mov     [rsp+48h+phkResult], rax; phkResult
0x18001d412  mov     r9d, 20019h; samDesired
0x18001d418  xor     r8d, r8d; ulOptions
0x18001d41b  call    cs:__imp_RegOpenKeyExW
0x18001d422  nop     dword ptr [rax+rax+00h]
0x18001d427  mov     ebx, eax
0x18001d429  test    eax, eax
0x18001d42b  jz      short loc_18001D46A
0x18001d42d  jle     short loc_18001D438
0x18001d42f  movzx   ebx, ax
0x18001d432  or      ebx, 80070000h
0x18001d438  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d43f  jz      loc_18001D4C5
0x18001d445  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d44c  mov     [rsp+48h+lpcbData], rax
0x18001d451  mov     dword ptr [rsp+48h+phkResult], 0D7h
0x18001d459  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d460  mov     r8d, ebx
0x18001d463  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d468  jmp     short loc_18001D4C5
0x18001d46a  mov     rcx, [rsp+48h+hKey]; hKey
0x18001d46f  lea     rax, [rsp+48h+cbData]
0x18001d474  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001d479  xor     r9d, r9d; lpType
0x18001d47c  xor     r8d, r8d; lpReserved
0x18001d47f  mov     [rsp+48h+phkResult], rdi; lpData
0x18001d484  mov     rdx, rsi; lpValueName
0x18001d487  call    cs:__imp_RegQueryValueExW
0x18001d48e  nop     dword ptr [rax+rax+00h]
0x18001d493  mov     ebx, eax
0x18001d495  test    eax, eax
0x18001d497  jz      short loc_18001D4C3
0x18001d499  jle     short loc_18001D4A4
0x18001d49b  movzx   ebx, ax
0x18001d49e  or      ebx, 80070000h
0x18001d4a4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d4ab  jz      short loc_18001D4C5
0x18001d4ad  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001d4b4  mov     [rsp+48h+lpcbData], rax
0x18001d4b9  mov     dword ptr [rsp+48h+phkResult], 0E0h
0x18001d4c1  jmp     short loc_18001D459
0x18001d4c3  xor     ebx, ebx
0x18001d4c5  mov     rcx, [rsp+48h+hKey]; hKey
0x18001d4ca  test    rcx, rcx
0x18001d4cd  jz      short loc_18001D4DB
0x18001d4cf  call    cs:__imp_RegCloseKey
0x18001d4d6  nop     dword ptr [rax+rax+00h]
0x18001d4db  mov     rsi, [rsp+48h+arg_8]
0x18001d4e0  mov     eax, ebx
0x18001d4e2  mov     rbx, [rsp+48h+arg_0]
0x18001d4e7  add     rsp, 40h
0x18001d4eb  pop     rdi
0x18001d4ec  retn
```
