# PNewSubFontByCopy

- ea: `0x18001107c`
- end: `0x1800111c8`
- name: `PNewSubFontByCopy`
- size: `332`
- prototype: `_BYTE *__fastcall(__int64, __int64, __int16, __int16, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f2e4`
- `0x18000f9d4`

## callees

- `0x18001036c`
- `0x180010ea8`
- `0x18001107c`
- `0x18001d208`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001116d`
- `KERNEL32!LocalFree` at `0x18001116d`
- `KERNEL32!LocalAlloc` at `0x1800110fd`
- `KERNEL32!LocalAlloc` at `0x1800110fd`

## pseudocode

```c
_BYTE *__fastcall PNewSubFontByCopy(__int64 a1, __int64 a2, __int16 a3, __int16 a4, __int64 a5)
{
  __int64 *v5; // rsi
  __int64 i; // rdi
  _WORD *j; // rbx
  _WORD *v11; // rax
  int v12; // r14d

  v5 = (__int64 *)(a2 + 200);
  if ( a3 )
  {
    for ( i = *v5; i && *(_WORD *)(i + 8) != a3; i = *(_QWORD *)i )
      ;
  }
  else
  {
    i = a2 + 200;
  }
  if ( i && *(_BYTE *)(i + 10) )
  {
    if ( a4 )
    {
      for ( j = (_WORD *)*v5; j && j[4] != a4; j = *(_WORD **)j )
        ;
    }
    else
    {
      j = (_WORD *)(a2 + 200);
    }
    if ( j )
    {
      v12 = 0;
    }
    else
    {
      v11 = LocalAlloc(0x40u, 0xA8u);
      j = v11;
      if ( !v11 )
        return PNewSubFont(a1, a2, a4, a5);
      v11[4] = a4;
      v12 = 1;
    }
    if ( *((_BYTE *)j + 10) )
      return j;
    *((_QWORD *)j + 19) = a2;
    CreateSubFontPSName(a1, a2, (__int64)j);
    if ( BCopyFont(a1, i, (__int64)j, *(_DWORD *)(a2 + 196)) )
    {
      if ( v12 )
      {
        *(_QWORD *)j = *v5;
        *v5 = (__int64)j;
      }
      return j;
    }
    if ( !a4 )
      *((_BYTE *)j + 10) = 0;
    if ( v12 )
      LocalFree(j);
    return PNewSubFont(a1, a2, a4, a5);
  }
  return PNewSubFont(a1, a2, a4, a5);
}

```

## disassembly

```asm
0x18001107c  push    rbx
0x18001107e  push    rbp
0x18001107f  push    rsi
0x180011080  push    rdi
0x180011081  push    r12
0x180011083  push    r13
0x180011085  push    r14
0x180011087  push    r15
0x180011089  sub     rsp, 28h
0x18001108d  xor     r13d, r13d
0x180011090  lea     rsi, [rdx+0C8h]
0x180011097  movzx   ebp, r9w
0x18001109b  mov     r15, rdx
0x18001109e  mov     r12, rcx
0x1800110a1  test    r8w, r8w
0x1800110a5  jnz     short loc_1800110AC
0x1800110a7  mov     rdi, rsi
0x1800110aa  jmp     short loc_1800110C0
0x1800110ac  mov     rdi, [rsi]
0x1800110af  jmp     short loc_1800110BB
0x1800110b1  cmp     [rdi+8], r8w
0x1800110b6  jz      short loc_1800110C0
0x1800110b8  mov     rdi, [rdi]
0x1800110bb  test    rdi, rdi
0x1800110be  jnz     short loc_1800110B1
0x1800110c0  test    rdi, rdi
0x1800110c3  jz      loc_1800111A5
0x1800110c9  cmp     [rdi+0Ah], r13b
0x1800110cd  jz      loc_1800111A5
0x1800110d3  test    bp, bp
0x1800110d6  jnz     short loc_1800110DD
0x1800110d8  mov     rbx, rsi
0x1800110db  jmp     short loc_1800110F0
0x1800110dd  mov     rbx, [rsi]
0x1800110e0  jmp     short loc_1800110EB
0x1800110e2  cmp     [rbx+8], bp
0x1800110e6  jz      short loc_1800110F0
0x1800110e8  mov     rbx, [rbx]
0x1800110eb  test    rbx, rbx
0x1800110ee  jnz     short loc_1800110E2
0x1800110f0  test    rbx, rbx
0x1800110f3  jnz     short loc_18001111D
0x1800110f5  mov     edx, 0A8h; uBytes
0x1800110fa  lea     ecx, [rbx+40h]; uFlags
0x1800110fd  call    cs:__imp_LocalAlloc
0x180011104  nop     dword ptr [rax+rax+00h]
0x180011109  mov     rbx, rax
0x18001110c  test    rax, rax
0x18001110f  jz      short loc_180011179
0x180011111  mov     [rax+8], bp
0x180011115  mov     r14d, 1
0x18001111b  jmp     short loc_180011120
0x18001111d  mov     r14d, r13d
0x180011120  cmp     [rbx+0Ah], r13b
0x180011124  jz      short loc_18001112E
0x180011126  mov     rax, rbx
0x180011129  jmp     loc_1800111B6
0x18001112e  mov     r8, rbx
0x180011131  mov     [rbx+98h], r15
0x180011138  mov     rdx, r15
0x18001113b  mov     rcx, r12
0x18001113e  call    CreateSubFontPSName
0x180011143  mov     r9d, [r15+0C4h]
0x18001114a  mov     r8, rbx
0x18001114d  mov     rdx, rdi
0x180011150  mov     rcx, r12
0x180011153  call    BCopyFont
0x180011158  test    eax, eax
0x18001115a  jnz     short loc_180011195
0x18001115c  test    bp, bp
0x18001115f  jnz     short loc_180011165
0x180011161  mov     [rbx+0Ah], r13b
0x180011165  test    r14d, r14d
0x180011168  jz      short loc_180011179
0x18001116a  mov     rcx, rbx; hMem
0x18001116d  call    cs:__imp_LocalFree
0x180011174  nop     dword ptr [rax+rax+00h]
0x180011179  mov     r9, [rsp+68h+arg_20]
0x180011181  movzx   r8d, bp
0x180011185  mov     rdx, r15
0x180011188  mov     rcx, r12
0x18001118b  call    PNewSubFont
0x180011190  mov     rbx, rax
0x180011193  jmp     short loc_180011126
0x180011195  test    r14d, r14d
0x180011198  jz      short loc_180011126
0x18001119a  mov     rax, [rsi]
0x18001119d  mov     [rbx], rax
0x1800111a0  mov     [rsi], rbx
0x1800111a3  jmp     short loc_180011126
0x1800111a5  mov     r9, [rsp+68h+arg_20]
0x1800111ad  movzx   r8d, bp
0x1800111b1  call    PNewSubFont
0x1800111b6  add     rsp, 28h
0x1800111ba  pop     r15
0x1800111bc  pop     r14
0x1800111be  pop     r13
0x1800111c0  pop     r12
0x1800111c2  pop     rdi
0x1800111c3  pop     rsi
0x1800111c4  pop     rbp
0x1800111c5  pop     rbx
0x1800111c6  retn
```
