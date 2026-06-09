# MdmGetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)

- ea: `0x1800035e0`
- end: `0x1800036bd`
- name: `?MdmGetLocation@@YAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x1800035e0`
- `0x180006560`
- `0x1800065c0`
- `0x1800170f0`

## string_xrefs

- `0x18000364d`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`

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
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+38h] [rbp-30h] BYREF
  int *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  v4 = a1;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_GET_LOCATION, a3, 1u, &v11);
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
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
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
    McGenEventWrite_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)MDMCOMMON_TRACE_GET_LOCATION_RESULT, v7, 2u, &v11);
  }
  return (unsigned int)Location;
}

```

## disassembly

```asm
0x1800035e0  mov     [rsp+arg_10], rbx
0x1800035e5  push    rdi
0x1800035e6  sub     rsp, 60h
0x1800035ea  mov     rax, cs:__security_cookie
0x1800035f1  xor     rax, rsp
0x1800035f4  mov     [rsp+68h+var_10], rax
0x1800035f9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003600  mov     rdi, rdx
0x180003603  mov     ebx, ecx
0x180003605  jz      short loc_180003623
0x180003607  lea     rax, [rsp+68h+var_30]
0x18000360c  mov     r9d, 1
0x180003612  lea     rdx, MDMCOMMON_TRACE_GET_LOCATION
0x180003619  mov     [rsp+68h+var_48], rax
0x18000361e  call    McGenEventWrite_EventWriteTransfer
0x180003623  mov     rdx, rdi
0x180003626  mov     ecx, ebx
0x180003628  call    ?GetLocation@MdmLocationHelper@@SAJW4PositionAccuracy@Geolocation@Devices@Windows@@PEAUMdmLocation@@@Z; MdmLocationHelper::GetLocation(Windows::Devices::Geolocation::PositionAccuracy,MdmLocation *)
0x18000362d  mov     ebx, eax
0x18000362f  test    eax, eax
0x180003631  jns     short loc_180003661
0x180003633  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180003639  test    cl, 1
0x18000363c  jz      short loc_180003667
0x18000363e  lea     rax, aChrMdmlocation; "CHR(MdmLocationHelper::GetLocation(desi"...
0x180003645  mov     r8d, ebx
0x180003648  mov     [rsp+68h+var_40], rax
0x18000364d  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180003654  mov     dword ptr [rsp+68h+var_48], 230h
0x18000365c  call    McTemplateU0dsqs_EventWriteTransfer
0x180003661  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x180003667  test    cl, 2
0x18000366a  jz      short loc_18000369F
0x18000366c  lea     rax, [rsp+68h+var_38]
0x180003671  mov     [rsp+68h+var_38], ebx
0x180003675  mov     [rsp+68h+var_20], rax
0x18000367a  lea     rdx, MDMCOMMON_TRACE_GET_LOCATION_RESULT
0x180003681  lea     rax, [rsp+68h+var_30]
0x180003686  mov     [rsp+68h+var_18], 4
0x18000368f  mov     r9d, 2
0x180003695  mov     [rsp+68h+var_48], rax
0x18000369a  call    McGenEventWrite_EventWriteTransfer
0x18000369f  mov     eax, ebx
0x1800036a1  mov     rcx, [rsp+68h+var_10]
0x1800036a6  xor     rcx, rsp; StackCookie
0x1800036a9  call    __security_check_cookie
0x1800036ae  mov     rbx, [rsp+68h+arg_10]
0x1800036b6  add     rsp, 60h
0x1800036ba  pop     rdi
0x1800036bb  retn
```
