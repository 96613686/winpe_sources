# _DdcRegistry::GetStringValue_::_1_::catch$0

- ea: `0x180029a35`
- end: `0x180029a8a`
- name: `_DdcRegistry::GetStringValue_::_1_::catch$0`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800050b8`
- `0x180029a35`

## string_xrefs

- `0x180029a66`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
__int64 __fastcall DdcRegistry::GetStringValue_::_1_::catch_0(int a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      a2,
      -2147024882,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
      28,
      "CHR(((HRESULT)0x8007000EL))");
  return 0;
}

```

## disassembly

```asm
0x180029a35  mov     [rsp+arg_8], rdx
0x180029a3a  push    rbp
0x180029a3b  sub     rsp, 30h
0x180029a3f  mov     rbp, rdx
0x180029a42  mov     dword ptr [rbp+30h], 8007000Eh
0x180029a49  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180029a50  jz      short loc_180029A79
0x180029a52  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x8007000EL))"
0x180029a59  mov     [rsp+38h+var_10], rax
0x180029a5e  mov     [rsp+38h+var_18], 11Ch
0x180029a66  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180029a6d  mov     r8d, 8007000Eh
0x180029a73  call    McTemplateU0dsqs_EventWriteTransfer
0x180029a78  nop
0x180029a79  mov     rax, 0
0x180029a83  add     rsp, 30h
0x180029a87  pop     rbp
0x180029a88  retn
```
