# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$63

- ea: `0x18001e00e`
- end: `0x18001e063`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$63`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001e00e`

## string_xrefs

- `0x18001e03f`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

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
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      69,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e00e  mov     [rsp+arg_8], rdx
0x18001e013  push    rbp
0x18001e014  sub     rsp, 30h
0x18001e018  mov     rbp, rdx
0x18001e01b  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e022  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e029  jz      short loc_18001E052
0x18001e02b  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e032  mov     [rsp+38h+var_10], rax
0x18001e037  mov     [rsp+38h+var_18], 145h
0x18001e03f  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e046  mov     r8d, 8007000Eh
0x18001e04c  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e051  nop
0x18001e052  mov     rax, 0
0x18001e05c  add     rsp, 30h
0x18001e060  pop     rbp
0x18001e061  retn
```
