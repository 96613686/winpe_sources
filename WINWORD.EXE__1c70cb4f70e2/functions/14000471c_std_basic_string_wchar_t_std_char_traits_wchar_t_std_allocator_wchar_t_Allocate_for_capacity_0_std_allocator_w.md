# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)

- ea: `0x14000471c`
- end: `0x140004754`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004754`
- `0x140004cdc`

## callees

- `0x140003430`
- `0x1400041c4`
- `0x14000471c`

## pseudocode

```c
void *__fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rcx
  void *result; // rax

  v2 = *a2 + 1;
  *a2 = v2;
  if ( v2 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Throw_bad_array_new_length();
  result = std::_Allocate<16,std::_Default_allocate_traits>(2 * v2);
  --*a2;
  return result;
}

```

## disassembly

```asm
0x14000471c  push    rbx
0x14000471e  sub     rsp, 20h
0x140004722  mov     rcx, [rdx]
0x140004725  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000472f  inc     rcx
0x140004732  mov     rbx, rdx
0x140004735  mov     [rdx], rcx
0x140004738  cmp     rcx, rax
0x14000473b  jbe     short loc_140004743
0x14000473d  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x140004743  add     rcx, rcx
0x140004746  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14000474b  dec     qword ptr [rbx]
0x14000474e  add     rsp, 20h
0x140004752  pop     rbx
0x140004753  retn
```
