# std::_Destroy_range<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x18000db18`
- end: `0x18000db49`
- name: `??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dd98`
- `0x18000de78`
- `0x18000df58`
- `0x18000dfd4`
- `0x18000f144`

## callees

- `0x18000db18`
- `0x18000f200`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<std::wstring>>(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = std::wstring::_Tidy_deallocate(v3);
      v3 += 32;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x18000db18  cmp     rcx, rdx
0x18000db1b  jz      short locret_18000DB48
0x18000db1d  mov     [rsp+arg_0], rbx
0x18000db22  push    rdi
0x18000db23  sub     rsp, 20h
0x18000db27  mov     rdi, rdx
0x18000db2a  mov     rbx, rcx
0x18000db2d  mov     rcx, rbx
0x18000db30  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000db35  add     rbx, 20h ; ' '
0x18000db39  cmp     rbx, rdi
0x18000db3c  jnz     short loc_18000DB2D
0x18000db3e  mov     rbx, [rsp+28h+arg_0]
0x18000db43  add     rsp, 20h
0x18000db47  pop     rdi
0x18000db48  retn
```
