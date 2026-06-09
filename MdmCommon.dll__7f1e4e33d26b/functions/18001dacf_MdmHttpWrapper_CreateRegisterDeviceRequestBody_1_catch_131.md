# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::catch$131

- ea: `0x18001dacf`
- end: `0x18001db24`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::catch$131`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001dacf`

## string_xrefs

- `0x18001db00`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::catch_131(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      80,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001dacf  mov     [rsp+arg_8], rdx
0x18001dad4  push    rbp
0x18001dad5  sub     rsp, 30h
0x18001dad9  mov     rbp, rdx
0x18001dadc  mov     dword ptr [rbp+70h], 8007000Eh
0x18001dae3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001daea  jz      short loc_18001DB13
0x18001daec  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001daf3  mov     [rsp+38h+var_10], rax
0x18001daf8  mov     [rsp+38h+var_18], 350h
0x18001db00  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001db07  mov     r8d, 8007000Eh
0x18001db0d  call    McTemplateU0dsqs_EventWriteTransfer
0x18001db12  nop
0x18001db13  mov     rax, 0
0x18001db1d  add     rsp, 30h
0x18001db21  pop     rbp
0x18001db22  retn
```
