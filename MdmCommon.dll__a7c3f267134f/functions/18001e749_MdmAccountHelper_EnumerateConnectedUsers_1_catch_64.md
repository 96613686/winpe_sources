# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$64

- ea: `0x18001e749`
- end: `0x18001e79e`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$64`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e749`

## string_xrefs

- `0x18001e77a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch_64(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      83,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e749  mov     [rsp+arg_8], rdx
0x18001e74e  push    rbp
0x18001e74f  sub     rsp, 30h
0x18001e753  mov     rbp, rdx
0x18001e756  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e75d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e764  jz      short loc_18001E78D
0x18001e766  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e76d  mov     [rsp+38h+var_10], rax
0x18001e772  mov     [rsp+38h+var_18], 153h
0x18001e77a  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e781  mov     r8d, 8007000Eh
0x18001e787  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e78c  nop
0x18001e78d  mov     rax, 0
0x18001e797  add     rsp, 30h
0x18001e79b  pop     rbp
0x18001e79c  retn
```
