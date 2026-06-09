# _MdmAccountHelper::EnumerateAllUsers_::_1_::catch$46

- ea: `0x18001e638`
- end: `0x18001e68d`
- name: `_MdmAccountHelper::EnumerateAllUsers_::_1_::catch$46`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e638`

## string_xrefs

- `0x18001e669`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateAllUsers_::_1_::catch_46(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      96,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e638  mov     [rsp+arg_8], rdx
0x18001e63d  push    rbp
0x18001e63e  sub     rsp, 30h
0x18001e642  mov     rbp, rdx
0x18001e645  mov     dword ptr [rbp+40h], 8007000Eh
0x18001e64c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e653  jz      short loc_18001E67C
0x18001e655  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e65c  mov     [rsp+38h+var_10], rax
0x18001e661  mov     [rsp+38h+var_18], 60h ; '`'
0x18001e669  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e670  mov     r8d, 8007000Eh
0x18001e676  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e67b  nop
0x18001e67c  mov     rax, 0
0x18001e686  add     rsp, 30h
0x18001e68a  pop     rbp
0x18001e68b  retn
```
