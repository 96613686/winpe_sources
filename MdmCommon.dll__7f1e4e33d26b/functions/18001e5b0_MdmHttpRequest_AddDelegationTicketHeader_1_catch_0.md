# _MdmHttpRequest::AddDelegationTicketHeader_::_1_::catch$0

- ea: `0x18001e5b0`
- end: `0x18001e605`
- name: `_MdmHttpRequest::AddDelegationTicketHeader_::_1_::catch$0`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001e5b0`

## string_xrefs

- `0x18001e5e1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddDelegationTicketHeader_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      75,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e5b0  mov     [rsp+arg_8], rdx
0x18001e5b5  push    rbp
0x18001e5b6  sub     rsp, 30h
0x18001e5ba  mov     rbp, rdx
0x18001e5bd  mov     dword ptr [rbp+60h], 8007000Eh
0x18001e5c4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e5cb  jz      short loc_18001E5F4
0x18001e5cd  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e5d4  mov     [rsp+38h+var_10], rax
0x18001e5d9  mov     [rsp+38h+var_18], 34Bh
0x18001e5e1  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e5e8  mov     r8d, 8007000Eh
0x18001e5ee  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e5f3  nop
0x18001e5f4  mov     rax, 0
0x18001e5fe  add     rsp, 30h
0x18001e602  pop     rbp
0x18001e603  retn
```
