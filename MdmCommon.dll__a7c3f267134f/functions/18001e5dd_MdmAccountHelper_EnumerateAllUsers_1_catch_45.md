# _MdmAccountHelper::EnumerateAllUsers_::_1_::catch$45

- ea: `0x18001e5dd`
- end: `0x18001e632`
- name: `_MdmAccountHelper::EnumerateAllUsers_::_1_::catch$45`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e5dd`

## string_xrefs

- `0x18001e60e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateAllUsers_::_1_::catch_45(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      177,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e5dd  mov     [rsp+arg_8], rdx
0x18001e5e2  push    rbp
0x18001e5e3  sub     rsp, 30h
0x18001e5e7  mov     rbp, rdx
0x18001e5ea  mov     dword ptr [rbp+40h], 8007000Eh
0x18001e5f1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e5f8  jz      short loc_18001E621
0x18001e5fa  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e601  mov     [rsp+38h+var_10], rax
0x18001e606  mov     [rsp+38h+var_18], 0B1h
0x18001e60e  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e615  mov     r8d, 8007000Eh
0x18001e61b  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e620  nop
0x18001e621  mov     rax, 0
0x18001e62b  add     rsp, 30h
0x18001e62f  pop     rbp
0x18001e630  retn
```
