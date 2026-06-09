# DdcDeviceInfoHelper::SetMasterLocationSwitch(int)

- ea: `0x18001ae84`
- end: `0x18001af4d`
- name: `?SetMasterLocationSwitch@DdcDeviceInfoHelper@@SAJH@Z`
- size: `201`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800101f0`

## callees

- `0x1800050b8`
- `0x18001ae84`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aeb1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aeb1`

## string_xrefs

- `0x18001af15`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001aec6`: `CHR(CoCreateInstance( __uuidof(LocationManager), nullptr, CLSCTX_LOCAL_SERVER, __uuidof(**(pLocationManager.GetAddressOf())), IID_PPV_ARGS_Helper(pLocationManager.GetAddressOf())))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcDeviceInfoHelper::SetMasterLocationSwitch()
{
  int v0; // edx
  int v1; // ecx
  HRESULT v2; // ebx
  int v3; // edx
  int v4; // ecx
  LPVOID v5; // rcx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v2 = CoCreateInstance(
         &GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd,
         0,
         4u,
         &GUID_bb31bcf1_230a_4bea_abef_26a3887f122a,
         &ppv);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 104LL))(ppv, 1);
    if ( v2 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        v2,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        172,
        "CHR(pLocationManager->put_LocationMasterSwitch(fEnable))");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v1,
      v0,
      v2,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      170,
      "CHR(CoCreateInstance( __uuidof(LocationManager), nullptr, CLSCTX_LOCAL_SERVER, __uuidof(**(pLocationManager.GetAdd"
      "ressOf())), IID_PPV_ARGS_Helper(pLocationManager.GetAddressOf())))");
  }
  v5 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001ae84  push    rbx
0x18001ae86  sub     rsp, 30h
0x18001ae8a  mov     [rsp+38h+arg_8], 0
0x18001ae93  lea     rax, [rsp+38h+arg_8]
0x18001ae98  mov     [rsp+38h+ppv], rax; ppv
0x18001ae9d  lea     r9, _GUID_bb31bcf1_230a_4bea_abef_26a3887f122a; riid
0x18001aea4  xor     edx, edx; pUnkOuter
0x18001aea6  lea     r8d, [rdx+4]; dwClsContext
0x18001aeaa  lea     rcx, _GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd; rclsid
0x18001aeb1  call    cs:__imp_CoCreateInstance
0x18001aeb7  mov     ebx, eax
0x18001aeb9  test    eax, eax
0x18001aebb  jns     short loc_18001AEDC
0x18001aebd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001aec4  jz      short loc_18001AF25
0x18001aec6  lea     rax, aChrCocreateins_3; "CHR(CoCreateInstance( __uuidof(Location"...
0x18001aecd  mov     [rsp+38h+var_10], rax
0x18001aed2  mov     dword ptr [rsp+38h+ppv], 3AAh
0x18001aeda  jmp     short loc_18001AF15
0x18001aedc  mov     rcx, [rsp+38h+arg_8]
0x18001aee1  mov     rax, [rcx]
0x18001aee4  mov     edx, 1
0x18001aee9  mov     rax, [rax+68h]
0x18001aeed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aef2  mov     ebx, eax
0x18001aef4  test    eax, eax
0x18001aef6  jns     short loc_18001AF25
0x18001aef8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001aeff  jz      short loc_18001AF25
0x18001af01  lea     rax, aChrPlocationma_0; "CHR(pLocationManager->put_LocationMaste"...
0x18001af08  mov     [rsp+38h+var_10], rax
0x18001af0d  mov     dword ptr [rsp+38h+ppv], 3ACh
0x18001af15  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001af1c  mov     r8d, ebx
0x18001af1f  call    McTemplateU0dsqs_EventWriteTransfer
0x18001af24  nop
0x18001af25  mov     rcx, [rsp+38h+arg_8]
0x18001af2a  test    rcx, rcx
0x18001af2d  jz      short loc_18001AF45
0x18001af2f  mov     [rsp+38h+arg_8], 0
0x18001af38  mov     rax, [rcx]
0x18001af3b  mov     rax, [rax+10h]
0x18001af3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af44  nop
0x18001af45  mov     eax, ebx
0x18001af47  add     rsp, 30h
0x18001af4b  pop     rbx
0x18001af4c  retn
```
