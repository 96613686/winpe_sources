# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$52

- ea: `0x18001e143`
- end: `0x18001e198`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$52`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006548`
- `0x18001e143`

## string_xrefs

- `0x18001e174`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch_52(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      193,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e143  mov     [rsp+arg_8], rdx
0x18001e148  push    rbp
0x18001e149  sub     rsp, 30h
0x18001e14d  mov     rbp, rdx
0x18001e150  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e157  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e15e  jz      short loc_18001E187
0x18001e160  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e167  mov     [rsp+38h+var_10], rax
0x18001e16c  mov     [rsp+38h+var_18], 1C1h
0x18001e174  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e17b  mov     r8d, 8007000Eh
0x18001e181  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e186  nop
0x18001e187  mov     rax, 0
0x18001e191  add     rsp, 30h
0x18001e195  pop     rbp
0x18001e196  retn
```
