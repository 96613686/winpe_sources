# wistd::__function::__func__lambda_a8db8c53c4d8f1132d3b58544171a766__void___cdecl(void)_::__move

- ea: `0x18000c880`
- end: `0x18000c893`
- name: `wistd::__function::__func__lambda_a8db8c53c4d8f1132d3b58544171a766__void___cdecl(void)_::__move`
- size: `19`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall wistd::__function::__func__lambda_a8db8c53c4d8f1132d3b58544171a766__void___cdecl_void__::__move(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  *a2 = &wistd::__function::__func<_lambda_a8db8c53c4d8f1132d3b58544171a766_,void (void)>::`vftable';
  result = *(_QWORD *)(a1 + 8);
  a2[1] = result;
  return result;
}

```

## disassembly

```asm
0x18000c880  lea     rax, ??_7?$__func@V_lambda_a8db8c53c4d8f1132d3b58544171a766_@@$$A6AXXZ@__function@wistd@@6B@; const wistd::__function::__func<_lambda_a8db8c53c4d8f1132d3b58544171a766_,void (void)>::`vftable'
0x18000c887  mov     [rdx], rax
0x18000c88a  mov     rax, [rcx+8]
0x18000c88e  mov     [rdx+8], rax
0x18000c892  retn
```
