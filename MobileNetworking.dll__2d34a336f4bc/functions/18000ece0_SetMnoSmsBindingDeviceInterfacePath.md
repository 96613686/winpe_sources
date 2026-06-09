# SetMnoSmsBindingDeviceInterfacePath

- ea: `0x18000ece0`
- end: `0x18000ed3a`
- name: `SetMnoSmsBindingDeviceInterfacePath`
- size: `90`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008ff0`
- `0x18000eac4`
- `0x18000ece0`

## string_xrefs

- `0x18000ed21`: `SmsProviderBindingDeviceInterfacePath`

## pseudocode

```c
__int64 __fastcall SetMnoSmsBindingDeviceInterfacePath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids);
  return SetBindingDeviceInterfacePath(a1, L"SmsProviderBindingDeviceInterfacePath", a2);
}

```

## disassembly

```asm
0x18000ece0  mov     [rsp+arg_0], rbx
0x18000ece5  push    rdi
0x18000ece6  sub     rsp, 20h
0x18000ecea  mov     rbx, rdx
0x18000eced  mov     rdi, rcx
0x18000ecf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecf7  lea     rax, WPP_GLOBAL_Control
0x18000ecfe  cmp     rcx, rax
0x18000ed01  jz      short loc_18000ED1E
0x18000ed03  test    byte ptr [rcx+1Ch], 10h
0x18000ed07  jz      short loc_18000ED1E
0x18000ed09  mov     rcx, [rcx+10h]
0x18000ed0d  lea     r8, WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids
0x18000ed14  mov     edx, 11h
0x18000ed19  call    WPP_SF_
0x18000ed1e  mov     r8, rbx; unsigned __int16 *
0x18000ed21  lea     rdx, aSmsproviderbin; "SmsProviderBindingDeviceInterfacePath"
0x18000ed28  mov     rcx, rdi; unsigned __int16 *
0x18000ed2b  mov     rbx, [rsp+28h+arg_0]
0x18000ed30  add     rsp, 20h
0x18000ed34  pop     rdi
0x18000ed35  jmp     _SetBindingDeviceInterfacePath
```
