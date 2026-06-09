# MdmUpdateStatus(ulong *,ushort const *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)

- ea: `0x180005a60`
- end: `0x180005cf7`
- name: `?MdmUpdateStatus@@YAJPEAKPEBGKW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU3@5PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@7777PEAH888PEAPEAG@Z`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001520`
- `0x180005a60`
- `0x180006560`
- `0x1800065c0`
- `0x180012414`

## string_xrefs

- `0x180005c70`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180005c61`: `CHR(MdmHttpWrapper::UpdateStatus( pdwHttpStatus, pwszTicket, dwRequestId, eCommandStatus, eCommandSource, dwRetries, hrErrorCode, ftCommandReceived, pftWorkStarted, pftWorkFinished, pLocation, pAuthorizedCids, pAdmins, pDeviceOwners, pStandardUsers, pConnectedAdmins, pfMasterLocationSwitchOn, pfLocationSyncEnabled, pfMasterLocationEnabledByClient, pfLocationSyncEnabledByClient, ppwszBuffer))`

## pseudocode

```c
__int64 __fastcall MdmUpdateStatus(
        _DWORD *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        struct Windows::Data::Json::IJsonValue *a14,
        __int64 a15,
        struct Windows::Data::Json::IJsonValue *a16,
        _DWORD *a17,
        _DWORD *a18,
        _DWORD *a19,
        _DWORD *a20,
        void **a21)
{
  struct Windows::Data::Json::IJsonValue *v23; // r8
  struct Windows::Data::Json::IJsonValue *v25; // rdx
  struct Windows::Data::Json::IJsonValue *v27; // rcx
  struct Windows::Data::Json::IJsonValue *v28; // r9
  _DWORD *v29; // r10
  _DWORD *v30; // r11
  int v31; // edx
  int updated; // ebx
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v36; // [rsp+B0h] [rbp-B8h] BYREF
  struct Windows::Data::Json::IJsonValue *v37; // [rsp+B8h] [rbp-B0h]
  struct Windows::Data::Json::IJsonValue *v38; // [rsp+C0h] [rbp-A8h]
  struct Windows::Data::Json::IJsonValue *v39; // [rsp+C8h] [rbp-A0h]
  struct Windows::Data::Json::IJsonValue *v40; // [rsp+D0h] [rbp-98h]
  _DWORD *v41; // [rsp+D8h] [rbp-90h]
  _DWORD *v42; // [rsp+E0h] [rbp-88h]
  void **v43; // [rsp+E8h] [rbp-80h]
  _DWORD *v44; // [rsp+F0h] [rbp-78h]
  _DWORD *v45; // [rsp+F8h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+100h] [rbp-68h] BYREF
  __int64 *v47; // [rsp+110h] [rbp-58h]
  __int64 v48; // [rsp+118h] [rbp-50h]

  v23 = (struct Windows::Data::Json::IJsonValue *)a15;
  v25 = a14;
  v27 = (struct Windows::Data::Json::IJsonValue *)a13;
  v28 = a16;
  v29 = a17;
  v30 = a18;
  v36 = a12;
  v45 = a19;
  v44 = a20;
  v43 = a21;
  v37 = (struct Windows::Data::Json::IJsonValue *)a13;
  v38 = a14;
  v39 = (struct Windows::Data::Json::IJsonValue *)a15;
  v40 = a16;
  v41 = a17;
  v42 = a18;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(a13, (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_UPDATE_STATUS, a15, 1u, &v46);
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
    McGenEventWrite_EventWriteTransfer(
      v34,
      (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_UPDATE_STATUS_RESULT,
      v33,
      2u,
      &v46);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180005a60  push    rbx
0x180005a62  push    rsi
0x180005a63  push    rdi
0x180005a64  push    r12
0x180005a66  push    r13
0x180005a68  push    r14
0x180005a6a  push    r15
0x180005a6c  sub     rsp, 130h
0x180005a73  mov     rax, cs:__security_cookie
0x180005a7a  xor     rax, rsp
0x180005a7d  mov     [rsp+168h+var_48], rax
0x180005a85  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180005a8c  mov     r14d, r9d
0x180005a8f  mov     rax, [rsp+168h+arg_58]
0x180005a97  mov     esi, r8d
0x180005a9a  mov     r8, [rsp+168h+arg_70]
0x180005aa2  mov     rdi, rdx
0x180005aa5  mov     rdx, [rsp+168h+arg_68]
0x180005aad  mov     rbx, rcx
0x180005ab0  mov     rcx, [rsp+168h+arg_60]
0x180005ab8  mov     r9, [rsp+168h+arg_78]
0x180005ac0  mov     r10, [rsp+168h+arg_80]
0x180005ac8  mov     r11, [rsp+168h+arg_88]
0x180005ad0  mov     r15, [rsp+168h+arg_40]
0x180005ad8  mov     r12, [rsp+168h+arg_48]
0x180005ae0  mov     r13, [rsp+168h+arg_50]
0x180005ae8  mov     [rsp+168h+var_B8], rax
0x180005af0  mov     rax, [rsp+168h+arg_90]
0x180005af8  mov     [rsp+168h+var_70], rax
0x180005b00  mov     rax, [rsp+168h+arg_98]
0x180005b08  mov     [rsp+168h+var_78], rax
0x180005b10  mov     rax, [rsp+168h+arg_A0]
0x180005b18  mov     [rsp+168h+var_80], rax
0x180005b20  mov     [rsp+168h+var_B0], rcx
0x180005b28  mov     [rsp+168h+var_A8], rdx
0x180005b30  mov     [rsp+168h+var_A0], r8
0x180005b38  mov     [rsp+168h+var_98], r9
0x180005b40  mov     [rsp+168h+var_90], r10
0x180005b48  mov     [rsp+168h+var_88], r11
0x180005b50  jz      short loc_180005BA1
0x180005b52  lea     rax, [rsp+168h+var_68]
0x180005b5a  mov     r9d, 1
0x180005b60  lea     rdx, MDMCOMMON_TRACE_UPDATE_STATUS
0x180005b67  mov     [rsp+168h+var_148], rax
0x180005b6c  call    McGenEventWrite_EventWriteTransfer
0x180005b71  mov     rcx, [rsp+168h+var_B0]
0x180005b79  mov     rdx, [rsp+168h+var_A8]
0x180005b81  mov     r8, [rsp+168h+var_A0]
0x180005b89  mov     r9, [rsp+168h+var_98]
0x180005b91  mov     r10, [rsp+168h+var_90]
0x180005b99  mov     r11, [rsp+168h+var_88]
0x180005ba1  mov     rax, [rsp+168h+var_80]
0x180005ba9  mov     [rsp+168h+var_C8], rax
0x180005bb1  mov     rax, [rsp+168h+var_78]
0x180005bb9  mov     [rsp+168h+var_D0], rax
0x180005bc1  mov     rax, [rsp+168h+var_70]
0x180005bc9  mov     [rsp+168h+var_D8], rax
0x180005bd1  mov     rax, [rsp+168h+var_B8]
0x180005bd9  mov     [rsp+168h+var_E0], r11
0x180005be1  mov     [rsp+168h+var_E8], r10
0x180005be9  mov     [rsp+168h+var_F0], r9
0x180005bee  mov     r9d, r14d
0x180005bf1  mov     [rsp+168h+var_F8], r8
0x180005bf6  mov     r8d, esi
0x180005bf9  mov     [rsp+168h+var_100], rdx
0x180005bfe  mov     rdx, rdi
0x180005c01  mov     [rsp+168h+var_108], rcx
0x180005c06  mov     rcx, rbx
0x180005c09  mov     [rsp+168h+var_110], rax
0x180005c0e  mov     rax, [rsp+168h+arg_38]
0x180005c16  mov     [rsp+168h+var_118], r13
0x180005c1b  mov     [rsp+168h+var_120], r12
0x180005c20  mov     [rsp+168h+var_128], r15
0x180005c25  mov     [rsp+168h+var_130], rax
0x180005c2a  mov     eax, [rsp+168h+arg_30]
0x180005c31  mov     [rsp+168h+var_138], eax
0x180005c35  mov     eax, [rsp+168h+arg_28]
0x180005c3c  mov     dword ptr [rsp+168h+var_140], eax
0x180005c40  mov     eax, [rsp+168h+arg_20]
0x180005c47  mov     dword ptr [rsp+168h+var_148], eax
0x180005c4b  call    ?UpdateStatus@MdmHttpWrapper@@SAJPEAKPEBGKW4MdmCommandStatus@@W4MdmCommandChannelType@@KJU_FILETIME@@PEAU4@5PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@7777PEAH888PEAPEAG@Z; MdmHttpWrapper::UpdateStatus(ulong *,ushort const *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,long,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x180005c50  mov     ebx, eax
0x180005c52  test    eax, eax
0x180005c54  jns     short loc_180005C84
0x180005c56  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005c5c  test    cl, 1
0x180005c5f  jz      short loc_180005C8A
0x180005c61  lea     rax, aChrMdmhttpwrap; "CHR(MdmHttpWrapper::UpdateStatus( pdwHt"...
0x180005c68  mov     r8d, ebx
0x180005c6b  mov     [rsp+168h+var_140], rax
0x180005c70  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180005c77  mov     dword ptr [rsp+168h+var_148], 1D1h
0x180005c7f  call    McTemplateU0dsqs_EventWriteTransfer
0x180005c84  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180005c8a  test    cl, 2
0x180005c8d  jz      short loc_180005CD1
0x180005c8f  lea     rax, [rsp+168h+var_B8]
0x180005c97  mov     dword ptr [rsp+168h+var_B8], ebx
0x180005c9e  mov     [rsp+168h+var_58], rax
0x180005ca6  lea     rdx, MDMCOMMON_TRACE_UPDATE_STATUS_RESULT
0x180005cad  lea     rax, [rsp+168h+var_68]
0x180005cb5  mov     [rsp+168h+var_50], 4
0x180005cc1  mov     r9d, 2
0x180005cc7  mov     [rsp+168h+var_148], rax
0x180005ccc  call    McGenEventWrite_EventWriteTransfer
0x180005cd1  mov     eax, ebx
0x180005cd3  mov     rcx, [rsp+168h+var_48]
0x180005cdb  xor     rcx, rsp; StackCookie
0x180005cde  call    __security_check_cookie
0x180005ce3  add     rsp, 130h
0x180005cea  pop     r15
0x180005cec  pop     r14
0x180005cee  pop     r13
0x180005cf0  pop     r12
0x180005cf2  pop     rdi
0x180005cf3  pop     rsi
0x180005cf4  pop     rbx
0x180005cf5  retn
```
