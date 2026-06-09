# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::copy(ushort * const,unsigned __int64,unsigned __int64)

- ea: `0x14000f5c8`
- end: `0x14000f600`
- name: `?copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEAG_K_K@Z`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000f500`

## callees

- `0x14000f0b0`
- `0x14000f27c`
- `0x14000f5c8`

## pseudocode

```c
unsigned __int64 __fastcall std::wstring::copy(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // r9

  v3 = a3;
  if ( *(_QWORD *)(a1 + 16) < a3 )
    v3 = *(_QWORD *)(a1 + 16);
  if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(a1) )
    v4 = (_QWORD *)*v4;
  std::_Char_traits<unsigned short,unsigned short>::copy(v5, v4, v3);
  return v3;
}

```

## disassembly

```asm
0x14000f5c8  push    rbx
0x14000f5ca  sub     rsp, 20h
0x14000f5ce  cmp     [rcx+10h], r8
0x14000f5d2  mov     rbx, r8
0x14000f5d5  mov     r9, rdx
0x14000f5d8  cmovb   rbx, [rcx+10h]
0x14000f5dd  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x14000f5e2  test    al, al
0x14000f5e4  jz      short loc_14000F5E9
0x14000f5e6  mov     rcx, [rcx]
0x14000f5e9  mov     rdx, rcx
0x14000f5ec  mov     r8, rbx
0x14000f5ef  mov     rcx, r9
0x14000f5f2  call    ?copy@?$_Char_traits@GG@std@@SAPEAGQEAGQEBG_K@Z; std::_Char_traits<ushort,ushort>::copy(ushort * const,ushort const * const,unsigned __int64)
0x14000f5f7  mov     rax, rbx
0x14000f5fa  add     rsp, 20h
0x14000f5fe  pop     rbx
0x14000f5ff  retn
```
