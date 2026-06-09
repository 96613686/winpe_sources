# DeviceConfiguration::DeviceInstaller::_MarkPrintQueueAsFaxDevice(std::shared_ptr<DeviceConfiguration::Device>)

- ea: `0x180015ad0`
- end: `0x180015d84`
- name: `?_MarkPrintQueueAsFaxDevice@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180015d8c`

## callees

- `0x1800020c0`
- `0x18000af54`
- `0x18000d89c`
- `0x18000e818`
- `0x1800115a0`
- `0x18001164c`
- `0x1800141a4`
- `0x180014658`
- `0x180014d38`
- `0x180015ad0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015c04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015c04`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180015cf0`
- `api-ms-win-devices-query-l1-1-0!DevSetObjectProperties` at `0x180015cf0`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180015b66`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180015b66`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180015d3b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180015d3b`

## string_xrefs

- `0x180015b83`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180015c62`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180015d0d`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x180015b74`: `DevGetObjectProperties for DEVPKEY_Device_ConfigFlags failed!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_MarkPrintQueueAsFaxDevice(__int64 a1, _QWORD *a2)
{
  _QWORD *DeviceId; // rax
  unsigned int ObjectProperties; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  unsigned int v11; // eax
  const char *v12; // r9
  std::_Ref_count_base *v13; // rcx
  __int64 result; // rax
  std::_Ref_count_base *v15; // rcx
  char *v16; // [rsp+28h] [rbp-D0h]
  char v17[4]; // [rsp+40h] [rbp-B8h] BYREF
  char v18[8]; // [rsp+48h] [rbp-B0h] BYREF
  _QWORD *v19; // [rsp+50h] [rbp-A8h]
  char *v20; // [rsp+58h] [rbp-A0h]
  char *v21; // [rsp+60h] [rbp-98h]
  char v22; // [rsp+68h] [rbp-90h]
  __int128 v23; // [rsp+70h] [rbp-88h] BYREF
  int v24; // [rsp+80h] [rbp-78h]
  int v25; // [rsp+84h] [rbp-74h]
  __int64 v26; // [rsp+88h] [rbp-70h]
  int v27; // [rsp+90h] [rbp-68h]
  int v28; // [rsp+94h] [rbp-64h]
  char *v29; // [rsp+98h] [rbp-60h]
  _QWORD v30[4]; // [rsp+A0h] [rbp-58h] BYREF
  _BYTE v31[32]; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  try
  {
    v19 = a2;
    *(_DWORD *)v17 = 0;
    *(_QWORD *)v18 = 0;
    v20 = v18;
    v21 = v17;
    v22 = 1;
    DeviceId = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(*a2, v31);
    if ( DeviceId[3] > 7u )
      DeviceId = (_QWORD *)*DeviceId;
    ObjectProperties = DevGetObjectProperties(3, DeviceId, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x152,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)ObjectProperties,
      (int)"DevGetObjectProperties for DEVPKEY_Device_ConfigFlags failed!",
      v17);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::wstring(v30);
    v5 = *(_QWORD *)v18;
    if ( dword_180024288 != *(_DWORD *)(*(_QWORD *)v18 + 16LL) )
      goto LABEL_16;
    v6 = qword_180024278 - **(_QWORD **)v18;
    if ( qword_180024278 == **(_QWORD **)v18 )
      v6 = qword_180024280 - *(_QWORD *)(*(_QWORD *)v18 + 8LL);
    if ( v6 || dword_18002428C != *(_DWORD *)(*(_QWORD *)v18 + 20LL) )
      goto LABEL_16;
    v7 = *(_QWORD *)(*(_QWORD *)v18 + 24LL);
    if ( qword_180024290 != v7 )
    {
      if ( !qword_180024290 || !v7 || (unsigned int)_o__wcsicmp(qword_180024290) )
      {
LABEL_16:
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0x15A,
          (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
          (const char *)0x80070490LL,
          v30[2] == 0,
          (bool)"Failed to retrieve device id for Fax print queue!",
          v18);
        v23 = xmmword_18001EAD0;
        v24 = 8;
        v25 = 0;
        v26 = 0;
        v27 = 17;
        v28 = 1;
        v29 = &byte_1800241F9;
        v10 = v30;
        if ( v30[3] > 7u )
          v10 = (_QWORD *)v30[0];
        v11 = DevSetObjectProperties(3, v10, 1, &v23);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x164,
          (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
          (const char *)v11,
          (int)"DevSetObjectProperties for PKEY_Printer_IsFaxDevice failed!",
          v16);
        std::wstring::_Tidy_deallocate(v30);
        if ( *(_QWORD *)v18 )
          DevFreeObjectProperties(*(unsigned int *)v17);
        v13 = (std::_Ref_count_base *)a2[1];
        if ( v13 )
          std::_Ref_count_base::_Decref(v13);
        return 0;
      }
      v5 = *(_QWORD *)v18;
    }
    if ( *(_DWORD *)(v5 + 32) == 8210 )
    {
      v8 = std::_WChar_traits<unsigned short>::length(*(_QWORD *)(v5 + 40));
      std::wstring::_Assign<unsigned short>(v30, v9, v8);
    }
    goto LABEL_16;
  }
  catch ( ... )
  {
    *(_DWORD *)v17 = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x168,
                       (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
                       v12);
    v15 = (std::_Ref_count_base *)v19[1];
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    return *(unsigned int *)v17;
  }
  return result;
}

```

## disassembly

```asm
0x180015ad0  mov     r11, rsp
0x180015ad3  push    rdi
0x180015ad4  sub     rsp, 0F0h
0x180015adb  mov     rax, cs:__security_cookie
0x180015ae2  xor     rax, rsp
0x180015ae5  mov     [rsp+0F8h+var_18], rax
0x180015aed  mov     rdi, rdx
0x180015af0  mov     [rsp+0F8h+var_A8], rdx
0x180015af5  mov     dword ptr [rsp+0F8h+var_B8], 0
0x180015afd  mov     qword ptr [rsp+0F8h+var_B0], 0
0x180015b06  lea     rax, [rsp+0F8h+var_B0]
0x180015b0b  mov     [rsp+0F8h+var_A0], rax
0x180015b10  lea     rax, [rsp+0F8h+var_B8]
0x180015b15  mov     [rsp+0F8h+var_98], rax
0x180015b1a  mov     [rsp+0F8h+var_90], 1
0x180015b1f  lea     rdx, [r11-38h]
0x180015b23  mov     rcx, [rdi]
0x180015b26  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x180015b2b  nop
0x180015b2c  cmp     qword ptr [rax+18h], 7
0x180015b31  jbe     short loc_180015B36
0x180015b33  mov     rax, [rax]
0x180015b36  lea     rcx, [rsp+0F8h+var_B0]
0x180015b3b  mov     [rsp+0F8h+var_C8], rcx; char *
0x180015b40  lea     rcx, [rsp+0F8h+var_B8]
0x180015b45  mov     [rsp+0F8h+var_D0], rcx; char *
0x180015b4a  lea     rcx, qword_180024278
0x180015b51  mov     qword ptr [rsp+0F8h+var_D8], rcx
0x180015b56  mov     r9d, 1
0x180015b5c  xor     r8d, r8d
0x180015b5f  mov     rdx, rax
0x180015b62  lea     ecx, [r9+2]
0x180015b66  call    cs:__imp_DevGetObjectProperties
0x180015b6c  mov     rcx, [rsp+0F8h]; this
0x180015b74  lea     rdx, aDevgetobjectpr_0; "DevGetObjectProperties for DEVPKEY_Devi"...
0x180015b7b  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180015b80  mov     r9d, eax; char *
0x180015b83  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015b8a  mov     edx, 152h; void *
0x180015b8f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015b94  nop
0x180015b95  lea     rcx, [rsp+0F8h+var_38]
0x180015b9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015ba2  lea     rcx, [rsp+0F8h+var_58]
0x180015baa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015baf  nop
0x180015bb0  mov     rcx, qword ptr [rsp+0F8h+var_B0]
0x180015bb5  mov     eax, [rcx+10h]
0x180015bb8  cmp     cs:dword_180024288, eax
0x180015bbe  jnz     short loc_180015C38
0x180015bc0  mov     rax, cs:qword_180024278
0x180015bc7  sub     rax, [rcx]
0x180015bca  jnz     short loc_180015BD7
0x180015bcc  mov     rax, cs:qword_180024280
0x180015bd3  sub     rax, [rcx+8]
0x180015bd7  test    rax, rax
0x180015bda  jnz     short loc_180015C38
0x180015bdc  mov     eax, [rcx+14h]
0x180015bdf  cmp     cs:dword_18002428C, eax
0x180015be5  jnz     short loc_180015C38
0x180015be7  mov     rdx, [rcx+18h]
0x180015beb  mov     rax, cs:qword_180024290
0x180015bf2  cmp     rax, rdx
0x180015bf5  jz      short loc_180015C13
0x180015bf7  test    rax, rax
0x180015bfa  jz      short loc_180015C38
0x180015bfc  test    rdx, rdx
0x180015bff  jz      short loc_180015C38
0x180015c01  mov     rcx, rax
0x180015c04  call    cs:__imp__o__wcsicmp
0x180015c0a  test    eax, eax
0x180015c0c  jnz     short loc_180015C38
0x180015c0e  mov     rcx, qword ptr [rsp+0F8h+var_B0]
0x180015c13  cmp     dword ptr [rcx+20h], 2012h
0x180015c1a  jnz     short loc_180015C38
0x180015c1c  mov     rcx, [rcx+28h]
0x180015c20  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180015c25  mov     r8, rax
0x180015c28  mov     rdx, rcx
0x180015c2b  lea     rcx, [rsp+0F8h+var_58]
0x180015c33  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180015c38  cmp     [rsp+0F8h+var_48], 0
0x180015c41  setz    al
0x180015c44  mov     rcx, [rsp+0F8h]; this
0x180015c4c  lea     rdx, aFailedToRetrie; "Failed to retrieve device id for Fax pr"...
0x180015c53  mov     [rsp+0F8h+var_D0], rdx; char *
0x180015c58  mov     [rsp+0F8h+var_D8], al; char
0x180015c5c  mov     r9d, 80070490h; char *
0x180015c62  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015c69  mov     edx, 15Ah; void *
0x180015c6e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180015c73  movups  xmm0, cs:xmmword_18001EAD0
0x180015c7a  movups  [rsp+0F8h+var_88], xmm0
0x180015c7f  mov     eax, cs:dword_18001EAE0
0x180015c85  mov     [rsp+0F8h+var_78], eax
0x180015c8c  mov     [rsp+0F8h+var_74], 0
0x180015c97  mov     [rsp+0F8h+var_70], 0
0x180015ca3  mov     [rsp+0F8h+var_68], 11h
0x180015cae  mov     [rsp+0F8h+var_64], 1
0x180015cb9  lea     rax, byte_1800241F9
0x180015cc0  mov     [rsp+0F8h+var_60], rax
0x180015cc8  lea     rdx, [rsp+0F8h+var_58]
0x180015cd0  cmp     [rsp+0F8h+var_40], 7
0x180015cd9  cmova   rdx, [rsp+0F8h+var_58]
0x180015ce2  lea     r9, [rsp+0F8h+var_88]
0x180015ce7  mov     ecx, 3
0x180015cec  lea     r8d, [rcx-2]
0x180015cf0  call    cs:__imp_DevSetObjectProperties
0x180015cf6  mov     rcx, [rsp+0F8h]; this
0x180015cfe  lea     rdx, aDevsetobjectpr_0; "DevSetObjectProperties for PKEY_Printer"...
0x180015d05  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180015d0a  mov     r9d, eax; char *
0x180015d0d  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x180015d14  mov     edx, 164h; void *
0x180015d19  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015d1e  nop
0x180015d1f  lea     rcx, [rsp+0F8h+var_58]
0x180015d27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d2c  nop
0x180015d2d  mov     rdx, qword ptr [rsp+0F8h+var_B0]
0x180015d32  test    rdx, rdx
0x180015d35  jz      short loc_180015D42
0x180015d37  mov     ecx, dword ptr [rsp+0F8h+var_B8]
0x180015d3b  call    cs:__imp_DevFreeObjectProperties
0x180015d41  nop
0x180015d42  mov     rcx, [rdi+8]; this
0x180015d46  test    rcx, rcx
0x180015d49  jz      short loc_180015D50
0x180015d4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015d50  xor     eax, eax
0x180015d52  jmp     short loc_180015D6B
0x180015d54  mov     rax, [rsp+0F8h+var_A8]
0x180015d59  mov     rcx, [rax+8]; this
0x180015d5d  test    rcx, rcx
0x180015d60  jz      short loc_180015D67
0x180015d62  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015d67  mov     eax, dword ptr [rsp+0F8h+var_B8]
0x180015d6b  mov     rcx, [rsp+0F8h+var_18]
0x180015d73  xor     rcx, rsp; StackCookie
0x180015d76  call    __security_check_cookie
0x180015d7b  add     rsp, 0F0h
0x180015d82  pop     rdi
0x180015d83  retn
```
