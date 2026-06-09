# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180012af4`
- end: `0x180012b41`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAH_K0PEBG0@Z`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a890`
- `0x18000ac6c`
- `0x18000af60`
- `0x18000be18`

## callees

- `0x180009f58`
- `0x180012af4`

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
0x180012af4  sub     rsp, 28h
0x180012af8  cmp     [rcx+10h], r8
0x180012afc  mov     r10, r8
0x180012aff  mov     r11, [rsp+28h+arg_20]
0x180012b04  cmovb   r10, [rcx+10h]
0x180012b09  mov     r8, r11
0x180012b0c  cmp     r10, r11
0x180012b0f  cmovb   r8, r10
0x180012b13  cmp     qword ptr [rcx+18h], 8
0x180012b18  jb      short loc_180012B1D
0x180012b1a  mov     rcx, [rcx]
0x180012b1d  mov     rdx, r9
0x180012b20  call    ?compare@?$char_traits@G@std@@SAHPEBG0_K@Z; std::char_traits<ushort>::compare(ushort const *,ushort const *,unsigned __int64)
0x180012b25  test    eax, eax
0x180012b27  jnz     short loc_180012B3B
0x180012b29  cmp     r10, r11
0x180012b2c  jnb     short loc_180012B33
0x180012b2e  or      eax, 0FFFFFFFFh
0x180012b31  jmp     short loc_180012B3B
0x180012b33  xor     eax, eax
0x180012b35  cmp     r10, r11
0x180012b38  setnz   al
0x180012b3b  add     rsp, 28h
0x180012b3f  retn
```
