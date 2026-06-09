# GetMnoSmsBindingDeviceInterfacePath

- ea: `0x18000dbb0`
- end: `0x18000dc19`
- name: `GetMnoSmsBindingDeviceInterfacePath`
- size: `105`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _WORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008ff0`
- `0x18000da00`
- `0x18000dbb0`

## string_xrefs

- `0x18000dbf8`: `SmsProviderBindingDeviceInterfacePath`

## pseudocode

```c
__int64 __fastcall GetMnoSmsBindingDeviceInterfacePath(unsigned __int16 *a1, __int64 a2, _WORD *a3)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_805f8623832e3be342dd4daabae23659_Traceguids);
  return GetBindingDeviceInterfacePath(a1, L"SmsProviderBindingDeviceInterfacePath", a2, a3);
}

```

## disassembly

```asm
0x18000dbb0  mov     [rsp+arg_0], rbx
0x18000dbb5  mov     [rsp+arg_8], rsi
0x18000dbba  push    rdi
0x18000dbbb  sub     rsp, 20h
0x18000dbbf  mov     rbx, r8
0x18000dbc2  mov     rdi, rdx
0x18000dbc5  mov     rsi, rcx
0x18000dbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbcf  lea     rax, WPP_GLOBAL_Control
0x18000dbd6  cmp     rcx, rax
0x18000dbd9  jz      short loc_18000DBF5
0x18000dbdb  mov     edx, 10h
0x18000dbe0  test    [rcx+1Ch], dl
0x18000dbe3  jz      short loc_18000DBF5
0x18000dbe5  mov     rcx, [rcx+10h]
0x18000dbe9  lea     r8, WPP_805f8623832e3be342dd4daabae23659_Traceguids
0x18000dbf0  call    WPP_SF_
0x18000dbf5  mov     r9, rbx
0x18000dbf8  lea     rdx, aSmsproviderbin; "SmsProviderBindingDeviceInterfacePath"
0x18000dbff  mov     r8, rdi
0x18000dc02  mov     rcx, rsi; unsigned __int16 *
0x18000dc05  mov     rbx, [rsp+28h+arg_0]
0x18000dc0a  mov     rsi, [rsp+28h+arg_8]
0x18000dc0f  add     rsp, 20h
0x18000dc13  pop     rdi
0x18000dc14  jmp     _GetBindingDeviceInterfacePath
```
