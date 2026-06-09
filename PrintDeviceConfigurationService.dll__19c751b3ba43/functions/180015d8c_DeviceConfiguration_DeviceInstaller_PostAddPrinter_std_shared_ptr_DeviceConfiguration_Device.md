# DeviceConfiguration::DeviceInstaller::_PostAddPrinter(std::shared_ptr<DeviceConfiguration::Device>)

- ea: `0x180015d8c`
- end: `0x180015e51`
- name: `?_PostAddPrinter@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180014e28`

## callees

- `0x18000af54`
- `0x18000b838`
- `0x180014f80`
- `0x180015ad0`
- `0x180015d8c`
- `0x1800160c0`

## string_xrefs

- `0x180015dd0`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180015e0a`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_PostAddPrinter(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // eax
  std::_Ref_count_base *v9; // rcx
  const char *v11; // [rsp+28h] [rbp-20h]
  _BYTE v12[24]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( *(_BYTE *)(*a2 + 241LL) )
  {
    v3 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v12, a2);
    v5 = DeviceConfiguration::DeviceInstaller::_MarkPrintQueueAsFaxDevice(v4, v3);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xAC,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)v5,
      (int)"Failed to mark print queue as fax device!",
      v11);
  }
  v6 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v12, a2);
  v8 = DeviceConfiguration::DeviceInstaller::_TrySetPsaInformation(v7, v6);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0xB2,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
    (const char *)v8,
    (int)"Failed to set PSA information for the device!",
    v11);
  v9 = (std::_Ref_count_base *)a2[1];
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  return 0;
}

```

## disassembly

```asm
0x180015d8c  mov     [rsp+arg_8], rdx
0x180015d91  mov     [rsp+arg_0], rcx
0x180015d96  push    rbx
0x180015d97  sub     rsp, 40h
0x180015d9b  mov     rbx, rdx
0x180015d9e  mov     rax, [rdx]
0x180015da1  cmp     byte ptr [rax+0F1h], 0
0x180015da8  jz      short loc_180015DE1
0x180015daa  lea     rcx, [rsp+48h+var_18]
0x180015daf  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180015db4  mov     rdx, rax
0x180015db7  call    ?_MarkPrintQueueAsFaxDevice@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z; DeviceConfiguration::DeviceInstaller::_MarkPrintQueueAsFaxDevice(std::shared_ptr<DeviceConfiguration::Device>)
0x180015dbc  mov     rcx, [rsp+48h]; this
0x180015dc1  lea     rdx, aFailedToMarkPr; "Failed to mark print queue as fax devic"...
0x180015dc8  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180015dcd  mov     r9d, eax; char *
0x180015dd0  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015dd7  mov     edx, 0ACh; void *
0x180015ddc  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015de1  mov     rdx, rbx
0x180015de4  lea     rcx, [rsp+48h+var_18]
0x180015de9  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180015dee  mov     rdx, rax
0x180015df1  call    ?_TrySetPsaInformation@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z; DeviceConfiguration::DeviceInstaller::_TrySetPsaInformation(std::shared_ptr<DeviceConfiguration::Device>)
0x180015df6  mov     rcx, [rsp+48h]; this
0x180015dfb  lea     rdx, aFailedToSetPsa_0; "Failed to set PSA information for the d"...
0x180015e02  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180015e07  mov     r9d, eax; char *
0x180015e0a  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015e11  mov     edx, 0B2h; void *
0x180015e16  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015e1b  lea     rax, [rbx+8]
0x180015e1f  mov     [rsp+48h+arg_0], rax
0x180015e24  mov     rcx, [rax]; this
0x180015e27  test    rcx, rcx
0x180015e2a  jz      short loc_180015E31
0x180015e2c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015e31  xor     eax, eax
0x180015e33  jmp     short loc_180015E4B
0x180015e35  mov     rax, [rsp+48h+arg_0]
0x180015e3a  mov     rcx, [rax]; this
0x180015e3d  test    rcx, rcx
0x180015e40  jz      short loc_180015E47
0x180015e42  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015e47  mov     eax, dword ptr [rsp+48h+arg_8]
0x180015e4b  add     rsp, 40h
0x180015e4f  pop     rbx
0x180015e50  retn
```
