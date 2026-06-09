# _MdmAccountHelper::EnumerateAllUsers_::_1_::catch$44

- ea: `0x18001dea2`
- end: `0x18001def7`
- name: `_MdmAccountHelper::EnumerateAllUsers_::_1_::catch$44`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001dea2`

## string_xrefs

- `0x18001ded3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateAllUsers_::_1_::catch_44(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      163,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001dea2  mov     [rsp+arg_8], rdx
0x18001dea7  push    rbp
0x18001dea8  sub     rsp, 30h
0x18001deac  mov     rbp, rdx
0x18001deaf  mov     dword ptr [rbp+40h], 8007000Eh
0x18001deb6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001debd  jz      short loc_18001DEE6
0x18001debf  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001dec6  mov     [rsp+38h+var_10], rax
0x18001decb  mov     [rsp+38h+var_18], 0A3h
0x18001ded3  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001deda  mov     r8d, 8007000Eh
0x18001dee0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dee5  nop
0x18001dee6  mov     rax, 0
0x18001def0  add     rsp, 30h
0x18001def4  pop     rbp
0x18001def5  retn
```
