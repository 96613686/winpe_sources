# UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)

- ea: `0x180011bf0`
- end: `0x180011e6b`
- name: `?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z`
- size: `635`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800101f0`
- `0x1800107e0`
- `0x180010dd4`
- `0x18001122c`
- `0x1800118fc`

## callees

- `0x1800024c0`
- `0x1800036e8`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x180011bf0`
- `0x180026474`

## import_xrefs

- `MdmCommon!MdmUpdateStatus` at `0x180011dff`
- `MdmCommon!MdmUpdateStatus` at `0x180011dff`

## string_xrefs

- `0x180011e28`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x180011e14`: `CHR(MdmUpdateStatus( pdwHttpStatus, wstrTicket.c_str(), dwRequestId, eStatus, eCommandSource, dwRetries, dwErrorCode, ftReceivedTime, pftWorkStarted, pftWorkFinished, pfLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, pfLocationSyncEnabledByClient, ppwszBuffer))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UpdateStatusWrapper(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20)
{
  int v24; // edx
  int v25; // edx
  int v26; // ecx
  int DeviceTicket; // ebx
  __int64 v28; // rax
  int v29; // edx
  int v30; // ecx
  _BYTE v32[32]; // [rsp+100h] [rbp-78h] BYREF

  std::wstring::wstring((__int64)v32);
  DeviceTicket = DdcMsaHelper::GetDeviceTicket((__int64)v32, v24);
  if ( DeviceTicket >= 0 )
  {
    v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    DeviceTicket = MdmUpdateStatus(
                     a1,
                     v28,
                     a2,
                     a3,
                     a4,
                     a5,
                     a6,
                     a7,
                     a8,
                     a9,
                     a10,
                     a11,
                     a12,
                     a13,
                     a14,
                     a15,
                     a16,
                     a17,
                     a18,
                     a19,
                     a20);
    if ( DeviceTicket < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v30,
        v29,
        DeviceTicket,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        88,
        "CHR(MdmUpdateStatus( pdwHttpStatus, wstrTicket.c_str(), dwRequestId, eStatus, eCommandSource, dwRetries, dwError"
        "Code, ftReceivedTime, pftWorkStarted, pftWorkFinished, pfLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pSta"
        "ndardUsers, pConnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, "
        "pfLocationSyncEnabledByClient, ppwszBuffer))");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v26,
      v25,
      DeviceTicket,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
      66,
      "CHR(DdcMsaHelper::GetDeviceTicket(&wstrTicket))");
  }
  std::wstring::_Tidy_deallocate((__int64)v32);
  return (unsigned int)DeviceTicket;
}

```

## disassembly

```asm
0x180011bf0  mov     r11, rsp
0x180011bf3  push    rbx
0x180011bf4  push    rbp
0x180011bf5  push    rsi
0x180011bf6  push    rdi
0x180011bf7  push    r12
0x180011bf9  push    r13
0x180011bfb  push    r14
0x180011bfd  push    r15
0x180011bff  sub     rsp, 138h
0x180011c06  mov     rax, cs:__security_cookie
0x180011c0d  xor     rax, rsp
0x180011c10  mov     [rsp+178h+var_58], rax
0x180011c18  mov     r14d, r9d
0x180011c1b  mov     ebp, r8d
0x180011c1e  mov     esi, edx
0x180011c20  mov     rdi, rcx
0x180011c23  mov     r15, [rsp+178h+arg_38]
0x180011c2b  mov     r12, [rsp+178h+arg_40]
0x180011c33  mov     r13, [rsp+178h+arg_48]
0x180011c3b  mov     rax, [rsp+178h+arg_50]
0x180011c43  mov     [rsp+178h+var_80], rax
0x180011c4b  mov     rax, [rsp+178h+arg_58]
0x180011c53  mov     [rsp+178h+var_88], rax
0x180011c5b  mov     rax, [rsp+178h+arg_60]
0x180011c63  mov     [rsp+178h+var_90], rax
0x180011c6b  mov     rax, [rsp+178h+arg_68]
0x180011c73  mov     [rsp+178h+var_98], rax
0x180011c7b  mov     rax, [rsp+178h+arg_70]
0x180011c83  mov     [rsp+178h+var_A0], rax
0x180011c8b  mov     rax, [rsp+178h+arg_78]
0x180011c93  mov     [rsp+178h+var_A8], rax
0x180011c9b  mov     rax, [rsp+178h+arg_80]
0x180011ca3  mov     [rsp+178h+var_B0], rax
0x180011cab  mov     rax, [rsp+178h+arg_88]
0x180011cb3  mov     [rsp+178h+var_B8], rax
0x180011cbb  mov     rax, [rsp+178h+arg_90]
0x180011cc3  mov     [rsp+178h+var_C0], rax
0x180011ccb  mov     rax, [rsp+178h+arg_98]
0x180011cd3  mov     [rsp+178h+var_C8], rax
0x180011cdb  lea     rcx, [r11-78h]
0x180011cdf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180011ce4  nop
0x180011ce5  lea     rcx, [rsp+178h+var_78]
0x180011ced  call    ?GetDeviceTicket@DdcMsaHelper@@SAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DdcMsaHelper::GetDeviceTicket(std::wstring *)
0x180011cf2  mov     ebx, eax
0x180011cf4  test    eax, eax
0x180011cf6  jns     short loc_180011D1E
0x180011cf8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011cff  jz      loc_180011E38
0x180011d05  lea     rax, aChrDdcmsahelpe; "CHR(DdcMsaHelper::GetDeviceTicket(&wstr"...
0x180011d0c  mov     [rsp+178h+var_150], rax
0x180011d11  mov     [rsp+178h+var_158], 42h ; 'B'
0x180011d19  jmp     loc_180011E28
0x180011d1e  lea     rcx, [rsp+178h+var_78]
0x180011d26  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011d2b  mov     rdx, rax
0x180011d2e  mov     rax, [rsp+178h+var_C8]
0x180011d36  mov     [rsp+178h+var_D8], rax
0x180011d3e  mov     rax, [rsp+178h+var_C0]
0x180011d46  mov     [rsp+178h+var_E0], rax
0x180011d4e  mov     rax, [rsp+178h+var_B8]
0x180011d56  mov     [rsp+178h+var_E8], rax
0x180011d5e  mov     rax, [rsp+178h+var_B0]
0x180011d66  mov     [rsp+178h+var_F0], rax
0x180011d6e  mov     rax, [rsp+178h+var_A8]
0x180011d76  mov     [rsp+178h+var_F8], rax
0x180011d7e  mov     rax, [rsp+178h+var_A0]
0x180011d86  mov     [rsp+178h+var_100], rax
0x180011d8b  mov     rax, [rsp+178h+var_98]
0x180011d93  mov     [rsp+178h+var_108], rax
0x180011d98  mov     rax, [rsp+178h+var_90]
0x180011da0  mov     [rsp+178h+var_110], rax
0x180011da5  mov     rax, [rsp+178h+var_88]
0x180011dad  mov     [rsp+178h+var_118], rax
0x180011db2  mov     rax, [rsp+178h+var_80]
0x180011dba  mov     [rsp+178h+var_120], rax
0x180011dbf  mov     [rsp+178h+var_128], r13
0x180011dc4  mov     [rsp+178h+var_130], r12
0x180011dc9  mov     [rsp+178h+var_138], r15
0x180011dce  mov     rax, [rsp+178h+arg_30]
0x180011dd6  mov     [rsp+178h+var_140], rax
0x180011ddb  mov     eax, [rsp+178h+arg_28]
0x180011de2  mov     [rsp+178h+var_148], eax
0x180011de6  mov     eax, [rsp+178h+arg_20]
0x180011ded  mov     dword ptr [rsp+178h+var_150], eax
0x180011df1  mov     [rsp+178h+var_158], r14d
0x180011df6  mov     r9d, ebp
0x180011df9  mov     r8d, esi
0x180011dfc  mov     rcx, rdi
0x180011dff  call    cs:__imp_?MdmUpdateStatus@@YAJPEAKPEBGKW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU3@5PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@7777PEAH888PEAPEAG@Z; MdmUpdateStatus(ulong *,ushort const *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x180011e05  mov     ebx, eax
0x180011e07  test    eax, eax
0x180011e09  jns     short loc_180011E38
0x180011e0b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011e12  jz      short loc_180011E38
0x180011e14  lea     rax, aChrMdmupdatest; "CHR(MdmUpdateStatus( pdwHttpStatus, wst"...
0x180011e1b  mov     [rsp+178h+var_150], rax
0x180011e20  mov     [rsp+178h+var_158], 58h ; 'X'
0x180011e28  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180011e2f  mov     r8d, ebx
0x180011e32  call    McTemplateU0dsqs_EventWriteTransfer
0x180011e37  nop
0x180011e38  lea     rcx, [rsp+178h+var_78]
0x180011e40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011e45  mov     eax, ebx
0x180011e47  mov     rcx, [rsp+178h+var_58]
0x180011e4f  xor     rcx, rsp; StackCookie
0x180011e52  call    __security_check_cookie
0x180011e57  add     rsp, 138h
0x180011e5e  pop     r15
0x180011e60  pop     r14
0x180011e62  pop     r13
0x180011e64  pop     r12
0x180011e66  pop     rdi
0x180011e67  pop     rsi
0x180011e68  pop     rbp
0x180011e69  pop     rbx
0x180011e6a  retn
```
