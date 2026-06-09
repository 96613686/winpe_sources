# _Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor$9

- ea: `0x1800183da`
- end: `0x1800183e6`
- name: `_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor$9`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fed0`

## pseudocode

```c
__int64 __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_Init_::_1_::dtor_9(
        __int64 a1,
        __int64 a2)
{
  return `std::_Global_new<std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>,_lambda_052e919cc0e5399df76dff3972c0cac1_ const &>'::`2'::_Guard_type::~_Guard_type(a2 + 32);
}

```

## disassembly

```asm
0x1800183da  lea     rcx, [rdx+20h]
0x1800183e1  jmp     ??1_Guard_type@?1???$_Global_new@V?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@AEBV_lambda_052e919cc0e5399df76dff3972c0cac1_@@@std@@YAPEAV?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@1@AEBV_lambda_052e919cc0e5399df76dff3972c0cac1_@@@Z@QEAA@XZ; `std::_Global_new<std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>,_lambda_052e919cc0e5399df76dff3972c0cac1_ const &>(_lambda_052e919cc0e5399df76dff3972c0cac1_ const &)'::`2'::_Guard_type::~_Guard_type(void)
```
