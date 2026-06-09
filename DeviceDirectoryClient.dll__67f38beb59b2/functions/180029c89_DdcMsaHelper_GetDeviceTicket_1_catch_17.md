# _DdcMsaHelper::GetDeviceTicket_::_1_::catch$17

- ea: `0x180029c89`
- end: `0x180029ce1`
- name: `_DdcMsaHelper::GetDeviceTicket_::_1_::catch$17`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x180029c89`

## string_xrefs

- `0x180029cbd`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmsahelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcMsaHelper::GetDeviceTicket_::_1_::catch_17(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 128) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
      77,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x180029c89  mov     [rsp+arg_8], rdx
0x180029c8e  push    rbp
0x180029c8f  sub     rsp, 30h
0x180029c93  mov     rbp, rdx
0x180029c96  mov     dword ptr [rbp+80h], 8007000Eh
0x180029ca0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029ca7  jz      short loc_180029CD0
0x180029ca9  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180029cb0  mov     [rsp+38h+var_10], rax
0x180029cb5  mov     [rsp+38h+var_18], 4Dh ; 'M'
0x180029cbd  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029cc4  mov     r8d, 8007000Eh
0x180029cca  call    McTemplateU0dsqs_EventWriteTransfer
0x180029ccf  nop
0x180029cd0  mov     rax, 0
0x180029cda  add     rsp, 30h
0x180029cde  pop     rbp
0x180029cdf  retn
```
