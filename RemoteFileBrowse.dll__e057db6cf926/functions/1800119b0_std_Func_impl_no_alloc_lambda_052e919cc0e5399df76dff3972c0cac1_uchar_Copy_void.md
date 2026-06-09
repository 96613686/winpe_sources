# std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::_Copy(void *)

- ea: `0x1800119b0`
- end: `0x180011a1d`
- name: `?_Copy@?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@EEBAPEAV?$_Func_base@E$$V@2@PEAX@Z`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000208c`
- `0x1800119b0`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::_Copy(
        __int64 a1)
{
  _QWORD *v2; // rbx
  __int64 (__fastcall ***v3)(_QWORD, __int64); // rcx

  v2 = operator new(0x48u);
  *v2 = &std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::`vftable';
  v2[8] = 0;
  v3 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a1 + 64);
  if ( v3 )
    v2[8] = (**v3)(v3, (__int64)(v2 + 1));
  return v2;
}

```

## disassembly

```asm
0x1800119b0  mov     [rsp+arg_8], rbx
0x1800119b5  mov     [rsp+arg_18], rsi
0x1800119ba  push    rdi
0x1800119bb  sub     rsp, 20h
0x1800119bf  mov     rdi, rcx
0x1800119c2  mov     ecx, 48h ; 'H'; Size
0x1800119c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800119cc  mov     rbx, rax
0x1800119cf  mov     [rsp+28h+arg_0], rax
0x1800119d4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x1800119db  mov     [rbx], rax
0x1800119de  lea     rsi, [rbx+8]
0x1800119e2  mov     [rsp+28h+arg_10], rsi
0x1800119e7  mov     qword ptr [rsi+38h], 0
0x1800119ef  mov     rcx, [rdi+40h]
0x1800119f3  test    rcx, rcx
0x1800119f6  jz      short loc_180011A0A
0x1800119f8  mov     rax, [rcx]
0x1800119fb  mov     rdx, rsi
0x1800119fe  mov     rax, [rax]
0x180011a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a06  mov     [rsi+38h], rax
0x180011a0a  mov     rax, rbx
0x180011a0d  mov     rbx, [rsp+28h+arg_8]
0x180011a12  mov     rsi, [rsp+28h+arg_18]
0x180011a17  add     rsp, 20h
0x180011a1b  pop     rdi
0x180011a1c  retn
```
