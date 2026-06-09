# std::_Uninit_copy<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000f3f4`
- end: `0x18000f44c`
- name: `??$_Uninit_copy@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fbb0`

## callees

- `0x18000f3f4`
- `0x18000f744`

## pseudocode

```c
__int64 __fastcall std::_Uninit_copy<std::wstring *,std::wstring *,std::allocator<std::wstring>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  __int64 result; // rax
  __int64 i; // rbx
  __int64 v8; // [rsp+40h] [rbp+18h]

  v8 = a3;
  v3 = a3;
  v5 = a1;
  try
  {
    while ( v5 != a2 )
    {
      std::wstring::wstring(v3, v5);
      v3 += 40;
      v8 = v3;
      v5 += 40;
    }
    result = v3;
  }
  catch ( ... )
  {
    for ( i = a3; i != v8; i += 40 )
      std::_Dest_val<std::allocator<std::wstring>,std::wstring>(a1, i);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000f3f4  mov     rax, rsp
0x18000f3f7  mov     [rax+8], rbx
0x18000f3fb  mov     [rax+10h], rsi
0x18000f3ff  mov     [rax+20h], r9
0x18000f403  mov     [rax+18h], r8
0x18000f407  push    rdi
0x18000f408  sub     rsp, 20h
0x18000f40c  mov     rbx, r8
0x18000f40f  mov     rsi, rdx
0x18000f412  mov     rdi, rcx
0x18000f415  mov     [rsp+28h+arg_18], rbx
0x18000f41a  cmp     rdi, rsi
0x18000f41d  jz      short loc_18000F439
0x18000f41f  mov     rdx, rdi
0x18000f422  mov     rcx, rbx
0x18000f425  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f42a  add     rbx, 28h ; '('
0x18000f42e  mov     [rsp+28h+arg_10], rbx
0x18000f433  add     rdi, 28h ; '('
0x18000f437  jmp     short loc_18000F41A
0x18000f439  mov     rax, rbx
0x18000f43c  mov     rbx, [rsp+28h+arg_0]
0x18000f441  mov     rsi, [rsp+28h+arg_8]
0x18000f446  add     rsp, 20h
0x18000f44a  pop     rdi
0x18000f44b  retn
```
