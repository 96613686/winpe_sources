# _DdcMsaHelper::GetUserTicket_::_1_::catch$32

- ea: `0x180029d53`
- end: `0x180029da8`
- name: `_DdcMsaHelper::GetUserTicket_::_1_::catch$32`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x180029d53`

## string_xrefs

- `0x180029d84`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmsahelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcMsaHelper::GetUserTicket_::_1_::catch_32(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
      192,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x180029d53  mov     [rsp+arg_8], rdx
0x180029d58  push    rbp
0x180029d59  sub     rsp, 30h
0x180029d5d  mov     rbp, rdx
0x180029d60  mov     dword ptr [rbp+38h], 8007000Eh
0x180029d67  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029d6e  jz      short loc_180029D97
0x180029d70  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180029d77  mov     [rsp+38h+var_10], rax
0x180029d7c  mov     [rsp+38h+var_18], 0C0h
0x180029d84  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029d8b  mov     r8d, 8007000Eh
0x180029d91  call    McTemplateU0dsqs_EventWriteTransfer
0x180029d96  nop
0x180029d97  mov     rax, 0
0x180029da1  add     rsp, 30h
0x180029da5  pop     rbp
0x180029da6  retn
```
