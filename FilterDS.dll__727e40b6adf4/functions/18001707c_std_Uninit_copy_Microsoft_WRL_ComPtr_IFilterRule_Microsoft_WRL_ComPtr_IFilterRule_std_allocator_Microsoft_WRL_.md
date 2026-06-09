# std::_Uninit_copy<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>(Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18001707c`
- end: `0x1800170e4`
- name: `??$_Uninit_copy@PEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@YAPEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@00AEAU?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `104`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001734c`

## callees

- `0x18001707c`
- `0x180024010`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_copy<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v3; // rbx
  _QWORD *i; // rdi
  _QWORD *result; // rax
  _QWORD *j; // rbx
  _QWORD *v8; // [rsp+40h] [rbp+18h]

  v8 = a3;
  try
  {
    v3 = a3;
    for ( i = a1; i != a2; ++i )
    {
      a1 = (_QWORD *)*i;
      *v3 = *i;
      if ( a1 )
        (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
      v8 = ++v3;
    }
    result = v3;
  }
  catch ( ... )
  {
    for ( j = a3; j != v8; ++j )
      std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::destroy<Microsoft::WRL::ComPtr<IFilterRule>>(
        a1,
        j);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18001707c  mov     rax, rsp
0x18001707f  mov     [rax+8], rbx
0x180017083  mov     [rax+10h], rsi
0x180017087  mov     [rax+20h], r9
0x18001708b  mov     [rax+18h], r8
0x18001708f  push    rdi
0x180017090  sub     rsp, 20h
0x180017094  mov     rbx, r8
0x180017097  mov     rsi, rdx
0x18001709a  mov     rdi, rcx
0x18001709d  mov     [rsp+28h+arg_18], rbx
0x1800170a2  cmp     rcx, rdx
0x1800170a5  jz      short loc_1800170D1
0x1800170a7  mov     rcx, [rdi]
0x1800170aa  mov     [rbx], rcx
0x1800170ad  test    rcx, rcx
0x1800170b0  jz      short loc_1800170BF
0x1800170b2  mov     rax, [rcx]
0x1800170b5  mov     rax, [rax+8]
0x1800170b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170be  nop
0x1800170bf  add     rbx, 8
0x1800170c3  mov     [rsp+28h+arg_10], rbx
0x1800170c8  add     rdi, 8
0x1800170cc  cmp     rdi, rsi
0x1800170cf  jnz     short loc_1800170A7
0x1800170d1  mov     rax, rbx
0x1800170d4  mov     rbx, [rsp+28h+arg_0]
0x1800170d9  mov     rsi, [rsp+28h+arg_8]
0x1800170de  add     rsp, 20h
0x1800170e2  pop     rdi
0x1800170e3  retn
```
