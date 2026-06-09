# DeviceConfiguration::ConfigurationManager::_ResetWindowsProtectedPrint(void)

- ea: `0x180013534`
- end: `0x1800135f8`
- name: `?_ResetWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(DeviceConfiguration::ConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011c38`

## callees

- `0x18000ba40`
- `0x18000d89c`
- `0x180012a50`
- `0x180012df8`
- `0x180013534`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800135b7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800135b7`

## string_xrefs

- `0x1800135a1`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x1800135d8`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_ResetWindowsProtectedPrint(
        DeviceConfiguration::ConfigurationManager *this)
{
  int v1; // ebx
  unsigned int DwordValue; // eax
  DeviceConfiguration::ConfigurationManager *v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  const char *v11; // [rsp+28h] [rbp-10h]
  const char *v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DeviceConfiguration::ConfigurationManager *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = this;
  LOBYTE(v14) = 0;
  v1 = 0;
  v15 = -2147483646;
  try
  {
    DwordValue = PrintCore::RegHelpers::GetDwordValue(
                   (HKEY *)&v15,
                   L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
                   L"EnabledBy",
                   (bool *)&v14);
    if ( (_BYTE)v14 )
    {
      v4 = DwordValue - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          if ( v5 == 1 )
            v1 = 2;
        }
        else
        {
          v1 = 1;
        }
      }
    }
    v6 = DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(v3);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x17D,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v6,
      (int)"Failed to disable Windows Protected Print mode for reset!",
      v11);
    Sleep(0x1388u);
    v8 = DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint(v7, v1);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x183,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v8,
      (int)"Failed to enable Windows Protected Print mode for reset!",
      v12);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x187,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\conf"
                                         "igurationmanager.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180013534  mov     rax, rsp
0x180013537  mov     [rax+8], rcx
0x18001353b  push    rbx
0x18001353c  sub     rsp, 30h
0x180013540  mov     byte ptr [rax+8], 0
0x180013544  xor     ebx, ebx
0x180013546  mov     qword ptr [rax+10h], 0FFFFFFFF80000002h
0x18001354e  lea     r9, [rax+8]; bool *
0x180013552  lea     r8, aEnabledby; "EnabledBy"
0x180013559  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows "...
0x180013560  lea     rcx, [rax+10h]; HKEY *
0x180013564  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x180013569  cmp     byte ptr [rsp+38h+arg_0], bl
0x18001356d  jz      short loc_180013588
0x18001356f  sub     eax, 1
0x180013572  jz      short loc_180013588
0x180013574  sub     eax, 1
0x180013577  jz      short loc_180013583
0x180013579  cmp     eax, 1
0x18001357c  jnz     short loc_180013588
0x18001357e  lea     ebx, [rax+1]
0x180013581  jmp     short loc_180013588
0x180013583  mov     ebx, 1
0x180013588  call    ?_DisableWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJXZ; DeviceConfiguration::ConfigurationManager::_DisableWindowsProtectedPrint(void)
0x18001358d  mov     rcx, [rsp+38h]; this
0x180013592  lea     rdx, aFailedToDisabl; "Failed to disable Windows Protected Pri"...
0x180013599  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18001359e  mov     r9d, eax; char *
0x1800135a1  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800135a8  mov     edx, 17Dh; void *
0x1800135ad  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800135b2  mov     ecx, 1388h; dwMilliseconds
0x1800135b7  call    cs:__imp_Sleep
0x1800135bd  mov     edx, ebx
0x1800135bf  call    ?_EnableWindowsProtectedPrint@ConfigurationManager@DeviceConfiguration@@AEAAJW4WindowsProtectedPrintConfigurationSource@PrintCore@@@Z; DeviceConfiguration::ConfigurationManager::_EnableWindowsProtectedPrint(PrintCore::WindowsProtectedPrintConfigurationSource)
0x1800135c4  mov     rcx, [rsp+38h]; this
0x1800135c9  lea     rdx, aFailedToEnable; "Failed to enable Windows Protected Prin"...
0x1800135d0  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800135d5  mov     r9d, eax; char *
0x1800135d8  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800135df  mov     edx, 183h; void *
0x1800135e4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800135e9  xor     eax, eax
0x1800135eb  jmp     short loc_1800135F1
0x1800135ed  mov     eax, dword ptr [rsp+38h+arg_0]
0x1800135f1  add     rsp, 30h
0x1800135f5  pop     rbx
0x1800135f6  retn
```
