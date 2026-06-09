# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x1400031c8`
- end: `0x140003275`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `173`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140006720`
- `0x140006760`
- `0x1400067b0`

## callees

- `0x1400031c8`
- `0x140006278`
- `0x140006550`
- `0x14000a326`

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
0x1400031c8  mov     [rsp+arg_0], rbx
0x1400031cd  mov     [rsp+arg_8], rsi
0x1400031d2  push    rdi
0x1400031d3  sub     rsp, 20h
0x1400031d7  mov     qword ptr [rcx+18h], 0Fh
0x1400031df  mov     rsi, rdx
0x1400031e2  mov     qword ptr [rcx+10h], 0
0x1400031ea  mov     rbx, rcx
0x1400031ed  mov     byte ptr [rcx], 0
0x1400031f0  cmp     byte ptr [rdx], 0
0x1400031f3  jnz     short loc_1400031F9
0x1400031f5  xor     edi, edi
0x1400031f7  jmp     short loc_140003206
0x1400031f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400031fd  inc     rdi
0x140003200  cmp     byte ptr [rdx+rdi], 0
0x140003204  jnz     short loc_1400031FD
0x140003206  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x14000320a  ja      short loc_14000326F
0x14000320c  cmp     rdi, 0Fh
0x140003210  jbe     short loc_140003229
0x140003212  xor     r8d, r8d
0x140003215  mov     rdx, rdi
0x140003218  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x14000321d  cmp     qword ptr [rbx+18h], 10h
0x140003222  jb      short loc_140003237
0x140003224  mov     rcx, [rbx]
0x140003227  jmp     short loc_14000323A
0x140003229  test    rdi, rdi
0x14000322c  jnz     short loc_14000321D
0x14000322e  mov     [rcx+10h], rdi
0x140003232  mov     [rcx], dil
0x140003235  jmp     short loc_14000325C
0x140003237  mov     rcx, rbx; void *
0x14000323a  mov     r8, rdi; Size
0x14000323d  mov     rdx, rsi; Src
0x140003240  call    memcpy_0
0x140003245  cmp     qword ptr [rbx+18h], 10h
0x14000324a  jb      short loc_140003251
0x14000324c  mov     rax, [rbx]
0x14000324f  jmp     short loc_140003254
0x140003251  mov     rax, rbx
0x140003254  mov     [rbx+10h], rdi
0x140003258  mov     byte ptr [rax+rdi], 0
0x14000325c  mov     rsi, [rsp+28h+arg_8]
0x140003261  mov     rax, rbx
0x140003264  mov     rbx, [rsp+28h+arg_0]
0x140003269  add     rsp, 20h
0x14000326d  pop     rdi
0x14000326e  retn
0x14000326f  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
