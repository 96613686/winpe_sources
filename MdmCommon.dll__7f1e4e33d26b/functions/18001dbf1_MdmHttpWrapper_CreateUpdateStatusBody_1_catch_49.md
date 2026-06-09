# _MdmHttpWrapper::CreateUpdateStatusBody_::_1_::catch$49

- ea: `0x18001dbf1`
- end: `0x18001dc46`
- name: `_MdmHttpWrapper::CreateUpdateStatusBody_::_1_::catch$49`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006548`
- `0x18001dbf1`

## string_xrefs

- `0x18001dc22`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

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
0x18001dbf1  mov     [rsp+arg_8], rdx
0x18001dbf6  push    rbp
0x18001dbf7  sub     rsp, 30h
0x18001dbfb  mov     rbp, rdx
0x18001dbfe  mov     dword ptr [rbp+48h], 8007000Eh
0x18001dc05  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001dc0c  jz      short loc_18001DC35
0x18001dc0e  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001dc15  mov     [rsp+38h+var_10], rax
0x18001dc1a  mov     [rsp+38h+var_18], 43Bh
0x18001dc22  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001dc29  mov     r8d, 8007000Eh
0x18001dc2f  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dc34  nop
0x18001dc35  mov     rax, 0
0x18001dc3f  add     rsp, 30h
0x18001dc43  pop     rbp
0x18001dc44  retn
```
