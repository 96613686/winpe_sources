# _MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$62

- ea: `0x18001dfb3`
- end: `0x18001e008`
- name: `_MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch$62`
- size: `85`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006548`
- `0x18001dfb3`

## string_xrefs

- `0x18001dfe4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmaccounthelper.cpp`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::EnumerateConnectedUsers_::_1_::catch_62(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 72) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmaccounthelper.cpp",
      55,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18001dfb3  mov     [rsp+arg_8], rdx
0x18001dfb8  push    rbp
0x18001dfb9  sub     rsp, 30h
0x18001dfbd  mov     rbp, rdx
0x18001dfc0  mov     dword ptr [rbp+48h], 8007000Eh
0x18001dfc7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001dfce  jz      short loc_18001DFF7
0x18001dfd0  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8007000EL))"
0x18001dfd7  mov     [rsp+38h+var_10], rax
0x18001dfdc  mov     [rsp+38h+var_18], 137h
0x18001dfe4  lea     r9, aOnecoreuapShel_10; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001dfeb  mov     r8d, 8007000Eh
0x18001dff1  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dff6  nop
0x18001dff7  mov     rax, 0
0x18001e001  add     rsp, 30h
0x18001e005  pop     rbp
0x18001e006  retn
```
