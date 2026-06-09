# _DdcDeviceInfoHelper::GetProcessorInformation_::_1_::catch$0

- ea: `0x180029900`
- end: `0x180029955`
- name: `_DdcDeviceInfoHelper::GetProcessorInformation_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x180029900`

## string_xrefs

- `0x180029931`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetProcessorInformation_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      183,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x180029900  mov     [rsp+arg_8], rdx
0x180029905  push    rbp
0x180029906  sub     rsp, 30h
0x18002990a  mov     rbp, rdx
0x18002990d  mov     dword ptr [rbp+30h], 8007000Eh
0x180029914  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002991b  jz      short loc_180029944
0x18002991d  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180029924  mov     [rsp+38h+var_10], rax
0x180029929  mov     [rsp+38h+var_18], 5B7h
0x180029931  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029938  mov     r8d, 8007000Eh
0x18002993e  call    McTemplateU0dsqs_EventWriteTransfer
0x180029943  nop
0x180029944  mov     rax, 0
0x18002994e  add     rsp, 30h
0x180029952  pop     rbp
0x180029953  retn
```
