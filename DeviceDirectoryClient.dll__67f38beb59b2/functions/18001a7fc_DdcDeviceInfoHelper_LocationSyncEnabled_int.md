# DdcDeviceInfoHelper::LocationSyncEnabled(int *)

- ea: `0x18001a7fc`
- end: `0x18001a87e`
- name: `?LocationSyncEnabled@DdcDeviceInfoHelper@@SAJPEAH@Z`
- size: `130`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800101f0`
- `0x1800183c4`

## callees

- `0x1800050b8`
- `0x18001a7fc`

## import_xrefs

- `MdmCommon!MdmIsFindMyDeviceEnabled` at `0x18001a83e`
- `MdmCommon!MdmIsFindMyDeviceEnabled` at `0x18001a83e`

## string_xrefs

- `0x18001a867`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::LocationSyncEnabled(int *a1, int a2)
{
  int MyDeviceEnabled; // ebx
  int v3; // edx
  int v4; // ecx
  int v6; // [rsp+40h] [rbp+8h] BYREF

  v6 = 0;
  if ( a1 )
  {
    *a1 = 0;
    MyDeviceEnabled = MdmIsFindMyDeviceEnabled(a1, &v6);
    if ( MyDeviceEnabled < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        MyDeviceEnabled,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        104,
        "CHR(hr)");
  }
  else
  {
    MyDeviceEnabled = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        100,
        "CPR(pfLocationSyncEnabled)");
  }
  return (unsigned int)MyDeviceEnabled;
}

```

## disassembly

```asm
0x18001a7fc  push    rbx
0x18001a7fe  sub     rsp, 30h
0x18001a802  mov     [rsp+38h+arg_0], 0
0x18001a80a  test    rcx, rcx
0x18001a80d  jnz     short loc_18001A833
0x18001a80f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a816  mov     ebx, 80070057h
0x18001a81b  jz      short loc_18001A876
0x18001a81d  lea     rax, aCprPflocations; "CPR(pfLocationSyncEnabled)"
0x18001a824  mov     [rsp+38h+var_10], rax
0x18001a829  mov     [rsp+38h+var_18], 364h
0x18001a831  jmp     short loc_18001A867
0x18001a833  lea     rdx, [rsp+38h+arg_0]
0x18001a838  mov     dword ptr [rcx], 0
0x18001a83e  call    cs:__imp_?MdmIsFindMyDeviceEnabled@@YAJPEAH0@Z; MdmIsFindMyDeviceEnabled(int *,int *)
0x18001a844  mov     ebx, eax
0x18001a846  test    eax, eax
0x18001a848  jns     short loc_18001A876
0x18001a84a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a851  jz      short loc_18001A876
0x18001a853  lea     rax, aChrHr; "CHR(hr)"
0x18001a85a  mov     [rsp+38h+var_10], rax
0x18001a85f  mov     [rsp+38h+var_18], 368h
0x18001a867  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001a86e  mov     r8d, ebx
0x18001a871  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a876  mov     eax, ebx
0x18001a878  add     rsp, 30h
0x18001a87c  pop     rbx
0x18001a87d  retn
```
