# MdmRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18001d248`
- end: `0x18001d365`
- name: `?SetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `285`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, __int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800133bc`
- `0x1800134ec`
- `0x18001361c`
- `0x18001374c`
- `0x18001387c`
- `0x180013b74`
- `0x180013e10`

## callees

- `0x180006548`
- `0x18001d248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d34d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d34d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d30b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d30b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d294`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d294`

## string_xrefs

- `0x18001d2cc`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

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
        (__int64)"CBR(lRet == 0L)");
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
          (__int64)"CBR(lRet == 0L)");
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
0x18001d248  mov     r11, rsp
0x18001d24b  mov     [r11+8], rbx
0x18001d24f  mov     [r11+10h], rsi
0x18001d253  push    rdi
0x18001d254  sub     rsp, 60h
0x18001d258  mov     qword ptr [r11-28h], 0
0x18001d260  lea     rax, [r11-18h]
0x18001d264  mov     [r11-30h], rax
0x18001d268  mov     rdi, r9
0x18001d26b  mov     qword ptr [r11-38h], 0
0x18001d273  mov     rsi, r8
0x18001d276  mov     [rsp+68h+samDesired], 20006h; samDesired
0x18001d27e  xor     r9d, r9d; lpClass
0x18001d281  xor     r8d, r8d; Reserved
0x18001d284  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001d28c  mov     qword ptr [r11-18h], 0
0x18001d294  call    cs:__imp_RegCreateKeyExW
0x18001d29a  mov     ebx, eax
0x18001d29c  test    eax, eax
0x18001d29e  jz      short loc_18001D2DD
0x18001d2a0  jle     short loc_18001D2AB
0x18001d2a2  movzx   ebx, ax
0x18001d2a5  or      ebx, 80070000h
0x18001d2ab  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d2b2  jz      loc_18001D343
0x18001d2b8  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d2bf  mov     qword ptr [rsp+68h+samDesired], rax
0x18001d2c4  mov     [rsp+68h+dwOptions], 1C3h
0x18001d2cc  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d2d3  mov     r8d, ebx
0x18001d2d6  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d2db  jmp     short loc_18001D343
0x18001d2dd  cmp     qword ptr [rdi+18h], 7
0x18001d2e2  mov     eax, [rdi+10h]
0x18001d2e5  lea     eax, ds:2[rax*2]
0x18001d2ec  jbe     short loc_18001D2F1
0x18001d2ee  mov     rdi, [rdi]
0x18001d2f1  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d2f6  mov     r9d, 1; dwType
0x18001d2fc  mov     [rsp+68h+samDesired], eax; cbData
0x18001d300  xor     r8d, r8d; Reserved
0x18001d303  mov     rdx, rsi; lpValueName
0x18001d306  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x18001d30b  call    cs:__imp_RegSetValueExW
0x18001d311  mov     ebx, eax
0x18001d313  test    eax, eax
0x18001d315  jz      short loc_18001D341
0x18001d317  jle     short loc_18001D322
0x18001d319  movzx   ebx, ax
0x18001d31c  or      ebx, 80070000h
0x18001d322  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d329  jz      short loc_18001D343
0x18001d32b  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d332  mov     qword ptr [rsp+68h+samDesired], rax
0x18001d337  mov     [rsp+68h+dwOptions], 1CEh
0x18001d33f  jmp     short loc_18001D2CC
0x18001d341  xor     ebx, ebx
0x18001d343  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d348  test    rcx, rcx
0x18001d34b  jz      short loc_18001D353
0x18001d34d  call    cs:__imp_RegCloseKey
0x18001d353  mov     rsi, [rsp+68h+arg_8]
0x18001d358  mov     eax, ebx
0x18001d35a  mov     rbx, [rsp+68h+arg_0]
0x18001d35f  add     rsp, 60h
0x18001d363  pop     rdi
0x18001d364  retn
```
