# MdmSettings::GetServiceHost(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001321c`
- end: `0x18001327a`
- name: `?GetServiceHost@MdmSettings@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bd20`
- `0x18001cc30`

## callees

- `0x1800065c0`
- `0x18001321c`
- `0x18001d4f4`

## string_xrefs

- `0x180013233`: `Software\Microsoft\MdmCommon\Internal`
- `0x180013225`: `ServiceHost`
- `0x18001325d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001324e`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszServiceHostValueName, pszValue))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetServiceHost(_QWORD *a1)
{
  int v1; // edx
  int v2; // ecx
  int StringValue; // ebx

  StringValue = MdmRegistry::GetStringValue(
                  HKEY_LOCAL_MACHINE,
                  L"Software\\Microsoft\\MdmCommon\\Internal",
                  L"ServiceHost",
                  a1);
  if ( StringValue < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v2,
      v1,
      StringValue,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      23,
      "CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszServiceHostValueName, pszValue))");
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x18001321c  push    rbx
0x18001321e  sub     rsp, 30h
0x180013222  mov     r9, rcx
0x180013225  lea     r8, aServicehost; "ServiceHost"
0x18001322c  mov     rcx, 0FFFFFFFF80000002h
0x180013233  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x18001323a  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x18001323f  mov     ebx, eax
0x180013241  test    eax, eax
0x180013243  jns     short loc_180013271
0x180013245  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001324c  jz      short loc_180013271
0x18001324e  lea     rax, aChrMdmregistry_17; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x180013255  mov     r8d, ebx
0x180013258  mov     [rsp+38h+var_10], rax
0x18001325d  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180013264  mov     [rsp+38h+var_18], 217h
0x18001326c  call    McTemplateU0dsqs_EventWriteTransfer
0x180013271  mov     eax, ebx
0x180013273  add     rsp, 30h
0x180013277  pop     rbx
0x180013278  retn
```
