# DeviceConfiguration::ConfigurationManager::_RemoveInternetPrintComponents(void)

- ea: `0x180013360`
- end: `0x18001344e`
- name: `?_RemoveInternetPrintComponents@ConfigurationManager@DeviceConfiguration@@AEAAXXZ`
- size: `238`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012df8`

## callees

- `0x18000d89c`
- `0x1800131dc`
- `0x180013360`
- `0x180013454`

## import_xrefs

- `DismApi!DismInitialize` at `0x180013379`
- `DismApi!DismInitialize` at `0x180013379`
- `DismApi!DismCloseSession` at `0x18001341b`
- `DismApi!DismCloseSession` at `0x18001341b`
- `DismApi!DismOpenSession` at `0x1800133b5`
- `DismApi!DismOpenSession` at `0x1800133b5`

## string_xrefs

- `0x180013393`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x1800133cf`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013435`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x1800133c0`: `Failed to open the DISM Session`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_RemoveInternetPrintComponents(
        DeviceConfiguration::ConfigurationManager *this)
{
  unsigned int v1; // eax
  unsigned int v2; // eax
  DeviceConfiguration::ConfigurationManager *v3; // rcx
  DeviceConfiguration::ConfigurationManager *v4; // rcx
  DeviceConfiguration::ConfigurationManager *v5; // rcx
  unsigned int v6; // eax
  const char *v7; // r9
  const char *v8; // [rsp+28h] [rbp-10h]
  const char *v9; // [rsp+28h] [rbp-10h]
  const char *v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v12; // [rsp+40h] [rbp+8h] BYREF
  int v13; // [rsp+44h] [rbp+Ch]

  v13 = HIDWORD(this);
  v12 = -1073479676;
  v1 = DismInitialize(2, 0, 0);
  try
  {
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x2DE,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v1,
      (int)"Failed to initialize DISM",
      v8);
    v2 = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x2DF,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v2,
      (int)"Failed to open the DISM Session",
      v9);
    if ( DeviceConfiguration::ConfigurationManager::_IsClientSKU(v3) )
    {
      DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(
        v4,
        v12,
        (const char *)L"Printing-Foundation-InternetPrinting-Client");
    }
    else
    {
      DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(
        v4,
        v12,
        (const char *)L"Printing-InternetPrinting-Server");
      DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(
        v5,
        v12,
        (const char *)L"Printing-InternetPrinting-Client");
    }
    v6 = DismCloseSession(v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v6,
      (int)"Failed to close the DISM Session",
      v10);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2EE,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x180013360  mov     qword ptr [rsp+arg_0], rcx
0x180013365  sub     rsp, 38h
0x180013369  mov     [rsp+38h+arg_0], 0C0040004h
0x180013371  xor     r8d, r8d
0x180013374  xor     edx, edx
0x180013376  lea     ecx, [rdx+2]
0x180013379  call    cs:__imp_DismInitialize
0x18001337f  mov     rcx, [rsp+38h]; this
0x180013384  lea     rdx, aFailedToInitia; "Failed to initialize DISM"
0x18001338b  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180013390  mov     r9d, eax; char *
0x180013393  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x18001339a  mov     edx, 2DEh; void *
0x18001339f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800133a4  lea     r9, [rsp+38h+arg_0]
0x1800133a9  xor     r8d, r8d
0x1800133ac  xor     edx, edx
0x1800133ae  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x1800133b5  call    cs:__imp_DismOpenSession
0x1800133bb  mov     rcx, [rsp+38h]; this
0x1800133c0  lea     rdx, aFailedToOpenTh_0; "Failed to open the DISM Session"
0x1800133c7  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800133cc  mov     r9d, eax; char *
0x1800133cf  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800133d6  mov     edx, 2DFh; void *
0x1800133db  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800133e0  call    ?_IsClientSKU@ConfigurationManager@DeviceConfiguration@@AEAA_NXZ; DeviceConfiguration::ConfigurationManager::_IsClientSKU(void)
0x1800133e5  mov     edx, [rsp+38h+arg_0]; unsigned int
0x1800133e9  test    al, al
0x1800133eb  jz      short loc_1800133FB
0x1800133ed  lea     r8, aPrintingFounda; "Printing-Foundation-InternetPrinting-Cl"...
0x1800133f4  call    ?_RemoveRoleOrFeature@ConfigurationManager@DeviceConfiguration@@AEAAXIPEBG@Z; DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(uint,ushort const *)
0x1800133f9  jmp     short loc_180013417
0x1800133fb  lea     r8, aPrintingIntern; "Printing-InternetPrinting-Server"
0x180013402  call    ?_RemoveRoleOrFeature@ConfigurationManager@DeviceConfiguration@@AEAAXIPEBG@Z; DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(uint,ushort const *)
0x180013407  lea     r8, aPrintingIntern_0; "Printing-InternetPrinting-Client"
0x18001340e  mov     edx, [rsp+38h+arg_0]; unsigned int
0x180013412  call    ?_RemoveRoleOrFeature@ConfigurationManager@DeviceConfiguration@@AEAAXIPEBG@Z; DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(uint,ushort const *)
0x180013417  mov     ecx, [rsp+38h+arg_0]
0x18001341b  call    cs:__imp_DismCloseSession
0x180013421  mov     rcx, [rsp+38h]; this
0x180013426  lea     rdx, aFailedToCloseT; "Failed to close the DISM Session"
0x18001342d  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180013432  mov     r9d, eax; char *
0x180013435  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x18001343c  mov     edx, 2ECh; void *
0x180013441  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013446  nop
0x180013447  jmp     short $+2
0x180013449  add     rsp, 38h
0x18001344d  retn
```
