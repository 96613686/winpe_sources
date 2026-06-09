# _DdcMsaHelper::CreateScope_::_1_::catch$17

- ea: `0x180029c0a`
- end: `0x180029c5f`
- name: `_DdcMsaHelper::CreateScope_::_1_::catch$17`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800050b8`
- `0x180029c0a`

## string_xrefs

- `0x180029c3b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmsahelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcMsaHelper::CreateScope_::_1_::catch_17(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmsahelper.cpp",
      235,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x180029c0a  mov     [rsp+arg_8], rdx
0x180029c0f  push    rbp
0x180029c10  sub     rsp, 30h
0x180029c14  mov     rbp, rdx
0x180029c17  mov     dword ptr [rbp+30h], 8007000Eh
0x180029c1e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029c25  jz      short loc_180029C4E
0x180029c27  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180029c2e  mov     [rsp+38h+var_10], rax
0x180029c33  mov     [rsp+38h+var_18], 0EBh
0x180029c3b  lea     r9, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029c42  mov     r8d, 8007000Eh
0x180029c48  call    McTemplateU0dsqs_EventWriteTransfer
0x180029c4d  nop
0x180029c4e  mov     rax, 0
0x180029c58  add     rsp, 30h
0x180029c5c  pop     rbp
0x180029c5d  retn
```
