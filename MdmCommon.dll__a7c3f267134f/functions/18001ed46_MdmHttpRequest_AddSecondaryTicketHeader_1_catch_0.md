# _MdmHttpRequest::AddSecondaryTicketHeader_::_1_::catch$0

- ea: `0x18001ed46`
- end: `0x18001ed9b`
- name: `_MdmHttpRequest::AddSecondaryTicketHeader_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001ed46`

## string_xrefs

- `0x18001ed77`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

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
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      36,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001ed46  mov     [rsp+arg_8], rdx
0x18001ed4b  push    rbp
0x18001ed4c  sub     rsp, 30h
0x18001ed50  mov     rbp, rdx
0x18001ed53  mov     dword ptr [rbp+50h], 8007000Eh
0x18001ed5a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ed61  jz      short loc_18001ED8A
0x18001ed63  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001ed6a  mov     [rsp+38h+var_10], rax
0x18001ed6f  mov     [rsp+38h+var_18], 324h
0x18001ed77  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ed7e  mov     r8d, 8007000Eh
0x18001ed84  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ed89  nop
0x18001ed8a  mov     rax, 0
0x18001ed94  add     rsp, 30h
0x18001ed98  pop     rbp
0x18001ed99  retn
```
