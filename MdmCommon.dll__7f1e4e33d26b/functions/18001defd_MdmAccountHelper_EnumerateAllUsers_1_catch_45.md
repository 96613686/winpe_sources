# _MdmAccountHelper::EnumerateAllUsers_::_1_::catch$45

- ea: `0x18001defd`
- end: `0x18001df52`
- name: `_MdmAccountHelper::EnumerateAllUsers_::_1_::catch$45`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001defd`

## string_xrefs

- `0x18001df2e`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

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
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      177,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001defd  mov     [rsp+arg_8], rdx
0x18001df02  push    rbp
0x18001df03  sub     rsp, 30h
0x18001df07  mov     rbp, rdx
0x18001df0a  mov     dword ptr [rbp+40h], 8007000Eh
0x18001df11  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001df18  jz      short loc_18001DF41
0x18001df1a  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001df21  mov     [rsp+38h+var_10], rax
0x18001df26  mov     [rsp+38h+var_18], 0B1h
0x18001df2e  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001df35  mov     r8d, 8007000Eh
0x18001df3b  call    McTemplateU0dsqs_EventWriteTransfer
0x18001df40  nop
0x18001df41  mov     rax, 0
0x18001df4b  add     rsp, 30h
0x18001df4f  pop     rbp
0x18001df50  retn
```
