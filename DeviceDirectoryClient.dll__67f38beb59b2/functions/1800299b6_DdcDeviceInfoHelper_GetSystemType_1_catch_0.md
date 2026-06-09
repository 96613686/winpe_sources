# _DdcDeviceInfoHelper::GetSystemType_::_1_::catch$0

- ea: `0x1800299b6`
- end: `0x180029a0b`
- name: `_DdcDeviceInfoHelper::GetSystemType_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x1800299b6`

## string_xrefs

- `0x1800299e7`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetSystemType_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      146,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x1800299b6  mov     [rsp+arg_8], rdx
0x1800299bb  push    rbp
0x1800299bc  sub     rsp, 30h
0x1800299c0  mov     rbp, rdx
0x1800299c3  mov     dword ptr [rbp+40h], 8007000Eh
0x1800299ca  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800299d1  jz      short loc_1800299FA
0x1800299d3  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x1800299da  mov     [rsp+38h+var_10], rax
0x1800299df  mov     [rsp+38h+var_18], 592h
0x1800299e7  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800299ee  mov     r8d, 8007000Eh
0x1800299f4  call    McTemplateU0dsqs_EventWriteTransfer
0x1800299f9  nop
0x1800299fa  mov     rax, 0
0x180029a04  add     rsp, 30h
0x180029a08  pop     rbp
0x180029a09  retn
```
