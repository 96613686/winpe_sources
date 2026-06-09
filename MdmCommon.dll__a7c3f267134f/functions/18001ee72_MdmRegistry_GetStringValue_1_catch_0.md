# _MdmRegistry::GetStringValue_::_1_::catch$0

- ea: `0x18001ee72`
- end: `0x18001eec7`
- name: `_MdmRegistry::GetStringValue_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800065c0`
- `0x18001ee72`

## string_xrefs

- `0x18001eea3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::GetStringValue_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 52) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
      138,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001ee72  mov     [rsp+arg_8], rdx
0x18001ee77  push    rbp
0x18001ee78  sub     rsp, 30h
0x18001ee7c  mov     rbp, rdx
0x18001ee7f  mov     dword ptr [rbp+34h], 8007000Eh
0x18001ee86  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001ee8d  jz      short loc_18001EEB6
0x18001ee8f  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001ee96  mov     [rsp+38h+var_10], rax
0x18001ee9b  mov     [rsp+38h+var_18], 18Ah
0x18001eea3  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001eeaa  mov     r8d, 8007000Eh
0x18001eeb0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001eeb5  nop
0x18001eeb6  mov     rax, 0
0x18001eec0  add     rsp, 30h
0x18001eec4  pop     rbp
0x18001eec5  retn
```
