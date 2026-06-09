# _DdcDeviceInfoHelper::GetHardwareSpecifications_::_1_::catch$3

- ea: `0x18002984a`
- end: `0x18002989f`
- name: `_DdcDeviceInfoHelper::GetHardwareSpecifications_::_1_::catch$3`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x18002984a`

## string_xrefs

- `0x18002987b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetHardwareSpecifications_::_1_::catch_3(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      220,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18002984a  mov     [rsp+arg_8], rdx
0x18002984f  push    rbp
0x180029850  sub     rsp, 30h
0x180029854  mov     rbp, rdx
0x180029857  mov     dword ptr [rbp+30h], 8007000Eh
0x18002985e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029865  jz      short loc_18002988E
0x180029867  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x18002986e  mov     [rsp+38h+var_10], rax
0x180029873  mov     [rsp+38h+var_18], 5DCh
0x18002987b  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029882  mov     r8d, 8007000Eh
0x180029888  call    McTemplateU0dsqs_EventWriteTransfer
0x18002988d  nop
0x18002988e  mov     rax, 0
0x180029898  add     rsp, 30h
0x18002989c  pop     rbp
0x18002989d  retn
```
