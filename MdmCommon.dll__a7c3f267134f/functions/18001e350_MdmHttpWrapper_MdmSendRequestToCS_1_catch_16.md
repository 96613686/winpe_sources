# _MdmHttpWrapper::MdmSendRequestToCS_::_1_::catch$16

- ea: `0x18001e350`
- end: `0x18001e3a5`
- name: `_MdmHttpWrapper::MdmSendRequestToCS_::_1_::catch$16`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e350`

## string_xrefs

- `0x18001e381`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

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
0x18001e350  mov     [rsp+arg_8], rdx
0x18001e355  push    rbp
0x18001e356  sub     rsp, 50h
0x18001e35a  mov     rbp, rdx
0x18001e35d  mov     dword ptr [rbp+70h], 8007000Eh
0x18001e364  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e36b  jz      short loc_18001E394
0x18001e36d  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e374  mov     [rsp+58h+var_30], rax
0x18001e379  mov     [rsp+58h+var_38], 1E2h
0x18001e381  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e388  mov     r8d, 8007000Eh
0x18001e38e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e393  nop
0x18001e394  mov     rax, 0
0x18001e39e  add     rsp, 50h
0x18001e3a2  pop     rbp
0x18001e3a3  retn
```
