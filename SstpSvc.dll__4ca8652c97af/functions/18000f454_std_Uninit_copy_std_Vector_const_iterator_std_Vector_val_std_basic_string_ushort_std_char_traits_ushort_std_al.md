# std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::_Vector_const_iterator<std::_Vector_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000f454`
- end: `0x18000f4ae`
- name: `??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@0PEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f8fc`

## callees

- `0x18000f454`
- `0x18000f744`

## pseudocode

```c
__int64 __fastcall std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::wstring *,std::allocator<std::wstring>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  __int64 v7; // rcx
  __int64 i; // rbx
  __int64 v9; // [rsp+40h] [rbp+18h]

  v3 = a3;
  while ( a1 != a2 )
  {
    try
    {
      std::wstring::wstring(v3, a1);
      v3 += 40;
      v9 = v3;
      a1 += 40;
    }
    catch ( ... )
    {
      for ( i = a3; i != v9; i += 40 )
        std::_Dest_val<std::allocator<std::wstring>,std::wstring>(v7, i);
      throw;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000f454  mov     rax, rsp
0x18000f457  mov     [rax+8], rbx
0x18000f45b  mov     [rax+10h], rsi
0x18000f45f  mov     [rax+20h], r9
0x18000f463  mov     [rax+18h], r8
0x18000f467  push    rdi
0x18000f468  sub     rsp, 20h
0x18000f46c  mov     rsi, r8
0x18000f46f  mov     rdi, rdx
0x18000f472  mov     rbx, rcx
0x18000f475  mov     [rsp+28h+arg_18], r8
0x18000f47a  cmp     rbx, rdi
0x18000f47d  jnz     short loc_18000F492
0x18000f47f  mov     rax, rsi
0x18000f482  mov     rbx, [rsp+28h+arg_0]
0x18000f487  mov     rsi, [rsp+28h+arg_8]
0x18000f48c  add     rsp, 20h
0x18000f490  pop     rdi
0x18000f491  retn
0x18000f492  mov     rdx, rbx
0x18000f495  mov     rcx, rsi
0x18000f498  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f49d  add     rsi, 28h ; '('
0x18000f4a1  mov     [rsp+28h+arg_10], rsi
0x18000f4a6  add     rbx, 28h ; '('
0x18000f4aa  jmp     short loc_18000F47A
```
