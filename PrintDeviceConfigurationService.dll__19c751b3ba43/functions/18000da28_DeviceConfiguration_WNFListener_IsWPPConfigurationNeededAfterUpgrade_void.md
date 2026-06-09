# DeviceConfiguration::WNFListener::_IsWPPConfigurationNeededAfterUpgrade(void)

- ea: `0x18000da28`
- end: `0x18000da7e`
- name: `?_IsWPPConfigurationNeededAfterUpgrade@WNFListener@DeviceConfiguration@@AEAA_NXZ`
- size: `86`
- prototype: `char __fastcall(DeviceConfiguration::WNFListener *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d668`

## callees

- `0x18000ba40`
- `0x18000da28`

## string_xrefs

- `0x18000da50`: `SYSTEM\CurrentControlSet\Services\PrintDeviceConfigurationService\State\WPP`
- `0x18000da49`: `WindowsProtectedPrintOobeConfigComplete`

## pseudocode

```c
char __fastcall DeviceConfiguration::WNFListener::_IsWPPConfigurationNeededAfterUpgrade(
        DeviceConfiguration::WNFListener *this)
{
  char v1; // bl
  unsigned int DwordValue; // eax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DeviceConfiguration::WNFListener *v6; // [rsp+30h] [rbp+8h] BYREF
  char v7; // [rsp+38h] [rbp+10h]
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v6 = this;
  try
  {
    v1 = 0;
    v7 = 0;
    LOBYTE(v6) = 0;
    v8 = -2147483646;
    DwordValue = PrintCore::RegHelpers::GetDwordValue(
                   (HKEY *)&v8,
                   L"SYSTEM\\CurrentControlSet\\Services\\PrintDeviceConfigurationService\\State\\WPP",
                   L"WindowsProtectedPrintOobeConfigComplete",
                   (bool *)&v6);
    if ( !(_BYTE)v6 || !DwordValue )
    {
      v1 = 1;
      v7 = 1;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xC1,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
      v3);
    return v7;
  }
  return v1;
}

```

## disassembly

```asm
0x18000da28  mov     rax, rsp
0x18000da2b  mov     [rax+8], rcx
0x18000da2f  push    rbx
0x18000da30  sub     rsp, 20h
0x18000da34  xor     bl, bl
0x18000da36  mov     [rsp+28h+arg_8], bl
0x18000da3a  mov     [rax+8], bl
0x18000da3d  mov     qword ptr [rax+18h], 0FFFFFFFF80000002h
0x18000da45  lea     r9, [rax+8]; bool *
0x18000da49  lea     r8, aWindowsprotect; "WindowsProtectedPrintOobeConfigComplete"
0x18000da50  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Pr"...
0x18000da57  lea     rcx, [rax+18h]; HKEY *
0x18000da5b  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x18000da60  cmp     byte ptr [rsp+28h+arg_0], bl
0x18000da64  jz      short loc_18000DA6A
0x18000da66  test    eax, eax
0x18000da68  jnz     short loc_18000DA70
0x18000da6a  mov     bl, 1
0x18000da6c  mov     [rsp+28h+arg_8], bl
0x18000da70  jmp     short loc_18000DA76
0x18000da72  mov     bl, [rsp+28h+arg_8]
0x18000da76  mov     al, bl
0x18000da78  add     rsp, 20h
0x18000da7c  pop     rbx
0x18000da7d  retn
```
