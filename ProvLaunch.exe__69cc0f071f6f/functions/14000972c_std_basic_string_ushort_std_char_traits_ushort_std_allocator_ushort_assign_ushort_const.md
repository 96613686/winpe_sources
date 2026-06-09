# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x14000972c`
- end: `0x140009832`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `262`
- prototype: `void **__fastcall(void **, char *Src)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000693c`
- `0x140006e18`
- `0x140008a2c`
- `0x140008ce4`
- `0x140008f54`

## callees

- `0x140006550`
- `0x14000937c`
- `0x14000961c`
- `0x14000972c`
- `0x14000a326`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, char *Src)
{
  void **v3; // rbx
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rdx
  char *v6; // rax
  char *v7; // rax
  void *v8; // rcx
  _WORD *v9; // rcx
  _WORD *v10; // rcx

  v3 = a1;
  if ( *(_WORD *)Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&Src[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  v5 = (unsigned __int64)a1[3];
  if ( v5 < 8 )
    v6 = (char *)a1;
  else
    v6 = (char *)*a1;
  if ( Src >= v6 )
  {
    if ( v5 >= 8 )
      a1 = (void **)*a1;
    if ( (char *)a1 + 2 * (_QWORD)v3[2] > Src )
    {
      if ( v5 < 8 )
        v7 = (char *)v3;
      else
        v7 = (char *)*v3;
      return std::wstring::assign(v3, v3, (Src - v7) >> 1, v4);
    }
  }
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( v5 < v4 )
  {
    std::wstring::_Copy((const void **)v3, v4, (__int64)v3[2]);
    if ( !v4 )
      return v3;
    goto LABEL_19;
  }
  if ( v4 )
  {
LABEL_19:
    if ( (unsigned __int64)v3[3] < 8 )
      v8 = v3;
    else
      v8 = *v3;
    memcpy_0(v8, Src, 2 * v4);
    if ( (unsigned __int64)v3[3] < 8 )
      v10 = v3;
    else
      v10 = *v3;
    v3[2] = (void *)v4;
    v10[v4] = 0;
    return v3;
  }
  if ( v5 < 8 )
    v9 = v3;
  else
    v9 = *v3;
  v3[2] = 0;
  *v9 = 0;
  return v3;
}

```

## disassembly

```asm
0x14000972c  push    rbx
0x14000972e  push    rbp
0x14000972f  push    rsi
0x140009730  push    rdi
0x140009731  sub     rsp, 28h
0x140009735  xor     ebp, ebp
0x140009737  mov     rsi, rdx
0x14000973a  mov     rbx, rcx
0x14000973d  cmp     [rdx], bp
0x140009740  jnz     short loc_140009746
0x140009742  mov     edi, ebp
0x140009744  jmp     short loc_140009753
0x140009746  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000974a  inc     rdi
0x14000974d  cmp     [rdx+rdi*2], bp
0x140009751  jnz     short loc_14000974A
0x140009753  mov     rdx, [rcx+18h]
0x140009757  cmp     rdx, 8
0x14000975b  jb      short loc_140009762
0x14000975d  mov     rax, [rcx]
0x140009760  jmp     short loc_140009765
0x140009762  mov     rax, rbx
0x140009765  cmp     rsi, rax
0x140009768  jb      short loc_1400097AA
0x14000976a  cmp     rdx, 8
0x14000976e  jb      short loc_140009773
0x140009770  mov     rcx, [rcx]
0x140009773  mov     rax, [rbx+10h]
0x140009777  lea     rcx, [rcx+rax*2]
0x14000977b  cmp     rcx, rsi
0x14000977e  jbe     short loc_1400097AA
0x140009780  cmp     rdx, 8
0x140009784  jb      short loc_14000978B
0x140009786  mov     rax, [rbx]
0x140009789  jmp     short loc_14000978E
0x14000978b  mov     rax, rbx
0x14000978e  sub     rsi, rax
0x140009791  mov     r9, rdi
0x140009794  sar     rsi, 1
0x140009797  mov     rdx, rbx
0x14000979a  mov     r8, rsi
0x14000979d  mov     rcx, rbx; void *
0x1400097a0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400097a5  mov     rbx, rax
0x1400097a8  jmp     short loc_140009820
0x1400097aa  mov     rax, 7FFFFFFFFFFFFFFEh
0x1400097b4  cmp     rdi, rax
0x1400097b7  ja      short loc_14000982C
0x1400097b9  cmp     rdx, rdi
0x1400097bc  jnb     short loc_1400097DE
0x1400097be  mov     r8, [rbx+10h]
0x1400097c2  mov     rdx, rdi
0x1400097c5  mov     rcx, rbx; Src
0x1400097c8  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1400097cd  test    rdi, rdi
0x1400097d0  jz      short loc_140009820
0x1400097d2  cmp     qword ptr [rbx+18h], 8
0x1400097d7  jb      short loc_1400097FA
0x1400097d9  mov     rcx, [rbx]
0x1400097dc  jmp     short loc_1400097FD
0x1400097de  test    rdi, rdi
0x1400097e1  jnz     short loc_1400097D2
0x1400097e3  cmp     rdx, 8
0x1400097e7  jb      short loc_1400097EE
0x1400097e9  mov     rcx, [rbx]
0x1400097ec  jmp     short loc_1400097F1
0x1400097ee  mov     rcx, rbx
0x1400097f1  mov     [rbx+10h], rbp
0x1400097f5  mov     [rcx], bp
0x1400097f8  jmp     short loc_140009820
0x1400097fa  mov     rcx, rbx; void *
0x1400097fd  lea     r8, [rdi+rdi]; Size
0x140009801  mov     rdx, rsi; Src
0x140009804  call    memcpy_0
0x140009809  cmp     qword ptr [rbx+18h], 8
0x14000980e  jb      short loc_140009815
0x140009810  mov     rcx, [rbx]
0x140009813  jmp     short loc_140009818
0x140009815  mov     rcx, rbx
0x140009818  mov     [rbx+10h], rdi
0x14000981c  mov     [rcx+rdi*2], bp
0x140009820  mov     rax, rbx
0x140009823  add     rsp, 28h
0x140009827  pop     rdi
0x140009828  pop     rsi
0x140009829  pop     rbp
0x14000982a  pop     rbx
0x14000982b  retn
0x14000982c  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
