# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$64

- ea: `0x18001e069`
- end: `0x18001e0be`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$64`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001e069`

## string_xrefs

- `0x18001e09a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch_64(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      83,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001e069  mov     [rsp+arg_8], rdx
0x18001e06e  push    rbp
0x18001e06f  sub     rsp, 30h
0x18001e073  mov     rbp, rdx
0x18001e076  mov     dword ptr [rbp+48h], 8007000Eh
0x18001e07d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001e084  jz      short loc_18001E0AD
0x18001e086  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001e08d  mov     [rsp+38h+var_10], rax
0x18001e092  mov     [rsp+38h+var_18], 153h
0x18001e09a  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001e0a1  mov     r8d, 8007000Eh
0x18001e0a7  call    McTemplateU0dsqs_EventWriteTransfer
0x18001e0ac  nop
0x18001e0ad  mov     rax, 0
0x18001e0b7  add     rsp, 30h
0x18001e0bb  pop     rbp
0x18001e0bc  retn
```
