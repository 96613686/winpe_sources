# _MdmHttpRequest::AddCorrelationVectorHeader_::_1_::catch$5

- ea: `0x18001ec35`
- end: `0x18001ec8a`
- name: `_MdmHttpRequest::AddCorrelationVectorHeader_::_1_::catch$5`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001ec35`

## string_xrefs

- `0x18001ec66`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddCorrelationVectorHeader_::_1_::catch_5(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      250,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001ec35  mov     [rsp+arg_8], rdx
0x18001ec3a  push    rbp
0x18001ec3b  sub     rsp, 30h
0x18001ec3f  mov     rbp, rdx
0x18001ec42  mov     dword ptr [rbp+30h], 8007000Eh
0x18001ec49  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ec50  jz      short loc_18001EC79
0x18001ec52  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001ec59  mov     [rsp+38h+var_10], rax
0x18001ec5e  mov     [rsp+38h+var_18], 2FAh
0x18001ec66  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001ec6d  mov     r8d, 8007000Eh
0x18001ec73  call    McTemplateU0dsqs_EventWriteTransfer
0x18001ec78  nop
0x18001ec79  mov     rax, 0
0x18001ec83  add     rsp, 30h
0x18001ec87  pop     rbp
0x18001ec88  retn
```
