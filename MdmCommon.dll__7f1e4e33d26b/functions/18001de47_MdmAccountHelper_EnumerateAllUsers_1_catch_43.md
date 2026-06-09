# _MdmAccountHelper::EnumerateAllUsers_::_1_::catch$43

- ea: `0x18001de47`
- end: `0x18001de9c`
- name: `_MdmAccountHelper::EnumerateAllUsers_::_1_::catch$43`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001de47`

## string_xrefs

- `0x18001de78`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

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
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      149,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001de47  mov     [rsp+arg_8], rdx
0x18001de4c  push    rbp
0x18001de4d  sub     rsp, 30h
0x18001de51  mov     rbp, rdx
0x18001de54  mov     dword ptr [rbp+40h], 8007000Eh
0x18001de5b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001de62  jz      short loc_18001DE8B
0x18001de64  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001de6b  mov     [rsp+38h+var_10], rax
0x18001de70  mov     [rsp+38h+var_18], 95h
0x18001de78  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001de7f  mov     r8d, 8007000Eh
0x18001de85  call    McTemplateU0dsqs_EventWriteTransfer
0x18001de8a  nop
0x18001de8b  mov     rax, 0
0x18001de95  add     rsp, 30h
0x18001de99  pop     rbp
0x18001de9a  retn
```
