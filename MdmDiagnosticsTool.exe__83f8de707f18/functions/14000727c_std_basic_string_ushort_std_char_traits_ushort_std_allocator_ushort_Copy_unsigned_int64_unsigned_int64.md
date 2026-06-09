# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000727c`
- end: `0x140007384`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140007494`

## callees

- `0x1400014e4`
- `0x140001688`
- `0x14000727c`
- `0x140007610`
- `0x140007db4`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rbx
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // r14
  _QWORD *v11; // rdx
  _QWORD *result; // rax
  _QWORD *v13; // rax
  unsigned __int64 v14; // rcx
  _BYTE *v15; // rdx
  _BYTE v16[72]; // [rsp+0h] [rbp-48h] BYREF
  _QWORD *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = a1[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v16;
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( v5[3] < 8u )
      v11 = v5;
    else
      v11 = (_QWORD *)*v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = v4;
  result = v5;
  if ( v4 >= 8 )
    result = v10;
  v5[2] = v3;
  *((_WORD *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x14000727c  mov     [rsp+arg_10], r8
0x140007281  mov     [rsp+arg_8], rdx
0x140007286  mov     [rsp+arg_0], rcx
0x14000728b  push    rbx
0x14000728c  push    rsi
0x14000728d  push    rdi
0x14000728e  push    r14
0x140007290  push    r15
0x140007292  sub     rsp, 20h
0x140007296  mov     r15, r8
0x140007299  mov     rbx, rdx
0x14000729c  mov     rdi, rcx
0x14000729f  or      rdx, 7
0x1400072a3  mov     r9, 7FFFFFFFFFFFFFFEh
0x1400072ad  cmp     rdx, r9
0x1400072b0  ja      short loc_1400072E6
0x1400072b2  mov     rbx, rdx
0x1400072b5  mov     r8, [rcx+18h]
0x1400072b9  mov     rcx, r8
0x1400072bc  shr     rcx, 1
0x1400072bf  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400072c9  mul     rdx
0x1400072cc  shr     rdx, 1
0x1400072cf  cmp     rcx, rdx
0x1400072d2  jbe     short loc_1400072E6
0x1400072d4  mov     rax, r9
0x1400072d7  sub     rax, rcx
0x1400072da  cmp     r8, rax
0x1400072dd  lea     rbx, [rcx+r8]
0x1400072e1  jbe     short loc_1400072E6
0x1400072e3  mov     rbx, r9
0x1400072e6  lea     rcx, [rbx+1]
0x1400072ea  xor     esi, esi
0x1400072ec  test    rcx, rcx
0x1400072ef  jz      short loc_140007315
0x1400072f1  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400072fb  cmp     rcx, rax
0x1400072fe  ja      short loc_140007310
0x140007300  add     rcx, rcx; Size
0x140007303  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007308  mov     r14, rax
0x14000730b  test    rax, rax
0x14000730e  jnz     short loc_140007318
0x140007310  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140007315  mov     r14, rsi
0x140007318  jmp     short loc_140007330
0x14000731a  xor     esi, esi
0x14000731c  mov     rdi, [rsp+48h+arg_0]
0x140007321  mov     r15, [rsp+48h+arg_10]
0x140007326  mov     rbx, [rsp+48h+arg_8]
0x14000732b  mov     r14, [rsp+48h+arg_18]
0x140007330  test    r15, r15
0x140007333  jz      short loc_14000734F
0x140007335  cmp     qword ptr [rdi+18h], 8
0x14000733a  jb      short loc_140007341
0x14000733c  mov     rdx, [rdi]
0x14000733f  jmp     short loc_140007344
0x140007341  mov     rdx, rdi
0x140007344  mov     r8, r15
0x140007347  mov     rcx, r14
0x14000734a  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x14000734f  xor     r8d, r8d
0x140007352  mov     dl, 1
0x140007354  mov     rcx, rdi
0x140007357  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000735c  mov     [rdi], r14
0x14000735f  mov     [rdi+18h], rbx
0x140007363  mov     rax, rdi
0x140007366  cmp     rbx, 8
0x14000736a  cmovnb  rax, r14
0x14000736e  mov     [rdi+10h], r15
0x140007372  mov     [rax+r15*2], si
0x140007377  add     rsp, 20h
0x14000737b  pop     r15
0x14000737d  pop     r14
0x14000737f  pop     rdi
0x140007380  pop     rsi
0x140007381  pop     rbx
0x140007382  retn
```
