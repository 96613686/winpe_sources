# std::_String_base::_Xlen(void)

- ea: `0x1800016a4`
- end: `0x1800016f9`
- name: `?_Xlen@_String_base@std@@SAXXZ`
- size: `85`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180001760`
- `0x180001850`
- `0x18000379c`
- `0x1800038a8`
- `0x1800039e8`

## callees

- `0x1800010a8`
- `0x18000115c`
- `0x18000227c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn std::_String_base::_Xlen(void)
{
  _BYTE v0[40]; // [rsp+28h] [rbp-80h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-58h] BYREF

  std::string::string(v0, "string too long");
  std::length_error::length_error(pExceptionObject, v0);
  throw (std::length_error *)pExceptionObject;
}

```

## disassembly

```asm
0x1800016a4  sub     rsp, 0A8h
0x1800016ab  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x1800016b4  mov     rax, cs:__security_cookie
0x1800016bb  xor     rax, rsp
0x1800016be  mov     [rsp+0A8h+var_18], rax
0x1800016c6  lea     rdx, aStringTooLong; "string too long"
0x1800016cd  lea     rcx, [rsp+0A8h+var_80]
0x1800016d2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1800016d7  nop
0x1800016d8  lea     rdx, [rsp+0A8h+var_80]
0x1800016dd  lea     rcx, [rsp+0A8h+pExceptionObject]
0x1800016e2  call    ??0length_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::length_error::length_error(std::string const &)
0x1800016e7  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1800016ee  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800016f3  call    _CxxThrowException_0
```
