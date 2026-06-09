# _MdmHttpRequest::AddCorrelationVectorHeader_::_1_::catch$5

- ea: `0x18001e555`
- end: `0x18001e5aa`
- name: `_MdmHttpRequest::AddCorrelationVectorHeader_::_1_::catch$5`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001e555`

## string_xrefs

- `0x18001e586`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttprequest.cpp`

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
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
      250,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e555  mov     [rsp+arg_8], rdx
0x18001e55a  push    rbp
0x18001e55b  sub     rsp, 30h
0x18001e55f  mov     rbp, rdx
0x18001e562  mov     dword ptr [rbp+30h], 8007000Eh
0x18001e569  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e570  jz      short loc_18001E599
0x18001e572  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e579  mov     [rsp+38h+var_10], rax
0x18001e57e  mov     [rsp+38h+var_18], 2FAh
0x18001e586  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e58d  mov     r8d, 8007000Eh
0x18001e593  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e598  nop
0x18001e599  mov     rax, 0
0x18001e5a3  add     rsp, 30h
0x18001e5a7  pop     rbp
0x18001e5a8  retn
```
