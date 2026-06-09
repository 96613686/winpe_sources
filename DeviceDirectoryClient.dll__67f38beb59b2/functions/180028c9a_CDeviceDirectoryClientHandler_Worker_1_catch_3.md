# _CDeviceDirectoryClientHandler::Worker_::_1_::catch$3

- ea: `0x180028c9a`
- end: `0x180028cef`
- name: `_CDeviceDirectoryClientHandler::Worker_::_1_::catch$3`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800050b8`
- `0x180028c9a`

## string_xrefs

- `0x180028ccb`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\dll\devicedirectoryclient.cpp`

## pseudocode

```c
__int64 __fastcall CDeviceDirectoryClientHandler::Worker_::_1_::catch_3(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
      248,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x180028c9a  mov     [rsp+arg_8], rdx
0x180028c9f  push    rbp
0x180028ca0  sub     rsp, 30h
0x180028ca4  mov     rbp, rdx
0x180028ca7  mov     dword ptr [rbp+38h], 8007000Eh
0x180028cae  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180028cb5  jz      short loc_180028CDE
0x180028cb7  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180028cbe  mov     [rsp+38h+var_10], rax
0x180028cc3  mov     [rsp+38h+var_18], 0F8h
0x180028ccb  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180028cd2  mov     r8d, 8007000Eh
0x180028cd8  call    McTemplateU0dsqs_EventWriteTransfer
0x180028cdd  nop
0x180028cde  mov     rax, 0
0x180028ce8  add     rsp, 30h
0x180028cec  pop     rbp
0x180028ced  retn
```
