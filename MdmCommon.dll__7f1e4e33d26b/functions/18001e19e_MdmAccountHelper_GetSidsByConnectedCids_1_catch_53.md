# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$53

- ea: `0x18001e19e`
- end: `0x18001e1f3`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$53`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006548`
- `0x18001e19e`

## string_xrefs

- `0x18001e1cf`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch_53(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      170,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e19e  mov     [rsp+arg_8], rdx
0x18001e1a3  push    rbp
0x18001e1a4  sub     rsp, 30h
0x18001e1a8  mov     rbp, rdx
0x18001e1ab  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e1b2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e1b9  jz      short loc_18001E1E2
0x18001e1bb  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e1c2  mov     [rsp+38h+var_10], rax
0x18001e1c7  mov     [rsp+38h+var_18], 1AAh
0x18001e1cf  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e1d6  mov     r8d, 8007000Eh
0x18001e1dc  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e1e1  nop
0x18001e1e2  mov     rax, 0
0x18001e1ec  add     rsp, 30h
0x18001e1f0  pop     rbp
0x18001e1f1  retn
```
