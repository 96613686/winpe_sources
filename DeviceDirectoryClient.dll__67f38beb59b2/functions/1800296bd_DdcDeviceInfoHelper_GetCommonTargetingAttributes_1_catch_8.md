# _DdcDeviceInfoHelper::GetCommonTargetingAttributes_::_1_::catch$8

- ea: `0x1800296bd`
- end: `0x180029712`
- name: `_DdcDeviceInfoHelper::GetCommonTargetingAttributes_::_1_::catch$8`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x1800296bd`

## string_xrefs

- `0x1800296ee`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetCommonTargetingAttributes_::_1_::catch_8(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      235,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x1800296bd  mov     [rsp+arg_8], rdx
0x1800296c2  push    rbp
0x1800296c3  sub     rsp, 30h
0x1800296c7  mov     rbp, rdx
0x1800296ca  mov     dword ptr [rbp+48h], 8007000Eh
0x1800296d1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800296d8  jz      short loc_180029701
0x1800296da  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x1800296e1  mov     [rsp+38h+var_10], rax
0x1800296e6  mov     [rsp+38h+var_18], 6EBh
0x1800296ee  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800296f5  mov     r8d, 8007000Eh
0x1800296fb  call    McTemplateU0dsqs_EventWriteTransfer
0x180029700  nop
0x180029701  mov     rax, 0
0x18002970b  add     rsp, 30h
0x18002970f  pop     rbp
0x180029710  retn
```
