# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x1800060cc`
- end: `0x1800061e9`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `285`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800061f0`
- `0x180006840`

## callees

- `0x180005b50`
- `0x180005ce8`
- `0x1800060cc`
- `0x1800062dc`
- `0x180009ef2`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  _QWORD *v6; // r14
  _QWORD *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r14
  _WORD *v11; // rax
  _WORD *v12; // rcx
  unsigned __int64 v13; // r14
  _WORD *v14; // rax
  void *v15; // rcx
  _WORD *v16; // rax

  v4 = a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
  {
    std::wstring::_Xran();
    __debugbreak();
  }
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = v8 + a3;
    if ( a1[2] < v8 + a3 )
    {
      std::wstring::_Xran();
      __debugbreak();
    }
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    v7[2] = v9;
    *((_WORD *)a1 + v9) = 0;
    v10 = v7[2];
    if ( v10 > a3 )
    {
      if ( a3 )
      {
        if ( v7[3] < 8u )
          v12 = v7;
        else
          v12 = (_WORD *)*v7;
        v13 = v10 - a3;
        if ( v13 )
          memmove_0(v12, &v12[a3], 2 * v13);
        if ( v7[3] < 8u )
          v14 = v7;
        else
          v14 = (_WORD *)*v7;
        v7[2] = v13;
        v14[v13] = 0;
      }
    }
    else
    {
      if ( v7[3] < 8u )
        v11 = v7;
      else
        v11 = (_WORD *)*v7;
      v7[2] = 0;
      *v11 = 0;
    }
  }
  else if ( (unsigned __int8)std::wstring::_Grow(a1, v8) )
  {
    if ( v6[3] >= 8u )
      v6 = (_QWORD *)*v6;
    if ( v7[3] < 8u )
      v15 = v7;
    else
      v15 = (void *)*v7;
    std::char_traits<unsigned short>::copy(v15, (char *)v6 + 2 * a3, v8);
    if ( v7[3] < 8u )
      v16 = v7;
    else
      v16 = (_WORD *)*v7;
    v7[2] = v8;
    v16[v8] = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800060cc  push    rbx
0x1800060ce  push    rbp
0x1800060cf  push    rsi
0x1800060d0  push    rdi
0x1800060d1  push    r14
0x1800060d3  sub     rsp, 20h
0x1800060d7  mov     rdi, [rdx+10h]
0x1800060db  mov     rbp, r8
0x1800060de  mov     r14, rdx
0x1800060e1  mov     rbx, rcx
0x1800060e4  cmp     rdi, r8
0x1800060e7  jnb     short loc_1800060EF
0x1800060e9  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800060ee  int     3; Trap to Debugger
0x1800060ef  sub     rdi, rbp
0x1800060f2  cmp     r9, rdi
0x1800060f5  cmovb   rdi, r9
0x1800060f9  cmp     rbx, r14
0x1800060fc  jnz     loc_180006190
0x180006102  lea     rax, [rdi+r8]
0x180006106  cmp     [rcx+10h], rax
0x18000610a  jnb     short loc_180006112
0x18000610c  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180006111  int     3; Trap to Debugger
0x180006112  cmp     qword ptr [rcx+18h], 8
0x180006117  jb      short loc_18000611C
0x180006119  mov     rcx, [rcx]
0x18000611c  xor     esi, esi
0x18000611e  mov     [rbx+10h], rax
0x180006122  mov     [rcx+rax*2], si
0x180006126  mov     r14, [rbx+10h]
0x18000612a  cmp     r14, rbp
0x18000612d  ja      short loc_18000614A
0x18000612f  cmp     qword ptr [rbx+18h], 8
0x180006134  jb      short loc_18000613B
0x180006136  mov     rax, [rbx]
0x180006139  jmp     short loc_18000613E
0x18000613b  mov     rax, rbx
0x18000613e  mov     [rbx+10h], rsi
0x180006142  mov     [rax], si
0x180006145  jmp     loc_1800061DA
0x18000614a  test    rbp, rbp
0x18000614d  jz      loc_1800061DA
0x180006153  cmp     qword ptr [rbx+18h], 8
0x180006158  jb      short loc_18000615F
0x18000615a  mov     rcx, [rbx]
0x18000615d  jmp     short loc_180006162
0x18000615f  mov     rcx, rbx; void *
0x180006162  sub     r14, rbp
0x180006165  lea     rdi, [r14+r14]
0x180006169  jz      short loc_180006177
0x18000616b  lea     rdx, [rcx+r8*2]; Src
0x18000616f  mov     r8, rdi; Size
0x180006172  call    memmove_0
0x180006177  cmp     qword ptr [rbx+18h], 8
0x18000617c  jb      short loc_180006183
0x18000617e  mov     rax, [rbx]
0x180006181  jmp     short loc_180006186
0x180006183  mov     rax, rbx
0x180006186  mov     [rbx+10h], r14
0x18000618a  mov     [rdi+rax], si
0x18000618e  jmp     short loc_1800061DA
0x180006190  mov     rdx, rdi
0x180006193  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180006198  xor     esi, esi
0x18000619a  test    al, al
0x18000619c  jz      short loc_1800061DA
0x18000619e  cmp     qword ptr [r14+18h], 8
0x1800061a3  jb      short loc_1800061A8
0x1800061a5  mov     r14, [r14]
0x1800061a8  cmp     qword ptr [rbx+18h], 8
0x1800061ad  jb      short loc_1800061B4
0x1800061af  mov     rcx, [rbx]
0x1800061b2  jmp     short loc_1800061B7
0x1800061b4  mov     rcx, rbx
0x1800061b7  lea     rdx, [r14+rbp*2]
0x1800061bb  mov     r8, rdi
0x1800061be  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x1800061c3  cmp     qword ptr [rbx+18h], 8
0x1800061c8  jb      short loc_1800061CF
0x1800061ca  mov     rax, [rbx]
0x1800061cd  jmp     short loc_1800061D2
0x1800061cf  mov     rax, rbx
0x1800061d2  mov     [rbx+10h], rdi
0x1800061d6  mov     [rax+rdi*2], si
0x1800061da  mov     rax, rbx
0x1800061dd  add     rsp, 20h
0x1800061e1  pop     r14
0x1800061e3  pop     rdi
0x1800061e4  pop     rsi
0x1800061e5  pop     rbp
0x1800061e6  pop     rbx
0x1800061e7  retn
```
