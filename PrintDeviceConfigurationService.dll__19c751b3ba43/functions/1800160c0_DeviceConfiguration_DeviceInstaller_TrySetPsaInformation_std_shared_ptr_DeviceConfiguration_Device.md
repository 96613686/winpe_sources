# DeviceConfiguration::DeviceInstaller::_TrySetPsaInformation(std::shared_ptr<DeviceConfiguration::Device>)

- ea: `0x1800160c0`
- end: `0x180016166`
- name: `?_TrySetPsaInformation@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, DeviceConfiguration::Device **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180015d8c`

## callees

- `0x18000af54`
- `0x18000d89c`
- `0x18001497c`
- `0x180014c44`
- `0x1800160c0`

## string_xrefs

- `0x1800160f8`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180016125`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_TrySetPsaInformation(
        __int64 a1,
        DeviceConfiguration::Device **a2)
{
  unsigned int PsaInfo; // eax
  unsigned int v4; // eax
  const char *v5; // r9
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v8; // rcx
  const char *v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v11; // [rsp+40h] [rbp+8h]

  try
  {
    if ( !*((_QWORD *)*a2 + 26) )
    {
      PsaInfo = DeviceConfiguration::Device::RetrievePsaInfo(*a2);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x170,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
        (const char *)PsaInfo,
        (int)"Failed to retrieve PSA information!",
        v9);
    }
    v4 = DeviceConfiguration::Device::SetPsaInfoForPrinter(*a2);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x173,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)v4,
      (int)"Failed to set PSA information!",
      v9);
  }
  catch ( ... )
  {
    v11 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x177,
            (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
            v5);
    v8 = a2[1];
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    return v11;
  }
  v6 = a2[1];
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return 0;
}

```

## disassembly

```asm
0x1800160c0  mov     [rsp+arg_8], rdx
0x1800160c5  mov     [rsp+arg_0], rcx
0x1800160ca  push    rbx
0x1800160cb  sub     rsp, 30h
0x1800160cf  mov     rbx, rdx
0x1800160d2  mov     rcx, [rdx]; this
0x1800160d5  cmp     qword ptr [rcx+0D0h], 0
0x1800160dd  jnz     short loc_180016109
0x1800160df  call    ?RetrievePsaInfo@Device@DeviceConfiguration@@QEAAJXZ; DeviceConfiguration::Device::RetrievePsaInfo(void)
0x1800160e4  mov     rcx, [rsp+38h]; this
0x1800160e9  lea     rdx, aFailedToRetrie_0; "Failed to retrieve PSA information!"
0x1800160f0  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800160f5  mov     r9d, eax; char *
0x1800160f8  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800160ff  mov     edx, 170h; void *
0x180016104  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016109  mov     rcx, [rbx]; this
0x18001610c  call    ?SetPsaInfoForPrinter@Device@DeviceConfiguration@@QEAAJXZ; DeviceConfiguration::Device::SetPsaInfoForPrinter(void)
0x180016111  mov     rcx, [rsp+38h]; this
0x180016116  lea     rdx, aFailedToSetPsa; "Failed to set PSA information!"
0x18001611d  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180016122  mov     r9d, eax; char *
0x180016125  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x18001612c  mov     edx, 173h; void *
0x180016131  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016136  nop
0x180016137  mov     rcx, [rbx+8]; this
0x18001613b  test    rcx, rcx
0x18001613e  jz      short loc_180016145
0x180016140  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016145  xor     eax, eax
0x180016147  jmp     short loc_180016160
0x180016149  mov     rax, [rsp+38h+arg_8]
0x18001614e  mov     rcx, [rax+8]; this
0x180016152  test    rcx, rcx
0x180016155  jz      short loc_18001615C
0x180016157  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001615c  mov     eax, dword ptr [rsp+38h+arg_0]
0x180016160  add     rsp, 30h
0x180016164  pop     rbx
0x180016165  retn
```
