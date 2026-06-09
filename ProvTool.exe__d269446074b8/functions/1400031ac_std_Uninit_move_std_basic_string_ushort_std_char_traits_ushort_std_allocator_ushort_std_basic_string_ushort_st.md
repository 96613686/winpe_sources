# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1400031ac`
- end: `0x140003207`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008994`

## callees

- `0x1400031ac`
- `0x1400033a8`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<std::wstring *,std::wstring *,std::allocator<std::wstring>,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 32 )
  {
    std::wstring::wstring(a3, i);
    a3 += 32;
  }
  return a3;
}

```

## disassembly

```asm
0x1400031ac  mov     rax, rsp
0x1400031af  mov     [rax+8], rbx
0x1400031b3  mov     [rax+10h], rsi
0x1400031b7  mov     [rax+20h], r9
0x1400031bb  mov     [rax+18h], r8
0x1400031bf  push    rdi
0x1400031c0  sub     rsp, 20h
0x1400031c4  mov     rbx, r8
0x1400031c7  mov     rsi, rdx
0x1400031ca  mov     rdi, rcx
0x1400031cd  mov     [rsp+28h+arg_18], rbx
0x1400031d2  cmp     rcx, rdx
0x1400031d5  jz      short loc_1400031F4
0x1400031d7  mov     rdx, rdi
0x1400031da  mov     rcx, rbx
0x1400031dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1400031e2  add     rbx, 20h ; ' '
0x1400031e6  mov     [rsp+28h+arg_10], rbx
0x1400031eb  add     rdi, 20h ; ' '
0x1400031ef  cmp     rdi, rsi
0x1400031f2  jnz     short loc_1400031D7
0x1400031f4  mov     rax, rbx
0x1400031f7  mov     rbx, [rsp+28h+arg_0]
0x1400031fc  mov     rsi, [rsp+28h+arg_8]
0x140003201  add     rsp, 20h
0x140003205  pop     rdi
0x140003206  retn
```
