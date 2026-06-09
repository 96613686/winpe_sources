# _MdmAccountHelper::EnumerateAllUsers_::_1_::catch$46

- ea: `0x18001df58`
- end: `0x18001dfad`
- name: `_MdmAccountHelper::EnumerateAllUsers_::_1_::catch$46`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001df58`

## string_xrefs

- `0x18001df89`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

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
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      96,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001df58  mov     [rsp+arg_8], rdx
0x18001df5d  push    rbp
0x18001df5e  sub     rsp, 30h
0x18001df62  mov     rbp, rdx
0x18001df65  mov     dword ptr [rbp+40h], 8007000Eh
0x18001df6c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001df73  jz      short loc_18001DF9C
0x18001df75  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001df7c  mov     [rsp+38h+var_10], rax
0x18001df81  mov     [rsp+38h+var_18], 60h ; '`'
0x18001df89  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001df90  mov     r8d, 8007000Eh
0x18001df96  call    McTemplateU0dsqs_EventWriteTransfer
0x18001df9b  nop
0x18001df9c  mov     rax, 0
0x18001dfa6  add     rsp, 30h
0x18001dfaa  pop     rbp
0x18001dfab  retn
```
