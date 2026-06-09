# _GetLockScreenTitle_::_1_::catch$0

- ea: `0x18002924e`
- end: `0x1800292a3`
- name: `_GetLockScreenTitle_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x18002924e`

## string_xrefs

- `0x18002927f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`

## pseudocode

```c
__int64 __fastcall GetLockScreenTitle_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 52) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      "onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
      207,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x18002924e  mov     [rsp+arg_8], rdx
0x180029253  push    rbp
0x180029254  sub     rsp, 30h
0x180029258  mov     rbp, rdx
0x18002925b  mov     dword ptr [rbp+34h], 8007000Eh
0x180029262  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029269  jz      short loc_180029292
0x18002926b  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180029272  mov     [rsp+38h+var_10], rax
0x180029277  mov     [rsp+38h+var_18], 1CFh
0x18002927f  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029286  mov     r8d, 8007000Eh
0x18002928c  call    McTemplateU0dsqs_EventWriteTransfer
0x180029291  nop
0x180029292  mov     rax, 0
0x18002929c  add     rsp, 30h
0x1800292a0  pop     rbp
0x1800292a1  retn
```
