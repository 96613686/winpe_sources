# GetNetworkAccountBindingDeviceInterfacePath

- ea: `0x18000dc20`
- end: `0x18000dc8a`
- name: `GetNetworkAccountBindingDeviceInterfacePath`
- size: `106`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e6a0`

## callees

- `0x180008ff0`
- `0x18000da00`
- `0x18000dc20`

## string_xrefs

- `0x18000dc69`: `AccountBindingDeviceInterfacePath`

## pseudocode

```c
__int64 __fastcall GetNetworkAccountBindingDeviceInterfacePath(unsigned __int16 *a1, __int64 a2, _WORD *a3)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_805f8623832e3be342dd4daabae23659_Traceguids);
  return GetBindingDeviceInterfacePath(a1, L"AccountBindingDeviceInterfacePath", a2, a3);
}

```

## disassembly

```asm
0x18000dc20  mov     [rsp+arg_0], rbx
0x18000dc25  mov     [rsp+arg_8], rsi
0x18000dc2a  push    rdi
0x18000dc2b  sub     rsp, 20h
0x18000dc2f  mov     rbx, r8
0x18000dc32  mov     rdi, rdx
0x18000dc35  mov     rsi, rcx
0x18000dc38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc3f  lea     rax, WPP_GLOBAL_Control
0x18000dc46  cmp     rcx, rax
0x18000dc49  jz      short loc_18000DC66
0x18000dc4b  test    byte ptr [rcx+1Ch], 10h
0x18000dc4f  jz      short loc_18000DC66
0x18000dc51  mov     rcx, [rcx+10h]
0x18000dc55  lea     r8, WPP_805f8623832e3be342dd4daabae23659_Traceguids
0x18000dc5c  mov     edx, 0Fh
0x18000dc61  call    WPP_SF_
0x18000dc66  mov     r9, rbx
0x18000dc69  lea     rdx, aAccountbinding; "AccountBindingDeviceInterfacePath"
0x18000dc70  mov     r8, rdi
0x18000dc73  mov     rcx, rsi; unsigned __int16 *
0x18000dc76  mov     rbx, [rsp+28h+arg_0]
0x18000dc7b  mov     rsi, [rsp+28h+arg_8]
0x18000dc80  add     rsp, 20h
0x18000dc84  pop     rdi
0x18000dc85  jmp     _GetBindingDeviceInterfacePath
```
