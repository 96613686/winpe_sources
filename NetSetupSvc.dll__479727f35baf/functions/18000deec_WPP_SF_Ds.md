# WPP_SF_Ds

- ea: `0x18000deec`
- end: `0x18000df5a`
- name: `WPP_SF_Ds`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000df42`
- `ntdll!EtwTraceMessage` at `0x18000df42`

## string_xrefs

- `0x18000df0a`: `m_ServiceHandle`

## pseudocode

```c
__int64 __fastcall WPP_SF_Ds(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids);
}

```

## disassembly

```asm
0x18000deec  mov     r11, rsp
0x18000deef  sub     rsp, 68h
0x18000def3  mov     rax, cs:__security_cookie
0x18000defa  xor     rax, rsp
0x18000defd  mov     [rsp+68h+var_10], rax
0x18000df02  mov     qword ptr [r11-28h], 0
0x18000df0a  lea     rax, aMServicehandle; "m_ServiceHandle"
0x18000df11  mov     qword ptr [r11-30h], 10h
0x18000df19  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000df20  mov     [r11-38h], rax
0x18000df24  lea     rax, [r11-18h]
0x18000df28  mov     [r11-18h], r9d
0x18000df2c  mov     r9d, 0Fh
0x18000df32  mov     qword ptr [r11-40h], 4
0x18000df3a  mov     [r11-48h], rax
0x18000df3e  lea     edx, [r9+1Ch]
0x18000df42  call    cs:__imp_EtwTraceMessage
0x18000df48  mov     rcx, [rsp+68h+var_10]
0x18000df4d  xor     rcx, rsp; StackCookie
0x18000df50  call    __security_check_cookie
0x18000df55  add     rsp, 68h
0x18000df59  retn
```
