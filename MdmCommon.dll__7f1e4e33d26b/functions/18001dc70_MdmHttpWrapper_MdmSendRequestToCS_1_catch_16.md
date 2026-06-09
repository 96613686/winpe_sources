# _MdmHttpWrapper::MdmSendRequestToCS_::_1_::catch$16

- ea: `0x18001dc70`
- end: `0x18001dcc5`
- name: `_MdmHttpWrapper::MdmSendRequestToCS_::_1_::catch$16`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001dc70`

## string_xrefs

- `0x18001dca1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::MdmSendRequestToCS_::_1_::catch_16(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      226,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001dc70  mov     [rsp+arg_8], rdx
0x18001dc75  push    rbp
0x18001dc76  sub     rsp, 50h
0x18001dc7a  mov     rbp, rdx
0x18001dc7d  mov     dword ptr [rbp+70h], 8007000Eh
0x18001dc84  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001dc8b  jz      short loc_18001DCB4
0x18001dc8d  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001dc94  mov     [rsp+58h+var_30], rax
0x18001dc99  mov     [rsp+58h+var_38], 1E2h
0x18001dca1  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001dca8  mov     r8d, 8007000Eh
0x18001dcae  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dcb3  nop
0x18001dcb4  mov     rax, 0
0x18001dcbe  add     rsp, 50h
0x18001dcc2  pop     rbp
0x18001dcc3  retn
```
