# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x140004c00`
- end: `0x140004c2a`
- name: `?_Calculate_growth@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CA_K_K00@Z`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004754`
- `0x140004cdc`

## callees

- `0x140004c00`

## pseudocode

```c
unsigned __int64 __fastcall std::wstring::_Calculate_growth(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // r9
  unsigned __int64 result; // rax

  v3 = a1 | 7;
  if ( v3 > a3 )
    return a3;
  v4 = a2 >> 1;
  if ( a2 > a3 - (a2 >> 1) )
    return a3;
  result = v4 + a2;
  if ( v3 >= v4 + a2 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x140004c00  or      rcx, 7
0x140004c04  cmp     rcx, r8
0x140004c07  ja      short loc_140004C26
0x140004c09  mov     r9, rdx
0x140004c0c  mov     rax, r8
0x140004c0f  shr     r9, 1
0x140004c12  sub     rax, r9
0x140004c15  cmp     rdx, rax
0x140004c18  ja      short loc_140004C26
0x140004c1a  lea     rax, [r9+rdx]
0x140004c1e  cmp     rcx, rax
0x140004c21  cmovnb  rax, rcx
0x140004c25  retn
0x140004c26  mov     rax, r8
0x140004c29  retn
```
