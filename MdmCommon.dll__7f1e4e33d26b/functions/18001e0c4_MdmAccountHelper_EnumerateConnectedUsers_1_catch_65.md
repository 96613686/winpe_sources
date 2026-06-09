# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$65

- ea: `0x18001e0c4`
- end: `0x18001e119`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$65`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001e0c4`

## string_xrefs

- `0x18001e0f5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

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
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      12,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e0c4  mov     [rsp+arg_8], rdx
0x18001e0c9  push    rbp
0x18001e0ca  sub     rsp, 30h
0x18001e0ce  mov     rbp, rdx
0x18001e0d1  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e0d8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e0df  jz      short loc_18001E108
0x18001e0e1  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e0e8  mov     [rsp+38h+var_10], rax
0x18001e0ed  mov     [rsp+38h+var_18], 10Ch
0x18001e0f5  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e0fc  mov     r8d, 8007000Eh
0x18001e102  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e107  nop
0x18001e108  mov     rax, 0
0x18001e112  add     rsp, 30h
0x18001e116  pop     rbp
0x18001e117  retn
```
