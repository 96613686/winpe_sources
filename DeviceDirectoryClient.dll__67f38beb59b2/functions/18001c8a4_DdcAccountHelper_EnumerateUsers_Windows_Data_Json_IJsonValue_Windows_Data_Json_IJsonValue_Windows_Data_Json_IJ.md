# DdcAccountHelper::EnumerateUsers(Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *,ulong *)

- ea: `0x18001c8a4`
- end: `0x18001c972`
- name: `?EnumerateUsers@DdcAccountHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@000PEAK111@Z`
- size: `206`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonValue **, struct Windows::Data::Json::IJsonValue **, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000921c`
- `0x18000c034`
- `0x1800107e0`

## callees

- `0x1800050b8`
- `0x18001bf54`
- `0x18001c8a4`

## string_xrefs

- `0x18001c956`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcAccountHelper::EnumerateUsers(
        struct Windows::Data::Json::IJsonValue **a1,
        struct Windows::Data::Json::IJsonValue **a2,
        struct Windows::Data::Json::IJsonValue **a3,
        struct Windows::Data::Json::IJsonValue **a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  int v8; // edx
  int v9; // ecx
  int v10; // ebx
  int v11; // edx
  int v12; // ecx

  v10 = DdcAccountHelper::EnumerateUsers(0, a1, a2, a3, a5, a6, a7);
  if ( v10 >= 0 )
  {
    v10 = DdcAccountHelper::EnumerateUsers(1u, a4, 0, 0, 0, 0, 0);
    if ( v10 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        v10,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
        33,
        "CHR(EnumerateUsers(1, ppConnectedAdmins, nullptr, nullptr, pcConnectedAdmins, nullptr, nullptr))");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v9,
      v8,
      v10,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcaccounthelper.cpp",
      32,
      "CHR(EnumerateUsers(0, ppAdmins, ppDeviceOwners, ppStandardUsers, pcAdmins, pcDeviceOwners, pcStandardUsers))");
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c8a4  mov     r11, rsp
0x18001c8a7  mov     [r11+8], rbx
0x18001c8ab  push    rdi
0x18001c8ac  sub     rsp, 40h
0x18001c8b0  mov     rax, [rsp+48h+arg_30]
0x18001c8b8  mov     rdi, r9
0x18001c8bb  mov     [r11-18h], rax
0x18001c8bf  mov     r9, r8; struct Windows::Data::Json::IJsonValue **
0x18001c8c2  mov     rax, [rsp+48h+arg_28]
0x18001c8c7  mov     r8, rdx; struct Windows::Data::Json::IJsonValue **
0x18001c8ca  mov     [r11-20h], rax
0x18001c8ce  mov     rdx, rcx; struct Windows::Data::Json::IJsonValue **
0x18001c8d1  mov     rax, [rsp+48h+arg_20]
0x18001c8d6  xor     ecx, ecx; int
0x18001c8d8  mov     [r11-28h], rax
0x18001c8dc  call    ?EnumerateUsers@DdcAccountHelper@@SAJHPEAPEAUIJsonValue@Json@Data@Windows@@00PEAK11@Z; DdcAccountHelper::EnumerateUsers(int,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *)
0x18001c8e1  mov     ebx, eax
0x18001c8e3  test    eax, eax
0x18001c8e5  jns     short loc_18001C906
0x18001c8e7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c8ee  jz      short loc_18001C965
0x18001c8f0  lea     rax, aChrEnumerateus; "CHR(EnumerateUsers(0, ppAdmins, ppDevic"...
0x18001c8f7  mov     [rsp+48h+var_20], rax
0x18001c8fc  mov     dword ptr [rsp+48h+var_28], 20h ; ' '
0x18001c904  jmp     short loc_18001C956
0x18001c906  xor     r9d, r9d; struct Windows::Data::Json::IJsonValue **
0x18001c909  mov     [rsp+48h+var_18], 0; unsigned int *
0x18001c912  mov     [rsp+48h+var_20], 0; unsigned int *
0x18001c91b  xor     r8d, r8d; struct Windows::Data::Json::IJsonValue **
0x18001c91e  mov     rdx, rdi; struct Windows::Data::Json::IJsonValue **
0x18001c921  mov     [rsp+48h+var_28], 0; unsigned int *
0x18001c92a  lea     ecx, [r9+1]; int
0x18001c92e  call    ?EnumerateUsers@DdcAccountHelper@@SAJHPEAPEAUIJsonValue@Json@Data@Windows@@00PEAK11@Z; DdcAccountHelper::EnumerateUsers(int,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *)
0x18001c933  mov     ebx, eax
0x18001c935  test    eax, eax
0x18001c937  jns     short loc_18001C965
0x18001c939  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001c940  jz      short loc_18001C965
0x18001c942  lea     rax, aChrEnumerateus_0; "CHR(EnumerateUsers(1, ppConnectedAdmins"...
0x18001c949  mov     [rsp+48h+var_20], rax
0x18001c94e  mov     dword ptr [rsp+48h+var_28], 21h ; '!'
0x18001c956  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001c95d  mov     r8d, ebx
0x18001c960  call    McTemplateU0dsqs_EventWriteTransfer
0x18001c965  mov     eax, ebx
0x18001c967  mov     rbx, [rsp+48h+arg_0]
0x18001c96c  add     rsp, 40h
0x18001c970  pop     rdi
0x18001c971  retn
```
