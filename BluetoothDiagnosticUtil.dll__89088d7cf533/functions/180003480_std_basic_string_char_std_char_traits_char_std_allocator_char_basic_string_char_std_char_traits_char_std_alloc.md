# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x180003480`
- end: `0x18000352e`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `174`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008480`
- `0x1800084c0`
- `0x180008510`

## callees

- `0x180003480`
- `0x180007f58`
- `0x1800081b8`
- `0x180009c46`

## pseudocode

```c
const void **__fastcall std::string::string(const void **a1, _BYTE *Src)
{
  unsigned __int64 v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rax

  a1[3] = (const void *)15;
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
    std::string::_Xlen();
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
    std::string::_Copy(a1, v4, 0);
  }
  if ( (unsigned __int64)a1[3] < 0x10 )
    v5 = a1;
  else
    v5 = (void *)*a1;
  memcpy_0(v5, Src, v4);
  if ( (unsigned __int64)a1[3] < 0x10 )
    v6 = a1;
  else
    v6 = *a1;
  a1[2] = (const void *)v4;
  *((_BYTE *)v6 + v4) = 0;
  return a1;
}

```

## disassembly

```asm
0x180003480  mov     [rsp+arg_0], rbx
0x180003485  mov     [rsp+arg_8], rsi
0x18000348a  push    rdi
0x18000348b  sub     rsp, 20h
0x18000348f  mov     qword ptr [rcx+18h], 0Fh
0x180003497  mov     rsi, rdx
0x18000349a  mov     qword ptr [rcx+10h], 0
0x1800034a2  mov     rbx, rcx
0x1800034a5  mov     byte ptr [rcx], 0
0x1800034a8  cmp     byte ptr [rdx], 0
0x1800034ab  jnz     short loc_1800034B1
0x1800034ad  xor     edi, edi
0x1800034af  jmp     short loc_1800034BE
0x1800034b1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800034b5  inc     rdi
0x1800034b8  cmp     byte ptr [rdx+rdi], 0
0x1800034bc  jnz     short loc_1800034B5
0x1800034be  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800034c2  ja      short loc_180003528
0x1800034c4  cmp     rdi, 0Fh
0x1800034c8  jbe     short loc_1800034E1
0x1800034ca  xor     r8d, r8d
0x1800034cd  mov     rdx, rdi
0x1800034d0  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800034d5  cmp     qword ptr [rbx+18h], 10h
0x1800034da  jb      short loc_1800034EF
0x1800034dc  mov     rcx, [rbx]
0x1800034df  jmp     short loc_1800034F2
0x1800034e1  test    rdi, rdi
0x1800034e4  jnz     short loc_1800034D5
0x1800034e6  mov     [rcx+10h], rdi
0x1800034ea  mov     [rcx], dil
0x1800034ed  jmp     short loc_180003514
0x1800034ef  mov     rcx, rbx; void *
0x1800034f2  mov     r8, rdi; Size
0x1800034f5  mov     rdx, rsi; Src
0x1800034f8  call    memcpy_0
0x1800034fd  cmp     qword ptr [rbx+18h], 10h
0x180003502  jb      short loc_180003509
0x180003504  mov     rax, [rbx]
0x180003507  jmp     short loc_18000350C
0x180003509  mov     rax, rbx
0x18000350c  mov     [rbx+10h], rdi
0x180003510  mov     byte ptr [rax+rdi], 0
0x180003514  mov     rsi, [rsp+28h+arg_8]
0x180003519  mov     rax, rbx
0x18000351c  mov     rbx, [rsp+28h+arg_0]
0x180003521  add     rsp, 20h
0x180003525  pop     rdi
0x180003526  retn
0x180003528  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
