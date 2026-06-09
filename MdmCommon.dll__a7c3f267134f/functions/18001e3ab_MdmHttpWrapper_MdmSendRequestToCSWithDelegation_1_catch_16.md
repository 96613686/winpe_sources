# _MdmHttpWrapper::MdmSendRequestToCSWithDelegation_::_1_::catch$16

- ea: `0x18001e3ab`
- end: `0x18001e400`
- name: `_MdmHttpWrapper::MdmSendRequestToCSWithDelegation_::_1_::catch$16`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e3ab`

## string_xrefs

- `0x18001e3dc`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::MdmSendRequestToCSWithDelegation_::_1_::catch_16(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      140,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e3ab  mov     [rsp+arg_8], rdx
0x18001e3b0  push    rbp
0x18001e3b1  sub     rsp, 50h
0x18001e3b5  mov     rbp, rdx
0x18001e3b8  mov     dword ptr [rbp+70h], 8007000Eh
0x18001e3bf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e3c6  jz      short loc_18001E3EF
0x18001e3c8  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e3cf  mov     [rsp+58h+var_30], rax
0x18001e3d4  mov     [rsp+58h+var_38], 18Ch
0x18001e3dc  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e3e3  mov     r8d, 8007000Eh
0x18001e3e9  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e3ee  nop
0x18001e3ef  mov     rax, 0
0x18001e3f9  add     rsp, 50h
0x18001e3fd  pop     rbp
0x18001e3fe  retn
```
