# DeviceConfiguration::Device::SetPsaInfoForPrinter(void)

- ea: `0x180014c44`
- end: `0x180014d30`
- name: `?SetPsaInfoForPrinter@Device@DeviceConfiguration@@QEAAJXZ`
- size: `236`
- prototype: `__int64 __fastcall(DeviceConfiguration::Device *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800160c0`

## callees

- `0x18000aeac`
- `0x18000c158`
- `0x180014c44`
- `0x180014d38`

## import_xrefs

- `WINSPOOL!SetPrinterDataExW` at `0x180014cf6`
- `WINSPOOL!SetPrinterDataExW` at `0x180014cf6`

## string_xrefs

- `0x180014ca8`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`
- `0x180014d10`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`
- `0x180014c62`: `DeviceConfiguration::Device::SetPsaInfoForPrinter`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::SetPsaInfoForPrinter(DeviceConfiguration::Device *this)
{
  const char *v2; // rdx
  BYTE *pData; // rax
  DWORD v4; // eax
  const char *v5; // r9
  __int64 result; // rax
  const char *cbData; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::Device::SetPsaInfoForPrinter",
    L"Setting PSA Package Id on printer %ws");
  if ( *((_QWORD *)this + 3) <= 7u )
    v2 = (const char *)this;
  else
    v2 = *(const char **)this;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xF9,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
      (const char *)0x80070057LL,
      *((_QWORD *)this + 26) == 0,
      (bool)"PSA AUMID info is not available for device %ws",
      v2);
    pData = (BYTE *)this + 192;
    if ( *((_QWORD *)this + 27) > 7u )
      pData = *(BYTE **)pData;
    v4 = SetPrinterDataExW(*((HANDLE *)this + 33), L"PnPData", L"PSAPackageId", 1u, pData, 2 * *((_DWORD *)this + 52));
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xFB,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
      (const char *)v4,
      (unsigned int)"Failed to set the PSA Package Id!",
      cbData);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xFF,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180014c44  push    rbx
0x180014c46  sub     rsp, 40h
0x180014c4a  mov     rbx, rcx
0x180014c4d  lea     r8, [rcx+20h]
0x180014c51  cmp     qword ptr [r8+18h], 7
0x180014c56  jbe     short loc_180014C5B
0x180014c58  mov     r8, [r8]
0x180014c5b  lea     rdx, aSettingPsaPack; "Setting PSA Package Id on printer %ws"
0x180014c62  lea     rcx, aDeviceconfigur_5; "DeviceConfiguration::Device::SetPsaInfo"...
0x180014c69  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014c6e  cmp     qword ptr [rbx+18h], 7
0x180014c73  jbe     short loc_180014C7A
0x180014c75  mov     rdx, [rbx]
0x180014c78  jmp     short loc_180014C7D
0x180014c7a  mov     rdx, rbx
0x180014c7d  cmp     qword ptr [rbx+0D0h], 0
0x180014c85  setz    al
0x180014c88  mov     rcx, [rsp+48h]; this
0x180014c8d  mov     [rsp+48h+var_18], rdx; char *
0x180014c92  lea     rdx, aPsaAumidInfoIs; "PSA AUMID info is not available for dev"...
0x180014c99  mov     qword ptr [rsp+48h+cbData], rdx; bool
0x180014c9e  mov     byte ptr [rsp+48h+pData], al; char
0x180014ca2  mov     r9d, 80070057h; char *
0x180014ca8  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x180014caf  mov     edx, 0F9h; void *
0x180014cb4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180014cb9  mov     ecx, [rbx+0D0h]
0x180014cbf  add     ecx, ecx
0x180014cc1  lea     rax, [rbx+0C0h]
0x180014cc8  cmp     qword ptr [rax+18h], 7
0x180014ccd  jbe     short loc_180014CD2
0x180014ccf  mov     rax, [rax]
0x180014cd2  mov     [rsp+48h+cbData], ecx; char *
0x180014cd6  mov     [rsp+48h+pData], rax; pData
0x180014cdb  mov     r9d, 1; Type
0x180014ce1  lea     r8, pValueName; "PSAPackageId"
0x180014ce8  lea     rdx, pKeyName; "PnPData"
0x180014cef  mov     rcx, [rbx+108h]; hPrinter
0x180014cf6  call    cs:__imp_SetPrinterDataExW
0x180014cfc  mov     r9d, eax; char *
0x180014cff  mov     rcx, [rsp+48h]; this
0x180014d04  lea     rax, aFailedToSetThe; "Failed to set the PSA Package Id!"
0x180014d0b  mov     [rsp+48h+pData], rax; unsigned int
0x180014d10  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x180014d17  mov     edx, 0FBh; void *
0x180014d1c  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180014d21  xor     eax, eax
0x180014d23  jmp     short loc_180014D29
0x180014d25  mov     eax, [rsp+48h+arg_0]
0x180014d29  add     rsp, 40h
0x180014d2d  pop     rbx
0x180014d2e  retn
```
