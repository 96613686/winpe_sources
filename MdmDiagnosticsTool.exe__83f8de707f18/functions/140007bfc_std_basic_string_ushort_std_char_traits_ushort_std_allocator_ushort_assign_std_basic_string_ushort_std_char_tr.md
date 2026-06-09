# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x140007bfc`
- end: `0x140007cc0`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `196`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140002ff0`
- `0x140007cc8`
- `0x140008448`

## callees

- `0x1400016dc`
- `0x140007494`
- `0x140007bfc`
- `0x140007db4`
- `0x140008034`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, void **a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  void **v6; // rsi
  void **v7; // rbx
  unsigned __int64 v8; // rdi
  void *v9; // rax
  void *v10; // rcx
  _WORD *v11; // rax

  v4 = (unsigned __int64)a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    goto LABEL_20;
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] >= v8 + a3 )
    {
      if ( (unsigned __int64)a1[3] >= 8 )
        a1 = (void **)*a1;
      v7[2] = v9;
      *((_WORD *)a1 + (_QWORD)v9) = 0;
      std::wstring::erase(v7, 0);
      return v7;
    }
LABEL_20:
    std::_Xout_of_range("invalid string position");
  }
  if ( (unsigned __int8)std::wstring::_Grow(a1, v8) )
  {
    if ( (unsigned __int64)v6[3] >= 8 )
      v6 = (void **)*v6;
    if ( (unsigned __int64)v7[3] < 8 )
      v10 = v7;
    else
      v10 = *v7;
    std::char_traits<unsigned short>::copy(v10, (char *)v6 + 2 * a3, v8);
    if ( (unsigned __int64)v7[3] < 8 )
      v11 = v7;
    else
      v11 = *v7;
    v7[2] = (void *)v8;
    v11[v8] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140007bfc  push    rbx
0x140007bfe  push    rbp
0x140007bff  push    rsi
0x140007c00  push    rdi
0x140007c01  push    r14
0x140007c03  sub     rsp, 20h
0x140007c07  mov     rdi, [rdx+10h]
0x140007c0b  mov     rbp, r8
0x140007c0e  mov     rsi, rdx
0x140007c11  mov     rbx, rcx
0x140007c14  cmp     rdi, r8
0x140007c17  jb      loc_140007CB3
0x140007c1d  sub     rdi, r8
0x140007c20  cmp     r9, rdi
0x140007c23  cmovb   rdi, r9
0x140007c27  cmp     rcx, rdx
0x140007c2a  jnz     short loc_140007C58
0x140007c2c  lea     rax, [rdi+r8]
0x140007c30  cmp     [rcx+10h], rax
0x140007c34  jb      short loc_140007CB3
0x140007c36  cmp     qword ptr [rcx+18h], 8
0x140007c3b  jb      short loc_140007C40
0x140007c3d  mov     rcx, [rcx]
0x140007c40  xor     r14d, r14d
0x140007c43  mov     [rbx+10h], rax
0x140007c47  mov     [rcx+rax*2], r14w
0x140007c4c  xor     edx, edx
0x140007c4e  mov     rcx, rbx
0x140007c51  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x140007c56  jmp     short loc_140007CA4
0x140007c58  mov     rdx, rdi
0x140007c5b  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x140007c60  xor     r14d, r14d
0x140007c63  test    al, al
0x140007c65  jz      short loc_140007CA4
0x140007c67  cmp     qword ptr [rsi+18h], 8
0x140007c6c  jb      short loc_140007C71
0x140007c6e  mov     rsi, [rsi]
0x140007c71  cmp     qword ptr [rbx+18h], 8
0x140007c76  jb      short loc_140007C7D
0x140007c78  mov     rcx, [rbx]
0x140007c7b  jmp     short loc_140007C80
0x140007c7d  mov     rcx, rbx
0x140007c80  lea     rdx, [rsi+rbp*2]
0x140007c84  mov     r8, rdi
0x140007c87  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140007c8c  cmp     qword ptr [rbx+18h], 8
0x140007c91  jb      short loc_140007C98
0x140007c93  mov     rax, [rbx]
0x140007c96  jmp     short loc_140007C9B
0x140007c98  mov     rax, rbx
0x140007c9b  mov     [rbx+10h], rdi
0x140007c9f  mov     [rax+rdi*2], r14w
0x140007ca4  mov     rax, rbx
0x140007ca7  add     rsp, 20h
0x140007cab  pop     r14
0x140007cad  pop     rdi
0x140007cae  pop     rsi
0x140007caf  pop     rbp
0x140007cb0  pop     rbx
0x140007cb1  retn
0x140007cb3  lea     rcx, aInvalidStringP; "invalid string position"
0x140007cba  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
