# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$53

- ea: `0x18001e87e`
- end: `0x18001e8d3`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$53`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e87e`

## string_xrefs

- `0x18001e8af`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

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
0x18001e87e  mov     [rsp+arg_8], rdx
0x18001e883  push    rbp
0x18001e884  sub     rsp, 30h
0x18001e888  mov     rbp, rdx
0x18001e88b  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e892  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e899  jz      short loc_18001E8C2
0x18001e89b  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e8a2  mov     [rsp+38h+var_10], rax
0x18001e8a7  mov     [rsp+38h+var_18], 1AAh
0x18001e8af  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e8b6  mov     r8d, 8007000Eh
0x18001e8bc  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e8c1  nop
0x18001e8c2  mov     rax, 0
0x18001e8cc  add     rsp, 30h
0x18001e8d0  pop     rbp
0x18001e8d1  retn
```
