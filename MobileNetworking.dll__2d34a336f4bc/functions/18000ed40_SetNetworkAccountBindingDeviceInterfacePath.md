# SetNetworkAccountBindingDeviceInterfacePath

- ea: `0x18000ed40`
- end: `0x18000ed99`
- name: `SetNetworkAccountBindingDeviceInterfacePath`
- size: `89`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008ff0`
- `0x18000eac4`
- `0x18000ed40`

## string_xrefs

- `0x18000ed80`: `AccountBindingDeviceInterfacePath`

## pseudocode

```c
__int64 __fastcall SetNetworkAccountBindingDeviceInterfacePath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids);
  return SetBindingDeviceInterfacePath(a1, L"AccountBindingDeviceInterfacePath", a2);
}

```

## disassembly

```asm
0x18000ed40  mov     [rsp+arg_0], rbx
0x18000ed45  push    rdi
0x18000ed46  sub     rsp, 20h
0x18000ed4a  mov     rbx, rdx
0x18000ed4d  mov     rdi, rcx
0x18000ed50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed57  lea     rax, WPP_GLOBAL_Control
0x18000ed5e  cmp     rcx, rax
0x18000ed61  jz      short loc_18000ED7D
0x18000ed63  mov     edx, 10h
0x18000ed68  test    [rcx+1Ch], dl
0x18000ed6b  jz      short loc_18000ED7D
0x18000ed6d  mov     rcx, [rcx+10h]
0x18000ed71  lea     r8, WPP_e12f368a0cb238e419f0d89ee3ed1f0e_Traceguids
0x18000ed78  call    WPP_SF_
0x18000ed7d  mov     r8, rbx; unsigned __int16 *
0x18000ed80  lea     rdx, aAccountbinding; "AccountBindingDeviceInterfacePath"
0x18000ed87  mov     rcx, rdi; unsigned __int16 *
0x18000ed8a  mov     rbx, [rsp+28h+arg_0]
0x18000ed8f  add     rsp, 20h
0x18000ed93  pop     rdi
0x18000ed94  jmp     _SetBindingDeviceInterfacePath
```
