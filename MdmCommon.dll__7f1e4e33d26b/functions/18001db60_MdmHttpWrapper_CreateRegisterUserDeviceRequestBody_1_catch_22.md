# _MdmHttpWrapper::CreateRegisterUserDeviceRequestBody_::_1_::catch$22

- ea: `0x18001db60`
- end: `0x18001dbb5`
- name: `_MdmHttpWrapper::CreateRegisterUserDeviceRequestBody_::_1_::catch$22`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001db60`

## string_xrefs

- `0x18001db91`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

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
0x18001db60  mov     [rsp+arg_8], rdx
0x18001db65  push    rbp
0x18001db66  sub     rsp, 30h
0x18001db6a  mov     rbp, rdx
0x18001db6d  mov     dword ptr [rbp+58h], 8007000Eh
0x18001db74  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001db7b  jz      short loc_18001DBA4
0x18001db7d  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001db84  mov     [rsp+38h+var_10], rax
0x18001db89  mov     [rsp+38h+var_18], 386h
0x18001db91  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001db98  mov     r8d, 8007000Eh
0x18001db9e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dba3  nop
0x18001dba4  mov     rax, 0
0x18001dbae  add     rsp, 30h
0x18001dbb2  pop     rbp
0x18001dbb3  retn
```
