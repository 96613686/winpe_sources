# MdmGetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)

- ea: `0x1800035d0`
- end: `0x1800036ac`
- name: `?MdmGetLocation@@YAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800035d0`
- `0x1800064f0`
- `0x180006548`
- `0x180016bf0`

## string_xrefs

- `0x18000363d`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall MdmGetLocation(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  int v5; // edx
  int Location; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  int v10; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-30h] BYREF
  int *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  v4 = a1;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_TRACE_GET_LOCATION, a3, 1, v11);
  Location = MdmLocationHelper::GetLocation(v4, a2);
  if ( Location < 0 )
  {
    v8 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_7;
    McTemplateU0dsqs_EventWriteTransfer(
      Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits,
      v5,
      Location,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      48,
      "CHR(MdmLocationHelper::GetLocation(desiredAccuracy, pResult))");
  }
  v8 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v8 & 2) != 0 )
  {
    v10 = Location;
    v12 = &v10;
    v13 = 4;
    McGenEventWrite_EventWriteTransfer(v8, MDMCOMMON_TRACE_GET_LOCATION_RESULT, v7, 2, v11);
  }
  return (unsigned int)Location;
}

```

## disassembly

```asm
0x1800035d0  mov     [rsp+arg_10], rbx
0x1800035d5  push    rdi
0x1800035d6  sub     rsp, 60h
0x1800035da  mov     rax, cs:__security_cookie
0x1800035e1  xor     rax, rsp
0x1800035e4  mov     [rsp+68h+var_10], rax
0x1800035e9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x1800035f0  mov     rdi, rdx
0x1800035f3  mov     ebx, ecx
0x1800035f5  jz      short loc_180003613
0x1800035f7  lea     rax, [rsp+68h+var_30]
0x1800035fc  mov     r9d, 1
0x180003602  lea     rdx, MDMCOMMON_TRACE_GET_LOCATION
0x180003609  mov     [rsp+68h+var_48], rax
0x18000360e  call    McGenEventWrite_EventWriteTransfer
0x180003613  mov     rdx, rdi
0x180003616  mov     ecx, ebx
0x180003618  call    ?GetLocation@MdmLocationHelper@@SAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z; MdmLocationHelper::GetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)
0x18000361d  mov     ebx, eax
0x18000361f  test    eax, eax
0x180003621  jns     short loc_180003651
0x180003623  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180003629  test    cl, 1
0x18000362c  jz      short loc_180003657
0x18000362e  lea     rax, aChrMdmlocation; "CHR(MdmLocationHelper::GetLocation(desi"...
0x180003635  mov     r8d, ebx
0x180003638  mov     [rsp+68h+var_40], rax
0x18000363d  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003644  mov     dword ptr [rsp+68h+var_48], 230h
0x18000364c  call    McTemplateU0dsqs_EventWriteTransfer
0x180003651  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180003657  test    cl, 2
0x18000365a  jz      short loc_18000368F
0x18000365c  lea     rax, [rsp+68h+var_38]
0x180003661  mov     [rsp+68h+var_38], ebx
0x180003665  mov     [rsp+68h+var_20], rax
0x18000366a  lea     rdx, MDMCOMMON_TRACE_GET_LOCATION_RESULT
0x180003671  lea     rax, [rsp+68h+var_30]
0x180003676  mov     [rsp+68h+var_18], 4
0x18000367f  mov     r9d, 2
0x180003685  mov     [rsp+68h+var_48], rax
0x18000368a  call    McGenEventWrite_EventWriteTransfer
0x18000368f  mov     eax, ebx
0x180003691  mov     rcx, [rsp+68h+var_10]
0x180003696  xor     rcx, rsp; StackCookie
0x180003699  call    __security_check_cookie
0x18000369e  mov     rbx, [rsp+68h+arg_10]
0x1800036a6  add     rsp, 60h
0x1800036aa  pop     rdi
0x1800036ab  retn
```
