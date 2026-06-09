# _DdcDeviceInfoHelper::GetOemSerialNumber_::_1_::catch$0

- ea: `0x1800298a5`
- end: `0x1800298fa`
- name: `_DdcDeviceInfoHelper::GetOemSerialNumber_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x1800298a5`

## string_xrefs

- `0x1800298d6`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetOemSerialNumber_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 80) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      147,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x1800298a5  mov     [rsp+arg_8], rdx
0x1800298aa  push    rbp
0x1800298ab  sub     rsp, 30h
0x1800298af  mov     rbp, rdx
0x1800298b2  mov     dword ptr [rbp+50h], 8007000Eh
0x1800298b9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800298c0  jz      short loc_1800298E9
0x1800298c2  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x1800298c9  mov     [rsp+38h+var_10], rax
0x1800298ce  mov     [rsp+38h+var_18], 493h
0x1800298d6  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800298dd  mov     r8d, 8007000Eh
0x1800298e3  call    McTemplateU0dsqs_EventWriteTransfer
0x1800298e8  nop
0x1800298e9  mov     rax, 0
0x1800298f3  add     rsp, 30h
0x1800298f7  pop     rbp
0x1800298f8  retn
```
