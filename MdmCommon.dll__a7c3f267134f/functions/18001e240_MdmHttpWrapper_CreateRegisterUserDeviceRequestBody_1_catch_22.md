# _MdmHttpWrapper::CreateRegisterUserDeviceRequestBody_::_1_::catch$22

- ea: `0x18001e240`
- end: `0x18001e295`
- name: `_MdmHttpWrapper::CreateRegisterUserDeviceRequestBody_::_1_::catch$22`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e240`

## string_xrefs

- `0x18001e271`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterUserDeviceRequestBody_::_1_::catch_22(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 88) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      134,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e240  mov     [rsp+arg_8], rdx
0x18001e245  push    rbp
0x18001e246  sub     rsp, 30h
0x18001e24a  mov     rbp, rdx
0x18001e24d  mov     dword ptr [rbp+58h], 8007000Eh
0x18001e254  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e25b  jz      short loc_18001E284
0x18001e25d  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e264  mov     [rsp+38h+var_10], rax
0x18001e269  mov     [rsp+38h+var_18], 386h
0x18001e271  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e278  mov     r8d, 8007000Eh
0x18001e27e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e283  nop
0x18001e284  mov     rax, 0
0x18001e28e  add     rsp, 30h
0x18001e292  pop     rbp
0x18001e293  retn
```
