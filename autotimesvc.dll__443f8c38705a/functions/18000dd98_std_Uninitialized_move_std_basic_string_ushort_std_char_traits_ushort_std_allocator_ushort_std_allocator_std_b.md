# std::_Uninitialized_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x18000dd98`
- end: `0x18000ddd5`
- name: `??$_Uninitialized_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z`
- size: `61`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000db50`
- `0x18000dc74`

## callees

- `0x18000db18`
- `0x18000dd98`
- `0x18000dddc`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<std::wstring *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 i; // r9
  __int64 v6; // r8

  v4 = a1;
  for ( i = a2; v4 != i; v4 = v6 + 32 )
  {
    std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring>(a1, a3, v4, i);
    a3 += 32;
  }
  std::_Destroy_range<std::allocator<std::wstring>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18000dd98  push    rbx
0x18000dd9a  sub     rsp, 20h
0x18000dd9e  mov     rbx, r8
0x18000dda1  mov     r8, rcx
0x18000dda4  mov     r9, rdx
0x18000dda7  cmp     rcx, rdx
0x18000ddaa  jz      short loc_18000DDC1
0x18000ddac  mov     rdx, rbx
0x18000ddaf  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::wstring>(std::allocator<std::wstring> &,std::wstring * const,std::wstring &&)
0x18000ddb4  add     rbx, 20h ; ' '
0x18000ddb8  add     r8, 20h ; ' '
0x18000ddbc  cmp     r8, r9
0x18000ddbf  jnz     short loc_18000DDAC
0x18000ddc1  mov     rdx, rbx
0x18000ddc4  mov     rcx, rbx
0x18000ddc7  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18000ddcc  mov     rax, rbx
0x18000ddcf  add     rsp, 20h
0x18000ddd3  pop     rbx
0x18000ddd4  retn
```
