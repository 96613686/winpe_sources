# DdcDeviceInfoHelper::MasterLocationSwitchOn(int *)

- ea: `0x18001a8e4`
- end: `0x18001aa01`
- name: `?MasterLocationSwitchOn@DdcDeviceInfoHelper@@SAJPEAH@Z`
- size: `285`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800101f0`
- `0x1800183c4`

## callees

- `0x1800050b8`
- `0x18001a8e4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a965`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a965`

## string_xrefs

- `0x18001a92d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001a97a`: `CHR(CoCreateInstance( __uuidof(LocationManager), nullptr, CLSCTX_LOCAL_SERVER, __uuidof(**(pLocationManager.GetAddressOf())), IID_PPV_ARGS_Helper(pLocationManager.GetAddressOf())))`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DdcDeviceInfoHelper::MasterLocationSwitchOn(int *a1, int a2)
{
  HRESULT v3; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // edx
  int v7; // ecx
  LPVOID v8; // rcx
  int v10; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v10 = 0;
  if ( a1 )
  {
    *a1 = 0;
    v3 = CoCreateInstance(
           &GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd,
           0,
           4u,
           &GUID_bb31bcf1_230a_4bea_abef_26a3887f122a,
           &ppv);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 96LL))(ppv, &v10);
      if ( v3 >= 0 )
      {
        *a1 = v10;
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v3,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          153,
          "CHR(pLocationManager->get_LocationMasterSwitch(&fMasterLocationSwitchOn))");
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        v3,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        151,
        "CHR(CoCreateInstance( __uuidof(LocationManager), nullptr, CLSCTX_LOCAL_SERVER, __uuidof(**(pLocationManager.GetA"
        "ddressOf())), IID_PPV_ARGS_Helper(pLocationManager.GetAddressOf())))");
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        144,
        "CPR(pfMasterLocationSwitchOn)");
  }
  v8 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a8e4  mov     [rsp+arg_10], rbx
0x18001a8e9  push    rdi
0x18001a8ea  sub     rsp, 30h
0x18001a8ee  mov     rdi, rcx
0x18001a8f1  mov     [rsp+38h+arg_8], 0
0x18001a8fa  mov     [rsp+38h+arg_0], 0
0x18001a902  test    rcx, rcx
0x18001a905  jnz     short loc_18001A941
0x18001a907  mov     ebx, 80070057h
0x18001a90c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a913  jz      loc_18001A9D4
0x18001a919  lea     rax, aCprPfmasterloc; "CPR(pfMasterLocationSwitchOn)"
0x18001a920  mov     [rsp+38h+var_10], rax
0x18001a925  mov     dword ptr [rsp+38h+ppv], 390h
0x18001a92d  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001a934  mov     r8d, ebx
0x18001a937  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a93c  jmp     loc_18001A9D4
0x18001a941  mov     dword ptr [rcx], 0
0x18001a947  lea     rax, [rsp+38h+arg_8]
0x18001a94c  mov     [rsp+38h+ppv], rax; ppv
0x18001a951  lea     r9, _GUID_bb31bcf1_230a_4bea_abef_26a3887f122a; riid
0x18001a958  xor     edx, edx; pUnkOuter
0x18001a95a  lea     r8d, [rdx+4]; dwClsContext
0x18001a95e  lea     rcx, _GUID_08d9dfdf_c6f7_404a_a20f_66eec0a609cd; rclsid
0x18001a965  call    cs:__imp_CoCreateInstance
0x18001a96b  mov     ebx, eax
0x18001a96d  test    eax, eax
0x18001a96f  jns     short loc_18001A990
0x18001a971  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a978  jz      short loc_18001A9D4
0x18001a97a  lea     rax, aChrCocreateins_3; "CHR(CoCreateInstance( __uuidof(Location"...
0x18001a981  mov     [rsp+38h+var_10], rax
0x18001a986  mov     dword ptr [rsp+38h+ppv], 397h
0x18001a98e  jmp     short loc_18001A92D
0x18001a990  mov     rcx, [rsp+38h+arg_8]
0x18001a995  mov     rax, [rcx]
0x18001a998  lea     rdx, [rsp+38h+arg_0]
0x18001a99d  mov     rax, [rax+60h]
0x18001a9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9a6  mov     ebx, eax
0x18001a9a8  test    eax, eax
0x18001a9aa  jns     short loc_18001A9CE
0x18001a9ac  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a9b3  jz      short loc_18001A9D4
0x18001a9b5  lea     rax, aChrPlocationma; "CHR(pLocationManager->get_LocationMaste"...
0x18001a9bc  mov     [rsp+38h+var_10], rax
0x18001a9c1  mov     dword ptr [rsp+38h+ppv], 399h
0x18001a9c9  jmp     loc_18001A92D
0x18001a9ce  mov     eax, [rsp+38h+arg_0]
0x18001a9d2  mov     [rdi], eax
0x18001a9d4  mov     rcx, [rsp+38h+arg_8]
0x18001a9d9  test    rcx, rcx
0x18001a9dc  jz      short loc_18001A9F4
0x18001a9de  mov     [rsp+38h+arg_8], 0
0x18001a9e7  mov     rax, [rcx]
0x18001a9ea  mov     rax, [rax+10h]
0x18001a9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9f3  nop
0x18001a9f4  mov     eax, ebx
0x18001a9f6  mov     rbx, [rsp+38h+arg_10]
0x18001a9fb  add     rsp, 30h
0x18001a9ff  pop     rdi
0x18001aa00  retn
```
