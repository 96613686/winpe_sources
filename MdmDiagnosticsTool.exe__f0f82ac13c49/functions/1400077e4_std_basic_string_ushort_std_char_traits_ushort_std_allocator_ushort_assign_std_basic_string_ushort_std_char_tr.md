# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x1400077e4`
- end: `0x1400078a7`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `195`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140002f5c`
- `0x1400078b0`
- `0x140007f64`

## callees

- `0x1400016ac`
- `0x140007098`
- `0x1400077e4`
- `0x140007998`
- `0x140007c00`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  _QWORD *v6; // rsi
  _QWORD *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  _QWORD *v10; // rcx
  _QWORD *v11; // rax

  v4 = a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    goto LABEL_20;
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = v8 + a3;
    if ( a1[2] >= v8 + a3 )
    {
      if ( a1[3] >= 8u )
        a1 = (_QWORD *)*a1;
      v7[2] = v9;
      *((_WORD *)a1 + v9) = 0;
      std::wstring::erase(v7, 0);
      return v7;
    }
LABEL_20:
    std::_Xout_of_range("invalid string position");
  }
  if ( std::wstring::_Grow(a1, v8) )
  {
    if ( v6[3] >= 8u )
      v6 = (_QWORD *)*v6;
    if ( v7[3] < 8u )
      v10 = v7;
    else
      v10 = (_QWORD *)*v7;
    std::char_traits<unsigned short>::copy(v10, (char *)v6 + 2 * a3, v8);
    if ( v7[3] < 8u )
      v11 = v7;
    else
      v11 = (_QWORD *)*v7;
    v7[2] = v8;
    *((_WORD *)v11 + v8) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1400077e4  push    rbx
0x1400077e6  push    rbp
0x1400077e7  push    rsi
0x1400077e8  push    rdi
0x1400077e9  push    r14
0x1400077eb  sub     rsp, 20h
0x1400077ef  mov     rdi, [rdx+10h]
0x1400077f3  mov     rbp, r8
0x1400077f6  mov     rsi, rdx
0x1400077f9  mov     rbx, rcx
0x1400077fc  cmp     rdi, r8
0x1400077ff  jb      loc_14000789A
0x140007805  sub     rdi, r8
0x140007808  cmp     r9, rdi
0x14000780b  cmovb   rdi, r9
0x14000780f  cmp     rcx, rdx
0x140007812  jnz     short loc_140007840
0x140007814  lea     rax, [rdi+r8]
0x140007818  cmp     [rcx+10h], rax
0x14000781c  jb      short loc_14000789A
0x14000781e  cmp     qword ptr [rcx+18h], 8
0x140007823  jb      short loc_140007828
0x140007825  mov     rcx, [rcx]
0x140007828  xor     r14d, r14d
0x14000782b  mov     [rbx+10h], rax
0x14000782f  mov     [rcx+rax*2], r14w
0x140007834  xor     edx, edx
0x140007836  mov     rcx, rbx
0x140007839  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x14000783e  jmp     short loc_14000788C
0x140007840  mov     rdx, rdi
0x140007843  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x140007848  xor     r14d, r14d
0x14000784b  test    al, al
0x14000784d  jz      short loc_14000788C
0x14000784f  cmp     qword ptr [rsi+18h], 8
0x140007854  jb      short loc_140007859
0x140007856  mov     rsi, [rsi]
0x140007859  cmp     qword ptr [rbx+18h], 8
0x14000785e  jb      short loc_140007865
0x140007860  mov     rcx, [rbx]
0x140007863  jmp     short loc_140007868
0x140007865  mov     rcx, rbx
0x140007868  lea     rdx, [rsi+rbp*2]
0x14000786c  mov     r8, rdi
0x14000786f  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140007874  cmp     qword ptr [rbx+18h], 8
0x140007879  jb      short loc_140007880
0x14000787b  mov     rax, [rbx]
0x14000787e  jmp     short loc_140007883
0x140007880  mov     rax, rbx
0x140007883  mov     [rbx+10h], rdi
0x140007887  mov     [rax+rdi*2], r14w
0x14000788c  mov     rax, rbx
0x14000788f  add     rsp, 20h
0x140007893  pop     r14
0x140007895  pop     rdi
0x140007896  pop     rsi
0x140007897  pop     rbp
0x140007898  pop     rbx
0x140007899  retn
0x14000789a  lea     rcx, aInvalidStringP; "invalid string position"
0x1400078a1  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
