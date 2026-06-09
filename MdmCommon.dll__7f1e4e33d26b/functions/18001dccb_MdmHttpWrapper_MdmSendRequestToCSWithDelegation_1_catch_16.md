# _MdmHttpWrapper::MdmSendRequestToCSWithDelegation_::_1_::catch$16

- ea: `0x18001dccb`
- end: `0x18001dd20`
- name: `_MdmHttpWrapper::MdmSendRequestToCSWithDelegation_::_1_::catch$16`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001dccb`

## string_xrefs

- `0x18001dcfc`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

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
0x18001dccb  mov     [rsp+arg_8], rdx
0x18001dcd0  push    rbp
0x18001dcd1  sub     rsp, 50h
0x18001dcd5  mov     rbp, rdx
0x18001dcd8  mov     dword ptr [rbp+70h], 8007000Eh
0x18001dcdf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001dce6  jz      short loc_18001DD0F
0x18001dce8  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001dcef  mov     [rsp+58h+var_30], rax
0x18001dcf4  mov     [rsp+58h+var_38], 18Ch
0x18001dcfc  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001dd03  mov     r8d, 8007000Eh
0x18001dd09  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dd0e  nop
0x18001dd0f  mov     rax, 0
0x18001dd19  add     rsp, 50h
0x18001dd1d  pop     rbp
0x18001dd1e  retn
```
