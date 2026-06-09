# Marshal::Details::ParseJsonName<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,>(std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,Marshal::UnmarshalContext const &)

- ea: `0x140005124`
- end: `0x14000514b`
- name: `??$ParseJsonName@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@Details@Marshal@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBVUnmarshalContext@1@@Z`
- size: `39`
- prototype: `char __fastcall(__int64, void **, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400048f0`

## callees

- `0x140005124`
- `0x140006790`

## pseudocode

```c
char __fastcall Marshal::Details::ParseJsonName<std::wstring,>(__int64 a1, void **a2, __int64 a3)
{
  char result; // al
  unsigned int v4; // [rsp+20h] [rbp-18h] BYREF
  __int64 v5; // [rsp+28h] [rbp-10h]

  v5 = a3;
  try
  {
    std::wstring::_Assign<unsigned short>(a2, *(const void **)a1, *(_QWORD *)(a1 + 8));
    result = 1;
  }
  catch ( Marshal::UnmarshalError v4 )
  {
    Marshal::UnmarshalContext::ReportError(v5, v4);
    return 0;
  }
  std::wstring::_Assign<unsigned short>(a2, *(const void **)a1, *(_QWORD *)(a1 + 8));
}

```

## disassembly

```asm
0x140005124  sub     rsp, 38h
0x140005128  mov     rax, rdx
0x14000512b  mov     [rsp+38h+var_10], r8
0x140005130  mov     r8, [rcx+8]
0x140005134  mov     rdx, [rcx]
0x140005137  mov     rcx, rax
0x14000513a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14000513f  mov     al, 1
0x140005141  jmp     short loc_140005145
0x140005143  xor     al, al
0x140005145  add     rsp, 38h
0x140005149  retn
```
