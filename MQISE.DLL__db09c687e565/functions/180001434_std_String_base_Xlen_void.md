# std::_String_base::_Xlen(void)

- ea: `0x180001434`
- end: `0x180001489`
- name: `?_Xlen@_String_base@std@@SAXXZ`
- size: `85`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d0c`
- `0x18000bf0c`
- `0x18000c000`
- `0x18000c0e8`

## callees

- `0x180001c0c`
- `0x180002cd0`
- `0x180003284`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn std::_String_base::_Xlen(void)
{
  _BYTE v0[40]; // [rsp+28h] [rbp-80h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-58h] BYREF

  std::string::string((__int64)v0, (__int64)"string too long");
  std::length_error::length_error(pExceptionObject, v0);
  throw (std::length_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180001434  sub     rsp, 0A8h
0x18000143b  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x180001444  mov     rax, cs:__security_cookie
0x18000144b  xor     rax, rsp
0x18000144e  mov     [rsp+0A8h+var_18], rax
0x180001456  lea     rdx, aStringTooLong; "string too long"
0x18000145d  lea     rcx, [rsp+0A8h+var_80]
0x180001462  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x180001467  nop
0x180001468  lea     rdx, [rsp+0A8h+var_80]
0x18000146d  lea     rcx, [rsp+0A8h+pExceptionObject]
0x180001472  call    ??0length_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::length_error::length_error(std::string const &)
0x180001477  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x18000147e  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180001483  call    _CxxThrowException_0
```
