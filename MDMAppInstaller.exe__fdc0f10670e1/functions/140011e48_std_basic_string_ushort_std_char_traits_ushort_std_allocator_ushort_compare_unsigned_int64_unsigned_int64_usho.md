# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x140011e48`
- end: `0x140011e94`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64, __int64, unsigned __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008318`
- `0x140008600`
- `0x140008790`
- `0x1400097ac`
- `0x140011844`
- `0x14001273c`
- `0x1400127f4`
- `0x140012a1c`
- `0x140018668`

## callees

- `0x140011e48`
- `0x140011e9c`

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
0x140011e48  sub     rsp, 28h
0x140011e4c  cmp     [rcx+10h], r8
0x140011e50  mov     r10, r8
0x140011e53  mov     r11, [rsp+28h+arg_20]
0x140011e58  cmovb   r10, [rcx+10h]
0x140011e5d  mov     r8, r11
0x140011e60  cmp     r10, r11
0x140011e63  cmovb   r8, r10
0x140011e67  cmp     qword ptr [rcx+18h], 8
0x140011e6c  jb      short loc_140011E71
0x140011e6e  mov     rcx, [rcx]
0x140011e71  mov     rdx, r9
0x140011e74  call    ?compare@?$char_traits@G@std@@SAHPEBG0_K@Z; std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)
0x140011e79  test    eax, eax
0x140011e7b  jnz     short loc_140011E8F
0x140011e7d  cmp     r10, r11
0x140011e80  jnb     short loc_140011E87
0x140011e82  or      eax, 0FFFFFFFFh
0x140011e85  jmp     short loc_140011E8F
0x140011e87  xor     eax, eax
0x140011e89  cmp     r10, r11
0x140011e8c  setnz   al
0x140011e8f  add     rsp, 28h
0x140011e93  retn
```
