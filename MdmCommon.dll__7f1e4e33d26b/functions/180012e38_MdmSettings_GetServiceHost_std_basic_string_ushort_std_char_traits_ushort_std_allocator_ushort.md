# MdmSettings::GetServiceHost(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180012e38`
- end: `0x180012e95`
- name: `?GetServiceHost@MdmSettings@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b780`
- `0x18001c5f0`

## callees

- `0x180006548`
- `0x180012e38`
- `0x18001ce60`

## string_xrefs

- `0x180012e4f`: `Software\Microsoft\MdmCommon\Internal`
- `0x180012e41`: `ServiceHost`
- `0x180012e79`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012e6a`: `CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszServiceHostValueName, pszValue))`

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
      (__int64)"CHR(MdmRegistry::GetStringValue( c_pszGeneralInternalKey, c_pszServiceHostValueName, pszValue))");
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180012e38  push    rbx
0x180012e3a  sub     rsp, 30h
0x180012e3e  mov     r9, rcx
0x180012e41  lea     r8, aServicehost; "ServiceHost"
0x180012e48  mov     rcx, 0FFFFFFFF80000002h
0x180012e4f  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\MdmCommon\\Interna"...
0x180012e56  call    ?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x180012e5b  mov     ebx, eax
0x180012e5d  test    eax, eax
0x180012e5f  jns     short loc_180012E8D
0x180012e61  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012e68  jz      short loc_180012E8D
0x180012e6a  lea     rax, aChrMdmregistry_17; "CHR(MdmRegistry::GetStringValue( c_pszG"...
0x180012e71  mov     r8d, ebx
0x180012e74  mov     [rsp+38h+var_10], rax
0x180012e79  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012e80  mov     [rsp+38h+var_18], 217h
0x180012e88  call    McTemplateU0dsqs_EventWriteTransfer
0x180012e8d  mov     eax, ebx
0x180012e8f  add     rsp, 30h
0x180012e93  pop     rbx
0x180012e94  retn
```
