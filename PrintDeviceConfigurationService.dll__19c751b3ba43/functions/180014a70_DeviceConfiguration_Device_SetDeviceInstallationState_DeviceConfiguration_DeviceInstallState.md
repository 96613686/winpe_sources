# DeviceConfiguration::Device::SetDeviceInstallationState(DeviceConfiguration::DeviceInstallState)

- ea: `0x180014a70`
- end: `0x180014b81`
- name: `?SetDeviceInstallationState@Device@DeviceConfiguration@@QEAAJW4DeviceInstallState@2@@Z`
- size: `273`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000ed18`
- `0x180010ca4`

## callees

- `0x1800020c0`
- `0x18000d89c`
- `0x180014358`
- `0x180014a70`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180014b31`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180014b31`

## string_xrefs

- `0x180014b4e`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\device.cpp`
- `0x180014b3f`: `DevSetObjectProperties for PKEY_Printer_DeviceInstallState failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::SetDeviceInstallationState(__int64 a1, int a2)
{
  __int64 *v2; // rax
  __int64 *v3; // rdx
  unsigned int v4; // eax
  const char *v6; // [rsp+28h] [rbp-80h]
  int v7; // [rsp+30h] [rbp-78h] BYREF
  int v8; // [rsp+34h] [rbp-74h] BYREF
  __int64 v9; // [rsp+38h] [rbp-70h]
  __int64 v10; // [rsp+40h] [rbp-68h]
  char v11; // [rsp+48h] [rbp-60h]
  _BYTE v12[16]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v13; // [rsp+60h] [rbp-48h] BYREF
  int v14; // [rsp+70h] [rbp-38h]
  int v15; // [rsp+74h] [rbp-34h]
  __int64 v16; // [rsp+78h] [rbp-30h]
  int v17; // [rsp+80h] [rbp-28h]
  int v18; // [rsp+84h] [rbp-24h]
  int *v19; // [rsp+88h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v8 = *(_DWORD *)(a1 + 252);
  *(_DWORD *)(a1 + 252) = a2;
  v2 = (__int64 *)lambda_e4087390eaf4aaeb7fa1a8b5d2ba85de_::_lambda_e4087390eaf4aaeb7fa1a8b5d2ba85de_(v12, a1, &v8);
  v9 = *v2;
  v10 = v2[1];
  v11 = 1;
  v7 = *((_DWORD *)v3 + 63);
  v13 = xmmword_18001E498;
  v14 = 7;
  v15 = 0;
  v16 = 0;
  v17 = 7;
  v18 = 4;
  v19 = &v7;
  if ( (unsigned __int64)v3[3] > 7 )
    v3 = (__int64 *)*v3;
  v4 = DevSetObjectProperties(3, v3, 1, &v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xDE,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
    (const char *)v4,
    (int)"DevSetObjectProperties for PKEY_Printer_DeviceInstallState failed!",
    v6);
  return 0;
}

```

## disassembly

```asm
0x180014a70  sub     rsp, 0A8h
0x180014a77  mov     rax, cs:__security_cookie
0x180014a7e  xor     rax, rsp
0x180014a81  mov     [rsp+0A8h+var_18], rax
0x180014a89  mov     r8d, edx
0x180014a8c  mov     rdx, rcx
0x180014a8f  mov     eax, [rcx+0FCh]
0x180014a95  mov     [rsp+0A8h+var_74], eax
0x180014a99  mov     [rcx+0FCh], r8d
0x180014aa0  lea     r8, [rsp+0A8h+var_74]
0x180014aa5  lea     rcx, [rsp+0A8h+var_58]
0x180014aaa  call    _lambda_e4087390eaf4aaeb7fa1a8b5d2ba85de____lambda_e4087390eaf4aaeb7fa1a8b5d2ba85de_
0x180014aaf  mov     rcx, [rax]
0x180014ab2  mov     [rsp+0A8h+var_70], rcx
0x180014ab7  mov     rax, [rax+8]
0x180014abb  mov     [rsp+0A8h+var_68], rax
0x180014ac0  mov     [rsp+0A8h+var_60], 1
0x180014ac5  mov     eax, [rdx+0FCh]
0x180014acb  mov     [rsp+0A8h+var_78], eax
0x180014acf  movups  xmm0, cs:xmmword_18001E498
0x180014ad6  movups  [rsp+0A8h+var_48], xmm0
0x180014adb  mov     eax, cs:dword_18001E4A8
0x180014ae1  mov     [rsp+0A8h+var_38], eax
0x180014ae5  mov     [rsp+0A8h+var_34], 0
0x180014aed  mov     [rsp+0A8h+var_30], 0
0x180014af6  mov     [rsp+0A8h+var_28], 7
0x180014b01  mov     [rsp+0A8h+var_24], 4
0x180014b0c  lea     rax, [rsp+0A8h+var_78]
0x180014b11  mov     [rsp+0A8h+var_20], rax
0x180014b19  cmp     qword ptr [rdx+18h], 7
0x180014b1e  jbe     short loc_180014B23
0x180014b20  mov     rdx, [rdx]
0x180014b23  lea     r9, [rsp+0A8h+var_48]
0x180014b28  mov     ecx, 3
0x180014b2d  lea     r8d, [rcx-2]
0x180014b31  call    cs:__imp_DevSetObjectProperties
0x180014b37  mov     rcx, [rsp+0A8h]; this
0x180014b3f  lea     rdx, aDevsetobjectpr_1; "DevSetObjectProperties for PKEY_Printer"...
0x180014b46  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x180014b4b  mov     r9d, eax; char *
0x180014b4e  lea     r8, aPrintscanPrint_3; "printscan\\print\\spooler\\configuratio"...
0x180014b55  mov     edx, 0DEh; void *
0x180014b5a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014b5f  nop
0x180014b60  xor     eax, eax
0x180014b62  jmp     short loc_180014B68
0x180014b64  mov     eax, [rsp+0A8h+var_78]
0x180014b68  mov     rcx, [rsp+0A8h+var_18]
0x180014b70  xor     rcx, rsp; StackCookie
0x180014b73  call    __security_check_cookie
0x180014b78  add     rsp, 0A8h
0x180014b7f  retn
```
