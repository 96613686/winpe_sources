# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$65

- ea: `0x18001e7a4`
- end: `0x18001e7f9`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$65`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e7a4`

## string_xrefs

- `0x18001e7d5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch_65(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      12,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e7a4  mov     [rsp+arg_8], rdx
0x18001e7a9  push    rbp
0x18001e7aa  sub     rsp, 30h
0x18001e7ae  mov     rbp, rdx
0x18001e7b1  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e7b8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e7bf  jz      short loc_18001E7E8
0x18001e7c1  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e7c8  mov     [rsp+38h+var_10], rax
0x18001e7cd  mov     [rsp+38h+var_18], 10Ch
0x18001e7d5  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e7dc  mov     r8d, 8007000Eh
0x18001e7e2  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e7e7  nop
0x18001e7e8  mov     rax, 0
0x18001e7f2  add     rsp, 30h
0x18001e7f6  pop     rbp
0x18001e7f7  retn
```
