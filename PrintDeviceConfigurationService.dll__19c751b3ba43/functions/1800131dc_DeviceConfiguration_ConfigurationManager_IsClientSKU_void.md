# DeviceConfiguration::ConfigurationManager::_IsClientSKU(void)

- ea: `0x1800131dc`
- end: `0x18001326e`
- name: `?_IsClientSKU@ConfigurationManager@DeviceConfiguration@@AEAA_NXZ`
- size: `146`
- prototype: `bool __fastcall(DeviceConfiguration::ConfigurationManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180013360`
- `0x180013b24`

## callees

- `0x1800020c0`
- `0x180002b28`
- `0x18000d8e4`
- `0x1800131dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180013214`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180013214`

## string_xrefs

- `0x18001322e`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
bool __fastcall DeviceConfiguration::ConfigurationManager::_IsClientSKU(
        DeviceConfiguration::ConfigurationManager *this)
{
  unsigned int Version; // eax
  const char *v3; // [rsp+28h] [rbp-140h]
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-138h] BYREF
  char v5; // [rsp+14Ah] [rbp-1Eh]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = GetVersionExW(&VersionInformation);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x241,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)Version,
    (int)"GetVersionEx failed!",
    v3);
  return v5 != 2 && v5 != 3;
}

```

## disassembly

```asm
0x1800131dc  sub     rsp, 168h
0x1800131e3  mov     rax, cs:__security_cookie
0x1800131ea  xor     rax, rsp
0x1800131ed  mov     [rsp+168h+var_18], rax
0x1800131f5  xor     edx, edx; Val
0x1800131f7  lea     rcx, [rsp+168h+VersionInformation.dwMajorVersion]; void *
0x1800131fc  mov     r8d, 118h; Size
0x180013202  call    memset_0
0x180013207  lea     rcx, [rsp+168h+VersionInformation]; lpVersionInformation
0x18001320c  mov     [rsp+168h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180013214  call    cs:__imp_GetVersionExW
0x18001321a  mov     rcx, [rsp+168h]; this
0x180013222  lea     rdx, aGetversionexFa; "GetVersionEx failed!"
0x180013229  mov     qword ptr [rsp+168h+var_148], rdx; int
0x18001322e  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013235  mov     edx, 241h; void *
0x18001323a  mov     r9d, eax; char *
0x18001323d  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180013242  mov     al, [rsp+168h+var_1E]
0x180013249  cmp     al, 2
0x18001324b  jz      short loc_180013254
0x18001324d  cmp     al, 3
0x18001324f  setnz   al
0x180013252  jmp     short loc_180013256
0x180013254  xor     al, al
0x180013256  mov     rcx, [rsp+168h+var_18]
0x18001325e  xor     rcx, rsp; StackCookie
0x180013261  call    __security_check_cookie
0x180013266  add     rsp, 168h
0x18001326d  retn
```
