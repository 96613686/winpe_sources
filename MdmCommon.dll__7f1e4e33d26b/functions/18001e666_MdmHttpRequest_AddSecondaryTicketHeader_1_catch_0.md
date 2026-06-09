# _MdmHttpRequest::AddSecondaryTicketHeader_::_1_::catch$0

- ea: `0x18001e666`
- end: `0x18001e6bb`
- name: `_MdmHttpRequest::AddSecondaryTicketHeader_::_1_::catch$0`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001e666`

## string_xrefs

- `0x18001e697`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddSecondaryTicketHeader_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 80) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      36,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e666  mov     [rsp+arg_8], rdx
0x18001e66b  push    rbp
0x18001e66c  sub     rsp, 30h
0x18001e670  mov     rbp, rdx
0x18001e673  mov     dword ptr [rbp+50h], 8007000Eh
0x18001e67a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e681  jz      short loc_18001E6AA
0x18001e683  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e68a  mov     [rsp+38h+var_10], rax
0x18001e68f  mov     [rsp+38h+var_18], 324h
0x18001e697  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e69e  mov     r8d, 8007000Eh
0x18001e6a4  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e6a9  nop
0x18001e6aa  mov     rax, 0
0x18001e6b4  add     rsp, 30h
0x18001e6b8  pop     rbp
0x18001e6b9  retn
```
