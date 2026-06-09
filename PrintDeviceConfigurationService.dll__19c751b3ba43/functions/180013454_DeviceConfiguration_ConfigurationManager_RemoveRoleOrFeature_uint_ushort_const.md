# DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(uint,ushort const *)

- ea: `0x180013454`
- end: `0x18001352b`
- name: `?_RemoveRoleOrFeature@ConfigurationManager@DeviceConfiguration@@AEAAXIPEBG@Z`
- size: `215`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *this, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180013360`

## callees

- `0x18000d89c`
- `0x180011c0c`
- `0x180013454`

## import_xrefs

- `DismApi!DismDisableFeature` at `0x1800134e5`
- `DismApi!DismDisableFeature` at `0x1800134e5`
- `DismApi!DismGetFeatureInfo` at `0x180013484`
- `DismApi!DismGetFeatureInfo` at `0x180013484`

## string_xrefs

- `0x1800134a3`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013504`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x1800134f5`: `Could not remove the Feature: %ws`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_RemoveRoleOrFeature(
        DeviceConfiguration::ConfigurationManager *this,
        unsigned int a2,
        const char *a3)
{
  unsigned int FeatureInfo; // eax
  unsigned int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = 0;
  FeatureInfo = DismGetFeatureInfo(a2, a3, 0, 0, &v8);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2D3,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)FeatureInfo,
    (int)"Failed to get DISM Feature Info: %ws",
    a3);
  if ( *(_DWORD *)(v8 + 8) == 4 )
  {
    v6 = DismDisableFeature(a2, a3, 0, 0, 0, 0, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v6,
      (int)"Could not remove the Feature: %ws",
      a3);
  }
  wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(&v8);
}

```

## disassembly

```asm
0x180013454  mov     r11, rsp
0x180013457  mov     [r11+10h], rbx
0x18001345b  mov     [r11+8], rcx
0x18001345f  push    rdi
0x180013460  sub     rsp, 40h
0x180013464  mov     rbx, r8
0x180013467  mov     edi, edx
0x180013469  mov     qword ptr [r11+8], 0
0x180013471  lea     rax, [r11+8]
0x180013475  mov     [r11-28h], rax
0x180013479  xor     r9d, r9d
0x18001347c  xor     r8d, r8d
0x18001347f  mov     rdx, rbx
0x180013482  mov     ecx, edi
0x180013484  call    cs:__imp_DismGetFeatureInfo
0x18001348a  mov     rcx, [rsp+48h]; this
0x18001348f  mov     [rsp+48h+var_20], rbx; char *
0x180013494  lea     rdx, aFailedToGetDis; "Failed to get DISM Feature Info: %ws"
0x18001349b  mov     qword ptr [rsp+48h+var_28], rdx; int
0x1800134a0  mov     r9d, eax; char *
0x1800134a3  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800134aa  mov     edx, 2D3h; void *
0x1800134af  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800134b4  mov     rax, [rsp+48h+arg_0]
0x1800134b9  cmp     dword ptr [rax+8], 4
0x1800134bd  jnz     short loc_180013516
0x1800134bf  mov     [rsp+48h+var_18], 0
0x1800134c8  mov     [rsp+48h+var_20], 0
0x1800134d1  mov     qword ptr [rsp+48h+var_28], 0
0x1800134da  xor     r9d, r9d
0x1800134dd  xor     r8d, r8d
0x1800134e0  mov     rdx, rbx
0x1800134e3  mov     ecx, edi
0x1800134e5  call    cs:__imp_DismDisableFeature
0x1800134eb  mov     rcx, [rsp+48h]; this
0x1800134f0  mov     [rsp+48h+var_20], rbx; char *
0x1800134f5  lea     rdx, aCouldNotRemove; "Could not remove the Feature: %ws"
0x1800134fc  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180013501  mov     r9d, eax; char *
0x180013504  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x18001350b  mov     edx, 2D6h; void *
0x180013510  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013515  nop
0x180013516  lea     rcx, [rsp+48h+arg_0]
0x18001351b  call    ??1?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@P6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(void)
0x180013520  mov     rbx, [rsp+48h+arg_8]
0x180013525  add     rsp, 40h
0x180013529  pop     rdi
0x18001352a  retn
```
