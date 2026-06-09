# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006230`
- end: `0x140006338`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `264`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140006398`

## callees

- `0x140001ba8`
- `0x140006230`
- `0x140006480`
- `0x14000679c`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400062c4`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400062c4`

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
  _QWORD *v24; // [rsp+68h] [rbp+20h]

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
      goto LABEL_9;
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
LABEL_9:
      v10 = 0;
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
      v24 = v13;
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
    v10 = v24;
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
0x140006230  mov     [rsp+arg_10], r8
0x140006235  mov     [rsp+arg_8], rdx
0x14000623a  mov     [rsp+arg_0], rcx
0x14000623f  push    rbx
0x140006240  push    rsi
0x140006241  push    rdi
0x140006242  push    r14
0x140006244  push    r15
0x140006246  sub     rsp, 20h
0x14000624a  mov     r15, r8
0x14000624d  mov     rbx, rdx
0x140006250  mov     rdi, rcx
0x140006253  or      rdx, 7
0x140006257  mov     r9, 7FFFFFFFFFFFFFFEh
0x140006261  cmp     rdx, r9
0x140006264  ja      short loc_14000629A
0x140006266  mov     rbx, rdx
0x140006269  mov     r8, [rcx+18h]
0x14000626d  mov     rcx, r8
0x140006270  shr     rcx, 1
0x140006273  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000627d  mul     rdx
0x140006280  shr     rdx, 1
0x140006283  cmp     rcx, rdx
0x140006286  jbe     short loc_14000629A
0x140006288  mov     rax, r9
0x14000628b  sub     rax, rcx
0x14000628e  cmp     r8, rax
0x140006291  lea     rbx, [rcx+r8]
0x140006295  jbe     short loc_14000629A
0x140006297  mov     rbx, r9
0x14000629a  lea     rcx, [rbx+1]
0x14000629e  xor     esi, esi
0x1400062a0  test    rcx, rcx
0x1400062a3  jz      short loc_1400062CA
0x1400062a5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400062af  cmp     rcx, rax
0x1400062b2  ja      short loc_1400062C4
0x1400062b4  add     rcx, rcx; Size
0x1400062b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400062bc  mov     r14, rax
0x1400062bf  test    rax, rax
0x1400062c2  jnz     short loc_1400062CD
0x1400062c4  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1400062ca  mov     r14, rsi
0x1400062cd  jmp     short loc_1400062E5
0x1400062cf  xor     esi, esi
0x1400062d1  mov     rdi, [rsp+48h+arg_0]
0x1400062d6  mov     r15, [rsp+48h+arg_10]
0x1400062db  mov     rbx, [rsp+48h+arg_8]
0x1400062e0  mov     r14, [rsp+48h+arg_18]
0x1400062e5  test    r15, r15
0x1400062e8  jz      short loc_140006304
0x1400062ea  cmp     qword ptr [rdi+18h], 8
0x1400062ef  jb      short loc_1400062F6
0x1400062f1  mov     rdx, [rdi]
0x1400062f4  jmp     short loc_1400062F9
0x1400062f6  mov     rdx, rdi
0x1400062f9  mov     r8, r15
0x1400062fc  mov     rcx, r14
0x1400062ff  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140006304  xor     r8d, r8d
0x140006307  mov     dl, 1
0x140006309  mov     rcx, rdi
0x14000630c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140006311  mov     [rdi], r14
0x140006314  mov     [rdi+18h], rbx
0x140006318  mov     rax, rdi
0x14000631b  cmp     rbx, 8
0x14000631f  cmovnb  rax, r14
0x140006323  mov     [rdi+10h], r15
0x140006327  mov     [rax+r15*2], si
0x14000632c  add     rsp, 20h
0x140006330  pop     r15
0x140006332  pop     r14
0x140006334  pop     rdi
0x140006335  pop     rsi
0x140006336  pop     rbx
0x140006337  retn
```
