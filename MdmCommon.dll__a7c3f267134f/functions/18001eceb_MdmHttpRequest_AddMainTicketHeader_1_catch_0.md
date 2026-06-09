# _MdmHttpRequest::AddMainTicketHeader_::_1_::catch$0

- ea: `0x18001eceb`
- end: `0x18001ed40`
- name: `_MdmHttpRequest::AddMainTicketHeader_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001eceb`

## string_xrefs

- `0x18001ed1c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

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
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      15,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001eceb  mov     [rsp+arg_8], rdx
0x18001ecf0  push    rbp
0x18001ecf1  sub     rsp, 30h
0x18001ecf5  mov     rbp, rdx
0x18001ecf8  mov     dword ptr [rbp+50h], 8007000Eh
0x18001ecff  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ed06  jz      short loc_18001ED2F
0x18001ed08  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001ed0f  mov     [rsp+38h+var_10], rax
0x18001ed14  mov     [rsp+38h+var_18], 30Fh
0x18001ed1c  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ed23  mov     r8d, 8007000Eh
0x18001ed29  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ed2e  nop
0x18001ed2f  mov     rax, 0
0x18001ed39  add     rsp, 30h
0x18001ed3d  pop     rbp
0x18001ed3e  retn
```
