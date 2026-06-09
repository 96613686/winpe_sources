# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x18000310c`
- end: `0x1800031b9`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `173`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180006790`
- `0x1800067d0`
- `0x180006820`

## callees

- `0x18000310c`
- `0x18000645c`
- `0x1800065dc`
- `0x180010f36`

## pseudocode

```c
_QWORD *__fastcall std::string::string(_QWORD *a1, _BYTE *Src)
{
  size_t v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rax

  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  if ( *Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( Src[v4] );
  }
  else
  {
    v4 = 0;
  }
  if ( v4 == -1 )
    std::wstring::_Xlen();
  if ( v4 <= 0xF )
  {
    if ( !v4 )
    {
      a1[2] = 0;
      *(_BYTE *)a1 = 0;
      return a1;
    }
  }
  else
  {
    std::string::_Copy(a1);
  }
  if ( a1[3] < 0x10u )
    v5 = a1;
  else
    v5 = (void *)*a1;
  memcpy_0(v5, Src, v4);
  if ( a1[3] < 0x10u )
    v6 = a1;
  else
    v6 = (_QWORD *)*a1;
  a1[2] = v4;
  *((_BYTE *)v6 + v4) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000310c  mov     [rsp+arg_0], rbx
0x180003111  mov     [rsp+arg_8], rsi
0x180003116  push    rdi
0x180003117  sub     rsp, 20h
0x18000311b  mov     qword ptr [rcx+18h], 0Fh
0x180003123  mov     rsi, rdx
0x180003126  mov     qword ptr [rcx+10h], 0
0x18000312e  mov     rbx, rcx
0x180003131  mov     byte ptr [rcx], 0
0x180003134  cmp     byte ptr [rdx], 0
0x180003137  jnz     short loc_18000313D
0x180003139  xor     edi, edi
0x18000313b  jmp     short loc_18000314A
0x18000313d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003141  inc     rdi
0x180003144  cmp     byte ptr [rdx+rdi], 0
0x180003148  jnz     short loc_180003141
0x18000314a  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000314e  ja      short loc_1800031B3
0x180003150  cmp     rdi, 0Fh
0x180003154  jbe     short loc_18000316D
0x180003156  xor     r8d, r8d
0x180003159  mov     rdx, rdi
0x18000315c  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180003161  cmp     qword ptr [rbx+18h], 10h
0x180003166  jb      short loc_18000317B
0x180003168  mov     rcx, [rbx]
0x18000316b  jmp     short loc_18000317E
0x18000316d  test    rdi, rdi
0x180003170  jnz     short loc_180003161
0x180003172  mov     [rcx+10h], rdi
0x180003176  mov     [rcx], dil
0x180003179  jmp     short loc_1800031A0
0x18000317b  mov     rcx, rbx; void *
0x18000317e  mov     r8, rdi; Size
0x180003181  mov     rdx, rsi; Src
0x180003184  call    memcpy_0
0x180003189  cmp     qword ptr [rbx+18h], 10h
0x18000318e  jb      short loc_180003195
0x180003190  mov     rax, [rbx]
0x180003193  jmp     short loc_180003198
0x180003195  mov     rax, rbx
0x180003198  mov     [rbx+10h], rdi
0x18000319c  mov     byte ptr [rax+rdi], 0
0x1800031a0  mov     rsi, [rsp+28h+arg_8]
0x1800031a5  mov     rax, rbx
0x1800031a8  mov     rbx, [rsp+28h+arg_0]
0x1800031ad  add     rsp, 20h
0x1800031b1  pop     rdi
0x1800031b2  retn
0x1800031b3  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
