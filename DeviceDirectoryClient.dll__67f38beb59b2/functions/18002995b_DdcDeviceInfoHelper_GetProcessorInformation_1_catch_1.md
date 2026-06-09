# _DdcDeviceInfoHelper::GetProcessorInformation_::_1_::catch$1

- ea: `0x18002995b`
- end: `0x1800299b0`
- name: `_DdcDeviceInfoHelper::GetProcessorInformation_::_1_::catch$1`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x18002995b`

## string_xrefs

- `0x18002998c`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetProcessorInformation_::_1_::catch_1(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      171,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18002995b  mov     [rsp+arg_8], rdx
0x180029960  push    rbp
0x180029961  sub     rsp, 30h
0x180029965  mov     rbp, rdx
0x180029968  mov     dword ptr [rbp+30h], 8007000Eh
0x18002996f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029976  jz      short loc_18002999F
0x180029978  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x18002997f  mov     [rsp+38h+var_10], rax
0x180029984  mov     [rsp+38h+var_18], 5ABh
0x18002998c  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029993  mov     r8d, 8007000Eh
0x180029999  call    McTemplateU0dsqs_EventWriteTransfer
0x18002999e  nop
0x18002999f  mov     rax, 0
0x1800299a9  add     rsp, 30h
0x1800299ad  pop     rbp
0x1800299ae  retn
```
