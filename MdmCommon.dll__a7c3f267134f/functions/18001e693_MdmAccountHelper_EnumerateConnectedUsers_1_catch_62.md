# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$62

- ea: `0x18001e693`
- end: `0x18001e6e8`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$62`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e693`

## string_xrefs

- `0x18001e6c4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch_62(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      55,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e693  mov     [rsp+arg_8], rdx
0x18001e698  push    rbp
0x18001e699  sub     rsp, 30h
0x18001e69d  mov     rbp, rdx
0x18001e6a0  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e6a7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e6ae  jz      short loc_18001E6D7
0x18001e6b0  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e6b7  mov     [rsp+38h+var_10], rax
0x18001e6bc  mov     [rsp+38h+var_18], 137h
0x18001e6c4  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e6cb  mov     r8d, 8007000Eh
0x18001e6d1  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e6d6  nop
0x18001e6d7  mov     rax, 0
0x18001e6e1  add     rsp, 30h
0x18001e6e5  pop     rbp
0x18001e6e6  retn
```
