# _MdmHttpWrapper::CreateUpdateStatusBody_::_1_::catch$49

- ea: `0x18001e2d1`
- end: `0x18001e326`
- name: `_MdmHttpWrapper::CreateUpdateStatusBody_::_1_::catch$49`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e2d1`

## string_xrefs

- `0x18001e302`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateUpdateStatusBody_::_1_::catch_49(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      59,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e2d1  mov     [rsp+arg_8], rdx
0x18001e2d6  push    rbp
0x18001e2d7  sub     rsp, 30h
0x18001e2db  mov     rbp, rdx
0x18001e2de  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e2e5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e2ec  jz      short loc_18001E315
0x18001e2ee  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e2f5  mov     [rsp+38h+var_10], rax
0x18001e2fa  mov     [rsp+38h+var_18], 43Bh
0x18001e302  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e309  mov     r8d, 8007000Eh
0x18001e30f  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e314  nop
0x18001e315  mov     rax, 0
0x18001e31f  add     rsp, 30h
0x18001e323  pop     rbp
0x18001e324  retn
```
