# _com_raise_error(long,IErrorInfo *)

- ea: `0x1400140fc`
- end: `0x14001412f`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `51`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014010`

## callees

- `0x140003adc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2)
{
  void **v2; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+28h] [rbp-20h]
  struct IErrorInfo *v4; // [rsp+30h] [rbp-18h]
  __int64 v5; // [rsp+38h] [rbp-10h]

  v2 = &_com_error::`vftable';
  v3 = a1;
  v4 = a2;
  v5 = 0;
  throw (_com_error *)&v2;
}

```

## disassembly

```asm
0x1400140fc  mov     r11, rsp
0x1400140ff  sub     rsp, 48h
0x140014103  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x14001410a  mov     [r11-28h], rax
0x14001410e  mov     [rsp+48h+var_20], ecx
0x140014112  mov     [r11-18h], rdx
0x140014116  mov     qword ptr [r11-10h], 0
0x14001411e  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x140014125  lea     rcx, [r11-28h]; pExceptionObject
0x140014129  call    _CxxThrowException_0
```
