# DeviceConfiguration::Device::RestartDevice(void)

- ea: `0x18001481c`
- end: `0x180014973`
- name: `?RestartDevice@Device@DeviceConfiguration@@QEAAJXZ`
- size: `343`
- prototype: `__int64 __fastcall(DeviceConfiguration::Device *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000fad4`

## callees

- `0x1800020c0`
- `0x18000aeac`
- `0x18000f9ec`
- `0x1800143e8`
- `0x18001481c`

## import_xrefs

- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001489b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001489b`
- `DEVOBJ!DevObjChangeState` at `0x18001490d`
- `DEVOBJ!DevObjChangeState` at `0x18001490d`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1800148c9`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1800148c9`

## string_xrefs

- `0x1800148ec`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`
- `0x180014930`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`
- `0x180014851`: `DeviceConfiguration::Device::RestartDevice`
- `0x1800148dc`: `DevObjOpenDeviceInfo failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::RestartDevice(DeviceConfiguration::Device *this)
{
  DeviceConfiguration::Device *v1; // rdi
  DeviceConfiguration::Device *v2; // r8
  __int64 DeviceInfoList; // rbx
  int v4; // eax
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  const char *v8; // [rsp+28h] [rbp-60h]
  const char *v9; // [rsp+28h] [rbp-60h]
  __int64 v10; // [rsp+30h] [rbp-58h] BYREF
  int v11; // [rsp+38h] [rbp-50h] BYREF
  __int64 v12; // [rsp+3Ch] [rbp-4Ch]
  _OWORD v13[3]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = this;
  if ( *((_QWORD *)this + 3) <= 7u )
    v2 = this;
  else
    v2 = *(DeviceConfiguration::Device **)this;
  DeviceConfigurationTelemetry::WriteDbgTraceInfo(
    "DeviceConfiguration::Device::RestartDevice",
    L"Restarting device %ws",
    v2);
  memset(v13, 0, sizeof(v13));
  LODWORD(v13[0]) = 48;
  v11 = 3;
  v12 = 1;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v10 = DeviceInfoList;
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(DeviceConfiguration::Device **)v1;
  v4 = DevObjOpenDeviceInfo(DeviceInfoList, v1, 0, 0, v13);
  try
  {
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xED,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
      (const char *)(v4 == 0),
      (bool)"DevObjOpenDeviceInfo failed!",
      v8);
    v5 = DevObjChangeState(DeviceInfoList, v13, &v11, 0);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xEE,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
      (const char *)(v5 == 0),
      (bool)"DevObjChangeState",
      v9);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF2,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18001481c  mov     [rsp+arg_8], rbx
0x180014821  push    rdi
0x180014822  sub     rsp, 80h
0x180014829  mov     rax, cs:__security_cookie
0x180014830  xor     rax, rsp
0x180014833  mov     [rsp+88h+var_10], rax
0x180014838  mov     rdi, rcx
0x18001483b  cmp     qword ptr [rcx+18h], 7
0x180014840  jbe     short loc_180014847
0x180014842  mov     r8, [rcx]
0x180014845  jmp     short loc_18001484A
0x180014847  mov     r8, rdi
0x18001484a  lea     rdx, aRestartingDevi; "Restarting device %ws"
0x180014851  lea     rcx, aDeviceconfigur_2; "DeviceConfiguration::Device::RestartDev"...
0x180014858  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001485d  xorps   xmm0, xmm0
0x180014860  movups  [rsp+88h+var_40], xmm0
0x180014865  movups  [rsp+88h+var_30], xmm0
0x18001486a  movups  [rsp+88h+var_20], xmm0
0x18001486f  mov     dword ptr [rsp+88h+var_40], 30h ; '0'
0x180014877  mov     [rsp+88h+var_50], 3
0x18001487f  mov     [rsp+88h+var_4C], 1
0x180014888  mov     qword ptr [rsp+88h+var_68], 0
0x180014891  xor     r9d, r9d
0x180014894  xor     r8d, r8d
0x180014897  xor     edx, edx
0x180014899  xor     ecx, ecx
0x18001489b  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800148a1  mov     rbx, rax
0x1800148a4  mov     [rsp+88h+var_58], rax
0x1800148a9  cmp     qword ptr [rdi+18h], 7
0x1800148ae  jbe     short loc_1800148B3
0x1800148b0  mov     rdi, [rdi]
0x1800148b3  lea     rax, [rsp+88h+var_40]
0x1800148b8  mov     qword ptr [rsp+88h+var_68], rax
0x1800148bd  xor     r9d, r9d
0x1800148c0  xor     r8d, r8d
0x1800148c3  mov     rdx, rdi
0x1800148c6  mov     rcx, rbx
0x1800148c9  call    cs:__imp_DevObjOpenDeviceInfo
0x1800148cf  test    eax, eax
0x1800148d1  setz    al
0x1800148d4  mov     rcx, [rsp+88h]; this
0x1800148dc  lea     rdx, aDevobjopendevi_0; "DevObjOpenDeviceInfo failed!"
0x1800148e3  mov     qword ptr [rsp+88h+var_68], rdx; bool
0x1800148e8  movzx   r9d, al; char *
0x1800148ec  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x1800148f3  mov     edx, 0EDh; void *
0x1800148f8  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800148fd  xor     r9d, r9d
0x180014900  lea     r8, [rsp+88h+var_50]
0x180014905  lea     rdx, [rsp+88h+var_40]
0x18001490a  mov     rcx, rbx
0x18001490d  call    cs:__imp_DevObjChangeState
0x180014913  test    eax, eax
0x180014915  setz    al
0x180014918  mov     rcx, [rsp+88h]; this
0x180014920  lea     rdx, aDevobjchangest_0; "DevObjChangeState"
0x180014927  mov     qword ptr [rsp+88h+var_68], rdx; bool
0x18001492c  movzx   r9d, al; char *
0x180014930  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x180014937  mov     edx, 0EEh; void *
0x18001493c  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180014941  nop
0x180014942  lea     rcx, [rsp+88h+var_58]
0x180014947  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18001494c  xor     eax, eax
0x18001494e  jmp     short loc_180014954
0x180014950  mov     eax, dword ptr [rsp+88h+var_58]
0x180014954  mov     rcx, [rsp+88h+var_10]
0x180014959  xor     rcx, rsp; StackCookie
0x18001495c  call    __security_check_cookie
0x180014961  mov     rbx, [rsp+88h+arg_8]
0x180014969  add     rsp, 80h
0x180014970  pop     rdi
0x180014971  retn
```
