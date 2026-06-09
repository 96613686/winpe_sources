# _MdmHttpWrapper::RegistrationTriggerToString_::_1_::catch$0

- ea: `0x18001dda4`
- end: `0x18001ddf9`
- name: `_MdmHttpWrapper::RegistrationTriggerToString_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001dda4`

## string_xrefs

- `0x18001ddd5`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::RegistrationTriggerToString_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      25,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001dda4  mov     [rsp+arg_8], rdx
0x18001dda9  push    rbp
0x18001ddaa  sub     rsp, 30h
0x18001ddae  mov     rbp, rdx
0x18001ddb1  mov     dword ptr [rbp+40h], 8007000Eh
0x18001ddb8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ddbf  jz      short loc_18001DDE8
0x18001ddc1  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001ddc8  mov     [rsp+38h+var_10], rax
0x18001ddcd  mov     [rsp+38h+var_18], 519h
0x18001ddd5  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001dddc  mov     r8d, 8007000Eh
0x18001dde2  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dde7  nop
0x18001dde8  mov     rax, 0
0x18001ddf2  add     rsp, 30h
0x18001ddf6  pop     rbp
0x18001ddf7  retn
```
