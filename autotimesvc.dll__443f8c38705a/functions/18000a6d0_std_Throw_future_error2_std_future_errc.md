# std::_Throw_future_error2(std::future_errc)

- ea: `0x18000a6d0`
- end: `0x18000a710`
- name: `?_Throw_future_error2@std@@YAXW4future_errc@1@@Z`
- size: `64`
- prototype: `void __fastcall __noreturn(int, const char *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007534`
- `0x1800081ac`
- `0x18000a3c0`
- `0x18000a53c`
- `0x18000a5f0`

## callees

- `0x180003668`
- `0x180005364`

## pseudocode

```c
void __fastcall __noreturn std::_Throw_future_error2(int a1, const char *a2)
{
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-38h] BYREF
  int v4; // [rsp+38h] [rbp-20h]
  void ***v5; // [rsp+40h] [rbp-18h]

  std::logic_error::logic_error((std::logic_error *)pExceptionObject, a2);
  v4 = a1;
  pExceptionObject[0] = &std::future_error::`vftable';
  v5 = &`std::_Immortalize_memcpy_image<std::_Future_error_category2>'::`2'::_Static;
  throw (std::future_error *)pExceptionObject;
}

```

## disassembly

```asm
0x18000a6d0  push    rbx
0x18000a6d2  sub     rsp, 50h
0x18000a6d6  mov     ebx, ecx
0x18000a6d8  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000a6dd  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x18000a6e2  lea     rax, ??_7future_error@std@@6B@; const std::future_error::`vftable'
0x18000a6e9  mov     [rsp+58h+var_20], ebx
0x18000a6ed  mov     [rsp+58h+pExceptionObject], rax
0x18000a6f2  lea     rdx, _TI3?AVfuture_error@std@@; pThrowInfo
0x18000a6f9  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Future_error_category2@std@@@std@@YAAEBV_Future_error_category2@1@XZ@4U?$_Constexpr_immortalize_impl@V_Future_error_category2@std@@@1@A; std::_Constexpr_immortalize_impl<std::_Future_error_category2> `std::_Immortalize_memcpy_image<std::_Future_error_category2>(void)'::`2'::_Static
0x18000a700  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000a705  mov     [rsp+58h+var_18], rax
0x18000a70a  call    _CxxThrowException_0
```
