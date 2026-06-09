# MdmUpdateStatus(ulong *,ushort const *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)

- ea: `0x180005a10`
- end: `0x180005ca6`
- name: `?MdmUpdateStatus@@YAJPEAKPEBGKW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU3@5PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@7777PEAH888PEAPEAG@Z`
- size: `662`
- prototype: `__int64 __fastcall(_DWORD *, __int64, unsigned int, int, int, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001520`
- `0x180005a10`
- `0x1800064f0`
- `0x180006548`
- `0x180012038`

## string_xrefs

- `0x180005c20`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180005c11`: `CHR(MdmHttpWrapper::UpdateStatus( pdwHttpStatus, pwszTicket, dwRequestId, eCommandStatus, eCommandSource, dwRetries, hrErrorCode, ftCommandReceived, pftWorkStarted, pftWorkFinished, pLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, pfLocationSyncEnabledByClient, ppwszBuffer))`

## pseudocode

```c
__int64 __fastcall MdmUpdateStatus(
        _DWORD *a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        int a7,
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
        __int64 a20,
        void **a21)
{
  __int64 v23; // r8
  __int64 v25; // rdx
  __int64 v27; // rcx
  __int64 v28; // r9
  __int64 v29; // r10
  __int64 v30; // r11
  int v31; // edx
  int updated; // ebx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v36; // [rsp+B0h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-B0h]
  __int64 v38; // [rsp+C0h] [rbp-A8h]
  __int64 v39; // [rsp+C8h] [rbp-A0h]
  __int64 v40; // [rsp+D0h] [rbp-98h]
  __int64 v41; // [rsp+D8h] [rbp-90h]
  __int64 v42; // [rsp+E0h] [rbp-88h]
  void **v43; // [rsp+E8h] [rbp-80h]
  __int64 v44; // [rsp+F0h] [rbp-78h]
  __int64 v45; // [rsp+F8h] [rbp-70h]
  _BYTE v46[16]; // [rsp+100h] [rbp-68h] BYREF
  __int64 *v47; // [rsp+110h] [rbp-58h]
  __int64 v48; // [rsp+118h] [rbp-50h]

  v23 = a15;
  v25 = a14;
  v27 = a13;
  v28 = a16;
  v29 = a17;
  v30 = a18;
  v36 = a12;
  v45 = a19;
  v44 = a20;
  v43 = a21;
  v37 = a13;
  v38 = a14;
  v39 = a15;
  v40 = a16;
  v41 = a17;
  v42 = a18;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(a13, MDMCOMMON_TRACE_UPDATE_STATUS, a15, 1, v46);
    v27 = v37;
    v25 = v38;
    v23 = v39;
    v28 = v40;
    v29 = v41;
    v30 = v42;
  }
  updated = MdmHttpWrapper::UpdateStatus(
              a1,
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
              v36,
              v27,
              v25,
              v23,
              v28,
              v29,
              v30,
              v45,
              v44,
              v43);
  if ( updated < 0 )
  {
    v34 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_7;
    McTemplateU0dsqs_EventWriteTransfer(
      Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits,
      v31,
      updated,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      209,
      "CHR(MdmHttpWrapper::UpdateStatus( pdwHttpStatus, pwszTicket, dwRequestId, eCommandStatus, eCommandSource, dwRetrie"
      "s, hrErrorCode, ftCommandReceived, pftWorkStarted, pftWorkFinished, pLocation, pAuthorizedCids, pAdmins, pDeviceOw"
      "ners, pStandardUsers, pConnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledBy"
      "Client, pfLocationSyncEnabledByClient, ppwszBuffer))");
  }
  v34 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v34 & 2) != 0 )
  {
    LODWORD(v36) = updated;
    v47 = &v36;
    v48 = 4;
    McGenEventWrite_EventWriteTransfer(v34, MDMCOMMON_TRACE_UPDATE_STATUS_RESULT, v33, 2, v46);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180005a10  push    rbx
0x180005a12  push    rsi
0x180005a13  push    rdi
0x180005a14  push    r12
0x180005a16  push    r13
0x180005a18  push    r14
0x180005a1a  push    r15
0x180005a1c  sub     rsp, 130h
0x180005a23  mov     rax, cs:__security_cookie
0x180005a2a  xor     rax, rsp
0x180005a2d  mov     [rsp+168h+var_48], rax
0x180005a35  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005a3c  mov     r14d, r9d
0x180005a3f  mov     rax, [rsp+168h+arg_58]
0x180005a47  mov     esi, r8d
0x180005a4a  mov     r8, [rsp+168h+arg_70]
0x180005a52  mov     rdi, rdx
0x180005a55  mov     rdx, [rsp+168h+arg_68]
0x180005a5d  mov     rbx, rcx
0x180005a60  mov     rcx, [rsp+168h+arg_60]
0x180005a68  mov     r9, [rsp+168h+arg_78]
0x180005a70  mov     r10, [rsp+168h+arg_80]
0x180005a78  mov     r11, [rsp+168h+arg_88]
0x180005a80  mov     r15, [rsp+168h+arg_40]
0x180005a88  mov     r12, [rsp+168h+arg_48]
0x180005a90  mov     r13, [rsp+168h+arg_50]
0x180005a98  mov     [rsp+168h+var_B8], rax
0x180005aa0  mov     rax, [rsp+168h+arg_90]
0x180005aa8  mov     [rsp+168h+var_70], rax
0x180005ab0  mov     rax, [rsp+168h+arg_98]
0x180005ab8  mov     [rsp+168h+var_78], rax
0x180005ac0  mov     rax, [rsp+168h+arg_A0]
0x180005ac8  mov     [rsp+168h+var_80], rax
0x180005ad0  mov     [rsp+168h+var_B0], rcx
0x180005ad8  mov     [rsp+168h+var_A8], rdx
0x180005ae0  mov     [rsp+168h+var_A0], r8
0x180005ae8  mov     [rsp+168h+var_98], r9
0x180005af0  mov     [rsp+168h+var_90], r10
0x180005af8  mov     [rsp+168h+var_88], r11
0x180005b00  jz      short loc_180005B51
0x180005b02  lea     rax, [rsp+168h+var_68]
0x180005b0a  mov     r9d, 1
0x180005b10  lea     rdx, MDMCOMMON_TRACE_UPDATE_STATUS
0x180005b17  mov     [rsp+168h+var_148], rax
0x180005b1c  call    McGenEventWrite_EventWriteTransfer
0x180005b21  mov     rcx, [rsp+168h+var_B0]
0x180005b29  mov     rdx, [rsp+168h+var_A8]
0x180005b31  mov     r8, [rsp+168h+var_A0]
0x180005b39  mov     r9, [rsp+168h+var_98]
0x180005b41  mov     r10, [rsp+168h+var_90]
0x180005b49  mov     r11, [rsp+168h+var_88]
0x180005b51  mov     rax, [rsp+168h+var_80]
0x180005b59  mov     [rsp+168h+var_C8], rax
0x180005b61  mov     rax, [rsp+168h+var_78]
0x180005b69  mov     [rsp+168h+var_D0], rax
0x180005b71  mov     rax, [rsp+168h+var_70]
0x180005b79  mov     [rsp+168h+var_D8], rax
0x180005b81  mov     rax, [rsp+168h+var_B8]
0x180005b89  mov     [rsp+168h+var_E0], r11
0x180005b91  mov     [rsp+168h+var_E8], r10
0x180005b99  mov     [rsp+168h+var_F0], r9
0x180005b9e  mov     r9d, r14d
0x180005ba1  mov     [rsp+168h+var_F8], r8
0x180005ba6  mov     r8d, esi
0x180005ba9  mov     [rsp+168h+var_100], rdx
0x180005bae  mov     rdx, rdi
0x180005bb1  mov     [rsp+168h+var_108], rcx
0x180005bb6  mov     rcx, rbx
0x180005bb9  mov     [rsp+168h+var_110], rax
0x180005bbe  mov     rax, [rsp+168h+arg_38]
0x180005bc6  mov     [rsp+168h+var_118], r13
0x180005bcb  mov     [rsp+168h+var_120], r12
0x180005bd0  mov     [rsp+168h+var_128], r15
0x180005bd5  mov     [rsp+168h+var_130], rax
0x180005bda  mov     eax, [rsp+168h+arg_30]
0x180005be1  mov     [rsp+168h+var_138], eax
0x180005be5  mov     eax, [rsp+168h+arg_28]
0x180005bec  mov     dword ptr [rsp+168h+var_140], eax
0x180005bf0  mov     eax, [rsp+168h+arg_20]
0x180005bf7  mov     dword ptr [rsp+168h+var_148], eax
0x180005bfb  call    ?UpdateStatus@MdmHttpWrapper@@SAJPEAKPEBGKW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU4@5PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@7777PEAH888PEAPEAG@Z; MdmHttpWrapper::UpdateStatus(ulong *,ushort const *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x180005c00  mov     ebx, eax
0x180005c02  test    eax, eax
0x180005c04  jns     short loc_180005C34
0x180005c06  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005c0c  test    cl, 1
0x180005c0f  jz      short loc_180005C3A
0x180005c11  lea     rax, aChrMdmhttpwrap; "CHR(MdmHttpWrapper::UpdateStatus( pdwHt"...
0x180005c18  mov     r8d, ebx
0x180005c1b  mov     [rsp+168h+var_140], rax
0x180005c20  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180005c27  mov     dword ptr [rsp+168h+var_148], 1D1h
0x180005c2f  call    McTemplateU0dsqs_EventWriteTransfer
0x180005c34  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005c3a  test    cl, 2
0x180005c3d  jz      short loc_180005C81
0x180005c3f  lea     rax, [rsp+168h+var_B8]
0x180005c47  mov     dword ptr [rsp+168h+var_B8], ebx
0x180005c4e  mov     [rsp+168h+var_58], rax
0x180005c56  lea     rdx, MDMCOMMON_TRACE_UPDATE_STATUS_RESULT
0x180005c5d  lea     rax, [rsp+168h+var_68]
0x180005c65  mov     [rsp+168h+var_50], 4
0x180005c71  mov     r9d, 2
0x180005c77  mov     [rsp+168h+var_148], rax
0x180005c7c  call    McGenEventWrite_EventWriteTransfer
0x180005c81  mov     eax, ebx
0x180005c83  mov     rcx, [rsp+168h+var_48]
0x180005c8b  xor     rcx, rsp; StackCookie
0x180005c8e  call    __security_check_cookie
0x180005c93  add     rsp, 130h
0x180005c9a  pop     r15
0x180005c9c  pop     r14
0x180005c9e  pop     r13
0x180005ca0  pop     r12
0x180005ca2  pop     rdi
0x180005ca3  pop     rsi
0x180005ca4  pop     rbx
0x180005ca5  retn
```
