# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>::~pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>>(void)

- ea: `0x14000d258`
- end: `0x14000d281`
- name: `??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@V12@@std@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000db74`
- `0x14000f548`
- `0x14000fe40`
- `0x1400135b5`
- `0x1400135c7`

## callees

- `0x14000fa04`

## pseudocode

```c
__int64 __fastcall std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(__int64 a1)
{
  std::wstring::_Tidy(a1 + 40, 1, 0);
  return std::wstring::_Tidy(a1, 1, 0);
}

```

## disassembly

```asm
0x14000d258  push    rbx
0x14000d25a  sub     rsp, 20h
0x14000d25e  mov     rbx, rcx
0x14000d261  xor     r8d, r8d
0x14000d264  add     rcx, 28h ; '('
0x14000d268  mov     dl, 1
0x14000d26a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000d26f  xor     r8d, r8d
0x14000d272  mov     dl, 1
0x14000d274  mov     rcx, rbx
0x14000d277  add     rsp, 20h
0x14000d27b  pop     rbx
0x14000d27c  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
