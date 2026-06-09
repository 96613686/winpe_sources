# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::catch$131

- ea: `0x18001e1af`
- end: `0x18001e204`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::catch$131`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001e1af`

## string_xrefs

- `0x18001e1e0`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmhttpwrapper.cpp`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::catch_131(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttpwrapper.cpp",
      80,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e1af  mov     [rsp+arg_8], rdx
0x18001e1b4  push    rbp
0x18001e1b5  sub     rsp, 30h
0x18001e1b9  mov     rbp, rdx
0x18001e1bc  mov     dword ptr [rbp+70h], 8007000Eh
0x18001e1c3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e1ca  jz      short loc_18001E1F3
0x18001e1cc  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e1d3  mov     [rsp+38h+var_10], rax
0x18001e1d8  mov     [rsp+38h+var_18], 350h
0x18001e1e0  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e1e7  mov     r8d, 8007000Eh
0x18001e1ed  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e1f2  nop
0x18001e1f3  mov     rax, 0
0x18001e1fd  add     rsp, 30h
0x18001e201  pop     rbp
0x18001e202  retn
```
