# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x1400078b0`
- end: `0x14000794e`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z`
- size: `158`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140002f94`
- `0x140004754`
- `0x140008130`

## callees

- `0x140007098`
- `0x140007144`
- `0x1400077e4`
- `0x1400078b0`
- `0x140007998`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  _QWORD *v6; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rcx

  if ( std::wstring::_Inside(a1, a2) )
  {
    if ( a1[3] < 8u )
      v6 = a1;
    else
      v6 = (_QWORD *)*a1;
    return std::wstring::assign(a1, a1, (__int64)(a2 - (_QWORD)v6) >> 1, a3);
  }
  else
  {
    if ( std::wstring::_Grow(a1, a3) )
    {
      if ( a1[3] < 8u )
        v8 = a1;
      else
        v8 = (_QWORD *)*a1;
      std::char_traits<unsigned short>::copy(v8, a2, a3);
      if ( a1[3] < 8u )
        v9 = a1;
      else
        v9 = (_QWORD *)*a1;
      a1[2] = a3;
      *((_WORD *)v9 + a3) = 0;
    }
    return a1;
  }
}

```

## disassembly

```asm
0x1400078b0  mov     [rsp+arg_0], rbx
0x1400078b5  mov     [rsp+arg_8], rsi
0x1400078ba  push    rdi
0x1400078bb  sub     rsp, 20h
0x1400078bf  mov     rdi, r8
0x1400078c2  mov     rsi, rdx
0x1400078c5  mov     rbx, rcx
0x1400078c8  call    ?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z; std::wstring::_Inside(ushort const *)
0x1400078cd  test    al, al
0x1400078cf  jz      short loc_1400078F9
0x1400078d1  cmp     qword ptr [rbx+18h], 8
0x1400078d6  jb      short loc_1400078DD
0x1400078d8  mov     rax, [rbx]
0x1400078db  jmp     short loc_1400078E0
0x1400078dd  mov     rax, rbx
0x1400078e0  sub     rsi, rax
0x1400078e3  mov     r9, rdi
0x1400078e6  sar     rsi, 1
0x1400078e9  mov     rdx, rbx
0x1400078ec  mov     r8, rsi
0x1400078ef  mov     rcx, rbx
0x1400078f2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400078f7  jmp     short loc_14000793E
0x1400078f9  mov     rdx, rdi
0x1400078fc  mov     rcx, rbx
0x1400078ff  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x140007904  test    al, al
0x140007906  jz      short loc_14000793B
0x140007908  cmp     qword ptr [rbx+18h], 8
0x14000790d  jb      short loc_140007914
0x14000790f  mov     rcx, [rbx]
0x140007912  jmp     short loc_140007917
0x140007914  mov     rcx, rbx
0x140007917  mov     r8, rdi
0x14000791a  mov     rdx, rsi
0x14000791d  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140007922  cmp     qword ptr [rbx+18h], 8
0x140007927  jb      short loc_14000792E
0x140007929  mov     rcx, [rbx]
0x14000792c  jmp     short loc_140007931
0x14000792e  mov     rcx, rbx
0x140007931  xor     eax, eax
0x140007933  mov     [rbx+10h], rdi
0x140007937  mov     [rcx+rdi*2], ax
0x14000793b  mov     rax, rbx
0x14000793e  mov     rbx, [rsp+28h+arg_0]
0x140007943  mov     rsi, [rsp+28h+arg_8]
0x140007948  add     rsp, 20h
0x14000794c  pop     rdi
0x14000794d  retn
```
