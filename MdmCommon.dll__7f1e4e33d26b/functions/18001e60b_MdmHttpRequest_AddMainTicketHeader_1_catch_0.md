# _MdmHttpRequest::AddMainTicketHeader_::_1_::catch$0

- ea: `0x18001e60b`
- end: `0x18001e660`
- name: `_MdmHttpRequest::AddMainTicketHeader_::_1_::catch$0`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001e60b`

## string_xrefs

- `0x18001e63c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddMainTicketHeader_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 80) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      15,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e60b  mov     [rsp+arg_8], rdx
0x18001e610  push    rbp
0x18001e611  sub     rsp, 30h
0x18001e615  mov     rbp, rdx
0x18001e618  mov     dword ptr [rbp+50h], 8007000Eh
0x18001e61f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e626  jz      short loc_18001E64F
0x18001e628  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e62f  mov     [rsp+38h+var_10], rax
0x18001e634  mov     [rsp+38h+var_18], 30Fh
0x18001e63c  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e643  mov     r8d, 8007000Eh
0x18001e649  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e64e  nop
0x18001e64f  mov     rax, 0
0x18001e659  add     rsp, 30h
0x18001e65d  pop     rbp
0x18001e65e  retn
```
