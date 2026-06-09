# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$63

- ea: `0x18001e6ee`
- end: `0x18001e743`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$63`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e6ee`

## string_xrefs

- `0x18001e71f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch_63(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      69,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e6ee  mov     [rsp+arg_8], rdx
0x18001e6f3  push    rbp
0x18001e6f4  sub     rsp, 30h
0x18001e6f8  mov     rbp, rdx
0x18001e6fb  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e702  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e709  jz      short loc_18001E732
0x18001e70b  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e712  mov     [rsp+38h+var_10], rax
0x18001e717  mov     [rsp+38h+var_18], 145h
0x18001e71f  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e726  mov     r8d, 8007000Eh
0x18001e72c  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e731  nop
0x18001e732  mov     rax, 0
0x18001e73c  add     rsp, 30h
0x18001e740  pop     rbp
0x18001e741  retn
```
