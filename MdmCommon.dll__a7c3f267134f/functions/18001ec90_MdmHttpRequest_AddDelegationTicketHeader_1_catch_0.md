# _MdmHttpRequest::AddDelegationTicketHeader_::_1_::catch$0

- ea: `0x18001ec90`
- end: `0x18001ece5`
- name: `_MdmHttpRequest::AddDelegationTicketHeader_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001ec90`

## string_xrefs

- `0x18001ecc1`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

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
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      75,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001ec90  mov     [rsp+arg_8], rdx
0x18001ec95  push    rbp
0x18001ec96  sub     rsp, 30h
0x18001ec9a  mov     rbp, rdx
0x18001ec9d  mov     dword ptr [rbp+60h], 8007000Eh
0x18001eca4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ecab  jz      short loc_18001ECD4
0x18001ecad  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001ecb4  mov     [rsp+38h+var_10], rax
0x18001ecb9  mov     [rsp+38h+var_18], 34Bh
0x18001ecc1  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ecc8  mov     r8d, 8007000Eh
0x18001ecce  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ecd3  nop
0x18001ecd4  mov     rax, 0
0x18001ecde  add     rsp, 30h
0x18001ece2  pop     rbp
0x18001ece3  retn
```
