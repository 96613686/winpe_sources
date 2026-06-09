# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000f4dc`
- end: `0x18000f534`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001317c`

## callees

- `0x18000f4dc`
- `0x18000f714`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<std::wstring *,std::wstring *,std::allocator<std::wstring>,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  while ( a1 != a2 )
  {
    std::wstring::wstring(a3, a1);
    a3 += 40;
    a1 += 40;
  }
  return a3;
}

```

## disassembly

```asm
0x18000f4dc  mov     rax, rsp
0x18000f4df  mov     [rax+8], rbx
0x18000f4e3  mov     [rax+10h], rsi
0x18000f4e7  mov     [rax+20h], r9
0x18000f4eb  mov     [rax+18h], r8
0x18000f4ef  push    rdi
0x18000f4f0  sub     rsp, 20h
0x18000f4f4  mov     rbx, r8
0x18000f4f7  mov     rsi, rdx
0x18000f4fa  mov     rdi, rcx
0x18000f4fd  mov     [rsp+28h+arg_18], rbx
0x18000f502  cmp     rdi, rsi
0x18000f505  jz      short loc_18000F521
0x18000f507  mov     rdx, rdi
0x18000f50a  mov     rcx, rbx
0x18000f50d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000f512  add     rbx, 28h ; '('
0x18000f516  mov     [rsp+28h+arg_10], rbx
0x18000f51b  add     rdi, 28h ; '('
0x18000f51f  jmp     short loc_18000F502
0x18000f521  mov     rax, rbx
0x18000f524  mov     rbx, [rsp+28h+arg_0]
0x18000f529  mov     rsi, [rsp+28h+arg_8]
0x18000f52e  add     rsp, 20h
0x18000f532  pop     rdi
0x18000f533  retn
```
