# _MdmAccountHelper::EnumerateAllUsers_::_1_::catch$43

- ea: `0x18001e527`
- end: `0x18001e57c`
- name: `_MdmAccountHelper::EnumerateAllUsers_::_1_::catch$43`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e527`

## string_xrefs

- `0x18001e558`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateAllUsers_::_1_::catch_43(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      149,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e527  mov     [rsp+arg_8], rdx
0x18001e52c  push    rbp
0x18001e52d  sub     rsp, 30h
0x18001e531  mov     rbp, rdx
0x18001e534  mov     dword ptr [rbp+40h], 8007000Eh
0x18001e53b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e542  jz      short loc_18001E56B
0x18001e544  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e54b  mov     [rsp+38h+var_10], rax
0x18001e550  mov     [rsp+38h+var_18], 95h
0x18001e558  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e55f  mov     r8d, 8007000Eh
0x18001e565  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e56a  nop
0x18001e56b  mov     rax, 0
0x18001e575  add     rsp, 30h
0x18001e579  pop     rbp
0x18001e57a  retn
```
