# std::_Func_impl_no_alloc__lambda_4bc228a33a7adc1015eb6bff6e85dd8e__long_DiagHubCommon::AutoEvent_const_&_void___::_Delete_this

- ea: `0x140009000`
- end: `0x140009017`
- name: `std::_Func_impl_no_alloc__lambda_4bc228a33a7adc1015eb6bff6e85dd8e__long_DiagHubCommon::AutoEvent_const_&_void___::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009000`
- `0x14001382c`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_4bc228a33a7adc1015eb6bff6e85dd8e__long_DiagHubCommon::AutoEvent_const___void___::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x140009000  sub     rsp, 28h
0x140009004  test    dl, dl
0x140009006  jz      short loc_140009012
0x140009008  mov     edx, 18h
0x14000900d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009012  add     rsp, 28h
0x140009016  retn
```
