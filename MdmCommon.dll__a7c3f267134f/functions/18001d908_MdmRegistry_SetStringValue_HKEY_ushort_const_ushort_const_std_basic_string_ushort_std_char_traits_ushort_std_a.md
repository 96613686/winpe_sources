# MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18001d908`
- end: `0x18001da38`
- name: `?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `304`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800137ac`
- `0x1800138dc`
- `0x180013a0c`
- `0x180013b3c`
- `0x180013c6c`
- `0x180013f74`
- `0x180014214`

## callees

- `0x1800065c0`
- `0x18001d908`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d9d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d9d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d954`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d954`

## string_xrefs

- `0x18001d992`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::SetStringValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, __int64 *a4)
{
  LSTATUS v6; // eax
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // ebx
  DWORD v10; // eax
  LSTATUS v11; // eax
  int v12; // edx
  int v13; // ecx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v6 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x20006u, 0, &hKey, 0);
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
        195,
        "CBR(lRet == 0L)");
  }
  else
  {
    v10 = 2 * *((_DWORD *)a4 + 4) + 2;
    if ( (unsigned __int64)a4[3] > 7 )
      a4 = (__int64 *)*a4;
    v11 = RegSetValueExW(hKey, a3, 0, 1u, (const BYTE *)a4, v10);
    v9 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v13,
          v12,
          v9,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
          206,
          "CBR(lRet == 0L)");
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
0x18001d908  mov     r11, rsp
0x18001d90b  mov     [r11+8], rbx
0x18001d90f  mov     [r11+10h], rsi
0x18001d913  push    rdi
0x18001d914  sub     rsp, 60h
0x18001d918  mov     qword ptr [r11-28h], 0
0x18001d920  lea     rax, [r11-18h]
0x18001d924  mov     [r11-30h], rax
0x18001d928  mov     rdi, r9
0x18001d92b  mov     qword ptr [r11-38h], 0
0x18001d933  mov     rsi, r8
0x18001d936  mov     [rsp+68h+samDesired], 20006h; samDesired
0x18001d93e  xor     r9d, r9d; lpClass
0x18001d941  xor     r8d, r8d; Reserved
0x18001d944  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001d94c  mov     qword ptr [r11-18h], 0
0x18001d954  call    cs:__imp_RegCreateKeyExW
0x18001d95b  nop     dword ptr [rax+rax+00h]
0x18001d960  mov     ebx, eax
0x18001d962  test    eax, eax
0x18001d964  jz      short loc_18001D9A3
0x18001d966  jle     short loc_18001D971
0x18001d968  movzx   ebx, ax
0x18001d96b  or      ebx, 80070000h
0x18001d971  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d978  jz      loc_18001DA0F
0x18001d97e  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d985  mov     qword ptr [rsp+68h+samDesired], rax
0x18001d98a  mov     [rsp+68h+dwOptions], 1C3h
0x18001d992  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d999  mov     r8d, ebx
0x18001d99c  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d9a1  jmp     short loc_18001DA0F
0x18001d9a3  cmp     qword ptr [rdi+18h], 7
0x18001d9a8  mov     eax, [rdi+10h]
0x18001d9ab  lea     eax, ds:2[rax*2]
0x18001d9b2  jbe     short loc_18001D9B7
0x18001d9b4  mov     rdi, [rdi]
0x18001d9b7  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d9bc  mov     r9d, 1; dwType
0x18001d9c2  mov     [rsp+68h+samDesired], eax; cbData
0x18001d9c6  xor     r8d, r8d; Reserved
0x18001d9c9  mov     rdx, rsi; lpValueName
0x18001d9cc  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x18001d9d1  call    cs:__imp_RegSetValueExW
0x18001d9d8  nop     dword ptr [rax+rax+00h]
0x18001d9dd  mov     ebx, eax
0x18001d9df  test    eax, eax
0x18001d9e1  jz      short loc_18001DA0D
0x18001d9e3  jle     short loc_18001D9EE
0x18001d9e5  movzx   ebx, ax
0x18001d9e8  or      ebx, 80070000h
0x18001d9ee  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d9f5  jz      short loc_18001DA0F
0x18001d9f7  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d9fe  mov     qword ptr [rsp+68h+samDesired], rax
0x18001da03  mov     [rsp+68h+dwOptions], 1CEh
0x18001da0b  jmp     short loc_18001D992
0x18001da0d  xor     ebx, ebx
0x18001da0f  mov     rcx, [rsp+68h+hKey]; hKey
0x18001da14  test    rcx, rcx
0x18001da17  jz      short loc_18001DA25
0x18001da19  call    cs:__imp_RegCloseKey
0x18001da20  nop     dword ptr [rax+rax+00h]
0x18001da25  mov     rsi, [rsp+68h+arg_8]
0x18001da2a  mov     eax, ebx
0x18001da2c  mov     rbx, [rsp+68h+arg_0]
0x18001da31  add     rsp, 60h
0x18001da35  pop     rdi
0x18001da36  retn
```
