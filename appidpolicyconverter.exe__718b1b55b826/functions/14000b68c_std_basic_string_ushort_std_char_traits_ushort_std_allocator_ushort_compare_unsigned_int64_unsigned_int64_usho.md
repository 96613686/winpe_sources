# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x14000b68c`
- end: `0x14000b6d8`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000918c`
- `0x1400091c0`

## callees

- `0x14000b68c`
- `0x14000b6e0`

## pseudocode

```c
__int64 __fastcall std::wstring::compare(_QWORD *a1, __int64 a2, unsigned __int64 a3, __int64 a4, unsigned __int64 a5)
{
  unsigned __int64 v5; // r10
  unsigned __int64 v6; // r8
  __int64 result; // rax
  unsigned __int64 v8; // r10
  unsigned __int64 v9; // r11

  v5 = a3;
  if ( a1[2] < a3 )
    v5 = a1[2];
  v6 = a5;
  if ( v5 < a5 )
    v6 = v5;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  result = std::char_traits<unsigned short>::compare(a1, a4, v6);
  if ( !(_DWORD)result )
  {
    if ( v8 >= v9 )
      return v8 != v9;
    else
      return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x14000b68c  sub     rsp, 28h
0x14000b690  cmp     [rcx+10h], r8
0x14000b694  mov     r10, r8
0x14000b697  mov     r11, [rsp+28h+arg_20]
0x14000b69c  cmovb   r10, [rcx+10h]
0x14000b6a1  mov     r8, r11
0x14000b6a4  cmp     r10, r11
0x14000b6a7  cmovb   r8, r10
0x14000b6ab  cmp     qword ptr [rcx+18h], 8
0x14000b6b0  jb      short loc_14000B6B5
0x14000b6b2  mov     rcx, [rcx]
0x14000b6b5  mov     rdx, r9
0x14000b6b8  call    ?compare@?$char_traits@G@std@@SAHPEBG0_K@Z; std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)
0x14000b6bd  test    eax, eax
0x14000b6bf  jnz     short loc_14000B6D3
0x14000b6c1  cmp     r10, r11
0x14000b6c4  jnb     short loc_14000B6CB
0x14000b6c6  or      eax, 0FFFFFFFFh
0x14000b6c9  jmp     short loc_14000B6D3
0x14000b6cb  xor     eax, eax
0x14000b6cd  cmp     r10, r11
0x14000b6d0  setnz   al
0x14000b6d3  add     rsp, 28h
0x14000b6d7  retn
```
