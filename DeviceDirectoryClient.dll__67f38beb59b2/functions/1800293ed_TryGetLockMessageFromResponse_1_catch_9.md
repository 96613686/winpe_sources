# _TryGetLockMessageFromResponse_::_1_::catch$9

- ea: `0x1800293ed`
- end: `0x180029442`
- name: `_TryGetLockMessageFromResponse_::_1_::catch$9`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x1800293ed`

## string_xrefs

- `0x18002941e`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`

## pseudocode

```c
__int64 __fastcall TryGetLockMessageFromResponse_::_1_::catch_9(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 88) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
      122,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x1800293ed  mov     [rsp+arg_8], rdx
0x1800293f2  push    rbp
0x1800293f3  sub     rsp, 30h
0x1800293f7  mov     rbp, rdx
0x1800293fa  mov     dword ptr [rbp+58h], 8007000Eh
0x180029401  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029408  jz      short loc_180029431
0x18002940a  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180029411  mov     [rsp+38h+var_10], rax
0x180029416  mov     [rsp+38h+var_18], 17Ah
0x18002941e  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029425  mov     r8d, 8007000Eh
0x18002942b  call    McTemplateU0dsqs_EventWriteTransfer
0x180029430  nop
0x180029431  mov     rax, 0
0x18002943b  add     rsp, 30h
0x18002943f  pop     rbp
0x180029440  retn
```
