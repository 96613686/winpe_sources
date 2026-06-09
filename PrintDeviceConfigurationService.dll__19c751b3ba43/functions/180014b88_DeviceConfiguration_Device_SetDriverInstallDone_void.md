# DeviceConfiguration::Device::SetDriverInstallDone(void)

- ea: `0x180014b88`
- end: `0x180014c3e`
- name: `?SetDriverInstallDone@Device@DeviceConfiguration@@QEAAJXZ`
- size: `182`
- prototype: `__int64 __fastcall(DeviceConfiguration::Device *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000fad4`

## callees

- `0x1800020c0`
- `0x18000d89c`
- `0x180014b88`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180014bf8`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180014bf8`

## string_xrefs

- `0x180014c12`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`
- `0x180014c03`: `DevSetObjectProperties for PKEY_Printer_DriverInstallDone failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::SetDriverInstallDone(DeviceConfiguration::Device *this)
{
  unsigned int v1; // eax
  const char *v2; // r9
  __int64 result; // rax
  const char *v4; // [rsp+28h] [rbp-50h]
  __int128 v5; // [rsp+38h] [rbp-40h] BYREF
  int v6; // [rsp+48h] [rbp-30h]
  int v7; // [rsp+4Ch] [rbp-2Ch]
  __int64 v8; // [rsp+50h] [rbp-28h]
  int v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+5Ch] [rbp-1Ch]
  char *v11; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = xmmword_18001E4B0;
  v6 = 5;
  v7 = 0;
  v8 = 0;
  v9 = 17;
  v10 = 1;
  v11 = &byte_1800241F8;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(DeviceConfiguration::Device **)this;
  v1 = DevSetObjectProperties(3, this, 1, &v5);
  try
  {
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xA0,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
      (const char *)v1,
      (int)"DevSetObjectProperties for PKEY_Printer_DriverInstallDone failed!",
      v4);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA4,
                           (int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180014b88  sub     rsp, 78h
0x180014b8c  mov     rax, cs:__security_cookie
0x180014b93  xor     rax, rsp
0x180014b96  mov     [rsp+78h+var_10], rax
0x180014b9b  movups  xmm0, cs:xmmword_18001E4B0
0x180014ba2  movups  [rsp+78h+var_40], xmm0
0x180014ba7  mov     eax, cs:dword_18001E4C0
0x180014bad  mov     [rsp+78h+var_30], eax
0x180014bb1  mov     [rsp+78h+var_2C], 0
0x180014bb9  mov     [rsp+78h+var_28], 0
0x180014bc2  mov     [rsp+78h+var_20], 11h
0x180014bca  mov     r8d, 1
0x180014bd0  mov     [rsp+78h+var_1C], r8d
0x180014bd5  lea     rax, byte_1800241F8
0x180014bdc  mov     [rsp+78h+var_18], rax
0x180014be1  cmp     qword ptr [rcx+18h], 7
0x180014be6  jbe     short loc_180014BEB
0x180014be8  mov     rcx, [rcx]
0x180014beb  lea     r9, [rsp+78h+var_40]
0x180014bf0  mov     rdx, rcx
0x180014bf3  mov     ecx, 3
0x180014bf8  call    cs:__imp_DevSetObjectProperties
0x180014bfe  mov     rcx, [rsp+78h]; this
0x180014c03  lea     rdx, aDevsetobjectpr_2; "DevSetObjectProperties for PKEY_Printer"...
0x180014c0a  mov     qword ptr [rsp+78h+var_58], rdx; int
0x180014c0f  mov     r9d, eax; char *
0x180014c12  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x180014c19  mov     edx, 0A0h; void *
0x180014c1e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014c23  xor     eax, eax
0x180014c25  jmp     short loc_180014C2B
0x180014c27  mov     eax, [rsp+78h+var_48]
0x180014c2b  mov     rcx, [rsp+78h+var_10]
0x180014c30  xor     rcx, rsp; StackCookie
0x180014c33  call    __security_check_cookie
0x180014c38  add     rsp, 78h
0x180014c3c  retn
```
