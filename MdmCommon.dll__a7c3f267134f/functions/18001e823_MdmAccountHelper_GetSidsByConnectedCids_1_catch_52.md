# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$52

- ea: `0x18001e823`
- end: `0x18001e878`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::catch$52`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e823`

## string_xrefs

- `0x18001e854`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

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
0x18001e823  mov     [rsp+arg_8], rdx
0x18001e828  push    rbp
0x18001e829  sub     rsp, 30h
0x18001e82d  mov     rbp, rdx
0x18001e830  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e837  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e83e  jz      short loc_18001E867
0x18001e840  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e847  mov     [rsp+38h+var_10], rax
0x18001e84c  mov     [rsp+38h+var_18], 1C1h
0x18001e854  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e85b  mov     r8d, 8007000Eh
0x18001e861  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e866  nop
0x18001e867  mov     rax, 0
0x18001e871  add     rsp, 30h
0x18001e875  pop     rbp
0x18001e876  retn
```
