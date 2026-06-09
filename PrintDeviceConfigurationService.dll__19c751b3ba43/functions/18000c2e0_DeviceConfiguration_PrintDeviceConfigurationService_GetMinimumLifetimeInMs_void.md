# DeviceConfiguration::PrintDeviceConfigurationService::_GetMinimumLifetimeInMs(void)

- ea: `0x18000c2e0`
- end: `0x18000c336`
- name: `?_GetMinimumLifetimeInMs@PrintDeviceConfigurationService@DeviceConfiguration@@AEAAKXZ`
- size: `86`
- prototype: `__int64 __fastcall(DeviceConfiguration::PrintDeviceConfigurationService *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bac8`

## callees

- `0x18000ba40`
- `0x18000c2e0`

## string_xrefs

- `0x18000c30c`: `Software\Microsoft\Windows\CurrentVersion\PrintDeviceConfigurationService`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::PrintDeviceConfigurationService::_GetMinimumLifetimeInMs(
        DeviceConfiguration::PrintDeviceConfigurationService *this)
{
  unsigned int v1; // ebx
  unsigned int DwordValue; // eax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DeviceConfiguration::PrintDeviceConfigurationService *v6; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v7; // [rsp+38h] [rbp+10h]
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v6 = this;
  try
  {
    v1 = 120000;
    v7 = 120000;
    LOBYTE(v6) = 0;
    v8 = -2147483646;
    DwordValue = PrintCore::RegHelpers::GetDwordValue(
                   (HKEY *)&v8,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\PrintDeviceConfigurationService",
                   L"MinimumLifetime",
                   (bool *)&v6);
    if ( (_BYTE)v6 )
      v1 = DwordValue;
    v7 = v1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xF0,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\printdeviceconfigurationservice.cpp",
      v3);
    return v7;
  }
  return v1;
}

```

## disassembly

```asm
0x18000c2e0  mov     rax, rsp
0x18000c2e3  mov     [rax+8], rcx
0x18000c2e7  push    rbx
0x18000c2e8  sub     rsp, 20h
0x18000c2ec  mov     ebx, 1D4C0h
0x18000c2f1  mov     [rsp+28h+arg_8], ebx
0x18000c2f5  mov     byte ptr [rax+8], 0
0x18000c2f9  mov     qword ptr [rax+18h], 0FFFFFFFF80000002h
0x18000c301  lea     r9, [rax+8]; bool *
0x18000c305  lea     r8, aMinimumlifetim; "MinimumLifetime"
0x18000c30c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c313  lea     rcx, [rax+18h]; HKEY *
0x18000c317  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x18000c31c  cmp     byte ptr [rsp+28h+arg_0], 0
0x18000c321  cmovnz  ebx, eax
0x18000c324  mov     [rsp+28h+arg_8], ebx
0x18000c328  jmp     short loc_18000C32E
0x18000c32a  mov     ebx, [rsp+28h+arg_8]
0x18000c32e  mov     eax, ebx
0x18000c330  add     rsp, 20h
0x18000c334  pop     rbx
0x18000c335  retn
```
