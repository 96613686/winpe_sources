# MdmRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)

- ea: `0x18001cd64`
- end: `0x18001ce57`
- name: `?GetDWORDValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z`
- size: `243`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, BYTE *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c38c`
- `0x180013004`
- `0x1800132d4`
- `0x18001cb38`

## callees

- `0x180006548`
- `0x18001cd64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cdfd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cdfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ce3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ce3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd9b`

## string_xrefs

- `0x18001cdcf`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

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
0x18001cd64  mov     rax, rsp
0x18001cd67  mov     [rax+8], rbx
0x18001cd6b  mov     [rax+10h], rsi
0x18001cd6f  push    rdi
0x18001cd70  sub     rsp, 40h
0x18001cd74  mov     dword ptr [rax-18h], 4
0x18001cd7b  mov     rdi, r9
0x18001cd7e  mov     qword ptr [rax-10h], 0
0x18001cd86  lea     rax, [rax-10h]
0x18001cd8a  mov     rsi, r8
0x18001cd8d  mov     [rsp+48h+phkResult], rax; phkResult
0x18001cd92  mov     r9d, 20019h; samDesired
0x18001cd98  xor     r8d, r8d; ulOptions
0x18001cd9b  call    cs:__imp_RegOpenKeyExW
0x18001cda1  mov     ebx, eax
0x18001cda3  test    eax, eax
0x18001cda5  jz      short loc_18001CDE0
0x18001cda7  jle     short loc_18001CDB2
0x18001cda9  movzx   ebx, ax
0x18001cdac  or      ebx, 80070000h
0x18001cdb2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cdb9  jz      short loc_18001CE35
0x18001cdbb  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001cdc2  mov     [rsp+48h+lpcbData], rax
0x18001cdc7  mov     dword ptr [rsp+48h+phkResult], 0D7h
0x18001cdcf  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001cdd6  mov     r8d, ebx
0x18001cdd9  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cdde  jmp     short loc_18001CE35
0x18001cde0  mov     rcx, [rsp+48h+hKey]; hKey
0x18001cde5  lea     rax, [rsp+48h+cbData]
0x18001cdea  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001cdef  xor     r9d, r9d; lpType
0x18001cdf2  xor     r8d, r8d; lpReserved
0x18001cdf5  mov     [rsp+48h+phkResult], rdi; lpData
0x18001cdfa  mov     rdx, rsi; lpValueName
0x18001cdfd  call    cs:__imp_RegQueryValueExW
0x18001ce03  mov     ebx, eax
0x18001ce05  test    eax, eax
0x18001ce07  jz      short loc_18001CE33
0x18001ce09  jle     short loc_18001CE14
0x18001ce0b  movzx   ebx, ax
0x18001ce0e  or      ebx, 80070000h
0x18001ce14  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ce1b  jz      short loc_18001CE35
0x18001ce1d  lea     rax, aCbr0lDwresult; "CBR(0L == dwResult)"
0x18001ce24  mov     [rsp+48h+lpcbData], rax
0x18001ce29  mov     dword ptr [rsp+48h+phkResult], 0E0h
0x18001ce31  jmp     short loc_18001CDCF
0x18001ce33  xor     ebx, ebx
0x18001ce35  mov     rcx, [rsp+48h+hKey]; hKey
0x18001ce3a  test    rcx, rcx
0x18001ce3d  jz      short loc_18001CE45
0x18001ce3f  call    cs:__imp_RegCloseKey
0x18001ce45  mov     rsi, [rsp+48h+arg_8]
0x18001ce4a  mov     eax, ebx
0x18001ce4c  mov     rbx, [rsp+48h+arg_0]
0x18001ce51  add     rsp, 40h
0x18001ce55  pop     rdi
0x18001ce56  retn
```
